---
title: Human Resources alkalmazás a Teams rendszerben
description: Ez a témakör bemutatja a Microsoft Dynamics 365 Human Resources alkalmazást a Microsoft Teams rendszerben.
author: andreabichsel
ms.date: 02/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3926acd07a68f59682c18f4f7bc290dc1e21d0b6
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5889740"
---
# <a name="human-resources-app-in-teams"></a><span data-ttu-id="35c32-103">Human Resources alkalmazás a Teams rendszerben</span><span class="sxs-lookup"><span data-stu-id="35c32-103">Human Resources app in Teams</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="35c32-104">A Microsoft Dynamics 365 Human Resources alkalmazás a Microsoft Teams rendszerben lehetővé teszi, hogy az alkalmazottak gyorsan kérelmezzenek szabadságot, és megtekintsék a szabadságegyenlegükett közvetlenül a Microsoft Teams rendszerben.</span><span class="sxs-lookup"><span data-stu-id="35c32-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets employees quickly request time off and view their time-off balance information in Microsoft Teams.</span></span> <span data-ttu-id="35c32-105">Az alkalmazottak egy robottal léphetnek kapcsolatba információ kéréséhez.</span><span class="sxs-lookup"><span data-stu-id="35c32-105">Employees can interact with a bot to request information.</span></span> <span data-ttu-id="35c32-106">A **Szabadság** lapon részletesebb információk olvashatók.</span><span class="sxs-lookup"><span data-stu-id="35c32-106">The **Time off** tab provides more detailed information.</span></span> <span data-ttu-id="35c32-107">Ezenkívül a közelgő szabadságaikról információkat küldhetnek az embereknek a Teamsben és a Human Resources alkalmazáson kívüli csevegőfelületeken.</span><span class="sxs-lookup"><span data-stu-id="35c32-107">In addition, they can send people information about upcoming time off in teams and chats outside the Human Resources app.</span></span>

![Human Resources Teams szabadságkezelő alkalmazás robot](./media/hr-teams-leave-app-bot.png)

![Human Resources Teams szabadságkezelő alkalmazás Szabadság lap](./media/hr-teams-leave-app-timeoff-tab.png)

![A Human Resources szabadságkérelem kártya](./media/hr-teams-leave-app-chat-card.png)

## <a name="install-and-setup"></a><span data-ttu-id="35c32-111">Telepítés és beállítás</span><span class="sxs-lookup"><span data-stu-id="35c32-111">Install and setup</span></span>

