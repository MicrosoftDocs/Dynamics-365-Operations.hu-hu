---
title: A juttatáskezelés paramétereinek beállítása
description: A Juttatáskezelés paramétereinek konfigurálása a Microsoft Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
manager: AnnBe
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
ms.openlocfilehash: 85bbe5d3b422f2f29f1d1fe8ee269b407da691c2
ms.sourcegitcommit: 9dc5c7dd5877cc6e7cd0059d173bcd8052ba13bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/16/2020
ms.locfileid: "3599356"
---
# <a name="set-benefits-management-parameters"></a><span data-ttu-id="c5b1e-103">Juttatáskezelés paramétereinek beállítása</span><span class="sxs-lookup"><span data-stu-id="c5b1e-103">Set Benefits management parameters</span></span>

<span data-ttu-id="c5b1e-104">Mielőtt beállítaná a szabadságterveket a Microsoft Dynamics 365 Human Resources alkalmazásban, konfigurálnia kell a Juttatáskezelés paramétereit.</span><span class="sxs-lookup"><span data-stu-id="c5b1e-104">Before you can set up leave plans in Microsoft Dynamics 365 Human Resources, you must configure Benefits management parameters.</span></span> <span data-ttu-id="c5b1e-105">Ezek a paraméterek az alapértelmezett értékeket, okkódokat és egyéb beállításokat határozzák meg.</span><span class="sxs-lookup"><span data-stu-id="c5b1e-105">These parameters set default values, reason codes, and other options.</span></span>

## <a name="configure-general-parameters"></a><span data-ttu-id="c5b1e-106">Általános paraméterek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c5b1e-106">Configure general parameters</span></span>

1. <span data-ttu-id="c5b1e-107">A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Emberi erőforrások megosztott paraméterei** elemet.</span><span class="sxs-lookup"><span data-stu-id="c5b1e-107">In the **Benefits management** workspace, under **Setup**, select **Human Resources Shared Parameters**.</span></span>

