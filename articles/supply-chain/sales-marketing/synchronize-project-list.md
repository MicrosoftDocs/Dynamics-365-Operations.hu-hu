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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 12708b35be87baf1ad13296b56507f3246f96394
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010872"
---
# <a name="synchronize-project-list-from-supply-chain-management-to-field-service"></a><span data-ttu-id="b2b5e-103">Projektlista szinkronizálása a Supply Chain Management alkalmazásból a Field Service alkalmazásba</span><span class="sxs-lookup"><span data-stu-id="b2b5e-103">Synchronize project list from Supply Chain Management to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="b2b5e-104">Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Supply Chain Management projektjeinek a Dynamics 365 Field Service szolgáltatásba történő szinkronizálására használatosak.</span><span class="sxs-lookup"><span data-stu-id="b2b5e-104">This topic discusses the templates and underlying tasks that are used to synchronize projects from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="b2b5e-105">[![Üzleti folyamatok szinkronizálása a Supply Chain Management és a Field Service között](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span><span class="sxs-lookup"><span data-stu-id="b2b5e-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="b2b5e-106">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="b2b5e-106">Templates and tasks</span></span>
<span data-ttu-id="b2b5e-107">A következő sablonokat és alapul szolgáló feladatokat használják a projektszinkronizálás futtatásához a Supply Chain Management és a Field Service között:</span><span class="sxs-lookup"><span data-stu-id="b2b5e-107">The following template and underlying tasks are used to run synchronization of projects from Supply Chain Management to Field Service.</span></span>

<span data-ttu-id="b2b5e-108">**Sablon az adatintegrációban**</span><span class="sxs-lookup"><span data-stu-id="b2b5e-108">**Template in Data integration**</span></span>
- <span data-ttu-id="b2b5e-109">Projektek (Supply Chain Management és Field Service között)</span><span class="sxs-lookup"><span data-stu-id="b2b5e-109">Projects (Supply Chain Management to Field Service)</span></span>

<span data-ttu-id="b2b5e-110">**Feladat az adatintegrációs projektben**</span><span class="sxs-lookup"><span data-stu-id="b2b5e-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="b2b5e-111">Projektek</span><span class="sxs-lookup"><span data-stu-id="b2b5e-111">Projects</span></span>

<span data-ttu-id="b2b5e-112">A következő szinkronizálási feladatok kötelezők, mielőtt a projektlisták szinkronizálása megtörténhetne:</span><span class="sxs-lookup"><span data-stu-id="b2b5e-112">The following synchronization tasks are required before synchronization of project list can occur:</span></span>
- <span data-ttu-id="b2b5e-113">Számlák (Sales és Supply Chain Management között)</span><span class="sxs-lookup"><span data-stu-id="b2b5e-113">Accounts (Sales to Supply Chain Management)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="b2b5e-114">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="b2b5e-114">Entity set</span></span>
| <span data-ttu-id="b2b5e-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="b2b5e-115">Field Service</span></span>           | <span data-ttu-id="b2b5e-116">Ellátásilánc-kezelés</span><span class="sxs-lookup"><span data-stu-id="b2b5e-116">Supply Chain Management</span></span>  |
|-------------------------|-------------------------|
|<span data-ttu-id="b2b5e-117">msdynce_externalprojects</span><span class="sxs-lookup"><span data-stu-id="b2b5e-117">msdynce_externalprojects</span></span> | <span data-ttu-id="b2b5e-118">Projektek</span><span class="sxs-lookup"><span data-stu-id="b2b5e-118">Projects</span></span>                |

