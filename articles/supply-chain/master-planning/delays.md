---
title: Késések
description: Ez a témakör az alaptervezésben szereplő késleltetett dátumokról szolgál információval. A késleltetett dátum egy olyan valós határidő, amelyet a tranzakció kap meg, akkor ha az alaptervezés által kiszámított legkorábbi teljesítési dátum későbbre esik, mint a kért dátum.
author: roxanadiaconu
manager: AnnBe
ms.date: 03/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c1a8c738fffda76f2a8492c20e2c67a154c68559
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1522289"
---
# <a name="delays"></a><span data-ttu-id="88e3d-104">Késések</span><span class="sxs-lookup"><span data-stu-id="88e3d-104">Delays</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="88e3d-105">Ez a témakör az alaptervezésben szereplő késleltetett dátumokról szolgál információval.</span><span class="sxs-lookup"><span data-stu-id="88e3d-105">This topic provides information about delayed dates in master planning.</span></span> <span data-ttu-id="88e3d-106">A késleltetett dátum egy olyan valós határidő, amelyet a tranzakció kap meg, akkor ha az alaptervezés által kiszámított legkorábbi teljesítési dátum későbbre esik, mint a kért dátum.</span><span class="sxs-lookup"><span data-stu-id="88e3d-106">A delayed date is a realistic due date that a transaction receives if the earliest fulfillment date that master planning calculates is later than the requested date.</span></span>

<span data-ttu-id="88e3d-107">Az alaptervezés kiszámíthatja egy tranzakció legkorábbi teljesítési dátumát, az átfutási idők, az anyagok rendelkezésre állása, a rendelkezésre álló kapacitás és a különböző tervezési paraméterek alapján.</span><span class="sxs-lookup"><span data-stu-id="88e3d-107">Master planning can calculate the earliest fulfillment date for a transaction, based on lead times, material availability, capacity availability, and various planning parameters.</span></span> 

<span data-ttu-id="88e3d-108">Ha az alaptervezés olyan rendelési dátumot számít ki, amely az aktuális dátumnál korábbi, akkor a rendelés időben nem teljesíthető.</span><span class="sxs-lookup"><span data-stu-id="88e3d-108">If master planning calculates an order date that precedes the current date, the order can't be fulfilled on time.</span></span> <span data-ttu-id="88e3d-109">Emiatt a rendelés késik.</span><span class="sxs-lookup"><span data-stu-id="88e3d-109">Therefore, the order is delayed.</span></span> <span data-ttu-id="88e3d-110">Ebben az esetben az alaptervezés az aktuális dátumtól kezdve előretolja a tervet, és figyelembe veszi az átfutási időket is.</span><span class="sxs-lookup"><span data-stu-id="88e3d-110">In this case, master planning forward-plans the order from the current date and includes lead times.</span></span> <span data-ttu-id="88e3d-111">Ezek az átfutási idők bármely alacsonyabb szintű összetevő elemmel kezdődhetnek.</span><span class="sxs-lookup"><span data-stu-id="88e3d-111">These lead times start with any lower-level component items.</span></span> <span data-ttu-id="88e3d-112">A rendelés ezután egy késleltetett dátumot kap.</span><span class="sxs-lookup"><span data-stu-id="88e3d-112">The order then receives a delayed date.</span></span> <span data-ttu-id="88e3d-113">A késleltetett dátum egy valószerű, a tényleges adatokon alapuló dátum lesz.</span><span class="sxs-lookup"><span data-stu-id="88e3d-113">A delayed date is a realistic due date, based on the current data.</span></span> <span data-ttu-id="88e3d-114">Az alaptervezés emellett a késés napjait is kiszámítja.</span><span class="sxs-lookup"><span data-stu-id="88e3d-114">Master planning also calculates the number of delay days.</span></span> 

