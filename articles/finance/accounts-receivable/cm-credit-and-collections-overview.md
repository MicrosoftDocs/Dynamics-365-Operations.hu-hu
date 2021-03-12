---
title: Hitelek és beszedések áttekintése
description: Ez a témakör a hitel és beszedések funkcióhoz nyújt áttekintést.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: ade76b822904f49135e07dfe0a39d2227dd1dd77
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992988"
---
# <a name="credit-and-collections-overview"></a><span data-ttu-id="733c1-103">Hitelek és beszedések áttekintése</span><span class="sxs-lookup"><span data-stu-id="733c1-103">Credit and collections overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="733c1-104">A vevői hitelkeretek kezelhetők, és szükség esetén a beszedési tevékenységek hajthatók végre.</span><span class="sxs-lookup"><span data-stu-id="733c1-104">You can manage credit limits for your customers and perform collection activities when they become necessary.</span></span>

## <a name="credit-management"></a><span data-ttu-id="733c1-105">Hitelkezelés</span><span class="sxs-lookup"><span data-stu-id="733c1-105">Credit management</span></span>

<span data-ttu-id="733c1-106">A vevői hitelkezelés lehetővé teszi a hitelkeretek kezelését, valamint az értékesítési rendelések áramlásának szabályozását a feladási folyamaton keresztül, az Ön által létrehozott hitelszabályok alapján.</span><span class="sxs-lookup"><span data-stu-id="733c1-106">Customer credit management lets you manage credit limits and control the flow of sales orders through the posting process, based on credit rules that you create.</span></span>

<span data-ttu-id="733c1-107">A hitelkezelési folyamat a következő lépések bármelyikét tartalmazhatja:</span><span class="sxs-lookup"><span data-stu-id="733c1-107">The credit management process can include any of the following steps:</span></span>

- <span data-ttu-id="733c1-108">Hitelattribútumok frissítése a vevők számára további információk megadásához hitelképességükről.</span><span class="sxs-lookup"><span data-stu-id="733c1-108">Update credit attributes for customers to provide additional information about their credit worthiness.</span></span>
- <span data-ttu-id="733c1-109">Hitelkeretek létrehozása ügyefelekhez hitelkeret-kiigazítások használatával.</span><span class="sxs-lookup"><span data-stu-id="733c1-109">Create credit limits for customers by using credit limit adjustments.</span></span>
- <span data-ttu-id="733c1-110">Ideiglenes hitelkeretek létrehozása ügyefelekhez hitelkeret-kiigazítások használatával.</span><span class="sxs-lookup"><span data-stu-id="733c1-110">Create temporary credit limits for customers by using credit limit adjustments.</span></span> <span data-ttu-id="733c1-111">Így ideiglenesen növelheti vagy csökkentheti a vevői hitelkereteket az üzleti szükségletek alapján.</span><span class="sxs-lookup"><span data-stu-id="733c1-111">In this way, you can temporarily increase or decrease customer credit limits, based on business requirements.</span></span>
- <span data-ttu-id="733c1-112">A hitelkeretet befolyásoló adatok, például a biztosítással és a garanciával kapcsolatos információk hozzáadása.</span><span class="sxs-lookup"><span data-stu-id="733c1-112">Add information that can affect the credit limit, such as information about insurance and guarantees.</span></span>
- <span data-ttu-id="733c1-113">Vevői hitelcsoportok létrehozása, amelyekkel a vevők összekapcsolhatók úgy, hogy egyetlen hitelkeretet osszanak meg egymással.</span><span class="sxs-lookup"><span data-stu-id="733c1-113">Create customer credit groups that link customers together so that they share a single credit limit.</span></span>
- <span data-ttu-id="733c1-114">Kockázati pontszámok hozzárendelése a vevőkhöz, majd a pontszámok használatával hitelkereteket hozhat létre a vevőkhöz a hitelkeret-módosítások használatával.</span><span class="sxs-lookup"><span data-stu-id="733c1-114">Assign risk scores to customers, and then use the scores to automatically generate credit limits for those customers through credit limit adjustments.</span></span>
- <span data-ttu-id="733c1-115">Létrehozhat zárolási szabályokat, amelyek egy vagy több feladási folyamat során várakoztatnak egy rendelést, olyan tényezők alapján, mint a kockázat, a fizetési feltételek, a hitelkeretek, a lejárt tartozások és felhasznált hitelkeret százaléka.</span><span class="sxs-lookup"><span data-stu-id="733c1-115">Create blocking rules that put an order on hold during one or more posting processes, based on factors such as risk, payment terms, credit limits, overdue amounts, and the percentage of the credit limit that has been used.</span></span>
- <span data-ttu-id="733c1-116">A várakoztatott értékesítési rendelések listájának kezelése, a várakoztatási okok áttekintése, valamint a problémák megoldása.</span><span class="sxs-lookup"><span data-stu-id="733c1-116">Manage a list of sales orders that are on hold, review the reasons for the hold, and mitigate issues.</span></span>
- <span data-ttu-id="733c1-117">Értékesítési rendelések felszabadítása, hogy a feladási folyamatban továbbhaladhassanak.</span><span class="sxs-lookup"><span data-stu-id="733c1-117">Release sales orders so that they continue through the posting process.</span></span>
- <span data-ttu-id="733c1-118">Munkafolyamatot állíthat be a hitelkeret-módosítások és az értékesítési rendelés felszabadítások jóváhagyásának kezelésére.</span><span class="sxs-lookup"><span data-stu-id="733c1-118">Set up a workflow to manage the approval of credit limit changes and sales order releases.</span></span>

## <a name="collections-management"></a><span data-ttu-id="733c1-119">Beszedések kezelése</span><span class="sxs-lookup"><span data-stu-id="733c1-119">Collections management</span></span>