2. <span data-ttu-id="c5b1e-108">Az **Általános** lapon adja meg a megfelelő értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="c5b1e-108">In the **General** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="c5b1e-109">Mező</span><span class="sxs-lookup"><span data-stu-id="c5b1e-109">Field</span></span> | <span data-ttu-id="c5b1e-110">Leírás</span><span class="sxs-lookup"><span data-stu-id="c5b1e-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="c5b1e-111">**Ország/régió**</span><span class="sxs-lookup"><span data-stu-id="c5b1e-111">**Country/region**</span></span> | <span data-ttu-id="c5b1e-112">Az **Ország/régió** mező határozza meg az irányítószámok/államok megjelenítési sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="c5b1e-112">The **Country/region** field determines the display order of ZIP codes/states.</span></span> <span data-ttu-id="c5b1e-113">A kiválasztott ország jelenik meg elsőként a legördülő listában.</span><span class="sxs-lookup"><span data-stu-id="c5b1e-113">The selected country displays first in the dropdown list.</span></span> |
   | <span data-ttu-id="c5b1e-114">**Regisztráció okkódja**</span><span class="sxs-lookup"><span data-stu-id="c5b1e-114">**Enrollment reason code**</span></span> | <span data-ttu-id="c5b1e-115">Válasszon ki egy alapértelmezett okkódot, amely az alkalmazotti tervek létrehozásakor kerül felhasználásra a nyitott regisztrációs feldolgozás során.</span><span class="sxs-lookup"><span data-stu-id="c5b1e-115">Select a default reason code to use when employee plans are created during open enrollment processing.</span></span> |
   | <span data-ttu-id="c5b1e-116">**Megszakítás okkódja**</span><span class="sxs-lookup"><span data-stu-id="c5b1e-116">**Cancellation reason code**</span></span> | <span data-ttu-id="c5b1e-117">Az alkalmazotti juttatási konstrukció érvénytelenítése során használandó okkód.</span><span class="sxs-lookup"><span data-stu-id="c5b1e-117">The reason code to use when an employee benefit plan is canceled.</span></span> <span data-ttu-id="c5b1e-118">Egy párbeszédablakban jelenik meg az érvénytelenítési folyamat során.</span><span class="sxs-lookup"><span data-stu-id="c5b1e-118">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="c5b1e-119">Ha szükséges, a felhasználók módosthatják az **Érvénytelenítési okkód** részben.</span><span class="sxs-lookup"><span data-stu-id="c5b1e-119">Users can change it the **Cancellation reason code** if necessary.</span></span> |
   | <span data-ttu-id="c5b1e-120">**Újranyitás okkódja**</span><span class="sxs-lookup"><span data-stu-id="c5b1e-120">**Reopen reason code**</span></span> | <span data-ttu-id="c5b1e-121">Az alkalmazotti juttatási konstrukció újranyitása során használandó okkód.</span><span class="sxs-lookup"><span data-stu-id="c5b1e-121">The reason code to use when an employee benefit plan is reopened.</span></span> <span data-ttu-id="c5b1e-122">Egy párbeszédablakban jelenik meg az érvénytelenítési folyamat során.</span><span class="sxs-lookup"><span data-stu-id="c5b1e-122">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="c5b1e-123">Ha szükséges, a felhasználók módosthatják az **Újranyitási okkód** részben.</span><span class="sxs-lookup"><span data-stu-id="c5b1e-123">Users can change the **Reopen reason code** if necessary.</span></span> | 
   | <span data-ttu-id="c5b1e-124">**Életesemény okkódja**</span><span class="sxs-lookup"><span data-stu-id="c5b1e-124">**Life event reason code**</span></span> | <span data-ttu-id="c5b1e-125">A élettartam-esemény bekövetkezésekor használandó okkód.</span><span class="sxs-lookup"><span data-stu-id="c5b1e-125">The reason code to use when a life event occurs.</span></span> |
   | <span data-ttu-id="c5b1e-126">**Díjváltozás okkódja**</span><span class="sxs-lookup"><span data-stu-id="c5b1e-126">**Rate change reason code**</span></span> | <span data-ttu-id="c5b1e-127">Az alkalmazotti juttatási konstrukciónak az árfolyam-módosítási frissítési folyamat során történő érvénytelenítése és újbóli megnyitása alkalmával használandó okkód.</span><span class="sxs-lookup"><span data-stu-id="c5b1e-127">The reason code to use when canceling and reopening an employee benefit plan during the rate change update process.</span></span> <span data-ttu-id="c5b1e-128">Azt jelzi, hogy az árfolyam-módosítási frissítési folyamat mely rekordokat módosította.</span><span class="sxs-lookup"><span data-stu-id="c5b1e-128">It indicates which records were changed by the rate change update process.</span></span> |
   | <span data-ttu-id="c5b1e-129">**Juttatások éves fizetése**</span><span class="sxs-lookup"><span data-stu-id="c5b1e-129">**Benefits annual salary**</span></span> | <span data-ttu-id="c5b1e-130">Lehetővé teszi az alkalmazottakra vonatkozó **Juttatások évi fizetési** összegének beállítását.</span><span class="sxs-lookup"><span data-stu-id="c5b1e-130">Enables you to set a **Benefits annual salary** amount for an employee.</span></span> <span data-ttu-id="c5b1e-131">Az emberi erőforrások a fix kompenzációs éves összeg helyett a fedezeti összegek meghatározásakor a **Juttatások évi fizetésének** összegét fogják használni.</span><span class="sxs-lookup"><span data-stu-id="c5b1e-131">Human Resources will use the **Benefits annual salary** amount when determing coverage amounts, instead of the fixed compensation annual amount.</span></span> |
   | <span data-ttu-id="c5b1e-132">**Új dolgozó jogosult**</span><span class="sxs-lookup"><span data-stu-id="c5b1e-132">**New hire eligible**</span></span> | <span data-ttu-id="c5b1e-133">Megadja, hogy az új dolgozók jogosultak-e.</span><span class="sxs-lookup"><span data-stu-id="c5b1e-133">Specifies whether new hires are eligible.</span></span> |
   | <span data-ttu-id="c5b1e-134">**Új dolgozó regisztrációs időszaka**</span><span class="sxs-lookup"><span data-stu-id="c5b1e-134">**New hire enrollment period**</span></span> | <span data-ttu-id="c5b1e-135">Az az időszak, amikor az új dolgozói regisztráció engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="c5b1e-135">The period of time the new hire enrollment is allowed.</span></span></br></br><span data-ttu-id="c5b1e-136">**Megjegyzés**: Ez a beállítás felülbírál minden új dolgozói regisztrációs időszakot, amelyet a konstrukció jogosultsági szabályai között beállított.</span><span class="sxs-lookup"><span data-stu-id="c5b1e-136">**Note**: This setting overrides any new hire enrollment period you set on the plan eligibility rule.</span></span> |
   | <span data-ttu-id="c5b1e-137">**Alapértelmezett fizetési gyakoriság**</span><span class="sxs-lookup"><span data-stu-id="c5b1e-137">**Default pay frequency**</span></span> | <span data-ttu-id="c5b1e-138">Az új dolgozók hozzáadásakor használt alapértelmezett fizetési gyakoriság.</span><span class="sxs-lookup"><span data-stu-id="c5b1e-138">The default pay frequency to use when new workers are added.</span></span> |
   | <span data-ttu-id="c5b1e-139">**Életesemények engedélyezve**</span><span class="sxs-lookup"><span data-stu-id="c5b1e-139">**Life events enabled**</span></span> | <span data-ttu-id="c5b1e-140">Élettartam-események engedélyezése.</span><span class="sxs-lookup"><span data-stu-id="c5b1e-140">Enables life events.</span></span> |
   | <span data-ttu-id="c5b1e-141">**Korábbi juttatási űrlapok elrejtése**</span><span class="sxs-lookup"><span data-stu-id="c5b1e-141">**Hide legacy benefit forms**</span></span> | <span data-ttu-id="c5b1e-142">Lehetővé teszi a korábbi juttatási űrlapok elrejtését.</span><span class="sxs-lookup"><span data-stu-id="c5b1e-142">Allows you to hide legacy benefit forms.</span></span> |

