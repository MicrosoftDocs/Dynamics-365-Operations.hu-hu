---
title: ISEMPTY ER-függvény
description: A témakör tájékoztatást nyújt az ISEMPTY Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 5b6fde7cbadec7aae052742ef598e1af4dbae793
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745129"
---
# <a name="isempty-er-function"></a><span data-ttu-id="40e0f-103">ISEMPTY ER-függvény</span><span class="sxs-lookup"><span data-stu-id="40e0f-103">ISEMPTY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="40e0f-104">Az `ISEMPTY` függvény **IGAZ** *Logikai* értéket ad eredményül, ha a megadott lista nem tartalmaz rekordokat.</span><span class="sxs-lookup"><span data-stu-id="40e0f-104">The `ISEMPTY` function returns a *Boolean* value of **TRUE** if the specified list contains no records.</span></span> <span data-ttu-id="40e0f-105">Ellenkező esetben **HAMIS** *logikai* eredményt ad.</span><span class="sxs-lookup"><span data-stu-id="40e0f-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="40e0f-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="40e0f-106">Syntax</span></span>

```vb
ISEMPTY (list)
```

## <a name="arguments"></a><span data-ttu-id="40e0f-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="40e0f-107">Arguments</span></span>

<span data-ttu-id="40e0f-108">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="40e0f-108">`list`: *Record list*</span></span>

<span data-ttu-id="40e0f-109">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="40e0f-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="40e0f-110">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="40e0f-110">Return values</span></span>

<span data-ttu-id="40e0f-111">*Logikai*</span><span class="sxs-lookup"><span data-stu-id="40e0f-111">*Boolean*</span></span>

<span data-ttu-id="40e0f-112">Az eredményül kapott *Logikai* érték.</span><span class="sxs-lookup"><span data-stu-id="40e0f-112">The resulting *Boolean* value.</span></span>

## <a name="example-1"></a><span data-ttu-id="40e0f-113">1. példa</span><span class="sxs-lookup"><span data-stu-id="40e0f-113">Example 1</span></span>

<span data-ttu-id="40e0f-114">Ha megadja a *Számított mező* típusú **DS** adatforrást és az tartalmazza a `SPLIT ("A|B|C", "|")` kifejezést, akkor a `ISEMPTY(DS)` kifejezés a **HAMIS** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="40e0f-114">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `ISEMPTY(DS)` returns **FALSE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="40e0f-115">2. példa</span><span class="sxs-lookup"><span data-stu-id="40e0f-115">Example 2</span></span>

<span data-ttu-id="40e0f-116">Az `ISEMPTY (SPLIT ("",1))` kifejezés az **IGAZ** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="40e0f-116">The expression `ISEMPTY (SPLIT ("",1))` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="40e0f-117">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="40e0f-117">Additional resources</span></span>

[<span data-ttu-id="40e0f-118">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="40e0f-118">List functions</span></span>](er-functions-category-list.md)
