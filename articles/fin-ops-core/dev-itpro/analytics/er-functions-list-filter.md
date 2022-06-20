---
title: FILTER ER-funkció
description: Ez a cikk a FILTER Electronic Reporting (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
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
ms.openlocfilehash: dfa4afdcfad8c1855a10e1fa37c36cc5b20682ef
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884517"
---
# <a name="filter-er-function"></a>FILTER ER-funkció

[!include [banner](../includes/banner.md)]

A `FILTER` függvény a megadott listát egy *Rekordlista* értékként adja vissza, miután a lekérdezés módosult, és a megadott feltételt szűri.

## <a name="syntax"></a>Szintaxis

```vb
FILTER (list, condition)
```

## <a name="arguments"></a>Argumentumok

`list`: *Rekordlista*

A *Rekordlista* adattípus adatforrásának érvényes elérési útja.

`condition`: *Logikai*

Érvényes feltételes kifejezés, amely a megadott lista rekordjainak szűrésére szolgál.

## <a name="return-values"></a>Visszaadott értékek

*Rekordlista*

A rekordok eredményül kapott listája.

## <a name="usage-notes"></a><a name="usage-notes"></a>Használati megjegyzések

Ez a függvény eltér a [WHERE](er-functions-list-where.md) függvénytől, mivel a megadott feltétel az adatbázis szintjén kerül alkalmazásra a *Táblarekordok* típus bármely Elektronikus jelentéskészítés (ER) adatforrására. A lista és a feltétel táblák és kapcsolatok segítségével határozhatók meg.

Ha a függvényhez konfigurált egyik vagy mindkét argumentum (`list` és `condition`) nem engedélyezi ennek a kérésnek a lefordítását a közvetlen SQL-hívásra, akkor a tervezési időben kivétel történik. Ez a kivétel tájékoztatja a felhasználót, hogy a `list` vagy `condition` nem használható az adatbázis lekérdezéséhez.

> [!NOTE]
> A `FILTER` funkció másképp működik, mint a `WHERE` funkció, [`VALUEIN`](er-functions-logical-valuein.md) ha a funkció a kiválasztási feltételek megadására használható.
> 
> - `VALUEIN` Ha a függvényt a `WHERE` függvény hatókörében használják, és a második argumentum olyan adatforrásra hivatkozik, `VALUEIN` amely nem ad vissza rekordokat, a rendszer a logikai hamis *[...](er-formula-supported-data-types-primitive.md#boolean)*`VALUEIN` értéket figyelembe véve adja vissza. Ebből következően a kifejezés `WHERE(Vendors, VALUEIN(Vendors.VendGroup, VendGroups, VendGroups.VendGroup))` nem ad vissza szállítói rekordokat, ha **a VendGroups** adatforrás nem ad vissza szállítóicsoport-rekordot.
> - `VALUEIN` Ha a függvényt a `FILTER` függvény hatókörében használják, és a második argumentum olyan adatforrásra hivatkozik, `VALUEIN` amely nem ad vissza rekordokat, *[a rendszer figyelmen kívül hagyja a logikai értékként megadott](er-formula-supported-data-types-primitive.md#boolean)*`VALUEIN` hamis értéket. Emiatt a kifejezés `FILTER(Vendors, VALUEIN(Vendors.VendGroup, VendGroups, VendGroups.VendGroup))` a **szállítói** adatforrás összes szállítói rekordját visszaadja, még akkor is, **ha a VendGroups** adatforrás nem ad vissza szállítóicsoport-rekordot.

## <a name="example-1"></a>1. példa

Ha a **Szállító** a VendTable táblára hivatkozó ER-adatforrásként van konfigurálva, akkor a `FILTER (Vendors, Vendors.VendGroup = "40")` kifejezés csak a 40-es szállítócsoporthoz tartozó szállítók listáját adja vissza.

## <a name="example-2"></a>2. példa

Ha a **Szállító** ER-adatforrásként van konfigurálva, amely a VendTable táblára hivatkozik, és ha a **parmVendorBankGroup** ER-adatforrásként van konfigurálva, amely az értéket *Karakterlánc* adattípusként adja vissza, a `FILTER ( Vendor.'<Relations'.VendBankAccount, Vendor.'<Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)` kifejezés csak az adott bankcsoporthoz tartozó szállítói számlák listáját adja vissza.

## <a name="example-3"></a>3. példa

A **Számított mező** típushoz adja meg a *DS* adatforrást, és az a `SPLIT ("A,B,C", ",")` kifejezést tartalmazza. Ezután adjon meg egy másik kifejezést: `FILTER( DS, DS.Value = "B")`. Amikor megpróbálja menteni ezt a kifejezést az ER-képlettervezőben, a következő kivétel történik: „Érvényesítési hiba: A FILTER függvény listakifejezése nem elérhető.”

## <a name="additional-resources"></a>További erőforrások

[Lista függvények](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
