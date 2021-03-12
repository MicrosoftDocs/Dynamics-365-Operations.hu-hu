---
title: Automatizált feladatok konfigurálása munkafolyamatban
description: Ez a témakör bemutatja, hogyan kell konfigurálni az automatizált feladat tulajdonságait.
author: ChrisGarty
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 192061
ms.assetid: c0aceb57-b5e6-4ef3-91e7-89a21c9f048a
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 003a5d2332aaf12ee7e9352ecb61ef190c04a41f
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798905"
---
# <a name="configure-automated-tasks-in-a-workflow"></a><span data-ttu-id="33668-103">Automatizált feladatok konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="33668-103">Configure automated tasks in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="33668-104">Ez a témakör bemutatja, hogyan kell konfigurálni az automatizált feladat tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="33668-104">This topic explains how to configure the properties for an automated task.</span></span>

<span data-ttu-id="33668-105">A munkafolyamat-szerkesztő automatizált feladatának konfigurálásához, kattintson a jobb gombbal a feladatra, és kattintson **Tulajdonságok** oldal megnyitásához a **Tulajdonságok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="33668-105">To configure an automated task in the workflow editor, right-click the task, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="33668-106">Ezt követően a következő eljárások segítségével állítsa be az automatizált feladat tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="33668-106">Then use the following procedures to configure the properties for the automated task.</span></span>

## <a name="name-the-task"></a><span data-ttu-id="33668-107">A feladat elnevezése</span><span class="sxs-lookup"><span data-stu-id="33668-107">Name the task</span></span>

<span data-ttu-id="33668-108">A következő lépések segítségével elnevezheti az automatizált feladatot.</span><span class="sxs-lookup"><span data-stu-id="33668-108">Follow these steps to enter a name for the automated task.</span></span>

1. <span data-ttu-id="33668-109">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="33668-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="33668-110">Adja meg a feladat egyedi nevét a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="33668-110">In the **Name** field, enter a unique name for the task.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="33668-111">Az értesítések küldési idejének meghatározása</span><span class="sxs-lookup"><span data-stu-id="33668-111">Specify when notifications are sent</span></span>

<span data-ttu-id="33668-112">Értesítéseket küldhet a felhasználóknak az automatizált feladat futtatásakor, vagy visszavonásakor.</span><span class="sxs-lookup"><span data-stu-id="33668-112">You can send notifications to people when an automated task has been run or canceled.</span></span> <span data-ttu-id="33668-113">Végezze el a következő lépéseket, annak meghatározása érdekében, hogy mikor és kinek küldje el a rendszer az értesítéseket.</span><span class="sxs-lookup"><span data-stu-id="33668-113">Follow these steps to specify when notifications are sent, and who they are sent to.</span></span>

1. <span data-ttu-id="33668-114">A bal oldali panelen kattintson az **Értesítések** gombra.</span><span class="sxs-lookup"><span data-stu-id="33668-114">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="33668-115">Jelölje be a jelölőnégyzetet azon eseményekhez, amelyekhez ki kell küldeni az értesítéseket:</span><span class="sxs-lookup"><span data-stu-id="33668-115">Select the check box next to the events to send notifications for:</span></span>

    - <span data-ttu-id="33668-116">**Végrehajtás** – A rendszer értesítéseket küld a feladat futtatásakor.</span><span class="sxs-lookup"><span data-stu-id="33668-116">**Execution** – Notifications are sent when the task has been run.</span></span>
    - <span data-ttu-id="33668-117">**Érvénytelenítve** – A rendszer értesítéseket küld a feladat érvénytelenítésekor.</span><span class="sxs-lookup"><span data-stu-id="33668-117">**Canceled** – Notifications are sent when the task has been canceled.</span></span>

3. <span data-ttu-id="33668-118">Jelölje ki a sort a 2. lépésben választott eseményhez.</span><span class="sxs-lookup"><span data-stu-id="33668-118">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="33668-119">Írja be az értesítés szövegét az **Értesítési szöveg** lapon lévő szövegdobozba.</span><span class="sxs-lookup"><span data-stu-id="33668-119">On the **Notification text** tab, in the text box, enter the text of the notification.</span></span>
5. <span data-ttu-id="33668-120">Az értesítések személyre szabásához, helyőrzőket szúrhat be.</span><span class="sxs-lookup"><span data-stu-id="33668-120">To personalize the notification, you can insert placeholders.</span></span> <span data-ttu-id="33668-121">A helyőrzők helyére a megfelelő adatok kerülnek, amikor az értesítés megjelenik a felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="33668-121">Placeholders are replaced with appropriate data when the notification is shown to users.</span></span> <span data-ttu-id="33668-122">Végezze el a következő lépéseket a helyőrzők beillesztéséhez:</span><span class="sxs-lookup"><span data-stu-id="33668-122">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="33668-123">Kattintson oda a szövegdobozban, ahol meg szeretné jeleníteni a helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="33668-123">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="33668-124">Kattintson a **Helyőrző beszúrása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="33668-124">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="33668-125">A megjelenő listában válassza ki a beilleszteni kívánt helyőrzőt.</span><span class="sxs-lookup"><span data-stu-id="33668-125">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="33668-126">Kattintson a **Beszúrás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="33668-126">Click **Insert**.</span></span>

