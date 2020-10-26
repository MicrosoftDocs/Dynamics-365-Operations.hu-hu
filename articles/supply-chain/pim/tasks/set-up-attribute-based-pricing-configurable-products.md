---
title: Állítsa be a konfigurálható termékek attribútum-alapú árképzését
description: Ez a témakör azt ismerteti, hogyan állítható be az attribútumalapú árképzés.
author: ShylaThompson
manager: tfehr
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3a75f3afcf4761ac6a9575eae9a620a1e9f01c8e
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3981038"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a><span data-ttu-id="0d7b5-103">Állítsa be a konfigurálható termékek attribútum-alapú árképzését</span><span class="sxs-lookup"><span data-stu-id="0d7b5-103">Set up attribute-based pricing for configurable products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0d7b5-104">Ez a témakör azt ismerteti, hogyan állítható be az attribútumalapú árképzés.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-104">This topic explains how to set up attribute-based pricing.</span></span> <span data-ttu-id="0d7b5-105">Előfeltételként rendelkeznie kell egy olyan termékkonfigurációs modellel, amelynek egy vagy több összetevője és attribútuma van.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-105">As a prerequisite, you must have a product configuration model that has one or more components and attributes.</span></span> <span data-ttu-id="0d7b5-106">Ebben a példában a High End hangszóró termékmodellt használjuk a USMF bemutatócég esetében.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-106">This example uses the High End Speaker product model in the USMF demo data company.</span></span> <span data-ttu-id="0d7b5-107">Ezt az eljárást általában a termékmenedzser használja.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-107">Typically, a product manager uses this procedure.</span></span>


## <a name="create-a-new-price-model"></a><span data-ttu-id="0d7b5-108">Új ármodell létrehozása</span><span class="sxs-lookup"><span data-stu-id="0d7b5-108">Create a new price model</span></span>
1. <span data-ttu-id="0d7b5-109">Válassza ki a **Termékváltozat modelldefiníciója** elemet a kezdőlapon.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-109">Select **Product variant model definition** on the home page.</span></span>
2. <span data-ttu-id="0d7b5-110">Válassza ki a **Termékkonfigurációs modellek** lehetőséget a **hivatkozások** részben.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-110">Select **Product configuration models** in the **links** section.</span></span>
3. <span data-ttu-id="0d7b5-111">A listában válassza ki a **High End hangszóró** sort, de ne válassza ki a név hivatkozását.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-111">In the list, select the **High End Speaker** line, but don't select the link for the name.</span></span>
4. <span data-ttu-id="0d7b5-112">A Műveleti ablaktáblán kattintson a **Modell** elemre.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-112">On the Action Pane, select **Model** .</span></span>
5. <span data-ttu-id="0d7b5-113">Válassza ki az **Ármodellek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-113">Select **Price models** .</span></span>
6. <span data-ttu-id="0d7b5-114">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-114">Select **New** .</span></span>
7. <span data-ttu-id="0d7b5-115">Írjon be egy értéket az **Ármodell neve** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-115">In the **Price model name** field, type a value.</span></span> <span data-ttu-id="0d7b5-116">Olyan nevet használjon, amelyik könnyen azonosíthatóvá teszi a modellt.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-116">Use a name that makes the model easy to identify.</span></span>  
8. <span data-ttu-id="0d7b5-117">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-117">In the **Description** field, type a value.</span></span>
9. <span data-ttu-id="0d7b5-118">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-118">Select **Save** .</span></span>

## <a name="add-price-elements"></a><span data-ttu-id="0d7b5-119">Árelem hozzáadása</span><span class="sxs-lookup"><span data-stu-id="0d7b5-119">Add price elements</span></span>
1. <span data-ttu-id="0d7b5-120">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-120">Select **Edit** .</span></span> <span data-ttu-id="0d7b5-121">A termékmodell minden egyes összetevőjéhez tartozhat egy alapár elem és tetszőleges számú árkifejezés-szabály.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-121">Each component in a product model can have a base price element and any number of price expression rules.</span></span> <span data-ttu-id="0d7b5-122">Különböző pénznemben szereplő árak is hozzáadhatók.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-122">You can also add prices in different currencies.</span></span>  
2. <span data-ttu-id="0d7b5-123">Írjon be egy értéket az **Alapár kifejezése** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-123">In the **Base price expression** field, type a value.</span></span> <span data-ttu-id="0d7b5-124">Például írja be a „100” értéket.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-124">For example, type 100.</span></span> <span data-ttu-id="0d7b5-125">Az alapár kifejezése numerikus érték lehet, vagy számítás, amely magában foglal egy vagy több attribútumot.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-125">A base price expression can be a numerical value, or it can consist of an arithmetic calculation that involves one or more attributes.</span></span>  
3. <span data-ttu-id="0d7b5-126">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-126">Select **Add** .</span></span>
4. <span data-ttu-id="0d7b5-127">A **Név** mezőbe írja be a `Rosewood` kifejezést.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-127">In the **Name** field, type `Rosewood`.</span></span> <span data-ttu-id="0d7b5-128">Az árkifejezés neve azt segít azonosítani, amit az ár elem jelöl.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-128">The price expression name helps identify what the price element represents.</span></span> <span data-ttu-id="0d7b5-129">Ebben a példában ár elemet hozunk létre a Rosewood hangszórókabinet befejezés opciójához.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-129">In this example, we are creating a price element for the Rosewood speaker cabinet finish option.</span></span>  
5. <span data-ttu-id="0d7b5-130">Válassza ki a **Szerkesztési feltétel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-130">Select **Edit condition** .</span></span> <span data-ttu-id="0d7b5-131">Ár feltétel segít garantálni, hogy az eladási árnak csak akkor legyen része az árkifejezés elem, ha jelen van az attribútumok egyedi kombinációja.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-131">A price condition helps guarantee that a price expression element is included in the sales price only if a specific combination of attributes is present.</span></span>  
6. <span data-ttu-id="0d7b5-132">A **ConstraintBody** mezőben adja meg a `CabinetFinish=="Rosewood"` értéket.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-132">In the **ConstraintBody** field, enter `CabinetFinish=="Rosewood"`.</span></span>
7. <span data-ttu-id="0d7b5-133">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-133">Select **OK** .</span></span>
8. <span data-ttu-id="0d7b5-134">Adjon meg egy értéket a **Kifejezés** mezőben.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-134">In the **Expression** field, type a value.</span></span> <span data-ttu-id="0d7b5-135">Például írja be a `50` értéket.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-135">For example, type `50`.</span></span> 
9. <span data-ttu-id="0d7b5-136">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="0d7b5-136">Close the page.</span></span>

