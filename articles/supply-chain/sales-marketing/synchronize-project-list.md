---
title: Projektlista szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Microsoft Dynamics 365 for Finance and Operations projektjeinek a Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.
author: ChristianRytt
manager: AnnBe
ms.date: 01/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: b5aeb4c3925994d7488e8e113e88b9d06ee6b350
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "312508"
---
# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a><span data-ttu-id="b5abb-103">Projektlista szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba</span><span class="sxs-lookup"><span data-stu-id="b5abb-103">Synchronize project list from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="b5abb-104">Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Microsoft Dynamics 365 for Finance and Operations projektjeinek a Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.</span><span class="sxs-lookup"><span data-stu-id="b5abb-104">This topic discusses the templates and underlying tasks that are used to synchronize projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="b5abb-105">[![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span><span class="sxs-lookup"><span data-stu-id="b5abb-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="b5abb-106">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="b5abb-106">Templates and tasks</span></span>
<span data-ttu-id="b5abb-107">A következő sablonok és a mögöttes tevékenységek használatosak a projektek szinkronizálásához a Microsoft Dynamics 365 for Finance and Operations alkalmazásból a Microsoft Dynamics 365 for Field Service alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="b5abb-107">The following template and underlying tasks are used to run synchronization of projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="b5abb-108">**Sablon az adatintegrációban**</span><span class="sxs-lookup"><span data-stu-id="b5abb-108">**Template in Data integration**</span></span>
- <span data-ttu-id="b5abb-109">Projektek (a Finance and Operations megoldásból a Field Service megoldásba)</span><span class="sxs-lookup"><span data-stu-id="b5abb-109">Projects (Finance and Operations to Field Service)</span></span>

<span data-ttu-id="b5abb-110">**Feladat az adatintegrációs projektben**</span><span class="sxs-lookup"><span data-stu-id="b5abb-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="b5abb-111">Projektek</span><span class="sxs-lookup"><span data-stu-id="b5abb-111">Projects</span></span>

<span data-ttu-id="b5abb-112">A következő szinkronizálási feladatok kötelezők, mielőtt a projektlisták szinkronizálása megtörténhetne:</span><span class="sxs-lookup"><span data-stu-id="b5abb-112">The following synchronization tasks are required before synchronization of project list can occur:</span></span>
- <span data-ttu-id="b5abb-113">Fiókok (a Sales megoldásból a Finance and Operations megoldásba)</span><span class="sxs-lookup"><span data-stu-id="b5abb-113">Accounts (Sales to Finance and Operations)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="b5abb-114">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="b5abb-114">Entity set</span></span>
| <span data-ttu-id="b5abb-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="b5abb-115">Field Service</span></span>           | <span data-ttu-id="b5abb-116">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b5abb-116">Finance and Operations</span></span>  |
|-------------------------|-------------------------|
|<span data-ttu-id="b5abb-117">msdynce_externalprojects</span><span class="sxs-lookup"><span data-stu-id="b5abb-117">msdynce_externalprojects</span></span> | <span data-ttu-id="b5abb-118">Projektek</span><span class="sxs-lookup"><span data-stu-id="b5abb-118">Projects</span></span>                |

## <a name="entity-flow"></a><span data-ttu-id="b5abb-119">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="b5abb-119">Entity flow</span></span>
<span data-ttu-id="b5abb-120">A projektek létrehozása a Finance and Operations alkalmazásban történik.</span><span class="sxs-lookup"><span data-stu-id="b5abb-120">Projects are created in Finance and Operations.</span></span> <span data-ttu-id="b5abb-121">A projektek, amelyek esetében a **Projekttípus** **Idő és anyag**, a **Projektfokozat** pedig **Folyamatban**, a Field Service **Külső projekt** entitásába szinkronizálódnak, a következő információkat beleértve: projekt száma, projektnév, projektfokozat és vevői számla adatai.</span><span class="sxs-lookup"><span data-stu-id="b5abb-121">Projects with **Project type** set to **Time and material** and **Project stage** set to **In process** will synchronize to the **External Project** entity in Field Service, including Project number, Project name, Project stage, and Customer account information.</span></span> <span data-ttu-id="b5abb-122">A **Külső projekt** listát a rendszer a Field Service munkarendelések és a Finance and Operations projektek párosítására használja.</span><span class="sxs-lookup"><span data-stu-id="b5abb-122">The **External Project** list is used to pair Field service work orders with Finance and Operations projects.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="b5abb-123">Field Service CRM megoldás</span><span class="sxs-lookup"><span data-stu-id="b5abb-123">Field Service CRM solution</span></span>
<span data-ttu-id="b5abb-124">A **Külső projekt** entitás lekér minden projektet a Finance and Operations rendszerből.</span><span class="sxs-lookup"><span data-stu-id="b5abb-124">The **External Project** entity gets all the projects from Finance and Operations.</span></span> <span data-ttu-id="b5abb-125">A **Külső projekt** mezőt hozzáadtuk a **Munkarendelés** entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="b5abb-125">The **External Project** field has been added to the **Work Order** entity.</span></span> <span data-ttu-id="b5abb-126">Ez a mező egy keresőmező felcímkézi a munkarendelést egy projekttel, majd az értékesítési rendelés kapcsolódik egy projekthez a Finance and Operations megoldáson belül.</span><span class="sxs-lookup"><span data-stu-id="b5abb-126">This is a lookup field, so by tagging your work order with a project, the sales order will be connected to a project within Finance and Operations.</span></span> <span data-ttu-id="b5abb-127">Miután a **Rendszer állapota** **Nyitott – folyamatban (690,970,000)** állapotból magasabb állapba kerül, a **Külső projekt** mezőt a rendszer zárolja, és a továbbiakban nem lehet felvenni, törölni vagy módosítani az értéket.</span><span class="sxs-lookup"><span data-stu-id="b5abb-127">After the **System Status** changes **Open – In Progress(690,970,000)** to a higher status, the **External Project** field will be locked and you can no longer add, remove, or change the value.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="b5abb-128">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="b5abb-128">Prerequisites and mapping setup</span></span>
### <a name="finance-and-operations"></a><span data-ttu-id="b5abb-129">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b5abb-129">Finance and Operations</span></span>
<span data-ttu-id="b5abb-130">A változáskövetés engedélyezése az Adatentitás projektekhez.</span><span class="sxs-lookup"><span data-stu-id="b5abb-130">Enable change tracking for Data entity projects.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="b5abb-131">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="b5abb-131">Template mapping in Data integration</span></span>


### <a name="projects-finance-and-operations-to-field-service-projects"></a><span data-ttu-id="b5abb-132">Projektek (a Finance and Operations megoldásból a Field Service megoldásba): Projektek</span><span class="sxs-lookup"><span data-stu-id="b5abb-132">Projects (Finance and Operations to Field Service): Projects</span></span>

<span data-ttu-id="b5abb-133">[![Sablonleképezés az adatintegrátorban](./media/FSProject1.png)](./media/FSProject1.png)</span><span class="sxs-lookup"><span data-stu-id="b5abb-133">[![Template mapping in Data integration](./media/FSProject1.png)](./media/FSProject1.png)</span></span>
