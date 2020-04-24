---
title: A juttatáskezelés paramétereinek beállítása
description: A Juttatáskezelés paramétereinek konfigurálása a Microsoft Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
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
ms.openlocfilehash: 9d6d463df08b9ae68047f09316f19e98740a8441
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/06/2020
ms.locfileid: "3229763"
---
# <a name="set-benefits-management-parameters"></a><span data-ttu-id="122d7-103">Juttatáskezelés paramétereinek beállítása</span><span class="sxs-lookup"><span data-stu-id="122d7-103">Set Benefits management parameters</span></span>

<span data-ttu-id="122d7-104">Mielőtt beállítaná a szabadságterveket a Microsoft Dynamics 365 Human Resources alkalmazásban, konfigurálnia kell a Juttatáskezelés paramétereit.</span><span class="sxs-lookup"><span data-stu-id="122d7-104">Before you can set up leave plans in Microsoft Dynamics 365 Human Resources, you must configure Benefits management parameters.</span></span> <span data-ttu-id="122d7-105">Ezek a paraméterek az alapértelmezett értékeket, okkódokat és egyéb beállításokat határozzák meg.</span><span class="sxs-lookup"><span data-stu-id="122d7-105">These parameters set default values, reason codes, and other options.</span></span>

## <a name="configure-general-parameters"></a><span data-ttu-id="122d7-106">Általános paraméterek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="122d7-106">Configure general parameters</span></span>

1. <span data-ttu-id="122d7-107">A **Juttatások kezelése** munkaterület **Beállítás** részén válassza a **Paraméterek** elemet.</span><span class="sxs-lookup"><span data-stu-id="122d7-107">In the **Benefits management** workspace, under **Setup**, select **Parameters**.</span></span>

2. <span data-ttu-id="122d7-108">Az **Általános** lapon adja meg a megfelelő értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="122d7-108">In the **General** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="122d7-109">Mező</span><span class="sxs-lookup"><span data-stu-id="122d7-109">Field</span></span> | <span data-ttu-id="122d7-110">Leírás</span><span class="sxs-lookup"><span data-stu-id="122d7-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="122d7-111">**Ország/régió**</span><span class="sxs-lookup"><span data-stu-id="122d7-111">**Country/region**</span></span> | <span data-ttu-id="122d7-112">Az **Ország/régió** mező határozza meg az irányítószámok/államok megjelenítési sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="122d7-112">The **Country/region** field determines the display order of ZIP codes/states.</span></span> <span data-ttu-id="122d7-113">A kiválasztott ország jelenik meg elsőként a legördülő listában.</span><span class="sxs-lookup"><span data-stu-id="122d7-113">The selected country displays first in the dropdown list.</span></span> |
   | <span data-ttu-id="122d7-114">**Regisztráció okkódja**</span><span class="sxs-lookup"><span data-stu-id="122d7-114">**Enrollment reason code**</span></span> | <span data-ttu-id="122d7-115">Válasszon ki egy alapértelmezett okkódot, amely az alkalmazotti tervek létrehozásakor kerül felhasználásra a nyitott regisztrációs feldolgozás során.</span><span class="sxs-lookup"><span data-stu-id="122d7-115">Select a default reason code to use when employee plans are created during open enrollment processing.</span></span> |
   | <span data-ttu-id="122d7-116">**Megszakítás okkódja**</span><span class="sxs-lookup"><span data-stu-id="122d7-116">**Cancellation reason code**</span></span> | <span data-ttu-id="122d7-117">Az alkalmazotti juttatási konstrukció érvénytelenítése során használandó okkód.</span><span class="sxs-lookup"><span data-stu-id="122d7-117">The reason code to use when an employee benefit plan is canceled.</span></span> <span data-ttu-id="122d7-118">Egy párbeszédablakban jelenik meg az érvénytelenítési folyamat során.</span><span class="sxs-lookup"><span data-stu-id="122d7-118">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="122d7-119">Ha szükséges, a felhasználók módosthatják az **Érvénytelenítési okkód** részben.</span><span class="sxs-lookup"><span data-stu-id="122d7-119">Users can change it the **Cancellation reason code** if necessary.</span></span> |
   | <span data-ttu-id="122d7-120">**Újranyitás okkódja**</span><span class="sxs-lookup"><span data-stu-id="122d7-120">**Reopen reason code**</span></span> | <span data-ttu-id="122d7-121">Az alkalmazotti juttatási konstrukció újranyitása során használandó okkód.</span><span class="sxs-lookup"><span data-stu-id="122d7-121">The reason code to use when an employee benefit plan is reopened.</span></span> <span data-ttu-id="122d7-122">Egy párbeszédablakban jelenik meg az érvénytelenítési folyamat során.</span><span class="sxs-lookup"><span data-stu-id="122d7-122">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="122d7-123">Ha szükséges, a felhasználók módosthatják az **Újranyitási okkód** részben.</span><span class="sxs-lookup"><span data-stu-id="122d7-123">Users can change the **Reopen reason code** if necessary.</span></span> | 
   | <span data-ttu-id="122d7-124">**Életesemény okkódja**</span><span class="sxs-lookup"><span data-stu-id="122d7-124">**Life event reason code**</span></span> | <span data-ttu-id="122d7-125">A élettartam-esemény bekövetkezésekor használandó okkód.</span><span class="sxs-lookup"><span data-stu-id="122d7-125">The reason code to use when a life event occurs.</span></span> |
   | <span data-ttu-id="122d7-126">**Díjváltozás okkódja**</span><span class="sxs-lookup"><span data-stu-id="122d7-126">**Rate change reason code**</span></span> | <span data-ttu-id="122d7-127">Az alkalmazotti juttatási konstrukciónak az árfolyam-módosítási frissítési folyamat során történő érvénytelenítése és újbóli megnyitása alkalmával használandó okkód.</span><span class="sxs-lookup"><span data-stu-id="122d7-127">The reason code to use when canceling and reopening an employee benefit plan during the rate change update process.</span></span> <span data-ttu-id="122d7-128">Azt jelzi, hogy az árfolyam-módosítási frissítési folyamat mely rekordokat módosította.</span><span class="sxs-lookup"><span data-stu-id="122d7-128">It indicates which records were changed by the rate change update process.</span></span> |
   | <span data-ttu-id="122d7-129">**Új dolgozó jogosult**</span><span class="sxs-lookup"><span data-stu-id="122d7-129">**New hire eligible**</span></span> | <span data-ttu-id="122d7-130">Megadja, hogy az új dolgozók jogosultak-e.</span><span class="sxs-lookup"><span data-stu-id="122d7-130">Specifies whether new hires are eligible.</span></span> |
   | <span data-ttu-id="122d7-131">**Új dolgozó regisztrációs időszaka**</span><span class="sxs-lookup"><span data-stu-id="122d7-131">**New hire enrollment period**</span></span> | <span data-ttu-id="122d7-132">Az az időszak, amikor az új dolgozói regisztráció engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="122d7-132">The period of time the new hire enrollment is allowed.</span></span></br></br><span data-ttu-id="122d7-133">**Megjegyzés**: Ez a beállítás felülbírál minden új dolgozói regisztrációs időszakot, amelyet a konstrukció jogosultsági szabályai között beállított.</span><span class="sxs-lookup"><span data-stu-id="122d7-133">**Note**: This setting overrides any new hire enrollment period you set on the plan eligibility rule.</span></span> | 
   | <span data-ttu-id="122d7-134">**Életesemények engedélyezve**</span><span class="sxs-lookup"><span data-stu-id="122d7-134">**Life events enabled**</span></span> | <span data-ttu-id="122d7-135">Élettartam-események engedélyezése.</span><span class="sxs-lookup"><span data-stu-id="122d7-135">Enables life events.</span></span> |
   | <span data-ttu-id="122d7-136">**Korábbi juttatási űrlapok elrejtése**</span><span class="sxs-lookup"><span data-stu-id="122d7-136">**Hide legacy benefit forms**</span></span> | <span data-ttu-id="122d7-137">Lehetővé teszi a korábbi juttatási űrlapok elrejtését.</span><span class="sxs-lookup"><span data-stu-id="122d7-137">Allows you to hide legacy benefit forms.</span></span> |

