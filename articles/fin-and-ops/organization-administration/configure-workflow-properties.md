---
title: "A munkafolyamat elemeinek beállítása"
description: "Ez a témakör bemutatja, hogyan kell konfigurálni a munkafolyamat különböző tulajdonságait."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 196083
ms.assetid: 192b7a98-7d04-4c7a-a986-29d797a8a837
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6cad67d4108a81de545a1e633dc4e12a31af683b
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="configure-the-properties-of-a-workflow"></a><span data-ttu-id="659ea-103">A munkafolyamat elemeinek beállítása</span><span class="sxs-lookup"><span data-stu-id="659ea-103">Configure the properties of a workflow</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="659ea-104">Ez a témakör bemutatja, hogyan kell konfigurálni a munkafolyamat különböző tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="659ea-104">This topic explains how to configure the various properties of a workflow.</span></span>

<span data-ttu-id="659ea-105">A munkafolyamat tulajdonságainak beállítására, a munkafolyamat-szerkesztő megnyitása a munkafolyamat.</span><span class="sxs-lookup"><span data-stu-id="659ea-105">To configure the properties of a workflow, open the workflow in the workflow editor.</span></span> <span data-ttu-id="659ea-106">Kattintson a munkafolyamat-szerkesztő vásznára, majd ezt követően kattintson a **Tulajdonságok** megnyitásához a **Tulajdonságok** képernyőn.</span><span class="sxs-lookup"><span data-stu-id="659ea-106">Click the canvas of the workflow editor, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="659ea-107">A következő eljárások segítségével beállíthatja a munkafolyamat különféle tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="659ea-107">You can then use the following procedures to configure the various properties of the workflow.</span></span>

## <a name="name-the-workflow"></a><span data-ttu-id="659ea-108">A munkafolyamat elnevezése</span><span class="sxs-lookup"><span data-stu-id="659ea-108">Name the workflow</span></span>
<span data-ttu-id="659ea-109">A következő lépések segítségével elnevezheti a munkafolyamatot.</span><span class="sxs-lookup"><span data-stu-id="659ea-109">Follow these steps to enter a name for the workflow.</span></span>

1.  <span data-ttu-id="659ea-110">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="659ea-110">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="659ea-111">A **Név** mezőbe írja be a munkafolyamat egyedi nevét.</span><span class="sxs-lookup"><span data-stu-id="659ea-111">In the **Name** field, enter a unique name for the workflow.</span></span> <span data-ttu-id="659ea-112">Például, ha létrehoz egy beszerzési igénylési munkafolyamatot minden működési országhoz/régióhoz, a beszerzési igénylés munkafolyamatának a **Beszerzési igénylések Dánia** vagy **Beszerzési igénylések Spanyolország** nevet adhatja.</span><span class="sxs-lookup"><span data-stu-id="659ea-112">For example, if you create a purchase requisition workflow for each country/region that you operate in, you can name the purchase requisition workflow **Purchase Requisitions Denmark** or **Purchase Requisitions Spain**.</span></span>

## <a name="specify-the-workflow-owner"></a><span data-ttu-id="659ea-113">A munkafolyamat tulajdonosának meghatározása</span><span class="sxs-lookup"><span data-stu-id="659ea-113">Specify the workflow owner</span></span>
<span data-ttu-id="659ea-114">A munkafolyamat tulajdonosa az a személy, aki az adott munkafolyamatot kezeli és karbantartja.</span><span class="sxs-lookup"><span data-stu-id="659ea-114">The workflow owner is the person who manages and maintains the workflow.</span></span> <span data-ttu-id="659ea-115">A következő lépések segítségével megadhatja a munkafolyamat tulajdonosát.</span><span class="sxs-lookup"><span data-stu-id="659ea-115">Follow these steps to specify the workflow owner.</span></span>

1.  <span data-ttu-id="659ea-116">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="659ea-116">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="659ea-117">Válassza ki a munkafolyamatot kezelő személy nevét a **Tulajdonos** listából.</span><span class="sxs-lookup"><span data-stu-id="659ea-117">In the **Owner** list, select the name of the person who will manage the workflow.</span></span>

