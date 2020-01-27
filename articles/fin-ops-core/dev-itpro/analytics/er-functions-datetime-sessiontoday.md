---
title: SESSIONTODAY ER-függvény
description: A témakör tájékoztatást nyújt a SESSIONTODAY Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: bcfb36d6e3fb8475546f7cfb420c4aca848ac896
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917465"
---
# <a name="SESSIONTODAY">SESSIONTODAY ER-függvény</a>

[!include [banner](../includes/banner.md)]

A `SESSIONTODAY` függvény egy *Dátum* értéket ad eredményül, amely az alkalmazás-munkamenet aktuális dátumát mutatja.

## <a name="syntax"></a>Szintaxis

```
SESSIONTODAY ()
```

## <a name="return-values"></a>Visszaadott értékek

*Dátum*

Az eredményül kapott dátumérték.

## <a name="example"></a>Példa

A `DATEFORMAT (SESSIONTODAY (), "d", "DE")` az aktuális alkalmazás-munkamenet dátumát adja vissza (2015. december 24.) a **"24-12-2015"** karakterláncként a kiválasztott német területi beállítás és a megadott formátum alapján.

## <a name="additional-resources"></a>További erőforrások

[Dátum és idő függvények](er-functions-category-datetime.md)
