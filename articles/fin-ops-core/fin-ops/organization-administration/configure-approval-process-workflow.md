---
title: Jóváhagyási folyamatok konfigurálása munkafolyamatban
description: A következő eljárás segítségével állítsa be a jóváhagyási folyamat tulajdonságait.
author: ChrisGarty
ms.date: 01/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195643
ms.assetid: f853f57b-83ae-4fb0-a9fa-06ea3fc34fa1
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a5738c5993c129f9bb4932180916befaf6f6377a
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751800"
---
# <a name="configure-approval-processes-in-a-workflow"></a><span data-ttu-id="841e6-103">Jóváhagyási folyamatok konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="841e6-103">Configure approval processes in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="841e6-104">A következő eljárás segítségével állítsa be a jóváhagyási folyamat tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="841e6-104">Use the following procedure to configure the properties of the approval process.</span></span>

<span data-ttu-id="841e6-105">A munkafolyamat-szerkesztő jóváhagyási folyamatának beállításához kattintson a jobb gombbal a jóváhagyási elemre, és kattintson **Tulajdonságok** lapon a **Tulajdonságok** űrlap megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="841e6-105">To configure an approval process, in the workflow editor, right-click the approval element, and then click **Properties** to open the **Properties** form.</span></span>

## <a name="name-the-approval-process"></a><span data-ttu-id="841e6-106">A jóváhagyási munkafolyamat elnevezése</span><span class="sxs-lookup"><span data-stu-id="841e6-106">Name the approval process</span></span>

<span data-ttu-id="841e6-107">Kövesse ezeket a lépéseket annak érdekében, hogy nevet adjon a jóváhagyási munkafolyamatnak.</span><span class="sxs-lookup"><span data-stu-id="841e6-107">Follow these steps to enter a name for the approval process.</span></span>

1. <span data-ttu-id="841e6-108">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="841e6-108">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="841e6-109">Írja be a jóváhagyási munkafolyamat egyedi nevét a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="841e6-109">In the **Name** field, enter a unique name for the approval process.</span></span>

## <a name="specify-when-the-system-automatically-acts-on-the-document"></a><span data-ttu-id="841e6-110">Adja meg, hogy mikor intézkedjen a rendszer automatikusan a dokumentum tekintetében</span><span class="sxs-lookup"><span data-stu-id="841e6-110">Specify when the system automatically acts on the document</span></span>

<span data-ttu-id="841e6-111">Beállíthatja, hogy a rendszer automatikusan intézkedjen arról a dokumentumról, amely megfelel a megadott feltételeknek.</span><span class="sxs-lookup"><span data-stu-id="841e6-111">You can configure the system to automatically act on the document if specific conditions are met.</span></span> <span data-ttu-id="841e6-112">A rendszer például 100 USD értéknél kisebb végösszeggel rendelkező költségjelentések jóváhagyására jogosult.</span><span class="sxs-lookup"><span data-stu-id="841e6-112">For example, the system can approve expense reports that have total amounts that are less than USD 100.</span></span> <span data-ttu-id="841e6-113">Végezze el az alábbi lépéseket a dokumentum tekintetében történő intézkedés idejének meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="841e6-113">Follow these steps to specify when the system acts on the document.</span></span>

