---
title: Manuális feladatok konfigurálása munkafolyamatban
description: Ez a témakör bemutatja, hogyan kell konfigurálni a manuális feladat tulajdonságait.
author: sericks007
manager: AnnBe
ms.date: 08/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 192191
ms.assetid: 27f1afde-ff26-4b6f-8c11-27ec49130bbb
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 492c49b1a3e8334bca401770c4c2db04e8892691
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190166"
---
# <a name="configure-manual-tasks-in-a-workflow"></a><span data-ttu-id="4f8de-103">Manuális feladatok konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="4f8de-103">Configure manual tasks in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4f8de-104">Ez a témakör bemutatja, hogyan kell konfigurálni a manuális feladat tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="4f8de-104">This topic explains how to configure the properties for a manual task.</span></span>

<span data-ttu-id="4f8de-105">A munkafolyamat-szerkesztő manuális feladatának konfigurálásához, kattintson a jobb gombbal a feladatra, és kattintson **Tulajdonságok** oldal megnyitásához a **Tulajdonságok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4f8de-105">To configure a manual task in the workflow editor, right-click the task, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="4f8de-106">Ezt követően a következő eljárások segítségével állítsa be a manuális feladat tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="4f8de-106">Then use the following procedures to configure the properties for the manual task.</span></span>

## <a name="name-the-task"></a><span data-ttu-id="4f8de-107">A feladat elnevezése</span><span class="sxs-lookup"><span data-stu-id="4f8de-107">Name the task</span></span>

<span data-ttu-id="4f8de-108">A következő lépések segítségével elnevezheti a manuális feladatot.</span><span class="sxs-lookup"><span data-stu-id="4f8de-108">Follow these steps to enter a name for the manual task.</span></span>

1. <span data-ttu-id="4f8de-109">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="4f8de-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="4f8de-110">Adja meg a feladat egyedi nevét a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4f8de-110">In the **Name** field, enter a unique name for the task.</span></span>

## <a name="enter-a-subject-line-and-instructions"></a><span data-ttu-id="4f8de-111">A tárgysor és az utasítások megadása</span><span class="sxs-lookup"><span data-stu-id="4f8de-111">Enter a subject line and instructions</span></span>

<span data-ttu-id="4f8de-112">Meg kell adnia egy tárgysort, illetve utasításokat a feladathoz hozzárendelt felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="4f8de-112">You must provide a subject line and instructions to users who are assigned to the task.</span></span> <span data-ttu-id="4f8de-113">Például, ha a beszerzési igénylések feladatát konfigurálja, a feladathoz hozzárendelt felhasználó látja a tárgysort és az utasításokat a **Beszerzési igénylések** oldalon.</span><span class="sxs-lookup"><span data-stu-id="4f8de-113">For example, if you're configuring a task for purchase requisitions, the user who is assigned to the task sees the subject line and instructions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="4f8de-114">A tárgysor az oldal egy üzenetsorán jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="4f8de-114">The subject line appears in a message bar on the page.</span></span> <span data-ttu-id="4f8de-115">A felhasználó ezt követően rákattinthat az üzenetsoron található ikonra az útmutatás megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="4f8de-115">The user can then click the icon in the message bar to view the instructions.</span></span> <span data-ttu-id="4f8de-116">Kövesse a következő lépéseket a tárgysor és az utasítások megadásához.</span><span class="sxs-lookup"><span data-stu-id="4f8de-116">Follow these steps to enter a subject line and instructions.</span></span>

1. <span data-ttu-id="4f8de-117">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="4f8de-117">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="4f8de-118">Írja be a tárgysort a **Munkatétel tárgya** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4f8de-118">In the **Work item subject** field, enter the subject line.</span></span>
3. <span data-ttu-id="4f8de-119">A tárgysor személyre szabásához helyőrzőket illeszthet be.</span><span class="sxs-lookup"><span data-stu-id="4f8de-119">To personalize the subject line, you can insert placeholders.</span></span> <span data-ttu-id="4f8de-120">A helyőrzők helyére a megfelelő adatok kerülnek, amikor a tárgysor megjelenik a felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="4f8de-120">Placeholders are replaced with appropriate data when the subject line is shown to users.</span></span> <span data-ttu-id="4f8de-121">Végezze el a következő lépéseket a helyőrzők beillesztéséhez:</span><span class="sxs-lookup"><span data-stu-id="4f8de-121">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="4f8de-122">Kattintson oda a szövegdobozban, ahol meg szeretné jeleníteni a helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="4f8de-122">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="4f8de-123">Kattintson a **Helyőrző beszúrása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4f8de-123">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="4f8de-124">A megjelenő listában válassza ki a beilleszteni kívánt helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="4f8de-124">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="4f8de-125">Kattintson a **Beszúrás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4f8de-125">Click **Insert**.</span></span>

4. <span data-ttu-id="4f8de-126">A tárgysor fordításai hozzáadásához, végezze el a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="4f8de-126">To add translations of the subject line, follow these steps:</span></span>

    1. <span data-ttu-id="4f8de-127">Kattintson a **Fordítások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4f8de-127">Click **Translations**.</span></span>
    2. <span data-ttu-id="4f8de-128">A megjelenő oldalon kattintson a **Hozzáadás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4f8de-128">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="4f8de-129">A megjelenő listában válassza ki az éppen begépelt szöveg nyelvét.</span><span class="sxs-lookup"><span data-stu-id="4f8de-129">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="4f8de-130">Írja be a szöveget a **Lefordított szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4f8de-130">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="4f8de-131">A szöveg személyre szabásához, helyőrzőket illeszthet be a 3. lépésben leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="4f8de-131">To personalize the text, you can insert placeholders as described in step 3.</span></span>
    6. <span data-ttu-id="4f8de-132">Kattintson a **Bezárás** gombra.</span><span class="sxs-lookup"><span data-stu-id="4f8de-132">Click **Close**.</span></span>

5. <span data-ttu-id="4f8de-133">Írja be az utasításokat a **Munkatétel utasításai** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4f8de-133">In the **Work item instructions** field, enter the instructions.</span></span>
6. <span data-ttu-id="4f8de-134">Az utasítások testreszabásához, helyőrzőket illeszthet be.</span><span class="sxs-lookup"><span data-stu-id="4f8de-134">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="4f8de-135">A helyőrzők helyére a megfelelő adatok kerülnek, amikor az utasítások megjelennek a felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="4f8de-135">Placeholders are replaced with appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="4f8de-136">Végezze el a következő lépéseket a helyőrzők beillesztéséhez:</span><span class="sxs-lookup"><span data-stu-id="4f8de-136">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="4f8de-137">Kattintson oda a szövegdobozban, ahol meg szeretné jeleníteni a helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="4f8de-137">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="4f8de-138">Kattintson a **Helyőrző beszúrása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4f8de-138">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="4f8de-139">A megjelenő listában válassza ki a beilleszteni kívánt helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="4f8de-139">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="4f8de-140">Kattintson a **Beszúrás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4f8de-140">Click **Insert**.</span></span>

