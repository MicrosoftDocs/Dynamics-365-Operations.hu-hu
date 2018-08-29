---
title: "Dynamics 365 for Unified Operations Mobile alkalmazás kezdőlapja"
description: "Ez a témakör bemutatja a Microsoft Dynamics 365 for Unified Operations mobilalkalmazást, és olyan forrásokra mutató linkeket tartalmaz, amelyek segíthetnek annak szervezeténél történő implementálásában."
author: sericks007
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 272853
ms.assetid: c99f818f-27b3-4e45-92b4-74272dad0e17
ms.search.region: Global
ms.author: sericks
ms.dyn365.ops.version: Platform update 4
ms.search.validFrom: 2017-02-28
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: b9cdb2b2c2b5aaf7743cd2cd0dbfee6c602a5a46
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2018

---

# <a name="dynamics-365-for-unified-operations-mobile-app-home-page"></a><span data-ttu-id="b8757-103">Dynamics 365 for Unified Operations Mobile alkalmazás kezdőlapja</span><span class="sxs-lookup"><span data-stu-id="b8757-103">Dynamics 365 for Unified Operations mobile app home page</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b8757-104">Ez a témakör bemutatja a Microsoft Dynamics 365 for Unified Operations mobilalkalmazást, és olyan forrásokra mutató linkeket tartalmaz, amelyek segíthetnek annak szervezeténél történő implementálásában.</span><span class="sxs-lookup"><span data-stu-id="b8757-104">This topic describes the Microsoft Dynamics 365 for Unified Operations mobile app and provides links to resources that can help you implement it in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="b8757-105">A mobilalkalmazás neve korábban *Microsoft Dynamics 365 for Finance and Operations* volt.</span><span class="sxs-lookup"><span data-stu-id="b8757-105">The mobile app was previously named *Microsoft Dynamics 365 for Finance and Operations*.</span></span>

<a name="overview"></a><span data-ttu-id="b8757-106">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="b8757-106">Overview</span></span>
--------

<span data-ttu-id="b8757-107">A mobilalkalmazás lehetővé teszi a szervezet számára, hogy üzleti folyamatait mobileszközökön is elérhetővé tegye.</span><span class="sxs-lookup"><span data-stu-id="b8757-107">The mobile app enables your organization to make its business processes available on mobile devices.</span></span> <span data-ttu-id="b8757-108">Miután a rendszergazda lehetővé teszi a mobil munkaterületeket a szervezetnél, a felhasználók bejelentkezhetnek az alkalmazásba, és azonnal elkezdhetik az üzleti folyamatok mobileszközökről történő futtatását.</span><span class="sxs-lookup"><span data-stu-id="b8757-108">After your IT admin enables the mobile workspaces for your organization, users can sign in to the app and immediately begin to run business processes from their mobile devices.</span></span> <span data-ttu-id="b8757-109">A mobilalkalmazás a következő olyan funkciókat tartalmazza, amelyek segíthetnek a hatékonyság növelésében:</span><span class="sxs-lookup"><span data-stu-id="b8757-109">The mobile app includes the following features that can help increase productivity:</span></span>

