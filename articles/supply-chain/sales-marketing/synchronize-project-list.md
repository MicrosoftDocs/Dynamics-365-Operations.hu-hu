---
title: Projektlista szinkronizálása a Supply Chain Management alkalmazásból a Field Service alkalmazásba
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Supply Chain Management projektjeinek a Dynamics 365 Field Service szolgáltatásba történő szinkronizálására használatosak.
author: ChristianRytt
manager: tfehr
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: d80fce409ee92973a6134d96ce839b9722980918
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429186"
---
# <a name="synchronize-project-list-from-supply-chain-management-to-field-service"></a><span data-ttu-id="725f8-103">Projektlista szinkronizálása a Supply Chain Management alkalmazásból a Field Service alkalmazásba</span><span class="sxs-lookup"><span data-stu-id="725f8-103">Synchronize project list from Supply Chain Management to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="725f8-104">Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Supply Chain Management projektjeinek a Dynamics 365 Field Service szolgáltatásba történő szinkronizálására használatosak.</span><span class="sxs-lookup"><span data-stu-id="725f8-104">This topic discusses the templates and underlying tasks that are used to synchronize projects from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="725f8-105">[![Üzleti folyamatok szinkronizálása a Supply Chain Management és a Field Service között](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span><span class="sxs-lookup"><span data-stu-id="725f8-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="725f8-106">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="725f8-106">Templates and tasks</span></span>
<span data-ttu-id="725f8-107">A következő sablonokat és alapul szolgáló feladatokat használják a projektszinkronizálás futtatásához a Supply Chain Management és a Field Service között:</span><span class="sxs-lookup"><span data-stu-id="725f8-107">The following template and underlying tasks are used to run synchronization of projects from Supply Chain Management to Field Service.</span></span>

<span data-ttu-id="725f8-108">**Sablon az adatintegrációban**</span><span class="sxs-lookup"><span data-stu-id="725f8-108">**Template in Data integration**</span></span>
- <span data-ttu-id="725f8-109">Projektek (Supply Chain Management és Field Service között)</span><span class="sxs-lookup"><span data-stu-id="725f8-109">Projects (Supply Chain Management to Field Service)</span></span>

<span data-ttu-id="725f8-110">**Feladat az adatintegrációs projektben**</span><span class="sxs-lookup"><span data-stu-id="725f8-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="725f8-111">Projektek</span><span class="sxs-lookup"><span data-stu-id="725f8-111">Projects</span></span>

<span data-ttu-id="725f8-112">A következő szinkronizálási feladatok kötelezők, mielőtt a projektlisták szinkronizálása megtörténhetne:</span><span class="sxs-lookup"><span data-stu-id="725f8-112">The following synchronization tasks are required before synchronization of project list can occur:</span></span>
- <span data-ttu-id="725f8-113">Számlák (Sales és Supply Chain Management között)</span><span class="sxs-lookup"><span data-stu-id="725f8-113">Accounts (Sales to Supply Chain Management)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="725f8-114">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="725f8-114">Entity set</span></span>
| <span data-ttu-id="725f8-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="725f8-115">Field Service</span></span>           | <span data-ttu-id="725f8-116">Ellátásilánc-kezelés</span><span class="sxs-lookup"><span data-stu-id="725f8-116">Supply Chain Management</span></span>  |
|-------------------------|-------------------------|
|<span data-ttu-id="725f8-117">msdynce_externalprojects</span><span class="sxs-lookup"><span data-stu-id="725f8-117">msdynce_externalprojects</span></span> | <span data-ttu-id="725f8-118">Projektek</span><span class="sxs-lookup"><span data-stu-id="725f8-118">Projects</span></span>                |

