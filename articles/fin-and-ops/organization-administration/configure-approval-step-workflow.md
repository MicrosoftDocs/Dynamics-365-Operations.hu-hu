---
title: Jóváhagyási lépések konfigurálása munkafolyamatban
description: Ez a témakör bemutatja, hogyan kell konfigurálni a jóváhagyási lépés tulajdonságait.
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
ms.custom: 192161
ms.assetid: 8b478e3d-d6b4-403b-aae0-f639a71ca36c
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8f52b6ffed7c1edb97c7a673cefbc8bf486ba831
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1570763"
---
# <a name="configure-approval-steps-in-a-workflow"></a><span data-ttu-id="9b1b5-103">Jóváhagyási lépések konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="9b1b5-103">Configure approval steps in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9b1b5-104">Ez a témakör bemutatja, hogyan kell konfigurálni a jóváhagyási lépés tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-104">This topic explains how to configure the properties of an approval step.</span></span>

<span data-ttu-id="9b1b5-105">A munkafolyamat-szerkesztő jóváhagyási lépésének beállításához kattintson a jobb gombbal a jóváhagyási lépésre, és kattintson **Tulajdonságok** oldalon a **Tulajdonságok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-105">To configure an approval step in the workflow editor, right-click the approval step, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="9b1b5-106">Ezt követően a következő eljárások segítségével állítsa be a jóváhagyási lépés tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-106">Then use the following procedures to configure the properties of the approval step.</span></span>

## <a name="name-the-step"></a><span data-ttu-id="9b1b5-107">A lépés neve</span><span class="sxs-lookup"><span data-stu-id="9b1b5-107">Name the step</span></span>
<span data-ttu-id="9b1b5-108">A következő lépések segítségével elnevezheti a jóváhagyási lépést.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-108">Follow these steps to enter a name for the approval step.</span></span>

1. <span data-ttu-id="9b1b5-109">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="9b1b5-110">Írja be a jóváhagyási lépés egyedi nevét a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-110">In the **Name** field, enter a unique name for the approval step.</span></span>

## <a name="enter-a-subject-line-and-instructions"></a><span data-ttu-id="9b1b5-111">A tárgysor és az utasítások megadása</span><span class="sxs-lookup"><span data-stu-id="9b1b5-111">Enter a subject line and instructions</span></span>

<span data-ttu-id="9b1b5-112">Meg kell adnia egy tárgysort, illetve utasításokat a jóváhagyási lépéshez hozzárendelt felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-112">You must provide a subject line and instructions to users who are assigned to the approval step.</span></span> <span data-ttu-id="9b1b5-113">Például, ha a beszerzésiigénylések jóváhagyásilépését állítja be, a lépéshez hozzárendelt felhasználó látja a tárgysort és az utasításokat a **Beszerzési igénylések** oldalon.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-113">For example, if you're configuring an approval step for purchase requisitions, the user who is assigned to the step sees the subject line and instructions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="9b1b5-114">A tárgysor az oldal egy üzenetsorán jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-114">The subject line appears in a message bar on the page.</span></span> <span data-ttu-id="9b1b5-115">A felhasználó ezt követően rákattinthat az üzenetsoron található ikonra az útmutatás megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-115">The user can then click the icon in the message bar to see the instructions.</span></span> <span data-ttu-id="9b1b5-116">Kövesse a következő lépéseket a tárgysor és az utasítások megadásához.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-116">Follow these steps to enter a subject line and instructions.</span></span>

1. <span data-ttu-id="9b1b5-117">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-117">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="9b1b5-118">Írja be a tárgysort a **Munkatétel tárgya** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-118">In the **Work item subject** field, enter the subject line.</span></span>
3. <span data-ttu-id="9b1b5-119">A tárgysor személyre szabásához helyőrzőket illeszthet be.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-119">To personalize the subject line, you can insert placeholders.</span></span> <span data-ttu-id="9b1b5-120">A helyőrzők helyére a megfelelő adatok kerülnek, amikor a tárgysor megjelenik a felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-120">Placeholders are replaced with appropriate data when the subject line is shown to users.</span></span> <span data-ttu-id="9b1b5-121">Végezze el a következő lépéseket a helyőrzők beillesztéséhez:</span><span class="sxs-lookup"><span data-stu-id="9b1b5-121">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="9b1b5-122">Kattintson oda a szövegdobozban, ahol meg szeretné jeleníteni a helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-122">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="9b1b5-123">Kattintson a **Helyőrző beszúrása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-123">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="9b1b5-124">A megjelenő listában válassza ki a beilleszteni kívánt helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-124">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="9b1b5-125">Kattintson a **Beszúrás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-125">Click **Insert**.</span></span>

4. <span data-ttu-id="9b1b5-126">A tárgysor fordításai hozzáadásához, végezze el a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="9b1b5-126">To add translations of the subject line, follow these steps:</span></span>

    1. <span data-ttu-id="9b1b5-127">Kattintson a **Fordítások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-127">Click **Translations**.</span></span>
    2. <span data-ttu-id="9b1b5-128">A megjelenő oldalon kattintson a **Hozzáadás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-128">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="9b1b5-129">A megjelenő listában válassza ki az éppen begépelt szöveg nyelvét.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-129">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="9b1b5-130">Írja be a szöveget a **Lefordított szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-130">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="9b1b5-131">A szöveg személyre szabásához, helyőrzőket illeszthet be a 3. lépésben leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-131">To personalize the text, you can insert placeholders as described in step 3.</span></span>
    6. <span data-ttu-id="9b1b5-132">Kattintson a **Bezárás** gombra.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-132">Click **Close**.</span></span>