<span data-ttu-id="733c1-120">A kinnlevőségek kezelésével kapcsolatos adatokat egyetlen központi nézetből, a **Beszedések** oldalon kezelheti.</span><span class="sxs-lookup"><span data-stu-id="733c1-120">The **Collections** page provides a centralized view where accounts receivable collections information is managed.</span></span> <span data-ttu-id="733c1-121">A Beszedési vezetők ezt a központi nézetet használhatják a beszedések kezelésére.</span><span class="sxs-lookup"><span data-stu-id="733c1-121">Collections managers can use this centralized view to manage collections.</span></span> <span data-ttu-id="733c1-122">A pénzbehajtó elkezdheti a beszedési folyamatot az előre meghatározott beszedési feltételek használata által létrehozott vevői listából vagy a **Vevők** oldalon.</span><span class="sxs-lookup"><span data-stu-id="733c1-122">Collections agents can begin the collections process either from customer lists that are generated by using predefined collection criteria or from the **Customers** page.</span></span>

<span data-ttu-id="733c1-123">Mielőtt elkezdené beállítani a beszedéseket vagy elkezdene dolgozni velük, ismerje meg a következő fogalmakat:</span><span class="sxs-lookup"><span data-stu-id="733c1-123">Before you start to set up or work with collections, you should understand the following concepts:</span></span>

- <span data-ttu-id="733c1-124">Vevő korosítási pillanatképei egy adott időpontban tartalmazzák Korosított egyenleget.</span><span class="sxs-lookup"><span data-stu-id="733c1-124">Customer aging snapshots contain aged balance information at a specific point in time.</span></span>
- <span data-ttu-id="733c1-125">Beszedések vevőgyűjtő segíthet a munkáját megszervezni.</span><span class="sxs-lookup"><span data-stu-id="733c1-125">Collections customer pools help you organize your work.</span></span>
- <span data-ttu-id="733c1-126">A pénzbehajtók saját vevőgyűjtővel rendelkezhetnek.</span><span class="sxs-lookup"><span data-stu-id="733c1-126">Collections agents can have their own customer pools.</span></span>
- <span data-ttu-id="733c1-127">A listalapok megszervezik a vevők összegyűjtését, a tevékenységeket és az eseteket.</span><span class="sxs-lookup"><span data-stu-id="733c1-127">List pages organize collections customers, activities, and cases.</span></span>
- <span data-ttu-id="733c1-128">A vevővel kapcsolatos minden összegyűjtött információ rajta van a lapon, és itt végezhet műveleteket is.</span><span class="sxs-lookup"><span data-stu-id="733c1-128">All collections information for a customer is on one page, and you can take action from that page.</span></span>
- <span data-ttu-id="733c1-129">Kamatok vagy díjak elengedése, visszaállítása vagy sztornírozása elvégezhető egy lépésben.</span><span class="sxs-lookup"><span data-stu-id="733c1-129">Interest and fees can be waived, reinstated, or reversed in one step.</span></span>
- <span data-ttu-id="733c1-130">A leírási tranzakciók létrehozása elvégezhető egy lépésben.</span><span class="sxs-lookup"><span data-stu-id="733c1-130">Write-off transactions can be created in one step.</span></span>
- <span data-ttu-id="733c1-131">Az Elégtelen fedezetű (NSF) fizetések feldolgozása egy lépésben elvégezhető.</span><span class="sxs-lookup"><span data-stu-id="733c1-131">Not sufficient funds (NSF) payments can be processed in one step.</span></span>

<span data-ttu-id="733c1-132">A fogalmak leírása a következő témakörben olvasható: [A beszedéskezelés kulcsfogalmai](./cm-collections-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="733c1-132">For descriptions of these concepts, see [Collections management key concepts](./cm-collections-concepts.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="733c1-133">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="733c1-133">Additional resources</span></span>

[<span data-ttu-id="733c1-134">Vásárlói hitelkezelési pereméterek beállítása</span><span class="sxs-lookup"><span data-stu-id="733c1-134">Customer credit management parameters setup</span></span>](./cm-credit-mgmt-setup.md)

[<span data-ttu-id="733c1-135">Vásárlói hitelkezelési pereméterek beállításával kapcsolatos információk</span><span class="sxs-lookup"><span data-stu-id="733c1-135">Customer credit management setup information</span></span>](./cm-setup-information.md)

[<span data-ttu-id="733c1-136">Hitelkezelési információk hozzáadása egy ügyfélhez</span><span class="sxs-lookup"><span data-stu-id="733c1-136">Add credit management information for a customer</span></span>](./cm-add-credit-mgmt-information-customer.md)

[<span data-ttu-id="733c1-137">Vevői hitelcsoportok</span><span class="sxs-lookup"><span data-stu-id="733c1-137">Customer credit groups</span></span>](./cm-customer-credit-groups.md)

[<span data-ttu-id="733c1-138">Vevői hitelkeret helyesbítései</span><span class="sxs-lookup"><span data-stu-id="733c1-138">Customer credit limit adjustments</span></span>](./cm-credit-limit-adjustments.md)

[<span data-ttu-id="733c1-139">Hitelkeret felfüggesztése értékesítési rendelésekhez</span><span class="sxs-lookup"><span data-stu-id="733c1-139">Credit holds for sales orders</span></span>](./cm-sales-order-credit-holds.md)

[<span data-ttu-id="733c1-140">Vevői hitelkockázatkezelés – időszakos feladatok</span><span class="sxs-lookup"><span data-stu-id="733c1-140">Customer credit management periodic tasks</span></span>](./cm-periodic-tasks.md)
