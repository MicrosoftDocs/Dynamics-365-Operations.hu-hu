---
title: Eszközkezelés mobil munkaterület beállítása
description: Ez a témakör azt mutatja be, hogyan lehet beállítani a Microsoft Dynamics 365 Supply Chain Management és a Finance and Operations (Dynamics 365) mobilalkalmazást egy eszközkezelési mobil munkaterület futtatására, amely a dolgozók számára az eszközkezelési feladatok elvégzésére használható.
author: johanhoffmann
manager: tfehr
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-22
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 9c2410c50b5d289792e2cc364674e1e093653590
ms.sourcegitcommit: 995c678b4715be267f1f97148902a6b3dde3bcab
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/20/2021
ms.locfileid: "5033211"
---
# <a name="set-up-the-asset-management-mobile-workspace"></a><span data-ttu-id="b40bd-103">Eszközkezelés mobil munkaterület beállítása</span><span class="sxs-lookup"><span data-stu-id="b40bd-103">Set up the Asset management mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b40bd-104">Ez a témakör azt mutatja be, hogyan lehet beállítani a Microsoft Dynamics 365 Supply Chain Management és a Finance and Operations (Dynamics 365) mobilalkalmazást egy **Eszközkezelési** mobil munkaterület futtatására, amely a dolgozók számára az eszközkezelési feladatok elvégzésére használható.</span><span class="sxs-lookup"><span data-stu-id="b40bd-104">This topic describes how to set up Microsoft Dynamics 365 Supply Chain Management and the Finance and Operations (Dynamics 365) mobile app to run an **Asset management** mobile workspace that workers can use to perform asset management tasks.</span></span>

## <a name="set-up-maintenance-worker-users-in-supply-chain-management"></a><span data-ttu-id="b40bd-105">Karbantartási dolgozói felhasználók beállítása a Supply Chain Management szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="b40bd-105">Set up maintenance worker users in Supply Chain Management</span></span>

<span data-ttu-id="b40bd-106">Az alábbi lépéseket kell követni minden olyan felhasználó számára, akinek hozzá kell férni az **Eszközkezelés** mobil munkaterülethez.</span><span class="sxs-lookup"><span data-stu-id="b40bd-106">For each user that requires access to the **Asset management** mobile workspace, follow these steps.</span></span>

1. <span data-ttu-id="b40bd-107">A Supply Chain Management szolgáltatásban ugorjon az **Emberi erőforrások \> Dolgozók** elemre, és győződjön meg róla, hogy létezik dolgozórekord a beállítani kívánt felhasználóhoz.</span><span class="sxs-lookup"><span data-stu-id="b40bd-107">In Supply Chain Management, go to **Human resources \> Workers**, and make sure that a worker record exists for the user that you want to set up.</span></span> <span data-ttu-id="b40bd-108">Hozzon létre igény szerint egy új dolgozói rekordot.</span><span class="sxs-lookup"><span data-stu-id="b40bd-108">Create a new worker record as required.</span></span>
1. <span data-ttu-id="b40bd-109">Ugorjon az **Eszközkezelés \> Beállítás \> Dolgozók \> Dolgozók** elemre, és győződjön meg róla, hogy az előző lépésben azonosított (vagy létrehozott) dolgozórekord egy karbantartási dolgozói rekordhoz van leképezve.</span><span class="sxs-lookup"><span data-stu-id="b40bd-109">Go to **Asset management \> Setup \> Workers \> Workers**, and make sure that the worker record that you identified (or created) in the previous step is mapped to a maintenance worker record.</span></span> <span data-ttu-id="b40bd-110">Szükség szerint hozzon létre egy új karbantartási dolgozói rekordot, és állítsa a **Dolgozó** mezőt az előző lépésből származó dolgozórekordra.</span><span class="sxs-lookup"><span data-stu-id="b40bd-110">Create a new maintenance worker record as required, and set the **Worker** field to the worker record from the previous step.</span></span>
1. <span data-ttu-id="b40bd-111">Ugorjon az **Eszközkezelés \> Beállítás \> Dolgozók \> Karbantartási dolgozói csoportok** elemre, és győződjön meg róla, hogy az előző lépésben azonosított (vagy létrehozott) karbantartási dolgozói rekord egy karbantartási dolgozói csoporthoz van leképezve.</span><span class="sxs-lookup"><span data-stu-id="b40bd-111">Go to **Asset management \> Setup \> Workers \> Maintenance worker groups**, and make sure that the maintenance worker record that you identified (or created) in the previous step belongs to a maintenance worker group.</span></span>
1. <span data-ttu-id="b40bd-112">Ugorjon a **Rendszerfelügyelet \> Felhasználók** elemre.</span><span class="sxs-lookup"><span data-stu-id="b40bd-112">Go to **System administration \> Users**.</span></span>
1. <span data-ttu-id="b40bd-113">Válassza ki a releváns felhasználót a rácsban.</span><span class="sxs-lookup"><span data-stu-id="b40bd-113">Select the relevant user in the grid.</span></span>
1. <span data-ttu-id="b40bd-114">A **Felhasználói adatok** gyorslapon állítsa a **Személy** mezőt arra a dolgozói fiókra, amelyet szeretne hozzárendelni az aktuális felhasználói fiókhoz.</span><span class="sxs-lookup"><span data-stu-id="b40bd-114">On the **User Details** FastTab, set the **Person** field to the worker account that you want to associate with the current user account.</span></span> <span data-ttu-id="b40bd-115">Ennek a dolgozói fióknak az 1. lépésben azonosított (vagy létrehozott) dolgozói rekordnak kell lennie, amely a 2. lépésben egy karbantartási dolgozói rekordhoz van leképezve.</span><span class="sxs-lookup"><span data-stu-id="b40bd-115">This worker account should be the worker record that you identified (or created) in step 1 and mapped to a maintenance worker record in step 2.</span></span>