7. <span data-ttu-id="4f8de-141">Az utasítások fordításainak hozzáadásához, végezze el a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="4f8de-141">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="4f8de-142">Kattintson a **Fordítások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4f8de-142">Click **Translations**.</span></span>
    2. <span data-ttu-id="4f8de-143">A megjelenő oldalon kattintson a **Hozzáadás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4f8de-143">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="4f8de-144">A megjelenő listában válassza ki az éppen begépelt szöveg nyelvét.</span><span class="sxs-lookup"><span data-stu-id="4f8de-144">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="4f8de-145">Írja be a szöveget a **Lefordított szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4f8de-145">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="4f8de-146">A szöveg személyre szabásához, helyőrzőket illeszthet be a 6. lépésben leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="4f8de-146">To personalize the text, you can insert placeholders as described in step 6.</span></span>
    6. <span data-ttu-id="4f8de-147">Kattintson a **Bezárás** gombra.</span><span class="sxs-lookup"><span data-stu-id="4f8de-147">Click **Close**.</span></span>

## <a name="assign-the-task"></a><span data-ttu-id="4f8de-148">A feladat hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="4f8de-148">Assign the task</span></span>

<span data-ttu-id="4f8de-149">Végezze el ezeket a lépéseket azon személyek meghatározásához, akiket a manuális feladathoz hozzá kell rendelni.</span><span class="sxs-lookup"><span data-stu-id="4f8de-149">Follow these steps to specify who the manual task should be assigned to.</span></span>

1. <span data-ttu-id="4f8de-150">A bal oldali panelen kattintson a **Hozzárendelés** gombra.</span><span class="sxs-lookup"><span data-stu-id="4f8de-150">In the left pane, click **Assignment**.</span></span>
2. <span data-ttu-id="4f8de-151">A **Hozzárendelés-típus** lapon válasszon ki egy lehetőséget a következő táblázatban, majd ezt követően végezze el a további lépéseket a beállításhoz, mielőtt továbblép a 3. lépésre.</span><span class="sxs-lookup"><span data-stu-id="4f8de-151">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 3.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="4f8de-152">Lehetőség</span><span class="sxs-lookup"><span data-stu-id="4f8de-152">Option</span></span></th>
    <th><span data-ttu-id="4f8de-153">A feladathoz hozzárendelt felhasználók</span><span class="sxs-lookup"><span data-stu-id="4f8de-153">Users that the task is assigned to</span></span></th>
    <th><span data-ttu-id="4f8de-154">További lépések</span><span class="sxs-lookup"><span data-stu-id="4f8de-154">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="4f8de-155">Résztvevő</span><span class="sxs-lookup"><span data-stu-id="4f8de-155">Participant</span></span></td>
    <td><span data-ttu-id="4f8de-156">Egy adott csoporthoz vagy szerephez hozzárendelt felhasználók</span><span class="sxs-lookup"><span data-stu-id="4f8de-156">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="4f8de-157">Miután kiválasztotta <strong>Résztvevő</strong> lehetőséget a <strong>Szerepkör-alapú</strong> lapon, a <strong>Résztvevő típusa</strong> listán jelölje ki a feladathoz hozzárendelni kívánt csoport vagy a szerepkör típusát.</span><span class="sxs-lookup"><span data-stu-id="4f8de-157">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to assign the task to.</span></span></li>
    <li><span data-ttu-id="4f8de-158">A <strong>Résztvevő</strong> listáján jelölje ki a feladathoz hozzárendelni kívánt csoportot vagy szerepkört.</span><span class="sxs-lookup"><span data-stu-id="4f8de-158">In the <strong>Participant</strong> list, select the group or role to assign the task to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="4f8de-159">Hierarchia</span><span class="sxs-lookup"><span data-stu-id="4f8de-159">Hierarchy</span></span></td>
    <td><span data-ttu-id="4f8de-160">A meghatározott szervezeti hierarchiában lévő felhasználók.</span><span class="sxs-lookup"><span data-stu-id="4f8de-160">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="4f8de-161">Miután kiválasztotta <strong>Hierarchia</strong> lehetőséget a <strong>Hierarchia kiválasztása</strong> lapon, a <strong>Hierarchia típusa</strong> listán, jelölje ki a feladathoz hozzárendelni kívánt hierarchia típusát.</span><span class="sxs-lookup"><span data-stu-id="4f8de-161">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to assign the task to.</span></span></li>
    <li><span data-ttu-id="4f8de-162">A rendszernek be kell olvasnia az felhasználó névtartományát a hierarchiából.</span><span class="sxs-lookup"><span data-stu-id="4f8de-162">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="4f8de-163">Ezek a nevek a feladatokhoz hozzárendelhető felhasználókat jelölik.</span><span class="sxs-lookup"><span data-stu-id="4f8de-163">These names represent users that the task can be assigned to.</span></span> <span data-ttu-id="4f8de-164">Végezze el a következő lépéseket azon felhasználók névtartományának kezdő- és végpontját, amelyet a rendszer beolvas:</span><span class="sxs-lookup"><span data-stu-id="4f8de-164">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="4f8de-165">A kezdő pont megadásához válasszon ki egy személyt a <strong>Kezdet</strong> listából.</span><span class="sxs-lookup"><span data-stu-id="4f8de-165">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="4f8de-166">A végpont megadásához kattintson a <strong>Feltétel létrehozása</strong> lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4f8de-166">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="4f8de-167">Ezt követően adja meg azt a feltételt, amely meghatározza, hogy a rendszer hol állítsa meg a hierarchiában a nevek beolvasását.</span><span class="sxs-lookup"><span data-stu-id="4f8de-167">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="4f8de-168">A <strong>Hierarchia beállításai</strong> lapon adja meg, hogy mely, a tartományban szereplő felhasználók számára kell a feladatot hozzárendelni:</span><span class="sxs-lookup"><span data-stu-id="4f8de-168">On the <strong>Hierarchy options</strong> tab, specify which users in the range the task should be assigned to:</span></span> <ul>
    <li><span data-ttu-id="4f8de-169"><strong>Minden lekért felhasználó hozzárendelése</strong> – A tartományban szereplő összes felhasználóhoz hozzá van rendelve a feladat.</span><span class="sxs-lookup"><span data-stu-id="4f8de-169"><strong>Assign to all users retrieved</strong> – The task is assigned to all users in the range.</span></span></li>
    <li><span data-ttu-id="4f8de-170"><strong>Csak a legutóbb lekért felhasználó hozzárendelése</strong> – Csak a tartományban szereplő utolsó felhasználóhoz van hozzárendelve a feladat.</span><span class="sxs-lookup"><span data-stu-id="4f8de-170"><strong>Assign only to last user retrieved</strong> – The task is assigned to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="4f8de-171"><strong>A következő feltételnek megfelelő felhasználók kihagyása</strong> – A feladat nincs hozzárendelve a tartomány minden olyan felhasználójához, akik megfelelnek egy adott feltételnek.</span><span class="sxs-lookup"><span data-stu-id="4f8de-171"><strong>Exclude users with the following condition</strong> – The task isn't assigned to users in the range who meet a specific condition.</span></span> <span data-ttu-id="4f8de-172">Kattintson a <strong>Feltétel hozzáadása</strong> lehetőségre, ha meg szeretné adni a feltételt.</span><span class="sxs-lookup"><span data-stu-id="4f8de-172">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="4f8de-173">Munkafolyamat felhasználója</span><span class="sxs-lookup"><span data-stu-id="4f8de-173">Workflow user</span></span></td>
    <td><span data-ttu-id="4f8de-174">Az aktuális munkafolyamatban szereplő felhasználó</span><span class="sxs-lookup"><span data-stu-id="4f8de-174">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="4f8de-175">Miután kijelölte <strong>Munkafolyamat-felhasználó</strong> lehetőséget a <strong>Munkafolyamat-felhasználó</strong> lapon a <strong>Munkafolyamat-felhasználó</strong> listából, jelöljön ki egy felhasználót, aki részt vesz a munkafolyamatban.</span><span class="sxs-lookup"><span data-stu-id="4f8de-175">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="4f8de-176">Felhasználó</span><span class="sxs-lookup"><span data-stu-id="4f8de-176">User</span></span></td>
    <td><span data-ttu-id="4f8de-177">Meghatározott felhasználók</span><span class="sxs-lookup"><span data-stu-id="4f8de-177">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="4f8de-178">Miután kijelölte <strong>Felhasználó</strong> lehetőséget, kattintson a <strong>Felhasználó</strong> fülre.</span><span class="sxs-lookup"><span data-stu-id="4f8de-178">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="4f8de-179">A <strong>Rendelkezésre álló felhasználók</strong> listája az összes felhasználót tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="4f8de-179">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="4f8de-180">Válassza ki a feladathoz hozzárendelni kívánt felhasználókat, majd ezt követően helyezze át ezeket a felhasználókat a <strong>Kijelölt felhasználók</strong> listájára.</span><span class="sxs-lookup"><span data-stu-id="4f8de-180">Select the users to assign the task to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="4f8de-181">Várakozási sor</span><span class="sxs-lookup"><span data-stu-id="4f8de-181">Queue</span></span></td>
    <td><span data-ttu-id="4f8de-182">Munkatétel-várólista</span><span class="sxs-lookup"><span data-stu-id="4f8de-182">A work item queue</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="4f8de-183">Miután kijelölte <strong>Várólista</strong> lehetőséget, kattintson a <strong>Várólistán alapuló</strong> fülre.</span><span class="sxs-lookup"><span data-stu-id="4f8de-183">After you select <strong>Queue</strong>, click the <strong>Queue based</strong> tab.</span></span></li>
    <li><span data-ttu-id="4f8de-184">A feladat egy specifikus várólistához történő hozzárendeléséhez, kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="4f8de-184">To assign the task to a specific queue, follow these steps:</span></span> <ol>
    <li><span data-ttu-id="4f8de-185">A <strong>Várólista típusa</strong> listán, válassza ki a <strong>Munkatétel-várólisták</strong> lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4f8de-185">In the <strong>Queue type</strong> list, select <strong>Work item queues</strong>.</span></span></li>
    <li><span data-ttu-id="4f8de-186">A <strong>Várólista neve</strong> listán jelölje ki a várólistát.</span><span class="sxs-lookup"><span data-stu-id="4f8de-186">In the <strong>Queue name</strong> list, select the queue.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="4f8de-187">Ha egy adott feltételnek meg kell határozni, hogy melyik várólistához rendeljék hozzá a feladatot, végezze el a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="4f8de-187">If a specific condition should determine which queue the task is assigned to, follow these steps:</span></span> <ol>
    <li><span data-ttu-id="4f8de-188">A <strong>Várólista típusa</strong> listán, válassza ki a <strong>Feltételes munkatétel-várólisták</strong> lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4f8de-188">In the <strong>Queue type</strong> list, select <strong>Conditional work item queues</strong>.</span></span></li>
    <li><span data-ttu-id="4f8de-189">A <strong>Várólista neve</strong> listán jelölje ki a <strong>Feltételes várólista</strong> lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4f8de-189">In the <strong>Queue name</strong> list, select <strong>Conditional queue</strong>.</span></span></li>
    </ol>
    </li>
    </ol>
    <blockquote>[!NOTE] <span data-ttu-id="4f8de-190">Ezt a beállítást csak néhány munkafolyamatnál használják, például Esetkezelésnél.</span><span class="sxs-lookup"><span data-stu-id="4f8de-190">This option is used for only a few workflows, such as Case management.</span></span></blockquote>
    </td>
    </tr>
    </tbody>
    </table>