1. <span data-ttu-id="841e6-114">A bal oldali panelen kattintson az **Automatikus műveletek** gombra.</span><span class="sxs-lookup"><span data-stu-id="841e6-114">In the left pane, click **Automatic actions**.</span></span>
2. <span data-ttu-id="841e6-115">Jelölje ki az **Automatikus műveletek engedélyezése** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="841e6-115">Select the **Enable automatic actions** check box.</span></span>
3. <span data-ttu-id="841e6-116">Kattintson a **Feltétel hozzáadása** parancsra.</span><span class="sxs-lookup"><span data-stu-id="841e6-116">Click **Add condition**.</span></span>
4. <span data-ttu-id="841e6-117">Feltétel megadása.</span><span class="sxs-lookup"><span data-stu-id="841e6-117">Enter a condition.</span></span>
5. <span data-ttu-id="841e6-118">Ha szükséges, adjon meg további feltételeket.</span><span class="sxs-lookup"><span data-stu-id="841e6-118">Enter additional conditions, if necessary.</span></span>
6. <span data-ttu-id="841e6-119">Ha ellenőrizni szeretné, hogy a megadott feltételek helyesen vannak-e konfigurálva, végezze el a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="841e6-119">To verify that the conditions that you entered are configured correctly, complete the following steps:</span></span>

    1. <span data-ttu-id="841e6-120">Kattintson a **Teszt** elemre a **Munkafolyamati feltétel tesztelése** űrlap megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="841e6-120">Click **Test** to open the **Test workflow condition** form.</span></span>
    2. <span data-ttu-id="841e6-121">Válasszon ki egy bejegyzést a képernyő **Feltétel érvényesítése** területén.</span><span class="sxs-lookup"><span data-stu-id="841e6-121">Select a record in the **Validate condition** area of the form.</span></span>
    3. <span data-ttu-id="841e6-122">Kattintson a **Teszt** gombra.</span><span class="sxs-lookup"><span data-stu-id="841e6-122">Click **Test**.</span></span> <span data-ttu-id="841e6-123">A rendszer értékeli a bejegyzést, annak érdekében, hogy meghatározza, hogy a meghatározott feltételeknek megfeleljen-e.</span><span class="sxs-lookup"><span data-stu-id="841e6-123">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4. <span data-ttu-id="841e6-124">Kattintson az **OK** vagy a **Mégse** lehetőségre a **Tulajdonságok** űrlapra történő visszalépéshez.</span><span class="sxs-lookup"><span data-stu-id="841e6-124">Click **OK** or **Cancel** to return to the **Properties** form.</span></span>

7. <span data-ttu-id="841e6-125">Válassza ki az **Automatikus befejezési művelet** listából, hogy milyen intézkedéseket kell a rendszernek végrehajtania a dokumentum tekintetében.</span><span class="sxs-lookup"><span data-stu-id="841e6-125">In the **Auto complete action** list, select the action that the system should take on the document.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="841e6-126">Az értesítések küldési idejének meghatározása</span><span class="sxs-lookup"><span data-stu-id="841e6-126">Specify when notifications are sent</span></span>

<span data-ttu-id="841e6-127">Értesítéseket küldhet a felhasználóknak a dokumentum jóváhagyása, elutasítása, delegálása vagy eszkalálása, illetve változás kérése esetén.</span><span class="sxs-lookup"><span data-stu-id="841e6-127">You can send notifications to people when a document has been approved, rejected, delegated, or escalated, or when a change has been requested.</span></span> <span data-ttu-id="841e6-128">Végezze el a következő lépéseket, annak meghatározása érdekében, hogy mikor és kinek küldje el a rendszer az értesítéseket.</span><span class="sxs-lookup"><span data-stu-id="841e6-128">Follow these steps to specify when notifications are sent, and who the notifications are sent to.</span></span>