> [!NOTE]
> <span data-ttu-id="b40bd-116">A felhasználói engedélyek és a biztonsági szerepkörök úgy alkalmazandók az **Eszközkezelés** mobil munkaterület funkcióira, ahogyan a Supply Chain Management felhasználói felületének funkcióira.</span><span class="sxs-lookup"><span data-stu-id="b40bd-116">User permissions and security roles apply to the features of the **Asset management** mobile workspace just as they apply to the features of the Supply Chain Management user interface.</span></span> <span data-ttu-id="b40bd-117">Emiatt minden felhasználónak, aki úgy van beállítva, hogy hozzáférjen az **Eszközkezelés** mobil munkaterülethez, olyan biztonsági szerepkörökkel kell rendelkeznie, amelyek a hasonló műveleteknek közvetlenül a Supply Chain Managementben való közvetlen végrehajtásához szükségesek.</span><span class="sxs-lookup"><span data-stu-id="b40bd-117">Therefore, every user that you set up to access the **Asset management** mobile workspace must have the security roles that are required to perform similar operations directly in Supply Chain Management.</span></span>

## <a name="publish-the-asset-management-mobile-workspace"></a><span data-ttu-id="b40bd-118">Eszközkezelés mobil munkaterület közzététele</span><span class="sxs-lookup"><span data-stu-id="b40bd-118">Publish the Asset management mobile workspace</span></span>

<span data-ttu-id="b40bd-119">Ahhoz, hogy elérhetővé tegye az eszközkezelési funkciókat a Finance and Operations (Dynamics 365) mobilalkalmazásban, közzé kell tennie az **Eszközkezelés** mobil munkaterületet.</span><span class="sxs-lookup"><span data-stu-id="b40bd-119">To make asset management features available in the Finance and Operations (Dynamics 365) mobile app, you must publish the **Asset management** mobile workspace.</span></span>

