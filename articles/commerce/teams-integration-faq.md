---
title: Dynamics 365 Commerce- és Microsoft Teams-integráció GYIK
description: Ez a témakör a Microsoft Dynamics 365 Commerce és a Microsoft Teams integrációjával kapcsolatos gyakori kérdésekre ad válaszokat.
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
ms.openlocfilehash: 26e1dc53126c0615332457aa785415c4c7112bbd
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842679"
---
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-faq"></a><span data-ttu-id="c9385-103">Dynamics 365 Commerce- és Microsoft Teams-integráció GYIK</span><span class="sxs-lookup"><span data-stu-id="c9385-103">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="c9385-104">Ez a témakör a Microsoft Dynamics 365 Commerce és a Microsoft Teams integrációjával kapcsolatos gyakori kérdésekre ad válaszokat.</span><span class="sxs-lookup"><span data-stu-id="c9385-104">This topic provides answers to frequently asked questions regarding Microsoft Dynamics 365 Commerce and Microsoft Teams integration.</span></span>

### <a name="who-in-the-store-becomes-an-owner-of-a-team-while-provisioning-teams-from-commerce"></a><span data-ttu-id="c9385-105">Az üzletben ki válik egy csapat tulajdonosvá a Teams Commerce rendszerből való létesítése alatt?</span><span class="sxs-lookup"><span data-stu-id="c9385-105">Who in the store becomes an owner of a team while provisioning Teams from Commerce?</span></span> 

<span data-ttu-id="c9385-106">A program minden üzletvezetőt automatikusan hozzáad a megfelelő csapatcsoporthoz, hogy végrehajtsa például egy saját csatorna hozzáadását és tagok hozzáadását vagy törlését.</span><span class="sxs-lookup"><span data-stu-id="c9385-106">All store managers are automatically added as owners to the corresponding team group so that they can perform operations such as adding a private channel and adding or deleting members.</span></span> 

### <a name="how-do-i-assign-the-communications-manager-role-to-an-employee-in-commerce-headquarters"></a><span data-ttu-id="c9385-107">Hogyan lehet a „kommunikációs vezető” szerepkört hozzárendelni a Commerce központi alkalmazotthoz?</span><span class="sxs-lookup"><span data-stu-id="c9385-107">How do I assign the "communications manager" role to an employee in Commerce headquarters?</span></span> 

<span data-ttu-id="c9385-108">A kommunikációvezetők a Microsoft Teams szolgáltatásban feladatlisták létrehozására és közzétételére is képesek.</span><span class="sxs-lookup"><span data-stu-id="c9385-108">Communication managers in Microsoft Teams have the ability to create and publish task lists.</span></span> <span data-ttu-id="c9385-109">A szervezetnek azokat az alkalmazottakat, akiknek kommunikációs vezetővé kell válniuk, hozzá kell rendelni a „kiskereskedelmi feladatkezelő” szerepkört a Commerce központban.</span><span class="sxs-lookup"><span data-stu-id="c9385-109">Organization employees who need to become communication managers must have the "retail task manager" role assigned to them in Commerce headquarters.</span></span>

<span data-ttu-id="c9385-110">A következő lépések szerint rendelje hozzá a kiskereskedelmi feladatkezelő szerepkört egy alkalmazotthoz a Commerce központban.</span><span class="sxs-lookup"><span data-stu-id="c9385-110">To assign the retail task manager role to an employee in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="c9385-111">Nyissa meg a következőt: **Retail és Commerce \> Alkalmazottak \> Felhasználók**.</span><span class="sxs-lookup"><span data-stu-id="c9385-111">Go to **Retail and Commerce \> Employees \> Users**.</span></span>
1. <span data-ttu-id="c9385-112">Válasszon egy alkalmazottat.</span><span class="sxs-lookup"><span data-stu-id="c9385-112">Select an employee.</span></span>
1. <span data-ttu-id="c9385-113">A **Felhasználó szerepkörei** gyorslapon válassza a **Szerepkörök hozzárendelése** elemet.</span><span class="sxs-lookup"><span data-stu-id="c9385-113">On the **User's roles** FastTab, select **Assign roles**.</span></span>
1. <span data-ttu-id="c9385-114">A **Szerepkörök társítása a felhasználóhoz** párbeszédpanelen válassza ki a **Retail feladatkezelő** szerepkört, majd kattintsonaz **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="c9385-114">In the **Assign roles to user** dialog box, select the **Retail task manager** role, and then select **OK**.</span></span>