## <a name="entity-flow"></a><span data-ttu-id="b2b5e-119">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="b2b5e-119">Entity flow</span></span>
<span data-ttu-id="b2b5e-120">A Projekteket a Supply Chain Management szolgáltatásban hozzák létre.</span><span class="sxs-lookup"><span data-stu-id="b2b5e-120">Projects are created in Supply Chain Management.</span></span> <span data-ttu-id="b2b5e-121">A projektek, amelyek esetében a **Projekttípus** **Idő és anyag**, a **Projektfokozat** pedig **Folyamatban**, a Field Service **Külső projekt** entitásába szinkronizálódnak, a következő információkat beleértve: projekt száma, projektnév, projektfokozat és vevői számla adatai.</span><span class="sxs-lookup"><span data-stu-id="b2b5e-121">Projects with **Project type** set to **Time and material** and **Project stage** set to **In process** will synchronize to the **External Project** entity in Field Service, including Project number, Project name, Project stage, and Customer account information.</span></span> <span data-ttu-id="b2b5e-122">A **Külső projekt** listát a rendszer a Field Service munkarendelések és a Supply Chain Management projektek párosítására használja.</span><span class="sxs-lookup"><span data-stu-id="b2b5e-122">The **External Project** list is used to pair Field service work orders with Supply Chain Management projects.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="b2b5e-123">Field Service CRM megoldás</span><span class="sxs-lookup"><span data-stu-id="b2b5e-123">Field Service CRM solution</span></span>
<span data-ttu-id="b2b5e-124">A **Külső projekt** entitás lekér minden projektet a Supply Chain Management rendszerből.</span><span class="sxs-lookup"><span data-stu-id="b2b5e-124">The **External Project** entity gets all the projects from Supply Chain Management.</span></span> <span data-ttu-id="b2b5e-125">A **Külső projekt** mezőt hozzáadtuk a **Munkarendelés** entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="b2b5e-125">The **External Project** field has been added to the **Work Order** entity.</span></span> <span data-ttu-id="b2b5e-126">Ez a mező egy keresőmező felcímkézi a munkarendelést egy projekttel, majd az értékesítési rendelés kapcsolódik egy projekthez a Supply Chain Management megoldáson belül.</span><span class="sxs-lookup"><span data-stu-id="b2b5e-126">This is a lookup field, so by tagging your work order with a project, the sales order will be connected to a project within Supply Chain Management.</span></span> <span data-ttu-id="b2b5e-127">Miután a **Rendszer állapota** **Nyitott – folyamatban (690,970,000)** állapotból magasabb állapba kerül, a **Külső projekt** mezőt a rendszer zárolja, és a továbbiakban nem lehet felvenni, törölni vagy módosítani az értéket.</span><span class="sxs-lookup"><span data-stu-id="b2b5e-127">After the **System Status** changes **Open – In Progress(690,970,000)** to a higher status, the **External Project** field will be locked and you can no longer add, remove, or change the value.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="b2b5e-128">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="b2b5e-128">Prerequisites and mapping setup</span></span>
### <a name="supply-chain-management"></a><span data-ttu-id="b2b5e-129">Ellátásilánc-kezelés</span><span class="sxs-lookup"><span data-stu-id="b2b5e-129">Supply Chain Management</span></span>
<span data-ttu-id="b2b5e-130">A változáskövetés engedélyezése az Adatentitás projektekhez.</span><span class="sxs-lookup"><span data-stu-id="b2b5e-130">Enable change tracking for Data entity projects.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="b2b5e-131">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="b2b5e-131">Template mapping in Data integration</span></span>


### <a name="projects-supply-chain-management-to-field-service-projects"></a><span data-ttu-id="b2b5e-132">Projektek (Supply Chain Management és Field Service között): Projektek</span><span class="sxs-lookup"><span data-stu-id="b2b5e-132">Projects (Supply Chain Management to Field Service): Projects</span></span>

<span data-ttu-id="b2b5e-133">[![Sablonleképezés az adatintegrátorban](./media/FSProject1.png)](./media/FSProject1.png)</span><span class="sxs-lookup"><span data-stu-id="b2b5e-133">[![Template mapping in Data integration](./media/FSProject1.png)](./media/FSProject1.png)</span></span>
