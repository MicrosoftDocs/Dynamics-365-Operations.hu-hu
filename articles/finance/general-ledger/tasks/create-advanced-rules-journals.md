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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ea6ca24d27bb5b00bbe31060ce2f7e40bf2fb335
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444054"
---
# <a name="create-advanced-rules-for-journals"></a><span data-ttu-id="298d0-103">Speciális szabályok létrehozása naplók részére</span><span class="sxs-lookup"><span data-stu-id="298d0-103">Create advanced rules for journals</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="298d0-104">Ez az eljárás bemutatja a naplók speciális szabályainak létrehozását.</span><span class="sxs-lookup"><span data-stu-id="298d0-104">This procedure steps through creating advanced rules for journals.</span></span> <span data-ttu-id="298d0-105">Ide tartozik a napló ellenőrzése és a felhasználók feladási korlátozásainak beállítása.</span><span class="sxs-lookup"><span data-stu-id="298d0-105">This includes setting up journal control and user posting restrictions.</span></span> <span data-ttu-id="298d0-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="298d0-106">This procedure uses the USMF demo data company.</span></span>


## <a name="set-up-journal-control"></a><span data-ttu-id="298d0-107">Napló-ellenőrzés beállítása</span><span class="sxs-lookup"><span data-stu-id="298d0-107">Set up journal control</span></span>
1. <span data-ttu-id="298d0-108">Nyissa meg a **Navigációs ablakban** a **Modulok > Főkönyv > Napló beállítása > Naplónevek** elemet.</span><span class="sxs-lookup"><span data-stu-id="298d0-108">In the **Navigation pane**, go to **Modules > General ledger > Journal setup > Journal names**.</span></span>
2. <span data-ttu-id="298d0-109">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="298d0-109">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="298d0-110">A **Műveleti ablaktáblán** kattintson a **Napló ellenőrzése** elemre.</span><span class="sxs-lookup"><span data-stu-id="298d0-110">On the **Action pane**, click **Journal control**.</span></span>
4. <span data-ttu-id="298d0-111">A **Mely számlatípusok adhatók fel?** gyorslapon kattintson a **Hozzáadás** gombra.</span><span class="sxs-lookup"><span data-stu-id="298d0-111">In the **Which account types can be posted** fastTab, click **Add**.</span></span>
5. <span data-ttu-id="298d0-112">A **Vállalati számlák** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="298d0-112">In the **Company accounts** field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="298d0-113">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="298d0-113">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="298d0-114">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="298d0-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="298d0-115">A **Mely szegmensértékek érvényesek erre a naplóra?** gyorslapon, kattintson a **Hozzáadás** gombra.</span><span class="sxs-lookup"><span data-stu-id="298d0-115">In the **Which segment values are valid for this journal** fastTab, click **Add**.</span></span>
9. <span data-ttu-id="298d0-116">A **Számlastruktúra** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="298d0-116">In the **Account structure** field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="298d0-117">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="298d0-117">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="298d0-118">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="298d0-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="298d0-119">A **Szegmens** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="298d0-119">In the **Segment** field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="298d0-120">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="298d0-120">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="298d0-121">A **Kezdő érték** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="298d0-121">In the **From value** field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="298d0-122">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="298d0-122">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="298d0-123">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="298d0-123">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="298d0-124">A **Záró érték** mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="298d0-124">In the **To value** field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="298d0-125">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="298d0-125">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="298d0-126">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="298d0-126">In the list, click the link in the selected row.</span></span>

## <a name="set-up-posting-restrictions"></a><span data-ttu-id="298d0-127">Feladási korlátozások beállítása</span><span class="sxs-lookup"><span data-stu-id="298d0-127">Set up posting restrictions</span></span>
1. <span data-ttu-id="298d0-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="298d0-128">Close the page.</span></span>
2. <span data-ttu-id="298d0-129">Kattintson a **Feladásra vonatkozó korlátozások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="298d0-129">Click **Posting restrictions**.</span></span>
3. <span data-ttu-id="298d0-130">A **Hogyan szeretné beállítani a feladási korlátozásokat** mezőben válassza a „Felhasználócsoport szerint” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="298d0-130">In the **How do you want to set up posting restrictions** field, select 'By user group'.</span></span>
4. <span data-ttu-id="298d0-131">A fán ellenőrizze „a csoportot, amelynek engedélyezni kívánja a naplónévhez feladást.”.</span><span class="sxs-lookup"><span data-stu-id="298d0-131">In the tree, check 'the group that you want to allow posting for this journal name.'.</span></span>
5. <span data-ttu-id="298d0-132">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="298d0-132">Click **OK**.</span></span>

