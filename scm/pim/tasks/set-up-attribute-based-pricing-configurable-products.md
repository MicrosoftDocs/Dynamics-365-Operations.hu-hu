--- 
title: "Állítsa be a konfigurálható termékek attribútum-alapú árképzését"
description: "Ez az eljárás bemutatja, hogyan állítható be az attribútumalapú árképzés."
author: BibiSp
manager: AnnBe
ms.date: 10/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: b113fb639b5d7c50e519a0225b1e5d8315b7f3a9
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a><span data-ttu-id="ce4b8-103">Állítsa be a konfigurálható termékek attribútum-alapú árképzését</span><span class="sxs-lookup"><span data-stu-id="ce4b8-103">Set up attribute-based pricing for configurable products</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ce4b8-104">Ez az eljárás bemutatja, hogyan állítható be az attribútumalapú árképzés.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-104">This procedure shows how to set up attribute-based pricing.</span></span> <span data-ttu-id="ce4b8-105">Előfeltételként rendelkeznie kell egy olyan termékkonfigurációs modellel, amelynek egy vagy több összetevője és attribútuma van.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-105">As a prerequisite, you must have a product configuration model that has one or more components and attributes.</span></span> <span data-ttu-id="ce4b8-106">Ebben a példában a High End hangszóró termékmodellt használjuk a USMF bemutatócég esetében.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-106">This example uses the High End Speaker product model in the USMF demo data company.</span></span> <span data-ttu-id="ce4b8-107">Ezt az eljárást általában a termékmenedzser használja.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-107">Typically, a product manager uses this procedure.</span></span>


## <a name="create-a-new-price-model"></a><span data-ttu-id="ce4b8-108">Új ármodell létrehozása</span><span class="sxs-lookup"><span data-stu-id="ce4b8-108">Create a new price model</span></span>
1. <span data-ttu-id="ce4b8-109">Kattintson a Termékváltozat modelldefinícióra.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="ce4b8-110">Kattintson a Termékkonfigurációs modellek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-110">Click Product configuration models.</span></span>
3. <span data-ttu-id="ce4b8-111">A listában válassza ki a High End hangszóró sort, de ne kattintson a név hivatkozására.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-111">In the list, select the High End Speaker line, but don’t click the link for the name.</span></span>
4. <span data-ttu-id="ce4b8-112">A Művelet panelen kattintson a Modell elemre.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-112">On the Action Pane, click Model.</span></span>
5. <span data-ttu-id="ce4b8-113">Kattintson az Ármodellek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-113">Click Price models.</span></span>
6. <span data-ttu-id="ce4b8-114">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-114">Click New.</span></span>
7. <span data-ttu-id="ce4b8-115">Írjon be egy értéket az Ármodell neve mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-115">In the Price model name field, type a value.</span></span>
    * <span data-ttu-id="ce4b8-116">Olyan nevet használjon, amelyik könnyen azonosíthatóvá teszi a modellt.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-116">Use a name that makes the model easy to identify.</span></span>  
8. <span data-ttu-id="ce4b8-117">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-117">In the Description field, type a value.</span></span>
9. <span data-ttu-id="ce4b8-118">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-118">Click Save.</span></span>

## <a name="add-price-elements"></a><span data-ttu-id="ce4b8-119">Árelem hozzáadása</span><span class="sxs-lookup"><span data-stu-id="ce4b8-119">Add price elements</span></span>
1. <span data-ttu-id="ce4b8-120">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-120">Click Edit.</span></span>
    * <span data-ttu-id="ce4b8-121">A termékmodell minden egyes összetevőjéhez tartozhat egy alapár elem és tetszőleges számú árkifejezés-szabály.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-121">Each component in a product model can have a base price element and any number of price expression rules.</span></span> <span data-ttu-id="ce4b8-122">Különböző pénznemben szereplő árak is hozzáadhatók.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-122">You can also add prices in different currencies.</span></span>  
2. <span data-ttu-id="ce4b8-123">Írjon be egy értéket az Alapár kifejezése mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-123">In the Base price expression field, type a value.</span></span>
    * <span data-ttu-id="ce4b8-124">Például írja be a „100” értéket.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-124">For example, type 100.</span></span>   <span data-ttu-id="ce4b8-125">Az alapár kifejezése numerikus érték lehet, vagy számítás, amely magában foglal egy vagy több attribútumot.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-125">A base price expression can be a numerical value, or it can consist of an arithmetic calculation that involves one or more attributes.</span></span>  
3. <span data-ttu-id="ce4b8-126">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-126">Click Add.</span></span>
4. <span data-ttu-id="ce4b8-127">A Név mezőbe írja be a „Rosewood” szót.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-127">In the Name field, type ‘Rosewood’.</span></span>
    * <span data-ttu-id="ce4b8-128">Az árkifejezés neve azt segít azonosítani, amit az ár elem jelöl.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-128">The price expression name helps identify what the price element represents.</span></span> <span data-ttu-id="ce4b8-129">Ebben a példában ár elemet hozunk létre a Rosewood hangszórókabinet befejezés opciójához.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-129">In this example, we are creating a price element for the Rosewood speaker cabinet finish option.</span></span>  
5. <span data-ttu-id="ce4b8-130">Kattintson a Feltétel szerkesztése elemre.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-130">Click Edit condition.</span></span>
    * <span data-ttu-id="ce4b8-131">Ár feltétel segít garantálni, hogy az eladási árnak csak akkor legyen része az árkifejezés elem, ha jelen van az attribútumok egyedi kombinációja.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-131">A price condition helps guarantee that a price expression element is included in the sales price only if a specific combination of attributes is present.</span></span>  
6. <span data-ttu-id="ce4b8-132">A ConstraintBody mezőbe írja be a következőt: CabinetFinish=="Rosewood".</span><span class="sxs-lookup"><span data-stu-id="ce4b8-132">In the ConstraintBody field, enter 'CabinetFinish=="Rosewood"'.</span></span>
7. <span data-ttu-id="ce4b8-133">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-133">Click OK.</span></span>
8. <span data-ttu-id="ce4b8-134">A Kifejezés mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-134">In the Expression field, type a value.</span></span>
    * <span data-ttu-id="ce4b8-135">Például írja be a „50” értéket.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-135">For example, type 50.</span></span>  
9. <span data-ttu-id="ce4b8-136">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-136">Close the page.</span></span>
10. <span data-ttu-id="ce4b8-137">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ce4b8-137">Close the page.</span></span>


