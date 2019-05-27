---
title: Felhasználók hozzárendelése a biztonsági szerepkörökhöz
description: A Microsoft Dynamics 365 for Finance and Operations, Enterprise kiadás eléréséhez hozzá kell rendelni a felhasználókat a biztonsági szerepkörökhöz.
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 55cb085bb5170aa4894a2240a12f6ca451b922fb
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556709"
---
# <a name="assign-users-to-security-roles"></a><span data-ttu-id="6d690-103">Felhasználók hozzárendelése a biztonsági szerepkörökhöz</span><span class="sxs-lookup"><span data-stu-id="6d690-103">Assign users to security roles</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6d690-104">A Microsoft Dynamics 365 for Finance and Operations, Enterprise kiadás eléréséhez hozzá kell rendelni a felhasználókat a biztonsági szerepkörökhöz.</span><span class="sxs-lookup"><span data-stu-id="6d690-104">To access Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, users must be assigned to security roles.</span></span> <span data-ttu-id="6d690-105">Ez az eljárás bemutatja, hogy hogyan lehet hozzárendelni automatikusan a szerepkörökhöz az üzleti adatokon alapuló rendszergazdákat.</span><span class="sxs-lookup"><span data-stu-id="6d690-105">This procedure explains how system administrators can assign users to roles automatically, based on business data.</span></span> <span data-ttu-id="6d690-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="6d690-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="automatically-assign-users-to-roles"></a><span data-ttu-id="6d690-107">Felhasználók automatikus hozzárendelése a szerepkörökhöz</span><span class="sxs-lookup"><span data-stu-id="6d690-107">Automatically assign users to roles</span></span>
1. <span data-ttu-id="6d690-108">Ugorjon a Rendszerfelügyelet > Biztonság > Felhasználók szerepkörökhöz rendelése pontra.</span><span class="sxs-lookup"><span data-stu-id="6d690-108">Go to System administration > Security > Assign users to roles.</span></span>
2. <span data-ttu-id="6d690-109">Válassza ki a fastruktúrában a „Számviteli felügyelő” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6d690-109">In the tree, select 'Accounting supervisor'.</span></span>
    * <span data-ttu-id="6d690-110">Válassza ki azt a szerepkört, amelyre vonatkozóan konfigurálni kívánja a szabályt.</span><span class="sxs-lookup"><span data-stu-id="6d690-110">Select the role that you want to configure the rule for.</span></span> <span data-ttu-id="6d690-111">Ebben a példában válassza ki a Számviteli felügyelő lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6d690-111">In this example, select Accounting supervisor.</span></span>  
3. <span data-ttu-id="6d690-112">Kattintson a Szabály hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="6d690-112">Click Add rule to open the drop dialog.</span></span>
4. <span data-ttu-id="6d690-113">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="6d690-113">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="6d690-114">Válassza ki a lekérdezést ezen szabály használatához.</span><span class="sxs-lookup"><span data-stu-id="6d690-114">Select the query to use for this rule.</span></span>  
5. <span data-ttu-id="6d690-115">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="6d690-115">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="6d690-116">Kattintson A lekérdezés szerkesztése elemre.</span><span class="sxs-lookup"><span data-stu-id="6d690-116">Click Edit query.</span></span>
    * <span data-ttu-id="6d690-117">Igény szerint módosítsa a lekérdezést.</span><span class="sxs-lookup"><span data-stu-id="6d690-117">Edit the query, as needed.</span></span>  
7. <span data-ttu-id="6d690-118">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="6d690-118">Click OK.</span></span>

## <a name="exclude-users-from-automatic-role-assignment"></a><span data-ttu-id="6d690-119">A felhasználók kizárása az Automatikus szerepkör-hozzárendelésből</span><span class="sxs-lookup"><span data-stu-id="6d690-119">Exclude users from automatic role assignment</span></span>
1. <span data-ttu-id="6d690-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6d690-120">Close the page.</span></span>
2. <span data-ttu-id="6d690-121">Ugorjon a Rendszerfelügyelet > Biztonság > Felhasználók szerepkörökhöz rendelése pontra.</span><span class="sxs-lookup"><span data-stu-id="6d690-121">Go to System administration > Security > Assign users to roles.</span></span>
3. <span data-ttu-id="6d690-122">Válassza ki a fastruktúrában a „Számviteli felügyelő” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6d690-122">In the tree, select 'Accounting supervisor'.</span></span>
    * <span data-ttu-id="6d690-123">Szerepkör választása.</span><span class="sxs-lookup"><span data-stu-id="6d690-123">Select a role.</span></span> <span data-ttu-id="6d690-124">Például, válassza ki a Számviteli felügyelő lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6d690-124">For this example, select Accounting supervisor.</span></span>  
4. <span data-ttu-id="6d690-125">Kattintson a Felhasználók kézi hozzárendelése/kizárása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6d690-125">Click Manually assign / exclude users.</span></span>
5. <span data-ttu-id="6d690-126">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="6d690-126">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="6d690-127">Felhasználó kiválasztása</span><span class="sxs-lookup"><span data-stu-id="6d690-127">Select a user.</span></span>  
6. <span data-ttu-id="6d690-128">Kattintson a Kizárás szerepkörből lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6d690-128">Click Exclude from role.</span></span>
    * <span data-ttu-id="6d690-129">Kattintson a Kizárás szerepkörből lehetőségre a kiválasztott felhasználók szerepkörből történő kizárásához.</span><span class="sxs-lookup"><span data-stu-id="6d690-129">Click Exclude from role to exclude the selected users from the role.</span></span> <span data-ttu-id="6d690-130">A kivételek eltávolításához jelölje ki azokat a felhasználókat, akikre vonatkozóan el szeretné távolítani a kizárásokat, majd ezt követően kattintson az Állapot visszaállítása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6d690-130">To remove exclusions, select the users that you want to remove exclusions for, and then click Reset status.</span></span> <span data-ttu-id="6d690-131">Amikor eltávolít egy kizárást a felhasználói állapot visszaállításával, a rendszer ismét automatikusan hozzárendeli a felhasználó szerepkört.</span><span class="sxs-lookup"><span data-stu-id="6d690-131">When you remove an exclusion by resetting the user’s status, the user’s role is again assigned automatically.</span></span> <span data-ttu-id="6d690-132">Azonban a rendszer a felhasználót nem rendeli hozzá automatikusan a szerepkörhöz és kizárja a szerepkörből, amikor a rendszer visszaállítja az állapotát.</span><span class="sxs-lookup"><span data-stu-id="6d690-132">However, the user is not immediately assigned to the role or excluded from the role when you reset the status.</span></span> <span data-ttu-id="6d690-133">A rendszer ehelyett a felhasználót vagy hozzárendeli a szerepkörhöz vagy eltávolítja a szerepkörből a következő alkalommal, hogy az automatikus szerepkör-hozzárendelési szabályokat futtassa a rendszer.</span><span class="sxs-lookup"><span data-stu-id="6d690-133">Instead, the user is either assigned to the role or removed from the role the next time that the rules for automatic role assignment are run.</span></span>  

