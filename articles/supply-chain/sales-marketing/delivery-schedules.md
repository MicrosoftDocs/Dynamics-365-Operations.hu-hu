---
title: Szállítási ütemezések
description: A szállítási ütemezések lehetővé teszik a rendeléssor mennyiségének nyomon követését, amikor több szállítást használ egyetlen értékesítési rendeléshez, értékesítési ajánlathoz vagy beszerzési rendeléshez.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchDeliverySchedule, SalesDeliverySchedule, SalesQuotationDeliverySchedule, SalesQuotationDeliverySchedule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 213984
ms.assetid: 44cac104-c36c-4371-a992-9178b3fd65e9
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3dbd66d499b5d5f9f8ef21c0ce3752031a5f4672
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193782"
---
# <a name="delivery-schedules"></a><span data-ttu-id="75d7f-103">Szállítási ütemezések</span><span class="sxs-lookup"><span data-stu-id="75d7f-103">Delivery schedules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="75d7f-104">A szállítási ütemezések lehetővé teszik a rendeléssor mennyiségének nyomon követését, amikor több szállítást használ egyetlen értékesítési rendeléshez, értékesítési ajánlathoz vagy beszerzési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="75d7f-104">Delivery schedules allow you to track order line quantity when you are using multiple deliveries for a single sales order, sales quotation, or purchase order.</span></span>

<span data-ttu-id="75d7f-105">A szállítási ütemezés akkor használatos, ha egy rendeléshez vagy ajánlati sorhoz tartozó teljes mennyiséget több részletben kell szállítani.</span><span class="sxs-lookup"><span data-stu-id="75d7f-105">Use a delivery schedule when the total quantity on an order or quotation line must be delivered in multiple shipments.</span></span> <span data-ttu-id="75d7f-106">Az egyes szállítmányokat szállítási sorok jelölik.</span><span class="sxs-lookup"><span data-stu-id="75d7f-106">Individual shipments are represented by delivery lines.</span></span> <span data-ttu-id="75d7f-107">Két vagy több szállítási sor alkot egy szállítási ütemezést.</span><span class="sxs-lookup"><span data-stu-id="75d7f-107">Two or more delivery lines make up one delivery schedule.</span></span> <span data-ttu-id="75d7f-108">A szállítási sorok különböző szállítási dátumokkal, mennyiségekkel, szállítási módokkal és tárolási dimenziókkal rendelkezhetnek, például webhely és raktár.</span><span class="sxs-lookup"><span data-stu-id="75d7f-108">The delivery lines can have different delivery dates, quantities, modes of delivery, and storage dimensions, such as site and warehouse.</span></span>  

<span data-ttu-id="75d7f-109">**Példa szállítási ütemezésre**</span><span class="sxs-lookup"><span data-stu-id="75d7f-109">**Example of a delivery schedule**</span></span>

| <span data-ttu-id="75d7f-110">Tétel</span><span class="sxs-lookup"><span data-stu-id="75d7f-110">Item</span></span>                              | <span data-ttu-id="75d7f-111">Érték</span><span class="sxs-lookup"><span data-stu-id="75d7f-111">Value</span></span>                                    |
|-----------------------------------|------------------------------------------|
| <span data-ttu-id="75d7f-112">Teljes rendelés (eredeti rendelési sor)</span><span class="sxs-lookup"><span data-stu-id="75d7f-112">Total order (original order line)</span></span> | <span data-ttu-id="75d7f-113">600 szék</span><span class="sxs-lookup"><span data-stu-id="75d7f-113">600 chairs</span></span>                               |
| <span data-ttu-id="75d7f-114">Kért kézbesítési ütemezés</span><span class="sxs-lookup"><span data-stu-id="75d7f-114">Requested delivery schedule</span></span>       | <span data-ttu-id="75d7f-115">Havonta 100 szék</span><span class="sxs-lookup"><span data-stu-id="75d7f-115">100 chairs per month</span></span>                     |
| <span data-ttu-id="75d7f-116">Kért kézbesítési időkeret</span><span class="sxs-lookup"><span data-stu-id="75d7f-116">Requested time frame for delivery</span></span> | <span data-ttu-id="75d7f-117">6 hónapon keresztül, minden hónap első napján</span><span class="sxs-lookup"><span data-stu-id="75d7f-117">6 months, on the first day of each month</span></span> |

<span data-ttu-id="75d7f-118">Ebben az esetben a vevő a 600 szék kiszállítását 100 darabos kötegekben kérte, 6 hónap alatt</span><span class="sxs-lookup"><span data-stu-id="75d7f-118">In this scenario, the customer requests delivery of 600 chairs in batches of 100 chairs over a period of six months.</span></span> <span data-ttu-id="75d7f-119">A szállítási követelmények nyomon követéséhez szállítási ütemezést kell létrehozni.</span><span class="sxs-lookup"><span data-stu-id="75d7f-119">To keep track of the delivery requirements, you create a delivery schedule.</span></span> <span data-ttu-id="75d7f-120">A szállítási ütemezés lapon hat külön szállítás sort kell létrehozni.</span><span class="sxs-lookup"><span data-stu-id="75d7f-120">On the delivery schedule page, you create six separate delivery lines.</span></span> <span data-ttu-id="75d7f-121">Minden egyes kézbesítési sor 100 széket tartalmaz, és jelzi az adott 100 szék szállítási dátumát.</span><span class="sxs-lookup"><span data-stu-id="75d7f-121">Each delivery line contains 100 chairs and indicates the delivery date for those 100 chairs.</span></span> <span data-ttu-id="75d7f-122">Ebben az esetben minden sor hat egymást követő hónapig minden hónap elsején lesz elindítva.</span><span class="sxs-lookup"><span data-stu-id="75d7f-122">In this case, each line is offset on the first of the month for six consecutive months.</span></span>  

