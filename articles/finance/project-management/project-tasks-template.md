---
title: Projektfeladatok közvetlen szinkronizálása a Project Service Automation alkalmazásból közvetlenül a Finance and Operations alkalmazásba
description: Ez a témakör bemutatja a sablont és a mögöttes feladatot, amelyek a Dynamics 365 Project Service Automation projektfeladatainak közvetlenül a Microsoft Dynamics 365 Finance szolgáltatásba történő szinkronizálására használatosak.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: 977037f0e2b313ebf05a3e1616d34567f82e82d7
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250392"
---
# <a name="synchronize-project-tasks-directly-from-project-service-automation-to-finance-and-operations"></a><span data-ttu-id="4e708-103">Projektfeladatok közvetlen szinkronizálása a Project Service Automation alkalmazásból közvetlenül a Finance and Operations alkalmazásba</span><span class="sxs-lookup"><span data-stu-id="4e708-103">Synchronize project tasks directly from Project Service Automation to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="4e708-104">Ez a témakör bemutatja a sablont és a mögöttes feladatot, amelyek a Dynamics 365 Project Service Automation projektfeladatainak közvetlenül a Dynamics 365 Finance szolgáltatásba történő szinkronizálására használatosak.</span><span class="sxs-lookup"><span data-stu-id="4e708-104">This topic describes the template and underlying task that are used to synchronize project tasks directly from Dynamics 365 Project Service Automation to Dynamics 365 Finance.</span></span>

> [!NOTE]
> - <span data-ttu-id="4e708-105">Ha a 8.0-ás verzióját használja a projektfeladat integrációja, költségtranzakció-kategóriák, munkaóra-becslés, költségbecslések és a funkciók zárolása funkciókat használhatja.</span><span class="sxs-lookup"><span data-stu-id="4e708-105">Project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking are available in version 8.0.</span></span>
> - <span data-ttu-id="4e708-106">Amennyiben az Enterprise edition 7.3.0-ás verziót használja, a KB 4132657 és KB 4132660 telepítését követően, használhat sablonokat projektfeladatok, kiadási tranzakciókategóriák, becsült órák, becsült kiadások és a tényleges értékek integrálásához, és a funkciók zárolásának beállításához.</span><span class="sxs-lookup"><span data-stu-id="4e708-106">If you're using Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you will be able to use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking.</span></span> <span data-ttu-id="4e708-107">Ha a könyvelési felosztásokat kell visszaállítania, ajánlott a KB 4131710 telepítése is.</span><span class="sxs-lookup"><span data-stu-id="4e708-107">If you must reset the accounting distributions, we recommended that you also install KB 4131710.</span></span>
> - <span data-ttu-id="4e708-108">Tényleges integráció a 8.0.1 vagy újabb verzióiban érhető el.</span><span class="sxs-lookup"><span data-stu-id="4e708-108">Actuals integration is available in version 8.0.1 or later.</span></span>

## <a name="data-flow-for-project-service-automation-to-finance"></a><span data-ttu-id="4e708-109">Adatáramlás a Project Service Automation és a Finance között</span><span class="sxs-lookup"><span data-stu-id="4e708-109">Data flow for Project Service Automation to Finance</span></span>

<span data-ttu-id="4e708-110">A Project Service Automation és a Finance közötti integrációs megoldás az adatintegrációs funkciót használja a Project Service Automation és Finance példányok közötti szinkronizáláshoz.</span><span class="sxs-lookup"><span data-stu-id="4e708-110">The Project Service Automation to Finance integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance.</span></span> <span data-ttu-id="4e708-111">Az integrációs sablon, amelyek elérhető az adatintegrációs funkcióval lehetővé teszi a projektfeladatok adatainak áramlását a Project Service Automation alkalmazásból a Finance alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="4e708-111">The integration template that is available with the Data integration feature enables the flow of data about project tasks from Project Service Automation to Finance.</span></span>

<span data-ttu-id="4e708-112">A következő ábra bemutatja a Project Service Automation és a Finance közötti adatszinkronizálást.</span><span class="sxs-lookup"><span data-stu-id="4e708-112">The following illustration shows how the data is synchronized between Project Service Automation and Finance.</span></span>

