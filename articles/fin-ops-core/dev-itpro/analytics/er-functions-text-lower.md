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
ms.openlocfilehash: 12577e571c8e87db79395895e2a22e66ee7df32c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745681"
---
# <a name="lower-er-function"></a><span data-ttu-id="79bc3-103">LOWER ER-függvény</span><span class="sxs-lookup"><span data-stu-id="79bc3-103">LOWER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="79bc3-104">A `LOWER` függvény *Karakterlánc* értékként adja vissza a megadott karakterláncot, miután a program kisbetűssé alakította.</span><span class="sxs-lookup"><span data-stu-id="79bc3-104">The `LOWER` function returns the specified text string as a *String* value after it has been converted to lowercase letters.</span></span>

## <a name="syntax"></a><span data-ttu-id="79bc3-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="79bc3-105">Syntax</span></span>

```vb
LOWER (text)
```

## <a name="arguments"></a><span data-ttu-id="79bc3-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="79bc3-106">Arguments</span></span>

<span data-ttu-id="79bc3-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="79bc3-107">`text`: *String*</span></span>

<span data-ttu-id="79bc3-108">Az eredeti szöveget jelölő *Karakterlánc* érték.</span><span class="sxs-lookup"><span data-stu-id="79bc3-108">A *String* value that specifies the text.</span></span>

## <a name="return-values"></a><span data-ttu-id="79bc3-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="79bc3-109">Return values</span></span>

<span data-ttu-id="79bc3-110">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="79bc3-110">*String*</span></span>

<span data-ttu-id="79bc3-111">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="79bc3-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="79bc3-112">Példa</span><span class="sxs-lookup"><span data-stu-id="79bc3-112">Example</span></span>

<span data-ttu-id="79bc3-113">A `LOWER ("Sample")` a **"sample"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="79bc3-113">`LOWER ("Sample")` returns **"sample"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="79bc3-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="79bc3-114">Additional resources</span></span>

[<span data-ttu-id="79bc3-115">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="79bc3-115">Text functions</span></span>](er-functions-category-text.md)
