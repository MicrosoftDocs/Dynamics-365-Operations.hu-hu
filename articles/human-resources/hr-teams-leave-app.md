---
title: Szabadság- és távollétkérelmek kezelése a Teams alkalmazásban
description: Ez a témakör azt mutatja be, hogyan lehet szabadságot kérelmezni a Dynamics 365 Human Resources alkalmazásban a Microsoft Teams rendszerben.
author: andreabichsel
manager: AnnBe
ms.date: 05/18/2020
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
ms.openlocfilehash: b3daa76385518ad4c7150fa93ce33be0351bfd57
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2020
ms.locfileid: "3428828"
---
# <a name="manage-leave-requests-in-teams"></a><span data-ttu-id="5d9f1-103">Szabadság- és távollétkérelmek kezelése a Teams alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="5d9f1-103">Manage leave requests in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="5d9f1-104">A Microsoft Dynamics 365 Human Resources alkalmazás a Microsoft Teams rendszerben lehetővé teszi, hogy gyorsan kérelmezzen szabadságot, és megtekintse a szabadságegyenlegét közvetlenül a Microsoft Teams rendszerben.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets you quickly request time off and view your time-off balance information right in Microsoft Teams.</span></span> <span data-ttu-id="5d9f1-105">Egy robottal léphet kapcsolatba információ kéréséhez.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-105">You can interact with a bot to request information.</span></span> <span data-ttu-id="5d9f1-106">A **Szabadság** lapon részletesebb információk olvashatók.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-106">The **Time off** tab provides more detailed information.</span></span>

## <a name="install-the-app"></a><span data-ttu-id="5d9f1-107">Az alkalmazás telepítése</span><span class="sxs-lookup"><span data-stu-id="5d9f1-107">Install the app</span></span>

<span data-ttu-id="5d9f1-108">A Human Resources app a Teams áruházban található.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-108">You can find the Human Resources app in the Teams store.</span></span>

1. <span data-ttu-id="5d9f1-109">A Microsoft Teams rendszerben válassza ki a három pontot.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-109">In Microsoft Teams, select the ellipses.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás három pontja](./media/hr-teams-leave-app-ellipses.png)
 
2. <span data-ttu-id="5d9f1-111">Keresse meg a Dynamics 365 Human Resources alkalmazást, majd válassza ki a **Human Resources** címet.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-111">Search for Dynamics 365 Human Resources, and then select the **Human Resources** tile.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás HR címe](./media/hr-teams-leave-app-human-resources-tile.png)

3. <span data-ttu-id="5d9f1-113">Válassza a **Hozzáadás** gombot az alkalmazás telepítéséhez.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-113">Select the **Add** button to install the app.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás telepítése](./media/hr-teams-leave-app-in-store.png)

<span data-ttu-id="5d9f1-115">Ha az alkalmazás nem lépteti be automatikusan, válassza a **Beállítás** lapot a bejelentkezéshez.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-115">If the app doesn't automatically sign you in, select the **Settings** tab to sign in.</span></span>