### <a name="how-do-i-make-a-specific-organization-hierarchy-available-to-upload-into-microsoft-teams"></a><span data-ttu-id="c9385-115">Hogyan lehet egy adott szervezeti hierarchiát feltölthetővé tenni a Microsoft Teams szolgáltatásba?</span><span class="sxs-lookup"><span data-stu-id="c9385-115">How do I make a specific organization hierarchy available to upload into Microsoft Teams?</span></span>

<span data-ttu-id="c9385-116">A Commerce központban minden szervezeti hierarchia egy vagy több célhoz van társítva.</span><span class="sxs-lookup"><span data-stu-id="c9385-116">In Commerce headquarters, every organization's hierarchy is associated with one or more purposes.</span></span> <span data-ttu-id="c9385-117">Győződjön meg róla, hogy a hierarchiához, amelyet a Microsoft Teams szolgáltatásba ki szeretne építeni, társítva van a **Kiskereskedelmi jelentéskészítés**, ahogy a következő mintaképen látható.</span><span class="sxs-lookup"><span data-stu-id="c9385-117">Make sure the hierarchy that you want to provision into Microsoft Teams has the **Retail reporting** purpose associated with it, as shown in the following example image.</span></span> 

![Példa szervezeti hierarchia céljára a Commerce központ alkalmazásban](media/d365-commerce-organization-hierarchies-purpose.png)

### <a name="how-do-i-enable-retail-store-workers-to-sign-in-to-commerce-point-of-sale-pos-using-azure-active-directory-azure-ad"></a><span data-ttu-id="c9385-119">Hogyan lehet engedélyezni a kiskereskedelmi üzlet dolgozóinak, hogy az Azure Active Directory (Azure AD) használatával jelentkezzenek be a Commerce pénztár (POS) alkalmazásba?</span><span class="sxs-lookup"><span data-stu-id="c9385-119">How do I enable retail store workers to sign in to Commerce point of sale (POS) using Azure Active Directory (Azure AD)?</span></span>

<span data-ttu-id="c9385-120">A Commerce pénztár bejelentkezési felületének az Azure AD hitelesítés használatára való konfigurálásával kapcsolatos további információkért lásd: [Azure Active Directory-hitelesítés engedélyezése pénztári bejelentkezéshez](aad-pos-logon.md).</span><span class="sxs-lookup"><span data-stu-id="c9385-120">For information about how to configure the Commerce POS sign-in experience to use Azure AD authentication, see [Enable Azure Active Directory authentication for POS sign-in](aad-pos-logon.md).</span></span>

### <a name="how-do-i-map-stores-and-corresponding-teams-in-commerce-headquarters-if-my-organization-has-already-created-teams-in-microsoft-teams"></a><span data-ttu-id="c9385-121">Hogyan kell megfeleltetni az áruházakat és a megfelelő csapatokat a Commerce központon belül, ha a szervezetem már létrehozta a csapatokat a Microsoft Teams szolgáltatásban?</span><span class="sxs-lookup"><span data-stu-id="c9385-121">How do I map stores and corresponding teams in Commerce headquarters if my organization has already created teams in Microsoft Teams?</span></span>

<span data-ttu-id="c9385-122">Ha vannak már létező csapatok, az üzletek és csapatok leképezésével kapcsolatos tudnivalókat lásd: [Üzletek és megfelelő csapatok leképezése, h a szervezetben már találhatók meglévő csapatok a Microsoft Teams szolgáltatásban](map-stores-existing-teams.md).</span><span class="sxs-lookup"><span data-stu-id="c9385-122">For information on how to map stores and teams if there are pre-existing teams, see [Map stores and corresponding teams if your organization has pre-existing teams in Microsoft Teams](map-stores-existing-teams.md).</span></span>

