---
title: CONCATENATE ER-függvény
description: A témakör tájékoztatást nyújt a CONCATENATE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 6e4800ce44d9da07818acec55c50224a9a000fe6
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569605"
---
# <a name="concatenate-er-function"></a><span data-ttu-id="fe738-103">CONCATENATE ER-függvény</span><span class="sxs-lookup"><span data-stu-id="fe738-103">CONCATENATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fe738-104">A `CONCATENATE` függvény az összes megadott karakterláncot *Karakterlánc* értékként adja vissza, miután egy karakterláncba lettek egyesítve.</span><span class="sxs-lookup"><span data-stu-id="fe738-104">The `CONCATENATE` function returns all the specified text strings as a *String* value after they have been joined into one string.</span></span>

## <a name="syntax"></a><span data-ttu-id="fe738-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="fe738-105">Syntax</span></span>

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a><span data-ttu-id="fe738-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="fe738-106">Arguments</span></span>

<span data-ttu-id="fe738-107">`text 1`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="fe738-107">`text 1`: *String*</span></span>

<span data-ttu-id="fe738-108">Hivatkozás a *Karakterlánc* adattípusú adatforrásra.</span><span class="sxs-lookup"><span data-stu-id="fe738-108">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="fe738-109">Az argumentum megadása kötelező.</span><span class="sxs-lookup"><span data-stu-id="fe738-109">This argument is required.</span></span>

<span data-ttu-id="fe738-110">`text N`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="fe738-110">`text N`: *String*</span></span>

<span data-ttu-id="fe738-111">Hivatkozás a *Karakterlánc* adattípusú adatforrásra.</span><span class="sxs-lookup"><span data-stu-id="fe738-111">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="fe738-112">Ezek a további argumentumok nem kötelezők.</span><span class="sxs-lookup"><span data-stu-id="fe738-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="fe738-113">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="fe738-113">Return values</span></span>

<span data-ttu-id="fe738-114">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="fe738-114">*String*</span></span>

<span data-ttu-id="fe738-115">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="fe738-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="fe738-116">Példa</span><span class="sxs-lookup"><span data-stu-id="fe738-116">Example</span></span>

<span data-ttu-id="fe738-117">A `CONCATENATE ("abc", "def")` az **"abcdef"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="fe738-117">`CONCATENATE ("abc", "def")` returns **"abcdef"**.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="fe738-118">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="fe738-118">Usage notes</span></span>

<span data-ttu-id="fe738-119">Az `"abc" & "def"` kifejezés szintén az **"abcdef"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="fe738-119">The expression `"abc" & "def"` also returns **"abcdef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fe738-120">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="fe738-120">Additional resources</span></span>

[<span data-ttu-id="fe738-121">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="fe738-121">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]