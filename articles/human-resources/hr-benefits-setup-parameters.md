---
title: A juttatáskezelés paramétereinek beállítása
description: A Juttatáskezelés paramétereinek konfigurálása a Microsoft Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
manager: tfehr
ms.date: 07/16/2020
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
ms.openlocfilehash: cb9dd6eb8ef840dab54eabab8526200a3a8e21f0
ms.sourcegitcommit: e100c1c7c8dcdacf066defc206dd2f44b8ce6100
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/20/2020
ms.locfileid: "4057028"
---
# <a name="set-benefits-management-parameters"></a><span data-ttu-id="3c01a-103">Juttatáskezelés paramétereinek beállítása</span><span class="sxs-lookup"><span data-stu-id="3c01a-103">Set Benefits management parameters</span></span>

<span data-ttu-id="3c01a-104">Mielőtt beállítaná a szabadságterveket a Microsoft Dynamics 365 Human Resources alkalmazásban, konfigurálnia kell a Juttatáskezelés paramétereit.</span><span class="sxs-lookup"><span data-stu-id="3c01a-104">Before you can set up leave plans in Microsoft Dynamics 365 Human Resources, you must configure Benefits management parameters.</span></span> <span data-ttu-id="3c01a-105">Ezek a paraméterek az alapértelmezett értékeket, okkódokat és egyéb beállításokat határozzák meg.</span><span class="sxs-lookup"><span data-stu-id="3c01a-105">These parameters set default values, reason codes, and other options.</span></span>

## <a name="configure-general-parameters"></a><span data-ttu-id="3c01a-106">Általános paraméterek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="3c01a-106">Configure general parameters</span></span>

1. <span data-ttu-id="3c01a-107">A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Emberi erőforrások megosztott paraméterei** elemet.</span><span class="sxs-lookup"><span data-stu-id="3c01a-107">In the **Benefits management** workspace, under **Setup** , select **Human Resources Shared Parameters**.</span></span>

