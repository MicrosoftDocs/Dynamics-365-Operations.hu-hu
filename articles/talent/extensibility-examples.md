---
title: A Talent bővítése a PowerApps és a Microsoft Flow segítségével – forgatókönyvek
description: Ez a témakör néhány példa bővítési forgatókönyvet ír le a Microsoft Dynamics 365 for Talent alkalmazáshoz, amelyek a Microsoft PowerApps és Microsoft Flow megoldásokat használják.
author: negudava
manager: Annbe
ms.date: 05/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: Dynamics 365 for Talent;PowerApps;Flow;Common Data Service
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent;Core;Experience Apps
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2019-03-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: c113b0f4ab2c8e44d00fcfca3f0a6ca828a854ae
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518160"
---
# <a name="extend-talent-by-using-powerapps-and-microsoft-flow---example-scenarios"></a><span data-ttu-id="a903c-103">A Talent bővítése a PowerApps és a Microsoft Flow segítségével – forgatókönyvek</span><span class="sxs-lookup"><span data-stu-id="a903c-103">Extend Talent by using PowerApps and Microsoft Flow - Example scenarios</span></span>

<span data-ttu-id="a903c-104">Ez a témakör néhány példa bővítési forgatókönyvet ír le a Microsoft Dynamics 365 for Talent alkalmazáshoz, amelyek a Microsoft PowerApps és Microsoft Flow megoldásokat használják.</span><span class="sxs-lookup"><span data-stu-id="a903c-104">This topic describes some examples of extensibility scenarios for Microsoft Dynamics 365 for Talent that use Microsoft PowerApps and Microsoft Flow.</span></span> <span data-ttu-id="a903c-105">Az egyes példákhoz társított megoldáscsomagot importálhatja a PowerApps környezetébe.</span><span class="sxs-lookup"><span data-stu-id="a903c-105">You can import the solution package that is associated with each example into your PowerApps environment.</span></span> <span data-ttu-id="a903c-106">Majd használhatja a csomagokat iránymutatásként vagy kiindulási pontként a szervezetre vonatkozó forgatókönyvek végrehajtásához.</span><span class="sxs-lookup"><span data-stu-id="a903c-106">You can then use the packages either as guidance or as starting points to implement scenarios that are applicable to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a903c-107">Ha a témakörben bemutatott sablonokat és alkalmazást „adott”állapotukban szeretné használni, ügyeljen arra, hogy tesztelje az összeset, és győződjön meg arról minden az Ön implementációjához tartozó forgatókönyvet.</span><span class="sxs-lookup"><span data-stu-id="a903c-107">If you want to use the templates and app that are described in this topic "as is," be sure to test them to make sure that they cover all the scenarios that are specific to your implementation.</span></span>


## <a name="prerequisites"></a><span data-ttu-id="a903c-108">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="a903c-108">Prerequisites</span></span>

- <span data-ttu-id="a903c-109">Csomagok importálásához felhasználóknak rendelkezniük kell a **Környezetkészítő** engedéllyel.</span><span class="sxs-lookup"><span data-stu-id="a903c-109">To import packages, users must have the **Environment Maker** permission.</span></span>
- <span data-ttu-id="a903c-110">Az alkalmazások exportálásához vagy importálásához a felhasználóknak PowerApps Plan 2 licenccel, vagy PowerApps Plan 2 próbalicenccel kell rendelkezniük.</span><span class="sxs-lookup"><span data-stu-id="a903c-110">To export or import apps, users must have a PowerApps Plan 2 license or a PowerApps Plan 2 trial license.</span></span>

## <a name="flow--form-connect"></a><span data-ttu-id="a903c-111">Flow – Form Connect</span><span class="sxs-lookup"><span data-stu-id="a903c-111">Flow – Form Connect</span></span>

<span data-ttu-id="a903c-112">A **Flow – Form Connect** sablon adatok beolvasására használható Microsoft Forms űrlapokból illetve azok tárolására a Common Data Service entitásban.</span><span class="sxs-lookup"><span data-stu-id="a903c-112">The **Flow – Form Connect** template can be used to read data from Microsoft Forms and store it in a Common Data Service entity.</span></span>