1. <span data-ttu-id="841e6-129">A bal oldali panelen kattintson az **Értesítések** gombra.</span><span class="sxs-lookup"><span data-stu-id="841e6-129">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="841e6-130">Jelölje be a jelölőnégyzetet azon eseményekhez, amelyekhez ki kell küldeni az értesítéseket:</span><span class="sxs-lookup"><span data-stu-id="841e6-130">Select the check box next to the events to send notifications for:</span></span>

    - <span data-ttu-id="841e6-131">**Delegálás** – amikor jóváhagyás céljából a dokumentumot egy másik felhasználóhoz rendelték hozzá.</span><span class="sxs-lookup"><span data-stu-id="841e6-131">**Delegate** – When a document has been assigned to another user for approval.</span></span>
    - <span data-ttu-id="841e6-132">**Eszkalálás** – Ha a kijelölt felhasználó nem intézkedett a dokumentummal kapcsolatban a megadott idő alatt.</span><span class="sxs-lookup"><span data-stu-id="841e6-132">**Escalate** – When the assigned user has not acted on a document in the allotted time.</span></span>
    - <span data-ttu-id="841e6-133">**Jóváhagyás** – amikor egy dokumentumot jóváhagytak.</span><span class="sxs-lookup"><span data-stu-id="841e6-133">**Approve** – When a document has been approved.</span></span>
    - <span data-ttu-id="841e6-134">**Elutasítás** – amikor egy dokumentumot elutasítottak.</span><span class="sxs-lookup"><span data-stu-id="841e6-134">**Reject** – When a document has been rejected.</span></span>
    - <span data-ttu-id="841e6-135">**Változtatás kérése** – amikor a hozzárendelt felhasználó kérte egy már elküldött dokumentum módosítását.</span><span class="sxs-lookup"><span data-stu-id="841e6-135">**Request change** – When the assigned user has requested a change to a document that was submitted.</span></span>

3. <span data-ttu-id="841e6-136">Jelölje ki a sort a 2. lépésben választott eseményhez.</span><span class="sxs-lookup"><span data-stu-id="841e6-136">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="841e6-137">Kattintson az **Értesítés szövege** lapra.</span><span class="sxs-lookup"><span data-stu-id="841e6-137">Click the **Notification text** tab.</span></span>
5. <span data-ttu-id="841e6-138">A szövegmezőbe írja be az értesítés szövegét.</span><span class="sxs-lookup"><span data-stu-id="841e6-138">In the text box, enter the text for the notification.</span></span>
6. <span data-ttu-id="841e6-139">Ha személyre szeretné szabni a szöveget, illesszen be helyőrzőket, amelyek helyére a megfelelő adatok kerülnek akkor, amikor azok megjelennek a felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="841e6-139">To personalize the text, you can insert placeholders, which are replaced with the appropriate data when they are displayed to users.</span></span> <span data-ttu-id="841e6-140">Végezze el a következő lépéseket a helyőrzők beillesztéséhez:</span><span class="sxs-lookup"><span data-stu-id="841e6-140">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="841e6-141">Jelölje ki az egérrel azt a helyet a szövegmezőben, ahol meg szeretné jeleníteni a helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="841e6-141">Click in the text box at the location where the placeholder should appear.</span></span>
    2. <span data-ttu-id="841e6-142">Kattintson a **Helyőrző beszúrása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="841e6-142">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="841e6-143">A megjelenő listában válassza ki a beilleszteni kívánt helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="841e6-143">In the list that is displayed, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="841e6-144">Kattintson a **Beszúrás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="841e6-144">Click **Insert**.</span></span>

7. <span data-ttu-id="841e6-145">Az értesítések fordításainak hozzáadásához kattintson a **Fordítások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="841e6-145">To add translations of the notification, click **Translations**.</span></span> <span data-ttu-id="841e6-146">A megjelenő űrlapon tegye a következőket:</span><span class="sxs-lookup"><span data-stu-id="841e6-146">In the form that is displayed, follow these steps:</span></span>

    1. <span data-ttu-id="841e6-147">Kattintson a **Hozzáadás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="841e6-147">Click **Add**.</span></span>
    2. <span data-ttu-id="841e6-148">A megjelenő listában válassza ki a megírandó szöveg nyelvét.</span><span class="sxs-lookup"><span data-stu-id="841e6-148">In the list that is displayed, select the language in which you will enter the text.</span></span>
    3. <span data-ttu-id="841e6-149">Írja be a szöveget az **Lefordított szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="841e6-149">In the **Translated text** text box, enter the text.</span></span>
    4. <span data-ttu-id="841e6-150">A szöveg testreszabásához illesszen be helyőrzőket.</span><span class="sxs-lookup"><span data-stu-id="841e6-150">To personalize the text, insert placeholders.</span></span>
    5. <span data-ttu-id="841e6-151">Kattintson a **Bezárás** gombra.</span><span class="sxs-lookup"><span data-stu-id="841e6-151">Click **Close**.</span></span>