## <a name="select-an-email-template"></a><span data-ttu-id="659ea-118">E-mail sablon kiválasztása</span><span class="sxs-lookup"><span data-stu-id="659ea-118">Select an email template</span></span>
<span data-ttu-id="659ea-119">Végezze el az alábbi lépéseket azon e-mail sablon kiválasztásához, amelyet a munkafolyamattal kapcsolatos értesítések létrehozására használ.</span><span class="sxs-lookup"><span data-stu-id="659ea-119">Follow these steps to select the email template that is used to generate notification messages about the workflow.</span></span>

1.  <span data-ttu-id="659ea-120">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="659ea-120">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="659ea-121">Válasszak ki a sablont az **E-mail sablon munkafolyamat-értesítésekhez** listáján.</span><span class="sxs-lookup"><span data-stu-id="659ea-121">In the **Email template for workflow notifications** list, select the template.</span></span>

## <a name="enter-instructions-for-users"></a><span data-ttu-id="659ea-122">Utasítások megadása felhasználók számára</span><span class="sxs-lookup"><span data-stu-id="659ea-122">Enter instructions for users</span></span>
<span data-ttu-id="659ea-123">Utasításokat adhat meg azon felhasználók számára, akik a dokumentumokat feldolgozásra és jóváhagyásra továbbítják.</span><span class="sxs-lookup"><span data-stu-id="659ea-123">You can provide instructions to users who submit documents for processing and approval.</span></span> <span data-ttu-id="659ea-124">Ezeket a felhasználókat *létrehozók* néven is nevezik.</span><span class="sxs-lookup"><span data-stu-id="659ea-124">These users are also referred to as *originators*.</span></span> <span data-ttu-id="659ea-125">Például, ha Ön egy beszerzési igénylési munkafolyamatot hoz létre, akkor utasításokat ad meg.</span><span class="sxs-lookup"><span data-stu-id="659ea-125">For example, you're creating a purchase requisition workflow, and you enter instructions.</span></span> <span data-ttu-id="659ea-126">Ezeket az utasításokat azok a felhasználók tekinthetik meg, akik a **Beszerzési igénylések** képernyőn beszerzési igényléseket adnak meg.</span><span class="sxs-lookup"><span data-stu-id="659ea-126">Those instructions can then be viewed by users who enter purchase requisitions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="659ea-127">Az útmutatás megtekintéséhez, a létrehozó a munkafolyamat üzenetsorán található ikonra kattint.</span><span class="sxs-lookup"><span data-stu-id="659ea-127">To view instructions, the originator clicks the icon in the workflow message bar.</span></span> <span data-ttu-id="659ea-128">A következő lépések segítségével utasításokat adhat meg a felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="659ea-128">Follow these steps to enter instructions for users.</span></span>

1.  <span data-ttu-id="659ea-129">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="659ea-129">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="659ea-130">Írja be az utasításokat a **Küldési utasítások** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="659ea-130">In the **Submission instructions** field, enter the instructions.</span></span>
3.  <span data-ttu-id="659ea-131">Az utasítások testreszabásához, helyőrzőket illeszthet be.</span><span class="sxs-lookup"><span data-stu-id="659ea-131">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="659ea-132">A helyőrzők helyére a megfelelő adatok kerülnek, amikor az utasítások megjelennek a felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="659ea-132">Placeholders are replaced with the appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="659ea-133">Végezze el a következő lépéseket a helyőrzők beillesztéséhez:</span><span class="sxs-lookup"><span data-stu-id="659ea-133">To insert a placeholder, follow these steps:</span></span>
    1.  <span data-ttu-id="659ea-134">Kattintson a **Küldési utasítások** mezőre a helyőrző helyének meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="659ea-134">Click in the **Submission instructions** field to specify where the placeholder should appear.</span></span>
    2.  <span data-ttu-id="659ea-135">Kattintson a **Helyőrző beszúrása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="659ea-135">Click **Insert placeholder**.</span></span>
    3.  <span data-ttu-id="659ea-136">A megjelenő listában válassza ki a beilleszteni kívánt helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="659ea-136">In the list that appears, select the placeholder to insert.</span></span>
    4.  <span data-ttu-id="659ea-137">Kattintson a **Beszúrás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="659ea-137">Click **Insert**.</span></span>

