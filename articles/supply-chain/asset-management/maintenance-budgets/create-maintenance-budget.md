---
title: Karbantartási költségvetések létrehozása
description: Ez a témakör azt mutatja be, hogyan lehet a karbantartási költségvetést létrehozni az Eszközkezelés modulban.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetBudgetLineAdjust, EntAssetBudget, EntAssetBudgetRecalc, EntAssetBudgetCopy, EntAssetBudgetLine, EntAssetBudgetCreate, EntAssetBudgetApprove, EntAssetBudgetCalculateActualCost
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2aaba8794bf0025f0449509752e4f197d3bf3db4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429583"
---
# <a name="create-maintenance-budgets"></a><span data-ttu-id="03bc9-103">Karbantartási költségvetések létrehozása</span><span class="sxs-lookup"><span data-stu-id="03bc9-103">Create maintenance budgets</span></span>

[!include [banner](../../includes/banner.md)]

 



<span data-ttu-id="03bc9-104">A karbantartási költségvetések a megelőző karbantartás várható költségeinek áttekintését szolgálják.</span><span class="sxs-lookup"><span data-stu-id="03bc9-104">Maintenance budgets are used to provide an overview of expected costs for preventive maintenance.</span></span> <span data-ttu-id="03bc9-105">A költségvetési sorok számítása a karbantartási ütemezési sorok alapján történik, amelyeknek a várható kezdési dátuma a költségvetési időszakra esik.</span><span class="sxs-lookup"><span data-stu-id="03bc9-105">Budget lines are calculated based on maintenance schedule lines that have an expected start date during the budget period.</span></span>

<span data-ttu-id="03bc9-106">A karbantartási költségvetések alapját az Eszközkezeléshez használt költségtípusok jelentik: **Megelőző**, **Javító** és **Beruházás**.</span><span class="sxs-lookup"><span data-stu-id="03bc9-106">Maintenance budgets are based on the cost types that are used in Asset Management: **Preventive**, **Corrective**, and **Investment**.</span></span> <span data-ttu-id="03bc9-107">A beruházás karbantartás költségvetési költségei szerepelnek az olyan aktív eszközöknél, amelyek helyettesítési dátuma a költségvetési időszakban van, és van kapcsolódó helyettesítő értékük.</span><span class="sxs-lookup"><span data-stu-id="03bc9-107">Budget costs for investment maintenance are included for active assets that have a replacement date during the budget period and a related replacement value.</span></span> <span data-ttu-id="03bc9-108">A helyesbítő karbantartás költségvetési költségei akkor szerepelnek, ha a költségvetés-számításban szerepel egy múltbeli helyesbítő dátum.</span><span class="sxs-lookup"><span data-stu-id="03bc9-108">Budget costs for corrective maintenance are included if a past corrective date is included in the budget calculation.</span></span> <span data-ttu-id="03bc9-109">Ebben az esetben a korábbi időszak javító költségét ugyanarra a jövőbeli időszakra számítja ki a rendszer, amelyre a karbantartás költségvetését kiszámította.</span><span class="sxs-lookup"><span data-stu-id="03bc9-109">In that case, corrective costs from an earlier period are calculated for the same future period that you calculate the maintenance budget for.</span></span>

## <a name="create-a-maintenance-budget"></a><span data-ttu-id="03bc9-110">Karbantartási költségvetés létrehozása</span><span class="sxs-lookup"><span data-stu-id="03bc9-110">Create a maintenance budget</span></span>

