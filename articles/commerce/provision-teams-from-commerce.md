---
title: Microsoft Teams kiépítése a Dynamics 365 Commerce rendszerből
description: Ez a témakör azt ismerteti, hogyan lehet a Dynamics 365 Commerce szervezeti adatainak használatával Microsoft Teams alkalmazást kiépíteni.
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
ms.openlocfilehash: ba7c74942735b723d1015dc4da0068fbb631bc6b
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908904"
---
# <a name="provision-microsoft-teams-from-dynamics-365-commerce"></a><span data-ttu-id="ebdab-103">Microsoft Teams kiépítése a Dynamics 365 Commerce rendszerből</span><span class="sxs-lookup"><span data-stu-id="ebdab-103">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ebdab-104">Ez a témakör azt ismerteti, hogyan lehet a Dynamics 365 Commerce szervezeti adatainak használatával Microsoft Teams alkalmazást kiépíteni.</span><span class="sxs-lookup"><span data-stu-id="ebdab-104">This topic describes how to provision Microsoft Teams by using organizational data from Dynamics 365 Commerce.</span></span>

<span data-ttu-id="ebdab-105">A Dynamics 365 Commerce segítségével könnyen kiépíthető a Teams, ha még nem állított be itt csapatokat a kiskereskedelmi áruházai számára.</span><span class="sxs-lookup"><span data-stu-id="ebdab-105">Dynamics 365 Commerce offers an easy way to provision Teams if you haven't yet set up teams for your retail stores there.</span></span> <span data-ttu-id="ebdab-106">Ha kihasználja a Commerce rendszerből származó, a Teamsben használni kívánt, jól definiált információkat, az segíthet üzlete alkalmazottainak a Teams használatának megkezdésében.</span><span class="sxs-lookup"><span data-stu-id="ebdab-106">By taking advantage of well-defined information from Commerce that you want to use in Teams, you can help your store employees get started in Teams.</span></span> <span data-ttu-id="ebdab-107">Ezen információk közé tartozik a szervezeti hierarchia, az üzletnevek, az alkalmazotti adatok és az Azure Active Directory (Azure AD) fiókok.</span><span class="sxs-lookup"><span data-stu-id="ebdab-107">This information includes the organizational hierarchy, store names, employee information, and Azure Active Directory (Azure AD) accounts.</span></span> 

<span data-ttu-id="ebdab-108">A Teams létesítés folyamatának két lépése van:</span><span class="sxs-lookup"><span data-stu-id="ebdab-108">The process of provisioning Teams has two main steps:</span></span>

1. <span data-ttu-id="ebdab-109">A Teamsben hozzon létre egy-egy csapatot minden kiskereskedelmi üzlethez, és adja hozzá az üzlet dolgozóit a megfelelő csapat tagjaiként.</span><span class="sxs-lookup"><span data-stu-id="ebdab-109">In Teams, create a team for each retail store, and add store workers as members of the appropriate team.</span></span> <span data-ttu-id="ebdab-110">Ha egy alkalmazott több kiskereskedelmi üzlethez is társítva van, a csoporttagság ezt a tényt fogja tükrözni.</span><span class="sxs-lookup"><span data-stu-id="ebdab-110">If an employee is associated with more than one retail store, team membership will reflect that fact.</span></span> <span data-ttu-id="ebdab-111">A Teams feladatainak közzétételét segítő, regionális vezetőket tagként tartalmazó kommunikációs csoport jön létre.</span><span class="sxs-lookup"><span data-stu-id="ebdab-111">A communications team that includes regional managers as members will be created to help publish tasks from Teams.</span></span>
1. <span data-ttu-id="ebdab-112">Töltse fel a szervezeti hierarchiát a Commerce rendszerből a Teamsbe.</span><span class="sxs-lookup"><span data-stu-id="ebdab-112">Upload your organizational hierarchy from Commerce to Teams.</span></span>

## <a name="provision-teams-in-commerce-headquarters"></a><span data-ttu-id="ebdab-113">Teams kiépítése a Commerce központi felületén</span><span class="sxs-lookup"><span data-stu-id="ebdab-113">Provision Teams in Commerce headquarters</span></span>

