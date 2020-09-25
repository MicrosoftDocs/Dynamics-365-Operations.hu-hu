---
title: Human Resources alkalmazás a Teams rendszerben
description: Ez a témakör bemutatja a Microsoft Dynamics 365 Human Resources alkalmazást a Microsoft Teams rendszerben.
author: andreabichsel
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
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
ms.openlocfilehash: a022f8297066793080d254baa01410884a3fafd9
ms.sourcegitcommit: 55b729361ea852e38531c51972c6730e3d9c2b45
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/08/2020
ms.locfileid: "3776308"
---
# <a name="human-resources-app-in-teams"></a><span data-ttu-id="b8321-103">Human Resources alkalmazás a Teams rendszerben</span><span class="sxs-lookup"><span data-stu-id="b8321-103">Human Resources app in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="b8321-104">A Microsoft Dynamics 365 Human Resources alkalmazás a Microsoft Teams rendszerben lehetővé teszi, hogy az alkalmazottak gyorsan kérelmezzenek szabadságot, és megtekintsék a szabadságegyenlegükett közvetlenül a Microsoft Teams rendszerben.</span><span class="sxs-lookup"><span data-stu-id="b8321-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets employees quickly request time off and view their time-off balance information in Microsoft Teams.</span></span> <span data-ttu-id="b8321-105">Az alkalmazottak egy robottal léphetnek kapcsolatba információ kéréséhez.</span><span class="sxs-lookup"><span data-stu-id="b8321-105">Employees can interact with a bot to request information.</span></span> <span data-ttu-id="b8321-106">A **Szabadság** lapon részletesebb információk olvashatók.</span><span class="sxs-lookup"><span data-stu-id="b8321-106">The **Time off** tab provides more detailed information.</span></span>

![Human Resources Teams szabadságkezelő alkalmazás robot](./media/hr-admin-teams-leave-app-bot.png)

![Human Resources Teams szabadságkezelő alkalmazás Szabadság lap](./media/hr-teams-leave-app-timeoff-tab.png)

## <a name="install-and-setup"></a><span data-ttu-id="b8321-109">Telepítés és beállítás</span><span class="sxs-lookup"><span data-stu-id="b8321-109">Install and setup</span></span>

