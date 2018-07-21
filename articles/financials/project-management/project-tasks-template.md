---
title: "Projektfeladatok szinkronizálása a Project Service Automation alkalmazásból"
description: "Ez a témakör azt a sablont és kapcsolódó feladatot mutatja be, mely a projektfeladatok a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Project Service Automation közötti közvetlen szinkronizálásra szolgál."
author: KimANelson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: 399b519ab0da4de405aeb06f3e7f4bf29a6c5cc3
ms.openlocfilehash: 89df0d99d780441ad08cd6bff3e1fd203694eb8e
ms.contentlocale: hu-hu
ms.lasthandoff: 05/30/2018

---

# <a name="synchronize-project-tasks-from-project-service-automation-directly-to-project-activities-in-finance-and-operations"></a><span data-ttu-id="bd9a3-103">Projektfeladatok szinkronizálása a Project Service Automation alkalmazásból a Finance and Operations projekttevékenységeibe</span><span class="sxs-lookup"><span data-stu-id="bd9a3-103">Synchronize project tasks from Project Service Automation directly to project activities in Finance and Operations</span></span>

<span data-ttu-id="bd9a3-104">Ez a témakör azt a sablont és kapcsolódó feladatot mutatja be, mely a projektfeladatok a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Project Service Automation közötti közvetlen szinkronizálásra szolgál.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-104">This topic describes the template and underlying task that is used to synchronize project tasks directly from Microsoft Dynamics 365 for Project Service Automation to Dynamics 365 for Finance and Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="bd9a3-105">Projektfeladatok integrációja, költségtranzakció-kategóriák, munkaóra-becslés, költségbecslések és a funkciók zárolása a Dynamics 365 for Finance and Operations 8.0-ás verziójában érhető el.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-105">Project tasks integration, expense transaction categories, hour estimates, expense estimates, and functionality locking is available in Dynamics 365 for Finance and Operations version 8.0.</span></span>

## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a><span data-ttu-id="bd9a3-106">Adatáramlás a Project Service Automation és a Finance and Operations között</span><span class="sxs-lookup"><span data-stu-id="bd9a3-106">Data flow for Project Service Automation to Finance and Operations</span></span>

<span data-ttu-id="bd9a3-107">A Project Service Automation és Finance and Operations közötti integrációs megoldása az adatintegrációs funkciót használja a Project Service Automation and Finance és Operations példányok közötti szinkronizáláshoz.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-107">The Project Service Automation to Finance and Operations integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance and Operations.</span></span> <span data-ttu-id="bd9a3-108">Az integrációs sablon, amelyek elérhető az adatintegrációs funkcióval lehetővé teszi a projektfeladatok adatainak áramlását a Project Service Automation alkalmazásból a Finance and Operations alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-108">The integration template that is available with the Data integration feature enables the flow of data about project tasks from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="bd9a3-109">A következő ábra bemutatja a Project Service Automation és a Finance and Operations közötti adatszinkronizálást.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-109">The following illustration shows how the data is synchronized between Project Service Automation and Finance and Operations.</span></span>

