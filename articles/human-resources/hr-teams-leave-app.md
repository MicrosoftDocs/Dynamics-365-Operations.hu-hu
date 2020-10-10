---
title: Szabadság- és távollétkérelmek kezelése a Teams alkalmazásban
description: Ez a témakör azt mutatja be, hogyan lehet szabadságot kérelmezni a Dynamics 365 Human Resources alkalmazásban a Microsoft Teams rendszerben.
author: andreabichsel
manager: AnnBe
ms.date: 09/03/2020
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
ms.openlocfilehash: c7b74983cbddf661456b0a65939e272078d59f6d
ms.sourcegitcommit: e27510ba52623c801353eed4853f8c0aeea3bb2d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/22/2020
ms.locfileid: "3828944"
---
# <a name="manage-leave-requests-in-teams"></a><span data-ttu-id="f1936-103">Szabadság- és távollétkérelmek kezelése a Teams alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="f1936-103">Manage leave requests in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="f1936-104">A Microsoft Dynamics 365 Human Resources alkalmazás a Microsoft Teams rendszerben lehetővé teszi, hogy gyorsan kérelmezzen szabadságot, és megtekintse a szabadságegyenlegét közvetlenül a Microsoft Teams rendszerben.</span><span class="sxs-lookup"><span data-stu-id="f1936-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets you quickly request time off and view your time-off balance information right in Microsoft Teams.</span></span> <span data-ttu-id="f1936-105">A robottal együttműködhet a szükséges adatok lekéréséhez és a szabadságkérelem elindításához.</span><span class="sxs-lookup"><span data-stu-id="f1936-105">You can interact with a bot to request information and start a leave request.</span></span> <span data-ttu-id="f1936-106">A **Szabadság** lapon részletesebb információk olvashatók.</span><span class="sxs-lookup"><span data-stu-id="f1936-106">The **Time off** tab provides more detailed information.</span></span> <span data-ttu-id="f1936-107">Ezenkívül a közelgő szabadságairól információkat küldhet az embereknek a Teamsben és a Human Resources alkalmazáson kívüli csevegőfelületeken.</span><span class="sxs-lookup"><span data-stu-id="f1936-107">In addition, you can send people information about your upcoming time off in teams and chats outside the Human Resources app.</span></span>

## <a name="install-the-app"></a><span data-ttu-id="f1936-108">Az alkalmazás telepítése</span><span class="sxs-lookup"><span data-stu-id="f1936-108">Install the app</span></span>

<span data-ttu-id="f1936-109">A Human Resources app a Teams áruházban található.</span><span class="sxs-lookup"><span data-stu-id="f1936-109">You can find the Human Resources app in the Teams store.</span></span>

1. <span data-ttu-id="f1936-110">A Microsoft Teams rendszerben válassza ki a három pontot.</span><span class="sxs-lookup"><span data-stu-id="f1936-110">In Microsoft Teams, select the ellipses.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás három pontja](./media/hr-teams-leave-app-ellipses.png)
 
2. <span data-ttu-id="f1936-112">Keresse meg a Dynamics 365 Human Resources alkalmazást, majd válassza ki a **Human Resources** címet.</span><span class="sxs-lookup"><span data-stu-id="f1936-112">Search for Dynamics 365 Human Resources, and then select the **Human Resources** tile.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás HR címe](./media/hr-teams-leave-app-human-resources-tile.png)

3. <span data-ttu-id="f1936-114">Válassza a **Hozzáadás** gombot az alkalmazás telepítéséhez.</span><span class="sxs-lookup"><span data-stu-id="f1936-114">Select the **Add** button to install the app.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás telepítése](./media/hr-teams-leave-app-in-store.png)

<span data-ttu-id="f1936-116">Ha az alkalmazás nem lépteti be automatikusan, válassza a **Beállítás** lapot a bejelentkezéshez.</span><span class="sxs-lookup"><span data-stu-id="f1936-116">If the app doesn't automatically sign you in, select the **Settings** tab to sign in.</span></span>

