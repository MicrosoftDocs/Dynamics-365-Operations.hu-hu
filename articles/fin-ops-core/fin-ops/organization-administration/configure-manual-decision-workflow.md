---
title: Manuális döntések konfigurálása munkafolyamatban
description: Ez a témakör bemutatja, hogy hogyan kell konfigurálni a manuális döntés tulajdonságait.
author: ChrisGarty
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 192101
ms.assetid: 0bccad77-1a44-4f08-967b-12c62c02afc7
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e16ed97351423a50aff433d535ea4c575d97e7fd
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747879"
---
# <a name="configure-manual-decisions-in-a-workflow"></a><span data-ttu-id="4ed4c-103">Manuális döntések konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="4ed4c-103">Configure manual decisions in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4ed4c-104">Ez a témakör bemutatja, hogy hogyan kell konfigurálni a manuális döntés tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-104">This topic explains how to configure the properties of a manual decision.</span></span>

<span data-ttu-id="4ed4c-105">A munkafolyamat-szerkesztő manuális döntésének konfigurálásához, kattintson a jobb gombbal a manuális döntésre, és kattintson **Tulajdonságok** oldal megnyitásához a **Tulajdonságok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-105">To configure a manual decision in the workflow editor, right-click the manual decision, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="4ed4c-106">Ezt követően a következő eljárások segítségével állítsa be a manuális döntés tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-106">Then use the following procedures to configure the properties of the manual decision.</span></span>

## <a name="name-the-decision"></a><span data-ttu-id="4ed4c-107">A döntés elnevezése</span><span class="sxs-lookup"><span data-stu-id="4ed4c-107">Name the decision</span></span>

<span data-ttu-id="4ed4c-108">A következő lépések segítségével elnevezheti a manuális döntést.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-108">Follow these steps to enter a name for the manual decision.</span></span>

1. <span data-ttu-id="4ed4c-109">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="4ed4c-110">Adja meg a manuális döntés egyedi nevét az **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-110">In the **Name** field, enter a unique name for the manual decision.</span></span>

## <a name="enter-a-subject-line-and-instructions"></a><span data-ttu-id="4ed4c-111">A tárgysor és az utasítások megadása</span><span class="sxs-lookup"><span data-stu-id="4ed4c-111">Enter a subject line and instructions</span></span>

<span data-ttu-id="4ed4c-112">Meg kell adnia egy tárgysort, illetve utasításokat a manuális döntéshez hozzárendelt felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-112">You must provide a subject line and instructions to users who are assigned to the manual decision.</span></span> <span data-ttu-id="4ed4c-113">Például, ha a beszerzési igénylések döntését konfigurálja, a döntéshez hozzárendelt felhasználó látja a tárgysort és az utasításokat a **Beszerzési igénylések** oldalon.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-113">For example, if you're configuring a decision for purchase requisitions, the user who is assigned to the decision sees the subject line and instructions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="4ed4c-114">A tárgysor az oldal egy üzenetsorán jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-114">The subject line appears in a message bar on the page.</span></span> <span data-ttu-id="4ed4c-115">A felhasználó ezt követően rákattinthat az üzenetsoron található ikonra az útmutatás megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-115">The user can then click the icon in the message bar to view the instructions.</span></span> <span data-ttu-id="4ed4c-116">Kövesse a következő lépéseket a tárgysor és az utasítások megadásához.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-116">Follow these steps to enter a subject line and instructions.</span></span>

1. <span data-ttu-id="4ed4c-117">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-117">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="4ed4c-118">Írja be a tárgysort a **Munkatétel tárgya** oldalon található **Munkatétel tárgya** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-118">On the **Instructions** tab, in the **Work item subject** field, enter the subject line.</span></span>
3. <span data-ttu-id="4ed4c-119">A tárgysor személyre szabásához helyőrzőket illeszthet be.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-119">To personalize the subject line, you can insert placeholders.</span></span> <span data-ttu-id="4ed4c-120">A helyőrzők helyére a megfelelő adatok kerülnek, amikor a tárgysor megjelenik a felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-120">Placeholders are replaced with appropriate data when the subject line is shown to users.</span></span> <span data-ttu-id="4ed4c-121">Végezze el a következő lépéseket a helyőrzők beillesztéséhez:</span><span class="sxs-lookup"><span data-stu-id="4ed4c-121">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="4ed4c-122">Kattintson oda a szövegdobozban, ahol meg szeretné jeleníteni a helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-122">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="4ed4c-123">Kattintson a **Helyőrző beszúrása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-123">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="4ed4c-124">A megjelenő listában válassza ki a beilleszteni kívánt helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-124">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="4ed4c-125">Kattintson a **Beszúrás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-125">Click **Insert**.</span></span>

4. <span data-ttu-id="4ed4c-126">A tárgysor fordításai hozzáadásához, végezze el a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="4ed4c-126">To add translations of the subject line, follow these steps:</span></span>

    1. <span data-ttu-id="4ed4c-127">Kattintson a **Fordítások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-127">Click **Translations**.</span></span>
    2. <span data-ttu-id="4ed4c-128">A megjelenő oldalon kattintson a **Hozzáadás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-128">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="4ed4c-129">A megjelenő listában válassza ki az éppen begépelt szöveg nyelvét.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-129">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="4ed4c-130">Írja be a szöveget a **Lefordított szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-130">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="4ed4c-131">A szöveg személyre szabásához, helyőrzőket illeszthet be a 3. lépésben leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-131">To personalize the text, you can insert placeholders as described in step 3.</span></span>
    6. <span data-ttu-id="4ed4c-132">Kattintson a **Bezárás** gombra.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-132">Click **Close**.</span></span>

