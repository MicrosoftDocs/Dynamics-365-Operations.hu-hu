---
title: Fedezeti lehetőségek létrehozása
description: A Microsoft Dynamics 365 Human Resources fedezeti beállításai olyan fedezeti szintek, amelyek a résztvevők megválasztását jellemzik a juttatási tervben vagy programban, például az egészségügyi terv esetében a „csak alkalmazottak„ terv, vagy az életbiztosítási terv esetében a „kétszeri fizetés”.
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
ms.openlocfilehash: 0af2b6ae0853b4c7f64c4d4f04299c87089d622b
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092706"
---
# <a name="create-coverage-options"></a><span data-ttu-id="51722-103">Fedezeti lehetőségek létrehozása</span><span class="sxs-lookup"><span data-stu-id="51722-103">Create coverage options</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="51722-104">A Microsoft Dynamics 365 Human Resources fedezeti beállításai olyan fedezeti szintek, amelyek a résztvevők megválasztását jellemzik a juttatási tervben vagy programban, például az egészségügyi terv esetében a „csak alkalmazottak„ terv, vagy az életbiztosítási terv esetében a „kétszeri fizetés”.</span><span class="sxs-lookup"><span data-stu-id="51722-104">Coverage options in Microsoft Dynamics 365 Human Resources are levels of coverage for a participant's election in a benefit plan or program, such as Employee Only for a medical plan, or 2x Salary for a life insurance plan.</span></span> <span data-ttu-id="51722-105">Ha már egyszer megadták, a juttatások fedezeti beállításai újra felhasználhatók, valamint a beállítások újra társíthatók egy vagy több tervhez.</span><span class="sxs-lookup"><span data-stu-id="51722-105">Once defined, benefit coverage options are re-usable and you can associate an option with one or more plans.</span></span>

<span data-ttu-id="51722-106">A fedezeti beállítások megadása után csatolja a fedezeti beállításokat egy juttatásiterv-típushoz.</span><span class="sxs-lookup"><span data-stu-id="51722-106">Once the coverage options are defined, attach the coverage options to a benefit plan type.</span></span> <span data-ttu-id="51722-107">A program ezt követően egy juttatási tervhez vagy programhoz rendeli hozzá a tervtípust.</span><span class="sxs-lookup"><span data-stu-id="51722-107">The plan type is then associated with a benefit plan or program.</span></span> <span data-ttu-id="51722-108">A tervtípushoz társított fedezeti beállítások minden olyan terv számára elérhetők lesznek, amelyeket az adott tervtípussal hoztak létre.</span><span class="sxs-lookup"><span data-stu-id="51722-108">Coverage options that are associated with a plan type will be available to all plans that are created with that plan type.</span></span> 

1. <span data-ttu-id="51722-109">A **Juttatások kezelése** munkaterületen, amely a **Beállítás** menüpont alatt található, válassza a **Fedezeti beállítások** elemet.</span><span class="sxs-lookup"><span data-stu-id="51722-109">In the **Benefits management** workspace, under **Setup**, select **Coverage options**.</span></span>

2. <span data-ttu-id="51722-110">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="51722-110">Select **New**.</span></span>

