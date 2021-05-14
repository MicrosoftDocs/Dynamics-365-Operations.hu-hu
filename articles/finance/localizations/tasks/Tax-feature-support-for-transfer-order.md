---
title: Adófunkció támogatása átmozgatási rendelésekhez
description: Ez a témakör ismerteti az átutalási rendelések új adózási szolgáltatásának támogatását az adószámítási szolgáltatás használatával.
author: kailiang
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d1b99046b0e439c9dadbb240050e270a7b2a6914
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920955"
---
# <a name="tax-feature-support-for-transfer-orders"></a>Adófunkció támogatása átmozgatási rendelésekhez

[!include [banner](../../includes/banner.md)]

Ez a témakör az adószámításról és az átmozgatási rendelések integrációjának feladásáról nyújt tájékoztatást. Ezzel a funkcióval áfaszámítást és könyvelést állíthat be a készletáthelyezések átmozgatási rendeléseiben. Az Európai Unió (EU) általános forgalmi adóval (ÁFA) kapcsolatos szabályozása szerint a készletátmozgatások közösségen belüli beszállításnak és közösségen belüli beszerzéseknek minősülnek.

A funkció konfigurálásához és használathoz három fő lépést kell elvégeznie:

1. **RCS beállítása:** A Regulatory Configuration Services szolgáltatásban állítsa be az adófunkciót, az adókódok és az adókódok alkalmazhatóságát az adókód meghatározására az átviteli rendelésekben.
2. **Finance beállítása:** A Microsoft Dynamics 365 Finance alkalmazásban kapcsolja be az **Adó az átmozgatási rendelésben** szolgáltatást, állítsa be a készlet adószolgáltatásának paramétereit, és állítsa be az alapvető adóparamétereket.
3. **Készletbeállítás:** Állítsa be az átviteli rendelési tranzakciók készletkonfigurációját.

## <a name="set-up-rcs-for-tax-and-transfer-order-transactions"></a>Az RCS beállítása adóhoz és az átmozgatási rendelési tranzakciókhoz

Az átmozgatási rendelésben érintett adó beállítását az alábbi lépésekkel állíthatja be. Az itt látható példában az átmozgatási rendelés Hollandiából Belgiumba irányul.

1. Az **Adófunkciók** oldalon a **Verziók** lapon jelölje ki a vázlat funkcióverziót, majd kattintson a **Szerkesztés** gombra.

    ![Szerkesztés kiválasztása](../media/image1.png)

2. Az **Adófunkciók beállítása** oldal **Adókódok** lapján válassza a **Hozzáadás** lehetőséget új adókódok létrehozásához. Ebben a példában három adókód jön létre: **NL-Exempt**, **BE-RC-21** és **BE-RC+21**.

    - Amikor egy átutalási megbízást egy hollandiai raktárból szállítanak, a holland áfamentes adókódot (**NL-exempt**) alkalmazzák.
      
        Hozza létre az **NL-Exempt** adókódot.
        1. Válassza a **Hozzáadás** lehetőséget, írja be az **NL-adómentes** értéket az **Adókód** mezőbe.
        2. Válassza a **Nettó összeg szerint** lehetőséget az **Adóösszetevő** mezőben.
        3. Válassza a **Mentés** lehetőséget.
        4. A **Díj** táblában válassza a **Hozzáadás** lehetőséget.
        5. Kapcsolja az **Adómentes** lehetőséget **Igen** értékre az **Általános** részben.

        ![NL adómentes adókód](../media/image2.png)

    - Amikor átmozgatási rendelés megérkezik egy belgiumi raktárba, a fordított adózás mechanizmusa a **BE-RC-21** és **BE-RC+21** adókódok használatával kerül alkalmazásra.
        
        Hozza létre a **BE-RC-21** adókódot.      
        1. Válassza a **Hozzáadás** lehetőséget, írja be a **BE-RC-21** értéket az **Adókód** mezőbe.
        2. Válassza a **Nettó összeg szerint** lehetőséget az **Adóösszetevő** mezőben.
        3. Válassza a **Mentés** lehetőséget.
        4. A **Díj** táblában válassza a **Hozzáadás** lehetőséget.
        5. Adja meg a **-21** értéket az **Adókulcs** mezőbe.
        6. Kapcsolja a **Fordított áfás** lehetőséget **Igen** értékre az **Általános** részben.
        7. Válassza a **Mentés** lehetőséget.

        ![BE-RC-21 adókód a fordított áfához](../media/image3.png)
        
        Hozza létre a **BE-RC+21** adókódot.
        1. Válassza a **Hozzáadás** lehetőséget, írja be a **BE-RC-21** értéket az **Adókód** mezőbe.
        2. Válassza a **Nettó összeg szerint** lehetőséget az **Adóösszetevő** mezőben.
        3. Válassza a **Mentés** lehetőséget.
        4. A **Díj** táblában válassza a **Hozzáadás** lehetőséget.
        5. Adja meg a **21** értéket az **Adókulcs** mezőbe.
        6. Válassza a **Mentés** lehetőséget.

        ![BE-RC+21 adókód a fordított áfához](../media/image4.png)