5. <span data-ttu-id="9b1b5-133">Írja be az utasításokat a **Munkatétel utasításai** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-133">In the **Work item instructions** field, enter the instructions.</span></span>
6. <span data-ttu-id="9b1b5-134">Az utasítások testreszabásához, helyőrzőket illeszthet be.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-134">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="9b1b5-135">A helyőrzők helyére a megfelelő adatok kerülnek, amikor az utasítások megjelennek a felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-135">Placeholders are replaced with appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="9b1b5-136">Végezze el a következő lépéseket a helyőrzők beillesztéséhez:</span><span class="sxs-lookup"><span data-stu-id="9b1b5-136">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="9b1b5-137">Kattintson oda a szövegdobozban, ahol meg szeretné jeleníteni a helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-137">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="9b1b5-138">Kattintson a **Helyőrző beszúrása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-138">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="9b1b5-139">A megjelenő listában válassza ki a beilleszteni kívánt helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-139">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="9b1b5-140">Kattintson a **Beszúrás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-140">Click **Insert**.</span></span>

7. <span data-ttu-id="9b1b5-141">Az utasítások fordításainak hozzáadásához, végezze el a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="9b1b5-141">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="9b1b5-142">Kattintson a **Fordítások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-142">Click **Translations**.</span></span>
    2. <span data-ttu-id="9b1b5-143">A megjelenő oldalon kattintson a **Hozzáadás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-143">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="9b1b5-144">A megjelenő listában válassza ki az éppen begépelt szöveg nyelvét.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-144">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="9b1b5-145">Írja be a szöveget a **Lefordított szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-145">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="9b1b5-146">A szöveg személyre szabásához, helyőrzőket illeszthet be a 6. lépésben leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-146">To personalize the text, you can insert placeholders as described in step 6.</span></span>
    6. <span data-ttu-id="9b1b5-147">Kattintson a **Bezárás** gombra.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-147">Click **Close**.</span></span>

## <a name="assign-the-approval-step"></a><span data-ttu-id="9b1b5-148">A jóváhagyási lépés hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="9b1b5-148">Assign the approval step</span></span>

<span data-ttu-id="9b1b5-149">Végezze el ezeket a lépéseket azon személyek meghatározásához, akiket jóváhagyási lépéshez hozzá kell rendelni.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-149">Follow these steps to specify who the approval step should be assigned to.</span></span>

