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
ms.openlocfilehash: 04c7b32e2a9578f8864570a552817ec3ce28fa43
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041167"
---
# <span data-ttu-id="26c18-103"><a name="CONCATENATE">CONCATENATE ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="26c18-103"><a name="CONCATENATE">CONCATENATE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="26c18-104">A `CONCATENATE` függvény az összes megadott karakterláncot *Karakterlánc* értékként adja vissza, miután egy karakterláncba lettek egyesítve.</span><span class="sxs-lookup"><span data-stu-id="26c18-104">The `CONCATENATE` function returns all the specified text strings as a *String* value after they have been joined into one string.</span></span>

## <a name="syntax"></a><span data-ttu-id="26c18-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="26c18-105">Syntax</span></span>

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a><span data-ttu-id="26c18-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="26c18-106">Arguments</span></span>

<span data-ttu-id="26c18-107">`text 1`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="26c18-107">`text 1`: *String*</span></span>

<span data-ttu-id="26c18-108">Hivatkozás a *Karakterlánc* adattípusú adatforrásra.</span><span class="sxs-lookup"><span data-stu-id="26c18-108">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="26c18-109">Az argumentum megadása kötelező.</span><span class="sxs-lookup"><span data-stu-id="26c18-109">This argument is required.</span></span>

<span data-ttu-id="26c18-110">`text N`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="26c18-110">`text N`: *String*</span></span>

<span data-ttu-id="26c18-111">Hivatkozás a *Karakterlánc* adattípusú adatforrásra.</span><span class="sxs-lookup"><span data-stu-id="26c18-111">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="26c18-112">Ezek a további argumentumok nem kötelezők.</span><span class="sxs-lookup"><span data-stu-id="26c18-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="26c18-113">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="26c18-113">Return values</span></span>

<span data-ttu-id="26c18-114">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="26c18-114">*String*</span></span>

<span data-ttu-id="26c18-115">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="26c18-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="26c18-116">Példa</span><span class="sxs-lookup"><span data-stu-id="26c18-116">Example</span></span>

<span data-ttu-id="26c18-117">A `CONCATENATE ("abc", "def")` az **"abcdef"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="26c18-117">`CONCATENATE ("abc", "def")` returns **"abcdef"**.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="26c18-118">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="26c18-118">Usage notes</span></span>

<span data-ttu-id="26c18-119">Az `"abc" & "def"` kifejezés szintén az **"abcdef"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="26c18-119">The expression `"abc" & "def"` also returns **"abcdef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="26c18-120">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="26c18-120">Additional resources</span></span>

[<span data-ttu-id="26c18-121">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="26c18-121">Text functions</span></span>](er-functions-category-text.md)