- <span data-ttu-id="b8757-110">A felhasználók megtekinthetik vagy szerkeszthetik az üzleti adatokat, és reagálhatnak rájuk még akkor is, ha időszakos hálózati kapcsolatuk van, vagy mobileszközeik teljesen offline állapotban vannak.</span><span class="sxs-lookup"><span data-stu-id="b8757-110">Users can view, edit, and act on business data, even if they have intermittent network connectivity or their mobile devices are completely offline.</span></span> <span data-ttu-id="b8757-111">Ha egy eszköz újra hálózati kapcsolatot létesít, az offline adatműveletek automatikusan szinkronizálódnak a Dynamics 365 for Finance and Operations programmal.</span><span class="sxs-lookup"><span data-stu-id="b8757-111">When a device reestablishes a network connection, offline data operations are automatically synchronized with Dynamics 365 for Finance and Operations.</span></span>
- <span data-ttu-id="b8757-112">A rendszergazdák vagy fejlesztők képesek olyan mobil munkaterületek létrehozására és közzétételére, amelyeket testre szabtak a szervezetük igényeinek megfelelően.</span><span class="sxs-lookup"><span data-stu-id="b8757-112">IT admins or developers can build and publish mobile workspaces that have been tailored to their organization.</span></span> <span data-ttu-id="b8757-113">Az alkalmazás a meglévő kódolási lehetőségeket használja.</span><span class="sxs-lookup"><span data-stu-id="b8757-113">The app uses your existing code assets.</span></span> <span data-ttu-id="b8757-114">Ezért nem kell ismét implementálnia a validálási eljárásokat, az üzleti logikát vagy a biztonsági konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="b8757-114">Therefore, you don't have to re-implement your validation procedures, business logic, or security configuration.</span></span>
- <span data-ttu-id="b8757-115">A rendszergazdák vagy fejlesztők könnyen megtervezhetik a mobil munkaterületeket a webes klienshez mellékelt „point-and-click” típusú munkaterület-tervező segítségével.</span><span class="sxs-lookup"><span data-stu-id="b8757-115">IT admins or developers can easily design mobile workspaces by using the point-and-click workspace designer that is included with the web client.</span></span>
- <span data-ttu-id="b8757-116">A rendszergazdák vagy fejlesztők opcionálisan optimalizálhatják a munkaterületek offline funkcióit is az Üzleti logika bővítési keretrendszer használatával.</span><span class="sxs-lookup"><span data-stu-id="b8757-116">IT admins or developers can optionally optimize the offline capabilities of workspaces by using the Business logic extensibility framework.</span></span> <span data-ttu-id="b8757-117">Mivel az adatok feldolgozása az eszköz offline állapotában is folytatódik, mobilos forgatókönyvei továbbra is gazdagok és naprakészek maradnak még akkor is, ha az eszközök nem rendelkeznek állandó hálózati kapcsolattal.</span><span class="sxs-lookup"><span data-stu-id="b8757-117">Because data continues to be processed while a device is offline, your mobile scenarios remain rich and fluid, even if devices don't have constant network connectivity.</span></span>

## <a name="elements-of-the-mobile-app"></a><span data-ttu-id="b8757-118">A mobilalkalmazás elemei</span><span class="sxs-lookup"><span data-stu-id="b8757-118">Elements of the mobile app</span></span>
<span data-ttu-id="b8757-119">A mobilalkalmazásban történő navigáció négy egyszerű részből áll: ezek az irányítópult, a munkaterület, az oldalak és a műveletek.</span><span class="sxs-lookup"><span data-stu-id="b8757-119">Navigation in the mobile app consists of four basic concepts: the dashboard, workspaces, pages, and actions.</span></span> 

