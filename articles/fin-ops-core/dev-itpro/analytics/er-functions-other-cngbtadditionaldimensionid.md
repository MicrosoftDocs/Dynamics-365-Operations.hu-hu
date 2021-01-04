---
title: CN_GBT_ADDITIONALDIMENSIONID ER-függvény
description: A témakör tájékoztatást nyújt a CN_GBT_ADDITIONALDIMENSIONID Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 38908c63c35465747505479bc983ada891f9e2bf
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686810"
---
# <a name="cn_gbt_additionaldimensionid-er-function"></a><span data-ttu-id="cbf07-103">CN_GBT_ADDITIONALDIMENSIONID ER-függvény</span><span class="sxs-lookup"><span data-stu-id="cbf07-103">CN_GBT_ADDITIONALDIMENSIONID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cbf07-104">A `CN_GBT_ADDITIONALDIMENSIONID` függvény olyan *String* értéket ad vissza, amely egyetlen pénzügyi dimenzióazonosítót jelöl, amely a megadott karakterláncból származik.</span><span class="sxs-lookup"><span data-stu-id="cbf07-104">The `CN_GBT_ADDITIONALDIMENSIONID` function returns a *String* value that represents a single financial dimension ID that is taken from the specified string.</span></span> <span data-ttu-id="cbf07-105">A megadott karakterlánc az összes dimenziót vesszővel tagolt azonosítólistaként jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="cbf07-105">The specified string presents all dimensions as a comma-separated list of IDs.</span></span>

## <a name="syntax"></a><span data-ttu-id="cbf07-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="cbf07-106">Syntax</span></span>

```vb
CN_GBT_ADDITIONALDIMENSIONID (text, number)
```

## <a name="arguments"></a><span data-ttu-id="cbf07-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="cbf07-107">Arguments</span></span>

<span data-ttu-id="cbf07-108">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="cbf07-108">`text`: *String*</span></span>

<span data-ttu-id="cbf07-109">A megadott *Karakterlánc* érték az összes dimenziót vesszővel tagolt azonosítólistaként jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="cbf07-109">A *String* value that presents all dimensions as a comma-separated list of IDs.</span></span>

<span data-ttu-id="cbf07-110">`number`: Egész</span><span class="sxs-lookup"><span data-stu-id="cbf07-110">`number`: Integer</span></span>

<span data-ttu-id="cbf07-111">Az *Egész* érték a kért dimenzió számsorozatkódját határozza meg a megadott karakterláncban.</span><span class="sxs-lookup"><span data-stu-id="cbf07-111">An *Integer* value that defines the sequence code of the requested dimension in the specified string.</span></span>

## <a name="return-values"></a><span data-ttu-id="cbf07-112">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="cbf07-112">Return values</span></span>

<span data-ttu-id="cbf07-113">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="cbf07-113">*String*</span></span>

<span data-ttu-id="cbf07-114">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="cbf07-114">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="cbf07-115">Példa</span><span class="sxs-lookup"><span data-stu-id="cbf07-115">Example</span></span>

<span data-ttu-id="cbf07-116">A `CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` a **"CC"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="cbf07-116">`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` returns **"CC"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cbf07-117">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="cbf07-117">Additional resources</span></span>

[<span data-ttu-id="cbf07-118">Egyéb (üzleti területre jellemző) függvények</span><span class="sxs-lookup"><span data-stu-id="cbf07-118">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
