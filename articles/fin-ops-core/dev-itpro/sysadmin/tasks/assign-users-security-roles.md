---
title: Felhasználók hozzárendelése a biztonsági szerepkörökhöz
description: A Finance and Operations alkalmazások eléréséhez hozzá kell rendelni a felhasználókat a biztonsági szerepkörökhöz.
author: ChrisGarty
manager: AnnBe
ms.date: 11/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0744f45ac91dfb9b5aae35091e3675202c9144f9
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143546"
---
# <a name="assign-users-to-security-roles"></a><span data-ttu-id="3f7ef-103">Felhasználók hozzárendelése a biztonsági szerepkörökhöz</span><span class="sxs-lookup"><span data-stu-id="3f7ef-103">Assign users to security roles</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3f7ef-104">A közös képességeken túl más képességek használatához a felhasználóknak biztonsági szerepkörökhöz kell lenniük társítva.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-104">To use anything other than common capabilities, users must be assigned to security roles.</span></span> <span data-ttu-id="3f7ef-105">Ez az eljárás bemutatja, hogy hogyan lehet hozzárendelni automatikusan a szerepkörökhöz az üzleti adatokon alapuló rendszergazdákat.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-105">This procedure explains how system administrators can automatically assign users to roles, based on business data.</span></span> 

## <a name="automatically-assign-users-to-roles"></a><span data-ttu-id="3f7ef-106">Felhasználók automatikus hozzárendelése a szerepkörökhöz</span><span class="sxs-lookup"><span data-stu-id="3f7ef-106">Automatically assign users to roles</span></span>
1. <span data-ttu-id="3f7ef-107">Ugorjon a **Navigációs lap > Modulok > Rendszerfelügyelet > Biztonság > Felhasználók szerepkörökhöz rendelése** pontra.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-107">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
2. <span data-ttu-id="3f7ef-108">Válassza ki a fastruktúrában a „Számviteli felügyelő” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-108">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="3f7ef-109">Válassza ki azt a szerepkört, amelyre vonatkozóan konfigurálni kívánja a szabályt.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-109">Select the role that you want to configure the rule for.</span></span> <span data-ttu-id="3f7ef-110">Ebben a példában válassza ki a Számviteli felügyelő lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-110">In this example, select Accounting supervisor.</span></span> 
3. <span data-ttu-id="3f7ef-111">Kattintson a **Szabály hozzáadása** lehetőségre a legördülő párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-111">Click **Add rule** to open the drop dialog.</span></span>
4. <span data-ttu-id="3f7ef-112">A kívánt rekord megkeresése és kijelölése a **Lekérdezés kiválasztása** listában.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-112">In the **Select a query**list, find and select the desired record.</span></span> <span data-ttu-id="3f7ef-113">Válassza ki a lekérdezést ezen szabály használatához.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-113">Select the query to use for this rule.</span></span>  
5. <span data-ttu-id="3f7ef-114">A **Tagsági szabály neve** listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-114">In the **Membership rule name** list, click the link in the selected row.</span></span>
6. <span data-ttu-id="3f7ef-115">Kattintson a **Lekérdezés szerkesztése** elemre.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-115">Click **Edit query**.</span></span> <span data-ttu-id="3f7ef-116">Igény szerint módosítsa a lekérdezést.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-116">Edit the query, as needed.</span></span>  
7. <span data-ttu-id="3f7ef-117">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-117">Click **OK**.</span></span>
8. <span data-ttu-id="3f7ef-118">Kattintson az **Automatikus szerepkör-hozzárendelés futtatása** elemre.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-118">Click **Run automatic role assignment**.</span></span>
9. <span data-ttu-id="3f7ef-119">Lépjen a **Navigációs ablaktábla > Modulok > Rendszerfelügyelet > Felhasználók > Felhasználók** részre (lehetőleg másik böngészőlapon).</span><span class="sxs-lookup"><span data-stu-id="3f7ef-119">Go to **Navigation pane > Modules > System administration > Users > Users** (ideally in a separate browser tab).</span></span>
10. <span data-ttu-id="3f7ef-120">Tekintse át a különböző felhasználókhoz rendelt szerepköröket, és győződjön meg arról, hogy a szerepkör-hozzárendelési lekérdezés helyes volt.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-120">Review the roles assigned to various users to confirm that the role assignment query was correct.</span></span> <span data-ttu-id="3f7ef-121">Szükség esetén módosítsa, majd futtassa újra.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-121">Adjust and re-run if needed.</span></span>

