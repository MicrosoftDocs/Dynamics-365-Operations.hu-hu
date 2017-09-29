--- 
title: "Dolgozó konfigurálása mobil feladatvégző eszközzel"
description: "Ez az eljárás bemutatja, hogyan lehet a megfelelő szerepköröket hozzárendelni egy dolgozó felhasználói fiókjához, és ezt követően engedélyezni a dolgozónak az üzemi regisztrációk végrehajtását."
author: YuyuScheller
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: d56f861dbbf579e44fcd3fc4d8b45c24029acecc
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="configure-a-worker-using-the-mobile-job-device"></a><span data-ttu-id="9b71f-103">Dolgozó konfigurálása mobil feladatvégző eszközzel</span><span class="sxs-lookup"><span data-stu-id="9b71f-103">Configure a worker using the mobile job device</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9b71f-104">Ez az eljárás bemutatja, hogyan lehet a megfelelő szerepköröket hozzárendelni egy dolgozó felhasználói fiókjához, és ezt követően engedélyezni a dolgozónak az üzemi regisztrációk végrehajtását.</span><span class="sxs-lookup"><span data-stu-id="9b71f-104">This procedure shows you how to assign the correct roles to the user account of a worker, and then enable the worker to do shop floor registrations.</span></span>


## <a name="assign-roles-to-user-account"></a><span data-ttu-id="9b71f-105">Szerepkörök hozzárendelése a felhasználói fiókhoz</span><span class="sxs-lookup"><span data-stu-id="9b71f-105">Assign roles to user account</span></span>
1. <span data-ttu-id="9b71f-106">Ugrás a Rendszerfelügyelet > Felhasználók > Felhasználók elemre.</span><span class="sxs-lookup"><span data-stu-id="9b71f-106">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="9b71f-107">A gyorsszűrő segítségével szűrheti a dolgozó nevét, amikor a felhasználói fiók társítva van a gépkezelő szerepkörrel.</span><span class="sxs-lookup"><span data-stu-id="9b71f-107">Use the Quick Filter to filter on the name of a worker where the user account is associated with the machine operator role.</span></span> <span data-ttu-id="9b71f-108">A mintaadatok esetében a név Shannon lenne.</span><span class="sxs-lookup"><span data-stu-id="9b71f-108">In the sample data, the name would be Shannon.</span></span>
3. <span data-ttu-id="9b71f-109">Jelölje ki a Felhasználói fiók rekordot.</span><span class="sxs-lookup"><span data-stu-id="9b71f-109">Highlight the user account record.</span></span>
4. <span data-ttu-id="9b71f-110">A listában kattintson a „Név” hivatkozásra a kijelölt sorban a felhasználói fiók adatainak megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="9b71f-110">In the list, click the "Name" link in the selected row to view the details of the user account.</span></span>
5. <span data-ttu-id="9b71f-111">A fán jelölje be a „Szerepkörök\gépkezelő" lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9b71f-111">In the tree, select 'Roles\Machine operator'.</span></span>
6. <span data-ttu-id="9b71f-112">Zárja be a Felhasználói fiók részletei lapot.</span><span class="sxs-lookup"><span data-stu-id="9b71f-112">Close the user account details page.</span></span>
7. <span data-ttu-id="9b71f-113">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9b71f-113">Close the page.</span></span>

