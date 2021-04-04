---
title: Juttatási jogosultság feldolgozása
description: Ez az eljárással bemutatja, hogyan működik a juttatásjogosultsági folyamat.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: 3720adf26d2cb942bc5d9f6988641bf5e504a852
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465126"
---
# <a name="benefit-eligibility-process"></a><span data-ttu-id="e24d3-103">Juttatási jogosultság feldolgozása</span><span class="sxs-lookup"><span data-stu-id="e24d3-103">Benefit eligibility process</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="e24d3-104">Ez az eljárással bemutatja, hogyan működik a juttatásjogosultsági folyamat.</span><span class="sxs-lookup"><span data-stu-id="e24d3-104">This procedure shows how the benefit eligibility process works.</span></span> <span data-ttu-id="e24d3-105">A folyamat befejeztével megtekintheti az eredményt.</span><span class="sxs-lookup"><span data-stu-id="e24d3-105">When the process is complete you can view the results.</span></span> <span data-ttu-id="e24d3-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="e24d3-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="e24d3-107">Ugorjon az Emberi erőforrások > Juttatások > Juttatások pontra.</span><span class="sxs-lookup"><span data-stu-id="e24d3-107">Go to Human resources > Benefits > Benefits.</span></span>
2. <span data-ttu-id="e24d3-108">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="e24d3-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="e24d3-109">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e24d3-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="e24d3-110">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e24d3-110">Click Edit.</span></span>
5. <span data-ttu-id="e24d3-111">Az Alkalmazhatóság mezőben válassza ki a „Szabályalapú” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e24d3-111">In the Eligibility field, select 'Rule based'.</span></span>
6. <span data-ttu-id="e24d3-112">A Szabály típusa mezőben válassza ki a juttatási irányelvszabály, amelyet alkalmazni szeretne a juttatásra.</span><span class="sxs-lookup"><span data-stu-id="e24d3-112">In the Rule type field, select the benefit policy rule you would like applied to the benefit.</span></span>
7. <span data-ttu-id="e24d3-113">A Műveleti ablaktáblán kattintson a Juttatás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e24d3-113">On the Action Pane, click Benefit.</span></span>
8. <span data-ttu-id="e24d3-114">A Jogosultsági esemény létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="e24d3-114">Click Create eligibility event to open the drop dialog.</span></span>
9. <span data-ttu-id="e24d3-115">Írjon be egy értéket az Esemény típusa mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e24d3-115">In the Event field, type a value.</span></span>
10. <span data-ttu-id="e24d3-116">Írjon egy értéket a „Leírás” mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e24d3-116">In the Description field, type a value.</span></span>
11. <span data-ttu-id="e24d3-117">Válasszon a „Felvétel megnyitása” lehetőséget az Eseménytípus mezőben.</span><span class="sxs-lookup"><span data-stu-id="e24d3-117">In the Event type field, select 'Open enrollment'.</span></span>
12. <span data-ttu-id="e24d3-118">A Fedezet kezdő dátuma mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="e24d3-118">In the Coverage start date field, enter a date and time.</span></span>
13. <span data-ttu-id="e24d3-119">A Felvétel kezdő dátuma mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="e24d3-119">In the Enrollment period start date field, enter a date and time.</span></span>
14. <span data-ttu-id="e24d3-120">Adjon meg egy számot a Napok a felvétekig mezőben.</span><span class="sxs-lookup"><span data-stu-id="e24d3-120">In the Days to enroll field, enter a number.</span></span>
15. <span data-ttu-id="e24d3-121">Kattintson az esemény létrehozása elemre.</span><span class="sxs-lookup"><span data-stu-id="e24d3-121">Click Create event.</span></span>
16. <span data-ttu-id="e24d3-122">Kattintson a Hozzáadás elemre a Dolgozók gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="e24d3-122">Click Add in the Workers FastTab.</span></span>
17. <span data-ttu-id="e24d3-123">A Mutatás típus szerint mezőben válassza a „Dolgozók” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e24d3-123">In the Show by type field, select 'Employees'.</span></span>
18. <span data-ttu-id="e24d3-124">A Mutatás jogi személy szerint mezben válassza az „Aktuális Jogi személy” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e24d3-124">In the Show by legal entity field, select 'Current legal entity'.</span></span>
19. <span data-ttu-id="e24d3-125">A listában jelölje meg az összes sort, vagy törölje a jelölésüket.</span><span class="sxs-lookup"><span data-stu-id="e24d3-125">In the list, mark or unmark all rows.</span></span>
20. <span data-ttu-id="e24d3-126">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="e24d3-126">Click OK.</span></span>
21. <span data-ttu-id="e24d3-127">Kattintson a Folyamat gombra.</span><span class="sxs-lookup"><span data-stu-id="e24d3-127">Click Process.</span></span>
22. <span data-ttu-id="e24d3-128">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="e24d3-128">Click OK.</span></span>
23. <span data-ttu-id="e24d3-129">Frissítse a lapot..</span><span class="sxs-lookup"><span data-stu-id="e24d3-129">Refresh the page.</span></span>
24. <span data-ttu-id="e24d3-130">Kattintson az Eredmények mutatása elemre.</span><span class="sxs-lookup"><span data-stu-id="e24d3-130">Click Show results.</span></span>
25. <span data-ttu-id="e24d3-131">Nyissa meg az Állapot oszlopszűrőt.</span><span class="sxs-lookup"><span data-stu-id="e24d3-131">Open Status column filter.</span></span>
26. <span data-ttu-id="e24d3-132">Rendezés ábécérendben</span><span class="sxs-lookup"><span data-stu-id="e24d3-132">Sort A to Z</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]