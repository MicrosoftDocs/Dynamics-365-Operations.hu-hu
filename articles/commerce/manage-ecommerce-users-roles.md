---
title: Az e-kereskedelem felhasználóinak és szerepköreinek kezelése
description: Ez a témakör azt mutatja be, hogyan lehet engedélyezni a felhasználóknak a Microsoft Dynamics 365 Commerce webhely szerzői környezetéhez való hozzáférést.
author: bicyclingfool
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 44b02f262136c0d970ca9eee3e5e63ef6dc8ccb7
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794283"
---
# <a name="manage-e-commerce-users-and-roles"></a><span data-ttu-id="887ce-103">Az e-kereskedelem felhasználóinak és szerepköreinek kezelése</span><span class="sxs-lookup"><span data-stu-id="887ce-103">Manage e-Commerce users and roles</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="887ce-104">Ez a témakör azt mutatja be, hogyan lehet engedélyezni a felhasználóknak a Microsoft Dynamics 365 Commerce webhely szerzői környezetéhez való hozzáférést.</span><span class="sxs-lookup"><span data-stu-id="887ce-104">This topic explains how to grant users access to the authoring environment for your Microsoft Dynamics 365 Commerce site.</span></span>

<span data-ttu-id="887ce-105">A felhasználói hozzáférés szabályozására és a felhasználóknak a meghatározott feladatok végrehajtásához való jogosultságának biztosítására a webhelyszerkesztő környezet a Microsoft Azure Active Directory (Azure AD) felületen létrehozott biztonsági csoportokat használja.</span><span class="sxs-lookup"><span data-stu-id="887ce-105">To help control user access and grant users permission to perform specific tasks, the site authoring environment uses security groups that you create in Microsoft Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="887ce-106">Először egy új vagy meglévő biztonsági csoportot kell társítania a fejlesztői környezet minden szerepköréhez az Azure AD felületről.</span><span class="sxs-lookup"><span data-stu-id="887ce-106">You first assign a new or existing security group from Azure AD to each role in the authoring environment.</span></span> <span data-ttu-id="887ce-107">Ezt követően megadhatja vagy visszavonhatja az egyes felhasználók engedélyeit, ha hozzáadja ezeket a felhasználókat egy megfelelő biztonsági csoporthoz, vagy eltávolítja őket egy biztonsági csoportból.</span><span class="sxs-lookup"><span data-stu-id="887ce-107">You then grant or revoke permissions for individual users by either adding those users to an appropriate security group or removing them from a security group.</span></span>

## <a name="overview-of-roles-in-the-authoring-environment"></a><span data-ttu-id="887ce-108">A szerkesztői környezet szerepköreinek áttekintése</span><span class="sxs-lookup"><span data-stu-id="887ce-108">Overview of roles in the authoring environment</span></span>

<span data-ttu-id="887ce-109">A Dynamics 365 for Commerce szerkesztői környezet a következő szerepköröket támogatja.</span><span class="sxs-lookup"><span data-stu-id="887ce-109">The Dynamics 365 for Commerce authoring environment supports the following roles.</span></span>