3. <span data-ttu-id="4f8de-191">A **Határidő** lapon az **Időtartam** mezőben adja meg, hogy mennyi idő kell a felhasználónak a feladat elvégzéséhez.</span><span class="sxs-lookup"><span data-stu-id="4f8de-191">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to complete the task.</span></span> <span data-ttu-id="4f8de-192">Válasszon a következő lehetőségek közül:</span><span class="sxs-lookup"><span data-stu-id="4f8de-192">Select one of the following options:</span></span>

    - <span data-ttu-id="4f8de-193">**Órák** – Adja meg azon órák számát, amely alatt a felhasználónak be kell fejeznie a feladatot.</span><span class="sxs-lookup"><span data-stu-id="4f8de-193">**Hours** – Enter the number of hours that the user has to complete the task.</span></span> <span data-ttu-id="4f8de-194">Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.</span><span class="sxs-lookup"><span data-stu-id="4f8de-194">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="4f8de-195">**Napok** – Adja meg azon napok számát, amely alatt a felhasználónak be kell fejeznie a feladatot.</span><span class="sxs-lookup"><span data-stu-id="4f8de-195">**Days** – Enter the number of days that the user has to complete the task.</span></span> <span data-ttu-id="4f8de-196">Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.</span><span class="sxs-lookup"><span data-stu-id="4f8de-196">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="4f8de-197">**Hetek** – Adja meg azon hetek számát, amely alatt a felhasználónak be kell fejeznie a feladatot.</span><span class="sxs-lookup"><span data-stu-id="4f8de-197">**Weeks** – Enter the number of weeks that the user has to complete the task.</span></span>
    - <span data-ttu-id="4f8de-198">**Hónapok** – Válassza ki, hogy melyik hét mely napjáig kell a felhasználónak befejeznie a feladatot.</span><span class="sxs-lookup"><span data-stu-id="4f8de-198">**Months** – Select the day and week that the user must complete the task by.</span></span> <span data-ttu-id="4f8de-199">Kérheti például, hogy a felhasználó a hónap harmadik hetének péntekéig hajtsa végre a feladatot.</span><span class="sxs-lookup"><span data-stu-id="4f8de-199">For example, you might want the user to complete the task by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="4f8de-200">**Évek** – Válassza ki, hogy mely hónap, mely hét, mely napjáig kell a felhasználónak befejeznie a feladatot.</span><span class="sxs-lookup"><span data-stu-id="4f8de-200">**Years** – Select the day, week, and month that the user must complete the task by.</span></span> <span data-ttu-id="4f8de-201">Kérheti például, hogy a felhasználó december harmadik hetének péntekéig hajtsa végre a feladatot.</span><span class="sxs-lookup"><span data-stu-id="4f8de-201">For example, you might want the user to complete the task by Friday of the third week of December.</span></span>

    <span data-ttu-id="4f8de-202">Ha a felhasználó nem hajtja végre a feladatot a megadott idő alatt, lejár a feladat.</span><span class="sxs-lookup"><span data-stu-id="4f8de-202">If the user doesn't complete the task in the allotted time, the task is overdue.</span></span> <span data-ttu-id="4f8de-203">A lejárt feladatot eszkalálni lehet, amely az **Eszkaláció** terület lapján kiválasztott beállításokon alapul.</span><span class="sxs-lookup"><span data-stu-id="4f8de-203">A task that is overdue can be escalated, based on the options that you select in the **Escalation** area of the page.</span></span>