![Human Resources Teams szabadságkezelő alkalmazás Beállítások lap](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> <span data-ttu-id="f1936-118">Ha nem jelenik meg a bejelentkezési párbeszédpanel, ellenőrizze, hogy az előugró ablakok engedélyezve vannak-e a böngésző beállításaiban.</span><span class="sxs-lookup"><span data-stu-id="f1936-118">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span> 

<span data-ttu-id="f1936-119">Ha egynél több Human Resources-példányhoz van hozzáférése, akkor a **Beállítások** lapon kiválaszthatja, hogy melyik környezethez kíván csatlakozni.</span><span class="sxs-lookup"><span data-stu-id="f1936-119">If you have access to more than one instance of Human Resources, you can select which environment you want to connect to in the **Settings** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="f1936-120">Az alkalmazás most már támogatja a Rendszergazda biztonsági szerepkört.</span><span class="sxs-lookup"><span data-stu-id="f1936-120">The app now supports the System Administrator security role.</span></span>
 
## <a name="use-the-bot"></a><span data-ttu-id="f1936-121">A robot használata</span><span class="sxs-lookup"><span data-stu-id="f1936-121">Use the bot</span></span>

<span data-ttu-id="f1936-122">Az alkalmazás telepítése után egy üdvözlő üzenet jelenik meg, amely ismerteti, hogy milyen típusú intézkedéseket tehet a robot az Ön nevében.</span><span class="sxs-lookup"><span data-stu-id="f1936-122">After the app installs, a welcome message appears, letting you know the types of actions the bot can take on your behalf.</span></span>

![Human Resources Teams szabadságkezelő alkalmazás robot üdvözlőüzenete](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> <span data-ttu-id="f1936-124">A robottal való első interakciót követően szükség lehet a bejelentkezésre.</span><span class="sxs-lookup"><span data-stu-id="f1936-124">When first interacting with the bot, you might need to sign in.</span></span> <span data-ttu-id="f1936-125">Ha nem jelenik meg a bejelentkezési párbeszédpanel, ellenőrizze, hogy az előugró ablakok engedélyezve vannak-e a böngésző beállításaiban.</span><span class="sxs-lookup"><span data-stu-id="f1936-125">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span>

<span data-ttu-id="f1936-126">A robot a következőre kérhető:</span><span class="sxs-lookup"><span data-stu-id="f1936-126">You can ask the bot to:</span></span>

- <span data-ttu-id="f1936-127">Az egyes regisztrált szabadságtípusokhoz tartozó szabadságegyenleg-információk megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="f1936-127">Show time-off balance information for each leave type you're enrolled in.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás egyenlegek megjelenítése](./media/hr-teams-leave-app-bot-balances.png)
 
- <span data-ttu-id="f1936-129">Egy adott szabadságtípussal kapcsolatos további részletek megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="f1936-129">Show additional details about a specific leave type.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás részletes adatok megjelenítése](./media/hr-teams-leave-app-bot-details.png)

- <span data-ttu-id="f1936-131">Szabadságkérelem indítása az Ön számára.</span><span class="sxs-lookup"><span data-stu-id="f1936-131">Start a leave request for you.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás szabadság kérelmezése](./media/hr-teams-leave-app-bot-request.png)
 
<span data-ttu-id="f1936-133">A szabadságkérelem elindítását követően a napokat közvetlenül a kártyán állíthatja be.</span><span class="sxs-lookup"><span data-stu-id="f1936-133">After you start a leave request, you can adjust the days right within the card.</span></span>

![Human Resources Teams szabadságkezelő alkalmazás kérelem szerkesztése](./media/hr-teams-leave-app-bot-edit.png)
 
<span data-ttu-id="f1936-135">Ha befejezte az adatok megadását, válassza az **Elküldés** lehetőséget, hogy elküldje jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="f1936-135">When you're done entering information, select **Submit** to submit it for approval.</span></span> <span data-ttu-id="f1936-136">Választhatja a **Mentés piszkozatként** lehetőséget is, hogy később visszatérhessen hozzá.</span><span class="sxs-lookup"><span data-stu-id="f1936-136">You can also select **Save as draft** to come back to it later.</span></span>

![Human Resources Teams szabadságkezelő alkalmazás kérelem elküldése](./media/hr-teams-leave-app-bot-submit.png)

## <a name="manage-your-leave-in-teams"></a><span data-ttu-id="f1936-138">Távollét kezelése a Teams alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="f1936-138">Manage your leave in Teams</span></span>

<span data-ttu-id="f1936-139">A **Szabadság** lapon a következők jeleníthetők meg:</span><span class="sxs-lookup"><span data-stu-id="f1936-139">The **Time off** tab allows you to view:</span></span>

