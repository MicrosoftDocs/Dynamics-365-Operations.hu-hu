--- 
title: "Áfafizetési időszakok beállítása"
description: "Az Áfakiegyenlítési időszakok információval rendelkeznek a periódusokról, hogy melyik áfát kell jelenteni és fizetni."
author: twheeloc
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: fcf4ebcb8a9c27961e250177d4254f28aaefc883
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="set-up-sales-tax-settlement-periods"></a><span data-ttu-id="f5ee4-103">Áfafizetési időszakok beállítása</span><span class="sxs-lookup"><span data-stu-id="f5ee4-103">Set up sales tax settlement periods</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f5ee4-104">Az Áfakiegyenlítési időszakok információval rendelkeznek a periódusokról, hogy melyik áfát kell jelenteni és fizetni.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-104">Sales tax settlement periods contain information about the period intervals for which sales tax needs to be reported and paid.</span></span> <span data-ttu-id="f5ee4-105">Egy kiegyenlítési folyamat futtatható egy kiegyenlítési időszak megadott intervallumában.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-105">A settlement process can be run for a settlement period for a specific date interval.</span></span> <span data-ttu-id="f5ee4-106">Minden kiegyenlítési időszakhoz rendelt adókód kiegyenlítésre kerül.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-106">All tax codes associated with the settlement period will be settled.</span></span> <span data-ttu-id="f5ee4-107">Az érintett Adóhatóság beállításaitól függően az adókötelezettség feladásra kerül a szállítóhoz vagy a Főkönyvi számlához.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-107">Depending on the set up of the related Sales tax authority, the tax liability is posted either to a vendor or a General ledger account.</span></span>



<span data-ttu-id="f5ee4-108">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-108">This task uses the USMF demo company.</span></span>



1. <span data-ttu-id="f5ee4-109">Ugrás az Adó > Közvetett adók > Áfa > Áfa kiegyenlítési periódusok elemre.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-109">Go to Tax > Indirect taxes > Sales tax > Sales tax settlement periods.</span></span>
2. <span data-ttu-id="f5ee4-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-110">Click New.</span></span>
3. <span data-ttu-id="f5ee4-111">Írjon be egy értéket a Kiegyenlítési időszak meghatározása mezőbe.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-111">In the Settlement period field, type a value.</span></span>
4. <span data-ttu-id="f5ee4-112">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="f5ee4-113">A Hatóság mezőben válassza ki azt az adóhatóságot, amely a kifizetési időszakhoz létrehozott jelentéseket és kifizetéseket kapja.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-113">In the Authority field, select the sales tax authority that receives the reports and the payments that are created for the settlement period.</span></span>
6. <span data-ttu-id="f5ee4-114">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="f5ee4-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="f5ee4-115">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-115">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="f5ee4-116">A Fizetési feltételek mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-116">In the Terms of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="f5ee4-117">Az érintett Adóhatóság beállítható szállítóként és az Áfakiegyenlítés nyitott szállítói számlát hoz létre.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-117">The related Sales tax authority can be set up as a vendor and the Sales tax settlement will create an open vendor invoice.</span></span> <span data-ttu-id="f5ee4-118">A Fizetés feltételei meghatározzák a Határidőt nyitott szállítói számla esetén.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-118">The Terms of payment defines the Due date for the open vendor invoice.</span></span>  
9. <span data-ttu-id="f5ee4-119">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-119">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="f5ee4-120">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-120">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="f5ee4-121">Válasszon a kiegyenlítési időszakok időtartamaihoz egy típust.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-121">Select a type for the settlement period intervals.</span></span>
12. <span data-ttu-id="f5ee4-122">Adja meg a Periódus időtartam egységek periódusokra vonatkoztatott számát.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-122">Enter the number of Period interval units per period.</span></span> <span data-ttu-id="f5ee4-123">Például egy negyedév 3 hónapból áll.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-123">For example, a quarter has 3 months.</span></span>
13. <span data-ttu-id="f5ee4-124">Jelölje be, vagy törölje a Kötegfolyamat használata forgalmi adó kiegyenlítéshez jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-124">Select or clear the Use batch processing for sales tax settlement check box.</span></span>
    * <span data-ttu-id="f5ee4-125">A kiegyenlítési időszakhoz tartozó kiegyenlítési folyamat kötegelt feladatként feldolgozható a háttérben.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-125">The settlement process for the settlement period can be processed as batch job in the background.</span></span> <span data-ttu-id="f5ee4-126">Ez adott időszakban nagyszámú adótranzakcióhoz ajánlott.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-126">This is recommended for a large number of tax transactions within a period interval.</span></span>  
14. <span data-ttu-id="f5ee4-127">Bontsa ki az Időszak időtartamai fület.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-127">Expand the Period intervals tab.</span></span>
15. <span data-ttu-id="f5ee4-128">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-128">Click Add.</span></span>
16. <span data-ttu-id="f5ee4-129">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-129">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="f5ee4-130">Adjon meg egy
Adjon meg egy dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-130">In the From date field, enter a date.</span></span>
18. <span data-ttu-id="f5ee4-131">Adja meg a dátumot a „Záró dátum” mezőben.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-131">In the To date field, enter a date.</span></span>
19. <span data-ttu-id="f5ee4-132">Kattintson az Új időszak intervalluma.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-132">Click New period interval.</span></span>
    * <span data-ttu-id="f5ee4-133">Amint megadta az első intervallumot az új időszakok automatikusan létrejönnek.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-133">Once the first period interval has been entered, new periods can be created automatically.</span></span> <span data-ttu-id="f5ee4-134">Visszatérhet és szükség szerint új intervallumokat adhat hozzá.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-134">You can come back and add new period intervals as required.</span></span>  
20. <span data-ttu-id="f5ee4-135">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="f5ee4-135">Close the page.</span></span>


