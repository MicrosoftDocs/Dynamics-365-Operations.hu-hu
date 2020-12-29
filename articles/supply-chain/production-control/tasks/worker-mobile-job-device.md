---
title: Dolgozó konfigurálása mobil feladatvégző eszközzel
description: Ez a témakör bemutatja, hogyan lehet a megfelelő szerepköröket hozzárendelni egy dolgozó felhasználói fiókjához, és ezt követően engedélyezni a dolgozónak az üzemi regisztrációk végrehajtását.
author: ShylaThompson
manager: tfehr
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, HcmWorker, JmgRegistrationSetupTouch, JmgRegistrationSetupAssignUsers
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ada42a98a8a87e377f939d063b17f9904f6b3408
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429684"
---
# <a name="configure-a-worker-using-the-mobile-job-device"></a><span data-ttu-id="1857e-103">Dolgozó konfigurálása mobil feladatvégző eszközzel</span><span class="sxs-lookup"><span data-stu-id="1857e-103">Configure a worker using the mobile job device</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1857e-104">Ez a témakör bemutatja, hogyan lehet a megfelelő szerepköröket hozzárendelni egy dolgozó felhasználói fiókjához, és ezt követően engedélyezni a dolgozónak az üzemi regisztrációk végrehajtását.</span><span class="sxs-lookup"><span data-stu-id="1857e-104">This topic explains how to assign the correct roles to the user account of a worker, and then enable the worker to do shop floor registrations.</span></span>

## <a name="verify-that-a-worker-is-assigned-a-certain-role"></a><span data-ttu-id="1857e-105">Annak ellenőrzése, hogy a dolgozó hozzá van-e rendelve egy adott szerephez</span><span class="sxs-lookup"><span data-stu-id="1857e-105">Verify that a worker is assigned a certain role</span></span>

<span data-ttu-id="1857e-106">Ebben a példában a dolgozó fiókjának konfigurálása előtt ellenőrizze, hogy a „SHANNON” nevű felhasználó hozzá van-e rendelve a gépkezelői szerepkörhöz.</span><span class="sxs-lookup"><span data-stu-id="1857e-106">For this example, verify that user "SHANNON" is assigned the machine operator role before you configure the worker account.</span></span>

1. <span data-ttu-id="1857e-107">Ugorjon a **Navigációs ablaktábla > Modulok > Rendszerfelügyelet > Felhasználók > Felhasználók** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1857e-107">Go to **Navigation pane > Modules > System administration > Users > Users**.</span></span>
2. <span data-ttu-id="1857e-108">Keressen felhasználót a gyorsszűrőben.</span><span class="sxs-lookup"><span data-stu-id="1857e-108">Search for a user in the quick filter.</span></span> <span data-ttu-id="1857e-109">Ennél a példánál adja meg a `shannon` nevet.</span><span class="sxs-lookup"><span data-stu-id="1857e-109">For this example, enter `shannon`.</span></span>
3. <span data-ttu-id="1857e-110">Válassza ki a hivatkozást a felhasználói fiók **Felhasználóazonosító** oszlopában.</span><span class="sxs-lookup"><span data-stu-id="1857e-110">Select the link in the **User ID** column of the user account that appears.</span></span>
4. <span data-ttu-id="1857e-111">A **Felhasználói szerepkörök** fán, válassza ki a **Szerepkörök > Gépkezelő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1857e-111">In the **User's roles** tree, select **Roles > Machine operator**.</span></span>
5. <span data-ttu-id="1857e-112">A kezdőlapra való visszatéréshez zárja be a **felhasználói adatok** és **felhasználók** oldalakat.</span><span class="sxs-lookup"><span data-stu-id="1857e-112">Close the **user details** and **users** pages to return to the home page.</span></span>

