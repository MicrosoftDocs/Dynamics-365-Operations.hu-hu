---
title: LOWER ER-függvény
description: A témakör tájékoztatást nyújt a LOWER Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: b016feb0c907ef384eae91840791c357d61cf634
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916821"
---
# <span data-ttu-id="8bbdc-103"><a name="LOWER">LOWER ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="8bbdc-103"><a name="LOWER">LOWER ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8bbdc-104">A `LOWER` függvény *Karakterlánc* értékként adja vissza a megadott karakterláncot, miután a program kisbetűssé alakította.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-104">The `LOWER` function returns the specified text string as a *String* value after it has been converted to lowercase letters.</span></span>

## <a name="syntax"></a><span data-ttu-id="8bbdc-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="8bbdc-105">Syntax</span></span>

```
LOWER (text)
```

## <a name="arguments"></a><span data-ttu-id="8bbdc-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="8bbdc-106">Arguments</span></span>

<span data-ttu-id="8bbdc-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="8bbdc-107">`text`: *String*</span></span>

<span data-ttu-id="8bbdc-108">Az eredeti szöveget jelölő *Karakterlánc* érték.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-108">A *String* value that specifies the text.</span></span>

## <a name="return-values"></a><span data-ttu-id="8bbdc-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="8bbdc-109">Return values</span></span>

<span data-ttu-id="8bbdc-110">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="8bbdc-110">*String*</span></span>

<span data-ttu-id="8bbdc-111">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="8bbdc-112">Példa</span><span class="sxs-lookup"><span data-stu-id="8bbdc-112">Example</span></span>

<span data-ttu-id="8bbdc-113">A `LOWER ("Sample")` a **"sample"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-113">`LOWER ("Sample")` returns **"sample"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8bbdc-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="8bbdc-114">Additional resources</span></span>

[<span data-ttu-id="8bbdc-115">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="8bbdc-115">Text functions</span></span>](er-functions-category-text.md)
