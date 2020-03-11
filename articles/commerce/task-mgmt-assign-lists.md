---
title: Feladatlisták hozzárendelése áruházakhoz vagy alkalmazottakhoz
description: Ez a témakör bemutatja, hogy hogyan lehet feladatlistákat hozzárendelni az üzletekhez vagy munkavállalókhoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 82cec9861b759037f40315fb2e6f36002a0ac059
ms.sourcegitcommit: 80cbb7d22267aa6a0ae0568d0063fb95556958a5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/11/2020
ms.locfileid: "3036809"
---
# <a name="assign-task-lists-to-stores-or-employees"></a><span data-ttu-id="383c6-103">Feladatlisták hozzárendelése áruházakhoz vagy alkalmazottakhoz</span><span class="sxs-lookup"><span data-stu-id="383c6-103">Assign task lists to stores or employees</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="383c6-104">Ez a témakör bemutatja, hogy hogyan lehet feladatlistákat hozzárendelni az üzletekhez vagy munkavállalókhoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="383c6-104">This topic describes how to assign task lists to stores or employees in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="383c6-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="383c6-105">Overview</span></span>

<span data-ttu-id="383c6-106">A Feladatkezelés a Dynamics 365 Commerce alkalmazásban lehetővé teszi egy feladatlista hozzárendelését több üzlethez vagy alkalmazotthoz, illetve üzletekhez és alkalmazottak kombinációjához is.</span><span class="sxs-lookup"><span data-stu-id="383c6-106">Task management in Dynamics 365 Commerce lets you assign a task list to multiple stores or employees, or to a combination of stores and employees.</span></span> <span data-ttu-id="383c6-107">Például egy 20 üzletet kezelő területi vezető a **Felkészülés az ünnepi időszakra** feladatlistáját mind a 20 üzlethez társítani szeretné.</span><span class="sxs-lookup"><span data-stu-id="383c6-107">For example, a regional manager for 20 stores might want to assign the **Holiday season preparation** task list to all 20 stores.</span></span>

## <a name="start-the-task-list-assignment-process"></a><span data-ttu-id="383c6-108">A Feladatlista-hozzárendelési folyamat elindítása</span><span class="sxs-lookup"><span data-stu-id="383c6-108">Start the task list assignment process</span></span>

<span data-ttu-id="383c6-109">A Feladatlista hozzárendelési folyamatának megkezdéséhez hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="383c6-109">To start the process of assigning a task list, follow these steps.</span></span>

1. <span data-ttu-id="383c6-110">Válassza a **Retail és Commerce \> Feladatok kezelése \> Feladatkezelés adminisztrációja** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="383c6-110">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="383c6-111">Válassza ki a hozzárendelni kívánt feladatlistát.</span><span class="sxs-lookup"><span data-stu-id="383c6-111">Select the task list to assign.</span></span>
1. <span data-ttu-id="383c6-112">Válassz a **Folyamat indítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="383c6-112">Select **Start process**.</span></span>
1. <span data-ttu-id="383c6-113">A **Folyamat indítása** párbeszédpanelen az **Általános** lapon a **Folyamat neve** mezőbe írjon be egy nevet (például **Keleti területi üzletei**).</span><span class="sxs-lookup"><span data-stu-id="383c6-113">In the **Start process** dialog box, on the **General** tab, in the **Process name** field, enter a name (for example, **East region stores**).</span></span>
1. <span data-ttu-id="383c6-114">Válasszon ki egy dátumot a **Céldátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="383c6-114">In the **Target date** field, specify a date.</span></span>
1. <span data-ttu-id="383c6-115">A Feladatlista üzletekhez történő hozzárendeléséhez az **üzletek** lapon a **Szervezeti hierarchia** szűrője segítségével keresse meg és válassza ki az üzleteket.</span><span class="sxs-lookup"><span data-stu-id="383c6-115">To assign the task list to stores, on the **Stores** tab, use the **Organization hierarchy** filter to find and select the stores.</span></span>

    <span data-ttu-id="383c6-116">A Feladatlista alkalmazottakhoz rendeléséhez a **Dolgozók** lapon keresse meg és válassza ki az alkalmazottakat.</span><span class="sxs-lookup"><span data-stu-id="383c6-116">To assign the task list to employees, on the **Workers** tab, find and select the employees.</span></span>

