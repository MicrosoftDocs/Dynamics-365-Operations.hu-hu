---
title: Munkafolyamat-tulajdonságok konfigurálása
description: Ez a témakör bemutatja, hogyan kell konfigurálni a munkafolyamat különböző tulajdonságait.
author: ChrisGarty
manager: AnnBe
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 196083
ms.assetid: 192b7a98-7d04-4c7a-a986-29d797a8a837
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4d01a784b0f0cbfce30f1197278f015b236ef0b8
ms.sourcegitcommit: e55efd2f62bf60f678108c09ad4701a76b20cc68
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/17/2020
ms.locfileid: "3698144"
---
# <a name="configure-workflow-properties"></a><span data-ttu-id="1409f-103">Munkafolyamat-tulajdonságok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="1409f-103">Configure workflow properties</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1409f-104">Ez a témakör bemutatja, hogyan kell konfigurálni a munkafolyamat különböző tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="1409f-104">This topic explains how to configure the various properties of a workflow.</span></span>

<span data-ttu-id="1409f-105">A munkafolyamat tulajdonságainak beállítására, a munkafolyamat-szerkesztő megnyitása a munkafolyamat.</span><span class="sxs-lookup"><span data-stu-id="1409f-105">To configure the properties of a workflow, open the workflow in the workflow editor.</span></span> <span data-ttu-id="1409f-106">Kattintson a munkafolyamat-szerkesztő vásznára, majd ezt követően kattintson a **Tulajdonságok** megnyitásához a **Tulajdonságok** képernyőn.</span><span class="sxs-lookup"><span data-stu-id="1409f-106">Click the canvas of the workflow editor, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="1409f-107">A következő eljárások segítségével beállíthatja a munkafolyamat különféle tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="1409f-107">You can then use the following procedures to configure the various properties of the workflow.</span></span>

## <a name="name-the-workflow"></a><span data-ttu-id="1409f-108">A munkafolyamat elnevezése</span><span class="sxs-lookup"><span data-stu-id="1409f-108">Name the workflow</span></span>

<span data-ttu-id="1409f-109">A következő lépések segítségével elnevezheti a munkafolyamatot.</span><span class="sxs-lookup"><span data-stu-id="1409f-109">Follow these steps to enter a name for the workflow.</span></span>

1. <span data-ttu-id="1409f-110">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="1409f-110">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="1409f-111">A **Név** mezőbe írja be a munkafolyamat egyedi nevét.</span><span class="sxs-lookup"><span data-stu-id="1409f-111">In the **Name** field, enter a unique name for the workflow.</span></span> <span data-ttu-id="1409f-112">Például, ha létrehoz egy beszerzési igénylési munkafolyamatot minden működési országhoz/régióhoz, a beszerzési igénylés munkafolyamatának a **Beszerzési igénylések Dánia** vagy **Beszerzési igénylések Spanyolország** nevet adhatja.</span><span class="sxs-lookup"><span data-stu-id="1409f-112">For example, if you create a purchase requisition workflow for each country/region that you operate in, you can name the purchase requisition workflow **Purchase Requisitions Denmark** or **Purchase Requisitions Spain**.</span></span>

## <a name="specify-the-workflow-owner"></a><span data-ttu-id="1409f-113">A munkafolyamat tulajdonosának meghatározása</span><span class="sxs-lookup"><span data-stu-id="1409f-113">Specify the workflow owner</span></span>

<span data-ttu-id="1409f-114">A munkafolyamat tulajdonosa az a személy, aki az adott munkafolyamatot kezeli és karbantartja.</span><span class="sxs-lookup"><span data-stu-id="1409f-114">The workflow owner is the person who manages and maintains the workflow.</span></span> <span data-ttu-id="1409f-115">A következő lépések segítségével megadhatja a munkafolyamat tulajdonosát.</span><span class="sxs-lookup"><span data-stu-id="1409f-115">Follow these steps to specify the workflow owner.</span></span>

1. <span data-ttu-id="1409f-116">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="1409f-116">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="1409f-117">Válassza ki a munkafolyamatot kezelő személy nevét a **Tulajdonos** listából.</span><span class="sxs-lookup"><span data-stu-id="1409f-117">In the **Owner** list, select the name of the person who will manage the workflow.</span></span>

## <a name="select-an-email-template"></a><span data-ttu-id="1409f-118">E-mail sablon kiválasztása</span><span class="sxs-lookup"><span data-stu-id="1409f-118">Select an email template</span></span>