1. <span data-ttu-id="9b1b5-150">A bal oldali panelen kattintson a **Hozzárendelés** gombra.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-150">In the left pane, click **Assignment**.</span></span>
2. <span data-ttu-id="9b1b5-151">A **Hozzárendelés-típus** lapon válasszon ki egy lehetőséget a következő táblázatban, majd ezt követően végezze el a további lépéseket a beállításhoz, mielőtt továbblép a 3. lépésre.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-151">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 3.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="9b1b5-152">Lehetőség</span><span class="sxs-lookup"><span data-stu-id="9b1b5-152">Option</span></span></th>
    <th><span data-ttu-id="9b1b5-153">A jóváhagyási lépéshez hozzárendelt felhasználók</span><span class="sxs-lookup"><span data-stu-id="9b1b5-153">Users that the approval step is assigned to</span></span></th>
    <th><span data-ttu-id="9b1b5-154">További lépések</span><span class="sxs-lookup"><span data-stu-id="9b1b5-154">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="9b1b5-155">Résztvevő</span><span class="sxs-lookup"><span data-stu-id="9b1b5-155">Participant</span></span></td>
    <td><span data-ttu-id="9b1b5-156">Egy adott csoporthoz vagy szerephez hozzárendelt felhasználók</span><span class="sxs-lookup"><span data-stu-id="9b1b5-156">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="9b1b5-157">Miután kiválasztotta <strong>Résztvevő</strong> lehetőséget a <strong>Szerepkör-alapú</strong> lapon, a <strong>Résztvevő típusa</strong> listán jelölje ki a lépéshez hozzárendelni kívánt csoport vagy a szerepkör típusát.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-157">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to assign the step to.</span></span></li>
    <li><span data-ttu-id="9b1b5-158">A <strong>Résztvevő</strong> listáján jelölje ki a lépéshez hozzárendelni kívánt csoportot vagy szerepkört.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-158">In the <strong>Participant</strong> list, select the group or role to assign the step to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="9b1b5-159">Hierarchia</span><span class="sxs-lookup"><span data-stu-id="9b1b5-159">Hierarchy</span></span></td>
    <td><span data-ttu-id="9b1b5-160">A meghatározott szervezeti hierarchiában lévő felhasználók.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-160">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="9b1b5-161">Miután kiválasztotta <strong>Hierarchia</strong> lehetőséget a <strong>Hierarchia kiválasztása</strong> lapon, a <strong>Hierarchia típusa</strong> listán, jelölje ki a lépéshez hozzárendelni kívánt hierarchia típusát.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-161">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to assign the step to.</span></span></li>
    <li><span data-ttu-id="9b1b5-162">A rendszernek be kell olvasnia az felhasználó névtartományát a hierarchiából.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-162">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="9b1b5-163">Ezek a nevek a lépéshez hozzárendelhető felhasználókat jelölik.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-163">These names represent users that the step can be assigned to.</span></span> <span data-ttu-id="9b1b5-164">Végezze el a következő lépéseket azon felhasználók névtartományának kezdő- és végpontját, amelyet a rendszer beolvas:</span><span class="sxs-lookup"><span data-stu-id="9b1b5-164">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="9b1b5-165">A kezdő pont megadásához válasszon ki egy személyt a <strong>Kezdet</strong> listából.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-165">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="9b1b5-166">A végpont megadásához kattintson a <strong>Feltétel létrehozása</strong> lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-166">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="9b1b5-167">Ezt követően adja meg azt a feltételt, amely meghatározza, hogy a rendszer hol állítsa meg a hierarchiában a nevek beolvasását.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-167">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="9b1b5-168">A <strong>Hierarchia beállításai</strong> lapon adja meg, hogy mely, a tartományban szereplő felhasználók számára kell a lépést hozzárendelni:</span><span class="sxs-lookup"><span data-stu-id="9b1b5-168">On the <strong>Hierarchy options</strong> tab, specify which users in the range the step should be assigned to:</span></span> <ul>
    <li><span data-ttu-id="9b1b5-169"><strong>Minden lekért felhasználó hozzárendelése</strong> – A tartományban szereplő összes felhasználóhoz hozzá van rendelve a lépés.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-169"><strong>Assign to all users retrieved</strong> – The step is assigned to all users in the range.</span></span></li>
    <li><span data-ttu-id="9b1b5-170"><strong>Csak a legutóbb lekért felhasználó hozzárendelése</strong> – Csak a tartományban szereplő utolsó felhasználóhoz van hozzárendelve a lépés.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-170"><strong>Assign only to last user retrieved</strong> – The step is assigned to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="9b1b5-171"><strong>A következő feltételnek megfelelő felhasználók kihagyása</strong> – A lépés nincs hozzárendelve a tartomány minden olyan felhasználójához, akik megfelelnek egy adott feltételnek.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-171"><strong>Exclude users with the following condition</strong> – The step isn't assigned to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="9b1b5-172">Kattintson a <strong>Feltétel hozzáadása</strong> lehetőségre, ha meg szeretné adni a feltételt.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-172">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="9b1b5-173">Munkafolyamat felhasználója</span><span class="sxs-lookup"><span data-stu-id="9b1b5-173">Workflow user</span></span></td>
    <td><span data-ttu-id="9b1b5-174">Az aktuális munkafolyamatban szereplő felhasználó</span><span class="sxs-lookup"><span data-stu-id="9b1b5-174">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="9b1b5-175">Miután kijelölte <strong>Munkafolyamat-felhasználó</strong> lehetőséget a <strong>Munkafolyamat-felhasználó</strong> lapon a <strong>Munkafolyamat-felhasználó</strong> listából, jelöljön ki egy felhasználót, aki részt vesz a munkafolyamatban.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-175">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="9b1b5-176">Felhasználó</span><span class="sxs-lookup"><span data-stu-id="9b1b5-176">User</span></span></td>
    <td><span data-ttu-id="9b1b5-177">Meghatározott Microsoft Dynamics 365 for Finance and Operations-felhasználók</span><span class="sxs-lookup"><span data-stu-id="9b1b5-177">Specific Microsoft Dynamics 365 for Finance and Operations users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="9b1b5-178">Miután kijelölte <strong>Felhasználó</strong> lehetőséget, kattintson a <strong>Felhasználó</strong> fülre.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-178">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="9b1b5-179">A <strong>Rendelkezésre álló felhasználók</strong> lista az összes Finance and Operations-felhasználót tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-179">The <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="9b1b5-180">Válassza ki a lépéshez hozzárendelni kívánt felhasználókat, majd ezt követően helyezze át ezeket a felhasználókat a <strong>Kijelölt felhasználók</strong> listájára.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-180">Select the users to assign the step to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

