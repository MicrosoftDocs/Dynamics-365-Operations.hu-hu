---
title: Elektronikus jelentéskészítés képletének nyelve
description: A témakör tájékoztatást nyújt a képlet nyelvének használatának módjáról az elektronikus jelentésekben (ER).
author: NickSelin
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1e48c02ecc9d69cf14ed257aae56081925cedfe9
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6355394"
---
# <a name="electronic-reporting-formula-language"></a>Elektronikus jelentéskészítés képletének nyelve

[!include [banner](../includes/banner.md)]

Az elektronikus jelentés (ER) hatékony adatátalakítási élményt nyújt. Az [ER képlettervezőnél](general-electronic-reporting-formula-designer.md) a szükséges adatmanipulációk kifejezésére használt nyelv hasonlít a Microsoft Excel képletek nyelvére.

## <a name="basic-syntax"></a>Alap szintaxis

ER kifejezések bármennyi vagy az összes elemet tartalmazhatja a következő elemek közül:

- [Állandók](#Constants)
- [Operátorok](#Operators)
- [Hivatkozások](#References)
- [Útvonalak](#Paths)
- [Funkciók](#Functions)

## <a name="constants"></a><a name="Constants"></a>Állandók

Amikor a kifejezéseket tervezi, használhat szöveges és a numerikus állandókat (nem számított értékeket). Például a `VALUE ("100") + 20` kifejezés **20** numerikus konstanst és **„100”** szövegkonstanst használ és megjeleníti a **120** numerikus értéket.

Az ER képletszerkesztő támogatja a feloldó szakaszokat. Így meghatározhat olyan kifejezés-karakterláncot, amelyet eltérően kell kezelni. A `"Leo Tolstoy ""War and Peace"" Volume 1"` kifejezés például a következő karaktersorozatot adja eredményül: **Leo Tolsztoj „Háború és béke” 1. kötet**.

## <a name="operators"></a><a name="Operators"></a>Operátorok

Az alábbi táblázat bemutatja az aritmetikai operátorokat, amelyek segítségével elvégezheti a matematikai alapműveleteket, mint például összeadás, kivonás, szorzás és osztás.

| Operátor | Jelentés               | Példa     |
|----------|-----------------------|-------------|
| +        | Hozzáadás              | `1+2`       |
| -        | Kivonás, tagadás | `5-2`, `-1` |
| \*       | szorzás        | `7\*8`      |
| /        | Osztály              | `9/3`       |

A következő táblázat a támogatott összehasonlító operátorokat mutatja. Ezen operátorok segítségével összehasonlíthat két értéket.

| Operátor | Jelentés                  | Példa      |
|----------|--------------------------|--------------|
| =        | Egyenlő                    | `X=Y`        |
| &gt;     | Nagyobb, mint             | `X>Y`        |
| &lt;     | Kisebb, mint                | `X<Y`        |
| &gt;=    | Nagyobb vagy egyenlő | `X>=Y`       |
| &lt;=    | Kisebb vagy egyenlő    | `X<=Y`       |
| &lt;&gt; | Nem egyenlő             | `X<>Y`       |

Ezenkívül használhat és-jelet (&) szövegösszefűző operátorként. Így egy vagy több szövegláncot összekapcsolhat vagy összefűzhet egyetlen szöveggé.

| Operátor | Jelentés     | Példa                                               |
|----------|-------------|-------------------------------------------------------|
| &        | Összefűzés | `"Nothing to print:" & " " & "no records found"`      |

### <a name="operator-precedence"></a>Operátor elsőbbségi sorrend

Fontos a sorrend, amelyben az összetett kifejezés egy része kiértékelésre került. Például az `1 + 4 / 2` kifejezés eredménye attól függően változik, hogy az összeadás vagy az osztás művelet hajtódik-e végre először. A zárójelek segítségével megadhatja egy kifejezés kiértékelésének módját. Például, ha jelezni szeretné, hogy először a hozzáadás műveletet kell végrehajtani, így módosíthatja az előző kifejezést: `(1 + 4) / 2`. Ha a kifejezésben elvégzendő műveletek sorrendje nincs megadva explicit módon, akkor a a sorrend támogatott operátorokhoz rendelt alapértelmezett elsőbbségi sorrenden alapul. A következő táblázatok az egyes operátorokhoz rendelt elsőbbségi sorrendet jeleníti meg. A magasabb elsőbbségi sorrenddel (például 7) rendelkező operátorok az alacsonyabb elsőbbségi sorrenddel rendelkező operátorok előtt (például 1) kerülnek kiértékelésre.

| Elsőbbségi sorrend | Operátorok      | Szintaxis                                                                  |
|------------|----------------|-------------------------------------------------------------------------|
| 7          | Csoportosítás       | ( … )                                                                   |
| 6          | Tag hozzáférés  | … gombra. …                                                                   |
| 5          | Függvényhívás  | … ( … )                                                                 |
| 4          | Szorzás | … \* …<br>… / …                                                         |
| 3          | Additív       | … + …<br>… - …                                                          |
| 2          | Összehasonlítás     | … &lt; …<br>… &lt;= …<br>… =&gt; …<br>… &gt; …<br>… = …<br>… &lt;&gt; … |
| 1          | Kiválasztás     | … , …                                                                   |

Ha egy kifejezés olyan több egymást követő operátort tartalmaz, amelyek ugyanolyan elsőbbséget élveznek, akkor ezen műveletek kiértékelése balról jobbra történik. Például az `1 + 6 / 2 \* 3 > 5` kifejezés **igaz** választ jelenít meg. Ajánlatos a zárójelek használata a kifejezésekben található műveletek kívánt sorrendjének explicit módon történő jelzéséhez, illetve a kifejezések könnyebb olvasása és kezelése érdekében.

## <a name="references"></a><a name="References"></a>Hivatkozások

Egy kifejezés tervezése során elérhető jelenlegi ER komponens összes adatforrását elnevezett hivatkozásként lehet használni. A jelenlegi ER-komponens modell-hozzárendelés vagy formátum lehet. Például az aktuális ER modell-leképezés tartalmazza a **ReportingDate** adatforrást, amely megjeleníti a [*DateTime*](er-formula-supported-data-types-primitive.md#datetime) adattípus értékét. Annak érdekében, hogy a létrejövő dokumentumban megfelelően formázott értéket kapjon, a következőképpen hivatkozhat a kifejezésben szereplő adatforrásokra: `DATETIMEFORMAT (ReportingDate, "dd-MM-yyyy")`.

Az adatforrásra hivatkozó minden név minden olyan karaktere előtt, amely nem az ábécé egy betűjét jelöli, egyszeres idézőjelet (') kell használni. A hivatkozási adatforrás minden nevének, amely tartalmaz legalább egy szimbólumot, amely nem az ábécé egy betűjét jelenti, egyszeres idézőjelekben kell megjelennie. Ezek a nem alfabetikus szimbólumok lehetnek például írásjelek vagy más írott szimbólumok. Íme néhány példa:

- A **Mai dátum és idő** adatforrást a következőképpen kell hivatkozni egy ER kifejezésben: `'Today''s date & time'`.
- A **Vevők** adatforrás **név()** metódusát a következőképp kell hivatkozni az ER kifejezésben: `Customers.'name()'`.

Ha az alkalmazás-adatforrásainak metódusai paraméterekkel rendelkeznek, a következő szintaxist kell használni ezen metódusok meghívásához:

- Ha a **Rendszer** adatforrás **isLanguageRTL** metódusa rendelkezik egy [*Karakterlánc*](er-formula-supported-data-types-primitive.md#string) adattípusú **EN-US** paraméterrel, erre a metódusra a következő módon kell hivatkozni az ER-kifejezésekben: `System.isLanguageRTL("EN-US")`.
- Az idézőjelek nem kötelezőek, ha egy metódus neve csak alfanumerikus szimbólumokat tartalmaz. Az olyan táblametódusok esetén viszont kötelezőek, amikor a név zárójeleket tartalmaz.

Amikor a **Rendszer** adatforrás hozzá van adva egy ER-hozzárendeléshez, amelyik a **Globális** alkalmazásosztályra hivatkozik, a `System.isLanguageRTL("EN-US ")` kifejezés a **HAMIS** *logikai* értéket adja vissza. A módosított `System.isLanguageRTL("AR")` kifejezés az **IGAZ** *logikai* értéket adja eredményül.

Az ilyen típusú metódusok paramétereinek átadott értékek átadásának módja korlátozható:

- Csak állandók adhatók át ilyen típusú metódusoknak. Az állandók értékeit a tervezés során kell meghatározni.
- Az ilyen típusú paraméterekhez csak [egyszerű](er-formula-supported-data-types-primitive.md) (alap) adattípusok támogatottak. Az egyszerű adattípusok: *Egész*, *Valós*, *Logikai* és *Karakterlánc*.

## <a name="paths"></a><a name="Paths"></a>Útvonalak

Amikor a kifejezés egy adatforrásra hivatkozik, az útvonal meghatározása segítségével kiválaszthatja az adatforrás egy megadott egyszerű elemének kiválasztásához. A pont karaktert (.) a strukturált adatforrás egyes elemeinek elkülönítésére használják. Például az aktuális ER modell-leképezés tartalmazza a **InvoiceTransactions** adatforrást, és ez az adatforrás rekordok listáját adja vissza. Az **InvoiceTransactions** rekordszerkezete tartalmazza az **AmountDebit** és **AmountCredit** mezőket, amelyek mindegyike numerikus értékeket ad vissza. Ezért a számlázott összeg kiszámításához a következő kifejezést tervezhetjük: `InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit`. A kifejezésben szereplő `InvoiceTransactions.AmountDebit` szerkezet a *Rekordlista* **InvoiceTransactions** adatforrásának **AmountDebit** mezőjének elérésére szolgáló útvonal.

### <a name="relative-path"></a>Relatív elérési út

Ha egy strukturált adatforrás elérési útja „kukac” jellel (@) kezdődik, akkor ez relatív útvonal. A „kukac” jel a használt hierarchikus fastruktúra abszolút elérési útjának fennmaradó része helyett jelenik meg. A következő ábrán egy példa látható. Itt a `Ledger.'accountingCurrency()'` abszolút útvonal azt jelzi, hogy a **Főkönyv** adatforrásból származó számviteli pénznem értéke bekerül az adatmodell **AccountingCurrency** mezőjébe.

![Példa abszolút elérési útra az ER modell-leképezési tervező lapon.](./media/ER-FormulaLanguage-AbsolutePath.png)

Az alábbi ábrán látható példa szemlélteti, hogyan használja a rendszer a relatív elérési utat. A `@.AccountNum` relatív elérési út azt jelzi , hogy az **Intrastat** adatforrás **AccountNum** mezője (amely az adatmodell hierarchikus fájának **AccountNum** mezője felett egy szinttel feljebb jelenik meg) a vevő vagy szállító számlaszámának bevitelére szolgál az adatmodell **AccountNum** mezőjében.

![Példa relatív elérési útra az ER modell-leképezési tervező lapon.](./media/ER-FormulaLanguage-RelativePath1.png)

Az abszolút elérési út maradék része is megjelenik az [ER képletszerkesztőben](general-electronic-reporting-formula-designer.md).

![A teljes elérési út hátralévő része az ER képlettervező lapon.](./media/ER-FormulaLanguage-RelativePath2.png)

További információ: [Relatív elérési út használata az ER-modellek és -formátumok adatkötéseiben](relative-path-data-bindings-er-models-format.md).

## <a name="functions"></a><a name="Functions"></a>Funkciók

A beépített ER függvények ER kifejezésekben használhatók. A kifejezéskörnyezet (aktuális ER modell-leképezés vagy ER formátum) minden adatforrása használható függvénymeghívási paraméterként a függvénymeghívási argumentumok listájával összhangban. Az állandók szintén használhatók függvények meghívásának paraméterként. Például az aktuális ER modell-leképezés tartalmazza a **InvoiceTransactions** adatforrást, és ez az adatforrás rekordok listáját adja vissza. Az **InvoiceTransactions** rekordszerkezete tartalmazza az **AmountDebit** és **AmountCredit** mezőket, amelyek mindegyike numerikus értékeket ad vissza. Ezért a számlázott összeg kiszámításához, megtervezheti azokat a következő kifejezéseket, amelyek az ER kerekítési funkciót használják: `ROUND (InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit, 2)`.

Az ER-modell-leképezések és az ER-jelentések tervezésénél az ER-függvények az alábbi kategóriákban használhatók:

- [Dátum és idő függvények](er-functions-category-datetime.md)
- [Lista függvények](er-functions-category-list.md)
- [Logikai függvények](er-functions-category-logical.md)
- [Matematikai funkciók](er-functions-category-mathematical.md)
- [Rekord függvények](er-functions-category-record.md)
- [Szöveg függvények](er-functions-category-text.md)
- [Adatgyűjtési függvények](er-functions-category-data-collection.md)
- [Egyéb (üzleti területre jellemző) függvények](er-functions-category-other.md)
- [Típuskonverziós függvények](er-functions-category-type-conversion.md)

## <a name="functions-list-extension"></a>A funkciók lista kiterjesztése

Az ER segítségével bővítheti az ER kifejezésekben használt függvények listáját. Ez bizonyos műszaki erőfeszítést igényel. Részletes tudnivalókat lásd: [Elektronikus jelentéskészítési (ER) funkciók listájának kibővítése](general-electronic-reporting-formulas-list-extension.md).

## <a name="compound-expressions"></a>Összetett kifejezések

Olyan összetett kifejezéseket is létrehozhat, amelyek különböző kategóriákhoz tartozó függvényeket használnak, feltéve, hogy az adattípusok megegyeznek. A függvények együttes használatakor az egyik függvény kimenetének adattípusát adja meg a másik függvény által igényelt bemeneti adattípusnak. Ha például el szeretne kerülni egy lehetséges „lista üres” hibaüzenetet egy mező ER-formátumú elemhez kötésében, a következő példa szerint egyesítsen függvényeket a [Lista](er-functions-category-list.md) kategóriából a [Logikai](er-functions-category-logical.md) kategória egyik függvényével. Itt a képlet a [IF](er-functions-logical-if.md) függvényt használja arra, hogy ellenőrizze, hogy az **IntrastatTotals** lista üres-e, mielőtt a listából a szükséges összesítés értékét adja eredményül. Ha az **IntrastatTotals** lista üres, a képlet eredménye **0** (nulla).

```vb
IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded') 
```

## <a name="multiple-solutions"></a>Többféle megoldás

Gyakran előfordul, hogy ugyanaz az adatátalakítási eredmény többféle módon, különböző kategóriákhoz tartozó függvények használatával vagy ugyanabból a kategóriából különböző függvényekkel is elérhető. Például a korábbi kifejezés konfigurálható a [COUNT](er-functions-list-count.md) függvénnyel a [Lista](er-functions-category-list.md) kategóriából.

```vb
IF(COUNT (IntrastatTotals)=0, 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded') 
```

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentések áttekintése](general-electronic-reporting.md)

[Képletszerkesztő az Elektronikus jelentéskészítésben](general-electronic-reporting-formula-designer.md)

[Elektronikus jelentéskészítési funkciók listájának kibővítése](general-electronic-reporting-formulas-list-extension.md)

[Támogatott egyszerű adattípusok](er-formula-supported-data-types-primitive.md)

[Támogatott összetett adattípusok](er-formula-supported-data-types-composite.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
