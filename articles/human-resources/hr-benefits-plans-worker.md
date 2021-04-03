---
title: Dolgozói juttatási tervek létrehozása
description: A Microsoft Dynamics 365 Human Resources dolgozói juttatási tervek létrehozásával kiválaszthatja az alkalmazottak juttatási terveit, és megerősítheti a kiválasztott juttatási terveket.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitPlanEmployee, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5ac357bbef4bf84b9eaf153834bc7a609240c45e
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464226"
---
# <a name="create-worker-benefit-plans"></a><span data-ttu-id="48da5-103">Dolgozói juttatási tervek létrehozása</span><span class="sxs-lookup"><span data-stu-id="48da5-103">Create worker benefit plans</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="48da5-104">A Microsoft Dynamics 365 Human Resources dolgozói juttatási tervek létrehozásával kiválaszthatja az alkalmazottak juttatási terveit, és megerősítheti a kiválasztott juttatási terveket.</span><span class="sxs-lookup"><span data-stu-id="48da5-104">You can create worker benefit plans in Microsoft Dynamics 365 Human Resources to select benefit plans for employees and to confirm benefit plan selections.</span></span> <span data-ttu-id="48da5-105">Az alkalmazottak általában saját maguk választják ki a juttatási terveket az Alkalmazotti önkiszolgáló rendszer segítségével, majd a juttatások rendszergazdái visszaigazolják a választást.</span><span class="sxs-lookup"><span data-stu-id="48da5-105">Typically, employees select benefit plans themselves by using Employee self service, and then a benefits administrator confirms the selections.</span></span> 

1. <span data-ttu-id="48da5-106">A **Juttatások kezelése** munkaterületen, amely a **Tervek** pontban található, válassza a **Dolgozó juttatási tervei** elemet.</span><span class="sxs-lookup"><span data-stu-id="48da5-106">In the **Benefits management** workspace, under **Plans**, select **Worker benefit plans**.</span></span>

2. <span data-ttu-id="48da5-107">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="48da5-107">Select **New**.</span></span>

