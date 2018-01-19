--- 
title: " Dolgozó konfigurálása"
description: "Ez az eljárás bemutatja, hogyan konfigurálhatja a kiskereskedelmi dolgozót pénztári eladási jutalékra jogosult üzletkötőként."
author: jblucher
manager: AnnBe
ms.date: 02/22/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: 721c075aa7bbe9d1ed439a84cae907e3db3aafa8
ms.contentlocale: hu-hu
ms.lasthandoff: 01/19/2018

---
# <a name="configure-a-worker"></a><span data-ttu-id="11fa1-103"> Dolgozó konfigurálása</span><span class="sxs-lookup"><span data-stu-id="11fa1-103">Configure a worker</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="11fa1-104">Ez az eljárás bemutatja, hogyan konfigurálhatja a kiskereskedelmi dolgozót pénztári eladási jutalékra jogosult üzletkötőként.</span><span class="sxs-lookup"><span data-stu-id="11fa1-104">This procedure demonstrates how to configure a retail worker as a sales representative who is eligible for commission on sales in POS.</span></span> <span data-ttu-id="11fa1-105">Ez az eljárás az USRT bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="11fa1-105">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-commission-sales-group-for-the-worker"></a><span data-ttu-id="11fa1-106">Jutalék értékesítési csoportjának létrehozása a dolgozóhoz</span><span class="sxs-lookup"><span data-stu-id="11fa1-106">Create a commission sales group for the worker</span></span>
1. <span data-ttu-id="11fa1-107">Ugrás a Értékesítés és marketing> Jutalékok > Érékesítési csoportok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="11fa1-107">Go to Sales and marketing > Commissions > Sales groups.</span></span>
    * <span data-ttu-id="11fa1-108">A dolgozók egy vagy több értékesítési csoporthoz rendelhetők.</span><span class="sxs-lookup"><span data-stu-id="11fa1-108">Workers can be assigned to one or more sales groups.</span></span> <span data-ttu-id="11fa1-109">A pénztárban lehetőség van bármely értékesítési csoport kiválasztására, amely az áruház címjegyzékében megtalálható dolgozókat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="11fa1-109">In POS, you can choose any sales group that contains workers from the store's address book.</span></span>  
2. <span data-ttu-id="11fa1-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="11fa1-110">Click New.</span></span>
3. <span data-ttu-id="11fa1-111">Érték beírása a Csoport mezőbe.</span><span class="sxs-lookup"><span data-stu-id="11fa1-111">In the Group field, type a value.</span></span>
4. <span data-ttu-id="11fa1-112">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="11fa1-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="11fa1-113">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="11fa1-113">Click Save.</span></span>
6. <span data-ttu-id="11fa1-114">A Művelet panelen kattintson az Általános elemre.</span><span class="sxs-lookup"><span data-stu-id="11fa1-114">On the Action Pane, click General.</span></span>
7. <span data-ttu-id="11fa1-115">Kattintson az Üzletkötő lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="11fa1-115">Click Sales rep.</span></span>
    * <span data-ttu-id="11fa1-116">Az értékesítési csoport több dolgozót is tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="11fa1-116">A sales group can contain more than one worker.</span></span> <span data-ttu-id="11fa1-117">A jutalékok feloszthatók a dolgozók között attól függően, hogyan határozza meg jutalékok felosztását.</span><span class="sxs-lookup"><span data-stu-id="11fa1-117">Commissions can be split between workers based on how you define the commission share.</span></span>  
8. <span data-ttu-id="11fa1-118">A Név mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="11fa1-118">In the Name field, enter or select a value.</span></span>
9. <span data-ttu-id="11fa1-119">Adjon meg egy számot a Jutalékfelosztások mezőben.</span><span class="sxs-lookup"><span data-stu-id="11fa1-119">In the Commission share field, enter a number.</span></span>
10. <span data-ttu-id="11fa1-120">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="11fa1-120">Click Save.</span></span>
11. <span data-ttu-id="11fa1-121">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="11fa1-121">Close the page.</span></span>
12. <span data-ttu-id="11fa1-122">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="11fa1-122">Close the page.</span></span>

## <a name="assign-the-workers-default-sales-group"></a><span data-ttu-id="11fa1-123">A dolgozók alapértelmezett értékesítési csoportjának hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="11fa1-123">Assign the workers default sales group</span></span>
1. <span data-ttu-id="11fa1-124">Nyissa meg a következőt: Kiskereskedelem és kereskedelem > Alkalmazottak > Dolgozók.</span><span class="sxs-lookup"><span data-stu-id="11fa1-124">Go to Retail and commerce > Employees > Workers.</span></span>
2. <span data-ttu-id="11fa1-125">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="11fa1-125">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="11fa1-126">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="11fa1-126">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="11fa1-127">Kattintson a Kiskereskedelem fülre.</span><span class="sxs-lookup"><span data-stu-id="11fa1-127">Click the Retail tab.</span></span>
    * <span data-ttu-id="11fa1-128">A dolgozók hozzárendelhetők egy alapértelmezett értékesítési csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="11fa1-128">A worker can be assigned to a default sales group.</span></span> <span data-ttu-id="11fa1-129">Az alapértelmezett értékesítési csoport automatikusan hozzáadódik a pénztár eladási soraihoz, ha a beállítás engedélyezve van az üzlet funkcióprofiljában.</span><span class="sxs-lookup"><span data-stu-id="11fa1-129">The default sales group will be automatically added to sales lines in POS if the option is enabled in the functionality profile for the store.</span></span>  
5. <span data-ttu-id="11fa1-130">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="11fa1-130">Click Edit.</span></span>
6. <span data-ttu-id="11fa1-131">Adjon meg vagy válasszon ki egy értéket az Alapértelmezett csoport mezőben.</span><span class="sxs-lookup"><span data-stu-id="11fa1-131">In the Default group field, enter or select a value.</span></span>
7. <span data-ttu-id="11fa1-132">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="11fa1-132">Click Save.</span></span>


