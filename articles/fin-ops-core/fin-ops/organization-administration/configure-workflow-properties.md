---
title: Munkafolyamat-tulajdonságok konfigurálása
description: Ez a témakör bemutatja, hogyan kell konfigurálni a munkafolyamat különböző tulajdonságait.
author: sericks007
manager: AnnBe
ms.date: 07/17/2018
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
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 76d44c472989a73d71c2edd19f1187ecd09827ae
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190120"
---
# <a name="configure-workflow-properties"></a><span data-ttu-id="c5fd5-103">Munkafolyamat-tulajdonságok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c5fd5-103">Configure workflow properties</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c5fd5-104">Ez a témakör bemutatja, hogyan kell konfigurálni a munkafolyamat különböző tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-104">This topic explains how to configure the various properties of a workflow.</span></span>

<span data-ttu-id="c5fd5-105">A munkafolyamat tulajdonságainak beállítására, a munkafolyamat-szerkesztő megnyitása a munkafolyamat.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-105">To configure the properties of a workflow, open the workflow in the workflow editor.</span></span> <span data-ttu-id="c5fd5-106">Kattintson a munkafolyamat-szerkesztő vásznára, majd ezt követően kattintson a **Tulajdonságok** megnyitásához a **Tulajdonságok** képernyőn.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-106">Click the canvas of the workflow editor, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="c5fd5-107">A következő eljárások segítségével beállíthatja a munkafolyamat különféle tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-107">You can then use the following procedures to configure the various properties of the workflow.</span></span>

## <a name="name-the-workflow"></a><span data-ttu-id="c5fd5-108">A munkafolyamat elnevezése</span><span class="sxs-lookup"><span data-stu-id="c5fd5-108">Name the workflow</span></span>

<span data-ttu-id="c5fd5-109">A következő lépések segítségével elnevezheti a munkafolyamatot.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-109">Follow these steps to enter a name for the workflow.</span></span>

1. <span data-ttu-id="c5fd5-110">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-110">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="c5fd5-111">A **Név** mezőbe írja be a munkafolyamat egyedi nevét.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-111">In the **Name** field, enter a unique name for the workflow.</span></span> <span data-ttu-id="c5fd5-112">Például, ha létrehoz egy beszerzési igénylési munkafolyamatot minden működési országhoz/régióhoz, a beszerzési igénylés munkafolyamatának a **Beszerzési igénylések Dánia** vagy **Beszerzési igénylések Spanyolország** nevet adhatja.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-112">For example, if you create a purchase requisition workflow for each country/region that you operate in, you can name the purchase requisition workflow **Purchase Requisitions Denmark** or **Purchase Requisitions Spain**.</span></span>

## <a name="specify-the-workflow-owner"></a><span data-ttu-id="c5fd5-113">A munkafolyamat tulajdonosának meghatározása</span><span class="sxs-lookup"><span data-stu-id="c5fd5-113">Specify the workflow owner</span></span>

<span data-ttu-id="c5fd5-114">A munkafolyamat tulajdonosa az a személy, aki az adott munkafolyamatot kezeli és karbantartja.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-114">The workflow owner is the person who manages and maintains the workflow.</span></span> <span data-ttu-id="c5fd5-115">A következő lépések segítségével megadhatja a munkafolyamat tulajdonosát.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-115">Follow these steps to specify the workflow owner.</span></span>

1. <span data-ttu-id="c5fd5-116">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-116">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="c5fd5-117">Válassza ki a munkafolyamatot kezelő személy nevét a **Tulajdonos** listából.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-117">In the **Owner** list, select the name of the person who will manage the workflow.</span></span>

## <a name="select-an-email-template"></a><span data-ttu-id="c5fd5-118">E-mail sablon kiválasztása</span><span class="sxs-lookup"><span data-stu-id="c5fd5-118">Select an email template</span></span>