1. <span data-ttu-id="b40bd-120">A Supply Chain Management szolgáltatásban válassza a **Beállítások** gombot (a jobb felső sarkában látható fogaskerekek szimbólumát), majd válassza a menüben a **Mobilalkalmazás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b40bd-120">In Supply Chain Management, select the **Settings** button (the gear symbol in upper-right corner), and then select **Mobile app** on the menu.</span></span>
1. <span data-ttu-id="b40bd-121">A **Mobilalkalmazás-kezelés** párbeszédpanelen keresse meg az **Eszközkezelés** csempét.</span><span class="sxs-lookup"><span data-stu-id="b40bd-121">In the **Manage mobile app** dialog box, find the **Asset Management** tile.</span></span> <span data-ttu-id="b40bd-122">Ha azt a szöveget tartalmazza, hogy "Metaadatok között - nincs közzétéve", akkor a munkaterület még nincs közzétéve.</span><span class="sxs-lookup"><span data-stu-id="b40bd-122">If it contains the text "In metadata - not published," the workspace hasn't yet been published.</span></span> <span data-ttu-id="b40bd-123">Ha a "Metaadatok között - közzétett" szöveget tartalmazza, a munkaterület már közzé van téve, és a művelet hátralévő részét kihagyhatja.</span><span class="sxs-lookup"><span data-stu-id="b40bd-123">If it contains the text "In metadata - published," the workspace has already been published, and you can skip the rest of this procedure.</span></span>

    <span data-ttu-id="b40bd-124">![Mobilalkalmazás párbeszédpanel kezelése](media/mobile-workspaces.png "Mobilalkalmazás párbeszédpanel kezelése")</span><span class="sxs-lookup"><span data-stu-id="b40bd-124">![Manage mobile app dialog box](media/mobile-workspaces.png "Manage mobile app dialog box")</span></span>

1. <span data-ttu-id="b40bd-125">Válassza az **Eszközkezelés** csempét, majd az eszköztár **Közzététel** gombját.</span><span class="sxs-lookup"><span data-stu-id="b40bd-125">Select the **Asset Management** tile, and then select **Publish** on the toolbar.</span></span> <span data-ttu-id="b40bd-126">Néhány másodperc múlva értesítést kell kapnia arról, hogy sikeresen megtörtént a munkaterület közzététele.</span><span class="sxs-lookup"><span data-stu-id="b40bd-126">After a few seconds, you should receive a notification that states that the workspace has been successfully published.</span></span> <span data-ttu-id="b40bd-127">Ezenkívül a csempe szövegének a "Metaadatok között – közzétéve" szövegre kell váltania.</span><span class="sxs-lookup"><span data-stu-id="b40bd-127">Additionally, the text on the tile should change to "In metadata - published."</span></span>

## <a name="install-and-set-up-the-finance-and-operations-dynamics-365-mobile-app"></a><span data-ttu-id="b40bd-128">A Finance and Operations (Dynamics 365) mobilalkalmazás telepítése és beállítása</span><span class="sxs-lookup"><span data-stu-id="b40bd-128">Install and set up the Finance and Operations (Dynamics 365) mobile app</span></span>

