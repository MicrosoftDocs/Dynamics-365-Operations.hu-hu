---
title: Munkaterületek konfigurálása és szűrése
description: Ez a cikk a munkaterületek konfigurálásáról és szűréséről nyújt áttekintést.
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankTreasurerWorkspace, HcmBenefitWorkspace, BudgetPlanningWorkspace, BusinessProcessGenericWorkspace, RetailCatalogManagementWorkspace, RetailCategoryAndProductWorkspace, RetailChannelManagementWorkspace, HcmCompensationWorkspace, CAMCostAccountingLedgerAdminWorkspace, CostAdminWorkspace, CostAnalysisWorkspace, CAMCostControlWorkspace, CustomerCollectionManagerWorkspace, CustomerInvoiceWorkspace, CustPaymentWorkspace, DataManagementWorkspace, DataValidationWorkspace, ERWorkspace, LedgerPeriodCloseProjectWorkspace, AssetWorkspace, GeneralJournalEntryWorkspace, VendVendorPortalInvoiceWorkspace, BudgetTrackingWorkspace, ReqCreatePlanWorkspace, BusinessProcessGenericOwnerWorkspace, SelfHealingWorkspace, WHSOutboundWorkMonitoringWorkspace, WHSWavePlanningWorkspace, PayrollWorkspace, HcmWorkforceWorkspace, RetailDiscountPricingWorkspace, EcoResProductDiscreteManufacturingWorkspace, KanbanPrepareProductForLeanWorkspace, EcoResProductProcessManufacturingWorkspace, EcoResProductVariantMaintainWorkspace, JmgShopSupervisorWorkspace, ProjProjectManagementWorkspace, VendVendorPortalWorkspace, PurchOrderMaintainWorkspace, PurchOrderProcessReceiptsWorkspace, HcmRecruitmentWorkspace, EcoResProductMaintainWorkspace, FMClerkWorkspace, OpResLifecycleManagementWorkspace, RetailITWorkspace, RetailChannelOperationsWorkspace, RetailStoreManagementWorkspace, SalesOrderProcessingWorkspace, SalesReturnWorkspace, SystemAdministrationWorkspaceForm, VendVendorRequestForQuotationsWorkspace, VendVendorProfileManagementWorkspace, VendInvoiceWorkspace, VendPaymentWorkspace
audience: Application User
ms.reviewer: sericks
ms.custom: 17491
ms.assetid: 541e6012-4680-4684-8494-e9b5ca4684ee
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b4f587608b03512aabce1d9b76ec4b9d6ec9227b
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559432"
---
# <a name="configure-and-filter-workspaces"></a><span data-ttu-id="6d63c-103">Munkaterületek konfigurálása és szűrése</span><span class="sxs-lookup"><span data-stu-id="6d63c-103">Configure and filter workspaces</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6d63c-104">Ez a cikk a munkaterületek konfigurálásáról és szűréséről nyújt áttekintést.</span><span class="sxs-lookup"><span data-stu-id="6d63c-104">This article provides an overview about how to configure and filter workspaces.</span></span>

## <a name="configuring-a-workspace"></a><span data-ttu-id="6d63c-105">Munkaterület konfigurációja</span><span class="sxs-lookup"><span data-stu-id="6d63c-105">Configuring a workspace</span></span>

<span data-ttu-id="6d63c-106">Teljes munkaterületre vonatkozó beállítások módosításával megváltoztathatja bizonyos munkaterületek megjelenését és viselkedését.</span><span class="sxs-lookup"><span data-stu-id="6d63c-106">You can change the appearance and behavior of some workspaces by updating settings that apply to the whole workspace.</span></span> <span data-ttu-id="6d63c-107">Konfigurálható munkaterületek esetén a Művelet panel tartalmaz egy olyan gombot, amellyel az ott megjelenő leírás szerint megváltoztatható a konfiguráció.</span><span class="sxs-lookup"><span data-stu-id="6d63c-107">When a workspace can be configured, the Action Pane includes a button that instructs you to click it to make configuration changes.</span></span> <span data-ttu-id="6d63c-108">Például az alábbi példában a megfelelő gomb neve: **Munkaterület konfigurálása**.</span><span class="sxs-lookup"><span data-stu-id="6d63c-108">For example, in the following illustration, the button is named **Configure my workspace**.</span></span>

