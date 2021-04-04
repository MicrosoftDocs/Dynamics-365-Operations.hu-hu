---
title: Fedezeti lehetőségek létrehozása
description: A Microsoft Dynamics 365 Human Resources fedezeti lehetőségei fedezeti szintek a résztvevőknek egy juttatási csomagban vagy programban.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2e1d5fc80d93e41626da8eb5bdf8f389fb0bd531
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466182"
---
# <a name="create-coverage-options"></a><span data-ttu-id="918cc-103">Fedezeti lehetőségek létrehozása</span><span class="sxs-lookup"><span data-stu-id="918cc-103">Create coverage options</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="918cc-104">A Microsoft Dynamics 365 Human Resources fedezeti lehetőségei fedezeti szintek a résztvevőknek egy juttatási csomagban vagy programban.</span><span class="sxs-lookup"><span data-stu-id="918cc-104">Coverage options in Microsoft Dynamics 365 Human Resources are levels of coverage for a participant's election in a benefit plan or program.</span></span> <span data-ttu-id="918cc-105">A fedezeti beállítások például tartalmazhatják a **Csak munkavállaló** értéket egy egészségügyi csomaghoz vagy a **2x fizetés** értéket egy biztosítási csomaghoz.</span><span class="sxs-lookup"><span data-stu-id="918cc-105">For example, coverage options could include **Employee Only** for a medical plan, or **2x Salary** for a life insurance plan.</span></span> <span data-ttu-id="918cc-106">A definiálást követően, a juttatások fedezeti beállításai újra felhasználhatók.</span><span class="sxs-lookup"><span data-stu-id="918cc-106">Once defined, you can reuse benefit coverage options.</span></span> <span data-ttu-id="918cc-107">Egy beállítást egy vagy több tervhez is társítani lehet.</span><span class="sxs-lookup"><span data-stu-id="918cc-107">You can associate an option with one or more plans.</span></span>

<span data-ttu-id="918cc-108">A fedezeti beállítások megadása után csatolja a fedezeti beállításokat egy juttatásiterv-típushoz.</span><span class="sxs-lookup"><span data-stu-id="918cc-108">After you define coverage options, attach the coverage options to a benefit plan type.</span></span> <span data-ttu-id="918cc-109">A program ezt követően egy juttatási tervhez vagy programhoz rendeli hozzá a tervtípust.</span><span class="sxs-lookup"><span data-stu-id="918cc-109">The plan type is then associated with a benefit plan or program.</span></span> <span data-ttu-id="918cc-110">A tervtípushoz társított fedezeti beállítások minden olyan terv számára elérhetők, amelyeket az adott tervtípussal hoztak létre.</span><span class="sxs-lookup"><span data-stu-id="918cc-110">Coverage options that are associated with a plan type are available to all plans that are created with that plan type.</span></span> 

1. <span data-ttu-id="918cc-111">A **Juttatások kezelése** munkaterületen, amely a **Beállítás** menüpont alatt található, válassza a **Fedezeti beállítások** elemet.</span><span class="sxs-lookup"><span data-stu-id="918cc-111">In the **Benefits management** workspace, under **Setup**, select **Coverage options**.</span></span>

2. <span data-ttu-id="918cc-112">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="918cc-112">Select **New**.</span></span>