<span data-ttu-id="4e708-113">[![Adatáramlás a Project Service Automation és a Finance integrációjához](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)</span><span class="sxs-lookup"><span data-stu-id="4e708-113">[![Data flow for Project Service Automation integration with Finance](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)</span></span>

## <a name="template-and-task"></a><span data-ttu-id="4e708-114">Sablon és feladat</span><span class="sxs-lookup"><span data-stu-id="4e708-114">Template and task</span></span>

<span data-ttu-id="4e708-115">A rendelkezésre álló sablon eléréséhez a Microsoft PowerApps adminisztrációs központban válassza a **Projektek** lehetőséget, majd kattintson a jobb felső sarkában **Új projekt** lehetőségre a nyilvános sablonok kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="4e708-115">To access the template, in the Microsoft PowerApps admin center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="4e708-116">A következő sablon és alapul szolgáló feladat használható az aktuális projektfeladatok szinkronizálásához a Project Service Automation és Finance között:</span><span class="sxs-lookup"><span data-stu-id="4e708-116">The following template and underlying task are used to synchronize project tasks from Project Service Automation to Finance:</span></span>

- <span data-ttu-id="4e708-117">**Sablon neve az adatintegrációban:** Projektfeladatok(PSA to Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="4e708-117">**Name of the template in Data integration:** Project tasks (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="4e708-118">**A feladat neve a projektben:** Projektfeladatok</span><span class="sxs-lookup"><span data-stu-id="4e708-118">**Name of the task in the project:** Project tasks</span></span>

<span data-ttu-id="4e708-119">Projektfeladatok szinkronizálása előtt szinkronizálnia kell a projektszerződéseket és a projekteket..</span><span class="sxs-lookup"><span data-stu-id="4e708-119">Before synchronization of project tasks can occur, you must synchronize project contracts and projects.</span></span>

## <a name="entity-set"></a><span data-ttu-id="4e708-120">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="4e708-120">Entity set</span></span>

| <span data-ttu-id="4e708-121">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="4e708-121">Project Service Automation</span></span> | <span data-ttu-id="4e708-122">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="4e708-122">Finance</span></span>                             |
|----------------------------|-------------------------------------|
| <span data-ttu-id="4e708-123">Projektfeladatok</span><span class="sxs-lookup"><span data-stu-id="4e708-123">Project Tasks</span></span>              | <span data-ttu-id="4e708-124">Integrációs entitás a projektfeladathoz</span><span class="sxs-lookup"><span data-stu-id="4e708-124">Integration entity for project task</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="4e708-125">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="4e708-125">Entity flow</span></span>

<span data-ttu-id="4e708-126">Projektfeladatok kezelése a Project Service Automation alkalmazásban történik, majd ezek szinkronizálva lesznek a Finance alkalmazásba projekttevékenységként.</span><span class="sxs-lookup"><span data-stu-id="4e708-126">Project tasks are managed in Project Service Automation, and they are synchronized to Finance as project activities.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="4e708-127">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="4e708-127">Prerequisites and mapping setup</span></span>

<span data-ttu-id="4e708-128">Projektfeladatok szinkronizálása előtt szinkronizálnia kell a projektszerződéseket és a projekteket..</span><span class="sxs-lookup"><span data-stu-id="4e708-128">Before synchronization of project tasks can occur, you must synchronize project contracts and projects.</span></span>

## <a name="power-query"></a><span data-ttu-id="4e708-129">Power Query</span><span class="sxs-lookup"><span data-stu-id="4e708-129">Power Query</span></span>

<span data-ttu-id="4e708-130">Microsoft Power Query for Excelt kell használnia az adatok szűréséhez, ha teljesül a következő feltétel:</span><span class="sxs-lookup"><span data-stu-id="4e708-130">You must use Microsoft Power Query for Excel to filter data if this condition is met:</span></span>

- <span data-ttu-id="4e708-131">Erőforrásspecifikus bejegyzései vannak egy projekttevékenységen belül.</span><span class="sxs-lookup"><span data-stu-id="4e708-131">You have resource-specific records in a project task.</span></span>

<span data-ttu-id="4e708-132">Ha a Power Query-t kell használnia, kövesse az alábbi útmutatást:</span><span class="sxs-lookup"><span data-stu-id="4e708-132">If you must use Power Query, follow this guideline:</span></span>

- <span data-ttu-id="4e708-133">A Projektfeladatok (Fin és Ops PSA) sablon rendelkezik egy alapértelmezett szűrővel, mely kizárja az erőforrás-specifikus rekordokat egy projektfeladaton belül azáltal, hogy az **IsLineTask** szűrőjét **hamis** értékre állítja.</span><span class="sxs-lookup"><span data-stu-id="4e708-133">The Project tasks (PSA to Fin and Ops) template has a default filter that excludes resource-specific records from a project task by setting the filter on **IsLineTask** to **False**.</span></span> <span data-ttu-id="4e708-134">Ha saját sablont hoz létre, hozzá kell adnia ezt a szűrőt.</span><span class="sxs-lookup"><span data-stu-id="4e708-134">If you create your own template, you must add this filter.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="4e708-135">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="4e708-135">Template mapping in Data integration</span></span>

<span data-ttu-id="4e708-136">Az alábbi ábrán egy példát mutat a sablonfeladat hozzárendelésekre az Adatintegrációban</span><span class="sxs-lookup"><span data-stu-id="4e708-136">The following illustration shows an example of the template task mappings in Data integration.</span></span> <span data-ttu-id="4e708-137">A leképezés mutatja, hogy melyik mezőadatok szinkronizálódnak a Project Service Automation – Finance irányban.</span><span class="sxs-lookup"><span data-stu-id="4e708-137">The mapping shows the field information that will be synchronized from Project Service Automation to Finance.</span></span>

<span data-ttu-id="4e708-138">[![Sablon-hozzárendelés](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)</span><span class="sxs-lookup"><span data-stu-id="4e708-138">[![Template mapping](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)</span></span>