<span data-ttu-id="6d63c-109">[![Munkaterületek konfigurálása és szűrése](./media/configure-and-filter-workspaces.png)](./media/configure-and-filter-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="6d63c-109">[![configure-and-filter-workspaces](./media/configure-and-filter-workspaces.png)](./media/configure-and-filter-workspaces.png)</span></span>

<span data-ttu-id="6d63c-110">Amikor rákattint a gombra, megjelenik egy párbeszédpanel, ahol módosíthatja a munkaterület előre megadott beállításait.</span><span class="sxs-lookup"><span data-stu-id="6d63c-110">When you click the button, a dialog appears, where you can modify the predefined settings for the workspace.</span></span> <span data-ttu-id="6d63c-111">A párbeszédpanelen látható beállítási lehetőségek munkaterületenként változnak, az adott munkaterületen elérhető vezérlőktől és üzleti adatoktól függenek.</span><span class="sxs-lookup"><span data-stu-id="6d63c-111">The specific settings that you see in this dialog vary by workspace, and depend on the specific controls and business data that are available in the workspace.</span></span>

<span data-ttu-id="6d63c-112">[![Munkaterület konfigurálása](./media/configure-my-workspace.png)](./media/configure-my-workspace.png)</span><span class="sxs-lookup"><span data-stu-id="6d63c-112">[![configure-my-workspace](./media/configure-my-workspace.png)](./media/configure-my-workspace.png)</span></span>

## <a name="filtering-a-workspace"></a><span data-ttu-id="6d63c-113">Egy munkaterület szűrése</span><span class="sxs-lookup"><span data-stu-id="6d63c-113">Filtering a workspace</span></span>

<span data-ttu-id="6d63c-114">Sok munkaterületen szűrhető az ott megjelenő tartalom.</span><span class="sxs-lookup"><span data-stu-id="6d63c-114">Many workspaces let you filter the content that appears in them.</span></span> <span data-ttu-id="6d63c-115">Az elérhető vezérlők lehetővé tehetik a munkaterület teljes tartalmának a szűrését, vagy a munkaterület egy bizonyos szakaszában lévő tartalomnak a szűrését.</span><span class="sxs-lookup"><span data-stu-id="6d63c-115">The controls that are available might let you filter all the content in the workspace or only the content in a specific section of the workspace.</span></span> <span data-ttu-id="6d63c-116">A munkaterület szűrői lehetnek keresések, kombinált listák, szabadszöveges mezők, vagy egyéb vezérlőtípusok.</span><span class="sxs-lookup"><span data-stu-id="6d63c-116">The filters on workspaces can be lookups, combo boxes, free-form text fields, or other types of controls.</span></span> <span data-ttu-id="6d63c-117">Azonban minden szűrőtípusnak ugyanolyan a hatása; ez a következő szakaszokban olvasható.</span><span class="sxs-lookup"><span data-stu-id="6d63c-117">However, every type of filter has the same effects, as described in the following sections.</span></span>

### <a name="workspace-wide-filters"></a><span data-ttu-id="6d63c-118">Munkaterület szintű szűrés</span><span class="sxs-lookup"><span data-stu-id="6d63c-118">Workspace-wide filters</span></span>

<span data-ttu-id="6d63c-119">Lehetősége van az egész munkaterület szűrésére egy munkaterület szintű szűrő segítségével.</span><span class="sxs-lookup"><span data-stu-id="6d63c-119">You can filter the whole workspace by using a workspace-wide filter.</span></span> <span data-ttu-id="6d63c-120">A munkaterület szintű szűrő a munkaterület bal felső sarkában jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="6d63c-120">A workspace-wide filter appears in the upper-left corner of the workspace.</span></span> <span data-ttu-id="6d63c-121">Ha kiválaszt egy konkrét értéket a legördülő menüből, a munkaterületen lévő tartalom a kiválasztott érték szerinti szűrés alapján rendeződik át.</span><span class="sxs-lookup"><span data-stu-id="6d63c-121">When you select a specific value in the drop-down list, the contents of the workspace are filtered based on that selection.</span></span>

<span data-ttu-id="6d63c-122">[![Munkaterület szűrése](./media/workspace-filter.png)](./media/workspace-filter.png)</span><span class="sxs-lookup"><span data-stu-id="6d63c-122">[![workspace-filter](./media/workspace-filter.png)](./media/workspace-filter.png)</span></span>

<span data-ttu-id="6d63c-123">Kattintással megnyílik a szűrő; ezután több lehetőség közül választhat.</span><span class="sxs-lookup"><span data-stu-id="6d63c-123">When you click to open the filter, you're presented with several options.</span></span>

<span data-ttu-id="6d63c-124">[![Kibontott munkaterületszűrő](./media/workspace-filter-expanded.png)](./media/workspace-filter-expanded.png)</span><span class="sxs-lookup"><span data-stu-id="6d63c-124">[![workspace-filter-expanded](./media/workspace-filter-expanded.png)](./media/workspace-filter-expanded.png)</span></span>

<span data-ttu-id="6d63c-125">Válasszon ki egy lehetőséget, amely alapján szűrni kívánja a munkaterületet.</span><span class="sxs-lookup"><span data-stu-id="6d63c-125">Select an option to filter the workspace based on that option.</span></span>

### <a name="workspace-section-filters"></a><span data-ttu-id="6d63c-126">Munkaterület szakasz szűrők</span><span class="sxs-lookup"><span data-stu-id="6d63c-126">Workspace section filters</span></span>

<span data-ttu-id="6d63c-127">Ha a munkaterület szakaszai rendelkeznek saját szűrővel, az egyes szakaszok külön-külön is szűrhetők.</span><span class="sxs-lookup"><span data-stu-id="6d63c-127">If individual sections of the workspace have filters, you can filter each section separately.</span></span> <span data-ttu-id="6d63c-128">A következő ábra a szabadszöveges mező típusú szűrőre mutat példát (a szűrő az a mező, amely a „Szűrő” szöveget tartalmazza).</span><span class="sxs-lookup"><span data-stu-id="6d63c-128">In the following illustration, the filter (the field that contains the text "Filter") is an example of a free-form text field filter.</span></span>

<span data-ttu-id="6d63c-129">[![Munkaterületszakasz-szűrők](./media/workspace-section-filters.png)](./media/workspace-section-filters.png)</span><span class="sxs-lookup"><span data-stu-id="6d63c-129">[![workspace-section-filters](./media/workspace-section-filters.png)](./media/workspace-section-filters.png)</span></span>

<span data-ttu-id="6d63c-130">Ahogyan a munkaterület szintű szűrőnél, itt is válassza ki vagy adja meg azt az értékét, amely alapján a szakasz tartalmát szűkíteni kívánja.</span><span class="sxs-lookup"><span data-stu-id="6d63c-130">As with a workspace-wide filter, select or enter a value in the field to filter the contents of the section.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]