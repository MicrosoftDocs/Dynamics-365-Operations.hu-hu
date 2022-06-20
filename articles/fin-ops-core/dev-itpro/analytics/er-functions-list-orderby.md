---
title: ORDERBY ER-függvény
description: Ez a cikk az ORDERBY Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 1a922405ea23d2b1ff5ac062785e68626edbc8f0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883759"
---
# <a name="orderby-er-function"></a>ORDERBY ER-függvény

[!include [banner](../includes/banner.md)]

Az `ORDERBY` függvény a megadott listát *Rekordlista* értékként adja vissza, miután a megadott argumentumok szerint rendezésre került. Ezek az argumentumok kifejezésként adhatók meg.

## <a name="syntax-1"></a><a name="syntax-1"></a>Szintaxis 1

```vb
ORDERBY (list, expression 1[, expression 2, …, expression N])
```

## <a name="syntax-2"></a><a name="syntax-2"></a>Szintaxis 2

```vb
ORDERBY (location, list, expression 1[, expression 2, …, expression N])
```

> [!NOTE]
> Ez a szintaxis a Microsoft Dynamics 365 Pénzügyi verzió 10.0.25-ös és újabb verzióiban támogatott.

## <a name="arguments"></a>Argumentumok

`location`: Karakterlánc *[...](er-formula-supported-data-types-primitive.md#string)*

Az a hely, ahol a rendezést futtatni kell. A következő lehetőségek érvényesek:

- "Lekérdezés"
- "InMemory"

`list`: *[rekordlista](er-formula-supported-data-types-composite.md#record-list)*

A *Rekordlista* adattípus adatforrásának érvényes elérési útja.

`expression 1`: *Mező*

Az adatforrás egy mezőjének érvényes elérési útja, amelyre a hívott függvény `list` argumentuma hivatkozik. A hivatkozott mezőnek primitív adattípusú mezőnek kell lennie. Az argumentum megadása kötelező.

`expression N`: *Mező*

Az adatforrás egy mezőjének érvényes elérési útja, amelyre a hívott függvény `list` argumentuma hivatkozik. A hivatkozott mezőnek primitív adattípusú mezőnek kell lennie. Ezek a további argumentumok nem kötelezők.

## <a name="return-values"></a>Visszatérési értékek

*Rekordlista*

A rekordok eredményül kapott listája.

## <a name="usage-notes"></a>Használati megjegyzések

### <a name="syntax-1"></a>Szintaxis 1

Az adatok rendezése mindig az alkalmazáskiszolgáló memóriájában történik. További részleteket az [1. példában talál](#example-1).

### <a name="syntax-2"></a>Szintaxis 2

### <a name="sorting-in-memory"></a>Rendezés a memóriában

Ha az `location` argumentum **InMemory** típusú, az adatok rendezése az alkalmazáskiszolgáló memóriájában történik. További részleteket a [2. példában talál](#example-2).

### <a name="sorting-in-database"></a>Rendezés az adatbázisban

Ha az `location` argumentum Lekérdezés, **az** adatok rendezése az adatbázis szintjén történik. Ebben az esetben az `list`[argumentumnak a következő elektronikus jelentési (ER)](general-electronic-reporting.md) adatforrásra kell mutatnie, amely meghatározza azt az alkalmazásforrást, amely számára közvetlen adatbázis-lekérdezést lehet létrehozni:

- A táblarekord-típus *adatforrása*
- A Tábla rekordtípus egyik adatforrásának *kapcsolata*
- A Számítás mezőtípus *adatforrása*

Az `expression 1` argumentumok `expression N` csak olyan ER-adatforrás mezőire mutatnak, amelyeken az alkalmazásforrás olyan mezői is megadhatók, amelyekre közvetlen adatbázis-lekérdezést lehet létrehozni.

Ha nem lehet közvetlen adatbázis-lekérdezést létrehozni, ellenőrzési hiba történik [az](er-components-inspections.md#i18) ER modellleképezés-tervezőben. Az üzenet arról tájékoztatja, hogy a függvényt tartalmazó ER kifejezés, amely a `ORDERBY` függvényt tartalmazza nem futtatható futásidőben.

A jobb teljesítmény **érdekében érdemes a Lekérdezés** lehetőséget használni olyan alkalmazás-adatforrások rendezése esetén, amelyek nagy számú rekordot tartalmazhatnak (például tranzakciós alkalmazástáblák esetén).

> [!NOTE]
> Magát `ORDEBY` a függvényt nem lehet lefordítani közvetlen adatbázis-lekérdezésre. Ennek megfelelően nem lehet lekérdezni olyan ER-adatforrást, amely tartalmazza ezt a funkciót. Az ER-függvények [hatókörében (például FILTER](er-functions-list-filter.md)[és ALLITEMSQUERY](er-functions-list-allitemsquery.md)) nem használható, ahol csak lekérdezésre használható adatforrások használhatók.

A további részleteket lásd a [3](#example-3)[. és a 4. példában](#example-4).

### <a name="comparability"></a>Összehasonlíthatóságát

Mivel az SQL adatbázismotor és a Pénzügy alkalmazáskiszolgáló más rangsorolási értéket használhat egy karakterhez, a rekordok azonos listájának rendezési eredménye eltérő lehet, amikor a [Rendezés](er-formula-supported-data-types-primitive.md#string) karakterlánc mezőt használ. További részleteket az [5. példában talál](#example-5).

## <a name="example-1-in-memory-default-execution"></a><a name="example-1"></a> 1. példa: Alapértelmezett végrehajtás a memóriában

Ha megadja a *Számított mező* típusú **DS** adatforrást és az tartalmazza a `SPLIT ("C|B|A", "|")` kifejezést, akkor a `FIRST( ORDERBY( DS, DS. Value)).Value` kifejezés az **„A”** szöveges értéket adja vissza.

## <a name="example-2-in-memory-explicit-execution"></a><a name="example-2"></a> 2. példa: memóriában való explicit végrehajtás

Ha **a Szállító egy ER** *adatforrásként* van beállítva a VendTable **táblára hivatkozó táblarekord-típushoz,**`ORDERBY (Vendor, Vendor.'name()')` mind a kifejezés, mind a kifejezés a szállítók listáját adja vissza, amely név szerint, növekvő sorrendben van rendezve.`ORDERBY ("InMemory", Vendor, Vendor.'name()')`

Amikor az `ORDERBY ("Query", Vendor, Vendor.'name()')` ER modellleképezés tervezőben konfigurálja a kifejezést, [ellenőrzési](er-components-inspections.md#i8) hiba történik a tervezéskor, mivel az elérési út olyan alkalmazás metódusra hivatkozik, `Vendor.'name()'` amely logikája nem fordítható le közvetlen adatbázis-lekérdezésre.

## <a name="example-3-database-query"></a><a name="example-3"></a> 3. példa: adatbázis-lekérdezés

**Ha a TaxTransaction** a TaxTrans *táblára hivatkozó táblarekord-típus ER* **adatforrásaként** van konfigurálva, a kifejezés az alkalmazás adatbázisának szintjén rendezi a rekordokat, `ORDERBY ("Query", TaxTransaction, TaxTransaction.TaxCode)` és az adókódok alapján növekvő sorrendben rendezi a tranzakciók listáját.

## <a name="example-4-queryable-data-sources"></a><a name="example-4"></a> 4. példa: Lekérdezhető adatforrások

**Ha a TaxTransaction** *·* **a TaxTrans** táblára hivatkozó táblarekord-típus ER adatforrásaként van konfigurálva, **a TaxTransactionFiltered** ER `FILTER(TaxTransaction, TaxCode="VAT19")` adatforrás konfigurálható úgy, hogy tartalmazza azt a kifejezést, amely egy adott adókód tranzakcióit fogja bekérni. **Mivel a beállított TaxTransactionFiltered** ER adatforrás lekérdezhető, a kifejezés beállítható úgy, `ORDERBY ("Query", TaxTransactionFiltered, TaxTransactionFiltered.TransDate)` hogy a tranzakciódátum szerint növekvő sorrendben állítsa vissza a szűrt adótranzakciók listáját.

**Ha a TaxTransactionOrdered adatforrásként konfigurálja a TaxTransactionOrdered** *·*`ORDERBY ("Query", TaxTransaction, TaxTransaction.TransDate)` adatforrást annak a Számított mezőtípusnak, amely a kifejezést és a kifejezést tartalmazó Számított mezőtípus EGYIK ER-adatforrását tartalmazza, akkor az *ER* `FILTER(TaxTransactionOrdered, TaxCode="VAT19")`[modellleképezés](er-components-inspections.md#i18) tervezője tervezési időpontban érvényesítési hibát jelez. Ez a [hiba azért fordul elő, mert a FILTER](er-functions-list-filter.md#usage-notes) függvény első argumentumának egy lekérdezhető ER adatforrásra kell hivatkozni, **de a funkciót tartalmazó TaxTransactionOrdered**`ORDERBY` adatforrás nem lekérdezhető.

## <a name="example-5-comparability"></a><a name="example-5"></a> 5. példa: Összehasonlíthatóság

### <a name="prerequisites"></a>Előfeltételek

1. Adja meg a kifejezést **tartalmazó Számított mezőtípus** DS1 *adatforrását* `SPLIT ("D1|_D2|D3", "|")`.
2. Nyissa meg **[a Pénzügyi dimenzióértékek lapot](../../../finance/general-ledger/financial-dimensions.md)**, és válassza ki a **CostCenter dimenziót**.
3. Adja meg a következő dimenzióértékeket: **D1**, **\_ D2** és **D3**.

### <a name="sorting-in-memory"></a>Rendezés a memóriában

1. Konfigurálja a kifejezést **tartalmazó Számított mezőtípus** DS2 *adatforrását* `ORDERBY("InMemory", DS1, DS1.Value)`.
2. Ne feledjük `FIRST(DS2).Value`**, hogy a kifejezés a "D1**" szövegértéket adja vissza, `INDEX(DS2, COUNT(DS2)).Value`**a kifejezés a "\_ D2**" szöveges értéket adja eredményül, `STRINGJOIN(DS2, DS2.Value, "|")`**a kifejezés a "D1\| D3\|\_ D2**" szövegértéket.

### <a name="sorting-in-database"></a>Rendezés az adatbázisban

1. **A FinancialDimensionValueEntity entitásra hivatkozó táblarekord-típus adatforrásának DS3-a.** *·* **·**
2. Konfigurálja a kifejezést **tartalmazó Számított mezőtípus** DS4 *adatforrását* `FILTER(DS3, DS3.FinancialDimension="CostCenter")`.
3. Konfigurálja a kifejezést **tartalmazó Számított mezőtípus** DS5 *adatforrását* `ORDERBY(DS4, DS4.DimensionValue)`.
4. Ne feledjük `FIRST(DS5).Value`**, hogy a kifejezés a "\_ D2**" szövegértéket adja eredményül, `INDEX(DS5, COUNT(DS5)).Value`**a kifejezés a "D3**" szöveges értéket adja eredményül, `STRINGJOIN(DS5, DS5.Value, "|")`**a kifejezés a "\_ D2\| D1\| D3**" szövegértéket.

## <a name="additional-resources"></a>További erőforrások

[Listafüggvények](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