## <a name="specify-what-happens-when-the-task-is-overdue"></a><span data-ttu-id="4f8de-204">Annak megadása, hogy mi történjen, amikor lejár a feladat</span><span class="sxs-lookup"><span data-stu-id="4f8de-204">Specify what happens when the task is overdue</span></span>

<span data-ttu-id="4f8de-205">Ha a felhasználó nem hajtja végre a manuális feladatot a megadott idő alatt, lejár a feladat.</span><span class="sxs-lookup"><span data-stu-id="4f8de-205">If a user doesn't complete the manual task in the allotted time, the task is overdue.</span></span> <span data-ttu-id="4f8de-206">A lejárt feladatot eszkalálhatja, illetve automatikusan egy másik felhasználóhoz rendelheti jóváhagyás céljából.</span><span class="sxs-lookup"><span data-stu-id="4f8de-206">A task that is overdue can be escalated, or automatically assigned to another user.</span></span> <span data-ttu-id="4f8de-207">Kövesse az alábbi lépéseket a feladat eszkalálásához, ha lejárt a feladat.</span><span class="sxs-lookup"><span data-stu-id="4f8de-207">Follow these steps to escalate the task if it's overdue.</span></span>

1. <span data-ttu-id="4f8de-208">A bal oldali panelen kattintson az **Eszkalálás** gombra.</span><span class="sxs-lookup"><span data-stu-id="4f8de-208">In the left pane, click **Escalation**.</span></span>
2. <span data-ttu-id="4f8de-209">Válassza ki az **Eszkalációs útvonal használata** jelölőnégyzetet egy eszkalációs útvonal létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="4f8de-209">Select the **Use escalation path** check box to create an escalation path.</span></span> <span data-ttu-id="4f8de-210">A rendszer automatikusan hozzárendeli a feladatot az eszkalációs útvonalon felsorolt felhasználókhoz.</span><span class="sxs-lookup"><span data-stu-id="4f8de-210">The system automatically assigns the task to the users who are listed in the escalation path.</span></span> <span data-ttu-id="4f8de-211">Például az alábbi táblázat egy eszkalációs útvonalat jelent.</span><span class="sxs-lookup"><span data-stu-id="4f8de-211">For example, the following table represents an escalation path.</span></span>

    | <span data-ttu-id="4f8de-212">Sorozat</span><span class="sxs-lookup"><span data-stu-id="4f8de-212">Sequence</span></span> | <span data-ttu-id="4f8de-213">Eszkalációs útvonal</span><span class="sxs-lookup"><span data-stu-id="4f8de-213">Escalation path</span></span>      |
    |----------|----------------------|
    | <span data-ttu-id="4f8de-214">1</span><span class="sxs-lookup"><span data-stu-id="4f8de-214">1</span></span>        | <span data-ttu-id="4f8de-215">Hozzárendelés a következőhöz: Dóra</span><span class="sxs-lookup"><span data-stu-id="4f8de-215">Assign to: Donna</span></span>     |
    | <span data-ttu-id="4f8de-216">2</span><span class="sxs-lookup"><span data-stu-id="4f8de-216">2</span></span>        | <span data-ttu-id="4f8de-217">Hozzárendelés a következőhöz: Ervin</span><span class="sxs-lookup"><span data-stu-id="4f8de-217">Assign to: Erin</span></span>      |
    | <span data-ttu-id="4f8de-218">3</span><span class="sxs-lookup"><span data-stu-id="4f8de-218">3</span></span>        | <span data-ttu-id="4f8de-219">Utolsó művelet: Elutasítás</span><span class="sxs-lookup"><span data-stu-id="4f8de-219">Final action: Reject</span></span> |

    <span data-ttu-id="4f8de-220">Ebben a példában a rendszer Dórához rendeli a lejárt feladatot.</span><span class="sxs-lookup"><span data-stu-id="4f8de-220">In this example, the system assigns the overdue task to Donna.</span></span> <span data-ttu-id="4f8de-221">Ha Dóra nem fejezi be a feladatot a kijelölt időkereten belül, a rendszer Ervinhez rendeli hozzá.</span><span class="sxs-lookup"><span data-stu-id="4f8de-221">If Donna doesn't complete the task in the allotted time, the system assigns the task to Erin.</span></span> <span data-ttu-id="4f8de-222">Ha Ervin nem hajtja végre a feladatot a kijelölt időkereten belül, a rendszer elutasítja a feldolgozásra elküldött dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="4f8de-222">If Erin doesn't complete the task in the allotted time, the system rejects the document that was submitted for processing.</span></span>