<span data-ttu-id="b8321-110">A Human Resources app a Teams áruházban található.</span><span class="sxs-lookup"><span data-stu-id="b8321-110">You can find the Human Resources app in the Teams store.</span></span> <span data-ttu-id="b8321-111">A Teams alkalmazás telepítésével kapcsolatos tudnivalókat lásd: [Szabadságkérelmek kezelése a Teams rendszerben](hr-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="b8321-111">For information about installing the Teams app, see [Manage leave requests in Teams](hr-teams-leave-app.md).</span></span>

<span data-ttu-id="b8321-112">A Teams alkalmazásengedélyeinek kezelésével kapcsolatos információkért lásd: [Alkalmazásengedély-irányelvek kezelése a Microsoft Teams rendszerben](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="b8321-112">For information about managing app permissions in Teams, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a><span data-ttu-id="b8321-113">Értesítések engedélyezése a Human Resources alkalmazáshoz a Teamsben</span><span class="sxs-lookup"><span data-stu-id="b8321-113">Enable notifications for the Human Resources app in Teams</span></span>

<span data-ttu-id="b8321-114">Ha azt szeretné, hogy a felhasználók távolléti értesítéseket a Teams alkalmazásban, engedélyeznie kell az értesítéseket a Human Resources alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="b8321-114">If you want users to receive leave request notifications in the Teams app, you must enable notifications in Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="b8321-115">Csak azok a felhasználók kapják meg az értesítéseket, akik bejelentkeztek a Teams szolgáltatásba és a Human Resources Teams alkalmazást használják.</span><span class="sxs-lookup"><span data-stu-id="b8321-115">Only users who are signed into Teams and using the Human Resources Teams app will receive notifications.</span></span>

1. <span data-ttu-id="b8321-116">A Human Resources alkalmazásban válassza a **Rendszerfelügyelet** elemet.</span><span class="sxs-lookup"><span data-stu-id="b8321-116">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="b8321-117">Válassza a **Hivatkozások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8321-117">Select **Links**.</span></span>

3. <span data-ttu-id="b8321-118">A **Beállítás** területen válassza ki a **Rendszer paraméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8321-118">Under **Setup**, select **System parameters**.</span></span>

4. <span data-ttu-id="b8321-119">Az **Általános** lapon állítsa be az **Értesítések engedélyezése a Teams alkalmazáshoz** elemet **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="b8321-119">On the **General** tab, set **Enable notifications for Teams app** to **Yes**.</span></span>

   ![A Teams alkalmazás értesítések engedélyezése a Rendszer paraméterei között](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. <span data-ttu-id="b8321-121">Ha minden felhasználó számára be kívánja kapcsolni a Teams értesítéseit, válassza az **Igen** lehetőséget a kérdésnél.</span><span class="sxs-lookup"><span data-stu-id="b8321-121">To turn on Teams notifications for all users, select **Yes** at the prompt.</span></span>

   ![Értesítések engedélyezése a Teams alkalmazáshoz minden felhasználónak](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a><span data-ttu-id="b8321-123">A Teams értesítéseinek be-és kikapcsolása egyéni felhasználókhoz</span><span class="sxs-lookup"><span data-stu-id="b8321-123">Turn Teams notifications on or off for individual users</span></span>

<span data-ttu-id="b8321-124">Miután engedélyezte az értesítéseket a Human Resources Teams alkalmazáshoz, ki-és bekapcsolhatja az egyes felhasználók értesítéseit.</span><span class="sxs-lookup"><span data-stu-id="b8321-124">After you've enabled notifications for the Human Resources Teams app, you can turn notifications on or off for individual users.</span></span>

1. <span data-ttu-id="b8321-125">A Human Resources alkalmazásban válassza a **Rendszerfelügyelet** elemet.</span><span class="sxs-lookup"><span data-stu-id="b8321-125">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="b8321-126">Válassza a **Hivatkozások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8321-126">Select **Links**.</span></span>

3. <span data-ttu-id="b8321-127">A **Felhasználók** területen válassza ki a **Felhasználói beállítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8321-127">Under **Users**, select **User options**.</span></span>

4. <span data-ttu-id="b8321-128">Válassza ki a **Munkafolyamat** lapot.</span><span class="sxs-lookup"><span data-stu-id="b8321-128">Select the **Workflow** tab.</span></span>

5. <span data-ttu-id="b8321-129">Állítsa az **Értesítések engedélyezése a Teams alkalmazáshoz** beállítást **Igen** értékre, hogy engedélyezze az értesítéseket a felhasználó számára. és **Nem** értékre az értesítések letiltásához a felhasználó számára.</span><span class="sxs-lookup"><span data-stu-id="b8321-129">Set **Enable notifications for Teams app** to **Yes** to enable notifications for the user or **No** to disable notifications for the user.</span></span>

   ![A Teams alkalmazásértesítések engedélyezése a felhasználói beállítások Munkafolyamat lapján](./media/hr-admin-teams-leave-app-notifications.png)

6. <span data-ttu-id="b8321-131">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8321-131">Select **Save**.</span></span>

## <a name="known-issues"></a><span data-ttu-id="b8321-132">Ismert problémák</span><span class="sxs-lookup"><span data-stu-id="b8321-132">Known issues</span></span>

| <span data-ttu-id="b8321-133">Kiadás</span><span class="sxs-lookup"><span data-stu-id="b8321-133">Issue</span></span> | <span data-ttu-id="b8321-134">Állapot</span><span class="sxs-lookup"><span data-stu-id="b8321-134">Status</span></span> |
| --- | --- |
| <span data-ttu-id="b8321-135">A vízszintes görgetés nem használható Android-telefonokon</span><span class="sxs-lookup"><span data-stu-id="b8321-135">Horizontal scrolling doesn't work on Android phones</span></span> | <span data-ttu-id="b8321-136">A vízszintes görgetés nem jelent problémát iOS- vagy asztali eszközön.</span><span class="sxs-lookup"><span data-stu-id="b8321-136">Horizontal scrolling isn't an issue on iOS or desktop devices.</span></span> <span data-ttu-id="b8321-137">Dolgozunk a javításon az Android rendszerhez.</span><span class="sxs-lookup"><span data-stu-id="b8321-137">We're working on a fix for Android.</span></span> |
| <span data-ttu-id="b8321-138">Hiba: Probléma adódott a kapcsolódásra szolgáló környezet keresésekor.</span><span class="sxs-lookup"><span data-stu-id="b8321-138">Error: There is an issue finding an environment to connect to.</span></span> | <span data-ttu-id="b8321-139">Ez a hibaüzenet akkor is megjelenhet, ha ellenőrizte, hogy a felhasználó hozzáférhet-e egy vagy több Human Resources környezethez.</span><span class="sxs-lookup"><span data-stu-id="b8321-139">You might receive this error even if you've verified that the user can access one or more Human Resources environments.</span></span> <span data-ttu-id="b8321-140">Emellett előfordulhat, hogy a várt környezetek nem mindegyike látható.</span><span class="sxs-lookup"><span data-stu-id="b8321-140">Also, you might not see all the environments you expect.</span></span> <span data-ttu-id="b8321-141">A probléma megoldásáig törölje a felhasználót, majd importálja újra, hogy elkerülje a problémát.</span><span class="sxs-lookup"><span data-stu-id="b8321-141">Until we fix this issue, delete the user and then import them in again to resolve the problem.</span></span> |
| <span data-ttu-id="b8321-142">Az egyenleg nem helyes, amikor jövőbeli dátumra vonatkozó szabadságot küld be.</span><span class="sxs-lookup"><span data-stu-id="b8321-142">The balance is incorrect when submitting time off for a future date.</span></span> | <span data-ttu-id="b8321-143">Az előrejelzés még nem érhető el.</span><span class="sxs-lookup"><span data-stu-id="b8321-143">Forecasting isn't yet available.</span></span> <span data-ttu-id="b8321-144">A megjelenített egyenleg az aktuális dátumra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="b8321-144">The balance displays for the current date.</span></span> |
| <span data-ttu-id="b8321-145">Nem lehet visszavonni egy **Ellenőrzés alatt** állapotú kérelmet.</span><span class="sxs-lookup"><span data-stu-id="b8321-145">Unable to cancel an **In review** request.</span></span> | <span data-ttu-id="b8321-146">Ez a funkció jelenleg nem támogatott, és egy későbbi verzióban kerül hozzáadásra.</span><span class="sxs-lookup"><span data-stu-id="b8321-146">This functionality isn't currently supported and will be added in a future release.</span></span> |
| <span data-ttu-id="b8321-147">Az egyenleg adatait a mai naptól számítja ki a program.</span><span class="sxs-lookup"><span data-stu-id="b8321-147">Balance information is calculated as of today.</span></span> | <span data-ttu-id="b8321-148">A rendszer jelenleg nem jeleníti meg a könyvelési időszak egyenlegeit, még akkor sem, ha be van állítva a Szabadság és távollét paraméterei között.</span><span class="sxs-lookup"><span data-stu-id="b8321-148">The system currently doesn't display balances as of the accrual period, even if it's configured in Leave and absence parameters.</span></span> |

## <a name="privacy-notice"></a><span data-ttu-id="b8321-149">Adatvédelmi nyilatkozat</span><span class="sxs-lookup"><span data-stu-id="b8321-149">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="b8321-150">Microsoft Language Understanding Intelligent Service (LUIS)</span><span class="sxs-lookup"><span data-stu-id="b8321-150">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="b8321-151">A Microsoft Teams rendszer Dynamics 365 Human Resources robotjával elemezhetők a felhasználó szöveges bemenetei az alapul szolgáló kérdés/szándék megértéséhez.</span><span class="sxs-lookup"><span data-stu-id="b8321-151">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="b8321-152">A felhasználó bemenete (például a „Contoso fiók keresése”) a Microsoft egyik kognitív szolgáltatásához, a Language Understanding Intelligent Service (LUIS) szolgáltatáshoz van irányítva.</span><span class="sxs-lookup"><span data-stu-id="b8321-152">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="b8321-153">A LUIS-ról  [itt](https://www.luis.ai/) olvashat többet.</span><span class="sxs-lookup"><span data-stu-id="b8321-153">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="b8321-154">A LUIS szolgáltatás egyértelműsíti vagy megérti a felhasználói bevitel szándékát (ebben az esetben a szándék az, hogy információt találjon) és a cél entitást (ebben az esetben a szándékolt entitás egy Contoso nevű számla).</span><span class="sxs-lookup"><span data-stu-id="b8321-154">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="b8321-155">Ez az információ ezután a Microsoft  [Azure bot keretrendszerébe](https://azure.microsoft.com/services/bot-service/) kerül, amely kapcsolatba lép a Dynamics 365 Human Resources adataival, és lekéri a kívánt információkat a felhasználói lekérdezéshez.</span><span class="sxs-lookup"><span data-stu-id="b8321-155">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="b8321-156">A robot telepítésével és a használatához való hozzáférés engedélyezésével Ön elfogadja, hogy a LUIS szolgáltatás és az Azure robot keretrendszer feldolgozza a bemenet mögötti szándékot, ami egy továbbfejlesztett, társalgásszerű felhasználói élményt eredményez.</span><span class="sxs-lookup"><span data-stu-id="b8321-156">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="b8321-157">A LUIS szolgáltatás és az Azure robot keretrendszer különböző szintű megfeleléssel rendelkezhet a Dynamics 365 Human Resources alkalmazáshoz képest.</span><span class="sxs-lookup"><span data-stu-id="b8321-157">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="b8321-158">Noha a LUIS szolgáltatás csak a felhasználói lekérdezésekhez férhet hozzá, és nem a felhasználó Dynamics 365 Human Resources adataihoz vagy fiókjához való kapcsolódásra készült, a Dynamics 365 Human Resources robot felhasználója önként adhat meg egy lekérdezést, amely tartalmazza a vevői adatokat, személyes adatokat vagy más adatokat, és az ilyen lekérdezés tartalma elküldhető a LUIS szolgáltatásnak és az Azure robot keretrendszernek.</span><span class="sxs-lookup"><span data-stu-id="b8321-158">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="b8321-159">A felhasználói lekérdezések és üzenetek tartalma legfeljebb 30 napig megmarad a LUIS rendszerben, a nyugalmi formában titkosítva van, és nincs használatban a tréningek vagy a szolgáltatások fejlesztése során.</span><span class="sxs-lookup"><span data-stu-id="b8321-159">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="b8321-160">A Cognitive Services szolgáltatással kapcsolatban  [itt](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/) olvashat többet.</span><span class="sxs-lookup"><span data-stu-id="b8321-160">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="b8321-161">Az Microsoft Teams-alkalmazások felügyeleti beállításainak kezeléséhez nyissa meg a [Microsoft Teams felügyeleti központot](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="b8321-161">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-azure-event-grid-and-microsoft-teams"></a><span data-ttu-id="b8321-162">Microsoft Azure Esemény rácsa és a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b8321-162">Microsoft Azure Event Grid and Microsoft Teams</span></span>

<span data-ttu-id="b8321-163">Amikor a Teamsben a Dynamics 365 Human Resources alkalmazás értesítések funkcióját használja , bizonyos ügyféladatok azon a földrajzi területen kívül kerülnek, amelyen a bérlő humánerőforrás-szolgáltatását telepítették.</span><span class="sxs-lookup"><span data-stu-id="b8321-163">When using the notifications feature for the Dynamics 365 Human Resources app in Teams, certain customer data will flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span> <span data-ttu-id="b8321-164">Dynamics 365 Human Resources az alkalmazott szabadság iránti kérelmének és a munkafolyamat-feladat részleteit átküldi a Microsoft Azure Event Grid és Microsoft Teams szolgáltatásokba.</span><span class="sxs-lookup"><span data-stu-id="b8321-164">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="b8321-165">Ezeket az adatokat az Egyesült Államokban legfeljebb 24 óráig tárolhatjuk, és a rendszer a szállítás és tárolás titkosítja, és a Microsoft vagy az alfeldolgozók nem használják a tanításhoz vagy szolgáltatások fejlesztéséhez.</span><span class="sxs-lookup"><span data-stu-id="b8321-165">This data may be stored for up to 24 hours and processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span>

## <a name="see-also"></a><span data-ttu-id="b8321-166">Lásd még</span><span class="sxs-lookup"><span data-stu-id="b8321-166">See also</span></span> 

[<span data-ttu-id="b8321-167">A Microsoft Teams letöltése és telepítése</span><span class="sxs-lookup"><span data-stu-id="b8321-167">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="b8321-168">Microsoft Teams súgóközpont</span><span class="sxs-lookup"><span data-stu-id="b8321-168">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="b8321-169">Szabadságkérelmek kezelése a Teamsben</span><span class="sxs-lookup"><span data-stu-id="b8321-169">Manage leave requests in Teams</span></span>](hr-teams-leave-app.md)

