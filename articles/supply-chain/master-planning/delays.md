---
title: Késések
description: Ez a témakör az alaptervezésben szereplő késleltetett dátumokról szolgál információval. A késleltetett dátum egy olyan valós határidő, amelyet a tranzakció kap meg, akkor ha az alaptervezés által kiszámított legkorábbi teljesítési dátum későbbre esik, mint a kért dátum.
author: roxanadiaconu
manager: tfehr
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 195a966ea8baee7783af84ec5f178d7c35ee5cea
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207087"
---
# <a name="delays"></a><span data-ttu-id="7b568-104">Késések</span><span class="sxs-lookup"><span data-stu-id="7b568-104">Delays</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7b568-105">Ez a témakör az alaptervezésben szereplő késleltetett dátumokról szolgál információval.</span><span class="sxs-lookup"><span data-stu-id="7b568-105">This topic provides information about delayed dates in master planning.</span></span> <span data-ttu-id="7b568-106">A késleltetett dátum egy olyan valós határidő, amelyet a tranzakció kap meg, akkor ha az alaptervezés által kiszámított legkorábbi teljesítési dátum későbbre esik, mint a kért dátum.</span><span class="sxs-lookup"><span data-stu-id="7b568-106">A delayed date is a realistic due date that a transaction receives if the earliest fulfillment date that master planning calculates is later than the requested date.</span></span>

<span data-ttu-id="7b568-107">Az alaptervezés kiszámíthatja egy tranzakció legkorábbi teljesítési dátumát, az átfutási idők, az anyagok rendelkezésre állása, a rendelkezésre álló kapacitás és a különböző tervezési paraméterek alapján.</span><span class="sxs-lookup"><span data-stu-id="7b568-107">Master planning can calculate the earliest fulfillment date for a transaction, based on lead times, material availability, capacity availability, and various planning parameters.</span></span> 

<span data-ttu-id="7b568-108">Ha az alaptervezés olyan rendelési dátumot számít ki, amely az aktuális dátumnál korábbi, akkor a rendelés időben nem teljesíthető.</span><span class="sxs-lookup"><span data-stu-id="7b568-108">If master planning calculates an order date that precedes the current date, the order can't be fulfilled on time.</span></span> <span data-ttu-id="7b568-109">Emiatt a rendelés késik.</span><span class="sxs-lookup"><span data-stu-id="7b568-109">Therefore, the order is delayed.</span></span> <span data-ttu-id="7b568-110">Ebben az esetben az alaptervezés az aktuális dátumtól kezdve előretolja a tervet, és figyelembe veszi az átfutási időket is.</span><span class="sxs-lookup"><span data-stu-id="7b568-110">In this case, master planning forward-plans the order from the current date and includes lead times.</span></span> <span data-ttu-id="7b568-111">Ezek az átfutási idők bármely alacsonyabb szintű összetevő elemmel kezdődhetnek.</span><span class="sxs-lookup"><span data-stu-id="7b568-111">These lead times start with any lower-level component items.</span></span> <span data-ttu-id="7b568-112">A rendelés ezután egy késleltetett dátumot kap.</span><span class="sxs-lookup"><span data-stu-id="7b568-112">The order then receives a delayed date.</span></span> <span data-ttu-id="7b568-113">A késleltetett dátum egy valószerű, a tényleges adatokon alapuló dátum lesz.</span><span class="sxs-lookup"><span data-stu-id="7b568-113">A delayed date is a realistic due date, based on the current data.</span></span> <span data-ttu-id="7b568-114">Az alaptervezés emellett a késés napjait is kiszámítja.</span><span class="sxs-lookup"><span data-stu-id="7b568-114">Master planning also calculates the number of delay days.</span></span> 

<span data-ttu-id="7b568-115">Bizonyos esetekben előfordulhat, hogy nem kívánja kiszámolni a késést, például amikor a felhasználók tudják, hogy alternatív szállítási módok kiválasztásával megsürgethetik az átfutási időt.</span><span class="sxs-lookup"><span data-stu-id="7b568-115">In some situations, you might choose not to calculate delays, such as when users know that they can expedite lead times by selecting alternative modes of delivery.</span></span> 

<span data-ttu-id="7b568-116">Beállíthatja, hogyan számítsa ki a rendszer a fedezetcsoport késéseit.</span><span class="sxs-lookup"><span data-stu-id="7b568-116">You can configure how delays are calculated for a coverage group.</span></span> <span data-ttu-id="7b568-117">Ezt követően csatolhatja a fedezetcsoportot egy cikkhez.</span><span class="sxs-lookup"><span data-stu-id="7b568-117">You can then attach the coverage group to an item later.</span></span> 

<span data-ttu-id="7b568-118">Az **Alaptervezés paraméterei** lapon beállíthatja a késések számításának kezdő időpontját.</span><span class="sxs-lookup"><span data-stu-id="7b568-118">On the **Master planning parameters** page, you can set the start time for the calculation of delays.</span></span> <span data-ttu-id="7b568-119">Ha egy rendelés ezen időpont után teljesül, akkor egy nap hozzáadódik a rendelés késési dátumához.</span><span class="sxs-lookup"><span data-stu-id="7b568-119">If an order is fulfilled after this time, a delay of one day is added to the delay date of the order.</span></span> 