5. <span data-ttu-id="4ed4c-133">Írja be az utasításokat a **Munkatétel utasításai** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-133">In the **Work item instructions** field, enter the instructions.</span></span>
6. <span data-ttu-id="4ed4c-134">Az utasítások testreszabásához, helyőrzőket illeszthet be.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-134">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="4ed4c-135">A helyőrzők helyére a megfelelő adatok kerülnek, amikor az utasítások megjelennek a felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-135">Placeholders are replaced with appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="4ed4c-136">Végezze el a következő lépéseket a helyőrzők beillesztéséhez:</span><span class="sxs-lookup"><span data-stu-id="4ed4c-136">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="4ed4c-137">Kattintson oda a szövegdobozban, ahol meg szeretné jeleníteni a helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-137">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="4ed4c-138">Kattintson a **Helyőrző beszúrása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-138">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="4ed4c-139">A megjelenő listában válassza ki a beilleszteni kívánt helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-139">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="4ed4c-140">Kattintson a **Beszúrás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-140">Click **Insert**.</span></span>

7. <span data-ttu-id="4ed4c-141">Az utasítások fordításainak hozzáadásához, végezze el a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="4ed4c-141">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="4ed4c-142">Kattintson a **Fordítások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-142">Click **Translations**.</span></span>
    2. <span data-ttu-id="4ed4c-143">A megjelenő oldalon kattintson a **Hozzáadás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-143">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="4ed4c-144">A megjelenő listában válassza ki az éppen begépelt szöveg nyelvét.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-144">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="4ed4c-145">Írja be a szöveget a **Lefordított szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-145">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="4ed4c-146">A szöveg személyre szabásához, helyőrzőket illeszthet be a 6. lépésben leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-146">To personalize the text, you can insert placeholders as described in step 6.</span></span>
    6. <span data-ttu-id="4ed4c-147">Kattintson a **Bezárás** gombra.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-147">Click **Close**.</span></span>

## <a name="specify-the-possible-outcomes-of-a-decision"></a><span data-ttu-id="4ed4c-148">A döntés lehetséges kimeneteinek meghatározása</span><span class="sxs-lookup"><span data-stu-id="4ed4c-148">Specify the possible outcomes of a decision</span></span>

<span data-ttu-id="4ed4c-149">Általában, amikor a rendszer hozzárendeli a dokumentumot a döntéshozóhoz, a döntéshozónak meg kell válaszolnia egy kérdést.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-149">Typically, when a document is assigned to a decision maker, the decision maker is asked a question.</span></span> <span data-ttu-id="4ed4c-150">A válasz a kérdésre általában **Igen** vagy **Nem**, vagy **Igaz** vagy **Hamis**.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-150">The answer to this question is usually **Yes** or **No**, or **True** or **False**.</span></span> <span data-ttu-id="4ed4c-151">Végezze el a következő lépéseket a manuális döntés lehetséges kimeneteinek meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-151">Follow these steps to specify the possible outcomes of the manual decision.</span></span>

1. <span data-ttu-id="4ed4c-152">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-152">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="4ed4c-153">Írja be az eredmény vagy a beállítás nevét az **Eredmények** oldalon található **1. Eredmény** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-153">On the **Outcomes** tab, in the **Outcome 1** field, enter the name of the outcome, or the option.</span></span>
3. <span data-ttu-id="4ed4c-154">Az eredmény fordításainak hozzáadásához, végezze el a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="4ed4c-154">To add translations of the outcome, follow these steps:</span></span>

    1. <span data-ttu-id="4ed4c-155">Kattintson a **Fordítások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-155">Click **Translations**.</span></span>
    2. <span data-ttu-id="4ed4c-156">A megjelenő oldalon kattintson a **Hozzáadás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-156">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="4ed4c-157">A megjelenő listában válassza ki az éppen begépelt szöveg nyelvét.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-157">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="4ed4c-158">Írja be a szöveget a **Lefordított szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-158">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="4ed4c-159">Kattintson a **Bezárás** gombra.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-159">Click **Close**.</span></span>

4. <span data-ttu-id="4ed4c-160">Írja be az eredmény vagy a beállítás nevét az **2. Eredmény** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-160">In the **Outcome 2** field, enter the name of the outcome, or the option.</span></span>
5. <span data-ttu-id="4ed4c-161">Az eredmény fordításainak hozzáadásához, végezze el a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="4ed4c-161">To add translations of the outcome, follow these steps:</span></span>

    1. <span data-ttu-id="4ed4c-162">Kattintson a **Fordítások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-162">Click **Translations**.</span></span>
    2. <span data-ttu-id="4ed4c-163">A megjelenő oldalon kattintson a **Hozzáadás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-163">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="4ed4c-164">A megjelenő listában válassza ki az éppen begépelt szöveg nyelvét.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-164">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="4ed4c-165">Írja be a szöveget a **Lefordított szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-165">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="4ed4c-166">Kattintson a **Bezárás** gombra.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-166">Click **Close**.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="4ed4c-167">Az értesítések küldési idejének meghatározása</span><span class="sxs-lookup"><span data-stu-id="4ed4c-167">Specify when notifications are sent</span></span>