## <a name="configure-worker-account"></a><span data-ttu-id="9b71f-114">Dolgozói fiók konfigurálása</span><span class="sxs-lookup"><span data-stu-id="9b71f-114">Configure worker account.</span></span>
1. <span data-ttu-id="9b71f-115">Ugrás az Emberi erőforrások > Dolgozók > Dolgozók elemre.</span><span class="sxs-lookup"><span data-stu-id="9b71f-115">Go to Human resources > Workers > Workers.</span></span>
2. <span data-ttu-id="9b71f-116">A gyorsszűrő segítségével szűrheti a dolgozó nevét, amikor a felhasználói fiók társítva van a gépkezelő szerepkörrel.</span><span class="sxs-lookup"><span data-stu-id="9b71f-116">Use the Quick Filter to filter on the name of a worker where the user account is associated with the machine operator role.</span></span> <span data-ttu-id="9b71f-117">A mintaadatok esetében a név Shannon lenne.</span><span class="sxs-lookup"><span data-stu-id="9b71f-117">In the sample data, the name would be Shannon.</span></span>
3. <span data-ttu-id="9b71f-118">Jelölje ki a Felhasználói fiók rekordot.</span><span class="sxs-lookup"><span data-stu-id="9b71f-118">Highlight the user account record.</span></span>
4. <span data-ttu-id="9b71f-119">A listában kattintson a „Név” hivatkozásra a kijelölt sorban a felhasználói fiók adatainak megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="9b71f-119">In the list, click the "Name" link in the selected row to view the details of the user account.</span></span>
5. <span data-ttu-id="9b71f-120">Kattintson a Foglalkoztatás lapra.</span><span class="sxs-lookup"><span data-stu-id="9b71f-120">Click the Employment tab.</span></span>
6. <span data-ttu-id="9b71f-121">Bontsa ki a munkaidő-nyilvántartás gyorslapot, és kattintson az Aktiválás a regisztrációs terminálokon elemre.</span><span class="sxs-lookup"><span data-stu-id="9b71f-121">Expand the Time registration FastTab and click Activate on registration terminals.</span></span>
7. <span data-ttu-id="9b71f-122">Kattintson az Aktiválás a regisztrációs terminálokon elemre.</span><span class="sxs-lookup"><span data-stu-id="9b71f-122">Click Activate on registration terminals.</span></span>
8. <span data-ttu-id="9b71f-123">A Számításcsoport mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9b71f-123">In the Calculation group field, enter or select a value.</span></span>
9. <span data-ttu-id="9b71f-124">Az Alapértelmezett számítási csoport mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9b71f-124">In the Default calculation group field, enter or select a value.</span></span>
10. <span data-ttu-id="9b71f-125">A Jóváhagyáscsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9b71f-125">In the Approval group field, enter or select a value.</span></span>
11. <span data-ttu-id="9b71f-126">A Normál profil mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9b71f-126">In the Standard profile field, enter or select a value.</span></span>
12. <span data-ttu-id="9b71f-127">Az Profilcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9b71f-127">In the Profile group field, enter or select a value.</span></span>
13. <span data-ttu-id="9b71f-128">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9b71f-128">Click OK.</span></span>
14. <span data-ttu-id="9b71f-129">Kattintson a Szerkesztés gombra az új munkaidő-nyilvántartásos munkavállaló belépőkártyaszámának megadásához.</span><span class="sxs-lookup"><span data-stu-id="9b71f-129">Click Edit to enter a badge number for the new time registration worker.</span></span>
15. <span data-ttu-id="9b71f-130">Írjon be egy értéket a Belépőkártya-azonosító mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9b71f-130">In the Badge ID field, type a value.</span></span>
16. <span data-ttu-id="9b71f-131">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="9b71f-131">Click Save.</span></span>
17. <span data-ttu-id="9b71f-132">Használja a SaveRecord parancsikont.</span><span class="sxs-lookup"><span data-stu-id="9b71f-132">Use the SaveRecord shortcut.</span></span>
18. <span data-ttu-id="9b71f-133">Zárja be a Dolgozók részletei lapot.</span><span class="sxs-lookup"><span data-stu-id="9b71f-133">Close the worker details page.</span></span>
19. <span data-ttu-id="9b71f-134">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9b71f-134">Close the page.</span></span>

## <a name="assign-worker-to-device-group"></a><span data-ttu-id="9b71f-135">Társítsa a dolgozót az eszközcsoporthoz.</span><span class="sxs-lookup"><span data-stu-id="9b71f-135">Assign worker to device group.</span></span>
1. <span data-ttu-id="9b71f-136">Ugrás a Gyártásvezérlés > Beállítás > Gyártásvégrehajtás > Feladatkártya konfigurálása az eszközökhöz elemre.</span><span class="sxs-lookup"><span data-stu-id="9b71f-136">Go to Production control > Setup > Manufacturing execution > Configure job card for devices.</span></span>
2. <span data-ttu-id="9b71f-137">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="9b71f-137">Click Add.</span></span>
3. <span data-ttu-id="9b71f-138">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="9b71f-138">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="9b71f-139">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9b71f-139">Click OK.</span></span>
5. <span data-ttu-id="9b71f-140">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9b71f-140">Click Edit.</span></span>
6. <span data-ttu-id="9b71f-141">A Termelési egység mezőben megadhatja az alapértelmezett szűrőt a dolgozóhoz.</span><span class="sxs-lookup"><span data-stu-id="9b71f-141">In the Production unit field, you can set the default filter for the worker.</span></span> <span data-ttu-id="9b71f-142">Ez biztosítja, hogy csak a kijelölt termelési egység termelési feladatai jelenjenek meg, amikor a dolgozó bejelentkezik az eszközön.</span><span class="sxs-lookup"><span data-stu-id="9b71f-142">This will ensure that only production jobs for the selected production unit are shown when the worker logs on to the device.</span></span>
7. <span data-ttu-id="9b71f-143">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9b71f-143">Close the page.</span></span>


