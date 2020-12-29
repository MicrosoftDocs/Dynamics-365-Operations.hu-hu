---
title: Szabadság- és távollétkérelmek kezelése a Teams alkalmazásban
description: Ez a témakör azt mutatja be, hogyan lehet szabadságot kérelmezni a Dynamics 365 Human Resources alkalmazásban a Microsoft Teams rendszerben.
author: andreabichsel
manager: AnnBe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
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
ms.openlocfilehash: d24c257054578282f1a2eafa050094194a358aa0
ms.sourcegitcommit: 369639cd92e03fe792ed9d61a329d842aafa052f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2020
ms.locfileid: "4418936"
---
# <a name="manage-leave-requests-in-teams"></a><span data-ttu-id="f7c56-103">Szabadság- és távollétkérelmek kezelése a Teams alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="f7c56-103">Manage leave requests in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="f7c56-104">A Microsoft Dynamics 365 Human Resources alkalmazás a Microsoft Teams rendszerben lehetővé teszi, hogy gyorsan kérelmezzen szabadságot, és megtekintse a szabadságegyenlegét közvetlenül a Microsoft Teams rendszerben.</span><span class="sxs-lookup"><span data-stu-id="f7c56-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets you quickly request time off and view your time-off balance information right in Microsoft Teams.</span></span> <span data-ttu-id="f7c56-105">A robottal együttműködhet a szükséges adatok lekéréséhez és a szabadságkérelem elindításához.</span><span class="sxs-lookup"><span data-stu-id="f7c56-105">You can interact with a bot to request information and start a leave request.</span></span> <span data-ttu-id="f7c56-106">A **Szabadság** lapon részletesebb információk olvashatók.</span><span class="sxs-lookup"><span data-stu-id="f7c56-106">The **Time off** tab provides more detailed information.</span></span> <span data-ttu-id="f7c56-107">A közelgő szabadságairól is információkat küldhet az embereknek a Teamsben és a Human Resources alkalmazáson kívüli csevegőfelületeken.</span><span class="sxs-lookup"><span data-stu-id="f7c56-107">You can also send people information about your upcoming time off in teams and chats outside the Human Resources app.</span></span>

## <a name="install-the-app"></a><span data-ttu-id="f7c56-108">Az alkalmazás telepítése</span><span class="sxs-lookup"><span data-stu-id="f7c56-108">Install the app</span></span>

<span data-ttu-id="f7c56-109">A Human Resources app a Teams áruházban található.</span><span class="sxs-lookup"><span data-stu-id="f7c56-109">You can find the Human Resources app in the Teams store.</span></span>

1. <span data-ttu-id="f7c56-110">A Microsoft Teams rendszerben válassza ki a három pontot.</span><span class="sxs-lookup"><span data-stu-id="f7c56-110">In Microsoft Teams, select the ellipses.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás három pontja](./media/hr-teams-leave-app-ellipses.png)
 
2. <span data-ttu-id="f7c56-112">Keresse meg a Dynamics 365 Human Resources alkalmazást, majd válassza ki a **Human Resources** címet.</span><span class="sxs-lookup"><span data-stu-id="f7c56-112">Search for Dynamics 365 Human Resources, and then select the **Human Resources** tile.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás HR címe](./media/hr-teams-leave-app-human-resources-tile.png)

3. <span data-ttu-id="f7c56-114">Válassza a **Hozzáadás** gombot az alkalmazás telepítéséhez.</span><span class="sxs-lookup"><span data-stu-id="f7c56-114">Select the **Add** button to install the app.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás telepítése](./media/hr-teams-leave-app-in-store.png)

<span data-ttu-id="f7c56-116">Ha az alkalmazás nem lépteti be automatikusan, válassza a **Beállítás** lapot a bejelentkezéshez.</span><span class="sxs-lookup"><span data-stu-id="f7c56-116">If the app doesn't automatically sign you in, select the **Settings** tab to sign in.</span></span>

