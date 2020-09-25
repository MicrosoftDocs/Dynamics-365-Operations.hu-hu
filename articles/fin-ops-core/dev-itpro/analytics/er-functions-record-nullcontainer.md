---
title: NULLCONTAINER ER-függvény
description: A témakör tájékoztatást nyújt a NULLCONTAINER Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: dac6283ec35d3d03f586ca157048bd3ecc4bfa8a
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743927"
---
# <a name="nullcontainer-er-function"></a><span data-ttu-id="61f65-103">NULLCONTAINER ER-függvény</span><span class="sxs-lookup"><span data-stu-id="61f65-103">NULLCONTAINER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="61f65-104">A `NULLCONTAINER` függvény egy nulla *Tároló (rekord)* értéket ad vissza, amely ugyanazzal a struktúrával rendelkezik, mint a megadott rekordlista vagy rekord.</span><span class="sxs-lookup"><span data-stu-id="61f65-104">The `NULLCONTAINER` function returns a null *Container (record)* value that has the same structure as the specified record list or record.</span></span>

## <a name="syntax"></a><span data-ttu-id="61f65-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="61f65-105">Syntax</span></span>

```vb
NULLCONTAINER (list)
```

## <a name="arguments"></a><span data-ttu-id="61f65-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="61f65-106">Arguments</span></span>

<span data-ttu-id="61f65-107">`list`: *Rekordlista* vagy *Tároló (rekord)*</span><span class="sxs-lookup"><span data-stu-id="61f65-107">`list`: *Record list* or *Container (record)*</span></span>

<span data-ttu-id="61f65-108">A *Rekordlista* vagy *Tároló (rekord)* típusú adatforrás érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="61f65-108">The valid path of a data source of either the *Record list* or *Container (record)* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="61f65-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="61f65-109">Return values</span></span>

<span data-ttu-id="61f65-110">*Tároló (rekord)*</span><span class="sxs-lookup"><span data-stu-id="61f65-110">*Container (record)*</span></span>

<span data-ttu-id="61f65-111">Az eredményül kapott rekordérték.</span><span class="sxs-lookup"><span data-stu-id="61f65-111">The resulting record value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="61f65-112">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="61f65-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="61f65-113">Ez a funkció már elavult.</span><span class="sxs-lookup"><span data-stu-id="61f65-113">This function is obsolete.</span></span> <span data-ttu-id="61f65-114">Használja helyette az `EMPTYRECORD` függvényt.</span><span class="sxs-lookup"><span data-stu-id="61f65-114">Use the `EMPTYRECORD` function instead.</span></span> <span data-ttu-id="61f65-115">További tudnivalók: [EMPTYRECORD](er-functions-record-emptyrecord.md).</span><span class="sxs-lookup"><span data-stu-id="61f65-115">For more information, see [EMPTYRECORD](er-functions-record-emptyrecord.md).</span></span>

## <a name="example"></a><span data-ttu-id="61f65-116">Példa</span><span class="sxs-lookup"><span data-stu-id="61f65-116">Example</span></span>

<span data-ttu-id="61f65-117">A `NULLCONTAINER (SPLIT ("abc", 1))` új üres rekordot ad vissza, amelynek ugyanolyan szerkezete van, mint a `SPLIT` funkció által megjelenített listának.</span><span class="sxs-lookup"><span data-stu-id="61f65-117">`NULLCONTAINER (SPLIT ("abc", 1))` returns a new empty record that has the same structure as the list that is returned by the `SPLIT` function.</span></span> <span data-ttu-id="61f65-118">További tudnivalók: [SPLIT](er-functions-list-split.md).</span><span class="sxs-lookup"><span data-stu-id="61f65-118">For more information, see [SPLIT](er-functions-list-split.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="61f65-119">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="61f65-119">Additional resources</span></span>

[<span data-ttu-id="61f65-120">Rekord függvények</span><span class="sxs-lookup"><span data-stu-id="61f65-120">Record functions</span></span>](er-functions-category-record.md)
