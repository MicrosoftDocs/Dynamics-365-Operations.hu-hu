---
title: Saját csapat mobil munkaterület
description: Ez a témakör tájékoztatást nyújt a Saját csapat mobil munkaterületről, amely lehetővé teszi a vezetők számára a közvetlen beosztottjaik és a bővebb személyzet megtekintését.
author: ShielaSogge
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 5dc2f8b5195fb5210ca6399cbf744f210671f475
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570089"
---
# <a name="my-team-mobile-workspace"></a><span data-ttu-id="51173-103">Saját csapat mobil munkaterülete</span><span class="sxs-lookup"><span data-stu-id="51173-103">My team mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="51173-104">Ez a témakör a **Saját csapat** mobil munkaterülettel kapcsolatban tartalmaz tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="51173-104">This topic provides information about the **My team** mobile workspace.</span></span> <span data-ttu-id="51173-105">A munkaterület lehetővé teszi a vezetők számára a közvetlen beosztottjaik és a bővebb személyzet megtekintését.</span><span class="sxs-lookup"><span data-stu-id="51173-105">This workspace lets managers view their direct reports and extended staff.</span></span> <span data-ttu-id="51173-106">Emellett pozitív visszajelzést is küldhetnek beosztotti láncukban levő egyéneknek.</span><span class="sxs-lookup"><span data-stu-id="51173-106">They can also send praise to individuals in their reporting chain.</span></span>

<span data-ttu-id="51173-107">A mobil munkaterületet a Finance and Operations mobilalkalmazásban való használatra tervezték.</span><span class="sxs-lookup"><span data-stu-id="51173-107">This mobile workspace is intended to be used with the Finance and Operations mobile app.</span></span>

## <a name="overview"></a><span data-ttu-id="51173-108">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="51173-108">Overview</span></span> 
<span data-ttu-id="51173-109">A **Saját csapat** mobil munkaterület a következő műveletek végrehajtását teszi lehetővé a vezetők számára:</span><span class="sxs-lookup"><span data-stu-id="51173-109">The **My team** mobile workspace lets managers perform these tasks:</span></span>

- <span data-ttu-id="51173-110">A vezető közvetlen beosztottjait tartalmazó lista megtekintése.</span><span class="sxs-lookup"><span data-stu-id="51173-110">View a list of the manager’s direct reports.</span></span>
- <span data-ttu-id="51173-111">A vezető kiterjesztett beosztotti csapatát tartalmazó lista megtekintése.</span><span class="sxs-lookup"><span data-stu-id="51173-111">View a list of the manager’s extended reporting team.</span></span>
- <span data-ttu-id="51173-112">Részletes információk tekinthetők meg mindegyik csoporttagról, például születési dátum, szolgálati idő dátuma, foglalkoztatotti évek száma, kompenzációs és teljesítményadatok.</span><span class="sxs-lookup"><span data-stu-id="51173-112">View detailed information for each team member, such as birth date, seniority date, years of service, and compensation and performance information.</span></span>
- <span data-ttu-id="51173-113">Pozitív visszajelzés küldése egy személynek a vezető kiterjesztett beosztotti csoportjában.</span><span class="sxs-lookup"><span data-stu-id="51173-113">Send praise to any individual in the manager’s extended reporting team.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="51173-114">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="51173-114">Prerequisites</span></span>
<span data-ttu-id="51173-115">A mobil munkaterület csak a következő előfeltételek teljesülése esetén használható.</span><span class="sxs-lookup"><span data-stu-id="51173-115">Before you can use this mobile workspace, the following prerequisites must be met.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="51173-116">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="51173-116">Prerequisite</span></span></th>
<th><span data-ttu-id="51173-117">Szerep</span><span class="sxs-lookup"><span data-stu-id="51173-117">Role</span></span></th>
<th><span data-ttu-id="51173-118">Leírás</span><span class="sxs-lookup"><span data-stu-id="51173-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="51173-119">A következő termékek egyikének telepítve kell lennie a szervezeténél:</span><span class="sxs-lookup"><span data-stu-id="51173-119">One of the following products must be deployed in your organization:</span></span>
<ul><li><span data-ttu-id="51173-120">Egy Finance and Operations-alkalmazás</span><span class="sxs-lookup"><span data-stu-id="51173-120">A Finance and Operations app</span></span></li>
<li><span data-ttu-id="51173-121">Microsoft Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="51173-121">Microsoft Dynamics 365 Human Resources</span></span></li>
</ul>
</td>
<td><span data-ttu-id="51173-122">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="51173-122">System administrator</span></span></td>
<td><span data-ttu-id="51173-123">Ha a vállalati hálózatra még nincs telepítve a Finance and Operations alkalmazás, lásd a következő tudnivalókat: <a href="../deployment/deploy-demo-environment.md">Bemutatókörnyezet telepítése</a>.</span><span class="sxs-lookup"><span data-stu-id="51173-123">If you don&#39;t already have a Finance and Operations app deployed in your organization, see <a href="../deployment/deploy-demo-environment.md">Deploy a demo environment</a>.</span></span> <span data-ttu-id="51173-124">Ha a szervezetében még nincs telepítve az Emberi erőforrások, a rendszergazda hozzáférhet a próbaverzióhoz az <a href="https://dynamics.microsoft.com/human-resources/overview/">Emberi erőforrások weboldaláról</a>.</span><span class="sxs-lookup"><span data-stu-id="51173-124">If you don&#39;t already have Human Resources deployed in your organization, the system administrator can access a trial version from the <a href="https://dynamics.microsoft.com/human-resources/overview/">Human Resources webpage</a>.</span></span>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="51173-125">A <strong>Saját csapat</strong> mobil munkaterületet közzé kell tenni.</span><span class="sxs-lookup"><span data-stu-id="51173-125">The <strong>My team</strong> mobile workspace must be published.</span></span></td>
<td><span data-ttu-id="51173-126">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="51173-126">System administrator</span></span></td>
<td><span data-ttu-id="51173-127">Lásd: <a href="publish-mobile-workspace.md">Mobil munkaterület közzététele</a>.</span><span class="sxs-lookup"><span data-stu-id="51173-127">See <a href="publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="51173-128">A mobilalkalmazás letöltése és telepítése</span><span class="sxs-lookup"><span data-stu-id="51173-128">Download and install the mobile app</span></span>