<span data-ttu-id="ebdab-114">A Microsoft Teams kiépítése előtt végezze el ezeket a feladatokat:</span><span class="sxs-lookup"><span data-stu-id="ebdab-114">Before you provision Microsoft Teams, complete these tasks:</span></span>

- <span data-ttu-id="ebdab-115">Erősítse meg, hogy minden regionális vezető kommunikációs vezetői minősítést kapott.</span><span class="sxs-lookup"><span data-stu-id="ebdab-115">Confirm that all regional managers have been made communications managers.</span></span>
- <span data-ttu-id="ebdab-116">Ellenőrizze, hogy minden üzletvezető és dolgozó Azure-fiókja hozzá van társítva az adott vezető vagy dolgozó munkavégzői rekordjához a Commerce központi felületén.</span><span class="sxs-lookup"><span data-stu-id="ebdab-116">Confirm that the Azure account of every store manager and worker has been associated with that manager's or worker's worker record in Commerce headquarters.</span></span>

<span data-ttu-id="ebdab-117">A Teams kiépítéséhez a Commerce központi felületén kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ebdab-117">To provision Teams in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="ebdab-118">Lépjen a **Retail és Commerce \> Csatorna beállítása \> Microsoft Teams integrációs konfiguráció** elemre.</span><span class="sxs-lookup"><span data-stu-id="ebdab-118">Go to **Retail and Commerce \> Channel setup \> Microsoft Teams Integration Configuration**.</span></span>
1. <span data-ttu-id="ebdab-119">A Művelet panelen válassza a **Csapatok kiépítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ebdab-119">On the Action Pane, select **Provision teams**.</span></span> <span data-ttu-id="ebdab-120">Létrejön egy **Csapatok kiépítése** nevű kötegelt feladat.</span><span class="sxs-lookup"><span data-stu-id="ebdab-120">A batch job that is named **Teams provision** is created.</span></span>
1. <span data-ttu-id="ebdab-121">Menjen a **Rendszerfelügyelet \> Lekérdezések \> Kötegelt feladatok** ponthoz, és keresse meg azt a legutóbbi feladatot, amely a **Teams-kiépítés** leírását tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="ebdab-121">Go to **System administration \> Inquiries \> Batch jobs**, and find the most recent job that has the description **Teams provision**.</span></span> <span data-ttu-id="ebdab-122">Várjon, amíg a feladat be nem fejeződik.</span><span class="sxs-lookup"><span data-stu-id="ebdab-122">Wait until this job has finished running.</span></span>

> [!TIP]
> <span data-ttu-id="ebdab-123">Ha a regionális vezetők, üzletvezetők és áruházi dolgozók egyike sem lett Teams-licenccel társítva, a következő hibaüzenet jelenhet meg: „Nem sikerült beolvasni az alkalmazható SKU-kategóriákat a felhasználóhoz.”</span><span class="sxs-lookup"><span data-stu-id="ebdab-123">If none of your regional managers, store managers, and store workers have been associated with a Teams license, you might receive the following error message: "Failed to retrieve appliable Sku categories for the user."</span></span> <span data-ttu-id="ebdab-124">A probléma megoldásához válassza a **Csoportok és tagok szinkronizálása** lehetőséget a Művelet panelen.</span><span class="sxs-lookup"><span data-stu-id="ebdab-124">To correct the issue, select **Sync teams and members** on the Action Pane.</span></span>

<!-- ![Dynamics 365 Commerce - Teams integration configuration](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)-->

## <a name="validate-teams-provisioning-in-the-teams-admin-center"></a><span data-ttu-id="ebdab-125">A Teams kiépítésének ellenőrzése a Teams felügyeleti központjában</span><span class="sxs-lookup"><span data-stu-id="ebdab-125">Validate Teams provisioning in the Teams admin center</span></span>

<span data-ttu-id="ebdab-126">A Microsoft Teams felügyeleti központban a Microsoft Teams-kiépítés ellenőrzéshez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ebdab-126">To validate Microsoft Teams provisioning in the Microsoft Teams admin center, follow these steps.</span></span>
    
