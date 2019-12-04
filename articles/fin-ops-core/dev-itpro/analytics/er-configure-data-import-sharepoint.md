---
title: Adatok importálásának konfigurálása a SharePoint-rendszerből
description: Ez a témakör ismerteti az adatok importálásának módját a Microsoft SharePoint rendszerből.
author: NickSelin
manager: AnnBe
ms.date: 11/29/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: c11123c0d53fcf4ba67e83fe64d2d6e692d5b6f1
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771352"
---
# <a name="configure-data-import-from-sharepoint"></a>Adatok importálásának konfigurálása a SharePoint-rendszerből

[!include[banner](../includes/banner.md)]

Ahhoz, hogy bejövő fájlból adatokat importálhasson az Elektronikus jelentéskészítési keretrendszer segítségével, konfigurálnia kell egy elektronikus jelentéskészítési formátumot, amely támogatja az importálást, majd futtatnia kell a **Célhoz** típus modell-leképezését, amely adatforrásként használja az adott formátumot. Az adatok importálásához meg kell keresnie az importálni kívánt fájlt. A bejövő fájlt a felhasználó manuálisan is kiválaszthatja. Az új elektronikus jelentéskészítési lehetőséggel, amely támogatja az adatok importálását a Microsoft SharePoint rendszerből, ez a folyamat felügyelet nélkül is konfigurálható. Az elektronikus jelentéskészítés konfigurációk segítségével végrehajthatja az adatok importálását a Microsoft SharePoint mappáiban tárolt fájlokból. Ez a témakör bemutatja, hogyan lehet végrehajtani az importálást a SharePoint megoldásból. A példákban a szállítói tranzakciók üzleti adatokként szerepelnek.

## <a name="prerequisites"></a>Előfeltételek
A jelen témakörben szereplő példák elvégzéséhez a következő hozzáférésekkel kell rendelkeznie:

- Hozzáférés a következő szerepkörök egyikéhez:

    - Elektronikus jelentések fejlesztője
    - Elektronikus jelentések funkcióival foglalkozó konzulens
    - Rendszergazda

- Hozzáférés a Microsoft SharePoint -kiszolgáló példányához, amelyet az alkalmazással való használatra konfiguráltak.
- Elektronikus jelentéskészítési formátum és modellkonfigurációk 1099-es kifizetésekhez.

### <a name="create-required-er-configurations"></a>Szükséges elektronikus jelentéskészítés-konfigurációk létrehozása
Játssza le az **Elektronikus jelentéskészítés – adatok importálása Microsoft Excel-fájlból** feladat-útmutatókat, amelyek a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat részei. Ezek a feladat-útmutatók végigvezetik a szállítói tranzakciók Microsoft Excel-fájlokból történő interaktív importálásához szükséges elektronikus jelentéskészítés-konfigurációk tervezésének és felhasználásának folyamatán. További tudnivalókért lásd: [Bejövő dokumentumok elemzése Excel formátumban](parse-incoming-documents-excel.md). Miután elvégezte a feladatútmutatókat, akkor a következő be vannak állítva.

#### <a name="er-configurations"></a>Elektronikus jelentéskészítés-konfigurációk

- Elektronikus jelentéskészítés modellkonfiguráció, **1099-es kifizetések modell**
- Elektronikus jelentéskészítés formátumkonfiguráció, **Formátum a szállítói tranzakciók importálához Excelből**

![Elektronikus jelentéskészítés-konfigurációk adatok importálásához a SharePoint-rendszerből](./media/GERImportFromSharePoint-01-Configurations.PNG)

#### <a name="sample-of-the-incoming-file-for-data-import"></a>Minta bejövő fájlról adatimportáláshoz

- Excel-fájl **1099import-data.xlsx**, szállítói tranzakciókkal, amelyeket importálni kell az alkalmazásba.

![Minta Microsoft Excel-fájl a SharePoint rendszerből való importáláshoz](./media/GERImportFromSharePoint-02-Excel.PNG)
    
> [!NOTE]
> A szállítói tranzakciók importálásához szükséges formátum alapértelmezett modell-leképezésként van megadva. Következésképpen, ha futtatja az **1099-es kifizetésekhez modell** modell-leképezését, és a modell-leképezés **Célhoz** típusú, akkor a modell-leképezés ezt a formátumot futtatja a külső fájlokból történő adatimportáláshoz. Ezután az adatokat felhasználja az alkalmazástáblák frissítéséhez.