3. <span data-ttu-id="4f8de-223">A felhasználó eszkalációs útvonalhoz történő hozzáadásához, kattintson az **Újabb eszkalációs lépés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4f8de-223">To add a user to the escalation path, click **Add escalation**.</span></span> <span data-ttu-id="4f8de-224">A **Hozzárendelés-típus** lapon válasszon ki egy lehetőséget a következő táblázatban, majd ezt követően végezze el a további lépéseket a beállításhoz, mielőtt továbblép a 4. lépésre.</span><span class="sxs-lookup"><span data-stu-id="4f8de-224">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 4.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="4f8de-225">Lehetőség</span><span class="sxs-lookup"><span data-stu-id="4f8de-225">Option</span></span></th>
    <th><span data-ttu-id="4f8de-226">A feladathoz eszkalált felhasználók</span><span class="sxs-lookup"><span data-stu-id="4f8de-226">Users that the task is escalated to</span></span></th>
    <th><span data-ttu-id="4f8de-227">További lépések</span><span class="sxs-lookup"><span data-stu-id="4f8de-227">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="4f8de-228">Hierarchia</span><span class="sxs-lookup"><span data-stu-id="4f8de-228">Hierarchy</span></span></td>
    <td><span data-ttu-id="4f8de-229">A meghatározott szervezeti hierarchiában lévő felhasználók.</span><span class="sxs-lookup"><span data-stu-id="4f8de-229">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="4f8de-230">Miután kiválasztotta <strong>Hierarchia</strong> lehetőséget a <strong>Hierarchia kiválasztása</strong> lapon, a <strong>Hierarchia típusa</strong> listán, jelölje ki a feladathoz eszkalálni kívánt hierarchia típusát.</span><span class="sxs-lookup"><span data-stu-id="4f8de-230">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to escalate the task to.</span></span></li>
    <li><span data-ttu-id="4f8de-231">A rendszernek be kell olvasnia az felhasználó névtartományát a hierarchiából.</span><span class="sxs-lookup"><span data-stu-id="4f8de-231">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="4f8de-232">Ezek a nevek a feladathoz eszkalálható felhasználókat jelölik.</span><span class="sxs-lookup"><span data-stu-id="4f8de-232">These names represent users that the task can be escalated to.</span></span> <span data-ttu-id="4f8de-233">Végezze el a következő lépéseket azon felhasználók névtartományának kezdő- és végpontját, amelyet a rendszer beolvas:</span><span class="sxs-lookup"><span data-stu-id="4f8de-233">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="4f8de-234">A kezdő pont megadásához válasszon ki egy személyt a <strong>Kezdet</strong> listából.</span><span class="sxs-lookup"><span data-stu-id="4f8de-234">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="4f8de-235">A végpont megadásához kattintson a <strong>Feltétel létrehozása</strong> lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4f8de-235">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="4f8de-236">Ezt követően adja meg azt a feltételt, amely meghatározza, hogy a rendszer hol állítsa meg a hierarchiában a nevek beolvasását.</span><span class="sxs-lookup"><span data-stu-id="4f8de-236">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="4f8de-237">A <strong>Hierarchia beállításai</strong> lapon adja meg, hogy mely, a tartományban szereplő felhasználók számára kell a feladatot eszkalálni:</span><span class="sxs-lookup"><span data-stu-id="4f8de-237">On the <strong>Hierarchy options</strong> tab, specify which users in the range the task should be escalated to:</span></span> <ul>
    <li><span data-ttu-id="4f8de-238"><strong>Minden lekért felhasználó hozzárendelése</strong> – A tartományban szereplő összes felhasználóhoz eszkalálva van a feladat.</span><span class="sxs-lookup"><span data-stu-id="4f8de-238"><strong>Assign to all users retrieved</strong> – The task is escalated to all users in the range.</span></span></li>
    <li><span data-ttu-id="4f8de-239"><strong>Csak a legutóbb lekért felhasználó hozzárendelése</strong> – Csak a tartományban szereplő utolsó felhasználóhoz van eszkalálva a feladat.</span><span class="sxs-lookup"><span data-stu-id="4f8de-239"><strong>Assign only to last user retrieved</strong> – The task is escalated to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="4f8de-240"><strong>A következő feltételnek megfelelő felhasználók kihagyása</strong> – Ez a feladat nincs eszkalálva a tartomány minden olyan felhasználójához, akik megfelelnek egy adott feltételnek.</span><span class="sxs-lookup"><span data-stu-id="4f8de-240"><strong>Exclude users with the following condition</strong> – This task isn't escalated to users in the range who meet a specific condition.</span></span> <span data-ttu-id="4f8de-241">Kattintson a <strong>Feltétel hozzáadása</strong> lehetőségre, ha meg szeretné adni a feltételt.</span><span class="sxs-lookup"><span data-stu-id="4f8de-241">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="4f8de-242">Munkafolyamat felhasználója</span><span class="sxs-lookup"><span data-stu-id="4f8de-242">Workflow user</span></span></td>
    <td><span data-ttu-id="4f8de-243">Az aktuális munkafolyamatban szereplő felhasználó</span><span class="sxs-lookup"><span data-stu-id="4f8de-243">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="4f8de-244">Miután kijelölte <strong>Munkafolyamat-felhasználó</strong> lehetőséget a <strong>Munkafolyamat-felhasználó</strong> lapon a <strong>Munkafolyamat-felhasználó</strong> listából, jelöljön ki egy felhasználót, aki részt vesz a munkafolyamatban.</span><span class="sxs-lookup"><span data-stu-id="4f8de-244">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="4f8de-245">Felhasználó</span><span class="sxs-lookup"><span data-stu-id="4f8de-245">User</span></span></td>
    <td><span data-ttu-id="4f8de-246">Meghatározott felhasználók</span><span class="sxs-lookup"><span data-stu-id="4f8de-246">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="4f8de-247">Miután kijelölte <strong>Felhasználó</strong> lehetőséget, kattintson a <strong>Felhasználó</strong> fülre.</span><span class="sxs-lookup"><span data-stu-id="4f8de-247">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="4f8de-248">A <strong>Rendelkezésre álló felhasználók</strong> listája az összes felhasználót tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="4f8de-248">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="4f8de-249">Válassza ki a feladathoz eszkalálni kívánt felhasználókat, majd ezt követően helyezze át ezeket a felhasználókat a <strong>Kijelölt felhasználók</strong> listájára.</span><span class="sxs-lookup"><span data-stu-id="4f8de-249">Select the users to escalate the task to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. <span data-ttu-id="4f8de-250">A **Határidő** lapon az **Időtartam** mezőben adja meg, hogy mennyi idő kell a felhasználónak a feladat elvégzéséhez.</span><span class="sxs-lookup"><span data-stu-id="4f8de-250">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to complete the task.</span></span> <span data-ttu-id="4f8de-251">Válasszon a következő lehetőségek közül:</span><span class="sxs-lookup"><span data-stu-id="4f8de-251">Select one of the following options:</span></span>

    - <span data-ttu-id="4f8de-252">**Órák** – Adja meg azon órák számát, amely alatt a felhasználónak be kell fejeznie a feladatot.</span><span class="sxs-lookup"><span data-stu-id="4f8de-252">**Hours** – Enter the number of hours that the user has to complete the task.</span></span> <span data-ttu-id="4f8de-253">Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.</span><span class="sxs-lookup"><span data-stu-id="4f8de-253">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="4f8de-254">**Napok** – Adja meg azon napok számát, amely alatt a felhasználónak be kell fejeznie a feladatot.</span><span class="sxs-lookup"><span data-stu-id="4f8de-254">**Days** – Enter the number of days that the user has to complete the task.</span></span> <span data-ttu-id="4f8de-255">Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.</span><span class="sxs-lookup"><span data-stu-id="4f8de-255">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="4f8de-256">**Hetek** – Adja meg azon hetek számát, amely alatt a felhasználónak be kell fejeznie a feladatot.</span><span class="sxs-lookup"><span data-stu-id="4f8de-256">**Weeks** – Enter the number of weeks that the user has to complete the task.</span></span>
    - <span data-ttu-id="4f8de-257">**Hónapok** – Válassza ki, hogy melyik hét mely napjáig kell a felhasználónak befejeznie a feladatot.</span><span class="sxs-lookup"><span data-stu-id="4f8de-257">**Months** – Select the day and week that the user must complete the task by.</span></span> <span data-ttu-id="4f8de-258">Kérheti például, hogy a felhasználó a hónap harmadik hetének péntekéig hajtsa végre a feladatot.</span><span class="sxs-lookup"><span data-stu-id="4f8de-258">For example, you might want the user to complete the task by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="4f8de-259">**Évek** – Válassza ki, hogy mely hónap, mely hét, mely napjáig kell a felhasználónak befejeznie a feladatot.</span><span class="sxs-lookup"><span data-stu-id="4f8de-259">**Years** – Select the day, week, and month that the user must complete the task by.</span></span> <span data-ttu-id="4f8de-260">Kérheti például, hogy a felhasználó december harmadik hetének péntekéig hajtsa végre a feladatot.</span><span class="sxs-lookup"><span data-stu-id="4f8de-260">For example, you might want the user to complete the task by Friday of the third week of December.</span></span>

5. <span data-ttu-id="4f8de-261">Ismételje meg a 3 – 4. lépést minden egyes olyan felhasználóra vonatkozóan, akiket hozzá kell adni az eszkalációs útvonalhoz.</span><span class="sxs-lookup"><span data-stu-id="4f8de-261">Repeat steps 3 through 4 for each user that should be added to the escalation path.</span></span> <span data-ttu-id="4f8de-262">A felhasználók sorrendje módosítható.</span><span class="sxs-lookup"><span data-stu-id="4f8de-262">You can change the order of the users.</span></span>
6. <span data-ttu-id="4f8de-263">Ha az eszkalációs útvonalban szereplő felhasználók nem fejezik be a feladatot a megadott időn belül, a rendszer automatikusan végrehajtja a feladatot.</span><span class="sxs-lookup"><span data-stu-id="4f8de-263">If the users in the escalation path don't complete the task in the allotted time, the system takes action on the task.</span></span> <span data-ttu-id="4f8de-264">A rendszer által végzett művelet meghatározásához, válassza ki a **Művelet** sort, majd a **Művelet lezárása** fülön válasszon ki egy műveletet.</span><span class="sxs-lookup"><span data-stu-id="4f8de-264">To specify the action that the system takes, select the **Action** row, and then, on the **End action** tab, select an action.</span></span>

