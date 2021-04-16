---
title: ENDSWITH ER függvény
description: A témakör tájékoztatást nyújt az ENDSWITH Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
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
ms.openlocfilehash: bdd2f364e2d0b80d3df20592ec827dcabf99a06c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745401"
---
# <a name="endswith-er-function"></a><span data-ttu-id="f9bac-103">ENDSWITH ER függvény</span><span class="sxs-lookup"><span data-stu-id="f9bac-103">ENDSWITH ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f9bac-104">Az `ENDSWITH` függvény határozza meg, hogy a megadott bemenet a megadott szöveggel végződik-e.</span><span class="sxs-lookup"><span data-stu-id="f9bac-104">The `ENDSWITH` function determines whether the specified input ends with the specified text.</span></span> <span data-ttu-id="f9bac-105">A visszaadott *logikai* érték **IGAZ** lesz, ha a megadott bemenet a megadott szövegre végződik.</span><span class="sxs-lookup"><span data-stu-id="f9bac-105">It returns a *Boolean* value of **TRUE** if the specified input ends with the specified text.</span></span> <span data-ttu-id="f9bac-106">Ellenkező esetben **HAMIS** *logikai* eredményt ad.</span><span class="sxs-lookup"><span data-stu-id="f9bac-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="f9bac-107">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="f9bac-107">Syntax</span></span>

```vb
ENDSWITH (input, end text)
```

## <a name="arguments"></a><span data-ttu-id="f9bac-108">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="f9bac-108">Arguments</span></span>

<span data-ttu-id="f9bac-109">`input`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="f9bac-109">`input`: *String*</span></span>

<span data-ttu-id="f9bac-110">A *Sztring* típusú adatforrás elemének vagy egy sztring konstans érvényes útvonala, amelynek értéke a második argumentummal zárulhat.</span><span class="sxs-lookup"><span data-stu-id="f9bac-110">The valid path of an item of a data source of the *String* type or a string constant, the value of which might end with the second argument.</span></span>

<span data-ttu-id="f9bac-111">`start text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="f9bac-111">`start text`: *String*</span></span>

<span data-ttu-id="f9bac-112">A *Sztring* típusú adatforrás vagy egy sztring konstans érvényes útvonala, amely az első argumentum végén lehet.</span><span class="sxs-lookup"><span data-stu-id="f9bac-112">The valid path of a data source of the *String* data type or a string constant, the value of which might be at the end of the first argument.</span></span>

## <a name="return-values"></a><span data-ttu-id="f9bac-113">Visszatérési értékek</span><span class="sxs-lookup"><span data-stu-id="f9bac-113">Return values</span></span>

<span data-ttu-id="f9bac-114">*Logikai*</span><span class="sxs-lookup"><span data-stu-id="f9bac-114">*Boolean*</span></span>

<span data-ttu-id="f9bac-115">Az eredményül kapott *Logikai* érték.</span><span class="sxs-lookup"><span data-stu-id="f9bac-115">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="f9bac-116">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="f9bac-116">Usage notes</span></span>

<span data-ttu-id="f9bac-117">Ezzel a funkcióval csak akkor lehet megadni a [FILTER](er-functions-list-filter.md) függvény feltételkifejezését, ha a megfelelő hozzárendelés a [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) be van állítva a [Microsoft Dataverse](../data-entities/data-integration-cds.md) szolgáltatáshoz való hozzáféréshez.</span><span class="sxs-lookup"><span data-stu-id="f9bac-117">This function can be used to specify a condition expression of the [FILTER](er-functions-list-filter.md) function only when the relevant mapping is configured in [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) to access [Microsoft Dataverse](../data-entities/data-integration-cds.md).</span></span> <span data-ttu-id="f9bac-118">Ellenkező esetben a rendszer kivételt ad a tervezéskor.</span><span class="sxs-lookup"><span data-stu-id="f9bac-118">Otherwise, an exception is thrown at design time.</span></span> <span data-ttu-id="f9bac-119">A kapott üzenet azt javasolja, hogy a hatásfok növelése érdekében a [WHERE](er-functions-list-where.md) függvény helyett a `FILTER` függvényt használja.</span><span class="sxs-lookup"><span data-stu-id="f9bac-119">The message that you receive recommends that you use the [WHERE](er-functions-list-where.md) function instead of the `FILTER` function.</span></span>

## <a name="example-1"></a><span data-ttu-id="f9bac-120">1. példa</span><span class="sxs-lookup"><span data-stu-id="f9bac-120">Example 1</span></span>

<span data-ttu-id="f9bac-121">Az `ENDSWITH ("abc", "d")` **HAMIS** eredményt ad, az `ENDSWITH ("abc", "C")` kifejezés pedig **IGAZ** eredményt ad.</span><span class="sxs-lookup"><span data-stu-id="f9bac-121">The expression `ENDSWITH ("abc", "d")` returns **FALSE**, whereas the expression `ENDSWITH ("abc", "C")` returns **TRUE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="f9bac-122">2. példa</span><span class="sxs-lookup"><span data-stu-id="f9bac-122">Example 2</span></span>

<span data-ttu-id="f9bac-123">Az `ENDSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "USA")` kifejezés értéke **IGAZ**, ha a **modell** adatforrás **Cím** mezőjének értéke az **USA** sztringgel végződik.</span><span class="sxs-lookup"><span data-stu-id="f9bac-123">The expression `ENDSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "USA")` returns **TRUE** if the value of the **Address** field of the **model** data source ends with the string **USA**.</span></span> <span data-ttu-id="f9bac-124">Ellenkező esetben **HAMIS** választ jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="f9bac-124">Otherwise, it returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f9bac-125">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="f9bac-125">Additional resources</span></span>

[<span data-ttu-id="f9bac-126">Logikai függvények</span><span class="sxs-lookup"><span data-stu-id="f9bac-126">Logical functions</span></span>](er-functions-category-logical.md)
