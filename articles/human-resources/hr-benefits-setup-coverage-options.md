---
title: Fedezeti beállítások létrehozása
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 27b43d858a92beac526ac0fc40b544649ef658b0
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009224"
---
# <a name="create-coverage-options"></a><span data-ttu-id="25ea1-102">Fedezeti beállítások létrehozása</span><span class="sxs-lookup"><span data-stu-id="25ea1-102">Create coverage options</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="25ea1-103">A Microsoft Dynamics 365 Human Resources fedezeti beállításai olyan fedezeti szintek, amelyek a résztvevők megválasztását jellemzik a juttatási tervben vagy programban, például az egészségügyi terv esetében a „csak alkalmazottak„ terv, vagy az életbiztosítási terv esetében a „kétszeri fizetés”.</span><span class="sxs-lookup"><span data-stu-id="25ea1-103">Coverage options in Microsoft Dynamics 365 Human Resources are levels of coverage for a participant's election in a benefit plan or program, such as Employee Only for a medical plan, or 2x Salary for a life insurance plan.</span></span> <span data-ttu-id="25ea1-104">Ha már egyszer megadták, a juttatások fedezeti beállításai újra felhasználhatók, valamint a beállítások újra társíthatók egy vagy több tervhez.</span><span class="sxs-lookup"><span data-stu-id="25ea1-104">Once defined, benefit coverage options are re-usable and you can associate an option with one or more plans.</span></span>

<span data-ttu-id="25ea1-105">A fedezeti beállítások megadása után csatolja a fedezeti beállításokat egy juttatásiterv-típushoz.</span><span class="sxs-lookup"><span data-stu-id="25ea1-105">Once the coverage options are defined, attach the coverage options to a benefit plan type.</span></span> <span data-ttu-id="25ea1-106">A program ezt követően egy juttatási tervhez vagy programhoz rendeli hozzá a tervtípust.</span><span class="sxs-lookup"><span data-stu-id="25ea1-106">The plan type is then associated with a benefit plan or program.</span></span> <span data-ttu-id="25ea1-107">A tervtípushoz társított fedezeti beállítások minden olyan terv számára elérhetők lesznek, amelyeket az adott tervtípussal hoztak létre.</span><span class="sxs-lookup"><span data-stu-id="25ea1-107">Coverage options that are associated with a plan type will be available to all plans that are created with that plan type.</span></span> 

1. <span data-ttu-id="25ea1-108">A **Juttatások kezelése** munkaterületen, amely a **Beállítás** menüpont alatt található, válassza a **Fedezeti beállítások** elemet.</span><span class="sxs-lookup"><span data-stu-id="25ea1-108">In the **Benefits management** workspace, under **Setup**, select **Coverage options**.</span></span>

2. <span data-ttu-id="25ea1-109">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="25ea1-109">Select **New**.</span></span>

