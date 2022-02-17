---
title: Csoportosítsa a rekordokat és az összesített számításokat GROUPBY adatforrások használatával
description: Ez a témakör bemutatja, hogyan használhatja a GROUPBY típusú adatforrásokat az elektronikus jelentésekben (ER).
author: NickSelin
ms.date: 01/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5a6cdc486c5f799bdedafa38e90be989fd328c96
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075752"
---
# <a name="group-records-and-aggregate-calculations-by-using-groupby-data-sources"></a>Csoportosítsa a rekordokat és az összesített számításokat GROUPBY adatforrások használatával

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

Amikor konfigurálod [Elektronikus jelentéstétel (ER)](general-electronic-reporting.md) modellleképezéseket vagy formátumokat [add hozzá](#AddMmDataSource2) a szükséges adatforrások **Csoportosít** típus.

A tervezés idején a **Csoportosít** az adatforrás a következő elemek azonosítására van beállítva:

- A [alap adatforrás](#BaseDataSource) amely futás közben csoportosított rekordokat tartalmaz
- [Mezők csoportosítása](#GroupingFields) az alap adatforrásból, amelyet futás közben a rekordok csoportosítására használunk
- [Összesített függvények](#AggregateFunctions) amelyek meghatározzák az összesített számításokat, amelyeket minden egyes felfedezett csoportra futás közben kell elvégezni

Futás közben egy konfigurált **Csoportosít** az adatforrás azokat a rekordokat csoportosítja, amelyeknek azonos értékei vannak a csoportosítási mezőkben, majd visszaadja a rekordok listáját. Minden rekord egyetlen csoportot képvisel. Az adatforrás minden csoportnál feltárja azokat a mezőértékeket, amelyek alapján a kezdeti rekordokat csoportosították, a számított összesített függvények értékeit, valamint a csoporthoz tartozó alapadatforrás rekordjainak listáját.

## <a name="aggregate-functions"></a><a name="AggregateFunctions"></a> Összesített függvények

Futás közben minden összesített számítás minden rekordcsoporthoz megtörténik. Ez a számítás egyetlen mező értékének vagy kifejezésnek az adatforrás rekordjaiban történő felhasználásával történik, amely csoportosításra lett kiválasztva a szerkeszthető adatforrásban.**Csoportosít** típus. Jelenleg a következő összesítő funkciók támogatottak:

- **AVG** – Ez a függvény egy csoport értékeinek átlagát adja vissza. Csak numerikus mezőkkel használható.
- **SZÁMOL** – Ez a függvény a csoportban talált elemek számát adja vissza.
- **Min** – Ez a függvény a minimális értéket adja vissza a csoport értékei közül.
- **Max** – Ez a függvény a maximális értéket adja vissza a csoport értékei közül.
- **ÖSSZEG** – Ez a függvény egy csoport összes értékének összegét adja vissza. Csak numerikus mezőkkel használható.

## <a name="execution-location"></a><a name="ExecutionLocation"></a>Végrehajtás helye

Amikor szerkeszti a **Csoportosít** adatforrást és adja meg a csoportosítandó rekordokat tartalmazó alapadatforrást, a rendszer automatikusan felismeri a leghatékonyabb [elhelyezkedés](#ExecutionLocation) ennek végrehajtására **Csoportosít** adatforrás. Ha az alapadatforrás az [lekérdezhető](er-functions-list-filter.md#usage-notes) (vagyis ha adatbázis szinten futtatható), az alkalmazás adatbázisa is meg van adva a szerkeszthető végrehajtási helyeként **Csoportosít** adatforrás. Ellenkező esetben az alkalmazáskiszolgáló memóriája van megadva végrehajtási helyként.

Manuálisan módosíthatja az automatikusan észlelt végrehajtási helyet a konfigurált adatforrásra vonatkozó hely kiválasztásával. Ha a kiválasztott végrehajtási hely nem alkalmazható, a [érvényesítési hiba](er-components-inspections.md#i5) tervezési időre dobják.

> [!TIP]
> Javasoljuk, hogy az adatbázis helyét használja a nagy számú rekordot felfedő adatforrások csoportosítására.

## <a name="memory-consumption"></a><a name="MemoryConsumption"></a> Memória fogyasztás

Alapértelmezés szerint, ha a **Csoportosít** az adatforrás a memóriában fut, az alkalmazáskiszolgáló memóriája az egyes felderített csoportokhoz tartozó alapadatforrás rekordjainak egyetlen csoport rekordjaként való tárolására szolgál. A memóriafelhasználás csökkentése érdekében letilthatja a rekordok tárolását **Csoportosít** adatforrások, ha úgy vannak beállítva, hogy csak összesített függvényeket számítsanak ki, és a csoportjuk rekordjait nem használják futás közben. A memóriafelhasználás ilyen módon történő csökkentéséhez engedélyezze a **Csökkentse a memóriahasználatot az ER-ben, ha a rekordok csoportosítását csak aggregációk kiszámítására használják** funkció a **Funkciókezelés** munkaterület.

## <a name="alternatives"></a><a name="Alternatives"></a> Alternatívák

Hasonló aggregátumok számíthatók a használatával [különböző](er-data-collection-data-sources.md#if-i-have-to-calculate-running-totals-and-collect-data-what-is-the-difference-between-using-a-data-collection-data-source-and-using-the-built-in-data-collection-functions) típusú adatforrások vagy ER beépített függvények.

Ha többet szeretne megtudni erről a funkcióról, töltse ki az alábbi példát.

## <a name="example-use-a-groupby-data-source-for-aggregate-calculations-and-record-grouping"></a><a name="Example"></a> Példa: Használjon GROUPBY adatforrást összesített számításokhoz és rekordok csoportosításához

Ez a példa bemutatja, hogyan konfigurálhat egy rendszergazdai vagy elektronikus jelentési tanácsadói szerepet betöltő felhasználó egy olyan ER-modell-leképezést, amely rendelkezik **CSOPORTOSÍT** adatforrás, amely az összesített függvények és csoportrekordok kiszámítására szolgál. Ez a modellleképezés az Intrastat-nyilatkozat generálásakor az ellenőrzési jelentés kinyomtatására szolgál. Ez a jelentés lehetővé teszi a jelentett Intrastat-tranzakciók áttekintését.

Az ebben a példában szereplő eljárások a **DEMF** cég a Microsoftban Dynamics 365 Finance. 

### <a name="prepare-sample-data"></a>Mintaadatok készítése

Győződjön meg arról, hogy rendelkezik Intrastat-tranzakciókkal a jelentéskészítéshez **Intrastat** oldalon. Különböző szállítási kódokhoz kell tranzakciókat rendelnie, mert a tranzakciókat a szerint csoportosítja **Szállítás** mező ebben a példában.

![Intrastat tranzakciók előkészítése az Intrastat oldalon.](./media/er-groupby-data-sources-prepare-transactions.png)

### <a name="configure-the-er-framework"></a>ER-keretrendszer konfigurálása

Kövesse az [ER-keretrendszer konfigurálása](er-quick-start2-customize-report.md#ConfigureFramework) rész lépéseit az ER-paraméterek minimális készletének beállításához. Ezt a beállítást be kell fejeznie, mielőtt elkezdi használni az ER-keretrendszert az ER-modell-leképezés tervezésére.

### <a name="import-the-standard-er-format-configuration"></a>A szabvány ER-formátumkonfiguráció importálása

A [A szabvány ER-formátumkonfiguráció importálása](er-quick-start2-customize-report.md#ImportERSolution1) rész lépéseit követve adja hozzá a szabványos ER-konfigurációkat az aktuális Dynamics 365 Finance-példányhoz. Az 1. verzió importálása **Intrastat modell** konfigurációt a tárolóból.

### <a name="create-a-custom-data-model-configuration"></a>Hozzon létre egyéni adatmodell-konfigurációt

Kövesse a lépéseket [Adjon hozzá egyéni adatmodell-konfigurációt](er-quick-start3-customize-report.md#add-a-custom-data-model-configuration) új manuális hozzáadásához **Intrastat modell (Litware)** ER adatmodell-konfiguráció, amelyet az importáltból származtat **Intrastat modell** konfigurációt.

### <a name="configure-a-custom-data-model-component"></a>Egyéni adatmodell-összetevő konfigurálása

Kövesse ezeket a lépéseket a szükséges módosítások elvégzéséhez a származtatotton **Intrastat modell (Litware)** adatmodellt, hogy fel lehessen tárni a szükséges részletekkel rendelkező szállítási kódokat.

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon válassza ki a konfigurációs fában **Intrastat modell (Litware)**.
3. Válassza a **Tervező** lehetőséget.
4. A **Adatmodell tervező** oldalon válassza ki a modellfában **Intrastat**.
5. Válassza ki **Új** új beágyazott csomópont hozzáadásához a kiválasztotthoz **Intrastat** csomópont. Az adatmodell csomópontjainak hozzáadására szolgáló legördülő párbeszédpanelen hajtsa végre az alábbi lépéseket:

    1. Ban,-ben **Név** mezőbe írja be **Szállítás**.
    2. A **Cikktípus** mezőben válassza ki a **Rekordlista** lehetőséget.
    3. Új csomópont hozzáadásához kattintson a **Hozzáadás** lehetőségre.

6. Válassza ki **Új** új beágyazott csomópont hozzáadásához a **Szállítás** az imént hozzáadott csomópont. Az adatmodell csomópontjainak hozzáadására szolgáló legördülő párbeszédpanelen hajtsa végre az alábbi lépéseket:

    1. Ban,-ben **Név** mezőbe írja be **Kód**.
    2. A **Cikktípus** mezőben válassza ki a **Karakterlánc** lehetőséget.
    3. Új csomópont hozzáadásához kattintson a **Hozzáadás** lehetőségre.

7. Válassza ki **Új** további új beágyazott csomópont hozzáadásához a **Szállítás** csomópont. Az adatmodell csomópontjainak hozzáadására szolgáló legördülő párbeszédpanelen hajtsa végre az alábbi lépéseket:

    1. Ban,-ben **Név** mezőbe írja be **TotalInvoicedAmount**.
    2. A **Cikktípus** mezőben válassza ki a **Valós** lehetőséget.
    3. Új csomópont hozzáadásához kattintson a **Hozzáadás** lehetőségre.

8. Válassza ki **Új** további új beágyazott csomópont hozzáadásához a **Szállítás** csomópont. Az adatmodell csomópontjainak hozzáadására szolgáló legördülő párbeszédpanelen hajtsa végre az alábbi lépéseket:

    1. Ban,-ben **Név** mezőbe írja be **Tranzakciók száma**.
    2. A **Cikktípus** mezőben válassza ki az **Egész szám** lehetőséget.
    3. Új csomópont hozzáadásához kattintson a **Hozzáadás** lehetőségre.

9. Válassza ki **Új** további új beágyazott csomópont hozzáadásához a **Szállítás** csomópont. Az adatmodell csomópontjainak hozzáadására szolgáló legördülő párbeszédpanelen hajtsa végre az alábbi lépéseket:

    1. Ban,-ben **Név** mezőbe írja be **Tranzakció**.
    2. A **Cikktípus** mezőben válassza ki a **Rekordlista** lehetőséget.
    3. Új csomópont hozzáadásához kattintson a **Hozzáadás** lehetőségre.

10. A **Tranzakció** az imént hozzáadott csomópont a **Csomópont** FastTab, válassza ki **Tételreferencia váltása**.
11. Ban,-ben **Tételreferencia váltása** párbeszédpanelen az adatmodell-fában válassza ki **CommodityRecord**. Majd kattintson az **OK** lehetőségre.

![Konfigurált adatmodell az ER-adatmodell tervezőjében.](./media/er-groupby-data-sources-configure-data-model.png)

### <a name="complete-the-design-of-a-custom-data-model"></a>Fejezze be az egyéni adatmodell tervezését

Kövesse a lépéseket [Fejezze be az adatmodell tervezését](er-quick-start3-customize-report.md#add-a-custom-data-model-configuration) hogy befejezze a származtatott tervezését **Intrastat modell (Litware)** adatmodell.

### <a name="create-a-new-model-mapping-configuration"></a>Új modell-leképezési konfiguráció létrehozása

Kövesse a lépéseket [Hozzon létre egy új modellleképezési konfigurációt](er-quick-start1-new-solution.md#CreateModelMapping) új manuális hozzáadásához **Intrastat mintatérképezés** ER-modell leképezési konfigurációja a származtatotthoz **Intrastat modell (Litware)** konfigurációt.

### <a name="add-a-new-model-mapping-component"></a>Adjon hozzá egy új modellleképezési összetevőt

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon a konfigurációs fában bontsa ki a **Intrastat modell** konfigurációt.
3. Válaszd ki a **Intrastat mintatérképezés** konfigurációt.
4. Válassza ki a **Tervezőt** a leképezések listájának megnyitásához.
5. Válassza ki **Töröl** a meglévő leképezési komponens eltávolításához.
6. Válassza ki **Új** új leképezési komponens hozzáadásához.
7. Ban,-ben **Meghatározás** mezőben válassza ki **Intrastat**.
8. Ban,-ben **Név** mezőbe írja be **Intrastat térképezés**.
9. Válassza ki **Tervező** az új leképezés konfigurálásához.

### <a name="design-the-added-model-mapping-component"></a>Tervezze meg a hozzáadott modellleképezési komponenst

#### <a name="add-a-data-source-to-access-an-application-table"></a><a name="AddMmDataSource1"></a> Adjon hozzá adatforrást az alkalmazástáblázat eléréséhez

Konfiguráljon adatforrást az Intrastat-tranzakciók részleteit tartalmazó alkalmazástáblázatok eléréséhez.

1. A **Modell-leképezés tervező** oldal **Adatforrástípusok** paneljén válassza a **Dynamics 365 for Operations\\Táblarekordok** lehetőséget.
2. Ban,-ben **Adatforrások** ablaktáblát, válassza ki **Gyökér hozzáadása** új adatforrás hozzáadásához, amelyet a hozzáféréshez használunk **Intrastat** asztal. Minden rekord a **Intrastat** táblázat egyetlen Intrastat-tranzakciót jelent.
3. Ban,-ben **Adatforrás tulajdonságai** párbeszédpanelen, a **Név** mezőbe írja be **Tranzakció**.
4. Ban,-ben **asztal** mezőbe írja be **Intrastat**.
5. Az új adatforrás hozzáadásához kattintson az **OK** gombra.

#### <a name="add-a-data-source-to-group-intrastat-transactions"></a><a name="AddMmDataSource2"></a> Adatforrás hozzáadása az Intrastat-tranzakciók csoportosításához

**GroupBy** adatforrás konfigurálása intrastat tranzakciók csoportosítására és számítási összesítési függvények kiszámítására.

1. **A Modellleképezés tervező** lapján az Adatforrástípusok **ablaktáblán válassza a** FunctionsGroup **by\\ lehetőséget**.
2. Az Adatforrások **ablaktáblán válassza a** Gyökér **hozzáadása lehetőséget** egy új adatforrás hozzáadásához, amely az Intrastat-tranzakciók csoportosítására és az összesítési függvények kiszámítására szolgál.
3. **Az Adatforrás tulajdonságai** párbeszédpanel Név **mezőjében írja be a** TransportRecord **parancsot**.
4. A csoportosítási feltételek konfigurálásához válassza **a Csoport** szerkesztése lehetőséget.
5. **A "Csoportosítás" paraméterek szerkesztése lapon, a jobb oldali ablaktábla adatforrások listájában jelölje ki a** Tranzakció **adatforrást, és bontsa** ki.
6. Válassza a Hozzáadás mező lehetőséget **a Csoportosításhoz \> lehetőséget annak jelzésére, hogy a** Tranzakció **adatforrás a konfigurált** GroupBy <a name="BaseDataSource">adatforrás alap adatforrásaként</a>**van** kiválasztva. A tranzakció **adatforrásának rekordjai** csoportosítva lesznek, és ennek az adatforrásnak a mezőértékeit az összesített függvények számításaihoz használjuk.
7. Jelölje be a Tranzakció\Átvitel mezőt, majd válassza a **Mező hozzáadása a** Csoportosított mezőhöz **lehetőséget \> annak jelzésére, hogy az** alap adatforrás Átviteli **mezője van kiválasztva a** konfigurált <a name="GroupingFields">GroupBy</a> adatforrás csoportosítási feltételeként **.** Más szóval, a Tranzakció **adatforrás rekordjai a** Szállítás **mező értéke** alapján lesznek csoportosítva. A konfigurált **GroupBy** adatforrás minden rekordja egyetlen átviteli kódot fog képviselni, amely az alap adatforrás rekordjaiban található.
8. Jelölje ki a **Tranzakció\AmountMST** mezőt, majd kövesse az alábbi lépéseket:

    1. Válassza a Mező hozzáadása az Összesítés mezőkhöz **\> lehetőséget** annak jelzésére, hogy <a name="AggregateFunctions">ehhez a mezőhöz összesítő függvény</a> kerül kiszámításra.
    2. **Az Összesítések** ablaktáblán a kijelölt **Tranzakció\AmountMST** mezőhöz hozzáadott rekordban a **Módszer** mezőben jelölje ki az **Összeg** függvényt.
    3. A Név **választható mezőbe írja be** a **TotalInvoicedAmount parancsot**.

    Ezek a beállítások azt határozzák meg, hogy minden átviteli csoport esetében a rendszer kiszámítja a **Tranzakció\AmountMST** mező teljes összegét.

9. Jelölje ki a **Tranzakció\RecId** mezőt, majd kövesse az alábbi lépéseket:

    1. Válassza a Mező hozzáadása az Összesítés mezőkhöz **\> lehetőséget** annak jelzésére, hogy ehhez a mezőhöz összesítő függvény kerül kiszámításra.
    2. **Az Összesítések** ablaktáblán a kijelölt **Tranzakció\RecId** mezőhöz hozzáadott rekordban a **Módszer** mezőben jelölje ki a **Számolás** függvényt.
    3. A Név **választható mezőbe írja be** a **NumberOfTransactions parancsot**.

    Ezek a beállítások azt határozzák meg, hogy minden átviteli csoport esetében a rendszer kiszámítja a csoport tranzakcióinak számát.

10. Válassza a **Mentés** lehetőséget.
11. Tekintse át a <a name="ExecutionLocation">szerkeszthető adatforrás végrehajtási</a> paramétereit. Figyelje meg, hogy **az Automatikus rajz automatikusan** ki van választva a **Végrehajtás hely** mezőben, és a **Végrehajtás a** mezőben az SQL **értéket** tartalmazza. Ezek a beállítások azt a megadását határozzák meg, hogy a kiválasztott **Tranzakciós** alap adatforrás jelenleg lekérdezhető, és a szerkeszthető **GroupBy** adatforrást adatbázis szinten is futtathatja.
12. Nyissa meg a **Végrehajtás helymező** keresését a rendelkezésre álló értékek listájának áttekintéséhez. Figyelje meg, hogy a Lekérdezés **vagy** a Memóriában **lehetőséget választva** kényszerítheti ezt **a GroupBy** adatforrást az adatbázis szintjén vagy az alkalmazáskiszolgáló memóriájában való futtatására.
13. Válassza a Mentés **lehetőséget**, és zárja be a **"Csoportosítás szerint" paraméterek** szerkesztése lapot.
14. A GroupBy **adatforrás beállításainak végrehajtásához válassza az** OK **lehetőséget**.

#### <a name="bind-the-groupby-data-source-to-data-model-fields"></a><a name="AddMmBindings"></a> A GroupBy adatforrás kötése adatmodell mezőkhöz

A konfigurált adatforrást az adatmodell mezőihez köti, hogy megadhatja, hogy az adatmodell hogyan lesz kitöltve alkalmazásadatokkal futásidőben.

1. **A Modellleképezés tervező** lapján, az **Adatmodell** ablaktáblán bontsa ki az **Átviteli** csomópontot.
2. **Az Adatforrások** ablaktáblán bontsa ki a **TransportRecord adatforrást**.
3. Kötés hozzáadása a felderített átviteli csoportok listájának elérhetővé tegyék:

    1. **Az Adatmodell** ablaktáblán jelölje ki a **Szállítás** elemet.
    2. **Az Adatforrások** ablaktáblán válassza a **TransportRecord adatforrást**.
    3. Válassza a **Bind** elemet.

4. Kötés hozzáadása az egyes felderített szállítási csoportok szállítási kódjának elérhetővé tegyék:

    1. Válassza ki a **Transport.Code** adatmodell elemet.
    2. Válassza a **TransportRecord.grouped.TransportMode** csoportosított mezőt.
    3. Válassza a **Bind** elemet.

5. Kötés hozzáadása az egyes felderített szállítási csoportok számított összesítő függvényeinek értékeinek elérhetővé ítéséhez:

    1. Válassza a **Transport.NumberOfTransactions** adatmodellelemet.
    2. Válassza a **TransportRecord.aggregated.NumberOfTransactions** összesített mezőt.
    3. Válassza a **Bind** elemet.
    4. Válassza a **Transport.TotalInvoicedAmount** adatmodellelemet.
    5. Válassza ki a **TransportRecord.aggregated.TotalInvoicedAmount** összesített mezőt.
    6. Válassza a **Bind** elemet.

6. Kötés hozzáadása az egyes felderített átviteli csoportokhoz tartozó tranzakciórekordok felfedésére:

    1. Válassza a **Transport.Transaction** adatmodell elemet.
    2. Jelölje be a **TransportRecord.lines** mezőt.
    3. Válassza a **Bind** elemet.

    Továbbra is konfigurálhatja a Transport.Transaction **adatmodell cikk és a** **TransportRecord.lines** adatforrás mező beágyazott elemeihez tartozó kötéseket, hogy futásidőben felfedje az egyes felderített átviteli csoportokhoz tartozó Intrastat-tranzakciók részleteit.

![Konfigurált modell-leképezés az ER-modell leképezésének tervezőjében.](./media/er-groupby-data-sources-configure-model-mapping.png)

### <a name="debug-the-added-model-mapping-component"></a>A hozzáadott modellleképezési összetevő hibakeresése

[Az ER adatforrás-hibakeresővel](er-debug-data-sources.md) tesztelje a konfigurált modellleképezést.

1. A Modellleképezés tervező **lapján válassza a** Hibakeresés **indítása lehetőséget**.
2. **A Debug adatforrások** lap bal oldali ablaktáblájában jelölje ki a TransportRecord adatforrást **, majd válassza az** Összes rekord **olvasása lehetőséget**.
3. Bontsa ki a **TransportRecord adatforrást**, majd kövesse az alábbi lépéseket:

    1. Válassza a **TransportRecord.grouped.TransportMode** adatforrást.
    2. Válassza ki az **Érték beolvasása** lehetőséget.
    3. Válassza a **TransportRecord.grouped.NumberOfTransactions** adatforrást.
    4. Válassza ki az **Érték beolvasása** lehetőséget.
    5. Válassza a **TransportRecord.grouped.TotalInvoicedAmount adatforrást**.
    6. Válassza ki az **Érték beolvasása** lehetőséget.

4. A jobb oldali ablaktáblában válassza az Összes **kibontása lehetőséget**.

A **TransportRecord** adatforrás két rekordot tesz közzé, és két szállítási kódot mutat be. A rendszer minden szállítási kód esetében kiszámítja a tranzakciók számát és a teljes számlázott összeget.

> [!NOTE]
> A "lusta olvasás" megközelítést akkor használja a csoport, **amely adatforrást** hív meg az adatbázishívások optimalizálására. Ezért a **GroupBy** adatforrás egyes mezőértékeit csak akkor számítja ki a rendszer az ER adatforrás-hibakeresőben, ha adatmodellmezőkhöz vannak kötve.

![Az adatforrás hibakeresésének eredményei a Debug adatforrások lapon.](./media/er-groupby-data-sources-debug-datasource.png)

## <a name="frequently-asked-questions"></a>Gyakori kérdések

### <a name="is-there-any-way-to-calculate-grand-totals-when-the-group-totals-are-calculated"></a>Van-e mód a végösszegek kiszámítására a csoportösszegek kiszámításakor?

Igen. A végösszegek kiszámításához konfiguráljon egy másik **GroupBy** adatforrást, ahol a **korábban konfigurált GroupBy** adatforrást használja alap adatforrásként. A következő ábrán látható a **Összesen** adatforrása **Csoportosít** típus, amelyet az aggregátum kiszámításához használnak **ÖSSZEG** függvény alapján a **ÖSSZEG** összesítése a **TransportRecord** adatforrása **Csoportosít** típus.

![Összesíti az adatforrást az ER-modell-leképezés tervezőjében.](./media/er-groupby-data-sources-configure-model-mapping2.png)

Az alábbi ábra a **Összesen** adatforrás hibakeresés.

![Az Összes adatforrások hibakeresésének eredményei az Adatforrások hibakeresése oldalon.](./media/er-groupby-data-sources-debug-datasource2.png)

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus jelentések áttekintése](general-electronic-reporting.md)
- [Egy végrehajtott ER formátum hibakeresési adatforrásai az adatfolyam elemzéséhez és átalakításához](er-debug-data-sources.md)
- [Adatgyűjtési adatforrások használata elektronikus jelentési formátumokban](er-data-collection-data-sources.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