1. <span data-ttu-id="383c6-117">A folyamat az **OK** gombot választva indítható el.</span><span class="sxs-lookup"><span data-stu-id="383c6-117">Select **OK** to start the process.</span></span> <span data-ttu-id="383c6-118">A feladatlista a kiválasztott üzletekhez vagy alkalmazottakhoz van rendelve.</span><span class="sxs-lookup"><span data-stu-id="383c6-118">The tasks list is assigned to the selected stores or employees.</span></span>

<span data-ttu-id="383c6-119">A következő ábra egy példát mutat be az üzletek megtalálására és kiválasztására a **Folyamat indítása** párbeszédpanelen.</span><span class="sxs-lookup"><span data-stu-id="383c6-119">The following illustration shows an example of how to find and select stores in the **Start process** dialog box.</span></span>

![Üzletek keresése és kiválasztása a Folyamat indítása párbeszédpanelen](media/HQ-Assign-Tasks-Lists.png)

## <a name="assign-task-lists-on-a-recurring-basis"></a><span data-ttu-id="383c6-121">Feladatlisták társítása ismétlődő alapon</span><span class="sxs-lookup"><span data-stu-id="383c6-121">Assign task lists on a recurring basis</span></span>

<span data-ttu-id="383c6-122">A kiskereskedőnek néha ismétlődő feladatai is vannak, például a „Csütörtöki zárási ellenőrzőlista” vagy „A hónap első napjának ellenőrzőlistája”.</span><span class="sxs-lookup"><span data-stu-id="383c6-122">Retailer sometimes have recurrent tasks, such as "Thursday closure checklist" or "First day of the month checklist."</span></span> <span data-ttu-id="383c6-123">Ezért előfordulhat, hogy a feladatlistát ismétlődően szeretné hozzárendelni.</span><span class="sxs-lookup"><span data-stu-id="383c6-123">Therefore, they might want to assign the task list on a recurring basis.</span></span>

1. <span data-ttu-id="383c6-124">Válassza a **Retail és Commerce \> Feladatok kezelése \> Feladatkezelés adminisztrációja** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="383c6-124">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="383c6-125">Válassza ki a hozzárendelni kívánt feladatlistát.</span><span class="sxs-lookup"><span data-stu-id="383c6-125">Select the task list to assign.</span></span>
1. <span data-ttu-id="383c6-126">Válassz a **Folyamat indítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="383c6-126">Select **Start process**.</span></span>
1. <span data-ttu-id="383c6-127">A **Folyamat indítása** párbeszédpanelen az **Általános** lapon a **Folyamat neve** mezőbe írjon be egy nevet.</span><span class="sxs-lookup"><span data-stu-id="383c6-127">In the **Start process** dialog box, on the **General** tab, in the **Process name** field, enter a name.</span></span>
1. <span data-ttu-id="383c6-128">Állítsa az **Ismétlődés** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="383c6-128">Set the **Recurrence** option to **Yes**.</span></span>
1. <span data-ttu-id="383c6-129">Írjon be a napok számár az **Ismétlődés céldátumának eltolása napokban** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="383c6-129">In the **Recurrence target date offset in days** field, enter a number of days.</span></span> <span data-ttu-id="383c6-130">Ha például a **4**értéket adja meg, akkor a céldátum az ismétlődés dátuma plusz négy nap.</span><span class="sxs-lookup"><span data-stu-id="383c6-130">For example, if you enter **4**, the target date is the recurrence date plus four days.</span></span>
1. <span data-ttu-id="383c6-131">A **Futtatás a háttérben** lapon válassz az **Ismétlődés** elemet.</span><span class="sxs-lookup"><span data-stu-id="383c6-131">On the **Run in the background** tab, select **Recurrence**.</span></span>
1. <span data-ttu-id="383c6-132">Az **Ismétlődés definiálása** párbeszédpanelen írja be a gyakorisági feltételeket, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="383c6-132">In the **Define recurrence** dialog box, enter the frequency criteria, and then select **OK**.</span></span>

