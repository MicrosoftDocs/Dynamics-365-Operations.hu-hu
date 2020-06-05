---
title: Human Resources alkalmazás a Teams rendszerben
description: Ez a témakör bemutatja a Microsoft Dynamics 365 Human Resources alkalmazást a Microsoft Teams rendszerben.
author: andreabichsel
manager: AnnBe
ms.date: 05/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 423ec36a73e8af9d915c5cfe16bd4d552448e2b6
ms.sourcegitcommit: d1541831d556b722a71aed442043ffb4a4576d87
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/20/2020
ms.locfileid: "3388116"
---
# <a name="human-resources-app-in-teams"></a><span data-ttu-id="59b67-103">Human Resources alkalmazás a Teams rendszerben</span><span class="sxs-lookup"><span data-stu-id="59b67-103">Human Resources app in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="59b67-104">A Microsoft Dynamics 365 Human Resources alkalmazás a Microsoft Teams rendszerben lehetővé teszi, hogy az alkalmazottak gyorsan kérelmezzenek szabadságot, és megtekintsék a szabadságegyenlegükett közvetlenül a Microsoft Teams rendszerben.</span><span class="sxs-lookup"><span data-stu-id="59b67-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets employees quickly request time off and view their time-off balance information in Microsoft Teams.</span></span> <span data-ttu-id="59b67-105">Az alkalmazottak egy robottal léphetnek kapcsolatba információ kéréséhez.</span><span class="sxs-lookup"><span data-stu-id="59b67-105">Employees can interact with a bot to request information.</span></span> <span data-ttu-id="59b67-106">A **Szabadság** lapon részletesebb információk olvashatók.</span><span class="sxs-lookup"><span data-stu-id="59b67-106">The **Time off** tab provides more detailed information.</span></span>

![Human Resources Teams szabadságkezelő alkalmazás robot](./media/hr-admin-teams-leave-app-bot.png)

![Human Resources Teams szabadságkezelő alkalmazás Szabadság lap](./media/hr-teams-leave-app-timeoff-tab.png)

## <a name="install-and-setup"></a><span data-ttu-id="59b67-109">Telepítés és beállítás</span><span class="sxs-lookup"><span data-stu-id="59b67-109">Install and setup</span></span>