<span data-ttu-id="c5fd5-119">Végezze el az alábbi lépéseket azon e-mail sablon kiválasztásához, amelyet a munkafolyamattal kapcsolatos értesítések létrehozására használ.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-119">Follow these steps to select the email template that is used to generate notification messages about the workflow.</span></span>

1. <span data-ttu-id="c5fd5-120">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-120">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="c5fd5-121">Válasszak ki a sablont az **E-mail sablon munkafolyamat-értesítésekhez** listáján.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-121">In the **Email template for workflow notifications** list, select the template.</span></span>

## <a name="enter-instructions-for-users"></a><span data-ttu-id="c5fd5-122">Utasítások megadása felhasználók számára</span><span class="sxs-lookup"><span data-stu-id="c5fd5-122">Enter instructions for users</span></span>

<span data-ttu-id="c5fd5-123">Utasításokat adhat meg azon felhasználók számára, akik a dokumentumokat feldolgozásra és jóváhagyásra továbbítják.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-123">You can provide instructions to users who submit documents for processing and approval.</span></span> <span data-ttu-id="c5fd5-124">Ezeket a felhasználókat *létrehozók* néven is nevezik.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-124">These users are also referred to as *originators*.</span></span> <span data-ttu-id="c5fd5-125">Például, ha Ön egy beszerzési igénylési munkafolyamatot hoz létre, akkor utasításokat ad meg.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-125">For example, you're creating a purchase requisition workflow, and you enter instructions.</span></span> <span data-ttu-id="c5fd5-126">Ezeket az utasításokat azok a felhasználók tekinthetik meg, akik a **Beszerzési igénylések** képernyőn beszerzési igényléseket adnak meg.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-126">Those instructions can then be viewed by users who enter purchase requisitions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="c5fd5-127">Az útmutatás megtekintéséhez, a létrehozó a munkafolyamat üzenetsorán található ikonra kattint.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-127">To view instructions, the originator clicks the icon in the workflow message bar.</span></span> <span data-ttu-id="c5fd5-128">A következő lépések segítségével utasításokat adhat meg a felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-128">Follow these steps to enter instructions for users.</span></span>

1. <span data-ttu-id="c5fd5-129">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-129">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="c5fd5-130">Írja be az utasításokat a **Küldési utasítások** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-130">In the **Submission instructions** field, enter the instructions.</span></span>
3. <span data-ttu-id="c5fd5-131">Az utasítások testreszabásához, helyőrzőket illeszthet be.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-131">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="c5fd5-132">A helyőrzők helyére a megfelelő adatok kerülnek, amikor az utasítások megjelennek a felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-132">Placeholders are replaced with the appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="c5fd5-133">Végezze el a következő lépéseket a helyőrzők beillesztéséhez:</span><span class="sxs-lookup"><span data-stu-id="c5fd5-133">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="c5fd5-134">Kattintson a **Küldési utasítások** mezőre a helyőrző helyének meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-134">Click in the **Submission instructions** field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="c5fd5-135">Kattintson a **Helyőrző beszúrása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-135">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="c5fd5-136">A megjelenő listában válassza ki a beilleszteni kívánt helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-136">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="c5fd5-137">Kattintson a **Beszúrás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-137">Click **Insert**.</span></span>

4. <span data-ttu-id="c5fd5-138">Az utasítások fordításainak hozzáadásához, végezze el a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="c5fd5-138">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="c5fd5-139">Kattintson a **Fordítások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-139">Click **Translations**.</span></span>
    2. <span data-ttu-id="c5fd5-140">A megjelenő oldalon kattintson a **Hozzáadás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-140">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="c5fd5-141">A megjelenő listában válassza ki a szöveg nyelvét, amelyen írni fogja azt.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-141">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="c5fd5-142">Írja be a szöveget a **Lefordított szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-142">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="c5fd5-143">A szöveg testreszabásához, illesszen be helyőrzőket.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-143">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="c5fd5-144">A helyőrző megadásával kapcsolatos további tudnivalókért lásd a 3. lépést.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-144">For instructions about how to enter a placeholder, see step 3.</span></span>
    6. <span data-ttu-id="c5fd5-145">Kattintson a **Bezárás** gombra.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-145">Click **Close**.</span></span>

