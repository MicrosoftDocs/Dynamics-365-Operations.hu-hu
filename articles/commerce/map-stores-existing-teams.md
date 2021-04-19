---
title: Üzletek és csapatok leképezése, ha már vannak csapatok a Microsoft Teams alkalmazásban
description: Ez a témakör azt mutatja be, hogyan lehet leképezni az üzleteket és a megfelelő csapatokat a Dynamics 365 Commerce központi felületén, ha a szervezet már létrehozott csapatokat a Microsoft Teams alkalmazásban a Commerce-integráció előtt.
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3edd176788b24a5f5246e9b7bcb3c6fbcdca2254
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842676"
---
# <a name="map-stores-and-teams-if-there-are-pre-existing-teams-in-microsoft-teams"></a><span data-ttu-id="9586c-103">Üzletek és csapatok leképezése, ha már vannak csapatok a Microsoft Teams alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="9586c-103">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="9586c-104">Ez a témakör azt mutatja be, hogyan lehet leképezni az üzleteket és a megfelelő csapatokat a Dynamics 365 Commerce központi felületén, ha a szervezet már létrehozott csapatokat a Microsoft Teams alkalmazásban a Commerce-integráció előtt.</span><span class="sxs-lookup"><span data-stu-id="9586c-104">This topic covers how to map stores and corresponding teams in Dynamics 365 Commerce headquarters if your organization has already created teams in Microsoft Teams before Commerce integration.</span></span>

<span data-ttu-id="9586c-105">Előfordulhat, hogy a szervezet a Dynamics 365 Commerce és a Microsoft Teams integrációja előtt csapatokat hoz létre az összes üzlet egy részére vagy mindegyikére.</span><span class="sxs-lookup"><span data-stu-id="9586c-105">Your organization may have teams created for some or all of your stores before integrating Dynamics 365 Commerce and Microsoft Teams.</span></span> <span data-ttu-id="9586c-106">Ebben az esetben a feladatszinkronizálás létrehozásához a Commerce POS és a Microsoft Teams között, és meg kell adnia az üzletek és a megfelelő csapat hozzárendelését a Commerce központi felületén.</span><span class="sxs-lookup"><span data-stu-id="9586c-106">If this is the case, to establish task synchronization between Commerce POS and Microsoft Teams you must provide the mapping of stores and corresponding team in Commerce headquarters.</span></span>

## <a name="map-stores-and-corresponding-teams-in-commerce-headquarters"></a><span data-ttu-id="9586c-107">Üzletek és a megfelelő csapatok leképezése a Commerce központi felületén</span><span class="sxs-lookup"><span data-stu-id="9586c-107">Map stores and corresponding teams in Commerce headquarters</span></span> 