3. <span data-ttu-id="122d7-138">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="122d7-138">Select **Save**.</span></span>

## <a name="configure-employee-self-service-parameters"></a><span data-ttu-id="122d7-139">Alkalmazotti önkiszolgáló rendszer paramétereinek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="122d7-139">Configure Employee self service parameters</span></span>

1. <span data-ttu-id="122d7-140">A **Juttatások kezelése** munkaterület **Beállítás** részén válassza a **Paraméterek** elemet.</span><span class="sxs-lookup"><span data-stu-id="122d7-140">In the **Benefits management** workspace, under **Setup**, select **Parameters**.</span></span>

2. <span data-ttu-id="122d7-141">Az **Alkalmazotti önkiszolgáló rendszer** lapon adja meg a megfelelő értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="122d7-141">In the **Employee self service** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="122d7-142">Mező</span><span class="sxs-lookup"><span data-stu-id="122d7-142">Field</span></span> | <span data-ttu-id="122d7-143">Leírás</span><span class="sxs-lookup"><span data-stu-id="122d7-143">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="122d7-144">**Juttatás ellenőrzése**</span><span class="sxs-lookup"><span data-stu-id="122d7-144">**Benefit verification**</span></span> | <span data-ttu-id="122d7-145">Az önkiszolgáló juttatásfizetés során használandó ellenőrzési szöveg.</span><span class="sxs-lookup"><span data-stu-id="122d7-145">The verification text to use during self-service benefits checkout.</span></span> |
   | <span data-ttu-id="122d7-146">**Kijelölt személyek automatikus kiválasztása**</span><span class="sxs-lookup"><span data-stu-id="122d7-146">**Auto select designees**</span></span> | <span data-ttu-id="122d7-147">Megadja, hogy a program automatikusan kiválassza-e a függő feleket és a kedvezményezetteket a konstrukció opcióira való jogosultságuk alapján.</span><span class="sxs-lookup"><span data-stu-id="122d7-147">Specifies whether to automatically select dependents and beneficiaries based on their eligibility for plan options.</span></span> |

3. <span data-ttu-id="122d7-148">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="122d7-148">Select **Save**.</span></span>