3. <span data-ttu-id="c5b1e-143">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c5b1e-143">Select **Save**.</span></span>

## <a name="configure-employee-self-service-parameters"></a><span data-ttu-id="c5b1e-144">Alkalmazotti önkiszolgáló rendszer paramétereinek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c5b1e-144">Configure Employee self service parameters</span></span>

1. <span data-ttu-id="c5b1e-145">A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Emberi erőforrások paraméterei** elemet.</span><span class="sxs-lookup"><span data-stu-id="c5b1e-145">In the **Benefits management** workspace, under **Setup**, select **Human Resources Parameters**.</span></span>

2. <span data-ttu-id="c5b1e-146">Az **Alkalmazotti önkiszolgáló rendszer** lapon adja meg a megfelelő értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="c5b1e-146">In the **Employee self service** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="c5b1e-147">Mező</span><span class="sxs-lookup"><span data-stu-id="c5b1e-147">Field</span></span> | <span data-ttu-id="c5b1e-148">Leírás</span><span class="sxs-lookup"><span data-stu-id="c5b1e-148">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="c5b1e-149">**Juttatás ellenőrzése**</span><span class="sxs-lookup"><span data-stu-id="c5b1e-149">**Benefit verification**</span></span> | <span data-ttu-id="c5b1e-150">Az önkiszolgáló juttatásfizetés során használandó ellenőrzési szöveg.</span><span class="sxs-lookup"><span data-stu-id="c5b1e-150">The verification text to use during self-service benefits checkout.</span></span> |
   | <span data-ttu-id="c5b1e-151">**Kijelölt személyek automatikus kiválasztása**</span><span class="sxs-lookup"><span data-stu-id="c5b1e-151">**Auto select designees**</span></span> | <span data-ttu-id="c5b1e-152">Megadja, hogy a program automatikusan kiválassza-e a függő feleket és a kedvezményezetteket a konstrukció opcióira való jogosultságuk alapján.</span><span class="sxs-lookup"><span data-stu-id="c5b1e-152">Specifies whether to automatically select dependents and beneficiaries based on their eligibility for plan options.</span></span> |

3. <span data-ttu-id="c5b1e-153">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c5b1e-153">Select **Save**.</span></span>
