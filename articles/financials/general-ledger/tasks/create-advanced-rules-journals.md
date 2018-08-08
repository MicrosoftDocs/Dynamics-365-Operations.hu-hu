--- 
title: "Speciális szabályok létrehozása naplók részére"
description: "Ez az eljárás bemutatja a naplók speciális szabályainak létrehozását."
author: aprilolson
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: 2c5f63f0ca5859a7d5b93682c7bc43f15df5bda2
ms.contentlocale: hu-hu
ms.lasthandoff: 08/07/2018

---
# <a name="create-advanced-rules-for-journals"></a><span data-ttu-id="4f109-103">Speciális szabályok létrehozása naplók részére</span><span class="sxs-lookup"><span data-stu-id="4f109-103">Create advanced rules for journals</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4f109-104">Ez az eljárás bemutatja a naplók speciális szabályainak létrehozását.</span><span class="sxs-lookup"><span data-stu-id="4f109-104">This procedure steps through creating advanced rules for journals.</span></span> <span data-ttu-id="4f109-105">Ide tartozik a napló ellenőrzése és a felhasználók feladási korlátozásainak beállítása.</span><span class="sxs-lookup"><span data-stu-id="4f109-105">This includes setting up journal control and user posting restrictions.</span></span> <span data-ttu-id="4f109-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="4f109-106">This procedure uses the USMF demo data company.</span></span>


## <a name="set-up-journal-control"></a><span data-ttu-id="4f109-107">Napló-ellenőrzés beállítása</span><span class="sxs-lookup"><span data-stu-id="4f109-107">Set up journal control</span></span>
1. <span data-ttu-id="4f109-108">Ugorjon a Főkönyv > Naplóbeállítások > Naplónevek pontra.</span><span class="sxs-lookup"><span data-stu-id="4f109-108">Go to General ledger > Journal setup > Journal names.</span></span>
2. <span data-ttu-id="4f109-109">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="4f109-109">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="4f109-110">Kattintson a Napló ellenőrzése pontra.</span><span class="sxs-lookup"><span data-stu-id="4f109-110">Click Journal control.</span></span>
4. <span data-ttu-id="4f109-111">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="4f109-111">Click Add.</span></span>
5. <span data-ttu-id="4f109-112">A Vállalati számlák mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="4f109-112">In the Company accounts field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="4f109-113">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="4f109-113">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="4f109-114">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="4f109-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="4f109-115">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="4f109-115">Click Add.</span></span>
9. <span data-ttu-id="4f109-116">A Számlastruktúra mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="4f109-116">In the Account structure field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="4f109-117">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="4f109-117">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="4f109-118">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="4f109-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="4f109-119">A Szegmens mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="4f109-119">In the Segment field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="4f109-120">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="4f109-120">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="4f109-121">A Kezdő érték mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="4f109-121">In the From value field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="4f109-122">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="4f109-122">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="4f109-123">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="4f109-123">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="4f109-124">A Záró érték mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="4f109-124">In the To value field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="4f109-125">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="4f109-125">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="4f109-126">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="4f109-126">In the list, click the link in the selected row.</span></span>

## <a name="set-up-posting-restrictions"></a><span data-ttu-id="4f109-127">Feladási korlátozások beállítása</span><span class="sxs-lookup"><span data-stu-id="4f109-127">Set up posting restrictions</span></span>
1. <span data-ttu-id="4f109-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4f109-128">Close the page.</span></span>
2. <span data-ttu-id="4f109-129">Kattintson a Feladásra vonatkozó korlátozások lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4f109-129">Click Posting restrictions.</span></span>
3. <span data-ttu-id="4f109-130">A Hogyan szeretné beállítani a feladási korlátozásokat pontnál válassza a Felhasználók szerint lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4f109-130">In the How do you want to set up posting restrictions, select By user group.</span></span>
4. <span data-ttu-id="4f109-131">A fán ellenőrizze „a csoportot, amelynek engedélyezni kívánja a naplónévhez feladást.”.</span><span class="sxs-lookup"><span data-stu-id="4f109-131">In the tree, check 'the group that you want to allow posting for this journal name.'.</span></span>
5. <span data-ttu-id="4f109-132">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="4f109-132">Click OK.</span></span>