3. <span data-ttu-id="918cc-113">Adjon meg értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="918cc-113">Specify values for the following fields:</span></span>

   | <span data-ttu-id="918cc-114">Mező</span><span class="sxs-lookup"><span data-stu-id="918cc-114">Field</span></span> | <span data-ttu-id="918cc-115">Leírás</span><span class="sxs-lookup"><span data-stu-id="918cc-115">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="918cc-116">**Fedezeti beállítás**</span><span class="sxs-lookup"><span data-stu-id="918cc-116">**Coverage option**</span></span> | <span data-ttu-id="918cc-117">A fedezeti beállítások egyedi neve.</span><span class="sxs-lookup"><span data-stu-id="918cc-117">A unique coverage option name.</span></span> |
   | <span data-ttu-id="918cc-118">**Leírás**</span><span class="sxs-lookup"><span data-stu-id="918cc-118">**Description**</span></span> | <span data-ttu-id="918cc-119">A fedezeti beállítás leírása.</span><span class="sxs-lookup"><span data-stu-id="918cc-119">A description of the coverage option.</span></span> |
   | <span data-ttu-id="918cc-120">**Fedezeti kód**</span><span class="sxs-lookup"><span data-stu-id="918cc-120">**Coverage code**</span></span> | <span data-ttu-id="918cc-121">A fedezeti kódok minimális és maximális összegeket rendelnek hozzá minden jogosult fedezett személytípushoz.</span><span class="sxs-lookup"><span data-stu-id="918cc-121">Coverage codes assign minimum and maximum amounts for each eligible covered person type.</span></span> <span data-ttu-id="918cc-122">A fedezeti kód a jogosultságot vagy azt jelzi, hogy az adott tervtípushoz mekkora fedezetösszeg engedélyezett.</span><span class="sxs-lookup"><span data-stu-id="918cc-122">A coverage code indicates who is covered or the amount of coverage allowed for a plan type.</span></span> <span data-ttu-id="918cc-123">A fedezet összegét dollárban vagy százalékban lehet kifejezni.</span><span class="sxs-lookup"><span data-stu-id="918cc-123">You can express the amount of coverage as a dollar amount or a percentage.</span></span> <span data-ttu-id="918cc-124">Példa:</span><span class="sxs-lookup"><span data-stu-id="918cc-124">For example:</span></span></br></br><span data-ttu-id="918cc-125">- **Alk+1** – a minősítéshez az alkalmazottnak ki kell választania egy függő felet (ha egynél több van kiválasztva, már nem lehet jogosult).</span><span class="sxs-lookup"><span data-stu-id="918cc-125">- **Emp+1** – to be qualified, the employee must have one dependent selected (if more than one is selected, they no longer qualify).</span></span></br></br><span data-ttu-id="918cc-126">- **Alk+család** – a minősítéshez az alkalmazottnak legalább két függő felet kell kiválasztania.</span><span class="sxs-lookup"><span data-stu-id="918cc-126">- **Emp+family** – to be qualified, the employee must have at least two dependents selected.</span></span> |
   | <span data-ttu-id="918cc-127">**Maximális szám**</span><span class="sxs-lookup"><span data-stu-id="918cc-127">**Maximum number**</span></span> | <span data-ttu-id="918cc-128">A függő felek maximális száma.</span><span class="sxs-lookup"><span data-stu-id="918cc-128">The maximum number of dependents.</span></span> |
   | <span data-ttu-id="918cc-129">**Állapot**</span><span class="sxs-lookup"><span data-stu-id="918cc-129">**Status**</span></span> | <span data-ttu-id="918cc-130">A fedezeti beállítás állapota.</span><span class="sxs-lookup"><span data-stu-id="918cc-130">The status of the coverage option.</span></span> <span data-ttu-id="918cc-131">Ha a Fedezeti beállítás állapota inaktív értékre van állítva, akkor a program nem jelöli be a fedezeti beállítást a tervtípusokon.</span><span class="sxs-lookup"><span data-stu-id="918cc-131">If the Coverage option status is set to Inactive, the Coverage option can’t be selected on plan types.</span></span> |
   | <span data-ttu-id="918cc-132">**Százalék**</span><span class="sxs-lookup"><span data-stu-id="918cc-132">**Percent**</span></span> | <span data-ttu-id="918cc-133">A százalékos összeg.</span><span class="sxs-lookup"><span data-stu-id="918cc-133">The percent amount.</span></span> <span data-ttu-id="918cc-134">Ez a mező csak akkor aktív, ha a Fedezet kódja mezőben % x Fizetés van kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="918cc-134">This field is only active if % x Salary was selected in the Coverage code field.</span></span> |
   | <span data-ttu-id="918cc-135">**Osztó**</span><span class="sxs-lookup"><span data-stu-id="918cc-135">**Divisor**</span></span> | <span data-ttu-id="918cc-136">A(z) % x fedezeti kód kiválasztásakor a számításban használt osztó.</span><span class="sxs-lookup"><span data-stu-id="918cc-136">The divisor to use in the calculation when you select the coverage code % x salary.</span></span> |
   | <span data-ttu-id="918cc-137">**Százalék minimuma**</span><span class="sxs-lookup"><span data-stu-id="918cc-137">**Percent minimum**</span></span> | <span data-ttu-id="918cc-138">Minimális százalék a százalékos fedezeti kód kiválasztása esetén.</span><span class="sxs-lookup"><span data-stu-id="918cc-138">The minimum percentage when you select the Percentage coverage code.</span></span> |
   | <span data-ttu-id="918cc-139">**Százalék maximuma**</span><span class="sxs-lookup"><span data-stu-id="918cc-139">**Percent maximum**</span></span> | <span data-ttu-id="918cc-140">Maximális százalék a százalékos fedezeti kód kiválasztása esetén.</span><span class="sxs-lookup"><span data-stu-id="918cc-140">The maximum percentage when you select the Percentage coverage code.</span></span> |

