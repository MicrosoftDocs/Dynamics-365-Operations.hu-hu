---
title: Egy munkafolyamat munkatételeinek delegálása
description: Ha azt tervezi, hogy távol lesz a munkahelyétől, vagy valamilyen más okból nem tud elvégezni egy adott munkaelemet, a munkaelemeket más felhasználóknak delegálhatja, illetve hozzárendelheti a felhasználókhoz.
author: jasongre
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f85a1318822ceaf829134bf2eb3581e350d5bea4
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "346249"
---
# <a name="delegate-work-items-in-a-workflow"></a><span data-ttu-id="27bf7-103">Egy munkafolyamat munkatételeinek delegálása</span><span class="sxs-lookup"><span data-stu-id="27bf7-103">Delegate work items in a workflow</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="27bf7-104">Ha azt tervezi, hogy távol lesz a munkahelyétől, vagy valamilyen más okból nem tud elvégezni egy adott munkaelemet, a munkaelemeket más felhasználóknak delegálhatja, illetve hozzárendelheti a felhasználókhoz.</span><span class="sxs-lookup"><span data-stu-id="27bf7-104">If you plan to be out of the office or otherwise unavailable to act on work items, you can delegate, or reassign, your work items to other users.</span></span> <span data-ttu-id="27bf7-105">Az eljárás segítségével beállíthatja a rendszert arra, hogy automatikusan delegálja az Ön munkaelemeit egy másik felhasználónak.</span><span class="sxs-lookup"><span data-stu-id="27bf7-105">This procedure helps you configure the system to automatically delegate your work items to another user.</span></span>



<span data-ttu-id="27bf7-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="27bf7-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-automatic-delegation"></a><span data-ttu-id="27bf7-107">Automatikus delegálás beállítása</span><span class="sxs-lookup"><span data-stu-id="27bf7-107">Set up automatic delegation</span></span>
1. <span data-ttu-id="27bf7-108">Ugrás a Közös > Beállítás > Felhasználói beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="27bf7-108">Go to Common > Setup > User options.</span></span>
2. <span data-ttu-id="27bf7-109">Kattintson a Munkafolyamat fülre.</span><span class="sxs-lookup"><span data-stu-id="27bf7-109">Click the Workflow tab.</span></span>
    * <span data-ttu-id="27bf7-110">Győződjön meg arról, hogy a Delegálás terület ki legyen bontva.</span><span class="sxs-lookup"><span data-stu-id="27bf7-110">Make sure the Delegation section is expanded.</span></span>    <span data-ttu-id="27bf7-111">Annak a konfigurálásához, hogy a rendszer automatikusan delegálja az Ön munkaelemeit más felhasználóknak, delegálási szabályok kell létrehoznia, amelyek megadják, hogy mikor kell bizonyos típusú munkatételeket delegálni.</span><span class="sxs-lookup"><span data-stu-id="27bf7-111">To configure the system to automatically delegate your work items to other users, you must create delegation rules, which specify when certain types of work items are delegated.</span></span> <span data-ttu-id="27bf7-112">Delegálási szabály létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="27bf7-112">Follow these steps to create a delegation rule.</span></span>  
3. <span data-ttu-id="27bf7-113">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="27bf7-113">Click Add.</span></span>
4. <span data-ttu-id="27bf7-114">A Hatókör mezőben válasszon egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="27bf7-114">In the Scope field, select an option.</span></span>
    * <span data-ttu-id="27bf7-115">Mind – Az Önhöz rendelt összes munkaelem delegálása.</span><span class="sxs-lookup"><span data-stu-id="27bf7-115">All – Delegate all work items that are assigned to you.</span></span>    <span data-ttu-id="27bf7-116">Modul – Csak azoknak a munkaelemeknek a delegálása, amelyek adott típusú munkafolyamathoz kapcsolódnak.</span><span class="sxs-lookup"><span data-stu-id="27bf7-116">Module – Delegate only the work items that are related to a specific type of workflow.</span></span> <span data-ttu-id="27bf7-117">Ha ezt a lehetőséget választja, a Név mezőben ki kell választania a munkafolyamat típusát.</span><span class="sxs-lookup"><span data-stu-id="27bf7-117">If you select this option, you must select the type of workflow in the Name field.</span></span>    <span data-ttu-id="27bf7-118">Munkafolyamat – Csak azoknak a munkaelemeknek a delegálása, amelyek adott munkafolyamathoz kapcsolódnak.</span><span class="sxs-lookup"><span data-stu-id="27bf7-118">Workflow – Delegate only the work items that are related to a specific workflow.</span></span> <span data-ttu-id="27bf7-119">Ha ezt a lehetőséget választja, a Név mezőben ki kell választania a munkafolyamatot.</span><span class="sxs-lookup"><span data-stu-id="27bf7-119">If you select this option, you must select the workflow in the Name field.</span></span>  
5. <span data-ttu-id="27bf7-120">A Delegálás mezőben jelölje ki azt a felhasználót, akihez a munkatételeket delegálni szeretné.</span><span class="sxs-lookup"><span data-stu-id="27bf7-120">In the Delegate field, select the user to delegate the work items to.</span></span>
    * <span data-ttu-id="27bf7-121">A Kezdő dátum/idő és a Záró dátum/idő mezők használatával adja meg, mikor szeretné, hogy automatikusan megtörténjen a munkatételek delegálása.</span><span class="sxs-lookup"><span data-stu-id="27bf7-121">Use the Start date/time and End date/time fields to specify when you want the work items to be automatically delegated.</span></span>  
6. <span data-ttu-id="27bf7-122">A Kezdő dátum/idő mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="27bf7-122">In the Start date/time field, enter a date and time.</span></span>
7. <span data-ttu-id="27bf7-123">A Záró dátum/idő mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="27bf7-123">In the End date/time field, enter a date and time.</span></span>
8. <span data-ttu-id="27bf7-124">A delegálási szabály aktiválásához jelölje be az Engedélyezett jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="27bf7-124">Select the Enabled check box to activate the delegation rule.</span></span>
    * <span data-ttu-id="27bf7-125">Ha hatókörként a modult választotta, ki kell választania a modult a Név mezőben.</span><span class="sxs-lookup"><span data-stu-id="27bf7-125">If you selected Module as the Scope, then you must select the module in the Name field.</span></span>    <span data-ttu-id="27bf7-126">Ha hatókörként a munkafolyamatot választotta, ki kell választania a konkrét munkafolyamatot a Név mezőben.</span><span class="sxs-lookup"><span data-stu-id="27bf7-126">If you selected Workflow as the Scope, then you must select the specific workflow to delegate in the Name field.</span></span>  
9. <span data-ttu-id="27bf7-127">A Megjegyzés mezőben adjon meg egy megjegyzést, amely leírja, miért delegálja a munkatételeket.</span><span class="sxs-lookup"><span data-stu-id="27bf7-127">In the Comment field, enter a comment that explains why you are delegating the work items.</span></span>