![Human Resources Teams szabadságkezelő alkalmazás Beállítások lap](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> <span data-ttu-id="f7c56-118">Ha nem jelenik meg a bejelentkezési párbeszédpanel, ellenőrizze, hogy az előugró ablakok engedélyezve vannak-e a böngésző beállításaiban.</span><span class="sxs-lookup"><span data-stu-id="f7c56-118">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span> 

<span data-ttu-id="f7c56-119">Ha egynél több Human Resources-példányhoz van hozzáférése, akkor a **Beállítások** lapon kiválaszthatja, hogy melyik környezethez kíván csatlakozni.</span><span class="sxs-lookup"><span data-stu-id="f7c56-119">If you have access to more than one instance of Human Resources, you can select which environment you want to connect to in the **Settings** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="f7c56-120">Az alkalmazás most már támogatja a Rendszergazda biztonsági szerepkört.</span><span class="sxs-lookup"><span data-stu-id="f7c56-120">The app now supports the System Administrator security role.</span></span>
 
## <a name="use-the-bot"></a><span data-ttu-id="f7c56-121">A robot használata</span><span class="sxs-lookup"><span data-stu-id="f7c56-121">Use the bot</span></span>

<span data-ttu-id="f7c56-122">Az alkalmazás telepítése után egy üdvözlő üzenet jelenik meg, amely ismerteti, hogy milyen típusú intézkedéseket tehet a robot az Ön nevében.</span><span class="sxs-lookup"><span data-stu-id="f7c56-122">After the app installs, a welcome message appears, letting you know the types of actions the bot can take on your behalf.</span></span>

![Human Resources Teams szabadságkezelő alkalmazás robot üdvözlőüzenete](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> <span data-ttu-id="f7c56-124">A robottal való első interakciót követően szükség lehet a bejelentkezésre.</span><span class="sxs-lookup"><span data-stu-id="f7c56-124">When first interacting with the bot, you might need to sign in.</span></span> <span data-ttu-id="f7c56-125">Ha nem jelenik meg a bejelentkezési párbeszédpanel, ellenőrizze, hogy az előugró ablakok engedélyezve vannak-e a böngésző beállításaiban.</span><span class="sxs-lookup"><span data-stu-id="f7c56-125">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span>

<span data-ttu-id="f7c56-126">A robot a következőre kérhető:</span><span class="sxs-lookup"><span data-stu-id="f7c56-126">You can ask the bot to:</span></span>

- <span data-ttu-id="f7c56-127">Az egyes regisztrált szabadságtípusokhoz tartozó szabadságegyenleg-információk megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="f7c56-127">Show time-off balance information for each leave type you're enrolled in.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás egyenlegek megjelenítése](./media/hr-teams-leave-app-bot-balances.png)
 
- <span data-ttu-id="f7c56-129">Egy adott szabadságtípussal kapcsolatos további részletek megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="f7c56-129">Show additional details about a specific leave type.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás részletes adatok megjelenítése](./media/hr-teams-leave-app-bot-details.png)

- <span data-ttu-id="f7c56-131">Szabadságkérelem indítása az Ön számára.</span><span class="sxs-lookup"><span data-stu-id="f7c56-131">Start a leave request for you.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás szabadság kérelmezése](./media/hr-teams-leave-app-bot-request.png)
 
<span data-ttu-id="f7c56-133">A szabadságkérelem elindítását követően a napokat közvetlenül a kártyán állíthatja be.</span><span class="sxs-lookup"><span data-stu-id="f7c56-133">After you start a leave request, you can adjust the days right within the card.</span></span>

![Human Resources Teams szabadságkezelő alkalmazás kérelem szerkesztése](./media/hr-teams-leave-app-bot-edit.png)
 
<span data-ttu-id="f7c56-135">Ha befejezte az adatok megadását, válassza az **Elküldés** lehetőséget, hogy elküldje jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="f7c56-135">When you're done entering information, select **Submit** to submit it for approval.</span></span> <span data-ttu-id="f7c56-136">Választhatja a **Mentés piszkozatként** lehetőséget is, hogy később visszatérhessen hozzá.</span><span class="sxs-lookup"><span data-stu-id="f7c56-136">You can also select **Save as draft** to come back to it later.</span></span>

![Human Resources Teams szabadságkezelő alkalmazás kérelem elküldése](./media/hr-teams-leave-app-bot-submit.png)

## <a name="manage-your-leave-in-teams"></a><span data-ttu-id="f7c56-138">Távollét kezelése a Teams alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="f7c56-138">Manage your leave in Teams</span></span>

<span data-ttu-id="f7c56-139">A **Szabadság** lapon a következők jeleníthetők meg:</span><span class="sxs-lookup"><span data-stu-id="f7c56-139">The **Time off** tab allows you to view:</span></span>

- <span data-ttu-id="f7c56-140">Az egyes regisztrált szabadságtípusokhoz tartozó egyenleg-információk</span><span class="sxs-lookup"><span data-stu-id="f7c56-140">Balance information for each leave type you're enrolled in</span></span>

