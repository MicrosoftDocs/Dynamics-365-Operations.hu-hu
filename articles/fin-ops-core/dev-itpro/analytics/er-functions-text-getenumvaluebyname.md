---
title: GETENUMVALUEBYNAME ER-függvény
description: A témakör tájékoztatást nyújt a GETENUMVALUEBYNAME Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 4ded0c62b4556b21e731cd9b98db2863ec6ec442
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916844"
---
# <span data-ttu-id="08192-103"><a name="GETENUMVALUEBYNAME">GETENUMVALUEBYNAME ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="08192-103"><a name="GETENUMVALUEBYNAME">GETENUMVALUEBYNAME ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="08192-104">A `GETENUMVALUEBYNAME` függvény egy adott *Felsorolás* értéket keres a megadott felsorolási adatforrásban a *Karakterlánc* értékként megadott felsorolási név használatával.</span><span class="sxs-lookup"><span data-stu-id="08192-104">The `GETENUMVALUEBYNAME` function searches for a specific *Enum* value in the specified enumeration data source by using the enumeration name that is specified as a *String* value.</span></span> <span data-ttu-id="08192-105">Ha a *Felsorolás* értéke megtalálható, a függvény azt visszaadja.</span><span class="sxs-lookup"><span data-stu-id="08192-105">If the *Enum* value is found, the function returns it.</span></span> <span data-ttu-id="08192-106">Ellenkező esetben a függvény **null** értékű felsorolási értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="08192-106">Otherwise, the function returns the **null** enumeration value.</span></span>

## <a name="syntax"></a><span data-ttu-id="08192-107">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="08192-107">Syntax</span></span>

```
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a><span data-ttu-id="08192-108">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="08192-108">Arguments</span></span>

<span data-ttu-id="08192-109">`enumeration data source path`: *Felsorolás*</span><span class="sxs-lookup"><span data-stu-id="08192-109">`enumeration data source path`: *Enumeration*</span></span>

<span data-ttu-id="08192-110">A következő felsorolástípusok egyikéhez tartozó adatforrás érvényes útvonala:</span><span class="sxs-lookup"><span data-stu-id="08192-110">The valid path of a data source of one of the following enumeration types:</span></span>

- <span data-ttu-id="08192-111">Elektronikus jelentéskészítési (ER) modell felsorolása</span><span class="sxs-lookup"><span data-stu-id="08192-111">Electronic reporting (ER) model enumeration</span></span>
- <span data-ttu-id="08192-112">ER-formátum felsorolása</span><span class="sxs-lookup"><span data-stu-id="08192-112">ER format enumeration</span></span>
- <span data-ttu-id="08192-113">Microsoft Dynamics 365 Finance felsorolás</span><span class="sxs-lookup"><span data-stu-id="08192-113">Microsoft Dynamics 365 Finance enumeration</span></span>

<span data-ttu-id="08192-114">`enumeration value text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="08192-114">`enumeration value text`: *String*</span></span>

<span data-ttu-id="08192-115">Egy karakterláncérték, amely egy felsorolási érték nevét jelöli.</span><span class="sxs-lookup"><span data-stu-id="08192-115">A string value that represents the name of a single enumeration value.</span></span>

## <a name="return-values"></a><span data-ttu-id="08192-116">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="08192-116">Return values</span></span>

<span data-ttu-id="08192-117">Nullázható *Felsorolás*</span><span class="sxs-lookup"><span data-stu-id="08192-117">Nullable *Enum*</span></span>

<span data-ttu-id="08192-118">Az eredményül kapott felsorolási érték.</span><span class="sxs-lookup"><span data-stu-id="08192-118">The resulting enumeration value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="08192-119">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="08192-119">Usage notes</span></span>

<span data-ttu-id="08192-120">Nem történik kivétel, ha a *Felsorolás* érték nem található a *Karakterlánc* értékként megadott felsorolási érték nevével.</span><span class="sxs-lookup"><span data-stu-id="08192-120">No exception is thrown if an *Enum* value isn't found by using the name of the enumeration value that is specified as a *String* value.</span></span>

## <a name="example"></a><span data-ttu-id="08192-121">Példa</span><span class="sxs-lookup"><span data-stu-id="08192-121">Example</span></span>

<span data-ttu-id="08192-122">A következő ábra az adatmodellbe bevezetett **ReportDirection** sorszámozást mutatja be.</span><span class="sxs-lookup"><span data-stu-id="08192-122">In the following illustration, the **ReportDirection** enumeration is introduced in a data model.</span></span> <span data-ttu-id="08192-123">Vegye figyelembe, hogy a címkék a felsorolási értékekhez vannak megadva.</span><span class="sxs-lookup"><span data-stu-id="08192-123">Notice that labels are defined for the enumeration values.</span></span>

<p><a href="./media/ER-data-model-enumeration-values.PNG"><img src="./media/ER-data-model-enumeration-values.PNG" alt="Available values for a data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

<span data-ttu-id="08192-124">A következő ábrán ezek a részletek láthatók:</span><span class="sxs-lookup"><span data-stu-id="08192-124">The following illustration shows these details:</span></span>

- <span data-ttu-id="08192-125">A **$Direction** -adatforrást egy ER-jelentés konfigurálja.</span><span class="sxs-lookup"><span data-stu-id="08192-125">The **$Direction** data source is configured in an ER report.</span></span> <span data-ttu-id="08192-126">Ez az adatforrás a **ReportDirection** modell felsorolása alapján van konfigurálva.</span><span class="sxs-lookup"><span data-stu-id="08192-126">This data source is configured based on the **ReportDirection** model enumeration.</span></span>
- <span data-ttu-id="08192-127">Az `$IsArrivals` kifejezés a modellfelsorolás-alapú **$Direction** adatforrást a jelen függvény paramétereként használja.</span><span class="sxs-lookup"><span data-stu-id="08192-127">The `$IsArrivals` expression is designed to use the model enumeration–based **$Direction** data source as a parameter of this function.</span></span>
- <span data-ttu-id="08192-128">Az összehasonlító kifejezés értéke **IGAZ**.</span><span class="sxs-lookup"><span data-stu-id="08192-128">The value of this comparison expression is **TRUE**.</span></span>

<a href="./media/ER-data-model-enumeration-usage.PNG"><img src="./media/ER-data-model-enumeration-usage.PNG" alt="Example of data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

## <a name="additional-resources"></a><span data-ttu-id="08192-129">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="08192-129">Additional resources</span></span>

[<span data-ttu-id="08192-130">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="08192-130">Text functions</span></span>](er-functions-category-text.md)
