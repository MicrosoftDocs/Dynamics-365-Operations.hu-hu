--- 
title: "Pénzügyi időszakok tömeges lezárása"
description: "Ez az eljárás bemutatja, hogyan helyezhető várakoztatásba, illetve hogyan zárható le véglegesen egy időszak egy időben több jogi személyre vonatkoztatva."
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerCalendar, LedgerPeriodModuleAccessControlUpdate, SysLookupPicklist, LedgerFiscalCalendarPeriodStatus
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: a2988b7ab0837cc9a3e4f1c4eaf3fe6e219fa721
ms.contentlocale: hu-hu
ms.lasthandoff: 09/14/2018

---
# <a name="mass-financial-period-close"></a><span data-ttu-id="229d6-103">Pénzügyi időszakok tömeges lezárása</span><span class="sxs-lookup"><span data-stu-id="229d6-103">Mass financial period close</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="229d6-104">Ez az eljárás bemutatja, hogyan helyezhető várakoztatásba, illetve hogyan zárható le véglegesen egy időszak egy időben több jogi személyre vonatkoztatva.</span><span class="sxs-lookup"><span data-stu-id="229d6-104">This procedure shows how to place a period on hold or permanently close a period or more than one legal entity at a time.</span></span> <span data-ttu-id="229d6-105">Ezenkívül a feladat megmutatja, hogyan lehet bizonyos modulokra korlátozni a felhasználói csoportok könyvelését.</span><span class="sxs-lookup"><span data-stu-id="229d6-105">In addition, the task will show how to restrict user group posting to specific modules.</span></span>

1. <span data-ttu-id="229d6-106">Lépjen a Főkönyv > Időszak lezárása > Főkönyvi naptárak elemre.</span><span class="sxs-lookup"><span data-stu-id="229d6-106">Go to General ledger > Period close > Ledger calendars.</span></span>
    * <span data-ttu-id="229d6-107">Vegye figyelembe, hogy a megjelenített jogi személyek listája a lapon kiválasztott pénzügyi naptár függvénye.</span><span class="sxs-lookup"><span data-stu-id="229d6-107">Note that the list of legal entities displayed is dependent on the fiscal calendar selected on the page.</span></span> <span data-ttu-id="229d6-108">Csak azok a jogi személyek jelennek meg, akik a kijelölt pénzügyi naptárat használják.</span><span class="sxs-lookup"><span data-stu-id="229d6-108">Only legal entities using the selected fiscal calendar will display.</span></span>  
2. <span data-ttu-id="229d6-109">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="229d6-109">Click Edit.</span></span>
3. <span data-ttu-id="229d6-110">Válassza ki azt az időszakot, amelynek az állapotát módosítani szeretné.</span><span class="sxs-lookup"><span data-stu-id="229d6-110">Select the period for which you want to modify the status.</span></span>
4. <span data-ttu-id="229d6-111">Válassza ki a jogi személyeket, amelyeknek az állapotát frissíteni szeretné.</span><span class="sxs-lookup"><span data-stu-id="229d6-111">Select the legal entities for which you want to update the status.</span></span>
    * <span data-ttu-id="229d6-112">Gyorsan kijelölhet minden jogi személyt a rács bal felső oldalán látható pipa kiválasztásával.</span><span class="sxs-lookup"><span data-stu-id="229d6-112">You can quickly select all legal entities  by selecting the check mark on the upper left side of the grid.</span></span>  
5. <span data-ttu-id="229d6-113">A kiválasztott modul könyvelés általi elérésének megadásához jelölje be a Modulelérés frissítése lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="229d6-113">Select Update module access to define the posting access to a selected module.</span></span>
    * <span data-ttu-id="229d6-114">A modul állapota egyesével is frissíthető, ha egyenként szerkeszti a rácsban szereplő rekordokat.</span><span class="sxs-lookup"><span data-stu-id="229d6-114">The module status can also be updated one-by-one by editing the records in the grid.</span></span> <span data-ttu-id="229d6-115">A gomb akkor hasznos, ha több jogi személy rekordjait kívánja gyorsan frissíteni.</span><span class="sxs-lookup"><span data-stu-id="229d6-115">The button is useful when you want to quickly update multiple legal entity records.</span></span>  
