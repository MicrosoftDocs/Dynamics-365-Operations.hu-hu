---
title: LOWER ER-függvény
description: A témakör tájékoztatást nyújt a LOWER Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/11/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: e507a17f5125a3cba0d2434a1aaec0f04f0cd388
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562783"
---
# <a name="lower-er-function"></a><span data-ttu-id="ca5f4-103">LOWER ER-függvény</span><span class="sxs-lookup"><span data-stu-id="ca5f4-103">LOWER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ca5f4-104">A `LOWER` függvény *Karakterlánc* értékként adja vissza a megadott karakterláncot, miután a program kisbetűssé alakította.</span><span class="sxs-lookup"><span data-stu-id="ca5f4-104">The `LOWER` function returns the specified text string as a *String* value after it has been converted to lowercase letters.</span></span>

## <a name="syntax"></a><span data-ttu-id="ca5f4-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="ca5f4-105">Syntax</span></span>

```vb
LOWER (text)
```

## <a name="arguments"></a><span data-ttu-id="ca5f4-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="ca5f4-106">Arguments</span></span>

<span data-ttu-id="ca5f4-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="ca5f4-107">`text`: *String*</span></span>

<span data-ttu-id="ca5f4-108">Az eredeti szöveget jelölő *Karakterlánc* érték.</span><span class="sxs-lookup"><span data-stu-id="ca5f4-108">A *String* value that specifies the text.</span></span>

## <a name="return-values"></a><span data-ttu-id="ca5f4-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="ca5f4-109">Return values</span></span>

<span data-ttu-id="ca5f4-110">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="ca5f4-110">*String*</span></span>

<span data-ttu-id="ca5f4-111">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="ca5f4-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="ca5f4-112">Példa</span><span class="sxs-lookup"><span data-stu-id="ca5f4-112">Example</span></span>

<span data-ttu-id="ca5f4-113">A `LOWER ("Sample")` a **"sample"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="ca5f4-113">`LOWER ("Sample")` returns **"sample"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ca5f4-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="ca5f4-114">Additional resources</span></span>

[<span data-ttu-id="ca5f4-115">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="ca5f4-115">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]