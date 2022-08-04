---
title: Adófunkció támogatása átmozgatási rendelésekhez
description: Ez a cikk bemutatja az áthozott rendelések adó funkciótámogatását az adószámítási szolgáltatással.
author: Kai-Cloud
ms.date: 10/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: b611abb2d68d93178d0c26ba40b22f1b8d26b191
ms.sourcegitcommit: 6d9fcb52d723ac5022a3002e0ced8e7b56e9bc2a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/27/2022
ms.locfileid: "9203109"
---
# <a name="tax-feature-support-for-transfer-orders"></a>Adófunkció támogatása átmozgatási rendelésekhez

[!include [banner](../../includes/banner.md)]

Ez a cikk az átrendelt rendelések adószámítással és feladási integrációjával kapcsolatban tartalmaz tájékoztatást. Ezzel a funkcióval áfaszámítást és könyvelést állíthat be a készletáthelyezések átmozgatási rendeléseiben. Az Európai Unió (EU) általános forgalmi adóval (ÁFA) kapcsolatos szabályozása szerint a készletátmozgatások közösségen belüli beszállításnak és közösségen belüli beszerzéseknek minősülnek.

A funkció konfigurálásához és használathoz három fő lépést kell elvégeznie:

1. **RCS beállítása:** A Regulatory Configuration Services szolgáltatásban állítsa be az adófunkciót, az adókódok és az adókódok alkalmazhatóságát az adókód meghatározására az átviteli rendelésekben.
2. **Dynamics 365 Pénzügy beállítása:** A **Pénzügyben** engedélyezze az Átszámítási rendelés adója szolgáltatást, állítsa be a készlet adószámítási szolgáltatási paramétereit, és állítsa be az alapvető adóparamétereket.
3. **Készletbeállítás:** Állítsa be az átviteli rendelési tranzakciók készletkonfigurációját.

## <a name="set-up-rcs-for-tax-and-transfer-order-transactions"></a>Az RCS beállítása adóhoz és az átmozgatási rendelési tranzakciókhoz

Az átmozgatási rendelésben érintett adó beállítását az alábbi lépésekkel állíthatja be. Az itt látható példában az átmozgatási rendelés Hollandiából Belgiumba irányul.

1. Az **Adófunkciók** oldalon a **Verziók** lapon jelölje ki a vázlat funkcióverziót, majd kattintson a **Szerkesztés** gombra.

2. Az **Adófunkciók beállítása** oldal **Adókódok** lapján válassza a **Hozzáadás** lehetőséget új adókódok létrehozásához. Ebben a példában három adókód jön létre: **NL-Exempt**, **BE-RC-21** és **BE-RC+21**.

    - Amikor egy átutalási megbízást egy hollandiai raktárból szállítanak, a holland áfamentes adókódot (**NL-exempt**) alkalmazzák.
      
        Hozza létre az **NL-Exempt** adókódot.
        1. Válassza a **Hozzáadás** lehetőséget, írja be az **NL-adómentes** értéket az **Adókód** mezőbe.
        2. Válassza a **Nettó összeg szerint** lehetőséget az **Adóösszetevő** mezőben.
        3. Válassza a **Mentés** lehetőséget.
        4. A **Díj** táblában válassza a **Hozzáadás** lehetőséget.
        5. Állíts be az **Adómentes** lehetőséget **Igen** értékre az **Általános** részben.
        6. A **Mentességi kód** mezőbe adja meg az **EC** értéket.

    - Amikor átmozgatási rendelés megérkezik egy belgiumi raktárba, a fordított adózás mechanizmusa a **BE-RC-21** és **BE-RC+21** adókódok használatával kerül alkalmazásra.
        
        Hozza létre a **BE-RC-21** adókódot.      
        1. Válassza a **Hozzáadás** lehetőséget, írja be a **BE-RC-21** értéket az **Adókód** mezőbe.
        2. Válassza a **Nettó összeg szerint** lehetőséget az **Adóösszetevő** mezőben.
        3. Válassza a **Mentés** lehetőséget.
        4. A **Díj** táblában válassza a **Hozzáadás** lehetőséget.
        5. Adja meg a **-21** értéket az **Adókulcs** mezőbe.
        6. Állítsa be a **Fordított áfás** lehetőséget **Igen** értékre az **Általános** részben.
        7. Válassza a **Mentés** lehetőséget.
        
        Hozza létre a **BE-RC+21** adókódot.
        1. Válassza a **Hozzáadás** lehetőséget, írja be a **BE-RC-21** értéket az **Adókód** mezőbe.
        2. Válassza a **Nettó összeg szerint** lehetőséget az **Adóösszetevő** mezőben.
        3. Válassza a **Mentés** lehetőséget.
        4. A **Díj** táblában válassza a **Hozzáadás** lehetőséget.
        5. Adja meg a **21** értéket az **Adókulcs** mezőbe.
        6. Válassza a **Mentés** lehetőséget.