1. <span data-ttu-id="03bc9-111">Válassza ki: **Eszközkezelés** \> **Lekérdezések** \> **Karbantartási költségvetés** \> **Költségvetés**.</span><span class="sxs-lookup"><span data-stu-id="03bc9-111">Select **Asset management** \> **Inquiries** \> **Maintenance budget** \> **Budget**.</span></span>
2. <span data-ttu-id="03bc9-112">Válassza a **Költségvetés létrehozása** elemet.</span><span class="sxs-lookup"><span data-stu-id="03bc9-112">Select **Create budget**.</span></span>
3. <span data-ttu-id="03bc9-113">A **Karbantartási költségvetés** mezőbe írja be a költségvetés azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="03bc9-113">In the **Maintenance budget** field, enter a budget ID.</span></span>
4. <span data-ttu-id="03bc9-114">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="03bc9-114">In the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="03bc9-115">Az **Időszak** gyorslapon, a **Kezdő dátum** és a **Záró dátum** mezőkben, adja meg a költségvetési időszak kezdő és záró dátumát.</span><span class="sxs-lookup"><span data-stu-id="03bc9-115">On the **Period** FastTab, in the **From date** and **To date** fields, enter the start and end dates of the budget period.</span></span>
5. <span data-ttu-id="03bc9-116">Az előző időszak tényleges költségei alapján kiszámított javító költségvetési költségek felvételéhez, a **Helyesbítő kezdő dátum** mezőbe írja be annak az időszaknak a kezdő dátumát, amelyből a költségeket figyelembe kell venni.</span><span class="sxs-lookup"><span data-stu-id="03bc9-116">To include corrective budget costs that are calculated on the basis of actual costs from a previous period, in the **Corrective from date** field, enter the start date of the period that those costs should be included from.</span></span>
6. <span data-ttu-id="03bc9-117">A költségvetésben szükséges részletességi szinttől függően adja meg a megfelelő beállításokat az öt **Csoport által** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="03bc9-117">Depending on the level of detail that is required in the budget, set the relevant options on the five **Group by** FastTabs.</span></span>
7. <span data-ttu-id="03bc9-118">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="03bc9-118">Select **OK**.</span></span>
8. <span data-ttu-id="03bc9-119">Válassza ki a **Költségvetési sorok** lehetőséget a **Karbantartási költségvetési sorok** lap megnyitásához, amelyen megtekintheti az adott időszakra vonatkozóan létrehozott összes költségvetési sort.</span><span class="sxs-lookup"><span data-stu-id="03bc9-119">Select **Budget lines** to open **Maintenance budget lines** page, where you can view all the budget lines that have been created for the period.</span></span>
9. <span data-ttu-id="03bc9-120">A költségvetés jóváhagyásához jelölje ki a **Karbantartási költségvetések** lapon, majd válassza a **Jóváhagyás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="03bc9-120">To approve the budget, select it on the **Maintenance budgets** page, and then select **Approve**.</span></span> <span data-ttu-id="03bc9-121">Ezután kattintson a **Költségvetési jóváhagyása** párbeszédpanelen az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="03bc9-121">Then, in the **Approve budget** dialog box, select **OK**.</span></span> <span data-ttu-id="03bc9-122">A név megadása az **Jóváhagyó** mezőben történik a **Karbantartási költségvetések** lapon.</span><span class="sxs-lookup"><span data-stu-id="03bc9-122">Your name is entered in the **Approved by** field on the **Maintenance budgets** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="03bc9-123">A karbantartási költségvetés jóváhagyása után nem lehet újraszámolni vagy módosítani a kapcsolódó sorokat a **Karbantartás költségvetési sorok** lapon, hacsak nem törli a jóváhagyást.</span><span class="sxs-lookup"><span data-stu-id="03bc9-123">After you've approved a maintenance budget, you can't recalculate or adjust the related lines on the **Maintenance budget lines** page unless you first remove the approval.</span></span> <span data-ttu-id="03bc9-124">A karbantartási költségvetés jóváhagyásának visszavonásához jelölje ki a **Karbantartási költségvetések** lapon, majd válassza a **Jóváhagyás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="03bc9-124">To remove the approval of a maintenance budget, select it on the **Maintenance budgets** page, and then select **Approve**.</span></span> <span data-ttu-id="03bc9-125">Ezután kattintson a **Költségvetési jóváhagyása** párbeszédpanelen az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="03bc9-125">Then, in the **Approve budget** dialog box, select **OK**.</span></span>

![Karbantartási költségvetések](media/01-maintenance-budgets.png)

<span data-ttu-id="03bc9-127">Új karbantartási költségvetés egy meglévő költségvetés másolásával is létrehozhat.</span><span class="sxs-lookup"><span data-stu-id="03bc9-127">You can also create a new maintenance budget by copying an existing budget.</span></span> <span data-ttu-id="03bc9-128">A **Karbantartási költségvetések** lapon válassza ki a másolandó költségvetést, majd válassza a **Másolás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="03bc9-128">On the **Maintenance budgets** page, select the budget to copy, and then select **Copy**.</span></span> <span data-ttu-id="03bc9-129">Ez a megközelítés akkor lehet hasznos, ha például egy hónapra már létrehoztak egy költségvetést, és át szeretné másolni más hónapokra.</span><span class="sxs-lookup"><span data-stu-id="03bc9-129">This approach is useful if, for example, you've created a budget for one month and want to copy it to other months.</span></span>

> [!NOTE]
> <span data-ttu-id="03bc9-130">A karbantartási költségvetés csak a karbantartási ütemezés sorai alapján számítja ki a költségvetési költségeket.</span><span class="sxs-lookup"><span data-stu-id="03bc9-130">The maintenance budget calculates only budget costs based on maintenance schedule lines.</span></span> <span data-ttu-id="03bc9-131">Ha ugyanarra az időszakra vonatkozóan szeretné kiszámítani a tényleges költségeket, akkor ezt az **Eszközköltség ellenőrzése** lapon teheti meg.</span><span class="sxs-lookup"><span data-stu-id="03bc9-131">To calculate actual costs for the same period, you can do that calculation on the **Asset cost control** page.</span></span> 
