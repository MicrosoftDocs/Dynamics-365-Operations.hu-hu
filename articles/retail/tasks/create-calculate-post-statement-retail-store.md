---
title: Kiskereskedelmi üzlet kimutatásának létrehozása, kiszámítása és feladása
description: Ez az eljárás végigveszi egy üzlet kimutatása létrehozásának, kiszámításának és feladásának manuális lépéseit.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailStatementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9ea30e7e008bfcce77a7ee2f4d7d01a6cf1ababc
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "354391"
---
# <a name="create-calculate-and-post-a-statement-for-a-retail-store"></a><span data-ttu-id="2b38e-103">Kiskereskedelmi üzlet kimutatásának létrehozása, kiszámítása és feladása</span><span class="sxs-lookup"><span data-stu-id="2b38e-103">Create, calculate, and post a statement for a retail store</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="2b38e-104">Ez az eljárás végigveszi egy üzlet kimutatása létrehozásának, kiszámításának és feladásának manuális lépéseit.</span><span class="sxs-lookup"><span data-stu-id="2b38e-104">This procedure walks through the manual steps for creating, calculating, and posting a statement for a store.</span></span> <span data-ttu-id="2b38e-105">Kötegelt feladatok is léteznek, amelyek ugyanazon eljárásokhoz konfigurálhatók.</span><span class="sxs-lookup"><span data-stu-id="2b38e-105">There are also batch jobs that can be configured for the same tasks.</span></span> <span data-ttu-id="2b38e-106">A kötegelt feladatok konfigurálásának és futtatásának lépései egy másik témakörben találhatók meg.</span><span class="sxs-lookup"><span data-stu-id="2b38e-106">The steps for configuring and running the batch jobs can be found in other topics.</span></span> <span data-ttu-id="2b38e-107">Az eljárás végrehajtásához rendelkeznie kell olyan tranzakciókkal, amelyeket a pénztárban hajtottak végre, majd átvezették a Dynamics AX programba.</span><span class="sxs-lookup"><span data-stu-id="2b38e-107">To complete this procedure, you must have transactions that were completed in POS and then pulled into Dynamics AX.</span></span> <span data-ttu-id="2b38e-108">Ez a bejegyzés az USRT cég adatait használja, mint bemutatóadatokat.</span><span class="sxs-lookup"><span data-stu-id="2b38e-108">This recording uses the USRT company in demo data.</span></span> <span data-ttu-id="2b38e-109">Az eljárás a Microsoft Dynamics AX szolgáltatásra vonatkozhat.</span><span class="sxs-lookup"><span data-stu-id="2b38e-109">This procedure may refer to Microsoft Dynamics AX.</span></span> <span data-ttu-id="2b38e-110">Ne feledje, hogy a Dynamics AX új neve Microsoft Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="2b38e-110">Please note that Dynamics AX is now called Microsoft Dynamics 365 for Operations.</span></span>

1. <span data-ttu-id="2b38e-111">Lépjen Az összes munkaterület > ..</span><span class="sxs-lookup"><span data-stu-id="2b38e-111">Go to All workspaces > ..</span></span> <span data-ttu-id="2b38e-112">> Kiskereskedelmi üzlet pénzügyei lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2b38e-112">> Retail store financials.</span></span>
2. <span data-ttu-id="2b38e-113">Kattintson az Új kimutatás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2b38e-113">Click New statement.</span></span>
3. <span data-ttu-id="2b38e-114">Az Üzlet száma mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="2b38e-114">In the Store number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="2b38e-115">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="2b38e-115">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="2b38e-116">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="2b38e-116">Click OK.</span></span>
    * <span data-ttu-id="2b38e-117">A Beállítások csoportban beállíthatja, hogy mely tranzakciók szerepeljenek a kimutatásban, és hogy azok hogyan legyenek sorokba csoportosítva.</span><span class="sxs-lookup"><span data-stu-id="2b38e-117">The Setup group has the settings that control what transactions are included in the statement and how they are grouped into statement lines.</span></span> <span data-ttu-id="2b38e-118">Megnyithatja a Beállítások csoportot és megváltoztathatja a beállításokat, vagy használhatja az alapértelmezett beállításokat is.</span><span class="sxs-lookup"><span data-stu-id="2b38e-118">You can open the Setup group and change these settings, or you can use the defaults.</span></span>  
    * <span data-ttu-id="2b38e-119">A Kimutatás módja mező megadja, hogy a kimutatás sorai hogyan lesznek csoportosítva.</span><span class="sxs-lookup"><span data-stu-id="2b38e-119">The Statement method field defines how the statement lines will be grouped.</span></span>  
    * <span data-ttu-id="2b38e-120">Válasszon ki egy munkatársat vagy egy jegyzéket, ha a kimutatást csak egy bizonyos munkatársra vagy jegyzékre vonatkozóan szeretné elkészíteni.</span><span class="sxs-lookup"><span data-stu-id="2b38e-120">Select a staff member or a register if you want to calculate a statement only for the specific staff member or register.</span></span>  
6. <span data-ttu-id="2b38e-121">Válassza ki valamelyik lehetőséget a Zárási mód mezőben.</span><span class="sxs-lookup"><span data-stu-id="2b38e-121">In the Closing method field, select an option.</span></span>
7. <span data-ttu-id="2b38e-122">Kattintson a Kimutatás számítása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2b38e-122">Click Calculate statement.</span></span>
8. <span data-ttu-id="2b38e-123">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="2b38e-123">Click Yes.</span></span>
    * <span data-ttu-id="2b38e-124">A kimutatás elkészítése után külön sorokban kell szerepelnie a teljes összegnek minden alkalmazott fizetési mód és kimutatási mód esetén.</span><span class="sxs-lookup"><span data-stu-id="2b38e-124">After calculating the statement, there should be lines created with total amounts for each payment method and statement method that was used.</span></span>  
    * <span data-ttu-id="2b38e-125">Adjon meg egy leszámolt összeget minden sorban, amelyben meg kell adni vagy frissíteni kell az értéket.</span><span class="sxs-lookup"><span data-stu-id="2b38e-125">Enter a counted amount in each line if it needs to be entered or updated.</span></span> <span data-ttu-id="2b38e-126">A leszámolt értéket tartalmazó mező a pénztárban végrehajtott fizetőeszköz-elszámolások során kapott összeggel van kitöltve.</span><span class="sxs-lookup"><span data-stu-id="2b38e-126">The counted field is populated with amounts from tender declarations done in POS.</span></span>  
9. <span data-ttu-id="2b38e-127">Kattintson a Kimutatás feladása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2b38e-127">Click Post statement.</span></span>
10. <span data-ttu-id="2b38e-128">Kattintson a Bezárás gombra.</span><span class="sxs-lookup"><span data-stu-id="2b38e-128">Click Close.</span></span>
11. <span data-ttu-id="2b38e-129">Ugorjon a következő oldalra: Kiskereskedelem és kereskedelem > Csatornák > Kiskereskedelmi üzlet pénzügyei.</span><span class="sxs-lookup"><span data-stu-id="2b38e-129">Go to Retail and commerce > Channels > Retail store financials.</span></span>
12. <span data-ttu-id="2b38e-130">Kattintson a Feladott kimutatások fülre.</span><span class="sxs-lookup"><span data-stu-id="2b38e-130">Click the Posted statements tab.</span></span>

