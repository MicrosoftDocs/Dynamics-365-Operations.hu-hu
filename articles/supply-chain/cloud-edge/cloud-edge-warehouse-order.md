---
title: Raktérkezelés rendelései felhőalapú és peremhálózat-lépték szerinti egységekhez
description: Ez a témakör a raktári rendelési funkcióval kapcsolatban tartalmaz tájékoztatást, amely a raktári mérlegegység terhelésének részeként használatos.
author: perlynne
manager: tfeyr
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWarehouseOrderLine, WHSWarehouseReceiptEntry, PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: c04127b9fe621d962be2d7fe06358b3bd1b78916
ms.sourcegitcommit: 289e9183d908825f4c8dcf85d9affd4119238d0c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/02/2021
ms.locfileid: "5105710"
---
# <a name="warehouse-orders-for-cloud-and-edge-scale-units"></a><span data-ttu-id="f301e-103">Raktérkezelés rendelései felhőalapú és peremhálózat-lépték szerinti egységekhez</span><span class="sxs-lookup"><span data-stu-id="f301e-103">Warehouse orders for cloud and edge scale units</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> <span data-ttu-id="f301e-104">Nem minden üzleti funkció teljes mértékben támogatott a nyilvános előzetes verzióban, ha a mérlegegység munkaterheléseket használja.</span><span class="sxs-lookup"><span data-stu-id="f301e-104">Not all business functionality is fully supported in the public preview when scale unit workloads are used.</span></span> <span data-ttu-id="f301e-105">Ha a mérlegegységeket használja, ügyeljen arra, hogy csak azokat a folyamatokat használja, amelyeket ez a témakör kifejezetten támogatottként ír le.</span><span class="sxs-lookup"><span data-stu-id="f301e-105">If you're using scale units, be sure to use only those processes that this topic explicitly describes as supported.</span></span>

## <a name="what-are-warehouse-orders"></a><span data-ttu-id="f301e-106">Mi az a raktári rendelés?</span><span class="sxs-lookup"><span data-stu-id="f301e-106">What are warehouse orders?</span></span>

<span data-ttu-id="f301e-107">A *raktári rendelések* olyan rendelési típus, amely a központi és mérlegegységraktárak telepítésének támogatásához jött létre.</span><span class="sxs-lookup"><span data-stu-id="f301e-107">*Warehouse orders* are a type of order that was created to support hub and scale unit warehouse deployments.</span></span> <span data-ttu-id="f301e-108">Akkor kaphat készletet, amikor egy mérlegegységen futtat egy raktári terhelést.</span><span class="sxs-lookup"><span data-stu-id="f301e-108">They let you receive inventory when you're running a warehouse workload on a scale unit.</span></span> <span data-ttu-id="f301e-109">Jelenleg csak beszerzési rendelésekkel használatosak.</span><span class="sxs-lookup"><span data-stu-id="f301e-109">They are currently used only with purchase orders.</span></span>

<span data-ttu-id="f301e-110">A raktári rendelések a raktárkezelés feldolgozásában használatosak, például amikor a raktári alkalmazás segítségével regisztrálják a tényleges aktuális készletet a bejövő beszerzési rendelések feldolgozása során.</span><span class="sxs-lookup"><span data-stu-id="f301e-110">Warehouse orders are used as part of warehouse management processing, such as when the warehouse app is used to register physical on-hand inventory during processing of an inbound purchase order.</span></span> <span data-ttu-id="f301e-111">A raktári rendelések létrehozása a *raktárba való kiadás* folyamat részeként történik, amely a raktárkezelési folyamatok használatára engedélyezett mérlegegységraktárat megszabadó beszerzési rendelésekhez áll rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="f301e-111">Warehouse orders are created as part of the *Release to warehouse* process that is available for purchase orders that specify a scale unit warehouse and items that are enabled to use warehouse management processes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f301e-112">A raktári rendelések csak olyan telepítésekben érhetők el, amelyek [raktárkezelési terheléseket használnak a felhő- és peremhálózati egységekhez](cloud-edge-workload-warehousing.md).</span><span class="sxs-lookup"><span data-stu-id="f301e-112">Warehouse orders are available only in deployments that use [warehouse management workloads for cloud and edge scale units](cloud-edge-workload-warehousing.md).</span></span>

## <a name="create-a-warehouse-order"></a><span data-ttu-id="f301e-113">Raktári rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="f301e-113">Create a warehouse order</span></span>

<span data-ttu-id="f301e-114">Raktári rendelés létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="f301e-114">To create a warehouse order, follow these steps.</span></span>

