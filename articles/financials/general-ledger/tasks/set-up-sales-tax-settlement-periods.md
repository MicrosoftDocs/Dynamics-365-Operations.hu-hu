--- 
title: "Áfafizetési időszakok beállítása"
description: "Az Áfakiegyenlítési időszakok információval rendelkeznek a periódusokról, hogy melyik áfát kell jelenteni és fizetni."
author: twheeloc
manager: AnnBe
ms.date: 10/15/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 81214cc52b1488bb70ac5fd6ccc817f6f979163d
ms.openlocfilehash: 1087ed78e91b487ca7157bfdac1d72ae3f477875
ms.contentlocale: hu-hu
ms.lasthandoff: 10/16/2018

---
# <a name="set-up-sales-tax-settlement-periods"></a><span data-ttu-id="c85fa-103">Áfafizetési időszakok beállítása</span><span class="sxs-lookup"><span data-stu-id="c85fa-103">Set up sales tax settlement periods</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c85fa-104">Az Áfakiegyenlítési időszakok információval rendelkeznek a periódusokról, hogy melyik áfát kell jelenteni és fizetni.</span><span class="sxs-lookup"><span data-stu-id="c85fa-104">Sales tax settlement periods contain information about the period intervals for which sales tax needs to be reported and paid.</span></span> <span data-ttu-id="c85fa-105">Egy kiegyenlítési folyamat futtatható egy kiegyenlítési időszak megadott intervallumában.</span><span class="sxs-lookup"><span data-stu-id="c85fa-105">A settlement process can be run for a settlement period for a specific date interval.</span></span> <span data-ttu-id="c85fa-106">Minden kiegyenlítési időszakhoz rendelt adókód kiegyenlítésre kerül.</span><span class="sxs-lookup"><span data-stu-id="c85fa-106">All tax codes associated with the settlement period will be settled.</span></span> <span data-ttu-id="c85fa-107">Az érintett Adóhatóság beállításaitól függően az adókötelezettség feladásra kerül a szállítóhoz vagy a Főkönyvi számlához.</span><span class="sxs-lookup"><span data-stu-id="c85fa-107">Depending on the set up of the related Sales tax authority, the tax liability is posted either to a vendor or a General ledger account.</span></span>



<span data-ttu-id="c85fa-108">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="c85fa-108">This task uses the USMF demo company.</span></span>



1. <span data-ttu-id="c85fa-109">Ugrás az Adó > Közvetett adók > Áfa > Áfa kiegyenlítési periódusok elemre.</span><span class="sxs-lookup"><span data-stu-id="c85fa-109">Go to Tax > Indirect taxes > Sales tax > Sales tax settlement periods.</span></span>
2. <span data-ttu-id="c85fa-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c85fa-110">Click New.</span></span>
3. <span data-ttu-id="c85fa-111">Írjon be egy értéket a Kiegyenlítési időszak meghatározása mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c85fa-111">In the Settlement period field, type a value.</span></span>
4. <span data-ttu-id="c85fa-112">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c85fa-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="c85fa-113">A Hatóság mezőben válassza ki azt az adóhatóságot, amely a kifizetési időszakhoz létrehozott jelentéseket és kifizetéseket kapja.</span><span class="sxs-lookup"><span data-stu-id="c85fa-113">In the Authority field, select the sales tax authority that receives the reports and the payments that are created for the settlement period.</span></span>
6. <span data-ttu-id="c85fa-114">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="c85fa-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="c85fa-115">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="c85fa-115">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="c85fa-116">A Fizetési feltételek mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="c85fa-116">In the Terms of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="c85fa-117">Az érintett Adóhatóság beállítható szállítóként és az Áfakiegyenlítés nyitott szállítói számlát hoz létre.</span><span class="sxs-lookup"><span data-stu-id="c85fa-117">The related Sales tax authority can be set up as a vendor and the Sales tax settlement will create an open vendor invoice.</span></span> <span data-ttu-id="c85fa-118">A Fizetés feltételei meghatározzák a Határidőt nyitott szállítói számla esetén.</span><span class="sxs-lookup"><span data-stu-id="c85fa-118">The Terms of payment defines the Due date for the open vendor invoice.</span></span>  
9. <span data-ttu-id="c85fa-119">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="c85fa-119">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="c85fa-120">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="c85fa-120">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="c85fa-121">Válasszon a kiegyenlítési időszakok időtartamaihoz egy típust.</span><span class="sxs-lookup"><span data-stu-id="c85fa-121">Select a type for the settlement period intervals.</span></span>
12. <span data-ttu-id="c85fa-122">Adja meg a Periódus időtartam egységek periódusokra vonatkoztatott számát.</span><span class="sxs-lookup"><span data-stu-id="c85fa-122">Enter the number of Period interval units per period.</span></span> <span data-ttu-id="c85fa-123">Például egy negyedév 3 hónapból áll.</span><span class="sxs-lookup"><span data-stu-id="c85fa-123">For example, a quarter has 3 months.</span></span>
13. <span data-ttu-id="c85fa-124">Jelölje be, vagy törölje a Kötegfolyamat használata forgalmi adó kiegyenlítéshez jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="c85fa-124">Select or clear the Use batch processing for sales tax settlement check box.</span></span>
    * <span data-ttu-id="c85fa-125">A kiegyenlítési időszakhoz tartozó kiegyenlítési folyamat kötegelt feladatként feldolgozható a háttérben.</span><span class="sxs-lookup"><span data-stu-id="c85fa-125">The settlement process for the settlement period can be processed as batch job in the background.</span></span> <span data-ttu-id="c85fa-126">Ez adott időszakban nagyszámú adótranzakcióhoz ajánlott.</span><span class="sxs-lookup"><span data-stu-id="c85fa-126">This is recommended for a large number of tax transactions within a period interval.</span></span>  