- <span data-ttu-id="f7c56-141">Várható szabadságkérelmek</span><span class="sxs-lookup"><span data-stu-id="f7c56-141">Upcoming leave requests</span></span>

- <span data-ttu-id="f7c56-142">Szabadságkérelmek</span><span class="sxs-lookup"><span data-stu-id="f7c56-142">Time-off requests</span></span>

- <span data-ttu-id="f7c56-143">Vázlat szabadságkérelmek</span><span class="sxs-lookup"><span data-stu-id="f7c56-143">Draft leave requests</span></span>

![Human Resources Teams szabadságkezelő alkalmazás Szabadság lap](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a><span data-ttu-id="f7c56-145">Új kérelem létrehozása</span><span class="sxs-lookup"><span data-stu-id="f7c56-145">Create a new request</span></span>

1. <span data-ttu-id="f7c56-146">Új szabadségkérelem létrehozásához válassza az **Új kérelem** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f7c56-146">To create a new leave request, select **New request**.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás Új kérelem](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. <span data-ttu-id="f7c56-148">Adja meg a kivenni kívánt napot vagy napokat, majd válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f7c56-148">Enter the day or days you want to take off, and then select **Add**.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás szabadság hozzáadása](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. <span data-ttu-id="f7c56-150">Ha szükséges, írjon be egy okkódot.</span><span class="sxs-lookup"><span data-stu-id="f7c56-150">If applicable, enter a reason code.</span></span> <span data-ttu-id="f7c56-151">Adjon meg bármilyen megjegyzést, és vegyen fel hozzá mellékleteket.</span><span class="sxs-lookup"><span data-stu-id="f7c56-151">Also enter any comments and add any attachments.</span></span>

4. <span data-ttu-id="f7c56-152">Ha befejezte az adatok megadását, írja be az **Elküldés** kifejezést, hogy elküldje jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="f7c56-152">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="f7c56-153">Beírhatja a **Mentés piszkozatként** kifejezést is, hogy később visszatérhessen hozzá.</span><span class="sxs-lookup"><span data-stu-id="f7c56-153">You can also type **Save as draft** to come back to it later.</span></span>

### <a name="manage-draft-requests"></a><span data-ttu-id="f7c56-154">Vázlat kérelmek kezelése</span><span class="sxs-lookup"><span data-stu-id="f7c56-154">Manage draft requests</span></span>

1. <span data-ttu-id="f7c56-155">Válassza ki a **Vázlatok** lapot.</span><span class="sxs-lookup"><span data-stu-id="f7c56-155">Select the **Drafts** tab.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás Vázlatok lap](./media/hr-teams-leave-app-drafts-tab.png)

2. <span data-ttu-id="f7c56-157">A kérelem szerkesztéséhez válassza ki a ceruzát, vagy válassza ki a szemétkosarat a kérelem törléséhez.</span><span class="sxs-lookup"><span data-stu-id="f7c56-157">Select the pencil to edit the request, or select the trash can to delete the request.</span></span>

3. <span data-ttu-id="f7c56-158">Hajtsa végre a szükséges módosításokat.</span><span class="sxs-lookup"><span data-stu-id="f7c56-158">Make any necessary changes.</span></span> <span data-ttu-id="f7c56-159">Ha befejezte az adatok megadását, írja be az **Elküldés** kifejezést, hogy elküldje jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="f7c56-159">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="f7c56-160">Választhatja a **Mentés piszkozatként** lehetőséget is, hogy később visszatérhessen hozzá.</span><span class="sxs-lookup"><span data-stu-id="f7c56-160">You can also select **Save as draft** to come back to it later.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás vázlat szerkesztése](./media/hr-teams-leave-app-drafts-edit.png)
   
### <a name="respond-to-teams-notifications"></a><span data-ttu-id="f7c56-162">Válaszadás a Teams értesítéseire</span><span class="sxs-lookup"><span data-stu-id="f7c56-162">Respond to Teams notifications</span></span>

<span data-ttu-id="f7c56-163">Ha Ön vagy egy olyan dolgozó, akinek Ön jóváhagyója a szabadságkérelmet küld be, akkor a Teamsben értesítést kap a Human Resources alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="f7c56-163">When you or a worker you're an approver for submits a leave request, you'll receive a notification in the Human Resources app in Teams.</span></span> <span data-ttu-id="f7c56-164">A megtekintéséhez kiválaszthatja az értesítést.</span><span class="sxs-lookup"><span data-stu-id="f7c56-164">You can select the notification to view it.</span></span> <span data-ttu-id="f7c56-165">Az értesítések megjelennek a **Csevegés** területen is.</span><span class="sxs-lookup"><span data-stu-id="f7c56-165">Notifications also appear in the **Chat** area.</span></span>

