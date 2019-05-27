---
title: Egy cikk vagy egy alapanyag nyomon követése
description: Ez az eljárás bemutatja, hogy a cikk-követéssel, hogyan lehet azonosítani, hogy hol használtak vagy használnak egy adott cikket vagy nyersanyagot.
author: pjacobse
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTrackingDimTracing, InventTrackingDimTracingCriteria, InventTrackingItemIdLookup, InventBatchIdLookup, CustTable, SalesLine
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: pjacobse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 897a777b3f4ce05fe995aa98a72feb99d82837ef
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1561294"
---
# <a name="trace-an-item-or-raw-material"></a><span data-ttu-id="7c6b6-103">Egy cikk vagy egy alapanyag nyomon követése</span><span class="sxs-lookup"><span data-stu-id="7c6b6-103">Trace an item or raw material</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7c6b6-104">Ez az eljárás bemutatja, hogy a cikk-követéssel, hogyan lehet azonosítani, hogy hol használtak vagy használnak egy adott cikket vagy nyersanyagot.</span><span class="sxs-lookup"><span data-stu-id="7c6b6-104">This procedure demonstrates how to use item tracing to identify where items or raw materials have been used or are being used.</span></span> <span data-ttu-id="7c6b6-105">Ezzel az eljárással azonosíthat egy cikket, visszakövetheti a forráshoz, majd onnan előre követheti a termelésen és a késztermék értékesítésén keresztül.</span><span class="sxs-lookup"><span data-stu-id="7c6b6-105">With this procedure, you can identify an item, trace it back to the source, and then trace forward through the production and sale of the finished product.</span></span> <span data-ttu-id="7c6b6-106">A folyamat segítségével kivizsgálhatók az érintett ügyfelek és értékesítési rendelések, illetve még több minden más is.</span><span class="sxs-lookup"><span data-stu-id="7c6b6-106">The process can be used to investigate the customers impacted, the sales orders affected, and more.</span></span> <span data-ttu-id="7c6b6-107">Ez az eljárás az USP2 bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="7c6b6-107">This procedure uses demo data company USP2.</span></span>


## <a name="trace-an-item-backwards-using-a-known-batch-number"></a><span data-ttu-id="7c6b6-108">Egy cikk visszakövetése ismert kötegszám alapján</span><span class="sxs-lookup"><span data-stu-id="7c6b6-108">Trace an item backwards using a known batch number</span></span>
1. <span data-ttu-id="7c6b6-109">Ugrás a Készletgazdálkodás > Lekérdezések és jelentések > Nyomon követési dimenziók > Cikk-követés menüpontba.</span><span class="sxs-lookup"><span data-stu-id="7c6b6-109">Go to Inventory management > Inquiries and reports > Tracking dimensions > Item tracing.</span></span>
2. <span data-ttu-id="7c6b6-110">A Cikkszám mezőben válassza ki a P9100 értéket.</span><span class="sxs-lookup"><span data-stu-id="7c6b6-110">In the Item number field, select P9100.</span></span>
3. <span data-ttu-id="7c6b6-111">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="7c6b6-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="7c6b6-112">Az Előrefelé vagy visszafelé mezőben válassza a „Visszafelé” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7c6b6-112">In the Forward or backward field, select 'Backward'.</span></span>
5. <span data-ttu-id="7c6b6-113">A Kötegszám mezőben válassza a „mint-12-344-01” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7c6b6-113">In the Batch number field, select as-12-344-01.</span></span>
6. <span data-ttu-id="7c6b6-114">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="7c6b6-114">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="7c6b6-115">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="7c6b6-115">Click OK.</span></span>

## <a name="identify-an-item-trace-it-forward-and-make-an-analysis"></a><span data-ttu-id="7c6b6-116">Egy cikk azonosítása, előre irányuló követése és az elemzés végrehajtása</span><span class="sxs-lookup"><span data-stu-id="7c6b6-116">Identify an item, trace it forward, and make an analysis</span></span>
    * <span data-ttu-id="7c6b6-117">A fastruktúra felső csomópontja a kiválasztott cikk és köteg aktuális készletmennyiségét jelöli.</span><span class="sxs-lookup"><span data-stu-id="7c6b6-117">The top node of the tree represents the on hand quantity of the selected item and batch.</span></span> <span data-ttu-id="7c6b6-118">Ki kell bontani a fastruktúra csomóit annak érdekében, hogy megtalálja azt a cikket, amelyen az előre irányuló követést végre kell hajtani.</span><span class="sxs-lookup"><span data-stu-id="7c6b6-118">You need to expand the nodes of the tree to find the item that the forward trace should be executed on.</span></span>   