2. <span data-ttu-id="3c01a-108">Az **Általános** lapon adja meg a megfelelő értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="3c01a-108">In the **General** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="3c01a-109">Mező</span><span class="sxs-lookup"><span data-stu-id="3c01a-109">Field</span></span> | <span data-ttu-id="3c01a-110">Leírás</span><span class="sxs-lookup"><span data-stu-id="3c01a-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="3c01a-111">**Ország/régió**</span><span class="sxs-lookup"><span data-stu-id="3c01a-111">**Country/region**</span></span> | <span data-ttu-id="3c01a-112">Az **Ország/régió** mező határozza meg az irányítószámok/államok megjelenítési sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="3c01a-112">The **Country/region** field determines the display order of ZIP codes/states.</span></span> <span data-ttu-id="3c01a-113">A kiválasztott ország/régió jelenik meg elsőként a legördülő listában.</span><span class="sxs-lookup"><span data-stu-id="3c01a-113">The selected country displays first in the dropdown list.</span></span> |
   | <span data-ttu-id="3c01a-114">**Regisztráció okkódja**</span><span class="sxs-lookup"><span data-stu-id="3c01a-114">**Enrollment reason code**</span></span> | <span data-ttu-id="3c01a-115">Válasszon ki egy alapértelmezett okkódot, amely az alkalmazotti tervek létrehozásakor kerül felhasználásra a nyitott regisztrációs feldolgozás során.</span><span class="sxs-lookup"><span data-stu-id="3c01a-115">Select a default reason code to use when employee plans are created during open enrollment processing.</span></span> |
   | <span data-ttu-id="3c01a-116">**Megszakítás okkódja**</span><span class="sxs-lookup"><span data-stu-id="3c01a-116">**Cancellation reason code**</span></span> | <span data-ttu-id="3c01a-117">Az alkalmazotti juttatási konstrukció érvénytelenítése során használandó okkód.</span><span class="sxs-lookup"><span data-stu-id="3c01a-117">The reason code to use when an employee benefit plan is canceled.</span></span> <span data-ttu-id="3c01a-118">Egy párbeszédablakban jelenik meg az érvénytelenítési folyamat során.</span><span class="sxs-lookup"><span data-stu-id="3c01a-118">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="3c01a-119">Ha szükséges, a felhasználók módosthatják az **Érvénytelenítési okkód** részben.</span><span class="sxs-lookup"><span data-stu-id="3c01a-119">Users can change it the **Cancellation reason code** if necessary.</span></span> |
   | <span data-ttu-id="3c01a-120">**Újranyitás okkódja**</span><span class="sxs-lookup"><span data-stu-id="3c01a-120">**Reopen reason code**</span></span> | <span data-ttu-id="3c01a-121">Az alkalmazotti juttatási konstrukció újranyitása során használandó okkód.</span><span class="sxs-lookup"><span data-stu-id="3c01a-121">The reason code to use when an employee benefit plan is reopened.</span></span> <span data-ttu-id="3c01a-122">Egy párbeszédablakban jelenik meg az érvénytelenítési folyamat során.</span><span class="sxs-lookup"><span data-stu-id="3c01a-122">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="3c01a-123">Ha szükséges, a felhasználók módosthatják az **Újranyitási okkód** részben.</span><span class="sxs-lookup"><span data-stu-id="3c01a-123">Users can change the **Reopen reason code** if necessary.</span></span> | 
   | <span data-ttu-id="3c01a-124">**Életesemény okkódja**</span><span class="sxs-lookup"><span data-stu-id="3c01a-124">**Life event reason code**</span></span> | <span data-ttu-id="3c01a-125">A élettartam-esemény bekövetkezésekor használandó okkód.</span><span class="sxs-lookup"><span data-stu-id="3c01a-125">The reason code to use when a life event occurs.</span></span> |
   | <span data-ttu-id="3c01a-126">**Díjváltozás okkódja**</span><span class="sxs-lookup"><span data-stu-id="3c01a-126">**Rate change reason code**</span></span> | <span data-ttu-id="3c01a-127">Az alkalmazotti juttatási konstrukciónak az árfolyam-módosítási frissítési folyamat során történő érvénytelenítése és újbóli megnyitása alkalmával használandó okkód.</span><span class="sxs-lookup"><span data-stu-id="3c01a-127">The reason code to use when canceling and reopening an employee benefit plan during the rate change update process.</span></span> <span data-ttu-id="3c01a-128">Azt jelzi, hogy az árfolyam-módosítási frissítési folyamat mely rekordokat módosította.</span><span class="sxs-lookup"><span data-stu-id="3c01a-128">It indicates which records were changed by the rate change update process.</span></span> |
   | <span data-ttu-id="3c01a-129">**Juttatások éves fizetése**</span><span class="sxs-lookup"><span data-stu-id="3c01a-129">**Benefits annual salary**</span></span> | <span data-ttu-id="3c01a-130">Lehetővé teszi az alkalmazottakra vonatkozó **Juttatások évi fizetési** összegének beállítását.</span><span class="sxs-lookup"><span data-stu-id="3c01a-130">Enables you to set a **Benefits annual salary** amount for an employee.</span></span> <span data-ttu-id="3c01a-131">Az emberi erőforrások a fix kompenzációs éves összeg helyett a fedezeti összegek meghatározásakor a **Juttatások évi fizetésének** összegét fogják használni.</span><span class="sxs-lookup"><span data-stu-id="3c01a-131">Human Resources will use the **Benefits annual salary** amount when determing coverage amounts, instead of the fixed compensation annual amount.</span></span> |
   | <span data-ttu-id="3c01a-132">**Új dolgozó jogosult**</span><span class="sxs-lookup"><span data-stu-id="3c01a-132">**New hire eligible**</span></span> | <span data-ttu-id="3c01a-133">Megadja, hogy az új dolgozók jogosultak-e.</span><span class="sxs-lookup"><span data-stu-id="3c01a-133">Specifies whether new hires are eligible.</span></span> |
   | <span data-ttu-id="3c01a-134">**Új dolgozó regisztrációs időszaka**</span><span class="sxs-lookup"><span data-stu-id="3c01a-134">**New hire enrollment period**</span></span> | <span data-ttu-id="3c01a-135">Az az időszak, amikor az új dolgozói regisztráció engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="3c01a-135">The period of time the new hire enrollment is allowed.</span></span></br></br><span data-ttu-id="3c01a-136">**Megjegyzés** : Ez a beállítás felülbírál minden új dolgozói regisztrációs időszakot, amelyet a konstrukció jogosultsági szabályai között beállított.</span><span class="sxs-lookup"><span data-stu-id="3c01a-136">**Note** : This setting overrides any new hire enrollment period you set on the plan eligibility rule.</span></span> |
   | <span data-ttu-id="3c01a-137">**Alapértelmezett fizetési gyakoriság**</span><span class="sxs-lookup"><span data-stu-id="3c01a-137">**Default pay frequency**</span></span> | <span data-ttu-id="3c01a-138">Az új dolgozók hozzáadásakor használt alapértelmezett fizetési gyakoriság.</span><span class="sxs-lookup"><span data-stu-id="3c01a-138">The default pay frequency to use when new workers are added.</span></span> |
   | <span data-ttu-id="3c01a-139">**Életesemények engedélyezve**</span><span class="sxs-lookup"><span data-stu-id="3c01a-139">**Life events enabled**</span></span> | <span data-ttu-id="3c01a-140">Élettartam-események engedélyezése.</span><span class="sxs-lookup"><span data-stu-id="3c01a-140">Enables life events.</span></span> |
   | <span data-ttu-id="3c01a-141">**Korábbi juttatási űrlapok elrejtése**</span><span class="sxs-lookup"><span data-stu-id="3c01a-141">**Hide legacy benefit forms**</span></span> | <span data-ttu-id="3c01a-142">Lehetővé teszi a korábbi juttatási űrlapok elrejtését.</span><span class="sxs-lookup"><span data-stu-id="3c01a-142">Allows you to hide legacy benefit forms.</span></span> |