4. <span data-ttu-id="918cc-141">A **Személyes kapcsolattartásra vonatkozó jogosultsági beállítások** pontban csatolja a megfelelő személyes kapcsolattartók jogosultsági beállítását mindegyik fedezeti beállításhoz.</span><span class="sxs-lookup"><span data-stu-id="918cc-141">Under **Personal contact eligibility options**, attach the appropriate personal contacts eligibility option to each coverage option.</span></span>

5. <span data-ttu-id="918cc-142">Az **Önkiszolgálás** pontban adja meg a megfelelő értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="918cc-142">Under **Self service**, specify values for the following fields:</span></span>

   | <span data-ttu-id="918cc-143">Mező</span><span class="sxs-lookup"><span data-stu-id="918cc-143">Field</span></span> | <span data-ttu-id="918cc-144">Leírás</span><span class="sxs-lookup"><span data-stu-id="918cc-144">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="918cc-145">**Alkalmazotti hozzájárulás összegének engedélyezése**</span><span class="sxs-lookup"><span data-stu-id="918cc-145">**Allow employee contribution amount**</span></span> | <span data-ttu-id="918cc-146">Azt adja meg, hogy az alkalmazottak módosíthatják-e az önkiszolgálói juttatás összegét a juttatások kiválasztása alkalmával.</span><span class="sxs-lookup"><span data-stu-id="918cc-146">Specifies whether to allow employees to modify the contribution amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="918cc-147">Ha bejelöli ezt a jelölőnégyzetet, a rendszer kiszámítja a juttatási terv paramétereit azon hozzájárulás összege alapján, amelyet az alkalmazott önkiszolgáló juttatásként megad.</span><span class="sxs-lookup"><span data-stu-id="918cc-147">If you select this check box, the system will calculate benefit plan parameters based on the contribution amount the employee enters on benefits self-service.</span></span> |
   | <span data-ttu-id="918cc-148">**Alkalmazotti fedezet összegének engedélyezése**</span><span class="sxs-lookup"><span data-stu-id="918cc-148">**Allow employee coverage amount**</span></span> | <span data-ttu-id="918cc-149">Azt adja meg, hogy az alkalmazottak módosíthatják-e a fedezeti juttatás önkiszolgálói összegét a juttatások kiválasztása alkalmával.</span><span class="sxs-lookup"><span data-stu-id="918cc-149">Specifies whether to allow employees to modify the coverage amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="918cc-150">Ha bejelöli ezt a jelölőnégyzetet, a rendszer kiszámítja a juttatási terv paramétereit azon fedezeti összeg alapján, amelyet az alkalmazott önkiszolgáló alkalmazottként megad.</span><span class="sxs-lookup"><span data-stu-id="918cc-150">If you select this check box, the system will calculate benefit plan parameters based on the coverage amount the employee enters in Employee self service.</span></span> |

6. <span data-ttu-id="918cc-151">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="918cc-151">Select **Save**.</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]