<span data-ttu-id="bd9a3-110">[![Adatáramlás a Project Service Automation és a Finance and Operations integrációjához](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)</span><span class="sxs-lookup"><span data-stu-id="bd9a3-110">[![Data flow for Project Service Automation integration with Finance and Operations](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)</span></span>

## <a name="template-and-task"></a><span data-ttu-id="bd9a3-111">Sablon és feladat</span><span class="sxs-lookup"><span data-stu-id="bd9a3-111">Template and task</span></span>

<span data-ttu-id="bd9a3-112">A rendelkezésre álló sablon eléréséhez a Microsoft PowerApps Admin Centerben válassza a **Projektek** lehetőséget, majd kattintson a jobb felső sarkában **Új projekt** lehetőségre a nyilvános sablonok kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-112">To access the template, in the Microsoft PowerApps Admin Center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="bd9a3-113">A következő sablon és alapul szolgáló feladat használható az aktuális projektfeladatok szinkronizálásához a Project Service Automation és Finance and Operations között:</span><span class="sxs-lookup"><span data-stu-id="bd9a3-113">The following template and underlying task is used to synchronize project tasks from Project Service Automation to Finance and Operations:</span></span>

<span data-ttu-id="bd9a3-114">-**A sablon neve az adatintegrációban:** Projektfeladatok (PSA to Fin and Ops) -**A feladat neve a projektben:** Projektfeladatok</span><span class="sxs-lookup"><span data-stu-id="bd9a3-114">-**Name of the template in Data integration:** Project tasks (PSA to Fin and Ops) -**Name of the task in the project:** Project tasks</span></span>

<span data-ttu-id="bd9a3-115">Projektfeladatok szinkronizálása előtt szinkronizálnia kell a projektszerződéseket és a projekteket..</span><span class="sxs-lookup"><span data-stu-id="bd9a3-115">Before synchronization of project tasks can occur, you must synchronize project contracts and projects.</span></span>

## <a name="entity-set"></a><span data-ttu-id="bd9a3-116">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="bd9a3-116">Entity set</span></span>

|<span data-ttu-id="bd9a3-117">Projekt szolgáltatásautomatizálása</span><span class="sxs-lookup"><span data-stu-id="bd9a3-117">Project Service Automation</span></span>               | <span data-ttu-id="bd9a3-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bd9a3-118">Finance and Operations</span></span>                |
|-----------------------------------------|---------------------------------------|
| <span data-ttu-id="bd9a3-119">Projektfeladatok</span><span class="sxs-lookup"><span data-stu-id="bd9a3-119">Project Tasks</span></span>                           | <span data-ttu-id="bd9a3-120">Integrációs entitás a projektfeladathoz.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-120">Integration entity for project task.</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="bd9a3-121">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="bd9a3-121">Entity flow</span></span>

<span data-ttu-id="bd9a3-122">Projektfeladatok kezelése a Project Service Automation alkalmazásban történik, majd ezek szinkronizálva lesznek a Finance and Operations alkalmazásba projekttevékenységként.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-122">Project tasks are managed in Project Service Automation, and they are synchronized to Finance and Operations as project activities.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="bd9a3-123">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="bd9a3-123">Prerequisites and mapping setup</span></span>

<span data-ttu-id="bd9a3-124">Projektfeladatok szinkronizálása előtt szinkronizálnia kell a projektszerződéseket és a projekteket..</span><span class="sxs-lookup"><span data-stu-id="bd9a3-124">Before synchronization of project tasks can occur, you must synchronize project contracts and projects.</span></span>

## <a name="power-query"></a><span data-ttu-id="bd9a3-125">Power Query</span><span class="sxs-lookup"><span data-stu-id="bd9a3-125">Power Query</span></span>

<span data-ttu-id="bd9a3-126">Microsoft Power Query-t kell használnia az adatok szűréséhez, ha teljesülnek ezek feltételek:</span><span class="sxs-lookup"><span data-stu-id="bd9a3-126">You must use Microsoft Power Query to filter data if these conditions are met:</span></span>

- <span data-ttu-id="bd9a3-127">Erőforrásspecifikus bejegyzései vannak egy projekttevékenységen belül.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-127">You have resource specific records within a project task.</span></span>

<span data-ttu-id="bd9a3-128">Ha a Power Query-t kell használnia, kövesse az alábbiakat:</span><span class="sxs-lookup"><span data-stu-id="bd9a3-128">If you must use Power Query, follow these guidelines:</span></span>

- <span data-ttu-id="bd9a3-129">A Projektfeladatok (Fin és Ops PSA) sablon rendelkezik egy alapértelmezett szűrővel az erőforrás-specifikus rekordokat egy projektfeladaton belül azáltal, hogy az **IsLineTask** szűrőjét **hamis** értékre állítja.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-129">The Project tasks (PSA to Fin and Ops) template has a default filter to exclude resource specific records from within a project task by setting the filter on the **IsLineTask** to **False**.</span></span> <span data-ttu-id="bd9a3-130">Ha saját sablont hoz létre, hozzá kell adnia ezt a szűrőt.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-130">If you create your own template, you must add this filter.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="bd9a3-131">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="bd9a3-131">Template mapping in Data integration</span></span>

<span data-ttu-id="bd9a3-132">Az alábbi ábrán egy példát mutat a sablonfeladat hozzárendelésekre az Adatintegrációban</span><span class="sxs-lookup"><span data-stu-id="bd9a3-132">The following illustration shows an example of the template task mappings in Data integration.</span></span> <span data-ttu-id="bd9a3-133">A leképezés mutatja, hogy melyik mezőadatok szinkronizálódnak a Project Service Automation – Finance and Operations irányban.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-133">The mapping shows the field information that will be synchronized from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="bd9a3-134">[![Sablon-hozzárendelés](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)</span><span class="sxs-lookup"><span data-stu-id="bd9a3-134">[![Template mapping](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)</span></span>


