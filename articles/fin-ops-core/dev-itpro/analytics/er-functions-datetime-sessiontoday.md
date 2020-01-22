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
# <span data-ttu-id="46bac-103"><a name="SESSIONTODAY">SESSIONTODAY ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="46bac-103"><a name="SESSIONTODAY">SESSIONTODAY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="46bac-104">A `SESSIONTODAY` függvény egy *Dátum* értéket ad eredményül, amely az alkalmazás-munkamenet aktuális dátumát mutatja.</span><span class="sxs-lookup"><span data-stu-id="46bac-104">The `SESSIONTODAY` function returns a *Date* value that represents the current application session date.</span></span>

## <a name="syntax"></a><span data-ttu-id="46bac-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="46bac-105">Syntax</span></span>

```
SESSIONTODAY ()
```

## <a name="return-values"></a><span data-ttu-id="46bac-106">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="46bac-106">Return values</span></span>

<span data-ttu-id="46bac-107">*Dátum*</span><span class="sxs-lookup"><span data-stu-id="46bac-107">*Date*</span></span>

<span data-ttu-id="46bac-108">Az eredményül kapott dátumérték.</span><span class="sxs-lookup"><span data-stu-id="46bac-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="46bac-109">Példa</span><span class="sxs-lookup"><span data-stu-id="46bac-109">Example</span></span>

<span data-ttu-id="46bac-110">A `DATEFORMAT (SESSIONTODAY (), "d", "DE")` az aktuális alkalmazás-munkamenet dátumát adja vissza (2015. december 24.) a **"24-12-2015"** karakterláncként a kiválasztott német területi beállítás és a megadott formátum alapján.</span><span class="sxs-lookup"><span data-stu-id="46bac-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="46bac-111">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="46bac-111">Additional resources</span></span>

[<span data-ttu-id="46bac-112">Dátum és idő függvények</span><span class="sxs-lookup"><span data-stu-id="46bac-112">Date and time functions</span></span>](er-functions-category-datetime.md)
