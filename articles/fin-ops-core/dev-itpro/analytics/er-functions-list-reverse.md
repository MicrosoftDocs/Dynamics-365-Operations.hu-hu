---
title: REVERSE ER-függvény
description: A témakör tájékoztatást nyújt a REVERSE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 895d5f13f065b2188f245d081fa69e7e63555dde
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686440"
---
# <a name="reverse-er-function"></a>REVERSE ER-függvény

[!include [banner](../includes/banner.md)]

A `REVERSE` függvény a megadott listát *Rekordlista* értékként adja vissza fordított rendezési sorrendben.

## <a name="syntax"></a>Szintaxis

```vb
REVERSE (list)
```

## <a name="arguments"></a>Argumentumok

`list`: *Rekordlista*

A *Rekordlista* adattípus adatforrásának érvényes elérési útja.

## <a name="return-values"></a>Visszaadott értékek

*Rekordlista*

A rekordok eredményül kapott listája.

## <a name="example-1"></a>1. példa

Ha megadja a *Számított mező* típusú **DS** adatforrást és az tartalmazza a `SPLIT ("C|B|A", "|")` kifejezést, akkor a `FIRST( REVERSE( ORDERBY( DS, DS. Value))).Value` kifejezés a **„C”** szöveges értéket adja vissza.

## <a name="example-2"></a>2. példa

Ha **Szállító** a VendTable táblára hivatkozó Elektronikus jelentéskészítési (ER) adatforrásként van konfigurálva, akkor a `REVERSE (ORDERBY (Vendors, Vendors.'name()'))` kifejezés megjeleníti a név szerinti csökkenő sorrendben rendezett szállítók listáját.

## <a name="additional-resources"></a>További erőforrások

[Lista függvények](er-functions-category-list.md)