1. <span data-ttu-id="b40bd-129">Ha mobileszközére telepítenie kell a **Microsoft Finance and Operations (Dynamics 365)** alkalmazást, ugorjon a következő alkalmazásáruházak egyikére:</span><span class="sxs-lookup"><span data-stu-id="b40bd-129">Go to one of the following app stores to install the **Microsoft Finance and Operations (Dynamics 365)** app on your mobile device:</span></span>

    - [<span data-ttu-id="b40bd-130">Google Android eszközök esetében</span><span class="sxs-lookup"><span data-stu-id="b40bd-130">For Google Android devices</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
    - [<span data-ttu-id="b40bd-131">Apple IOS eszközök esetében</span><span class="sxs-lookup"><span data-stu-id="b40bd-131">For Apple iOS devices</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

1. <span data-ttu-id="b40bd-132">Nyissa meg Finance and Operations (Dynamics 365) alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="b40bd-132">Open the Finance and Operations (Dynamics 365) app.</span></span> <span data-ttu-id="b40bd-133">A bejelentkezési oldalnak meg kell jelenni.</span><span class="sxs-lookup"><span data-stu-id="b40bd-133">The sign-in page should appear.</span></span> <span data-ttu-id="b40bd-134">A **Bejelentkezés** mezőben adja meg a saját Supply Chain Management URL-címét, vagy válassza ki a közelmúltbeli URL-címet a **Közelmúltbeli környezetek** listában, majd koppintson a **Csatlakozás** gombra.</span><span class="sxs-lookup"><span data-stu-id="b40bd-134">In the **Sign in** field, enter your Supply Chain Management URL, or select a recent URL in the **Recent environments** list, and then tap **Connect**.</span></span>

    <span data-ttu-id="b40bd-135">![Bejelentkezési oldal](media/mobile-app-sign-in.png "Bejelentkezési oldal")</span><span class="sxs-lookup"><span data-stu-id="b40bd-135">![Sign-in page](media/mobile-app-sign-in.png "Sign-in page")</span></span>

1. <span data-ttu-id="b40bd-136">Ha a program kéri a kapcsolat megerősítését, jelölje be a **Megértettem** jelölőnégyzetet, majd koppintson a **Csatlakozás** gombra.</span><span class="sxs-lookup"><span data-stu-id="b40bd-136">If you're prompted to confirm the connection, select the **I understand** check box, and then tap **Connect**.</span></span>
1. <span data-ttu-id="b40bd-137">A **Fiókválasztó** oldalon Microsoft-fiókjával jelentkezhet be a mobilalkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="b40bd-137">On the **Pick an account** page, use your Microsoft account to sign in to the mobile application.</span></span>

    <span data-ttu-id="b40bd-138">Megjelenik a **Munkaterületek** oldal.</span><span class="sxs-lookup"><span data-stu-id="b40bd-138">The **Workspaces** page appears.</span></span> <span data-ttu-id="b40bd-139">Felsorolja a saját Supply Chain Management példánya által közzétett összes mobil munkaterületet.</span><span class="sxs-lookup"><span data-stu-id="b40bd-139">It lists every mobile workspace that has been published by your Supply Chain Management instance.</span></span>

    <span data-ttu-id="b40bd-140">![Munkaterületek listája](media/mobile-app-workspaces.png "Munkaterületek listája")</span><span class="sxs-lookup"><span data-stu-id="b40bd-140">![List of workspaces](media/mobile-app-workspaces.png "List of workspaces")</span></span>

1. <span data-ttu-id="b40bd-141">Ha módosítania kell a jogi személyt (vállalatot), kattintson a bal felső sarkában látható Menü gombra (néha hamburgernek vagy a hamburgergombnak is nevezik), majd válassza a **Vállalat módosítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b40bd-141">If you must change the legal entity (company), tap the Menu button (sometimes referred to as the hamburger or the hamburger button) in the upper-left corner, and then tap **Change company**.</span></span>

    <span data-ttu-id="b40bd-142">![A jogi személy módosítása](media/mobile-app-change-comp.png "A jogi személy módosítása")</span><span class="sxs-lookup"><span data-stu-id="b40bd-142">![Changing the legal entity](media/mobile-app-change-comp.png "Changing the legal entity")</span></span>

1. <span data-ttu-id="b40bd-143">Válassza ki a **Munkaterületek** lapon azt a munkaterületet, amelyet használni szeretne a megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="b40bd-143">On the **Workspaces** page, select the workspace that you want to work with to open it.</span></span>

    <span data-ttu-id="b40bd-144">![Eszközkezelési mobil munkaterület](media/mobile-app-asset-workspace.png "Eszközkezelési mobil munkaterület")</span><span class="sxs-lookup"><span data-stu-id="b40bd-144">![Asset management mobile workspace](media/mobile-app-asset-workspace.png "Asset management mobile workspace")</span></span>

## <a name="work-with-the-asset-management-mobile-workspace"></a><span data-ttu-id="b40bd-145">Eszközkezelés mobil munkaterület használata</span><span class="sxs-lookup"><span data-stu-id="b40bd-145">Work with the Asset management mobile workspace</span></span>

<span data-ttu-id="b40bd-146">Az **Eszközkezelés** mobil munkaterület használatával kapcsolatos további tudnivalókat lásd az [Eszközkezelés mobil munkaterület használata](asset-management-mobile-workspace.md) oldalt.</span><span class="sxs-lookup"><span data-stu-id="b40bd-146">For more information about how to work with the **Asset management** mobile workspace, see [Use the Asset management mobile workspace](asset-management-mobile-workspace.md).</span></span>

<span data-ttu-id="b40bd-147">A Finance and Operations (Dynamics 365) mobilalkalmazással kapcsolatos további tudnivalókat lásd: [Mobilalkalmazás kezdőlapja](../../fin-ops-core/dev-itpro/mobile-apps/Mobile-app-home-page.md).</span><span class="sxs-lookup"><span data-stu-id="b40bd-147">For more information about the Finance and Operations (Dynamics 365) mobile app, see the [Mobile app home page](../../fin-ops-core/dev-itpro/mobile-apps/Mobile-app-home-page.md).</span></span>
