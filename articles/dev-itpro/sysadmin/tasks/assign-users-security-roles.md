--- 
title: "A felhasználók hozzárendelése a biztonsági szerepkörökhöz"
description: "A Microsoft Dynamics 365 for Finance and Operations eléréséhez hozzá kell rendelni a felhasználókat a biztonsági szerepkörökhöz."
author: maertenm
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 0ab51a56c33a84dea9cf945e808fa7bc42d3727c
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="assign-users-to-security-roles"></a><span data-ttu-id="7bb25-103">Felhasználók hozzárendelése a biztonsági szerepkörökhöz</span><span class="sxs-lookup"><span data-stu-id="7bb25-103">Assign users to security roles</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7bb25-104">A Microsoft Dynamics 365 for Finance and Operations eléréséhez hozzá kell rendelni a felhasználókat a biztonsági szerepkörökhöz.</span><span class="sxs-lookup"><span data-stu-id="7bb25-104">To access Microsoft Dynamics 365 for Finance and Operations, users must be assigned to security roles.</span></span> <span data-ttu-id="7bb25-105">Ez az eljárás bemutatja, hogy hogyan lehet hozzárendelni automatikusan a szerepkörökhöz az üzleti adatokon alapuló rendszergazdákat.</span><span class="sxs-lookup"><span data-stu-id="7bb25-105">This procedure explains how system administrators can assign users to roles automatically, based on business data.</span></span> <span data-ttu-id="7bb25-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="7bb25-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="automatically-assign-users-to-roles"></a><span data-ttu-id="7bb25-107">Felhasználók automatikus hozzárendelése a szerepkörökhöz</span><span class="sxs-lookup"><span data-stu-id="7bb25-107">Automatically assign users to roles</span></span>
1. <span data-ttu-id="7bb25-108">Ugorjon a Rendszerfelügyelet > Biztonság > Felhasználók szerepkörökhöz rendelése pontra.</span><span class="sxs-lookup"><span data-stu-id="7bb25-108">Go to System administration > Security > Assign users to roles.</span></span>
2. <span data-ttu-id="7bb25-109">Válassza ki a fastruktúrában a „Számviteli felügyelő” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7bb25-109">In the tree, select 'Accounting supervisor'.</span></span>
    * <span data-ttu-id="7bb25-110">Válassza ki azt a szerepkört, amelyre vonatkozóan konfigurálni kívánja a szabályt.</span><span class="sxs-lookup"><span data-stu-id="7bb25-110">Select the role that you want to configure the rule for.</span></span> <span data-ttu-id="7bb25-111">Ebben a példában válassza ki a Számviteli felügyelő lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7bb25-111">In this example, select Accounting supervisor.</span></span>  
3. <span data-ttu-id="7bb25-112">Kattintson a Szabály hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="7bb25-112">Click Add rule to open the drop dialog.</span></span>
4. <span data-ttu-id="7bb25-113">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="7bb25-113">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="7bb25-114">Válassza ki a lekérdezést ezen szabály használatához.</span><span class="sxs-lookup"><span data-stu-id="7bb25-114">Select the query to use for this rule.</span></span>  
5. <span data-ttu-id="7bb25-115">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="7bb25-115">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="7bb25-116">Kattintson A lekérdezés szerkesztése elemre.</span><span class="sxs-lookup"><span data-stu-id="7bb25-116">Click Edit query.</span></span>
    * <span data-ttu-id="7bb25-117">Igény szerint módosítsa a lekérdezést.</span><span class="sxs-lookup"><span data-stu-id="7bb25-117">Edit the query, as needed.</span></span>  
7. <span data-ttu-id="7bb25-118">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="7bb25-118">Click OK.</span></span>

## <a name="exclude-users-from-automatic-role-assignment"></a><span data-ttu-id="7bb25-119">A felhasználók kizárása az Automatikus szerepkör-hozzárendelésből</span><span class="sxs-lookup"><span data-stu-id="7bb25-119">Exclude users from automatic role assignment</span></span>
1. <span data-ttu-id="7bb25-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7bb25-120">Close the page.</span></span>
2. <span data-ttu-id="7bb25-121">Ugorjon a Rendszerfelügyelet > Biztonság > Felhasználók szerepkörökhöz rendelése pontra.</span><span class="sxs-lookup"><span data-stu-id="7bb25-121">Go to System administration > Security > Assign users to roles.</span></span>
3. <span data-ttu-id="7bb25-122">Válassza ki a fastruktúrában a „Számviteli felügyelő” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7bb25-122">In the tree, select 'Accounting supervisor'.</span></span>
    * <span data-ttu-id="7bb25-123">Szerepkör választása.</span><span class="sxs-lookup"><span data-stu-id="7bb25-123">Select a role.</span></span> <span data-ttu-id="7bb25-124">Például, válassza ki a Számviteli felügyelő lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7bb25-124">For this example, select Accounting supervisor.</span></span>  
4. <span data-ttu-id="7bb25-125">Kattintson a Felhasználók kézi hozzárendelése/kizárása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7bb25-125">Click Manually assign / exclude users.</span></span>
5. <span data-ttu-id="7bb25-126">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="7bb25-126">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="7bb25-127">Felhasználó kiválasztása</span><span class="sxs-lookup"><span data-stu-id="7bb25-127">Select a user.</span></span>  
6. <span data-ttu-id="7bb25-128">Kattintson a Kizárás szerepkörből lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7bb25-128">Click Exclude from role.</span></span>
    * <span data-ttu-id="7bb25-129">Kattintson a Kizárás szerepkörből lehetőségre a kiválasztott felhasználók szerepkörből történő kizárásához.</span><span class="sxs-lookup"><span data-stu-id="7bb25-129">Click Exclude from role to exclude the selected users from the role.</span></span> <span data-ttu-id="7bb25-130">A kivételek eltávolításához jelölje ki azokat a felhasználókat, akikre vonatkozóan el szeretné távolítani a kizárásokat, majd ezt követően kattintson az Állapot visszaállítása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7bb25-130">To remove exclusions, select the users that you want to remove exclusions for, and then click Reset status.</span></span> <span data-ttu-id="7bb25-131">Amikor eltávolít egy kizárást a felhasználói állapot visszaállításával, a rendszer ismét automatikusan hozzárendeli a felhasználó szerepkört.</span><span class="sxs-lookup"><span data-stu-id="7bb25-131">When you remove an exclusion by resetting the user’s status, the user’s role is again assigned automatically.</span></span> <span data-ttu-id="7bb25-132">Azonban a rendszer a felhasználót nem rendeli hozzá automatikusan a szerepkörhöz és kizárja a szerepkörből, amikor a rendszer visszaállítja az állapotát.</span><span class="sxs-lookup"><span data-stu-id="7bb25-132">However, the user is not immediately assigned to the role or excluded from the role when you reset the status.</span></span> <span data-ttu-id="7bb25-133">A rendszer ehelyett a felhasználót vagy hozzárendeli a szerepkörhöz vagy eltávolítja a szerepkörből a következő alkalommal, hogy az automatikus szerepkör-hozzárendelési szabályokat futtassa a rendszer.</span><span class="sxs-lookup"><span data-stu-id="7bb25-133">Instead, the user is either assigned to the role or removed from the role the next time that the rules for automatic role assignment are run.</span></span>  


