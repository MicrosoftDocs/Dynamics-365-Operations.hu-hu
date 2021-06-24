---
title: Befejezetlen vagy hiányzó munka miatt nem erősítheti meg a szállítmányt
description: Befejezetlen vagy hiányzó munka miatt nem erősítheti meg a szállítmányt
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm, WHSContainerCloseDiag_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: beef0909d41e69f3e7bcc1021527be35b7e6fd44
ms.sourcegitcommit: c2c6d687a89bc1534c029109315c23e92865b63b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/31/2021
ms.locfileid: "6123843"
---
# <a name="you-cant-confirm-a-shipment-because-of-incomplete-or-missing-work"></a><span data-ttu-id="7502a-103">Befejezetlen vagy hiányzó munka miatt nem erősítheti meg a szállítmányt</span><span class="sxs-lookup"><span data-stu-id="7502a-103">You can't confirm a shipment because of incomplete or missing work</span></span>

<span data-ttu-id="7502a-104">Hibakód: WAX515</span><span class="sxs-lookup"><span data-stu-id="7502a-104">Error code: WAX515</span></span>

## <a name="symptoms"></a><span data-ttu-id="7502a-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="7502a-105">Symptoms</span></span>

<span data-ttu-id="7502a-106">Szállítmány megerősítésekor a rendszer a következő hibaüzenetet jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="7502a-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="7502a-107">A(z) %1 szállítmány szállítása nem igazolható vissza, mert a rakomány minden munkájának be kell fejeződnie.</span><span class="sxs-lookup"><span data-stu-id="7502a-107">The shipment for load %1 could not be confirmed because all work for the load must be complete.</span></span>

<span data-ttu-id="7502a-108">Ezért nem tudja megerősíteni a szállítmányt a betöltéshez.</span><span class="sxs-lookup"><span data-stu-id="7502a-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="7502a-109">Ok</span><span class="sxs-lookup"><span data-stu-id="7502a-109">Cause</span></span>

<span data-ttu-id="7502a-110">A rakomány vagy szállítmány jelenleg olyan állapotban van, amelyben a szállítmány megerősítése sikertelen.</span><span class="sxs-lookup"><span data-stu-id="7502a-110">The load or shipment is currently in a state where shipment confirmation fails.</span></span> <span data-ttu-id="7502a-111">A szállítmány megerősítése előtt legalább egy munkának léteznie kell a rakományhoz, és minden munkának *Lezárt* vagy *Visszavonva* állapotúnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="7502a-111">Before you can confirm the shipment, at least some work must exist for the load, and all that work must have a status of *Closed* or *Canceled*.</span></span>

## <a name="resolution"></a><span data-ttu-id="7502a-112">Felbontás</span><span class="sxs-lookup"><span data-stu-id="7502a-112">Resolution</span></span>

<span data-ttu-id="7502a-113">Ellenőrizze a rakomány vagy szállítmány kapcsolódó értékesítési rendeléseit és átmozgatott rendeléseit, illetve győződjön meg arról, hogy minden kapcsolódó munkát befejeztek vagy töröltek.</span><span class="sxs-lookup"><span data-stu-id="7502a-113">Check the related sales orders or transfer orders for the load or shipment, and make sure that all the related work has been completed or canceled.</span></span>

<span data-ttu-id="7502a-114">A szállítmányokkal és a rakományokkal több oldalon is dolgozhat.</span><span class="sxs-lookup"><span data-stu-id="7502a-114">You can work with shipments and loads on several pages.</span></span> <span data-ttu-id="7502a-115">Az alábbi alszakaszok néhány példát mutatnak be.</span><span class="sxs-lookup"><span data-stu-id="7502a-115">The following subsections provide a few examples.</span></span>

### <a name="all-loads-page"></a><span data-ttu-id="7502a-116">Minden rakomány lap</span><span class="sxs-lookup"><span data-stu-id="7502a-116">All loads page</span></span>

