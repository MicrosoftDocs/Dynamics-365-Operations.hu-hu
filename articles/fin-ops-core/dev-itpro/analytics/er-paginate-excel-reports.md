---
title: ER-formátum megtervezése a létrehozott dokumentumok Excel programban való oldalszámozásához
description: Ez a témakör azt mutatja be, hogyan lehet Elektronikus jelentéskészítési (ER) formátumotz tervezni, amely oldalszámoz egy Microsoft Excel használatával létrehozott dokumentumot.
author: NickSelin
ms.date: 09/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-08-01
ms.dyn365.ops.version: Version 10.0.22
ms.openlocfilehash: ce29225c4bce24adc2abefc3d3d6f20774852af4
ms.sourcegitcommit: 7a2001e4d01b252f5231d94b50945fd31562b2bc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/15/2021
ms.locfileid: "7488339"
---
# <a name="design-an-er-format-to-paginate-generated-documents-in-excel"></a>ER-formátum megtervezése a létrehozott dokumentumok Excel programban való oldalszámozásához

[!include [banner](../includes/banner.md)]

Ez a témakör leírja, hogyan konfigurálhat egy Rendszergazda vagy Elektronikus jelentéskészítési szakterületi konzulens egy [Elektronikus jelentéskészítési](general-electronic-reporting.md) formátumot, hogy kimenő dokumentumokat hozzon létre a Microsoft Excelben, és kezelje a dokumentumok oldalszámozását.

Ebben a példában módosítja a Microsoft által megadott ER-formátumot, amely az ellenőrző jelentés nyomtatására használható az Intrastat nyilatkozat [létrehozásakor](../../../finance/localizations/tasks/eur-00002-eu-intrastat-declaration.md). Ezzel a jelentéssel megfigyelheti a jelentett Intrastat-tranzakciókat. A módosításokkal kezelni lehet a létrehozott ellenőrzési jelentések oldalszámozását.

A jelen témakörben szereplő eljárások az **DEMF** vállalatnál végezhetők el. Nincs szükség kódolásra. Mielőtt belekezdene, a következő fájlokat is le kell töltenie és mentenie kell.