<span data-ttu-id="4ed4c-168">Értesítéseket küldhet a felhasználók számára, amikor a döntés meghozatalakor, delegálásakor, vagy eszkalálásakor.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-168">You can send notifications to people when a decision has been made, delegated, or escalated.</span></span> <span data-ttu-id="4ed4c-169">Végezze el a következő lépéseket, annak meghatározása érdekében, hogy mikor és kinek küldje el a rendszer az értesítéseket.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-169">Follow these steps to specify when notifications are sent, and who the notifications are sent to.</span></span>

1. <span data-ttu-id="4ed4c-170">A bal oldali panelen kattintson az **Értesítések** gombra.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-170">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="4ed4c-171">Jelölje be a jelölőnégyzetet azon eseményekhez, amelyekhez ki kell küldeni az értesítéseket:</span><span class="sxs-lookup"><span data-stu-id="4ed4c-171">Select the check box next to the events that notifications should be sent for:</span></span>

    - <span data-ttu-id="4ed4c-172">**\[Választható 1\]** – A hozzárendelt felhasználó a **\[Választható 1\]** lehetőséget választotta.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-172">**\[Choice 1\]** – The assigned user has selected **\[Choice 1\]**.</span></span>
    - <span data-ttu-id="4ed4c-173">**\[Választható 2\]** – A hozzárendelt felhasználó a **\[Választható 2\]** lehetőséget választotta.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-173">**\[Choice 2\]** – The assigned user has selected **\[Choice 2\]**.</span></span>
    - <span data-ttu-id="4ed4c-174">**Delegált** – A hozzárendelt felhasználó hozzárendelte a döntést egy másik felhasználóhoz.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-174">**Delegate** – The assigned user has assigned the decision to another user.</span></span>
    - <span data-ttu-id="4ed4c-175">**Eszkaláció** – A hozzárendelt felhasználó nem végezte el a döntést a kijelölt időn belül.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-175">**Escalate** – The assigned user hasn't made the decision in the allotted time.</span></span>

3. <span data-ttu-id="4ed4c-176">Jelölje ki a sort a 2. lépésben választott eseményhez.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-176">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="4ed4c-177">Írja be az értesítés szövegét az **Értesítési szöveg** lapon lévő szövegdobozba.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-177">On the **Notification text** tab, in the text box, enter the text of the notification.</span></span>
5. <span data-ttu-id="4ed4c-178">Az értesítések személyre szabásához, helyőrzőket szúrhat be.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-178">To personalize the notification, you can insert placeholders.</span></span> <span data-ttu-id="4ed4c-179">A helyőrzők helyére a megfelelő adatok kerülnek, amikor az értesítés megjelenik a felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-179">Placeholders are replaced with appropriate data when the notification is show to users.</span></span> <span data-ttu-id="4ed4c-180">Végezze el a következő lépéseket a helyőrzők beillesztéséhez:</span><span class="sxs-lookup"><span data-stu-id="4ed4c-180">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="4ed4c-181">Kattintson oda a szövegdobozban, ahol meg szeretné jeleníteni a helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-181">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="4ed4c-182">Kattintson a **Helyőrző beszúrása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-182">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="4ed4c-183">A megjelenő listában válassza ki a beilleszteni kívánt helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-183">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="4ed4c-184">Kattintson a **Beszúrás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-184">Click **Insert**.</span></span>

6. <span data-ttu-id="4ed4c-185">Az értesítések fordításainak hozzáadásához, végezze el a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="4ed4c-185">To add translations of the notification, follow these steps:</span></span>

    1. <span data-ttu-id="4ed4c-186">Kattintson a **Fordítások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-186">Click **Translations**.</span></span>
    2. <span data-ttu-id="4ed4c-187">A megjelenő oldalon kattintson a **Hozzáadás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-187">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="4ed4c-188">A megjelenő listában válassza ki az éppen begépelt szöveg nyelvét.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-188">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="4ed4c-189">Írja be a szöveget a **Lefordított szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-189">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="4ed4c-190">A szöveg személyre szabásához, helyőrzőket illeszthet be a 5. lépésben leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-190">To personalize the text, you can insert placeholders as described in step 5.</span></span>
    6. <span data-ttu-id="4ed4c-191">Kattintson a **Bezárás** gombra.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-191">Click **Close**.</span></span>

