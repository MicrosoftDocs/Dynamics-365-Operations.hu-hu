---
title: Előrejelzési modellek létrehozása projektköltségvetésekhez
description: Ez a témakör azt mutatja be, hogyan lehet előrejelzési modellt létrehozni a fennmaradó költségvetésekhez.
author: RadhikaRS
manager: AnnBe
ms.date: 04/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 07e540f23a668b40a54906a67d87552fe991825a
ms.sourcegitcommit: 5de75c61c33e57c813944f1ab6100aceb020d432
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/29/2020
ms.locfileid: "3321779"
---
# <a name="create-forecast-models-for-project-budgets"></a><span data-ttu-id="9d839-103">Előrejelzési modellek létrehozása projektköltségvetésekhez</span><span class="sxs-lookup"><span data-stu-id="9d839-103">Create forecast models for project budgets</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9d839-104">Ez a témakör azt mutatja be, hogyan lehet előrejelzési modellt létrehozni a fennmaradó költségvetésekhez.</span><span class="sxs-lookup"><span data-stu-id="9d839-104">This topic describes how to create a forecast model for remaining budgets.</span></span> <span data-ttu-id="9d839-105">A költségvetési ellenőrzés tárgyát képező projektekhez a költségvetések két típusa használható: az eredeti és a fennmaradó.</span><span class="sxs-lookup"><span data-stu-id="9d839-105">A project that is subject to budget control uses two types of budgets: original and remaining.</span></span> <span data-ttu-id="9d839-106">A projektköltségvetések létrehozásakor meg kell adnia az eredeti és a fennmaradó költségvetés előrejelzési modelljeit, amelyek az **Előrejelzési modellek** oldalon lettek létrehozva.</span><span class="sxs-lookup"><span data-stu-id="9d839-106">When you create a project budget, you must specify the original and remaining budget forecast models that were created in the **Forecast models** page.</span></span> <span data-ttu-id="9d839-107">A megadott modelleken alapuló projektköltségvetések a projektköltségvetés véglegesítésekor jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="9d839-107">Project budgets based on the specified models are created when you commit the project budget.</span></span>

> [!NOTE]
> <span data-ttu-id="9d839-108">A költségvetés-ellenőrzéshez használt előrejelzési modellekhez nem tartozhatnak részmodellek, illetve ezek a modellek részmodellként sem használhatók.</span><span class="sxs-lookup"><span data-stu-id="9d839-108">A forecast model that is used for budget control can’t have a submodel or be used as a submodel.</span></span>

