---
title: ORDERBY ER-függvény
description: A témakör tájékoztatást nyújt az ORDERBY Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 963d55bcf98a9109c8b6ceb57edf5b55f15a2b0f
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075174"
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
> Ezt a szintaxist a Microsoft támogatja Dynamics 365 Finance 10.0.25 és újabb verzió.

## <a name="arguments"></a>Argumentumok

`location`:*[Húr](er-formula-supported-data-types-primitive.md#string)*

Az a hely, ahol a válogatást le kell futtatni. A következő opciók érvényesek:

- "Lekérdezés"
- "Emlékül"

`list`:*[Rekordlista](er-formula-supported-data-types-composite.md#record-list)*

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

Az adatok rendezése mindig az alkalmazásszerver memóriájában történik. További részletekért lásd [példa 1](#example-1).

### <a name="syntax-2"></a>Szintaxis 2

### <a name="sorting-in-memory"></a>Rendezés a memóriában

Amikor az`location` argumentum így van megadva **Emlékül**, az adatok rendezése egy alkalmazásszerver memóriájában történik. További részletekért lásd [2. példa](#example-2).

### <a name="sorting-in-database"></a>Rendezés adatbázisban

Amikor az`location` argumentum így van megadva **Lekérdezés**, az adatok rendezése adatbázis szinten történik. Ebben az esetben a`list` Az argumentumnak a következők egyikére kell mutatnia [Elektronikus jelentéstétel (ER)](general-electronic-reporting.md) adatforrások, amelyek megadják azt az alkalmazásforrást, amelyhez közvetlen adatbázis-lekérdezés hozható létre:

- Adatforrás a *Táblázat rekordok* típus
- Az adatforrás kapcsolata a *Táblázat rekordok* típus
- Adatforrás a *Számítási mező* típus

A`expression 1` és`expression N` Az argumentumoknak egy olyan ER adatforrás mezőire kell mutatniuk, amelyek meghatározzák az alkalmazásforrás releváns mezőit, amelyekhez közvetlen adatbázis-lekérdezés is létrehozható.

Ha nem lehet közvetlen adatbázis-lekérdezést létrehozni, akkor érvényesítés [hiba](er-components-inspections.md#i18) az ER modell leképezés tervezőjében fordul elő. Az üzenet arról tájékoztatja, hogy a függvényt tartalmazó ER kifejezés, amely a `ORDERBY` függvényt tartalmazza nem futtatható futásidőben.

A jobb teljesítmény érdekében javasoljuk, hogy használja a **Lekérdezés** opció, ha a rendezés olyan alkalmazás-adatforrásokhoz van konfigurálva, amelyek nagyszámú rekordot tartalmazhatnak (például tranzakciós alkalmazástáblákhoz).

> [!NOTE]
> A`ORDEBY` maga a függvény nem fordítható le közvetlen adatbázis-lekérdezésre. Ezért az ezt a függvényt tartalmazó ER adatforrás nem lekérdezhető. Nem használható olyan ER-funkciókban sem, mint pl [SZŰRŐ](er-functions-list-filter.md) és [ALLITEMSQUERY](er-functions-list-allitemsquery.md), ahol csak lekérdezhető adatforrások használhatók.

További részletekért lásd [3. példa](#example-3) és [4. példa](#example-4).

### <a name="comparability"></a>Összehasonlíthatóság

Mivel az SQL adatbázismotor és a Finance alkalmazásszerver eltérő rangsorolási értéket használhat egyetlen karakterhez, ugyanazon rekordlista rendezési eredménye eltérhet, ha [Húr](er-formula-supported-data-types-primitive.md#string) mezőt a rendezésre használják. További részletekért lásd [5. példa](#example-5).

## <a name="example-1-in-memory-default-execution"></a><a name="example-1"></a> 1. példa: Alapértelmezett végrehajtás a memóriában

Ha megadja a *Számított mező* típusú **DS** adatforrást és az tartalmazza a `SPLIT ("C|B|A", "|")` kifejezést, akkor a `FIRST( ORDERBY( DS, DS. Value)).Value` kifejezés az **„A”** szöveges értéket adja vissza.

## <a name="example-2-in-memory-explicit-execution"></a><a name="example-2"></a> 2. példa: Explicit végrehajtás a memóriában

Ha **Eladó** ER adatforrásként van konfigurálva *Táblázat rekordok* típusra hivatkozik **VendTable** táblázat, mindkét kifejezés`ORDERBY (Vendor, Vendor.'name()')` és a kifejezés`ORDERBY ("InMemory", Vendor, Vendor.'name()')` visszaadja a szállítók listáját, amely név szerint növekvő sorrendben van rendezve.

Amikor konfigurálja a kifejezést`ORDERBY ("Query", Vendor, Vendor.'name()')` az ER modell leképezés tervezőjében egy érvényesítés [hiba](er-components-inspections.md#i8) tervezéskor fordul elő, mert a`Vendor.'name()'` Az elérési út olyan alkalmazási metódusra utal, amelynek logikája nem fordítható le közvetlen adatbázis-lekérdezésre.

## <a name="example-3-database-query"></a><a name="example-3"></a> 3. példa: Adatbázis lekérdezés

Ha **Adótranzakció** ER adatforrásként van konfigurálva *Táblázat rekordok* típusra hivatkozik **TaxTrans** táblázat, a kifejezés`ORDERBY ("Query", TaxTransaction, TaxTransaction.TaxCode)` az alkalmazás adatbázis szintjén rendezi a rekordokat, és visszaadja az adótranzakciók listáját, amely adókód szerint van rendezve növekvő sorrendben.

## <a name="example-4-queryable-data-sources"></a><a name="example-4"></a> 4. példa: Lekérdezhető adatforrások

Ha **Adótranzakció** ER adatforrásként van konfigurálva *Táblázat rekordok* típusra hivatkozik **TaxTrans** asztal, a **TaxTransactionFiltered** Az ER adatforrás konfigurálható úgy, hogy tartalmazza a kifejezést`FILTER(TaxTransaction, TaxCode="VAT19")` amely lekéri a tranzakciókat egy adott adószámhoz. Mivel a beállított **TaxTransactionFiltered** Az ER adatforrás lekérdezhető, a kifejezés`ORDERBY ("Query", TaxTransactionFiltered, TaxTransactionFiltered.TransDate)` konfigurálható úgy, hogy visszaadja a szűrt adótranzakciók listáját, amely a tranzakció dátuma szerint van rendezve növekvő sorrendben.

Ha beállítod **TaxTransactionOrdered** mint ER adatforrás a *Számított mező* kifejezést tartalmazó típus`ORDERBY ("Query", TaxTransaction, TaxTransaction.TransDate)` és egy ER adatforrás a *Számított mező* kifejezést tartalmazó típus`FILTER(TaxTransactionOrdered, TaxCode="VAT19")`, egy érvényesítés [hiba](er-components-inspections.md#i18) tervezéskor fordul elő az ER modell leképezés tervezőjében. Ez a hiba azért fordul elő, mert a [SZŰRŐ](er-functions-list-filter.md#usage-notes) függvénynek egy lekérdezhető ER adatforrásra kell hivatkoznia, de a **TaxTransactionOrdered** adatforrás, amely tartalmazza a`ORDERBY` függvény nem lekérdezhető.

## <a name="example-5-comparability"></a><a name="example-5"></a> 5. példa: Összehasonlíthatóság

### <a name="prerequisites"></a>Előfeltételek

1. Adja meg az adatforrást **DS1** a *Számított mező* kifejezést tartalmazó típus `SPLIT ("D1|_D2|D3", "|")`.
2. Nyissa meg a **[Pénzügyi dimenzió értékek](../../../finance/general-ledger/financial-dimensions.md)** oldalt, és válassza ki a **Költségközpont** dimenzió.
3. Adja meg a következő dimenzióértékeket: **D1**,**\_ D2**, és **D3**.

### <a name="sorting-in-memory"></a>Rendezés a memóriában

1. Adatforrás konfigurálása **DS2** a *Számított mező* kifejezést tartalmazó típus `ORDERBY("InMemory", DS1, DS1.Value)`.
2. Figyeljük meg, hogy a kifejezés`FIRST(DS2).Value` visszaadja a szöveges értéket **"D1"**, a kifejezés`INDEX(DS2, COUNT(DS2)).Value` visszaadja a szöveges értéket **"\_ D2"**, és a kifejezés`STRINGJOIN(DS2, DS2.Value, "|")` visszaadja a szöveges értéket **"D1\| D3\|\_ D2"**.

### <a name="sorting-in-database"></a>Rendezés adatbázisban

1. Adja meg az adatforrást **DS3** a *Táblázat rekordok* típusra hivatkozik **FinancialDimensionValueEntity** entitás.
2. Adatforrás konfigurálása **DS4** a *Számított mező* kifejezést tartalmazó típus `FILTER(DS3, DS3.FinancialDimension="CostCenter")`.
3. Adatforrás konfigurálása **DS5** a *Számított mező* kifejezést tartalmazó típus `ORDERBY(DS4, DS4.DimensionValue)`.
4. Figyeljük meg, hogy a kifejezés`FIRST(DS5).Value` visszaadja a szöveges értéket **"\_ D2"**, a kifejezés`INDEX(DS5, COUNT(DS5)).Value` visszaadja a szöveges értéket **"D3"**, és a kifejezés`STRINGJOIN(DS5, DS5.Value, "|")` visszaadja a szöveges értéket **"\_ D2\| D1\| D3"**.

## <a name="additional-resources"></a>További erőforrások

[Listafüggvények](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