| <span data-ttu-id="887ce-110">Szerep</span><span class="sxs-lookup"><span data-stu-id="887ce-110">Role</span></span>                 | <span data-ttu-id="887ce-111">Leírás</span><span class="sxs-lookup"><span data-stu-id="887ce-111">Description</span></span> |
|----------------------|-------------|
| <span data-ttu-id="887ce-112">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="887ce-112">System Administrator</span></span> | <span data-ttu-id="887ce-113">Azoknak a felhasználóknak, akik ezzel a szerepkörrel rendelkeznek hozzáférésük van az összes eszközhöz és az összes értékeléshez és minősítéshez.</span><span class="sxs-lookup"><span data-stu-id="887ce-113">Users who have this role have all privileges for all tools, and for all ratings and reviews.</span></span> <span data-ttu-id="887ce-114">Webhelyeket is létrehozhatnak.</span><span class="sxs-lookup"><span data-stu-id="887ce-114">They can also create sites.</span></span> |
| <span data-ttu-id="887ce-115">Adminisztrátor</span><span class="sxs-lookup"><span data-stu-id="887ce-115">Administrator</span></span>   | <span data-ttu-id="887ce-116">Azoknak a felhasználóknak, akik ezzel a szerepkörrel rendelkeznek jogosultságuk van minden eszköz, illetve értékelés és minősítés elérésére egy adott webhelystruktúrában.</span><span class="sxs-lookup"><span data-stu-id="887ce-116">Users who have this role have all privileges for all tools and RnR in a given site structure.</span></span> |
| <span data-ttu-id="887ce-117">Webes gyártó</span><span class="sxs-lookup"><span data-stu-id="887ce-117">Web Producer</span></span>         | <span data-ttu-id="887ce-118">A ezzel a szerepkörrel rendelkező felhasználók lapokat, töredékeket és sablonokat hozhatnak létre, feltölthetik és kezelhetik az eszközöket, valamint gazdagítják a termékeket és kategóriákat.</span><span class="sxs-lookup"><span data-stu-id="887ce-118">Users who have this role can create pages, fragments and templates, upload and manage assets, and enrich products and categories.</span></span> |
| <span data-ttu-id="887ce-119">Olvasó</span><span class="sxs-lookup"><span data-stu-id="887ce-119">Reader</span></span>               | <span data-ttu-id="887ce-120">Az ezzel a szerepkörrel rendelkező felhasználók megtekinthetik a lapokat, a sablonokat, eszközöket, töredékeket, elrendezéseket és a beállításokat, de nem módosíthatják őket.</span><span class="sxs-lookup"><span data-stu-id="887ce-120">Users who have this role can view pages, templates, assets, fragments, layouts and settings, but may not make changes.</span></span> |
| <span data-ttu-id="887ce-121">RnR-moderátor</span><span class="sxs-lookup"><span data-stu-id="887ce-121">RnR Moderator</span></span>        | <span data-ttu-id="887ce-122">Az ezzel a szerepkörrel rendelkező felhasználók moderálhatják a termékértékeléseket.</span><span class="sxs-lookup"><span data-stu-id="887ce-122">Users who have this role can moderate product reviews.</span></span> |

## <a name="system-administrator-role"></a><span data-ttu-id="887ce-123">Rendszergazda szerepkör</span><span class="sxs-lookup"><span data-stu-id="887ce-123">System Administrator role</span></span>

<span data-ttu-id="887ce-124">A mikor telepíti a Dynamics 365 Commerce példányt a Microsoft Dynamics Lifecycle Services (LCS) környezetbe, a rendszer ara kéri, hogy adjon meg egy biztonsági csoportot a **Rendszergazda** szerepkörhöz.</span><span class="sxs-lookup"><span data-stu-id="887ce-124">When you provision Dynamics 365 Commerce in the Microsoft Dynamics Lifecycle Services (LCS) environment, you're asked to provide a security group for the **System Administrator** role.</span></span> <span data-ttu-id="887ce-125">Ezt a szerepkört a program automatikusan alkalmazza minden olyan webhelyre, amelyet az Ön által konfigurált környezetben hoz létre.</span><span class="sxs-lookup"><span data-stu-id="887ce-125">This role is then automatically applied to all sites that you create in the environment that you're configuring.</span></span> <span data-ttu-id="887ce-126">Ennek a szerepkörnek a biztonsági csoportja csak az LCS-ben frissíthető.</span><span class="sxs-lookup"><span data-stu-id="887ce-126">The security group for this role can be updated only in LCS.</span></span> <span data-ttu-id="887ce-127">Az **Webhely kezelése** lapon az összes webhelyhez írásvédettként jeleni meg, és csak tájékoztatásul szolgál.</span><span class="sxs-lookup"><span data-stu-id="887ce-127">On the **Site Administration** page for all sites, it appears as read-only and is for informational purposes only.</span></span>

## <a name="administrator-role"></a><span data-ttu-id="887ce-128">Adminisztrátor szerepkör</span><span class="sxs-lookup"><span data-stu-id="887ce-128">Administrator role</span></span>

