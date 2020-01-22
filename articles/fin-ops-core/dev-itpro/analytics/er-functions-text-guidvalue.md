---
title: GUIDVALUE ER-függvény
description: A témakör tájékoztatást nyújt a GUIDVALUE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: be5e8e7625d0226c9eb59efd3217fce7b8eba086
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915694"
---
# <span data-ttu-id="9ce64-103"><a name="GUIDVALUE">GUIDVALUE ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="9ce64-103"><a name="GUIDVALUE">GUIDVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9ce64-104">A `GUIDVALUE` függvény a megadott *Karakterlánc* típusú bemenetet *GUID* típusú adatelemmé konvertálja.</span><span class="sxs-lookup"><span data-stu-id="9ce64-104">The `GUIDVALUE` function converts the specified input of the *String* type to a data item of the *GUID* type.</span></span>

## <a name="syntax"></a><span data-ttu-id="9ce64-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="9ce64-105">Syntax</span></span>

```
GUIDVALUE (input)
```

## <a name="arguments"></a><span data-ttu-id="9ce64-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="9ce64-106">Arguments</span></span>

<span data-ttu-id="9ce64-107">`input`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="9ce64-107">`input`: *String*</span></span>

<span data-ttu-id="9ce64-108">A *Karakterlánc* típus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="9ce64-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="9ce64-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="9ce64-109">Return values</span></span>

<span data-ttu-id="9ce64-110">*GUID*</span><span class="sxs-lookup"><span data-stu-id="9ce64-110">*GUID*</span></span>

<span data-ttu-id="9ce64-111">Az eredményül kapott globálisan egyedi azonosító (GUID) értéke.</span><span class="sxs-lookup"><span data-stu-id="9ce64-111">The resulting globally unique identifier (GUID) value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="9ce64-112">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="9ce64-112">Usage notes</span></span>

<span data-ttu-id="9ce64-113">Ellenkező irányú konverzió végrehajtásához (például a *GUID* adattípus megadott bemenetének a egy *Karakterlánc* adattípusú adatelemre konvertálásához) használhatja a [TEXT()](er-functions-text-text.md) függvényt.</span><span class="sxs-lookup"><span data-stu-id="9ce64-113">To do a conversion in the opposite direction (that is, to convert specified input of the *GUID* data type to a data item of the *String* data type), you can use the [TEXT](er-functions-text-text.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="9ce64-114">Példa</span><span class="sxs-lookup"><span data-stu-id="9ce64-114">Example</span></span>

<span data-ttu-id="9ce64-115">A következő adatforrás megadása a modell-hozzárendelésben:</span><span class="sxs-lookup"><span data-stu-id="9ce64-115">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="9ce64-116">A *Számított mező* típus **myID** adatforrása, amely a `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")` kifejezést tartalmazza</span><span class="sxs-lookup"><span data-stu-id="9ce64-116">A **myID** data source of the *Calculated field* type that contains the expression `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")`</span></span>
- <span data-ttu-id="9ce64-117">A *Táblarekordok* típus **Felhasználók** adatforrása, amely a UserInfo táblára hivatkozik</span><span class="sxs-lookup"><span data-stu-id="9ce64-117">A **Users** data source of the *Table records* type that refers to the UserInfo table</span></span>

<span data-ttu-id="9ce64-118">Ezután használhat olyan kifejezést, mint például a `FILTER (Users, Users.objectId = myID)`, a UserInfo táblának a *GUID* adattípusú **objectId** mező szerinti szűréséhez.</span><span class="sxs-lookup"><span data-stu-id="9ce64-118">You can then use an expression such as `FILTER (Users, Users.objectId = myID)` to filter the UserInfo table by the **objectId** field of the *GUID* data type.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9ce64-119">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="9ce64-119">Additional resources</span></span>

[<span data-ttu-id="9ce64-120">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="9ce64-120">Text functions</span></span>](er-functions-category-text.md)