3. Definiálja az adócsoportot.
    1. Válassza az **Oszlopok kezelése**, majd az **Adócsoport** sormezőt.
    2. Válassza a **->** lehetőséget, majd kattintson az **OK** gombra.
    3. Kattintson a **Hozzáadás** lehetőségre egy adócsoport hozzáadásához.
    4. Az **Adócsoport** oszlopban adja meg az **AR-EU** kódot, majd válassza ki az **NL-mentesség** adókódot.
    5. Kattintson a **Hozzáadás** lehetőségre egy adócsoport hozzáadásához.
    6. Az **Adócsoport** oszlopban adja meg az **RC-ÁFA** értéket, majd válassza ki a **BE-RC-21** és **BE-RC+21** adókódokat.
4. Definiálja a cikkáfacsoportot.
    1. Válassza az **Oszlopok kezelése**, majd az **Cikkáfacsoport** sormezőt.
    2. Válassza a **->** lehetőséget, majd kattintson az **OK** gombra.
    3. Kattintson a **Hozzáadás** lehetőségre egy cikkáfacsoport hozzáadásához.
    4. Adja meg a **TELJES** elemet a **Cikkáfacsoport** oszlopban. Válassza ki a **BE-RC-21**, **BE-RC+21** és **NL-Exempt** adókódokat.
5. Adja meg az adócsoportok alkalmazhatóságát.

    1. Válassza az **Oszlopok kezelése** lehetőséget, majd jelölje ki az alkalmazhatósági tábla létrehozásához használható oszlopokat.

        > [!NOTE]
        > Mindenképpen adja hozzá az **Üzleti folyamat** és az **Adóirányok** oszlopokat a táblához. Mindkét oszlop nélkülözhetetlen az átmozgatási rendelések adófunkciójához.

    2. Alkalmazhatósági szabályok hozzáadása. Ne hagyja üresen az **Adócsoport** mezőt.
        
        Adjon hozzá egy új szabályt az átmozgatási rendelés szállítmányához.
        1. A **Díj** táblában válassza az **Alkalmazhatósági szabályok** lehetőséget.
        2. Az **Üzleti folyamat** mezőben válassza a **Készlet** lehetőséget, hogy a szabály alkalmazható legyen az átmozgatási rendelésre.
        3. A **Szállítás országból/régióból** mezőbe írja be az **NLD** értéket.
        4. A **Szállítás országa/régiója** mezőbe írja be a **BEL** értéket.
        5. Az **Adó iránya** mezőben válassza a **Kimenet** lehetőséget, ha a szabályt az átmozgatási rendelés szállítmányára is alkalmazni kell.
        6. Az **Áfacsoport** mezőben válassza ki az **AR-EU** lehetőséget.
        
        Adjon hozzá egy másik szabályt az átmozgatási rendelés befogadásához.
        
        1. A **Díj** táblában válassza az **Alkalmazhatósági szabályok** lehetőséget.
        2. Az **Üzleti folyamat** mezőben válassza a **Készlet** lehetőséget, hogy a szabály alkalmazható legyen az átmozgatási rendelésre.
        3. A **Szállítás országból/régióból** mezőbe írja be az **NLD** értéket.
        4. A **Szállítás országa/régiója** mezőbe írja be a **BEL** értéket.
        5. Az **Adó iránya** mezőben válassza a **Bemenet** lehetőséget, ha a szabályt az átmozgatási rendelés fogadására is alkalmazni kell.
        6. Az **Áfacsoport** mezőben válassza ki az **RC-VAT** lehetőséget.