3. <span data-ttu-id="51722-111">Adjon meg értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="51722-111">Specify values for the following fields:</span></span>

   | <span data-ttu-id="51722-112">Mező</span><span class="sxs-lookup"><span data-stu-id="51722-112">Field</span></span> | <span data-ttu-id="51722-113">Leírás</span><span class="sxs-lookup"><span data-stu-id="51722-113">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="51722-114">**Fedezeti beállítás**</span><span class="sxs-lookup"><span data-stu-id="51722-114">**Coverage option**</span></span> | <span data-ttu-id="51722-115">A fedezeti beállítások egyedi neve.</span><span class="sxs-lookup"><span data-stu-id="51722-115">A unique coverage option name.</span></span> |
   | <span data-ttu-id="51722-116">**Leírás**</span><span class="sxs-lookup"><span data-stu-id="51722-116">**Description**</span></span> | <span data-ttu-id="51722-117">A fedezeti beállítás leírása.</span><span class="sxs-lookup"><span data-stu-id="51722-117">A description of the coverage option.</span></span> |
   | <span data-ttu-id="51722-118">**Fedezeti kód**</span><span class="sxs-lookup"><span data-stu-id="51722-118">**Coverage code**</span></span> | <span data-ttu-id="51722-119">A fedezeti kódok minimális és maximális összegeket rendelnek hozzá minden jogosult fedezett személytípushoz.</span><span class="sxs-lookup"><span data-stu-id="51722-119">Coverage codes assign minimum and maximum amounts for each eligible covered person type.</span></span> <span data-ttu-id="51722-120">A fedezeti kód a jogosultságot vagy azt jelzi, hogy az adott tervtípushoz mekkora fedezetösszeg engedélyezett.</span><span class="sxs-lookup"><span data-stu-id="51722-120">A coverage code indicates who is covered or the amount of coverage allowed for a plan type.</span></span> <span data-ttu-id="51722-121">A fedezet összegét dollárban vagy százalékban lehet kifejezni.</span><span class="sxs-lookup"><span data-stu-id="51722-121">You can express the amount of coverage as a dollar amount or a percentage.</span></span> <span data-ttu-id="51722-122">Példa:</span><span class="sxs-lookup"><span data-stu-id="51722-122">For example:</span></span></br></br><span data-ttu-id="51722-123">- **Alk+1** – a minősítéshez az alkalmazottnak ki kell választania egy függő felet (ha egynél több van kiválasztva, már nem lehet jogosult).</span><span class="sxs-lookup"><span data-stu-id="51722-123">- **Emp+1** – to be qualified, the employee must have one dependent selected (if more than one is selected, they no longer qualify).</span></span></br></br><span data-ttu-id="51722-124">- **Alk+család** – a minősítéshez az alkalmazottnak legalább két függő felet kell kiválasztania.</span><span class="sxs-lookup"><span data-stu-id="51722-124">- **Emp+family** – to be qualified, the employee must have at least two dependents selected.</span></span> |
   | <span data-ttu-id="51722-125">**Maximális szám**</span><span class="sxs-lookup"><span data-stu-id="51722-125">**Maximum number**</span></span> | <span data-ttu-id="51722-126">A függő felek maximális száma.</span><span class="sxs-lookup"><span data-stu-id="51722-126">The maximum number of dependents.</span></span> |
   | <span data-ttu-id="51722-127">**Állapot**</span><span class="sxs-lookup"><span data-stu-id="51722-127">**Status**</span></span> | <span data-ttu-id="51722-128">A fedezeti beállítás állapota.</span><span class="sxs-lookup"><span data-stu-id="51722-128">The status of the coverage option.</span></span> <span data-ttu-id="51722-129">Ha a Fedezeti beállítás állapota inaktív értékre van állítva, akkor a program nem jelöli be a fedezeti beállítást a tervtípusokon.</span><span class="sxs-lookup"><span data-stu-id="51722-129">If the Coverage option status is set to Inactive, the Coverage option can’t be selected on plan types.</span></span> |
   | <span data-ttu-id="51722-130">**Százalék**</span><span class="sxs-lookup"><span data-stu-id="51722-130">**Percent**</span></span> | <span data-ttu-id="51722-131">A százalékos összeg.</span><span class="sxs-lookup"><span data-stu-id="51722-131">The percent amount.</span></span> <span data-ttu-id="51722-132">Ez a mező csak akkor aktív, ha a Fedezet kódja mezőben % x Fizetés van kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="51722-132">This field is only active if % x Salary was selected in the Coverage code field.</span></span> |
   | <span data-ttu-id="51722-133">**Osztó**</span><span class="sxs-lookup"><span data-stu-id="51722-133">**Divisor**</span></span> | <span data-ttu-id="51722-134">A(z) % x fedezeti kód kiválasztásakor a számításban használt osztó.</span><span class="sxs-lookup"><span data-stu-id="51722-134">The divisor to use in the calculation when you select the coverage code % x salary.</span></span> |
   | <span data-ttu-id="51722-135">**Százalék minimuma**</span><span class="sxs-lookup"><span data-stu-id="51722-135">**Percent minimum**</span></span> | <span data-ttu-id="51722-136">Minimális százalék a százalékos fedezeti kód kiválasztása esetén.</span><span class="sxs-lookup"><span data-stu-id="51722-136">The minimum percentage when you select the Percentage coverage code.</span></span> |
   | <span data-ttu-id="51722-137">**Százalék maximuma**</span><span class="sxs-lookup"><span data-stu-id="51722-137">**Percent maximum**</span></span> | <span data-ttu-id="51722-138">Maximális százalék a százalékos fedezeti kód kiválasztása esetén.</span><span class="sxs-lookup"><span data-stu-id="51722-138">The maximum percentage when you select the Percentage coverage code.</span></span> |

