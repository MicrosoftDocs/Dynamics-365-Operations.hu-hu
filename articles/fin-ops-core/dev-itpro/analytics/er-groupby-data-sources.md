---
title: Rekordok csoportosítása és számítások összesítése GROUPBY adatforrások használatával
description: Ez a cikk bemutatja, hogy hogyan használhatók a GROUPBY típusú adatforrások az elektronikus jelentéskészítésben (ER).
author: NickSelin
ms.date: 03/18/2022
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
ms.openlocfilehash: 7b20b5db0794157560f27f15594a84083966642f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861787"
---
# <a name="group-records-and-aggregate-calculations-by-using-groupby-data-sources"></a>Rekordok csoportosítása és számítások összesítése GROUPBY adatforrások használatával

[!include[banner](../includes/banner.md)]

Az Elektronikus jelentéskészítés [(ER)](general-electronic-reporting.md) modellleképezések és -formátumok konfigurálása [során](#AddMmDataSource2)**hozzáadhatja a GroupBy típusú szükséges adatforrásokat.**

A tervezés során egy **GroupBy** adatforrás úgy van beállítva, hogy azonosítsa a következő elemeket:

- Olyan [alapadatforrás,](#BaseDataSource) amely futásidőben csoportosított rekordokat tartalmaz.
- [Az alapadatforrás](#GroupingFields) csoportosítási mezői, amelyeket a rendszer futásidőben való rekordcsoportozáshoz használ
- [Összesítő](#AggregateFunctions) függvények, amelyek az egyes fedezett csoportokhoz futásidőben elvégzett összesítő számításokat határozzák meg.

Futásidőben egy **konfigurált GroupBy** adatforráscsoport olyan rekordot tartalmaz, amelynek azonos az értéke a csoportosítási mezőkben, majd visszaadja a rekordok listáját. Minden rekord egy csoportot képvisel. Az adatforrás minden csoportnál elérhetővé teszi a kezdeti rekordok által csoportosított mezőértékeket, a számított összesítő függvények értékeit és a csoporthoz tartozó alapadatforrás rekordjainak listáját.

## <a name="aggregate-functions"></a><a name="AggregateFunctions"></a> Összesítő függvények

Futási időben minden egyes rekordcsoportra minden összesítési számítást végez. Ez a számítás egyetlen mező vagy kifejezés értékével történik egy olyan adatforrás rekordjaiban, amelyet a **GroupBy** típus szerkeszthető adatforrásában való csoportosításra kiválasztott. A következő összesítő függvények jelenleg támogatottak:

- **AVG** – ez a funkció egy csoportérték átlagát adja eredményül. Csak numerikus mezőkkel használható.
- **SZÁM** – ez a funkció a csoportban található cikkek számát adja eredményül.
- **Min** . – ez a funkció a csoport értékei közötti minimális értéket adja eredményül.
- **Max** . – ez a függvény egy csoport értékeinek maximális értékét adja eredményül.
- **SUM** – ez a funkció egy csoport értékeinek összegét adja eredményül. Csak numerikus mezőkkel használható.

## <a name="execution-location"></a><a name="ExecutionLocation"></a>Végrehajtás helye

Amikor szerkeszt **egy GroupBy adatforrást, és megadja a csoportosítni kívánt rekordokat tartalmazó alapadatforrást,**[a](#ExecutionLocation) rendszer automatikusan észleli a GroupBy **adatforrás** végrehajtásának leghatékonyabb helyét. Ha az alap adatforrás [lekérdezhető](er-functions-list-filter.md#usage-notes) (azaz az adatbázis szintjén futtatható), **akkor az alkalmazásadatbázis is meg van adva a szerkeszthető GroupBy adatforrás végrehajtási** helyeként. Ellenkező esetben az alkalmazáskiszolgáló memóriája van megadva végrehajtási helyként.

Manuálisan módosíthatja az automatikusan észlelt végrehajtási helyet a konfigurált adatforrásra vonatkozó hely kiválasztásával. Ha a kiválasztott végrehajtási hely nem alkalmazható, akkor a rendszer a [tervezéskor](er-components-inspections.md#i5) érvényesítési hibát jelez.

> [!TIP]
> Javasoljuk, hogy az adatbázis helyével csoportosítsa a sok rekordot elérhető adatforrásokat.

## <a name="memory-consumption"></a><a name="MemoryConsumption"></a> Memóriafelhasználás

Ha egy GroupBy **adatforrást a** memóriában futtat, akkor az alkalmazáskiszolgáló memóriája az alap adatforrás rekordjainak tárolására szolgál, amelyek az egyes fedezett csoportokhoz tartoznak, egyetlen csoport rekordjaiként. A memóriafelhasználás **csökkentése érdekében elrejtheti a GroupBy** adatforrások rekordtárolását, ha úgy van beállítva, hogy csak összesített függvényeket számítsa ki, és a csoport rekordjai nincsenek futásidőben használatban. Ha ezzel a módszerel csökkenteni szeretné a memóriafelhasználást, **engedélyezze a Memóriafelhasználás csökkentése az ER** **beállításban, ha a rekordcsoportozás csak a Funkciókezelési munkaterület összesítési funkciójának** kiszámítására használható.

## <a name="alternatives"></a><a name="Alternatives"></a> Alternatívák

A hasonló összesítések többféle adatforrás [vagy](er-data-collection-data-sources.md#if-i-have-to-calculate-running-totals-and-collect-data-what-is-the-difference-between-using-a-data-collection-data-source-and-using-the-built-in-data-collection-functions) az ER beépített funkciók használatával is kiszámíthatók.

Ha többet szeretne megtudni erről a funkcióról, töltse ki az alábbi példát.

## <a name="example-use-a-groupby-data-source-for-aggregate-calculations-and-record-grouping"></a><a name="Example"></a> Példa: EGY GROUPBY adatforrás használata az összesítési számításokhoz és a rekordcsoportozáshoz

A példa bemutatja, hogy a rendszergazdai vagy elektronikus jelentéskészítési funkcionális tanácsadói szerepkörű felhasználók hogyan konfigurálhatnak egy OLYAN ER-modellleképezést **, amelynek GROUPBY** adatforrása az összesítő függvények és a csoportrekordok kiszámítására használható. Ezzel a modellleképezéssel nyomtatható ki az ellenőrző jelentés az Intrastat-nyilatkozat generálása során. Ezzel a jelentéssel áttekintheti a jelentett Intrastat-tranzakciókat.

Az ebben a példában alkalmazott eljárások a **DEMF** Microsoft Dynamics vállalatnál, a 365 Pénzügyben használhatja. 

### <a name="prepare-sample-data"></a>Mintaadatok előkészítése

Győződjön meg róla, hogy vannak Intrastat-tranzakciók jelentéshez az **Intrastat** lapon. A tranzakcióknak különböző szállítási kódokhoz kell tartozikuk, **mivel** ebben a példában a Szállítás mező szerint fogja csoportosítni a tranzakciókat.

![Intrastat-tranzakciók előkészítése az Intrastat lapon.](./media/er-groupby-data-sources-prepare-transactions.png)

### <a name="configure-the-er-framework"></a>ER-keretrendszer konfigurálása

Kövesse az [ER-keretrendszer konfigurálása](er-quick-start2-customize-report.md#ConfigureFramework) rész lépéseit az ER-paraméterek minimális készletének beállításához. Ezt a beállítást be kell fejeznie, mielőtt az ER keretrendszert használva er modellleképezést tervez.

### <a name="import-the-standard-er-format-configuration"></a>A szabvány ER-formátumkonfiguráció importálása

A Szabványos ER [formátumkonfiguráció](er-quick-start2-customize-report.md#ImportERSolution1) importálása lépéseit követve adja hozzá a normál ER-konfigurációkat a Dynamics 365 Pénzügy aktuális példányához. Importálja az Intrastat-modell **konfigurációjának 1**. verzióját a tárházból.

### <a name="create-a-custom-data-model-configuration"></a>Egyéni adatmodell-konfiguráció létrehozása

Hajtsa végre az Egyéni adatmodell-konfiguráció [...](er-quick-start3-customize-report.md#add-a-custom-data-model-configuration)**hozzáadása lépést az új Intrastat-modell (Litware)** ER-adatmodell-konfiguráció **kézi hozzáadásához, amely az importált Intrastat modell konfigurációból származik**.

### <a name="configure-a-custom-data-model-component"></a>Egyéni adatmodell-összetevő konfigurálása

A következő lépések szerint hajtsa **végre a szükséges módosításokat a származtatott Intrastat-modell (Litware)** adatmodellben, hogy felhasználható legyen a szükséges adatokat tartalmazó szállítási kódokban.

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A Konfigurációk **lapon**, a konfigurációs fában válassza ki az **Intrastat-modellt (litware)**.
3. Válassza a **Tervező** lehetőséget.
4. Az Adatmodell-tervező **lapon**, a modellfában válassza ki az **Intrastat adatokat**.
5. Válassza az **Új** lehetőséget, ha új beágyazott csomópontot szeretne hozzáadni a kiválasztott **Intrastat-csomóponthoz**. Az adatmodell csomópontjainak hozzáadására szolgáló legördülő párbeszédpanelen hajtsa végre az alábbi lépéseket:

    1. A Név **mezőben** adja meg a Szállítás **mezőt**.
    2. A **Cikktípus** mezőben válassza ki a **Rekordlista** lehetőséget.
    3. Új csomópont hozzáadásához kattintson a **Hozzáadás** lehetőségre.

6. Válassza **az Új** lehetőséget, ha új beágyazott csomópontot szeretne hozzáadni **az éppen hozzáadott Átviteli** csomóponthoz. Az adatmodell csomópontjainak hozzáadására szolgáló legördülő párbeszédpanelen hajtsa végre az alábbi lépéseket:

    1. A Név **mezőben** adja meg a **kódot**.
    2. A **Cikktípus** mezőben válassza ki a **Karakterlánc** lehetőséget.
    3. Új csomópont hozzáadásához kattintson a **Hozzáadás** lehetőségre.

7. Az **Új lehetőség** kiválasztásával egy másik beágyazott csomópontot adhat hozzá a Szállítás **csomóponthoz**. Az adatmodell csomópontjainak hozzáadására szolgáló legördülő párbeszédpanelen hajtsa végre az alábbi lépéseket:

    1. A Név **mezőbe** írja be a **TotalInvoicedAmount mezőt**.
    2. A **Cikktípus** mezőben válassza ki a **Valós** lehetőséget.
    3. Új csomópont hozzáadásához kattintson a **Hozzáadás** lehetőségre.

8. Az **Új lehetőség** kiválasztásával egy másik beágyazott csomópontot adhat hozzá a Szállítás **csomóponthoz**. Az adatmodell csomópontjainak hozzáadására szolgáló legördülő párbeszédpanelen hajtsa végre az alábbi lépéseket:

    1. A Név **mezőbe** írja be a **NumberOfTransactions mezőt**.
    2. A **Cikktípus** mezőben válassza ki az **Egész szám** lehetőséget.
    3. Új csomópont hozzáadásához kattintson a **Hozzáadás** lehetőségre.

9. Az **Új lehetőség** kiválasztásával egy másik beágyazott csomópontot adhat hozzá a Szállítás **csomóponthoz**. Az adatmodell csomópontjainak hozzáadására szolgáló legördülő párbeszédpanelen hajtsa végre az alábbi lépéseket:

    1. A Név **mezőben** adja meg a **Tranzakciót**.
    2. A **Cikktípus** mezőben válassza ki a **Rekordlista** lehetőséget.
    3. Új csomópont hozzáadásához kattintson a **Hozzáadás** lehetőségre.

10. Az előbb **hozzáadott Transaction** csomóponthoz válassza **a Csomópont** gyorsét, **és válassza a Switch cikkhivatkozást**.
11. A Cikkhivatkozás **váltása** párbeszédpanel adatmodellfában válassza a **CommodityRecord elemet**. Majd kattintson az **OK** lehetőségre.

![Konfigurált adatmodell az ER-adatmodell tervezőjében.](./media/er-groupby-data-sources-configure-data-model.png)

### <a name="complete-the-design-of-a-custom-data-model"></a>Egyéni adatmodell tervének befejezése

Hajtsa végre az [adatmodell](er-quick-start3-customize-report.md#add-a-custom-data-model-configuration) **tervezésének lépéseit a származtatott Intrastat-modell (Litware)** adatmodell tervének befejezéséhez.

### <a name="create-a-new-model-mapping-configuration"></a>Új modell-leképezési konfiguráció létrehozása

Kövesse az új [modellleképezési](er-quick-start1-new-solution.md#CreateModelMapping) konfiguráció létrehozása lépést, ha kézzel hozzá szeretne adni egy új Intrastat-minta-hozzárendelési **ER-modellkonfigurációt** a **származtatott Intrastat-modell (Litware) konfigurációhoz**.

### <a name="add-a-new-model-mapping-component"></a>Új modellleképezési összetevő hozzáadása

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A Konfigurációk **lapon**, a konfigurációs fában bontsa ki az **Intrastat-modell konfigurációját**.
3. Válassza ki az **Intrastat minta-hozzárendelés konfigurációját**.
4. Válassza ki a **Tervezőt** a leképezések listájának megnyitásához.
5. Válassza a **Törlés** lehetőséget, ha el szeretné távolítani a meglévő hozzárendelési összetevőt.
6. Új hozzárendelési **összetevő** hozzáadásához válassza az Új lehetőséget.
7. A Definíció **mezőben** válassza az **Intrastatt**.
8. A Név **mezőben** adja meg az **Intrastat megfeleltetést**.
9. Az új **hozzárendelés** konfiguráléséhez válassza a Tervező lehetőséget.

### <a name="design-the-added-model-mapping-component"></a>A hozzáadott modellleképezési összetevő tervezése

#### <a name="add-a-data-source-to-access-an-application-table"></a><a name="AddMmDataSource1"></a> Adatforrás hozzáadása az alkalmazástáblák eléréséhez

Konfiguráljon egy adatforrást az Intrastat-tranzakciók adatait tartalmazó alkalmazástáblák eléréséhez.

1. A **Modell-leképezés tervező** oldal **Adatforrástípusok** paneljén válassza a **Dynamics 365 for Operations\\Táblarekordok** lehetőséget.
2. Az Adatforrások **ablakban** válassza **a** **Gyökér hozzáadása lehetőséget az Intrastat tábla elérésére használt új adatforrás hozzáadásához**. Az Intrastat tábla minden **rekordja** egyetlen Intrastat-tranzakciót képvisel.
3. Adja meg **a** **Tranzakciót az Adatforrás tulajdonságai párbeszédpanel Név** mezőjében **·**.
4. A Tábla **mezőbe** írja be az **Intrastat mezőt**.
5. Az új adatforrás hozzáadásához kattintson az **OK** gombra.

#### <a name="add-a-data-source-to-group-intrastat-transactions"></a><a name="AddMmDataSource2"></a> Adatforrás hozzáadása az Intrastat-tranzakciók csoportosítására

**GroupBy** adatforrás konfigurálása az Intrastat-tranzakciók csoportosítására és az összesítő függvények kiszámítására.

1. A **Modellleképezés tervezőlap** **Adatforrástípusok ablakában** válassza a **Functions\\Group by** lehetőséget.
2. Az Adatforrások **ablakban** **válassza** a Gyökér hozzáadása lehetőséget egy új adatforrás hozzáadásához, amely az Intrastat-tranzakciók csoportosítására és az összesítő függvények kiszámítására használható.
3. Az Adatforrás **tulajdonságai párbeszédpanel** **Név** mezőjébe írja be a **TransportRecord adatokat.**
4. Válassza a **Csoportosítás szerkesztése csoportosítási** feltételek beállítását.
5. Válassza ki **a Tranzakció adatforrását** **·**, és bontsa ki a "Csoportosítás szerint" paramétereket tartalmazó lapon, a jobb oldali ablakban található adatforráslistán.
6. Válassza a Hozzáadás mezőt a Micsoporthoz **\>** **·**<a name="BaseDataSource">mezőben, ezzel jelezve, hogy a konfigurált GroupBy adatforrás alapadatforrásának a Tranzakció adatforrása van</a> kijelölve.**·** A rendszer csoportosítja **a tranzakció** adatforrásának rekordjait, és ennek az adatforrásnak a mezőértékeit fogja használni az összesítő függvények számításaiban.
7. Jelölje be a **Tranzakció\Átvitel** mezőt, majd válassza a **Mező hozzáadása a\> Csoportosított mezőhöz** lehetőséget  annak jelzésére, hogy az alap adatforrás **Átviteli** <a name="GroupingFields">mezője van kiválasztva an</a> konfigurált **GroupBy** adatforrás csoportosítási feltételeként. Más szóval **a** **Tranzakció adatforrás rekordjai a Szállítás mező értéke alapján lesznek csoportosítva.** A konfigurált **GroupBy** adatforrás minden rekordja egyetlen átviteli kódot képvisel, amely megtalálható az alap adatforrás rekordjaiban.
8. Jelölje ki **a Transaction\AmountMST mezőt**, majd hajtsa végre a következő lépéseket:

    1. Az **Összesítő mezők hozzáadása \>** mező kiválasztásával jelezheti, hogy ehhez a mezőhöz ki lesz számítva egy <a name="AggregateFunctions">összesítő függvény</a>.
    2. Az Összesítés **ablak** **Tranzakció\AmountMST** **·** **mezőjéhez hozzáadott rekord Metódus mezőben válassza az Összeg funkciót.**
    3. A Név **(nem** kötelező) mezőbe írja be az **TotalInvoicedAmount paramétert**.

    Ezek a beállítások határozzák meg, **hogy minden szállítási csoportnál ki legyen számítva a Transaction\AmountMST** mező teljes összege.

9. Jelölje ki **a Transaction\RecId mezőt**, majd hajtsa végre a következő lépéseket:

    1. Az **Összesítő mezők hozzáadása \>** mező kiválasztásával jelezheti, hogy ehhez a mezőhöz ki lesz számítva egy összesítő függvény.
    2. Válassza a **Számlálás funkciót az Összesítés ablakTábla** **Tranzakció\RecId** **·** **mezőhöz hozzáadott rekordban.**
    3. A Név (**nem** kötelező) mezőbe írja be a **NumberOfTransactions paramétert**.

    Ezek a beállítások határozzák meg, hogy minden szállítási csoportnál ki legyen számítva a csoport tranzakcióinak száma.

10. Válassza a **Mentés** lehetőséget.
11. Tekintse át <a name="ExecutionLocation">a szerkeszthető</a> adatforrás végrehajtási paramétereit. Ne figyelje meg **, hogy az Automatikus kijelölés** **automatikusan** be van jelölve a Végrehajtási hely mezőben, **és a Végrehajtás itt** mezőben az SQL érték **található.** Ezek a beállítások határozzák **meg**, hogy a kijelölt tranzakció alapadatforrása jelenleg lekérdezhető legyen, **és adatbázisszinten futtatható a szerkeszthető GroupBy** adatforrás.
12. A Rendelkezésre álló értékek listájának ellenőrzésához **nyissa** meg a Végrehajtás hely mező keresését. Ne feledje, hogy **a Lekérdezés** **·** **vagy a Memóriában beállítás meghatétosodhat arra, hogy ez a GroupBy** adatforrás az adatbázis szintjén vagy az alkalmazáskiszolgáló memóriájában fusson.
13. Válassza **a Mentés** lehetőséget, és zárja be **a "Csoportosítás szerint" paraméterek szerkesztése lapot**.
14. A **GroupBy** adatforrás beállításainak **befejezéséhez kattintson az OK** gombra.

#### <a name="bind-the-groupby-data-source-to-data-model-fields"></a><a name="AddMmBindings"></a> A GroupBy adatforrás kötése az adatmodell-mezőkhöz

A konfigurált adatforrást az adatmodell mezőihez kötve adhatja meg, hogyan legyen kitöltve az adatmodell futásidőben az alkalmazás adataival.

1. Bontsa ki **a** Szállítás csomópontot **a Modellleképezés tervezőlap Adatmodell** **ablakában**.
2. Az Adatforrások **ablakban** bontsa ki **a TransportRecord** adatforrást.
3. Kötés hozzáadása a fedezett szállítási csoportok listájának elérhetővé teszi:

    1. Az Adatmodell **ablakban** válassza ki a **Szállítás** elemet.
    2. Az Adatforrások **ablakban** válassza ki **a TransportRecord** adatforrást.
    3. Válassza a **Bind** elemet.

4. Adjon meg egy kötést, hogy elérhetővé tegye az egyes fedezett szállítási csoportok szállítási kódját:

    1. Válassza ki **a Transport.Code** adatmodellelemet.
    2. Válassza ki **a TransportRecord.grouped.TransportMode** csoportosított mezőt.
    3. Válassza a **Bind** elemet.

5. Kötés hozzáadása a kiszámított összesítő függvények értékeinek elérhetővé teszi az egyes fedezett szállítási csoportokhoz:

    1. Válassza ki **a Transport.NumberOfTransactions** adatmodellelemet.
    2. Válassza ki **a TransportRecord.aggregated.NumberOfTransactions** összesített mezőt.
    3. Válassza a **Bind** elemet.
    4. **A Transport.TotalInvoicedAmount adatmodell** cikkének kiválasztása.
    5. Jelölje be **a TransportRecord.aggregated.TotalInvoicedAmount** összesített mezőt.
    6. Válassza a **Bind** elemet.

6. Kötés hozzáadása az egyes fedezett átviteli csoportokhoz tartozó tranzakciórekordok megjelenítése érdekében:

    1. Válassza ki **a Transport.Transaction** adatmodellcikket.
    2. Válassza ki **a TransportRecord.Lines mezőt**.
    3. Válassza a **Bind** elemet.

    Továbbra is **konfigurálhat kötéseket a Transport.Transaction** **adatmodellelemhez és a TransportRecord.lines** adatforrásmezőhöz, hogy futásidőben az egyes fedezett átviteli csoportokhoz tartozó Intrastat-tranzakciók adatait elérhetővé tegye.

![Konfigurált modell-leképezés az ER-modell leképezésének tervezőjében.](./media/er-groupby-data-sources-configure-model-mapping.png)

### <a name="debug-the-added-model-mapping-component"></a>Hibakeresés a hozzáadott modellleképezés összetevőben

[Az ER adatforrás-hibakeresővel](er-debug-data-sources.md) tesztelje a konfigurált modell megfeleltetését.

1. A Modellleképezés **tervezőlapon** válassza a Hibakeresés **kezdete lehetőséget**.
2. A Hibakeresési adatforrások **lapon** bal oldali ablaktáblán válassza ki a TransportRecord **adatforrást, majd** válassza az Összes rekord olvasása lehetőséget **.**
3. Bontsa ki **a TransportRecord** adatforrást, majd hajtsa végre a következő lépéseket:

    1. Válassza ki **a TransportRecord.grouped.TransportMode** adatforrást.
    2. Válassza ki az **Érték beolvasása** lehetőséget.
    3. Válassza ki **a TransportRecord.grouped.NumberOfTransactions** adatforrást.
    4. Válassza ki az **Érték beolvasása** lehetőséget.
    5. Válassza ki **a TransportRecord.grouped.TotalInvoicedAmount adatforrást**.
    6. Válassza ki az **Érték beolvasása** lehetőséget.

4. A jobb oldali ablakban válassza az összes kibontása **lehetőséget**.

A **TransportRecord** adatforrás két rekordot tartalmaz, és két átviteli kódot tartalmaz. A program minden szállítási kódhoz kiszámítja a tranzakciók számát és a teljes számlázott összeget.

> [!NOTE]
> A "leolvasás" megközelítés akkor használatos, amikor egy **GroupBy** adatforrást hívnak az adatbázishívások optimalizálása érdekében. Emiatt a GroupBy **adatforrás egyes mezőértékét csak akkor számítja ki a** program az ER adatforrás-hibakeresőben, ha az adatok modellmezőihez vannak kötve.

![Az adatforrás hibakeresésének eredményei a Hibakeresési adatforrások lapon.](./media/er-groupby-data-sources-debug-datasource.png)

## <a name="frequently-asked-questions"></a>Gyakori kérdések

### <a name="is-there-any-way-to-calculate-grand-totals-when-the-group-totals-are-calculated"></a>Van mód a végösszegek kiszámítására a csoportösszegek számításakor?

Igen. A végösszegek kiszámításához konfigurálnia kell egy másik GroupBy adatforrást, **amelynél a korábban konfigurált GroupBy** **adatforrás** lesz az alap adatforrás. A következő ábra a GroupBy **típus** Összesítés adatforrását mutatja be, amely az összesítő SUM **funkció kiszámítására szolgál,** **a** GroupBy **típus TransportRecord** **adatforrásának SUM összesítése alapján.** **·**

![Összegek adatforrása az ER modellleképezés tervezőben.](./media/er-groupby-data-sources-configure-model-mapping2.png)

Az alábbi ábra az Összes adatforrás hibakeresésének **eredményeit** mutatja be.

![Az Összesítés adatforrás hibakeresésének eredményei a Hibakeresési adatforrások lapon.](./media/er-groupby-data-sources-debug-datasource2.png)

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus jelentések áttekintése](general-electronic-reporting.md)
- [Egy végrehajtott ER formátum hibakeresési adatforrásai az adatfolyam elemzéséhez és átalakításához](er-debug-data-sources.md)
- [Adatgyűjtési adatforrások használata elektronikus jelentési formátumokban](er-data-collection-data-sources.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