## <a name="configure-worker-account"></a><span data-ttu-id="1857e-113">Konfigurálja a dolgozó fiókját</span><span class="sxs-lookup"><span data-stu-id="1857e-113">Configure worker account</span></span>
1. <span data-ttu-id="1857e-114">Ugorjon a **Navigációs ablaktábla > Modulok > Emberi erőforrások > Dolgozók > Dolgozók >** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1857e-114">Go to **Navigation pane > Modules > Human resources > Workers > Workers**.</span></span>
2. <span data-ttu-id="1857e-115">Keressen felhasználót a gyorsszűrőben.</span><span class="sxs-lookup"><span data-stu-id="1857e-115">Search for a user in the quick filter.</span></span> <span data-ttu-id="1857e-116">Ennél a példánál adja meg a `shannon` nevet.</span><span class="sxs-lookup"><span data-stu-id="1857e-116">For this example, enter `shannon`.</span></span>
3. <span data-ttu-id="1857e-117">Válassza ki a hivatkozást a felhasználói fiók **Név** oszlopában.</span><span class="sxs-lookup"><span data-stu-id="1857e-117">Select the link in the **Name** column of the user account that appears.</span></span>
4. <span data-ttu-id="1857e-118">Válassza ki az **Időnyilvántartás** fület.</span><span class="sxs-lookup"><span data-stu-id="1857e-118">Select the **Time registration** tab.</span></span>
5. <span data-ttu-id="1857e-119">Válassza ki az **Aktiválás a regisztrációs terminálokon** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1857e-119">Select **Activate on registration terminals**.</span></span>
6. <span data-ttu-id="1857e-120">Adja meg vagy válassza ki a következő mezőkben szereplő értékeket:</span><span class="sxs-lookup"><span data-stu-id="1857e-120">Enter or select values in the following fields:</span></span>  

    - <span data-ttu-id="1857e-121">**Számítási csoport**</span><span class="sxs-lookup"><span data-stu-id="1857e-121">**Calculation group**</span></span>  
    - <span data-ttu-id="1857e-122">**Alapértelmezett számítási csoport**</span><span class="sxs-lookup"><span data-stu-id="1857e-122">**Default calculation group**</span></span>  
    - <span data-ttu-id="1857e-123">**Jóváhagyási csoport**</span><span class="sxs-lookup"><span data-stu-id="1857e-123">**Approval group**</span></span>  
    - <span data-ttu-id="1857e-124">**Szokásos profil**</span><span class="sxs-lookup"><span data-stu-id="1857e-124">**Standard profile**</span></span>  
    - <span data-ttu-id="1857e-125">**Profilcsoport**</span><span class="sxs-lookup"><span data-stu-id="1857e-125">**Profile group**</span></span>  

7. <span data-ttu-id="1857e-126">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1857e-126">Select **OK**.</span></span>
8. <span data-ttu-id="1857e-127">Válassza ki a **Szerkesztés** lehetőséget az új munkaidő-nyilvántartásos dolgozó belépőkártyaszámának megadásához.</span><span class="sxs-lookup"><span data-stu-id="1857e-127">Select **Edit** to enter a badge number for the new time registration worker.</span></span> <span data-ttu-id="1857e-128">Adjon meg egy értéket a **Belépőkártya azonosítója** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1857e-128">Enter a value in the **Badge ID** field.</span></span>
9. <span data-ttu-id="1857e-129">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1857e-129">Select **Save**.</span></span>
10. <span data-ttu-id="1857e-130">Zárja be a **Dolgozó részletes adatai** és **Dolgozók** oldalt.</span><span class="sxs-lookup"><span data-stu-id="1857e-130">Close the **Worker details** and **Workers** pages.</span></span>

## <a name="assign-worker-to-device-group"></a><span data-ttu-id="1857e-131">Dolgozó társítása eszközcsoporthoz</span><span class="sxs-lookup"><span data-stu-id="1857e-131">Assign worker to device group</span></span>
1. <span data-ttu-id="1857e-132">Ugorjon a **Gyártásvezérlés > Beállítás > Gyártásvégrehajtás > Feladatkártya konfigurálása az eszközökhöz** elemre.</span><span class="sxs-lookup"><span data-stu-id="1857e-132">Go to **Production control > Setup > Manufacturing execution > Configure job card for devices**.</span></span>
2. <span data-ttu-id="1857e-133">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1857e-133">Select **Add**.</span></span>
3. <span data-ttu-id="1857e-134">Válassza ki a listából a kívánt dolgozót.</span><span class="sxs-lookup"><span data-stu-id="1857e-134">In the list, select the desired worker.</span></span> <span data-ttu-id="1857e-135">Ebben a példában válassza ki **SHANNON-t**.</span><span class="sxs-lookup"><span data-stu-id="1857e-135">For this example, select **SHANNON**.</span></span>
4. <span data-ttu-id="1857e-136">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1857e-136">Select **OK**.</span></span>
5. <span data-ttu-id="1857e-137">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="1857e-137">Select **Edit**.</span></span>
6. <span data-ttu-id="1857e-138">A **Termelési egység** mezőben megadhatja az alapértelmezett szűrőt a dolgozóhoz.</span><span class="sxs-lookup"><span data-stu-id="1857e-138">In the **Production unit** field, you can set the default filter for the worker.</span></span> <span data-ttu-id="1857e-139">Ez biztosítja, hogy csak a kijelölt termelési egység termelési feladatai jelenjenek meg, amikor a dolgozó bejelentkezik az eszközön.</span><span class="sxs-lookup"><span data-stu-id="1857e-139">This will ensure that only production jobs for the selected production unit are shown when the worker logs on to the device.</span></span> <span data-ttu-id="1857e-140">Adja meg a kívánt értéket.</span><span class="sxs-lookup"><span data-stu-id="1857e-140">Enter the desired value.</span></span>
7. <span data-ttu-id="1857e-141">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1857e-141">Close the page.</span></span>

