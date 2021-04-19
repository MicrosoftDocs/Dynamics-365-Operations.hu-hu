---
title: Raktérkezelés rendelései felhőalapú és peremhálózat-lépték szerinti egységekhez
description: Ez a témakör a raktári rendelési funkcióval kapcsolatban tartalmaz tájékoztatást, amely a raktári mérlegegység terhelésének részeként használatos.
author: perlynne
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: f2401102ab44f5c24f5cd6f545f30438db0a36cf
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836686"
---
# <a name="warehouse-orders-for-cloud-and-edge-scale-units"></a><span data-ttu-id="1d080-103">Raktérkezelés rendelései felhőalapú és peremhálózat-lépték szerinti egységekhez</span><span class="sxs-lookup"><span data-stu-id="1d080-103">Warehouse orders for cloud and edge scale units</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> <span data-ttu-id="1d080-104">Nem minden üzleti funkció teljes mértékben támogatott a nyilvános előzetes verzióban, ha a mérlegegység munkaterheléseket használja.</span><span class="sxs-lookup"><span data-stu-id="1d080-104">Not all business functionality is fully supported in the public preview when scale unit workloads are used.</span></span> <span data-ttu-id="1d080-105">Ha a mérlegegységeket használja, ügyeljen arra, hogy csak azokat a folyamatokat használja, amelyeket ez a témakör kifejezetten támogatottként ír le.</span><span class="sxs-lookup"><span data-stu-id="1d080-105">If you're using scale units, be sure to use only those processes that this topic explicitly describes as supported.</span></span>

## <a name="what-are-warehouse-orders"></a><span data-ttu-id="1d080-106">Mi az a raktári rendelés?</span><span class="sxs-lookup"><span data-stu-id="1d080-106">What are warehouse orders?</span></span>

<span data-ttu-id="1d080-107">A *raktári rendelések* olyan rendelési típus, amely a központi és mérlegegységraktárak telepítésének támogatásához jött létre.</span><span class="sxs-lookup"><span data-stu-id="1d080-107">*Warehouse orders* are a type of order that was created to support hub and scale unit warehouse deployments.</span></span> <span data-ttu-id="1d080-108">Akkor kaphat készletet, amikor egy mérlegegységen futtat egy raktári terhelést.</span><span class="sxs-lookup"><span data-stu-id="1d080-108">They let you receive inventory when you're running a warehouse workload on a scale unit.</span></span> <span data-ttu-id="1d080-109">Jelenleg csak beszerzési rendelésekkel használatosak.</span><span class="sxs-lookup"><span data-stu-id="1d080-109">They are currently used only with purchase orders.</span></span>

<span data-ttu-id="1d080-110">A raktári rendelések a raktárkezelés feldolgozásában használatosak, például amikor a Raktárkezelés mobilalkalmazás segítségével regisztrálják a tényleges aktuális készletet a bejövő beszerzési rendelések feldolgozása során.</span><span class="sxs-lookup"><span data-stu-id="1d080-110">Warehouse orders are used as part of warehouse management processing, such as when the Warehouse Management mobile app is used to register physical on-hand inventory during processing of an inbound purchase order.</span></span> <span data-ttu-id="1d080-111">A raktári rendelések létrehozása a *raktárba való kiadás* folyamat részeként történik, amely a raktárkezelési folyamatok használatára engedélyezett mérlegegységraktárat megszabadó beszerzési rendelésekhez áll rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="1d080-111">Warehouse orders are created as part of the *Release to warehouse* process that is available for purchase orders that specify a scale unit warehouse and items that are enabled to use warehouse management processes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d080-112">A raktári rendelések csak olyan telepítésekben érhetők el, amelyek [raktárkezelési terheléseket használnak a felhő- és peremhálózati egységekhez](cloud-edge-workload-warehousing.md).</span><span class="sxs-lookup"><span data-stu-id="1d080-112">Warehouse orders are available only in deployments that use [warehouse management workloads for cloud and edge scale units](cloud-edge-workload-warehousing.md).</span></span>

