---
title: ISEMPTY ER-függvény
description: A témakör tájékoztatást nyújt az ISEMPTY Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 5dbba375104b57f9fb09ed4e330d85181ec0dff8
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684883"
---
# <a name="isempty-er-function"></a>ISEMPTY ER-függvény

[!include [banner](../includes/banner.md)]

Az `ISEMPTY` függvény **IGAZ** *Logikai* értéket ad eredményül, ha a megadott lista nem tartalmaz rekordokat. Ellenkező esetben **HAMIS** *logikai* eredményt ad.

## <a name="syntax"></a>Szintaxis

```vb
ISEMPTY (list)
```

## <a name="arguments"></a>Argumentumok

`list`: *Rekordlista*

A *Rekordlista* adattípus adatforrásának érvényes elérési útja.

## <a name="return-values"></a>Visszaadott értékek

*Logikai*

Az eredményül kapott *Logikai* érték.

## <a name="example-1"></a>1. példa

Ha megadja a *Számított mező* típusú **DS** adatforrást és az tartalmazza a `SPLIT ("A|B|C", "|")` kifejezést, akkor a `ISEMPTY(DS)` kifejezés a **HAMIS** értéket adja vissza.

## <a name="example-2"></a>2. példa

Az `ISEMPTY (SPLIT ("",1))` kifejezés az **IGAZ** értéket adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Lista függvények](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]