<span data-ttu-id="f7c56-166">Ha a jóváhagyó, akkor az értesítésben kiválaszthatja a **Jóváhagyás** vagy **Elutasítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f7c56-166">If you're an approver, you can select **Approve** or **Deny** in the notification.</span></span> <span data-ttu-id="f7c56-167">Egy opcionális üzenetet is megadhat.</span><span class="sxs-lookup"><span data-stu-id="f7c56-167">You can also provide an optional message.</span></span>

![Szabadságkérelem értesítése a Human Resources Teams alkalmazásban](./media/hr-teams-leave-app-notification.png)

## <a name="send-upcoming-time-off-information-to-your-coworkers"></a><span data-ttu-id="f7c56-169">Várható szabadságadatok küldése a munkatársai számára</span><span class="sxs-lookup"><span data-stu-id="f7c56-169">Send upcoming time-off information to your coworkers</span></span>

<span data-ttu-id="f7c56-170">Miután telepítette az Human Resources alkalmazást a Teams számára, egyszerűen küldhet információt a Teamsben vagy csevegésekben a munkatársai számára.</span><span class="sxs-lookup"><span data-stu-id="f7c56-170">After you install the Human Resources app for Teams, you can easily send information about your upcoming time off to your coworkers in teams or chats.</span></span>

1. <span data-ttu-id="f7c56-171">Egy csapatban vagy csevegésben a Teamsben válassza a chat ablak alatti Human Resources gombot.</span><span class="sxs-lookup"><span data-stu-id="f7c56-171">In a team or chat in Teams, select the Human Resources button below the chat window.</span></span>

   ![A chat ablak alatti Human Resources gomb](./media/hr-teams-leave-app-chat-button.png)

2. <span data-ttu-id="f7c56-173">Válassza ki a megosztani kívánt szabadságkérelmet.</span><span class="sxs-lookup"><span data-stu-id="f7c56-173">Select the leave request you want to share.</span></span> <span data-ttu-id="f7c56-174">Ha meg szeretné osztani egy vázlat szabadságkérelmet, először válassza a **Vázlatok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f7c56-174">If you want to share a draft leave request, select **Drafts** first.</span></span>

   ![Egy közelgő szabadságkérelem kiválasztása megosztásra](./media/hr-teams-leave-app-chat-search.png)

<span data-ttu-id="f7c56-176">A szabadságkérelem a csevegésben fog megjelenni.</span><span class="sxs-lookup"><span data-stu-id="f7c56-176">Your leave request will display in the chat.</span></span>

![A Human Resources szabadságkérelem kártya](./media/hr-teams-leave-app-chat-card.png)

<span data-ttu-id="f7c56-178">Ha megosztott egy vázlat állapotú kérelmet, akkor a program vázlatként jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="f7c56-178">If you shared a draft request, it will display as a draft:</span></span>

![A Human Resources vázlat szabadságkérelem kártya](./media/hr-teams-leave-app-chat-draft-card.png)

## <a name="view-your-teams-leave-calendar"></a><span data-ttu-id="f7c56-180">A csapata szabadságnaptárának megtekintése</span><span class="sxs-lookup"><span data-stu-id="f7c56-180">View your team's leave calendar</span></span>

<span data-ttu-id="f7c56-181">Ha Ön közvetlen beosztottakkal rendelkező vezető, akkor megtekintheti a csoport jóváhagyott és függőben távolléteit.</span><span class="sxs-lookup"><span data-stu-id="f7c56-181">If you're a manager with direct reports, you can view your team's approved and pending time off.</span></span>

1. <span data-ttu-id="f7c56-182">A Teamsben a Human Resources alkalmazásban válassza a **Távollét** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f7c56-182">In the Human Resources app in Teams, select **Time off**.</span></span>

2. <span data-ttu-id="f7c56-183">Válassza ki a **Csoport naptárát**.</span><span class="sxs-lookup"><span data-stu-id="f7c56-183">Select **Team calendar**.</span></span>

   ![Naptár megtekintése a Human Resources Teams alkalmazásban](./media/hr-teams-leave-app-view-calendar.png)

<span data-ttu-id="f7c56-185">A naptárban a közvetlen beosztottjai jóváhagyott és a függőben lévő távollétei láthatók.</span><span class="sxs-lookup"><span data-stu-id="f7c56-185">The calendar displays your direct reports' approved and pending time off.</span></span>