<span data-ttu-id="88e3d-115">Bizonyos esetekben előfordulhat, hogy nem kívánja kiszámolni a késést, például amikor a felhasználók tudják, hogy alternatív szállítási módok kiválasztásával megsürgethetik az átfutási időt.</span><span class="sxs-lookup"><span data-stu-id="88e3d-115">In some situations, you might choose not to calculate delays, such as when users know that they can expedite lead times by selecting alternative modes of delivery.</span></span> 

<span data-ttu-id="88e3d-116">Beállíthatja, hogyan számítsa ki a rendszer a fedezetcsoport késéseit.</span><span class="sxs-lookup"><span data-stu-id="88e3d-116">You can configure how delays are calculated for a coverage group.</span></span> <span data-ttu-id="88e3d-117">Ezt követően csatolhatja a fedezetcsoportot egy cikkhez.</span><span class="sxs-lookup"><span data-stu-id="88e3d-117">You can then attach the coverage group to an item later.</span></span> 

<span data-ttu-id="88e3d-118">Az **Alaptervezés paraméterei** lapon beállíthatja a késések számításának kezdő időpontját.</span><span class="sxs-lookup"><span data-stu-id="88e3d-118">On the **Master planning parameters** page, you can set the start time for the calculation of delays.</span></span> <span data-ttu-id="88e3d-119">Ha egy rendelés ezen időpont után teljesül, akkor egy nap hozzáadódik a rendelés késési dátumához.</span><span class="sxs-lookup"><span data-stu-id="88e3d-119">If an order is fulfilled after this time, a delay of one day is added to the delay date of the order.</span></span> 

> [!NOTE]
> <span data-ttu-id="88e3d-120">A korábbi változatokban a késések kiszámítását *határidős üzeneteknek* nevezték, a késleltetett dátum neve *határidős dátum* volt, a késleltetett tranzakcióé pedig *beállított jövőbeli tranzakció*.</span><span class="sxs-lookup"><span data-stu-id="88e3d-120">In earlier versions, calculated delays were known as *futures messages*, the delayed date was known as the *futures date*, and a delayed transaction was referred to as *a transaction that was future set*.</span></span>

## <a name="desired-date"></a><span data-ttu-id="88e3d-121">Kívánt dátum</span><span class="sxs-lookup"><span data-stu-id="88e3d-121">Desired date</span></span>

<span data-ttu-id="88e3d-122">A **Tervezett rendelés** oldalon a **Késések** lapon található a tervezett rendelés **Kívánt dátuma**.</span><span class="sxs-lookup"><span data-stu-id="88e3d-122">On the **Planned order** page, under the **Delays** tab is the **Desired date** for the planned order.</span></span> <span data-ttu-id="88e3d-123">Egy tervezett rendelés kívánt dátuma a késések alapdátuma, amely egy számított dátum, a **Kért dátum** értékével egyezik meg, amelyet a **Nettó követelmény** értékéből számítottak.</span><span class="sxs-lookup"><span data-stu-id="88e3d-123">The desired date of a planned order is the base date for delays, which is a computed date that equals the **Requested date** calculated from the **Net Requirement**.</span></span> <span data-ttu-id="88e3d-124">Ha a tervezett rendelés anyagjegyzéksor, termelési sor vagy kanbansor, akkor a kívánt dátum kiszámítása a **Követelmény dátuma** értékén alapul, és a kívánt dátum nem jelenik meg a **Tervezett rendelés** oldalon.</span><span class="sxs-lookup"><span data-stu-id="88e3d-124">If the planned order is a BOM line, production line or kanban line, the desired date is based on the **Requirement date** and the desired date will not be shown on the **Planned order** page.</span></span>

<a name="additional-resources"></a><span data-ttu-id="88e3d-125">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="88e3d-125">Additional resources</span></span>
--------

[<span data-ttu-id="88e3d-126">Fedezeti beállítások</span><span class="sxs-lookup"><span data-stu-id="88e3d-126">Coverage settings</span></span>](coverage-settings.md)