## <a name="create-a-warehouse-order"></a><span data-ttu-id="1d080-113">Raktári rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="1d080-113">Create a warehouse order</span></span>

<span data-ttu-id="1d080-114">Raktári rendelés létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1d080-114">To create a warehouse order, follow these steps.</span></span>

1. <span data-ttu-id="1d080-115">Jelentkezzen be a központon futó Microsoft Dynamics 365 Supply Chain Management példányára.</span><span class="sxs-lookup"><span data-stu-id="1d080-115">Sign in to the instance of Microsoft Dynamics 365 Supply Chain Management that is running on the hub.</span></span> <span data-ttu-id="1d080-116">(Kezdeményeznie kell a *Kiadás raktárba* folyamatot, amíg be van jelentkezve a központba.)</span><span class="sxs-lookup"><span data-stu-id="1d080-116">(You must initiate the *Release to warehouse* process while you're signed in on the hub.)</span></span>
1. <span data-ttu-id="1d080-117">Menjen a **Beszerzés és forrás \> Beszerzési rendelés \> Összes beszerzési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="1d080-117">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="1d080-118">Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Műveletek** csoportjának **Kiadás raktárba** parancsát.</span><span class="sxs-lookup"><span data-stu-id="1d080-118">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="1d080-119">A kapcsolódó raktári rendelési sorok megtekintéséhez nyissa meg a megfelelő beszerzési rendelést, válasszon ki egy sort a **Beszerzési rendelés** sorai szakaszban, majd az eszköztáron válassza a következőt: **Raktár \> Raktári rendelés sorai**.</span><span class="sxs-lookup"><span data-stu-id="1d080-119">To view the related warehouse order lines, open the relevant purchase order, select a line in the **Purchase order lines** section, and then, on the toolbar, select **Warehouse \> Warehouse order lines**.</span></span> <span data-ttu-id="1d080-120">Az összes sor megtekintéséhez menjen a **Raktárkezelés \> Lekérdezések és jelentések \> Raktári rendelési sorokhoz**.</span><span class="sxs-lookup"><span data-stu-id="1d080-120">To view all the lines, go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**.</span></span>

<span data-ttu-id="1d080-121">A *Kiadás raktárba* folyamatot kötegelt feladatból is elindíthatja, ha a **Raktárkezelés > Kiadás raktárba > Beszerzési rendelések automatikus kiadása** helyre lép.</span><span class="sxs-lookup"><span data-stu-id="1d080-121">You can also trigger the *Release to warehouse* process from a batch job by going to **Warehouse management > Release to warehouse > Automatic release of purchase orders**.</span></span> <span data-ttu-id="1d080-122">A kötegelt feladat beállításakor lekérdezés alapján meghatározott beszerzésirendelés-sorokat választhat ki.</span><span class="sxs-lookup"><span data-stu-id="1d080-122">When setting up the batch job, you can select specific purchase order lines based on a query.</span></span> <span data-ttu-id="1d080-123">Jellemző helyzet lehet egy ismétlődő kötegelt feladat, amely kiadja a következő napon várható összes visszaigazolt beszerzésirendelés-sort.</span><span class="sxs-lookup"><span data-stu-id="1d080-123">A typical scenario would be to set up a recurrent batch job that releases all the confirmed purchase order lines expected to arrive the next day.</span></span>

## <a name="cancel-a-warehouse-order"></a><span data-ttu-id="1d080-124">Raktári rendelés visszavonása</span><span class="sxs-lookup"><span data-stu-id="1d080-124">Cancel a warehouse order</span></span>

<span data-ttu-id="1d080-125">A *Raktárba való kiadás* folyamat részeként a beszerzési rendelés készlettranzakciói raktári rendelésekhez kapcsolódnak, és a központ nem frissíti őket.</span><span class="sxs-lookup"><span data-stu-id="1d080-125">As part of the *Release to warehouse* process, purchase order inventory transactions are linked to warehouse orders and locked from being updated by the hub.</span></span> <span data-ttu-id="1d080-126">Ha véletlenül ad ki a raktárba, vagy valamilyen más oka van a raktári rendeléssorok létrehozásának sztornírozásának, kérheti a raktári rendeléssorok érvénytelenítését.</span><span class="sxs-lookup"><span data-stu-id="1d080-126">If you released to the warehouse by mistake, or if you have some other reason to reverse the creation of warehouse order lines, you can request to cancel warehouse order lines.</span></span>

<span data-ttu-id="1d080-127">Raktári rendelési sorok érvénytelenítéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1d080-127">To cancel warehouse order lines, follow these steps.</span></span>

1. <span data-ttu-id="1d080-128">Jelentkezzen be a központon futó Supply Chain Management példányára.</span><span class="sxs-lookup"><span data-stu-id="1d080-128">Sign in to the Supply Chain Management instance that is running on the hub.</span></span>
1. <span data-ttu-id="1d080-129">Menjen a **Raktárkezelés \> Lekérdezések és jelentések \> Raktári rendelési sorokhoz**.</span><span class="sxs-lookup"><span data-stu-id="1d080-129">Go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**.</span></span>
1. <span data-ttu-id="1d080-130">Válassza ki a kívánt sort.</span><span class="sxs-lookup"><span data-stu-id="1d080-130">Select the relevant line.</span></span>
1. <span data-ttu-id="1d080-131">A munkaablakban válassza a **Raktári rendelési sorok visszavonása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1d080-131">On the Action Pane, select **Cancel warehouse order lines**.</span></span>

> [!NOTE]
> <span data-ttu-id="1d080-132">A sorok érvénytelenítésére vonatkozó kérést a rendszer megtagadja minden olyan sornál, amely már visszavonásra vár, vagy amely jelenleg aktív feldolgozás alatt áll egy olyan raktárban, amely a terhelést egy mérlegegységen futtatja.</span><span class="sxs-lookup"><span data-stu-id="1d080-132">The request to cancel lines will be denied for any lines that are already pending cancellation or that are actively being processed at a warehouse that is running its workload on a scale unit.</span></span>

## <a name="monitor-a-warehouse-order"></a><span data-ttu-id="1d080-133">Raktári rendelés monitorozása</span><span class="sxs-lookup"><span data-stu-id="1d080-133">Monitor a warehouse order</span></span>

<span data-ttu-id="1d080-134">A **Raktári rendelés sorai** nézetben nyomon követheti a bejövő bevételezés előrehaladását, ha áttekinti a **Bevételezésre megmaradt mennyiség** oszlopban szereplő értékeket.</span><span class="sxs-lookup"><span data-stu-id="1d080-134">In the **Warehouse order lines** view, you can monitor the progress of inbound receiving by reviewing the values in the **Quantity left to receive** column.</span></span> <span data-ttu-id="1d080-135">A Raktárkezelés mobilalkalmazás segítségével végzett munkához kapcsolódó részletek megtekintéséhez hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1d080-135">To view details that are related to work that is done by using the Warehouse Management mobile app, follow one of these steps.</span></span>

- <span data-ttu-id="1d080-136">Menjen a **Raktárkezelés \> Lekérdezések és jelentések \> Raktári rendelési sorok** elemhez, és a szűrő segítségével keresse meg a keresett sorokat.</span><span class="sxs-lookup"><span data-stu-id="1d080-136">Go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**, and use the filter to find the lines that you're looking for.</span></span>
- <span data-ttu-id="1d080-137">Ugorjon a **Beszerzés és forrás \> Beszerzési rendelések \> Összes beszerzési rendelés** elemre, és nyissa meg a megfelelő beszerzési rendelést.</span><span class="sxs-lookup"><span data-stu-id="1d080-137">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**, and open the relevant purchase order.</span></span> <span data-ttu-id="1d080-138">A **Beszerzési rendelés sorai** szakaszban válasszon ki egy vagy több sort, majd az eszköztáron válassza ki a **Raktár \> Raktári bevételezések bejegyzései** elemet.</span><span class="sxs-lookup"><span data-stu-id="1d080-138">In the **Purchase order lines** section, select one or more lines, and then, on the toolbar, select **Warehouse \> Warehouse receipt entries**.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]