7. <span data-ttu-id="4ed4c-192">Adja meg azokat a személyeket, akik értesítéseket kapnak a **Címzett** lapon.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-192">On the **Recipient** tab, specify who the notifications are sent to.</span></span> <span data-ttu-id="4ed4c-193">Válasszon ki egy lehetőséget a következő táblázatban, majd ezt követően végezze el a további lépéseket a beállításhoz, mielőtt továbblép a 8. lépésre.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-193">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 8.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="4ed4c-194">Lehetőség</span><span class="sxs-lookup"><span data-stu-id="4ed4c-194">Option</span></span></th>
    <th><span data-ttu-id="4ed4c-195">Értesítés címzettjei</span><span class="sxs-lookup"><span data-stu-id="4ed4c-195">Notification recipients</span></span></th>
    <th><span data-ttu-id="4ed4c-196">További lépések</span><span class="sxs-lookup"><span data-stu-id="4ed4c-196">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="4ed4c-197">Résztvevő</span><span class="sxs-lookup"><span data-stu-id="4ed4c-197">Participant</span></span></td>
    <td><span data-ttu-id="4ed4c-198">Egy adott csoporthoz vagy szerephez hozzárendelt felhasználók</span><span class="sxs-lookup"><span data-stu-id="4ed4c-198">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="4ed4c-199">Miután kiválasztotta <strong>Résztvevő</strong> lehetőséget a <strong>Szerepkör-alapú</strong> lapon, a <strong>Résztvevő típusa</strong> listán jelölje ki azon csoport vagy a szerepkör típusát, amely számára az értesítéseket el kívánja küldeni.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-199">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="4ed4c-200">A <strong>Résztvevő</strong> listán jelölje ki a csoportot vagy szerepkört, amely számára értesítést kíván küldeni.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-200">In the <strong>Participant</strong> list, select the group or to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="4ed4c-201">Munkafolyamat felhasználója</span><span class="sxs-lookup"><span data-stu-id="4ed4c-201">Workflow user</span></span></td>
    <td><span data-ttu-id="4ed4c-202">Az aktuális munkafolyamatban szereplő felhasználó</span><span class="sxs-lookup"><span data-stu-id="4ed4c-202">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="4ed4c-203">Miután kijelölte <strong>Munkafolyamat-felhasználó</strong> lehetőséget a <strong>Munkafolyamat-felhasználó</strong> lapon a <strong>Munkafolyamat-felhasználó</strong> listából, jelöljön ki egy felhasználót, aki részt vesz a munkafolyamatban.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-203">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="4ed4c-204">Felhasználó</span><span class="sxs-lookup"><span data-stu-id="4ed4c-204">User</span></span></td>
    <td><span data-ttu-id="4ed4c-205">Meghatározott felhasználók</span><span class="sxs-lookup"><span data-stu-id="4ed4c-205">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="4ed4c-206">Miután kijelölte <strong>Felhasználó</strong> lehetőséget, kattintson a <strong>Felhasználó</strong> fülre.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-206">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="4ed4c-207">A <strong>Rendelkezésre álló felhasználók</strong> listája az összes felhasználót tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-207">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="4ed4c-208">Válassza ki azokat a felhasználókat, akik számára értesítéseket kíván küldeni, majd helyezze át ezeket a felhasználókat a <strong>Kijelölt felhasználók</strong> listájára.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-208">Select the users to send notifications to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="4ed4c-209">Ismételje meg a 3 – 7. lépést a 2. lépésben kiválasztott összes eseményhez.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-209">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="assign-a-decision"></a><span data-ttu-id="4ed4c-210">Döntés hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="4ed4c-210">Assign a decision</span></span>

<span data-ttu-id="4ed4c-211">Végezze el ezeket a lépéseket azon személyek meghatározásához, akiket a manuális döntéshez hozzá kell rendelni.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-211">Follow these steps to specify who a manual decision should be assigned to.</span></span>

