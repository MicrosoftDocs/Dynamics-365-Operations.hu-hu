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
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: cc685fcd584fe2ab5cd9282e8fbefbd284d5b2a2
ms.sourcegitcommit: 80cbb7d22267aa6a0ae0568d0063fb95556958a5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/11/2020
ms.locfileid: "3036786"
---
# <a name="task-management-in-pos"></a><span data-ttu-id="f5774-103">Feladatkezelés a pénztárban</span><span class="sxs-lookup"><span data-stu-id="f5774-103">Task management in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f5774-104">Ez a témakör a Microsoft Dynamics 365 Commerce pénztár (POS) alkalmazásban a feladatok kezelését írja le.</span><span class="sxs-lookup"><span data-stu-id="f5774-104">This topic describes task management in the Microsoft Dynamics 365 Commerce point of sale (POS) application.</span></span>

## <a name="overview"></a><span data-ttu-id="f5774-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="f5774-105">Overview</span></span>

<span data-ttu-id="f5774-106">A Dynamics 365 Commerce pénztár alkalmazásnak vannak olyan kezelési funkcióik, amelyek lehetővé teszik a vezetők és dolgozók számára a feladatok kezelését és a feladat állapotának módosítását.</span><span class="sxs-lookup"><span data-stu-id="f5774-106">The Dynamics 365 Commerce POS application has task management features that let store managers and workers manage tasks and update task status.</span></span> <span data-ttu-id="f5774-107">Az üzlet dolgozói a feladatokhoz a pénztárkezdő lapján a **Feladatok** csempéjét kiválasztva vagy a feladatra vonatkozó értesítések kiválasztásával érhetik el a feladatokat.</span><span class="sxs-lookup"><span data-stu-id="f5774-107">Store workers can access tasks either by selecting the **Tasks** tile on the POS home page or by selecting task notifications.</span></span> <span data-ttu-id="f5774-108">Alapértelmezés szerint a dolgozók a **Saját feladatok** lapra kerülnek, ahol megtekinthetők azok a feladatok, amelyek hozzájuk vannak rendelve.</span><span class="sxs-lookup"><span data-stu-id="f5774-108">By default, store workers are taken to the **My tasks** tab, where they can view the tasks that are assigned to them.</span></span> <span data-ttu-id="f5774-109">Azonban egyszerűen átválthatnak a **Késedelmes feladatok**, **Nyitott feladatok** vagy a **Feladatlista** lapokra.</span><span class="sxs-lookup"><span data-stu-id="f5774-109">However, they can easily switch to the **Overdue tasks**, **Open tasks**, and **Task lists** tabs.</span></span>

## <a name="task-operations-for-store-managers"></a><span data-ttu-id="f5774-110">Az üzletvezetők feladatműveletei</span><span class="sxs-lookup"><span data-stu-id="f5774-110">Task operations for store managers</span></span>

<span data-ttu-id="f5774-111">Az üzletvezetők a következő feladatműveleteket végezhetik el a pénztár alkalmazásban a parancssáv gombjaival:</span><span class="sxs-lookup"><span data-stu-id="f5774-111">Store managers can perform the following task operations in the POS application by using the buttons on the command bar:</span></span>

- <span data-ttu-id="f5774-112">**Hozzárendelés** – A kiválasztott feladatok társítása az üzlet egy dolgozójához.</span><span class="sxs-lookup"><span data-stu-id="f5774-112">**Assign** – Assign selected tasks to a store worker.</span></span>
- <span data-ttu-id="f5774-113">**Feladat állapota** – A kijelölt feladatok állapotának módosítása.</span><span class="sxs-lookup"><span data-stu-id="f5774-113">**Task status** – Change the status of selected tasks.</span></span>
- <span data-ttu-id="f5774-114">**Szűrés** – Alapértelmezés szerint csak az aktív feladatok jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="f5774-114">**Filter** – By default, only active tasks are shown.</span></span> <span data-ttu-id="f5774-115">A szűrők alkalmazásával azonban a vezetők megtekinthetik az összes feladatot, még a már elvégzett vagy visszavont feladatokat is.</span><span class="sxs-lookup"><span data-stu-id="f5774-115">However, by applying filters, managers can view all tasks, even tasks that have been completed or canceled.</span></span>
- <span data-ttu-id="f5774-116">**Új feladat** – Feladat létrehozása egy létező feladatlistában, vagy egycélú feladat létrehozása.</span><span class="sxs-lookup"><span data-stu-id="f5774-116">**New task** – Create a task under an existing task list, or create an single-purpose task.</span></span>

<span data-ttu-id="f5774-117">Az üzlet dolgozói a következő feladatműveleteket végezhetik el a pénztár alkalmazásban a parancssáv gombjaival:</span><span class="sxs-lookup"><span data-stu-id="f5774-117">Store workers can perform the following task operations in the POS application by using the buttons on the command bar:</span></span>

- <span data-ttu-id="f5774-118">**Feladat állapota** – A kijelölt feladatok állapotának módosítása.</span><span class="sxs-lookup"><span data-stu-id="f5774-118">**Task status** – Change the status of selected tasks.</span></span>
- <span data-ttu-id="f5774-119">**Szűrés** – Alapértelmezés szerint csak az aktív feladatok jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="f5774-119">**Filter** – By default, only active tasks are shown.</span></span> <span data-ttu-id="f5774-120">A szűrők alkalmazásával azonban a dolgozók megtekinthetik az összes feladatot, még a már elvégzett vagy visszavont feladatokat is.</span><span class="sxs-lookup"><span data-stu-id="f5774-120">However, by applying filters, workers can view all tasks, even tasks that have been completed or canceled.</span></span>

<span data-ttu-id="f5774-121">A következő ábra a Commerce pénztár alkalmazása **Saját feladatok** lapját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="f5774-121">The following illustration shows the **My tasks** tab in the Commerce POS application.</span></span>

![A Commerce pénztár alkalmazás Saját feladatok lapja](media/POS-task-management.png)

<span data-ttu-id="f5774-123">A következő ábrán a **Feladatlisták** lap látható.</span><span class="sxs-lookup"><span data-stu-id="f5774-123">The following illustration shows the **Task lists** tab.</span></span>

![A Commerce pénztár alkalmazás Feladatlista lapja](media/POS-task-lists-management.png)

## <a name="additional-resources"></a><span data-ttu-id="f5774-125">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="f5774-125">Additional resources</span></span>

[<span data-ttu-id="f5774-126">Feladatkezelés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="f5774-126">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="f5774-127">Feladatkezelés konfigurálása</span><span class="sxs-lookup"><span data-stu-id="f5774-127">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="f5774-128">Feladatlisták létrehozása és feladatok hozzáadása</span><span class="sxs-lookup"><span data-stu-id="f5774-128">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="f5774-129">Feladatlisták hozzárendelése áruházakhoz vagy alkalmazottakhoz</span><span class="sxs-lookup"><span data-stu-id="f5774-129">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)