## <a name="specify-when-this-workflow-is-used"></a><span data-ttu-id="c5fd5-146">A munkafolyamat használati idejének meghatározása.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-146">Specify when this workflow is used</span></span>

<span data-ttu-id="c5fd5-147">Több, ugyanazon a típuson alapuló munkafolyamatot is megadhat.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-147">You can create multiple workflows that are based on the same type.</span></span> <span data-ttu-id="c5fd5-148">Például, ha létrehoz egy beszerzési igénylési munkafolyamatot minden működési országhoz/régióhoz, például a beszerzési igénylés munkafolyamatának a Beszerzési igénylések Dánia vagy Beszerzési igénylések Spanyolország nevet adhatja.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-148">For example, you can create a purchase requisition workflow for each country/region that you operate in, such as Purchase Requisitions Denmark and Purchase Requisitions Spain.</span></span> <span data-ttu-id="c5fd5-149">Ha több olyan munkafolyamata van, amelyeknek alapja ugyanaz a típus, meg kell adnia, hogy mikor szeretné a munkafolyamtot használni.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-149">When you have multiple workflows that are based on the same type, you must specify when each workflow is used.</span></span> <span data-ttu-id="c5fd5-150">Az előző példához adja meg a következő feltételeket:</span><span class="sxs-lookup"><span data-stu-id="c5fd5-150">For the preceding example, you specify the following conditions:</span></span>

- <span data-ttu-id="c5fd5-151">A Beszerzési igénylés Dánia akkor használandó, amikor: ország/terület = DK.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-151">Purchase Requisitions Denmark is used when: country/region = DK</span></span>
- <span data-ttu-id="c5fd5-152">A Beszerzési igénylés Spanyolország akkor használandó, amikor: az ország/terület = ES.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-152">Purchase Requisitions Spain is used when: country/region = ES</span></span>

<span data-ttu-id="c5fd5-153">A következő lépések segítségével megadhatja, hogy mikor szeretné használni az éppen konfigurált munkafolyamatot.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-153">Follow these steps to specify when the workflow that you're configuring is used.</span></span>

1. <span data-ttu-id="c5fd5-154">A bal oldali panelen kattintson az **Aktiválás** gombra.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-154">In the left pane, click **Activation**.</span></span>
2. <span data-ttu-id="c5fd5-155">Válassza ki a **A munkafolyamat futtatási feltételeinek beállítása** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-155">Select the **Set the conditions for running this workflow** check box.</span></span>
3. <span data-ttu-id="c5fd5-156">Kattintson a **Feltétel hozzáadása** parancsra.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-156">Click **Add condition**.</span></span>
4. <span data-ttu-id="c5fd5-157">Feltétel megadása.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-157">Enter a condition.</span></span>
5. <span data-ttu-id="c5fd5-158">Adja meg a további szükséges feltételeket.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-158">Enter any additional conditions that are required.</span></span>
6. <span data-ttu-id="c5fd5-159">Ha ellenőrizni szeretné, hogy a megadott feltételek helyesen vannak-e beállítva, végezze el a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="c5fd5-159">To verify that the conditions that you entered are set correctly, follow these steps:</span></span>

    1. <span data-ttu-id="c5fd5-160">Kattintson a **Teszt** gombra.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-160">Click **Test**.</span></span>
    2. <span data-ttu-id="c5fd5-161">A **Munkafolyamati feltétel tesztelése** oldalon, a **Feltétel érvényesítése** területen válasszon ki egy rekordot.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-161">On the **Test workflow condition** page, in the **Validate condition** area, select a record.</span></span>
    3. <span data-ttu-id="c5fd5-162">Kattintson a **Teszt** gombra.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-162">Click **Test**.</span></span> <span data-ttu-id="c5fd5-163">A rendszer értékeli a bejegyzést, annak érdekében, hogy meghatározza, hogy az megfeleljen-e a meghatározott feltételeknek.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-163">The system evaluates the record to determine whether it meets the conditions that you specified.</span></span> <span data-ttu-id="c5fd5-164">Ha például Spanyolországhoz egy beszerzési igénylési munkafolyamatot hoz létre az oldal **Feltétel érvényesítése** területe megjeleníti a beszerzési igénylések listáját.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-164">For example, if you're creating a purchase requisition workflow for Spain, the **Validate condition** area of the page shows a list of purchase requisitions.</span></span> <span data-ttu-id="c5fd5-165">Ha a **Teszt** parancsra kattint, a rendszer kiértékeli a kijelölt beszerzési igénylést annak érdekében, hogy meghatározza, hogy az ország/terület ES vagy sem.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-165">When you click **Test**, the system evaluates the selected purchase requisition to determine whether the country/region is ES.</span></span>
    4. <span data-ttu-id="c5fd5-166">Kattintson az **OK** vagy a **Mégse** lehetőségre a **Tulajdonságok** lapra történő visszalépéshez.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-166">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="c5fd5-167">Az értesítések küldési idejének meghatározása</span><span class="sxs-lookup"><span data-stu-id="c5fd5-167">Specify when notifications are sent</span></span>

