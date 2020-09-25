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
ms.openlocfilehash: 1a21140e5636ebd96eca4be90308c915e77510e1
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743903"
---
# <a name="concatenate-er-function"></a><span data-ttu-id="0351f-103">CONCATENATE ER-függvény</span><span class="sxs-lookup"><span data-stu-id="0351f-103">CONCATENATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0351f-104">A `CONCATENATE` függvény az összes megadott karakterláncot *Karakterlánc* értékként adja vissza, miután egy karakterláncba lettek egyesítve.</span><span class="sxs-lookup"><span data-stu-id="0351f-104">The `CONCATENATE` function returns all the specified text strings as a *String* value after they have been joined into one string.</span></span>

## <a name="syntax"></a><span data-ttu-id="0351f-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="0351f-105">Syntax</span></span>

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a><span data-ttu-id="0351f-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="0351f-106">Arguments</span></span>

<span data-ttu-id="0351f-107">`text 1`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="0351f-107">`text 1`: *String*</span></span>

<span data-ttu-id="0351f-108">Hivatkozás a *Karakterlánc* adattípusú adatforrásra.</span><span class="sxs-lookup"><span data-stu-id="0351f-108">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="0351f-109">Az argumentum megadása kötelező.</span><span class="sxs-lookup"><span data-stu-id="0351f-109">This argument is required.</span></span>

<span data-ttu-id="0351f-110">`text N`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="0351f-110">`text N`: *String*</span></span>

<span data-ttu-id="0351f-111">Hivatkozás a *Karakterlánc* adattípusú adatforrásra.</span><span class="sxs-lookup"><span data-stu-id="0351f-111">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="0351f-112">Ezek a további argumentumok nem kötelezők.</span><span class="sxs-lookup"><span data-stu-id="0351f-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="0351f-113">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="0351f-113">Return values</span></span>

<span data-ttu-id="0351f-114">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="0351f-114">*String*</span></span>

<span data-ttu-id="0351f-115">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="0351f-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="0351f-116">Példa</span><span class="sxs-lookup"><span data-stu-id="0351f-116">Example</span></span>

<span data-ttu-id="0351f-117">A `CONCATENATE ("abc", "def")` az **"abcdef"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="0351f-117">`CONCATENATE ("abc", "def")` returns **"abcdef"**.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="0351f-118">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="0351f-118">Usage notes</span></span>

<span data-ttu-id="0351f-119">Az `"abc" & "def"` kifejezés szintén az **"abcdef"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="0351f-119">The expression `"abc" & "def"` also returns **"abcdef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0351f-120">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="0351f-120">Additional resources</span></span>

[<span data-ttu-id="0351f-121">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="0351f-121">Text functions</span></span>](er-functions-category-text.md)
