---
title: LISTOFFIRSTITEM ER-függvény
description: A témakör tájékoztatást nyújt a LISTOFFIRSTITEM Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 069ec0c6d5578ca6ab68814adf325bd79e73b9e8
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745057"
---
# <a name="listoffirstitem-er-function"></a>LISTOFFIRSTITEM ER-függvény

[!include [banner](../includes/banner.md)]

A `LISTOFFIRSTITEM` függvény egy *Rekordlista* értéket ad vissza, amely csak a megadott lista első rekordjából áll.

## <a name="syntax"></a>Szintaxis

```vb
LISTOFFIRSTITEM (list)
```

## <a name="arguments"></a>Argumentumok

`list`: *Rekordlista*

A *Rekordlista* adattípus adatforrásának érvényes elérési útja.

## <a name="return-values"></a>Visszaadott értékek

*Rekordlista*

A rekordok eredményül kapott listája.

## <a name="example"></a>Példa

A `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` kifejezés az **„A”** szöveges értéket adja eredményül.

## <a name="additional-resources"></a>További erőforrások

[Lista függvények](er-functions-category-list.md)