- <span data-ttu-id="f1936-140">Az egyes regisztrált szabadságtípusokhoz tartozó egyenleg-információk</span><span class="sxs-lookup"><span data-stu-id="f1936-140">Balance information for each leave type you're enrolled in</span></span>

- <span data-ttu-id="f1936-141">Várható szabadságkérelmek</span><span class="sxs-lookup"><span data-stu-id="f1936-141">Upcoming leave requests</span></span>

- <span data-ttu-id="f1936-142">Szabadságkérelmek</span><span class="sxs-lookup"><span data-stu-id="f1936-142">Time-off requests</span></span>

- <span data-ttu-id="f1936-143">Vázlat szabadságkérelmek</span><span class="sxs-lookup"><span data-stu-id="f1936-143">Draft leave requests</span></span>

![Human Resources Teams szabadságkezelő alkalmazás Szabadság lap](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a><span data-ttu-id="f1936-145">Új kérelem létrehozása</span><span class="sxs-lookup"><span data-stu-id="f1936-145">Create a new request</span></span>

1. <span data-ttu-id="f1936-146">Új szabadségkérelem létrehozásához válassza az **Új kérelem** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1936-146">To create a new leave request, select **New request**.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás Új kérelem](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. <span data-ttu-id="f1936-148">Adja meg a kivenni kívánt napot vagy napokat, majd válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1936-148">Enter the day or days you want to take off, and then select **Add**.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás szabadság hozzáadása](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. <span data-ttu-id="f1936-150">Ha szükséges, írjon be egy okkódot.</span><span class="sxs-lookup"><span data-stu-id="f1936-150">If applicable, enter a reason code.</span></span> <span data-ttu-id="f1936-151">Adjon meg bármilyen megjegyzést, és vegyen fel hozzá mellékleteket.</span><span class="sxs-lookup"><span data-stu-id="f1936-151">Also enter any comments and add any attachments.</span></span>

4. <span data-ttu-id="f1936-152">Ha befejezte az adatok megadását, írja be az **Elküldés** kifejezést, hogy elküldje jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="f1936-152">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="f1936-153">Beírhatja a **Mentés piszkozatként** kifejezést is, hogy később visszatérhessen hozzá.</span><span class="sxs-lookup"><span data-stu-id="f1936-153">You can also type **Save as draft** to come back to it later.</span></span>

### <a name="manage-draft-requests"></a><span data-ttu-id="f1936-154">Vázlat kérelmek kezelése</span><span class="sxs-lookup"><span data-stu-id="f1936-154">Manage draft requests</span></span>

1. <span data-ttu-id="f1936-155">Válassza ki a **Vázlatok** lapot.</span><span class="sxs-lookup"><span data-stu-id="f1936-155">Select the **Drafts** tab.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás Vázlatok lap](./media/hr-teams-leave-app-drafts-tab.png)

2. <span data-ttu-id="f1936-157">A kérelem szerkesztéséhez válassza ki a ceruzát, vagy válassza ki a szemétkosarat a kérelem törléséhez.</span><span class="sxs-lookup"><span data-stu-id="f1936-157">Select the pencil to edit the request, or select the trash can to delete the request.</span></span>

3. <span data-ttu-id="f1936-158">Hajtsa végre a szükséges módosításokat.</span><span class="sxs-lookup"><span data-stu-id="f1936-158">Make any necessary changes.</span></span> <span data-ttu-id="f1936-159">Ha befejezte az adatok megadását, írja be az **Elküldés** kifejezést, hogy elküldje jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="f1936-159">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="f1936-160">Választhatja a **Mentés piszkozatként** lehetőséget is, hogy később visszatérhessen hozzá.</span><span class="sxs-lookup"><span data-stu-id="f1936-160">You can also select **Save as draft** to come back to it later.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás vázlat szerkesztése](./media/hr-teams-leave-app-drafts-edit.png)
   
### <a name="respond-to-teams-notifications"></a><span data-ttu-id="f1936-162">Válaszadás a Teams értesítéseire</span><span class="sxs-lookup"><span data-stu-id="f1936-162">Respond to Teams notifications</span></span>