<span data-ttu-id="383c6-133">A következő ábra egy példát mutat be a gyakorisági feltételek megadására az **Ismétlődés definiálása** párbeszédpanelen.</span><span class="sxs-lookup"><span data-stu-id="383c6-133">The following illustration shows an example of how to enter frequency criteria in the **Define recurrence** dialog box.</span></span>

![Gyakorisági feltételek megadása az Ismétlődés definiálása párbeszédpanelen](media/HQ-Assign-Tasks-Lists-Recurrently.png)

## <a name="track-task-list-status"></a><span data-ttu-id="383c6-135">A feladatlista állapotának nyomon követése</span><span class="sxs-lookup"><span data-stu-id="383c6-135">Track task list status</span></span>

<span data-ttu-id="383c6-136">Ha Ön egy területi vezető vagy üzletvezető, akkor lehet, hogy nyomon szeretné követni a több üzlethez vagy alkalmazotthoz rendelt feladatlisták állapotát.</span><span class="sxs-lookup"><span data-stu-id="383c6-136">If you're a regional manager or store manager, you might want to track the status of task lists that have been assigned to multiple stores or employees.</span></span> <span data-ttu-id="383c6-137">Ezután nyomon követheti azokat az üzleteket vagy dolgozókat, akik nem teljesítették a hozzájuk rendelt feladatokat időben.</span><span class="sxs-lookup"><span data-stu-id="383c6-137">You can then follow up with stores or workers that didn't complete their assigned tasks on time.</span></span> <span data-ttu-id="383c6-138">A Commerce háttériroda segítségével megtekintheti a feladatlisták állapotát, áthelyezheti a feladatokat, illetve módosíthatja egy feladat állapotát.</span><span class="sxs-lookup"><span data-stu-id="383c6-138">Commerce back office lets you view the status of task lists, reassign tasks, or change the status of a task.</span></span>

<span data-ttu-id="383c6-139">Ha nyomon szeretné követni a feladatlista állapotát az összes feladathoz, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="383c6-139">To track the task list status for all tasks, follow these steps.</span></span>

1. <span data-ttu-id="383c6-140">Válassza a **Retail és Commerce \> Feladatok kezelése \> Feladatkezelési folyamatok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="383c6-140">Go to **Retail and Commerce \> Task management \> Task management processes**.</span></span>
1. <span data-ttu-id="383c6-141">Válassza a **Minden Feladatlista** lapot, amelyen megtekintheti a különböző üzletekhez társított összes feladatlista állapotát.</span><span class="sxs-lookup"><span data-stu-id="383c6-141">Select the **All task lists** tab to view the status of all task lists that are assigned to various stores.</span></span>

<span data-ttu-id="383c6-142">Ha nyomon szeretné követni a az összes önhöz rendelt feladat feladatlista állapotát az összes feladathoz, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="383c6-142">To track the task list status for all tasks that are assigned to you, follow these steps.</span></span>

1. <span data-ttu-id="383c6-143">Válassza a **Retail és Commerce \> Feladatok kezelése \> Feladatkezelési folyamatok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="383c6-143">Go to **Retail and Commerce \> Task management \> Task management processes**.</span></span>
1. <span data-ttu-id="383c6-144">Válassza a **Saját feladatok** vagy az **Összes feladat** lapot az Önhöz rendelt feladatok állapotának megtekintéséhez vagy frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="383c6-144">Select the **My tasks** or **All tasks** tab to view or update the status of tasks that are assigned to you.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="383c6-145">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="383c6-145">Additional resources</span></span>

[<span data-ttu-id="383c6-146">Feladatkezelés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="383c6-146">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="383c6-147">Feladatkezelés konfigurálása</span><span class="sxs-lookup"><span data-stu-id="383c6-147">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="383c6-148">Feladatlisták létrehozása és feladatok hozzáadása</span><span class="sxs-lookup"><span data-stu-id="383c6-148">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="383c6-149">Feladatkezelés a pénztárban</span><span class="sxs-lookup"><span data-stu-id="383c6-149">Task management in POS</span></span>](task-mgmt-POS.md)