<span data-ttu-id="1409f-119">Végezze el az alábbi lépéseket azon e-mail sablon kiválasztásához, amelyet a munkafolyamattal kapcsolatos értesítések létrehozására használ.</span><span class="sxs-lookup"><span data-stu-id="1409f-119">Follow these steps to select the email template that is used to generate notification messages about the workflow.</span></span>

1. <span data-ttu-id="1409f-120">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="1409f-120">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="1409f-121">Válasszak ki a sablont az **E-mail sablon munkafolyamat-értesítésekhez** listáján.</span><span class="sxs-lookup"><span data-stu-id="1409f-121">In the **Email template for workflow notifications** list, select the template.</span></span>

## <a name="enter-instructions-for-users"></a><span data-ttu-id="1409f-122">Utasítások megadása felhasználók számára</span><span class="sxs-lookup"><span data-stu-id="1409f-122">Enter instructions for users</span></span>

<span data-ttu-id="1409f-123">Utasításokat adhat meg azon felhasználók számára, akik a dokumentumokat feldolgozásra és jóváhagyásra továbbítják.</span><span class="sxs-lookup"><span data-stu-id="1409f-123">You can provide instructions to users who submit documents for processing and approval.</span></span> <span data-ttu-id="1409f-124">Ezeket a felhasználókat *létrehozók* néven is nevezik.</span><span class="sxs-lookup"><span data-stu-id="1409f-124">These users are also referred to as *originators*.</span></span> <span data-ttu-id="1409f-125">Például, ha Ön egy beszerzési igénylési munkafolyamatot hoz létre, akkor utasításokat ad meg.</span><span class="sxs-lookup"><span data-stu-id="1409f-125">For example, you're creating a purchase requisition workflow, and you enter instructions.</span></span> <span data-ttu-id="1409f-126">Ezeket az utasításokat azok a felhasználók tekinthetik meg, akik a **Beszerzési igénylések** képernyőn beszerzési igényléseket adnak meg.</span><span class="sxs-lookup"><span data-stu-id="1409f-126">Those instructions can then be viewed by users who enter purchase requisitions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="1409f-127">Az útmutatás megtekintéséhez, a létrehozó a munkafolyamat üzenetsorán található ikonra kattint.</span><span class="sxs-lookup"><span data-stu-id="1409f-127">To view instructions, the originator clicks the icon in the workflow message bar.</span></span> <span data-ttu-id="1409f-128">A következő lépések segítségével utasításokat adhat meg a felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="1409f-128">Follow these steps to enter instructions for users.</span></span>

1. <span data-ttu-id="1409f-129">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="1409f-129">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="1409f-130">Írja be az utasításokat a **Küldési utasítások** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1409f-130">In the **Submission instructions** field, enter the instructions.</span></span>
3. <span data-ttu-id="1409f-131">Az utasítások testreszabásához, helyőrzőket illeszthet be.</span><span class="sxs-lookup"><span data-stu-id="1409f-131">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="1409f-132">A helyőrzők helyére a megfelelő adatok kerülnek, amikor az utasítások megjelennek a felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="1409f-132">Placeholders are replaced with the appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="1409f-133">Végezze el a következő lépéseket a helyőrzők beillesztéséhez:</span><span class="sxs-lookup"><span data-stu-id="1409f-133">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="1409f-134">Kattintson a **Küldési utasítások** mezőre a helyőrző helyének meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="1409f-134">Click in the **Submission instructions** field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="1409f-135">Kattintson a **Helyőrző beszúrása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1409f-135">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="1409f-136">A megjelenő listában válassza ki a beilleszteni kívánt helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="1409f-136">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="1409f-137">Kattintson a **Beszúrás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1409f-137">Click **Insert**.</span></span>