<span data-ttu-id="a903c-113">Ez a sablonnal kiterjeszthető, hogy egyéb forgatókönyvekben is használható legyen.</span><span class="sxs-lookup"><span data-stu-id="a903c-113">This template can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="a903c-114">Íme néhány példa:</span><span class="sxs-lookup"><span data-stu-id="a903c-114">Here are some examples:</span></span>

- <span data-ttu-id="a903c-115">Pályázó értékelések rögzítése.</span><span class="sxs-lookup"><span data-stu-id="a903c-115">Capture candidate assessments.</span></span>
- <span data-ttu-id="a903c-116">Tanfolyami kérdőív eredményeinek rögzítése.</span><span class="sxs-lookup"><span data-stu-id="a903c-116">Capture results from course questionnaires.</span></span>
- <span data-ttu-id="a903c-117">Interjú kérdések tárházának összeállítása Emberi erőforrások (HR) rendszergazdáknak.</span><span class="sxs-lookup"><span data-stu-id="a903c-117">Compile a library of interview questions for Human resources (HR) administrators.</span></span>
- <span data-ttu-id="a903c-118">A jelentkező értékelésének rögzítése az interjúfolyamatból</span><span class="sxs-lookup"><span data-stu-id="a903c-118">Capture a candidate's evaluation of the interview process</span></span>

<span data-ttu-id="a903c-119">A Microsoft Dynamics 365: Attract alkalmazásban a képernyők megjelenhetnek Pályázói portálon és a pályázók kitölthetik adataikat.</span><span class="sxs-lookup"><span data-stu-id="a903c-119">In Microsoft Dynamics 365: Attract, forms can appear in Candidate portal, and candidates can fill in details.</span></span> <span data-ttu-id="a903c-120">Képernyők be is ágyazhatók tevékenységként a beosztássablonban.</span><span class="sxs-lookup"><span data-stu-id="a903c-120">Forms can also be embedded as activities in a job template.</span></span>

<span data-ttu-id="a903c-121">Amikor a jelentkező egy elküld egy űrlapot, a Microsoft Flow rögzíti az űrlap benyújtását, beolvassa az adatokat, és tárolja azt a Common Data Service entitásban.</span><span class="sxs-lookup"><span data-stu-id="a903c-121">When a candidate submits a form, Microsoft Flow captures the form submission, reads the data, and stores it in the Common Data Service entity.</span></span>

<span data-ttu-id="a903c-122">A **Flow – Form Connects** sablon és az egyéni entitásstruktúra letöltéséhez nyissa meg a [Flow – Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) elemet a Microsoft letöltőközpontban.</span><span class="sxs-lookup"><span data-stu-id="a903c-122">To download the **Flow – Form Connect** template and Custom Entity Structure, go to [Flow – Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) on the Microsoft Download Center.</span></span>

## <a name="initiate-and-extract-parameters-passed-to-powerapps"></a><span data-ttu-id="a903c-123">A Powerapps részére átadott paraméterek kezdeményezése és kibontása</span><span class="sxs-lookup"><span data-stu-id="a903c-123">Initiate and Extract Parameters Passed to Powerapps</span></span>

<span data-ttu-id="a903c-124">A **A Powerapps részére átadott paraméterek kezdeményezése és kibontása** sablon bármilyen PowerApps forgatókönyv kiindulópontjaként használható, amely az Attract alkalmazásra jellemző.</span><span class="sxs-lookup"><span data-stu-id="a903c-124">The **Initiate and Extract Parameters Passed to Powerapps** template can be used as a starting point for any PowerApps scenario that is specific to Attract.</span></span> <span data-ttu-id="a903c-125">Az Attract részére átadott összes alapértelmezett paramétert tartalmazza, mint **Álláspályázat**, **Jelentkező azonosítója**, és **JobID**.</span><span class="sxs-lookup"><span data-stu-id="a903c-125">It includes all the default parameters that are passed by Attract, such as **Job Application**, **Candidate ID**, and **JobID**.</span></span>