4.  <span data-ttu-id="659ea-138">Az utasítások fordításainak hozzáadásához, végezze el a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="659ea-138">To add translations of the instructions, follow these steps:</span></span>
    1.  <span data-ttu-id="659ea-139">Kattintson a **Fordítások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="659ea-139">Click **Translations**.</span></span>
    2.  <span data-ttu-id="659ea-140">A megjelenő oldalon kattintson a **Hozzáadás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="659ea-140">On the page that appears, click **Add**.</span></span>
    3.  <span data-ttu-id="659ea-141">A megjelenő listában válassza ki a szöveg nyelvét, amelyen írni fogja azt.</span><span class="sxs-lookup"><span data-stu-id="659ea-141">In the list that appears, select the language that you will enter the text in.</span></span>
    4.  <span data-ttu-id="659ea-142">Írja be a szöveget a **Lefordított szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="659ea-142">In the **Translated text** field, enter the text.</span></span>
    5.  <span data-ttu-id="659ea-143">A szöveg testreszabásához, illesszen be helyőrzőket.</span><span class="sxs-lookup"><span data-stu-id="659ea-143">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="659ea-144">A helyőrző megadásával kapcsolatos további tudnivalókért lásd a 3. lépést.</span><span class="sxs-lookup"><span data-stu-id="659ea-144">For instructions about how to enter a placeholder, see step 3.</span></span>
    6.  <span data-ttu-id="659ea-145">Kattintson a **Bezárás** gombra.</span><span class="sxs-lookup"><span data-stu-id="659ea-145">Click **Close**.</span></span>

## <a name="specify-when-this-workflow-is-used"></a><span data-ttu-id="659ea-146">A munkafolyamat használati idejének meghatározása.</span><span class="sxs-lookup"><span data-stu-id="659ea-146">Specify when this workflow is used</span></span>
<span data-ttu-id="659ea-147">Több, ugyanazon a típuson alapuló munkafolyamatot is megadhat.</span><span class="sxs-lookup"><span data-stu-id="659ea-147">You can create multiple workflows that are based on the same type.</span></span> <span data-ttu-id="659ea-148">Például, ha létrehoz egy beszerzési igénylési munkafolyamatot minden működési országhoz/régióhoz, például a beszerzési igénylés munkafolyamatának a Beszerzési igénylések Dánia vagy Beszerzési igénylések Spanyolország nevet adhatja.</span><span class="sxs-lookup"><span data-stu-id="659ea-148">For example, you can create a purchase requisition workflow for each country/region that you operate in, such as Purchase Requisitions Denmark and Purchase Requisitions Spain.</span></span> <span data-ttu-id="659ea-149">Ha több olyan munkafolyamata van, amelyeknek alapja ugyanaz a típus, meg kell adnia, hogy mikor szeretné a munkafolyamtot használni.</span><span class="sxs-lookup"><span data-stu-id="659ea-149">When you have multiple workflows that are based on the same type, you must specify when each workflow is used.</span></span> <span data-ttu-id="659ea-150">Az előző példához adja meg a következő feltételeket:</span><span class="sxs-lookup"><span data-stu-id="659ea-150">For the preceding example, you specify the following conditions:</span></span>

-   <span data-ttu-id="659ea-151">A Beszerzési igénylés Dánia akkor használandó, amikor: ország/terület = DK.</span><span class="sxs-lookup"><span data-stu-id="659ea-151">Purchase Requisitions Denmark is used when: country/region = DK</span></span>
-   <span data-ttu-id="659ea-152">A Beszerzési igénylés Spanyolország akkor használandó, amikor: az ország/terület = ES.</span><span class="sxs-lookup"><span data-stu-id="659ea-152">Purchase Requisitions Spain is used when: country/region = ES</span></span>

<span data-ttu-id="659ea-153">A következő lépések segítségével megadhatja, hogy mikor szeretné használni az éppen konfigurált munkafolyamatot.</span><span class="sxs-lookup"><span data-stu-id="659ea-153">Follow these steps to specify when the workflow that you're configuring is used.</span></span>

