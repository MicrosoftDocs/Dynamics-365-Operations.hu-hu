---
title: Egy munkafolyamat munkatételeinek delegálása
description: Ha azt tervezi, hogy távol lesz a munkahelyétől, vagy valamilyen más okból nem tud elvégezni egy adott munkaelemet, a munkaelemeket más felhasználóknak delegálhatja, illetve hozzárendelheti a felhasználókhoz.
author: jasongre
manager: AnnBe
ms.date: 04/09/2019
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
ms.openlocfilehash: feace647d7acef6abf86b13fcb8019c622c55ff6
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1509452"
---
# <a name="delegate-work-items-in-a-workflow"></a><span data-ttu-id="a081f-103">Egy munkafolyamat munkatételeinek delegálása</span><span class="sxs-lookup"><span data-stu-id="a081f-103">Delegate work items in a workflow</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

## <a name="manually-delegate-a-work-item"></a><span data-ttu-id="a081f-104">Munkaelem delegálátsa manuálisan</span><span class="sxs-lookup"><span data-stu-id="a081f-104">Manually delegate a work item</span></span>

<span data-ttu-id="a081f-105">Ha egyetlen munkaelemet szeretne delegálni, válassza a **Delegálás** beállítást a **Munkafolyamat** menüben, majd adja meg a delegálni kívánt felhasználót a megjegyzéssel együtt.</span><span class="sxs-lookup"><span data-stu-id="a081f-105">To delegate an individual work item, select the **Delegate** option in the **Workflow** menu and then enter the user to be delegated to along with a comment.</span></span> <span data-ttu-id="a081f-106">Ez hozzárendeli a munkaelemet újra a felhasználóhoz, így végrehajthatja.</span><span class="sxs-lookup"><span data-stu-id="a081f-106">This will reassign the work item to that user so they can complete it.</span></span>

## <a name="automatically-delegate-work-items"></a><span data-ttu-id="a081f-107">Munkaelem delegálása automatikusan</span><span class="sxs-lookup"><span data-stu-id="a081f-107">Automatically delegate work items</span></span>

<span data-ttu-id="a081f-108">Ha úgy tervezi, hogy nem lesz az irodában vagy más okból nem lesz elérhető a munkaelemek feldolgozáshoz egy bizonyos ideig, automatikusan delegálhatja az új munkaelemeket más felhasználókhoz a **Felhasználói beállítások** oldal segítségével.</span><span class="sxs-lookup"><span data-stu-id="a081f-108">If you plan to be out of the office or otherwise unavailable to act on work items for a period of time, you can automatically delegate new work items to other users using the **User options** page.</span></span>

### <a name="set-up-automatic-delegation"></a><span data-ttu-id="a081f-109">Automatikus delegálás beállítása</span><span class="sxs-lookup"><span data-stu-id="a081f-109">Set up automatic delegation</span></span>
1. <span data-ttu-id="a081f-110">Ugrás a Közös > Beállítás > Felhasználói beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="a081f-110">Go to Common > Setup > User options.</span></span>
2. <span data-ttu-id="a081f-111">Kattintson a Munkafolyamat fülre.</span><span class="sxs-lookup"><span data-stu-id="a081f-111">Click the Workflow tab.</span></span>
    * <span data-ttu-id="a081f-112">Győződjön meg arról, hogy a Delegálás terület ki legyen bontva.</span><span class="sxs-lookup"><span data-stu-id="a081f-112">Make sure the Delegation section is expanded.</span></span>    <span data-ttu-id="a081f-113">Annak a konfigurálásához, hogy a rendszer automatikusan delegálja az Ön munkaelemeit más felhasználóknak, delegálási szabályok kell létrehoznia, amelyek megadják, hogy mikor kell bizonyos típusú munkatételeket delegálni.</span><span class="sxs-lookup"><span data-stu-id="a081f-113">To configure the system to automatically delegate your work items to other users, you must create delegation rules, which specify when certain types of work items are delegated.</span></span> <span data-ttu-id="a081f-114">Delegálási szabály létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a081f-114">Follow these steps to create a delegation rule.</span></span>  
