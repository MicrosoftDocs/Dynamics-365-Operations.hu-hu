---
title: Új felhasználók létrehozása
description: A felhasználók a szervezet olyan belső alkalmazottai vagy külső vevői és szállítói, akiknek hozzáféréssel kell rendelkezniük a rendszerhez a munkájuk elvégzéséhez.
author: maertenm
manager: AnnBe
ms.date: 02/06/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9db4b6d355d6499bce6c550b2fbe76b82cf69fd4
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143579"
---
# <a name="create-new-users"></a><span data-ttu-id="b4534-103">Új felhasználók létrehozása</span><span class="sxs-lookup"><span data-stu-id="b4534-103">Create new users</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b4534-104">A felhasználók a szervezet olyan belső alkalmazottai vagy külső vevői és szállítói, akiknek hozzáféréssel kell rendelkezniük a rendszerhez a munkájuk elvégzéséhez.</span><span class="sxs-lookup"><span data-stu-id="b4534-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to do their jobs.</span></span>

## <a name="associate-a-user-with-a-license-new-license-types-only"></a><span data-ttu-id="b4534-105">Felhasználó társítása licenchez (csak az új licenctípusok esetében)</span><span class="sxs-lookup"><span data-stu-id="b4534-105">Associate a user with a license (new license types only)</span></span>
<span data-ttu-id="b4534-106">Azoknak a vevőknek, akik a 2019 októberében hozzáadott új licenccel rendelkeznek, a felhasználókat társítaniuk kell egy licenchez.</span><span class="sxs-lookup"><span data-stu-id="b4534-106">For customers who are on one of the new license types that were added in October 2019, users must be associated with a license.</span></span> <span data-ttu-id="b4534-107">A licenchez társított felhasználók automatikusan olyan rendszerfelhasználóként jelennek meg, akiknek nincs szerepkörük az első bejelentkezés alkalmával.</span><span class="sxs-lookup"><span data-stu-id="b4534-107">Users who are associated with a license are automatically added as system users who have no roles the first time that they sign in.</span></span>

<span data-ttu-id="b4534-108">A rendszeradminisztrátorok [rendelhetnek hozzá licenceket a felhasználókhoz](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) a [Microsoft 365 felügyeleti központban](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="b4534-108">System admins can [assign licenses to users](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) in the [Microsoft 365 admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).</span></span>

## <a name="associate-an-external-user-with-a-license-new-license-types-only"></a><span data-ttu-id="b4534-109">Külső felhasználó társítása licenchez (csak az új licenctípusok esetében)</span><span class="sxs-lookup"><span data-stu-id="b4534-109">Associate an external user with a license (new license types only)</span></span>
<span data-ttu-id="b4534-110">A bérlő környezetének külső felhasználóit fel kell tüntetni a gazdabérlő címtárában (Azure Active Directory (Azure AD)), hogy hozzájuk lehessen rendelni a licenceket.</span><span class="sxs-lookup"><span data-stu-id="b4534-110">Users external to the tenant that the environment was deployed into need to be represented in the host tenant directory (Azure Active Directory (Azure AD)) so that they can be assigned licenses.</span></span> <span data-ttu-id="b4534-111">Ezeket a külső felhasználókat hozzá kell adni a bérlőhöz az Azure AD felületen vendég felhasználóként, majd hozzájuk rendelni a megfelelő licenceket.</span><span class="sxs-lookup"><span data-stu-id="b4534-111">Those external users should be added to the tenant in Azure AD as guest users and then assigned the appropriate licenses.</span></span> <span data-ttu-id="b4534-112">További tájékoztatás: [Azure Active Directory B2B együttműködő felhasználók hozzáadása az Azure Portal webhelyen](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span><span class="sxs-lookup"><span data-stu-id="b4534-112">For more information, see [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

## <a name="add-a-new-user"></a><span data-ttu-id="b4534-113">Új felhasználó hozzáadása</span><span class="sxs-lookup"><span data-stu-id="b4534-113">Add a new user</span></span>
1. <span data-ttu-id="b4534-114">Ugrás a **Rendszerfelügyelet \> Felhasználók \> Felhasználók** elemre.</span><span class="sxs-lookup"><span data-stu-id="b4534-114">Go to **System administration \> Users \> Users**.</span></span>
2. <span data-ttu-id="b4534-115">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="b4534-115">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="b4534-116">A **Felhasználói azonosító** mezőbe írja be a felhasználó egyedi azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="b4534-116">In the **User ID** field, enter a unique identifier for the user.</span></span> <span data-ttu-id="b4534-117">A felhasználó azonosítóját kötelező megadni.</span><span class="sxs-lookup"><span data-stu-id="b4534-117">A user ID is required.</span></span>  
4. <span data-ttu-id="b4534-118">Írja be a felhasználó nevét a **Felhasználónév** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b4534-118">In the **User name** field, enter the user's name.</span></span>  
5. <span data-ttu-id="b4534-119">A **Tartomány** mezőben adja meg a felhasználó tartományát.</span><span class="sxs-lookup"><span data-stu-id="b4534-119">In the **Domain** field, enter the user's domain.</span></span>  
6. <span data-ttu-id="b4534-120">Az **Alias** mezőbe írja be a felhasználó aliasát.</span><span class="sxs-lookup"><span data-stu-id="b4534-120">In the **Alias** field, enter the user's alias.</span></span>  
7. <span data-ttu-id="b4534-121">A **Vállalat** mezőben válassza ki a vállalatot.</span><span class="sxs-lookup"><span data-stu-id="b4534-121">In the **Company** field, select the desired company.</span></span> 
8. <span data-ttu-id="b4534-122">A **Felhasználó szerepkörei** gyorslapon válassza a **Szerepkörök társítása** lehetőséget a felhasználók biztonsági szerepkörökhöz történő hozzárendeléshez.</span><span class="sxs-lookup"><span data-stu-id="b4534-122">On the **User's roles** FastTab, select **Assign roles** to assign users to security roles.</span></span> <span data-ttu-id="b4534-123">További információ [Felhasználók hozzárendelése biztonsági szerepkörökhöz](assign-users-security-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b4534-123">For more information, see [Assign users to security roles](assign-users-security-roles.md).</span></span>
9. <span data-ttu-id="b4534-124">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b4534-124">Select **OK**.</span></span>
10. <span data-ttu-id="b4534-125">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b4534-125">Select **Save**.</span></span>

## <a name="import-users"></a><span data-ttu-id="b4534-126">Felhasználók importálása</span><span class="sxs-lookup"><span data-stu-id="b4534-126">Import users</span></span>
1. <span data-ttu-id="b4534-127">A műveleti ablaktáblán válassza a **Felhasználók importálása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b4534-127">On the Action Pane, select **Import users**.</span></span>
2. <span data-ttu-id="b4534-128">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="b4534-128">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="b4534-129">Válassza a **Felhasználók importálása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b4534-129">Select **Import users**.</span></span>
4. <span data-ttu-id="b4534-130">Válassza **Bezárás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b4534-130">Select **Close**.</span></span>