1.  <span data-ttu-id="659ea-154">A bal oldali panelen kattintson az **Aktiválás** gombra.</span><span class="sxs-lookup"><span data-stu-id="659ea-154">In the left pane, click **Activation**.</span></span>
2.  <span data-ttu-id="659ea-155">Válassza ki a **A munkafolyamat futtatási feltételeinek beállítása** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="659ea-155">Select the **Set the conditions for running this workflow** check box.</span></span>
3.  <span data-ttu-id="659ea-156">Kattintson a **Feltétel hozzáadása** parancsra.</span><span class="sxs-lookup"><span data-stu-id="659ea-156">Click **Add condition**.</span></span>
4.  <span data-ttu-id="659ea-157">Feltétel megadása.</span><span class="sxs-lookup"><span data-stu-id="659ea-157">Enter a condition.</span></span>
5.  <span data-ttu-id="659ea-158">Adja meg a további szükséges feltételeket.</span><span class="sxs-lookup"><span data-stu-id="659ea-158">Enter any additional conditions that are required.</span></span>
6.  <span data-ttu-id="659ea-159">Ha ellenőrizni szeretné, hogy a megadott feltételek helyesen vannak-e beállítva, végezze el a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="659ea-159">To verify that the conditions that you entered are set correctly, follow these steps:</span></span>
    1.  <span data-ttu-id="659ea-160">Kattintson a **Teszt** gombra.</span><span class="sxs-lookup"><span data-stu-id="659ea-160">Click **Test**.</span></span>
    2.  <span data-ttu-id="659ea-161">A **Munkafolyamati feltétel tesztelése** oldalon, a **Feltétel érvényesítése** területen válasszon ki egy rekordot.</span><span class="sxs-lookup"><span data-stu-id="659ea-161">On the **Test workflow condition** page, in the **Validate condition** area, select a record.</span></span>
    3.  <span data-ttu-id="659ea-162">Kattintson a **Teszt** gombra.</span><span class="sxs-lookup"><span data-stu-id="659ea-162">Click **Test**.</span></span> <span data-ttu-id="659ea-163">A rendszer értékeli a bejegyzést, annak érdekében, hogy meghatározza, hogy az megfeleljen-e a meghatározott feltételeknek.</span><span class="sxs-lookup"><span data-stu-id="659ea-163">The system evaluates the record to determine whether it meets the conditions that you specified.</span></span> <span data-ttu-id="659ea-164">Ha például Spanyolországhoz egy beszerzési igénylési munkafolyamatot hoz létre az oldal **Feltétel érvényesítése** területe megjeleníti a beszerzési igénylések listáját.</span><span class="sxs-lookup"><span data-stu-id="659ea-164">For example, if you're creating a purchase requisition workflow for Spain, the **Validate condition** area of the page shows a list of purchase requisitions.</span></span> <span data-ttu-id="659ea-165">Ha a **Teszt** parancsra kattint, a rendszer kiértékeli a kijelölt beszerzési igénylést annak érdekében, hogy meghatározza, hogy az ország/terület ES vagy sem.</span><span class="sxs-lookup"><span data-stu-id="659ea-165">When you click **Test**, the system evaluates the selected purchase requisition to determine whether the country/region is ES.</span></span>
    4.  <span data-ttu-id="659ea-166">Kattintson az **OK** vagy a **Mégse** lehetőségre a **Tulajdonságok** lapra történő visszalépéshez.</span><span class="sxs-lookup"><span data-stu-id="659ea-166">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="659ea-167">Az értesítések küldési idejének meghatározása</span><span class="sxs-lookup"><span data-stu-id="659ea-167">Specify when notifications are sent</span></span>
