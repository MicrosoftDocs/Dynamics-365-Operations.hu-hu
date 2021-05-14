---
title: Szabadság- és távollétkérelmek kezelése a Teams alkalmazásban
description: Ez a témakör azt mutatja be, hogyan lehet szabadságot kérelmezni a Dynamics 365 Human Resources alkalmazásban a Microsoft Teams rendszerben.
author: andreabichsel
ms.date: 02/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2ea495259ba29f302753991e260d5a8fa990322b
ms.sourcegitcommit: e3f11fc9a9dae416a490437678bb482a0094f9a9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/27/2021
ms.locfileid: "5953412"
---
# <a name="manage-leave-requests-in-teams"></a><span data-ttu-id="7ccc9-103">Szabadságkérelmek kezelése a Teamsben</span><span class="sxs-lookup"><span data-stu-id="7ccc9-103">Manage leave requests in Teams</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="7ccc9-104">A Dynamics 365 Human Resources alkalmazás a Microsoft Teams rendszerben lehetővé teszi, hogy gyorsan kérelmezzen szabadságot, és megtekintse a szabadságegyenlegét közvetlenül a Microsoft Teams rendszerben.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-104">The Dynamics 365 Human Resources app in Microsoft Teams lets you quickly request time off and view your time-off balance information right in Microsoft Teams.</span></span> <span data-ttu-id="7ccc9-105">A robottal együttműködhet a szükséges adatok lekéréséhez és a szabadságkérelem elindításához.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-105">You can interact with a bot to request information and start a leave request.</span></span> <span data-ttu-id="7ccc9-106">A **Szabadság** lapon részletesebb információk olvashatók.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-106">The **Time off** tab provides more detailed information.</span></span> <span data-ttu-id="7ccc9-107">A közelgő szabadságairól is információkat küldhet az embereknek a Teamsben és a Human Resources alkalmazáson kívüli csevegőfelületeken.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-107">You can also send people information about your upcoming time off in Teams and chats outside the Human Resources app.</span></span>

## <a name="install-the-app"></a><span data-ttu-id="7ccc9-108">Az alkalmazás telepítése</span><span class="sxs-lookup"><span data-stu-id="7ccc9-108">Install the app</span></span>

<span data-ttu-id="7ccc9-109">A Dynamics 365 Human Resources alkalmazás a Teams áruházban található.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-109">You can find the Dynamics 365 Human Resources app in the Teams store.</span></span>

1. <span data-ttu-id="7ccc9-110">A Microsoft Teams rendszerben válassza ki a három pontot.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-110">In Microsoft Teams, select the ellipses.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás három pontja](./media/hr-teams-leave-app-ellipses.png)
 
2. <span data-ttu-id="7ccc9-112">Keresse meg a Dynamics 365 Human Resources alkalmazást, majd válassza ki a **Human Resources** címet.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-112">Search for Dynamics 365 Human Resources, and then select the **Human Resources** tile.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás HR címe](./media/hr-teams-leave-app-human-resources-tile.png)

3. <span data-ttu-id="7ccc9-114">Válassza a **Hozzáadás** gombot az alkalmazás telepítéséhez.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-114">Select the **Add** button to install the app.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás telepítése](./media/hr-teams-leave-app-in-store.png)

<span data-ttu-id="7ccc9-116">Ha az alkalmazás nem lépteti be automatikusan, válassza a **Beállítás** lapot a bejelentkezéshez.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-116">If the app doesn't automatically sign you in, select the **Settings** tab to sign in.</span></span>