6. Adja meg a cikkáfacsoportok alkalmazhatóságát.

    1. Válassza az **Oszlopok kezelése** lehetőséget, majd jelölje ki az alkalmazhatósági tábla létrehozásához használható oszlopokat.
    2. Alkalmazhatósági szabályok hozzáadása.
        
       > [!NOTE]
       > Ha az adóköteles bizonylatsorokban alapértelmezett cikk áfacsoportja már helyes, akkor hagyja üresen ezt a mátrixot. 
        
        Adjon hozzá egy új szabályt az átmozgatási rendelés szállítmányához és nyugtájához.
        1. Az **Alkalmazhatósági szabályok** oldalon válassza a **Hozzáadás** lehetőséget.
        2. Az **Üzleti folyamat** mezőben válassza a **Készlet** lehetőséget, hogy a szabály alkalmazható legyen az átmozgatási rendelésre.
        3. A **Cikkáfacsoport** mezőben válassza ki az **FULL** lehetőséget.
7. Töltse ki és tegye közzé az új adófunkció-verziót.


## <a name="set-up-finance-for-transfer-order-transactions"></a>A Finance beállítása adóhoz és az átmozgatási rendelési tranzakciókhoz

Kövesse ezeket a lépseket az adók beállításához és engedélyezéséhez az értékesítési rendelésekhez.

1. A Finance-ben ugorjon **Munkaterületek** > **Funkciókezelés** lehetőségre.
2. A listában keresse meg és válassza az **Adó átmozgatási rendelésben** funkciót, majd az **Engedélyezés most** lehetőséget a bekapcsoláshoz.

    > [!IMPORTANT]
    > Az **Adó az átmozgatási rendelésben** funkció teljes mértékben függ az adószámítási szolgáltatástól. Ezért csak az adószámítási szolgáltatás telepítése után kapcsolható be.

    ![Adó az átmozgatási rendelés funkcióban.](../media/image7.png)

3. Engedélyezze az adószámítási szolgáltatást, és válassza ki a **Készlet** üzleti folyamatot.

    > [!IMPORTANT]
    > Ezt a lépést minden olyan jogi személynél el kell végeznie a Finance-ben, ahol az adószámítási szolgáltatást és az átmozgatási rendelések adófunkcióit elérhetővé szeretné tenni.

    1. Lépjen az **Adó** > **Beállítás** > **Adókonfiguráció** > **Adószámítási paraméterek** menüpontba.
    2. Az **Üzleti folyamat** mezőben válassza a **Készlet** lehetőséget.

4. Ellenőrizze, hogy a fordított áfa mechanizmus be van-e állítva. Válassza a **Főkönyv** \> **Beállítás** \> **Paraméterek** lapot, majd a **Fordított áfa** lapon ellenőrizze, hogy a **Fordított áfa engedélyezése** beállítás **Igen** értékű-e.

    ![Fordított áfa engedélyezése beállítás.](../media/image9.png)

