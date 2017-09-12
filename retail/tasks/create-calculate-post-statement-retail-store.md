--- 
title: "Kiskereskedelmi üzlet kimutatásának létrehozása, kiszámítása és feladása"
description: "Ez az eljárás végigveszi egy üzlet kimutatása létrehozásának, kiszámításának és feladásának manuális lépéseit."
author: jashanno
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 42ab631e29a7fae1140acd41ad80c13e55ca1404
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="create-calculate-and-post-a-statement-for-a-retail-store"></a><span data-ttu-id="cf0dc-103">Kiskereskedelmi üzlet kimutatásának létrehozása, kiszámítása és feladása</span><span class="sxs-lookup"><span data-stu-id="cf0dc-103">Create, calculate, and post a statement for a retail store</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="cf0dc-104">Ez az eljárás végigveszi egy üzlet kimutatása létrehozásának, kiszámításának és feladásának manuális lépéseit.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-104">This procedure walks through the manual steps for creating, calculating, and posting a statement for a store.</span></span> <span data-ttu-id="cf0dc-105">Kötegelt feladatok is léteznek, amelyek ugyanazon eljárásokhoz konfigurálhatók.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-105">There are also batch jobs that can be configured for the same tasks.</span></span> <span data-ttu-id="cf0dc-106">A kötegelt feladatok konfigurálásának és futtatásának lépései egy másik témakörben találhatók meg.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-106">The steps for configuring and running the batch jobs can be found in other topics.</span></span> <span data-ttu-id="cf0dc-107">Az eljárás végrehajtásához rendelkeznie kell olyan tranzakciókkal, amelyeket a pénztárban hajtottak végre, majd átvezették a Dynamics AX programba.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-107">To complete this procedure, you must have transactions that were completed in POS and then pulled into Dynamics AX.</span></span> <span data-ttu-id="cf0dc-108">Ez a bejegyzés az USRT cég adatait használja, mint bemutatóadatokat.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-108">This recording uses the USRT company in demo data.</span></span> <span data-ttu-id="cf0dc-109">Ez az eljárás a Microsoft Dynamics AX rendszerre vonatkozhat.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-109">This procedure may refer to Microsoft Dynamics AX.</span></span> <span data-ttu-id="cf0dc-110">Ne feledje, hogy a Dynamics AX új neve Microsoft Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-110">Please note that Dynamics AX is now called Microsoft Dynamics 365 for Operations.</span></span>

1. <span data-ttu-id="cf0dc-111">Lépjen Az összes munkaterület > ..</span><span class="sxs-lookup"><span data-stu-id="cf0dc-111">Go to All workspaces > ..</span></span> <span data-ttu-id="cf0dc-112">> Kiskereskedelmi üzlet pénzügyei lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-112">> Retail store financials.</span></span>
2. <span data-ttu-id="cf0dc-113">Kattintson az Új kimutatás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-113">Click New statement.</span></span>
3. <span data-ttu-id="cf0dc-114">Az Üzlet száma mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-114">In the Store number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="cf0dc-115">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-115">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="cf0dc-116">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-116">Click OK.</span></span>
    * <span data-ttu-id="cf0dc-117">A Beállítások csoportban beállíthatja, hogy mely tranzakciók szerepeljenek a kimutatásban, és hogy azok hogyan legyenek sorokba csoportosítva.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-117">The Setup group has the settings that control what transactions are included in the statement and how they are grouped into statement lines.</span></span> <span data-ttu-id="cf0dc-118">Megnyithatja a Beállítások csoportot és megváltoztathatja a beállításokat, vagy használhatja az alapértelmezett beállításokat is.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-118">You can open the Setup group and change these settings, or you can use the defaults.</span></span>  
    * <span data-ttu-id="cf0dc-119">A Kimutatás módja mező megadja, hogy a kimutatás sorai hogyan lesznek csoportosítva.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-119">The Statement method field defines how the statement lines will be grouped.</span></span>  
    * <span data-ttu-id="cf0dc-120">Válasszon ki egy munkatársat vagy egy jegyzéket, ha a kimutatást csak egy bizonyos munkatársra vagy jegyzékre vonatkozóan szeretné elkészíteni.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-120">Select a staff member or a register if you want to calculate a statement only for the specific staff member or register.</span></span>  
6. <span data-ttu-id="cf0dc-121">Válassza ki valamelyik lehetőséget a Zárási mód mezőben.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-121">In the Closing method field, select an option.</span></span>
7. <span data-ttu-id="cf0dc-122">Kattintson a Kimutatás számítása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-122">Click Calculate statement.</span></span>
8. <span data-ttu-id="cf0dc-123">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-123">Click Yes.</span></span>
    * <span data-ttu-id="cf0dc-124">A kimutatás elkészítése után külön sorokban kell szerepelnie a teljes összegnek minden alkalmazott fizetési mód és kimutatási mód esetén.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-124">After calculating the statement, there should be lines created with total amounts for each payment method and statement method that was used.</span></span>  
    * <span data-ttu-id="cf0dc-125">Adjon meg egy leszámolt összeget minden sorban, amelyben meg kell adni vagy frissíteni kell az értéket.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-125">Enter a counted amount in each line if it needs to be entered or updated.</span></span> <span data-ttu-id="cf0dc-126">A leszámolt értéket tartalmazó mező a pénztárban végrehajtott fizetőeszköz-elszámolások során kapott összeggel van kitöltve.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-126">The counted field is populated with amounts from tender declarations done in POS.</span></span>  
9. <span data-ttu-id="cf0dc-127">Kattintson a Kimutatás feladása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-127">Click Post statement.</span></span>
10. <span data-ttu-id="cf0dc-128">Kattintson a Bezárás gombra.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-128">Click Close.</span></span>
11. <span data-ttu-id="cf0dc-129">Ugorjon a következő oldalra: Kiskereskedelem és kereskedelem > Csatornák > Kiskereskedelmi üzlet pénzügyei.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-129">Go to Retail and commerce > Channels > Retail store financials.</span></span>
12. <span data-ttu-id="cf0dc-130">Kattintson a Feladott kimutatások fülre.</span><span class="sxs-lookup"><span data-stu-id="cf0dc-130">Click the Posted statements tab.</span></span>