3. <span data-ttu-id="9b1b5-181">A **Határidő** lapon az **Időtartam** mezőben adja meg, hogy mennyi idő kell a felhasználónak azon dokumentumok végrehajtásához, vagy a válaszolásához, amelyek érvényesek a jóváhagyási lépésre.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-181">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to take action on, or respond to, documents that reach the approval step.</span></span> <span data-ttu-id="9b1b5-182">Válasszon a következő lehetőségek közül:</span><span class="sxs-lookup"><span data-stu-id="9b1b5-182">Select one of the following options:</span></span>

    - <span data-ttu-id="9b1b5-183">**Órák** – Adja meg azon órák számát, amely alatt a felhasználónak reagálnia kell.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-183">**Hours** – Enter the number of hours that the user has to respond.</span></span> <span data-ttu-id="9b1b5-184">Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-184">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="9b1b5-185">**Napok** – Adja meg azon napok számát, amely alatt a felhasználónak reagálnia kell.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-185">**Days** – Enter the number of days that the user has to respond.</span></span> <span data-ttu-id="9b1b5-186">Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-186">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="9b1b5-187">**Hetek** – Adja meg azon hetek számát, amely alatt a felhasználónak reagálnia kell.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-187">**Weeks** – Enter the number of weeks that the user has to respond.</span></span>
    - <span data-ttu-id="9b1b5-188">**Hónapok** – Válassza ki, hogy melyik hét mely napjáig kell a felhasználónak reagálnia.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-188">**Months** – Select the day and week that the user must respond by.</span></span> <span data-ttu-id="9b1b5-189">Például meg lehet adni, hogy a felhasználó a hónap harmadik hetének pénteki napjáig kelljen reagálnia.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-189">For example, you might want the user to respond by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="9b1b5-190">**Évek** – Válassza ki, hogy melyik napon és melyik héten kell a felhasználónak reagálnia.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-190">**Years** – Select the day, week, and month that the user must respond by.</span></span> <span data-ttu-id="9b1b5-191">Például meg lehet adni, hogy a felhasználónak december harmadik hetének pénteki napjáig kelljen reagálnia.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-191">For example, you might want the user to respond by Friday of the third week of December.</span></span>

    <span data-ttu-id="9b1b5-192">Ha a felhasználó nem hajtja végre a dokumentum műveletét a megadott idő alatt, lejár a dokumentum.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-192">If the user doesn't take action on the document in the allotted time, the document is overdue.</span></span> <span data-ttu-id="9b1b5-193">A lejárt dokumentum eszkalált, amely az **Eszkaláció** terület lapján kiválasztott beállításokon alapul.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-193">A document that is overdue is escalated, based on the options that you select in the **Escalation** area of the page.</span></span>

4. <span data-ttu-id="9b1b5-194">Ha a jóváhagyási lépéshez több felhasználót vagy felhasználói csoportot rendel, a **Befejezési irányelv** fülön válasszon ki egyet a következő lehetőségek közül:</span><span class="sxs-lookup"><span data-stu-id="9b1b5-194">If you assigned the approval step to multiple users or a group of users, on the **Completion policy** tab, select one of the following options:</span></span>

    - <span data-ttu-id="9b1b5-195">**Egyedi jóváhagyó** – A dokumentumhoz kapcsolódó műveletet az elsőként válaszoló személy határozza meg.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-195">**Single approver** – The action that is applied to the document is determined by the first person who responds.</span></span> <span data-ttu-id="9b1b5-196">Például, Balázs egy 15 000 USA-dolláros költségjelentést küldött el.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-196">For example, Sam has submitted an expense report for USD 15,000.</span></span> <span data-ttu-id="9b1b5-197">A költségjelentés jelenleg Zsuzsannához, Jankához és Vilmoshoz van hozzárendelve.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-197">The expense report is currently assigned to Sue, Jo, and Bill.</span></span> <span data-ttu-id="9b1b5-198">Ha elsőként Zsuzsanna válaszol a dokumentumra, az általa végzett művelet érvényes a dokumentumra.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-198">If Sue is the first person who responds to the document, the action that she takes is applied to the document.</span></span> <span data-ttu-id="9b1b5-199">Ha Zsuzsanna visszautasítja a dokumentumot, akkor a visszautasított dokumentum visszakerül Balázshoz.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-199">If Sue rejects the document, it's rejected and sent back to Sam.</span></span> <span data-ttu-id="9b1b5-200">Ha Zsuzsanna jóváhagyja a dokumentumot, akkor a dokumentum Annához kerül jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-200">If Sue approves the document, it's sent to Ann for approval.</span></span>

        ![Jóváhagyási folyamattal rendelkező munkafolyamat](./media/workflow_multipleusersinstep.gif)

    - <span data-ttu-id="9b1b5-202">**A jóváhagyók többsége** – A dokumentumhoz rendelt művelet meg van határozva, ha a jóváhagyók többsége válaszol.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-202">**Majority of approvers** – The action that is applied to the document is determined when most of the approvers respond.</span></span> <span data-ttu-id="9b1b5-203">Például, Balázs egy 15 000 USA-dolláros költségjelentést küldött el.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-203">For example, Sam has submitted an expense report for USD 15,000.</span></span> <span data-ttu-id="9b1b5-204">A költségjelentés jelenleg Zsuzsannához, Jankához és Vilmoshoz van hozzárendelve.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-204">The expense report is currently assigned to Sue, Jo, and Bill.</span></span> <span data-ttu-id="9b1b5-205">Ha Zsuzsanna és Janka az első két választ adó jóváhagyó, a rendszer hozzárendeli az általuk végzett műveletet a dokumentumhoz.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-205">If Sue and Jo are the first two approvers who respond, the action that they take is applied to the document.</span></span>

        - <span data-ttu-id="9b1b5-206">Ha Zsuzsanna jóváhagyja a dokumentumot, viszont Janka visszautasítja azt, akkor a dokumentum visszautasításra kerül, és visszaküldik Balázs részére.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-206">If Sue approves the document, but Jo rejects it, the document is rejected and sent back to Sam.</span></span>
        - <span data-ttu-id="9b1b5-207">Ha Zsuzsanna és Janka jóváhagyja a dokumentumot, akkor a dokumentum Annához kerül jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-207">If both Sue and Jo approve the document, it's sent to Ann for approval.</span></span>

    - <span data-ttu-id="9b1b5-208">**A jóváhagyók százaléka** – A rendszer meghatározza a dokumentumhoz kapcsolódó műveletet, ha válaszol a jóváhagyók meghatározott százaléka.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-208">**Percentage of approvers** – The action that is applied to the document is determined when a specific percentage of the approvers respond.</span></span> <span data-ttu-id="9b1b5-209">Például, Balázs egy 15 000 USA-dolláros költségjelentést küldött el.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-209">For example, Sam has submitted an expense report for USD 15,000.</span></span> <span data-ttu-id="9b1b5-210">A költségjelentés jelenleg Zsuzsannához, Jankához és Vilmoshoz van hozzárendelve, **50** értéket adott meg százalékos értékként.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-210">The expense report is currently assigned to Sue, Jo, and Bill, and you entered **50** as the percentage.</span></span> <span data-ttu-id="9b1b5-211">Ha Zsuzsanna és Janka az első két jóváhagyó, aki válaszol, az általuk végzett művelet hozzá van rendelve a dokumentumhoz, mert azok megfelelnek a jóváhagyók 50%-os követelményének.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-211">If Sue and Jo are the first two approvers who respond, the action that they take is applied to the document, because they meet the requirement for 50 percent of approvers.</span></span>

        - <span data-ttu-id="9b1b5-212">Ha Zsuzsanna jóváhagyja a dokumentumot, viszont Janka visszautasítja azt, akkor a dokumentum visszautasításra kerül, és visszaküldik Balázs részére.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-212">If Sue approves the document, but Jo rejects it, the document is rejected and sent back to Sam.</span></span>
        - <span data-ttu-id="9b1b5-213">Ha Zsuzsanna és Janka jóváhagyja a dokumentumot, akkor a dokumentum Annához kerül jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-213">If both Sue and Jo approve the document, it's sent to Ann for approval.</span></span>

    - <span data-ttu-id="9b1b5-214">**Minden jóváhagyó** – Minden jóváhagyónak jóvá kell hagynia a dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-214">**All approvers** – All the approvers must approve the document.</span></span> <span data-ttu-id="9b1b5-215">Máskülönben a munkafolyamat nem folytatható.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-215">Otherwise, the workflow can't continue.</span></span> <span data-ttu-id="9b1b5-216">Például, Balázs egy 15 000 USA-dolláros költségjelentést küldött el.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-216">For example, Sam has submitted an expense report for USD 15,000.</span></span> <span data-ttu-id="9b1b5-217">A költségjelentés jelenleg Zsuzsannához, Jankához és Vilmoshoz van hozzárendelve.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-217">The expense report is currently assigned to Sue, Jo, and Bill.</span></span> <span data-ttu-id="9b1b5-218">Ha Zsuzsanna és Janka jóváhagyja a dokumentumot, viszont Vilmos visszautasítja azt, akkor a dokumentum visszautasításra kerül, és visszaküldik Balázs részére.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-218">If Sue and Joe approve the document, but Bill rejects it, the document is rejected and sent back to Sam.</span></span> <span data-ttu-id="9b1b5-219">Ha Zsuzsanna, Janka és Vilmos jóváhagyja a dokumentumot, akkor a dokumentum Annához kerül jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-219">If Sue, Jo, and Bill all approve the document, it's sent to Ann for approval.</span></span>