4. <span data-ttu-id="1409f-138">Az utasítások fordításainak hozzáadásához, végezze el a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="1409f-138">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="1409f-139">Kattintson a **Fordítások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1409f-139">Click **Translations**.</span></span>
    2. <span data-ttu-id="1409f-140">A megjelenő oldalon kattintson a **Hozzáadás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1409f-140">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="1409f-141">A megjelenő listában válassza ki a szöveg nyelvét, amelyen írni fogja azt.</span><span class="sxs-lookup"><span data-stu-id="1409f-141">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="1409f-142">Írja be a szöveget a **Lefordított szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1409f-142">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="1409f-143">A szöveg testreszabásához, illesszen be helyőrzőket.</span><span class="sxs-lookup"><span data-stu-id="1409f-143">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="1409f-144">A helyőrző megadásával kapcsolatos további tudnivalókért lásd a 3. lépést.</span><span class="sxs-lookup"><span data-stu-id="1409f-144">For instructions about how to enter a placeholder, see step 3.</span></span>
    6. <span data-ttu-id="1409f-145">Kattintson a **Bezárás** gombra.</span><span class="sxs-lookup"><span data-stu-id="1409f-145">Click **Close**.</span></span>

## <a name="specify-when-this-workflow-is-used-through-activation-conditions"></a><span data-ttu-id="1409f-146">Adja meg, hogy mikor használja ezt a munkafolyamatot aktiválási feltételeken keresztül</span><span class="sxs-lookup"><span data-stu-id="1409f-146">Specify when this workflow is used through activation conditions</span></span>

<span data-ttu-id="1409f-147">Több, ugyanazon a munkafolyamat-típuson alapuló munkafolyamatot is megadhat.</span><span class="sxs-lookup"><span data-stu-id="1409f-147">You can create multiple workflows that are based on the same workflow type.</span></span> <span data-ttu-id="1409f-148">Ha több olyan munkafolyamata van, amelyeknek alapja ugyanaz a típus, az aktiválási feltételekkel meg kell adnia, hogy mikor szeretné a munkafolyamatot használni.</span><span class="sxs-lookup"><span data-stu-id="1409f-148">When you have multiple workflows that are based on the same type, you must specify when each workflow is used using activation conditions.</span></span> <span data-ttu-id="1409f-149">Ha az aktiválási feltételek nem teljesülnek, akkor a rendszer az alapértelmezett munkafolyamatot használja.</span><span class="sxs-lookup"><span data-stu-id="1409f-149">If activation conditions are not met, then the default workflow is used.</span></span> <span data-ttu-id="1409f-150">Hasonlóképpen, ha egy munkafolyamat-típushoz csak egy munkafolyamat-konfiguráció van definiálva, akkor a munkafolyamat-konfiguráció az aktiválási feltételektől függetlenül használva lesz.</span><span class="sxs-lookup"><span data-stu-id="1409f-150">Similarly, if there is only one workflow configuration defined for a workflow type, then that workflow configuration will be used regardless of the activation conditions.</span></span>

<span data-ttu-id="1409f-151">Például, ha létrehoz egy beszerzési igénylési munkafolyamatot minden működési országhoz/régióhoz, például a beszerzési igénylés Beszerzési igénylések Dánia vagy Beszerzési igénylések Spanyolország munkafolyamatot a következő feltételekkel:</span><span class="sxs-lookup"><span data-stu-id="1409f-151">For example, you can create a purchase requisition workflow for each country/region that you operate in, such as Purchase Requisitions Denmark and Purchase Requisitions Spain, with the following conditions:</span></span>

- <span data-ttu-id="1409f-152">A Beszerzési igénylés Dánia akkor használandó, amikor: ország/régió = DK.</span><span class="sxs-lookup"><span data-stu-id="1409f-152">Purchase Requisitions Denmark is used when: country/region = DK</span></span>
- <span data-ttu-id="1409f-153">A Beszerzési igénylés Spanyolország akkor használandó, amikor: az ország/régió = ES.</span><span class="sxs-lookup"><span data-stu-id="1409f-153">Purchase Requisitions Spain is used when: country/region = ES</span></span>

<span data-ttu-id="1409f-154">A következő lépések segítségével megadhatja, hogy mikor szeretné használni az éppen konfigurált munkafolyamatot.</span><span class="sxs-lookup"><span data-stu-id="1409f-154">Follow these steps to specify when the workflow that you're configuring is used.</span></span>

