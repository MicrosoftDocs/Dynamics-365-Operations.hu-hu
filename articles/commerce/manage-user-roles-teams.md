---
title: Felhasználói szerepkörök kezelése a Microsoft Teams alkalmazásban
description: Ez a témakör a Microsoft Dynamics 365 Commerce felhasználói szerepek kezelésének módját ismerteti a Microsoft Teams alkalmazásban.
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
ms.openlocfilehash: 7b4734fd363cd5ee44f228e0c0f9ce73abad1aaa
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021852"
---
# <a name="manage-user-roles-in-microsoft-teams"></a><span data-ttu-id="c1675-103">Felhasználói szerepkörök kezelése a Microsoft Teams alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="c1675-103">Manage user roles in Microsoft Teams</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c1675-104">Ez a témakör a Microsoft Dynamics 365 Commerce felhasználói szerepek kezelésének módját ismerteti a Microsoft Teams alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="c1675-104">This topic describes how to manage Microsoft Dynamics 365 Commerce user roles in Microsoft Teams.</span></span>

<span data-ttu-id="c1675-105">Amikor csapatot hoz létre a Teams minden üzletéhez vagy csatornájához, létrejön egy csoporttagság, amely a létrehozott csapatnak felel meg (például: `HOUSTON_D365@<YourTenantAzureADDomain>.com`).</span><span class="sxs-lookup"><span data-stu-id="c1675-105">As you create a team for each store or channel in Teams, a group membership that corresponds to the team is created (for example, `HOUSTON_D365@<YourTenantAzureADDomain>.com`).</span></span> <span data-ttu-id="c1675-106">A csoporttagságba tartozó minden áruházi dolgozó a következő két szerepkör valamelyikét kapja meg: **Tulajdonos** vagy **Tag**.</span><span class="sxs-lookup"><span data-stu-id="c1675-106">All the store workers under a team group membership are assigned one of two user roles: **Owner** or **Member**.</span></span> <span data-ttu-id="c1675-107">Az üzlet olyan alkalmazottai, akiknek a **Tulajdonos** felhasználói szerepkörük van, műveleteket hajthatnak végre, például saját csatornát adhatnak hozzá, illetve tagokat adhatnak hozzá vagy törölhetnek.</span><span class="sxs-lookup"><span data-stu-id="c1675-107">Store employees who have the **Owner** user role can perform operations such as adding a private channel, and adding or deleting members.</span></span> <span data-ttu-id="c1675-108">Az üzletvezetők rendelkeznek általában a **Tulajdonos** felhasználói szerepkörrel.</span><span class="sxs-lookup"><span data-stu-id="c1675-108">Typically, store managers have the **Owner** user role.</span></span>

<span data-ttu-id="c1675-109">Az alábbi ábra a csapattagok listáját és a Microsoft Teams felügyeleti központban található felhasználói szerepköreiket mutatja be.</span><span class="sxs-lookup"><span data-stu-id="c1675-109">The following illustration shows an example of a list of team members and their user roles in the Microsoft Teams admin center.</span></span>

![Csapattagok és felhasználói szerepkörök a Microsoft Teams felügyeleti központban](media/d365-commerce-teams-integration-user-roles.png)

<span data-ttu-id="c1675-111">A további tudnivalókat lásd: [Csoporttulajdonosok és -tagok hozzárendelése a Microsoft Teams alkalmazásban](/microsoftteams/assign-roles-permissions).</span><span class="sxs-lookup"><span data-stu-id="c1675-111">For more information, see [Assign team owners and members in Microsoft Teams](/microsoftteams/assign-roles-permissions).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c1675-112">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c1675-112">Additional resources</span></span>

[<span data-ttu-id="c1675-113">A Dynamics 365 Commerce és a Microsoft Teams integrációjának áttekintése</span><span class="sxs-lookup"><span data-stu-id="c1675-113">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="c1675-114">A Dynamics 365 Commerce és a Microsoft Teams integrációjának engedélyezése</span><span class="sxs-lookup"><span data-stu-id="c1675-114">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="c1675-115">Microsoft Teams kiépítése a Dynamics 365 Commerce rendszerből</span><span class="sxs-lookup"><span data-stu-id="c1675-115">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="c1675-116">Feladatkezelés szinkronizálása a Microsoft Teams és a Dynamics 365 Commerce-pénztár között</span><span class="sxs-lookup"><span data-stu-id="c1675-116">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="c1675-117">Üzletek és csapatok leképezése, ha már vannak csapatok a Microsoft Teams alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="c1675-117">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="c1675-118">Dynamics 365 Commerce és Microsoft Teams integrációja – GYIK</span><span class="sxs-lookup"><span data-stu-id="c1675-118">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)