## <a name="specify-when-the-system-automatically-acts-on-the-task"></a><span data-ttu-id="4f8de-265">Adja meg, hogy mikor végzi a rendszer automatikusan a feladatot</span><span class="sxs-lookup"><span data-stu-id="4f8de-265">Specify when the system automatically acts on the task</span></span>

<span data-ttu-id="4f8de-266">Beállíthatja a rendszert egy manuális művelet végrehajtására, ha bizonyos feltételek teljesülésnek.</span><span class="sxs-lookup"><span data-stu-id="4f8de-266">You can configure the system to take action on the manual task if specific conditions are met.</span></span> <span data-ttu-id="4f8de-267">Például, egy feladathoz szükséges lehet, hogy a költség-jelentések részleg egyik tagja átvizsgálja azokat a bevételezéseket, amelyeket a költségjelentéssel együtt elküldtek.</span><span class="sxs-lookup"><span data-stu-id="4f8de-267">For example, a task requires that a member of the Expense reports department review the receipts that are submitted together with an expense report.</span></span> <span data-ttu-id="4f8de-268">A cég irányelvei szerint ezt a feladatot akkor kell elvégezni, ha a költségjelentés teljes összege meghaladja a 100 USD-t.</span><span class="sxs-lookup"><span data-stu-id="4f8de-268">According to company policy, this task must be performed if the total amount of the expense report is more than USD 100.</span></span> <span data-ttu-id="4f8de-269">Ebben az esetben állítsa be a rendszert, hogy automatikusan jelölje meg a feladatot **Készként**, ha a teljes összeg 100-nál kisebb.</span><span class="sxs-lookup"><span data-stu-id="4f8de-269">In this scenario, you can configure the system to automatically mark the task as **Complete** when the total amount is less than 100.</span></span> <span data-ttu-id="4f8de-270">Végezze el az alábbi lépéseket a manuális feladat végrehajtásának idejének meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="4f8de-270">Follow these steps to specify when the system takes action on the manual task.</span></span>

1. <span data-ttu-id="4f8de-271">A bal oldali panelen kattintson az **Automatikus műveletek** gombra.</span><span class="sxs-lookup"><span data-stu-id="4f8de-271">In the left pane, click **Automatic actions**.</span></span>
2. <span data-ttu-id="4f8de-272">Jelölje ki az **Automatikus műveletek engedélyezése** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="4f8de-272">Select the **Enable automatic actions** check box.</span></span>
3. <span data-ttu-id="4f8de-273">Kattintson a **Feltétel hozzáadása** parancsra.</span><span class="sxs-lookup"><span data-stu-id="4f8de-273">Click **Add condition**.</span></span>
4. <span data-ttu-id="4f8de-274">Feltétel megadása.</span><span class="sxs-lookup"><span data-stu-id="4f8de-274">Enter a condition.</span></span>
5. <span data-ttu-id="4f8de-275">Adja meg a további szükséges feltételeket.</span><span class="sxs-lookup"><span data-stu-id="4f8de-275">Enter any additional conditions that are required.</span></span>
6. <span data-ttu-id="4f8de-276">Ha ellenőrizni szeretné, hogy a megadott feltételek helyesen vannak-e konfigurálva, végezze el a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="4f8de-276">To verify that the conditions that you entered are configured correctly, follow these steps:</span></span>

    1. <span data-ttu-id="4f8de-277">Kattintson a **Teszt** gombra.</span><span class="sxs-lookup"><span data-stu-id="4f8de-277">Click **Test**.</span></span>
    2. <span data-ttu-id="4f8de-278">A **Munkafolyamati feltétel tesztelése** oldalon, a **Feltétel érvényesítése** területen válasszon ki egy rekordot.</span><span class="sxs-lookup"><span data-stu-id="4f8de-278">On the **Test workflow condition** page, in the **Validate condition** area, select a record.</span></span>
    3. <span data-ttu-id="4f8de-279">Kattintson a **Teszt** gombra.</span><span class="sxs-lookup"><span data-stu-id="4f8de-279">Click **Test**.</span></span> <span data-ttu-id="4f8de-280">A rendszer értékeli a bejegyzést, annak érdekében, hogy meghatározza, hogy a meghatározott feltételeknek megfeleljen-e.</span><span class="sxs-lookup"><span data-stu-id="4f8de-280">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4. <span data-ttu-id="4f8de-281">Kattintson az **OK** vagy a **Mégse** lehetőségre a **Tulajdonságok** lapra történő visszalépéshez.</span><span class="sxs-lookup"><span data-stu-id="4f8de-281">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

7. <span data-ttu-id="4f8de-282">Válassza ki **Automatikus befejezési művelet** listából, hogy milyen feladatokat kell a rendszernek végrehajtania.</span><span class="sxs-lookup"><span data-stu-id="4f8de-282">In the **Auto complete action** list, select the action that the system should take on the task.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="4f8de-283">Az értesítések küldési idejének meghatározása</span><span class="sxs-lookup"><span data-stu-id="4f8de-283">Specify when notifications are sent</span></span>

<span data-ttu-id="4f8de-284">Értesítéseket küldhet a felhasználóknak a manuális feladat delegálása, eszkalálása, illetve befejezése vagy visszautasítása, illetve változás kérése esetén.</span><span class="sxs-lookup"><span data-stu-id="4f8de-284">You can send notifications to people when a manual task has been delegated, escalated, completed, or rejected, or when a change has been requested.</span></span> <span data-ttu-id="4f8de-285">Végezze el a következő lépéseket, annak meghatározása érdekében, hogy mikor és kinek küldje el a rendszer az értesítéseket.</span><span class="sxs-lookup"><span data-stu-id="4f8de-285">Follow these steps to specify when notifications are sent, and who the notifications are sent to.</span></span>

1. <span data-ttu-id="4f8de-286">A bal oldali panelen kattintson az **Értesítések** gombra.</span><span class="sxs-lookup"><span data-stu-id="4f8de-286">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="4f8de-287">Jelölje be a jelölőnégyzetet azon eseményekhez, amelyekhez ki kell küldeni az értesítéseket:</span><span class="sxs-lookup"><span data-stu-id="4f8de-287">Select the check box next to the events that notifications should be sent for:</span></span>

    - <span data-ttu-id="4f8de-288">**Delegálás** – A feladat egy másik felhasználóhoz van rendelve.</span><span class="sxs-lookup"><span data-stu-id="4f8de-288">**Delegate** – The task has been assigned to another user.</span></span>
    - <span data-ttu-id="4f8de-289">**Eszkaláció** – A hozzárendelt felhasználó nem fejezte be a feladatot a kijelölt időn belül.</span><span class="sxs-lookup"><span data-stu-id="4f8de-289">**Escalate** – The assigned user hasn't completed the task in the allotted time.</span></span>
    - <span data-ttu-id="4f8de-290">**Teljes** – A hozzárendelt felhasználó befejezte a feladatot.</span><span class="sxs-lookup"><span data-stu-id="4f8de-290">**Complete** – The assigned user has completed the task.</span></span>
    - <span data-ttu-id="4f8de-291">**Elutasítás** – A hozzárendelt felhasználó elutasította az elküldött dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="4f8de-291">**Reject** – The assigned user has rejected the document that was submitted.</span></span>
    - <span data-ttu-id="4f8de-292">**Változtatás kérése** – A hozzárendelt felhasználó kérte az elküldött dokumentum módosítását.</span><span class="sxs-lookup"><span data-stu-id="4f8de-292">**Request change** – The assigned user has requested a change to the document that was submitted.</span></span>