1. <span data-ttu-id="1409f-155">A bal oldali panelen kattintson az **Aktiválás** gombra.</span><span class="sxs-lookup"><span data-stu-id="1409f-155">In the left pane, click **Activation**.</span></span>
2. <span data-ttu-id="1409f-156">Válassza ki a **A munkafolyamat futtatási feltételeinek beállítása** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="1409f-156">Select the **Set the conditions for running this workflow** check box.</span></span>
3. <span data-ttu-id="1409f-157">Kattintson a **Feltétel hozzáadása** parancsra.</span><span class="sxs-lookup"><span data-stu-id="1409f-157">Click **Add condition**.</span></span>
4. <span data-ttu-id="1409f-158">Feltétel megadása.</span><span class="sxs-lookup"><span data-stu-id="1409f-158">Enter a condition.</span></span>
5. <span data-ttu-id="1409f-159">Adja meg a további szükséges feltételeket.</span><span class="sxs-lookup"><span data-stu-id="1409f-159">Enter any additional conditions that are required.</span></span>
6. <span data-ttu-id="1409f-160">Futtassa végig a munkafolyamaton keresztül néhány célrekord használatával, és ellenőrizheti, hogy a feltétel helyesen szerepel-e, és ki vannak-e zárva a rekordok.</span><span class="sxs-lookup"><span data-stu-id="1409f-160">Run through the workflow with some target records to verify that the condition correctly includes and excludes records.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="1409f-161">Az értesítések küldési idejének meghatározása</span><span class="sxs-lookup"><span data-stu-id="1409f-161">Specify when notifications are sent</span></span>

<span data-ttu-id="1409f-162">Amikor elküldenek egy dokumentumot feldolgozásra, létrejön egy munkafolyamat-példány.</span><span class="sxs-lookup"><span data-stu-id="1409f-162">When a document is submitted for processing, a workflow instance is created.</span></span> <span data-ttu-id="1409f-163">Értesítést a felhasználóknak olyankor küldhet, amikor a munkafolyamat-példányok (melyeknek alapja a munkafolyamat) elkezdődtek, elkészültek, megszakították őket, vagy hiba miatt leálltak.</span><span class="sxs-lookup"><span data-stu-id="1409f-163">You can send notifications to users when workflow instances that are based on the workflow are started, completed, terminated, or stopped because of an error.</span></span> <span data-ttu-id="1409f-164">A következő lépések segítségével megadhatja, hogy mikor küldjön a rendszer értesítéseket.</span><span class="sxs-lookup"><span data-stu-id="1409f-164">Follow these steps to specify when notifications are sent.</span></span>

1. <span data-ttu-id="1409f-165">A bal oldali panelen kattintson az **Értesítések** gombra.</span><span class="sxs-lookup"><span data-stu-id="1409f-165">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="1409f-166">Jelölje be a jelölőnégyzetet minden olyan eseményhez, amely az előidézi értesítéseket:</span><span class="sxs-lookup"><span data-stu-id="1409f-166">Select the check box for each event that should trigger notifications:</span></span>

    - <span data-ttu-id="1409f-167">**Elindítva** – Értesítések küldése, ha a rendszer elkezdi a munkafolyamat-példányt.</span><span class="sxs-lookup"><span data-stu-id="1409f-167">**Started** – Send notifications when a workflow instance is started.</span></span>
    - <span data-ttu-id="1409f-168">**Leállítva** – Értesítések küldése, ha hiba miatt leáll a munkafolyamat-példány.</span><span class="sxs-lookup"><span data-stu-id="1409f-168">**Stopped** – Send notifications when a workflow instance is stopped because of an error.</span></span>
    - <span data-ttu-id="1409f-169">**Befejeződött** – Értesítések küldése, ha befejeződött a munkafolyamat-példány.</span><span class="sxs-lookup"><span data-stu-id="1409f-169">**Completed** – Send notifications when a workflow instance is completed.</span></span>
    - <span data-ttu-id="1409f-170">**Helyreállíthatatlan** – Értesítések küldése, ha helyreállíthatatlan hiba miatt leáll a munkafolyamat-példány.</span><span class="sxs-lookup"><span data-stu-id="1409f-170">**Unrecoverable** – Send notifications when a workflow instance is stopped because of an unrecoverable error.</span></span>
    - <span data-ttu-id="1409f-171">**Megszakítva** – Értesítések küldése, ha megszakították a munkafolyamat-példányt.</span><span class="sxs-lookup"><span data-stu-id="1409f-171">**Terminated** – Send notifications when a workflow instance is terminated.</span></span>