## <a name="specify-when-the-approval-step-is-required"></a><span data-ttu-id="9b1b5-220">Határozza meg, hogy mikor van szükség a jóváhagyási lépésre.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-220">Specify when the approval step is required</span></span>

<span data-ttu-id="9b1b5-221">Meghatározhatja, hogy mikor van szükség a jóváhagyási lépésre.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-221">You can specify when the approval step is required.</span></span> <span data-ttu-id="9b1b5-222">A jóváhagyási lépésre minden esetben szükség lehet, vagy csak akkor lehet szükséges, ha bizonyos feltételek teljesülnek.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-222">The approval step can always be required, or it can be required only if specific conditions are met.</span></span>

### <a name="the-approval-step-is-always-required"></a><span data-ttu-id="9b1b5-223">A jóhagyási lépés mindig szükséges.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-223">The approval step is always required</span></span>

<span data-ttu-id="9b1b5-224">Végezze el a következő lépéseket, ha a jóváhagyási lépés mindig szükséges.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-224">Follow these steps if the approval step is always required.</span></span>

1. <span data-ttu-id="9b1b5-225">A bal oldali panelen kattintson a **Feltétel** gombra.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-225">In the left pane, click **Condition**.</span></span>
2. <span data-ttu-id="9b1b5-226">Válassza az **Ez a lépés mindig legyen végrehajtva** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-226">Select the **Always run this step** option.</span></span>

### <a name="the-approval-step-is-required-in-specific-conditions"></a><span data-ttu-id="9b1b5-227">A bizonyos feltételek fennállása esetén szükséges jóváhagyási lépés</span><span class="sxs-lookup"><span data-stu-id="9b1b5-227">The approval step is required in specific conditions</span></span>