8. <span data-ttu-id="841e6-152">Kattintson az **Átvevő** lapra.</span><span class="sxs-lookup"><span data-stu-id="841e6-152">Click the **Recipient** tab.</span></span>
9. <span data-ttu-id="841e6-153">Határozza meg az értesítések címzettjeit.</span><span class="sxs-lookup"><span data-stu-id="841e6-153">Specify who the notifications are sent to.</span></span> <span data-ttu-id="841e6-154">Válasszon ki egy lehetőséget a következő táblázatban, majd ezt követően végezze el a további lépéseket a beállításhoz, mielőtt továbblép a 10. lépésre.</span><span class="sxs-lookup"><span data-stu-id="841e6-154">Select one of the options in the following table, and then follow the additional steps for the option before you go to step 10.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="841e6-155">Lehetőség</span><span class="sxs-lookup"><span data-stu-id="841e6-155">Option</span></span></th>
    <th><span data-ttu-id="841e6-156">Értesítés címzettjei</span><span class="sxs-lookup"><span data-stu-id="841e6-156">Notification recipients</span></span></th>
    <th><span data-ttu-id="841e6-157">További lépések</span><span class="sxs-lookup"><span data-stu-id="841e6-157">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="841e6-158"><strong>Résztvevő</strong></span><span class="sxs-lookup"><span data-stu-id="841e6-158"><strong>Participant</strong></span></span></td>
    <td><span data-ttu-id="841e6-159">Egy adott csoporthoz vagy szerephez hozzárendelt felhasználók</span><span class="sxs-lookup"><span data-stu-id="841e6-159">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="841e6-160">Miután kijelölte a <strong>Résztvevő</strong> lehetőséget, kattintson a <strong>Szerepköralapú</strong> lapra.</span><span class="sxs-lookup"><span data-stu-id="841e6-160">After you select <strong>Participant</strong>, click the <strong>Role based</strong> tab.</span></span></li>
    <li><span data-ttu-id="841e6-161">A <strong>Résztvevő típusa</strong> listában jelölje ki azt a csoport- vagy szerepkörtípust, amely számára értesítést kíván küldeni.</span><span class="sxs-lookup"><span data-stu-id="841e6-161">In the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="841e6-162">A <strong>Résztvevő</strong> listáján jelölje ki a csoportot vagy szerepkört, amely számára értesítést kíván küldeni.</span><span class="sxs-lookup"><span data-stu-id="841e6-162">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="841e6-163"><strong>Munkafolyamat felhasználója</strong></span><span class="sxs-lookup"><span data-stu-id="841e6-163"><strong>Workflow user</strong></span></span></td>
    <td><span data-ttu-id="841e6-164">Az aktuális munkafolyamatban részt vevő felhasználók</span><span class="sxs-lookup"><span data-stu-id="841e6-164">Users who participate in the current workflow</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="841e6-165">Miután kijelölte a <strong>Munkafolyamat felhasználója</strong> lehetőséget, kattintson a <strong>Munkafolyamat felhasználója</strong> lapra.</span><span class="sxs-lookup"><span data-stu-id="841e6-165">After you select <strong>Workflow user</strong>, click the <strong>Workflow user</strong> tab.</span></span></li>
    <li><span data-ttu-id="841e6-166">A <strong>Munkafolyamat felhasználója</strong> listában jelölje ki a munkafolyamatban részt vevő felhasználót.</span><span class="sxs-lookup"><span data-stu-id="841e6-166">In the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="841e6-167"><strong>Felhasználó</strong></span><span class="sxs-lookup"><span data-stu-id="841e6-167"><strong>User</strong></span></span></td>
    <td><span data-ttu-id="841e6-168">Meghatározott felhasználók</span><span class="sxs-lookup"><span data-stu-id="841e6-168">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="841e6-169">Miután kijelölte <strong>Felhasználó</strong> lehetőséget, kattintson a <strong>Felhasználó</strong> fülre.</span><span class="sxs-lookup"><span data-stu-id="841e6-169">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="841e6-170">Válassza ki azokat a felhasználókat, akik számára értesítéseket kíván küldeni, majd helyezze át ezeket a felhasználókat a <strong>Kijelölt felhasználók</strong> listába.</span><span class="sxs-lookup"><span data-stu-id="841e6-170">Select the users to send notifications to, and then move these users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