1. <span data-ttu-id="9d839-109">Válassza ki a **Projektvezetés és a könyvelés** > **Beállítás** > **Előrejelzések**  > **Előrejelzési modellek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9d839-109">Select **Project management and accounting** > **Setup** > **Forecasts**  > **Forecast models**.</span></span>
2. <span data-ttu-id="9d839-110">Válassza az **Új** elemet egy új előrejelzési modell létrehozásához, majd adja meg az új modell azonosítószámát és nevét.</span><span class="sxs-lookup"><span data-stu-id="9d839-110">Select **New** to create a new forecast model, and then enter a model ID number and name for the new model.</span></span> 
3. <span data-ttu-id="9d839-111">Állítsa a **Leállítva** beállítást **Igen** értékre előrejelzés soraiban történt módosítások megakadályozása érdekében.</span><span class="sxs-lookup"><span data-stu-id="9d839-111">Set the **Stopped** option to **Yes** to prevent any changes to the forecast lines for the forecast model.</span></span> 
4. <span data-ttu-id="9d839-112">Ha a modellhez rendelt előrejelzési soroknak pénzforgalmi előrejelzéseket kell létrehozniuk a főkönyvben, állítsa az **Költségvetések szerepeltetése pénzforgalmi előrejelzésekben** **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="9d839-112">If the forecast lines that the model is associated with should generate cash flow forecasts in the general ledger, set **Include in Cash flow forecasts** to **Yes.**</span></span> 
5. <span data-ttu-id="9d839-113">Ha azt szeretné, hogy a projekt dátuma a számla dátuma legyen, akkor az **Előrejelzési számladátum** beállítást állítsa **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="9d839-113">To use the project date as the invoice date, set **Forecast Invoice date** to **Yes**.</span></span> 
6. <span data-ttu-id="9d839-114">A **Költségvetés típusa** mezőben jelöljön ki egyet a következő modelltípusok közül:</span><span class="sxs-lookup"><span data-stu-id="9d839-114">In the **Budget type** field, select one of the following model types:</span></span>

   - <span data-ttu-id="9d839-115">**Eredeti költségvetés** Az eredeti költségvetési összegek használata, amelyek a kezdeti költségvetés létrehozásakor és jóváhagyásakor véglegesíthetők.</span><span class="sxs-lookup"><span data-stu-id="9d839-115">**Original budget**: Use the original budget amounts that are committed when the initial budget is created and approved.</span></span>
   - <span data-ttu-id="9d839-116">**Fennmaradó költségvetés**: A fennmaradó költségvetési összegek felhasználása a projekt élettartama során.</span><span class="sxs-lookup"><span data-stu-id="9d839-116">**Remaining budget**: Use the remaining budget amounts during the life of the project.</span></span> <span data-ttu-id="9d839-117">Ebben az előrejelzési modellben a tényleges tranzakciók csökkentik, a költségvetés-verziók pedig növelik vagy csökkentik az egyenlegeket.</span><span class="sxs-lookup"><span data-stu-id="9d839-117">The balances in this forecast model are reduced by actual transactions and increased or decreased by budget revisions.</span></span>
   - <span data-ttu-id="9d839-118">**Átvitel**: A projekt áthozott költségvetési összegeinek használata.</span><span class="sxs-lookup"><span data-stu-id="9d839-118">**Carry-forward**: Use the carry-forward budget amounts for the project.</span></span> <span data-ttu-id="9d839-119">Az átvitel egy választható folyamat, amelynek futtatásával a nem használt költségvetési összegek átvihetők egyik pénzügyi évből a másikba.</span><span class="sxs-lookup"><span data-stu-id="9d839-119">Carry-forward is an optional process that can be run to transfer unused budget amounts from one fiscal year to another.</span></span>

7. <span data-ttu-id="9d839-120">Szükség szerint adja meg a következő beállításokat:</span><span class="sxs-lookup"><span data-stu-id="9d839-120">Set the following options as required:</span></span>

   - <span data-ttu-id="9d839-121">Ha azt szeretné, hogy a projekt dátuma a számla dátuma legyen, akkor engedélyezze az **Előrejelzési számladátum** beállítást.</span><span class="sxs-lookup"><span data-stu-id="9d839-121">Enable **Forecast invoice date** to use the project date as the invoice date.</span></span>
   - <span data-ttu-id="9d839-122">Engedélyezze az **Előrejelzés befejezetlen termeléssel** a z előrejelzéshez folyamatban lévő munkák (WIP) alapján, majd válassza ki a WIP típusát.</span><span class="sxs-lookup"><span data-stu-id="9d839-122">Enable **Forecast with WIP** to forecast based on work in progress (WIP), and then select the type of WIP.</span></span> 
   - <span data-ttu-id="9d839-123">Az alapértelmezett **Költségvetési típust** **Nem** értéken hagyhatja vagy megadhat egy új típust is.</span><span class="sxs-lookup"><span data-stu-id="9d839-123">You can keep the default **Budget type** as **None** or enter a new type.</span></span> <span data-ttu-id="9d839-124">A költségvetés típusa nem módosítható egy rekord módosítása után.</span><span class="sxs-lookup"><span data-stu-id="9d839-124">The budget type can't be changed after you change a record.</span></span>     
    > [!NOTE]
    > <span data-ttu-id="9d839-125">Ha módosítja az alapértelmezett költségvetéstípust, akkor semmilyen további beállítás nem lesz elérhető a frissítésekhez, és ezt az előrejelzési modellt nem lehet újra felhasználni.</span><span class="sxs-lookup"><span data-stu-id="9d839-125">If you change the default budget type, all other options will become unavailable for updates, and you can't reuse this forecast model.</span></span> 
   


 

