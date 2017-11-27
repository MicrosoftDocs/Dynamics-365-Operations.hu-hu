---
title: "Szállítási ütemezések"
description: "A szállítási ütemezések lehetővé teszik a rendeléssor mennyiségének nyomon követését, amikor több szállítást használ egyetlen értékesítési rendeléshez, értékesítési ajánlathoz vagy beszerzési rendeléshez."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchDeliverySchedule, SalesDeliverySchedule, SalesQuotationDeliverySchedule
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 213984
ms.assetid: 44cac104-c36c-4371-a992-9178b3fd65e9
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ceb568cc223a631f704caf2417f1a3bd56b56288
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="delivery-schedules"></a><span data-ttu-id="3aeba-103">Szállítási ütemezések</span><span class="sxs-lookup"><span data-stu-id="3aeba-103">Delivery schedules</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="3aeba-104">A szállítási ütemezések lehetővé teszik a rendeléssor mennyiségének nyomon követését, amikor több szállítást használ egyetlen értékesítési rendeléshez, értékesítési ajánlathoz vagy beszerzési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="3aeba-104">Delivery schedules allow you to track order line quantity when you are using multiple deliveries for a single sales order, sales quotation, or purchase order.</span></span>

<span data-ttu-id="3aeba-105">A szállítási ütemezés akkor használatos, ha egy rendeléshez vagy ajánlati sorhoz tartozó teljes mennyiséget több részletben kell szállítani.</span><span class="sxs-lookup"><span data-stu-id="3aeba-105">Use a delivery schedule when the total quantity on an order or quotation line must be delivered in multiple shipments.</span></span> <span data-ttu-id="3aeba-106">Az egyes szállítmányokat szállítási sorok jelölik.</span><span class="sxs-lookup"><span data-stu-id="3aeba-106">Individual shipments are represented by delivery lines.</span></span> <span data-ttu-id="3aeba-107">Két vagy több szállítási sor alkot egy szállítási ütemezést.</span><span class="sxs-lookup"><span data-stu-id="3aeba-107">Two or more delivery lines make up one delivery schedule.</span></span> <span data-ttu-id="3aeba-108">A szállítási sorok különböző szállítási dátumokkal, mennyiségekkel, szállítási módokkal és tárolási dimenziókkal rendelkezhetnek, például hely és raktár.</span><span class="sxs-lookup"><span data-stu-id="3aeba-108">The delivery lines can have different delivery dates, quantities, modes of delivery, and storage dimensions, such as site and warehouse.</span></span>  

<span data-ttu-id="3aeba-109">**Példa szállítási ütemezésre**</span><span class="sxs-lookup"><span data-stu-id="3aeba-109">**Example of a delivery schedule**</span></span>

|                                   |                                          |
|-----------------------------------|------------------------------------------|
| <span data-ttu-id="3aeba-110">Teljes rendelés (eredeti rendelési sor)</span><span class="sxs-lookup"><span data-stu-id="3aeba-110">Total order (original order line)</span></span> | <span data-ttu-id="3aeba-111">600 szék</span><span class="sxs-lookup"><span data-stu-id="3aeba-111">600 chairs</span></span>                               |
| <span data-ttu-id="3aeba-112">Kért kézbesítési ütemezés</span><span class="sxs-lookup"><span data-stu-id="3aeba-112">Requested delivery schedule</span></span>       | <span data-ttu-id="3aeba-113">Havonta 100 szék</span><span class="sxs-lookup"><span data-stu-id="3aeba-113">100 chairs per month</span></span>                     |
| <span data-ttu-id="3aeba-114">Kért kézbesítési időkeret</span><span class="sxs-lookup"><span data-stu-id="3aeba-114">Requested time frame for delivery</span></span> | <span data-ttu-id="3aeba-115">6 hónapon keresztül, minden hónap első napján</span><span class="sxs-lookup"><span data-stu-id="3aeba-115">6 months, on the first day of each month</span></span> |

<span data-ttu-id="3aeba-116">Ebben az esetben a vevő a 600 szék kiszállítását 100 darabos kötegekben kérte, 6 hónap alatt</span><span class="sxs-lookup"><span data-stu-id="3aeba-116">In this scenario, the customer requests delivery of 600 chairs in batches of 100 chairs over a period of six months.</span></span> <span data-ttu-id="3aeba-117">A szállítási követelmények nyomon követéséhez szállítási ütemezést kell létrehozni.</span><span class="sxs-lookup"><span data-stu-id="3aeba-117">To keep track of the delivery requirements, you create a delivery schedule.</span></span> <span data-ttu-id="3aeba-118">A szállítási ütemezés lapon hat külön szállítás sort kell létrehozni.</span><span class="sxs-lookup"><span data-stu-id="3aeba-118">On the delivery schedule page, you create six separate delivery lines.</span></span> <span data-ttu-id="3aeba-119">Minden egyes kézbesítési sor 100 széket tartalmaz, és jelzi az adott 100 szék szállítási dátumát.</span><span class="sxs-lookup"><span data-stu-id="3aeba-119">Each delivery line contains 100 chairs and indicates the delivery date for those 100 chairs.</span></span> <span data-ttu-id="3aeba-120">Ebben az esetben minden sor hat egymást követő hónapig minden hónap elsején lesz elindítva.</span><span class="sxs-lookup"><span data-stu-id="3aeba-120">In this case, each line is offset on the first of the month for six consecutive months.</span></span>  

