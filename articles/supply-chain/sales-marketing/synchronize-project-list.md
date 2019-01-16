---
title: "Projektlista szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service közötti projektszinkronizálásra használhatók."
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.translationtype: HT
ms.sourcegitcommit: 8c6cb481f1a3fe48d329c5936118d8df88a4175b
ms.openlocfilehash: adcb1c1b241ce2b073cd26cf2a8a8d64931c8b0f
ms.contentlocale: hu-hu
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a><span data-ttu-id="2948c-103">Projektlista szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba</span><span class="sxs-lookup"><span data-stu-id="2948c-103">Synchronize project list from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="2948c-104">Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service közötti projektszinkronizálásra használhatók.</span><span class="sxs-lookup"><span data-stu-id="2948c-104">This topic discusses the templates and underlying tasks that are used to synchronize projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="2948c-105">[![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span><span class="sxs-lookup"><span data-stu-id="2948c-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="2948c-106">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="2948c-106">Templates and tasks</span></span>
<span data-ttu-id="2948c-107">A következő sablon és a kapcsolódó feladatok a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service közötti projektszinkronizálás futtatására használhatók.</span><span class="sxs-lookup"><span data-stu-id="2948c-107">The following template and underlying tasks are used to run synchronization of projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="2948c-108">**A sablon neve az adatintegrációban:**</span><span class="sxs-lookup"><span data-stu-id="2948c-108">**Name of the template in Data integration:**</span></span>
- <span data-ttu-id="2948c-109">Projektek (a Finance and Operations megoldásból a Field Service megoldásba)</span><span class="sxs-lookup"><span data-stu-id="2948c-109">Projects (Finance and Operations to Field Service)</span></span>

<span data-ttu-id="2948c-110">**A feladatok nevei az adatintegrációs projektben:**</span><span class="sxs-lookup"><span data-stu-id="2948c-110">**Names of the tasks in the Data integration project:**</span></span>
- <span data-ttu-id="2948c-111">Projektek</span><span class="sxs-lookup"><span data-stu-id="2948c-111">Projects</span></span>

<span data-ttu-id="2948c-112">A következő szinkronizálási feladatok kötelezők, mielőtt a projektlisták szinkronizálása megtörténhetne:</span><span class="sxs-lookup"><span data-stu-id="2948c-112">The following synchronization tasks are required before synchronization of project list can occur:</span></span>
- <span data-ttu-id="2948c-113">Fiókok (a Sales megoldásból a Finance and Operations megoldásba)</span><span class="sxs-lookup"><span data-stu-id="2948c-113">Accounts (Sales to Finance and Operations)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="2948c-114">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="2948c-114">Entity set</span></span>
<span data-ttu-id="2948c-115">Field Service   Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="2948c-115">Field Service   Finance and Operations</span></span>

| <span data-ttu-id="2948c-116">Field Service</span><span class="sxs-lookup"><span data-stu-id="2948c-116">Field Service</span></span>           | <span data-ttu-id="2948c-117">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="2948c-117">Finance and Operations</span></span>  |
|-------------------------|-------------------------|
|<span data-ttu-id="2948c-118">msdynce_externalprojects</span><span class="sxs-lookup"><span data-stu-id="2948c-118">msdynce_externalprojects</span></span> | <span data-ttu-id="2948c-119">Projektek</span><span class="sxs-lookup"><span data-stu-id="2948c-119">Projects</span></span>                |

## <a name="entity-flow"></a><span data-ttu-id="2948c-120">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="2948c-120">Entity flow</span></span>
<span data-ttu-id="2948c-121">A projektek létrehozása a Finance and Operations alkalmazásban történik.</span><span class="sxs-lookup"><span data-stu-id="2948c-121">Projects are created in Finance and Operations.</span></span> <span data-ttu-id="2948c-122">A projektek, amelyek esetében a **Projekttípus** Idő és anyag, a **Projektfokozat** pedig Folyamatban, a Field Service **Külső projekt** entitásába szinkronizálódnak, a következő információkat beleértve: projekt száma, projektnév, projektfokozat és vevői számla adatai.</span><span class="sxs-lookup"><span data-stu-id="2948c-122">Projects with **Project type** Time and material and **Project stage** In process will synchronize to the **External Project** entity in Field Service, including Project number, Project name, Project stage and Customer account information.</span></span> <span data-ttu-id="2948c-123">A **Külső projekt** listát a rendszer a Field Service munkarendelések és a Finance and Operations projektek párosítására használja.</span><span class="sxs-lookup"><span data-stu-id="2948c-123">The list of **External Project** is used to pair Field service Work orders with Finance and Operations projects.</span></span>
<span data-ttu-id="2948c-124">A Külső projekt Field Service CRM megoldás új entitás, amely minden projekt lekérés az Operations megoldásból.</span><span class="sxs-lookup"><span data-stu-id="2948c-124">Field Service CRM solution The External Project is a new entity that gets all the Projects from Operations.</span></span>
<span data-ttu-id="2948c-125">A Külső projekt mezőt hozzáadtuk a munkarendelés entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="2948c-125">The External Project field has been added to the Work Order entity.</span></span> <span data-ttu-id="2948c-126">Ez a mező egy keresés és vásárlás, felcímkézi a Munkarendelést egy projekttel, majd az értékesítési rendelés kapcsolódik egy projekthez az Operations megoldáson belül.</span><span class="sxs-lookup"><span data-stu-id="2948c-126">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Operations.</span></span> <span data-ttu-id="2948c-127">Miután a rendszer állapota Nyitott – folyamatban (690,970,000) magasabb állapba kerül, a külső projekt mezőt a rendszer zárolja, és nem lehet felvenni, törölni vagy módosítani az értéket.</span><span class="sxs-lookup"><span data-stu-id="2948c-127">Ones the System Status changes Open – In Progress(690,970,000) to a higher status the External Project field will be locked and you can't add, remove or change the value.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="2948c-128">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="2948c-128">Prerequisites and mapping setup</span></span>
### <a name="in-finance-and-operations"></a><span data-ttu-id="2948c-129">A Finance and Operations alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="2948c-129">In Finance and Operations</span></span>
<span data-ttu-id="2948c-130">A változáskövetés engedélyezése az adatentitás projektekhez</span><span class="sxs-lookup"><span data-stu-id="2948c-130">Enable change tracking for Data entity Projects</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="2948c-131">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="2948c-131">Template mapping in Data integration</span></span>


### <a name="projects-finance-and-operations-to-field-service-projects"></a><span data-ttu-id="2948c-132">Projektek (a Finance and Operations megoldásból a Field Service megoldásba): Projektek</span><span class="sxs-lookup"><span data-stu-id="2948c-132">Projects (Finance and Operations to Field Service): Projects</span></span>

<span data-ttu-id="2948c-133">[![Sablonleképezés az adatintegrátorban](./media/FSProject1.png)](./media/FSProject1.png)</span><span class="sxs-lookup"><span data-stu-id="2948c-133">[![Template mapping in Data integration](./media/FSProject1.png)](./media/FSProject1.png)</span></span>