<span data-ttu-id="75d7f-123">A szállítási ütemezés létrehozásakor az eredeti rendelési sor típusa automatikusan a **Rendeléssor több szállítással** lehetőségre módosul.</span><span class="sxs-lookup"><span data-stu-id="75d7f-123">When you create a delivery schedule, the type of the original order line is automatically changed to **Order line with multiple deliveries**.</span></span> <span data-ttu-id="75d7f-124">Egy ilyen típusú sorra a rendszer kereskedelmi sorként hivatkozik és egy ikon jelzi.</span><span class="sxs-lookup"><span data-stu-id="75d7f-124">A line of this type is referred to as a commercial line and is marked by an icon.</span></span> <span data-ttu-id="75d7f-125">A kézbesítési sort egy másik ikon jelzi.</span><span class="sxs-lookup"><span data-stu-id="75d7f-125">The delivery line is marked by a different icon.</span></span> <span data-ttu-id="75d7f-126">Ha módosítja egy kézbesítési sorban mennyiségét, a kereskedelmi sor a szállítási ütemezés teljes mennyiségére frissül.</span><span class="sxs-lookup"><span data-stu-id="75d7f-126">If you change a quantity on a delivery line, the commercial line is updated to the total quantity of the delivery schedule.</span></span> <span data-ttu-id="75d7f-127">Ha egy kereskedelmi megállapodás egy teljes engedményt határozott meg a rendeléshez, a szállítási ütemezés biztosítja, hogy a rendelés jogosult legyen a teljes rendelési engedményre, akkor is, ha a rendelés több kiszállításra oszlik.</span><span class="sxs-lookup"><span data-stu-id="75d7f-127">If a trade agreement has defined a total discount for the order, the delivery schedule ensures that your order is eligible for the total order discount, even when the order is split into separate deliveries.</span></span>  

<span data-ttu-id="75d7f-128">A szállítási ütemezéssel rendelkező rendeléseket a rendszer a szállítási sorok szerint dolgozza fel.</span><span class="sxs-lookup"><span data-stu-id="75d7f-128">Orders that have a delivery schedule are processed against the delivery lines.</span></span> <span data-ttu-id="75d7f-129">A feldolgozás magában foglalja a csomagjegyzékek, termékbevételezések és a számlázás feladását.</span><span class="sxs-lookup"><span data-stu-id="75d7f-129">Processing includes the posting of packing slips, product receipts, and invoicing.</span></span>  

<span data-ttu-id="75d7f-130">A szállítási ütemezéssel rendelkező rendelések és árajánlatok nyomtatott anyagai csak a szállítási sorokat tartalmazzák.</span><span class="sxs-lookup"><span data-stu-id="75d7f-130">Document printouts of orders and quotations that have a delivery schedule show only the delivery lines.</span></span> <span data-ttu-id="75d7f-131">Nem mutatják az eredeti sorokat (kereskedelmi sorokat).</span><span class="sxs-lookup"><span data-stu-id="75d7f-131">They don't show the original lines (commercial lines).</span></span> <span data-ttu-id="75d7f-132">**Megjegyzés:** Ezen kívül csak a szállítási sorok jelennek meg a rendszerben a műveletek végrehajtása során:</span><span class="sxs-lookup"><span data-stu-id="75d7f-132">**Note:** In addition, only the delivery lines are shown when you perform these actions:</span></span>

-   <span data-ttu-id="75d7f-133">Feladás</span><span class="sxs-lookup"><span data-stu-id="75d7f-133">Post</span></span>
-   <span data-ttu-id="75d7f-134">Oldalak másolása</span><span class="sxs-lookup"><span data-stu-id="75d7f-134">Copy pages</span></span>
-   <span data-ttu-id="75d7f-135">Tallózással keresse meg a listalapokat és jelentéseket</span><span class="sxs-lookup"><span data-stu-id="75d7f-135">Browse list pages and reports</span></span>

<span data-ttu-id="75d7f-136">Ha megerősíti az értékesítési ajánlatokat, az ebből származó értékesítési jelentések az egész szállítási ütemezést mutatják, még a több kiszállításból álló rendelési sorokat is.</span><span class="sxs-lookup"><span data-stu-id="75d7f-136">When you confirm sales quotations, the resulting sales orders show the whole delivery schedule, even the order lines that have multiple deliveries.</span></span> <span data-ttu-id="75d7f-137">Ezenkívül a teljes szállítási ütemezés megjelenik az összes fő lapon, például értékesítési rendelések, értékesítési ajánlatok és beszerzési rendelések lapokon.</span><span class="sxs-lookup"><span data-stu-id="75d7f-137">In addition, the whole delivery schedule is shown on all the major pages, such as sales orders, sales quotations, and purchase orders.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]