<span data-ttu-id="9586c-108">Üzletek és a megfelelő csapatok leképezéséhez a Commerce központi felületén hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="9586c-108">To map stores and corresponding teams in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="9586c-109">Lépjen a **Rendszerfelügyelet \> Munkaterület \> Adatkezelés** elemre.</span><span class="sxs-lookup"><span data-stu-id="9586c-109">Go to **System Administration \> Workspace \> Data management**.</span></span>
1. <span data-ttu-id="9586c-110">Válassza az **Exportálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9586c-110">Select **Export**.</span></span> 
1. <span data-ttu-id="9586c-111">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="9586c-111">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9586c-112">A **Csoport neve** alatt írja be a „Teams-leképezés exportálása” kifejezést.</span><span class="sxs-lookup"><span data-stu-id="9586c-112">Under **Group name**, enter "Export Teams mapping".</span></span>
1. <span data-ttu-id="9586c-113">A **Kiválasztott entitások** gyorslapon válassza az **Entitás hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="9586c-113">On the **Selected entities** FastTab, select **Add entity**.</span></span> <span data-ttu-id="9586c-114">Megjelenik az **Entitás hozzáadása** párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="9586c-114">The **Add entity** dialog box appears.</span></span>  
1. <span data-ttu-id="9586c-115">Az **Entitás neve** legördülő listában válassza a **Teams-leképezés a forrás és a csapat között** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9586c-115">In the **Entity name** drop-down list, select **Teams mapping between source and team**.</span></span>
1. <span data-ttu-id="9586c-116">A **Cél adatformátum** legördülő listában válassza a **CSV** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9586c-116">In the **Target data format** drop-down list, select **CSV**.</span></span>
1. <span data-ttu-id="9586c-117">Válassza ki a **Hozzáadás**, majd a **Bezárás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9586c-117">Select **Add**, and then select **Close**.</span></span>
1. <span data-ttu-id="9586c-118">A Művelet panel alatt bal felső sarokban válassza az **Exportálás most** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9586c-118">On the top left under the Action Pane, select **Export now**.</span></span>
1. <span data-ttu-id="9586c-119">A **Entitásfeldolgozás állapota** alatt válassza a **Fájl letöltése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9586c-119">Under **Entity processing status**, select **Download file**.</span></span>
1. <span data-ttu-id="9586c-120">Az exportált CSV-fájlban adja meg a **SOURCETYPE**, **SOURCEID** és **TEAMID** értékeket az alábbiak szerint:</span><span class="sxs-lookup"><span data-stu-id="9586c-120">In the exported CSV file, enter values for **SOURCETYPE**, **SOURCEID**, and **TEAMID** as follows:</span></span>
    - <span data-ttu-id="9586c-121">A **SOURCETYPE** esetében írja be a „RetailStore” kifejezést.</span><span class="sxs-lookup"><span data-stu-id="9586c-121">For **SOURCETYPE**, enter "RetailStore".</span></span> 
    - <span data-ttu-id="9586c-122">A **SOURCEID** esetében írja be az üzlet számát (például „000135” a San Francisco-i üzlethez).</span><span class="sxs-lookup"><span data-stu-id="9586c-122">For **SOURCEID**, enter the store number (for example, "000135" for the San Francisco store).</span></span> <span data-ttu-id="9586c-123">Az üzletek számát a **Retail és Commerce \> Csatornák \> Üzlete** alatt találja.</span><span class="sxs-lookup"><span data-stu-id="9586c-123">You can find store numbers at **Retail and Commerce \> Channels \> Stores**.</span></span>
    - <span data-ttu-id="9586c-124">A **TEAMID** esetében írja be a megfelelő csapatazonosítót a Microsoft Teams alkalmazásból (például „5f8bc92b-6aa8-451e-85d1-3949c01ddc6c”).</span><span class="sxs-lookup"><span data-stu-id="9586c-124">For **TEAMID**, enter the corresponding team ID from Microsoft Teams (for example, "5f8bc92b-6aa8-451e-85d1-3949c01ddc6c").</span></span> <span data-ttu-id="9586c-125">A csapatazonosító adatait itt találja: [admin.teams.microsoft.com](https://admin.teams.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="9586c-125">You can find team ID information at [admin.teams.microsoft.com](https://admin.teams.microsoft.com).</span></span>
1. <span data-ttu-id="9586c-126">Mentse a CSV-fájlt a helyi gépre.</span><span class="sxs-lookup"><span data-stu-id="9586c-126">Save the CSV file to your local machine.</span></span>
1. <span data-ttu-id="9586c-127">Lépjen a **Rendszerfelügyelet \> Munkaterület \> Adatkezelés** elemre, majd válassza az **Importálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9586c-127">Go to **System Administration \> Workspace \> Data management**, and then select **Import**.</span></span>
1. <span data-ttu-id="9586c-128">A **Kiválasztott entitások** gyorslapon válassza a **Fájl hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="9586c-128">On the **Selected entities** FastTab, select **Add file**.</span></span> <span data-ttu-id="9586c-129">Megjelenik a **Fájl hozzáadása** párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="9586c-129">The **Add file** dialog box appears.</span></span>
1. <span data-ttu-id="9586c-130">Az **Entitás neve** legördülő listában válassza a **Teams-leképezés a forrás és a csapat között** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9586c-130">In the **Entity name** drop-down list, select **Teams mapping between source and team**.</span></span>
1. <span data-ttu-id="9586c-131">A **Forrás adatformátum** legördülő listában válassza a **CSV** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9586c-131">In the **Source data format** drop-down list, select **CSV**.</span></span>
1. <span data-ttu-id="9586c-132">Válassza a **Feltöltés és hozzáadás** lehetőséget, válassza ki a korábban mentett CSV-fájl, majd a **Megnyitás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9586c-132">Select **Upload and add**, select the CSV file that you saved previously, and then select **Open**.</span></span>
1. <span data-ttu-id="9586c-133">A **Fájl hozzáadása** párbeszédpanelen válassza a **Bezárás** elemet.</span><span class="sxs-lookup"><span data-stu-id="9586c-133">In the **Add file** dialog box, select **Close**.</span></span>
1. <span data-ttu-id="9586c-134">Válassza a Művelet panel **Mentés** elemét, majd válassza az **Importálás** elemet.</span><span class="sxs-lookup"><span data-stu-id="9586c-134">On the Action Pane, select **Save** , and then select **Import**.</span></span>

<span data-ttu-id="9586c-135">A következő példakép az megjeleníti a Commerce rendszer **Csoportleképezések exportálása** csoportját az **Entitás hozzáadása** elemeket és az exportált CSV-fájlfejléceket kiemelve.</span><span class="sxs-lookup"><span data-stu-id="9586c-135">The following example image shows the **Export teams mapping** group in Commerce with **Add entity** elements and the exported CSV file headers highlighted.</span></span>

![A Commerce rendszer Csoportleképezések exportálása csoportja az entitás hozzáadása elemekkel és az exportált CSV-fájlfejlécekkel kiemelve](media/d365-commerce-data-mgmt-export-entity.png)

> [!NOTE]
> <span data-ttu-id="9586c-137">Az előzetes lépések befejezése után hajtsa végre a [Feladatkezelés szinkronizálása a Microsoft Teams és a pénztár között](synchronize-tasks-teams-pos.md) lépést a feladatkezelés szinkronizálása érdekében.</span><span class="sxs-lookup"><span data-stu-id="9586c-137">After you complete the preceeding steps, follow the steps in [Synchronize task management between Microsoft Teams and POS](synchronize-tasks-teams-pos.md) to synchronize task management.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="9586c-138">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="9586c-138">Additional resources</span></span>

[<span data-ttu-id="9586c-139">A Dynamics 365 Commerce és a Microsoft Teams integrációjának áttekintése</span><span class="sxs-lookup"><span data-stu-id="9586c-139">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="9586c-140">A Dynamics 365 Commerce és a Microsoft Teams integrációjának engedélyezése</span><span class="sxs-lookup"><span data-stu-id="9586c-140">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="9586c-141">Microsoft Teams kiépítése a Dynamics 365 Commerce rendszerből</span><span class="sxs-lookup"><span data-stu-id="9586c-141">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="9586c-142">Feladatkezelés szinkronizálása a Microsoft Teams és a Dynamics 365 Commerce-pénztár között</span><span class="sxs-lookup"><span data-stu-id="9586c-142">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="9586c-143">Felhasználói szerepkörök kezelése a Microsoft Teams alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="9586c-143">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="9586c-144">Dynamics 365 Commerce és Microsoft Teams integrációja – GYIK</span><span class="sxs-lookup"><span data-stu-id="9586c-144">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