4. <span data-ttu-id="51722-139">A **Személyes kapcsolattartásra vonatkozó jogosultsági beállítások** pontban csatolja a megfelelő személyes kapcsolattartók jogosultsági beállítását mindegyik fedezeti beállításhoz.</span><span class="sxs-lookup"><span data-stu-id="51722-139">Under **Personal contact eligibility options**, attach the appropriate personal contacts eligibility option to each coverage option.</span></span>

5. <span data-ttu-id="51722-140">Az **Önkiszolgálás** pontban adja meg a megfelelő értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="51722-140">Under **Self service**, specify values for the following fields:</span></span>

   | <span data-ttu-id="51722-141">Mező</span><span class="sxs-lookup"><span data-stu-id="51722-141">Field</span></span> | <span data-ttu-id="51722-142">Leírás</span><span class="sxs-lookup"><span data-stu-id="51722-142">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="51722-143">**Alkalmazotti hozzájárulás összegének engedélyezése**</span><span class="sxs-lookup"><span data-stu-id="51722-143">**Allow employee contribution amount**</span></span> | <span data-ttu-id="51722-144">Azt adja meg, hogy az alkalmazottak módosíthatják-e az önkiszolgálói juttatás összegét a juttatások kiválasztása alkalmával.</span><span class="sxs-lookup"><span data-stu-id="51722-144">Specifies whether to allow employees to modify the contribution amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="51722-145">Ha bejelöli ezt a jelölőnégyzetet, a rendszer kiszámítja a juttatási terv paramétereit azon hozzájárulás összege alapján, amelyet az alkalmazott önkiszolgáló juttatásként megad.</span><span class="sxs-lookup"><span data-stu-id="51722-145">If you select this check box, the system will calculate benefit plan parameters based on the contribution amount the employee enters on benefits self-service.</span></span> |
   | <span data-ttu-id="51722-146">**Alkalmazotti fedezet összegének engedélyezése**</span><span class="sxs-lookup"><span data-stu-id="51722-146">**Allow employee coverage amount**</span></span> | <span data-ttu-id="51722-147">Azt adja meg, hogy az alkalmazottak módosíthatják-e a fedezeti juttatás önkiszolgálói összegét a juttatások kiválasztása alkalmával.</span><span class="sxs-lookup"><span data-stu-id="51722-147">Specifies whether to allow employees to modify the coverage amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="51722-148">Ha bejelöli ezt a jelölőnégyzetet, a rendszer kiszámítja a juttatási terv paramétereit azon fedezeti összeg alapján, amelyet az alkalmazott önkiszolgáló alkalmazottként megad.</span><span class="sxs-lookup"><span data-stu-id="51722-148">If you select this check box, the system will calculate benefit plan parameters based on the coverage amount the employee enters in Employee self service.</span></span> |

6. <span data-ttu-id="51722-149">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="51722-149">Select **Save**.</span></span> 
