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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5dbba375104b57f9fb09ed4e330d85181ec0dff8
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684883"
---
# <a name="isempty-er-function"></a><span data-ttu-id="370cf-103">ISEMPTY ER-függvény</span><span class="sxs-lookup"><span data-stu-id="370cf-103">ISEMPTY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="370cf-104">Az `ISEMPTY` függvény **IGAZ** *Logikai* értéket ad eredményül, ha a megadott lista nem tartalmaz rekordokat.</span><span class="sxs-lookup"><span data-stu-id="370cf-104">The `ISEMPTY` function returns a *Boolean* value of **TRUE** if the specified list contains no records.</span></span> <span data-ttu-id="370cf-105">Ellenkező esetben **HAMIS** *logikai* eredményt ad.</span><span class="sxs-lookup"><span data-stu-id="370cf-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="370cf-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="370cf-106">Syntax</span></span>

```vb
ISEMPTY (list)
```

## <a name="arguments"></a><span data-ttu-id="370cf-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="370cf-107">Arguments</span></span>

<span data-ttu-id="370cf-108">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="370cf-108">`list`: *Record list*</span></span>

<span data-ttu-id="370cf-109">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="370cf-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="370cf-110">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="370cf-110">Return values</span></span>

<span data-ttu-id="370cf-111">*Logikai*</span><span class="sxs-lookup"><span data-stu-id="370cf-111">*Boolean*</span></span>

<span data-ttu-id="370cf-112">Az eredményül kapott *Logikai* érték.</span><span class="sxs-lookup"><span data-stu-id="370cf-112">The resulting *Boolean* value.</span></span>

## <a name="example-1"></a><span data-ttu-id="370cf-113">1. példa</span><span class="sxs-lookup"><span data-stu-id="370cf-113">Example 1</span></span>

<span data-ttu-id="370cf-114">Ha megadja a *Számított mező* típusú **DS** adatforrást és az tartalmazza a `SPLIT ("A|B|C", "|")` kifejezést, akkor a `ISEMPTY(DS)` kifejezés a **HAMIS** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="370cf-114">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `ISEMPTY(DS)` returns **FALSE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="370cf-115">2. példa</span><span class="sxs-lookup"><span data-stu-id="370cf-115">Example 2</span></span>

<span data-ttu-id="370cf-116">Az `ISEMPTY (SPLIT ("",1))` kifejezés az **IGAZ** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="370cf-116">The expression `ISEMPTY (SPLIT ("",1))` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="370cf-117">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="370cf-117">Additional resources</span></span>

[<span data-ttu-id="370cf-118">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="370cf-118">List functions</span></span>](er-functions-category-list.md)