5. Ellenőrizze, hogy a kapcsolódó adókódok, adócsoportok, cikkadócsoportok és áfaregisztrációs számok az adószámítási szolgáltatás útmutatónak megfelelően vannak-e beállítva a Finance-ben.
6. Ideiglenes tranzitszámla beállítása. Erre a lépésre csak akkor van szükség, ha az átutalási megbízásra alkalmazott adó nem alkalmazható adómentes vagy fordított adózású mechanizmusra.

    1. Ugrás az **Adó** > **Beállítás** > **Áfa** > **Főkönyvi feladási csoportok** elemre.
    2. Az **Ideigelens tranzit** mezőben jelöljön ki egy főkönyvi számlát.

       ![Ideiglenes tranzitszámla kiválasztása.](../media/image10.png)

## <a name="set-up-basic-inventory-for-transfer-order-transactions"></a>Alapleltár beállítása adóhoz és az átmozgatási rendelési tranzakciókhoz

Az alábbi lépésekkel állíthatja be az alapkészletet az átmozgatási rendelési tranzakciók engedélyezéséhez.

1. Hozzon létre szállítás kiindulási és szállítási célhelyeket a raktárakhoz különböző országokban vagy régiókban, és adja hozzá az egyes helyek elsődleges címét.

    1. Menjen a **Raktárkezelés** > **Beállítás** > **Raktár** > **Oldalak** pontra.
    2. Válassza az **Új** lehetőséget egy hely létrehozásához, amit később hozzárendelhet egy raktárhoz.
    3. Ismételje meg a 2. lépés minden más helyhez, amit létre kell hozna.

    > [!NOTE]
    > A létrehozott helyek egyikének **Tranzitnak** kell lennie. Az eljárás későbbi lépéseiben hozzárendeli ezt a helyet az árutovábbítási raktárhoz, hogy az adóval kapcsolatos készletutalványok feladásra kerülnek a "szállítási" és "fogadási" tranzakciókban az átadási rendelésekhez. A tranzithelyszín címe az adószámítás szempontjából irreleváns. Ezért akár üresen is hagyhatja.

    ![Helyszínek beállításai.](../media/image11.png)

2. Hozzon létre kiindulási, tranzit- és szállítási raktárakat. A raktárban megtartott címadatok felülírják a hely címét az adó kiszámítása során.

    1. Ugorjon a **Raktárkezelés** > **Beállítás** > **Raktár** > **Raktárak** pontra.
    2. Válassza az **Új** lehetőséget egy hely létrehozásához, és rendelje hozzá egy kapcsolódó helyhez.
    3. Ismételje meg a 2. lépést egy raktár létrehozásához mindegyik helyszínhez igény szerint.

       ![Raktárak beállítása.](../media/image12.png)

    > [!NOTE]
    > Feladó raktár esetén a tranzitraktárt a **Tranzit raktár** mezőben kell kiválasztani az átmozgatási rendelési tranzakciókhoz.
    >
    > ![Tranzitraktár kiválasztása.](../media/image13.png)

3. Ellenőrizze, hogy a készletfeladás konfigurációja be van-e állítva az átmozgatási rendelési tranzakciókhoz.

    1. Nyissa meg a **Készletkezelés** > **Beállítás** > **Feladás** > **Feladás** menüt.
    2. A **Készlet** lapon ellenőrizze, hogy a főkönyvi számla be van-e állítva mind a **Készletkiadás**, mind a **Készletbevételezés** feladásához.

        ![Készletkiadás és készletbevételezés feladásának beállítása.](../media/image14.png)

    3. Ellenőrizze, hogy a főkönyvi számla be van-e állítva a **Egységközi kötelezettségek** könyveléséhez.

        ![Egységközi kötelezettségek könyvelésének beállítása.](../media/image15.png)

    4. Ellenőrizze, hogy a főkönyvi számla be van-e állítva a **Egységközi követelések** könyveléséhez.

        ![Egységközi követelések könyvelésének beállítása.](../media/image16.png)
        
        
  [!INCLUDE[footer-include](../../../includes/footer-banner.md)]