3. Adja meg az adókódok alkalmazhatóságát.

    1. Válassza az **Oszlopok kezelése** lehetőséget, majd jelölje ki az alkalmazhatósági tábla létrehozásához használható oszlopokat.

        > [!NOTE]
        > Mindenképpen adja hozzá az **Üzleti folyamat** és az **Adóirányok** oszlopokat a táblához. Mindkét oszlop nélkülözhetetlen az átmozgatási rendelések adófunkciójához.

    2. Alkalmazhatósági szabályok hozzáadása. Ne hagyja üresen az **Adókódok**, **Adócsoport** és **Cikkáfacsoport** mezőket.
        
        Adjon hozzá egy új szabályt az átmozgatási rendelés szállítmányához.
        1. A **Díj** táblában válassza az **Alkalmazhatósági szabályok** lehetőséget.
        2. Az **Üzleti folyamat** mezőben válassza a **Készlet** lehetőséget, hogy a szabály alkalmazható legyen az átmozgatási rendelésre.
        3. A **Szállítás országból/régióból** mezőbe írja be az **NLD** értéket.
        4. A **Szállítás országa/régiója** mezőbe írja be a **BEL** értéket.
        5. Az **Adó iránya** mezőben válassza a **Kimenet** lehetőséget, ha a szabályt az átmozgatási rendelés szállítmányára is alkalmazni kell.
        6. Az **Adókódok** mezőben válassza ki az **NL-Exempt** értéket.
        7. Az **Adócsoport** mezőben és a **Cikkáfa csoportban** adja meg a Finance rendszerben definiált kapcsolódó áfacsoportot és cikkáfacsoportot.
        
        Adjon hozzá egy másik szabályt az átmozgatási rendelés befogadásához.
        1. A **Díj** táblában válassza az **Alkalmazhatósági szabályok** lehetőséget.
        2. Az **Üzleti folyamat** mezőben válassza a **Készlet** lehetőséget, hogy a szabály alkalmazható legyen az átmozgatási rendelésre.
        3. A **Szállítás országból/régióból** mezőbe írja be az **NLD** értéket.
        4. A **Szállítás országa/régiója** mezőbe írja be a **BEL** értéket.
        5. Az **Adó iránya** mezőben válassza a **Bemenet** lehetőséget, ha a szabályt az átmozgatási rendelés fogadására is alkalmazni kell.
        6. Az **Adókódok** mezőben válassza a **BE-RC+21** és a **BE-RC-21** lehetőséget.
        7. Az **Adócsoport** mezőben és a **Cikkáfa csoportban** adja meg a Finance rendszerben definiált kapcsolódó áfacsoportot és cikkáfacsoportot.

        ![Alkalmazhatósági szabályok](../media/image5.png)

4. Töltse ki és tegye közzé az új adófunkció-verziót.

    [![Az új verzió állapotának módosítása](../media/image6.png)](../media/image6.png)

## <a name="set-up-finance-for-transfer-order-transactions"></a>A Finance beállítása adóhoz és az átmozgatási rendelési tranzakciókhoz

Kövesse ezeket a lépseket az adók beállításához és engedélyezéséhez az értékesítési rendelésekhez.

1. A Finance-ben ugorjon **Munkaterületek** \> **Funkciókezelés** lehetőségre.
2. A listában keresse meg és válassza az **Adó átmozgatási rendelésben** funkciót, majd az **Engedélyezés most** lehetőséget a bekapcsoláshoz.

    > [!IMPORTANT]
    > Az **Adó az átmozgatási rendelésben** funkció teljes mértékben függ az adószolgáltatástól. Ezért csak az adó szolgáltatás telepítése után kapcsolható be.

    ![Adó az átmozgatási rendelés funkcióban](../media/image7.png)

3. Engedélyezze az adószolgáltatást, és válassza ki a **Készlet** üzleti folyamatot.

    > [!IMPORTANT]
    > Ezt a lépést minden olyan jogi személynél el kell végeznie a Finance-ben, ahol az adószolgáltatást és az átmozgatási rendelések adófunkcióit elérhetővé szeretné tenni.

    1. Ugrás az **Adó** \> **Beállítás** \> **Adókonfiguráció** \> **Adószolgáltatás beállítása** lapra.
    2. Az **Üzleti folyamat** mezőben válassza a **Készlet** lehetőséget.

    ![Az Üzleti folyamat mező beállítása](../media/image8.png)