<span data-ttu-id="659ea-168">Amikor elküldenek egy dokumentumot feldolgozásra, létrejön egy munkafolyamat-példány.</span><span class="sxs-lookup"><span data-stu-id="659ea-168">When a document is submitted for processing, a workflow instance is created.</span></span> <span data-ttu-id="659ea-169">Értesítést a felhasználóknak olyankor küldhet, amikor a munkafolyamat-példányok (melyeknek alapja a munkafolyamat) elkezdődtek, elkészültek, megszakították őket, vagy hiba miatt leálltak.</span><span class="sxs-lookup"><span data-stu-id="659ea-169">You can send notifications to users when workflow instances that are based on the workflow are started, completed, terminated, or stopped because of an error.</span></span> <span data-ttu-id="659ea-170">A következő lépések segítségével megadhatja, hogy mikor küldjön a rendszer értesítéseket.</span><span class="sxs-lookup"><span data-stu-id="659ea-170">Follow these steps to specify when notifications are sent.</span></span>

1.  <span data-ttu-id="659ea-171">A bal oldali panelen kattintson az **Értesítések** gombra.</span><span class="sxs-lookup"><span data-stu-id="659ea-171">In the left pane, click **Notifications**.</span></span>
2.  <span data-ttu-id="659ea-172">Jelölje be a jelölőnégyzetet minden olyan eseményhez, amely az előidézi értesítéseket:</span><span class="sxs-lookup"><span data-stu-id="659ea-172">Select the check box for each event that should trigger notifications:</span></span>
    -   <span data-ttu-id="659ea-173">**Elindítva** – Értesítések küldése, ha a rendszer elkezdi a munkafolyamat-példányt.</span><span class="sxs-lookup"><span data-stu-id="659ea-173">**Started** – Send notifications when a workflow instance is started.</span></span>
    -   <span data-ttu-id="659ea-174">**Leállítva** – Értesítések küldése, ha hiba miatt leáll a munkafolyamat-példány.</span><span class="sxs-lookup"><span data-stu-id="659ea-174">**Stopped** – Send notifications when a workflow instance is stopped because of an error.</span></span>
    -   <span data-ttu-id="659ea-175">**Befejeződött** – Értesítések küldése, ha befejeződött a munkafolyamat-példány.</span><span class="sxs-lookup"><span data-stu-id="659ea-175">**Completed** – Send notifications when a workflow instance is completed.</span></span>
    -   <span data-ttu-id="659ea-176">**Helyreállíthatatlan** – Értesítések küldése, ha helyreállíthatatlan hiba miatt leáll a munkafolyamat-példány.</span><span class="sxs-lookup"><span data-stu-id="659ea-176">**Unrecoverable** – Send notifications when a workflow instance is stopped because of an unrecoverable error.</span></span>
    -   <span data-ttu-id="659ea-177">**Megszakítva** – Értesítések küldése, ha megszakították a munkafolyamat-példányt.</span><span class="sxs-lookup"><span data-stu-id="659ea-177">**Terminated** – Send notifications when a workflow instance is terminated.</span></span>

3.  <span data-ttu-id="659ea-178">Jelölje ki a sort a 2. lépésben választott eseményhez.</span><span class="sxs-lookup"><span data-stu-id="659ea-178">Select the row for an event that you selected in step 2.</span></span>
4.  <span data-ttu-id="659ea-179">Az **Értesítési szöveg** lapon, írja be az értesítés szövegét.</span><span class="sxs-lookup"><span data-stu-id="659ea-179">On the **Notification text** tab, enter the text of the notification.</span></span>
5.  <span data-ttu-id="659ea-180">A szöveg testreszabásához, illesszen be helyőrzőket.</span><span class="sxs-lookup"><span data-stu-id="659ea-180">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="659ea-181">A helyőrzők helyére a megfelelő adatok kerülnek, amikor a szöveg megjelenik a felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="659ea-181">Placeholders are replaced with the appropriate data when the text is shown to users.</span></span> <span data-ttu-id="659ea-182">Végezze el a következő lépéseket a helyőrzők beillesztéséhez:</span><span class="sxs-lookup"><span data-stu-id="659ea-182">To insert a placeholder, follow these steps:</span></span>
    1.  <span data-ttu-id="659ea-183">Kattintson a mezőben oda, ahol meg szeretné jeleníteni a helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="659ea-183">Click in the field to specify where the placeholder should appear.</span></span>
    2.  <span data-ttu-id="659ea-184">Kattintson a **Helyőrző beszúrása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="659ea-184">Click **Insert placeholder**.</span></span>
    3.  <span data-ttu-id="659ea-185">A megjelenő listában válassza ki a beilleszteni kívánt helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="659ea-185">In the list that appears, select the placeholder to insert.</span></span>
    4.  <span data-ttu-id="659ea-186">Kattintson a **Beszúrás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="659ea-186">Click **Insert**.</span></span>