<span data-ttu-id="887ce-129">Amikor új webhelyet hoz létre a Commerce szolgáltatásban, meg kell adnia egy biztonsági csoportot s **Rendszergazda** szerepkörhöz.</span><span class="sxs-lookup"><span data-stu-id="887ce-129">When you create a new site in Commerce, you're asked to provide a security group for the **Administrator** role.</span></span> <span data-ttu-id="887ce-130">Az ebben a témakörben korábban ismertetett táblázatban megtekintheti az egyes szerepkörök által biztosított engedélyek áttekintését.</span><span class="sxs-lookup"><span data-stu-id="887ce-130">See the table earlier in this topic for an overview of the permissions that this role grants.</span></span>

## <a name="add-or-update-security-groups"></a><span data-ttu-id="887ce-131">Biztonsági csoportok hozzáadása vagy frissítése</span><span class="sxs-lookup"><span data-stu-id="887ce-131">Add or update security groups</span></span>

<span data-ttu-id="887ce-132">Miután létrehozta a webhelyet, csak azok a felhasználók férhetnek hozzá a webhely szerzői környezetéhez, akik **Rendszergazda** és az **Adminisztrátor** szerepkörökhöz társított biztonsági csoportnak tagjai.</span><span class="sxs-lookup"><span data-stu-id="887ce-132">After your site is created, only users who are in the security groups that are associated with the **System Administrator** and **Administrator** roles can access the authoring environment for that site.</span></span> <span data-ttu-id="887ce-133">Ha felhasználókat szeretne hozzárendelni a **Webes gyártó**, **RnR moderátor** és a **Olvasó** szerepkörökhöz biztonsági csoportokat kell hozzárendelnie azokhoz a szerepkörökhöz.</span><span class="sxs-lookup"><span data-stu-id="887ce-133">To assign users to the **Web Producer**, **RnR Moderator**, and **Reader** roles, you must assign security groups to those roles.</span></span> <span data-ttu-id="887ce-134">Ha egy szerepkörhöz egy biztonsági csoportot szeretne hozzáadni, vagy egy szerepkörhöz aktuálisan hozzárendelt biztonsági csoportot szeretne frissíteni, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="887ce-134">To add a security group to a role, or to update a security group that is currently assigned to a role, follow these steps.</span></span>

1. <span data-ttu-id="887ce-135">Menjen a frissíteni kívánt webhelyre.</span><span class="sxs-lookup"><span data-stu-id="887ce-135">Go to the site that you want to update.</span></span>
1. <span data-ttu-id="887ce-136">A **Webhely kezelése** modulban nyissa meg a **Biztonság** lapot.</span><span class="sxs-lookup"><span data-stu-id="887ce-136">In **Site management**, open the **Security** page.</span></span>
1. <span data-ttu-id="887ce-137">Válassza ki a módosítani kívánt szerepkört.</span><span class="sxs-lookup"><span data-stu-id="887ce-137">Select the role to modify.</span></span>
1. <span data-ttu-id="887ce-138">Adja hozzá a biztonsági csoportokat a szerepkörökhöz, vagy távolítson el biztonsági csoportokat a szerepköröktől.</span><span class="sxs-lookup"><span data-stu-id="887ce-138">Add security groups to roles, or remove security groups from roles.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="887ce-139">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="887ce-139">Additional resources</span></span>

[<span data-ttu-id="887ce-140">Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához</span><span class="sxs-lookup"><span data-stu-id="887ce-140">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

[<span data-ttu-id="887ce-141">A webhely keresőmotor-optimalizálási (SEO) szempontjai</span><span class="sxs-lookup"><span data-stu-id="887ce-141">Search engine optimization (SEO) considerations for your site</span></span>](search-engine-optimization-considerations.md)

[<span data-ttu-id="887ce-142">Tartalomra vonatkozó biztonsági házirend (CSP) kezelése</span><span class="sxs-lookup"><span data-stu-id="887ce-142">Manage Content Security Policy (CSP)</span></span>](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]