---
title: Dolgozók juttatásainak felvétele és eltávolítása
description: Ez az eljárás bemutatja, hogyan lehet egyetlen dolgozót besorolni egy vagy több juttatáshoz, valamint több dolgozó egyetlen juttatáshoz.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmWorker, HcmWorkerEnrollment, HcmBenefitByEligibilityLookup, HcmMassBenefitEnrollment, HcmBenefitLookup, HcmMassBenefitEnrollmentResults
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: 2e150032eb4c620a883520a2b24b74c66fca1fb4
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009345"
---
# <a name="enroll-and-remove-benefits-from-workers"></a><span data-ttu-id="22a66-103">Dolgozók juttatásainak felvétele és eltávolítása</span><span class="sxs-lookup"><span data-stu-id="22a66-103">Enroll and remove benefits from workers</span></span>



<span data-ttu-id="22a66-104">Ez az eljárás bemutatja, hogyan lehet egyetlen dolgozót besorolni egy vagy több juttatáshoz, valamint több dolgozó egyetlen juttatáshoz.</span><span class="sxs-lookup"><span data-stu-id="22a66-104">This procedure demonstrates how a single worker can be enrolled in one or more benefits, as well as multiple workers can be enrolled in a benefit.</span></span> <span data-ttu-id="22a66-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="22a66-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="enroll-a-single-worker-in-benefits"></a><span data-ttu-id="22a66-106">Egyetlen munkavállaló felvétele juttatási programba</span><span class="sxs-lookup"><span data-stu-id="22a66-106">Enroll a single worker in benefits</span></span>
1. <span data-ttu-id="22a66-107">Ugorjon az Emberi erőforrások > Dolgozók > Alkalmazottak pontra.</span><span class="sxs-lookup"><span data-stu-id="22a66-107">Go to Human resources > Workers > Employees</span></span>
2. <span data-ttu-id="22a66-108">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="22a66-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="22a66-109">Kattintson a Juttatások lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="22a66-109">Click Benefits.</span></span>
4. <span data-ttu-id="22a66-110">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="22a66-110">Click New.</span></span>
5. <span data-ttu-id="22a66-111">A Juttatás mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="22a66-111">In the Benefit field, enter or select a value.</span></span>
6. <span data-ttu-id="22a66-112">A Fedezet kezdő dátuma mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="22a66-112">In the Coverage start date field, enter a date and time.</span></span>
7. <span data-ttu-id="22a66-113">A Fedezet záró dátuma mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="22a66-113">In the Coverage end date field, enter a date and time.</span></span>
8. <span data-ttu-id="22a66-114">Bontsa ki a Kedvezményezettek szakaszt, ha a juttatáshoz kedvezményezetteket kell hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="22a66-114">Expand the Beneficiaries section if beneficiaries need to be added to the benefit.</span></span> <span data-ttu-id="22a66-115">Függő feleket is felvehet ezen az oldalon, ha ez alkalmazható a juttatás esetében.</span><span class="sxs-lookup"><span data-stu-id="22a66-115">You can also add dependents from this page if applicable to the benefit.</span></span>
9. <span data-ttu-id="22a66-116">Ezen a lapon szerkesztheti a juttatásban való részesítés adatait vagy törölheti őket.</span><span class="sxs-lookup"><span data-stu-id="22a66-116">You can also edit the details of a benefit enrollment or delete an enrollment on this page.</span></span> <span data-ttu-id="22a66-117">Amikor befejezte a juttatásban való részesítés módosítását, zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="22a66-117">When you have finished making changes to the benefit enrollment, close the page.</span></span>

## <a name="enroll-multiple-workers-in-a-benefit"></a><span data-ttu-id="22a66-118">Több dolgozók felvétele juttatási programba</span><span class="sxs-lookup"><span data-stu-id="22a66-118">Enroll multiple workers in a benefit</span></span>
1. <span data-ttu-id="22a66-119">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="22a66-119">Close the page.</span></span>
2. <span data-ttu-id="22a66-120">Ugorjon az Emberi erőforrások > Dolgozók > Alkalmazottak pontra.</span><span class="sxs-lookup"><span data-stu-id="22a66-120">Go to Human resources > Workers > Employees</span></span>
3. <span data-ttu-id="22a66-121">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="22a66-121">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="22a66-122">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="22a66-122">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="22a66-123">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="22a66-123">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="22a66-124">Kattintson a Juttatás felvétele elemre.</span><span class="sxs-lookup"><span data-stu-id="22a66-124">Click Enroll in benefits.</span></span>
7. <span data-ttu-id="22a66-125">A Juttatás mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="22a66-125">In the Benefit field, enter or select a value.</span></span>
8. <span data-ttu-id="22a66-126">A Fedezet kezdő dátuma mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="22a66-126">In the Coverage start date field, enter a date and time.</span></span>
9. <span data-ttu-id="22a66-127">A Fedezet záró dátuma mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="22a66-127">In the Coverage end date field, enter a date and time.</span></span>
10. <span data-ttu-id="22a66-128">Kattintson a felvétel elemre.</span><span class="sxs-lookup"><span data-stu-id="22a66-128">Click Enroll.</span></span>
11. <span data-ttu-id="22a66-129">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="22a66-129">Close the page.</span></span>
12. <span data-ttu-id="22a66-130">Ugorjon az Emberi erőforrások > Juttatások > Besorolás > Juttatásbesorolás eredménye pontra.</span><span class="sxs-lookup"><span data-stu-id="22a66-130">Go to Human Resources > Benefits > Enrollment > Benefit enrollment results</span></span>
13. <span data-ttu-id="22a66-131">Keresse meg a kívánt juttatáseredmények rekordot.</span><span class="sxs-lookup"><span data-stu-id="22a66-131">Find the benefit results record that you are looking for.</span></span>
14. <span data-ttu-id="22a66-132">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="22a66-132">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="22a66-133">Ezen az oldalon megtekinthető, hogy mely alkalmazottakat lettek besorolva a juttatáshoz, illetve azokat is, akik nem lettek besorolva.</span><span class="sxs-lookup"><span data-stu-id="22a66-133">This page allows you to view which employees have been enrolled in the benefit, as well as any employees who were not enrolled.</span></span>