1. <span data-ttu-id="7502a-117">Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="7502a-117">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="7502a-118">Válassza ki azt a rakományt, amelynél a szállítmányt nem lehet megerősíteni.</span><span class="sxs-lookup"><span data-stu-id="7502a-118">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="7502a-119">A Művelet ablaktábla **Betöltések** lapjának **Kapcsolódó információk** csoportjában válassza a **Munka** elemet.</span><span class="sxs-lookup"><span data-stu-id="7502a-119">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="7502a-120">Az egyes munkaazonosítók állapotának vizsgálata.</span><span class="sxs-lookup"><span data-stu-id="7502a-120">Inspect the status of each work ID.</span></span> <span data-ttu-id="7502a-121">Minden olyan munkaazonosító nyomon követési állapota, amely nem *Lezárt* vagy *Visszavonva* állapotú.</span><span class="sxs-lookup"><span data-stu-id="7502a-121">Follow up on each work ID that doesn't have a status of *Closed* or *Canceled*.</span></span>
1. <span data-ttu-id="7502a-122">Ha minden munkaazonosító állapota *Lezárt* vagy *Visszavonva*, akkor próbálja meg újra a szállítmány megerősítését.</span><span class="sxs-lookup"><span data-stu-id="7502a-122">When every work ID has a status of *Closed* or *Canceled*, try again to confirm the shipment.</span></span>

### <a name="all-shipments-page"></a><span data-ttu-id="7502a-123">Minden szállítmány oldal</span><span class="sxs-lookup"><span data-stu-id="7502a-123">All shipments page</span></span>

1. <span data-ttu-id="7502a-124">Lépjen a **Raktárkezelés \> Szállítmányok \> Minden szállítmány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="7502a-124">Go to **Warehouse management \> Shipments\> All shipments**.</span></span>
1. <span data-ttu-id="7502a-125">Válassza ki azt a rakományt, amelyet nem lehet megerősíteni.</span><span class="sxs-lookup"><span data-stu-id="7502a-125">Select the shipment that can't be confirmed.</span></span>
1. <span data-ttu-id="7502a-126">A Művelet ablaktábla **Szállítmányok** lapjának **Munka** csoportjában válassza a **Munka részletei** elemet.</span><span class="sxs-lookup"><span data-stu-id="7502a-126">On the Action Pane, on the **Shipments** tab, in the **Work** group, select **Work details**.</span></span>
1. <span data-ttu-id="7502a-127">Az egyes munkaazonosítók állapotának vizsgálata.</span><span class="sxs-lookup"><span data-stu-id="7502a-127">Inspect the status of each work ID.</span></span> <span data-ttu-id="7502a-128">Minden olyan munkaazonosító nyomon követési állapota, amely nem *Lezárt* vagy *Visszavonva* állapotú.</span><span class="sxs-lookup"><span data-stu-id="7502a-128">Follow up on each work ID that doesn't have a status of *Closed* or *Canceled*.</span></span>
1. <span data-ttu-id="7502a-129">Ha minden munkaazonosító állapota *Lezárt* vagy *Visszavonva*, akkor próbálja meg újra a szállítmány megerősítését.</span><span class="sxs-lookup"><span data-stu-id="7502a-129">When every work ID has a status of *Closed* or *Canceled*, try again to confirm the shipment.</span></span>

### <a name="all-work-page"></a><span data-ttu-id="7502a-130">Minden munka lap</span><span class="sxs-lookup"><span data-stu-id="7502a-130">All work page</span></span>

1. <span data-ttu-id="7502a-131">Ugorjon a **Raktárkezelés \> Munka \> Minden munka** pontra.</span><span class="sxs-lookup"><span data-stu-id="7502a-131">Go to **Warehouse management \> Work\> All work**.</span></span>
1. <span data-ttu-id="7502a-132">Válassza ki azt a rendelésszámot, amelyhez nem lehet megerősíteni a szállítmányt.</span><span class="sxs-lookup"><span data-stu-id="7502a-132">Select the work for the order number that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="7502a-133">A műveleti ablaktábla **Szállítmány** fülön lévő **Szállítmány** csoportban válassza a **Szállítmány megerősítése** elemet.</span><span class="sxs-lookup"><span data-stu-id="7502a-133">On the Action Pane, on the **Shipment** tab, in the **Shipment** group, select **Confirm shipment**.</span></span>
1. <span data-ttu-id="7502a-134">Az egyes munkaazonosítók állapotának vizsgálata.</span><span class="sxs-lookup"><span data-stu-id="7502a-134">Inspect the status of each work ID.</span></span> <span data-ttu-id="7502a-135">Minden olyan munkaazonosító nyomon követési állapota, amely nem *Lezárt* vagy *Visszavonva* állapotú.</span><span class="sxs-lookup"><span data-stu-id="7502a-135">Follow up on each work ID that doesn't have a status of *Closed* or *Canceled*.</span></span>
1. <span data-ttu-id="7502a-136">Ha minden munkaazonosító állapota *Lezárt* vagy *Visszavonva*, akkor próbálja meg újra a szállítmány megerősítését.</span><span class="sxs-lookup"><span data-stu-id="7502a-136">When every work ID has a status of *Closed* or *Canceled*, try again to confirm the shipment.</span></span>