![Távolléti naptár a Human Resources Teams alkalmazásban](./media/hr-teams-leave-app-calendar.png)

## <a name="troubleshooting"></a><span data-ttu-id="f7c56-187">Hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="f7c56-187">Troubleshooting</span></span>

<span data-ttu-id="f7c56-188">Ha nem sikerül bejelentkeznie a Human Resources Teams alkalmazásba vagy nem tudja használni, próbálja ki ezeket a hibaelhárítási utasításokat.</span><span class="sxs-lookup"><span data-stu-id="f7c56-188">If you're having trouble signing into or using the Human Resources Teams app, try following these troubleshooting instructions.</span></span> <span data-ttu-id="f7c56-189">Ha a hibaelhárítás után sem oldódott meg a probléma, akkor forduljon a támogatáshoz.</span><span class="sxs-lookup"><span data-stu-id="f7c56-189">If you're still having problems after troubleshooting, contact Support.</span></span> <span data-ttu-id="f7c56-190">További információért lásd a [Támogatás kérése](hr-admin-troubleshooting-support.md) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f7c56-190">For more information, see [Get support](hr-admin-troubleshooting-support.md).</span></span>

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a><span data-ttu-id="f7c56-191">Nem lehet bejelentkezni a Human Resources alkalmazásba a Teamsben.</span><span class="sxs-lookup"><span data-stu-id="f7c56-191">Can't sign into the Human Resources app in Teams</span></span>

<span data-ttu-id="f7c56-192">Ha nem tud bejelentkezni az alkalmazásba, akkor előfordulhat, hogy a Microsoft Teamsbe való bejelentkezéshez használt fiók nincs alkalmazotti rekordhoz társítva a Dynamics 365 Human Resources alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="f7c56-192">If you can't sign into the app, it's possible that the account you're using to sign into Microsoft Teams isn't associated with an employee record in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="f7c56-193">Forduljon a rendszergazdához, és ellenőrizze, hogy az alkalmazotti rekord helyesen van-e társítva.</span><span class="sxs-lookup"><span data-stu-id="f7c56-193">Contact your system administrator to ensure your employee record is correctly associated.</span></span>

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a><span data-ttu-id="f7c56-194">Hiba történt a Teamsen belüli Human Resource alkalmazásban a szabadságkérelmek jóváhagyásakor.</span><span class="sxs-lookup"><span data-stu-id="f7c56-194">Error when approving leave requests in the Human Resources app in Teams</span></span>

<span data-ttu-id="f7c56-195">Ha hibaüzenetet kap, amikor megpróbálja jóváhagyni a szabadságkérelmeket a Teams alkalmazásban, próbálja végrehajtani a következő hibaelhárítási lépéseket:</span><span class="sxs-lookup"><span data-stu-id="f7c56-195">If you receive an error when you're trying to approve leave requests in the Teams app, try the following troubleshooting steps:</span></span>

1. <span data-ttu-id="f7c56-196">Ellenőrizze, hogy a Microsoft Teamsbe való bejelentkezéshez használt fiók megegyezik-e a Dynamics 365 Human Resources eléréséhez használt fiókkal.</span><span class="sxs-lookup"><span data-stu-id="f7c56-196">Verify that the account you're using to sign into Microsoft Teams is the same one you use for accessing Dynamics 365 Human Resources.</span></span>

2. <span data-ttu-id="f7c56-197">Ellenőrizze, hogy Ön-e a kérelem érvényes jóváhagyója a szabadság jóváhagyására vonatkozó munkafolyamaton belüli beállítások ellenőrzésével.</span><span class="sxs-lookup"><span data-stu-id="f7c56-197">Verify that you're a valid approver for the request by checking the workflow settings for leave approval.</span></span> <span data-ttu-id="f7c56-198">A szabadságkérelem munkafolyamatairól további tudnivalókért lásd: [Szabadságkérelmezési munkafolyamat létrehozása](hr-leave-and-absence-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="f7c56-198">For more information about leave request workflows, see [Create a leave request workflow](hr-leave-and-absence-workflow.md).</span></span>

## <a name="known-accessibility-issues"></a><span data-ttu-id="f7c56-199">Ismert kisegítő lehetőségekkel kapcsolatos problémák</span><span class="sxs-lookup"><span data-stu-id="f7c56-199">Known accessibility issues</span></span>

<span data-ttu-id="f7c56-200">A Teams Human Resources alkalmazásában a következőak adálymentességgel kapcsolatos problémák tapasztalhatók amelyeket a későbbi kiadásokban kijavítunk.</span><span class="sxs-lookup"><span data-stu-id="f7c56-200">The Human Resources app in Teams has the following accessibility issues that we're working on fixing in future releases.</span></span>

