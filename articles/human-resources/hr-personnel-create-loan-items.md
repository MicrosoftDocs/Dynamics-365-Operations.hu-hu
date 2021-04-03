---
title: Kölcsöncikkek létrehozása
description: A kölcsöncikkek olyan rekordok, amelyek segítik követni a dolgozóknak kölcsönzött fizikai cikkeket, például telefonokat vagy számítógépeket.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmLoanType, DefaultDashboard, HcmLoanItem, HcmWorkerLookUp, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5b93f68790a72af28130d80ed189538f9c5c87ab
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467102"
---
# <a name="create-loan-items"></a><span data-ttu-id="6c213-103">Kölcsöncikkek létrehozása</span><span class="sxs-lookup"><span data-stu-id="6c213-103">Create loan items</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



<span data-ttu-id="6c213-104">A kölcsöncikkek olyan rekordok, amelyek segítik követni a dolgozóknak kölcsönzött fizikai cikkeket, például telefonokat vagy számítógépeket.</span><span class="sxs-lookup"><span data-stu-id="6c213-104">Loan items are records that help you track physical items, such as phones or computers, that your company lends to workers.</span></span> <span data-ttu-id="6c213-105">Minden fizikai cikknek rendelkeznie kell egy megfelelő kölcsöncikkel.</span><span class="sxs-lookup"><span data-stu-id="6c213-105">Each physical item must have a corresponding loan item.</span></span> <span data-ttu-id="6c213-106">Minden kölcsöncikk rekordnál le kell írni a kölcsönzött tételt, meg kell adni a kölcsönzésért felelős személyt, és a tétel kölcsönzési idejét (napokban).</span><span class="sxs-lookup"><span data-stu-id="6c213-106">Each loan item record should describe what is being loaned, who is responsible for the loan, and the number of days the item can be on loan.</span></span> <span data-ttu-id="6c213-107">Ezzel egy időben több kölcsöncikk, például kulcsok, belépőkártyák vagy egyenruhák is létrehozhatók.</span><span class="sxs-lookup"><span data-stu-id="6c213-107">You can create multiple loan items, such as keys, access cards, or uniforms, at the same time.</span></span> <span data-ttu-id="6c213-108">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="6c213-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-loan-types"></a><span data-ttu-id="6c213-109">Kölcsöntípus létrehozása</span><span class="sxs-lookup"><span data-stu-id="6c213-109">Create Loan types</span></span>
1. <span data-ttu-id="6c213-110">Ugorjon az Emberi erőforrások > Dolgozók > Kölcsöncikkek > Kölcsöntípusok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6c213-110">Go to Human resources > Workers > Loan items > Loan types.</span></span>
2. <span data-ttu-id="6c213-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6c213-111">Click New.</span></span>
3. <span data-ttu-id="6c213-112">Írjon be egy értéket a Kölcsön típusa mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6c213-112">In the Loan type field, type a value.</span></span>
4. <span data-ttu-id="6c213-113">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6c213-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="6c213-114">Adja meg azon napok számát, ahány nappal túlléphető a határidő az e kölcsöntípushoz rendelt cikkek esetében.</span><span class="sxs-lookup"><span data-stu-id="6c213-114">Enter the number of days that items assigned to this loan type can be overdue.</span></span> 
6. <span data-ttu-id="6c213-115">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="6c213-115">Click Save.</span></span>
7. <span data-ttu-id="6c213-116">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6c213-116">Close the page.</span></span>
8. <span data-ttu-id="6c213-117">Frissítse a lapot..</span><span class="sxs-lookup"><span data-stu-id="6c213-117">Refresh the page.</span></span>

## <a name="create-loan-items"></a><span data-ttu-id="6c213-118">Kölcsöncikkek létrehozása</span><span class="sxs-lookup"><span data-stu-id="6c213-118">Create Loan items</span></span>
1. <span data-ttu-id="6c213-119">Ugorjon az Emberi erőforrások > Dolgozók > Kölcsöncikkek > Kölcsöncikkek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6c213-119">Go to Human resources > Workers > Loan items > Loan items.</span></span>
2. <span data-ttu-id="6c213-120">Kattintson a Kölcsöncikk létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6c213-120">Click Create loan items.</span></span>
3. <span data-ttu-id="6c213-121">A menny. mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="6c213-121">In the Qty. field, enter a number.</span></span>
4. <span data-ttu-id="6c213-122">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6c213-122">In the Description field, type a value.</span></span>
5. <span data-ttu-id="6c213-123">A Kölcsön típusa mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="6c213-123">In the Loan type field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="6c213-124">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="6c213-124">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="6c213-125">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="6c213-125">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="6c213-126">Adja meg, hogy hány napra kölcsönözhető a cikk.</span><span class="sxs-lookup"><span data-stu-id="6c213-126">Enter the number of days the item can be on loan.</span></span>
    * <span data-ttu-id="6c213-127">A Kölcsönzött felszerelés oldal Tervezett visszakerülés mezőjének alapértelmezés szerinti értékét a rendszer az aktuális dátumból, plusz ebből a számból számítja ki.</span><span class="sxs-lookup"><span data-stu-id="6c213-127">The default value for the Planned return field on the Loaned equipment page is calculated as the current date plus this number.</span></span>  
9. <span data-ttu-id="6c213-128">A Felelős személy mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="6c213-128">In the Person in charge field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="6c213-129">Kattintson a Kiválasztás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6c213-129">Click Select.</span></span>
11. <span data-ttu-id="6c213-130">A Kezdőérték mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="6c213-130">In the Starting value field, enter a number.</span></span>
12. <span data-ttu-id="6c213-131">Az Intervallum mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="6c213-131">In the Interval field, enter a number.</span></span>
13. <span data-ttu-id="6c213-132">A Formátum mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6c213-132">In the Format field, type a value.</span></span>
    * <span data-ttu-id="6c213-133">Ha például a kölcsöncikk kezdőszáma 10, akkor két számszimbólumot kell beírni a Formátum mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6c213-133">For example, if the starting number for a loan item is 10, enter two number symbols symbols in the Format field.</span></span>  
14. <span data-ttu-id="6c213-134">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="6c213-134">Click OK.</span></span>
15. <span data-ttu-id="6c213-135">Frissítse a lapot..</span><span class="sxs-lookup"><span data-stu-id="6c213-135">Refresh the page.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]