3. <span data-ttu-id="25ea1-110">Adjon meg értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="25ea1-110">Specify values for the following fields:</span></span>

   | <span data-ttu-id="25ea1-111">Mező</span><span class="sxs-lookup"><span data-stu-id="25ea1-111">Field</span></span> | <span data-ttu-id="25ea1-112">Leírás</span><span class="sxs-lookup"><span data-stu-id="25ea1-112">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="25ea1-113">**Fedezeti beállítás**</span><span class="sxs-lookup"><span data-stu-id="25ea1-113">**Coverage option**</span></span> | <span data-ttu-id="25ea1-114">A fedezeti beállítások egyedi neve.</span><span class="sxs-lookup"><span data-stu-id="25ea1-114">A unique coverage option name.</span></span> |
   | <span data-ttu-id="25ea1-115">**Leírás**</span><span class="sxs-lookup"><span data-stu-id="25ea1-115">**Description**</span></span> | <span data-ttu-id="25ea1-116">A fedezeti beállítás leírása.</span><span class="sxs-lookup"><span data-stu-id="25ea1-116">A description of the coverage option.</span></span> |
   | <span data-ttu-id="25ea1-117">**Fedezeti kód**</span><span class="sxs-lookup"><span data-stu-id="25ea1-117">**Coverage code**</span></span> | <span data-ttu-id="25ea1-118">A fedezeti kódok minimális és maximális összegeket rendelnek hozzá minden jogosult fedezett személytípushoz.</span><span class="sxs-lookup"><span data-stu-id="25ea1-118">Coverage codes assign minimum and maximum amounts for each eligible covered person type.</span></span> <span data-ttu-id="25ea1-119">A fedezeti kód a jogosultságot vagy azt jelzi, hogy az adott tervtípushoz mekkora fedezetösszeg engedélyezett.</span><span class="sxs-lookup"><span data-stu-id="25ea1-119">A coverage code indicates who is covered or the amount of coverage allowed for a plan type.</span></span> <span data-ttu-id="25ea1-120">A fedezet összegét dollárban vagy százalékban lehet kifejezni.</span><span class="sxs-lookup"><span data-stu-id="25ea1-120">You can express the amount of coverage as a dollar amount or a percentage.</span></span> <span data-ttu-id="25ea1-121">Példa:</span><span class="sxs-lookup"><span data-stu-id="25ea1-121">For example:</span></span></br></br><span data-ttu-id="25ea1-122">- **Alk+1** – a minősítéshez az alkalmazottnak ki kell választania egy függő felet (ha egynél több van kiválasztva, már nem lehet jogosult).</span><span class="sxs-lookup"><span data-stu-id="25ea1-122">- **Emp+1** – to be qualified, the employee must have one dependent selected (if more than one is selected, they no longer qualify).</span></span></br></br><span data-ttu-id="25ea1-123">- **Alk+család** – a minősítéshez az alkalmazottnak legalább két függő felet kell kiválasztania.</span><span class="sxs-lookup"><span data-stu-id="25ea1-123">- **Emp+family** – to be qualified, the employee must have at least two dependents selected.</span></span> |
   | <span data-ttu-id="25ea1-124">**Maximális szám**</span><span class="sxs-lookup"><span data-stu-id="25ea1-124">**Maximum number**</span></span> | <span data-ttu-id="25ea1-125">A függő felek maximális száma.</span><span class="sxs-lookup"><span data-stu-id="25ea1-125">The maximum number of dependents.</span></span> |
   | <span data-ttu-id="25ea1-126">**Állapot**</span><span class="sxs-lookup"><span data-stu-id="25ea1-126">**Status**</span></span> | <span data-ttu-id="25ea1-127">A fedezeti beállítás állapota.</span><span class="sxs-lookup"><span data-stu-id="25ea1-127">The status of the coverage option.</span></span> <span data-ttu-id="25ea1-128">Ha a Fedezeti beállítás állapota inaktív értékre van állítva, akkor a program nem jelöli be a fedezeti beállítást a tervtípusokon.</span><span class="sxs-lookup"><span data-stu-id="25ea1-128">If the Coverage option status is set to Inactive, the Coverage option can’t be selected on plan types.</span></span> |
   | <span data-ttu-id="25ea1-129">**Százalék**</span><span class="sxs-lookup"><span data-stu-id="25ea1-129">**Percent**</span></span> | <span data-ttu-id="25ea1-130">A százalékos összeg.</span><span class="sxs-lookup"><span data-stu-id="25ea1-130">The percent amount.</span></span> <span data-ttu-id="25ea1-131">Ez a mező csak akkor aktív, ha a Fedezet kódja mezőben % x Fizetés van kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="25ea1-131">This field is only active if % x Salary was selected in the Coverage code field.</span></span> |
   | <span data-ttu-id="25ea1-132">**Osztó**</span><span class="sxs-lookup"><span data-stu-id="25ea1-132">**Divisor**</span></span> | <span data-ttu-id="25ea1-133">A(z) % x fedezeti kód kiválasztásakor a számításban használt osztó.</span><span class="sxs-lookup"><span data-stu-id="25ea1-133">The divisor to use in the calculation when you select the coverage code % x salary.</span></span> |
   | <span data-ttu-id="25ea1-134">**Százalék minimuma**</span><span class="sxs-lookup"><span data-stu-id="25ea1-134">**Percent minimum**</span></span> | <span data-ttu-id="25ea1-135">Minimális százalék a százalékos fedezeti kód kiválasztása esetén.</span><span class="sxs-lookup"><span data-stu-id="25ea1-135">The minimum percentage when you select the Percentage coverage code.</span></span> |
   | <span data-ttu-id="25ea1-136">**Százalék maximuma**</span><span class="sxs-lookup"><span data-stu-id="25ea1-136">**Percent maximum**</span></span> | <span data-ttu-id="25ea1-137">Maximális százalék a százalékos fedezeti kód kiválasztása esetén.</span><span class="sxs-lookup"><span data-stu-id="25ea1-137">The maximum percentage when you select the Percentage coverage code.</span></span> |