10. <span data-ttu-id="841e6-171">Ismételje meg a 3–9. lépést a 2. lépésben kiválasztott összes eseményhez.</span><span class="sxs-lookup"><span data-stu-id="841e6-171">Repeat steps 3 through 9 for each event that you selected in step 2.</span></span>

## <a name="specify-a-final-approver"></a><span data-ttu-id="841e6-172"> A végső jóváhagyó megadása</span><span class="sxs-lookup"><span data-stu-id="841e6-172">Specify a final approver</span></span>

<span data-ttu-id="841e6-173">A végső jóváhagyó kijelölhető olyan esetekre, amikor a jóváhagyó az a személy, aki a dokumentumot jóváhagyásra elküldte, és a „feladó általi jóváhagyás tiltása” van használatban.</span><span class="sxs-lookup"><span data-stu-id="841e6-173">You can designate a final approver for scenarios where the approver is the person who submitted the document for approval and the "disallow approval by submitter" is being used.</span></span> <span data-ttu-id="841e6-174">Kövesse az alábbi lépéseket a végső jóváhagyó megadásához.</span><span class="sxs-lookup"><span data-stu-id="841e6-174">Follow these steps to specify a final approver.</span></span>

1. <span data-ttu-id="841e6-175">A munkafolyamat-szerkesztőben kattintson a jobb gombbal a jóváhagyási elemre, és válassza a **Tulajdonságok** lapon a **Tulajdonságok** űrlap megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="841e6-175">In the workflow editor, right-click the approval element, and then select **Properties** to open the **Properties** form.</span></span>
2. <span data-ttu-id="841e6-176">A bal oldali panelen kattintson az **Speciális beállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="841e6-176">In the left pane, click **Advanced settings**.</span></span>
3. <span data-ttu-id="841e6-177">Jelölje be a **Végső jóváhagyó használata** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="841e6-177">Select the **Use final approver** check box.</span></span>
4. <span data-ttu-id="841e6-178">Válassza ki a listából, hogy ki legyen a végső jóváhagyó.</span><span class="sxs-lookup"><span data-stu-id="841e6-178">In the list, select a user to be the final approver.</span></span>

## <a name="set-a-time-limit"></a><span data-ttu-id="841e6-179">Időkorlát beállítása</span><span class="sxs-lookup"><span data-stu-id="841e6-179">Set a time limit</span></span>

<span data-ttu-id="841e6-180">Kövesse az alábbi lépéseket, ha a jóváhagyási folyamatot egy megadott időn belül be kell fejezni.</span><span class="sxs-lookup"><span data-stu-id="841e6-180">Follow these steps if the approval process must be completed in a specific time.</span></span>

> [!NOTE]
> <span data-ttu-id="841e6-181">Az ezen lépésekben kiválasztott beállítások felülbírálják az egyes jóváhagyási lépések esetében a **Hozzárendelés** és az **Eszkaláció** pontokban megadottakat.</span><span class="sxs-lookup"><span data-stu-id="841e6-181">The options that you select in these steps override the options that you selected in the **Assignment** and **Escalation** areas of each approval step.</span></span>