3. <span data-ttu-id="3c01a-143">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3c01a-143">Select **Save**.</span></span>

## <a name="configure-employee-self-service-parameters"></a><span data-ttu-id="3c01a-144">Alkalmazotti önkiszolgáló rendszer paramétereinek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="3c01a-144">Configure Employee self service parameters</span></span>

1. <span data-ttu-id="3c01a-145">A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Emberi erőforrások paraméterei** elemet.</span><span class="sxs-lookup"><span data-stu-id="3c01a-145">In the **Benefits management** workspace, under **Setup** , select **Human Resources Parameters**.</span></span>

2. <span data-ttu-id="3c01a-146">A **Juttatások kezelése** lapon adja meg a megfelelő értékeket az alábbi mezőkben:</span><span class="sxs-lookup"><span data-stu-id="3c01a-146">In the **Benefits management** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="3c01a-147">Mező</span><span class="sxs-lookup"><span data-stu-id="3c01a-147">Field</span></span> | <span data-ttu-id="3c01a-148">Leírás</span><span class="sxs-lookup"><span data-stu-id="3c01a-148">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="3c01a-149">**Juttatás ellenőrzése**</span><span class="sxs-lookup"><span data-stu-id="3c01a-149">**Benefit verification**</span></span> | <span data-ttu-id="3c01a-150">Az önkiszolgáló juttatásfizetés során használandó ellenőrzési szöveg.</span><span class="sxs-lookup"><span data-stu-id="3c01a-150">The verification text to use during self-service benefits checkout.</span></span> |
   | <span data-ttu-id="3c01a-151">**Kijelölt személyek automatikus kiválasztása**</span><span class="sxs-lookup"><span data-stu-id="3c01a-151">**Auto select designees**</span></span> | <span data-ttu-id="3c01a-152">Megadja, hogy a program automatikusan kiválassza-e a függő feleket és a kedvezményezetteket a konstrukció opcióira való jogosultságuk alapján.</span><span class="sxs-lookup"><span data-stu-id="3c01a-152">Specifies whether to automatically select dependents and beneficiaries based on their eligibility for plan options.</span></span> |

3. <span data-ttu-id="3c01a-153">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3c01a-153">Select **Save**.</span></span>
