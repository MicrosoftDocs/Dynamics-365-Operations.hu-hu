---
title: Felhasználók hozzárendelése a biztonsági szerepkörökhöz
description: A Microsoft Dynamics 365 for Finance and Operations, Enterprise kiadás eléréséhez hozzá kell rendelni a felhasználókat a biztonsági szerepkörökhöz.
author: maertenm
manager: AnnBe
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4c0afd0f5754e59307a82af9c9700b36c31edcc4
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/02/2019
ms.locfileid: "1851359"
---
# <a name="assign-users-to-security-roles"></a><span data-ttu-id="93257-103">Felhasználók hozzárendelése a biztonsági szerepkörökhöz</span><span class="sxs-lookup"><span data-stu-id="93257-103">Assign users to security roles</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="93257-104">A Microsoft Dynamics 365 for Finance and Operations, Enterprise kiadás eléréséhez hozzá kell rendelni a felhasználókat a biztonsági szerepkörökhöz.</span><span class="sxs-lookup"><span data-stu-id="93257-104">To access Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, users must be assigned to security roles.</span></span> <span data-ttu-id="93257-105">Ez az eljárás bemutatja, hogy hogyan lehet hozzárendelni automatikusan a szerepkörökhöz az üzleti adatokon alapuló rendszergazdákat.</span><span class="sxs-lookup"><span data-stu-id="93257-105">This procedure explains how system administrators can assign users to roles automatically, based on business data.</span></span> <span data-ttu-id="93257-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="93257-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="automatically-assign-users-to-roles"></a><span data-ttu-id="93257-107">Felhasználók automatikus hozzárendelése a szerepkörökhöz</span><span class="sxs-lookup"><span data-stu-id="93257-107">Automatically assign users to roles</span></span>
1. <span data-ttu-id="93257-108">Ugorjon a **Navigációs lap > Modulok > Rendszerfelügyelet > Biztonság > Felhasználók szerepkörökhöz rendelése** pontra.</span><span class="sxs-lookup"><span data-stu-id="93257-108">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
2. <span data-ttu-id="93257-109">Válassza ki a fastruktúrában a „Számviteli felügyelő” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="93257-109">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="93257-110">Válassza ki azt a szerepkört, amelyre vonatkozóan konfigurálni kívánja a szabályt.</span><span class="sxs-lookup"><span data-stu-id="93257-110">Select the role that you want to configure the rule for.</span></span> <span data-ttu-id="93257-111">Ebben a példában válassza ki a Számviteli felügyelő lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="93257-111">In this example, select Accounting supervisor.</span></span> 
3. <span data-ttu-id="93257-112">Kattintson a **Szabály hozzáadása** lehetőségre a legördülő párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="93257-112">Click **Add rule** to open the drop dialog.</span></span>
4. <span data-ttu-id="93257-113">A kívánt rekord megkeresése és kijelölése a **Lekérdezés kiválasztása** listában.</span><span class="sxs-lookup"><span data-stu-id="93257-113">In the **Select a query**list, find and select the desired record.</span></span> <span data-ttu-id="93257-114">Válassza ki a lekérdezést ezen szabály használatához.</span><span class="sxs-lookup"><span data-stu-id="93257-114">Select the query to use for this rule.</span></span>  
5. <span data-ttu-id="93257-115">A **Tagsági szabály neve** listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="93257-115">In the **Membership rule name** list, click the link in the selected row.</span></span>
6. <span data-ttu-id="93257-116">Kattintson a **Lekérdezés szerkesztése** elemre.</span><span class="sxs-lookup"><span data-stu-id="93257-116">Click **Edit query**.</span></span> <span data-ttu-id="93257-117">Igény szerint módosítsa a lekérdezést.</span><span class="sxs-lookup"><span data-stu-id="93257-117">Edit the query, as needed.</span></span>  
7. <span data-ttu-id="93257-118">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="93257-118">Click **OK**.</span></span>

