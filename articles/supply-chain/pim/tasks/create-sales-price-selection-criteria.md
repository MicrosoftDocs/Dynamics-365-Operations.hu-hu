---
title: Eladási ár kiválasztási feltételeinek létrehozása
description: Ez az eljárás bemutatja, hogyan hozhat létre eladási ár kiválasztási feltételeket az attribútumalapú eladásiár-modellekhez.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelSelectionCriteria, SysQueryForm, SysQueryTableLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 69d22c3321beaa2667ee20bff00acd746714b993
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920531"
---
# <a name="create-sales-price-selection-criteria"></a><span data-ttu-id="2d108-103">Eladási ár kiválasztási feltételeinek létrehozása</span><span class="sxs-lookup"><span data-stu-id="2d108-103">Create sales price selection criteria</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2d108-104">Ez az eljárás bemutatja, hogyan hozhat létre eladási ár kiválasztási feltételeket az attribútumalapú eladásiár-modellekhez.</span><span class="sxs-lookup"><span data-stu-id="2d108-104">This procedure shows how to create a sales price selection criterion for attribute-based sales price models.</span></span> <span data-ttu-id="2d108-105">Az eljáráshoz előfeltétel, hogy legyen legalább egy elérhető eladásiár-modell.</span><span class="sxs-lookup"><span data-stu-id="2d108-105">This procedure requires that at least one sales price model be available.</span></span> <span data-ttu-id="2d108-106">Ebben a példában a hangszóró megoldás eladásiár-modelljének ármodelljét használjuk a USMF bemutatócég esetében.</span><span class="sxs-lookup"><span data-stu-id="2d108-106">This example uses the price model for the Speaker solution sales price model in the USMF demo data company.</span></span> <span data-ttu-id="2d108-107">Ezt az eljárást általában a termékmenedzser használja.</span><span class="sxs-lookup"><span data-stu-id="2d108-107">Typically, a product manager uses this procedure.</span></span>

## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a><span data-ttu-id="2d108-108">Új feltétel hozzáadása a meglévő eladásiár-modellhez</span><span class="sxs-lookup"><span data-stu-id="2d108-108">Add a new criterion for an existing sales price model</span></span>

1. <span data-ttu-id="2d108-109">Lépjen a **Termékinformáció-kezelés \> Termékek \> Termékkonfigurációs modellek** elemre.</span><span class="sxs-lookup"><span data-stu-id="2d108-109">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="2d108-110">A listában jelölje ki a hangszóró megoldás termékmodelljének a sorát, de ne kattintson rá a modell nevének hivatkozására.</span><span class="sxs-lookup"><span data-stu-id="2d108-110">In the list, select the row for the Speaker solution product model, but don't select the link for the model name.</span></span>
1. <span data-ttu-id="2d108-111">A Műveleti ablaktáblán kattintson a **Modell** elemre.</span><span class="sxs-lookup"><span data-stu-id="2d108-111">On the Action Pane, select **Model**.</span></span>
1. <span data-ttu-id="2d108-112">Válassza ki az **Ármodellfeltételek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2d108-112">Select **Price model criteria**.</span></span>
1. <span data-ttu-id="2d108-113">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2d108-113">Select **New**.</span></span>
1. <span data-ttu-id="2d108-114">A **Név** mezőbe írja be a „10. vásárlócsoport” szöveget.</span><span class="sxs-lookup"><span data-stu-id="2d108-114">In the **Name** field, type 'Customer group 10'.</span></span>
    * <span data-ttu-id="2d108-115">Az ármodellfeltétel nevének a használata segít azonosítani az alapul szolgáló kiválasztási feltételeket.</span><span class="sxs-lookup"><span data-stu-id="2d108-115">The name of the price model criterion is used to help identify the underlying selection criteria.</span></span>  
1. <span data-ttu-id="2d108-116">Az **Ármodell** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2d108-116">In the **Price model** field, enter or select a value.</span></span>
1. <span data-ttu-id="2d108-117">A **Rendeléstípus** mezőben válassza ki az *Értékesítési rendelés* elemet.</span><span class="sxs-lookup"><span data-stu-id="2d108-117">In the **Order type** field, select *Sales order*.</span></span>
    * <span data-ttu-id="2d108-118">A rendelés típusa határozza meg, hogy az adatbázis mely mezői állnak rendelkezésre a kiválasztási lekérdezéshez.</span><span class="sxs-lookup"><span data-stu-id="2d108-118">The order type determines the database fields that will be available for the selection query.</span></span>  
1. <span data-ttu-id="2d108-119">Adja meg a dátumot az **Érvényesség kezdete** mezőben.</span><span class="sxs-lookup"><span data-stu-id="2d108-119">In the **Valid from** field, enter a date.</span></span>
1. <span data-ttu-id="2d108-120">Az **Érvényesség vége** mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="2d108-120">In the **Expire by** field, enter a date.</span></span>
1. <span data-ttu-id="2d108-121">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2d108-121">Select **Save**.</span></span>

## <a name="create-the-query-for-the-selection-criteria"></a><span data-ttu-id="2d108-122">A lekérdezés létrehozása a kiválasztási feltételekhez</span><span class="sxs-lookup"><span data-stu-id="2d108-122">Create the query for the selection criteria</span></span>

1. <span data-ttu-id="2d108-123">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="2d108-123">Select **Edit**.</span></span>
2. <span data-ttu-id="2d108-124">Válasszon ki **Vevőket** a *Tábla* mezőben.</span><span class="sxs-lookup"><span data-stu-id="2d108-124">In the **Table** field, select *Customers*.</span></span>
3. <span data-ttu-id="2d108-125">A **Mező** mezőben válassza ki a *Vevőcsoportot*.</span><span class="sxs-lookup"><span data-stu-id="2d108-125">In the **Field** field, select *Customer group*.</span></span>
    * <span data-ttu-id="2d108-126">Ebben a példában egy bizonyos vevőcsoportot fogunk használni kiválasztási feltételnek.</span><span class="sxs-lookup"><span data-stu-id="2d108-126">In this example, we will use a specific customer group for the selection criteria.</span></span>  
4. <span data-ttu-id="2d108-127">A **Feltétel** mezőben válassza ki a *10. vevőcsoportot*.</span><span class="sxs-lookup"><span data-stu-id="2d108-127">In the **Criteria** field, select *Customer group 10*.</span></span>
5. <span data-ttu-id="2d108-128">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2d108-128">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]