## <a name="exclude-users-from-automatic-role-assignment"></a><span data-ttu-id="3f7ef-122">A felhasználók kizárása az Automatikus szerepkör-hozzárendelésből</span><span class="sxs-lookup"><span data-stu-id="3f7ef-122">Exclude users from automatic role assignment</span></span>
1. <span data-ttu-id="3f7ef-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-123">Close the page.</span></span>
2. <span data-ttu-id="3f7ef-124">Ugorjon a **Navigációs lap > Modulok > Rendszerfelügyelet > Biztonság > Felhasználók szerepkörökhöz rendelése** pontra.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-124">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
3. <span data-ttu-id="3f7ef-125">Válassza ki a fastruktúrában a „Számviteli felügyelő” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-125">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="3f7ef-126">Szerepkör választása.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-126">Select a role.</span></span> <span data-ttu-id="3f7ef-127">Például, válassza ki a Számviteli felügyelő lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-127">For this example, select Accounting supervisor.</span></span>  
4. <span data-ttu-id="3f7ef-128">A **Szerepkörhöz rendelt felhasználók** menüben válassza ki a **Felhasználók manuális hozzárendelését/kizárását**.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-128">In the **Users assigned to role** menu, select **Manually assign / exclude users**.</span></span>
5. <span data-ttu-id="3f7ef-129">A **Felhasználók szerepkörhöz rendelése vagy kizárása onnan** listában jelölje meg a kiválasztott sorokat.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-129">In the **Assign users to or exclude users from role** list, mark the selected row.</span></span> <span data-ttu-id="3f7ef-130">Felhasználó kiválasztása</span><span class="sxs-lookup"><span data-stu-id="3f7ef-130">Select a user.</span></span>  
6. <span data-ttu-id="3f7ef-131">A **Műveleti ablaktáblán** kattintson a **Kizárás szerepkörből** elemre.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-131">On the **Action pane**, select **Exclude from role**.</span></span>
    
    <span data-ttu-id="3f7ef-132">Kattintson a **Kizárás szerepkörből** lehetőségre a kiválasztott felhasználók szerepkörből történő kizárásához.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-132">Click **Exclude from role** to exclude the selected users from the role.</span></span> <span data-ttu-id="3f7ef-133">A kivételek eltávolításához jelölje ki azokat a felhasználókat, akikre vonatkozóan el szeretné távolítani a kizárásokat, majd ezt követően kattintson az **Állapot visszaállítása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-133">To remove exclusions, select the users that you want to remove exclusions for, and then click **Reset status**.</span></span> <span data-ttu-id="3f7ef-134">Amikor eltávolít egy kizárást a felhasználói állapot visszaállításával, a rendszer ismét automatikusan hozzárendeli a felhasználó szerepkört.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-134">When you remove an exclusion by resetting the user's status, the user's role is again assigned automatically.</span></span> <span data-ttu-id="3f7ef-135">Azonban a rendszer a felhasználót nem rendeli hozzá automatikusan a szerepkörhöz és kizárja a szerepkörből, amikor a rendszer visszaállítja az állapotát.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-135">However, the user is not immediately assigned to the role or excluded from the role when you reset the status.</span></span> <span data-ttu-id="3f7ef-136">A rendszer ehelyett a felhasználót vagy hozzárendeli a szerepkörhöz vagy eltávolítja a szerepkörből a következő alkalommal, hogy az automatikus szerepkör-hozzárendelési szabályokat futtassa a rendszer.</span><span class="sxs-lookup"><span data-stu-id="3f7ef-136">Instead, the user is either assigned to the role or removed from the role the next time that the rules for automatic role assignment are run.</span></span>  
