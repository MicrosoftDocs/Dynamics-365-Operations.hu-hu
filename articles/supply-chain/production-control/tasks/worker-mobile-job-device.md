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
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6210cdeed99f26a6b58b75d9f5405c0e1ee5aef1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213330"
---
# <a name="configure-a-worker-using-the-mobile-job-device"></a><span data-ttu-id="a2e1b-103">Dolgozó konfigurálása mobil feladatvégző eszközzel</span><span class="sxs-lookup"><span data-stu-id="a2e1b-103">Configure a worker using the mobile job device</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a2e1b-104">Ez a témakör bemutatja, hogyan lehet a megfelelő szerepköröket hozzárendelni egy dolgozó felhasználói fiókjához, és ezt követően engedélyezni a dolgozónak az üzemi regisztrációk végrehajtását.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-104">This topic explains how to assign the correct roles to the user account of a worker, and then enable the worker to do shop floor registrations.</span></span>

## <a name="verify-that-a-worker-is-assigned-a-certain-role"></a><span data-ttu-id="a2e1b-105">Annak ellenőrzése, hogy a dolgozó hozzá van-e rendelve egy adott szerephez</span><span class="sxs-lookup"><span data-stu-id="a2e1b-105">Verify that a worker is assigned a certain role</span></span>

<span data-ttu-id="a2e1b-106">Ebben a példában a dolgozó fiókjának konfigurálása előtt ellenőrizze, hogy a „SHANNON” nevű felhasználó hozzá van-e rendelve a gépkezelői szerepkörhöz.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-106">For this example, verify that user "SHANNON" is assigned the machine operator role before you configure the worker account.</span></span>

1. <span data-ttu-id="a2e1b-107">Ugorjon a **Navigációs ablaktábla > Modulok > Rendszerfelügyelet > Felhasználók > Felhasználók** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-107">Go to **Navigation pane > Modules > System administration > Users > Users**.</span></span>
2. <span data-ttu-id="a2e1b-108">Keressen felhasználót a gyorsszűrőben.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-108">Search for a user in the quick filter.</span></span> <span data-ttu-id="a2e1b-109">Ennél a példánál adja meg a `shannon` nevet.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-109">For this example, enter `shannon`.</span></span>
3. <span data-ttu-id="a2e1b-110">Válassza ki a hivatkozást a felhasználói fiók **Felhasználóazonosító** oszlopában.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-110">Select the link in the **User ID** column of the user account that appears.</span></span>
4. <span data-ttu-id="a2e1b-111">A **Felhasználói szerepkörök** fán, válassza ki a **Szerepkörök > Gépkezelő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-111">In the **User's roles** tree, select **Roles > Machine operator**.</span></span>
5. <span data-ttu-id="a2e1b-112">A kezdőlapra való visszatéréshez zárja be a **felhasználói adatok** és **felhasználók** oldalakat.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-112">Close the **user details** and **users** pages to return to the home page.</span></span>