3. <span data-ttu-id="1409f-172">Jelölje ki a sort a 2. lépésben választott eseményhez.</span><span class="sxs-lookup"><span data-stu-id="1409f-172">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="1409f-173">Az **Értesítési szöveg** lapon, írja be az értesítés szövegét.</span><span class="sxs-lookup"><span data-stu-id="1409f-173">On the **Notification text** tab, enter the text of the notification.</span></span>
5. <span data-ttu-id="1409f-174">A szöveg testreszabásához, illesszen be helyőrzőket.</span><span class="sxs-lookup"><span data-stu-id="1409f-174">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="1409f-175">A helyőrzők helyére a megfelelő adatok kerülnek, amikor a szöveg megjelenik a felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="1409f-175">Placeholders are replaced with the appropriate data when the text is shown to users.</span></span> <span data-ttu-id="1409f-176">Végezze el a következő lépéseket a helyőrzők beillesztéséhez:</span><span class="sxs-lookup"><span data-stu-id="1409f-176">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="1409f-177">Kattintson a mezőben oda, ahol meg szeretné jeleníteni a helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="1409f-177">Click in the field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="1409f-178">Kattintson a **Helyőrző beszúrása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1409f-178">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="1409f-179">A megjelenő listában válassza ki a beilleszteni kívánt helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="1409f-179">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="1409f-180">Kattintson a **Beszúrás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1409f-180">Click **Insert**.</span></span>
    5. <span data-ttu-id="1409f-181">Egy gyakori **Értesítés szövege** helyőrző, melyet létrehoznak: „Utolsó jegyzetek: %Workflow.Last note%”, melly az előző lépés megjegyzéseit jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="1409f-181">A common **Notification text** placeholder to include is "Last Notes: %Workflow.Last note%", which displays any comments from the previous step.</span></span>

6. <span data-ttu-id="1409f-182">A szöveg fordításainak hozzáadásához, végezze el a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="1409f-182">To add translations of the text, follow these steps:</span></span>

    1. <span data-ttu-id="1409f-183">Kattintson a **Fordítások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1409f-183">Click **Translations**.</span></span>
    2. <span data-ttu-id="1409f-184">A megjelenő oldalon kattintson a **Hozzáadás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1409f-184">On the page that appears, Click **Add**.</span></span>
    3. <span data-ttu-id="1409f-185">A megjelenő listában válassza ki a szöveg nyelvét, amelyen írni fogja azt.</span><span class="sxs-lookup"><span data-stu-id="1409f-185">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="1409f-186">Írja be a szöveget a **Lefordított szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1409f-186">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="1409f-187">A szöveg testreszabásához, illesszen be helyőrzőket.</span><span class="sxs-lookup"><span data-stu-id="1409f-187">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="1409f-188">A helyőrző megadásával kapcsolatos további tudnivalókért lásd a 5. lépést.</span><span class="sxs-lookup"><span data-stu-id="1409f-188">For instructions about how to enter a placeholder, see step 5.</span></span>
    6. <span data-ttu-id="1409f-189">Kattintson a **Bezárás** gombra.</span><span class="sxs-lookup"><span data-stu-id="1409f-189">Click **Close**.</span></span>