<span data-ttu-id="3aeba-121">A szállítási ütemezés létrehozásakor az eredeti rendelési sor típusa automatikusan a **Rendeléssor több szállítással** lehetőségre módosul.</span><span class="sxs-lookup"><span data-stu-id="3aeba-121">When you create a delivery schedule, the type of the original order line is automatically changed to **Order line with multiple deliveries**.</span></span> <span data-ttu-id="3aeba-122">Egy ilyen típusú sorra a rendszer kereskedelmi sorként hivatkozik és egy ikon jelzi.</span><span class="sxs-lookup"><span data-stu-id="3aeba-122">A line of this type is referred to as a commercial line and is marked by an icon.</span></span> <span data-ttu-id="3aeba-123">A kézbesítési sort egy másik ikon jelzi.</span><span class="sxs-lookup"><span data-stu-id="3aeba-123">The delivery line is marked by a different icon.</span></span> <span data-ttu-id="3aeba-124">Ha módosítja egy kézbesítési sorban mennyiségét, a kereskedelmi sor a szállítási ütemezés teljes mennyiségére frissül.</span><span class="sxs-lookup"><span data-stu-id="3aeba-124">If you change a quantity on a delivery line, the commercial line is updated to the total quantity of the delivery schedule.</span></span> <span data-ttu-id="3aeba-125">Ha egy kereskedelmi megállapodás egy teljes engedményt határozott meg a rendeléshez, a szállítási ütemezés biztosítja, hogy a rendelés jogosult legyen a teljes rendelési engedményre, akkor is, ha a rendelés több kiszállításra oszlik.</span><span class="sxs-lookup"><span data-stu-id="3aeba-125">If a trade agreement has defined a total discount for the order, the delivery schedule ensures that your order is eligible for the total order discount, even when the order is split into separate deliveries.</span></span>  

<span data-ttu-id="3aeba-126">A szállítási ütemezéssel rendelkező rendeléseket a rendszer a szállítási sorok szerint dolgozza fel.</span><span class="sxs-lookup"><span data-stu-id="3aeba-126">Orders that have a delivery schedule are processed against the delivery lines.</span></span> <span data-ttu-id="3aeba-127">A feldolgozás magában foglalja a csomagjegyzékek, termékbevételezések és a számlázás feladását.</span><span class="sxs-lookup"><span data-stu-id="3aeba-127">Processing includes the posting of packing slips, product receipts, and invoicing.</span></span>  

<span data-ttu-id="3aeba-128">A szállítási ütemezéssel rendelkező rendelések és árajánlatok nyomtatott anyagai csak a szállítási sorokat tartalmazzák.</span><span class="sxs-lookup"><span data-stu-id="3aeba-128">Document printouts of orders and quotations that have a delivery schedule show only the delivery lines.</span></span> <span data-ttu-id="3aeba-129">Nem mutatják az eredeti sorokat (kereskedelmi sorokat).</span><span class="sxs-lookup"><span data-stu-id="3aeba-129">They don't show the original lines (commercial lines).</span></span> <span data-ttu-id="3aeba-130">**Megjegyzés:** Ezen kívül csak a szállítási sorok jelennek meg a rendszerben a műveletek végrehajtása során:</span><span class="sxs-lookup"><span data-stu-id="3aeba-130">**Note:** In addition, only the delivery lines are shown when you perform these actions:</span></span>

-   <span data-ttu-id="3aeba-131">Feladás</span><span class="sxs-lookup"><span data-stu-id="3aeba-131">Post</span></span>
-   <span data-ttu-id="3aeba-132">Oldalak másolása</span><span class="sxs-lookup"><span data-stu-id="3aeba-132">Copy pages</span></span>
-   <span data-ttu-id="3aeba-133">Tallózással keresse meg a listalapokat és jelentéseket</span><span class="sxs-lookup"><span data-stu-id="3aeba-133">Browse list pages and reports</span></span>

<span data-ttu-id="3aeba-134">Ha megerősíti az értékesítési ajánlatokat, az ebből származó értékesítési jelentések az egész szállítási ütemezést mutatják, még a több kiszállításból álló rendelési sorokat is.</span><span class="sxs-lookup"><span data-stu-id="3aeba-134">When you confirm sales quotations, the resulting sales orders show the whole delivery schedule, even the order lines that have multiple deliveries.</span></span> <span data-ttu-id="3aeba-135">Ezenkívül a teljes szállítási ütemezés megjelenik az összes fő lapon, például értékesítési rendelések, értékesítési ajánlatok és beszerzési rendelések lapokon.</span><span class="sxs-lookup"><span data-stu-id="3aeba-135">In addition, the whole delivery schedule is shown on all the major pages, such as sales orders, sales quotations, and purchase orders.</span></span>