| Leírás       | Fájlnév |
|-------------------|-----------| 
| Jelentéssablon 1 | [ERIntrastatReportDemo1.xlsx](https://download.microsoft.com/download/7/2/a/72ae292a-8bb2-4b9d-8397-9764218f6fa8/ERIntrastatReportDemo1%20.xlsx) |
| Jelentéssablon 2 | [ERIntrastatReportDemo2.xlsx](https://download.microsoft.com/download/7/d/1/7d15858d-6260-4afa-9dda-d8b955e59b1a/ERIntrastatReportDemo2.xlsx) |

## <a name="configure-the-er-framework"></a>ER-keretrendszer konfigurálása

Kövesse az [ER-keretrendszer konfigurálása](er-quick-start2-customize-report.md#ConfigureFramework) rész lépéseit az ER-paraméterek minimális készletének beállításához. Ezt a beállítást még az ER keretrendszer használata előtt el kell végeznie, hogy egy szabványos ER-formátum egyéni verzióját megtervezze.

## <a name="import-the-standard-er-format-configuration"></a>A szabvány ER-formátumkonfiguráció importálása

A [A szabvány ER-formátumkonfiguráció importálása](er-quick-start2-customize-report.md#ImportERSolution1) rész lépéseit követve adja hozzá a szabványos ER-konfigurációkat az aktuális Dynamics 365 Finance-példányhoz. Az **Intrastat jelentés** formátumkonfigurációjának **1.9**-es verziójának importálása. A rendszer automatikusan importálja a tárházból az alap **Intrastat-modell** konfigurációjának 1. alapverzióját.

## <a name="customize-the-standard-er-format"></a>A szabvány ER-formátum testreszabása

### <a name="create-the-custom-er-format"></a>Az egyéni ER-formátum létrehozása

Ebben az esetben Ön a Litware, Inc. képviselője, amelye a jelenleg aktív ER konfigurációs szolgáltatóként van kiválasztva. Új ER-formátumkonfigurációt kell létrehozni az **Intrastat jelentés** konfiguráció alapként való használatával.

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában bontsa ki az **Intrastat modell** elemet, majd válassza a **Intrastat jelentés** lehetőséget. A Litware, Inc. ennek az ER-formátumkonfigurációnak az 1.9-es verzióját fogja használni az egyéni verzió alapjaként.
3. A **Konfiguráció létrehozása** kiválasztásával megnyithatja a legördülő párbeszédablakot. A párbeszédablak segítségével új konfigurációt hozhat létre az egyéni fizetési formátumra vonatkozóan.
4. Az **Új** mezőcsoportban válassza ki a **Származtatás névből: Intrastat jelentés, Microsoft** lehetőséget.
5. A **Név** mezőbe írja be: **Intrastat-jelentés Litware**.
6. Az új formátum létrehozásához válassza a **Konfiguráció létrehozása** elemet.

Az **Intrastat jelentés Litware** ER-formátum konfigurációjának 1.9.1-es verziója jön létre. Ez a verzió **Piszkozat** [állapottal](general-electronic-reporting.md#component-versioning) rendelkezik, és szerkeszthető. Az egyéni ER-formátum jelenlegi tartalma megegyezik a Microsoft által biztosított formátum tartalmával.

### <a name="make-the-custom-format-runnable"></a>Egyéni formátum futtathatóvá tétele

Miután létrehozta az egyéni formátum első verzióját, és az a **Piszkozat** állapottal rendelkezik, tesztelés céljából futtathatja a formátumot. A jelentés futtatásához a szállítói kifizetést az egyéni ER-formátumra hivatkozó fizetési mód használatával dolgozza fel. Alapértelmezésben, amikor egy ER-formátumot hív meg az alkalmazásból, csak a **Befejeződött** vagy **Megosztott** állapotú verziókat [veszi figyelembe](general-electronic-reporting.md#component-versioning) a rendszer. Ez a viselkedés segít megakadályozni a befejezetlen konstrukciókkal rendelkező ER-formátumok használatát. A teszt futtatásakor azonban kényszerítheti az alkalmazást egy **Piszkozat** állapottal rendelkező ER-formátumverzió használatára. Ily módon módosíthatja az aktuális formátum verziószámát, ha bármilyen módosítás szükséges. További információ: [Alkalmazhatóság](electronic-reporting-destinations.md#applicability).

Ha egy ER-formátum piszkozat verzióját kívánja használni, ennek kifejezett módon be kell jelölnie az ER-formátumot.

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.
3. A **Felhasználói paraméterek** párbeszédpanelen állítsa a **Futtatási beállítások** beállítását **Igen** értékre, majd kattintson az **OK** gombra.
4. Ha szükséges, a **Szerkesztés** gombbal az aktuális lapot szerkeszthetőre állíthatja.
5. A bal oldali ablak konfigurációs fáján válassza ki az **Intrastat jelentés Litware** lehetőséget.
6. A **Piszozat futtatása** beállítást állítsa **Igen** értékre, majd válassza ki a **Mentés** elemet.

    ![Piszkozat futtatása beállítás a Konfigurációk oldalon.](./media/er-paginate-excel-reports-derived-format-configuration.png)

## <a name="set-up-foreign-trade-parameters-to-use-the-custom-er-format"></a>Külkereskedelmi paraméterek beállítása az egyéni ER-formátum használatára

A következő lépések szerint konfigurálhatja a Külkereskedelmi paramétereket az egyéni formátum használatára.

1. Ugrás az **Adó** \> **Beállítás** \> **Külkereskedelem** \> **Külkereskedelmi paraméterek** pontra.
2. Az **Külkereskedelmi paraméterek** lapon az **Elektronikus jelentéstétel** gyorslapon a **Fájlformátum leképezése** mezőben válassza az **Intrastat jelentés Litware** lehetőséget.
3. A **Jelentésformátum hozzárendelése** mezőben válassza az **Intrastat-jelentés Litware** lehetőséget.
4. Válassza a **Mentés** lehetőséget.

## <a name="configure-the-custom-format-to-use-the-downloaded-report-template"></a>Állítsa be az egyéni formátumot a letöltött jelentéssablon használatára

### <a name="review-the-first-downloaded-excel-template"></a>Tekintse át az első letöltött Excel-sablont

1. Az asztali Excel-alkalmazásban nyissa meg a korábban letöltött **ERIntrastatReportDemo1.xlsx** sablonfájlt.
2. Ellenőrizze, hogy a sablon tartalmaz-e elnevezett tartományokat a jelentésfejlécek, jelentésadatok és jelentéslábléc szakaszok létrehozásához a létrehozott dokumentumokban.

    ![Az 1. Excel-sablon elrendezése az asztali alkalmazásban.](./media/er-paginate-excel-reports-template1.gif)

### <a name="replace-the-current-excel-template-in-the-custom-er-format"></a><a id="replace-template"></a>Az aktuális Excel-sablon cseréje az egyéni ER formátumban

Új Excel-sablont kell hozzáadnia az egyéni ER-formátumhoz.

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában bontsa ki az **Intrastat modell** \> **Intrastat jelentés** elemet, majd válassza ki az **Intrastat jelentés Litware** konfigurációt.
3. Válassza a **Tervező** lehetőséget.
4. A **Formátumtervező** lapon a Műveleti ablaktáblában válassza ki a **Részletek megjelenítése** lehetőséget.
5. Győződjön meg róla, hogy az **Intrastat: Excel** gyökérformátum-összetevő ki van választva, majd a műveleti ablaktábla **Importálás** lapján, az **Importálás** csoportban válassza a **Frissítés Excelből** lehetőséget.
6. A **Frissítés az Excel programból** párbeszédpanelen válassza a **Sablon frissítése** lehetőséget.
7. A **Megnyitás** párbeszédpanelen tallózza ki, majd válassza ki a korábban letöltött **ERIntrastatReportDemo1.xlsx** fájlt, majd válassza a **Megnyitás** lehetőséget.
8. Válassza ki az **OK** lehetőséget.
9. Válassza a **Mentés** lehetőséget.

![Az ER-formátumtervező formátumszerkezete az új Excel-sablon hozzáadása után.](./media/er-paginate-excel-reports-format1.png)

## <a name="change-the-data-binding-to-show-the-item-description-on-a-generated-report"></a>Az adatkötés módosítása a cikkleírás megjelenítéséhez a létrehozott jelentésben

1. A **Formátumtervező** lapon válassza a **Hozzárendelés** fület.
2. Bontsa ki az **Intrastat** \> **Jelentéssorok** elemet, és válassza ki az **Árucikk-kód** összetevőt.
3. Válassza a **Képlet szerkesztése** elemet.
4. A kötési képlet módosítása a `@.CommodityCode` helyett a következőre: `CONCATENATE(@.CommodityCode, " ", @.ProductName)`.
5. Válassza a **Mentés** lehetőséget.

![Konfigurált kötés a cikkleírás megjelenítéséhez az ER formátumtervezőben.](./media/er-paginate-excel-reports-format1a.png)

## <a name="generate-an-intrastat-declaration-control-report"></a><a id="generate-intrastat-control-report"></a>Az EU Intrastat nyilatkozat ellenőrzőjelentésének létrehozása

Először győződjön meg róla, hogy vannak Intrastat-tranzakciók jelentéshez az **Intrastat** lapon.

![Tranzakciók az intrastat oldalon.](./media/er-paginate-excel-reports-transactions1.gif)

Ezután az egyéni ER-formátum használatával hozza létre az Intrastat nyilatkozat ellenőrző jelentését.

1. Ugorjon az **Adó** \> **Nyilatkozatok** \> **Külkereskedelem** \> **Intrastat** pontra.
2. Válassza ki a művelet ablaktábláján az **Intrastat** oldalon a **Kimenet** \> **Jelentés** lehetőséget.
3. Az **Intrastat jelentés** párbeszédpanelen a következő lépések szerint futtatja a jelentést:

    1. Állítsa be **Kezdő dátum** és **Befejező dátum** mezőket, hogy belefoglaljon adott Intrastat tranzakciókat a jelentésbe.
    2. Állítsa a **Fájl készítése** opciót **Nem** értékre.
    3. Állítsa a **Jelentés készítése** opciót **Igenre**.
    4. Válassza ki az **OK** lehetőséget.

4. Töltse le és mentse a létrehozott dokumentumot.
5. Nyissa meg a dokumentumot az Excel alkalmazásban, és ellenőrizze azt.

    ![Generált Excel-dokumentum az asztali alkalmazásban.](./media/er-paginate-excel-reports-document1.png)

## <a name="configure-the-custom-format-to-paginate-generated-documents"></a>Az egyéni formátum konfigurálása a létrehozott dokumentumok oldalszámozásához

### <a name="review-the-second-downloaded-excel-template"></a>Tekintse át a második letöltött Excel-sablont

1. Az asztali Excel asztali alkalmazásban nyissa meg a korábban letöltött **ERIntrastatReportDemo2.xlsx** sablonfájlt.
2. Hasonlítsa össze ezt a sablont az **ERIntrastatReportDemo1.xlsx** sablonnal, és ellenőrizze, hogy számos új Excel-nevet tartalmaz, hogy létrehozza és kitöltse az oldalspecifikus szakaszokat a generált dokumentumokban:

    - A lapfejlécek létrehozásához hozzáadja a **ReportPageHeader** tartományt.
    - A lapláblécek létrehozásához hozzáadja a **ReportPageFooter** tartományt.
    - A **ReportPagePageer\_PageLines** cella úgy van beállítva, hogy oldalanként mutatja a tranzakciók számát.
    - A **ReportPagePageer\_PageAmount** cella úgy van beállítva, hogy oldalanként mutatja a tranzakciók teljes összegét.
    - A **ReportPagePageer\_PageWeight** cella úgy van beállítva, hogy oldalanként mutatja a tranzakciók teljes tömegét.
    - A **ReportPagePageer\_RunningCounterLines** cella úgy van beállítva, hogy a jelentés kezdetétől kezdve mutatja a tranzakciók számlálóját az aktuális lapon keresztül.
    - A **ReportPagePageer\_RunningTotalAmount** cella úgy van beállítva, hogy a jelentés kezdetétől kezdve mutatja a tranzakciók görgetett összegét az aktuális lapon keresztül.
    - A **ReportPagePageer\_RunningTotalWeight** cella úgy van beállítva, hogy a jelentés kezdetétől kezdve mutatja a tranzakciók görgetett tömegét az aktuális lapon keresztül.

    ![Az 2. Excel-sablon elrendezése az asztali alkalmazásban.](./media/er-paginate-excel-reports-template2a.gif)

    A sablon **CommodityCode** cellája a cella a cellaszöveg tördelésére van konfigurálva. Mivel a tranzakció részletező sora úgy van beállítva, hogy automatikusan elférjen egy sormagasságban, az egész sor magasságának automatikusan módosulnia kell, amikor a **CommodityCode** cellában lévő szöveg tördelve van.

    ![A CommodityCode cella a cella szövegének tördelésére van konfigurálva.](./media/er-paginate-excel-reports-template2b.gif)

### <a name="repeat-the-replacement-of-the-current-excel-template-in-the-custom-er-format"></a>Az aktuális Excel-sablon cseréjének megismétlése az egyéni ER formátumban

1. Hajtsa végre a témakör [Az aktuális Excel-sablon cseréje az egyéni ER formátumban](#replace-template) szakaszának lépéseit. A 7. lépésben azonban válassza ki az **ERIntrastatReportDemo2.xlsx** fájlt.
2. A **Formátumtervező** oldalon bontsa ki az **Intrastat** elemet.
3. A szerkeszthető ER-formátumhoz hozzáadott [Tartomány](er-fillable-excel.md#range-component) formátum-összetevők neve, amelyek hozzá lettek adva a szerkeszthető ER-formátumban, hogy szinkronizálva legyen a struktúra az alkalmazott Excel-sablon struktúrájával.

    1. A **ReportPageHeader** Excel névhez társított **Tartomány** összetevő kiválasztása.
    2. Adja meg a **Jelentés lapfejlécét** a **Formátum** lap **Név** mezőjében.
    3. A **ReportPageFooter** Excel névhez társított **Tartomány** összetevő kiválasztása.
    4. Adja meg a **Jelentés lapláblécét** a **Formátum** lap **Név** mezőjében.

4. Válassza a **Mentés** lehetőséget.

![Az ER-formátumtervező formátumszerkezete az új Excel-sablon cseréje után.](./media/er-paginate-excel-reports-format2.png)

### <a name="change-the-format-structure-to-implement-document-pagination"></a>A formátumszerkezet módosítása a dokumentum-lapozás implementálásához

1. Válassza ki az **Intrastat** gyökérösszetevőt a bal oldali ablak formázási fájának **Formátumtervező** lapján.
2. Válassza a **Hozzáadás** lehetőséget.
3. A **Hozzáadás** párbeszédpanelen válassza ki az [Oldal](er-fillable-excel.md#page-component) összetevőt az **Excel** összetevőcsoportban.
4. Írja be az **Összetevő-tulajdonságok** párbeszédpanel **Név** mezőjébe ezt: **Jelentésoldal**. Majd kattintson az **OK** lehetőségre.
5. A **Jelentés lapfejléc** összetevőjét minden létrehozott lapon a következő lépések szerint használhatja oldalfejlécként:

    1. Válassza ki a **Jelentés lap fejléc** összetevőjét, majd válassza a **Kivágás** lehetőséget.
    2. Válassza ki a **Jelentés lap fejléc** összetevőjét, majd válassza a **Beillesztés** lehetőséget.
    3. Bontsa ki a **Jelentés oldalt**.
    4. Ha az **Oldal** összetevőt arra szeretné kényszeríteni, [hogy vegye figyelembe](er-fillable-excel.md#page-component-structure) ezt a tartományt, hogy figyelembe vegyen egy oldalfejlécet, válassza ki **Jelentés lap fejléce** lehetőséget, majd a **Formátum** lapon a **Replikálás iránya** mezőben válassza a **Nincs replikálás** lehetőséget.

6. A létrehozott dokumentumnak a jelentéssorok figyelembe vételével történő oldalakra bontása érdekében hajtsa végre a következő lépéseket:

    1. Válassza ki a **Jelentéssorok** összetevőjét, majd válassza a **Kivágás** lehetőséget.
    2. Válassza ki a **Jelentés lap fejléc** összetevőjét, majd válassza a **Beillesztés** lehetőséget.

7. Ha a jelentés láblécét a jelentéssorok után, de az utolsó oldal lábléce előtt kell szerepeltetni, kövesse a következő lépéseket:

    1. Válassza ki a **Jelentés lábléce** összetevőt, majd válassza a **Kivágás** lehetőséget.
    2. Válassza ki a **Jelentés lap fejléc** összetevőjét, majd válassza a **Beillesztés** lehetőséget.

8. A **Jelentés laplábléc** összetevőjét minden létrehozott lapon a következő lépések szerint használhatja oldalláblécként:

    1. Válassza ki a **Jelentés lap lábléc** összetevőjét, majd válassza a **Kivágás** lehetőséget.
    2. Válassza ki a **Jelentés lap fejléc** összetevőjét, majd válassza a **Beillesztés** lehetőséget.
    3. Ha az **Oldal** összetevőt arra szeretné kényszeríteni, [hogy vegye figyelembe](er-fillable-excel.md#page-component-structure) ezt a tartományt, hogy figyelembe vegyen egy oldalláblécet, válassza ki **Jelentés lap lábléce** lehetőséget, majd a **Formátum** lapon a **Replikálás iránya** mezőben válassza a **Nincs replikálás** lehetőséget.

![Az ER-formátumtervező formátumszerkezete a dokumentum láblécének implementálása után.](./media/er-paginate-excel-reports-format3.png)

### <a name="add-data-sources-to-calculate-page-footer-totals"></a>Adatforrások hozzáadása a laplábléc-összegek kiszámításához

Az új adatforrásokat úgy kell konfigurálni, hogy kiszámítsa a lap összesítését, a görgetett számlálót és a görgetett összesített értékeket, és hogy a lap láblécében meg tudja jeleníteni őket. Javasoljuk, hogy erre a célra [Adatgyűjtés](er-data-collection-data-sources.md) adatforrásokat használjon.

1. A **Formátumtervező** lapon válassza a **Hozzárendelés** fület.
2. Válassza a **Gyökér hozzáadása** lehetőséget, majd kövesse az alábbi lépéseket:

    1. Az **Adatforrás hozzáadása** párbeszédpanel **Általános** szakaszában válassza az **Üres tároló** lehetőséget.
    2. Az **"Üres tároló" adatforrás tulajdonságai** párbeszédpanel **Név** mezőjébe írja be az **Összesen** kifejezést.
    3. Válassza ki az **OK** lehetőséget.

3. Válassza az **Összeg** adatforrást, válassza a **Hozzáadás** lehetőséget, majd hajtsa végre a következő lépéseket:

    1. Az **Adatforrás hozzáadása** párbeszédpanel **Általános** szakaszában válassza az **Üres tároló** lehetőséget.
    2. Az **"Üres tároló" adatforrás tulajdonságai** párbeszédpanel **Név** mezőjébe írja be az **Oldal** kifejezést.
    3. Válassza ki az **OK** lehetőséget.

4. Válassza ismét a **Hozzáadás** lehetőséget, majd kövesse az alábbi lépéseket:

    1. Az **Adatforrás hozzáadása** párbeszédpanel **Általános** szakaszában válassza az **Üres tároló** lehetőséget.
    2. Az **"Üres tároló" adatforrás tulajdonságai** párbeszédpanel **Név** mezőjébe írja be a **Görgetett** kifejezést.
    3. Válassza ki az **OK** lehetőséget.

5. Válassza a **Total.Page** adatforrást, válassza a **Hozzáadás** lehetőséget, majd hajtsa végre a következő lépéseket:

    1. Az **Adatforrás hozzáadása** párbeszédpanel **Függvények** szakaszában válassza az **Adatgyűjtés** lehetőséget.
    2. Az **"Adatgyűjtés" adatforrás tulajdonságai** párbeszédpanel **Név** mezőjébe írja be az **Összeg** kifejezést.
    3. A **Cikktípus** mezőben válassza ki a **Valós** lehetőséget.
    4. Az **Összes érték gyűjtése** beállításnál adja meg az **Igen** értéket.
    5. Válassza ki az **OK** lehetőséget.

6. Válassza ismét a **Hozzáadás** lehetőséget, majd kövesse az alábbi lépéseket:

    1. Az **Adatforrás hozzáadása** párbeszédpanel **Függvények** szakaszában válassza az **Adatgyűjtés** lehetőséget.
    2. Az **"Adatgyűjtés" adatforrás tulajdonságai** párbeszédpanel **Név** mezőjébe írja be a **Tömeg** kifejezést.
    3. A **Cikktípus** mezőben válassza ki a **Valós** lehetőséget.
    4. Az **Összes érték gyűjtése** beállításnál adja meg az **Igen** értéket.
    5. Válassza ki az **OK** lehetőséget.

7. Válassza a **Total.Running** adatforrást, válassza a **Hozzáadás** lehetőséget, majd hajtsa végre a következő lépéseket:

    1. Az **Adatforrás hozzáadása** párbeszédpanel **Függvények** szakaszában válassza az **Adatgyűjtés** lehetőséget.
    2. Az **"Adatgyűjtés" adatforrás tulajdonságai** párbeszédpanel **Név** mezőjébe írja be az **Összeg** kifejezést.
    3. A **Cikktípus** mezőben válassza ki a **Valós** lehetőséget.
    4. Az **Összes érték gyűjtése** mezőnél adja meg az **Igen** értéket.
    5. Válassza ki az **OK** lehetőséget.

8. Válassza ismét a **Hozzáadás** lehetőséget, majd kövesse az alábbi lépéseket:

    1. Az **Adatforrás hozzáadása** párbeszédpanel **Függvények** szakaszában válassza az **Adatgyűjtés** lehetőséget.
    2. Az **"Adatgyűjtés" adatforrás tulajdonságai** párbeszédpanel **Név** mezőjébe írja be a **Tömeg** kifejezést.
    3. A **Cikktípus** mezőben válassza ki a **Valós** lehetőséget.
    4. Az **Összes érték gyűjtése** mezőnél adja meg az **Igen** értéket.
    5. Válassza ki az **OK** lehetőséget.

9. Válassza ismét a **Hozzáadás** lehetőséget, majd kövesse az alábbi lépéseket:

    1. Az **Adatforrás hozzáadása** párbeszédpanel **Függvények** szakaszában válassza az **Adatgyűjtés** lehetőséget.
    2. Az **"Adatgyűjtés" adatforrás tulajdonságai** párbeszédpanel **Név** mezőjébe írja be a **Sorok** kifejezést.
    3. A **Cikktípus** mezőben válassza ki az **Egész szám** lehetőséget.
    4. Az **Összes érték gyűjtése** mezőnél adja meg az **Igen** értéket.
    5. Válassza ki az **OK** lehetőséget.

10. Válassza a **Mentés** lehetőséget.

### <a name="add-data-sources-to-control-page-footer-visibility"></a>Adatforrások hozzáadása a laplábléc láthatóságának szabályozásához

Ha azt tervezi, hogy a lap láblécének láthatóságát ellenőrzi, és ha tranzakciót tartalmaz, akkor a láblécet nem tervezi a végleges lapon szerepeltetni, konfigurálja az új adatforrást a szükséges görgetett számláló kiszámításához.

1. A **Formátumtervező** lapon válassza a **Hozzárendelés** fület.
2. Válassza a **Total.Running** adatforrást, és válassza a **Hozzáadás** lehetőséget.
3. Az **Adatforrás hozzáadása** párbeszédpanel **Függvények** szakaszában válassza az **Adatgyűjtés** lehetőséget.
4. Az **"Adatgyűjtés" adatforrás tulajdonságai** párbeszédpanel **Név** mezőjébe írja be a **Lines2** kifejezést.
5. A **Cikktípus** mezőben válassza ki az **Egész szám** lehetőséget.
6. Az **Összes érték gyűjtése** beállításnál adja meg az **Igen** értéket.
7. Válassza ki az **OK** lehetőséget.
8. Válassza a **Mentés** lehetőséget.

![Adatforrások hozzáadva az ER formátumtervezőben.](./media/er-paginate-excel-reports-format4.png)

### <a name="configure-bindings-to-collect-total-values"></a>Kötések konfigurálása összegértékek összegyűjtéséhez

1. A **Formátumtervező** lapon, a formátumfában bontsa ki a **Jelentéssorok** összetevőt, és válassza ki a beágyazott **Számlaérték** összetevőt.
2. Válassza a **Képlet szerkesztése** elemet.
3. A kötési képlet módosítása a `NUMBERVALUE(NUMBERFORMAT(@.InvoiceValue, "F"&TEXT(model.Parameters.IntrastatAmountDecimals)), ".", "")` helyett a következőre: `Total.Page.Amount.Collect(NUMBERVALUE(NUMBERFORMAT(@.InvoiceValue, "F"&TEXT(model.Parameters.IntrastatAmountDecimals)), ".", ""))`.

    > [!NOTE]
    > A kötés nem csak az összes iterált tranzakció összegértékét helyezi el egy Excel-cellába is., hanem ez a kötés összegyűjti az értéket **Total.Page.Amount** adatgyűjtemény adatforrásban.

4. Válassza ki a beágyazott **Súly** összetevőt.
5. Válassza a **Képlet szerkesztése** elemet.
6. A kötési képlet módosítása a `@.'$RoundedWeight'` helyett a következőre: `Total.Page.Weight.Collect(@.'$RoundedWeight')`.

    > [!NOTE]
    > A kötés nem csak az összes iterált tranzakció súlyértékét helyezi el egy Excel-cellába is., hanem ez a kötés összegyűjti az értéket **Total.Page.Weight** adatgyűjtemény adatforrásban.

![Konfigurált kötések az összértékek összegyűjtéséhez az ER-formátumtervezőben.](./media/er-paginate-excel-reports-format5.png)

### <a name="configure-bindings-to-fill-in-page-footer-totals"></a>Kötések konfigurálása a lap láblécösszegek kitöltéséhez

1. A **Formátumtervező** lapon, a formátumfában bontsa ki a **Jelentéslap lábléce** összetevőt, válassza ki azt a beágyazott **Tartomány** összetevőt, amely az Excel **ReportPageFooter\_PageAmount** cellájára hivatkozik, majd hajtsa végre a következő lépéseket:

    1. A jobb oldali ablak adatforrásfában válassza az **Total.Page.Amount.Sum()** cikket.
    2. Válassza a **Bind** elemet.
    3. Válassza a **Képlet szerkesztése** elemet.
    4. A képlet frissítése a `Total.Page.Amount.Sum(false)` képletre.

    > [!NOTE]
    > A függvény argumentumát **Hamis** értékként kell megadni, hogy az összegyűjtött adatokat megtartsa az aktuális laphoz, mivel ezek az adatok a teljes görgetett összeg mennyisége, a sorok oldalankénti teljes száma és a sorok görgetett számlálója kiszámításához szükségesek.

2. Válassza ki a formátumfában azt a beágyazott **Tartomány** összetevőt, amely hivatkozik az Excel **ReportPageFooter\_PageWeight** cellájára, majd hajtsa végre a következő lépéseket:

    1. A jobb oldali ablak adatforrásfában válassza az **Total.Page.Weight.Sum()** cikket.
    2. Válassza a **Bind** elemet.
    3. Válassza a **Képlet szerkesztése** elemet.
    4. A képlet frissítése a `Total.Page.Weight.Sum(false)` képletre.

### <a name="configure-bindings-to-fill-in-page-running-totals"></a>Kötések konfigurálása a lap az oldal görgetett összegének kitöltéséhez

1. A **Formátumtervező** lapon, a formátumfában bontsa ki a **Jelentéslap lábléce** összetevőt, válassza ki azt a beágyazott **Tartomány** összetevőt, amely az Excel **ReportPageFooter\_RunningTotalAmount** cellájára hivatkozik, majd hajtsa végre a következő lépéseket:

    1. A jobb oldali ablak adatforrásfában válassza az **Total.Running.Amount.Collect()** cikket.
    2. Válassza a **Bind** elemet.
    3. Válassza a **Képlet szerkesztése** elemet.
    4. A képlet frissítése a `Total.Running.Amount.Sum(false)+Total.Running.Amount.Collect(Total.Page.Amount.Sum(true))` képletre.

    > [!NOTE]
    > Az `Total.Running.Amount.Sum(false)` operandus visszaadja a korábban összegyűjtött görgetett összege mennyiségét. A `Total.Running.Amount.Collect(Total.Page.Amount.Sum(true))` operandus az aktuális lap teljes összegét adja eredményül. A második operandus beágyazott függvényének argumentumát **Igaz** értékkel kell megadni, hogy a `Total.Page.Amount` adatgyűjtés alaphelyzetbe állítsa legyen, amint ez az érték be van helyezve a `Total.Running.Amount` görgetett összeg gyűjteménybe. A megadott argumentumnak el kell kezdenie összegyűjteni a következő oldalösszeget a 0 (nulla) összegtől.
    >
    > A `Total.Running.Amount.Sum(false)` függvény meg van hívva az összeg beírásához az aktuális lapon az Excel **ReportPageFooter\_RunningTotalAmount** cellába.

2. Válassza ki a formátumfában azt a beágyazott **Tartomány** összetevőt, amely hivatkozik az Excel **ReportPageFooter\_RunningTotalWeight** cellájára, majd hajtsa végre a következő lépéseket:

    1. A jobb oldali ablak adatforrásfában válassza az **Total.Running.Weight.Collect()** cikket.
    2. Válassza a **Bind** elemet.
    3. Válassza a **Képlet szerkesztése** elemet.
    4. A képlet frissítése a `Total.Running.Weight.Sum(false)+Total.Running.Weight.Collect(Total.Page.Weight.Sum(true))` képletre.

### <a name="configure-bindings-to-fill-in-the-page-running-counter"></a>Kötések konfigurálása a lap az oldal görgetett számlálójának kitöltéséhez

1. A **Formátumtervező** lapon, a formátumfában bontsa ki a **Jelentéslap lábléce** összetevőt, válassza ki azt a beágyazott **Tartomány** összetevőt, amely az Excel **ReportPageFooter\_RunningCounterLines** cellájára hivatkozik.
2. Válassza a **Képlet szerkesztése** elemet.
3. Adja hozzá a `Total.Running.Lines.Collect(COUNT(Total.Page.Amount.Result))` képletet.

    > [!NOTE]
    > Ez a képlet a teljes jelentés összegyűjtött összegértékeinek számát adja eredményül. Ez a szám egyenlő az ebben a pillanatban iteratedált tranzakciók számával. Ugyanakkor a képlet összegyűjti a visszaadott értéket a **Total.Running.Lines** gyűjteményben.

### <a name="configure-bindings-to-fill-in-the-page-footer-counter"></a>Kötések konfigurálása a lap az oldallábléc számlálójának kitöltéséhez

1. A **Formátumtervező** lapon, a formátumfában bontsa ki a **Jelentéslap lábléce** összetevőt, válassza ki azt a beágyazott **Tartomány** összetevőt, amely az Excel **ReportPageFooter\_PageLines** cellájára hivatkozik.
2. Válassza a **Képlet szerkesztése** elemet.
3. Adja hozzá a `COUNT(Total.Page.Amount.Result)-Total.Running.Lines.Sum(false)` képletet.

    > [!NOTE]
    > Ez a képlet az aktuális lapon található tranzakciók számát számítja ki a **Total.Page.Amount.Result** oldalon a teljes jelentéshez összegyűjtött tranzakciók száma és az ebben a fázisban a **Total.Running.Lines.Sum** szakaszban tárolt tranzakciók különbségeként. Mivel az aktuális lap tranzakcióinak száma a **Total.Running.Lines** elemben található az összekötő **Tartomány** komponensben, amely az Excel **ReportPageFooter\_RunningCounterLines** cellájára hivatkozik, az aktuális oldalon található tranzakciókat ez még nem tartalmazza. Ebből következően ez a különbség egyenlő az aktuális lapon lévő tranzakciók számával.

![Konfigurált kötések a lap láblécszámlálójának kitöltésére az ER formátumtervezőben.](./media/er-paginate-excel-reports-format6.png)

### <a name="configure-component-visibility"></a>Összetevőláthatóság konfigurálása

A létrehozott dokumentumok adott lapján módosíthatja a lap fejlécének és láblécének láthatóságát, hogy elrejtse a következő elemeket:

- Az oldalfejléc az első oldalon, mert a jelentésfejlécben már vannak oszlopcímek
- A lap fejléce bármelyik oldalon, amely nem tartalmaz tranzakciókat, amelyek az utolsó oldalon jelennek meg
- A lap lábléce bármelyik oldalon, amely nem tartalmaz tranzakciókat, amelyek az utolsó oldalon jelennek meg

A láthatóság módosítása érdekében frissítse a **Jelentés lap fejléce** és a **Jelentés lap lábléce** összetevők **Engedélyezett** tulajdonságát.

1. A **Formátumtervező** lapon, a formátumfában bontsa ki a **Jelentésoldal** összetevőt, és válassza ki a beágyazott **Jelentésoldal-fejléc** összetevőt, és kövesse ezeket a lépéseket:

    1. Válassza az **Engedélyezett** mezőhöz a **Szerkesztés** beállítást.
    2. A **Képlettervező** lap **Képlet** mezőjébe írja be a mezőbe a következőt kifejezést:

        `AND(`<br>
        `COUNT(Total.Page.Amount.Result)<>0,`<br>
        `COUNT(Total.Page.Amount.Result)<>COUNT(model.CommodityRecord)`<br>
        `)`

2. A formátumfában válassza ki a **Jelentéslap lábléce** összetevőt, majd hajtsa végre a következő lépéseket:

    1. Válassza az **Engedélyezett** mezőhöz a **Szerkesztés** beállítást.
    2. A **Képlettervező** lap **Képlet** mezőjébe írja be a mezőbe a következőt kifejezést:

        `(`<br>
        `COUNT(Total.Page.Amount.Result)-Total.Running.Lines2.Sum(false)+`<br>
        `0*Total.Running.Lines2.Collect(COUNT(Total.Page.Amount.Result))`<br>
        `)<>0`

    > [!NOTE]
    > A `COUNT(Total.Page.Amount.Result)-Total.Running.Lines2.Sum(false)` konstrukció az aktuális lapon található tranzakciók számának kiszámítására használható. A `0*Total.Running.Lines2.Collect(COUNT(Total.Page.Amount.Result)` konstrukció segítségével az aktuális lapon lévő tranzakciók számát hozzáadhatja a gyűjteményhez, hogy helyesen tudja kezelni a következő oldal láblécének láthatóságát.
    >
    > A `Total.Running.Lines` gyűjtemény itt nem használható fel, mert az alapösszetevő **Engedélyezett** tulajdonságának feldolgozása a beágyazott összetevők kötésének feldolgozása **után** történik. Az **Engedélyezett** tulajdonság feldolgozásakor a `Total.Running.Lines` gyűjtemény már növelve lett az aktuális lapon lévő tranzakciók számával.

3. Válassza a **Mentés** lehetőséget.

## <a name="generate-an-intrastat-declaration-control-report-updated"></a>Az EU Intrastat nyilatkozat ellenőrzőjelentésének létrehozása (frissített)

1. Győződjön meg róla, hogy 24 tranzakciója van az **Intrastat** lapon. Ismételje meg a témakör [Az Intrastat nyilatkozat ellenőrzőjelentésének létrehozása](#generate-intrastat-control-report) szakaszában található lépéseket az ellenőrző jelentés létrehozásához és ellenőrzéséhez.

    Minden tranzakció az első oldalon látható. A lap összesítései és számlálói egyenlők a jelentés végösszegeivel és számlálóival. Az oldalfejléctartomány az első oldalon el van rejtve, mert a jelentésfejlécben már vannak oszlopcímek. Az oldal fejléce és lábléce a második oldalon van elrejtve, mert az az oldal nem tartalmaz tranzakciókat.

    ![Generált Excel-dokumentum az asztali alkalmazásban.](./media/er-paginate-excel-reports-document2.gif)

2. Két tranzakció frissítése az **Intrastat** oldalon a **Cikkszám** kód módosításával **D00006**-ről **L0010**-re. Ne feledje, hogy az új cikk termékneve (**Aktív hangfalpár**) hosszabb, mint az eredeti cikk termékneve (**Normál hangszóró**). Ez a helyzet a létrehozott dokumentum megfelelő cellájában kényszeríti a szöveg tördelését. A dokumentum lapszámozását, valamint az oldalhoz kapcsolódó összegzést és leltározást most frissíteni kell. Ismételje meg a [Az Intrastat nyilatkozat ellenőrzőjelentésének létrehozása](#generate-intrastat-control-report) szakaszban található lépéseket az ellenőrző jelentés létrehozásához és ellenőrzéséhez.

    Jelenleg két oldalon jelennek meg a tranzakciók, és a lap összesítései és számlálói helyesen vannak kiszámítva. Az oldal fejléctartománya megfelelően el van rejtve az első oldalon, és látható a második oldalon. A lap lábléce mindkét oldalon látható, mert tranzakciókat tartalmaznak.

    ![Frissített generált Excel-dokumentum az asztali alkalmazásban.](./media/er-paginate-excel-reports-document3.gif)

## <a name="frequently-asked-questions"></a>Gyakori kérdések

### <a name="is-there-any-way-to-recognize-when-the-final-page-is-processed-by-the-page-format-component"></a>Fel lehet ismerni, amikor a végső oldalt a Oldalformátum-összetevő feldolgozza?

Az **Oldal** összetevő [nem tesz elérhetővé](er-fillable-excel.md#page-component-limitations) információkat a feldogozott oldalak számáról, és az oldalak teljes számáról a generált dokumentumban. Az ER-[képletek](er-formula-language.md) azonban ettől függetlenül felismerik az utolsó oldalt. Egy példa:

- A már feldolgozott tranzakciók számának kiszámítása a **Jelentésoldal** összetevő használatával. Ezt a számítást a `COUNT(Total.Page.Amount.Result)` képlettel végezheti el. 
- A feldolgozható tranzakciók számának kiszámítása, amelyet fel kell dolgozni a `model.CommodityRecord` kötés alapján, amely konfigurálva van a **Jelentéssorok** összetevőhöz. Ezt a számítást a `COUNT(model.CommodityRecord)` képlettel végezheti el.
- Két szám összehasonlítása az utolsó oldal felismeréséhez. Ha mindkét érték egyenlő, akkor a program létrehozza az utolsó lapot.

> [!NOTE]
> Javasoljuk, hogy ezt a megközelítést csak akkor használja, ha a **Jelentéssorok** összetevő **Engedélyezett** tulajdonsága nem tartalmaz olyan képletet, amely futásidőben [Hamis](er-formula-supported-data-types-primitive.md#boolean) értéket adhat vissza a kötött [Rekordlista](er-formula-supported-data-types-composite.md#record) egyes iterált [rekordjainál](er-formula-supported-data-types-composite.md#record-list).

## <a name="additional-resources"></a>További erőforrások

- [Tervezzen konfigurációkat a kimenő dokumentumok Excel-formátumban történő létrehozásához](er-fillable-excel.md)
- [Adatgyűjtési adatforrások használata elektronikus jelentéskészítési (ER) formátumokban](er-data-collection-data-sources.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
