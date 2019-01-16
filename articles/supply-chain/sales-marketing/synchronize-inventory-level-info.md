---
title: "Készletszintű információk szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a készletszint-információk szinkronizálására használhatók a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service között."
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
ms.openlocfilehash: 3ccc4d406fa4f9800dcdf8697a91892408783196
ms.contentlocale: hu-hu
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-inventory-level-information-from-finance-and-operations-to-field-service"></a><span data-ttu-id="b63a7-103">Készletszintű információk szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba</span><span class="sxs-lookup"><span data-stu-id="b63a7-103">Synchronize inventory level information from Finance and Operations to Field Service</span></span> 

[!include[banner](../includes/banner.md)]

<span data-ttu-id="b63a7-104">Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a készletszint-információk szinkronizálására használhatók a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service között.</span><span class="sxs-lookup"><span data-stu-id="b63a7-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory level information from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="b63a7-105">[![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span><span class="sxs-lookup"><span data-stu-id="b63a7-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="b63a7-106">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="b63a7-106">Templates and tasks</span></span>
<span data-ttu-id="b63a7-107">A következő sablon és a kapcsolódó feladatok a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service közötti aktuális készletszintek szinkronizálás futtatására használhatók.</span><span class="sxs-lookup"><span data-stu-id="b63a7-107">The following template and underlying tasks are used to run synchronization of inventory on-hand levels from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="b63a7-108">**A sablon neve az adatintegrációban:**</span><span class="sxs-lookup"><span data-stu-id="b63a7-108">**Name of the template in Data integration:**</span></span>
- <span data-ttu-id="b63a7-109">Termékkészlet (a Finance and Operations megoldásból a Field Service megoldásba)</span><span class="sxs-lookup"><span data-stu-id="b63a7-109">Product Inventory (Finance and Operations to Field Service)</span></span>
  
<span data-ttu-id="b63a7-110">**A feladatok nevei az adatintegrációs projektben:**</span><span class="sxs-lookup"><span data-stu-id="b63a7-110">**Names of the tasks in the Data integration project:**</span></span>
- <span data-ttu-id="b63a7-111">Termékkészlet</span><span class="sxs-lookup"><span data-stu-id="b63a7-111">Product inventory</span></span>

<span data-ttu-id="b63a7-112">A következő szinkronizálási feladatok kötelezők, mielőtt a készletszintek szinkronizálása megtörténhetne:</span><span class="sxs-lookup"><span data-stu-id="b63a7-112">The following synchronization tasks are required before synchronization of inventory levels can occur:</span></span>
- <span data-ttu-id="b63a7-113">Raktárak (a Finance and Operations megoldásból a Field Service megoldásba)</span><span class="sxs-lookup"><span data-stu-id="b63a7-113">Warehouses (Finance and Operations to Field Service)</span></span> 
- <span data-ttu-id="b63a7-114">Készletegységgel rendelkező Field Service termékek (a Finance and Operations alkalmazásból a Sales alkalmazásba)</span><span class="sxs-lookup"><span data-stu-id="b63a7-114">Field Service Products with Inventory unit (Finance and Operations to Sales)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="b63a7-115">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="b63a7-115">Entity set</span></span>

| <span data-ttu-id="b63a7-116">Field Service</span><span class="sxs-lookup"><span data-stu-id="b63a7-116">Field Service</span></span>                      | <span data-ttu-id="b63a7-117">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b63a7-117">Finance and Operations</span></span>                 |
|------------------------------------|----------------------------------------|
| <span data-ttu-id="b63a7-118">msdynce_externalproductinventories</span><span class="sxs-lookup"><span data-stu-id="b63a7-118">msdynce_externalproductinventories</span></span> | <span data-ttu-id="b63a7-119">CDS aktuális készlet raktár szerint</span><span class="sxs-lookup"><span data-stu-id="b63a7-119">CDS inventory on-hand by warehouse</span></span>     |

## <a name="entity-flow"></a><span data-ttu-id="b63a7-120">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="b63a7-120">Entity flow</span></span>
<span data-ttu-id="b63a7-121">Készletszintadatok küldése a Finance and Operations alkalmazásból a Field Service alkalmazásba a kiválasztott termékekre.</span><span class="sxs-lookup"><span data-stu-id="b63a7-121">Inventory level information from Finance and Operation is send to Field Service for selected products.</span></span> <span data-ttu-id="b63a7-122">A készletszintadatok magukban foglalják a következőket:</span><span class="sxs-lookup"><span data-stu-id="b63a7-122">The inventory level information include:</span></span> 
- <span data-ttu-id="b63a7-123">A készletben található mennyiség (aktuális rögzített, ténylegesen a raktárban található mennyiség)</span><span class="sxs-lookup"><span data-stu-id="b63a7-123">On hand quantity (current recorded physically quantity located in the warehouse)</span></span>
- <span data-ttu-id="b63a7-124">A rendelési mennyiség (teljes rögzített mennyiség rendelésen – azaz értékesítési rendelések)</span><span class="sxs-lookup"><span data-stu-id="b63a7-124">On order quantity (total recorded quantity on order - i.e. sales orders)</span></span>
- <span data-ttu-id="b63a7-125">Megrendelt mennyiség (teljes rögzített megrendelt mennyiség – azaz beszerzési rendelések)</span><span class="sxs-lookup"><span data-stu-id="b63a7-125">Ordered quantity (total recorded ordered quantity - i.e. purchase orders)</span></span>

<span data-ttu-id="b63a7-126">Ezt az információt a rendszer kiadott termékenként rögzíti minden egyes raktárhoz, és a változások nyomon követés alapján szinkronizálja a készletszint megváltozásakor.</span><span class="sxs-lookup"><span data-stu-id="b63a7-126">This information is captured per released product for each warehouse and synchronized based on change tracking, when the inventory level changes.</span></span>