1. <span data-ttu-id="841e6-182">A bal oldali panelen kattintson az **Speciális beállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="841e6-182">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="841e6-183">Válassza ki a **A munkafolyamat-elem időkorlátjának beállítása** **elem** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="841e6-183">Select the **Set a time limit for the workflow** **element** check box.</span></span>
3. <span data-ttu-id="841e6-184">Az **Időtartam** mezőben adja meg, hogy mikor kell végrehajtani a jóváhagyási folyamatot.</span><span class="sxs-lookup"><span data-stu-id="841e6-184">In the **Duration** field, specify when the approval process must be completed.</span></span> <span data-ttu-id="841e6-185">Válasszon a következő lehetőségek közül:</span><span class="sxs-lookup"><span data-stu-id="841e6-185">Select one of the following options:</span></span>

    - <span data-ttu-id="841e6-186">**Óra** – Adja meg, hogy hány órán belül kell végrehajtani a jóváhagyási folyamatot.</span><span class="sxs-lookup"><span data-stu-id="841e6-186">**Hours** – Enter the number of hours in which the approval process must be completed.</span></span> <span data-ttu-id="841e6-187">Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.</span><span class="sxs-lookup"><span data-stu-id="841e6-187">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="841e6-188">**Nap** – Adja meg, hogy hány napon belül kell végrehajtani a jóváhagyási folyamatot.</span><span class="sxs-lookup"><span data-stu-id="841e6-188">**Days** – Enter the number of days in which the approval process must be completed.</span></span> <span data-ttu-id="841e6-189">Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.</span><span class="sxs-lookup"><span data-stu-id="841e6-189">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="841e6-190">**Hét** – Adja meg, hogy hány héten belül kell végrehajtani a jóváhagyási folyamatot.</span><span class="sxs-lookup"><span data-stu-id="841e6-190">**Weeks** – Enter the number of weeks in which the approval process must be completed.</span></span>
    - <span data-ttu-id="841e6-191">**Hónap** – Válassza ki, hogy melyik hét mely napjáig kell befejezni a jóváhagyási folyamatot.</span><span class="sxs-lookup"><span data-stu-id="841e6-191">**Months** – Select the day and week by which the approval process must be completed.</span></span> <span data-ttu-id="841e6-192">Kérheti például, hogy a hónap harmadik péntekéig végre kelljen hajtani a jóváhagyási folyamatot.</span><span class="sxs-lookup"><span data-stu-id="841e6-192">For example, you may want the approval process to be completed by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="841e6-193">**Év** – Válassza ki, hogy melyik hónap melyik hetének mely napjáig kell befejezni a jóváhagyási folyamatot.</span><span class="sxs-lookup"><span data-stu-id="841e6-193">**Years** – Select the day, week, and month by which the approval process must be completed.</span></span> <span data-ttu-id="841e6-194">Kérheti például, hogy december harmadik hetének péntekéig végre kelljen hajtani a jóváhagyási folyamatot.</span><span class="sxs-lookup"><span data-stu-id="841e6-194">For example, you may want the approval process to be completed by Friday of the third week of December.</span></span>

4. <span data-ttu-id="841e6-195">Ha lejár az időkorlát, a rendszer intézkedik a dokumentummal kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="841e6-195">If the time limit is exceeded, the system acts on the document.</span></span> <span data-ttu-id="841e6-196">Válassza ki a **Művelet** listából, hogy milyen műveletet kell a rendszernek végrehajtania.</span><span class="sxs-lookup"><span data-stu-id="841e6-196">In the **Action** list, select the action that the system should take.</span></span>

## <a name="specify-which-actions-are-available-to-the-user"></a><span data-ttu-id="841e6-197">Annak megadása, hogy mely műveletek érhetők el a felhasználó számára.</span><span class="sxs-lookup"><span data-stu-id="841e6-197">Specify which actions are available to the user</span></span>

