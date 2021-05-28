---
title: Feladatkezelés szinkronizálása a Microsoft Teams és a Dynamics 365 Commerce-pénztár között
description: Ez a témakör azt ismerteti, hogyan kell szinkronizálni a feladatkezelést a Microsoft Teams és a Dynamics 365 Commerce pénztár (POS) között.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 74d53a850113c83979fba6baa4ff3c3e5d9ca02d
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020627"
---
# <a name="synchronize-task-management-between-microsoft-teams-and-dynamics-365-commerce-pos"></a><span data-ttu-id="70372-103">Feladatkezelés szinkronizálása a Microsoft Teams és a Dynamics 365 Commerce-pénztár között</span><span class="sxs-lookup"><span data-stu-id="70372-103">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="70372-104">Ez a témakör azt ismerteti, hogyan kell szinkronizálni a feladatkezelést a Microsoft Teams és a Dynamics 365 Commerce pénztár (POS) között.</span><span class="sxs-lookup"><span data-stu-id="70372-104">This topic describes how to synchronize task management between Microsoft Teams and Dynamics 365 Commerce point of sale (POS).</span></span>

<span data-ttu-id="70372-105">A Teams integráció egyik fő célja a feladatkezelés szinkronizálása a pénztáralkalmazás és a Teams között.</span><span class="sxs-lookup"><span data-stu-id="70372-105">One of the main purposes of Teams integration is to enable the synchronization of task management between the POS application and Teams.</span></span> <span data-ttu-id="70372-106">Ily módon az üzlet alkalmazottai a pénztáralkalmazást vagy a Teams alkalmazást használhatja feladatok kezelésére, és nem kell másik alkalmazásra váltani.</span><span class="sxs-lookup"><span data-stu-id="70372-106">In this way, store employees can use either the POS application or Teams to manage tasks, and don't have to switch applications.</span></span>

<span data-ttu-id="70372-107">Mivel a Tervező a Teamsben található feladatok adattára, kapcsolatnak kell lennie a Teams és a Dynamics 365 Commerce között.</span><span class="sxs-lookup"><span data-stu-id="70372-107">Because Planner is used as a repository for tasks in Teams, there must be a link between Teams and Dynamics 365 Commerce.</span></span> <span data-ttu-id="70372-108">Ez a hivatkozás egy adott üzletcsoporthoz megadott tervazonosító alapján jött létre.</span><span class="sxs-lookup"><span data-stu-id="70372-108">This link is established by using a specific plan ID for a given store team.</span></span>

<span data-ttu-id="70372-109">A következő eljárások be mutatják, hogyan lehet beállítani a feladatkezelés szinkronizálását a pénztár- és a Teams-alkalmazások között.</span><span class="sxs-lookup"><span data-stu-id="70372-109">The following procedures show how to set up task management synchronization between the POS and Teams applications.</span></span>

## <a name="publish-a-test-task-list-in-teams"></a><span data-ttu-id="70372-110">Tesztfeladatlista közzététele a Teamsben</span><span class="sxs-lookup"><span data-stu-id="70372-110">Publish a test task list in Teams</span></span>

<span data-ttu-id="70372-111">A következő eljárás feltételezi, hogy az üzletcsapatok első alkalommal használják a Microsoft Teams feladatkezelés integrációját a Commerce alkalmazással.</span><span class="sxs-lookup"><span data-stu-id="70372-111">The following procedure assumes that your store teams are using Microsoft Teams task management integration with Commerce for the first time.</span></span>

<span data-ttu-id="70372-112">A tesztfeladatok listájának a Teamsben való közzétételéhez hajtsa végre ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="70372-112">To publish a test task list in Teams, follow these steps.</span></span>

1. <span data-ttu-id="70372-113">Jelentkezzen be a Teamsbe kommunikációs vezetőként.</span><span class="sxs-lookup"><span data-stu-id="70372-113">Sign in to Teams as a communications manager.</span></span> <span data-ttu-id="70372-114">A kommunikációs vezetők általában olyan felhasználók, akiknek a Commerce-ben **Területi vezetői** szerepkörük van.</span><span class="sxs-lookup"><span data-stu-id="70372-114">Typically, communications managers are users who have the **Regional manager** role in Commerce.</span></span>
1. <span data-ttu-id="70372-115">A bal oldali navigációs ablakban válassza a **Feladatok tervező szerint** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="70372-115">In the left navigation pane, select **Tasks by Planner**.</span></span>
1. <span data-ttu-id="70372-116">A **Közzétett listák** lapon válassza az **Új lista** lehetőséget a bal alsó részén, és nevezze el az új listát **Tesztfeladatlistának**.</span><span class="sxs-lookup"><span data-stu-id="70372-116">On the **Published lists** tab, select **New list** in the lower left, and name the new list **Test task list**.</span></span>
1. <span data-ttu-id="70372-117">Válassza a **Létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="70372-117">Select **Create**.</span></span> <span data-ttu-id="70372-118">Az új lista a **Vázlatok** alatt jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="70372-118">The new list appears under **Drafts**.</span></span>
1. <span data-ttu-id="70372-119">A **Feladat címe** részben adja az első feladatnak a **Teams-integráció tesztelése** címet.</span><span class="sxs-lookup"><span data-stu-id="70372-119">Under **Task title**, give the first task the title **Testing Teams integration**.</span></span> <span data-ttu-id="70372-120">Ezután válassza a **Bevitel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="70372-120">Then select **Enter**.</span></span>
1. <span data-ttu-id="70372-121">A **Vázlatok** listán válassza ki a feladatlistát.</span><span class="sxs-lookup"><span data-stu-id="70372-121">In the **Drafts** list, select the task list.</span></span> <span data-ttu-id="70372-122">Ezután válassza a  **Közzététel** lehetőséget a jobb felső sarokban.</span><span class="sxs-lookup"><span data-stu-id="70372-122">Then select **Publish** in the upper-right corner.</span></span>
1. <span data-ttu-id="70372-123">A **Közzététel címzettjének kiválasztása** párbeszédpanelen, válassza ki azokat a csoportokat, amelyek megkapják a tesztfeladatok listáját.</span><span class="sxs-lookup"><span data-stu-id="70372-123">In the **Select who to publish to** dialog box, select the teams that should receive the test task list.</span></span>
1. <span data-ttu-id="70372-124">Válassza a **Tovább** gombot a közzétételi terv áttekintéshez.</span><span class="sxs-lookup"><span data-stu-id="70372-124">Select **Next** to review your publication plan.</span></span> <span data-ttu-id="70372-125">Ha módosításokat kell végrehajtania, válassza a  **Vissza** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="70372-125">If you must make changes, select **Back**.</span></span> 
1. <span data-ttu-id="70372-126">Válassza a **Megerősítés folytatáshoz** lehetőséget, majd válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="70372-126">Select **Confirm to proceed**, and then select **Publish**.</span></span>
1. <span data-ttu-id="70372-127">A közzététel befejeződése után a **Közzétett listák** lap tetején található üzenet jelzi, hogy sikeresen megtörtént-e a feladatlista kézbesítése.</span><span class="sxs-lookup"><span data-stu-id="70372-127">After publishing is completed, a message at the top of the **Published lists** tab indicates whether your task list was successfully delivered.</span></span>

