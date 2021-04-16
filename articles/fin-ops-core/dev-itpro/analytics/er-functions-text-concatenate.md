---
title: CONCATENATE ER-függvény
description: A témakör tájékoztatást nyújt a CONCATENATE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
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
ms.openlocfilehash: f1a47a05127412588f4628cb425eab0379493c3c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746482"
---
# <a name="concatenate-er-function"></a><span data-ttu-id="c2a43-103">CONCATENATE ER-függvény</span><span class="sxs-lookup"><span data-stu-id="c2a43-103">CONCATENATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c2a43-104">A `CONCATENATE` függvény az összes megadott karakterláncot *Karakterlánc* értékként adja vissza, miután egy karakterláncba lettek egyesítve.</span><span class="sxs-lookup"><span data-stu-id="c2a43-104">The `CONCATENATE` function returns all the specified text strings as a *String* value after they have been joined into one string.</span></span>

## <a name="syntax"></a><span data-ttu-id="c2a43-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="c2a43-105">Syntax</span></span>

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a><span data-ttu-id="c2a43-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="c2a43-106">Arguments</span></span>

<span data-ttu-id="c2a43-107">`text 1`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="c2a43-107">`text 1`: *String*</span></span>

<span data-ttu-id="c2a43-108">Hivatkozás a *Karakterlánc* adattípusú adatforrásra.</span><span class="sxs-lookup"><span data-stu-id="c2a43-108">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="c2a43-109">Az argumentum megadása kötelező.</span><span class="sxs-lookup"><span data-stu-id="c2a43-109">This argument is required.</span></span>

<span data-ttu-id="c2a43-110">`text N`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="c2a43-110">`text N`: *String*</span></span>

<span data-ttu-id="c2a43-111">Hivatkozás a *Karakterlánc* adattípusú adatforrásra.</span><span class="sxs-lookup"><span data-stu-id="c2a43-111">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="c2a43-112">Ezek a további argumentumok nem kötelezők.</span><span class="sxs-lookup"><span data-stu-id="c2a43-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="c2a43-113">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="c2a43-113">Return values</span></span>

<span data-ttu-id="c2a43-114">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="c2a43-114">*String*</span></span>

<span data-ttu-id="c2a43-115">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="c2a43-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="c2a43-116">Példa</span><span class="sxs-lookup"><span data-stu-id="c2a43-116">Example</span></span>

<span data-ttu-id="c2a43-117">A `CONCATENATE ("abc", "def")` az **"abcdef"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="c2a43-117">`CONCATENATE ("abc", "def")` returns **"abcdef"**.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="c2a43-118">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="c2a43-118">Usage notes</span></span>

<span data-ttu-id="c2a43-119">Az `"abc" & "def"` kifejezés szintén az **"abcdef"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="c2a43-119">The expression `"abc" & "def"` also returns **"abcdef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c2a43-120">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c2a43-120">Additional resources</span></span>

[<span data-ttu-id="c2a43-121">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="c2a43-121">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]