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
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 89e492ef5030dd28020094152259b615010aa676
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/02/2019
ms.locfileid: "1851311"
---
# <a name="create-new-users"></a><span data-ttu-id="2c8df-103">Új felhasználók létrehozása</span><span class="sxs-lookup"><span data-stu-id="2c8df-103">Create new users</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2c8df-104">A felhasználók a szervezet olyan belső alkalmazottai vagy külső vevői és szállítói, akiknek hozzáféréssel kell rendelkezniük a rendszerhez a munkájuk elvégzéséhez.</span><span class="sxs-lookup"><span data-stu-id="2c8df-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to perform their jobs.</span></span> <span data-ttu-id="2c8df-105">A rendszergazdák végrehajthatják ezt az eljárást, amivel felhasználókat adhatnak a rendszerhez.</span><span class="sxs-lookup"><span data-stu-id="2c8df-105">System administrators can complete this procedure to add users to the system.</span></span> <span data-ttu-id="2c8df-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="2c8df-106">The demo data company used to create this procedure is USMF.</span></span> 


## <a name="add-a-new-user"></a><span data-ttu-id="2c8df-107">Új felhasználó hozzáadása</span><span class="sxs-lookup"><span data-stu-id="2c8df-107">Add a new user</span></span>
1. <span data-ttu-id="2c8df-108">Ugrás a Rendszerfelügyelet > Felhasználók > Felhasználók elemre.</span><span class="sxs-lookup"><span data-stu-id="2c8df-108">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="2c8df-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2c8df-109">Click New.</span></span>
3. <span data-ttu-id="2c8df-110">Írjon be egy értéket a Felhasználói azonosító mezőbe.</span><span class="sxs-lookup"><span data-stu-id="2c8df-110">In the User ID field, type a value.</span></span>
    * <span data-ttu-id="2c8df-111">A felhasználó egyedi azonosítójának megadása.</span><span class="sxs-lookup"><span data-stu-id="2c8df-111">Enter a unique identifier for the user.</span></span> <span data-ttu-id="2c8df-112">A felhasználó azonosítóját kötelező megadni.</span><span class="sxs-lookup"><span data-stu-id="2c8df-112">A user ID is required.</span></span>  
4. <span data-ttu-id="2c8df-113">Írjon be egy értéket a Felhasználó neve mezőbe.</span><span class="sxs-lookup"><span data-stu-id="2c8df-113">In the User name field, type a value.</span></span>
    * <span data-ttu-id="2c8df-114">A felhasználó nevének megadása.</span><span class="sxs-lookup"><span data-stu-id="2c8df-114">Enter the user's name.</span></span>  
5. <span data-ttu-id="2c8df-115">Írjon be egy értéket a Tartomány mezőbe.</span><span class="sxs-lookup"><span data-stu-id="2c8df-115">In the Domain field, type a value.</span></span>
    * <span data-ttu-id="2c8df-116">A felhasználó tartományának megadása.</span><span class="sxs-lookup"><span data-stu-id="2c8df-116">Enter the user's domain.</span></span>  
6. <span data-ttu-id="2c8df-117">Írjon be egy értéket az Alias mezőbe.</span><span class="sxs-lookup"><span data-stu-id="2c8df-117">In the Alias field, type a value.</span></span>
    * <span data-ttu-id="2c8df-118">A felhasználó aliasának megadása.</span><span class="sxs-lookup"><span data-stu-id="2c8df-118">Enter the user's alias.</span></span>  
7. <span data-ttu-id="2c8df-119">A Cég neve mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="2c8df-119">In the Company field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="2c8df-120">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="2c8df-120">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="2c8df-121">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="2c8df-121">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2c8df-122">Válassza ki a felhasználó cégét</span><span class="sxs-lookup"><span data-stu-id="2c8df-122">Select the user's company</span></span>  
10. <span data-ttu-id="2c8df-123">Kattintson a Szerepkörök hozzárendelése elemre.</span><span class="sxs-lookup"><span data-stu-id="2c8df-123">Click Assign roles.</span></span>
11. <span data-ttu-id="2c8df-124">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="2c8df-124">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="2c8df-125">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="2c8df-125">Click OK.</span></span>
13. <span data-ttu-id="2c8df-126">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="2c8df-126">Click Save.</span></span>

## <a name="import-users"></a><span data-ttu-id="2c8df-127">Felhasználók importálása</span><span class="sxs-lookup"><span data-stu-id="2c8df-127">Import users</span></span>
1. <span data-ttu-id="2c8df-128">Kattintson a Felhasználók importálása elemre.</span><span class="sxs-lookup"><span data-stu-id="2c8df-128">Click Import users.</span></span>
2. <span data-ttu-id="2c8df-129">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="2c8df-129">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="2c8df-130">Kattintson a Felhasználók importálása elemre.</span><span class="sxs-lookup"><span data-stu-id="2c8df-130">Click Import users.</span></span>
4. <span data-ttu-id="2c8df-131">Kattintson a Bezárás gombra.</span><span class="sxs-lookup"><span data-stu-id="2c8df-131">Click Close.</span></span>

