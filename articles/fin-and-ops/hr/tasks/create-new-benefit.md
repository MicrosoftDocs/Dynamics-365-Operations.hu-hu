--- 
title: "Új juttatás létrehozása"
description: "A feladat bemutatja, hogyan hozhat létre juttatási elemeket, amelyeket az új juttatás létrehozása során használni fog."
author: kherr75
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: bef33595a09ea54ba246a04b5a838013c6d65271
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-new-benefit"></a><span data-ttu-id="c9e51-103">Új juttatás létrehozása</span><span class="sxs-lookup"><span data-stu-id="c9e51-103">Create a new benefit</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c9e51-104">A feladat bemutatja, hogyan hozhat létre juttatási elemeket, amelyeket az új juttatás létrehozása során használni fog.</span><span class="sxs-lookup"><span data-stu-id="c9e51-104">This task will show you how to create benefit elements which will be used when creating a new benefit.</span></span> <span data-ttu-id="c9e51-105">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="c9e51-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="c9e51-106">A feladat a Kompenzációkért és juttatásokért felelős vezetőnek szól.</span><span class="sxs-lookup"><span data-stu-id="c9e51-106">This task is intended for a Compensation and Benefits manager.</span></span>


## <a name="create-benefit-elements"></a><span data-ttu-id="c9e51-107">Juttatás elemeinek létrehozása</span><span class="sxs-lookup"><span data-stu-id="c9e51-107">Create benefit elements</span></span>
1. <span data-ttu-id="c9e51-108">Ugorjon az Emberi erőforrások > Juttatások > Beállítás > Juttatás elemei pontra.</span><span class="sxs-lookup"><span data-stu-id="c9e51-108">Go to Human resources > Benefits > Setup > Benefit elements.</span></span>
2. <span data-ttu-id="c9e51-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c9e51-109">Click New.</span></span>
3. <span data-ttu-id="c9e51-110">Írja be a most létrehozott juttatástípus nevét a Típus mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c9e51-110">In the Type field, Enter the name of the type of benefit you are creating..</span></span>
4. <span data-ttu-id="c9e51-111">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c9e51-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="c9e51-112">Egy lehetőség kiválasztása az Egyidejű belépés mezőben.</span><span class="sxs-lookup"><span data-stu-id="c9e51-112">In the Concurrent enrollment field, select an option.</span></span>
    * <span data-ttu-id="c9e51-113">Annak érdekében, hogy korlátozza az alkalmazottak több egészségügyi konstrukcióba való felvételét, válassza ki a Típusonként egy felvétel lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9e51-113">To restrict employees' ability to enroll in multiple medical plans, select One enrollment per type.</span></span>  
6. <span data-ttu-id="c9e51-114">Egy lehetőség kiválasztása a Bérlista kategóriája mezőben.</span><span class="sxs-lookup"><span data-stu-id="c9e51-114">In the Payroll category field, select an option.</span></span>
7. <span data-ttu-id="c9e51-115">Kattintson a Konstrukció fülre.</span><span class="sxs-lookup"><span data-stu-id="c9e51-115">Click the Plans tab.</span></span>
8. <span data-ttu-id="c9e51-116">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="c9e51-116">Click New.</span></span>
9. <span data-ttu-id="c9e51-117">Érték beírása a Konstrukció mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c9e51-117">In the Plan field, type a value.</span></span>
10. <span data-ttu-id="c9e51-118">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c9e51-118">In the Description field, type a value.</span></span>
11. <span data-ttu-id="c9e51-119">A Típus mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c9e51-119">In the Type field, enter or select a value.</span></span>
12. <span data-ttu-id="c9e51-120">Egy lehetőség kiválasztása a Bérlista hatása mezőben.</span><span class="sxs-lookup"><span data-stu-id="c9e51-120">In the Payroll impact field, select an option.</span></span>
13. <span data-ttu-id="c9e51-121">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="c9e51-121">Click Save.</span></span>

## <a name="create-a-benefit"></a><span data-ttu-id="c9e51-122">Juttatás létrehozása</span><span class="sxs-lookup"><span data-stu-id="c9e51-122">Create a benefit</span></span>
1. <span data-ttu-id="c9e51-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c9e51-123">Close the page.</span></span>
2. <span data-ttu-id="c9e51-124">Ugorjon az Emberi erőforrások > Juttatások > Juttatások pontra.</span><span class="sxs-lookup"><span data-stu-id="c9e51-124">Go to Human resources > Benefits > Benefits.</span></span>
3. <span data-ttu-id="c9e51-125">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="c9e51-125">Click New to open the drop dialog.</span></span>
4. <span data-ttu-id="c9e51-126">A Terv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c9e51-126">In the Plan field, enter or select a value.</span></span>
5. <span data-ttu-id="c9e51-127">A Lehetőség mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c9e51-127">In the Option field, enter or select a value.</span></span>
6. <span data-ttu-id="c9e51-128">Az Érvényesség mezőben adjon meg dátumot és időt.</span><span class="sxs-lookup"><span data-stu-id="c9e51-128">In the Effective field, enter a date and time.</span></span>
7. <span data-ttu-id="c9e51-129">Kattintson a Juttatás létrehozása hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="c9e51-129">Click Create benefit.</span></span>