1. <span data-ttu-id="4ed4c-212">A bal oldali panelen kattintson a **Hozzárendelés** gombra.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-212">In the left pane, click **Assignment**.</span></span>
2. <span data-ttu-id="4ed4c-213">A **Hozzárendelés-típus** lapon válasszon ki egy lehetőséget a következő táblázatban, majd ezt követően végezze el a további lépéseket a beállításhoz, mielőtt továbblép a 3. lépésre.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-213">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 3.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="4ed4c-214">Lehetőség</span><span class="sxs-lookup"><span data-stu-id="4ed4c-214">Option</span></span></th>
    <th><span data-ttu-id="4ed4c-215">A döntéshez hozzárendelt felhasználók</span><span class="sxs-lookup"><span data-stu-id="4ed4c-215">Users that the decision is assigned to</span></span></th>
    <th><span data-ttu-id="4ed4c-216">További lépések</span><span class="sxs-lookup"><span data-stu-id="4ed4c-216">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="4ed4c-217">Résztvevő</span><span class="sxs-lookup"><span data-stu-id="4ed4c-217">Participant</span></span></td>
    <td><span data-ttu-id="4ed4c-218">Egy adott csoporthoz vagy szerephez hozzárendelt felhasználók</span><span class="sxs-lookup"><span data-stu-id="4ed4c-218">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="4ed4c-219">Miután kiválasztotta <strong>Résztvevő</strong> lehetőséget a <strong>Szerepkör-alapú</strong> lapon, a <strong>Résztvevő típusa</strong> listán jelölje ki a döntéshez hozzárendelni kívánt csoport vagy a szerepkör típusát.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-219">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to assign the decision to.</span></span></li>
    <li><span data-ttu-id="4ed4c-220">A <strong>Résztvevő</strong> listán jelölje ki a döntéshez hozzárendelni kívánt csoportot vagy szerepkört.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-220">In the <strong>Participant</strong> list, select the group or role to assign the decision to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="4ed4c-221">Hierarchia</span><span class="sxs-lookup"><span data-stu-id="4ed4c-221">Hierarchy</span></span></td>
    <td><span data-ttu-id="4ed4c-222">A meghatározott szervezeti hierarchiában lévő felhasználók.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-222">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="4ed4c-223">Miután kiválasztotta <strong>Hierarchia</strong> lehetőséget a <strong>Hierarchia kiválasztása</strong> lapon, a <strong>Hierarchia típusa</strong> listán, jelölje ki a döntéshez hozzárendelni kívánt hierarchia típusát.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-223">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to assign the decision to.</span></span></li>
    <li><span data-ttu-id="4ed4c-224">A rendszernek be kell olvasnia az felhasználó névtartományát a hierarchiából.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-224">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="4ed4c-225">Ezek a nevek a döntéshez hozzárendelhető felhasználókat jelölik.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-225">These names represent users that the decision can be assigned to.</span></span> <span data-ttu-id="4ed4c-226">Végezze el a következő lépéseket azon felhasználók névtartományának kezdő- és végpontját, amelyet a rendszer beolvas:</span><span class="sxs-lookup"><span data-stu-id="4ed4c-226">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="4ed4c-227">A kezdő pont megadásához válasszon ki egy személyt a <strong>Kezdet</strong> listából.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-227">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="4ed4c-228">A végpont megadásához kattintson a <strong>Feltétel létrehozása</strong> lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-228">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="4ed4c-229">Ezt követően adja meg azt a feltételt, amely meghatározza, hogy a rendszer hol állítsa meg a hierarchiában a nevek beolvasását.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-229">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="4ed4c-230">A <strong>Hierarchia beállításai</strong> lapon adja meg, hogy mely, a tartományban szereplő felhasználók számára kell a döntést hozzárendelni:</span><span class="sxs-lookup"><span data-stu-id="4ed4c-230">On the <strong>Hierarchy options</strong> tab, specify which users in the range the decision should be assigned to:</span></span> <ul>
    <li><span data-ttu-id="4ed4c-231"><strong>Minden lekért felhasználó hozzárendelése</strong> – A tartományban szereplő összes felhasználóhoz hozzá van rendelve a döntés.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-231"><strong>Assign to all users retrieved</strong> – The decision is assigned to all users in the range.</span></span></li>
    <li><span data-ttu-id="4ed4c-232"><strong>Csak a legutóbb lekért felhasználó hozzárendelése</strong> – Csak a tartományban szereplő utolsó felhasználóhoz van hozzárendelve a döntés.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-232"><strong>Assign only to last user retrieved</strong> – The decision is assigned to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="4ed4c-233"><strong>A következő feltételnek megfelelő felhasználók kihagyása</strong> – A döntés nincs hozzárendelve a tartomány minden olyan felhasználójához, akik megfelelnek egy adott feltételnek.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-233"><strong>Exclude users with the following condition</strong> – The decision isn't assigned to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="4ed4c-234">Kattintson a <strong>Feltétel hozzáadása</strong> lehetőségre, ha meg szeretné adni a feltételt.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-234">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="4ed4c-235">Munkafolyamat felhasználója</span><span class="sxs-lookup"><span data-stu-id="4ed4c-235">Workflow user</span></span></td>
    <td><span data-ttu-id="4ed4c-236">Az aktuális munkafolyamatban szereplő felhasználó</span><span class="sxs-lookup"><span data-stu-id="4ed4c-236">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="4ed4c-237">Miután kijelölte <strong>Munkafolyamat-felhasználó</strong> lehetőséget a <strong>Munkafolyamat-felhasználó</strong> lapon a <strong>Munkafolyamat-felhasználó</strong> listából, jelöljön ki egy felhasználót, aki részt vesz a munkafolyamatban.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-237">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="4ed4c-238">Felhasználó</span><span class="sxs-lookup"><span data-stu-id="4ed4c-238">User</span></span></td>
    <td><span data-ttu-id="4ed4c-239">Meghatározott felhasználók</span><span class="sxs-lookup"><span data-stu-id="4ed4c-239">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="4ed4c-240">Miután kijelölte <strong>Felhasználó</strong> lehetőséget, kattintson a <strong>Felhasználó</strong> fülre.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-240">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="4ed4c-241">A <strong>Rendelkezésre álló felhasználók</strong> listája az összes felhasználót tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-241">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="4ed4c-242">Válassza ki a döntéshez hozzárendelni kívánt felhasználókat, majd ezt követően helyezze át ezeket a felhasználókat a <strong>Kijelölt felhasználók</strong> listájára.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-242">Select the users to assign the decision to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

3. <span data-ttu-id="4ed4c-243">A **Határidő** lapon az **Időtartam** mezőben adja meg, hogy mennyi idő kell a felhasználónak a döntéshozatalhoz.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-243">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to make the decision.</span></span> <span data-ttu-id="4ed4c-244">Válasszon a következő lehetőségek közül:</span><span class="sxs-lookup"><span data-stu-id="4ed4c-244">Select one of the following options:</span></span>

    - <span data-ttu-id="4ed4c-245">**Órák** – Adja meg azon órák számát, amely alatt a felhasználónak meg kell hoznia a döntést.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-245">**Hours** – Enter the number of hours that the user has to make the decision.</span></span> <span data-ttu-id="4ed4c-246">Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-246">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="4ed4c-247">**Napok** – Adja meg azon napok számát, amely alatt a felhasználónak meg kell hoznia a döntést.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-247">**Days** – Enter the number of days that the user has to make the decision.</span></span> <span data-ttu-id="4ed4c-248">Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-248">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="4ed4c-249">**Hetek** – Adja meg azon hetek számát, amely alatt a felhasználónak meg kell hoznia a döntést.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-249">**Weeks** – Enter the number of weeks that the user has to make the decision.</span></span>
    - <span data-ttu-id="4ed4c-250">**Hónapok** – Válassza ki, hogy melyik hét mely napjáig kell a felhasználónak meghoznia a döntést.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-250">**Months** – Select the day and week that the user must make the decision by.</span></span> <span data-ttu-id="4ed4c-251">Kérheti például, hogy a felhasználó a hónap harmadik hetének péntekéig hozza meg a döntést.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-251">For example, you might want the user to make the decision by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="4ed4c-252">**Évek** – Válassza ki, hogy melyik hónap mely hetéig kell a felhasználónak meghoznia a döntést.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-252">**Years** – Select the day, week, and month that the user must make the decision by.</span></span> <span data-ttu-id="4ed4c-253">Kérheti például, hogy a felhasználó december harmadik hetének péntekéig hozza meg a döntést.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-253">For example, you might want the user to make the decision by Friday of the third week of December.</span></span>

    <span data-ttu-id="4ed4c-254">Ha a felhasználó nem hozza meg a döntést a megadott idő alatt, lejár a döntés.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-254">If the user doesn't make the decision in the allotted time, the decision is overdue.</span></span> <span data-ttu-id="4ed4c-255">A lejárt döntés eszkalált, amely az **Eszkaláció** terület lapján kiválasztott beállításokon alapul.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-255">A decision that is overdue is escalated, based on the options that you select in the **Escalation** area of the page.</span></span>