3. <span data-ttu-id="4f8de-293">Jelölje ki a sort a 2. lépésben választott eseményhez.</span><span class="sxs-lookup"><span data-stu-id="4f8de-293">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="4f8de-294">Írja be az értesítés szövegét az **Értesítési szöveg** lapon lévő szövegdobozba.</span><span class="sxs-lookup"><span data-stu-id="4f8de-294">On the **Notification text** tab, in the text box, enter the text of the notification.</span></span>
5. <span data-ttu-id="4f8de-295">Az értesítések személyre szabásához, helyőrzőket szúrhat be.</span><span class="sxs-lookup"><span data-stu-id="4f8de-295">To personalize the notification, you can insert placeholders.</span></span> <span data-ttu-id="4f8de-296">A helyőrzők helyére a megfelelő adatok kerülnek, amikor az értesítés megjelenik a felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="4f8de-296">Placeholders are replaced with appropriate information when the notification is shown to users.</span></span> <span data-ttu-id="4f8de-297">Végezze el a következő lépéseket a helyőrzők beillesztéséhez:</span><span class="sxs-lookup"><span data-stu-id="4f8de-297">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="4f8de-298">Kattintson oda a szövegdobozban, ahol meg szeretné jeleníteni a helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="4f8de-298">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="4f8de-299">Kattintson a **Helyőrző beszúrása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4f8de-299">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="4f8de-300">A megjelenő listában válassza ki a beilleszteni kívánt helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="4f8de-300">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="4f8de-301">Kattintson a **Beszúrás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4f8de-301">Click **Insert**.</span></span>

6. <span data-ttu-id="4f8de-302">Az értesítések fordításainak hozzáadásához, végezze el a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="4f8de-302">To add translations of the notification, follow these steps:</span></span>

    1. <span data-ttu-id="4f8de-303">Kattintson a **Fordítások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4f8de-303">Click **Translations**.</span></span>
    2. <span data-ttu-id="4f8de-304">A megjelenő oldalon kattintson a **Hozzáadás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4f8de-304">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="4f8de-305">A megjelenő listában válassza ki az éppen begépelt szöveg nyelvét.</span><span class="sxs-lookup"><span data-stu-id="4f8de-305">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="4f8de-306">Írja be a szöveget a **Lefordított szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4f8de-306">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="4f8de-307">A szöveg személyre szabásához, helyőrzőket illeszthet be a 5. lépésben leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="4f8de-307">To personalize the text, you can insert placeholders as described in step 5.</span></span>
    6. <span data-ttu-id="4f8de-308">Kattintson a **Bezárás** gombra.</span><span class="sxs-lookup"><span data-stu-id="4f8de-308">Click **Close**.</span></span>

7. <span data-ttu-id="4f8de-309">Adja meg azokat a személyeket, akik értesítéseket kapnak a **Címzett** lapon.</span><span class="sxs-lookup"><span data-stu-id="4f8de-309">On the **Recipient** tab, specify who the notifications are sent to.</span></span> <span data-ttu-id="4f8de-310">Válasszon ki egy lehetőséget a következő táblázatban, majd ezt követően végezze el a további lépéseket a beállításhoz, mielőtt továbblép a 8. lépésre.</span><span class="sxs-lookup"><span data-stu-id="4f8de-310">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 8.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="4f8de-311">Lehetőség</span><span class="sxs-lookup"><span data-stu-id="4f8de-311">Option</span></span></th>
    <th><span data-ttu-id="4f8de-312">Értesítés címzettjei</span><span class="sxs-lookup"><span data-stu-id="4f8de-312">Notification recipients</span></span></th>
    <th><span data-ttu-id="4f8de-313">További lépések</span><span class="sxs-lookup"><span data-stu-id="4f8de-313">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="4f8de-314">Résztvevő</span><span class="sxs-lookup"><span data-stu-id="4f8de-314">Participant</span></span></td>
    <td><span data-ttu-id="4f8de-315">Egy adott csoporthoz vagy szerephez hozzárendelt felhasználók</span><span class="sxs-lookup"><span data-stu-id="4f8de-315">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="4f8de-316">Miután kiválasztotta <strong>Résztvevő</strong> lehetőséget a <strong>Szerepkör-alapú</strong> lapon, a <strong>Résztvevő típusa</strong> listán jelölje ki azon csoport vagy a szerepkör típusát, amely számára az értesítéseket el kívánja küldeni.</span><span class="sxs-lookup"><span data-stu-id="4f8de-316">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="4f8de-317">A <strong>Résztvevő</strong> listáján jelölje ki a csoportot vagy szerepkört, amely számára értesítést kíván küldeni.</span><span class="sxs-lookup"><span data-stu-id="4f8de-317">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="4f8de-318">Munkafolyamat felhasználója</span><span class="sxs-lookup"><span data-stu-id="4f8de-318">Workflow user</span></span></td>
    <td><span data-ttu-id="4f8de-319">Az aktuális munkafolyamatban szereplő felhasználó</span><span class="sxs-lookup"><span data-stu-id="4f8de-319">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="4f8de-320">Miután kijelölte <strong>Munkafolyamat-felhasználó</strong> lehetőséget a <strong>Munkafolyamat-felhasználó</strong> lapon a <strong>Munkafolyamat-felhasználó</strong> listából, jelöljön ki egy felhasználót, aki részt vesz a munkafolyamatban.</span><span class="sxs-lookup"><span data-stu-id="4f8de-320">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="4f8de-321">Felhasználó</span><span class="sxs-lookup"><span data-stu-id="4f8de-321">User</span></span></td>
    <td><span data-ttu-id="4f8de-322">Meghatározott felhasználók</span><span class="sxs-lookup"><span data-stu-id="4f8de-322">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="4f8de-323">Miután kijelölte <strong>Felhasználó</strong> lehetőséget, kattintson a <strong>Felhasználó</strong> fülre.</span><span class="sxs-lookup"><span data-stu-id="4f8de-323">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="4f8de-324">A <strong>Rendelkezésre álló felhasználók</strong> listája az összes felhasználót tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="4f8de-324">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="4f8de-325">Válassza ki azokat a felhasználókat, akik számára értesítéseket kíván küldeni, majd helyezze át ezeket a felhasználókat a <strong>Kijelölt felhasználók</strong> listájára.</span><span class="sxs-lookup"><span data-stu-id="4f8de-325">Select the users to send notifications to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="4f8de-326">Ismételje meg a 3 – 7. lépést a 2. lépésben kiválasztott összes eseményhez.</span><span class="sxs-lookup"><span data-stu-id="4f8de-326">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="set-a-time-limit"></a><span data-ttu-id="4f8de-327">Időkorlát beállítása</span><span class="sxs-lookup"><span data-stu-id="4f8de-327">Set a time limit</span></span>

<span data-ttu-id="4f8de-328">Kövesse az alábbi lépéseket, ha a kézi tevékenységet be kell fejezni egy megadott időn belül.</span><span class="sxs-lookup"><span data-stu-id="4f8de-328">Follow these steps if the manual task must be completed in a specific time.</span></span>

