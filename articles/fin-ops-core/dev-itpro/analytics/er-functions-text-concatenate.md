---
title: CONCATENATE ER-függvény
description: A témakör tájékoztatást nyújt a CONCATENATE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: e3d3ff87a59632d58a7c34ef96f856b38f005651
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915763"
---
# <span data-ttu-id="94faf-103"><a name="CONCATENATE">CONCATENATE ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="94faf-103"><a name="CONCATENATE">CONCATENATE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="94faf-104">A `CONCATENATE` függvény az összes megadott karakterláncot *Karakterlánc* értékként adja vissza, miután egy karakterláncba lettek egyesítve.</span><span class="sxs-lookup"><span data-stu-id="94faf-104">The `CONCATENATE` function returns all the specified text strings as a *String* value after they have been joined into one string.</span></span>

## <a name="syntax"></a><span data-ttu-id="94faf-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="94faf-105">Syntax</span></span>

```
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a><span data-ttu-id="94faf-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="94faf-106">Arguments</span></span>

<span data-ttu-id="94faf-107">`text 1`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="94faf-107">`text 1`: *String*</span></span>

<span data-ttu-id="94faf-108">Hivatkozás a *Karakterlánc* adattípusú adatforrásra.</span><span class="sxs-lookup"><span data-stu-id="94faf-108">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="94faf-109">Az argumentum megadása kötelező.</span><span class="sxs-lookup"><span data-stu-id="94faf-109">This argument is required.</span></span>

<span data-ttu-id="94faf-110">`text N`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="94faf-110">`text N`: *String*</span></span>

<span data-ttu-id="94faf-111">Hivatkozás a *Karakterlánc* adattípusú adatforrásra.</span><span class="sxs-lookup"><span data-stu-id="94faf-111">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="94faf-112">Ezek a további argumentumok nem kötelezők.</span><span class="sxs-lookup"><span data-stu-id="94faf-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="94faf-113">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="94faf-113">Return values</span></span>

<span data-ttu-id="94faf-114">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="94faf-114">*String*</span></span>

<span data-ttu-id="94faf-115">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="94faf-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="94faf-116">Példa</span><span class="sxs-lookup"><span data-stu-id="94faf-116">Example</span></span>

<span data-ttu-id="94faf-117">A `CONCATENATE ("abc", "def")` az **"abcdef"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="94faf-117">`CONCATENATE ("abc", "def")` returns **"abcdef"**.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="94faf-118">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="94faf-118">Usage notes</span></span>

<span data-ttu-id="94faf-119">Az `"abc" & "def"` kifejezés szintén az **"abcdef"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="94faf-119">The expression `"abc" & "def"` also returns **"abcdef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="94faf-120">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="94faf-120">Additional resources</span></span>

[<span data-ttu-id="94faf-121">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="94faf-121">Text functions</span></span>](er-functions-category-text.md)