## <a name="specify-what-happens-when-a-decision-is-overdue"></a><span data-ttu-id="4ed4c-256">Annak megadása, hogy mi történjen, amikor lejár a döntés</span><span class="sxs-lookup"><span data-stu-id="4ed4c-256">Specify what happens when a decision is overdue</span></span>

<span data-ttu-id="4ed4c-257">Ha a felhasználó nem hozza meg a döntést a megadott idő alatt, lejár a döntés.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-257">If a user doesn't make the decision in the allotted time, the decision is overdue.</span></span> <span data-ttu-id="4ed4c-258">A lejárt döntést eszkalálhatja, illetve automatikusan egy másik felhasználóhoz rendelheti jóváhagyás céljából.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-258">A decision that is overdue can be escalated, or automatically assigned to another user.</span></span> <span data-ttu-id="4ed4c-259">Kövesse az alábbi lépéseket a döntés eszkalálásához ha lejárt a döntés.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-259">Follow these steps to escalate the decision if it's overdue.</span></span>

1. <span data-ttu-id="4ed4c-260">A bal oldali panelen kattintson az **Eszkalálás** gombra.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-260">In the left pane, click **Escalation**.</span></span>
2. <span data-ttu-id="4ed4c-261">Válassza ki az **Eszkalációs útvonal használata** jelölőnégyzetet egy eszkalációs útvonal létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-261">Select the **Use escalation path** check box to create an escalation path.</span></span> <span data-ttu-id="4ed4c-262">A rendszer automatikusan hozzárendeli a döntést az eszkalációs útvonalon felsorolt felhasználókhoz.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-262">The system automatically assigns the decision to the users who are listed in the escalation path.</span></span> <span data-ttu-id="4ed4c-263">Például az alábbi táblázat egy eszkalációs útvonalat jelent.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-263">For example, the following table represents an escalation path.</span></span>

    | <span data-ttu-id="4ed4c-264">Sorozat</span><span class="sxs-lookup"><span data-stu-id="4ed4c-264">Sequence</span></span> | <span data-ttu-id="4ed4c-265">Eszkalációs útvonal</span><span class="sxs-lookup"><span data-stu-id="4ed4c-265">Escalation path</span></span>            |
    |----------|----------------------------|
    | <span data-ttu-id="4ed4c-266">1</span><span class="sxs-lookup"><span data-stu-id="4ed4c-266">1</span></span>        | <span data-ttu-id="4ed4c-267">Hozzárendelés a következőhöz: Dóra</span><span class="sxs-lookup"><span data-stu-id="4ed4c-267">Assign to: Donna</span></span>           |
    | <span data-ttu-id="4ed4c-268">2</span><span class="sxs-lookup"><span data-stu-id="4ed4c-268">2</span></span>        | <span data-ttu-id="4ed4c-269">Hozzárendelés a következőhöz: Ervin</span><span class="sxs-lookup"><span data-stu-id="4ed4c-269">Assign to: Erin</span></span>            |
    | <span data-ttu-id="4ed4c-270">3</span><span class="sxs-lookup"><span data-stu-id="4ed4c-270">3</span></span>        | <span data-ttu-id="4ed4c-271">Végső művelet: \[Választható 1\]</span><span class="sxs-lookup"><span data-stu-id="4ed4c-271">Final action: \[Choice 1\]</span></span> |

    <span data-ttu-id="4ed4c-272">Ebben a példában a rendszer Dórához rendeli a lejárt döntést.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-272">In this example, the system assigns the overdue decision to Donna.</span></span> <span data-ttu-id="4ed4c-273">Ha Dóra nem hozza meg a döntést a kijelölt időkereten belül, a rendszer Ervinhez rendeli hozzá.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-273">If Donna doesn't make the decision in the allotted time, the system assigns the decision to Erin.</span></span> <span data-ttu-id="4ed4c-274">Ha Ervin nem hozza meg a döntést a kijelölt időkereten belül, a rendszer a **\[Választható 1\]** lehetőséget választja ki döntésként.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-274">If Erin doesn't make the decision in the allotted time, the system selects **\[Choice 1\]** as the decision.</span></span>

