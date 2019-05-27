---
title: Projektlista szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Microsoft Dynamics 365 for Finance and Operations projektjeinek a Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
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
ms.openlocfilehash: ea5c188891bb97ba73d2d022e86bbff50897381b
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1525877"
---
# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a><span data-ttu-id="9cc55-103">Projektlista szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba</span><span class="sxs-lookup"><span data-stu-id="9cc55-103">Synchronize project list from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="9cc55-104">Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Microsoft Dynamics 365 for Finance and Operations projektjeinek a Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.</span><span class="sxs-lookup"><span data-stu-id="9cc55-104">This topic discusses the templates and underlying tasks that are used to synchronize projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="9cc55-105">[![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span><span class="sxs-lookup"><span data-stu-id="9cc55-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="9cc55-106">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="9cc55-106">Templates and tasks</span></span>
<span data-ttu-id="9cc55-107">A következő sablonok és a mögöttes tevékenységek használatosak a projektek szinkronizálásához a Microsoft Dynamics 365 for Finance and Operations alkalmazásból a Microsoft Dynamics 365 for Field Service alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="9cc55-107">The following template and underlying tasks are used to run synchronization of projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="9cc55-108">**Sablon az adatintegrációban**</span><span class="sxs-lookup"><span data-stu-id="9cc55-108">**Template in Data integration**</span></span>
- <span data-ttu-id="9cc55-109">Projektek (a Fin and Ops megoldásból a Field Service megoldásba)</span><span class="sxs-lookup"><span data-stu-id="9cc55-109">Projects (Fin and Ops to Field Service)</span></span>

<span data-ttu-id="9cc55-110">**Feladat az adatintegrációs projektben**</span><span class="sxs-lookup"><span data-stu-id="9cc55-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="9cc55-111">Projektek</span><span class="sxs-lookup"><span data-stu-id="9cc55-111">Projects</span></span>

<span data-ttu-id="9cc55-112">A következő szinkronizálási feladatok kötelezők, mielőtt a projektlisták szinkronizálása megtörténhetne:</span><span class="sxs-lookup"><span data-stu-id="9cc55-112">The following synchronization tasks are required before synchronization of project list can occur:</span></span>
- <span data-ttu-id="9cc55-113">Számlák (Sales – Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="9cc55-113">Accounts (Sales to Fin and Ops)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="9cc55-114">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="9cc55-114">Entity set</span></span>
| <span data-ttu-id="9cc55-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="9cc55-115">Field Service</span></span>           | <span data-ttu-id="9cc55-116">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="9cc55-116">Finance and Operations</span></span>  |
|-------------------------|-------------------------|
|<span data-ttu-id="9cc55-117">msdynce_externalprojects</span><span class="sxs-lookup"><span data-stu-id="9cc55-117">msdynce_externalprojects</span></span> | <span data-ttu-id="9cc55-118">Projektek</span><span class="sxs-lookup"><span data-stu-id="9cc55-118">Projects</span></span>                |

## <a name="entity-flow"></a><span data-ttu-id="9cc55-119">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="9cc55-119">Entity flow</span></span>
<span data-ttu-id="9cc55-120">A projektek létrehozása a Finance and Operations alkalmazásban történik.</span><span class="sxs-lookup"><span data-stu-id="9cc55-120">Projects are created in Finance and Operations.</span></span> <span data-ttu-id="9cc55-121">A projektek, amelyek esetében a **Projekttípus** **Idő és anyag**, a **Projektfokozat** pedig **Folyamatban**, a Field Service **Külső projekt** entitásába szinkronizálódnak, a következő információkat beleértve: projekt száma, projektnév, projektfokozat és vevői számla adatai.</span><span class="sxs-lookup"><span data-stu-id="9cc55-121">Projects with **Project type** set to **Time and material** and **Project stage** set to **In process** will synchronize to the **External Project** entity in Field Service, including Project number, Project name, Project stage, and Customer account information.</span></span> <span data-ttu-id="9cc55-122">A **Külső projekt** listát a rendszer a Field Service munkarendelések és a Finance and Operations projektek párosítására használja.</span><span class="sxs-lookup"><span data-stu-id="9cc55-122">The **External Project** list is used to pair Field service work orders with Finance and Operations projects.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="9cc55-123">Field Service CRM megoldás</span><span class="sxs-lookup"><span data-stu-id="9cc55-123">Field Service CRM solution</span></span>
<span data-ttu-id="9cc55-124">A **Külső projekt** entitás lekér minden projektet a Finance and Operations rendszerből.</span><span class="sxs-lookup"><span data-stu-id="9cc55-124">The **External Project** entity gets all the projects from Finance and Operations.</span></span> <span data-ttu-id="9cc55-125">A **Külső projekt** mezőt hozzáadtuk a **Munkarendelés** entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="9cc55-125">The **External Project** field has been added to the **Work Order** entity.</span></span> <span data-ttu-id="9cc55-126">Ez a mező egy keresőmező felcímkézi a munkarendelést egy projekttel, majd az értékesítési rendelés kapcsolódik egy projekthez a Finance and Operations megoldáson belül.</span><span class="sxs-lookup"><span data-stu-id="9cc55-126">This is a lookup field, so by tagging your work order with a project, the sales order will be connected to a project within Finance and Operations.</span></span> <span data-ttu-id="9cc55-127">Miután a **Rendszer állapota** **Nyitott – folyamatban (690,970,000)** állapotból magasabb állapba kerül, a **Külső projekt** mezőt a rendszer zárolja, és a továbbiakban nem lehet felvenni, törölni vagy módosítani az értéket.</span><span class="sxs-lookup"><span data-stu-id="9cc55-127">After the **System Status** changes **Open – In Progress(690,970,000)** to a higher status, the **External Project** field will be locked and you can no longer add, remove, or change the value.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="9cc55-128">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="9cc55-128">Prerequisites and mapping setup</span></span>
### <a name="finance-and-operations"></a><span data-ttu-id="9cc55-129">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="9cc55-129">Finance and Operations</span></span>
<span data-ttu-id="9cc55-130">A változáskövetés engedélyezése az Adatentitás projektekhez.</span><span class="sxs-lookup"><span data-stu-id="9cc55-130">Enable change tracking for Data entity projects.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="9cc55-131">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="9cc55-131">Template mapping in Data integration</span></span>


### <a name="projects-fin-and-ops-to-field-service-projects"></a><span data-ttu-id="9cc55-132">Projektek (a Fin and Ops megoldásból a Field Service megoldásba): Projektek</span><span class="sxs-lookup"><span data-stu-id="9cc55-132">Projects (Fin and Ops to Field Service): Projects</span></span>

<span data-ttu-id="9cc55-133">[![Sablonleképezés az adatintegrátorban](./media/FSProject1.png)](./media/FSProject1.png)</span><span class="sxs-lookup"><span data-stu-id="9cc55-133">[![Template mapping in Data integration](./media/FSProject1.png)](./media/FSProject1.png)</span></span>