<span data-ttu-id="70372-128">További információkért lásd: [Feladatlisták közzététele a munka létrehozásához és követéséhez a szervezetben](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df).</span><span class="sxs-lookup"><span data-stu-id="70372-128">For more information, see [Publish task lists to create and track work in your organization](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df).</span></span>

## <a name="link-pos-and-teams-for-task-management"></a><span data-ttu-id="70372-129">A pénztár és a Teams összekapcsolása feladatkezeléshez</span><span class="sxs-lookup"><span data-stu-id="70372-129">Link POS and Teams for task management</span></span>

<span data-ttu-id="70372-130">Ha a pénztárt és a Microsoft Teams alkalmazásokat feladatkezeléshez össze szeretné kapcsolni a Commerce központban, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="70372-130">To link the POS and Microsoft Teams applications for task management in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="70372-131">Lépjen ide: **Kiskereskedelem és kereskedelem \> Feladatkezelés \> Feladatok integrációja a Microsoft Teams szolgáltatással**.</span><span class="sxs-lookup"><span data-stu-id="70372-131">Go to **Retail and Commerce \> Task management \> Tasks integration with Microsoft Teams**.</span></span>
1. <span data-ttu-id="70372-132">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="70372-132">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="70372-133">Állíts a **Feladatkezelés-integráció engedélyezése** elemet **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="70372-133">Set the **Enable Task Management Integration** option to **Yes**.</span></span>
1. <span data-ttu-id="70372-134">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="70372-134">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="70372-135">A Műveleti ablaktáblán kattintson a **Feladatkezelés beállítása** elemre.</span><span class="sxs-lookup"><span data-stu-id="70372-135">On the Action Pane, select **Setup task management**.</span></span> <span data-ttu-id="70372-136">Értesítést kell kapnia, amely azt jelzi, hogy egy **Teams kiépítése** nevű kötegelt feladat létrehozása történik.</span><span class="sxs-lookup"><span data-stu-id="70372-136">You should receive a notification that indicates that a batch job that is named **Teams provision** is being created.</span></span>
1. <span data-ttu-id="70372-137">Menjen a **Rendszerfelügyelet \> Lekérdezések \> Kötegelt feladatok** ponthoz, és keresse meg azt a legutóbbi feladatot, amely a **Teams-kiépítés** leírását tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="70372-137">Go to **System administration \> Inquiries \> Batch jobs**, and find the most recent job that has the description **Teams provision**.</span></span> <span data-ttu-id="70372-138">Várjon, amíg a feladat be nem fejeződik.</span><span class="sxs-lookup"><span data-stu-id="70372-138">Wait until this job has finished running.</span></span>
1. <span data-ttu-id="70372-139">A **1070-es CDX-feladat** futtatásával tegye közzé a tervazonosítót és az üzlet hivatkozásait a Retail Server kiszolgálón.</span><span class="sxs-lookup"><span data-stu-id="70372-139">Run the **CDX job 1070** to publish the plan ID and store references to Retail Server.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="70372-140">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="70372-140">Additional resources</span></span>

[<span data-ttu-id="70372-141">A Dynamics 365 Commerce és a Microsoft Teams integrációjának áttekintése</span><span class="sxs-lookup"><span data-stu-id="70372-141">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="70372-142">A Dynamics 365 Commerce és a Microsoft Teams integrációjának engedélyezése</span><span class="sxs-lookup"><span data-stu-id="70372-142">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="70372-143">Microsoft Teams kiépítése a Dynamics 365 Commerce rendszerből</span><span class="sxs-lookup"><span data-stu-id="70372-143">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="70372-144">Felhasználói szerepkörök kezelése a Microsoft Teams alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="70372-144">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="70372-145">Üzletek és csapatok leképezése, ha már vannak csapatok a Microsoft Teams alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="70372-145">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="70372-146">Dynamics 365 Commerce és Microsoft Teams integrációja – GYIK</span><span class="sxs-lookup"><span data-stu-id="70372-146">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