4. Ellenőrizze, hogy a fordított áfa mechanizmus be van-e állítva. Válassza a **Főkönyv** \> **Beállítás** \> **Paraméterek** lapot, majd a **Fordított áfa** lapon ellenőrizze, hogy a **Fordított áfa engedélyezése** beállítás **Igen** értékű-e.

    ![Fordított áfa engedélyezése beállítás](../media/image9.png)

5. Ellenőrizze, hogy a kapcsolódó adókódok, adócsoportok, cikkadócsoportok és áfaregisztrációs számok az adószolgáltatási útmutatónak megfelelően vannak-e beállítva a Finance-ben.
6. Ideiglenes tranzitszámla beállítása. Erre a lépésre csak akkor van szükség, ha az átutalási megbízásra alkalmazott adó nem alkalmazható adómentes vagy fordított adózású mechanizmusra.

    1. Lépjen az **Adó** \> **Beállítás** \> **Áfa** \> **Főkönyvi feladási csoportok** elemre.
    2. Az **Ideigelens tranzit** mezőben jelöljön ki egy főkönyvi számlát.

    ![Ideiglenes tranzitszámla kiválasztása](../media/image10.png)

## <a name="set-up-basic-inventory-for-transfer-order-transactions"></a>Alapleltár beállítása adóhoz és az átmozgatási rendelési tranzakciókhoz

Az alábbi lépésekkel állíthatja be az alapkészletet az átmozgatási rendelési tranzakciók engedélyezéséhez.

1. Hozzon létre szállítás kiindulási és szállítási célhelyeket a raktárakhoz különböző országokban vagy régiókban, és adja hozzá az egyes helyek elsődleges címét.

    1. Ugorjon a **Raktárkezelés** \> **Beállítás** \> **Raktár** \> **Helyek** elemre.
    2. Válassza az **Új** lehetőséget egy hely létrehozásához, amit később hozzárendelhet egy raktárhoz.
    3. Ismételje meg a 2. lépés minden más helyhez, amit létre kell hozna.

    > [!NOTE]
    > A létrehozott helyek egyikének **Tranzitnak** kell lennie. Az eljárás későbbi lépéseiben hozzárendeli ezt a helyet az árutovábbítási raktárhoz, hogy az adóval kapcsolatos készletutalványok feladásra kerülnek a "szállítási" és "fogadási" tranzakciókban az átadási rendelésekhez. A tranzithelyszín címe az adószámítás szempontjából irreleváns. Ezért akár üresen is hagyhatja.

    ![Helyszínek beállításai](../media/image11.png)

2. Hozzon létre kiindulási, tranzit- és szállítási raktárakat. A raktárban megtartott címadatok felülírják a hely címét az adó kiszámítása során.

    1. Ugorjon a **Raktárkezelés** \> **Beállítás** \> **Raktár** \> **Raktárak** pontra.
    2. Válassza az **Új** lehetőséget egy hely létrehozásához, és rendelje hozzá egy kapcsolódó helyhez.
    3. Ismételje meg a 2. lépést egy raktár létrehozásához mindegyik helyszínhez igény szerint.

    ![Raktárak beállítása](../media/image12.png)

    > [!NOTE]
    > Feladó raktár esetén a tranzitraktárt a **Tranzit raktár** mezőben kell kiválasztani az átmozgatási rendelési tranzakciókhoz.
    >
    > ![Tranzitraktár kiválasztása](../media/image13.png)

3. Ellenőrizze, hogy a készletfeladás konfigurációja be van-e állítva az átmozgatási rendelési tranzakciókhoz.

    1. Nyissa meg a **Készletkezelés** \> **Beállítás** \> **Feladás** \> **Feladás** menüt.
    2. A **Készlet** lapon ellenőrizze, hogy a főkönyvi számla be van-e állítva mind a **Készletkiadás**, mind a **Készletbevételezés** feladásához.

        ![Készletkiadás és készletbevételezés feladásának beállítása](../media/image14.png)

    3. Ellenőrizze, hogy a főkönyvi számla be van-e állítva a **Egységközi kötelezettségek** könyveléséhez.

        ![Egységközi kötelezettségek könyvelésének beállítása](../media/image15.png)

    4. Ellenőrizze, hogy a főkönyvi számla be van-e állítva a **Egységközi követelések** könyveléséhez.

        ![Egységközi követelések könyvelésének beállítása](../media/image16.png)