3. <span data-ttu-id="a081f-115">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="a081f-115">Click Add.</span></span>
4. <span data-ttu-id="a081f-116">A Hatókör mezőben válasszon egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a081f-116">In the Scope field, select an option.</span></span>
    * <span data-ttu-id="a081f-117">Mind – Az Önhöz rendelt összes munkaelem delegálása.</span><span class="sxs-lookup"><span data-stu-id="a081f-117">All – Delegate all work items that are assigned to you.</span></span>    <span data-ttu-id="a081f-118">Modul – Csak azoknak a munkaelemeknek a delegálása, amelyek adott típusú munkafolyamathoz kapcsolódnak.</span><span class="sxs-lookup"><span data-stu-id="a081f-118">Module – Delegate only the work items that are related to a specific type of workflow.</span></span> <span data-ttu-id="a081f-119">Ha ezt a lehetőséget választja, a Név mezőben ki kell választania a munkafolyamat típusát.</span><span class="sxs-lookup"><span data-stu-id="a081f-119">If you select this option, you must select the type of workflow in the Name field.</span></span>    <span data-ttu-id="a081f-120">Munkafolyamat – Csak azoknak a munkaelemeknek a delegálása, amelyek adott munkafolyamathoz kapcsolódnak.</span><span class="sxs-lookup"><span data-stu-id="a081f-120">Workflow – Delegate only the work items that are related to a specific workflow.</span></span> <span data-ttu-id="a081f-121">Ha ezt a lehetőséget választja, a Név mezőben ki kell választania a munkafolyamatot.</span><span class="sxs-lookup"><span data-stu-id="a081f-121">If you select this option, you must select the workflow in the Name field.</span></span>  
5. <span data-ttu-id="a081f-122">A Delegálás mezőben jelölje ki azt a felhasználót, akihez a munkatételeket delegálni szeretné.</span><span class="sxs-lookup"><span data-stu-id="a081f-122">In the Delegate field, select the user to delegate the work items to.</span></span>
    * <span data-ttu-id="a081f-123">A Kezdő dátum/idő és a Záró dátum/idő mezők használatával adja meg, mikor szeretné, hogy automatikusan megtörténjen a munkatételek delegálása.</span><span class="sxs-lookup"><span data-stu-id="a081f-123">Use the Start date/time and End date/time fields to specify when you want the work items to be automatically delegated.</span></span>  
6. <span data-ttu-id="a081f-124">A Kezdő dátum/idő mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="a081f-124">In the Start date/time field, enter a date and time.</span></span>
7. <span data-ttu-id="a081f-125">A Záró dátum/idő mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="a081f-125">In the End date/time field, enter a date and time.</span></span>
8. <span data-ttu-id="a081f-126">A delegálási szabály aktiválásához jelölje be az Engedélyezett jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="a081f-126">Select the Enabled check box to activate the delegation rule.</span></span>
    * <span data-ttu-id="a081f-127">Ha hatókörként a modult választotta, ki kell választania a modult a Név mezőben.</span><span class="sxs-lookup"><span data-stu-id="a081f-127">If you selected Module as the Scope, then you must select the module in the Name field.</span></span>    <span data-ttu-id="a081f-128">Ha hatókörként a munkafolyamatot választotta, ki kell választania a konkrét munkafolyamatot a Név mezőben.</span><span class="sxs-lookup"><span data-stu-id="a081f-128">If you selected Workflow as the Scope, then you must select the specific workflow to delegate in the Name field.</span></span>  
9. <span data-ttu-id="a081f-129">A Megjegyzés mezőben adjon meg egy megjegyzést, amely leírja, miért delegálja a munkatételeket.</span><span class="sxs-lookup"><span data-stu-id="a081f-129">In the Comment field, enter a comment that explains why you are delegating the work items.</span></span>