<span data-ttu-id="b8757-120">[![A mobilalkalmazás navigációs fogalmai](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)</span><span class="sxs-lookup"><span data-stu-id="b8757-120">[![Navigation concepts in the mobile app](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)</span></span>

1. <span data-ttu-id="b8757-121">Az alkalmazás indításakor az **irányítópultra** kerül.</span><span class="sxs-lookup"><span data-stu-id="b8757-121">When you start the app, you go to the **dashboard**.</span></span>
2. <span data-ttu-id="b8757-122">Az irányítópulton látható a közzétett **Munkaterületek** listája.</span><span class="sxs-lookup"><span data-stu-id="b8757-122">On the dashboard, you can see a list of **workspaces** that have been published.</span></span>
3. <span data-ttu-id="b8757-123">Minden munkaterületnél látható az adott munkaterület rendelkezésre álló **lapjainak** listája.</span><span class="sxs-lookup"><span data-stu-id="b8757-123">In each workspace, you can see a list of **pages** that are available for that workspace.</span></span>
4. <span data-ttu-id="b8757-124">Az oldalakra lépve több művelet végezhető el.</span><span class="sxs-lookup"><span data-stu-id="b8757-124">After you're on a page, you can perform several actions.</span></span> <span data-ttu-id="b8757-125">Íme néhány példa:</span><span class="sxs-lookup"><span data-stu-id="b8757-125">Here are some examples:</span></span>

    - <span data-ttu-id="b8757-126">Részletes adatok megtekintése.</span><span class="sxs-lookup"><span data-stu-id="b8757-126">View detailed data.</span></span>
    - <span data-ttu-id="b8757-127">Navigálás a kapcsolódó adatokat, például az entitások részleteit vagy a sorokat tartalmazó lapokra.</span><span class="sxs-lookup"><span data-stu-id="b8757-127">Navigate to other pages for related data, such as entity details or lines.</span></span>
    - <span data-ttu-id="b8757-128">Lásd az adott oldalon rendelkezésre álló **műveletek** listáját.</span><span class="sxs-lookup"><span data-stu-id="b8757-128">See a list of **actions** that are available for that page.</span></span> <span data-ttu-id="b8757-129">A műveletek segítségével adatokat hozhat létre, vagy módosíthatja a meglévő adatokat.</span><span class="sxs-lookup"><span data-stu-id="b8757-129">Actions let you create or edit existing data.</span></span>

## <a name="implementation-process"></a><span data-ttu-id="b8757-130">Megvalósítási folyamat</span><span class="sxs-lookup"><span data-stu-id="b8757-130">Implementation process</span></span>
<span data-ttu-id="b8757-131">A következő ábra a Microsoft által biztosított, valamint az egyéni mobil munkaterületek implementálásának folyamatát mutatja.</span><span class="sxs-lookup"><span data-stu-id="b8757-131">The following illustration shows the process for implementing both mobile workspaces that are provided by Microsoft and custom mobile workspaces.</span></span> 

![Mobilalkalmazások megvalósítási folyamata](./media/Mobile-implementation-process-5.png)

<span data-ttu-id="b8757-133">Az alábbi táblázat azokra az erőforrásokra mutató hivatkozásokat tartalmaz, amelyek segítenek a Microsoft által biztosított, valamint az egyéni mobil munkaterületek implementálásában.</span><span class="sxs-lookup"><span data-stu-id="b8757-133">The following table includes links to resources that can help you implement both mobile workspaces that are provided by Microsoft and custom mobile workspaces.</span></span> <span data-ttu-id="b8757-134">Az első oszlopban szereplő számok az előzőekben bemutatott számozott lépéseknek felelnek meg.</span><span class="sxs-lookup"><span data-stu-id="b8757-134">The numbers in the first column correspond to the numbered steps in the previous illustration.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b8757-135">Lépés</span><span class="sxs-lookup"><span data-stu-id="b8757-135">Step</span></span></th>
<th><span data-ttu-id="b8757-136">Szerep</span><span class="sxs-lookup"><span data-stu-id="b8757-136">Role</span></span></th>
<th><span data-ttu-id="b8757-137">Művelet</span><span class="sxs-lookup"><span data-stu-id="b8757-137">Action</span></span></th>
<th><span data-ttu-id="b8757-138">Források, melyek segítenek a művelet végrehajtásában</span><span class="sxs-lookup"><span data-stu-id="b8757-138">Resources to help you complete the action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="b8757-139">1</span><span class="sxs-lookup"><span data-stu-id="b8757-139">1</span></span></td>
<td><span data-ttu-id="b8757-140">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="b8757-140">System administrator</span></span></td>
<td><span data-ttu-id="b8757-141">Finance and Operations alkalmazása a szervezeten belüli.</span><span class="sxs-lookup"><span data-stu-id="b8757-141">Implement Finance and Operations in your organization.</span></span></td>
<td><ul><li><span data-ttu-id="b8757-142">Ha még nem telepítette a Microsoft Dynamics 365 valamely verzióját, lásd: <a href="../deployment/deploy-demo-environment.md">Bemutatókörnyezet telepítése</a>.</span><span class="sxs-lookup"><span data-stu-id="b8757-142">If you haven&#39;t yet deployed a version of Microsoft Dynamics 365, see <a href="../deployment/deploy-demo-environment.md">Deploy a demo environment</a>.</span></span></li><li><span data-ttu-id="b8757-143">A használható mobil munkaterületek listájának megtekintéséhez lásd <a href="mobile-workspaces-released.md">Nemrég kiadott mobil munkaterületek</a>.</span><span class="sxs-lookup"><span data-stu-id="b8757-143">To see a list of mobile workspaces that can be used, see <a href="mobile-workspaces-released.md">Mobile workspaces recently released</a>.</span></span></li></ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b8757-144">2</span><span class="sxs-lookup"><span data-stu-id="b8757-144">2</span></span></td>
<td><span data-ttu-id="b8757-145">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="b8757-145">System administrator</span></span></td>
<td><span data-ttu-id="b8757-146"><strong>A Microsoft Dynamics 365 for Operations 1611-es verziójának használatakor:</strong> Töltse le és telepítse azokat a tudásbáziscikkeket, amelyek lehetővé teszik a Microsoft által biztosított mobil munkaterületek használatát.</span><span class="sxs-lookup"><span data-stu-id="b8757-146"><strong>If you&#39;re using Microsoft Dynamics 365 for Operations version 1611:</strong> Download and install KBs that enable the mobile workspaces that are provided by Microsoft.</span></span></td>
<td><span data-ttu-id="b8757-147">További információ a következő témakörökben olvasható:</span><span class="sxs-lookup"><span data-stu-id="b8757-147">See the following topics for more information:</span></span>
<ul>

<li><span data-ttu-id="b8757-148"><a href="../../financials/cost-accounting/cost-controlling-mobile-workspace.md">Költségkontroll mobil munkaterületek</a></span><span class="sxs-lookup"><span data-stu-id="b8757-148"><a href="../../financials/cost-accounting/cost-controlling-mobile-workspace.md">Cost controlling mobile workspaces</a></span></span></li>
<li><span data-ttu-id="b8757-149"><a href="../../supply-chain/inventory/inventory-on-hand-mobile-workspace.md">Aktuális készlet mobil munkaterület</a></span><span class="sxs-lookup"><span data-stu-id="b8757-149"><a href="../../supply-chain/inventory/inventory-on-hand-mobile-workspace.md">Inventory on-hand mobile workspace</a></span></span></li>
<li><span data-ttu-id="b8757-150"><a href="../../supply-chain/sales-marketing/sales-orders-mobile-workspace.md">Értékesítési rendelések mobil munkaterületek</a></span><span class="sxs-lookup"><span data-stu-id="b8757-150"><a href="../../supply-chain/sales-marketing/sales-orders-mobile-workspace.md">Sales orders mobile workspaces</a></span></span></li>
<li><span data-ttu-id="b8757-151"><a href="../../supply-chain/procurement/vendor-collaboration-mobile-workspace.md">Szállítói együttműködési mobil munkaterület</a></span><span class="sxs-lookup"><span data-stu-id="b8757-151"><a href="../../supply-chain/procurement/vendor-collaboration-mobile-workspace.md">Vendor collaboration mobile workspace</a></span></span></li>
<li><span data-ttu-id="b8757-152"><a href="../../financials/project-management/project-time-entry-mobile-workspace.md">Projektidő megadása mobil munkaterület</a></span><span class="sxs-lookup"><span data-stu-id="b8757-152"><a href="../../financials/project-management/project-time-entry-mobile-workspace.md">Project time entry mobile workspace</a></span></span></li>
<li><span data-ttu-id="b8757-153"><a href="../../financials/expense-management/expense-management-mobile-workspace.md">Költségkezelési mobil munkaterület</a></span><span class="sxs-lookup"><span data-stu-id="b8757-153"><a href="../../financials/expense-management/expense-management-mobile-workspace.md">Expense management mobile workspace</a></span></span></li>

</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b8757-154">3</span><span class="sxs-lookup"><span data-stu-id="b8757-154">3</span></span></td>
<td><span data-ttu-id="b8757-155">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="b8757-155">System administrator</span></span></td>
<td><span data-ttu-id="b8757-156">Tegye közzé a Microsoft által biztosított egyéni mobil munkaterületeket.</span><span class="sxs-lookup"><span data-stu-id="b8757-156">Publish the mobile workspaces that are provided by Microsoft.</span></span></td>
<td><span data-ttu-id="b8757-157"><a href="publish-mobile-workspace.md">Mobil munkaterület közzététele</a>
</span><span class="sxs-lookup"><span data-stu-id="b8757-157"><a href="publish-mobile-workspace.md">Publish a mobile workspace</a>
</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b8757-158">4</span><span class="sxs-lookup"><span data-stu-id="b8757-158">4</span></span></td>
<td><span data-ttu-id="b8757-159">Fejlesztő vagy független szoftverszállító (ISV)</span><span class="sxs-lookup"><span data-stu-id="b8757-159">Developer or independent software vendor (ISV)</span></span></td>
<td><span data-ttu-id="b8757-160">Használja a mobilplatformot egyéni mobil munkaterületek létrehozására.</span><span class="sxs-lookup"><span data-stu-id="b8757-160">Use the mobile platform to create custom mobile workspaces.</span></span></td>
<td><span data-ttu-id="b8757-161"><a href="platform/mobile-platform-home-page.md">Mobil platform</a></span><span class="sxs-lookup"><span data-stu-id="b8757-161"><a href="platform/mobile-platform-home-page.md">Mobile platform</a></span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b8757-162">5</span><span class="sxs-lookup"><span data-stu-id="b8757-162">5</span></span></td>
<td><span data-ttu-id="b8757-163">ISV</span><span class="sxs-lookup"><span data-stu-id="b8757-163">ISV</span></span></td>
<td><span data-ttu-id="b8757-164">Hozzon létre egy telepíthető csomagot, amely egyéni mobil munkaterületeket tartalmaz, és töltse fel a csomagot a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásra.</span><span class="sxs-lookup"><span data-stu-id="b8757-164">Create a deployable package that contains custom mobile workspaces, and upload the package to Microsoft Dynamics Lifecycle Services (LCS).</span></span></td>
<td><span data-ttu-id="b8757-165"><a href="../deployment/create-apply-deployable-package.md">Telepíthető csomag létrehozása</a></span><span class="sxs-lookup"><span data-stu-id="b8757-165"><a href="../deployment/create-apply-deployable-package.md">Create a deployable package</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b8757-166">6</span><span class="sxs-lookup"><span data-stu-id="b8757-166">6</span></span></td>
<td><span data-ttu-id="b8757-167">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="b8757-167">System administrator</span></span></td>
<td><span data-ttu-id="b8757-168">Alkalmazza a telepíthető csomagot, amely tartalmazza a független szoftverszállító (ISV) által biztosított egyéni munkaterületeket.</span><span class="sxs-lookup"><span data-stu-id="b8757-168">Apply the deployable package that contains the custom workspaces that are provided by the independent software vendor (ISV).</span></span></td>
<td><span data-ttu-id="b8757-169"><a href="../deployment/apply-deployable-package-system.md">Telepíthető csomag alkalmazása</a></span><span class="sxs-lookup"><span data-stu-id="b8757-169"><a href="../deployment/apply-deployable-package-system.md">Apply a deployable package</a></span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b8757-170">7</span><span class="sxs-lookup"><span data-stu-id="b8757-170">7</span></span></td>
<td><span data-ttu-id="b8757-171">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="b8757-171">System administrator</span></span></td>
<td><span data-ttu-id="b8757-172">Tegye közzé az ISV által biztosított egyéni mobil munkaterületeket.</span><span class="sxs-lookup"><span data-stu-id="b8757-172">Publish the custom mobile workspaces that are provided by the ISV.</span></span></td>
<td><span data-ttu-id="b8757-173"><a href="publish-mobile-workspace.md">Mobil munkaterület közzététele</a></span><span class="sxs-lookup"><span data-stu-id="b8757-173"><a href="publish-mobile-workspace.md">Publish a mobile workspace</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b8757-174">8</span><span class="sxs-lookup"><span data-stu-id="b8757-174">8</span></span></td>
<td><span data-ttu-id="b8757-175">Felhasználó</span><span class="sxs-lookup"><span data-stu-id="b8757-175">User</span></span></td>
<td><span data-ttu-id="b8757-176">Töltse le és telepítse a mobilalkalmazást.</span><span class="sxs-lookup"><span data-stu-id="b8757-176">Download and install the mobile app.</span></span></td>
<td><ul>
<li><span data-ttu-id="b8757-177"><a href="https://go.microsoft.com/fwlink/?linkid=850662">Android-telefonok esetében:</a></span><span class="sxs-lookup"><span data-stu-id="b8757-177"><a href="https://go.microsoft.com/fwlink/?linkid=850662">For Android phones</a></span></span></li>
<li><span data-ttu-id="b8757-178"><a href="https://go.microsoft.com/fwlink/?linkid=850663">iPhone esetében:</a></span><span class="sxs-lookup"><span data-stu-id="b8757-178"><a href="https://go.microsoft.com/fwlink/?linkid=850663">For iPhones</a></span></span></li></ul>
</td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b8757-179">9</span><span class="sxs-lookup"><span data-stu-id="b8757-179">9</span></span></td>
<td><span data-ttu-id="b8757-180">Felhasználó</span><span class="sxs-lookup"><span data-stu-id="b8757-180">User</span></span></td>
<td><span data-ttu-id="b8757-181">Jelentkezzen be, és használja a mobilalkalmazást.</span><span class="sxs-lookup"><span data-stu-id="b8757-181">Sign in, and use the mobile app.</span></span> <span data-ttu-id="b8757-182">Az alkalmazás tartalmazza a rendszergazda által közzétett mobil munkaterületeket.</span><span class="sxs-lookup"><span data-stu-id="b8757-182">The app includes the mobile workspaces that have been published by the system administrator.</span></span></td>
<td><span data-ttu-id="b8757-183">A Microsoft által biztosított mobil munkaterületek listájának megtekintéséhez lásd <a href="mobile-workspaces-released.md">Nemrég kiadott mobil munkaterületek</a>.</span><span class="sxs-lookup"><span data-stu-id="b8757-183">To see a list of mobile workspaces that are provided by Microsoft, see <a href="mobile-workspaces-released.md">Mobile workspaces recently released</a>.</span></span>
</td>
</tr>
</tbody>
</table>

