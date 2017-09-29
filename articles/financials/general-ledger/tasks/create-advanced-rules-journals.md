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
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 1bb1663b0f5d7e6a550e1ffd2ee2edf3771a13b3
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="create-advanced-rules-for-journals"></a><span data-ttu-id="5c614-103">Speciális szabályok létrehozása naplók részére</span><span class="sxs-lookup"><span data-stu-id="5c614-103">Create advanced rules for journals</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5c614-104">Ez az eljárás bemutatja a naplók speciális szabályainak létrehozását.</span><span class="sxs-lookup"><span data-stu-id="5c614-104">This procedure steps through creating advanced rules for journals.</span></span> <span data-ttu-id="5c614-105">Ide tartozik a napló ellenőrzése és a felhasználók feladási korlátozásainak beállítása.</span><span class="sxs-lookup"><span data-stu-id="5c614-105">This includes setting up journal control and user posting restrictions.</span></span> <span data-ttu-id="5c614-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="5c614-106">This procedure uses the USMF demo data company.</span></span>


## <a name="set-up-journal-control"></a><span data-ttu-id="5c614-107">Napló-ellenőrzés beállítása</span><span class="sxs-lookup"><span data-stu-id="5c614-107">Set up journal control</span></span>
1. <span data-ttu-id="5c614-108">Ugorjon a Főkönyv > Naplóbeállítások > Naplónevek pontra.</span><span class="sxs-lookup"><span data-stu-id="5c614-108">Go to General ledger > Journal setup > Journal names.</span></span>
2. <span data-ttu-id="5c614-109">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="5c614-109">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="5c614-110">Kattintson a Napló ellenőrzése pontra.</span><span class="sxs-lookup"><span data-stu-id="5c614-110">Click Journal control.</span></span>
4. <span data-ttu-id="5c614-111">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5c614-111">Click Add.</span></span>
5. <span data-ttu-id="5c614-112">A Vállalati számlák mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="5c614-112">In the Company accounts field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="5c614-113">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="5c614-113">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="5c614-114">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="5c614-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="5c614-115">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5c614-115">Click Add.</span></span>
9. <span data-ttu-id="5c614-116">A Számlastruktúra mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="5c614-116">In the Account structure field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="5c614-117">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="5c614-117">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="5c614-118">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="5c614-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="5c614-119">A Szegmens mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="5c614-119">In the Segment field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="5c614-120">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="5c614-120">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="5c614-121">A Kezdő érték mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="5c614-121">In the From value field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="5c614-122">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="5c614-122">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="5c614-123">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="5c614-123">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="5c614-124">A Záró érték mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="5c614-124">In the To value field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="5c614-125">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="5c614-125">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="5c614-126">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="5c614-126">In the list, click the link in the selected row.</span></span>

## <a name="set-up-posting-restrictions"></a><span data-ttu-id="5c614-127">Feladási korlátozások beállítása</span><span class="sxs-lookup"><span data-stu-id="5c614-127">Set up posting restrictions</span></span>
1. <span data-ttu-id="5c614-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5c614-128">Close the page.</span></span>
2. <span data-ttu-id="5c614-129">Kattintson a Feladásra vonatkozó korlátozások lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5c614-129">Click Posting restrictions.</span></span>
3. <span data-ttu-id="5c614-130">A Hogyan szeretné beállítani a feladási korlátozásokat pontnál válassza a Felhasználók szerint lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5c614-130">In the How do you want to set up posting restrictions, select By user group.</span></span>
4. <span data-ttu-id="5c614-131">A fán ellenőrizze „a csoportot, amelynek engedélyezni kívánja a naplónévhez feladást.”.</span><span class="sxs-lookup"><span data-stu-id="5c614-131">In the tree, check 'the group that you want to allow posting for this journal name.'.</span></span>
5. <span data-ttu-id="5c614-132">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="5c614-132">Click OK.</span></span>


