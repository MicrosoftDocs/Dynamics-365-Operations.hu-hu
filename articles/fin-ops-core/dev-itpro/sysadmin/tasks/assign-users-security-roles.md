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
ms.openlocfilehash: e4f4ef4535de9e371829c2d86d4fdc1400510c7b
ms.sourcegitcommit: 6aa74f66f1abd3a7977050a5339b0b17e62ff053
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/15/2019
ms.locfileid: "2807996"
---
# <a name="assign-users-to-security-roles"></a><span data-ttu-id="4e4be-103">Felhasználók hozzárendelése a biztonsági szerepkörökhöz</span><span class="sxs-lookup"><span data-stu-id="4e4be-103">Assign users to security roles</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4e4be-104">A közös képességeken túl más képességek használatához a felhasználóknak biztonsági szerepkörökhöz kell lenniük társítva.</span><span class="sxs-lookup"><span data-stu-id="4e4be-104">To use anything other than common capabilities, users must be assigned to security roles.</span></span> <span data-ttu-id="4e4be-105">Ez az eljárás bemutatja, hogy hogyan lehet hozzárendelni automatikusan a szerepkörökhöz az üzleti adatokon alapuló rendszergazdákat.</span><span class="sxs-lookup"><span data-stu-id="4e4be-105">This procedure explains how system administrators can automatically assign users to roles, based on business data.</span></span> 

## <a name="automatically-assign-users-to-roles"></a><span data-ttu-id="4e4be-106">Felhasználók automatikus hozzárendelése a szerepkörökhöz</span><span class="sxs-lookup"><span data-stu-id="4e4be-106">Automatically assign users to roles</span></span>
1. <span data-ttu-id="4e4be-107">Ugorjon a **Navigációs lap > Modulok > Rendszerfelügyelet > Biztonság > Felhasználók szerepkörökhöz rendelése** pontra.</span><span class="sxs-lookup"><span data-stu-id="4e4be-107">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
2. <span data-ttu-id="4e4be-108">Válassza ki a fastruktúrában a „Számviteli felügyelő” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4e4be-108">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="4e4be-109">Válassza ki azt a szerepkört, amelyre vonatkozóan konfigurálni kívánja a szabályt.</span><span class="sxs-lookup"><span data-stu-id="4e4be-109">Select the role that you want to configure the rule for.</span></span> <span data-ttu-id="4e4be-110">Ebben a példában válassza ki a Számviteli felügyelő lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4e4be-110">In this example, select Accounting supervisor.</span></span> 
3. <span data-ttu-id="4e4be-111">Kattintson a **Szabály hozzáadása** lehetőségre a legördülő párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="4e4be-111">Click **Add rule** to open the drop dialog.</span></span>
4. <span data-ttu-id="4e4be-112">A kívánt rekord megkeresése és kijelölése a **Lekérdezés kiválasztása** listában.</span><span class="sxs-lookup"><span data-stu-id="4e4be-112">In the **Select a query**list, find and select the desired record.</span></span> <span data-ttu-id="4e4be-113">Válassza ki a lekérdezést ezen szabály használatához.</span><span class="sxs-lookup"><span data-stu-id="4e4be-113">Select the query to use for this rule.</span></span>  
5. <span data-ttu-id="4e4be-114">A **Tagsági szabály neve** listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="4e4be-114">In the **Membership rule name** list, click the link in the selected row.</span></span>
6. <span data-ttu-id="4e4be-115">Kattintson a **Lekérdezés szerkesztése** elemre.</span><span class="sxs-lookup"><span data-stu-id="4e4be-115">Click **Edit query**.</span></span> <span data-ttu-id="4e4be-116">Igény szerint módosítsa a lekérdezést.</span><span class="sxs-lookup"><span data-stu-id="4e4be-116">Edit the query, as needed.</span></span>  
7. <span data-ttu-id="4e4be-117">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="4e4be-117">Click **OK**.</span></span>
8. <span data-ttu-id="4e4be-118">Kattintson az **Automatikus szerepkör-hozzárendelés futtatása** elemre.</span><span class="sxs-lookup"><span data-stu-id="4e4be-118">Click **Run automatic role assignment**.</span></span>
9. <span data-ttu-id="4e4be-119">Lépjen a **Navigációs ablaktábla > Modulok > Rendszerfelügyelet > Felhasználók > Felhasználók** részre (lehetőleg másik böngészőlapon).</span><span class="sxs-lookup"><span data-stu-id="4e4be-119">Go to **Navigation pane > Modules > System administration > Users > Users** (ideally in a separate browser tab).</span></span>
10. <span data-ttu-id="4e4be-120">Tekintse át a különböző felhasználókhoz rendelt szerepköröket, és győződjön meg arról, hogy a szerepkör-hozzárendelési lekérdezés helyes volt.</span><span class="sxs-lookup"><span data-stu-id="4e4be-120">Review the roles assigned to various users to confirm that the role assignment query was correct.</span></span> <span data-ttu-id="4e4be-121">Szükség esetén módosítsa, majd futtassa újra.</span><span class="sxs-lookup"><span data-stu-id="4e4be-121">Adjust and re-run if needed.</span></span>