> [!NOTE]
> <span data-ttu-id="4f8de-329">Az eljárásban kijelölt beállítások felülbírálják az oldal **Hozzárendelés** és **Eszkaláció** területén kijelölt beállításokat.</span><span class="sxs-lookup"><span data-stu-id="4f8de-329">The options that you select in this procedure override the options that you selected in the **Assignment** and **Escalation** areas of the page.</span></span>

1. <span data-ttu-id="4f8de-330">A bal oldali panelen kattintson az **Speciális beállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="4f8de-330">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="4f8de-331">Válassza ki a **A munkafolyamat-elem időkorlátjának beállítása** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="4f8de-331">Select the **Set a time limit for the workflow element** check box.</span></span>
3. <span data-ttu-id="4f8de-332">Az **Időtartam** mezőbe adja meg, hogy mikor kell végrehajtani a feladatot.</span><span class="sxs-lookup"><span data-stu-id="4f8de-332">In the **Duration** field, specify when the task must be completed.</span></span> <span data-ttu-id="4f8de-333">Válasszon a következő lehetőségek közül:</span><span class="sxs-lookup"><span data-stu-id="4f8de-333">Select one of the following options:</span></span>

    - <span data-ttu-id="4f8de-334">**Órák** – Adja meg azon órák számát, amely alatt be kell fejezni a feladatot.</span><span class="sxs-lookup"><span data-stu-id="4f8de-334">**Hours** – Enter the number of hours that the task must be completed in.</span></span> <span data-ttu-id="4f8de-335">Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.</span><span class="sxs-lookup"><span data-stu-id="4f8de-335">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="4f8de-336">**Napok** – Adja meg azon napok számát, amely alatt be kell fejezni a feladatot.</span><span class="sxs-lookup"><span data-stu-id="4f8de-336">**Days** – Enter the number of days that the task must be completed in.</span></span> <span data-ttu-id="4f8de-337">Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.</span><span class="sxs-lookup"><span data-stu-id="4f8de-337">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="4f8de-338">**Hetek** – Adja meg azon hetek számát, amely alatt be kell fejezni a feladatot.</span><span class="sxs-lookup"><span data-stu-id="4f8de-338">**Weeks** – Enter the number of weeks that the task must be completed in.</span></span>
    - <span data-ttu-id="4f8de-339">**Hónapok** – Válassza ki, hogy melyik hét mely napjáig kell a feladatot befejezni.</span><span class="sxs-lookup"><span data-stu-id="4f8de-339">**Months** – Select the day and week that the task must be completed by.</span></span> <span data-ttu-id="4f8de-340">Kérheti például, hogy a feladatot a hónap harmadik hetének péntekéig kell elvégezni.</span><span class="sxs-lookup"><span data-stu-id="4f8de-340">For example, you might want the task to be completed by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="4f8de-341">**Évek** – Válassza ki, hogy mely hónap, mely hét, mely napjáig kell a feladatot elvégezni.</span><span class="sxs-lookup"><span data-stu-id="4f8de-341">**Years** – Select the day, week, and month that the task must be completed by.</span></span> <span data-ttu-id="4f8de-342">Kérheti például, hogy a feladatot december harmadik hetének péntekéig kell elvégezni.</span><span class="sxs-lookup"><span data-stu-id="4f8de-342">For example, you might want the task to be completed by Friday of the third week of December.</span></span>

4. <span data-ttu-id="4f8de-343">Ha lejár az időkorlát, a rendszer intézkedik a feladatról.</span><span class="sxs-lookup"><span data-stu-id="4f8de-343">If the time limit is exceeded, the system takes action on the task.</span></span> <span data-ttu-id="4f8de-344">Válassza ki a **Művelet** listából, hogy milyen műveletet kell a rendszernek végrehajtania.</span><span class="sxs-lookup"><span data-stu-id="4f8de-344">In the **Action** list, select the action that the system should take.</span></span>

## <a name="specify-which-actions-are-available-to-the-user"></a><span data-ttu-id="4f8de-345">Annak megadása, hogy mely műveletek érhetők el a felhasználó számára.</span><span class="sxs-lookup"><span data-stu-id="4f8de-345">Specify which actions are available to the user</span></span>

<span data-ttu-id="4f8de-346">Amikor hozzárendelik a manuális feladatot egy felhasználóhoz, annak intézkednie kell a feladatról.</span><span class="sxs-lookup"><span data-stu-id="4f8de-346">When the manual task is assigned to a user, the user must take action on the task.</span></span> <span data-ttu-id="4f8de-347">Végezze el az alábbi lépéseket, annak meghatározásához, hogy mely műveleteket lehet elvégeznie a felhasználónak a feladaton.</span><span class="sxs-lookup"><span data-stu-id="4f8de-347">Follow these steps to specify which actions the user can take on the task.</span></span>

> [!NOTE]
> <span data-ttu-id="4f8de-348">Az elérhető műveletek változhatnak a feladat tervezetétől függően.</span><span class="sxs-lookup"><span data-stu-id="4f8de-348">The actions that are available vary, depending on the design of the task.</span></span>

1. <span data-ttu-id="4f8de-349">A bal oldali panelen kattintson az **Speciális beállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="4f8de-349">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="4f8de-350">Jelölje be a **Kész** jelölőnégyzetet, ha a felhasználónak a feladatot **Kész** állapotúnak kell minősítenie.</span><span class="sxs-lookup"><span data-stu-id="4f8de-350">Select the **Complete** check box if the user should be able to mark the task as **Complete**.</span></span>
3. <span data-ttu-id="4f8de-351">Jelölje be az **Elutasítás** jelölőnégyzetet, ha felhasználónak el kell utasítania az elküldött dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="4f8de-351">Select the **Reject** check box if the user should be able to reject the document that was submitted.</span></span>
4. <span data-ttu-id="4f8de-352">Jelölje be a **Változtatás kérése** jelölőnégyzetet, ha a felhasználónak a benyújtott dokumentum módosítását kell kérnie.</span><span class="sxs-lookup"><span data-stu-id="4f8de-352">Select the **Request change** check box if the user should be able to request changes to the document that was submitted.</span></span>
5. <span data-ttu-id="4f8de-353">Jelölje be a **Delegálás** jelölőnégyzetet, ha a felhasználónak hozzá kell rendelnie a feladatot egy másik felhasználóhoz.</span><span class="sxs-lookup"><span data-stu-id="4f8de-353">Select the **Delegate** check box if the user should be able to assign the task to another user.</span></span>
6. <span data-ttu-id="4f8de-354">Jelölje be a **Ismételt hozzárendelés** jelölőnégyzetet, ha a felhasználónak hozzá kell rendelnie ismét a feladatot a munkatétel-várólistán szereplő felhasználóhoz.</span><span class="sxs-lookup"><span data-stu-id="4f8de-354">Select the **Reassign** check box if the user should be able to reassign the task to another user in the work item queue.</span></span>
7. <span data-ttu-id="4f8de-355">Jelölje be a **Kiadás** jelölőnégyzetet, ha a felhasználónak hozzá kell rendelnie ismét a feladatot a munkatétel-várólistához.</span><span class="sxs-lookup"><span data-stu-id="4f8de-355">Select the **Release** check box if the user should be able to reassign the task to the work item queue.</span></span> <span data-ttu-id="4f8de-356">Ezt követően a másik felhasználó hajthatja végre a feladatot.</span><span class="sxs-lookup"><span data-stu-id="4f8de-356">Another user can then complete the task.</span></span>