> [!NOTE]
> <span data-ttu-id="7b568-120">A korábbi változatokban a késések kiszámítását *határidős üzeneteknek* nevezték, a késleltetett dátum neve *határidős dátum* volt, a késleltetett tranzakcióé pedig *beállított jövőbeli tranzakció*.</span><span class="sxs-lookup"><span data-stu-id="7b568-120">In earlier versions, calculated delays were known as *futures messages*, the delayed date was known as the *futures date*, and a delayed transaction was referred to as *a transaction that was future set*.</span></span>

## <a name="limited-delays-in-production-setup-with-multiple-bom-levels"></a><span data-ttu-id="7b568-121">Korlátozott késések a termelési beállításokban több anyagjegyzék-szinttel</span><span class="sxs-lookup"><span data-stu-id="7b568-121">Limited delays in production setup with multiple BOM levels</span></span>
<span data-ttu-id="7b568-122">Ha több anyagjegyzék-szintet tartalmazó termelési beállításnál késéseket dolgozik, fontos megjegyezni, hogy csak a késést okozó cikk fölött közvetlenül található cikkek (az anyagjegyzék szerkezetben) lesznek frissítve a késéssel az alaptervezés futtatásakor.</span><span class="sxs-lookup"><span data-stu-id="7b568-122">When you work with delays in a production setup that has multiple BOM levels, it is important to note that only the items directly above the item (in the BOM structure) causing the delay, will be updated with a delay as part of the master planning run.</span></span> <span data-ttu-id="7b568-123">Az anyagjegyzék-szerkezet többi cikkér nem lesz alkalmazva a késleltetés az első alaptervezés-futtatásig, amikor a felső szintű tervezett rendelés jóvá van hagyva vagy meg van erősítve.</span><span class="sxs-lookup"><span data-stu-id="7b568-123">Other items in the BOM structure will not get the delay applied until the first master planning run, when the planned order for the top level is approved or firmed.</span></span> 

<span data-ttu-id="7b568-124">Ha ezt az ismert korlátozást szeretné megkerülni akkor az anyagjegyzék-szerkezet felső részén található termelési rendelések jóváhagyása (vagy megerősítése) a következő Alaptervezés futtatása előtt elvégezhető.</span><span class="sxs-lookup"><span data-stu-id="7b568-124">To work around this known limitation, the production orders on the top of the BOM structure with delays can be approved (or firmed) prior to the next master planning run.</span></span> <span data-ttu-id="7b568-125">Ily módon a késleltetett jóváhagyott tervezett termelési rendelés késése meg lesz tartva, és a rendszer ennek megfelelően frissíti az összes mögöttes összetevőt.</span><span class="sxs-lookup"><span data-stu-id="7b568-125">This way the delay from the delayed approved planned production order will be kept and all underlying components will be updated accordingly.</span></span>
<span data-ttu-id="7b568-126">A műveletüzenetek a későbbi dátumra áthelyezhető tervezett rendelések azonosítására is használhatók, az anyagjegyzék-szerkezet egyéb késései miatt.</span><span class="sxs-lookup"><span data-stu-id="7b568-126">Action messages can also be used to identify planned orders that can be moved to a later date, due to other delays in the BOM structure.</span></span>

## <a name="desired-date"></a><span data-ttu-id="7b568-127">Kívánt dátum</span><span class="sxs-lookup"><span data-stu-id="7b568-127">Desired date</span></span>

<span data-ttu-id="7b568-128">A **Tervezett rendelés** oldalon a **Késések** lapon található a tervezett rendelés **Kívánt dátuma**.</span><span class="sxs-lookup"><span data-stu-id="7b568-128">On the **Planned order** page, under the **Delays** tab is the **Desired date** for the planned order.</span></span> <span data-ttu-id="7b568-129">Egy tervezett rendelés kívánt dátuma a késések alapdátuma, amely egy számított dátum, a **Kért dátum** értékével egyezik meg, amelyet a **Nettó követelmény** értékéből számítottak.</span><span class="sxs-lookup"><span data-stu-id="7b568-129">The desired date of a planned order is the base date for delays, which is a computed date that equals the **Requested date** calculated from the **Net Requirement**.</span></span> <span data-ttu-id="7b568-130">Ha a tervezett rendelés anyagjegyzéksor, termelési sor vagy kanbansor, akkor a kívánt dátum kiszámítása a **Követelmény dátuma** értékén alapul, és a kívánt dátum nem jelenik meg a **Tervezett rendelés** oldalon.</span><span class="sxs-lookup"><span data-stu-id="7b568-130">If the planned order is a BOM line, production line or kanban line, the desired date is based on the **Requirement date** and the desired date will not be shown on the **Planned order** page.</span></span>

<a name="additional-resources"></a><span data-ttu-id="7b568-131">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="7b568-131">Additional resources</span></span>
--------

[<span data-ttu-id="7b568-132">Fedezeti beállítások</span><span class="sxs-lookup"><span data-stu-id="7b568-132">Coverage settings</span></span>](coverage-settings.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]