<span data-ttu-id="b63a7-127">A Field Service megoldásban az integrációs megoldás készletnaplókat hoz létre a különbözethez, hogy a Field Service szintjei megfeleljenek a Finance and Operations szintjeinek.</span><span class="sxs-lookup"><span data-stu-id="b63a7-127">In Field Service the integration solution create inventory journals for the delta, to get the levels in Field Service to match the levels in Finance and Operations.</span></span>

<span data-ttu-id="b63a7-128">A Finance and Operations a készletszintek alapjaként szolgál.</span><span class="sxs-lookup"><span data-stu-id="b63a7-128">Finance and Operations will act as the master for inventory levels.</span></span> <span data-ttu-id="b63a7-129">Ezért fontos az integráció beállítása a munkarendelések, az átvitelek és a kiigazítások esetében a Field Service megoldásból a Finance and Operations megoldásba, ha a funkció használatban van a Field Service szolgáltatásban, a készletszintek szinkronizálásával együtt a Finance and Operations megoldásból.</span><span class="sxs-lookup"><span data-stu-id="b63a7-129">So it is important to setup integration for workorders, transfers and adjustments from Field Service to Finance and Operations if the this functionality is used in Field Service, together with synchronization of inventory levels from Finance and Operations.</span></span>

<span data-ttu-id="b63a7-130">Az olyan termékeket és raktárakat, ahol a készletszintek alapja a Finance and Operations, a speciális lekérdezés és szűrés (Power Query) segítségével lehet vezérelni.</span><span class="sxs-lookup"><span data-stu-id="b63a7-130">The products and warehouses where inventory levels are mastered from Finance and Operations can be controlled with the Advanced Query and Filtering (Power Query).</span></span>

<span data-ttu-id="b63a7-131">Megjegyzés: Lehetőség van több raktár létrehozására a Field Service megoldásban (ahol a Külsőleg karbantartott = Nem), majd a leképezésükre egy raktárba a Finance and Operations megoldásban, a speciális lekérdezési és szűrési funkcióval.</span><span class="sxs-lookup"><span data-stu-id="b63a7-131">Note: It is possible to create multiple warehouses in Field Services (with Is Externally Maintained = No) and then map them to a single warehouse in Finance and Operations, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="b63a7-132">Ez olyan helyzetekben használt, amikor azt szeretnénk, hogy a Field Service kezelje a részletes készletszintet, és csak frissítéseket küldjön a Finance and Operations megoldásba.</span><span class="sxs-lookup"><span data-stu-id="b63a7-132">This is used in situations where you want Field service to master the detailed inventory level and just send updates to Finance and Operations.</span></span> <span data-ttu-id="b63a7-133">Ebben az esetben a Field Service nem kap készletszint-frissítéseket a Finance and Operations megoldásból.</span><span class="sxs-lookup"><span data-stu-id="b63a7-133">In this case Field service will not receive inventory level updates from Finance and Operations.</span></span> <span data-ttu-id="b63a7-134">További információért lásd: Készletátvitelek és szinkronizálása a Field Service alkalmazásból a Finance and Operations alkalmazásba és A Field Service szolgáltatásokban lévő munkarendelések szinkronizálása a Finance and Operations értékesítési rendeléseivel.</span><span class="sxs-lookup"><span data-stu-id="b63a7-134">See additional information in Synchronize inventory adjustments from Field Service to Finance and Operations and Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="b63a7-135">Field Service CRM megoldás</span><span class="sxs-lookup"><span data-stu-id="b63a7-135">Field Service CRM solution</span></span>
<span data-ttu-id="b63a7-136">A külső termékkészlet entitás új entitás, amely csak az integráció háttérrendszereként használatos.</span><span class="sxs-lookup"><span data-stu-id="b63a7-136">The External Product Inventory entity is a new entity that’s only used for backend in the integration.</span></span> <span data-ttu-id="b63a7-137">A Finance and Operations készletszint-értékeit kapja meg az integrációban, majd ezeket az értékeket alakítja át manuális készletnaplókká, amelyek ezután módosítják a készlettermékeket a raktárban.</span><span class="sxs-lookup"><span data-stu-id="b63a7-137">It receives the inventory level values from Finance and Operations in the integration and then transforms those values to Manuel Inventory journals, that then changes the Inventory Products on the Warehouse.</span></span> 

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="b63a7-138">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="b63a7-138">Prerequisites and mapping setup</span></span>

### <a name="in-the-data-integration-project"></a><span data-ttu-id="b63a7-139">Az adatintegrációs projektben</span><span class="sxs-lookup"><span data-stu-id="b63a7-139">In the Data Integration project</span></span>
<span data-ttu-id="b63a7-140">Használja a speciális lekérdezés és szűrés szűrőit annak a vezérléséhez, hogy a kívánt termékek küldjenek raktárszintadatokat a Finance and Operations alkalmazásból a Field Service alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="b63a7-140">Apply filters with the Advanced  Query and Filtering to control that only desired products and warehouses send inventory level information from Finance and Operations to Field Service.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="b63a7-141">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="b63a7-141">Template mapping in Data integration</span></span>

### <a name="product-inventory-finance-and-operations-to-field-service-product-inventory"></a><span data-ttu-id="b63a7-142">Termékkészlet (a Finance and Operations megoldásból a Field Service megoldásba): Termékkészlet</span><span class="sxs-lookup"><span data-stu-id="b63a7-142">Product Inventory (Finance and Operations to Field Service): Product inventory</span></span>

<span data-ttu-id="b63a7-143">[![Sablonleképezés az adatintegrátorban](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span><span class="sxs-lookup"><span data-stu-id="b63a7-143">[![Template mapping in Data integration](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span></span>

