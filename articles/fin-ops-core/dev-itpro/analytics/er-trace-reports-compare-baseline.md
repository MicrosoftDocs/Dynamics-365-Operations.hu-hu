---
title: A létrehozott jelentés eredményeinek nyomon követése és összehasonlításuk a kiindulási értékekkel
description: Ez a cikk bemutatja, hogy hogyan hasonlíthatja össze a létrehozott elektronikus jelentési (ER) jelentések eredményeit a kiinduló jelentés értékeivel.
author: kfend
ms.date: 06/17/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.openlocfilehash: f37405b548a321735abdd73da5c7cf3f4b00ff01
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278766"
---
# <a name="trace-generated-report-results-and-compare-them-with-baseline-values"></a>A létrehozott jelentés eredményeinek nyomon követése és összehasonlításuk a kiindulási értékekkel

[!include[banner](../includes/banner.md)]

A kimenő elektronikus bizonylatokat létrehozó elektronikus jelentések (ER) formátumok eredményei nyomon követhetők. Nyomkövetés létrehozásának bekapcsolásakor (ER felhasználó paraméter: **Futtatás hibakeresési módban** használatával), új nyomon követés rekord jön létre az ER formátum végrehajtási naplóban, valahányszor egy ER jelentés fut. A következő adatok minden egyes létrehozott nyomkövetésben megtalálhatók:

- Ellenőrzési szabályok által generált összes figyelmeztetés
- Ellenőrzési szabályok által generált összes hiba
- Az összes létrehozott fájl, amely tárolva van mellékleteként a nyomkövetési bejegyzésnek

Egyéni kiindulási alkalmazásfájlok bármely ER formátumhoz tárolhatók. Fájlok kiindulási fájlnak számítanak, amikor leírják a várt eredményét a jelentéseknek, amelyek futnak. Ha kiindulási fájl érhető el egy ER formátumhoz, amely a nyomkövetés generálása bekapcsolva helyzetben van futtatva, a nyomkövetés a korábban említett részletek mellett tárolja a létrehozott elektronikus dokumentum és a kiindulási fájl összehasonlításának eredményét. Egy kattintással lekérheti a létrehozott elektronikus dokumentumot és a kiindulási fájlt egy tömörített fájlban. Részletes összehasonlítás egy külső eszköz segítségével végezhető el, például WinDiff.

A nyomkövetés elemezhetők annak az eldöntéséhez, hogy a generált elektronikus dokumentumok tartalmazzák-e a várt tartalmat. Megteheti, hogy ezt az értékelést a felhasználói elfogadás tesztelési (UAT) környezetben végzik el, az alapkód módosításakor (például amikor áttelepített egy új alkalmazáspéldányba, gyorsjavítás csomagokat telepített, vagy telepítette a kód módosításait). Ezzel a módszerrel biztosíthatja, hogy az értékelés nem befolyásolja a használt ER jelentések végrehajtását. Számos ER jelentésnél az értékelés felügyelet nélküli üzemmódban is megtehető.

Ezzel a funkcióval kapcsolatos további tudnivalókért játssza le: **ER Jelentések előállítása és eredmények összehasonlítása (1. rész)** és **ER Jelentések előállítása és eredmények összehasonlítása (2. rész)** útmutatókat, amelyek részei a következőnek: **7.5.4.3 Teszt informatikai szolgáltatások/megoldások (10679)** üzleti folyamat, valamint letölthetők innen: [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684). A feladatútmutatók elmagyarázza az ER keretrendszer konfigurálásának folyamatát, hogy kiindulási fájlok segítségével értékeljék ki az előállított elektronikus dokumentumokat.

## <a name="example-trace-generated-report-results-and-compare-them-with-baseline-values"></a>Példa: A létrehozott jelentés eredményeinek nyomon követése és összehasonlításuk a kiindulási értékekkel