## <a name="exclude-users-from-automatic-role-assignment"></a><span data-ttu-id="93257-119">A felhasználók kizárása az Automatikus szerepkör-hozzárendelésből</span><span class="sxs-lookup"><span data-stu-id="93257-119">Exclude users from automatic role assignment</span></span>
1. <span data-ttu-id="93257-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="93257-120">Close the page.</span></span>
2. <span data-ttu-id="93257-121">Ugorjon a **Navigációs lap > Modulok > Rendszerfelügyelet > Biztonság > Felhasználók szerepkörökhöz rendelése** pontra.</span><span class="sxs-lookup"><span data-stu-id="93257-121">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
3. <span data-ttu-id="93257-122">Válassza ki a fastruktúrában a „Számviteli felügyelő” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="93257-122">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="93257-123">Szerepkör választása.</span><span class="sxs-lookup"><span data-stu-id="93257-123">Select a role.</span></span> <span data-ttu-id="93257-124">Például, válassza ki a Számviteli felügyelő lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="93257-124">For this example, select Accounting supervisor.</span></span>  
4. <span data-ttu-id="93257-125">A **Szerepkörhöz rendelt felhasználók** menüben válassza ki a **Felhasználók manuális hozzárendelését/kizárását**.</span><span class="sxs-lookup"><span data-stu-id="93257-125">In the **Users assigned to role** menu, select **Manually assign / exclude users**.</span></span>
5. <span data-ttu-id="93257-126">A **Felhasználók szerepkörhöz rendelése vagy kizárása onnan** listában jelölje meg a kiválasztott sorokat.</span><span class="sxs-lookup"><span data-stu-id="93257-126">In the **Assign users to or exclude users from role** list, mark the selected row.</span></span> <span data-ttu-id="93257-127">Felhasználó kiválasztása</span><span class="sxs-lookup"><span data-stu-id="93257-127">Select a user.</span></span>  
6. <span data-ttu-id="93257-128">A **Műveleti ablaktáblán** kattintson a **Kizárás szerepkörből** elemre.</span><span class="sxs-lookup"><span data-stu-id="93257-128">On the **Action pane**, select **Exclude from role**.</span></span>
    
    <span data-ttu-id="93257-129">Kattintson a **Kizárás szerepkörből** lehetőségre a kiválasztott felhasználók szerepkörből történő kizárásához.</span><span class="sxs-lookup"><span data-stu-id="93257-129">Click **Exclude from role** to exclude the selected users from the role.</span></span> <span data-ttu-id="93257-130">A kivételek eltávolításához jelölje ki azokat a felhasználókat, akikre vonatkozóan el szeretné távolítani a kizárásokat, majd ezt követően kattintson az **Állapot visszaállítása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="93257-130">To remove exclusions, select the users that you want to remove exclusions for, and then click **Reset status**.</span></span> <span data-ttu-id="93257-131">Amikor eltávolít egy kizárást a felhasználói állapot visszaállításával, a rendszer ismét automatikusan hozzárendeli a felhasználó szerepkört.</span><span class="sxs-lookup"><span data-stu-id="93257-131">When you remove an exclusion by resetting the user’s status, the user’s role is again assigned automatically.</span></span> <span data-ttu-id="93257-132">Azonban a rendszer a felhasználót nem rendeli hozzá automatikusan a szerepkörhöz és kizárja a szerepkörből, amikor a rendszer visszaállítja az állapotát.</span><span class="sxs-lookup"><span data-stu-id="93257-132">However, the user is not immediately assigned to the role or excluded from the role when you reset the status.</span></span> <span data-ttu-id="93257-133">A rendszer ehelyett a felhasználót vagy hozzárendeli a szerepkörhöz vagy eltávolítja a szerepkörből a következő alkalommal, hogy az automatikus szerepkör-hozzárendelési szabályokat futtassa a rendszer.</span><span class="sxs-lookup"><span data-stu-id="93257-133">Instead, the user is either assigned to the role or removed from the role the next time that the rules for automatic role assignment are run.</span></span>  
