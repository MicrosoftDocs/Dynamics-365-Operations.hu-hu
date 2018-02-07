--- 
title: "Kiskereskedelmi üzlet kimutatásának létrehozása, kiszámítása és feladása"
description: "Ez az eljárás végigveszi egy üzlet kimutatása létrehozásának, kiszámításának és feladásának manuális lépéseit."
author: jashanno
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 33ebb28196baa9ae944dbd124274b05cb587fea4
ms.contentlocale: hu-hu
ms.lasthandoff: 02/07/2018

---
# <a name="create-calculate-and-post-a-statement-for-a-retail-store"></a><span data-ttu-id="e1754-103">Kiskereskedelmi üzlet kimutatásának létrehozása, kiszámítása és feladása</span><span class="sxs-lookup"><span data-stu-id="e1754-103">Create, calculate, and post a statement for a retail store</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="e1754-104">Ez az eljárás végigveszi egy üzlet kimutatása létrehozásának, kiszámításának és feladásának manuális lépéseit.</span><span class="sxs-lookup"><span data-stu-id="e1754-104">This procedure walks through the manual steps for creating, calculating, and posting a statement for a store.</span></span> <span data-ttu-id="e1754-105">Kötegelt feladatok is léteznek, amelyek ugyanazon eljárásokhoz konfigurálhatók.</span><span class="sxs-lookup"><span data-stu-id="e1754-105">There are also batch jobs that can be configured for the same tasks.</span></span> <span data-ttu-id="e1754-106">A kötegelt feladatok konfigurálásának és futtatásának lépései egy másik témakörben találhatók meg.</span><span class="sxs-lookup"><span data-stu-id="e1754-106">The steps for configuring and running the batch jobs can be found in other topics.</span></span> <span data-ttu-id="e1754-107">Az eljárás végrehajtásához rendelkeznie kell olyan tranzakciókkal, amelyeket a pénztárban hajtottak végre, majd átvezették a Dynamics AX programba.</span><span class="sxs-lookup"><span data-stu-id="e1754-107">To complete this procedure, you must have transactions that were completed in POS and then pulled into Dynamics AX.</span></span> <span data-ttu-id="e1754-108">Ez a bejegyzés az USRT cég adatait használja, mint bemutatóadatokat.</span><span class="sxs-lookup"><span data-stu-id="e1754-108">This recording uses the USRT company in demo data.</span></span> <span data-ttu-id="e1754-109">Ez az eljárás a Microsoft Dynamics AX rendszerre vonatkozhat.</span><span class="sxs-lookup"><span data-stu-id="e1754-109">This procedure may refer to Microsoft Dynamics AX.</span></span> <span data-ttu-id="e1754-110">Ne feledje, hogy a Dynamics AX új neve Microsoft Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="e1754-110">Please note that Dynamics AX is now called Microsoft Dynamics 365 for Operations.</span></span>

1. <span data-ttu-id="e1754-111">Lépjen Az összes munkaterület > ..</span><span class="sxs-lookup"><span data-stu-id="e1754-111">Go to All workspaces > ..</span></span> <span data-ttu-id="e1754-112">> Kiskereskedelmi üzlet pénzügyei lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e1754-112">> Retail store financials.</span></span>
2. <span data-ttu-id="e1754-113">Kattintson az Új kimutatás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e1754-113">Click New statement.</span></span>
3. <span data-ttu-id="e1754-114">Az Üzlet száma mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e1754-114">In the Store number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="e1754-115">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e1754-115">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="e1754-116">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="e1754-116">Click OK.</span></span>
    * <span data-ttu-id="e1754-117">A Beállítások csoportban beállíthatja, hogy mely tranzakciók szerepeljenek a kimutatásban, és hogy azok hogyan legyenek sorokba csoportosítva.</span><span class="sxs-lookup"><span data-stu-id="e1754-117">The Setup group has the settings that control what transactions are included in the statement and how they are grouped into statement lines.</span></span> <span data-ttu-id="e1754-118">Megnyithatja a Beállítások csoportot és megváltoztathatja a beállításokat, vagy használhatja az alapértelmezett beállításokat is.</span><span class="sxs-lookup"><span data-stu-id="e1754-118">You can open the Setup group and change these settings, or you can use the defaults.</span></span>  
    * <span data-ttu-id="e1754-119">A Kimutatás módja mező megadja, hogy a kimutatás sorai hogyan lesznek csoportosítva.</span><span class="sxs-lookup"><span data-stu-id="e1754-119">The Statement method field defines how the statement lines will be grouped.</span></span>  
    * <span data-ttu-id="e1754-120">Válasszon ki egy munkatársat vagy egy jegyzéket, ha a kimutatást csak egy bizonyos munkatársra vagy jegyzékre vonatkozóan szeretné elkészíteni.</span><span class="sxs-lookup"><span data-stu-id="e1754-120">Select a staff member or a register if you want to calculate a statement only for the specific staff member or register.</span></span>  
6. <span data-ttu-id="e1754-121">Válassza ki valamelyik lehetőséget a Zárási mód mezőben.</span><span class="sxs-lookup"><span data-stu-id="e1754-121">In the Closing method field, select an option.</span></span>
7. <span data-ttu-id="e1754-122">Kattintson a Kimutatás számítása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e1754-122">Click Calculate statement.</span></span>
8. <span data-ttu-id="e1754-123">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="e1754-123">Click Yes.</span></span>
    * <span data-ttu-id="e1754-124">A kimutatás elkészítése után külön sorokban kell szerepelnie a teljes összegnek minden alkalmazott fizetési mód és kimutatási mód esetén.</span><span class="sxs-lookup"><span data-stu-id="e1754-124">After calculating the statement, there should be lines created with total amounts for each payment method and statement method that was used.</span></span>  
    * <span data-ttu-id="e1754-125">Adjon meg egy leszámolt összeget minden sorban, amelyben meg kell adni vagy frissíteni kell az értéket.</span><span class="sxs-lookup"><span data-stu-id="e1754-125">Enter a counted amount in each line if it needs to be entered or updated.</span></span> <span data-ttu-id="e1754-126">A leszámolt értéket tartalmazó mező a pénztárban végrehajtott fizetőeszköz-elszámolások során kapott összeggel van kitöltve.</span><span class="sxs-lookup"><span data-stu-id="e1754-126">The counted field is populated with amounts from tender declarations done in POS.</span></span>  
9. <span data-ttu-id="e1754-127">Kattintson a Kimutatás feladása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e1754-127">Click Post statement.</span></span>
10. <span data-ttu-id="e1754-128">Kattintson a Bezárás gombra.</span><span class="sxs-lookup"><span data-stu-id="e1754-128">Click Close.</span></span>
11. <span data-ttu-id="e1754-129">Ugorjon a következő oldalra: Kiskereskedelem és kereskedelem > Csatornák > Kiskereskedelmi üzlet pénzügyei.</span><span class="sxs-lookup"><span data-stu-id="e1754-129">Go to Retail and commerce > Channels > Retail store financials.</span></span>
12. <span data-ttu-id="e1754-130">Kattintson a Feladott kimutatások fülre.</span><span class="sxs-lookup"><span data-stu-id="e1754-130">Click the Posted statements tab.</span></span>