Ez az eljárás azt mutatja be, hogyan lehet beállítani az ER-keretrendszert az ER-formátum végrehajtásával kapcsolatos információk gyűjtésére, majd a végrehajtási eredmények értékelésére. Az értékelés részeként a létrejövő dokumentumokat a program összehasonlítja a kiindulási fájljaival. Ebben a példában létrehozzuk a szükséges ER-konfigurációkat a Litware, Inc. mintavállalatra vonatkozóan. Ez az eljárás a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználók számára készült. Ezek a lépések bármely adathalmazzal végrehajthatók.

A példa lépéseinek végrehajtásához először el kell végeznie a jelen eljárás ([Konfigurációszolgáltatók létrehozása, és megjelölésük aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md)) lépéseit.

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. Győződjön meg róla, hogy a **Honosítási konfigurációk** lap **Konfigurációs szolgáltatók** szakaszában a Litware, Inc. Sample Company konfigurációs szolgáltatója szerepel a listán, és **Aktívként** van megjelölve. Ha nem látja a konfigurációszolgáltatót, végezze el a [Konfigurációszolgáltatók létrehozása, és megjelölésük aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárásban szereplő lépéseket.

### <a name="configure-document-management-parameters"></a>Dokumentumkezelés paraméterek konfigurálása

1. Nyissa meg a **Szervezeti felügyelet** \> **Dokumentumkezelés** \> **Dokumentumok típusait** pontot, és hozzon létre egy új dokumentumtípust, amely az alaptervek fájljait tárolja.
2. Az **Osztály** mezőben adja meg a **Fájl csatolása** elemet.
3. A **Csoport** mezőben adja meg a **Fájl** elemet.

![Dokumentumtípusok lapja.](media/GER-BaselineSample-SetupDocumentType.PNG "A dokumentumtípusok oldal képernyőképe")

> [!NOTE]
> Minden olyan adatkészlethez meg kell adni egy új dokumentumtípust, amelynél az ER alaptervi funkció használatát tervezi.

### <a name="configure-er-parameters-to-start-to-use-the-baseline-feature"></a>Az ER alaptervi funkció használatát elindító paraméterek konfigurálása

1. Az **Elektronikus jelentéskészítés** munkaterületen, a **Kapcsolódó hivatkozások** szakaszban, válassza az **Elektronikus jelentéskészítés paraméterei** elemet.

    ![Elektronikus jelentések munkaterülete.](media/GER-BaselineSample-ERWorkspace.PNG "Az elektronikus jelentéskészítés munkaterületének képernyőképe")

2. A **Mellékletek** lap **Alapterv** mezőjében adja meg vagy válassza ki az imént létrehozott dokumentumtípust.

    ![Az elektronikus jelentéskészítési paraméterek oldal mellékletek lapja.](media/GER-BaselineSample-ERParameters.PNG "Az elektronikus jelentéskészítési paraméterek képernyőképe")

3. Válassza a **Mentés** lehetőséget, majd zárja be az **Elektronikus jelentéskészítési paraméterek** lapot.

### <a name="add-a-new-er-model-configuration"></a>Új ER-modellkonfiguráció hozzáadása

1. Az **Elektronikus jelentéskészítés** munkaterületen, a **Konfigurációk** szakaszban, válassza ki a **Jelentéskészítési konfiguráció** csempét.
2. A Műveleti ablaktáblán kattintson a **Konfiguráció létrehozása** elemre.
3. Írjon be a legördülő párbeszédpanel **Név** mezőjébe ezt: **ER-kiindulások tanulásához használatos modell**.
4. Válassza a **Konfiguráció létrehozása** lehetőséget, hogy megerősítse egy új ER adatmodell-bejegyzés létrehozását.

![Konfigurációs párbeszédpanel létrehozása, új ER modellkonfiguráció hozzáadása.](media/GER-BaselineSample-ModelAdd.PNG "A konfiguráció létrehozása legördülő párbeszédpanel képernyőképe")

### <a name="design-a-data-model"></a>Adatmodell tervezése

1. A **Konfigurációk** lapon, a Művelet panelen, válassza a **Tervező** elemet.
2. Válassza az **Új** lehetőséget.
3. A legördülő párbeszédpanel **Név** mezőjébe írja be a **Gyökér** kifejezést.
4. Válassza a **Hozzáadás** lehetőséget.
5. Válassza a **Gyökérreferencia** elemet.
6. Válassza az **OK** parancsot, majd válassza a **Mentés** elemet.
7. Zárja be a **Modelltervező** lapot.
8. Válassza az **Állapot módosítása** lehetőséget.
9. Válassza a **Befejezés** parancsot, majd válassza az **OK** elemet.

![Konfigurációs oldal.](media/GER-BaselineSample-ModelComplete.PNG "A Konfigurációk oldal képernyőképe")

### <a name="add-a-new-er-format-configuration"></a>Új ER-formátum hozzáadása

1. A **Konfigurációk** lapon, a Művelet panelen, válassza a **Konfigurációk létrehozása** elemet.
2. A legördülő párbeszédpanel **Új** mezőcsoportjában válassza az **ER-kiindulások tanulásához használatos modell adatmodellen alapuló formátum** beállítást.
3. A **Név** mezőbe írja be: **ER-kiindulások tanulási formátuma**.
4. Válassza a **Konfiguráció létrehozása** lehetőséget, hogy megerősítse egy új ER formátumbejegyzés létrehozását.

![Konfigurációs párbeszédpanel létrehozása, új ER-formátumkonfiguráció hozzáadása.](media/GER-BaselineSample-FormatAdd.PNG "A konfiguráció létrehozása legördülő párbeszédpanel képernyőképe")

### <a name="design-a-format"></a>Formátum tervezése

Ebben a példában egyszerű ER-formátumot fog létrehozni az XML-dokumentumok létrehozásához.

1. A **Konfigurációk** lapon, a Művelet panelen, válassza a **Tervező** elemet.
2. Válassza a **Gyökér hozzáadása** elemet.
3. A legördülő párbeszédpanelen hajtsa végre a következő lépéseket:

    1. A fában válassza ki a **Common\\File** csomópontot.
    2. A **Név** mezőbe írja be a **Kimenet** szót.
    3. Válassza ki az **OK** lehetőséget.

4. Válassza a **Hozzáadás** lehetőséget.
5. A legördülő párbeszédpanelen hajtsa végre a következő lépéseket:

    1. A fában válassza ki az **XML\\Element** csomópontot.
    2. A **Név** mezőbe írja be a **Dokumentum** szót.
    3. Válassza ki az **OK** lehetőséget.

6. A fában válassza ki a **Output\\Document** csomópontot.
7. Válassza a **Hozzáadás** lehetőséget.
8. A legördülő párbeszédpanelen hajtsa végre a következő lépéseket:

    1. A fastruktúrában válassza ki az **XML\\Attribute** elemet.
    2. Adja meg a **Név** mezőben ezt: **ID**.
    3. Válassza ki az **OK** lehetőséget.

    ![Formátumtervező lap, a fastruktúrában kiválasztott XML-attribútum](media/GER-BaselineSample-FormatLayoutDesign.PNG "Képernyőkép – Formátumtervező oldala")

9. Válassza a **Hozzárendelés** lap **Törlés** elemét.
10. Válassza a **Gyökér hozzáadása** elemet.
11. Válassza ki a legördülő párbeszédpanel fastruktúrájában a **Általános\\Felhasználói bemeneti paraméterét**, majd kövesse az alábbi lépéseket:

    1. Adja meg a **Név** mezőben ezt: **ID**.
    2. A **Címke** mezőbe írja az **Azonosító megáda** értéket.
    3. Válassza ki az **OK** lehetőséget.

12. A fában válassza ki az **Output\\Document\\Id** csomópontot.
13. Válassza a **Kötés** parancsot, majd válassza a **Mentés** elemet.

![Formátumtervező lap, leképezési fül.](media/GER-BaselineSample-FormatMappingDesign.PNG "Képernyőkép – Formátumtervező oldala")

A tervezett szerkezet alapján a konfigurált formátum generál egy XML-fájlt. Ez az XML-fájl tartalmazza azt a **Gyökér** elemet, amely rendelkezik azzal az **Azonosító** attribútummal, amelynél a felhasználó által az ER futásidejű párbeszédpanelen megadott érték van megadva.

### <a name="generate-a-new-baseline-file-for-a-designed-er-format"></a>Új kiindulási fájl létrehozása egy tervezett ER formátumhoz

1. Válassza a **Konfigurációk** lap **Verziók** gyorslapján a **Futtatás** elemet.
2. Az **Azonosító megadása** mezőbe írja az **1** értéket.
3. Válassza ki az **OK** lehetőséget.

    ![Elektronikus jelentések paramétereinek párbeszédablaka.](media/GER-BaselineSample-FormatRunToMakeBaselineFile1.PNG "Az elektronikus jelentési paraméterek párbeszédablak képernyőképe")

4. Mentse a létrehozott **out.Admin.xml** fájl helyi másolatát, hogy később kiindulásként használhassa ehhez az ER-formátumhoz.

    ![Értesítés a Konfigurációk oldal létrejövő fájljáról.](media/GER-BaselineSample-FormatRunToMakeBaselineFile2.PNG "Képernyőkép – Értesítés a Konfigurációk oldal létrejövő fájljáról")

### <a name="configure-er-parameters-to-use-the-baseline-feature"></a>Az ER alaptervi funkció használatához paraméterek konfigurálása

1. A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, válassza a **Felhasználói paraméterek** lehetőséget.
2. A **Futtatás hibakeresési módban** beállítása legyen **Igen**.
3. Válassza ki az **OK** lehetőséget.

![A Felhasználói paraméterek párbeszédablak.](media/GER-BaselineSample-ERUserParameters.PNG "A felhasználói paraméterek párbeszédablak képernyőképe")

### <a name="add-a-new-baseline-for-designed-er-format"></a>Új alapterv hozzáadása a tervezett ER formátumhoz

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A Műveleti ablaktáblán válassza az **Alaptervek** elemet.

    ![Alaptervek gomb a Konfigurációk oldalon.](media/GER-BaselineSample-OpenBaselinePage.PNG "Képernyőkép – Alaptervek gomb a Konfigurációk oldalon")

3. A Műveleti ablaktáblán kattintson az **Új** elemre.
4. Válassza ki a korábban tervezett **ER-kiindulások tanulási formátuma** ER-formátumot.
5. Válassza a **Mentés** lehetőséget.

![Elektronikus jelentéskészítés formátumának alaptervei lap.](media/GER-BaselineSample-AddBaseline.PNG "Képernyőkép – az elektronikus jelentéskészítés formátumának alaptervei lap")

A program a hozzáadja az alaptervet az **ER-kiindulások tanulási formátuma** formátumhoz.

### <a name="configure-a-baseline-rule-for-the-added-baseline"></a>Konfiguráljon egy alaptervszabályt a hozzáadott kiinduláshoz.

1. Az **Elektronikus jelentési formátum alaptervei** lap műveleti paneljén válassza a **Mellékletek** gombot (a gemkapocs szimbólumát).
2. A Műveleti ablaktáblán válassza az **Új** \> **Fájl** elemet. Az ER paraméterei között előzőleg be kell jelölni a **Fájl** dokumentumtípust az alapfájlok tárolásához használt dokumentumtípusként.
3. Válassza a **Tallózás** lehetőséget, majd válassza ki az **out.Admin.xml** fájlt, amely a konfigurált ER formátum korábbi futtatásakor jött létre.

    ![Mellékletek oldala.](media/GER-BaselineSample-UploadBaselineFile.PNG "A Mellékletek oldal képernyőképe")

4. Zárja be a **Mellékletek** lapot.
5. Az **Alaptervek** gyorslapon válassza az **Új** értéket.
6. A **Név** mezőbe írja be: **1. alapterv**.
7. A **Fájlösszetevő neve** mezőbe írja be vagy válassza: **Kimenet**. Ez az érték azt jelzi, hogy a konfigurált alapterv össze lesz hasonlítva a **Kimenet** formátumelemmel létrejövő fájllal.
8. A **Fájlnév-maszk** mezőbe írja be a következőt: **\*.xml**.

    > [!NOTE]
    > A fájlnév-maszkot meg lehet határozni. Ha meg van adva a fájlnév-maszk, akkor a rendszer csak akkor fogja használni az alaptervrekordot a létrejött kimenet értékelésére, ha a létrejövő kimeneti fájl neve kielégíti a maszkot.

9. Ha a konfigurált alaptervet csak akkor kell használni, ha az **ER-kiindulások tanulási formátuma** formátumot adott vállalatokba bejelentkezett felhasználók futtatják, válassza ki ezeket a vállalatokat a **Vállalatok** mezőben.
10. Az **Alapterv** mezőbe írja be vagy válassza ki az **out.Admin** mellékletet.
11. Válassza a **Mentés** lehetőséget.

![Az elektronikus jelentéskészítés formátumának alaptervei oldal, alaptervek gyorslap, alapterv kiválasztva.](media/GER-BaselineSample-SetupBaselineLine.PNG "Képernyőkép – az elektronikus jelentéskészítés formátumának alaptervei lap")

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a>A tervezett ER formátum futtatása és a napló áttekintése az eredmények elemzéséhez

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A fában bontsa **ER-kiindulások tanulásához használatos modell** elemet, majd válassza ki a **ER-kiindulások tanulásához használatos modell\\ER-kiindulások tanulási formátuma** elemet.
3. A **Verziók** gyorslapon kattintson a **Futtatás** lehetőségre.
4. Az **Azonosító megadása** mezőbe írja az **1** értéket.
5. Válassza ki az **OK** lehetőséget.
6. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk hibakeresési naplói**.

    ![Az elektronikus jelentéskészítés futtatási naplója megegyező alapértékekkel.](media/GER-BaselineSample-ReviewBaselineComparison1.PNG "Az elektronikus jelentéskészítési futtatási naplók oldal képernyőképe")

    > [!NOTE]
    > A végrehajtási napló a megadott alapterv és a létrejövő fájl összehasonlításának eredményeiről tartalmaz információkat. Ebben a példában a napló azt jelzi, hogy a létrejövő fájl és az alapterv egyenlő.

7. Válassza a **Minden törlése** lehetőséget.

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a>A tervezett ER formátum futtatása és a napló áttekintése az eredmények elemzéséhez

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A fában bontsa **ER-kiindulások tanulásához használatos modell** elemet, majd válassza ki a **ER-kiindulások tanulásához használatos modell\\ER-kiindulások tanulási formátuma** elemet.
3. A **Verziók** gyorslapon kattintson a **Futtatás** lehetőségre.
4. Az **Azonosító megadása** mezőbe írja az **2** értéket.
5. Válassza ki az **OK** lehetőséget.
6. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk hibakeresési naplói**.

    ![Az elektronikus jelentéskészítés futtatási naplója eltérő alapértékekkel.](media/GER-BaselineSample-ReviewBaselineComparison2.PNG "Az elektronikus jelentéskészítési futtatási naplók oldal képernyőképe")

    > [!NOTE]
    > A végrehajtási napló a megadott alapterv és a létrejövő fájl összehasonlításának eredményeiről tartalmaz információkat. Ebben a példában a napló azt jelzi, hogy a létrejövő fájl és az alapterv eltér.

7. Válassza az **Összehasonlítás** lehetőséget.

> [!NOTE]
> A létrejövő fájl és az eredeti fájl zip-fájlként van felkínálva. A fájlok összehasonlításához és a különbségek áttekintéséhez külső összehasonlítási eszközök használhatók, például a WinDiff.

## <a name="additional-resources"></a>További erőforrások

- [Az elektronikus jelentéskészítési (ER) keretrendszer konfigurálása](electronic-reporting-er-configure-parameters.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