7. <span data-ttu-id="1409f-190">A **Címzett** lapon, a következő beállításokkal adja meg, határozza meg, hogy kik kaphatnak értesítéseket.</span><span class="sxs-lookup"><span data-stu-id="1409f-190">On the **Recipient** tab, use the following options to specify who should receive the notifications.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="1409f-191">Lehetőség</span><span class="sxs-lookup"><span data-stu-id="1409f-191">Option</span></span></th>
    <th><span data-ttu-id="1409f-192">Ezeknek a felhasználóknak küldött értesítések</span><span class="sxs-lookup"><span data-stu-id="1409f-192">Notifications are sent to these users</span></span></th>
    <th><span data-ttu-id="1409f-193">Az értesítések küldéséhez, végezze el a következő lépéseket</span><span class="sxs-lookup"><span data-stu-id="1409f-193">To send notifications, follow these steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="1409f-194">Résztvevő</span><span class="sxs-lookup"><span data-stu-id="1409f-194">Participant</span></span></td>
    <td><span data-ttu-id="1409f-195">Egy adott csoporthoz vagy szerephez hozzárendelt felhasználók</span><span class="sxs-lookup"><span data-stu-id="1409f-195">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="1409f-196">A <strong>Címzett</strong> lapon, kattintson a <strong>Résztvevő</strong> lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1409f-196">On the <strong>Recipient</strong> tab, click <strong>Participant</strong>.</span></span></li>
    <li><span data-ttu-id="1409f-197">A <strong>Szerepköralapú</strong> lapon, a <strong>Résztvevő típusa</strong> listán, válassza ki a csoport vagy a szerep típusát, amely számára értesítéseket kíván küldeni.</span><span class="sxs-lookup"><span data-stu-id="1409f-197">On the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="1409f-198">A <strong>Résztvevő</strong> listáján jelölje ki a csoportot vagy szerepkört, amely számára értesítést kíván küldeni.</span><span class="sxs-lookup"><span data-stu-id="1409f-198">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="1409f-199">Munkafolyamat felhasználója</span><span class="sxs-lookup"><span data-stu-id="1409f-199">Workflow user</span></span></td>
    <td><span data-ttu-id="1409f-200">A munkafolyamatban résztvevő felhasználók</span><span class="sxs-lookup"><span data-stu-id="1409f-200">Users who are participants in this workflow</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="1409f-201">A <strong>Címzett</strong> lapon, kattintson a <strong>Munkafolyamat felhasználója</strong> lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1409f-201">On the <strong>Recipient</strong> tab, click <strong>Workflow user</strong>.</span></span></li>
    <li><span data-ttu-id="1409f-202">A <strong>Munkafolyamat-felhasználó</strong> lapon található <strong>Munkafolyamat-felhasználó</strong> listából, jelöljön ki a munkafolyamat egy résztevevőjét.</span><span class="sxs-lookup"><span data-stu-id="1409f-202">On the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a participant in this workflow.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="1409f-203">Felhasználó</span><span class="sxs-lookup"><span data-stu-id="1409f-203">User</span></span></td>
    <td><span data-ttu-id="1409f-204">Meghatározott felhasználók</span><span class="sxs-lookup"><span data-stu-id="1409f-204">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="1409f-205">A <strong>Címzett</strong> lapon, kattintson a <strong>Felhasználó</strong> lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1409f-205">On the <strong>Recipient</strong> tab, click <strong>User</strong>.</span></span></li>
    <li><span data-ttu-id="1409f-206">A <strong>Felhasználók</strong> lapon található <strong>Rendelkezésre álló felhasználók</strong> lista az összes felhasználót tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="1409f-206">On the <strong>User</strong> tab, the <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="1409f-207">Válassza ki azokat a felhasználókat, akik számára értesítéseket kíván küldeni, majd helyezze át ezeket a felhasználókat a <strong>Kijelölt felhasználók</strong> listájára.</span><span class="sxs-lookup"><span data-stu-id="1409f-207">Select the users to send notifications to, and move those users into the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="1409f-208">Ismételje meg a 3 – 7. lépést a 2. lépésben kiválasztott összes eseményhez.</span><span class="sxs-lookup"><span data-stu-id="1409f-208">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a><span data-ttu-id="1409f-209">Írjon megjegyzéseket a munkafolyamathoz az elvégzett változtatásokkal kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="1409f-209">Enter comments about the changes that you made to the workflow</span></span>

<span data-ttu-id="1409f-210">Ha megjegyzéseket szeretne fűzni a munkafolyamathoz az elvégzett változtatásokkal kapcsolatban, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1409f-210">To enter comments about the changes that you made to the workflow, follow these steps.</span></span>

1. <span data-ttu-id="1409f-211">A bal oldali panelen kattintson a **Megjegyzések** gombra.</span><span class="sxs-lookup"><span data-stu-id="1409f-211">In the left pane, click **Notes**.</span></span>
2. <span data-ttu-id="1409f-212">Írja be a megjegyzéseit az **Adja meg a munkafolyamatra vonatkozó megjegyzéseket** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1409f-212">In the **Enter comments about the workflow** field, enter your comments.</span></span>
3. <span data-ttu-id="1409f-213">Megjegyzések áttekintése.</span><span class="sxs-lookup"><span data-stu-id="1409f-213">Review your comments.</span></span> <span data-ttu-id="1409f-214">Miután hozzáadta a megjegyzéseket, nem módosíthatja azokat.</span><span class="sxs-lookup"><span data-stu-id="1409f-214">After you add comments, you can't modify them.</span></span>
4. <span data-ttu-id="1409f-215">Kattintson a **Hozzáadás** gombra a megjegyzések az **Előző megjegyzések** területre történő hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="1409f-215">Click **Add** to add your comments to the **Comment history** area.</span></span>