<span data-ttu-id="841e6-198">Ha egy dokumentum hozzá van rendelve egy felhasználóhoz jóváhagyásra, a felhasználónak intézkednie kell a dokumentumról.</span><span class="sxs-lookup"><span data-stu-id="841e6-198">When a document is assigned to a user for approval, the user must act on the document.</span></span> <span data-ttu-id="841e6-199">Végezze el az alábbi lépéseket annak meghatározásához, hogy mely műveleteket végezhet el a felhasználó az elküldött dokumentumon.</span><span class="sxs-lookup"><span data-stu-id="841e6-199">Follows these steps to specify which actions the user can take on the document that was submitted.</span></span>

1. <span data-ttu-id="841e6-200">A bal oldali panelen kattintson az **Speciális beállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="841e6-200">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="841e6-201">Ha azt szeretné, hogy a felhasználó jóváhagyhassa a dokumentumot, jelölje be a **Jóváhagyás** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="841e6-201">Select the **Approve** check box if the user can approve the document.</span></span>
3. <span data-ttu-id="841e6-202">Ha azt szeretné, hogy a felhasználó elutasíthassa a dokumentumot, jelölje be az **Elutasítás** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="841e6-202">Select the **Reject** check box the user can reject the document.</span></span>
4. <span data-ttu-id="841e6-203">Ha azt szeretné, hogy a felhasználó kérhesse a dokumentum módosítását, jelölje be a **Változtatás kérése** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="841e6-203">Select the **Request change** check box the user can request changes to the document.</span></span>
5. <span data-ttu-id="841e6-204">Jelölje be a **Delegálás** jelölőnégyzetet, ha a felhasználó jóváhagyásra hozzárendelheti a dokumentumot egy másik felhasználóhoz.</span><span class="sxs-lookup"><span data-stu-id="841e6-204">Select the **Delegate** check box if the user can assign the document to another user for approval.</span></span>

> [!NOTE]
> <span data-ttu-id="841e6-205">A **Műveletek végrehajtásának engedélyezése az Enterprise Portalon** munkalistájából jelölőnégyzet elavult.</span><span class="sxs-lookup"><span data-stu-id="841e6-205">The **Enable actions from the work list in Enterprise Portal** check box has been deprecated.</span></span>

## <a name="configure-the-approval-steps"></a><span data-ttu-id="841e6-206"> Jóváhagyási lépések konfigurálása</span><span class="sxs-lookup"><span data-stu-id="841e6-206">Configure the approval steps</span></span>

<span data-ttu-id="841e6-207">Egy jóváhagyási eljárás jóváhagyási lépésekből áll.</span><span class="sxs-lookup"><span data-stu-id="841e6-207">An approval process consists of approval steps.</span></span> <span data-ttu-id="841e6-208">Az alábbi eljárással lépéseket adhat hozzá a jóváhagyási folyamathoz, valamint beállíthatja a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="841e6-208">Complete the following procedure to add steps the approval process and configure the steps.</span></span>

1. <span data-ttu-id="841e6-209">A munkafolyamat-szerkesztőben kattintson duplán a jóváhagyási folyamatra.</span><span class="sxs-lookup"><span data-stu-id="841e6-209">In the workflow editor, double-click the approval process.</span></span> <span data-ttu-id="841e6-210">A munkafolyamat-szerkesztő megjeleníti a jóváhagyási eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="841e6-210">The workflow editor displays the steps of the approval process.</span></span>
2. <span data-ttu-id="841e6-211">Jóváhagyási lépés hozzáadásához húzza a **Munkafolyamat-elemek** lehetőséget a vászonra.</span><span class="sxs-lookup"><span data-stu-id="841e6-211">To add an approval step, drag the step from the **Workflow elements** area to the canvas.</span></span>
3. <span data-ttu-id="841e6-212">A jóváhagyási lépés konfigurálása: [Jóváhagyási lépések konfigurálása munkafolyamatban](configure-approval-step-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="841e6-212">To configure an approval step, see [Configure approval steps in a workflow](configure-approval-step-workflow.md).</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]