## <a name="exclude-users-from-automatic-role-assignment"></a><span data-ttu-id="4e4be-122">A felhasználók kizárása az Automatikus szerepkör-hozzárendelésből</span><span class="sxs-lookup"><span data-stu-id="4e4be-122">Exclude users from automatic role assignment</span></span>
1. <span data-ttu-id="4e4be-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4e4be-123">Close the page.</span></span>
2. <span data-ttu-id="4e4be-124">Ugorjon a **Navigációs lap > Modulok > Rendszerfelügyelet > Biztonság > Felhasználók szerepkörökhöz rendelése** pontra.</span><span class="sxs-lookup"><span data-stu-id="4e4be-124">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
3. <span data-ttu-id="4e4be-125">Válassza ki a fastruktúrában a „Számviteli felügyelő” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4e4be-125">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="4e4be-126">Szerepkör választása.</span><span class="sxs-lookup"><span data-stu-id="4e4be-126">Select a role.</span></span> <span data-ttu-id="4e4be-127">Például, válassza ki a Számviteli felügyelő lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4e4be-127">For this example, select Accounting supervisor.</span></span>  
4. <span data-ttu-id="4e4be-128">A **Szerepkörhöz rendelt felhasználók** menüben válassza ki a **Felhasználók manuális hozzárendelését/kizárását**.</span><span class="sxs-lookup"><span data-stu-id="4e4be-128">In the **Users assigned to role** menu, select **Manually assign / exclude users**.</span></span>
5. <span data-ttu-id="4e4be-129">A **Felhasználók szerepkörhöz rendelése vagy kizárása onnan** listában jelölje meg a kiválasztott sorokat.</span><span class="sxs-lookup"><span data-stu-id="4e4be-129">In the **Assign users to or exclude users from role** list, mark the selected row.</span></span> <span data-ttu-id="4e4be-130">Felhasználó kiválasztása</span><span class="sxs-lookup"><span data-stu-id="4e4be-130">Select a user.</span></span>  
6. <span data-ttu-id="4e4be-131">A **Műveleti ablaktáblán** kattintson a **Kizárás szerepkörből** elemre.</span><span class="sxs-lookup"><span data-stu-id="4e4be-131">On the **Action pane**, select **Exclude from role**.</span></span>
    
    <span data-ttu-id="4e4be-132">Kattintson a **Kizárás szerepkörből** lehetőségre a kiválasztott felhasználók szerepkörből történő kizárásához.</span><span class="sxs-lookup"><span data-stu-id="4e4be-132">Click **Exclude from role** to exclude the selected users from the role.</span></span> <span data-ttu-id="4e4be-133">A kivételek eltávolításához jelölje ki azokat a felhasználókat, akikre vonatkozóan el szeretné távolítani a kizárásokat, majd ezt követően kattintson az **Állapot visszaállítása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4e4be-133">To remove exclusions, select the users that you want to remove exclusions for, and then click **Reset status**.</span></span> <span data-ttu-id="4e4be-134">Amikor eltávolít egy kizárást a felhasználói állapot visszaállításával, a rendszer ismét automatikusan hozzárendeli a felhasználó szerepkört.</span><span class="sxs-lookup"><span data-stu-id="4e4be-134">When you remove an exclusion by resetting the user’s status, the user’s role is again assigned automatically.</span></span> <span data-ttu-id="4e4be-135">Azonban a rendszer a felhasználót nem rendeli hozzá automatikusan a szerepkörhöz és kizárja a szerepkörből, amikor a rendszer visszaállítja az állapotát.</span><span class="sxs-lookup"><span data-stu-id="4e4be-135">However, the user is not immediately assigned to the role or excluded from the role when you reset the status.</span></span> <span data-ttu-id="4e4be-136">A rendszer ehelyett a felhasználót vagy hozzárendeli a szerepkörhöz vagy eltávolítja a szerepkörből a következő alkalommal, hogy az automatikus szerepkör-hozzárendelési szabályokat futtassa a rendszer.</span><span class="sxs-lookup"><span data-stu-id="4e4be-136">Instead, the user is either assigned to the role or removed from the role the next time that the rules for automatic role assignment are run.</span></span>  
