---
title: Juttatási program meghatározása és kezelése
description: Az emberi erőforrások számos olyan eszközt biztosít, amelyek segítségével beállíthatja és karbantarthatja a szervezet által a dolgozóknak biztosított juttatásokat, levonásokat és dolgozói kompenzációs terveket. Ez a cikk a juttatások beállításával és kezelésével kapcsolatban tartalmaz tájékoztatást.
author: andreabichsel
manager: AnnBe
ms.date: 11/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, HcmBenefitSelection, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: 033377f7d45bfa2b798c098be2dde0c21739bb51
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/19/2019
ms.locfileid: "857430"
---
# <a name="define-and-manage-a-benefits-program"></a><span data-ttu-id="eb1f1-104">Juttatási program meghatározása és kezelése</span><span class="sxs-lookup"><span data-stu-id="eb1f1-104">Define and manage a benefits program</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="eb1f1-105">Az emberi erőforrások számos olyan eszközt biztosít, amelyek segítségével beállíthatja és karbantarthatja a szervezet által a dolgozóknak biztosított juttatásokat, levonásokat és dolgozói kompenzációs terveket.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-105">Human resources provides a set of tools that can be used to set up and maintain benefits, deductions, and workers' compensation plans that an organization offers or processes for its workers.</span></span> <span data-ttu-id="eb1f1-106">Ez a témakör a juttatások beállításával és kezelésével kapcsolatban tartalmaz tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-106">This topic provides information about how to set up and manage benefits.</span></span>

<a name="benefit-setup"></a><span data-ttu-id="eb1f1-107">Juttatási beállítás</span><span class="sxs-lookup"><span data-stu-id="eb1f1-107">Benefit setup</span></span>
-------------

<span data-ttu-id="eb1f1-108">Mielőtt a dolgozókhoz juttatásokat rendelhetne, az adott juttatási elemeket létre kell hoznia.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-108">Before workers can be enrolled in benefits, you must create the elements of each benefit.</span></span> <span data-ttu-id="eb1f1-109">Ezek az elemek hasonló juttatási terveket kombinálnak és olyan alapértelmezett beállításokat tartalmaznak, mint a levonási díjak és a könyvelési részletek.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-109">These elements combine similar benefit plans and define default settings, such as deduction rates and accounting details.</span></span> <span data-ttu-id="eb1f1-110">Ezen beállítások közül sokat később is módosíthat, ha a dolgozók juttatásban részesülnek.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-110">Many of these settings can be adjusted when workers are later enrolled in the benefit.</span></span> <span data-ttu-id="eb1f1-111">Az egyes juttatási tervekhez egy szervezet több bejegyzési lehetőséget is biztosíthat, vagy a dolgozó is lemondhat egy tervben lévő juttatásról.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-111">For each benefit plan, an organization can offer several enrollment options, or a worker can waive enrollment in the plan.</span></span> 