### <a name="how-do-i-clear-the-microsoft-graph-api-token-stored-in-the-session-storage"></a><span data-ttu-id="c9385-123">Hogyan lehet törölni a munkamenet-tárolóban tárolt Microsoft Graph API-tokent?</span><span class="sxs-lookup"><span data-stu-id="c9385-123">How do I clear the Microsoft Graph API token stored in the session storage?</span></span>

<span data-ttu-id="c9385-124">A felhasználónak, aki a pénztárba (POS) Azure Active Directory (Azure AD) fiókkal jelentkezett be, ki kell jelentkeznie a pénztárból, vagy be kell zárnia az alkalmazást a munkamenet-tároló törléséhez.</span><span class="sxs-lookup"><span data-stu-id="c9385-124">A user who has signed in to the point of sale (POS) with an Azure Active Directory (Azure AD) account should sign out from the POS or close the application to clear the session storage.</span></span> 

> [!TIP]
> <span data-ttu-id="c9385-125">A javasolt legjobb gyakorlat az, ha az üzlet dolgozóit mindig zárolják a POS terminált, vagy kijelentkeznek egy munkamenetből, amikor nem használják a terminált.</span><span class="sxs-lookup"><span data-stu-id="c9385-125">A recommended best practice is to always have store workers lock the POS terminal or sign out from a session when not using the terminal.</span></span> 

### <a name="what-happens-if-a-store-doesnt-have-store-managers"></a><span data-ttu-id="c9385-126">Mi történik, ha egy üzletnek nincs üzletvezetői?</span><span class="sxs-lookup"><span data-stu-id="c9385-126">What happens if a store doesn't have store managers?</span></span>

<span data-ttu-id="c9385-127">Ha nincs vezető az üzletben, akkor nem jön létre csapatcsoport az üzlethez vagy a Teamsben.</span><span class="sxs-lookup"><span data-stu-id="c9385-127">If a store doesn't have managers, a team group will not be created for the store or in Teams.</span></span> 

### <a name="what-happens-if-a-store-manager-leaves-the-company"></a><span data-ttu-id="c9385-128">Mi történik, ha egy üzletvezető elhagyja a vállalatot?</span><span class="sxs-lookup"><span data-stu-id="c9385-128">What happens if a store manager leaves the company?</span></span>

<span data-ttu-id="c9385-129">Egy tulajdonos szerepkörrel rendelkező személy felvehet új üzletvezetőt a Commerce központban, és újra létesítheti a Teamst, hogy az új vezető a csoporthoz szükséges jogosultságokkal rendelkezzen a Teamsben.</span><span class="sxs-lookup"><span data-stu-id="c9385-129">Anyone with the owner role can add a new store manager in Commerce headquarters and reprovision Teams so that the new manager will have the necessary privileges in Teams for the group.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="c9385-130">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c9385-130">Additional resources</span></span>

[<span data-ttu-id="c9385-131">A Dynamics 365 Commerce és a Microsoft Teams integrációjának áttekintése</span><span class="sxs-lookup"><span data-stu-id="c9385-131">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="c9385-132">A Dynamics 365 Commerce és a Microsoft Teams integrációjának engedélyezése</span><span class="sxs-lookup"><span data-stu-id="c9385-132">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="c9385-133">Microsoft Teams kiépítése a Dynamics 365 Commerce rendszerből</span><span class="sxs-lookup"><span data-stu-id="c9385-133">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="c9385-134">Feladatkezelés szinkronizálása a Microsoft Teams és a Dynamics 365 Commerce-pénztár között</span><span class="sxs-lookup"><span data-stu-id="c9385-134">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="c9385-135">Felhasználói szerepkörök kezelése a Microsoft Teams alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="c9385-135">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="c9385-136">Üzletek és csapatok leképezése, ha már vannak csapatok a Microsoft Teams alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="c9385-136">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)