3. <span data-ttu-id="48da5-108">Adjon meg értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="48da5-108">Specify values for the following fields:</span></span>

   | <span data-ttu-id="48da5-109">Mező</span><span class="sxs-lookup"><span data-stu-id="48da5-109">Field</span></span> | <span data-ttu-id="48da5-110">Leírás</span><span class="sxs-lookup"><span data-stu-id="48da5-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="48da5-111">Időszak</span><span class="sxs-lookup"><span data-stu-id="48da5-111">Period</span></span> | <span data-ttu-id="48da5-112">Megadja a terveknek a Tervek gyorslapon történő szűréséhez használandó juttatási időszakot. A tervek szűrése segít kijelölni az összes tervrekord egy részhalmazát, és így megerősítheti a részhalmazt.</span><span class="sxs-lookup"><span data-stu-id="48da5-112">Specifies a benefits period to use to filter the plans in the Plans fast tab. Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> <span data-ttu-id="48da5-113">Például válassza ki azt az időszakot, amelyet 2015 nevűként hozott létre, hogy megerősítse a 2015-ös évben található, a juttatásokban való részesítésekre vonatkozó összes beállítást.</span><span class="sxs-lookup"><span data-stu-id="48da5-113">For example, select a period you created called 2015 to confirm all the benefit enrollment selections for 2015.</span></span> |
   | <span data-ttu-id="48da5-114">Dolgozó</span><span class="sxs-lookup"><span data-stu-id="48da5-114">Worker</span></span> | <span data-ttu-id="48da5-115">Megadja a terveknek a Tervek gyorslapon történő szűréséhez használandó dolgozót. A tervek szűrése segít kijelölni az összes tervrekord egy részhalmazát, és így megerősítheti a részhalmazt.</span><span class="sxs-lookup"><span data-stu-id="48da5-115">Specifies a worker to use to filter the plans in the Plans fast tab. Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> |
   | <span data-ttu-id="48da5-116">Jogi személy</span><span class="sxs-lookup"><span data-stu-id="48da5-116">Legal entity</span></span> | <span data-ttu-id="48da5-117">Megadja a terveknek a Tervek gyorslapon történő szűréséhez használandó jogi személyt. A tervek szűrése segít kijelölni az összes tervrekord egy részhalmazát, és így megerősítheti a részhalmazt.</span><span class="sxs-lookup"><span data-stu-id="48da5-117">Specifies a legal entity to use to filter the plans in the Plans fast tab. Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> |
   | <span data-ttu-id="48da5-118">Fedezeti beállítás</span><span class="sxs-lookup"><span data-stu-id="48da5-118">Coverage option</span></span> | <span data-ttu-id="48da5-119">Megadja a terveknek a Tervek gyorslapon történő szűréséhez használandó fedezeti lehetőséget. A tervek szűrése segít kijelölni az összes tervrekord egy részhalmazát, és így megerősítheti a részhalmazt.</span><span class="sxs-lookup"><span data-stu-id="48da5-119">Specifies a coverage option to use to filter the plans in the Plans fast tab. Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> |
   | <span data-ttu-id="48da5-120">Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="48da5-120">Default</span></span> | <span data-ttu-id="48da5-121">Szűri a juttatási terveket annak alapján, hogy ezek alapértelmezett tervek-e.</span><span class="sxs-lookup"><span data-stu-id="48da5-121">Filters the benefit plans based on whether they are a default plan.</span></span> <span data-ttu-id="48da5-122">A tervek szűrésével kiválaszthatja az összes tervrekord egy részhalmazát, így megerősítve a részhalmazt.</span><span class="sxs-lookup"><span data-stu-id="48da5-122">Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> |
   | <span data-ttu-id="48da5-123">Állapot</span><span class="sxs-lookup"><span data-stu-id="48da5-123">Status</span></span> | <span data-ttu-id="48da5-124">Szűri a juttatási terveket az állapotuk alapján.</span><span class="sxs-lookup"><span data-stu-id="48da5-124">Filters benefit plans based on their status.</span></span> <span data-ttu-id="48da5-125">A tervek szűrésével kiválaszthatja az összes tervrekord egy részhalmazát, így megerősítve a részhalmazt.</span><span class="sxs-lookup"><span data-stu-id="48da5-125">Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> |
   | <span data-ttu-id="48da5-126">Visszaigazolás</span><span class="sxs-lookup"><span data-stu-id="48da5-126">Confirmation</span></span> | <span data-ttu-id="48da5-127">Megadja a terveknek a Tervek gyorslapon történő szűréséhez használandó visszaigazolási állapotot. A tervek szűrése segít kijelölni az összes tervrekord egy részhalmazát, és így megerősítheti a részhalmazt.</span><span class="sxs-lookup"><span data-stu-id="48da5-127">Specifies the confirmation status to use to filter the plans in the Plans fast tab. Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> |
   | <span data-ttu-id="48da5-128">Érvénytelenítés</span><span class="sxs-lookup"><span data-stu-id="48da5-128">Cancellation</span></span> | <span data-ttu-id="48da5-129">Megadja a terveknek a Tervek gyorslapon történő szűréséhez használandó visszavonási állapotot. A tervek szűrése segít kijelölni az összes tervrekord egy részhalmazát, és így megerősítheti a részhalmazt.</span><span class="sxs-lookup"><span data-stu-id="48da5-129">Specifies the cancellation status to use to filter the plans in the Plans fast tab. Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> |
   | <span data-ttu-id="48da5-130">Érvényességidátum-szűrő</span><span class="sxs-lookup"><span data-stu-id="48da5-130">Effective date filter</span></span> | <span data-ttu-id="48da5-131">Szűri a terveket a jövőbeli állapotok lejártát, aktiválását vagy jövőbeli aktiválását illetően.</span><span class="sxs-lookup"><span data-stu-id="48da5-131">Filters the plans based on whether they’re expired, active, or will be active in the future.</span></span> <span data-ttu-id="48da5-132">Jelölje be azokat a jelölőnégyzeteket, amelyek megfelelnek azoknak a terveknek, amelyeket meg szeretne jeleníteni a Tervek gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="48da5-132">Select the check boxes that correspond to the plans you want to see in the Plans fast tab.</span></span> |
   | <span data-ttu-id="48da5-133">Konstrukciók</span><span class="sxs-lookup"><span data-stu-id="48da5-133">Plans</span></span> | <span data-ttu-id="48da5-134">A Tervek gyorslap tartalmazza a megadott szűrési feltételeknek megfelelő terveket.</span><span class="sxs-lookup"><span data-stu-id="48da5-134">The Plans fast tab contains the plans that meet the filter criteria you specified.</span></span> <span data-ttu-id="48da5-135">A HR-személyzet által beállított releváns konfigurációs beállítások, valamint az alkalmazottak által választott beléptetési kiválasztások mindegyik sorban szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="48da5-135">The relevant configuration options that were set by HR staff and the enrollment selections that were chosen by employees are included on each line.</span></span> <span data-ttu-id="48da5-136">A Minősített mező azt határozza meg, hogy van-e érvényesítési ütközés a terv kiválasztásával kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="48da5-136">The Qualified field specifies whether there is a validation conflict with the plan selection.</span></span> |

4. <span data-ttu-id="48da5-137">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="48da5-137">Select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]