![Human Resources Teams szabadságkezelő alkalmazás Beállítások lap](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> <span data-ttu-id="5d9f1-117">Ha nem jelenik meg a bejelentkezési párbeszédpanel, ellenőrizze, hogy az előugró ablakok engedélyezve vannak-e a böngésző beállításaiban.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-117">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span> 

<span data-ttu-id="5d9f1-118">Ha egynél több Human Resources-példányhoz van hozzáférése, akkor a **Beállítások** lapon kiválaszthatja, hogy melyik környezethez kíván csatlakozni.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-118">If you have access to more than one instance of Human Resources, you can select which environment you want to connect to in the **Settings** tab.</span></span>

> [!WARNING]
> <span data-ttu-id="5d9f1-119">Az alkalmazás jelenleg nem támogatja a Rendszergazda biztonsági szerepkört, és egy Rendszergazdai fiókkal való bejelentkezéskor hibaüzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-119">The app doesn't currently support the System Administrator security role, and will display an error message if you sign in with a System Administrator account.</span></span> <span data-ttu-id="5d9f1-120">Másik fiókkal való bejelentkezéshez a **Beállítások** lapon jelölje be a **Fiókok váltása** gombot, majd jelentkezzen be egy olyan felhasználói fiókkal, amely nem rendelkezik Rendszergazdai jogokkal.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-120">To sign in with a different account, on the **Settings** tab, select the **Switch accounts** button, and then sign in with a user account that doesn’t have System Administrator privileges.</span></span>
 
## <a name="use-the-bot"></a><span data-ttu-id="5d9f1-121">A robot használata</span><span class="sxs-lookup"><span data-stu-id="5d9f1-121">Use the bot</span></span>

<span data-ttu-id="5d9f1-122">Az alkalmazás telepítése után egy üdvözlő üzenet jelenik meg, amely ismerteti, hogy milyen típusú intézkedéseket tehet a robot az Ön nevében.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-122">After the app installs, a welcome message appears, letting you know the types of actions the bot can take on your behalf.</span></span>

![Human Resources Teams szabadságkezelő alkalmazás robot üdvözlőüzenete](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> <span data-ttu-id="5d9f1-124">A robottal való első interakciót követően szükség lehet a bejelentkezésre.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-124">When first interacting with the bot, you might need to sign in.</span></span> <span data-ttu-id="5d9f1-125">Ha nem jelenik meg a bejelentkezési párbeszédpanel, ellenőrizze, hogy az előugró ablakok engedélyezve vannak-e a böngésző beállításaiban.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-125">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span>

<span data-ttu-id="5d9f1-126">A robot a következőre kérhető:</span><span class="sxs-lookup"><span data-stu-id="5d9f1-126">You can ask the bot to:</span></span>

- <span data-ttu-id="5d9f1-127">Az egyes regisztrált szabadságtípusokhoz tartozó szabadságegyenleg-információk megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-127">Show time-off balance information for each leave type you're enrolled in.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás egyenlegek megjelenítése](./media/hr-teams-leave-app-bot-balances.png)
 
- <span data-ttu-id="5d9f1-129">Egy adott szabadságtípussal kapcsolatos további részletek megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-129">Show additional details about a specific leave type.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás részletes adatok megjelenítése](./media/hr-teams-leave-app-bot-details.png)

- <span data-ttu-id="5d9f1-131">Szabadságkérelem indítása az Ön számára.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-131">Start a leave request for you.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás szabadság kérelmezése](./media/hr-teams-leave-app-bot-request.png)
 
<span data-ttu-id="5d9f1-133">A szabadság iránti kérelem elindítását követően korrigálhatja a kártyán lévő napokat, vagy a **Részletek szerkesztése** lehetőséget választva további információkat adhat hozzá a kéréshez.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-133">After you start a leave request, you can adjust the days right within the card, or you can select **Edit details** to add additional information to your request.</span></span>

![Human Resources Teams szabadságkezelő alkalmazás kérelem szerkesztése](./media/hr-teams-leave-app-bot-edit.png)
 
<span data-ttu-id="5d9f1-135">Ha befejezte az adatok megadását, írja be az **Elküldés** kifejezést, hogy elküldje jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-135">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="5d9f1-136">Beírhatja a **Mentés piszkozatként** kifejezést is, hogy később visszatérhessen hozzá.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-136">You can also type **Save as draft** to come back to it later.</span></span>

![Human Resources Teams szabadságkezelő alkalmazás kérelem elküldése](./media/hr-teams-leave-app-bot-submit.png)

## <a name="manage-your-leave-in-teams"></a><span data-ttu-id="5d9f1-138">Távollét kezelése a Teams alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="5d9f1-138">Manage your leave in Teams</span></span>

<span data-ttu-id="5d9f1-139">A **Szabadság** lapon a következők jeleníthetők meg:</span><span class="sxs-lookup"><span data-stu-id="5d9f1-139">The **Time off** tab allows you to view:</span></span>

- <span data-ttu-id="5d9f1-140">Az egyes regisztrált szabadságtípusokhoz tartozó egyenleg-információk</span><span class="sxs-lookup"><span data-stu-id="5d9f1-140">Balance information for each leave type you're enrolled in</span></span>

- <span data-ttu-id="5d9f1-141">Várható szabadságkérelmek</span><span class="sxs-lookup"><span data-stu-id="5d9f1-141">Upcoming leave requests</span></span>

- <span data-ttu-id="5d9f1-142">Szabadságkérelmek</span><span class="sxs-lookup"><span data-stu-id="5d9f1-142">Time-off requests</span></span>

- <span data-ttu-id="5d9f1-143">Vázlat szabadságkérelmek</span><span class="sxs-lookup"><span data-stu-id="5d9f1-143">Draft leave requests</span></span>

![Human Resources Teams szabadságkezelő alkalmazás Szabadság lap](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a><span data-ttu-id="5d9f1-145">Új kérelem létrehozása</span><span class="sxs-lookup"><span data-stu-id="5d9f1-145">Create a new request</span></span>

1. <span data-ttu-id="5d9f1-146">Új szabadségkérelem létrehozásához válassza az **Új kérelem** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-146">To create a new leave request, select **New request**.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás Új kérelem](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. <span data-ttu-id="5d9f1-148">Adja meg a kivenni kívánt napot vagy napokat, majd válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-148">Enter the day or days you want to take off, and then select **Add**.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás szabadság hozzáadása](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. <span data-ttu-id="5d9f1-150">Ha szükséges, írjon be egy okkódot.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-150">If applicable, enter a reason code.</span></span> <span data-ttu-id="5d9f1-151">Adjon meg bármilyen megjegyzést, és vegyen fel hozzá mellékleteket.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-151">Also enter any comments and add any attachments.</span></span>

4. <span data-ttu-id="5d9f1-152">Ha befejezte az adatok megadását, írja be az **Elküldés** kifejezést, hogy elküldje jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-152">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="5d9f1-153">Beírhatja a **Mentés piszkozatként** kifejezést is, hogy később visszatérhessen hozzá.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-153">You can also type **Save as draft** to come back to it later.</span></span>

### <a name="manage-draft-requests"></a><span data-ttu-id="5d9f1-154">Vázlat kérelmek kezelése</span><span class="sxs-lookup"><span data-stu-id="5d9f1-154">Manage draft requests</span></span>

1. <span data-ttu-id="5d9f1-155">Válassza ki a **Vázlatok** lapot.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-155">Select the **Drafts** tab.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás Vázlatok lap](./media/hr-teams-leave-app-drafts-tab.png)

2. <span data-ttu-id="5d9f1-157">A kérelem szerkesztéséhez válassza ki a ceruzát, vagy válassza ki a szemétkosarat a kérelem törléséhez.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-157">Select the pencil to edit the request, or select the trash can to delete the request.</span></span>

3. <span data-ttu-id="5d9f1-158">Hajtsa végre a szükséges módosításokat.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-158">Make any necessary changes.</span></span> <span data-ttu-id="5d9f1-159">Ha befejezte az adatok megadását, írja be az **Elküldés** kifejezést, hogy elküldje jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-159">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="5d9f1-160">Választhatja a **Mentés piszkozatként** lehetőséget is, hogy később visszatérhessen hozzá.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-160">You can also select **Save as draft** to come back to it later.</span></span>

   ![Human Resources Teams szabadságkezelő alkalmazás vázlat szerkesztése](./media/hr-teams-leave-app-drafts-edit.png)
   
## <a name="privacy-notice"></a><span data-ttu-id="5d9f1-162">Adatvédelmi nyilatkozat</span><span class="sxs-lookup"><span data-stu-id="5d9f1-162">Privacy notice</span></span>

<span data-ttu-id="5d9f1-163">A Microsoft Teams rendszer Dynamics 365 Human Resources robotjával elemezhetők a felhasználó szöveges bemenetei az alapul szolgáló kérdés/szándék megértéséhez.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-163">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="5d9f1-164">A felhasználó bemenete (például a „Contoso fiók keresése”) a Microsoft egyik kognitív szolgáltatásához, a Language Understanding Intelligent Service (LUIS) szolgáltatáshoz van irányítva.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-164">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="5d9f1-165">A LUIS-ról  [itt](https://www.luis.ai/) olvashat többet.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-165">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="5d9f1-166">A LUIS szolgáltatás egyértelműsíti vagy megérti a felhasználói bevitel szándékát (ebben az esetben a szándék az, hogy információt találjon) és a cél entitást (ebben az esetben a szándékolt entitás egy Contoso nevű számla).</span><span class="sxs-lookup"><span data-stu-id="5d9f1-166">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="5d9f1-167">Ez az információ ezután a Microsoft  [Azure bot keretrendszerébe](https://azure.microsoft.com/services/bot-service/)  kerül, amely interaktál a Dynamics 365 Human Resources adataival, és lekéri a kívánt információkat a felhasználói lekérdezéshez.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-167">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/) which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="5d9f1-168">A robot telepítésével és a használatához való hozzáférés engedélyezésével Ön elfogadja, hogy a LUIS szolgáltatás és az Azure robot keretrendszer feldolgozza a bemenet mögötti szándékot, ami egy továbbfejlesztett, társalgásszerű felhasználói élményt eredményez.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-168">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="5d9f1-169">A LUIS szolgáltatás és az Azure robot keretrendszer különböző szintű megfeleléssel rendelkezhet a Dynamics 365 Human Resources alkalmazáshoz képest.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-169">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="5d9f1-170">Noha a LUIS szolgáltatás csak a felhasználói lekérdezésekhez férhet hozzá, és nem a felhasználó Dynamics 365 Human Resources adataihoz vagy fiókjához való kapcsolódásra készült, a Dynamics 365 Human Resources robot felhasználója önként adhat meg egy lekérdezést, amely tartalmazza a vevői adatokat, személyes adatokat vagy más adatokat, és az ilyen lekérdezés tartalma elküldhető a LUIS szolgáltatásnak és az Azure robot keretrendszernek.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-170">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="5d9f1-171">A felhasználói lekérdezések és üzenetek tartalma legfeljebb 30 napig megmarad a LUIS rendszerben, a nyugalmi formában titkosítva van, és nincs használatban a tréningek vagy a szolgáltatások fejlesztése során.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-171">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="5d9f1-172">A Cognitive Services szolgáltatással kapcsolatban  [itt](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/) olvashat többet.</span><span class="sxs-lookup"><span data-stu-id="5d9f1-172">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="5d9f1-173">Az Microsoft Teams-alkalmazások felügyeleti beállításainak kezeléséhez nyissa meg a [Microsoft Teams felügyeleti központot](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="5d9f1-173">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span> 

## <a name="see-also"></a><span data-ttu-id="5d9f1-174">Lásd még</span><span class="sxs-lookup"><span data-stu-id="5d9f1-174">See also</span></span>

[<span data-ttu-id="5d9f1-175">A Microsoft Teams letöltése és telepítése</span><span class="sxs-lookup"><span data-stu-id="5d9f1-175">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="5d9f1-176">Microsoft Teams súgóközpont</span><span class="sxs-lookup"><span data-stu-id="5d9f1-176">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="5d9f1-177">Human Resources alkalmazás a Teams rendszerben</span><span class="sxs-lookup"><span data-stu-id="5d9f1-177">Human Resources app in Teams</span></span>](hr-admin-teams-leave-app.md)
