---
title: VALUEIN ER-függvény
description: A témakör tájékoztatást nyújt a VALUEIN Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 12/14/2021
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
ms.openlocfilehash: efa811df360b2ca38eb59bac849e70041405fa81
ms.sourcegitcommit: b1c758ec4abfcf3bf9e50f18c1102d4a9c1316d0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/15/2021
ms.locfileid: "7922362"
---
# <a name="valuein-er-function"></a>VALUEIN ER-függvény

[!include [banner](../includes/banner.md)]

A `VALUEIN` függvény azt határozza meg, hogy a megadott bemenet megegyezik-e a megadott lista valamelyik megadott elemének bármilyen értékével. A függvény *Logikai* **IGAZ** értéket ad eredményül, ha a megadott bemenet megegyezik a megadott kifejezésnek a megadott lista legalább egy rekordján való futtatásának eredményével. Ellenkező esetben **HAMIS** *logikai* eredményt ad.

## <a name="syntax"></a>Szintaxis

```vb
VALUEIN (input, list, list item expression)
```

## <a name="arguments"></a>Argumentumok

`input`: *Mező*

A *Rekordlista* típusának megfelelő adatforrásra vonatkozó elem érvényes elérési útja. Az elem értékét a rendszer megfelelteti.

`list`: *Rekordlista*

A *Rekordlista* adattípus adatforrásának érvényes elérési útja.

`list item expression`: *Logikai*

Egy érvényes feltételes kifejezés, amely a megadott lista egyetlen mezőjére mutat vagy azt tartalmazza, amely a megfeleltetéshez használandó.

## <a name="return-values"></a>Visszaadott értékek

*Logikai*

Az eredményül kapott *Logikai* érték.

## <a name="usage-notes"></a>Használati megjegyzések

Általában a `VALUEIN` függvény **VAGY** feltételek egy csoportjára fordul le. Ha a **VAGY** feltételek listája nagy, és az SQL-utasítás maximális hosszát túllépik, akkor a [`VALUEINLARGE`](er-functions-logical-valueinlarge.md) függvény használatát érdemes megfontolni.

```vb
(input = list.item1.value) OR (input = list.item2.value) OR …
```

Bizonyos esetekben az `EXISTS JOIN` operátor használatával lefordítható egy adatbázis SQL-utasításra.

> [!NOTE]
> A függvény által visszaadott érték használata különböző, attól függően, hogy ez a funkció használatos-e a funkció vagy a `VALUEIN`[funkció kiválasztási](er-functions-list-filter.md#usage-notes)[`FILTER`](er-functions-list-filter.md) feltételeinek [`WHERE`](er-functions-list-where.md) megadására.

## <a name="example-1"></a>1. példa

A modell-hozzárendelésében meghatározza a *Számított mező* típus **Lista** adatforrását. Az adatforrás tartalmazza a `SPLIT ("a,b,c", ",")` kifejezést.

Adatforrás meghívásakor, ha `VALUEIN ("B", List, List.Value)` kifejezésként lett konfigurálva, akkor **IGAZ** értéket ad eredményül. Ebben az esetben a `VALUEIN` függvény a következő feltételek csoportjára fordul le: `(("B" = "a") or ("B" = "b") or ("B" = "c"))`, ahol `("B" = "b")` értéke **IGAZ**.

Adatforrás meghívásakor, ha a `VALUEIN ("B", List, LEFT(List.Value, 0))` kifejezésként lett konfigurálva, akkor **HAMIS** értéket ad eredményül. Ebben az esetben a `VALUEIN` függvény a következő feltételre fordul le: `("B" = "")`, amely nem egyenlő az **IGAZ** értékkel.

Az ilyen feltétel szövegében a karakterszám felső határa 32 768 karakter. Ezért ne hozzon létre olyan adatforrásokat, amelyek túlléphetik ezt a korlátot futásidőben. Ha túllépte a korlátot, az alkalmazás leáll, és kivételt küld. Például ez a helyzet akkor fordulhat elő, ha így van beállítva az adatforrás: `WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)`, és a **Lista 1** és **Lista 2** listák nagy mennyiségű rekordot tartalmaznak.

Bizonyos esetekben a `VALUEIN` funkció egy adatbázis-utasításra fordul le az `EXISTS JOIN` operátor használatával. Ez a viselkedés akkor fordul elő, amikor a [`FILTER`](er-functions-list-filter.md) függvény használatos, és a következő feltételek teljesülnek:

- A **LEKÉRDEZÉS KÉRÉSE** beállítás ki van kapcsolva a `VALUEIN` függvény adatforrása esetében, amely rekordok listájára hivatkozik. További feltételek nem vonatkoznak erre az adatforrásra futásidőben.
- Nincsenek konfigurálva beágyazott kifejezések az adatforrás `VALUEIN` függvényéhez, amely rekordok listájára hivatkozik.
- A `VALUEIN` függvény listaeleme a megadott adatforrás mezőjére hivatkozik, nem az adatforrás kifejezésére vagy metódusára.

Fontolja meg ennek használatát a [`WHERE`](er-functions-list-where.md) függvény helyett, ahogy ebben a példában korábban ismertettük.

## <a name="example-2"></a>2. példa

A következő adatforrás megadása a modell-hozzárendelésben:

- A *Táblázatbejegyzés* típus **Tartalmazza** adatforrása. Ez az adatforrás az Intrastat-táblára hivatkozik.
- A *Táblázatbejegyzés* típus **Port** adatforrása. Ez az adatforrás az IntrastatPort-táblára hivatkozik.

Amikor adatforrás van meghívva, amely a `FILTER (In, VALUEIN(In.Port, Port, Port.PortId)` kifejezésben van beállítva, a következő SQL-utasítás generálódik, hogy az Intrastat-tábla szűrt rekordjait adja vissza:

```vb
select … from Intrastat
exists join TableId from IntrastatPort
where IntrastatPort.PortId = Intrastat.Port
```

A **dataAreaId** mezők esetében a végső SQL-utasítás az `IN` operátor használatával van előállítva.

## <a name="example-3"></a>3. példa

A következő adatforrás megadása a modell-hozzárendelésben:

- A *Számított mező* típus **Le** adatforrása. Az adatforrás tartalmazza a `SPLIT ("DEMF,GBSI,USMF", ",")` kifejezést.
- A *Táblázatbejegyzés* típus **Tartalmazza** adatforrása. Ez az adatforrás az Intrastat-táblára hivatkozik, és a **Vállalatközi** beállítás be van kapcsolva.

Amikor adatforrás van meghívva, amely a `FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)` kifejezésként van beállítva, a végső SQL-utasítás tartalmazza a következő feltételt.

```vb
Intrastat.dataAreaId IN ('DEMF', 'GBSI', 'USMF')
```

## <a name="additional-resources"></a>További erőforrások

[Logikai függvények](er-functions-category-logical.md)

[VALUEINLARGE függvények](er-functions-logical-valueinlarge.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
