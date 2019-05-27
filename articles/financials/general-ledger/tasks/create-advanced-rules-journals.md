---
title: Speciális szabályok létrehozása naplók részére
description: Ez az eljárás bemutatja a naplók speciális szabályainak létrehozását.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalControl, CompanyLookup, LedgerJournalPostControl
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e3fc764a6fa92a050084ae610a11acac46995d2a
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1553107"
---
# <a name="create-advanced-rules-for-journals"></a><span data-ttu-id="b4b14-103">Speciális szabályok létrehozása naplók részére</span><span class="sxs-lookup"><span data-stu-id="b4b14-103">Create advanced rules for journals</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b4b14-104">Ez az eljárás bemutatja a naplók speciális szabályainak létrehozását.</span><span class="sxs-lookup"><span data-stu-id="b4b14-104">This procedure steps through creating advanced rules for journals.</span></span> <span data-ttu-id="b4b14-105">Ide tartozik a napló ellenőrzése és a felhasználók feladási korlátozásainak beállítása.</span><span class="sxs-lookup"><span data-stu-id="b4b14-105">This includes setting up journal control and user posting restrictions.</span></span> <span data-ttu-id="b4b14-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="b4b14-106">This procedure uses the USMF demo data company.</span></span>


## <a name="set-up-journal-control"></a><span data-ttu-id="b4b14-107">Napló-ellenőrzés beállítása</span><span class="sxs-lookup"><span data-stu-id="b4b14-107">Set up journal control</span></span>
1. <span data-ttu-id="b4b14-108">Ugorjon a Főkönyv > Naplóbeállítások > Naplónevek pontra.</span><span class="sxs-lookup"><span data-stu-id="b4b14-108">Go to General ledger > Journal setup > Journal names.</span></span>
2. <span data-ttu-id="b4b14-109">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="b4b14-109">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="b4b14-110">Kattintson a Napló ellenőrzése pontra.</span><span class="sxs-lookup"><span data-stu-id="b4b14-110">Click Journal control.</span></span>
4. <span data-ttu-id="b4b14-111">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="b4b14-111">Click Add.</span></span>
5. <span data-ttu-id="b4b14-112">A Vállalati számlák mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="b4b14-112">In the Company accounts field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="b4b14-113">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="b4b14-113">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="b4b14-114">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="b4b14-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="b4b14-115">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="b4b14-115">Click Add.</span></span>
9. <span data-ttu-id="b4b14-116">A Számlastruktúra mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="b4b14-116">In the Account structure field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="b4b14-117">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="b4b14-117">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="b4b14-118">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="b4b14-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="b4b14-119">A Szegmens mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="b4b14-119">In the Segment field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="b4b14-120">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="b4b14-120">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="b4b14-121">A Kezdő érték mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="b4b14-121">In the From value field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="b4b14-122">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="b4b14-122">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="b4b14-123">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="b4b14-123">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="b4b14-124">A Záró érték mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="b4b14-124">In the To value field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="b4b14-125">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="b4b14-125">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="b4b14-126">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="b4b14-126">In the list, click the link in the selected row.</span></span>

## <a name="set-up-posting-restrictions"></a><span data-ttu-id="b4b14-127">Feladási korlátozások beállítása</span><span class="sxs-lookup"><span data-stu-id="b4b14-127">Set up posting restrictions</span></span>
1. <span data-ttu-id="b4b14-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b4b14-128">Close the page.</span></span>
2. <span data-ttu-id="b4b14-129">Kattintson a Feladásra vonatkozó korlátozások lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b4b14-129">Click Posting restrictions.</span></span>
3. <span data-ttu-id="b4b14-130">A Hogyan szeretné beállítani a feladási korlátozásokat pontnál válassza a Felhasználók szerint lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b4b14-130">In the How do you want to set up posting restrictions, select By user group.</span></span>
4. <span data-ttu-id="b4b14-131">A fán ellenőrizze „a csoportot, amelynek engedélyezni kívánja a naplónévhez feladást.”.</span><span class="sxs-lookup"><span data-stu-id="b4b14-131">In the tree, check 'the group that you want to allow posting for this journal name.'.</span></span>
5. <span data-ttu-id="b4b14-132">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b4b14-132">Click OK.</span></span>

