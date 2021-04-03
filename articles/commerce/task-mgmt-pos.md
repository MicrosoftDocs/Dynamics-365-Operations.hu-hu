---
title: Feladatkezelés a pénztárban
description: Ez a témakör a Microsoft Dynamics 365 Commerce pénztár (POS) alkalmazásban a feladatok kezelését írja le.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 18ba781795058de6228c712c6a22e59038e96368
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478362"
---
# <a name="task-management-in-pos"></a><span data-ttu-id="45b3e-103">Feladatkezelés a pénztárban</span><span class="sxs-lookup"><span data-stu-id="45b3e-103">Task management in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="45b3e-104">Ez a témakör a Microsoft Dynamics 365 Commerce pénztár (POS) alkalmazásban a feladatok kezelését írja le.</span><span class="sxs-lookup"><span data-stu-id="45b3e-104">This topic describes task management in the Microsoft Dynamics 365 Commerce point of sale (POS) application.</span></span>

<span data-ttu-id="45b3e-105">A Dynamics 365 Commerce pénztár alkalmazásnak vannak olyan kezelési funkcióik, amelyek lehetővé teszik a vezetők és dolgozók számára a feladatok kezelését és a feladat állapotának módosítását.</span><span class="sxs-lookup"><span data-stu-id="45b3e-105">The Dynamics 365 Commerce POS application has task management features that let store managers and workers manage tasks and update task status.</span></span> <span data-ttu-id="45b3e-106">Az üzlet dolgozói a feladatokhoz a pénztárkezdő lapján a **Feladatok** csempéjét kiválasztva vagy a feladatra vonatkozó értesítések kiválasztásával érhetik el a feladatokat.</span><span class="sxs-lookup"><span data-stu-id="45b3e-106">Store workers can access tasks either by selecting the **Tasks** tile on the POS home page or by selecting task notifications.</span></span> <span data-ttu-id="45b3e-107">Alapértelmezés szerint a dolgozók a **Saját feladatok** lapra kerülnek, ahol megtekinthetők azok a feladatok, amelyek hozzájuk vannak rendelve.</span><span class="sxs-lookup"><span data-stu-id="45b3e-107">By default, store workers are taken to the **My tasks** tab, where they can view the tasks that are assigned to them.</span></span> <span data-ttu-id="45b3e-108">Azonban egyszerűen átválthatnak a **Késedelmes feladatok**, **Nyitott feladatok** vagy a **Feladatlista** lapokra.</span><span class="sxs-lookup"><span data-stu-id="45b3e-108">However, they can easily switch to the **Overdue tasks**, **Open tasks**, and **Task lists** tabs.</span></span>

## <a name="task-operations-for-store-managers"></a><span data-ttu-id="45b3e-109">Az üzletvezetők feladatműveletei</span><span class="sxs-lookup"><span data-stu-id="45b3e-109">Task operations for store managers</span></span>

<span data-ttu-id="45b3e-110">Az üzletvezetők a következő feladatműveleteket végezhetik el a pénztár alkalmazásban a parancssáv gombjaival:</span><span class="sxs-lookup"><span data-stu-id="45b3e-110">Store managers can perform the following task operations in the POS application by using the buttons on the command bar:</span></span>

- <span data-ttu-id="45b3e-111">**Hozzárendelés** – A kiválasztott feladatok társítása az üzlet egy dolgozójához.</span><span class="sxs-lookup"><span data-stu-id="45b3e-111">**Assign** – Assign selected tasks to a store worker.</span></span>
- <span data-ttu-id="45b3e-112">**Feladat állapota** – A kijelölt feladatok állapotának módosítása.</span><span class="sxs-lookup"><span data-stu-id="45b3e-112">**Task status** – Change the status of selected tasks.</span></span>
- <span data-ttu-id="45b3e-113">**Szűrés** – Alapértelmezés szerint csak az aktív feladatok jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="45b3e-113">**Filter** – By default, only active tasks are shown.</span></span> <span data-ttu-id="45b3e-114">A szűrők alkalmazásával azonban a vezetők megtekinthetik az összes feladatot, még a már elvégzett vagy visszavont feladatokat is.</span><span class="sxs-lookup"><span data-stu-id="45b3e-114">However, by applying filters, managers can view all tasks, even tasks that have been completed or canceled.</span></span>
- <span data-ttu-id="45b3e-115">**Új feladat** – Feladat létrehozása egy létező feladatlistában, vagy egycélú feladat létrehozása.</span><span class="sxs-lookup"><span data-stu-id="45b3e-115">**New task** – Create a task under an existing task list, or create an single-purpose task.</span></span>

<span data-ttu-id="45b3e-116">Az üzlet dolgozói a következő feladatműveleteket végezhetik el a pénztár alkalmazásban a parancssáv gombjaival:</span><span class="sxs-lookup"><span data-stu-id="45b3e-116">Store workers can perform the following task operations in the POS application by using the buttons on the command bar:</span></span>

- <span data-ttu-id="45b3e-117">**Feladat állapota** – A kijelölt feladatok állapotának módosítása.</span><span class="sxs-lookup"><span data-stu-id="45b3e-117">**Task status** – Change the status of selected tasks.</span></span>
- <span data-ttu-id="45b3e-118">**Szűrés** – Alapértelmezés szerint csak az aktív feladatok jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="45b3e-118">**Filter** – By default, only active tasks are shown.</span></span> <span data-ttu-id="45b3e-119">A szűrők alkalmazásával azonban a dolgozók megtekinthetik az összes feladatot, még a már elvégzett vagy visszavont feladatokat is.</span><span class="sxs-lookup"><span data-stu-id="45b3e-119">However, by applying filters, workers can view all tasks, even tasks that have been completed or canceled.</span></span>

<span data-ttu-id="45b3e-120">A következő ábra a Commerce pénztár alkalmazása **Saját feladatok** lapját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="45b3e-120">The following illustration shows the **My tasks** tab in the Commerce POS application.</span></span>

![A Commerce pénztár alkalmazás Saját feladatok lapja](media/POS-task-management.png)

<span data-ttu-id="45b3e-122">A következő ábrán a **Feladatlisták** lap látható.</span><span class="sxs-lookup"><span data-stu-id="45b3e-122">The following illustration shows the **Task lists** tab.</span></span>

![A Commerce pénztár alkalmazás Feladatlista lapja](media/POS-task-lists-management.png)

## <a name="additional-resources"></a><span data-ttu-id="45b3e-124">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="45b3e-124">Additional resources</span></span>

[<span data-ttu-id="45b3e-125">Feladatkezelés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="45b3e-125">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="45b3e-126">Feladatkezelés konfigurálása</span><span class="sxs-lookup"><span data-stu-id="45b3e-126">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="45b3e-127">Feladatlisták létrehozása és feladatok hozzáadása</span><span class="sxs-lookup"><span data-stu-id="45b3e-127">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="45b3e-128">Feladatlisták hozzárendelése áruházakhoz vagy alkalmazottakhoz</span><span class="sxs-lookup"><span data-stu-id="45b3e-128">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
