---
title: Új felhasználók létrehozása
description: A felhasználók a szervezet olyan belső alkalmazottai vagy külső vevői és szállítói, akiknek hozzáféréssel kell rendelkezniük a rendszerhez a munkájuk elvégzéséhez.
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 12cf223d262c4e0f2a195e95c83a00fc1a3f07e5
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "361958"
---
# <a name="create-new-users"></a><span data-ttu-id="f3acf-103">Új felhasználók létrehozása</span><span class="sxs-lookup"><span data-stu-id="f3acf-103">Create new users</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f3acf-104">A felhasználók a szervezet olyan belső alkalmazottai vagy külső vevői és szállítói, akiknek hozzáféréssel kell rendelkezniük a rendszerhez a munkájuk elvégzéséhez.</span><span class="sxs-lookup"><span data-stu-id="f3acf-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to perform their jobs.</span></span> <span data-ttu-id="f3acf-105">A rendszergazdák végrehajthatják ezt az eljárást, amivel felhasználókat adhatnak a rendszerhez.</span><span class="sxs-lookup"><span data-stu-id="f3acf-105">System administrators can complete this procedure to add users to the system.</span></span> <span data-ttu-id="f3acf-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="f3acf-106">The demo data company used to create this procedure is USMF.</span></span> 


## <a name="add-a-new-user"></a><span data-ttu-id="f3acf-107">Új felhasználó hozzáadása</span><span class="sxs-lookup"><span data-stu-id="f3acf-107">Add a new user</span></span>
1. <span data-ttu-id="f3acf-108">Ugrás a Rendszerfelügyelet > Felhasználók > Felhasználók elemre.</span><span class="sxs-lookup"><span data-stu-id="f3acf-108">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="f3acf-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f3acf-109">Click New.</span></span>
3. <span data-ttu-id="f3acf-110">Írjon be egy értéket a Felhasználói azonosító mezőbe.</span><span class="sxs-lookup"><span data-stu-id="f3acf-110">In the User ID field, type a value.</span></span>
    * <span data-ttu-id="f3acf-111">A felhasználó egyedi azonosítójának megadása.</span><span class="sxs-lookup"><span data-stu-id="f3acf-111">Enter a unique identifier for the user.</span></span> <span data-ttu-id="f3acf-112">A felhasználó azonosítóját kötelező megadni.</span><span class="sxs-lookup"><span data-stu-id="f3acf-112">A user ID is required.</span></span>  
4. <span data-ttu-id="f3acf-113">Írjon be egy értéket a Felhasználó neve mezőbe.</span><span class="sxs-lookup"><span data-stu-id="f3acf-113">In the User name field, type a value.</span></span>
    * <span data-ttu-id="f3acf-114">A felhasználó nevének megadása.</span><span class="sxs-lookup"><span data-stu-id="f3acf-114">Enter the user's name.</span></span>  
5. <span data-ttu-id="f3acf-115">Írjon be egy értéket a Tartomány mezőbe.</span><span class="sxs-lookup"><span data-stu-id="f3acf-115">In the Domain field, type a value.</span></span>
    * <span data-ttu-id="f3acf-116">A felhasználó tartományának megadása.</span><span class="sxs-lookup"><span data-stu-id="f3acf-116">Enter the user's domain.</span></span>  
6. <span data-ttu-id="f3acf-117">Írjon be egy értéket az Alias mezőbe.</span><span class="sxs-lookup"><span data-stu-id="f3acf-117">In the Alias field, type a value.</span></span>
    * <span data-ttu-id="f3acf-118">A felhasználó aliasának megadása.</span><span class="sxs-lookup"><span data-stu-id="f3acf-118">Enter the user's alias.</span></span>  
7. <span data-ttu-id="f3acf-119">A Cég neve mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="f3acf-119">In the Company field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="f3acf-120">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="f3acf-120">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="f3acf-121">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="f3acf-121">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="f3acf-122">Válassza ki a felhasználó cégét</span><span class="sxs-lookup"><span data-stu-id="f3acf-122">Select the user's company</span></span>  
10. <span data-ttu-id="f3acf-123">Kattintson a Szerepkörök hozzárendelése elemre.</span><span class="sxs-lookup"><span data-stu-id="f3acf-123">Click Assign roles.</span></span>
11. <span data-ttu-id="f3acf-124">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="f3acf-124">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="f3acf-125">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="f3acf-125">Click OK.</span></span>
13. <span data-ttu-id="f3acf-126">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="f3acf-126">Click Save.</span></span>

## <a name="import-users"></a><span data-ttu-id="f3acf-127">Felhasználók importálása</span><span class="sxs-lookup"><span data-stu-id="f3acf-127">Import users</span></span>
1. <span data-ttu-id="f3acf-128">Kattintson a Felhasználók importálása elemre.</span><span class="sxs-lookup"><span data-stu-id="f3acf-128">Click Import users.</span></span>
2. <span data-ttu-id="f3acf-129">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="f3acf-129">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="f3acf-130">Kattintson a Felhasználók importálása elemre.</span><span class="sxs-lookup"><span data-stu-id="f3acf-130">Click Import users.</span></span>
4. <span data-ttu-id="f3acf-131">Kattintson a Bezárás gombra.</span><span class="sxs-lookup"><span data-stu-id="f3acf-131">Click Close.</span></span>