6. <span data-ttu-id="229d6-116">A Pályázat modul mezőben válassza ki a modult, amelynek frissíteni kívánja az állapotát.</span><span class="sxs-lookup"><span data-stu-id="229d6-116">In the Application module, select the module that you want to update the status.</span></span> <span data-ttu-id="229d6-117">Kattintson a Kiválasztás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="229d6-117">Click Select.</span></span>
7. <span data-ttu-id="229d6-118">A Hozzáférési szint elemnél válasszon az Összes és az Egyik sem lehetőség, illetve adott felhasználói csoport között.</span><span class="sxs-lookup"><span data-stu-id="229d6-118">In the Access level, select All, None, or a specific user group.</span></span> <span data-ttu-id="229d6-119">Kattintson a Kiválasztás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="229d6-119">Click Select.</span></span>
    * <span data-ttu-id="229d6-120">Az Összes lehetőség jelezi, hogy az összes modulhoz szerkesztési joggal rendelkező felhasználó feladhat, ha az időszak nyitott.</span><span class="sxs-lookup"><span data-stu-id="229d6-120">All indicates all users with edit access to the module can post if the period is open.</span></span> <span data-ttu-id="229d6-121">Az Egyik sem lehetőség azt jelezi, hogy a felhasználók nem adhatnak fel a modulba, ha az időszak nyitott.</span><span class="sxs-lookup"><span data-stu-id="229d6-121">None indicates that users cannot post to the module if the period is open.</span></span> <span data-ttu-id="229d6-122">Egy adott felhasználócsoport lehetőség azt jelzi, hogy csak a csoportba tartozó felhasználók adhatnak fel a modulba, ha az időszak nyitott.</span><span class="sxs-lookup"><span data-stu-id="229d6-122">A specific user group indicates only users in the group are able to post to the module if the period is open.</span></span>  
8. <span data-ttu-id="229d6-123">Kattintson a Módosítás gombra.</span><span class="sxs-lookup"><span data-stu-id="229d6-123">Click Update.</span></span>
9. <span data-ttu-id="229d6-124">Válasszon másik időszakot állapotfrissítésre.</span><span class="sxs-lookup"><span data-stu-id="229d6-124">Select another period to update the status.</span></span>
10. <span data-ttu-id="229d6-125">Válassza ki a jogi személyeket, amelyek időszakállapotát frissíteni szeretné.</span><span class="sxs-lookup"><span data-stu-id="229d6-125">Select the legal entites for which you want to update the period status.</span></span>
11. <span data-ttu-id="229d6-126">Válassza az Időszak állapotának frissítése lehetőséget, és az állapotot állítsa Várakoztatott, Nyitott vagy Véglegesen lezárt értékre.</span><span class="sxs-lookup"><span data-stu-id="229d6-126">Select Update period status and set the status of On hold, Open, or Permanently closed.</span></span>
    * <span data-ttu-id="229d6-127">Nyitott lehetőség jelzi, hogy az időszakba fel lehet adni, ha a felhasználó rendelkezik hozzáféréssel.</span><span class="sxs-lookup"><span data-stu-id="229d6-127">Open indicates the period can be posted to, provided the user has access.</span></span> <span data-ttu-id="229d6-128">A Várakoztatott azt jelenti, hogy az időszak nem adható fel, de az időszak újra megnyitható.</span><span class="sxs-lookup"><span data-stu-id="229d6-128">On hold means the period cannot be posted to, but the period can be reopened.</span></span> <span data-ttu-id="229d6-129">A Véglegesen lezárt azt jelenti, hogy az időszak le van zárva, és többé nem lehet megnyitni.</span><span class="sxs-lookup"><span data-stu-id="229d6-129">Permanently closed means the period is closed and can never be opened.</span></span> <span data-ttu-id="229d6-130">Kiigazítások nem adhatók fel.</span><span class="sxs-lookup"><span data-stu-id="229d6-130">Adjustments cannot be posted.</span></span> <span data-ttu-id="229d6-131">Nem ajánlott véglegesen lezártra állítani egy időszakot, amíg az összes kiigazítás és vizsgálat le nem zárult.</span><span class="sxs-lookup"><span data-stu-id="229d6-131">We do not recommend setting a period to Permanently closed until all adjustments and audits are complete.</span></span>  
12. <span data-ttu-id="229d6-132">Kattintson a Módosítás gombra.</span><span class="sxs-lookup"><span data-stu-id="229d6-132">Click Update.</span></span>


