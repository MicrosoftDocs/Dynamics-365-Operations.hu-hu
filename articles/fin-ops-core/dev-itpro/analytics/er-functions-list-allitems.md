---
title: ALLITEMS ER-függvény
description: A témakör tájékoztatást nyújt az ALLITEMS Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 47113d52e15d3d61f00b3c54229e286eb0f1a8d7
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745393"
---
# <a name="allitems-er-function"></a>ALLITEMS ER-függvény

[!include [banner](../includes/banner.md)]

Az `ALLITEMS` függvény a memóriában lévő kiválasztásként fut, és egy új, összevont *Rekordlista* értéket ad eredményül rekordok listájaként, amely a megadott elérési útnak megfelelő összes elemet képviseli.

## <a name="syntax"></a>Szintaxis

```vb
ALLITEMS (path)
```

## <a name="arguments"></a>Argumentumok

`path`: *Rekordlista*

A *Rekordlista* adattípus adatforrásának érvényes elérési útja.

## <a name="return-values"></a>Visszaadott értékek

*Rekordlista*

A rekordok eredményül kapott listája.

## <a name="usage-notes"></a>Használati megjegyzések

Az elérési utat egy érvényes adatforrás útvonalaként kell megadni a *Rekordlista* adattípus adatforrásához. Adatelemek (például az elérési út karakterlánc és dátum eleme) hibaüzenetet jelenítenek meg az Elektronikus jelentéskészítés (ER) kifejezésszerkesztőben tervezéskor.

Ezt a függvényt nem ajánlott olyan tranzakciós adatforrásokhoz használni, amelyek nagy mennyiségű adatot tartalmazhatnak. Ehelyett érdemes az [ALLTEMSQUERY](er-functions-list-allitemsquery.md) függvényt használni.

## <a name="example-1"></a>1. példa

Ha megadja a `SPLIT("abcdef" , 2)` kifejezést **DS** adatforrásként, akkor a `COUNT( ALLITEMS (DS))` kifejezés a **3** értéket adja eredményül.

## <a name="example-2"></a>2. példa

Ha a **Szállító** értéket adja meg a *Rekordlista* adattípus adatforrásaként, amely a VendTable alkalmazástáblára hivatkozik, az `ALLITEMS (Vend.'<Relations'.ContactPerson)` kifejezés egy olyan összevont rekordlistát ad eredményül, amely tartalmazza a **ContactPerson** táblaszerkezetet, és minden olyan kapcsolattartót tartalmaz, amely a **ContactPerson.ContactForParty == VendTable.Party** objektumkapcsolat használatával hozzáférhető, és a hivatkozott szállítói tábla összes szállítója számára elérhető.

## <a name="additional-resources"></a>További erőforrások

[Lista függvények](er-functions-category-list.md)
