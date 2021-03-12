---
title: Speciális szabályok létrehozása naplók részére
description: Ez az eljárás bemutatja a naplók speciális szabályainak létrehozását.
author: aprilolson
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalControl, CompanyLookup, LedgerJournalPostControl
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c06855c7a7648c5829b90bc548a7d2e400967698
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4988602"
---
# <a name="create-advanced-rules-for-journals"></a><span data-ttu-id="52a23-103">Speciális szabályok létrehozása naplók részére</span><span class="sxs-lookup"><span data-stu-id="52a23-103">Create advanced rules for journals</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="52a23-104">Ez az eljárás bemutatja a naplók speciális szabályainak létrehozását.</span><span class="sxs-lookup"><span data-stu-id="52a23-104">This procedure steps through creating advanced rules for journals.</span></span> <span data-ttu-id="52a23-105">Ide tartozik a napló ellenőrzése és a felhasználók feladási korlátozásainak beállítása.</span><span class="sxs-lookup"><span data-stu-id="52a23-105">This includes setting up journal control and user posting restrictions.</span></span> <span data-ttu-id="52a23-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="52a23-106">This procedure uses the USMF demo data company.</span></span>


## <a name="set-up-journal-control"></a><span data-ttu-id="52a23-107">Napló-ellenőrzés beállítása</span><span class="sxs-lookup"><span data-stu-id="52a23-107">Set up journal control</span></span>
1. <span data-ttu-id="52a23-108">Nyissa meg a **Navigációs ablakban** a **Modulok > Főkönyv > Napló beállítása > Naplónevek** elemet.</span><span class="sxs-lookup"><span data-stu-id="52a23-108">In the **Navigation pane**, go to **Modules > General ledger > Journal setup > Journal names**.</span></span>
2. <span data-ttu-id="52a23-109">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="52a23-109">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="52a23-110">A **Műveleti ablaktáblán** kattintson a **Napló ellenőrzése** elemre.</span><span class="sxs-lookup"><span data-stu-id="52a23-110">On the **Action pane**, click **Journal control**.</span></span>
4. <span data-ttu-id="52a23-111">A **Mely számlatípusok adhatók fel?** gyorslapon kattintson a **Hozzáadás** gombra.</span><span class="sxs-lookup"><span data-stu-id="52a23-111">In the **Which account types can be posted** fastTab, click **Add**.</span></span>
5. <span data-ttu-id="52a23-112">A **Vállalati számlák** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="52a23-112">In the **Company accounts** field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="52a23-113">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="52a23-113">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="52a23-114">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="52a23-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="52a23-115">A **Mely szegmensértékek érvényesek erre a naplóra?** gyorslapon, kattintson a **Hozzáadás** gombra.</span><span class="sxs-lookup"><span data-stu-id="52a23-115">In the **Which segment values are valid for this journal** fastTab, click **Add**.</span></span>
9. <span data-ttu-id="52a23-116">A **Számlastruktúra** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="52a23-116">In the **Account structure** field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="52a23-117">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="52a23-117">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="52a23-118">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="52a23-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="52a23-119">A **Szegmens** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="52a23-119">In the **Segment** field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="52a23-120">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="52a23-120">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="52a23-121">A **Kezdő érték** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="52a23-121">In the **From value** field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="52a23-122">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="52a23-122">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="52a23-123">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="52a23-123">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="52a23-124">A **Záró érték** mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="52a23-124">In the **To value** field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="52a23-125">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="52a23-125">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="52a23-126">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="52a23-126">In the list, click the link in the selected row.</span></span>

## <a name="set-up-posting-restrictions"></a><span data-ttu-id="52a23-127">Feladási korlátozások beállítása</span><span class="sxs-lookup"><span data-stu-id="52a23-127">Set up posting restrictions</span></span>
1. <span data-ttu-id="52a23-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="52a23-128">Close the page.</span></span>
2. <span data-ttu-id="52a23-129">Kattintson a **Feladásra vonatkozó korlátozások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="52a23-129">Click **Posting restrictions**.</span></span>
3. <span data-ttu-id="52a23-130">A **Hogyan szeretné beállítani a feladási korlátozásokat** mezőben válassza a „Felhasználócsoport szerint” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="52a23-130">In the **How do you want to set up posting restrictions** field, select 'By user group'.</span></span>
4. <span data-ttu-id="52a23-131">A fán ellenőrizze „a csoportot, amelynek engedélyezni kívánja a naplónévhez feladást.”.</span><span class="sxs-lookup"><span data-stu-id="52a23-131">In the tree, check 'the group that you want to allow posting for this journal name.'.</span></span>
5. <span data-ttu-id="52a23-132">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="52a23-132">Click **OK**.</span></span>