## <a name="configure-worker-account"></a><span data-ttu-id="a2e1b-113">Konfigurálja a dolgozó fiókját</span><span class="sxs-lookup"><span data-stu-id="a2e1b-113">Configure worker account</span></span>
1. <span data-ttu-id="a2e1b-114">Ugorjon a **Navigációs ablaktábla > Modulok > Emberi erőforrások > Dolgozók > Dolgozók >** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-114">Go to **Navigation pane > Modules > Human resources > Workers > Workers**.</span></span>
2. <span data-ttu-id="a2e1b-115">Keressen felhasználót a gyorsszűrőben.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-115">Search for a user in the quick filter.</span></span> <span data-ttu-id="a2e1b-116">Ennél a példánál adja meg a `shannon` nevet.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-116">For this example, enter `shannon`.</span></span>
3. <span data-ttu-id="a2e1b-117">Válassza ki a hivatkozást a felhasználói fiók **Név** oszlopában.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-117">Select the link in the **Name** column of the user account that appears.</span></span>
4. <span data-ttu-id="a2e1b-118">Válassza ki az **Időnyilvántartás** fület.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-118">Select the **Time registration** tab.</span></span>
5. <span data-ttu-id="a2e1b-119">Válassza ki az **Aktiválás a regisztrációs terminálokon** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-119">Select **Activate on registration terminals**.</span></span>
6. <span data-ttu-id="a2e1b-120">Adja meg vagy válassza ki a következő mezőkben szereplő értékeket:</span><span class="sxs-lookup"><span data-stu-id="a2e1b-120">Enter or select values in the following fields:</span></span>  

    - <span data-ttu-id="a2e1b-121">**Számítási csoport**</span><span class="sxs-lookup"><span data-stu-id="a2e1b-121">**Calculation group**</span></span>  
    - <span data-ttu-id="a2e1b-122">**Alapértelmezett számítási csoport**</span><span class="sxs-lookup"><span data-stu-id="a2e1b-122">**Default calculation group**</span></span>  
    - <span data-ttu-id="a2e1b-123">**Jóváhagyási csoport**</span><span class="sxs-lookup"><span data-stu-id="a2e1b-123">**Approval group**</span></span>  
    - <span data-ttu-id="a2e1b-124">**Szokásos profil**</span><span class="sxs-lookup"><span data-stu-id="a2e1b-124">**Standard profile**</span></span>  
    - <span data-ttu-id="a2e1b-125">**Profilcsoport**</span><span class="sxs-lookup"><span data-stu-id="a2e1b-125">**Profile group**</span></span>  

7. <span data-ttu-id="a2e1b-126">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-126">Select **OK**.</span></span>
8. <span data-ttu-id="a2e1b-127">Válassza ki a **Szerkesztés** lehetőséget az új munkaidő-nyilvántartásos dolgozó belépőkártyaszámának megadásához.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-127">Select **Edit** to enter a badge number for the new time registration worker.</span></span> <span data-ttu-id="a2e1b-128">Adjon meg egy értéket a **Belépőkártya azonosítója** mezőben.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-128">Enter a value in the **Badge ID** field.</span></span>
9. <span data-ttu-id="a2e1b-129">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-129">Select **Save**.</span></span>
10. <span data-ttu-id="a2e1b-130">Zárja be a **Dolgozó részletes adatai** és **Dolgozók** oldalt.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-130">Close the **Worker details** and **Workers** pages.</span></span>

## <a name="assign-worker-to-device-group"></a><span data-ttu-id="a2e1b-131">Dolgozó társítása eszközcsoporthoz</span><span class="sxs-lookup"><span data-stu-id="a2e1b-131">Assign worker to device group</span></span>
1. <span data-ttu-id="a2e1b-132">Ugorjon a **Gyártásvezérlés > Beállítás > Gyártásvégrehajtás > Feladatkártya konfigurálása az eszközökhöz** elemre.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-132">Go to **Production control > Setup > Manufacturing execution > Configure job card for devices**.</span></span>
2. <span data-ttu-id="a2e1b-133">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-133">Select **Add**.</span></span>
3. <span data-ttu-id="a2e1b-134">Válassza ki a listából a kívánt dolgozót.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-134">In the list, select the desired worker.</span></span> <span data-ttu-id="a2e1b-135">Ebben a példában válassza ki **SHANNON-t**.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-135">For this example, select **SHANNON**.</span></span>
4. <span data-ttu-id="a2e1b-136">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-136">Select **OK**.</span></span>
5. <span data-ttu-id="a2e1b-137">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-137">Select **Edit**.</span></span>
6. <span data-ttu-id="a2e1b-138">A **Termelési egység** mezőben megadhatja az alapértelmezett szűrőt a dolgozóhoz.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-138">In the **Production unit** field, you can set the default filter for the worker.</span></span> <span data-ttu-id="a2e1b-139">Ez biztosítja, hogy csak a kijelölt termelési egység termelési feladatai jelenjenek meg, amikor a dolgozó bejelentkezik az eszközön.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-139">This will ensure that only production jobs for the selected production unit are shown when the worker logs on to the device.</span></span> <span data-ttu-id="a2e1b-140">Adja meg a kívánt értéket.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-140">Enter the desired value.</span></span>
7. <span data-ttu-id="a2e1b-141">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a2e1b-141">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]