| <span data-ttu-id="f7c56-201">Kiadás</span><span class="sxs-lookup"><span data-stu-id="f7c56-201">Issue</span></span> | <span data-ttu-id="f7c56-202">Megoldás vagy magyarázat</span><span class="sxs-lookup"><span data-stu-id="f7c56-202">Workaround or explanation</span></span> |
| --- | --- |
| <span data-ttu-id="f7c56-203">Ha az asztalon 400%-ra nagyít, a műveletgombok egy része kikerül a képből.</span><span class="sxs-lookup"><span data-stu-id="f7c56-203">Zooming to 400% on desktop hides some of the action buttons from view.</span></span> | <span data-ttu-id="f7c56-204">Ehelyett azt javasoljuk, hogy használja a nagyítót, amíg nem tudjuk támogatni ezt a nagyítási szintet.</span><span class="sxs-lookup"><span data-stu-id="f7c56-204">We recommend using a magnifier instead until we can support this zoom level.</span></span> |
| <span data-ttu-id="f7c56-205">A **Szabadságolás** lapon a Narrátor egy gombműveletet jelent be, miközben elolvassa a szabadságolás rács fejlécét.</span><span class="sxs-lookup"><span data-stu-id="f7c56-205">On the **Time off** tab, voiceover announces a button action while reading the header for the time-off grid.</span></span> | <span data-ttu-id="f7c56-206">A rács fejléce és elemei év szerint vannak csoportosítva, és összecsukhatók.</span><span class="sxs-lookup"><span data-stu-id="f7c56-206">The header and elements within the grid are grouped by year, and they're collapsible.</span></span> <span data-ttu-id="f7c56-207">A Narrátor ezt végrehajtható elemként értelmezi, de valójában nem az.</span><span class="sxs-lookup"><span data-stu-id="f7c56-207">Voiceover interprets this as an actionable item, but it isn't.</span></span> |
| <span data-ttu-id="f7c56-208">Ha pöccint, miközben egy előugró ablak vagy menü meg van nyitva, a Narrátor kihagyja a felugró ablak vagy a menü tartalmának olvasását.</span><span class="sxs-lookup"><span data-stu-id="f7c56-208">If you swipe while a popup or menu is open, voiceover skips reading the popup or menu contents.</span></span> | <span data-ttu-id="f7c56-209">Fedezze fel a tartalmat az ujjszkenneléssel.</span><span class="sxs-lookup"><span data-stu-id="f7c56-209">Explore the content using finger scanning.</span></span> |
| <span data-ttu-id="f7c56-210">A **Szabadságolás** lapon egy további pöccintési kézmozdulat jelenik meg, amikor egy új kérelemben az **Okkódra** navigál.</span><span class="sxs-lookup"><span data-stu-id="f7c56-210">On the **Time off** tab, there's an extra swipe gesture when navigating to **Reason code** in a new request.</span></span> | <span data-ttu-id="f7c56-211">Nincs olyan rejtett vezérlő, amelyhez a pöccintési navigáció megpróbálna eljutni.</span><span class="sxs-lookup"><span data-stu-id="f7c56-211">There is no hidden control that the swipe navigation is trying to get to.</span></span> |
| <span data-ttu-id="f7c56-212">Ha a **Szabadságolás** lapon pöccint, miközben a naptár meg van nyitva, akkor a vezérlőn kívülre kerül, nem pedig egy új kérés tetejére, vagy egy kérés szerkesztése közben.</span><span class="sxs-lookup"><span data-stu-id="f7c56-212">On the **Time off** tab, if you swipe while the calendar is open, you end up outside the control instead of at the top in a new request or while editing a request.</span></span> | <span data-ttu-id="f7c56-213">Amikor eléri az **Ugrás a mai napra** elemet, vegye úgy, hogy elért a vezérlő végére, és pöccintsen az ellenkező irányba, hogy visszakerüljön felülre.</span><span class="sxs-lookup"><span data-stu-id="f7c56-213">When you reach **Go to today**, consider that to be the end of the control and swipe in the reverse direction to get back to the top.</span></span> |
| <span data-ttu-id="f7c56-214">A Narrátor nem olvassa el a dátumok címkéit.</span><span class="sxs-lookup"><span data-stu-id="f7c56-214">Voiceover doesn't read the labels for dates.</span></span> | <span data-ttu-id="f7c56-215">A párokban előforduló dátumok mindig **Kezdő dátum** és **Záró dátum**.</span><span class="sxs-lookup"><span data-stu-id="f7c56-215">The dates encountered in pairs are always **Start date** and **End date**.</span></span> |
| <span data-ttu-id="f7c56-216">A **Csevegés** lapon a fókusz visszaugrik a képernyő tetejére, amikor dátumot ad meg a kisegítő eszközt vagy a billentyűzetes navigációt használja.</span><span class="sxs-lookup"><span data-stu-id="f7c56-216">On the **Chat** tab, the focus jumps back to the top when you enter a date while using the assistive tool or keyboard navigation.</span></span> | <span data-ttu-id="f7c56-217">Használja a Tab billentyűt addig, amíg újra el nem éri a beviteli területet.</span><span class="sxs-lookup"><span data-stu-id="f7c56-217">Tab until you reach your input area again.</span></span> |