1. <span data-ttu-id="f301e-115">Jelentkezzen be a központon futó Microsoft Dynamics 365 Supply Chain Management példányára.</span><span class="sxs-lookup"><span data-stu-id="f301e-115">Sign in to the instance of Microsoft Dynamics 365 Supply Chain Management that is running on the hub.</span></span> <span data-ttu-id="f301e-116">(Kezdeményeznie kell a *Kiadás raktárba* folyamatot, amíg be van jelentkezve a központba.)</span><span class="sxs-lookup"><span data-stu-id="f301e-116">(You must initiate the *Release to warehouse* process while you're signed in on the hub.)</span></span>
1. <span data-ttu-id="f301e-117">Menjen a **Beszerzés és forrás \> Beszerzési rendelés \> Összes beszerzési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="f301e-117">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="f301e-118">Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Műveletek** csoportjának **Kiadás raktárba** parancsát.</span><span class="sxs-lookup"><span data-stu-id="f301e-118">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="f301e-119">A kapcsolódó raktári rendelési sorok megtekintéséhez nyissa meg a megfelelő beszerzési rendelést, válasszon ki egy sort a **Beszerzési rendelés** sorai szakaszban, majd az eszköztáron válassza a következőt: **Raktár \> Raktári rendelés sorai**.</span><span class="sxs-lookup"><span data-stu-id="f301e-119">To view the related warehouse order lines, open the relevant purchase order, select a line in the **Purchase order lines** section, and then, on the toolbar, select **Warehouse \> Warehouse order lines**.</span></span> <span data-ttu-id="f301e-120">Az összes sor megtekintéséhez menjen a **Raktárkezelés \> Lekérdezések és jelentések \> Raktári rendelési sorokhoz**.</span><span class="sxs-lookup"><span data-stu-id="f301e-120">To view all the lines, go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**.</span></span>

## <a name="cancel-a-warehouse-order"></a><span data-ttu-id="f301e-121">Raktári rendelés visszavonása</span><span class="sxs-lookup"><span data-stu-id="f301e-121">Cancel a warehouse order</span></span>

<span data-ttu-id="f301e-122">A *Raktárba való kiadás* folyamat részeként a beszerzési rendelés készlettranzakciói raktári rendelésekhez kapcsolódnak, és a központ nem frissíti őket.</span><span class="sxs-lookup"><span data-stu-id="f301e-122">As part of the *Release to warehouse* process, purchase order inventory transactions are linked to warehouse orders and locked from being updated by the hub.</span></span> <span data-ttu-id="f301e-123">Ha véletlenül ad ki a raktárba, vagy valamilyen más oka van a raktári rendeléssorok létrehozásának sztornírozásának, kérheti a raktári rendeléssorok érvénytelenítését.</span><span class="sxs-lookup"><span data-stu-id="f301e-123">If you released to the warehouse by mistake, or if you have some other reason to reverse the creation of warehouse order lines, you can request to cancel warehouse order lines.</span></span>

<span data-ttu-id="f301e-124">Raktári rendelési sorok érvénytelenítéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="f301e-124">To cancel warehouse order lines, follow these steps.</span></span>

1. <span data-ttu-id="f301e-125">Jelentkezzen be a központon futó Supply Chain Management példányára.</span><span class="sxs-lookup"><span data-stu-id="f301e-125">Sign in to the Supply Chain Management instance that is running on the hub.</span></span>
1. <span data-ttu-id="f301e-126">Menjen a **Raktárkezelés \> Lekérdezések és jelentések \> Raktári rendelési sorokhoz**.</span><span class="sxs-lookup"><span data-stu-id="f301e-126">Go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**.</span></span>
1. <span data-ttu-id="f301e-127">Válassza ki a kívánt sort.</span><span class="sxs-lookup"><span data-stu-id="f301e-127">Select the relevant line.</span></span>
1. <span data-ttu-id="f301e-128">A munkaablakban válassza a **Raktári rendelési sorok visszavonása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f301e-128">On the Action Pane, select **Cancel warehouse order lines**.</span></span>

> [!NOTE]
> <span data-ttu-id="f301e-129">A sorok érvénytelenítésére vonatkozó kérést a rendszer megtagadja minden olyan sornál, amely már visszavonásra vár, vagy amely jelenleg aktív feldolgozás alatt áll egy olyan raktárban, amely a terhelést egy mérlegegységen futtatja.</span><span class="sxs-lookup"><span data-stu-id="f301e-129">The request to cancel lines will be denied for any lines that are already pending cancellation or that are actively being processed at a warehouse that is running its workload on a scale unit.</span></span>

## <a name="monitor-a-warehouse-order"></a><span data-ttu-id="f301e-130">Raktári rendelés monitorozása</span><span class="sxs-lookup"><span data-stu-id="f301e-130">Monitor a warehouse order</span></span>

<span data-ttu-id="f301e-131">A **Raktári rendelés sorai** nézetben nyomon követheti a bejövő bevételezés előrehaladását, ha áttekinti a **Bevételezésre megmaradt mennyiség** oszlopban szereplő értékeket.</span><span class="sxs-lookup"><span data-stu-id="f301e-131">In the **Warehouse order lines** view, you can monitor the progress of inbound receiving by reviewing the values in the **Quantity left to receive** column.</span></span> <span data-ttu-id="f301e-132">A raktári alkalmazás segítségével végzett munkához kapcsolódó részletek megtekintéséhez hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="f301e-132">To view details that are related to work that is done by using the warehouse app, follow one of these steps.</span></span>

- <span data-ttu-id="f301e-133">Menjen a **Raktárkezelés \> Lekérdezések és jelentések \> Raktári rendelési sorok** elemhez, és a szűrő segítségével keresse meg a keresett sorokat.</span><span class="sxs-lookup"><span data-stu-id="f301e-133">Go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**, and use the filter to find the lines that you're looking for.</span></span>
- <span data-ttu-id="f301e-134">Ugorjon a **Beszerzés és forrás \> Beszerzési rendelések \> Összes beszerzési rendelés** elemre, és nyissa meg a megfelelő beszerzési rendelést.</span><span class="sxs-lookup"><span data-stu-id="f301e-134">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**, and open the relevant purchase order.</span></span> <span data-ttu-id="f301e-135">A **Beszerzési rendelés sorai** szakaszban válasszon ki egy vagy több sort, majd az eszköztáron válassza ki a **Raktár \> Raktári bevételezések bejegyzései** elemet.</span><span class="sxs-lookup"><span data-stu-id="f301e-135">In the **Purchase order lines** section, select one or more lines, and then, on the toolbar, select **Warehouse \> Warehouse receipt entries**.</span></span>