![Human Resources Teams szabadságkezelő alkalmazás Beállítások lap](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> <span data-ttu-id="7ccc9-118">Ha nem jelenik meg a bejelentkezési párbeszédpanel, ellenőrizze, hogy az előugró ablakok engedélyezve vannak-e a böngésző beállításaiban.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-118">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span> 

<span data-ttu-id="7ccc9-119">Ha egynél több Human Resources-példányhoz van hozzáférése, akkor a **Beállítások** lapon kiválaszthatja, hogy melyik környezethez kíván csatlakozni.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-119">If you have access to more than one instance of Human Resources, you can select which environment you want to connect to in the **Settings** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="7ccc9-120">Az alkalmazás most már támogatja a Rendszergazda biztonsági szerepkört.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-120">The app now supports the System Administrator security role.</span></span>
 
## <a name="use-the-bot"></a><span data-ttu-id="7ccc9-121">A robot használata</span><span class="sxs-lookup"><span data-stu-id="7ccc9-121">Use the bot</span></span>

<span data-ttu-id="7ccc9-122">Az alkalmazás telepítése után egy üdvözlő üzenet jelenik meg, amely ismerteti, hogy milyen típusú intézkedéseket tehet a robot az Ön nevében.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-122">After the app installs, a welcome message appears, letting you know the types of actions the bot can take on your behalf.</span></span>

![Human Resources Teams szabadságkezelő alkalmazás robot üdvözlőüzenete](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> <span data-ttu-id="7ccc9-124">A robottal való első interakciót követően szükség lehet a bejelentkezésre.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-124">When first interacting with the bot, you might need to sign in.</span></span> <span data-ttu-id="7ccc9-125">Ha nem jelenik meg a bejelentkezési párbeszédpanel, ellenőrizze, hogy az előugró ablakok engedélyezve vannak-e a böngésző beállításaiban.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-125">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span>

<span data-ttu-id="7ccc9-126">A robot a következőre kérhető:</span><span class="sxs-lookup"><span data-stu-id="7ccc9-126">You can ask the bot to:</span></span>

- <span data-ttu-id="7ccc9-127">Szabadságkérelem indítása az Ön számára.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-127">Start a leave request for you.</span></span>

  ![Szabadságkérés indítása a Teams-csevegésben](./media/hr-teams-leave-app-initiate.png)

- <span data-ttu-id="7ccc9-129">A csevegőrobot automatikusan kitölti a szabadságra vonatkozó kérést.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-129">The chat bot will populate a leave request for you.</span></span> <span data-ttu-id="7ccc9-130">Válassza ki a **Távollét kérelmezése** lehetőséget, és szerkessze a kérés részleteit.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-130">Select **Request time off** and edit the details for your request.</span></span>

  ![Szabadságkérelem részletes adatainak szerkesztése](./media/hr-teams-leave-app-details.png)

- <span data-ttu-id="7ccc9-132">Ha végzett a szabadságkérés részleteinek szerkesztésével, a **Küldés** gombot kiválasztva küldje el jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-132">When you're done editing your leave request details, select **Submit** to submit it for approval.</span></span>

  ![Szabadságra vonatkozó kérelem elküldése](./media/hr-teams-leave-app-submit.png)

## <a name="manage-your-leave-in-teams"></a><span data-ttu-id="7ccc9-134">Távollét kezelése a Teams alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="7ccc9-134">Manage your leave in Teams</span></span>

<span data-ttu-id="7ccc9-135">A **Szabadság** lapon a következők jeleníthetők meg:</span><span class="sxs-lookup"><span data-stu-id="7ccc9-135">The **Time off** tab allows you to view:</span></span> 

- <span data-ttu-id="7ccc9-136">Az egyes regisztrált szabadságtípusokhoz tartozó egyenleg-információk</span><span class="sxs-lookup"><span data-stu-id="7ccc9-136">Balance information for each leave type you're enrolled in</span></span>

- <span data-ttu-id="7ccc9-137">Várható szabadságkérelmek</span><span class="sxs-lookup"><span data-stu-id="7ccc9-137">Upcoming leave requests</span></span>

- <span data-ttu-id="7ccc9-138">Szabadságkérelmek</span><span class="sxs-lookup"><span data-stu-id="7ccc9-138">Time-off requests</span></span>

- <span data-ttu-id="7ccc9-139">Vázlat szabadságkérelmek</span><span class="sxs-lookup"><span data-stu-id="7ccc9-139">Draft leave requests</span></span>

![Human Resources Teams szabadságkezelő alkalmazás Szabadság lap](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a><span data-ttu-id="7ccc9-141">Új kérelem létrehozása</span><span class="sxs-lookup"><span data-stu-id="7ccc9-141">Create a new request</span></span>

1. <span data-ttu-id="7ccc9-142">Új szabadségkérelem létrehozásához válassza az **Új kérelem** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-142">To create a new leave request, select **New request**.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás Új kérelem](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. <span data-ttu-id="7ccc9-144">Adja meg a kivenni kívánt napot vagy napokat, majd válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-144">Enter the day or days you want to take off, and then select **Add**.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás szabadság hozzáadása](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. <span data-ttu-id="7ccc9-146">Ha szükséges, írjon be egy okkódot.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-146">If applicable, enter a reason code.</span></span> <span data-ttu-id="7ccc9-147">Adjon meg bármilyen megjegyzést, és vegyen fel hozzá mellékleteket.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-147">Also enter any comments and add any attachments.</span></span>

4. <span data-ttu-id="7ccc9-148">Ha befejezte az adatok megadását, írja be az **Elküldés** kifejezést, hogy elküldje jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-148">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="7ccc9-149">Beírhatja a **Mentés piszkozatként** kifejezést is, hogy később visszatérhessen hozzá.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-149">You can also type **Save as draft** to come back to it later.</span></span>

### <a name="manage-draft-requests"></a><span data-ttu-id="7ccc9-150">Vázlat kérelmek kezelése</span><span class="sxs-lookup"><span data-stu-id="7ccc9-150">Manage draft requests</span></span>

1. <span data-ttu-id="7ccc9-151">Válassza ki a **Vázlatok** lapot.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-151">Select the **Drafts** tab.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás Vázlatok lap](./media/hr-teams-leave-app-drafts-tab.png)

2. <span data-ttu-id="7ccc9-153">A kérelem szerkesztéséhez válassza ki a ceruzát, vagy válassza ki a szemétkosarat a kérelem törléséhez.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-153">Select the pencil to edit the request, or select the trash can to delete the request.</span></span>

3. <span data-ttu-id="7ccc9-154">Hajtsa végre a szükséges módosításokat.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-154">Make any necessary changes.</span></span> <span data-ttu-id="7ccc9-155">Ha befejezte az adatok megadását, írja be az **Elküldés** kifejezést, hogy elküldje jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-155">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="7ccc9-156">Választhatja a **Mentés piszkozatként** lehetőséget is, hogy később visszatérhessen hozzá.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-156">You can also select **Save as draft** to come back to it later.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás vázlat szerkesztése](./media/hr-teams-leave-app-drafts-edit.png)
   
### <a name="respond-to-teams-notifications"></a><span data-ttu-id="7ccc9-158">Válaszadás a Teams értesítéseire</span><span class="sxs-lookup"><span data-stu-id="7ccc9-158">Respond to Teams notifications</span></span>

<span data-ttu-id="7ccc9-159">Ha Ön vagy egy olyan dolgozó, akinek Ön jóváhagyója a szabadságkérelmet küld be, akkor a Teamsben értesítést kap a Human Resources alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-159">When you or a worker you're an approver for submits a leave request, you'll receive a notification in the Human Resources app in Teams.</span></span> <span data-ttu-id="7ccc9-160">A megtekintéséhez kiválaszthatja az értesítést.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-160">You can select the notification to view it.</span></span> <span data-ttu-id="7ccc9-161">Az értesítések megjelennek a **Csevegés** területen is.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-161">Notifications also appear in the **Chat** area.</span></span>

<span data-ttu-id="7ccc9-162">Ha a jóváhagyó, akkor az értesítésben kiválaszthatja a **Jóváhagyás** vagy **Elutasítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-162">If you're an approver, you can select **Approve** or **Deny** in the notification.</span></span> <span data-ttu-id="7ccc9-163">Egy opcionális üzenetet is megadhat.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-163">You can also provide an optional message.</span></span>

![Szabadságkérelem értesítése a Human Resources Teams alkalmazásban](./media/hr-teams-leave-app-notification.png)

## <a name="send-upcoming-time-off-information-to-your-coworkers"></a><span data-ttu-id="7ccc9-165">Várható szabadságadatok küldése a munkatársai számára</span><span class="sxs-lookup"><span data-stu-id="7ccc9-165">Send upcoming time-off information to your coworkers</span></span>

<span data-ttu-id="7ccc9-166">Miután telepítette az Human Resources alkalmazást a Teams számára, egyszerűen küldhet információt a Teamsben vagy csevegésekben a munkatársai számára.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-166">After you install the Human Resources app for Teams, you can easily send information about your upcoming time off to your coworkers in teams or chats.</span></span>

1. <span data-ttu-id="7ccc9-167">Egy csapatban vagy csevegésben a Teamsben válassza a chat ablak alatti Human Resources gombot.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-167">In a team or chat in Teams, select the Human Resources button below the chat window.</span></span>

   ![A chat ablak alatti Human Resources gomb](./media/hr-teams-leave-app-chat-button.png)

2. <span data-ttu-id="7ccc9-169">Válassza ki a megosztani kívánt szabadságkérelmet.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-169">Select the leave request you want to share.</span></span> <span data-ttu-id="7ccc9-170">Ha meg szeretné osztani egy vázlat szabadságkérelmet, először válassza a **Vázlatok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-170">If you want to share a draft leave request, select **Drafts** first.</span></span>

   ![Egy közelgő szabadságkérelem kiválasztása megosztásra](./media/hr-teams-leave-app-chat-search.png)

<span data-ttu-id="7ccc9-172">A szabadságkérelem a csevegésben fog megjelenni.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-172">Your leave request will display in the chat.</span></span>

![A Human Resources szabadságkérelem kártya](./media/hr-teams-leave-app-chat-card.png)

<span data-ttu-id="7ccc9-174">Ha megosztott egy vázlat állapotú kérelmet, akkor a program vázlatként jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="7ccc9-174">If you shared a draft request, it will display as a draft:</span></span>

![A Human Resources vázlat szabadságkérelem kártya](./media/hr-teams-leave-app-chat-draft-card.png)

## <a name="view-your-teams-leave-calendar"></a><span data-ttu-id="7ccc9-176">A csapata szabadságnaptárának megtekintése</span><span class="sxs-lookup"><span data-stu-id="7ccc9-176">View your team's leave calendar</span></span>

<span data-ttu-id="7ccc9-177">Ha Ön közvetlen beosztottakkal rendelkező vezető, akkor megtekintheti a csoport jóváhagyott és függőben távolléteit.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-177">If you're a manager with direct reports, you can view your team's approved and pending time off.</span></span>

1. <span data-ttu-id="7ccc9-178">A Teamsben a Human Resources alkalmazásban válassza a **Távollét** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-178">In the Human Resources app in Teams, select **Time off**.</span></span>

2. <span data-ttu-id="7ccc9-179">Válassza ki a **Csoport naptárát**.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-179">Select **Team calendar**.</span></span> <span data-ttu-id="7ccc9-180">A naptárban a közvetlen beosztottjai jóváhagyott és a függőben lévő távollétei láthatók.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-180">The calendar displays your direct reports' approved and pending time off.</span></span>

   ![Naptár megtekintése a Human Resources Teams alkalmazásban](./media/hr-teams-leave-app-view-calendar.png)

   > [!NOTE]
   > <span data-ttu-id="7ccc9-182">Ha nem látja a csapatnaptárat, kérje meg a rendszergazdát, hogy engedélyezze.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-182">If you can't see the team calendar, ask your admin to enable it.</span></span> <span data-ttu-id="7ccc9-183">További információ: [Telepítés és beállítás](hr-admin-teams-leave-app.md#install-and-setup).</span><span class="sxs-lookup"><span data-stu-id="7ccc9-183">For more information, see [Install and setup](hr-admin-teams-leave-app.md#install-and-setup).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="7ccc9-184">Támogatott nyelvek</span><span class="sxs-lookup"><span data-stu-id="7ccc9-184">Supported languages</span></span>

<span data-ttu-id="7ccc9-185">A Dynamics 365 Human Resources alkalmazásban a Teamsben az alábbi nyelvek támogatottak:</span><span class="sxs-lookup"><span data-stu-id="7ccc9-185">The Dynamics 365 Human Resources app in Teams supports the following languages:</span></span>

| <span data-ttu-id="7ccc9-186">Területibeállítás-azonosító</span><span class="sxs-lookup"><span data-stu-id="7ccc9-186">Locale ID</span></span> | <span data-ttu-id="7ccc9-187">Nyelv</span><span class="sxs-lookup"><span data-stu-id="7ccc9-187">Language</span></span> |
| --- | --- |
| <span data-ttu-id="7ccc9-188">de-DE</span><span class="sxs-lookup"><span data-stu-id="7ccc9-188">de-DE</span></span> | <span data-ttu-id="7ccc9-189">Német (Németország)</span><span class="sxs-lookup"><span data-stu-id="7ccc9-189">German (Germany)</span></span> |
| <span data-ttu-id="7ccc9-190">es-ES</span><span class="sxs-lookup"><span data-stu-id="7ccc9-190">es-ES</span></span> | <span data-ttu-id="7ccc9-191">Spanyol (Spanyolország)</span><span class="sxs-lookup"><span data-stu-id="7ccc9-191">Spanish (Spain)</span></span> |
| <span data-ttu-id="7ccc9-192">es-MX</span><span class="sxs-lookup"><span data-stu-id="7ccc9-192">es-MX</span></span> | <span data-ttu-id="7ccc9-193">Spanyol (Mexikó)</span><span class="sxs-lookup"><span data-stu-id="7ccc9-193">Spanish (Mexico)</span></span> |
| <span data-ttu-id="7ccc9-194">fr-CA</span><span class="sxs-lookup"><span data-stu-id="7ccc9-194">fr-CA</span></span> | <span data-ttu-id="7ccc9-195">Francia (Kanada)</span><span class="sxs-lookup"><span data-stu-id="7ccc9-195">French (Canada)</span></span> |
| <span data-ttu-id="7ccc9-196">fr-FR</span><span class="sxs-lookup"><span data-stu-id="7ccc9-196">fr-FR</span></span> | <span data-ttu-id="7ccc9-197">Francia (Franciaország)</span><span class="sxs-lookup"><span data-stu-id="7ccc9-197">French (France)</span></span> |
| <span data-ttu-id="7ccc9-198">it-IT</span><span class="sxs-lookup"><span data-stu-id="7ccc9-198">it-IT</span></span> | <span data-ttu-id="7ccc9-199">Olasz (Olaszország)</span><span class="sxs-lookup"><span data-stu-id="7ccc9-199">Italian (Italy)</span></span> |
| <span data-ttu-id="7ccc9-200">nl-NL</span><span class="sxs-lookup"><span data-stu-id="7ccc9-200">nl-NL</span></span> | <span data-ttu-id="7ccc9-201">Holland (Hollandia)</span><span class="sxs-lookup"><span data-stu-id="7ccc9-201">Dutch (Netherlands)</span></span> |
| <span data-ttu-id="7ccc9-202">pt-BR</span><span class="sxs-lookup"><span data-stu-id="7ccc9-202">pt-BR</span></span> | <span data-ttu-id="7ccc9-203">Portugál (Brazília)</span><span class="sxs-lookup"><span data-stu-id="7ccc9-203">Portuguese (Brazil)</span></span> |
| <span data-ttu-id="7ccc9-204">tr-TR</span><span class="sxs-lookup"><span data-stu-id="7ccc9-204">tr-TR</span></span> | <span data-ttu-id="7ccc9-205">Török (Törökország)</span><span class="sxs-lookup"><span data-stu-id="7ccc9-205">Turkish (Turkey)</span></span> |
| <span data-ttu-id="7ccc9-206">zh-CN</span><span class="sxs-lookup"><span data-stu-id="7ccc9-206">zh-CN</span></span> | <span data-ttu-id="7ccc9-207">Kínai (egyszerűsített)</span><span class="sxs-lookup"><span data-stu-id="7ccc9-207">Chinese (Simplified)</span></span> |

## <a name="troubleshooting"></a><span data-ttu-id="7ccc9-208">Hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="7ccc9-208">Troubleshooting</span></span>

<span data-ttu-id="7ccc9-209">Ha nem sikerül bejelentkeznie a Dynamics 365 Human Resources Teams alkalmazásba vagy nem tudja használni, próbálja ki ezeket a hibaelhárítási utasításokat.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-209">If you're having trouble signing into or using the Dynamics 365 Human Resources Teams app, try following these troubleshooting instructions.</span></span> <span data-ttu-id="7ccc9-210">Ha a hibaelhárítás után sem oldódott meg a probléma, akkor forduljon a támogatáshoz.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-210">If you're still having problems after troubleshooting, contact Support.</span></span> <span data-ttu-id="7ccc9-211">További információért lásd a [Támogatás kérése](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-211">For more information, see [Get support](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span></span>

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a><span data-ttu-id="7ccc9-212">Nem lehet bejelentkezni a Human Resources alkalmazásba a Teamsben.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-212">Can't sign into the Human Resources app in Teams</span></span>

<span data-ttu-id="7ccc9-213">Ha nem tud bejelentkezni az alkalmazásba, akkor előfordulhat, hogy a Microsoft Teamsbe való bejelentkezéshez használt fiók nincs alkalmazotti rekordhoz társítva a Dynamics 365 Human Resources alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-213">If you can't sign into the app, it's possible that the account you're using to sign into Microsoft Teams isn't associated with an employee record in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="7ccc9-214">Forduljon a rendszergazdához, és ellenőrizze, hogy az alkalmazotti rekord helyesen van-e társítva.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-214">Contact your system administrator to ensure your employee record is correctly associated.</span></span>

### <a name="translations-dont-display-correctly"></a><span data-ttu-id="7ccc9-215">A fordítások nem megfelelően jelennek meg</span><span class="sxs-lookup"><span data-stu-id="7ccc9-215">Translations don't display correctly</span></span>

<span data-ttu-id="7ccc9-216">Ha a fordítások nem a vártnak megfelelően jelennek meg, győződjön meg róla, hogy a Teamsben kiválasztott nyelv megegyezik a Human Resources **Felhasználói beállítások** részén megadott nyelvvel.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-216">If translations don't display as expected, make sure the language you select in Teams matches the language selected in Human Resources **User options**.</span></span>

<span data-ttu-id="7ccc9-217">A Teamsben nézze meg az **Alkalmazás nyelve** elemet a **Beállítások** között.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-217">In Teams, look at **App language** in **Settings**.</span></span>

![Teams beállításai](./media/hr-teams-leave-app-settings.png)

<span data-ttu-id="7ccc9-219">A Humar Resources alkalmazásban válassza a **Beállítások** lehetőséget, majd a **Felhasználói beállítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-219">In Human Resources, select **Settings** and then select **User options**.</span></span> <span data-ttu-id="7ccc9-220">Ellenőrizze, hogy a **Nyelv** mező megegyezik-e a Teams **Alkalmazás nyelve** mezőjével.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-220">Verify that the **Language** field matches the **App language** field in Teams.</span></span>

![Human Resources Felhasználói beállítások](./media/hr-teams-leave-app-user-options.png)

<span data-ttu-id="7ccc9-222">Ha továbbra is fordítási problémákat tapasztal, tudassa velünk.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-222">If you still experience translation issues, let us know.</span></span> <span data-ttu-id="7ccc9-223">További információért tekintse át a [Támogatás igénylése a Finance and Operations alkalmazásokhoz vagy a Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json) szolgáltatáshoz.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-223">For information, see [Get support for Finance and Operations apps or Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).</span></span>

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a><span data-ttu-id="7ccc9-224">Hiba történt a Teamsen belüli Human Resource alkalmazásban a szabadságkérelmek jóváhagyásakor.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-224">Error when approving leave requests in the Human Resources app in Teams</span></span>

<span data-ttu-id="7ccc9-225">Ha hibaüzenetet kap, amikor megpróbálja jóváhagyni a szabadságkérelmeket a Teams alkalmazásban, próbálja végrehajtani a következő hibaelhárítási lépéseket:</span><span class="sxs-lookup"><span data-stu-id="7ccc9-225">If you receive an error when you're trying to approve leave requests in the Teams app, try the following troubleshooting steps:</span></span>

1. <span data-ttu-id="7ccc9-226">Ellenőrizze, hogy a Microsoft Teamsbe való bejelentkezéshez használt fiók megegyezik-e a Dynamics 365 Human Resources eléréséhez használt fiókkal.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-226">Verify that the account you're using to sign into Microsoft Teams is the same one you use for accessing Dynamics 365 Human Resources.</span></span>

2. <span data-ttu-id="7ccc9-227">Ellenőrizze, hogy Ön-e a kérelem érvényes jóváhagyója a szabadság jóváhagyására vonatkozó munkafolyamaton belüli beállítások ellenőrzésével.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-227">Verify that you're a valid approver for the request by checking the workflow settings for leave approval.</span></span> <span data-ttu-id="7ccc9-228">A szabadságkérelem munkafolyamatairól további tudnivalókért lásd: [Szabadságkérelmezési munkafolyamat létrehozása](hr-leave-and-absence-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="7ccc9-228">For more information about leave request workflows, see [Create a leave request workflow](hr-leave-and-absence-workflow.md).</span></span>

### <a name="leave-approvers-dont-receive-teams-chat-messages-to-approve-leave-requests"></a><span data-ttu-id="7ccc9-229">Hagyja a jóváhagyókat, ha nem kapnak Teams-üzeneteket a szabadságkérések jóváhagyásához</span><span class="sxs-lookup"><span data-stu-id="7ccc9-229">Leave approvers don't receive Teams chat messages to approve leave requests</span></span>

1. <span data-ttu-id="7ccc9-230">Győződjön meg róla, hogy az értesítések engedélyezve vannak a környezet és a felhasználó számára.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-230">Ensure notifications are enabled for the environment and the user.</span></span> <span data-ttu-id="7ccc9-231">További információért lásd: [Human Resources alkalmazás értesítéseinek engedélyezése a Teamsben](hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams), és a [Ki-és bekapcsolhatja az egyes felhasználók értesítéseit](hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users).</span><span class="sxs-lookup"><span data-stu-id="7ccc9-231">For more information, see [Enable notifications for the Human Resources app in Teams](hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) and [Turn Teams notifications on or off for individual users](hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users).</span></span>

2. <span data-ttu-id="7ccc9-232">Győződjön meg róla, hogy a felhasználók ugyanolyan hitelesítő adatokkal vannak bejelentkezve a **Csevegések** fülön, mint a szabadságkérések jóváhagyásához.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-232">Ensure users are signed into the **Chats** tab with the same credentials they use for approving leave requests.</span></span> <span data-ttu-id="7ccc9-233">A „kijelentkezés” és a „bejelentkezés” üzenetekkel jelentkezzen be a megfelelő hitelesítő adatokkal.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-233">Use the messages "sign out" and then "sign in" to sign in with the correct credentials.</span></span>

3. <span data-ttu-id="7ccc9-234">Ha a probléma továbbra is fennáll, ellenőrizze az Üzleti események rendszer kötegelt feladatának állapotát rendszergazdaként.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-234">If the issue persists, check the status of the Business Events system batch job as a system administrator.</span></span> <span data-ttu-id="7ccc9-235">Ha várakozási vagy végrehajtási állapotban van, térjen vissza néhány perc múlva.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-235">If it's in a waiting or executing stage, check back in a few minutes.</span></span> <span data-ttu-id="7ccc9-236">Ha az állapot változatlan marad, akkor adjon be egy támogatási jegyet, hogy a csapatunk segíthessen a probléma megoldásában.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-236">If the status remains unchanged, log a support ticket so our team can help resolve the issue.</span></span>

## <a name="known-accessibility-issues"></a><span data-ttu-id="7ccc9-237">Ismert kisegítő lehetőségekkel kapcsolatos problémák</span><span class="sxs-lookup"><span data-stu-id="7ccc9-237">Known accessibility issues</span></span>

<span data-ttu-id="7ccc9-238">A Teams Human Resources alkalmazásában a következőak adálymentességgel kapcsolatos problémák tapasztalhatók amelyeket a későbbi kiadásokban kijavítunk.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-238">The Human Resources app in Teams has the following accessibility issues that we're working on fixing in future releases.</span></span>

| <span data-ttu-id="7ccc9-239">Kiadás</span><span class="sxs-lookup"><span data-stu-id="7ccc9-239">Issue</span></span> | <span data-ttu-id="7ccc9-240">Megoldás vagy magyarázat</span><span class="sxs-lookup"><span data-stu-id="7ccc9-240">Workaround or explanation</span></span> |
| --- | --- |
| <span data-ttu-id="7ccc9-241">Ha az asztalon 400%-ra nagyít, a műveletgombok egy része kikerül a képből.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-241">Zooming to 400% on desktop hides some of the action buttons from view.</span></span> | <span data-ttu-id="7ccc9-242">Ehelyett azt javasoljuk, hogy használja a nagyítót, amíg nem tudjuk támogatni ezt a nagyítási szintet.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-242">We recommend using a magnifier instead until we can support this zoom level.</span></span> |
| <span data-ttu-id="7ccc9-243">A **Szabadságolás** lapon a Narrátor egy gombműveletet jelent be, miközben elolvassa a szabadságolás rács fejlécét.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-243">On the **Time off** tab, voiceover announces a button action while reading the header for the time-off grid.</span></span> | <span data-ttu-id="7ccc9-244">A rács fejléce és elemei év szerint vannak csoportosítva, és összecsukhatók.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-244">The header and elements within the grid are grouped by year, and they're collapsible.</span></span> <span data-ttu-id="7ccc9-245">A Narrátor ezt végrehajtható elemként értelmezi, de valójában nem az.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-245">Voiceover interprets this as an actionable item, but it isn't.</span></span> |
| <span data-ttu-id="7ccc9-246">A **Szabadságolás** lapon egy további pöccintési kézmozdulat jelenik meg, amikor egy új kérelemben az **Okkódra** navigál.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-246">On the **Time off** tab, there's an extra swipe gesture when navigating to **Reason code** in a new request.</span></span> | <span data-ttu-id="7ccc9-247">Nincs olyan rejtett vezérlő, amelyhez a pöccintési navigáció megpróbálna eljutni.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-247">There is no hidden control that the swipe navigation is trying to get to.</span></span> |
| <span data-ttu-id="7ccc9-248">Ha a **Szabadságolás** lapon pöccint, miközben a naptár meg van nyitva, akkor a vezérlőn kívülre kerül, nem pedig egy új kérés tetejére, vagy egy kérés szerkesztése közben.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-248">On the **Time off** tab, if you swipe while the calendar is open, you end up outside the control instead of at the top in a new request or while editing a request.</span></span> | <span data-ttu-id="7ccc9-249">Amikor eléri az **Ugrás a mai napra** elemet, vegye úgy, hogy elért a vezérlő végére, és pöccintsen az ellenkező irányba, hogy visszakerüljön felülre.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-249">When you reach **Go to today**, consider that to be the end of the control and swipe in the reverse direction to get back to the top.</span></span> |
| <span data-ttu-id="7ccc9-250">A **Csevegés** lapon a fókusz visszaugrik a képernyő tetejére, amikor dátumot ad meg a kisegítő eszközt vagy a billentyűzetes navigációt használja.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-250">On the **Chat** tab, the focus jumps back to the top when you enter a date while using the assistive tool or keyboard navigation.</span></span> | <span data-ttu-id="7ccc9-251">Használja a Tab billentyűt addig, amíg újra el nem éri a beviteli területet.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-251">Tab until you reach your input area again.</span></span> |

## <a name="privacy-notice"></a><span data-ttu-id="7ccc9-252">Adatvédelmi nyilatkozat</span><span class="sxs-lookup"><span data-stu-id="7ccc9-252">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="7ccc9-253">Microsoft Language Understanding Intelligent Service (LUIS)</span><span class="sxs-lookup"><span data-stu-id="7ccc9-253">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="7ccc9-254">A Microsoft Teams rendszer Dynamics 365 Human Resources robotjával elemezhetők a felhasználó szöveges bemenetei az alapul szolgáló kérdés/szándék megértéséhez.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-254">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="7ccc9-255">A felhasználó bemenete (például a „Contoso fiók keresése”) a Microsoft egyik kognitív szolgáltatásához, a Language Understanding Intelligent Service (LUIS) szolgáltatáshoz van irányítva.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-255">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="7ccc9-256">A LUIS-ról  [itt](https://www.luis.ai/) olvashat többet.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-256">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="7ccc9-257">A LUIS szolgáltatás egyértelműsíti vagy megérti a felhasználói bevitel szándékát (ebben az esetben a szándék az, hogy információt találjon) és a cél entitást (ebben az esetben a szándékolt entitás egy Contoso nevű számla).</span><span class="sxs-lookup"><span data-stu-id="7ccc9-257">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="7ccc9-258">Ez az információ ezután a Microsoft  [Azure bot keretrendszerébe](https://azure.microsoft.com/services/bot-service/) kerül, amely kapcsolatba lép a Dynamics 365 Human Resources adataival, és lekéri a kívánt információkat a felhasználói lekérdezéshez.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-258">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="7ccc9-259">A robot telepítésével és a használatához való hozzáférés engedélyezésével Ön elfogadja, hogy a LUIS szolgáltatás és az Azure robot keretrendszer feldolgozza a bemenet mögötti szándékot, ami egy továbbfejlesztett, társalgásszerű felhasználói élményt eredményez.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-259">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="7ccc9-260">A LUIS szolgáltatás és az Azure robot keretrendszer különböző szintű megfeleléssel rendelkezhet a Dynamics 365 Human Resources alkalmazáshoz képest.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-260">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="7ccc9-261">Noha a LUIS szolgáltatás csak a felhasználói lekérdezésekhez férhet hozzá, és nem a felhasználó Dynamics 365 Human Resources adataihoz vagy fiókjához való kapcsolódásra készült, a Dynamics 365 Human Resources robot felhasználója önként adhat meg egy lekérdezést, amely tartalmazza a vevői adatokat, személyes adatokat vagy más adatokat, és az ilyen lekérdezés tartalma elküldhető a LUIS szolgáltatásnak és az Azure robot keretrendszernek.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-261">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="7ccc9-262">A felhasználói lekérdezések és üzenetek tartalma legfeljebb 30 napig megmarad a LUIS rendszerben, a nyugalmi formában titkosítva van, és nincs használatban a tréningek vagy a szolgáltatások fejlesztése során.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-262">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="7ccc9-263">A Cognitive Services szolgáltatással kapcsolatban  [itt](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/) olvashat többet.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-263">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="7ccc9-264">Az Microsoft Teams-alkalmazások felügyeleti beállításainak kezeléséhez nyissa meg a [Microsoft Teams felügyeleti központot](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="7ccc9-264">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a><span data-ttu-id="7ccc9-265">Microsoft Teams, Azure Event Grid és Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="7ccc9-265">Microsoft Teams, Azure Event Grid, and Azure Cosmos DB</span></span>

<span data-ttu-id="7ccc9-266">Amikor a Microsoft Teams alkalmazásban a Dynamics 365 Human Resources alkalmazás értesítések funkcióját használja , bizonyos ügyféladatok azon a földrajzi területen kívül kerülnek, amelyen a bérlő humánerőforrás-szolgáltatását telepítették.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-266">When using the Dynamics 365 Human Resources app in Microsoft Teams, certain customer data may flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span>

<span data-ttu-id="7ccc9-267">Dynamics 365 Human Resources az alkalmazott szabadság iránti kérelmének és a munkafolyamat-feladat részleteit átküldi a Microsoft Azure Event Grid és Microsoft Teams szolgáltatásokba.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-267">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="7ccc9-268">Ezeket az adatokat a Microsoft Azure Event Grid felületen az Egyesült Államokban legfeljebb 24 óráig tárolhatjuk, és a rendszer a szállítás és tárolás során titkosítja, és a Microsoft vagy az alfeldolgozók nem használják a tanításhoz vagy szolgáltatások fejlesztéséhez.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-268">This data may be stored in Microsoft Azure Event Grid for up to 24 hours and will be processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="7ccc9-269">Annak megértéséhez, hogy az adatok a Teamsben hol vannak tárolva akkor lásd: [Adatok helye Microsoft Teams-alkalmazásban](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="7ccc9-269">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span></span>

<span data-ttu-id="7ccc9-270">Miközben a csevegőrobottal beszélget a Human Resources alkalmazásban beszélgetett, a beszélgetés tartalma lehet, hogy el lesz tárolva az Azure Cosmos DB-szolgáltatásban és át lesz adva Microsoft Teams alkalmazásnak.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-270">While conversing with the chat bot in the Human Resources app, the conversation content may be stored in Azure Cosmos DB and transmitted to Microsoft Teams.</span></span> <span data-ttu-id="7ccc9-271">Ezeket az adatokat a program legfeljebb 24 óráig tárolhatja az Azure Cosmos DB modulban, és feldolgozható azon a földrajzi régión kívül, amelyen a bérlő Human Resources szolgáltatását telepítették, a szállítás és a nyugalmi állapotban titkosítva van, és a Microsoft vagy annak alfeldolgozói nem használják a tréningek vagy szolgáltatások fejlesztése céljából.</span><span class="sxs-lookup"><span data-stu-id="7ccc9-271">This data may be stored in Azure Cosmos DB for up to 24 hours and may be processed outside of the geographic region where your tenant's Human Resources service is deployed, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="7ccc9-272">Annak megértéséhez, hogy az adatok a Teamsben hol vannak tárolva akkor lásd: [Adatok helye Microsoft Teams-alkalmazásban](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="7ccc9-272">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span></span>
 
<span data-ttu-id="7ccc9-273">Ha korlátozni szeretné a hozzáférést a szervezethez vagy a szervezeten belüli felhasználókhoz a Human Resources alkamazásban Microsoft Teams alkalmazásban, akkor lásd: [Alkalmazásengedély-irányelvek kezelése a Microsoft Teams-alkalmazásban](/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="7ccc9-273">To restrict access to the Human Resources app in Microsoft Teams for your organization or users within your organization, see [Manage app permission policies in Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="see-also"></a><span data-ttu-id="7ccc9-274">Lásd még</span><span class="sxs-lookup"><span data-stu-id="7ccc9-274">See also</span></span>

[<span data-ttu-id="7ccc9-275">A Microsoft Teams letöltése és telepítése</span><span class="sxs-lookup"><span data-stu-id="7ccc9-275">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="7ccc9-276">Microsoft Teams súgóközpont</span><span class="sxs-lookup"><span data-stu-id="7ccc9-276">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="7ccc9-277">Human Resources alkalmazás a Teamsben</span><span class="sxs-lookup"><span data-stu-id="7ccc9-277">Human Resources app in Teams</span></span>](hr-admin-teams-leave-app.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]