3. <span data-ttu-id="4ed4c-275">A felhasználó eszkalációs útvonalhoz történő hozzáadásához, kattintson az **Újabb eszkalációs lépés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-275">To add a user to the escalation path, click **Add escalation**.</span></span> <span data-ttu-id="4ed4c-276">Válasszon ki egy lehetőséget a következő táblázatban, majd ezt követően végezze el a további lépéseket a beállításhoz, mielőtt továbblép a 4. lépésre.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-276">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 4.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="4ed4c-277">Lehetőség</span><span class="sxs-lookup"><span data-stu-id="4ed4c-277">Option</span></span></th>
    <th><span data-ttu-id="4ed4c-278">A döntéshez eszkalált felhasználók</span><span class="sxs-lookup"><span data-stu-id="4ed4c-278">Users that the decision is escalated to</span></span></th>
    <th><span data-ttu-id="4ed4c-279">További lépések</span><span class="sxs-lookup"><span data-stu-id="4ed4c-279">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="4ed4c-280">Hierarchia</span><span class="sxs-lookup"><span data-stu-id="4ed4c-280">Hierarchy</span></span></td>
    <td><span data-ttu-id="4ed4c-281">A meghatározott szervezeti hierarchiában lévő felhasználók.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-281">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="4ed4c-282">Miután kiválasztotta <strong>Hierarchia</strong> lehetőséget a <strong>Hierarchia kiválasztása</strong> lapon, a <strong>Hierarchia típusa</strong> listán, jelölje ki a döntéshez eszkalálni hierarchia típusát.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-282">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to escalate the decision to.</span></span></li>
    <li><span data-ttu-id="4ed4c-283">A rendszernek be kell olvasnia az felhasználó névtartományát a hierarchiából.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-283">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="4ed4c-284">Ezek a nevek a döntéshez eszkalálható felhasználókat jelölik.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-284">These names represent users that the decision can be escalated to.</span></span> <span data-ttu-id="4ed4c-285">Végezze el a következő lépéseket azon felhasználók névtartományának kezdő- és végpontját, amelyet a rendszer beolvas:</span><span class="sxs-lookup"><span data-stu-id="4ed4c-285">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="4ed4c-286">A kezdő pont megadásához válasszon ki egy személyt a <strong>Kezdet</strong> listából.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-286">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="4ed4c-287">A végpont megadásához kattintson a <strong>Feltétel létrehozása</strong> lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-287">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="4ed4c-288">Ezt követően adja meg azt a feltételt, amely meghatározza, hogy a rendszer hol állítsa meg a hierarchiában a nevek beolvasását.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-288">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="4ed4c-289">A <strong>Hierarchia beállításai</strong> lapon adja meg, hogy mely, a tartományban szereplő felhasználókhoz kell a döntést eszkalálni:</span><span class="sxs-lookup"><span data-stu-id="4ed4c-289">On the <strong>Hierarchy options</strong> tab, specify which users in the range the decision should be escalated to:</span></span> <ul>
    <li><span data-ttu-id="4ed4c-290"><strong>Minden lekért felhasználó hozzárendelése</strong> – A tartományban szereplő összes felhasználóhoz eszkalálva van a döntés.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-290"><strong>Assign to all users retrieved</strong> – The decision is escalated to all users in the range.</span></span></li>
    <li><span data-ttu-id="4ed4c-291"><strong>Csak a legutóbb lekért felhasználó hozzárendelése</strong> – Csak a tartományban szereplő utolsó felhasználóhoz van eszkalálva a döntés.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-291"><strong>Assign only to last user retrieved</strong> – The decision is escalated to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="4ed4c-292"><strong>A következő feltételnek megfelelő felhasználók kihagyása</strong> – A döntés nincs eszkalálva a tartomány minden olyan felhasználójához, akik megfelelnek egy adott feltételnek.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-292"><strong>Exclude users with the following condition:</strong> – The decision isn't escalated to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="4ed4c-293">Kattintson a <strong>Feltétel hozzáadása</strong> lehetőségre, ha meg szeretné adni a feltételt.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-293">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="4ed4c-294">Munkafolyamat felhasználója</span><span class="sxs-lookup"><span data-stu-id="4ed4c-294">Workflow user</span></span></td>
    <td><span data-ttu-id="4ed4c-295">Az aktuális munkafolyamatban szereplő felhasználó</span><span class="sxs-lookup"><span data-stu-id="4ed4c-295">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="4ed4c-296">Miután kijelölte <strong>Munkafolyamat-felhasználó</strong> lehetőséget a <strong>Munkafolyamat-felhasználó</strong> lapon a <strong>Munkafolyamat-felhasználó</strong> listából, jelöljön ki egy felhasználót, aki részt vesz a munkafolyamatban.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-296">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="4ed4c-297">Felhasználó</span><span class="sxs-lookup"><span data-stu-id="4ed4c-297">User</span></span></td>
    <td><span data-ttu-id="4ed4c-298">Meghatározott felhasználók</span><span class="sxs-lookup"><span data-stu-id="4ed4c-298">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="4ed4c-299">Miután kijelölte <strong>Felhasználó</strong> lehetőséget, kattintson a <strong>Felhasználó</strong> fülre.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-299">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="4ed4c-300">A <strong>Rendelkezésre álló felhasználók</strong> listája az összes felhasználót tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-300">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="4ed4c-301">Válassza ki a döntéshez eszkalálni kívánt felhasználókat, majd ezt követően helyezze át ezeket a felhasználókat a <strong>Kijelölt felhasználók</strong> listájára.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-301">Select the users to escalate the decision to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. <span data-ttu-id="4ed4c-302">A **Határidő** lapon az **Időtartam** mezőben adja meg, hogy mennyi idő kell a felhasználónak a döntéshozatalhoz.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-302">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to make the decision.</span></span> <span data-ttu-id="4ed4c-303">Válasszon a következő lehetőségek közül:</span><span class="sxs-lookup"><span data-stu-id="4ed4c-303">Select one of the following options:</span></span>

    - <span data-ttu-id="4ed4c-304">**Órák** – Adja meg azon órák számát, amely alatt a felhasználónak meg kell hoznia a döntést.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-304">**Hours** – Enter the number of hours that the user has to make the decision.</span></span> <span data-ttu-id="4ed4c-305">Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-305">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="4ed4c-306">**Napok** – Adja meg azon napok számát, amely alatt a felhasználónak meg kell hoznia a döntést.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-306">**Days** – Enter the number of days that the user has to make the decision.</span></span> <span data-ttu-id="4ed4c-307">Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-307">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="4ed4c-308">**Hetek** – Adja meg azon hetek számát, amely alatt a felhasználónak meg kell hoznia a döntést.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-308">**Weeks** – Enter the number of weeks that the user has to make the decision.</span></span>
    - <span data-ttu-id="4ed4c-309">**Hónapok** – Válassza ki, hogy melyik hét mely napjáig kell a felhasználónak meghoznia a döntést.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-309">**Months** – Select the day and week that the user must make the decision by.</span></span> <span data-ttu-id="4ed4c-310">Kérheti például, hogy a felhasználó a hónap harmadik hetének péntekéig hozza meg a döntést.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-310">For example, you might want the user to make the decision by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="4ed4c-311">**Évek** – Válassza ki, hogy melyik hónap mely hetéig kell a felhasználónak meghoznia a döntést.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-311">**Years** – Select the day, week, and month that the user must make the decision by.</span></span> <span data-ttu-id="4ed4c-312">Kérheti például, hogy a felhasználó december harmadik hetének péntekéig hozza meg a döntést.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-312">For example, you might want the user to make the decision by Friday of the third week of December.</span></span>