## <a name="configure-access-to-sharepoint-for-file-storage"></a>A SharePoint-hozzáférés konfigurálása a fájlok tárolásához
Elektronikus jelentésfájlok tárolásához a SharePoint-helyen, konfigurálnia kell a SharePoint Server-példányt, amelyet az aktuális vállalat használ. Ebben a példában a vállalat a USMF. További tudnivalókért lásd: [SharePoint-tárhely konfigurálása](../../fin-ops/organization-administration/configure-document-management.md#configure-sharepoint-storage).

1. Hajtsa végre a [SharePoint-tárhely konfigurálása](../../fin-ops/organization-administration/configure-document-management.md#configure-sharepoint-storage) lépéseit.
2. Nyissa meg a konfigurált SharePoint-webhelyet.
3. Hozza létre a következő, a bejövő elektronikus jelentési fájlokat tárolására szolgáló mappákat:

     - Fájlok importálási forrása (fő) (Példa az alábbi képernyőképen látható)
     - Fájlok importálásának forrása (másodlagos)

    ![Fájlok importálásának forrása (fő)](./media/GERImportFromSharePoint-04-SharePointFolder1.png)

4. (Opcionális) Hozza létre a következő, a az importált elektronikus jelentési fájlok tárolására szolgáló mappákat: 

    - Fájlarchívum mappa – Ebben a mappába kerülnek a sikeresen importált fájlok.
    - Figyelmeztetéssel rendelkező fájlok mappaája – Ebbe a mappába kerülnek azok a fájlok, amelye figyelmeztetéssel lettek importálva.
    - Fájlhibák mappa – Ebben a mappába kerülnek a sikertelenül importált fájlok.

4. Lépjen a **Szervezeti adminisztráció > Dokumentumkezelés > Dokumentumtípusok** lehetőségre.
5. Hozza létre a következő dokumentumtípusokat, amelyek az újonnan létrehozott SharePoint mappák eléréséhez lesznek használva. További tudnivalókért lásd: [Dokumentumtípusok konfigurálása](../../fin-ops/organization-administration/configure-document-management.md#configure-document-types).

|Dokumentumtípus        | Csoport              | Tárolóhely      | SharePoint-mappa      |
|--------------------|--------------------|---------------|------------------------|
|SP fő             |Fájl                |SharePoint     |Fájlok importálásának forrása (fő)|
|SP másodlagos             |Fájl                |SharePoint     |Fájlok importálásának forrása (másodlagos)|
|SP-archívum             |Fájl                |SharePoint     |Fájlarchívum mappa|
|SP-figyelmeztetés             |Fájl                |SharePoint     |Fájlfigyelmeztetések mappája|
|SP-hiba             |Fájl                |SharePoint     |Fájlhibák mappája|

![SharePoint-beállítás – új dokumentumtípus](./media/GERImportFromSharePoint-06-SharePointDocumentTypesSetup.png)

## <a name="configure-er-sources-for-the-er-format"></a>Elektronikus jelentéskészítési források beállítása az elektronikus jelentéskészítési formátumhoz
1. Kattintson a **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Elektronikus jelentéskészítés forrása menüpontra**.
2. Az **Elektronikus jelentéskészítés forrása** oldalon állítsa be a forrásfájlokat az adatimportáláshoz a konfigurált elektronikus jelentéskészítési formátum segítségével.
3. Adjon meg egy fájlnév maszkot, így csak a .xlsx kiterjesztésű fájlok lesznek importálva. A fájlnév maszk nem kötelező, és csak akkor lehet használni, ha korábban már meghatározták. Minden elektronikus jelentéskészítési formátumhoz csak egy maszkot határozhat meg.
4. Módosítsa a **Fájlok rendezése importálás előtt** értéket **Nincs rendezés** értékre, ha sok fájlt kell importálni, és az importálás sorrendje nem fontos
5. Válassza ki a korábban létrehozott összes SharePoint-mappát.

    [![Elektronikus jelentéskészítési fájlok – forrás beállítása](./media/GERImportFromSharePoint-07-FormatSourceSetup.PNG)](./media/GERImportFromSharePoint-07-FormatSourceSetup.PNG)

> [!NOTE]
> - Az elektronikus jelentéskészítési *forrás* egyénileg meghatározott minden egyes alkalmazási vállalat esetén. A *konfigurációk* viszont kiterjednek az összes vállalatra.
> - Ha törli egy elektronikus jelentéskészítési formátum elektronikus jelentéskészítési forrásbeállítását, törlődik az összes csatlakoztatott fájlállapot (lásd alább) is a megerősítéssel.

## <a name="review-the-files-states-for-the-er-format"></a>Az elektronikus jelentéskészítési formátumhoz kapcsolódó fájlállapotok áttekintése
1. Az **Elektronikus jelentéskészítés forrása** oldalon válassza a **A források fájlállapotai** lehetőséget az aktuális elektronikus jelentéskészítési formátumhoz konfigurált fájlforrások tartalmának áttekintéséhez.
2. A **Fájlok** szakaszban ellenőrizze a fájlok listáját. A lista megjeleníti a következőket:

    - Alkalmazható forrásfájlok a fájlnév maszk alapján (ha meg van adva fájlnév maszk), amelyek készen állnak az adatimportálásra. Ezeknél a fájloknál az **Importálási formátumhoz tartozó forrásnapló** szakasz üres.
    - Korábban importált fájlok. Ezeknél a fájloknál az **Importálási formátumhoz tartozó forrásnapló** szakaszban áttekintheti az adott fájl importálási előzményeit.

**A források fájlállapotai** lapot úgy is megnyithatja, ha a **Szervezeti adminisztráció** \> **Elektronikus jelentés** \> **A források fájlállapotai** ponthoz navigál. Ebben az esetben az oldalon információk jelennek meg az összes olyan elektronikus jelentéskészítési formátumra vonatkozóan, amelyekhez a vállalat, amelybe jelenleg be van jelentkezve, fáljforrásokat konfigurált.

## <a name="import-data-from-excel-files-that-are-in-a-sharepoint-folder"></a>Adatok importálása SharePoint-mappában lévő Excel-fájlokból
1. Töltse fel a SharePoint rendszerben a **1099import-data.xlsx** Microsoft Excel-fájlt, amely tartalmazza a szállítói tranzakciókat, a korábban létrehozott **Fájlok importálásának forrása (fő)** SharePoint-mappába.

    [![SharePointtartalom – Microsoft Excel-fájl importáláshoz](./media/GERImportFromSharePoint-08-UploadFile.png)](./media/GERImportFromSharePoint-08-UploadFile.png)

2. **A források fájlállapotai** oldalon válassza a **Frissítés** lehetőséget az oldal frissítéséhez. Ne feledje, hogy a SharePoint rendszerbe feltöltött Excel-fájl ezen a lapon **Kész** állapotúként jelent meg. Jelenleg a következő állapotok támogatottak:

    - **Kész** – Automatikusan hozzárendelve minden új fájlhoz a SharePoint-mappában. Ez az állapot azt jelenti, hogy a fájl importálásra kész.
    - **Importálás** – Automatikusan hozzárendelve egy elektronikus jelentéskészítési jelentés által a fájl zárolásakor az importálási folyamat során, amely megakadályozza a felhasználását egyéb folyamatokhoz (ha sok közülük párhuzamosan fut).
    - **Az importált** – Automatikusan hozzárendelve egy elektronikus jelentéskészítési jelentés által, ha a fájl importálása sikeresen befejeződött. Ez az állapot azt jelenti, hogy az importált fájl törölve lett a konfigurált fájlforrásból (SharePoint-mappa).
    - **Sikertelen** – Automatikusan hozzárendelve egy elektronikus jelentéskészítési jelentés által, ha a fájl importálása hibákkal vagy kivételekkel zajlott le.
    - **Várakoztatott** – Manuálisan hozzárendelve a felhasználó által ezen a lapon. Ez az állapot azt jelenti, hogy a fájl most nem lesz importálva. Ezzel az állapottal elhalaszthatja néhány fájl importálását.

    [![Elektronikus jelentéskészítéshez tartozó fájlállapotok oldala a kiválasztott forrásokhoz](./media/GERImportFromSharePoint-09-FileStatesForm.png)](./media/GERImportFromSharePoint-09-FileStatesForm.png)

## <a name="import-data-from-sharepoint-files"></a>Adatok importálása SharePoint-fájlokból
1. Nyissa meg az elektronikus jelentéskészítés konfigurációs fát, kattintson az **1099-es kifizetési modell** elemre, majd bontsa ki az elektronikus jelentéskészítés modellösszetevők listáját.
2. A kiválasztott elektronikus jelentéskészítési modellkonfigurációhoz tartozó modell-leképezések listájának megnyitásához válassza ki a modell-leképezés nevét.

    [![Elektronikus jelentéskészítéshez tartozó fájlállapotok oldala a kiválasztott forrásokhoz](./media/GERImportFromSharePoint-10-SelectModelMapping.PNG)](./media/GERImportFromSharePoint-10-SelectModelMapping.PNG)

3. Válassza a **Futtatás** lehetőséget a kiválasztott modell-leképezés futtatásához. Mivel beállított fájlforrásokat az elektronikus jelentéskészítési formátumhoz, szükség esetén módosíthatja a **Fájl forrása** lehetőséget, ha szükséges. Ha megtartja a lehetőség beállítását, az .xslx fájlok importálása a beállított forrásokból történik (ebben a példában a SharePoint-mappákból).

    Ebben a példában csak egy fájlt importál. Azonban több fájl esetén a fájlok abban a sorrendben kerülnek kiválasztásra az importáláshoz, amilyen sorrendben hozzáadta őket a SharePoint-mappához. Az elektronikus jelentéskészítési formátum minden egyes futtatásával egyetlen kiválasztott fájlt importál.

    [![Elektronikus jelentéskészítés modell-leképezésének futtatása](./media/GERImportFromSharePoint-11-RunModelMapping.PNG)](./media/GERImportFromSharePoint-11-RunModelMapping.PNG)

4. A modell-leképezés felügyelet nélkül futtatható kötegelt módban. Ebben az esetben minden alkalommal, amikor egy köteg futtatja az adott elektronikus jelentéskészítési formátumot, a rendszer egyetlen fájlt importál a beállított fájlforrásokból.

    Ha egy fájl sikeresen importálva lett a SharePoint mappából, az törölve lesz a mappából, és átkerül a sikeresen importált fájlok mappájába vagy a figyelmeztetésekkel importált fájlok mappájába. Máskülönben átkerül a sikertelen fájlok mappájába, vagy ebben a mappában marad, ha a hibás fájlok mappája nincs beállítva. 

5. Adja meg a bizonylatazonosítót, például **V-00001**, majd válassza az **OK** lehetőséget.

    [![Elektronikus jelentéskészítés modell-leképezésének futtatása](./media/GERImportFromSharePoint-12-ModelMappingRunFinished.PNG)](./media/GERImportFromSharePoint-12-ModelMappingRunFinished.PNG)

6. **A források fájlállapotai** oldalon válassza a **Frissítés** lehetőséget az oldal frissítéséhez.

    [![Elektronikus jelentéskészítéshez tartozó fájlállapotok oldala a kiválasztott forrásokhoz](./media/GERImportFromSharePoint-13-FileStatesForm.PNG)](./media/GERImportFromSharePoint-13-FileStatesForm.PNG)

7. A **Fájlok** szakaszban ellenőrizze a fájlok listáját. Az **Importálási formátumhoz tartozó forrásnapló** szakaszban jelennek meg az Excel-fájl importálásának előzményei. Mivel a fájl sikeresen importálva lett, **Törölt** jelölést kap a SharePoint-mappában.
8. Tekintse át a **Fájlok importálásának forrása (fő)** SharePoint-mappát. Ebből a mappából törlődtek a sikeresen importált Excel-fájlok.
9. Válassza a **Kötelezettségek** \> **Időszakos feladatok** \> **1099-es adóűrlap** \> **Szállítói kiegyenlítések az 1099-es jelentéshez** elemet.
10. A **Kezdő dátum** és a **Záró dátum** mezőkbe írja be a megfelelő értékeket. Majd válassza a **Manuális 1099-es tranzakciók** lehetőséget.

    Az oldalon megjelennek a szállítói tranzakciók, amelyek lettek importálva az Excel-fájlokból a SharePoint rendszerben a **V-00001** bizonylattal.

    [![1099-es szállítói tranzakciók oldala](./media/GERImportFromSharePoint-14-ImportedTransactions.PNG)](./media/GERImportFromSharePoint-14-ImportedTransactions.PNG)

## <a name="prepare-an-excel-file-for-import"></a>Excel-fájl előkészítése importáláshoz
1. Nyissa meg a korábban használt Excel-fájlt. Az 1. sor 3 oszlopban adjon meg egy olyan szállítókód, amely nem szerepel az alkalmazásban. Adjon meg további hamis szállítói adatokat a sorban.

    [![Minta Microsoft Excel-fájl a SharePoint rendszerből való importáláshoz](./media/GERImportFromSharePoint-15-Excel.PNG)](./media/GERImportFromSharePoint-15-Excel.PNG)

2. Töltse fel a szállítói tranzakciókat tartalmazó frissített Excel-fájlt a **Fájlok importálásának forrása (fő)** SharePoint-mappába.
3. Nyissa meg az elektronikus jelentéskészítés konfigurációs fát, kattintson az **1099-es kifizetési modell** elemre, majd bontsa ki az elektronikus jelentéskészítés modellösszetevők listáját.
4. A modell-leképezés frissítéséhez kattintson a modell-leképezés nevére, így a hibás szállítói kód hibának minősül az adatok importálási folyamata során.
5. Válassza a **Tervező** lehetőséget.
6. Az **Ellenőrzések** lapon módosítania kell az ellenőrzési szabályhoz tartozó ellenőrzést követő műveletet, amely szabály alapján a rendszer meghatározza, hogy az importált szállítói számla szerepel-e az alkalmazásban. Frissítse az **Ellenőrzést követő művelet** mező értékét a **Végrehajtás leállítása** művelethez, mentse a módosításokat, és zárja be a lapot.

    [![Elektronikus jelentéskészítés – modell-leképezés tervező oldal](./media/GERImportFromSharePoint-16-UpdateModelMapping.PNG)](./media/GERImportFromSharePoint-16-UpdateModelMapping.PNG)

7. Mentse a módosításokat, majd zárja be az elektronikus jelentéskészítési modell-leképezés tervezőjét.
8. Válassza a **Futtatás** lehetőséget a módosított elektronikus jelentéskészítési modell-leképezés futtatásához.
9. Adja meg a bizonylatazonosítót, például **V-00002**, majd válassza az **OK** lehetőséget.

    Ne feledje, hogy az információs napló tartalmaz egy értesítést, amely tájékoztatja arról, hogy a SharePoint-mappában található fájl hibás szállítói számlát tartalmaz, és nem lehet importálni.

    [![Elektronikus jelentéskészítés modell-leképezésének futtatása](./media/GERImportFromSharePoint-17-ModelMappingRunFinished.PNG)](./media/GERImportFromSharePoint-17-ModelMappingRunFinished.PNG)

10. A **A források fájlállapotai** oldalon válassza a **Frissítés** lehetőséget, majd a **Fájlok** szakaszban ellenőrizze a fájlok listáját.

    [![Elektronikus jelentéskészítéshez tartozó fájlállapotok oldala a kiválasztott forrásokhoz](./media/GERImportFromSharePoint-18-FileStatesForm.PNG)](./media/GERImportFromSharePoint-18-FileStatesForm.PNG)

   Az **Importálási formátumhoz tartozó forrásnapló** szakasz jelzi, ha az importálási folyamat sikertelen volt, és a fájl továbbra is a Fájlhibák SharePoint-mappában van (a **Törölve van** jelölőnégyzet nincs bejelölve). Ha javítja ezt a fájlt a SharePoint rendszerben a megfelelő szállítói kód hozzáadásával, és áthelyezi azt a Fájlok importálásának forrása (fő) SharePoint-mappába, a fájlt importálhatja.

11. Válassza a **Kötelezettségek** \> **Időszakos feladatok** \> **1099-es adóűrlap** \> **Szállítói kiegyenlítések az 1099-es jelentéshez** lehetőséget, írja be a megfelelő értékeket a **Kezdő dátum** és a **Záró dátum** mezőkbe, majd válassza a **Manuális 1099-es tranzakciók** lehetőséget.

    Csak a V-00001 bizonylathoz tartozó tranzakciók használhatók. A V-00002 bizonylathoz nem érhetők el tranzakciók, akkor sem, ha a legutóbb importált tranzakció hibája szerepelt az Excel-fájlban.