<span data-ttu-id="f1936-163">Ha Ön vagy egy olyan dolgozó, akinek Ön jóváhagyója a szabadságkérelmet küld be, akkor a Teamsben értesítést kap a Human Resources alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="f1936-163">When you or a worker you're an approver for submits a leave request, you'll receive a notification in the Human Resources app in Teams.</span></span> <span data-ttu-id="f1936-164">A megtekintéséhez kiválaszthatja az értesítést.</span><span class="sxs-lookup"><span data-stu-id="f1936-164">You can select the notification to view it.</span></span> <span data-ttu-id="f1936-165">Az értesítések megjelennek a **Csevegés** területen is.</span><span class="sxs-lookup"><span data-stu-id="f1936-165">Notifications also appear in the **Chat** area.</span></span>

<span data-ttu-id="f1936-166">Ha a jóváhagyó, akkor az értesítésben kiválaszthatja a **Jóváhagyás** vagy **Elutasítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1936-166">If you're an approver, you can select **Approve** or **Deny** in the notification.</span></span> <span data-ttu-id="f1936-167">Egy opcionális üzenetet is megadhat.</span><span class="sxs-lookup"><span data-stu-id="f1936-167">You can also provide an optional message.</span></span>

![Szabadságkérelem értesítése a Human Resources Teams alkalmazásban](./media/hr-teams-leave-app-notification.png)

## <a name="send-upcoming-time-off-information-to-your-coworkers"></a><span data-ttu-id="f1936-169">Várható szabadságadatok küldése a munkatársai számára</span><span class="sxs-lookup"><span data-stu-id="f1936-169">Send upcoming time-off information to your coworkers</span></span>

<span data-ttu-id="f1936-170">Miután telepítette az Human Resources alkalmazást a Teams számára, egyszerűen küldhet információt a Teamsben vagy csevegésekben a munkatársai számára.</span><span class="sxs-lookup"><span data-stu-id="f1936-170">After you install the Human Resources app for Teams, you can easily send information about your upcoming time off to your coworkers in teams or chats.</span></span>

1. <span data-ttu-id="f1936-171">Egy csapatban vagy csevegésben a Teamsben válassza a chat ablak alatti Human Resources gombot.</span><span class="sxs-lookup"><span data-stu-id="f1936-171">In a team or chat in Teams, select the Human Resources button below the chat window.</span></span>

   ![A chat ablak alatti Human Resources gomb](./media/hr-teams-leave-app-chat-button.png)

2. <span data-ttu-id="f1936-173">Válassza ki a megosztani kívánt szabadságkérelmet.</span><span class="sxs-lookup"><span data-stu-id="f1936-173">Select the leave request you want to share.</span></span> <span data-ttu-id="f1936-174">Ha meg szeretné osztani egy vázlat szabadságkérelmet, először válassza a **Vázlatok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1936-174">If you want to share a draft leave request, select **Drafts** first.</span></span>

   ![Egy közelgő szabadságkérelem kiválasztása megosztásra](./media/hr-teams-leave-app-chat-search.png)

<span data-ttu-id="f1936-176">A szabadságkérelem a csevegésben fog megjelenni.</span><span class="sxs-lookup"><span data-stu-id="f1936-176">Your leave request will display in the chat.</span></span>

![A Human Resources szabadságkérelem kártya](./media/hr-teams-leave-app-chat-card.png)

<span data-ttu-id="f1936-178">Ha megosztott egy vázlat állapotú kérelmet, akkor a program vázlatként jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="f1936-178">If you shared a draft request, it will display as a draft:</span></span>

![A Human Resources vázlat szabadságkérelem kártya](./media/hr-teams-leave-app-chat-draft-card.png)

## <a name="view-your-teams-leave-calendar"></a><span data-ttu-id="f1936-180">A csapata szabadságnaptárának megtekintése</span><span class="sxs-lookup"><span data-stu-id="f1936-180">View your team's leave calendar</span></span>

<span data-ttu-id="f1936-181">Ha Ön közvetlen beosztottakkal rendelkező vezető, akkor megtekintheti a csoport jóváhagyott és függőben távolléteit.</span><span class="sxs-lookup"><span data-stu-id="f1936-181">If you're a manager with direct reports, you can view your team's approved and pending time off.</span></span>

1. <span data-ttu-id="f1936-182">A Teamsben a Human Resources alkalmazásban válassza a **Távollét** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1936-182">In the Human Resources app in Teams, select **Time off**.</span></span>