<span data-ttu-id="eb1f1-112">[![Juttatási folyamatábra](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)</span><span class="sxs-lookup"><span data-stu-id="eb1f1-112">[![Benefit process flow](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)</span></span>

## <a name="benefit-elements"></a><span data-ttu-id="eb1f1-113">Juttatás elemei</span><span class="sxs-lookup"><span data-stu-id="eb1f1-113">Benefit elements</span></span>
<span data-ttu-id="eb1f1-114">Mielőtt elkezdené a juttatások létrehozását és a dolgozók hozzáadását, meg kell határoznia a juttatás alkotóelemeit: a típusát, a tervet és a beállításokat.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-114">Before you begin to create to create benefits and enroll workers in them, you must define the elements that make up a benefit: the type, plan, and options.</span></span>

-   <span data-ttu-id="eb1f1-115">**Típus** – egy konkrét juttatásra, például az orvosi ellátásra vagy a parkolásra vonatkozó tervek gyűjteménye.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-115">**Type** – A collection of plans for a specific benefit, such as medical or parking.</span></span>
-   <span data-ttu-id="eb1f1-116">**Terv** – egy adott juttatás egy szerződött szolgáltatótól.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-116">**Plan** – A specific benefit that is contracted from a provider.</span></span>
-   <span data-ttu-id="eb1f1-117">**Beállítás** – a fedezeti szint, például csak az alkalmazott vagy az alkalmazott és a házastársa/élettársa is.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-117">**Option** – The coverage level, such as employee only, or employee and spouse/partner.</span></span>

<span data-ttu-id="eb1f1-118">Az egyes juttatási típusok, például látszerészeti vagy fogorvosi juttatás esetén a szervezet egy vagy több tervet is ajánlhat dolgozóinak.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-118">For each type of benefit, such as vision or dental, an organization can offer one or more plans to its workers.</span></span> <span data-ttu-id="eb1f1-119">Az egyes tervekhez a szervezet különböző beállításokat is biztosíthat.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-119">For each plan, the organization can offer different options.</span></span> <span data-ttu-id="eb1f1-120">A dolgozók például vásárolhatnak kiegészítő életbiztosítási csomagot éves bérük egyszeres, kétszeres vagy háromszoros mértékének megfelelően.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-120">For example, workers can buy additional term life insurance coverage at one, two, or three times their yearly salary.</span></span> <span data-ttu-id="eb1f1-121">A terv és annak minden beállítási kombinációja olyan juttatás lesz, amelyet a dolgozó kiválaszthat.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-121">Each combination of a plan and options becomes a benefit that workers can enroll in.</span></span> 

<span data-ttu-id="eb1f1-122">[![juttatási kép](./media/benefit-pic.png)](./media/benefit-pic.png)</span><span class="sxs-lookup"><span data-stu-id="eb1f1-122">[![benefit pic](./media/benefit-pic.png)](./media/benefit-pic.png)</span></span>

## <a name="eligibility"></a><span data-ttu-id="eb1f1-123">Jogosultság</span><span class="sxs-lookup"><span data-stu-id="eb1f1-123">Eligibility</span></span>
<span data-ttu-id="eb1f1-124">A munkáltató által ajánlott különböző típusú juttatásokra való megfelelőség számos tényezőtől függ.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-124">Many factors determine worker eligibility for the various types of benefits that an employer offers.</span></span> <span data-ttu-id="eb1f1-125">Ha egy juttatást hoz létre a Microsoft Talent rendszerben, meghatározhatja a megfelelőségi feltételeket az adott juttatáshoz.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-125">When you create a benefit in Microsoft Talent, you can set the type of eligibility that applies to that benefit.</span></span> 

<span data-ttu-id="eb1f1-126">A juttatást elérhetővé teheti minden dolgozó számára.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-126">You can make a benefit available to all workers.</span></span> <span data-ttu-id="eb1f1-127">Egyes vállalatok például mellékjuttatásként parkolási bérletet kínálnak dolgozóiknak.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-127">For example, some companies offer parking passes to all employees as a fringe benefit.</span></span> <span data-ttu-id="eb1f1-128">A juttatás létrehozásakor a jogosultságot beállíthatja **Minden dolgozó jogosult** beállításra.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-128">When you create this benefit, you set the eligibility to **All workers are eligible**.</span></span> 

<span data-ttu-id="eb1f1-129">Egyéb juttatások, például letiltások és adókivetések esetében a jogosultság nem érvényes.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-129">For other benefits, such as garnishments and tax levies, eligibility doesn't apply.</span></span> <span data-ttu-id="eb1f1-130">Ha ilyen típusú juttatást hoz létre, a jogosultságot a **Jogosultság feldolgozásának kihagyása** lehetőségre kell állítania.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-130">Whey you create these types of benefits, you set the eligibility to **Bypass eligibility process**.</span></span> 

<span data-ttu-id="eb1f1-131">A jogosultság továbbá szabályalapú is lehet.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-131">Finally, benefit eligibility can be rule-based.</span></span> <span data-ttu-id="eb1f1-132">Tegyük fel például, hogy egy vállalat kétféle életbiztosítást ajánl juttatásként a dolgozóinak.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-132">For example, a company offers two types of life insurance benefit to employees.</span></span> <span data-ttu-id="eb1f1-133">A vezetői beosztásban lévő dolgozók az egyik csomagra jogosultak, míg a többi teljes munkaidős dolgozó a másik életbiztosítási csomagra jogosult.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-133">Executive employees are eligible for one life insurance plan, whereas all other full-time employees are eligible for the other life insurance plan.</span></span> <span data-ttu-id="eb1f1-134">A Talent rendszerben létrehozhat egy jogosultsági szabályt, amelybe minden vezető beosztásban lévő dolgozót belevesz, majd egy másikat, amelybe a többi teljes munkaidős dolgozót veszi be, majd hozzárendelheti a megfelelő szabályokat az adott juttatáshoz.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-134">In Talent, you can create a benefit eligibility rule to find all executive employees and another rule to find all other full-time employees, and then apply those rules to the appropriate benefit.</span></span>

## <a name="enrollment"></a><span data-ttu-id="eb1f1-135">Bejegyzés</span><span class="sxs-lookup"><span data-stu-id="eb1f1-135">Enrollment</span></span>
<span data-ttu-id="eb1f1-136">Miután létrehozta a szervezet által kínált juttatásokat és meghatározta azok jogosultságát, már hozzárendelheti a dolgozókat a juttatásokhoz.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-136">After you've created the benefits that your organization offers and determined eligibility, you can enroll your workers in benefits.</span></span> <span data-ttu-id="eb1f1-137">Egyetlen dolgozót is hozzárendelhet egy juttatáshoz, de egyszerre több dolgozót is hozzáadhat egy vagy több juttatáshoz, egyetlen folyamat során.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-137">You can enroll a single worker in benefits, or you can enroll many workers in one or more benefits during a single process.</span></span> 

<span data-ttu-id="eb1f1-138">Előfordulhat, hogy egy szervezet visszavonja az egyik juttatását.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-138">Sometimes, an organization stops offering certain benefits.</span></span> <span data-ttu-id="eb1f1-139">Ebben az esetben frissítenie kell a juttatást és az abban lévő dolgozókat.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-139">In this case, you must update the benefit and the workers who are enrolled in.</span></span> <span data-ttu-id="eb1f1-140">A juttatás lejáratának tömeges beállításával egyszerre módosíthatja a juttatás lejárati dátumát, valamint az ahhoz rendelt dolgozókat is.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-140">Mass benefit expiration lets you change the expiration date of both a benefit and the worker enrollments for that benefit at the same time.</span></span> <span data-ttu-id="eb1f1-141">Kiválaszthat például a juttatásban részesülő több dolgozót, és a fedezetük lejárati dátumát egyszerre módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-141">You can also select multiple workers who are enrolled in a benefit and change the ending date of their coverage.</span></span> 

<span data-ttu-id="eb1f1-142">A juttatások tömeges bővítése funkció hasonlóan működik: ha a tervezetthez képest tovább szeretne egy juttatást biztosítani, egyszerre bővítheti annak lejárati dátumát és módosíthatja az adott juttatásban részesülő dolgozókat.</span><span class="sxs-lookup"><span data-stu-id="eb1f1-142">Similarly, mass benefit extension lets you extend the expiration date of both a benefit and the worker enrollments for that benefit if you decide to offer a benefit longer than you originally planned.</span></span>

<a name="additional-resources"></a><span data-ttu-id="eb1f1-143">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="eb1f1-143">Additional resources</span></span>
--------

[<span data-ttu-id="eb1f1-144">Juttatásra vonatkozó jogosultsági irányelvek</span><span class="sxs-lookup"><span data-stu-id="eb1f1-144">Benefit eligibility policies</span></span>](benefit-eligibility-policies.md)