<span data-ttu-id="51173-129">A Finance and Operations mobilalkalmazás letöltése és telepítése:</span><span class="sxs-lookup"><span data-stu-id="51173-129">Download and install the Finance and Operations mobile app:</span></span>

-   [<span data-ttu-id="51173-130">Android telefonok esetében:</span><span class="sxs-lookup"><span data-stu-id="51173-130">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="51173-131">iPhone esetében:</span><span class="sxs-lookup"><span data-stu-id="51173-131">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="51173-132">Bejelentkezés a mobilalkalmazásba</span><span class="sxs-lookup"><span data-stu-id="51173-132">Sign in to the mobile app</span></span>
1.  <span data-ttu-id="51173-133">Indítsa el az alkalmazást a mobileszközén.</span><span class="sxs-lookup"><span data-stu-id="51173-133">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="51173-134">Adja meg a Microsoft Dynamics 365 URL-címét.</span><span class="sxs-lookup"><span data-stu-id="51173-134">Enter your Microsoft Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="51173-135">Az első bejelentkezéskor a rendszer kéri a felhasználónevet és jelszót.</span><span class="sxs-lookup"><span data-stu-id="51173-135">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="51173-136">Adja meg a hitelesítési adatait.</span><span class="sxs-lookup"><span data-stu-id="51173-136">Enter your credentials.</span></span>
4.  <span data-ttu-id="51173-137">A bejelentkezést követően megjelennek a vállalata rendelkezésre álló munkaterületek.</span><span class="sxs-lookup"><span data-stu-id="51173-137">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="51173-138">Vegye figyelembe, hogy ha a rendszergazda később teszi közzé az új munkaterületet, akkor Önnek frissítenie kell a mobil munkaterületek listáját.</span><span class="sxs-lookup"><span data-stu-id="51173-138">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

<span data-ttu-id="51173-139">[![Lekérés frissítéshez](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="51173-139">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="view-team-members-by-using-the-my-team-mobile-workspace"></a><span data-ttu-id="51173-140">Csoporttagok megtekintése a Saját csapat mobil munkaterület használatával</span><span class="sxs-lookup"><span data-stu-id="51173-140">View team members by using the My team mobile workspace</span></span>
1.  <span data-ttu-id="51173-141">A mobil alkalmazásában jelölje ki a **Saját csapat** munkaterületet.</span><span class="sxs-lookup"><span data-stu-id="51173-141">In the mobile app, select the **My team** workspace.</span></span> <span data-ttu-id="51173-142">Megjelenik a csoporttagok listája.</span><span class="sxs-lookup"><span data-stu-id="51173-142">A list of team members is shown.</span></span> <span data-ttu-id="51173-143">A lista emellett megjeleníti minden csapattag beosztását, valamint a tag közvetlen beosztottjait, ha vannak ilyenek.</span><span class="sxs-lookup"><span data-stu-id="51173-143">The list also shows each team member's title, and any direct reports that the member has.</span></span>
2.  <span data-ttu-id="51173-144">Válasszon ki egy csapattagot.</span><span class="sxs-lookup"><span data-stu-id="51173-144">Select a team member.</span></span> <span data-ttu-id="51173-145">Megjelenik a **Csapattag összefoglalója** lap.</span><span class="sxs-lookup"><span data-stu-id="51173-145">The **Team member summary** page appears.</span></span> <span data-ttu-id="51173-146">Az ezen a lapon található információk tartalmazzák a csapattag születési dátumát, a szolgálati ideje dátuma, azt, hogy hány éve foglalkoztatott, a jelenlegi beosztásban eltöltött évek számát, valamint a kompenzációs adatokat.</span><span class="sxs-lookup"><span data-stu-id="51173-146">The information on this page includes the team member's birth date, seniority date, years of service, years in the current position, and compensation information.</span></span>

## <a name="view-extended-team-members-by-using-the-my-team-mobile-workspace"></a><span data-ttu-id="51173-147">Bővített csoport tagjainak megtekintése a Saját csapat mobil munkaterület használatával</span><span class="sxs-lookup"><span data-stu-id="51173-147">View extended team members by using the My team mobile workspace</span></span>
1.  <span data-ttu-id="51173-148">A mobil alkalmazásában jelölje ki a **Saját csapat** munkaterületet.</span><span class="sxs-lookup"><span data-stu-id="51173-148">In the mobile app, select the **My team** workspace.</span></span> <span data-ttu-id="51173-149">Megjelenik a csoporttagok listája.</span><span class="sxs-lookup"><span data-stu-id="51173-149">A list of team members is shown.</span></span> <span data-ttu-id="51173-150">A lista emellett megjeleníti minden csapattag beosztását, valamint a tag közvetlen beosztottjait, ha vannak ilyenek.</span><span class="sxs-lookup"><span data-stu-id="51173-150">The list also shows each team member's title, and any direct reports that the member has.</span></span>
1.  <span data-ttu-id="51173-151">Válassza ki a **Közvetlen beosztottak** hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="51173-151">Select the **Direct reports** link.</span></span> <span data-ttu-id="51173-152">Megjelenik a bővített csoport tagjainak listája.</span><span class="sxs-lookup"><span data-stu-id="51173-152">A list of your extended team is shown.</span></span>
1.  <span data-ttu-id="51173-153">Válasszon ki egy csapattagot.</span><span class="sxs-lookup"><span data-stu-id="51173-153">Select a team member.</span></span> <span data-ttu-id="51173-154">Megjelenik a **Csapattag összefoglalója** lap.</span><span class="sxs-lookup"><span data-stu-id="51173-154">The **Team member summary** page appears.</span></span> <span data-ttu-id="51173-155">Az ezen a lapon található információk tartalmazzák a csapattag születési dátumát, a szolgálati ideje dátuma, azt, hogy hány éve foglalkoztatott, a jelenlegi beosztásban eltöltött évek számát, valamint a kompenzációs adatokat.</span><span class="sxs-lookup"><span data-stu-id="51173-155">The information on this page includes the team member's birth date, seniority date, years of service, years in the current position, and compensation information.</span></span>

## <a name="send-praise-about-team-members-by-using-the-my-team-mobile-workspace"></a><span data-ttu-id="51173-156">Pozitív visszajelzés a csoporttagokkal kapcsolatban a Saját csapat mobil munkaterület használatával</span><span class="sxs-lookup"><span data-stu-id="51173-156">Send praise about team members by using the My team mobile workspace</span></span>
1.  <span data-ttu-id="51173-157">A mobil alkalmazásában jelölje ki a **Saját csapat** munkaterületet.</span><span class="sxs-lookup"><span data-stu-id="51173-157">In the mobile app, select the **My team** workspace.</span></span> <span data-ttu-id="51173-158">Megjelenik a csoporttagok listája.</span><span class="sxs-lookup"><span data-stu-id="51173-158">A list of team members is shown.</span></span> <span data-ttu-id="51173-159">A lista emellett megjeleníti minden csapattag beosztását, valamint a tag közvetlen beosztottjait, ha vannak ilyenek.</span><span class="sxs-lookup"><span data-stu-id="51173-159">The list also shows each team member's title, and any direct reports that the member has.</span></span>
1.  <span data-ttu-id="51173-160">Válasszon ki egy csapattagot.</span><span class="sxs-lookup"><span data-stu-id="51173-160">Select a team member.</span></span> <span data-ttu-id="51173-161">Megjelenik a **Csapattag összefoglalója** lap.</span><span class="sxs-lookup"><span data-stu-id="51173-161">The **Team member summary** page appears.</span></span>
1.  <span data-ttu-id="51173-162">Válassza ki a **Dicséret küldése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="51173-162">Select **Send praise**.</span></span> 
1. <span data-ttu-id="51173-163">Adja meg az elküldeni kívánt pozitív visszajelzés szövegét.</span><span class="sxs-lookup"><span data-stu-id="51173-163">Enter the text of the praise that you want to send.</span></span> 
1. <span data-ttu-id="51173-164">Válassza a **Kész** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="51173-164">Select **Done**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]