2. <span data-ttu-id="f1936-183">Válassza ki a **Csoport naptárát**.</span><span class="sxs-lookup"><span data-stu-id="f1936-183">Select **Team calendar**.</span></span>

   ![Naptár megtekintése a Human Resources Teams alkalmazásban](./media/hr-teams-leave-app-view-calendar.png)

<span data-ttu-id="f1936-185">A naptárban a közvetlen beosztottjai jóváhagyott és a függőben lévő távollétei láthatók.</span><span class="sxs-lookup"><span data-stu-id="f1936-185">The calendar displays your direct reports' approved and pending time off.</span></span>

![Távolléti naptár a Human Resources Teams alkalmazásban](./media/hr-teams-leave-app-calendar.png)

## <a name="privacy-notice"></a><span data-ttu-id="f1936-187">Adatvédelmi nyilatkozat</span><span class="sxs-lookup"><span data-stu-id="f1936-187">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="f1936-188">Microsoft Language Understanding Intelligent Service (LUIS)</span><span class="sxs-lookup"><span data-stu-id="f1936-188">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="f1936-189">A Microsoft Teams rendszer Dynamics 365 Human Resources robotjával elemezhetők a felhasználó szöveges bemenetei az alapul szolgáló kérdés/szándék megértéséhez.</span><span class="sxs-lookup"><span data-stu-id="f1936-189">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="f1936-190">A felhasználó bemenete (például a „Contoso fiók keresése”) a Microsoft egyik kognitív szolgáltatásához, a Language Understanding Intelligent Service (LUIS) szolgáltatáshoz van irányítva.</span><span class="sxs-lookup"><span data-stu-id="f1936-190">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="f1936-191">A LUIS-ról  [itt](https://www.luis.ai/) olvashat többet.</span><span class="sxs-lookup"><span data-stu-id="f1936-191">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="f1936-192">A LUIS szolgáltatás egyértelműsíti vagy megérti a felhasználói bevitel szándékát (ebben az esetben a szándék az, hogy információt találjon) és a cél entitást (ebben az esetben a szándékolt entitás egy Contoso nevű számla).</span><span class="sxs-lookup"><span data-stu-id="f1936-192">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="f1936-193">Ez az információ ezután a Microsoft  [Azure bot keretrendszerébe](https://azure.microsoft.com/services/bot-service/) kerül, amely kapcsolatba lép a Dynamics 365 Human Resources adataival, és lekéri a kívánt információkat a felhasználói lekérdezéshez.</span><span class="sxs-lookup"><span data-stu-id="f1936-193">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="f1936-194">A robot telepítésével és a használatához való hozzáférés engedélyezésével Ön elfogadja, hogy a LUIS szolgáltatás és az Azure robot keretrendszer feldolgozza a bemenet mögötti szándékot, ami egy továbbfejlesztett, társalgásszerű felhasználói élményt eredményez.</span><span class="sxs-lookup"><span data-stu-id="f1936-194">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="f1936-195">A LUIS szolgáltatás és az Azure robot keretrendszer különböző szintű megfeleléssel rendelkezhet a Dynamics 365 Human Resources alkalmazáshoz képest.</span><span class="sxs-lookup"><span data-stu-id="f1936-195">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="f1936-196">Noha a LUIS szolgáltatás csak a felhasználói lekérdezésekhez férhet hozzá, és nem a felhasználó Dynamics 365 Human Resources adataihoz vagy fiókjához való kapcsolódásra készült, a Dynamics 365 Human Resources robot felhasználója önként adhat meg egy lekérdezést, amely tartalmazza a vevői adatokat, személyes adatokat vagy más adatokat, és az ilyen lekérdezés tartalma elküldhető a LUIS szolgáltatásnak és az Azure robot keretrendszernek.</span><span class="sxs-lookup"><span data-stu-id="f1936-196">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="f1936-197">A felhasználói lekérdezések és üzenetek tartalma legfeljebb 30 napig megmarad a LUIS rendszerben, a nyugalmi formában titkosítva van, és nincs használatban a tréningek vagy a szolgáltatások fejlesztése során.</span><span class="sxs-lookup"><span data-stu-id="f1936-197">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="f1936-198">A Cognitive Services szolgáltatással kapcsolatban  [itt](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/) olvashat többet.</span><span class="sxs-lookup"><span data-stu-id="f1936-198">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="f1936-199">Az Microsoft Teams-alkalmazások felügyeleti beállításainak kezeléséhez nyissa meg a [Microsoft Teams felügyeleti központot](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="f1936-199">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a><span data-ttu-id="f1936-200">Microsoft Teams, Azure Event Grid és Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="f1936-200">Microsoft Teams, Azure Event Grid, and Azure Cosmos DB</span></span>

