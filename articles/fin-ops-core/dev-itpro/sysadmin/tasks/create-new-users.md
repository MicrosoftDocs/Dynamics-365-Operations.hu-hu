---
title: Új felhasználók létrehozása
description: A felhasználók a szervezet olyan belső alkalmazottai vagy külső vevői és szállítói, akiknek hozzáféréssel kell rendelkezniük a rendszerhez a munkájuk elvégzéséhez.
author: maertenm
manager: AnnBe
ms.date: 08/30/2019
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
ms.openlocfilehash: 4a5635f96132b2e52227b569e7e480fa55e82d61
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180944"
---
# <a name="create-new-users"></a><span data-ttu-id="497f9-103">Új felhasználók létrehozása</span><span class="sxs-lookup"><span data-stu-id="497f9-103">Create new users</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]
[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="497f9-104">A felhasználók a szervezet olyan belső alkalmazottai vagy külső vevői és szállítói, akiknek hozzáféréssel kell rendelkezniük a rendszerhez a munkájuk elvégzéséhez.</span><span class="sxs-lookup"><span data-stu-id="497f9-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to do their jobs.</span></span>

## <a name="associate-a-user-with-a-license-new-license-types-only"></a><span data-ttu-id="497f9-105">Felhasználó társítása licenchez (csak az új licenctípusok esetében)</span><span class="sxs-lookup"><span data-stu-id="497f9-105">Associate a user with a license (new license types only)</span></span>
<span data-ttu-id="497f9-106">Azoknak a vevőknek, akik a 2019 októberében hozzáadott új licenccel rendelkeznek, a felhasználókat társítaniuk kell egy licenchez.</span><span class="sxs-lookup"><span data-stu-id="497f9-106">For customers who are on one of the new license types that were added in October 2019, users must be associated with a license.</span></span> <span data-ttu-id="497f9-107">A licenchez társított felhasználók automatikusan olyan rendszerfelhasználóként jelennek meg, akiknek nincs szerepkörük az első bejelentkezés alkalmával.</span><span class="sxs-lookup"><span data-stu-id="497f9-107">Users who are associated with a license are automatically added as system users who have no roles the first time that they sign in.</span></span> <span data-ttu-id="497f9-108">A licenchez nem társított felhasználók figyelmeztető üzenetet kapnak.</span><span class="sxs-lookup"><span data-stu-id="497f9-108">Users who aren't associated with a licence receive a warning message.</span></span>

<span data-ttu-id="497f9-109">A rendszeradminisztrátorok [rendelhetnek hozzá licenceket a felhasználókhoz](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) a [Microsoft 365 felügyeleti központban](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="497f9-109">System admins can [assign licenses to users](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) in the [Microsoft 365 admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).</span></span>

## <a name="add-a-new-user"></a><span data-ttu-id="497f9-110">Új felhasználó hozzáadása</span><span class="sxs-lookup"><span data-stu-id="497f9-110">Add a new user</span></span>
1. <span data-ttu-id="497f9-111">Ugrás a **Rendszerfelügyelet \> Felhasználók \> Felhasználók** elemre.</span><span class="sxs-lookup"><span data-stu-id="497f9-111">Go to **System administration \> Users \> Users**.</span></span>
2. <span data-ttu-id="497f9-112">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="497f9-112">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="497f9-113">A **Felhasználói azonosító** mezőbe írja be a felhasználó egyedi azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="497f9-113">In the **User ID** field, enter a unique identifier for the user.</span></span> <span data-ttu-id="497f9-114">A felhasználó azonosítóját kötelező megadni.</span><span class="sxs-lookup"><span data-stu-id="497f9-114">A user ID is required.</span></span>  
4. <span data-ttu-id="497f9-115">Írja be a felhasználó nevét a **Felhasználónév** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="497f9-115">In the **User name** field, enter the user's name.</span></span>  
5. <span data-ttu-id="497f9-116">A **Tartomány** mezőben adja meg a felhasználó tartományát.</span><span class="sxs-lookup"><span data-stu-id="497f9-116">In the **Domain** field, enter the user's domain.</span></span>  
6. <span data-ttu-id="497f9-117">Az **Alias** mezőbe írja be a felhasználó aliasát.</span><span class="sxs-lookup"><span data-stu-id="497f9-117">In the **Alias** field, enter the user's alias.</span></span>  
7. <span data-ttu-id="497f9-118">A **Vállalat** mezőben válassza ki a vállalatot.</span><span class="sxs-lookup"><span data-stu-id="497f9-118">In the **Company** field, select the desired company.</span></span> 
8. <span data-ttu-id="497f9-119">A **Felhasználó szerepkörei** gyorslapon válassza a **Szerepkörök társítása** lehetőséget a [felhasználók biztonsági szerepkörökhöz történő hozzárendeléshez](assign-users-security-roles.md).</span><span class="sxs-lookup"><span data-stu-id="497f9-119">On the **User's roles** FastTab, select **Assign roles** to [assign users to security roles](assign-users-security-roles.md)</span></span>
9. <span data-ttu-id="497f9-120">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="497f9-120">Select **OK**.</span></span>
10. <span data-ttu-id="497f9-121">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="497f9-121">Select **Save**.</span></span>

## <a name="import-users"></a><span data-ttu-id="497f9-122">Felhasználók importálása</span><span class="sxs-lookup"><span data-stu-id="497f9-122">Import users</span></span>
1. <span data-ttu-id="497f9-123">A műveleti ablaktáblán válassza a **Felhasználók importálása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="497f9-123">On the Action Pane, select **Import users**.</span></span>
2. <span data-ttu-id="497f9-124">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="497f9-124">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="497f9-125">Válassza a **Felhasználók importálása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="497f9-125">Select **Import users**.</span></span>
4. <span data-ttu-id="497f9-126">Válassza **Bezárás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="497f9-126">Select **Close**.</span></span>