6.  <span data-ttu-id="659ea-187">A szöveg fordításainak hozzáadásához, végezze el a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="659ea-187">To add translations of the text, follow these steps:</span></span>
    1.  <span data-ttu-id="659ea-188">Kattintson a **Fordítások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="659ea-188">Click **Translations**.</span></span>
    2.  <span data-ttu-id="659ea-189">A megjelenő oldalon kattintson a **Hozzáadás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="659ea-189">On the page that appears, Click **Add**.</span></span>
    3.  <span data-ttu-id="659ea-190">A megjelenő listában válassza ki a szöveg nyelvét, amelyen írni fogja azt.</span><span class="sxs-lookup"><span data-stu-id="659ea-190">In the list that appears, select the language that you will enter the text in.</span></span>
    4.  <span data-ttu-id="659ea-191">Írja be a szöveget a **Lefordított szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="659ea-191">In the **Translated text** field, enter the text.</span></span>
    5.  <span data-ttu-id="659ea-192">A szöveg testreszabásához, illesszen be helyőrzőket.</span><span class="sxs-lookup"><span data-stu-id="659ea-192">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="659ea-193">A helyőrző megadásával kapcsolatos további tudnivalókért lásd a 5. lépést.</span><span class="sxs-lookup"><span data-stu-id="659ea-193">For instructions about how to enter a placeholder, see step 5.</span></span>
    6.  <span data-ttu-id="659ea-194">Kattintson a **Bezárás** gombra.</span><span class="sxs-lookup"><span data-stu-id="659ea-194">Click **Close**.</span></span>