1. <span data-ttu-id="7c6b6-119">Bontsa ki a fastruktúrában „az alább leírt csomópontot, és válassza ki a legutóbbi csomópontot”.</span><span class="sxs-lookup"><span data-stu-id="7c6b6-119">In the tree, expand 'the nodes described below, and then select the last node'.</span></span>
    * <span data-ttu-id="7c6b6-120">Bontsa ki: „P9100 1 / 10 / mint-12-344-01 ● 2 hordó ● 7,00 gallon \P9100 ● Kitárolva ● 000072 Értékesítési rendelés ● 2015.12.22. ● -1 hordó ● -4,00 gallon ● Hely = 1, Raktár = 10, Kötegszám = -12-344-01 \P9100 ● B-000050 Termelés● 2015.09.12. ● 7 hordó ● 27,00 gallon ● Hely = 1, Raktár = 10, Kötegszám = -12-344-01 ● Társtermékek: P9101” és válassza ki azt a csomópontot.</span><span class="sxs-lookup"><span data-stu-id="7c6b6-120">Expand: 'P9100 / 1 / 10 / as-12-344-01 ● 2 keg ● 7.00 gal  \P9100 ● Picked ● Sales order 000072 ● 12/22/2015  ● -1 keg ● -4.00 gal ● Site=1, Warehouse=10, Batch number=as-12-344-01  \P9100 ● Production B-000050 ● 12/9/2015● 7 keg ● 27.00 gal ● Site=1,Warehouse=10,Batch number=as-12-344-01 ● Co-products: P9101' and then select that node.</span></span>     
2. <span data-ttu-id="7c6b6-121">Bontsa ki a fastruktúrában „az alább leírt csomópontot, és válassza ki ezt a csomópontot”.</span><span class="sxs-lookup"><span data-stu-id="7c6b6-121">In the tree, expand 'the node described below and then select that node'.</span></span>
    * <span data-ttu-id="7c6b6-122">Kezdve az imént kijelölt csomóponttal bontsa ki a „M9103 ● B-000050 Termelési sor ● 2015.09.12. ●-160,00 kg ● Méret = 70, Szín = OK, Hely= 1, Raktár = 10, Kötegszám = App01” és válassza ki azt a csomópontot.</span><span class="sxs-lookup"><span data-stu-id="7c6b6-122">Starting from the node that you’ve just selected,  expand 'M9103 ● Production line B-000050 ● 12/9/2015  ● -160.00 lb ● Size=70, Color=OK, Site=1, Warehouse=10, Batch number=App01' and then select that node.</span></span>  
3. <span data-ttu-id="7c6b6-123">Kattintson a Nyomkövetés csomópontból lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7c6b6-123">Click Trace from node.</span></span>
4. <span data-ttu-id="7c6b6-124">Kattintson az Előrefelé lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7c6b6-124">Click Forward.</span></span>
5. <span data-ttu-id="7c6b6-125">A Művelet panelen kattintson a Nyomkövetés elemre.</span><span class="sxs-lookup"><span data-stu-id="7c6b6-125">On the Action Pane, click Tracing.</span></span>
    * <span data-ttu-id="7c6b6-126">Számos nyomkövetési beállítás megtalálható, amelyek tájékoztatást nyújtanak a nyomkövetési cikk által érintett vevőkkel, és a kiszállított és a ki nem szállított cikkhez kapcsolódó értékesítési rendelésekkel kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="7c6b6-126">There are several tracing options which provide information about the customers impacted by the item that you’re tracing, and the sales orders related to the item which have and haven’t been shipped.</span></span>   
6. <span data-ttu-id="7c6b6-127">Kattintson az Ügyfelek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7c6b6-127">Click Customers.</span></span>
7. <span data-ttu-id="7c6b6-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7c6b6-128">Close the page.</span></span>
8. <span data-ttu-id="7c6b6-129">A Művelet panelen kattintson a Nyomkövetés elemre.</span><span class="sxs-lookup"><span data-stu-id="7c6b6-129">On the Action Pane, click Tracing.</span></span>
9. <span data-ttu-id="7c6b6-130">Kattintson a Kiszállított értékesítési rendelések lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7c6b6-130">Click Shipped sales orders.</span></span>
10. <span data-ttu-id="7c6b6-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7c6b6-131">Close the page.</span></span>