<span data-ttu-id="35c32-112">A Dynamics 365 Human Resources alkalmazás a Teams áruházban található.</span><span class="sxs-lookup"><span data-stu-id="35c32-112">You can find the Dynamics 365 Human Resources app in the Teams store.</span></span> <span data-ttu-id="35c32-113">A Teams alkalmazás telepítésével kapcsolatos tudnivalókat lásd: [Szabadságkérelmek kezelése a Teams rendszerben](hr-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="35c32-113">For information about installing the Teams app, see [Manage leave requests in Teams](hr-teams-leave-app.md).</span></span>

<span data-ttu-id="35c32-114">A Teams alkalmazásengedélyeinek kezelésével kapcsolatos információkért lásd: [Alkalmazásengedély-irányelvek kezelése a Microsoft Teams rendszerben](/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="35c32-114">For information about managing app permissions in Teams, see [Manage app permission policies in Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).</span></span>

<span data-ttu-id="35c32-115">Ha azt szeretné, hogy a felhasználók a Távollét és szabadság naptárát az alkalmazásban tekintsék meg, engedélyeznie kell a **Szabadság és távollét naptárja a Teamsben** funkciót a Funkciókezelésben.</span><span class="sxs-lookup"><span data-stu-id="35c32-115">If you want your users to view the Leave and absence calendar in the app, you'll need to enable the **Leave and absence calendar in Teams** in Feature management.</span></span> <span data-ttu-id="35c32-116">A funkciók aktiválásával kapcsolatos további részletekért tekintse meg a [Szolgáltatások kezelése](hr-admin-manage-features.md) oldalt.</span><span class="sxs-lookup"><span data-stu-id="35c32-116">For more information about enabling features, see [Manage features](hr-admin-manage-features.md).</span></span>

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a><span data-ttu-id="35c32-117">Értesítések engedélyezése a Human Resources alkalmazáshoz a Teamsben</span><span class="sxs-lookup"><span data-stu-id="35c32-117">Enable notifications for the Human Resources app in Teams</span></span>

<span data-ttu-id="35c32-118">Ha azt szeretné, hogy a felhasználók távolléti értesítéseket a Teams alkalmazásban, engedélyeznie kell az értesítéseket a Dynamics 365 Human Resources alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="35c32-118">If you want users to receive leave request notifications in the Teams app, you must enable notifications in Dynamics 365 Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="35c32-119">Csak azok a felhasználók kapják meg az értesítéseket, akik bejelentkeztek a Teams szolgáltatásba és a Dynamics 365 Human Resources Teams alkalmazást használják.</span><span class="sxs-lookup"><span data-stu-id="35c32-119">Only users who are signed into Teams and using the Dynamics 365 Human Resources Teams app will receive notifications.</span></span>

1. <span data-ttu-id="35c32-120">A Human Resources alkalmazásban válassza a **Rendszerfelügyelet** elemet.</span><span class="sxs-lookup"><span data-stu-id="35c32-120">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="35c32-121">Válassza a **Hivatkozások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="35c32-121">Select **Links**.</span></span>

3. <span data-ttu-id="35c32-122">A **Beállítás** területen válassza ki a **Rendszer paraméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="35c32-122">Under **Setup**, select **System parameters**.</span></span>

4. <span data-ttu-id="35c32-123">Az **Általános** lapon állítsa be az **Értesítések engedélyezése a Teams alkalmazáshoz** elemet **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="35c32-123">On the **General** tab, set **Enable notifications for Teams app** to **Yes**.</span></span>

   ![A Teams alkalmazás értesítések engedélyezése a Rendszer paraméterei között](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. <span data-ttu-id="35c32-125">Ha minden felhasználó számára be kívánja kapcsolni a Teams értesítéseit, válassza az **Igen** lehetőséget a kérdésnél.</span><span class="sxs-lookup"><span data-stu-id="35c32-125">To turn on Teams notifications for all users, select **Yes** at the prompt.</span></span>

   ![Értesítések engedélyezése a Teams alkalmazáshoz minden felhasználónak](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a><span data-ttu-id="35c32-127">A Teams értesítéseinek be-és kikapcsolása egyéni felhasználókhoz</span><span class="sxs-lookup"><span data-stu-id="35c32-127">Turn Teams notifications on or off for individual users</span></span>

<span data-ttu-id="35c32-128">Miután engedélyezte az értesítéseket a Dynamics 365 Human Resources Teams alkalmazáshoz, ki-és bekapcsolhatja az egyes felhasználók értesítéseit.</span><span class="sxs-lookup"><span data-stu-id="35c32-128">After you've enabled notifications for the Dynamics 365 Human Resources Teams app, you can turn notifications on or off for individual users.</span></span>

1. <span data-ttu-id="35c32-129">A Human Resources alkalmazásban válassza a **Rendszerfelügyelet** elemet.</span><span class="sxs-lookup"><span data-stu-id="35c32-129">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="35c32-130">Válassza a **Hivatkozások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="35c32-130">Select **Links**.</span></span>

3. <span data-ttu-id="35c32-131">A **Felhasználók** területen válassza ki a **Felhasználói beállítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="35c32-131">Under **Users**, select **User options**.</span></span>

4. <span data-ttu-id="35c32-132">Válassza ki a **Munkafolyamat** lapot.</span><span class="sxs-lookup"><span data-stu-id="35c32-132">Select the **Workflow** tab.</span></span>

5. <span data-ttu-id="35c32-133">Állítsa az **Értesítések engedélyezése a Teams alkalmazáshoz** beállítást **Igen** értékre, hogy engedélyezze az értesítéseket a felhasználó számára. és **Nem** értékre az értesítések letiltásához a felhasználó számára.</span><span class="sxs-lookup"><span data-stu-id="35c32-133">Set **Enable notifications for Teams app** to **Yes** to enable notifications for the user or **No** to disable notifications for the user.</span></span>

   ![A Teams alkalmazásértesítések engedélyezése a felhasználói beállítások Munkafolyamat lapján](./media/hr-admin-teams-leave-app-notifications.png)

6. <span data-ttu-id="35c32-135">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="35c32-135">Select **Save**.</span></span>

## <a name="supported-languages"></a><span data-ttu-id="35c32-136">Támogatott nyelvek</span><span class="sxs-lookup"><span data-stu-id="35c32-136">Supported languages</span></span>

<span data-ttu-id="35c32-137">A Dynamics 365 Human Resources alkalmazásban a Teamsben az alábbi nyelvek támogatottak:</span><span class="sxs-lookup"><span data-stu-id="35c32-137">The Dynamics 365 Human Resources app in Teams supports the following languages:</span></span>

| <span data-ttu-id="35c32-138">Területibeállítás-azonosító</span><span class="sxs-lookup"><span data-stu-id="35c32-138">Locale ID</span></span> | <span data-ttu-id="35c32-139">Nyelv</span><span class="sxs-lookup"><span data-stu-id="35c32-139">Language</span></span> |
| --- | --- |
| <span data-ttu-id="35c32-140">de-DE</span><span class="sxs-lookup"><span data-stu-id="35c32-140">de-DE</span></span> | <span data-ttu-id="35c32-141">Német (Németország)</span><span class="sxs-lookup"><span data-stu-id="35c32-141">German (Germany)</span></span> |
| <span data-ttu-id="35c32-142">es-ES</span><span class="sxs-lookup"><span data-stu-id="35c32-142">es-ES</span></span> | <span data-ttu-id="35c32-143">Spanyol (Spanyolország)</span><span class="sxs-lookup"><span data-stu-id="35c32-143">Spanish (Spain)</span></span> |
| <span data-ttu-id="35c32-144">es-MX</span><span class="sxs-lookup"><span data-stu-id="35c32-144">es-MX</span></span> | <span data-ttu-id="35c32-145">Spanyol (Mexikó)</span><span class="sxs-lookup"><span data-stu-id="35c32-145">Spanish (Mexico)</span></span> |
| <span data-ttu-id="35c32-146">fr-CA</span><span class="sxs-lookup"><span data-stu-id="35c32-146">fr-CA</span></span> | <span data-ttu-id="35c32-147">Francia (Kanada)</span><span class="sxs-lookup"><span data-stu-id="35c32-147">French (Canada)</span></span> |
| <span data-ttu-id="35c32-148">fr-FR</span><span class="sxs-lookup"><span data-stu-id="35c32-148">fr-FR</span></span> | <span data-ttu-id="35c32-149">Francia (Franciaország)</span><span class="sxs-lookup"><span data-stu-id="35c32-149">French (France)</span></span> |
| <span data-ttu-id="35c32-150">it-IT</span><span class="sxs-lookup"><span data-stu-id="35c32-150">it-IT</span></span> | <span data-ttu-id="35c32-151">Olasz (Olaszország)</span><span class="sxs-lookup"><span data-stu-id="35c32-151">Italian (Italy)</span></span> |
| <span data-ttu-id="35c32-152">nl-NL</span><span class="sxs-lookup"><span data-stu-id="35c32-152">nl-NL</span></span> | <span data-ttu-id="35c32-153">Holland (Hollandia)</span><span class="sxs-lookup"><span data-stu-id="35c32-153">Dutch (Netherlands)</span></span> |
| <span data-ttu-id="35c32-154">pt-BR</span><span class="sxs-lookup"><span data-stu-id="35c32-154">pt-BR</span></span> | <span data-ttu-id="35c32-155">Portugál (Brazília)</span><span class="sxs-lookup"><span data-stu-id="35c32-155">Portuguese (Brazil)</span></span> |
| <span data-ttu-id="35c32-156">tr-TR</span><span class="sxs-lookup"><span data-stu-id="35c32-156">tr-TR</span></span> | <span data-ttu-id="35c32-157">Török (Törökország)</span><span class="sxs-lookup"><span data-stu-id="35c32-157">Turkish (Turkey)</span></span> |
| <span data-ttu-id="35c32-158">zh-CN</span><span class="sxs-lookup"><span data-stu-id="35c32-158">zh-CN</span></span> | <span data-ttu-id="35c32-159">Kínai (egyszerűsített)</span><span class="sxs-lookup"><span data-stu-id="35c32-159">Chinese (Simplified)</span></span> |

## <a name="notes"></a><span data-ttu-id="35c32-160">Jegyzetek</span><span class="sxs-lookup"><span data-stu-id="35c32-160">Notes</span></span>

<span data-ttu-id="35c32-161">A következő munkaelemek a későbbi verziókban jelennek meg:</span><span class="sxs-lookup"><span data-stu-id="35c32-161">The following work items are slated for future releases:</span></span>

| <span data-ttu-id="35c32-162">Munkatétel</span><span class="sxs-lookup"><span data-stu-id="35c32-162">Work item</span></span> | <span data-ttu-id="35c32-163">Állapot</span><span class="sxs-lookup"><span data-stu-id="35c32-163">Status</span></span> |
| --- | --- |
| <span data-ttu-id="35c32-164">Az egyenleg nem helyes, amikor jövőbeli dátumra vonatkozó szabadságot küld be.</span><span class="sxs-lookup"><span data-stu-id="35c32-164">The balance is incorrect when submitting time off for a future date.</span></span> | <span data-ttu-id="35c32-165">Az előrejelzés még nem érhető el.</span><span class="sxs-lookup"><span data-stu-id="35c32-165">Forecasting isn't yet available.</span></span> <span data-ttu-id="35c32-166">A megjelenített egyenleg az aktuális dátumra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="35c32-166">The balance displays for the current date.</span></span> |
| <span data-ttu-id="35c32-167">Nem lehet visszavonni egy **Ellenőrzés alatt** állapotú kérelmet.</span><span class="sxs-lookup"><span data-stu-id="35c32-167">Unable to cancel an **In review** request.</span></span> | <span data-ttu-id="35c32-168">Ez a funkció jelenleg nem támogatott, és egy későbbi verzióban kerül hozzáadásra.</span><span class="sxs-lookup"><span data-stu-id="35c32-168">This functionality isn't currently supported and will be added in a future release.</span></span> |
| <span data-ttu-id="35c32-169">Az egyenleg adatait a mai naptól számítja ki a program.</span><span class="sxs-lookup"><span data-stu-id="35c32-169">Balance information is calculated as of today.</span></span> | <span data-ttu-id="35c32-170">A rendszer jelenleg nem jeleníti meg a könyvelési időszak egyenlegeit, még akkor sem, ha be van állítva a Szabadság és távollét paraméterei között.</span><span class="sxs-lookup"><span data-stu-id="35c32-170">The system currently doesn't display balances as of the accrual period, even if it's configured in Leave and absence parameters.</span></span> |

## <a name="troubleshooting"></a><span data-ttu-id="35c32-171">Hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="35c32-171">Troubleshooting</span></span>

<span data-ttu-id="35c32-172">Ha egy felhasználónak sikerül bejelentkeznie a Human Resources Teams alkalmazásba vagy nem tudja használni, próbálja ki ezeket a hibaelhárítási utasításokat.</span><span class="sxs-lookup"><span data-stu-id="35c32-172">If a user is having trouble signing into or using the Human Resources Teams app, try following these troubleshooting instructions.</span></span> <span data-ttu-id="35c32-173">Ha a hibaelhárítás után sem oldódott meg a probléma, akkor forduljon a támogatáshoz.</span><span class="sxs-lookup"><span data-stu-id="35c32-173">If you're still having problems after troubleshooting, contact Support.</span></span> <span data-ttu-id="35c32-174">További információért lásd a [Támogatás kérése](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="35c32-174">For more information, see [Get support](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span></span>

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a><span data-ttu-id="35c32-175">Nem lehet bejelentkezni a Human Resources alkalmazásba a Teamsben.</span><span class="sxs-lookup"><span data-stu-id="35c32-175">Can't sign into the Human Resources app in Teams</span></span>

<span data-ttu-id="35c32-176">Ha egy felhasználó azzal keresi meg Önt, hogy nem tud bejelentkezni az alkalmazásba, akkor ellenőrizze, hogy a felhasználóhoz tartozik-e társított alkalmazotti rekord a HR-ben.</span><span class="sxs-lookup"><span data-stu-id="35c32-176">If a user contacts you because they can't sign into the app, verify that they have an associated employee record in Human Resources.</span></span>

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a><span data-ttu-id="35c32-177">Hiba történt a Teamsen belüli Human Resource alkalmazásban a szabadságkérelmek jóváhagyásakor.</span><span class="sxs-lookup"><span data-stu-id="35c32-177">Error when approving leave requests in the Human Resources app in Teams</span></span>

<span data-ttu-id="35c32-178">Ha egy felhasználó hibaüzenetet kap akkor, amikor megpróbálja jóváhagyni a szabadságkérelmeket a Teams alkalmazásban, próbálja meg a következő hibaelhárítási lépéseket:</span><span class="sxs-lookup"><span data-stu-id="35c32-178">If a user receives an error while trying to approve,  leave requests in the Teams app, try the following troubleshooting steps:</span></span>

1. <span data-ttu-id="35c32-179">Ellenőrizze, hogy a Teams-fiókjuk megegyezik-e azzal a fiókkal, amelyet a HR eléréséhez használnak.</span><span class="sxs-lookup"><span data-stu-id="35c32-179">Verify that their Teams account is the same one they use for accessing Human Resources.</span></span>

2. <span data-ttu-id="35c32-180">Ellenőrizze, hogy ők-e a kérelem érvényes jóváhagyója a szabadság jóváhagyására vonatkozó munkafolyamaton belüli beállítások ellenőrzésével.</span><span class="sxs-lookup"><span data-stu-id="35c32-180">Verify that they're a valid approver for the request by checking the workflow settings for leave approval.</span></span> <span data-ttu-id="35c32-181">A szabadságkérelem munkafolyamatairól további tudnivalókért lásd: [Szabadságkérelmezési munkafolyamat létrehozása](hr-leave-and-absence-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="35c32-181">For more information about leave request workflows, see [Create a leave request workflow](hr-leave-and-absence-workflow.md).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="35c32-182">Adatvédelmi nyilatkozat</span><span class="sxs-lookup"><span data-stu-id="35c32-182">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="35c32-183">Microsoft Language Understanding Intelligent Service (LUIS)</span><span class="sxs-lookup"><span data-stu-id="35c32-183">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="35c32-184">A Microsoft Teams rendszer Dynamics 365 Human Resources robotjával elemezhetők a felhasználó szöveges bemenetei az alapul szolgáló kérdés/szándék megértéséhez.</span><span class="sxs-lookup"><span data-stu-id="35c32-184">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="35c32-185">A felhasználó bemenete (például a „Contoso fiók keresése”) a Microsoft egyik kognitív szolgáltatásához, a Language Understanding Intelligent Service (LUIS) szolgáltatáshoz van irányítva.</span><span class="sxs-lookup"><span data-stu-id="35c32-185">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="35c32-186">A LUIS-ról  [itt](https://www.luis.ai/) olvashat többet.</span><span class="sxs-lookup"><span data-stu-id="35c32-186">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="35c32-187">A LUIS szolgáltatás egyértelműsíti vagy megérti a felhasználói bevitel szándékát (ebben az esetben a szándék az, hogy információt találjon) és a cél entitást (ebben az esetben a szándékolt entitás egy Contoso nevű számla).</span><span class="sxs-lookup"><span data-stu-id="35c32-187">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="35c32-188">Ez az információ ezután a Microsoft  [Azure bot keretrendszerébe](https://azure.microsoft.com/services/bot-service/) kerül, amely kapcsolatba lép a Dynamics 365 Human Resources adataival, és lekéri a kívánt információkat a felhasználói lekérdezéshez.</span><span class="sxs-lookup"><span data-stu-id="35c32-188">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="35c32-189">A robot telepítésével és a használatához való hozzáférés engedélyezésével Ön elfogadja, hogy a LUIS szolgáltatás és az Azure robot keretrendszer feldolgozza a bemenet mögötti szándékot, ami egy továbbfejlesztett, társalgásszerű felhasználói élményt eredményez.</span><span class="sxs-lookup"><span data-stu-id="35c32-189">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="35c32-190">A LUIS szolgáltatás és az Azure robot keretrendszer különböző szintű megfeleléssel rendelkezhet a Dynamics 365 Human Resources alkalmazáshoz képest.</span><span class="sxs-lookup"><span data-stu-id="35c32-190">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="35c32-191">Noha a LUIS szolgáltatás csak a felhasználói lekérdezésekhez férhet hozzá, és nem a felhasználó Dynamics 365 Human Resources adataihoz vagy fiókjához való kapcsolódásra készült, a Dynamics 365 Human Resources robot felhasználója önként adhat meg egy lekérdezést, amely tartalmazza a vevői adatokat, személyes adatokat vagy más adatokat, és az ilyen lekérdezés tartalma elküldhető a LUIS szolgáltatásnak és az Azure robot keretrendszernek.</span><span class="sxs-lookup"><span data-stu-id="35c32-191">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="35c32-192">A felhasználói lekérdezések és üzenetek tartalma legfeljebb 30 napig megmarad a LUIS rendszerben, a nyugalmi formában titkosítva van, és nincs használatban a tréningek vagy a szolgáltatások fejlesztése során.</span><span class="sxs-lookup"><span data-stu-id="35c32-192">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="35c32-193">A Cognitive Services szolgáltatással kapcsolatban  [itt](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/) olvashat többet.</span><span class="sxs-lookup"><span data-stu-id="35c32-193">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="35c32-194">Az Microsoft Teams-alkalmazások felügyeleti beállításainak kezeléséhez nyissa meg a [Microsoft Teams felügyeleti központot](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="35c32-194">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a><span data-ttu-id="35c32-195">Microsoft Teams, Azure Event Grid és Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="35c32-195">Microsoft Teams, Azure Event Grid, and Azure Cosmos DB</span></span>

<span data-ttu-id="35c32-196">Amikor a Microsoft Teams alkalmazásban a Dynamics 365 Human Resources alkalmazás értesítések funkcióját használja , bizonyos ügyféladatok azon a földrajzi területen kívül kerülnek, amelyen a bérlő humánerőforrás-szolgáltatását telepítették.</span><span class="sxs-lookup"><span data-stu-id="35c32-196">When using the Dynamics 365 Human Resources app in Microsoft Teams, certain customer data may flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span>

<span data-ttu-id="35c32-197">Dynamics 365 Human Resources az alkalmazott szabadság iránti kérelmének és a munkafolyamat-feladat részleteit átküldi a Microsoft Azure Event Grid és Microsoft Teams szolgáltatásokba.</span><span class="sxs-lookup"><span data-stu-id="35c32-197">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="35c32-198">Ezeket az adatokat a Microsoft Azure Event Grid felületen az Egyesült Államokban legfeljebb 24 óráig tárolhatjuk, és a rendszer a szállítás és tárolás során titkosítja, és a Microsoft vagy az alfeldolgozók nem használják a tanításhoz vagy szolgáltatások fejlesztéséhez.</span><span class="sxs-lookup"><span data-stu-id="35c32-198">This data may be stored in Microsoft Azure Event Grid for up to 24 hours and will be processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="35c32-199">Annak megértéséhez, hogy az adatok a Teamsben hol vannak tárolva akkor lásd: [Adatok helye Microsoft Teams-alkalmazásban](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="35c32-199">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span></span>

<span data-ttu-id="35c32-200">Miközben a csevegőrobottal beszélget a Human Resources alkalmazásban beszélgetett, a beszélgetés tartalma lehet, hogy el lesz tárolva az Azure Cosmos DB-szolgáltatásban és át lesz adva Microsoft Teams alkalmazásnak.</span><span class="sxs-lookup"><span data-stu-id="35c32-200">While conversing with the chat bot in the Human Resources app, the conversation content may be stored in Azure Cosmos DB and transmitted to Microsoft Teams.</span></span> <span data-ttu-id="35c32-201">Ezeket az adatokat a program legfeljebb 24 óráig tárolhatja az Azure Cosmos DB modulban, és feldolgozható azon a földrajzi régión kívül, amelyen a bérlő Human Resources szolgáltatását telepítették, a szállítás és a nyugalmi állapotban titkosítva van, és a Microsoft vagy annak alfeldolgozói nem használják a tréningek vagy szolgáltatások fejlesztése céljából.</span><span class="sxs-lookup"><span data-stu-id="35c32-201">This data may be stored in Azure Cosmos DB for up to 24 hours and may be processed outside of the geographic region where your tenant's Human Resources service is deployed, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="35c32-202">Annak megértéséhez, hogy az adatok a Teamsben hol vannak tárolva akkor lásd: [Adatok helye Microsoft Teams-alkalmazásban](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="35c32-202">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span></span>
 
<span data-ttu-id="35c32-203">Ha korlátozni szeretné a hozzáférést a szervezethez vagy a szervezeten belüli felhasználókhoz a Human Resources alkamazásban Microsoft Teams alkalmazásban, akkor lásd: [Alkalmazásengedély-irányelvek kezelése a Microsoft Teams-alkalmazásban](/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="35c32-203">To restrict access to the Human Resources app in Microsoft Teams for your organization or users within your organization, see [Manage app permission policies in Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="see-also"></a><span data-ttu-id="35c32-204">Lásd még</span><span class="sxs-lookup"><span data-stu-id="35c32-204">See also</span></span> 

[<span data-ttu-id="35c32-205">A Microsoft Teams letöltése és telepítése</span><span class="sxs-lookup"><span data-stu-id="35c32-205">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="35c32-206">Microsoft Teams súgóközpont</span><span class="sxs-lookup"><span data-stu-id="35c32-206">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="35c32-207">Szabadságkérelmek kezelése a Teamsben</span><span class="sxs-lookup"><span data-stu-id="35c32-207">Manage leave requests in Teams</span></span>](hr-teams-leave-app.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]