<span data-ttu-id="9b1b5-228">Lehet, hogy az éppen konfigurált lépést csak akkor szükséges megadni, ha bizonyos feltételek teljesülnek.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-228">The approval step that you're configuring might be required only if specific conditions are met.</span></span> <span data-ttu-id="9b1b5-229">Például, ha egy beszerzési igénylési munkafolyamat egyik jóváhagyási lépését konfigurálja, csak akkor érdemes elvégezni a jóváhagyási lépést, ha a beszerzési igénylés összege nagyobb 10 000 USA-dollárnál.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-229">For example, if you're configuring an approval step for a purchase requisition workflow, you might want the approval step to occur only if the amount of the purchase requisition is more than USD 10,000.</span></span> <span data-ttu-id="9b1b5-230">Végezze el a következő lépéseket, amikor szükséges a jóváhagyási lépés.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-230">Follow these steps to specify when the approval step is required.</span></span>

1. <span data-ttu-id="9b1b5-231">A bal oldali panelen kattintson a **Feltétel** gombra.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-231">In the left pane, click **Condition**.</span></span>
2. <span data-ttu-id="9b1b5-232">Jelölje be a **Csak akkor fusson ez a lépés, ha teljesül a következő feltétel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-232">Select the **Run this step only when the following condition is met** option.</span></span>
3. <span data-ttu-id="9b1b5-233">Feltétel megadása.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-233">Enter a condition.</span></span>
4. <span data-ttu-id="9b1b5-234">Adja meg a további szükséges feltételeket.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-234">Enter any additional conditions that are required.</span></span>
5. <span data-ttu-id="9b1b5-235">Ha ellenőrizni szeretné, hogy a megadott feltételek helyesen vannak-e konfigurálva, végezze el a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="9b1b5-235">To verify that the conditions that you entered are configured correctly, follow these steps:</span></span>

    1. <span data-ttu-id="9b1b5-236">Kattintson a **Teszt** gombra.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-236">Click **Test**.</span></span>
    2. <span data-ttu-id="9b1b5-237">A **Munkafolyamati feltétel tesztelése** oldalon, a **Feltétel érvényesítése** területen válasszon ki egy rekordot.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-237">On the **Test workflow condition** page, in the **Validate condition** area, select a record.</span></span>
    3. <span data-ttu-id="9b1b5-238">Kattintson a **Teszt** gombra.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-238">Click **Test**.</span></span> <span data-ttu-id="9b1b5-239">A rendszer értékeli a bejegyzést, annak érdekében, hogy meghatározza, hogy a meghatározott feltételeknek megfeleljen-e.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-239">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4. <span data-ttu-id="9b1b5-240">Kattintson az **OK** vagy a **Mégse** lehetőségre a **Tulajdonságok** lapra történő visszalépéshez.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-240">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

## <a name="specify-what-happens-when-the-document-is-overdue"></a><span data-ttu-id="9b1b5-241">Határozza meg, hogy mi történjen a dokumentum lejárata esetén</span><span class="sxs-lookup"><span data-stu-id="9b1b5-241">Specify what happens when the document is overdue</span></span>

<span data-ttu-id="9b1b5-242">Ha egy felhasználó nem hajtja végre a dokumentum műveletét a megadott idő alatt, lejár a dokumentum.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-242">If a user doesn't take action on a document in the allotted time, the document is overdue.</span></span> <span data-ttu-id="9b1b5-243">A lejárt dokumentumot eszkalálhatja, illetve automatikusan egy másik felhasználóhoz rendelheti jóváhagyás céljából.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-243">A document that is overdue can be escalated, or automatically assigned to another user for approval.</span></span> <span data-ttu-id="9b1b5-244">Kövesse az alábbi lépéseket a dokumentum eszkalálásához ha lejárt a dokumentum.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-244">Follow these steps to escalate the document if it's overdue.</span></span>

1. <span data-ttu-id="9b1b5-245">A bal oldali panelen kattintson az **Eszkalálás** gombra.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-245">In the left pane, click **Escalation**.</span></span>
2. <span data-ttu-id="9b1b5-246">Válassza ki az **Eszkalációs útvonal használata** jelölőnégyzetet egy eszkalációs útvonal létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-246">Select the **Use escalation path** check box to create an escalation path.</span></span> <span data-ttu-id="9b1b5-247">A rendszer automatikusan hozzárendeli a dokumentumot az eszkalációs útvonalon felsorolt felhasználókhoz.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-247">The system automatically assigns the document to the users who are listed in the escalation path.</span></span> <span data-ttu-id="9b1b5-248">Például az alábbi táblázat egy eszkalációs útvonalat jelent.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-248">For example, the following table represents an escalation path.</span></span>

    | <span data-ttu-id="9b1b5-249">Sorozat</span><span class="sxs-lookup"><span data-stu-id="9b1b5-249">Sequence</span></span> | <span data-ttu-id="9b1b5-250">Eszkalációs útvonal</span><span class="sxs-lookup"><span data-stu-id="9b1b5-250">Escalation path</span></span>      |
    |----------|----------------------|
    | <span data-ttu-id="9b1b5-251">1</span><span class="sxs-lookup"><span data-stu-id="9b1b5-251">1</span></span>        | <span data-ttu-id="9b1b5-252">Hozzárendelés a következőhöz: Dóra</span><span class="sxs-lookup"><span data-stu-id="9b1b5-252">Assign to: Donna</span></span>     |
    | <span data-ttu-id="9b1b5-253">2</span><span class="sxs-lookup"><span data-stu-id="9b1b5-253">2</span></span>        | <span data-ttu-id="9b1b5-254">Hozzárendelés a következőhöz: Ervin</span><span class="sxs-lookup"><span data-stu-id="9b1b5-254">Assign to: Erin</span></span>      |
    | <span data-ttu-id="9b1b5-255">3</span><span class="sxs-lookup"><span data-stu-id="9b1b5-255">3</span></span>        | <span data-ttu-id="9b1b5-256">Utolsó művelet: Elutasítás</span><span class="sxs-lookup"><span data-stu-id="9b1b5-256">Final action: Reject</span></span> |

    <span data-ttu-id="9b1b5-257">Ebben a példában a rendszer Dórához rendeli a lejárt dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-257">In this example, the system assigns the overdue document to Donna.</span></span> <span data-ttu-id="9b1b5-258">Ha Dóra nem válaszol a megadott idő alatt, a rendszer Ervinhez rendeli a dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-258">If Donna doesn't respond in the allotted time, the system assigns the document to Erin.</span></span> <span data-ttu-id="9b1b5-259">Ha Ervin nem válaszol a megadott idő alatt, a rendszer visszautasítja a dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-259">If Erin doesn't respond in the allotted time, the system rejects the document.</span></span>