## <a name="privacy-notice"></a><span data-ttu-id="f7c56-218">Adatvédelmi nyilatkozat</span><span class="sxs-lookup"><span data-stu-id="f7c56-218">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="f7c56-219">Microsoft Language Understanding Intelligent Service (LUIS)</span><span class="sxs-lookup"><span data-stu-id="f7c56-219">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="f7c56-220">A Microsoft Teams rendszer Dynamics 365 Human Resources robotjával elemezhetők a felhasználó szöveges bemenetei az alapul szolgáló kérdés/szándék megértéséhez.</span><span class="sxs-lookup"><span data-stu-id="f7c56-220">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="f7c56-221">A felhasználó bemenete (például a „Contoso fiók keresése”) a Microsoft egyik kognitív szolgáltatásához, a Language Understanding Intelligent Service (LUIS) szolgáltatáshoz van irányítva.</span><span class="sxs-lookup"><span data-stu-id="f7c56-221">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="f7c56-222">A LUIS-ról  [itt](https://www.luis.ai/) olvashat többet.</span><span class="sxs-lookup"><span data-stu-id="f7c56-222">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="f7c56-223">A LUIS szolgáltatás egyértelműsíti vagy megérti a felhasználói bevitel szándékát (ebben az esetben a szándék az, hogy információt találjon) és a cél entitást (ebben az esetben a szándékolt entitás egy Contoso nevű számla).</span><span class="sxs-lookup"><span data-stu-id="f7c56-223">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="f7c56-224">Ez az információ ezután a Microsoft  [Azure bot keretrendszerébe](https://azure.microsoft.com/services/bot-service/) kerül, amely kapcsolatba lép a Dynamics 365 Human Resources adataival, és lekéri a kívánt információkat a felhasználói lekérdezéshez.</span><span class="sxs-lookup"><span data-stu-id="f7c56-224">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="f7c56-225">A robot telepítésével és a használatához való hozzáférés engedélyezésével Ön elfogadja, hogy a LUIS szolgáltatás és az Azure robot keretrendszer feldolgozza a bemenet mögötti szándékot, ami egy továbbfejlesztett, társalgásszerű felhasználói élményt eredményez.</span><span class="sxs-lookup"><span data-stu-id="f7c56-225">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="f7c56-226">A LUIS szolgáltatás és az Azure robot keretrendszer különböző szintű megfeleléssel rendelkezhet a Dynamics 365 Human Resources alkalmazáshoz képest.</span><span class="sxs-lookup"><span data-stu-id="f7c56-226">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="f7c56-227">Noha a LUIS szolgáltatás csak a felhasználói lekérdezésekhez férhet hozzá, és nem a felhasználó Dynamics 365 Human Resources adataihoz vagy fiókjához való kapcsolódásra készült, a Dynamics 365 Human Resources robot felhasználója önként adhat meg egy lekérdezést, amely tartalmazza a vevői adatokat, személyes adatokat vagy más adatokat, és az ilyen lekérdezés tartalma elküldhető a LUIS szolgáltatásnak és az Azure robot keretrendszernek.</span><span class="sxs-lookup"><span data-stu-id="f7c56-227">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="f7c56-228">A felhasználói lekérdezések és üzenetek tartalma legfeljebb 30 napig megmarad a LUIS rendszerben, a nyugalmi formában titkosítva van, és nincs használatban a tréningek vagy a szolgáltatások fejlesztése során.</span><span class="sxs-lookup"><span data-stu-id="f7c56-228">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="f7c56-229">A Cognitive Services szolgáltatással kapcsolatban  [itt](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/) olvashat többet.</span><span class="sxs-lookup"><span data-stu-id="f7c56-229">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="f7c56-230">Az Microsoft Teams-alkalmazások felügyeleti beállításainak kezeléséhez nyissa meg a [Microsoft Teams felügyeleti központot](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="f7c56-230">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a><span data-ttu-id="f7c56-231">Microsoft Teams, Azure Event Grid és Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="f7c56-231">Microsoft Teams, Azure Event Grid, and Azure Cosmos DB</span></span>

