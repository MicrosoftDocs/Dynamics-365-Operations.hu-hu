---
title: Új juttatás létrehozása
description: A feladat bemutatja, hogyan hozhat létre juttatási elemeket, amelyeket az új juttatás létrehozása során használni fog.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmBenefitElementSetup, HcmBenefit, HcmBenefitNewBenefit, HcmBenefitPlanLookup, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: f9618e62e33655bfc1a0653cb767abe0094d1e79
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2020
ms.locfileid: "3430939"
---
# <a name="create-a-new-benefit"></a><span data-ttu-id="22328-103">Új juttatás létrehozása</span><span class="sxs-lookup"><span data-stu-id="22328-103">Create a new benefit</span></span>

<span data-ttu-id="22328-104">A feladat bemutatja, hogyan hozhat létre juttatási elemeket, amelyeket az új juttatás létrehozása során használni fog.</span><span class="sxs-lookup"><span data-stu-id="22328-104">This task will show you how to create benefit elements which will be used when creating a new benefit.</span></span> <span data-ttu-id="22328-105">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="22328-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="22328-106">A feladat a Kompenzációkért és juttatásokért felelős vezetőnek szól.</span><span class="sxs-lookup"><span data-stu-id="22328-106">This task is intended for a Compensation and Benefits manager.</span></span>


## <a name="create-benefit-elements"></a><span data-ttu-id="22328-107">Juttatás elemeinek létrehozása</span><span class="sxs-lookup"><span data-stu-id="22328-107">Create benefit elements</span></span>
1. <span data-ttu-id="22328-108">Ugorjon az Emberi erőforrások > Juttatások > Beállítás > Juttatás elemei pontra.</span><span class="sxs-lookup"><span data-stu-id="22328-108">Go to Human resources > Benefits > Setup > Benefit elements.</span></span>
2. <span data-ttu-id="22328-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="22328-109">Click New.</span></span>
3. <span data-ttu-id="22328-110">Írja be a most létrehozott juttatástípus nevét a Típus mezőbe.</span><span class="sxs-lookup"><span data-stu-id="22328-110">In the Type field, Enter the name of the type of benefit you are creating..</span></span>
4. <span data-ttu-id="22328-111">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="22328-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="22328-112">Egy lehetőség kiválasztása az Egyidejű belépés mezőben.</span><span class="sxs-lookup"><span data-stu-id="22328-112">In the Concurrent enrollment field, select an option.</span></span>
    * <span data-ttu-id="22328-113">Annak érdekében, hogy korlátozza az alkalmazottak több egészségügyi konstrukcióba való felvételét, válassza ki a Típusonként egy felvétel lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="22328-113">To restrict employees' ability to enroll in multiple medical plans, select One enrollment per type.</span></span>  
6. <span data-ttu-id="22328-114">Egy lehetőség kiválasztása a Bérlista kategóriája mezőben.</span><span class="sxs-lookup"><span data-stu-id="22328-114">In the Payroll category field, select an option.</span></span>
7. <span data-ttu-id="22328-115">Kattintson a Konstrukció fülre.</span><span class="sxs-lookup"><span data-stu-id="22328-115">Click the Plans tab.</span></span>
8. <span data-ttu-id="22328-116">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="22328-116">Click New.</span></span>
9. <span data-ttu-id="22328-117">Érték beírása a Konstrukció mezőbe.</span><span class="sxs-lookup"><span data-stu-id="22328-117">In the Plan field, type a value.</span></span>
10. <span data-ttu-id="22328-118">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="22328-118">In the Description field, type a value.</span></span>
11. <span data-ttu-id="22328-119">A Típus mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="22328-119">In the Type field, enter or select a value.</span></span>
12. <span data-ttu-id="22328-120">Egy lehetőség kiválasztása a Bérlista hatása mezőben.</span><span class="sxs-lookup"><span data-stu-id="22328-120">In the Payroll impact field, select an option.</span></span>
13. <span data-ttu-id="22328-121">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="22328-121">Click Save.</span></span>

## <a name="create-a-benefit"></a><span data-ttu-id="22328-122">Juttatás létrehozása</span><span class="sxs-lookup"><span data-stu-id="22328-122">Create a benefit</span></span>
1. <span data-ttu-id="22328-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="22328-123">Close the page.</span></span>
2. <span data-ttu-id="22328-124">Ugorjon az Emberi erőforrások > Juttatások > Juttatások pontra.</span><span class="sxs-lookup"><span data-stu-id="22328-124">Go to Human resources > Benefits > Benefits.</span></span>
3. <span data-ttu-id="22328-125">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="22328-125">Click New to open the drop dialog.</span></span>
4. <span data-ttu-id="22328-126">A Terv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="22328-126">In the Plan field, enter or select a value.</span></span>
5. <span data-ttu-id="22328-127">A Lehetőség mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="22328-127">In the Option field, enter or select a value.</span></span>
6. <span data-ttu-id="22328-128">Az Érvényesség mezőben adjon meg dátumot és időt.</span><span class="sxs-lookup"><span data-stu-id="22328-128">In the Effective field, enter a date and time.</span></span>
7. <span data-ttu-id="22328-129">Kattintson a Juttatás létrehozása hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="22328-129">Click Create benefit.</span></span>

