--- 
title: "Eladási ár kiválasztási feltételeinek létrehozása"
description: "Ez az eljárás bemutatja, hogyan hozhat létre eladási ár kiválasztási feltételeket az attribútumalapú eladásiár-modellekhez."
author: ShylaThompson
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: b7638bee0db30e161d4dbb9b9435c8b38db0ff9c
ms.contentlocale: hu-hu
ms.lasthandoff: 08/07/2018

---
# <a name="create-sales-price-selection-criteria"></a><span data-ttu-id="321ac-103">Eladási ár kiválasztási feltételeinek létrehozása</span><span class="sxs-lookup"><span data-stu-id="321ac-103">Create sales price selection criteria</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="321ac-104">Ez az eljárás bemutatja, hogyan hozhat létre eladási ár kiválasztási feltételeket az attribútumalapú eladásiár-modellekhez.</span><span class="sxs-lookup"><span data-stu-id="321ac-104">This procedure shows how to create a sales price selection criterion for attribute-based sales price models.</span></span> <span data-ttu-id="321ac-105">Az eljáráshoz előfeltétel, hogy legyen legalább egy elérhető eladásiár-modell.</span><span class="sxs-lookup"><span data-stu-id="321ac-105">This procedure requires that at least one sales price model be available.</span></span> <span data-ttu-id="321ac-106">Ebben a példában a hangszóró megoldás eladásiár-modelljének ármodelljét használjuk a USMF bemutatócég esetében.</span><span class="sxs-lookup"><span data-stu-id="321ac-106">This example uses the price model for the Speaker solution sales price model in the USMF demo data company.</span></span> <span data-ttu-id="321ac-107">Ezt az eljárást általában a termékmenedzser használja.</span><span class="sxs-lookup"><span data-stu-id="321ac-107">Typically, a product manager uses this procedure.</span></span>


## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a><span data-ttu-id="321ac-108">Új feltétel hozzáadása a meglévő eladásiár-modellhez</span><span class="sxs-lookup"><span data-stu-id="321ac-108">Add a new criterion for an existing sales price model</span></span>
1. <span data-ttu-id="321ac-109">Kattintson a Termékváltozat modelldefinícióra.</span><span class="sxs-lookup"><span data-stu-id="321ac-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="321ac-110">Kattintson a Termékkonfigurációs modellek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="321ac-110">Click Product configuration models.</span></span>
3. <span data-ttu-id="321ac-111">A listában jelölje ki a hangszóró megoldás termékmodelljének a sorát, de ne kattintson a modell nevének hivatkozására.</span><span class="sxs-lookup"><span data-stu-id="321ac-111">In the list, select the row for the Speaker solution product model, but don’t click the link for the model name.</span></span>
4. <span data-ttu-id="321ac-112">A Művelet panelen kattintson a Modell elemre.</span><span class="sxs-lookup"><span data-stu-id="321ac-112">On the Action Pane, click Model.</span></span>
5. <span data-ttu-id="321ac-113">Kattintson az Ármodellfeltételek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="321ac-113">Click Price model criteria.</span></span>
6. <span data-ttu-id="321ac-114">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="321ac-114">Click New.</span></span>
7. <span data-ttu-id="321ac-115">A Név mezőbe írja be a „10. vásárlócsoport” szöveget.</span><span class="sxs-lookup"><span data-stu-id="321ac-115">In the Name field, type ‘Customer group 10’.</span></span>
    * <span data-ttu-id="321ac-116">Az ármodellfeltétel nevének a használata segít azonosítani az alapul szolgáló kiválasztási feltételeket.</span><span class="sxs-lookup"><span data-stu-id="321ac-116">The name of the price model criterion is used to help identify the underlying selection criteria.</span></span>  
8. <span data-ttu-id="321ac-117">Az Ármodell mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="321ac-117">In the Price model field, enter or select a value.</span></span>
9. <span data-ttu-id="321ac-118">A Rendeléstípus mezőben válassza ki az Értékesítési rendelés elemet.</span><span class="sxs-lookup"><span data-stu-id="321ac-118">In the Order type field, select Sales order.</span></span>
    * <span data-ttu-id="321ac-119">A rendelés típusa határozza meg, hogy az adatbázis mely mezői állnak rendelkezésre a kiválasztási lekérdezéshez.</span><span class="sxs-lookup"><span data-stu-id="321ac-119">The order type determines the database fields that will be available for the selection query.</span></span>  
10. <span data-ttu-id="321ac-120">Adja meg a dátumot az Érvényesség kezdete mezőben.</span><span class="sxs-lookup"><span data-stu-id="321ac-120">In the Valid from field, enter a date.</span></span>
11. <span data-ttu-id="321ac-121">Az Érvényesség vége mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="321ac-121">In the Expire by field, enter a date.</span></span>
12. <span data-ttu-id="321ac-122">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="321ac-122">Click Save.</span></span>

## <a name="create-the-query-for-the-selection-criteria"></a><span data-ttu-id="321ac-123">A lekérdezés létrehozása a kiválasztási feltételekhez</span><span class="sxs-lookup"><span data-stu-id="321ac-123">Create the query for the selection criteria</span></span>
1. <span data-ttu-id="321ac-124">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="321ac-124">Click Edit.</span></span>
2. <span data-ttu-id="321ac-125">Válasszon ki vevőket a Tábla mezőben.</span><span class="sxs-lookup"><span data-stu-id="321ac-125">In the Table field, select Customers.</span></span> 
3. <span data-ttu-id="321ac-126">A Mező mezőben válassza ki a Vevőcsoportot.</span><span class="sxs-lookup"><span data-stu-id="321ac-126">In the Field field, select Customer group.</span></span>
    * <span data-ttu-id="321ac-127">Ebben a példában egy bizonyos vevőcsoportot fogunk használni kiválasztási feltételnek.</span><span class="sxs-lookup"><span data-stu-id="321ac-127">In this example, we will use a specific customer group for the selection criteria.</span></span>  
4. <span data-ttu-id="321ac-128">A Feltétel mezőben válassza ki a 10. vevőcsoportot.</span><span class="sxs-lookup"><span data-stu-id="321ac-128">In the Criteria field, select Customer group 10.</span></span> 
5. <span data-ttu-id="321ac-129">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="321ac-129">Click OK.</span></span>