6. <span data-ttu-id="33668-127">Az értesítések fordításainak hozzáadásához, végezze el a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="33668-127">To add translations of the notification, follow these steps:</span></span>

    1. <span data-ttu-id="33668-128">Kattintson a **Fordítások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="33668-128">Click **Translations**.</span></span>
    2. <span data-ttu-id="33668-129">A megjelenő oldalon kattintson a **Hozzáadás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="33668-129">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="33668-130">A megjelenő listában válassza ki az éppen begépelt szöveg nyelvét.</span><span class="sxs-lookup"><span data-stu-id="33668-130">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="33668-131">Írja be a szöveget a **Lefordított szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="33668-131">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="33668-132">A szöveg személyre szabásához, helyőrzőket illeszthet be a 5. lépésben leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="33668-132">To personalize the text, you can insert placeholders as described in step 5.</span></span>
    6. <span data-ttu-id="33668-133">Kattintson a **Bezárás** gombra.</span><span class="sxs-lookup"><span data-stu-id="33668-133">Click **Close**.</span></span>

7. <span data-ttu-id="33668-134">Adja meg azokat a személyeket, akik értesítéseket kapnak a **Címzett** lapon.</span><span class="sxs-lookup"><span data-stu-id="33668-134">On the **Recipient** tab, specify who the notifications are sent to.</span></span> <span data-ttu-id="33668-135">Válasszon ki egy lehetőséget a következő táblázatban, majd ezt követően végezze el a további lépéseket a beállításhoz, mielőtt továbblép a 8. lépésre.</span><span class="sxs-lookup"><span data-stu-id="33668-135">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 8.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="33668-136">Lehetőség</span><span class="sxs-lookup"><span data-stu-id="33668-136">Option</span></span></th>
    <th><span data-ttu-id="33668-137">Értesítés címzettjei</span><span class="sxs-lookup"><span data-stu-id="33668-137">Notification recipients</span></span></th>
    <th><span data-ttu-id="33668-138">További lépések</span><span class="sxs-lookup"><span data-stu-id="33668-138">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="33668-139">Résztvevő</span><span class="sxs-lookup"><span data-stu-id="33668-139">Participant</span></span></td>
    <td><span data-ttu-id="33668-140">Egy adott csoporthoz vagy szerephez hozzárendelt felhasználók</span><span class="sxs-lookup"><span data-stu-id="33668-140">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="33668-141">Miután kiválasztotta <strong>Résztvevő</strong> lehetőséget a <strong>Szerepkör-alapú</strong> lapon, a <strong>Résztvevő típusa</strong> listán jelölje ki azon csoport vagy a szerepkör típusát, amely számára az értesítéseket el kívánja küldeni.</span><span class="sxs-lookup"><span data-stu-id="33668-141">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="33668-142">A <strong>Résztvevő</strong> listáján jelölje ki a csoportot vagy szerepkört, amely számára értesítést kíván küldeni.</span><span class="sxs-lookup"><span data-stu-id="33668-142">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="33668-143">Munkafolyamat felhasználója</span><span class="sxs-lookup"><span data-stu-id="33668-143">Workflow user</span></span></td>
    <td><span data-ttu-id="33668-144">Az aktuális munkafolyamatban részt vevő felhasználók</span><span class="sxs-lookup"><span data-stu-id="33668-144">Users who participate in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="33668-145">Miután kijelölte <strong>Munkafolyamat-felhasználó</strong> lehetőséget a <strong>Munkafolyamat-felhasználó</strong> lapon a <strong>Munkafolyamat-felhasználó</strong> listából, jelöljön ki egy felhasználót, aki részt vesz a munkafolyamatban.</span><span class="sxs-lookup"><span data-stu-id="33668-145">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="33668-146">Felhasználó</span><span class="sxs-lookup"><span data-stu-id="33668-146">User</span></span></td>
    <td><span data-ttu-id="33668-147">Meghatározott felhasználók</span><span class="sxs-lookup"><span data-stu-id="33668-147">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="33668-148">Miután kijelölte <strong>Felhasználó</strong> lehetőséget, kattintson a <strong>Felhasználó</strong> fülre.</span><span class="sxs-lookup"><span data-stu-id="33668-148">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="33668-149">A <strong>Rendelkezésre álló felhasználók</strong> listája az összes felhasználót tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="33668-149">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="33668-150">Válassza ki azokat a felhasználókat, akik számára értesítéseket kíván küldeni, majd helyezze át ezeket a felhasználókat a <strong>Kijelölt felhasználók</strong> listájára.</span><span class="sxs-lookup"><span data-stu-id="33668-150">Select the users to send notifications to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="33668-151">Ismételje meg a 3 – 7. lépést a 2. lépésben kiválasztott összes eseményhez.</span><span class="sxs-lookup"><span data-stu-id="33668-151">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>
