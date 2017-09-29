---
title: "Késések"
description: "Ez a cikk az alaptervezésben szereplő késleltetett dátumokról szolgál információval. A késleltetett dátum egy olyan valós határidő, amelyet a tranzakció kap meg, akkor ha az alaptervezés által kiszámított legkorábbi teljesítési dátum későbbre esik, mint a kért dátum."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 8db5c507fbc68e637dbbc4ef3311d1fbd298f24f
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---

# <a name="delays"></a><span data-ttu-id="725a4-104">Késések</span><span class="sxs-lookup"><span data-stu-id="725a4-104">Delays</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="725a4-105">Ez a cikk az alaptervezésben szereplő késleltetett dátumokról szolgál információval.</span><span class="sxs-lookup"><span data-stu-id="725a4-105">This article provides information about delayed dates in master planning.</span></span> <span data-ttu-id="725a4-106">A késleltetett dátum egy olyan valós határidő, amelyet a tranzakció kap meg, akkor ha az alaptervezés által kiszámított legkorábbi teljesítési dátum későbbre esik, mint a kért dátum.</span><span class="sxs-lookup"><span data-stu-id="725a4-106">A delayed date is a realistic due date that a transaction receives if the earliest fulfillment date that master planning calculates is later than the requested date.</span></span>

<span data-ttu-id="725a4-107">Az alaptervezés kiszámíthatja egy tranzakció legkorábbi teljesítési dátumát, az átfutási idők, az anyagok rendelkezésre állása, a rendelkezésre álló kapacitás és a különböző tervezési paraméterek alapján.</span><span class="sxs-lookup"><span data-stu-id="725a4-107">Master planning can calculate the earliest fulfillment date for a transaction, based on lead times, material availability, capacity availability, and various planning parameters.</span></span> 

<span data-ttu-id="725a4-108">Ha az alaptervezés olyan rendelési dátumot számít ki, amely az aktuális dátumnál korábbi, akkor a rendelés időben nem teljesíthető.</span><span class="sxs-lookup"><span data-stu-id="725a4-108">If master planning calculates an order date that precedes the current date, the order can't be fulfilled on time.</span></span> <span data-ttu-id="725a4-109">Emiatt a rendelés késik.</span><span class="sxs-lookup"><span data-stu-id="725a4-109">Therefore, the order is delayed.</span></span> <span data-ttu-id="725a4-110">Ebben az esetben az alaptervezés az aktuális dátumtól kezdve előretolja a tervet, és figyelembe veszi az átfutási időket is.</span><span class="sxs-lookup"><span data-stu-id="725a4-110">In this case, master planning forward-plans the order from the current date and includes lead times.</span></span> <span data-ttu-id="725a4-111">Ezek az átfutási idők bármely alacsonyabb szintű összetevő elemmel kezdődhetnek.</span><span class="sxs-lookup"><span data-stu-id="725a4-111">These lead times start with any lower-level component items.</span></span> <span data-ttu-id="725a4-112">A rendelés ezután egy késleltetett dátumot kap.</span><span class="sxs-lookup"><span data-stu-id="725a4-112">The order then receives a delayed date.</span></span> <span data-ttu-id="725a4-113">A késleltetett dátum egy valószerű, a tényleges adatokon alapuló dátum lesz.</span><span class="sxs-lookup"><span data-stu-id="725a4-113">A delayed date is a realistic due date, based on the current data.</span></span> <span data-ttu-id="725a4-114">Az alaptervezés emellett a késés napjait is kiszámítja.</span><span class="sxs-lookup"><span data-stu-id="725a4-114">Master planning also calculates the number of delay days.</span></span> 

<span data-ttu-id="725a4-115">Bizonyos esetekben előfordulhat, hogy nem kívánja kiszámolni a késést, például amikor a felhasználók tudják, hogy alternatív szállítási módok kiválasztásával megsürgethetik az átfutási időt.</span><span class="sxs-lookup"><span data-stu-id="725a4-115">In some situations, you might choose not to calculate delays, such as when users know that they can expedite lead times by selecting alternative modes of delivery.</span></span> 

<span data-ttu-id="725a4-116">Beállíthatja, hogyan számítsa ki a rendszer a fedezetcsoport késéseit.</span><span class="sxs-lookup"><span data-stu-id="725a4-116">You can configure how delays are calculated for a coverage group.</span></span> <span data-ttu-id="725a4-117">Ezt követően csatolhatja a fedezetcsoportot egy cikkhez.</span><span class="sxs-lookup"><span data-stu-id="725a4-117">You can then attach the coverage group to an item later.</span></span> 

<span data-ttu-id="725a4-118">Az **Alaptervezés paraméterei** lapon beállíthatja a késések számításának kezdő időpontját.</span><span class="sxs-lookup"><span data-stu-id="725a4-118">On the **Master planning parameters** page, you can set the start time for the calculation of delays.</span></span> <span data-ttu-id="725a4-119">Ha egy rendelés ezen időpont után teljesül, akkor egy nap hozzáadódik a rendelés késési dátumához.</span><span class="sxs-lookup"><span data-stu-id="725a4-119">If an order is fulfilled after this time, a delay of one day is added to the delay date of the order.</span></span> 

<span data-ttu-id="725a4-120">**Megjegyzés:** A korábbi változatokban a késések kiszámítását *határidő-üzeneteknek* nevezték, a késleltetett dátum neve *határiő dátum* volt, a késleltetett tranzakcióé pedig *beállított jövőbeli tranzakció*.</span><span class="sxs-lookup"><span data-stu-id="725a4-120">**Note:** In earlier versions, calculated delays were known as *futures messages*, the delayed date was known as the *futures date*, and a delayed transaction was referred to as *a transaction that was future set*.</span></span>

<a name="see-also"></a><span data-ttu-id="725a4-121">Lásd még</span><span class="sxs-lookup"><span data-stu-id="725a4-121">See also</span></span>
--------

[<span data-ttu-id="725a4-122">Fedezeti beállítások</span><span class="sxs-lookup"><span data-stu-id="725a4-122">Coverage settings</span></span>](coverage-settings.md)




