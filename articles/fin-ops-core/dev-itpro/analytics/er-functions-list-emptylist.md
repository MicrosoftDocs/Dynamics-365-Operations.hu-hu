---
title: EMPTYLIST ER-függvény
description: A témakör tájékoztatást nyújt az EMPTYLIST Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 5fb991eb9ee08aeb418313eb782dbde7fa22b763
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042182"
---
# <a name="EMPTYLIST">EMPTYLIST ER-függvény</a>

[!include [banner](../includes/banner.md)]

Az `EMPTYLIST` függvény a megadott lista forrásként való felhasználásával egy üres *Rekordlista* értéket ad vissza a lista szerkezetére vonatkozó forrásként.

## <a name="syntax"></a>Szintaxis

```vb
EMPTYLIST (list)
```

## <a name="arguments"></a>Argumentumok

`list`: *Rekordlista*

A *Rekordlista* adattípus adatforrásának érvényes elérési útja.

## <a name="return-values"></a>Visszaadott értékek

*Rekordlista*

A rekordok eredményül kapott listája.

## <a name="example"></a>Példa

A `EMPTYLIST (SPLIT ("abc", 1))` új üres listát ad vissza, amelynek ugyanolyan szerkezete van, mint a felhasznált `SPLIT` függvény által megjelenített listának.

## <a name="additional-resources"></a>További erőforrások

[Lista függvények](er-functions-category-list.md)