7.  <span data-ttu-id="659ea-195">A **Címzett** lapon, a következő beállításokkal adja meg, határozza meg, hogy kik kaphatnak értesítéseket.</span><span class="sxs-lookup"><span data-stu-id="659ea-195">On the **Recipient** tab, use the following options to specify who should receive the notifications.</span></span>
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="659ea-196">Lehetőség</span><span class="sxs-lookup"><span data-stu-id="659ea-196">Option</span></span></th>
    <th><span data-ttu-id="659ea-197">Ezeknek a felhasználóknak küldött értesítések</span><span class="sxs-lookup"><span data-stu-id="659ea-197">Notifications are sent to these users</span></span></th>
    <th><span data-ttu-id="659ea-198">Az értesítések küldéséhez, végezze el a következő lépéseket</span><span class="sxs-lookup"><span data-stu-id="659ea-198">To send notifications, follow these steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="659ea-199">Résztvevő</span><span class="sxs-lookup"><span data-stu-id="659ea-199">Participant</span></span></td>
    <td><span data-ttu-id="659ea-200">Egy adott csoporthoz vagy szerephez hozzárendelt felhasználók</span><span class="sxs-lookup"><span data-stu-id="659ea-200">Users who are assigned to a specific group or role</span></span></td>
    <td><ol>
    <li><span data-ttu-id="659ea-201">A <strong>Címzett</strong> lapon, kattintson a <strong>Résztvevő</strong> lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="659ea-201">On the <strong>Recipient</strong> tab, click <strong>Participant</strong>.</span></span></li>
    <li><span data-ttu-id="659ea-202">A <strong>Szerepköralapú</strong> lapon, a <strong>Résztvevő típusa</strong> listán, válassza ki a csoport vagy a szerep típusát, amely számára értesítéseket kíván küldeni.</span><span class="sxs-lookup"><span data-stu-id="659ea-202">On the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="659ea-203">A <strong>Résztvevő</strong> listáján jelölje ki a csoportot vagy szerepkört, amely számára értesítést kíván küldeni.</span><span class="sxs-lookup"><span data-stu-id="659ea-203">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="659ea-204">Munkafolyamat felhasználója</span><span class="sxs-lookup"><span data-stu-id="659ea-204">Workflow user</span></span></td>
    <td><span data-ttu-id="659ea-205">A munkafolyamatban résztvevő felhasználók</span><span class="sxs-lookup"><span data-stu-id="659ea-205">Users who are participants in this workflow</span></span></td>
    <td><ol>
    <li><span data-ttu-id="659ea-206">A <strong>Címzett</strong> lapon, kattintson a <strong>Munkafolyamat felhasználója</strong> lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="659ea-206">On the <strong>Recipient</strong> tab, click <strong>Workflow user</strong>.</span></span></li>
    <li><span data-ttu-id="659ea-207">A <strong>Munkafolyamat-felhasználó</strong> lapon található <strong>Munkafolyamat-felhasználó</strong> listából, jelöljön ki a munkafolyamat egy résztevevőjét.</span><span class="sxs-lookup"><span data-stu-id="659ea-207">On the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a participant in this workflow.</span></span></li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="659ea-208">Felhasználó</span><span class="sxs-lookup"><span data-stu-id="659ea-208">User</span></span></td>
    <td><span data-ttu-id="659ea-209">Adott Finance and Operations-felhasználók</span><span class="sxs-lookup"><span data-stu-id="659ea-209">Specific Finance and Operations users</span></span></td>
    <td><ol>
    <li><span data-ttu-id="659ea-210">A <strong>Címzett</strong> lapon, kattintson a <strong>Felhasználó</strong> lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="659ea-210">On the <strong>Recipient</strong> tab, click <strong>User</strong>.</span></span></li>
    <li><span data-ttu-id="659ea-211">A <strong>Felhasználó</strong> lap <strong>Rendelkezésre álló felhasználók</strong> listája az összes Finance and Operations-felhasználót tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="659ea-211">On the <strong>User</strong> tab, the <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="659ea-212">Válassza ki azokat a felhasználókat, akik számára értesítéseket kíván küldeni, majd helyezze át ezeket a felhasználókat a <strong>Kijelölt felhasználók</strong> listájára.</span><span class="sxs-lookup"><span data-stu-id="659ea-212">Select the users to send notifications to, and move those users into the <strong>Selected users</strong> list.</span></span></li>
    </ol></td>
    </tr>
    </tbody>
    </table>

8.  <span data-ttu-id="659ea-213">Ismételje meg a 3 – 7. lépést a 2. lépésben kiválasztott összes eseményhez.</span><span class="sxs-lookup"><span data-stu-id="659ea-213">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a><span data-ttu-id="659ea-214">Írjon megjegyzéseket a munkafolyamathoz az elvégzett változtatásokkal kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="659ea-214">Enter comments about the changes that you made to the workflow</span></span>
<span data-ttu-id="659ea-215">Ha megjegyzéseket szeretne fűzni a munkafolyamathoz az elvégzett változtatásokkal kapcsolatban, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="659ea-215">To enter comments about the changes that you made to the workflow, follow these steps.</span></span>

1.  <span data-ttu-id="659ea-216">A bal oldali panelen kattintson a **Megjegyzések** gombra.</span><span class="sxs-lookup"><span data-stu-id="659ea-216">In the left pane, click **Notes**.</span></span>
2.  <span data-ttu-id="659ea-217">Írja be a megjegyzéseit az **Adja meg a munkafolyamatra vonatkozó megjegyzéseket** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="659ea-217">In the **Enter comments about the workflow** field, enter your comments.</span></span>
3.  <span data-ttu-id="659ea-218">Megjegyzések áttekintése.</span><span class="sxs-lookup"><span data-stu-id="659ea-218">Review your comments.</span></span> <span data-ttu-id="659ea-219">Miután hozzáadta a megjegyzéseket, nem módosíthatja azokat.</span><span class="sxs-lookup"><span data-stu-id="659ea-219">After you add comments, you can't modify them.</span></span>
4.  <span data-ttu-id="659ea-220">Kattintson a **Hozzáadás** gombra a megjegyzések az **Előző megjegyzések** területre történő hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="659ea-220">Click **Add** to add your comments to the **Comment history** area.</span></span>