<span data-ttu-id="c5fd5-168">Amikor elküldenek egy dokumentumot feldolgozásra, létrejön egy munkafolyamat-példány.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-168">When a document is submitted for processing, a workflow instance is created.</span></span> <span data-ttu-id="c5fd5-169">Értesítést a felhasználóknak olyankor küldhet, amikor a munkafolyamat-példányok (melyeknek alapja a munkafolyamat) elkezdődtek, elkészültek, megszakították őket, vagy hiba miatt leálltak.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-169">You can send notifications to users when workflow instances that are based on the workflow are started, completed, terminated, or stopped because of an error.</span></span> <span data-ttu-id="c5fd5-170">A következő lépések segítségével megadhatja, hogy mikor küldjön a rendszer értesítéseket.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-170">Follow these steps to specify when notifications are sent.</span></span>

1. <span data-ttu-id="c5fd5-171">A bal oldali panelen kattintson az **Értesítések** gombra.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-171">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="c5fd5-172">Jelölje be a jelölőnégyzetet minden olyan eseményhez, amely az előidézi értesítéseket:</span><span class="sxs-lookup"><span data-stu-id="c5fd5-172">Select the check box for each event that should trigger notifications:</span></span>

    - <span data-ttu-id="c5fd5-173">**Elindítva** – Értesítések küldése, ha a rendszer elkezdi a munkafolyamat-példányt.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-173">**Started** – Send notifications when a workflow instance is started.</span></span>
    - <span data-ttu-id="c5fd5-174">**Leállítva** – Értesítések küldése, ha hiba miatt leáll a munkafolyamat-példány.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-174">**Stopped** – Send notifications when a workflow instance is stopped because of an error.</span></span>
    - <span data-ttu-id="c5fd5-175">**Befejeződött** – Értesítések küldése, ha befejeződött a munkafolyamat-példány.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-175">**Completed** – Send notifications when a workflow instance is completed.</span></span>
    - <span data-ttu-id="c5fd5-176">**Helyreállíthatatlan** – Értesítések küldése, ha helyreállíthatatlan hiba miatt leáll a munkafolyamat-példány.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-176">**Unrecoverable** – Send notifications when a workflow instance is stopped because of an unrecoverable error.</span></span>
    - <span data-ttu-id="c5fd5-177">**Megszakítva** – Értesítések küldése, ha megszakították a munkafolyamat-példányt.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-177">**Terminated** – Send notifications when a workflow instance is terminated.</span></span>

