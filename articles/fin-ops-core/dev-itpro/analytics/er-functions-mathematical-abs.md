---
title: ABS ER-függvény
description: A témakör tájékoztatást nyújt az ABS Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 3c7156b9990397822a6bea9ed8b3df8f65490572
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683281"
---
# <a name="abs-er-function"></a>ABS ER-függvény

[!include [banner](../includes/banner.md)]

Az `ABS` függvény a megadott szám abszolútértékét (modulus) adja eredményül *Valós* értékként. Más szóval, a számot előjel nélkül adja vissza.

## <a name="syntax"></a>Szintaxis

```vb
ABS (number)
```

## <a name="arguments"></a>Argumentumok

`number`: *Valós*

Egy numerikus érték, amelynek a modulus értékét meg szeretné jeleníteni.

## <a name="return-values"></a>Visszaadott értékek

*Valós*

Az eredményül kapott numerikus érték.

## <a name="example"></a>Példa

Az `ABS (-1)` az **1** értéket adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Matematikai funkciók](er-functions-category-mathematical.md)
