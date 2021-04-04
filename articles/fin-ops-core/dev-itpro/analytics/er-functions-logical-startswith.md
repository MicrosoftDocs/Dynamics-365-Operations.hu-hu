---
title: STARTSWITH ER függvény
description: A témakör tájékoztatást nyújt a STARTSWITH Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 02/11/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: AX 10.0.18
ms.openlocfilehash: 22e99d9e131410820abd12536b8d4f3e868c6863
ms.sourcegitcommit: 08ac570bece3e4ee4a0f632f51623e328536dfcf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/08/2021
ms.locfileid: "5557525"
---
# <a name="startswith-er-function"></a><span data-ttu-id="d863c-103">STARTSWITH ER függvény</span><span class="sxs-lookup"><span data-stu-id="d863c-103">STARTSWITH ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d863c-104">A `STARTSWITH` függvény határozza meg, hogy a megadott bemenet a megadott szöveggel kezdődik-e.</span><span class="sxs-lookup"><span data-stu-id="d863c-104">The `STARTSWITH` function determines whether the specified input starts with the specified text.</span></span> <span data-ttu-id="d863c-105">A visszaadott *logikai* érték **IGAZ** lesz, ha a megadott bemenet a megadott szövegre kezdődik.</span><span class="sxs-lookup"><span data-stu-id="d863c-105">It returns a *Boolean* value of **TRUE** if the specified input starts with the specified text.</span></span> <span data-ttu-id="d863c-106">Ellenkező esetben **HAMIS** *logikai* eredményt ad.</span><span class="sxs-lookup"><span data-stu-id="d863c-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="d863c-107">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="d863c-107">Syntax</span></span>

```vb
STARTSWITH (input, start text)
```

## <a name="arguments"></a><span data-ttu-id="d863c-108">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="d863c-108">Arguments</span></span>

<span data-ttu-id="d863c-109">`input`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="d863c-109">`input`: *String*</span></span>

<span data-ttu-id="d863c-110">A *Sztring* típusú adatforrás elemének vagy egy sztring konstans érvényes útvonala, amelynek értéke a második argumentummal kezdődhet.</span><span class="sxs-lookup"><span data-stu-id="d863c-110">The valid path of an item of a data source of the *String* type or a string constant, the value of which might start with the second argument.</span></span>

<span data-ttu-id="d863c-111">`start text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="d863c-111">`start text`: *String*</span></span>

<span data-ttu-id="d863c-112">A *Sztring* típusú adatforrás vagy egy sztring konstans érvényes útvonala, amely az első argumentum elején lehet.</span><span class="sxs-lookup"><span data-stu-id="d863c-112">The valid path of a data source of the *String* data type or a string constant, the value of which might be at the beginning of the first argument.</span></span>

## <a name="return-values"></a><span data-ttu-id="d863c-113">Visszatérési értékek</span><span class="sxs-lookup"><span data-stu-id="d863c-113">Return values</span></span>

<span data-ttu-id="d863c-114">*Logikai*</span><span class="sxs-lookup"><span data-stu-id="d863c-114">*Boolean*</span></span>

<span data-ttu-id="d863c-115">Az eredményül kapott *Logikai* érték.</span><span class="sxs-lookup"><span data-stu-id="d863c-115">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="d863c-116">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="d863c-116">Usage notes</span></span>

<span data-ttu-id="d863c-117">Ezzel a funkcióval csak akkor lehet megadni a [FILTER](er-functions-list-filter.md) függvény feltételkifejezését, ha a megfelelő hozzárendelés a [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) be van állítva a [Microsoft Dataverse](../data-entities/data-integration-cds.md) szolgáltatáshoz való hozzáféréshez.</span><span class="sxs-lookup"><span data-stu-id="d863c-117">This function can be used to specify a condition expression of the [FILTER](er-functions-list-filter.md) function only when the relevant mapping is configured in [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) to access [Microsoft Dataverse](../data-entities/data-integration-cds.md).</span></span> <span data-ttu-id="d863c-118">Ellenkező esetben a rendszer kivételt ad a tervezéskor.</span><span class="sxs-lookup"><span data-stu-id="d863c-118">Otherwise, an exception is thrown at design time.</span></span> <span data-ttu-id="d863c-119">A kapott üzenet azt javasolja, hogy a hatásfok növelése érdekében a [WHERE](er-functions-list-where.md) függvény helyett a `FILTER` függvényt használja.</span><span class="sxs-lookup"><span data-stu-id="d863c-119">The message that you receive recommends that you use the [WHERE](er-functions-list-where.md) function instead of the `FILTER` function.</span></span>

## <a name="example-1"></a><span data-ttu-id="d863c-120">1. példa</span><span class="sxs-lookup"><span data-stu-id="d863c-120">Example 1</span></span>

<span data-ttu-id="d863c-121">A `STARTSWITH ("abc", "d")` **HAMIS** eredményt ad, az `STARTSWITH ("abc", "A")` kifejezés pedig **IGAZ** eredményt ad.</span><span class="sxs-lookup"><span data-stu-id="d863c-121">The expression `STARTSWITH ("abc", "d")` returns **FALSE**, whereas the expression `STARTSWITH ("abc", "A")` returns **TRUE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="d863c-122">2. példa</span><span class="sxs-lookup"><span data-stu-id="d863c-122">Example 2</span></span>

<span data-ttu-id="d863c-123">A `STARTSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "123 Coffee Street")` kifejezés értéke **IGAZ**, ha a **modell** adatforrás **Cím** mezőjének értéke az **123 Coffee Street** sztringgel kezdődik.</span><span class="sxs-lookup"><span data-stu-id="d863c-123">The expression `STARTSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "123 Coffee Street")` returns **TRUE** if the value of the **Address** field of the **model** data source starts with the string **123 Coffee Street**.</span></span> <span data-ttu-id="d863c-124">Ellenkező esetben **HAMIS** választ jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="d863c-124">Otherwise, it returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d863c-125">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="d863c-125">Additional resources</span></span>

[<span data-ttu-id="d863c-126">Logikai függvények</span><span class="sxs-lookup"><span data-stu-id="d863c-126">Logical functions</span></span>](er-functions-category-logical.md)