<span data-ttu-id="a903c-126">Ezzel a sablonnal lekérhető a jelölt értékelési űrlapja, hogy a humánerőforrás-vezető megtekinthesse a pályázó által kitöltött értékelést.</span><span class="sxs-lookup"><span data-stu-id="a903c-126">This template can be used to retrieve a candidate assessment form, so that a hiring manager can view the assessment that a candidate filled in.</span></span>

<span data-ttu-id="a903c-127">A PowerApps használatával létrehozott alkalmazások beágyazhatók az Attract feladatsablonjába.</span><span class="sxs-lookup"><span data-stu-id="a903c-127">Apps that are created by using PowerApps can be embedded into the job template in Attract.</span></span>

<span data-ttu-id="a903c-128">A **Powerapps részére átadott paraméterek kezdeményezése és kibontása** sablon és az egyéni entitásstruktúra letöltéséhez látogassa meg a [A Powerapps részére átadott paraméterek kezdeményezése és kibontása](https://go.microsoft.com/fwlink/?linkid=2081991) elemet a Microsoft letöltőközpontban.</span><span class="sxs-lookup"><span data-stu-id="a903c-128">To download the **Initiate and Extract Parameters Passed to Powerapps** template and Custom Entity Structure, go to [Initiate and Extract Parameters Passed to Powerapps](https://go.microsoft.com/fwlink/?linkid=2081991) on the Microsoft Download Center.</span></span>

## <a name="integration-with-office-365"></a><span data-ttu-id="a903c-129">Integráció a Office 365 rendszerrel</span><span class="sxs-lookup"><span data-stu-id="a903c-129">Integration with Office 365</span></span>

<span data-ttu-id="a903c-130">Az **Office 365 integráció** alkalmazást használható a csapatinformációk lekéréshez a Microsoft Office 365 bejelentkezett felhasználói számára.</span><span class="sxs-lookup"><span data-stu-id="a903c-130">The **Integration with Office 365** app can be used to extract team information for signed-in users from Microsoft Office 365.</span></span> <span data-ttu-id="a903c-131">Ez a Talent dolgozóira hivatkozik az érkezéskori és távozáskori blokkolás részletes adatai, és a kivételbejegyzések lekéréséhez.</span><span class="sxs-lookup"><span data-stu-id="a903c-131">It references workers in Talent to extract clock-in and clock-out details and exception recordings.</span></span> <span data-ttu-id="a903c-132">Az Érkezéskori és távozáskori blokkolás adatai egyéni Common Data Service entitásokban vannak tárolva.</span><span class="sxs-lookup"><span data-stu-id="a903c-132">Clock-in and Clock-out details are stored in custom Common Data Service entities.</span></span> <span data-ttu-id="a903c-133">A program feltételezi, hogy ezek az adatok ki vannak töltve integráción keresztül egy harmadik fél rendszeréből.</span><span class="sxs-lookup"><span data-stu-id="a903c-133">The assumption is that these details are filled in from third-party systems via integration.</span></span>

<span data-ttu-id="a903c-134">Ez az alkalmazás kiterjeszthető, hogy egyéb forgatókönyvekben is használható legyen.</span><span class="sxs-lookup"><span data-stu-id="a903c-134">This app can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="a903c-135">Például egy csapat szabadságadatainak, a naptár események és a más csapat-specifikus eseményeket megjelenítésére is használható.</span><span class="sxs-lookup"><span data-stu-id="a903c-135">For example, it can be used to show team vacation information, calendar events, and any team-specific events.</span></span>

<span data-ttu-id="a903c-136">Az **Office 365 integráció** és az egyéni entitásstruktúra letöltéséhez lépjen az [Office 365 integráció](https://go.microsoft.com/fwlink/?linkid=2081787) helyre a Microsoft letöltőközpontban.</span><span class="sxs-lookup"><span data-stu-id="a903c-136">To download the **Integration with Office 365** app and Custome Entity Structure, go to [Integration with Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) on the Microsoft Download Center.</span></span>

## <a name="flow--email-notification"></a><span data-ttu-id="a903c-137">Flow – E-mail-értesítés</span><span class="sxs-lookup"><span data-stu-id="a903c-137">Flow – Email Notification</span></span>

<span data-ttu-id="a903c-138">A **Flow – E-mail-értesítés** sablon e-mail értesítési forgatókönyvekhez használható.</span><span class="sxs-lookup"><span data-stu-id="a903c-138">The **Flow – Email Notification** template can be used for email notification scenarios.</span></span> <span data-ttu-id="a903c-139">Használható értesítő e-mailek indítására azon pályázók számára, akiket a toborzócsapat elutasít a toborzási folyamat bármelyik szakaszában.</span><span class="sxs-lookup"><span data-stu-id="a903c-139">It can be used to trigger notification emails to candidates that the hiring team rejects during any stage of the recruiting process.</span></span>

<span data-ttu-id="a903c-140">Ez a sablon kiterjeszthető a változások nyomon követésére a toborzási folyamat során a pályázó fokozatra és értesítés küldéséhez, a felvételi csapat és jelölt számára.</span><span class="sxs-lookup"><span data-stu-id="a903c-140">This template can be extended to track changes to the candidate stage throughout the recruiting process, and to send notifications to the hiring team and candidate.</span></span>

<span data-ttu-id="a903c-141">Általában a Common Data Service rendszerben tárolt entitásokhoz a folyamatok beállíthatók úgy, hogy értesítést küldjenek a Core HR, Attract vagy Dynamics 365 Talent: Onboard rendszerben történt eseményekről.</span><span class="sxs-lookup"><span data-stu-id="a903c-141">In general, for entities that are stored in Common Data Service, flows can be set up to send notifications for events that occur in Core HR, Attract, or Dynamics 365 Talent: Onboard.</span></span>

<span data-ttu-id="a903c-142">A **Flow – E-mail-értesítés** sablon letöltéséhez ugorjon a [Flow – E-mail-értesítések](https://go.microsoft.com/fwlink/?linkid=2082103) oldalra a Microsoft Letöltőközpontban</span><span class="sxs-lookup"><span data-stu-id="a903c-142">To download the **Flow – Email Notification** template, go to [Flow – Email Notification](https://go.microsoft.com/fwlink/?linkid=2082103) on the Microsoft Download Center.</span></span>

## <a name="flow--sql-connect-and-execute"></a><span data-ttu-id="a903c-143">Flow – SQL csatlakozás és végrehajtás</span><span class="sxs-lookup"><span data-stu-id="a903c-143">Flow – SQL Connect and execute</span></span>

<span data-ttu-id="a903c-144">A **Flow – SQL csatlakozás és végrehajtás** sablon csatlakozik a Microsoft SQL Server kiszolgálóhoz, és lehetővé teszi az SQL-lekérdezések futtatását.</span><span class="sxs-lookup"><span data-stu-id="a903c-144">The **Flow – SQL Connect and execute** template connects to Microsoft SQL Server and enables SQL queries to be run.</span></span>

<span data-ttu-id="a903c-145">Annak ellenére, hogy ez a sablon célja SQL táblák olvasása és frissítése, bővíthető, hogy más forgatókönyvekhez is használható legyen.</span><span class="sxs-lookup"><span data-stu-id="a903c-145">Although this template is designed to read and update SQL tables, it can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="a903c-146">Például használható előkészítési tábla kitöltés;re Common Data Service rekordokkal SQL Server kiszolgálóról, és előkészítési tábla rendszeres időközönkénti szinkronizálásához növekményes leküldéssel egy SQL Server kiszolgálóról.</span><span class="sxs-lookup"><span data-stu-id="a903c-146">For example, it can be used to fill a staging table in Common Data Service with records from SQL Server, and to periodically synchronize the staging table by using an incremental push from SQL Server.</span></span>

<span data-ttu-id="a903c-147">A **Flow – SQL csatlakozás és végrehajtás** sablon letöltéséhez nyissa meg a [Flow – SQL csatlakozás és végrehajtás](https://go.microsoft.com/fwlink/?linkid=2081789) elemet a Microsoft letöltőközpontban.</span><span class="sxs-lookup"><span data-stu-id="a903c-147">To download the **Flow – SQL Connect and execute** template, go to [Flow – SQL Connect and execute](https://go.microsoft.com/fwlink/?linkid=2081789) on the Microsoft Download Center.</span></span>

## <a name="flow--sharepoint-integration"></a><span data-ttu-id="a903c-148">Flow – SharePoint-integráció</span><span class="sxs-lookup"><span data-stu-id="a903c-148">Flow – SharePoint Integration</span></span>

<span data-ttu-id="a903c-149">A **Flow – SharePoint-integráció** sablon használható adatok beolvasására egy Microsoft SharePoint-listát, a lista mezőértékeinek összehasonlításához bármely Common Data Service entitással, és az összehasonlítás eredményéről egy értesítő e-mail küldéséhez.</span><span class="sxs-lookup"><span data-stu-id="a903c-149">The **Flow – SharePoint Integration** template can be used to read data from a Microsoft SharePoint list, compare the list with field values for any Common Data Service entity, and send the results of the comparison as a notification email.</span></span> 

<span data-ttu-id="a903c-150">Előfordulhat, hogy a szervezetnek sürgősen szüksége van egy szakértelemre.</span><span class="sxs-lookup"><span data-stu-id="a903c-150">An organization might have a set of skills that it urgently requires.</span></span> <span data-ttu-id="a903c-151">A szakértelmek tárolható SharePoint megoldásban, egy SharePoint listában.</span><span class="sxs-lookup"><span data-stu-id="a903c-151">These skills can be stored in SharePoint as a SharePoint list.</span></span> <span data-ttu-id="a903c-152">Ha egy jelölt olyan munkára jelentkezik, amelyhez szakértelmek vannak felsorolva, ha jelentős egyezés figyelhető meg a jelentkező szakértelme és a SharePoint megoldásban tárolt szakértelem között, egy értesítő e-mail érkezik.</span><span class="sxs-lookup"><span data-stu-id="a903c-152">When a candidate applies for any job that a set of required skills is listed for, if there is a significant match between the candidate's skill and the skills that are stored in SharePoint, a notification email is sent.</span></span> <span data-ttu-id="a903c-153">Ezzel a módszerrel pozíciókat, amelyek sürgősen szükségesek gyorsabban be lehet tölteni, mivel az értesítések lehetővé teszik a toborzóknak, hogy felvegyék a kapcsolatot és felvegyék a jelentkezőket szervezet szintjén.</span><span class="sxs-lookup"><span data-stu-id="a903c-153">In this way, positions that are urgently required are filled faster, because the notifications help recruiters reach out and cross-hire candidates throughout the organization.</span></span>

<span data-ttu-id="a903c-154">Ezzel a sablon bővíthető, így minden a SharePoint integrációt érintő forgatókönyvhöz használható.</span><span class="sxs-lookup"><span data-stu-id="a903c-154">This template can be extended so that it can be used for any scenario that involves SharePoint integration.</span></span>

<span data-ttu-id="a903c-155">A **Flow – SharePoint integráció** sablon letöltéséhez ugorjon a [Flow – SharePoint integráció](https://go.microsoft.com/fwlink/?linkid=2082109) oldalra a Microsoft Letöltőközpontban</span><span class="sxs-lookup"><span data-stu-id="a903c-155">To download the **Flow – SharePoint Integration** template, go to [Flow – SharePoint Integration](https://go.microsoft.com/fwlink/?linkid=2082109) on the Microsoft Download Center.</span></span>

## <a name="admin-console-to-manage-talent-pools"></a><span data-ttu-id="a903c-156">Felügyeleti konzol a tehetségállományok kezeléséhez</span><span class="sxs-lookup"><span data-stu-id="a903c-156">Admin console to manage talent pools</span></span>

<span data-ttu-id="a903c-157">Ha engedélyezi a LinkedIn integrációját, az Attract automatikusan létrehoz egy LinkedIn tehetségállományt.</span><span class="sxs-lookup"><span data-stu-id="a903c-157">When you enable integration with LinkedIn, Attract automatically createas a LinkedIn talent pool.</span></span> <span data-ttu-id="a903c-158">Amikor egy állásközvetítő InMail-t cserél LinkedIn-en keresztül, az Attract létrehoz egy profilt a toborzotthoz, és a toborzott tagja lesz a LinkedIn tehetségállományának.</span><span class="sxs-lookup"><span data-stu-id="a903c-158">When a recruiter exchanges InMail with a recruit through LinkedIn, Attract creates a profile for the recruit, and the recruit becomes a member of the LinkedIn talent pool.</span></span> <span data-ttu-id="a903c-159">Ez a PowerApps alkalmazás jól használható a tehetségállományokban lévő jelöltek átszervezéséhez a szakértelem alapján.</span><span class="sxs-lookup"><span data-stu-id="a903c-159">This PowerApps app is useful for reorganizing candidates in talent pools based on skill.</span></span>

<span data-ttu-id="a903c-160">Futtassa ezt a PowerApps alkalmazást felügyeleti konzolként a következő feladatok végrehajtásához:</span><span class="sxs-lookup"><span data-stu-id="a903c-160">Run this PowerApps app as an admin console to perform the following tasks:</span></span>

- <span data-ttu-id="a903c-161">Jelöltek lsitázása a tehetségállományban</span><span class="sxs-lookup"><span data-stu-id="a903c-161">List candidates in a talent pool</span></span>
- <span data-ttu-id="a903c-162">A tehetségállományból jelöltek hozzáadása egy álláshoz vagy eltávolításuk</span><span class="sxs-lookup"><span data-stu-id="a903c-162">Add and remove candidates from a talent pool</span></span>
- <span data-ttu-id="a903c-163">Jelöltek áthelyezése egyik tehetségállományból egy másikba</span><span class="sxs-lookup"><span data-stu-id="a903c-163">Move candidates from one talent pool to another</span></span>
- <span data-ttu-id="a903c-164">Annak meghatározása, hogy a jelöltek már részei-e egy tehetségállománynak, mielőtt áthelyezik azokat</span><span class="sxs-lookup"><span data-stu-id="a903c-164">Determine whether candidates are already part of a talent pool before moving them</span></span>
- <span data-ttu-id="a903c-165">A jelentkezők szakértelmének ellenőrzésére, mielőtt áthelyeznék őket egy másik tehetségállományba</span><span class="sxs-lookup"><span data-stu-id="a903c-165">Check the skills of candidates before moving them to other talent pools</span></span>

<span data-ttu-id="a903c-166">Ez a PowerApps alkalmazás több a többhöz kapcsolatot használ, így sablonként használhatja más esetekhez, ahol olyan rekordokat kell kinyernie, amelyek több a többhöz kapcsolattal rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="a903c-166">This PowerApps app uses many-to-many relationships, so you can use it as a template for other scenarios where you need to extract records that have many-to-many relationships.</span></span>

<span data-ttu-id="a903c-167">A **Felügyeleti konzol a tehetségállományok kezeléséhez** sablon kezeléséhez, nyissa meg [Felügyeleti konzol a tehetségállományok kezeléséhez](http://www.microsoft.com/downloads/details.aspx?FamilyID=780a5eee-0e2a-4159-9a83-009f9ccdc469) oldalt a Microsoft letöltőközpontban.</span><span class="sxs-lookup"><span data-stu-id="a903c-167">To download the **Admin console to manage talent pools** template,  go to [Admin console to manage talent pools](http://www.microsoft.com/downloads/details.aspx?FamilyID=780a5eee-0e2a-4159-9a83-009f9ccdc469) on the Microsoft Download Center.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a903c-168">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="a903c-168">Additional resources</span></span>

[<span data-ttu-id="a903c-169">A Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="a903c-169">The Microsoft Power Platform</span></span>](https://docs.microsoft.com/power-platform/admin/admin-documentation)

[<span data-ttu-id="a903c-170">Alkalmazás bérlők és környezetek közötti áttelepítése</span><span class="sxs-lookup"><span data-stu-id="a903c-170">Migrate app between tenants and environments</span></span>](https://docs.microsoft.com/en-us/power-platform/admin/environment-and-tenant-migration)