<span data-ttu-id="f7c56-232">Amikor a Microsoft Teams alkalmazásban a Dynamics 365 Human Resources alkalmazás értesítések funkcióját használja , bizonyos ügyféladatok azon a földrajzi területen kívül kerülnek, amelyen a bérlő humánerőforrás-szolgáltatását telepítették.</span><span class="sxs-lookup"><span data-stu-id="f7c56-232">When using the Dynamics 365 Human Resources app in Microsoft Teams, certain customer data may flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span>

<span data-ttu-id="f7c56-233">Dynamics 365 Human Resources az alkalmazott szabadság iránti kérelmének és a munkafolyamat-feladat részleteit átküldi a Microsoft Azure Event Grid és Microsoft Teams szolgáltatásokba.</span><span class="sxs-lookup"><span data-stu-id="f7c56-233">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="f7c56-234">Ezeket az adatokat a Microsoft Azure Event Grid felületen az Egyesült Államokban legfeljebb 24 óráig tárolhatjuk, és a rendszer a szállítás és tárolás során titkosítja, és a Microsoft vagy az alfeldolgozók nem használják a tanításhoz vagy szolgáltatások fejlesztéséhez.</span><span class="sxs-lookup"><span data-stu-id="f7c56-234">This data may be stored in Microsoft Azure Event Grid for up to 24 hours and will be processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="f7c56-235">Annak megértéséhez, hogy az adatok a Teamsben hol vannak tárolva akkor lásd: [Adatok helye Microsoft Teams-alkalmazásban](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="f7c56-235">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>

<span data-ttu-id="f7c56-236">Miközben a csevegőrobottal beszélget a Human Resources alkalmazásban beszélgetett, a beszélgetés tartalma lehet, hogy el lesz tárolva az Azure Cosmos DB-szolgáltatásban és át lesz adva Microsoft Teams alkalmazásnak.</span><span class="sxs-lookup"><span data-stu-id="f7c56-236">While conversing with the chat bot in the Human Resources app, the conversation content may be stored in Azure Cosmos DB and transmitted to Microsoft Teams.</span></span> <span data-ttu-id="f7c56-237">Ezeket az adatokat a program legfeljebb 24 óráig tárolhatja az Azure Cosmos DB modulban, és feldolgozható azon a földrajzi régión kívül, amelyen a bérlő Human Resources szolgáltatását telepítették, a szállítás és a nyugalmi állapotban titkosítva van, és a Microsoft vagy annak alfeldolgozói nem használják a tréningek vagy szolgáltatások fejlesztése céljából.</span><span class="sxs-lookup"><span data-stu-id="f7c56-237">This data may be stored in Azure Cosmos DB for up to 24 hours and may be processed outside of the geographic region where your tenant's Human Resources service is deployed, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="f7c56-238">Annak megértéséhez, hogy az adatok a Teamsben hol vannak tárolva akkor lásd: [Adatok helye Microsoft Teams-alkalmazásban](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="f7c56-238">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>
 
<span data-ttu-id="f7c56-239">Ha korlátozni szeretné a hozzáférést a szervezethez vagy a szervezeten belüli felhasználókhoz a Human Resources alkamazásban Microsoft Teams alkalmazásban, akkor lásd: [Alkalmazásengedély-irányelvek kezelése a Microsoft Teams-alkalmazásban](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="f7c56-239">To restrict access to the Human Resources app in Microsoft Teams for your organization or users within your organization, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="see-also"></a><span data-ttu-id="f7c56-240">Lásd még</span><span class="sxs-lookup"><span data-stu-id="f7c56-240">See also</span></span>

[<span data-ttu-id="f7c56-241">A Microsoft Teams letöltése és telepítése</span><span class="sxs-lookup"><span data-stu-id="f7c56-241">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="f7c56-242">Microsoft Teams súgóközpont</span><span class="sxs-lookup"><span data-stu-id="f7c56-242">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="f7c56-243">Human Resources alkalmazás a Teamsben</span><span class="sxs-lookup"><span data-stu-id="f7c56-243">Human Resources app in Teams</span></span>](hr-admin-teams-leave-app.md)