1. <span data-ttu-id="ebdab-127">Lépjen a [Teams felügyeleti központjába](https://admin.teams.microsoft.com/), és jelentkezzen be az e-kereskedelmi bérlő rendszergazdájaként.</span><span class="sxs-lookup"><span data-stu-id="ebdab-127">Go to the [Teams admin center](https://admin.teams.microsoft.com/), and sign in as the administrator of your e-commerce tenant.</span></span>
1. <span data-ttu-id="ebdab-128">A bal oldali navigációs panelen válassza a **Csapatok** lehetőséget a kibontásához, majd válassza a **Csapatok kezelése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ebdab-128">In the left navigation pane, select **Teams** to expand it, and then select **Manage teams**.</span></span>
1. <span data-ttu-id="ebdab-129">Ellenőrizze, hogy minden Commerce kiskereskedelmi üzlethez létrehoztak-e egy csapatot.</span><span class="sxs-lookup"><span data-stu-id="ebdab-129">Confirm that one team has been created for each Commerce retail store.</span></span>
1. <span data-ttu-id="ebdab-130">Jelöljön ki egy csapatot, és győződjön meg arról, hogy az áruházi dolgozók tagként hozzá lettek adva.</span><span class="sxs-lookup"><span data-stu-id="ebdab-130">Select a team, and confirm that store workers have been added to it as members.</span></span>
1. <span data-ttu-id="ebdab-131">A bal oldali navigációs ablakban válassza a **Felhasználók** lehetőséget, és ellenőrizze, hogy az összes áruház összes alkalmazottja felhasználóként hozzá lett-e adva.</span><span class="sxs-lookup"><span data-stu-id="ebdab-131">In the left navigation pane, select **Users**, and confirm that all store employees in all stores have been added as users.</span></span>

<span data-ttu-id="ebdab-132">Az alábbi ábra egy példát mutat be a **Csapatok kezelése** lapra a Teams felügyeleti központban.</span><span class="sxs-lookup"><span data-stu-id="ebdab-132">The following illustration shows an example of the **Manage teams** page in the Teams admin center.</span></span>

![Példa a Csapatok kezelése lapra a Teams felügyeleti központban](media/Teams-FLW-Admin-Teams.png)

## <a name="upload-a-commerce-organizational-hierarchy-to-teams"></a><span data-ttu-id="ebdab-134">Commerce szervezeti hierarchia feltöltése a Teamsbe</span><span class="sxs-lookup"><span data-stu-id="ebdab-134">Upload a Commerce organizational hierarchy to Teams</span></span>
    
<span data-ttu-id="ebdab-135">A Commerce szervezeti hierarchia a Microsoft Teams alkalmazásban használható tevékenységek közzétételére az összes vagy kijelölt, ugyanazt a hierarchiastruktúrát használó üzletben.</span><span class="sxs-lookup"><span data-stu-id="ebdab-135">The Commerce organizational hierarchy can be used in Microsoft Teams to publish tasks to all or selected stores that use the same hierarchy structure.</span></span>

<span data-ttu-id="ebdab-136">Ha fel szeretne tölteni egy Commerce szervezeti hierarchiát a Teamsbe, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ebdab-136">To upload a Commerce organizational hierarchy to Teams, follow these steps.</span></span>
    
1. <span data-ttu-id="ebdab-137">A Commerce központi felületén lépjen a **Retail és Commerce \> Csatornabeállítás \> Microsoft Teams-intergráció konfigurációja** elemre.</span><span class="sxs-lookup"><span data-stu-id="ebdab-137">In Commerce headquarters, go to **Retail and Commerce \> Channel setup \> Microsoft Teams Integration Configuration**.</span></span>
1. <span data-ttu-id="ebdab-138">Válassza a **Célzási hierarchia letöltése** lehetőséget, majd a szervezeti hierarchia vesszővel elválasztott értékfájlja (CSV) letöltéséhez válassza a **Kiskereskedelmi üzletek régiónként** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ebdab-138">Select **Download targeting hierarchy**, and then select **Retail Stores by Region** to download a comma-separated values (CSV) file of the organizational hierarchy.</span></span>
1. <span data-ttu-id="ebdab-139">Telepítse a Microsoft Teams PowerShell modult a [Microsoft Teams PowerShell telepítése](https://docs.microsoft.com/microsoftteams/teams-powershell-install) lépéseit követve.</span><span class="sxs-lookup"><span data-stu-id="ebdab-139">Install the Microsoft Teams PowerShell module by following the steps in [Install Microsoft Teams PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
1. <span data-ttu-id="ebdab-140">Amikor a rendszer kéri a Teams PowerShell ablakban, jelentkezzen be az Azure AD-bérlő rendszergazdai fiókjával.</span><span class="sxs-lookup"><span data-stu-id="ebdab-140">When you're prompted in the Teams PowerShell window, sign in by using the administrator account for your Azure AD tenant.</span></span>
1. <span data-ttu-id="ebdab-141">Kövesse a [Csoportcélzási hierarchia beállítása](https://docs.microsoft.com/microsoftteams/set-up-your-team-hierarchy) lépéseit a célzási hierarchia CSV-fájljának feltöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="ebdab-141">Follow the steps in [Set up your team targeting hierarchy](https://docs.microsoft.com/microsoftteams/set-up-your-team-hierarchy) to upload the CSV file for the targeting hierarchy.</span></span>

## <a name="verify-that-the-organizational-hierarchy-was-uploaded-to-teams"></a><span data-ttu-id="ebdab-142">Annak ellenőrzése, hogy a szervezeti hierarchia fel van-e töltve a Teamsbe</span><span class="sxs-lookup"><span data-stu-id="ebdab-142">Verify that the organizational hierarchy was uploaded to Teams</span></span>

<span data-ttu-id="ebdab-143">Annak ellenőrzéséhez, hogy a szervezeti hierarchia fel van-e töltve a Microsoft Teams alkalmazásba, tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="ebdab-143">To verify that the organizational hierarchy was uploaded to Microsoft Teams, follow these steps.</span></span>

1. <span data-ttu-id="ebdab-144">Jelentkezzen be a Teamsbe kommunikációs vezetőként.</span><span class="sxs-lookup"><span data-stu-id="ebdab-144">Sign in to Teams as a communications manager.</span></span>
1. <span data-ttu-id="ebdab-145">A bal oldali navigációs ablakban válassza a **Feladatok tervező szerint** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ebdab-145">In the left navigation pane, select **Tasks by Planner**.</span></span>
1. <span data-ttu-id="ebdab-146">A **Közzétett listák** lapon hozzon létre egy új listát, amely üres feladattal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="ebdab-146">On the **Published lists** tab, create a new list that has a dummy task.</span></span>
1. <span data-ttu-id="ebdab-147">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ebdab-147">Select **Publish**.</span></span> <span data-ttu-id="ebdab-148">A szervezeti hierarchiának meg kell jelennie a **Közzététel címzettjének kiválasztása** párbeszédpanelen, amint az az alábbi ábrán látható.</span><span class="sxs-lookup"><span data-stu-id="ebdab-148">The organizational hierarchy should appear in the **Select who to publish to** dialog box, as shown in the example in the following illustration.</span></span>

![Példa szervezeti hierarchiára a Közzététel címzettjének kiválasztása párbeszédpanelen](media/Microsoft-teams-verify-org-hierarchy.png)

## <a name="additional-resources"></a><span data-ttu-id="ebdab-150">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="ebdab-150">Additional resources</span></span>

[<span data-ttu-id="ebdab-151">A Dynamics 365 Commerce és a Microsoft Teams integrációjának áttekintése</span><span class="sxs-lookup"><span data-stu-id="ebdab-151">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="ebdab-152">A Dynamics 365 Commerce és a Microsoft Teams integrációjának engedélyezése</span><span class="sxs-lookup"><span data-stu-id="ebdab-152">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="ebdab-153">Feladatkezelés szinkronizálása a Microsoft Teams és a Dynamics 365 Commerce-pénztár között</span><span class="sxs-lookup"><span data-stu-id="ebdab-153">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="ebdab-154">Felhasználói szerepkörök kezelése a Microsoft Teams alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="ebdab-154">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="ebdab-155">Üzletek és csapatok leképezése, ha már vannak csapatok a Microsoft Teams alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="ebdab-155">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="ebdab-156">Dynamics 365 Commerce és Microsoft Teams integrációja – GYIK</span><span class="sxs-lookup"><span data-stu-id="ebdab-156">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