3. <span data-ttu-id="c5fd5-178">Jelölje ki a sort a 2. lépésben választott eseményhez.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-178">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="c5fd5-179">Az **Értesítési szöveg** lapon, írja be az értesítés szövegét.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-179">On the **Notification text** tab, enter the text of the notification.</span></span>
5. <span data-ttu-id="c5fd5-180">A szöveg testreszabásához, illesszen be helyőrzőket.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-180">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="c5fd5-181">A helyőrzők helyére a megfelelő adatok kerülnek, amikor a szöveg megjelenik a felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-181">Placeholders are replaced with the appropriate data when the text is shown to users.</span></span> <span data-ttu-id="c5fd5-182">Végezze el a következő lépéseket a helyőrzők beillesztéséhez:</span><span class="sxs-lookup"><span data-stu-id="c5fd5-182">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="c5fd5-183">Kattintson a mezőben oda, ahol meg szeretné jeleníteni a helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-183">Click in the field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="c5fd5-184">Kattintson a **Helyőrző beszúrása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-184">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="c5fd5-185">A megjelenő listában válassza ki a beilleszteni kívánt helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-185">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="c5fd5-186">Kattintson a **Beszúrás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-186">Click **Insert**.</span></span>
    5. <span data-ttu-id="c5fd5-187">Egy gyakori **Értesítés szövege** helyőrző, melyet létrehoznak: „Utolsó jegyzetek: %Workflow.Last note%”, melly az előző lépés megjegyzéseit jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-187">A common **Notification text** placeholder to include is "Last Notes: %Workflow.Last note%", which displays any comments from the previous step.</span></span>

6. <span data-ttu-id="c5fd5-188">A szöveg fordításainak hozzáadásához, végezze el a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="c5fd5-188">To add translations of the text, follow these steps:</span></span>

    1. <span data-ttu-id="c5fd5-189">Kattintson a **Fordítások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-189">Click **Translations**.</span></span>
    2. <span data-ttu-id="c5fd5-190">A megjelenő oldalon kattintson a **Hozzáadás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-190">On the page that appears, Click **Add**.</span></span>
    3. <span data-ttu-id="c5fd5-191">A megjelenő listában válassza ki a szöveg nyelvét, amelyen írni fogja azt.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-191">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="c5fd5-192">Írja be a szöveget a **Lefordított szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-192">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="c5fd5-193">A szöveg testreszabásához, illesszen be helyőrzőket.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-193">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="c5fd5-194">A helyőrző megadásával kapcsolatos további tudnivalókért lásd a 5. lépést.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-194">For instructions about how to enter a placeholder, see step 5.</span></span>
    6. <span data-ttu-id="c5fd5-195">Kattintson a **Bezárás** gombra.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-195">Click **Close**.</span></span>