5. <span data-ttu-id="4ed4c-313">Ismételje meg a 3 – 4. lépést minden egyes olyan felhasználóra vonatkozóan, akiket hozzá kell adni az eszkalációs útvonalhoz.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-313">Repeat steps 3 through 4 for each user that should be added to the escalation path.</span></span> <span data-ttu-id="4ed4c-314">A felhasználók sorrendje módosítható.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-314">You can change the order of the users.</span></span>
6. <span data-ttu-id="4ed4c-315">Ha az eszkalációs útvonalban szereplő felhasználók nem hozzák meg a döntést a megadott időn belül, a rendszer hozza meg a döntést.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-315">If the users in the escalation path don't make the decision in the allotted time, the system makes the decision.</span></span> <span data-ttu-id="4ed4c-316">A rendszer által kijelölt beállítás meghatározásához, válassza ki a **Művelet** sort, majd a **Művelet lezárása** fülön válasszon ki egy beállítást.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-316">To specify the option that the system selects, select the **Action** row, and then, on the **End action** tab, select an option.</span></span>

## <a name="set-a-time-limit"></a><span data-ttu-id="4ed4c-317">Időkorlát beállítása</span><span class="sxs-lookup"><span data-stu-id="4ed4c-317">Set a time limit</span></span>

<span data-ttu-id="4ed4c-318">Kövesse az alábbi lépéseket, ha a döntést egy megadott időn belül kell meghozni.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-318">Follow these steps if the decision must be made in a specific time.</span></span>

> [!NOTE]
> <span data-ttu-id="4ed4c-319">Az eljárásban kijelölt beállítások felülbírálják az oldal **Hozzárendelés** és **Eszkaláció** területén kijelölt beállításokat.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-319">The options that you select in this procedure override the options that you selected in the **Assignment** and **Escalation** areas of the page.</span></span>

1. <span data-ttu-id="4ed4c-320">A bal oldali panelen kattintson az **Speciális beállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-320">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="4ed4c-321">Válassza ki a **A munkafolyamat-elem időkorlátjának beállítása** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-321">Select the **Set a time limit for the workflow element** check box.</span></span>
3. <span data-ttu-id="4ed4c-322">Az **Időtartam** mezőbe adja meg, hogy mikor kell meghozni a döntést.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-322">In the **Duration** field, specify when the decision must be made.</span></span> <span data-ttu-id="4ed4c-323">Válasszon a következő lehetőségek közül:</span><span class="sxs-lookup"><span data-stu-id="4ed4c-323">Select one of the following options:</span></span>

    - <span data-ttu-id="4ed4c-324">**Órák** – Adja meg az órák számát.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-324">**Hours** – Enter the number of hours.</span></span> <span data-ttu-id="4ed4c-325">Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-325">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="4ed4c-326">**Napok** – Adja meg a napok számát.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-326">**Days** – Enter the number of days.</span></span> <span data-ttu-id="4ed4c-327">Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-327">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="4ed4c-328">**Hetek** – Adja meg a hetek számát.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-328">**Weeks** – Enter the number of weeks.</span></span>
    - <span data-ttu-id="4ed4c-329">**Hónapok** – Válassza ki, hogy melyik hét mely napjáig kell a döntést meghozni.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-329">**Months** – Select the day and week that the decision must be made by.</span></span> <span data-ttu-id="4ed4c-330">Kérheti például, hogy a döntést a hónap harmadik hetének péntekéig kell meghozni.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-330">For example, you might want the decision to be made by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="4ed4c-331">**Évek** – Válassza ki, hogy mely hónap, mely hét, mely napjáig kell a döntést meghozni.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-331">**Years** – Select the day, week, and month that the decision must be made by.</span></span> <span data-ttu-id="4ed4c-332">Kérheti például, hogy a döntést december harmadik hetének péntekéig kell meghozni.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-332">For example, you might want the decision to be made by Friday of the third week of December.</span></span>

4. <span data-ttu-id="4ed4c-333">Ha lejár az időkorlát, a rendszer hozza meg a döntést.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-333">If the time limit is exceeded, the system makes the decision.</span></span> <span data-ttu-id="4ed4c-334">Válassza ki a **Művelet** listából, hogy milyen beállítást kell a rendszernek kiválasztania.</span><span class="sxs-lookup"><span data-stu-id="4ed4c-334">In the **Action** list, select the option that the system should select.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]