14. <span data-ttu-id="c85fa-127">Válassza ki, vagy törölje a jelölést Az ellenoldali adótranzakciók létrehozásának megakadályozása jelölőnégyzetből.</span><span class="sxs-lookup"><span data-stu-id="c85fa-127">Select or clear the Prevent generating offset tax transactions check box.</span></span>
    * <span data-ttu-id="c85fa-128">Alapértelmezés szerint a rendszer létrehozza az ellenoldali adótranzakciókat a kiegyenlítési folyamat során, amely teljesítményproblémákat, okozhat ha nagy számú adótranzakciók van egy időintervallumon belül.</span><span class="sxs-lookup"><span data-stu-id="c85fa-128">By default, the system generates offset tax transactions during the settlement process, which cause can performance issue if there are a large number of tax transactions within a period interval.</span></span> <span data-ttu-id="c85fa-129">Jelölje be ezt a jelölőnégyzetet ellenoldali adótranzakciók létrehozásának megakadályozásához.</span><span class="sxs-lookup"><span data-stu-id="c85fa-129">Select this check box to prevent generating offset tax transactions.</span></span>
15. <span data-ttu-id="c85fa-130">Bontsa ki az Időszak időtartamai fület.</span><span class="sxs-lookup"><span data-stu-id="c85fa-130">Expand the Period intervals tab.</span></span>
16. <span data-ttu-id="c85fa-131">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="c85fa-131">Click Add.</span></span>
17. <span data-ttu-id="c85fa-132">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="c85fa-132">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="c85fa-133">Adjon meg egy dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="c85fa-133">In the From date field, enter a date.</span></span>
19. <span data-ttu-id="c85fa-134">Adja meg a dátumot a „Záró dátum” mezőben.</span><span class="sxs-lookup"><span data-stu-id="c85fa-134">In the To date field, enter a date.</span></span>
20. <span data-ttu-id="c85fa-135">Kattintson az Új időszak intervalluma.</span><span class="sxs-lookup"><span data-stu-id="c85fa-135">Click New period interval.</span></span>
    * <span data-ttu-id="c85fa-136">Amint megadta az első intervallumot az új időszakok automatikusan létrejönnek.</span><span class="sxs-lookup"><span data-stu-id="c85fa-136">Once the first period interval has been entered, new periods can be created automatically.</span></span> <span data-ttu-id="c85fa-137">Visszatérhet és szükség szerint új intervallumokat adhat hozzá.</span><span class="sxs-lookup"><span data-stu-id="c85fa-137">You can come back and add new period intervals as required.</span></span>  
21. <span data-ttu-id="c85fa-138">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c85fa-138">Close the page.</span></span>