3. <span data-ttu-id="9b1b5-260">A felhasználó eszkalációs útvonalhoz történő hozzáadásához, kattintson az **Újabb eszkalációs lépés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-260">To add a user to the escalation path, click **Add escalation**.</span></span> <span data-ttu-id="9b1b5-261">A **Hozzárendelés-típus** lapon válasszon ki egy lehetőséget a következő táblázatban, majd ezt követően végezze el a további lépéseket a beállításhoz, mielőtt továbblép a 4. lépésre.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-261">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 4.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="9b1b5-262">Lehetőség</span><span class="sxs-lookup"><span data-stu-id="9b1b5-262">Option</span></span></th>
    <th><span data-ttu-id="9b1b5-263">A dokumentumhoz eszkalált felhasználók</span><span class="sxs-lookup"><span data-stu-id="9b1b5-263">Users that the document is escalated to</span></span></th>
    <th><span data-ttu-id="9b1b5-264">További lépések</span><span class="sxs-lookup"><span data-stu-id="9b1b5-264">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="9b1b5-265">Hierarchia</span><span class="sxs-lookup"><span data-stu-id="9b1b5-265">Hierarchy</span></span></td>
    <td><span data-ttu-id="9b1b5-266">A meghatározott szervezeti hierarchiában lévő felhasználók.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-266">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="9b1b5-267">Miután kiválasztotta <strong>Hierarchia</strong> lehetőséget a <strong>Hierarchia kiválasztása</strong> lapon, a <strong>Hierarchia típusa</strong> listán, jelölje ki a dokumentumhoz eszkalálni hierarchia típusát.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-267">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to escalate the document to.</span></span></li>
    <li><span data-ttu-id="9b1b5-268">A rendszernek be kell olvasnia az felhasználó névtartományát a hierarchiából.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-268">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="9b1b5-269">Ezek a nevek a dokumentumhoz eszkalálható felhasználókat jelölik.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-269">These names represent users that the document can be escalated to.</span></span> <span data-ttu-id="9b1b5-270">Végezze el a következő lépéseket azon felhasználók névtartományának kezdő- és végpontját, amelyet a rendszer beolvas:</span><span class="sxs-lookup"><span data-stu-id="9b1b5-270">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="9b1b5-271">A kezdő pont megadásához válasszon ki egy személyt a <strong>Kezdet</strong> listából.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-271">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="9b1b5-272">A végpont megadásához kattintson a <strong>Feltétel létrehozása</strong> lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-272">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="9b1b5-273">Ezt követően adja meg azt a feltételt, amely meghatározza, hogy a rendszer hol állítsa meg a hierarchiában a nevek beolvasását.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-273">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="9b1b5-274">A <strong>Hierarchia beállításai</strong> lapon adja meg, hogy mely, a tartományban szereplő felhasználókhoz kell a dokumentumot eszkalálni:</span><span class="sxs-lookup"><span data-stu-id="9b1b5-274">On the <strong>Hierarchy options</strong> tab, specify which users in the range the document should be escalated to:</span></span> <ul>
    <li><span data-ttu-id="9b1b5-275"><strong>Minden lekért felhasználó hozzárendelése</strong> – A tartományban szereplő összes felhasználóhoz eszkalálva van a dokumentum.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-275"><strong>Assign to all users retrieved</strong> – The document is escalated to all users in the range.</span></span></li>
    <li><span data-ttu-id="9b1b5-276"><strong>Csak a legutóbb lekért felhasználó hozzárendelése</strong> – Csak a tartományban szereplő utolsó felhasználóhoz van eszkalálva a dokumentum.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-276"><strong>Assign only to last user retrieved</strong> – The document is escalated to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="9b1b5-277"><strong>A következő feltételnek megfelelő felhasználók kihagyása</strong> – A dokumentum nincs eszkalálva a tartomány összes olyan felhasználójához, akik megfelelnek egy adott feltételnek.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-277"><strong>Exclude users with the following condition</strong> – The document isn't escalated to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="9b1b5-278">Kattintson a <strong>Feltétel hozzáadása</strong> lehetőségre, ha meg szeretné adni a feltételt.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-278">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="9b1b5-279">Munkafolyamat felhasználója</span><span class="sxs-lookup"><span data-stu-id="9b1b5-279">Workflow user</span></span></td>
    <td><span data-ttu-id="9b1b5-280">Az aktuális munkafolyamatban szereplő felhasználó</span><span class="sxs-lookup"><span data-stu-id="9b1b5-280">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="9b1b5-281">Miután kijelölte <strong>Munkafolyamat-felhasználó</strong> lehetőséget a <strong>Munkafolyamat-felhasználó</strong> lapon a <strong>Munkafolyamat-felhasználó</strong> listából, jelöljön ki egy felhasználót, aki részt vesz a munkafolyamatban.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-281">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="9b1b5-282">Felhasználó</span><span class="sxs-lookup"><span data-stu-id="9b1b5-282">User</span></span></td>
    <td><span data-ttu-id="9b1b5-283">Adott Finance and Operations-felhasználók</span><span class="sxs-lookup"><span data-stu-id="9b1b5-283">Specific Finance and Operations users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="9b1b5-284">Miután kijelölte <strong>Felhasználó</strong> lehetőséget, kattintson a <strong>Felhasználó</strong> fülre.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-284">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="9b1b5-285">A <strong>Rendelkezésre álló felhasználók</strong> lista az összes Finance and Operations-felhasználót tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-285">The <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="9b1b5-286">Válassza ki a dokumentumhoz eszkalálni kívánt felhasználókat, majd ezt követően helyezze át ezeket a felhasználókat a <strong>Kijelölt felhasználók</strong> listájára.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-286">Select the users to escalate the document to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. <span data-ttu-id="9b1b5-287">A **Határidő** lapon az **Időtartam** mezőben adja meg, hogy mennyi idő kell a felhasználónak azon dokumentumok végrehajtásához, vagy a válaszolásához, amelyek érvényesek a jóváhagyási lépésre.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-287">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to take action on, or respond to, documents.</span></span> <span data-ttu-id="9b1b5-288">Válasszon a következő lehetőségek közül:</span><span class="sxs-lookup"><span data-stu-id="9b1b5-288">Select one of the following options:</span></span>

    - <span data-ttu-id="9b1b5-289">**Órák** – Adja meg azon órák számát, amely alatt a felhasználónak reagálnia kell.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-289">**Hours** – Enter the number of hours that the user has to respond.</span></span> <span data-ttu-id="9b1b5-290">Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-290">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="9b1b5-291">**Napok** – Adja meg azon napok számát, amely alatt a felhasználónak reagálnia kell.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-291">**Days** – Enter the number of days that the user has to respond.</span></span> <span data-ttu-id="9b1b5-292">Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-292">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="9b1b5-293">**Hetek** – Adja meg azon hetek számát, amely alatt a felhasználónak reagálnia kell.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-293">**Weeks** – Enter the number of weeks that the user has to respond.</span></span>
    - <span data-ttu-id="9b1b5-294">**Hónapok** – Válassza ki, hogy melyik hét mely napjáig kell a felhasználónak reagálnia.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-294">**Months** – Select the day and week that the user must respond by.</span></span> <span data-ttu-id="9b1b5-295">Például meg lehet adni, hogy a felhasználó a hónap harmadik hetének pénteki napjáig kelljen reagálnia.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-295">For example, you might want the user to respond by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="9b1b5-296">**Évek** – Válassza ki, hogy melyik napon és melyik héten kell a felhasználónak reagálnia.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-296">**Years** – Select the day, week, and month that the user must respond by.</span></span> <span data-ttu-id="9b1b5-297">Például meg lehet adni, hogy a felhasználónak december harmadik hetének pénteki napjáig kelljen reagálnia.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-297">For example, you might want the user to respond by Friday of the third week of December.</span></span>

5. <span data-ttu-id="9b1b5-298">Ismételje meg a 3 – 4. lépést minden egyes olyan felhasználóra vonatkozóan, akiket hozzá kell adni az eszkalációs útvonalhoz.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-298">Repeat steps 3 through 4 for each user that should be added to the escalation path.</span></span> <span data-ttu-id="9b1b5-299">A felhasználók sorrendje módosítható.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-299">You can change the order of the users.</span></span>
6. <span data-ttu-id="9b1b5-300">Ha az eszkalációs útvonalban szereplő felhasználók nem válaszolnak a megadott időn belül, a rendszer automatikusan végrehajtja a dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-300">If the users in the escalation path don't respond in the allotted time, the system automatically take action on the document.</span></span> <span data-ttu-id="9b1b5-301">A rendszer által végzett művelet meghatározásához, válassza ki a **Művelet** sort, majd a **Művelet lezárása** fülön válasszon ki egy műveletet.</span><span class="sxs-lookup"><span data-stu-id="9b1b5-301">To specify the action that the system takes, select the **Action** row, and then, on the **End action** tab, select an action.</span></span>