7. <span data-ttu-id="c5fd5-196">A **Címzett** lapon, a következő beállításokkal adja meg, határozza meg, hogy kik kaphatnak értesítéseket.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-196">On the **Recipient** tab, use the following options to specify who should receive the notifications.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="c5fd5-197">Lehetőség</span><span class="sxs-lookup"><span data-stu-id="c5fd5-197">Option</span></span></th>
    <th><span data-ttu-id="c5fd5-198">Ezeknek a felhasználóknak küldött értesítések</span><span class="sxs-lookup"><span data-stu-id="c5fd5-198">Notifications are sent to these users</span></span></th>
    <th><span data-ttu-id="c5fd5-199">Az értesítések küldéséhez, végezze el a következő lépéseket</span><span class="sxs-lookup"><span data-stu-id="c5fd5-199">To send notifications, follow these steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="c5fd5-200">Résztvevő</span><span class="sxs-lookup"><span data-stu-id="c5fd5-200">Participant</span></span></td>
    <td><span data-ttu-id="c5fd5-201">Egy adott csoporthoz vagy szerephez hozzárendelt felhasználók</span><span class="sxs-lookup"><span data-stu-id="c5fd5-201">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="c5fd5-202">A <strong>Címzett</strong> lapon, kattintson a <strong>Résztvevő</strong> lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-202">On the <strong>Recipient</strong> tab, click <strong>Participant</strong>.</span></span></li>
    <li><span data-ttu-id="c5fd5-203">A <strong>Szerepköralapú</strong> lapon, a <strong>Résztvevő típusa</strong> listán, válassza ki a csoport vagy a szerep típusát, amely számára értesítéseket kíván küldeni.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-203">On the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="c5fd5-204">A <strong>Résztvevő</strong> listáján jelölje ki a csoportot vagy szerepkört, amely számára értesítést kíván küldeni.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-204">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="c5fd5-205">Munkafolyamat felhasználója</span><span class="sxs-lookup"><span data-stu-id="c5fd5-205">Workflow user</span></span></td>
    <td><span data-ttu-id="c5fd5-206">A munkafolyamatban résztvevő felhasználók</span><span class="sxs-lookup"><span data-stu-id="c5fd5-206">Users who are participants in this workflow</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="c5fd5-207">A <strong>Címzett</strong> lapon, kattintson a <strong>Munkafolyamat felhasználója</strong> lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-207">On the <strong>Recipient</strong> tab, click <strong>Workflow user</strong>.</span></span></li>
    <li><span data-ttu-id="c5fd5-208">A <strong>Munkafolyamat-felhasználó</strong> lapon található <strong>Munkafolyamat-felhasználó</strong> listából, jelöljön ki a munkafolyamat egy résztevevőjét.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-208">On the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a participant in this workflow.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="c5fd5-209">Felhasználó</span><span class="sxs-lookup"><span data-stu-id="c5fd5-209">User</span></span></td>
    <td><span data-ttu-id="c5fd5-210">Meghatározott felhasználók</span><span class="sxs-lookup"><span data-stu-id="c5fd5-210">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="c5fd5-211">A <strong>Címzett</strong> lapon, kattintson a <strong>Felhasználó</strong> lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-211">On the <strong>Recipient</strong> tab, click <strong>User</strong>.</span></span></li>
    <li><span data-ttu-id="c5fd5-212">A <strong>Felhasználók</strong> lapon található <strong>Rendelkezésre álló felhasználók</strong> lista az összes felhasználót tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-212">On the <strong>User</strong> tab, the <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="c5fd5-213">Válassza ki azokat a felhasználókat, akik számára értesítéseket kíván küldeni, majd helyezze át ezeket a felhasználókat a <strong>Kijelölt felhasználók</strong> listájára.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-213">Select the users to send notifications to, and move those users into the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="c5fd5-214">Ismételje meg a 3 – 7. lépést a 2. lépésben kiválasztott összes eseményhez.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-214">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a><span data-ttu-id="c5fd5-215">Írjon megjegyzéseket a munkafolyamathoz az elvégzett változtatásokkal kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-215">Enter comments about the changes that you made to the workflow</span></span>

<span data-ttu-id="c5fd5-216">Ha megjegyzéseket szeretne fűzni a munkafolyamathoz az elvégzett változtatásokkal kapcsolatban, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-216">To enter comments about the changes that you made to the workflow, follow these steps.</span></span>

1. <span data-ttu-id="c5fd5-217">A bal oldali panelen kattintson a **Megjegyzések** gombra.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-217">In the left pane, click **Notes**.</span></span>
2. <span data-ttu-id="c5fd5-218">Írja be a megjegyzéseit az **Adja meg a munkafolyamatra vonatkozó megjegyzéseket** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-218">In the **Enter comments about the workflow** field, enter your comments.</span></span>
3. <span data-ttu-id="c5fd5-219">Megjegyzések áttekintése.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-219">Review your comments.</span></span> <span data-ttu-id="c5fd5-220">Miután hozzáadta a megjegyzéseket, nem módosíthatja azokat.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-220">After you add comments, you can't modify them.</span></span>
4. <span data-ttu-id="c5fd5-221">Kattintson a **Hozzáadás** gombra a megjegyzések az **Előző megjegyzések** területre történő hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="c5fd5-221">Click **Add** to add your comments to the **Comment history** area.</span></span>