## <a name="entity-flow"></a><span data-ttu-id="725f8-119">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="725f8-119">Entity flow</span></span>
<span data-ttu-id="725f8-120">A Projekteket a Supply Chain Management szolgáltatásban hozzák létre.</span><span class="sxs-lookup"><span data-stu-id="725f8-120">Projects are created in Supply Chain Management.</span></span> <span data-ttu-id="725f8-121">A projektek, amelyek esetében a **Projekttípus** **Idő és anyag**, a **Projektfokozat** pedig **Folyamatban**, a Field Service **Külső projekt** entitásába szinkronizálódnak, a következő információkat beleértve: projekt száma, projektnév, projektfokozat és vevői számla adatai.</span><span class="sxs-lookup"><span data-stu-id="725f8-121">Projects with **Project type** set to **Time and material** and **Project stage** set to **In process** will synchronize to the **External Project** entity in Field Service, including Project number, Project name, Project stage, and Customer account information.</span></span> <span data-ttu-id="725f8-122">A **Külső projekt** listát a rendszer a Field Service munkarendelések és a Supply Chain Management projektek párosítására használja.</span><span class="sxs-lookup"><span data-stu-id="725f8-122">The **External Project** list is used to pair Field service work orders with Supply Chain Management projects.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="725f8-123">Field Service CRM megoldás</span><span class="sxs-lookup"><span data-stu-id="725f8-123">Field Service CRM solution</span></span>
<span data-ttu-id="725f8-124">A **Külső projekt** entitás lekér minden projektet a Supply Chain Management rendszerből.</span><span class="sxs-lookup"><span data-stu-id="725f8-124">The **External Project** entity gets all the projects from Supply Chain Management.</span></span> <span data-ttu-id="725f8-125">A **Külső projekt** mezőt hozzáadtuk a **Munkarendelés** entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="725f8-125">The **External Project** field has been added to the **Work Order** entity.</span></span> <span data-ttu-id="725f8-126">Ez a mező egy keresőmező felcímkézi a munkarendelést egy projekttel, majd az értékesítési rendelés kapcsolódik egy projekthez a Supply Chain Management megoldáson belül.</span><span class="sxs-lookup"><span data-stu-id="725f8-126">This is a lookup field, so by tagging your work order with a project, the sales order will be connected to a project within Supply Chain Management.</span></span> <span data-ttu-id="725f8-127">Miután a **Rendszer állapota** **Nyitott – folyamatban (690,970,000)** állapotból magasabb állapba kerül, a **Külső projekt** mezőt a rendszer zárolja, és a továbbiakban nem lehet felvenni, törölni vagy módosítani az értéket.</span><span class="sxs-lookup"><span data-stu-id="725f8-127">After the **System Status** changes **Open – In Progress(690,970,000)** to a higher status, the **External Project** field will be locked and you can no longer add, remove, or change the value.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="725f8-128">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="725f8-128">Prerequisites and mapping setup</span></span>
### <a name="supply-chain-management"></a><span data-ttu-id="725f8-129">Ellátásilánc-kezelés</span><span class="sxs-lookup"><span data-stu-id="725f8-129">Supply Chain Management</span></span>
<span data-ttu-id="725f8-130">A változáskövetés engedélyezése az Adatentitás projektekhez.</span><span class="sxs-lookup"><span data-stu-id="725f8-130">Enable change tracking for Data entity projects.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="725f8-131">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="725f8-131">Template mapping in Data integration</span></span>


### <a name="projects-supply-chain-management-to-field-service-projects"></a><span data-ttu-id="725f8-132">Projektek (Supply Chain Management és Field Service között): Projektek</span><span class="sxs-lookup"><span data-stu-id="725f8-132">Projects (Supply Chain Management to Field Service): Projects</span></span>

<span data-ttu-id="725f8-133">[![Sablonleképezés az adatintegrátorban](./media/FSProject1.png)](./media/FSProject1.png)</span><span class="sxs-lookup"><span data-stu-id="725f8-133">[![Template mapping in Data integration](./media/FSProject1.png)](./media/FSProject1.png)</span></span>