<span data-ttu-id="59b67-110">A Human Resources app a Teams áruházban található.</span><span class="sxs-lookup"><span data-stu-id="59b67-110">You can find the Human Resources app in the Teams store.</span></span> <span data-ttu-id="59b67-111">A Teams alkalmazás telepítésével kapcsolatos tudnivalókat lásd: [Szabadságkérelmek kezelése a Teams rendszerben](hr-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="59b67-111">For information about installing the Teams app, see [Manage leave requests in Teams](hr-teams-leave-app.md).</span></span>

<span data-ttu-id="59b67-112">A Teams alkalmazásengedélyeinek kezelésével kapcsolatos információkért lásd: [Alkalmazásengedély-irányelvek kezelése a Microsoft Teams rendszerben](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="59b67-112">For information about managing app permissions in Teams, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="known-issues"></a><span data-ttu-id="59b67-113">Ismert problémák</span><span class="sxs-lookup"><span data-stu-id="59b67-113">Known issues</span></span>

| <span data-ttu-id="59b67-114">Kiadás</span><span class="sxs-lookup"><span data-stu-id="59b67-114">Issue</span></span> | <span data-ttu-id="59b67-115">Állapot</span><span class="sxs-lookup"><span data-stu-id="59b67-115">Status</span></span> |
| --- | --- |
| <span data-ttu-id="59b67-116">Az egyenleg nem helyes, amikor jövőbeli dátumra vonatkozó szabadságot küld be.</span><span class="sxs-lookup"><span data-stu-id="59b67-116">The balance is incorrect when submitting time off for a future date.</span></span> | <span data-ttu-id="59b67-117">Az előrejelzés még nem érhető el.</span><span class="sxs-lookup"><span data-stu-id="59b67-117">Forecasting isn't yet available.</span></span> <span data-ttu-id="59b67-118">A megjelenített egyenleg az aktuális dátumra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="59b67-118">The balance displays for the current date.</span></span> |
| <span data-ttu-id="59b67-119">Ha egy meglévő kérelemben szereplő órák számát csökkenti, akkor a **Fennmaradó egyenleg** csökken, ahelyett, hogy növekedne.</span><span class="sxs-lookup"><span data-stu-id="59b67-119">When reducing the number of hours taken in an existing request, the **Remaining balance** goes down instead of up.</span></span> | <span data-ttu-id="59b67-120">Ezt az ismert problémát a jövőben fogjuk kezelni.</span><span class="sxs-lookup"><span data-stu-id="59b67-120">We'll address this known issue in the future.</span></span> <span data-ttu-id="59b67-121">A kijelzett érték helytelen, de a megfelelő összegeket a program elküldésekor korrigálja.</span><span class="sxs-lookup"><span data-stu-id="59b67-121">The display is incorrect, but the correct amounts are adjusted upon submission.</span></span> |
| <span data-ttu-id="59b67-122">Két **Közelgő szabadság** kártya jelenik meg ugyanarra a dátumra.</span><span class="sxs-lookup"><span data-stu-id="59b67-122">Two **Upcoming time off** cards display for the same dates.</span></span> | <span data-ttu-id="59b67-123">A kártyák egyéni beküldéseket jelentenek.</span><span class="sxs-lookup"><span data-stu-id="59b67-123">The cards represent individual submissions.</span></span> <span data-ttu-id="59b67-124">A visszajelzéseket továbbra is figyelembe véve módosításokat fogunk eszközölni.</span><span class="sxs-lookup"><span data-stu-id="59b67-124">We'll continue to take feedback and make adjustments.</span></span> |
| <span data-ttu-id="59b67-125">Nem lehet visszavonni egy **Ellenőrzés alatt** állapotú kérelmet.</span><span class="sxs-lookup"><span data-stu-id="59b67-125">Unable to cancel an **In review** request.</span></span> | <span data-ttu-id="59b67-126">Ez a funkció jelenleg nem támogatott, és egy későbbi verzióban kerül hozzáadásra.</span><span class="sxs-lookup"><span data-stu-id="59b67-126">This functionality isn't currently supported and will be added in a future release.</span></span> |
| <span data-ttu-id="59b67-127">Az egyenleg adatait a mai naptól számítja ki a program.</span><span class="sxs-lookup"><span data-stu-id="59b67-127">Balance information is calculated as of today.</span></span> | <span data-ttu-id="59b67-128">A rendszer jelenleg nem jeleníti meg a könyvelési időszak egyenlegeit, még akkor sem, ha be van állítva a Szabadság és távollét paraméterei között.</span><span class="sxs-lookup"><span data-stu-id="59b67-128">The system currently doesn't display balances as of the accrual period, even if it's configured in Leave and absence parameters.</span></span> |

## <a name="privacy-notice"></a><span data-ttu-id="59b67-129">Adatvédelmi nyilatkozat</span><span class="sxs-lookup"><span data-stu-id="59b67-129">Privacy notice</span></span>

<span data-ttu-id="59b67-130">A Microsoft Teams rendszer Dynamics 365 Human Resources robotjával elemezhetők a felhasználó szöveges bemenetei az alapul szolgáló kérdés/szándék megértéséhez.</span><span class="sxs-lookup"><span data-stu-id="59b67-130">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="59b67-131">A felhasználó bemenete (például a „Contoso fiók keresése”) a Microsoft egyik kognitív szolgáltatásához, a Language Understanding Intelligent Service (LUIS) szolgáltatáshoz van irányítva.</span><span class="sxs-lookup"><span data-stu-id="59b67-131">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="59b67-132">A LUIS-ról  [itt](https://www.luis.ai/) olvashat többet.</span><span class="sxs-lookup"><span data-stu-id="59b67-132">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="59b67-133">A LUIS szolgáltatás egyértelműsíti vagy megérti a felhasználói bevitel szándékát (ebben az esetben a szándék az, hogy információt találjon) és a cél entitást (ebben az esetben a szándékolt entitás egy Contoso nevű számla).</span><span class="sxs-lookup"><span data-stu-id="59b67-133">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="59b67-134">Ez az információ ezután a Microsoft  [Azure bot keretrendszerébe](https://azure.microsoft.com/services/bot-service/)  kerül, amely interaktál a Dynamics 365 Human Resources adataival, és lekéri a kívánt információkat a felhasználói lekérdezéshez.</span><span class="sxs-lookup"><span data-stu-id="59b67-134">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/) which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="59b67-135">A robot telepítésével és a használatához való hozzáférés engedélyezésével Ön elfogadja, hogy a LUIS szolgáltatás és az Azure robot keretrendszer feldolgozza a bemenet mögötti szándékot, ami egy továbbfejlesztett, társalgásszerű felhasználói élményt eredményez.</span><span class="sxs-lookup"><span data-stu-id="59b67-135">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="59b67-136">A LUIS szolgáltatás és az Azure robot keretrendszer különböző szintű megfeleléssel rendelkezhet a Dynamics 365 Human Resources alkalmazáshoz képest.</span><span class="sxs-lookup"><span data-stu-id="59b67-136">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="59b67-137">Noha a LUIS szolgáltatás csak a felhasználói lekérdezésekhez férhet hozzá, és nem a felhasználó Dynamics 365 Human Resources adataihoz vagy fiókjához való kapcsolódásra készült, a Dynamics 365 Human Resources robot felhasználója önként adhat meg egy lekérdezést, amely tartalmazza a vevői adatokat, személyes adatokat vagy más adatokat, és az ilyen lekérdezés tartalma elküldhető a LUIS szolgáltatásnak és az Azure robot keretrendszernek.</span><span class="sxs-lookup"><span data-stu-id="59b67-137">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="59b67-138">A felhasználói lekérdezések és üzenetek tartalma legfeljebb 30 napig megmarad a LUIS rendszerben, a nyugalmi formában titkosítva van, és nincs használatban a tréningek vagy a szolgáltatások fejlesztése során.</span><span class="sxs-lookup"><span data-stu-id="59b67-138">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="59b67-139">A Cognitive Services szolgáltatással kapcsolatban  [itt](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/) olvashat többet.</span><span class="sxs-lookup"><span data-stu-id="59b67-139">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="59b67-140">Az Microsoft Teams-alkalmazások felügyeleti beállításainak kezeléséhez nyissa meg a [Microsoft Teams felügyeleti központot](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="59b67-140">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span> 

## <a name="see-also"></a><span data-ttu-id="59b67-141">Lásd még</span><span class="sxs-lookup"><span data-stu-id="59b67-141">See also</span></span> 

[<span data-ttu-id="59b67-142">A Microsoft Teams letöltése és telepítése</span><span class="sxs-lookup"><span data-stu-id="59b67-142">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="59b67-143">Microsoft Teams súgóközpont</span><span class="sxs-lookup"><span data-stu-id="59b67-143">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="59b67-144">Szabadság- és távollétkérelmek kezelése a Teams alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="59b67-144">Manage leave requests in Teams</span></span>](hr-teams-leave-app.md)

