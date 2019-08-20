---
title: Előzetes költségvetés létrehozása az állami szektor részére
description: Egy adott költségvetési modellre és dimenzió értékekre létrehozhat előzetes költségvetési tételjegyzék-bejegyzéseket.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetTransaction, BudgetAccountStructureLookup, BudgetTransactionMultiPost
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 800b7009f023bd2a0d8437b81d82c0e9de770841
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1836015"
---
# <a name="create-a-preliminary-budget-for-public-sector"></a><span data-ttu-id="ee5cb-103">Előzetes költségvetés létrehozása az állami szektor részére</span><span class="sxs-lookup"><span data-stu-id="ee5cb-103">Create a preliminary budget for Public sector</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ee5cb-104">Egy adott költségvetési modellre és dimenzió értékekre létrehozhat előzetes költségvetési tételjegyzék-bejegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-104">You can create preliminary budget register entries for a specific budget model and dimension values.</span></span> <span data-ttu-id="ee5cb-105">A tényleges költségvetés jóváhagyása után létrehozhat eredeti költségvetési tételjegyzék-bejegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-105">After the actual budget is approved, you can create original budget register entries.</span></span> <span data-ttu-id="ee5cb-106">Ez az eljárás az állami szektor partícióban lévő PSUS bemutató vállalati adatok használatával készült.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-106">This procedure was created using the PSUS demo company data in the public sector partition.</span></span>

1. <span data-ttu-id="ee5cb-107">Ugorjon a Költségvetés > Költségvetési tételjegyzék-bejegyzések pontra.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-107">Go to Budgeting > Budget register entries.</span></span>
2. <span data-ttu-id="ee5cb-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-108">Click New.</span></span>
3. <span data-ttu-id="ee5cb-109">A Költségvetési modell mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-109">In the Budget model field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="ee5cb-110">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="ee5cb-110">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="ee5cb-111">A Költségvetési kód mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-111">In the Budget code field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="ee5cb-112">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="ee5cb-112">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="ee5cb-113">Az Okkód mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-113">In the Reason code field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="ee5cb-114">A listában kattintson a kívánt rekordra.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-114">In the list, click the desired record.</span></span>
9. <span data-ttu-id="ee5cb-115">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-115">Click Save.</span></span>
10. <span data-ttu-id="ee5cb-116">Kattintson az Új sor hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-116">Click Add line.</span></span>
    * <span data-ttu-id="ee5cb-117">Választható: Ha módosítani kívánja a dátumot a fejlécben beállítotthoz képest, adjon meg egy új dátumot.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-117">Optional: If you want to change the date from the one in the header, enter a new date.</span></span> <span data-ttu-id="ee5cb-118">Ez a dátum határozza meg azt a pénzügyi időszakot, amelyre a költségvetés rögzítésre kerül.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-118">This date determines the fiscal period that the budget will be recorded to.</span></span> <span data-ttu-id="ee5cb-119">A feladat útmutató megtekintésekor a többi mező kitöltéséhez kattintson az oldal tetején a Feloldás gombra.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-119">When viewing the task guide, to fill out other fields, click Unlock at the top of the page.</span></span>  
11. <span data-ttu-id="ee5cb-120">A Számlastruktúra mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-120">In the Account structure field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="ee5cb-121">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="ee5cb-121">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="ee5cb-122">A Dimenzióértékek mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-122">In the Dimension values field, specify the desired values.</span></span>
14. <span data-ttu-id="ee5cb-123">Az Összeg mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-123">In the Amount field, enter a number.</span></span>
    * <span data-ttu-id="ee5cb-124">Az összeg típusa is megadható.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-124">You can also enter an amount type.</span></span>  
15. <span data-ttu-id="ee5cb-125">A Pénznem mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-125">In the Currency field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="ee5cb-126">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-126">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="ee5cb-127">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-127">Click Save.</span></span>
18. <span data-ttu-id="ee5cb-128">Kattintson a Költségvetési egyenlegek frissítése gombra.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-128">Click Update budget balances.</span></span>
19. <span data-ttu-id="ee5cb-129">Kattintson a Módosítás gombra.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-129">Click Update.</span></span>
    * <span data-ttu-id="ee5cb-130">A frissítés eredményeinek megtekintéséhez kattintson a kék sávon az Üzenetadatok gombra.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-130">To see the results of the update, click Message details on the blue bar.</span></span>  

