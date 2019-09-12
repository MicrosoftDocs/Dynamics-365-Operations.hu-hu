---
title: Új felhasználók létrehozása
description: A felhasználók a szervezet olyan belső alkalmazottai vagy külső vevői és szállítói, akiknek hozzáféréssel kell rendelkezniük a rendszerhez a munkájuk elvégzéséhez.
author: maertenm
manager: AnnBe
ms.date: 07/01/2019
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
ms.openlocfilehash: a542ece226750330262e0c44427e5654fa4f6369
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916484"
---
# <a name="create-new-users"></a><span data-ttu-id="76a02-103">Új felhasználók létrehozása</span><span class="sxs-lookup"><span data-stu-id="76a02-103">Create new users</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="76a02-104">A felhasználók a szervezet olyan belső alkalmazottai vagy külső vevői és szállítói, akiknek hozzáféréssel kell rendelkezniük a rendszerhez a munkájuk elvégzéséhez.</span><span class="sxs-lookup"><span data-stu-id="76a02-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to perform their jobs.</span></span> <span data-ttu-id="76a02-105">A rendszergazdák végrehajthatják ezt az eljárást, amivel felhasználókat adhatnak a rendszerhez.</span><span class="sxs-lookup"><span data-stu-id="76a02-105">System administrators can complete this procedure to add users to the system.</span></span> <span data-ttu-id="76a02-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="76a02-106">The demo data company used to create this procedure is USMF.</span></span> 


## <a name="add-a-new-user"></a><span data-ttu-id="76a02-107">Új felhasználó hozzáadása</span><span class="sxs-lookup"><span data-stu-id="76a02-107">Add a new user</span></span>
1. <span data-ttu-id="76a02-108">Ugorjon a **Navigációs ablaktábla > Modulok > Rendszerfelügyelet > Felhasználók > Felhasználók** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="76a02-108">Go to **Navigation pane > Modules > System administration > Users > Users**.</span></span>
2. <span data-ttu-id="76a02-109">A **Műveleti panelen** kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="76a02-109">On the **Action pane**, click **New**.</span></span>
3. <span data-ttu-id="76a02-110">Írjon be egy értéket a **Felhasználói azonosító** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="76a02-110">In the **User ID** field, type a value.</span></span> <span data-ttu-id="76a02-111">A felhasználó egyedi azonosítójának megadása.</span><span class="sxs-lookup"><span data-stu-id="76a02-111">Enter a unique identifier for the user.</span></span> <span data-ttu-id="76a02-112">A felhasználó azonosítóját kötelező megadni.</span><span class="sxs-lookup"><span data-stu-id="76a02-112">A user ID is required.</span></span>  
4. <span data-ttu-id="76a02-113">Írjon be egy értéket a **Felhasználó neve** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="76a02-113">In the **User name** field, type a value.</span></span> <span data-ttu-id="76a02-114">A felhasználó nevének megadása.</span><span class="sxs-lookup"><span data-stu-id="76a02-114">Enter the user's name.</span></span>  
5. <span data-ttu-id="76a02-115">Írjon be egy értéket a **Tartomány** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="76a02-115">In the **Domain** field, type a value.</span></span> <span data-ttu-id="76a02-116">A felhasználó tartományának megadása.</span><span class="sxs-lookup"><span data-stu-id="76a02-116">Enter the user's domain.</span></span>  
6. <span data-ttu-id="76a02-117">Írjon be egy értéket az **Alias** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="76a02-117">In the **Alias** field, type a value.</span></span> <span data-ttu-id="76a02-118">A felhasználó aliasának megadása.</span><span class="sxs-lookup"><span data-stu-id="76a02-118">Enter the user's alias.</span></span>  
7. <span data-ttu-id="76a02-119">A **Cég** neve mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="76a02-119">In the **Company** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="76a02-120">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="76a02-120">In the list, find and select the desired record.</span></span> 
9. <span data-ttu-id="76a02-121">Kattintson a **Felhasználó szerepkörei** szakasz **Szerepkörök hozzárendelése** elemére.</span><span class="sxs-lookup"><span data-stu-id="76a02-121">In the **User's roles** section, click **Assign roles**.</span></span>
10. <span data-ttu-id="76a02-122">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="76a02-122">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="76a02-123">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="76a02-123">Click **OK**.</span></span>
12. <span data-ttu-id="76a02-124">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="76a02-124">Click **Save**.</span></span>

## <a name="import-users"></a><span data-ttu-id="76a02-125">Felhasználók importálása</span><span class="sxs-lookup"><span data-stu-id="76a02-125">Import users</span></span>
1. <span data-ttu-id="76a02-126">A **Művelet panelen** kattintson a **Felhasználók importálása** elemre.</span><span class="sxs-lookup"><span data-stu-id="76a02-126">On the **Action pane**, click **Import users**.</span></span>
2. <span data-ttu-id="76a02-127">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="76a02-127">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="76a02-128">Kattintson a **Felhasználók importálása** elemre.</span><span class="sxs-lookup"><span data-stu-id="76a02-128">Click **Import users**.</span></span>
4. <span data-ttu-id="76a02-129">Kattintson a **Bezárás** gombra.</span><span class="sxs-lookup"><span data-stu-id="76a02-129">Click **Close**.</span></span>

