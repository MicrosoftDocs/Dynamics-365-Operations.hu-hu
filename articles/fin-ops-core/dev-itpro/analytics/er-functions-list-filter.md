---
title: FILTER ER-funkció
description: A témakör tájékoztatást nyújt a FILTER Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2783fbfa0ba45c8d3772cf9ca16d110549d227b4
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917373"
---
# <a name="FILTER">FILTER ER-funkció</a>

[!include [banner](../includes/banner.md)]

A `FILTER` függvény a megadott listát egy *Rekordlista* értékként adja vissza, miután a lekérdezés módosult, és a megadott feltételt szűri.

## <a name="syntax"></a>Szintaxis

```
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

## <a name="usage-notes"></a>Használati megjegyzések

Ez a függvény eltér a [WHERE](er-functions-list-where.md) függvénytől, mivel a megadott feltétel az adatbázis szintjén kerül alkalmazásra a *Táblarekordok* típus bármely Elektronikus jelentéskészítés (ER) adatforrására. A lista és a feltétel táblák és kapcsolatok segítségével határozhatók meg.

Ha a függvényhez konfigurált egyik vagy mindkét argumentum (`list` és `condition`) nem engedélyezi ennek a kérésnek a lefordítását a közvetlen SQL-hívásra, akkor a tervezési időben kivétel történik. Ez a kivétel tájékoztatja a felhasználót, hogy a `list` vagy `condition` nem használható az adatbázis lekérdezéséhez.

## <a name="example-1"></a>1. példa

Ha a **Szállító** a VendTable táblára hivatkozó ER-adatforrásként van konfigurálva, akkor a `FILTER (Vendors, Vendors.VendGroup = "40")` kifejezés csak a 40-es szállítócsoporthoz tartozó szállítók listáját adja vissza.

## <a name="example-2"></a>2. példa

Ha a **Szállító** ER-adatforrásként van konfigurálva, amely a VendTable táblára hivatkozik, és ha a **parmVendorBankGroup** ER-adatforrásként van konfigurálva, amely az értéket *Karakterlánc* adattípusként adja vissza, a `FILTER ( Vendor.'<Relations'.VendBankAccount, Vendor.'<Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)` kifejezés csak az adott bankcsoporthoz tartozó szállítói számlák listáját adja vissza.

## <a name="example-3"></a>3. példa

A **Számított mező** típushoz adja meg a *DS* adatforrást, és az a `SPLIT ("A,B,C", ",")` kifejezést tartalmazza. Ezután adjon meg egy másik kifejezést: `FILTER( DS, DS.Value = "B")`. Amikor megpróbálja menteni ezt a kifejezést az ER-képlettervezőben, a következő kivétel történik: „Érvényesítési hiba: A FILTER függvény listakifejezése nem elérhető.”

## <a name="additional-resources"></a>További erőforrások

[Lista függvények](er-functions-category-list.md)