4. <span data-ttu-id="25ea1-138">A **Személyes kapcsolattartásra vonatkozó jogosultsági beállítások** pontban csatolja a megfelelő személyes kapcsolattartók jogosultsági beállítását mindegyik fedezeti beállításhoz.</span><span class="sxs-lookup"><span data-stu-id="25ea1-138">Under **Personal contact eligibility options**, attach the appropriate personal contacts eligibility option to each coverage option.</span></span>

5. <span data-ttu-id="25ea1-139">Az **Önkiszolgálás** pontban adja meg a megfelelő értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="25ea1-139">Under **Self service**, specify values for the following fields:</span></span>

   | <span data-ttu-id="25ea1-140">Mező</span><span class="sxs-lookup"><span data-stu-id="25ea1-140">Field</span></span> | <span data-ttu-id="25ea1-141">Leírás</span><span class="sxs-lookup"><span data-stu-id="25ea1-141">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="25ea1-142">**Alkalmazotti hozzájárulás összegének engedélyezése**</span><span class="sxs-lookup"><span data-stu-id="25ea1-142">**Allow employee contribution amount**</span></span> | <span data-ttu-id="25ea1-143">Azt adja meg, hogy az alkalmazottak módosíthatják-e az önkiszolgálói juttatás összegét a juttatások kiválasztása alkalmával.</span><span class="sxs-lookup"><span data-stu-id="25ea1-143">Specifies whether to allow employees to modify the contribution amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="25ea1-144">Ha bejelöli ezt a jelölőnégyzetet, a rendszer kiszámítja a juttatási terv paramétereit azon hozzájárulás összege alapján, amelyet az alkalmazott önkiszolgáló juttatásként megad.</span><span class="sxs-lookup"><span data-stu-id="25ea1-144">If you select this check box, the system will calculate benefit plan parameters based on the contribution amount the employee enters on benefits self-service.</span></span> |
   | <span data-ttu-id="25ea1-145">**Alkalmazotti fedezet összegének engedélyezése**</span><span class="sxs-lookup"><span data-stu-id="25ea1-145">**Allow employee coverage amount**</span></span> | <span data-ttu-id="25ea1-146">Azt adja meg, hogy az alkalmazottak módosíthatják-e a fedezeti juttatás önkiszolgálói összegét a juttatások kiválasztása alkalmával.</span><span class="sxs-lookup"><span data-stu-id="25ea1-146">Specifies whether to allow employees to modify the coverage amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="25ea1-147">Ha bejelöli ezt a jelölőnégyzetet, a rendszer kiszámítja a juttatási terv paramétereit azon fedezeti összeg alapján, amelyet az alkalmazott önkiszolgáló alkalmazottként megad.</span><span class="sxs-lookup"><span data-stu-id="25ea1-147">If you select this check box, the system will calculate benefit plan parameters based on the coverage amount the employee enters in Employee self service.</span></span> |

6. <span data-ttu-id="25ea1-148">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="25ea1-148">Select **Save**.</span></span> 
