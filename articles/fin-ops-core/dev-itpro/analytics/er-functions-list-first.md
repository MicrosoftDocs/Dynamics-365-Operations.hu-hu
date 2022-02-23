---
title: FIRST ER-függvény
description: A témakör tájékoztatást nyújt a FIRST Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: a5c52d3f999b4c6fbdea0685977ab13fca1e8ffb
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679414"
---
# <a name="first-er-function"></a>FIRST ER-függvény

[!include [banner](../includes/banner.md)]

A `FIRST` függvény a megadott lista első rekordját *Tároló (rekord)* értékként adja vissza, ha a lista nem üres. Ha a lista üres, a függvény kivételt dob.

## <a name="syntax"></a>Szintaxis

```vb
FIRST (list)
```

## <a name="arguments"></a>Argumentumok

`list`: *Rekordlista*

A *Rekordlista* adattípus adatforrásának érvényes elérési útja.

## <a name="return-values"></a>Visszaadott értékek

*Tároló (rekord)*

Az eredményül kapott rekordérték.

## <a name="example-1"></a>1. példa

Az `FIRST(SPLIT("ABC",1)).Value` kifejezés az **„A”** szöveges értéket adja eredményül.

## <a name="example-2"></a>2. példa

A `FIRST(SPLIT("",1)).Value` kifejezés futásidőben kivételt dob.

## <a name="additional-resources"></a>További erőforrások

[Lista függvények](er-functions-category-list.md)