<span data-ttu-id="f1936-201">Amikor a Microsoft Teams alkalmazásban a Dynamics 365 Human Resources alkalmazás értesítések funkcióját használja , bizonyos ügyféladatok azon a földrajzi területen kívül kerülnek, amelyen a bérlő humánerőforrás-szolgáltatását telepítették.</span><span class="sxs-lookup"><span data-stu-id="f1936-201">When using the Dynamics 365 Human Resources app in Microsoft Teams, certain customer data may flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span>

<span data-ttu-id="f1936-202">Dynamics 365 Human Resources az alkalmazott szabadság iránti kérelmének és a munkafolyamat-feladat részleteit átküldi a Microsoft Azure Event Grid és Microsoft Teams szolgáltatásokba.</span><span class="sxs-lookup"><span data-stu-id="f1936-202">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="f1936-203">Ezeket az adatokat a Microsoft Azure Event Grid felületen az Egyesült Államokban legfeljebb 24 óráig tárolhatjuk, és a rendszer a szállítás és tárolás során titkosítja, és a Microsoft vagy az alfeldolgozók nem használják a tanításhoz vagy szolgáltatások fejlesztéséhez.</span><span class="sxs-lookup"><span data-stu-id="f1936-203">This data may be stored in Microsoft Azure Event Grid for up to 24 hours and will be processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="f1936-204">Annak megértéséhez, hogy az adatok a Teamsben hol vannak tárolva akkor lásd: [Adatok helye Microsoft Teams-alkalmazásban](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="f1936-204">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>

<span data-ttu-id="f1936-205">Miközben a csevegőrobottal beszélget a Human Resources alkalmazásban beszélgetett, a beszélgetés tartalma lehet, hogy el lesz tárolva az Azure Cosmos DB-szolgáltatásban és át lesz adva Microsoft Teams alkalmazásnak.</span><span class="sxs-lookup"><span data-stu-id="f1936-205">While conversing with the chat bot in the Human Resources app, the conversation content may be stored in Azure Cosmos DB and transmitted to Microsoft Teams.</span></span> <span data-ttu-id="f1936-206">Ezeket az adatokat a program legfeljebb 24 óráig tárolhatja az Azure Cosmos DB modulban, és feldolgozható azon a földrajzi régión kívül, amelyen a bérlő Human Resources szolgáltatását telepítették, a szállítás és a nyugalmi állapotban titkosítva van, és a Microsoft vagy annak alfeldolgozói nem használják a tréningek vagy szolgáltatások fejlesztése céljából.</span><span class="sxs-lookup"><span data-stu-id="f1936-206">This data may be stored in Azure Cosmos DB for up to 24 hours and may be processed outside of the geographic region where your tenant's Human Resources service is deployed, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="f1936-207">Annak megértéséhez, hogy az adatok a Teamsben hol vannak tárolva akkor lásd: [Adatok helye Microsoft Teams-alkalmazásban](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="f1936-207">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>
 
<span data-ttu-id="f1936-208">Ha korlátozni szeretné a hozzáférést a szervezethez vagy a szervezeten belüli felhasználókhoz a Human Resources alkamazásban Microsoft Teams alkalmazásban, akkor lásd: [Alkalmazásengedély-irányelvek kezelése a Microsoft Teams-alkalmazásban](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="f1936-208">To restrict access to the Human Resources app in Microsoft Teams for your organization or users within your organization, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="see-also"></a><span data-ttu-id="f1936-209">Lásd még</span><span class="sxs-lookup"><span data-stu-id="f1936-209">See also</span></span>

[<span data-ttu-id="f1936-210">A Microsoft Teams letöltése és telepítése</span><span class="sxs-lookup"><span data-stu-id="f1936-210">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="f1936-211">Microsoft Teams súgóközpont</span><span class="sxs-lookup"><span data-stu-id="f1936-211">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="f1936-212">Human Resources alkalmazás a Teamsben</span><span class="sxs-lookup"><span data-stu-id="f1936-212">Human Resources app in Teams</span></span>](hr-admin-teams-leave-app.md)
