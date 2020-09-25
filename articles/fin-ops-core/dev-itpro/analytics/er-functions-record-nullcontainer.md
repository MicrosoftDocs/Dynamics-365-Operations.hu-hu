---
title: NULLCONTAINER ER-függvény
description: A témakör tájékoztatást nyújt a NULLCONTAINER Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: dac6283ec35d3d03f586ca157048bd3ecc4bfa8a
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743927"
---
# <a name="nullcontainer-er-function"></a>NULLCONTAINER ER-függvény

[!include [banner](../includes/banner.md)]

A `NULLCONTAINER` függvény egy nulla *Tároló (rekord)* értéket ad vissza, amely ugyanazzal a struktúrával rendelkezik, mint a megadott rekordlista vagy rekord.

## <a name="syntax"></a>Szintaxis

```vb
NULLCONTAINER (list)
```

## <a name="arguments"></a>Argumentumok

`list`: *Rekordlista* vagy *Tároló (rekord)*

A *Rekordlista* vagy *Tároló (rekord)* típusú adatforrás érvényes elérési útja.

## <a name="return-values"></a>Visszaadott értékek

*Tároló (rekord)*

Az eredményül kapott rekordérték.

## <a name="usage-notes"></a>Használati megjegyzések

> [!NOTE] 
> Ez a funkció már elavult. Használja helyette az `EMPTYRECORD` függvényt. További tudnivalók: [EMPTYRECORD](er-functions-record-emptyrecord.md).

## <a name="example"></a>Példa

A `NULLCONTAINER (SPLIT ("abc", 1))` új üres rekordot ad vissza, amelynek ugyanolyan szerkezete van, mint a `SPLIT` funkció által megjelenített listának. További tudnivalók: [SPLIT](er-functions-list-split.md).

## <a name="additional-resources"></a>További erőforrások

[Rekord függvények](er-functions-category-record.md)
