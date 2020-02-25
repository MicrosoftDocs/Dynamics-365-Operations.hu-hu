---
title: Kiskereskedelmi üzlet kimutatásainak létrehozása, kiszámítása és feladása
description: Ez az témakör leírja egy üzlet kimutatása létrehozásának, kiszámításának és feladásának manuális lépéseit.
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
ms.openlocfilehash: 3b26ea5c816339eef88bfdd9ac59701dcaa31fe4
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022781"
---
# <a name="create-calculate-and-post-statements-for-a-retail-store"></a><span data-ttu-id="c3a44-103">Kiskereskedelmi üzlet kimutatásainak létrehozása, kiszámítása és feladása</span><span class="sxs-lookup"><span data-stu-id="c3a44-103">Create, calculate, and post statements for a retail store</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="c3a44-104">Ez az témakör leírja egy üzlet kimutatása létrehozásának, kiszámításának és feladásának manuális lépéseit.</span><span class="sxs-lookup"><span data-stu-id="c3a44-104">This topic describes the manual steps for creating, calculating, and posting a statement for a store.</span></span> <span data-ttu-id="c3a44-105">Kötegelt feladatok is léteznek, amelyek ugyanazon eljárásokhoz konfigurálhatók.</span><span class="sxs-lookup"><span data-stu-id="c3a44-105">There are also batch jobs that can be configured for the same tasks.</span></span> <span data-ttu-id="c3a44-106">A kötegelt feladatok konfigurálásának és futtatásának lépései egy másik témakörben találhatók meg.</span><span class="sxs-lookup"><span data-stu-id="c3a44-106">The steps for configuring and running the batch jobs can be found in other topics.</span></span> <span data-ttu-id="c3a44-107">Az eljárás végrehajtásához rendelkeznie kell olyan tranzakciókkal, amelyeket a pénztárban hajtottak végre, majd átvezették a Dynamics 365 Commerce programba.</span><span class="sxs-lookup"><span data-stu-id="c3a44-107">To complete this procedure, you must have transactions that were completed in POS and then pulled into Dynamics 365 Commerce.</span></span> <span data-ttu-id="c3a44-108">Ez a bejegyzés az USRT cég adatait használja, mint bemutatóadatokat.</span><span class="sxs-lookup"><span data-stu-id="c3a44-108">This recording uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="c3a44-109">Válassza ki az **Üzlet pénzügyei** lehetőséget a kezdőlapról.</span><span class="sxs-lookup"><span data-stu-id="c3a44-109">Select **Store financials** from the home page.</span></span>
2. <span data-ttu-id="c3a44-110">Válassza az **Új kimutatás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c3a44-110">Select **New statement**.</span></span>
3. <span data-ttu-id="c3a44-111">Az **Üzlet száma** mezőben válasszon ki egy opciót a legördülő menüben.</span><span class="sxs-lookup"><span data-stu-id="c3a44-111">In the **Store number** field, select a option from the drop-down.</span></span>
4. <span data-ttu-id="c3a44-112">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c3a44-112">Select **OK**.</span></span>
5. <span data-ttu-id="c3a44-113">A **Beállítások** csoportban beállíthatja, hogy mely tranzakciók szerepeljenek a kimutatásban, és hogy azok hogyan legyenek sorokba csoportosítva.</span><span class="sxs-lookup"><span data-stu-id="c3a44-113">The **Setup** group has the settings that control what transactions are included in the statement and how they are grouped into statement lines.</span></span> <span data-ttu-id="c3a44-114">Megnyithatja a **Beállítások** csoportot és megváltoztathatja a beállításokat, vagy használhatja az alapértelmezett beállításokat is.</span><span class="sxs-lookup"><span data-stu-id="c3a44-114">You can open the **Setup** group and change these settings, or you can use the defaults.</span></span>  
    - <span data-ttu-id="c3a44-115">A **Kimutatás módja** mező megadja, hogy a kimutatás sorai hogyan lesznek csoportosítva.</span><span class="sxs-lookup"><span data-stu-id="c3a44-115">The **Statement method** field defines how the statement lines will be grouped.</span></span>  
    - <span data-ttu-id="c3a44-116">Válasszon ki egy munkatársat vagy egy jegyzéket a **munkatárs/jegyzék** mezőben, ha a kimutatást csak egy bizonyos munkatársra vagy jegyzékre vonatkozóan szeretné elkészíteni.</span><span class="sxs-lookup"><span data-stu-id="c3a44-116">Select a staff member or a register in the **staff/register** field if you want to calculate a statement only for the specific staff member or register.</span></span>  
6. <span data-ttu-id="c3a44-117">Válassza ki valamelyik lehetőséget a **Zárási mód** mezőben.</span><span class="sxs-lookup"><span data-stu-id="c3a44-117">In the **Closing method** field, select an option.</span></span>
7. <span data-ttu-id="c3a44-118">Válassza a **Kimutatás számítása** lehetőséget a Művelet alaktábláról.</span><span class="sxs-lookup"><span data-stu-id="c3a44-118">Select **Calculate statement** from the Action Pane.</span></span>
8. <span data-ttu-id="c3a44-119">Válassza ki az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c3a44-119">Select **Yes**.</span></span>
    - <span data-ttu-id="c3a44-120">A kimutatás elkészítése után külön sorokban kell szerepelnie a teljes összegnek minden alkalmazott fizetési mód és kimutatási mód esetén.</span><span class="sxs-lookup"><span data-stu-id="c3a44-120">After calculating the statement, there should be lines created with total amounts for each payment method and statement method that was used.</span></span>  
    - <span data-ttu-id="c3a44-121">Adjon meg egy leszámolt összeget minden sorban, amelyben meg kell adni vagy frissíteni kell az értéket.</span><span class="sxs-lookup"><span data-stu-id="c3a44-121">Enter a counted amount in each line if it needs to be entered or updated.</span></span> <span data-ttu-id="c3a44-122">A leszámolt értéket tartalmazó mező a pénztárban végrehajtott fizetőeszköz-elszámolások során kapott összeggel van kitöltve.</span><span class="sxs-lookup"><span data-stu-id="c3a44-122">The counted field is populated with amounts from tender declarations done in POS.</span></span>  
9. <span data-ttu-id="c3a44-123">Válassza a **Kimutatás feladása** lehetőséget a Művelet alaktábláról.</span><span class="sxs-lookup"><span data-stu-id="c3a44-123">Select **Post statement** from the Action Pane.</span></span>
10. <span data-ttu-id="c3a44-124">Válassza **Bezárás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c3a44-124">Select **Close**.</span></span>
11. <span data-ttu-id="c3a44-125">Zárja be a panelt.</span><span class="sxs-lookup"><span data-stu-id="c3a44-125">Close the pane.</span></span>
12. <span data-ttu-id="c3a44-126">A kezdőlapon válassza ki az **Üzlet pénzügyei** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c3a44-126">At the home page, select **Store financials**.</span></span>
13. <span data-ttu-id="c3a44-127">Kattintson a **Feladott kimutatások** fülre.</span><span class="sxs-lookup"><span data-stu-id="c3a44-127">Select the **Posted statements** tab.</span></span>

