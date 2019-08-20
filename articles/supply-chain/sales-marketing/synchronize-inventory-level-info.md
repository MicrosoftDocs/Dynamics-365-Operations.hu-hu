---
title: Készletszintű információk szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Microsoft Dynamics 365 for Finance and Operations készletszint-adatainak közvetlenül a Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.
author: ChristianRytt
manager: AnnBe
ms.date: 05/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 6b56eb545f87c31ef30d6a897f48539068583486
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843433"
---
# <a name="synchronize-inventory-level-information-from-finance-and-operations-to-field-service"></a><span data-ttu-id="77e02-103">Készletszintű információk szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba</span><span class="sxs-lookup"><span data-stu-id="77e02-103">Synchronize inventory level information from Finance and Operations to Field Service</span></span> 

[!include[banner](../includes/banner.md)]

<span data-ttu-id="77e02-104">Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Microsoft Dynamics 365 for Finance and Operations készletszint-adatainak közvetlenül a Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.</span><span class="sxs-lookup"><span data-stu-id="77e02-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory-level information from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="77e02-105">[![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span><span class="sxs-lookup"><span data-stu-id="77e02-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="77e02-106">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="77e02-106">Templates and tasks</span></span>
<span data-ttu-id="77e02-107">A következő sablon és a mögöttes feladatok, amelyek a Microsoft Dynamics 365 for Finance and Operations aktuális készletszintjeinek közvetlenül a Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.</span><span class="sxs-lookup"><span data-stu-id="77e02-107">The following template and underlying tasks are used to synchronize inventory on-hand levels from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="77e02-108">**Sablon az adatintegrációban**</span><span class="sxs-lookup"><span data-stu-id="77e02-108">**Template in Data integration**</span></span>
- <span data-ttu-id="77e02-109">Termékkészlet (a Field Service megoldásból a Fin and Ops megoldásba)</span><span class="sxs-lookup"><span data-stu-id="77e02-109">Product Inventory (Fin and Ops to Field Service)</span></span>
  
<span data-ttu-id="77e02-110">**Feladat az adatintegrációs projektben**</span><span class="sxs-lookup"><span data-stu-id="77e02-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="77e02-111">Termékkészlet</span><span class="sxs-lookup"><span data-stu-id="77e02-111">Product inventory</span></span>

<span data-ttu-id="77e02-112">A következő szinkronizálási feladatok kötelezők, mielőtt a készletszintek szinkronizálása megtörténhetne:</span><span class="sxs-lookup"><span data-stu-id="77e02-112">The following synchronization tasks are required before synchronization of inventory levels can occur:</span></span>
- <span data-ttu-id="77e02-113">Raktárak (a Fin and Ops megoldásból a Field Service megoldásba)</span><span class="sxs-lookup"><span data-stu-id="77e02-113">Warehouses (Fin and Ops to Field Service)</span></span> 
- <span data-ttu-id="77e02-114">Készletegységgel rendelkező Field Service termékek (a Fin and Ops alkalmazásból a Sales alkalmazásba)</span><span class="sxs-lookup"><span data-stu-id="77e02-114">Field Service products with Inventory unit (Fin and Ops to Sales)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="77e02-115">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="77e02-115">Entity set</span></span>

| <span data-ttu-id="77e02-116">Field Service</span><span class="sxs-lookup"><span data-stu-id="77e02-116">Field Service</span></span>                      | <span data-ttu-id="77e02-117">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="77e02-117">Finance and Operations</span></span>                 |
|------------------------------------|----------------------------------------|
| <span data-ttu-id="77e02-118">msdynce_externalproductinventories</span><span class="sxs-lookup"><span data-stu-id="77e02-118">msdynce_externalproductinventories</span></span> | <span data-ttu-id="77e02-119">CDS aktuális készlet raktár szerint</span><span class="sxs-lookup"><span data-stu-id="77e02-119">CDS inventory on-hand by warehouse</span></span>     |

## <a name="entity-flow"></a><span data-ttu-id="77e02-120">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="77e02-120">Entity flow</span></span>
<span data-ttu-id="77e02-121">Készletszintadatok küldése a Finance and Operations alkalmazásból a Field Service alkalmazásba a kiválasztott termékekre.</span><span class="sxs-lookup"><span data-stu-id="77e02-121">Inventory-level information from Finance and Operation is sent to Field Service for selected products.</span></span> <span data-ttu-id="77e02-122">A készletszintadatok magukban foglalják a következőket:</span><span class="sxs-lookup"><span data-stu-id="77e02-122">The inventory-level information includes:</span></span> 
- <span data-ttu-id="77e02-123">A készletben található mennyiség (aktuális rögzített és ténylegesen a raktárban található mennyiség)</span><span class="sxs-lookup"><span data-stu-id="77e02-123">On hand quantity (current recorded physical quantity located in the warehouse)</span></span>
- <span data-ttu-id="77e02-124">A rendelési mennyiség (teljes rögzített mennyiség rendelésen, például értékesítési rendelések)</span><span class="sxs-lookup"><span data-stu-id="77e02-124">On order quantity (total recorded quantity on order, such as sales orders)</span></span>
- <span data-ttu-id="77e02-125">Megrendelt mennyiség (teljes rögzített megrendelt mennyiség, például beszerzési rendelések)</span><span class="sxs-lookup"><span data-stu-id="77e02-125">Ordered quantity (total recorded ordered quantity, such as purchase orders)</span></span>

<span data-ttu-id="77e02-126">Ezt az információt a rendszer kiadott termékenként rögzíti minden egyes raktárhoz, és a változások nyomon követés alapján szinkronizálja a készletszint megváltozásakor.</span><span class="sxs-lookup"><span data-stu-id="77e02-126">This information is captured per released product for each warehouse and synchronized based on change tracking, when the inventory level changes.</span></span>

<span data-ttu-id="77e02-127">A Field Service megoldásban az integrációs megoldás készletnaplókat hoz létre a különbözethez, hogy a Field Service szintjei megfeleljenek a Finance and Operations szintjeinek.</span><span class="sxs-lookup"><span data-stu-id="77e02-127">In Field Service, the integration solution creates inventory journals for the delta, so that the levels in Field Service match the levels in Finance and Operations.</span></span>

<span data-ttu-id="77e02-128">A Finance and Operations a készletszintek alapjaként szolgál.</span><span class="sxs-lookup"><span data-stu-id="77e02-128">Finance and Operations will act as the master for inventory levels.</span></span> <span data-ttu-id="77e02-129">Tehát, ezért fontos az integráció beállítása a munkarendelések, az átvitelek és a kiigazítások esetében a Field Service megoldásból a Finance and Operations megoldásba, ha a funkció használatban van a Field Service szolgáltatásban, a készletszintek szinkronizálásával együtt a Finance and Operations megoldásból.</span><span class="sxs-lookup"><span data-stu-id="77e02-129">Therefore it is important to set up integration for work orders, transfers, and adjustments from Field Service to Finance and Operations if this functionality is used in Field Service, together with synchronization of inventory levels from Finance and Operations.</span></span>

<span data-ttu-id="77e02-130">Az olyan termékeket és raktárakat, ahol a készletszintek alapja a Finance and Operations, a speciális lekérdezés és szűrés (Power Query) segítségével lehet vezérelni.</span><span class="sxs-lookup"><span data-stu-id="77e02-130">The products and warehouses where inventory levels are mastered from Finance and Operations can be controlled with the Advanced Query and Filtering (Power Query).</span></span>

> [!NOTE]
> <span data-ttu-id="77e02-131">Megjegyzés: Lehetőség van több raktár létrehozására a Field Services megoldásban (ahol a **Külsőleg karbantartott = Nem**), majd a leképezésükre egy raktárba a Finance and Operations megoldásban, a speciális lekérdezési és szűrési funkcióval.</span><span class="sxs-lookup"><span data-stu-id="77e02-131">It is possible to create multiple warehouses in Field Services (with **Is Externally Maintained = No**) and then map them to a single warehouse in Finance and Operations, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="77e02-132">Ez olyan helyzetekben használt, amikor azt szeretnénk, hogy a Field Service kezelje a részletes készletszintet, és csak frissítéseket küldjön a Finance and Operations megoldásba.</span><span class="sxs-lookup"><span data-stu-id="77e02-132">This is used in situations where you want Field Service to master the detailed inventory level and only send updates to Finance and Operations.</span></span> <span data-ttu-id="77e02-133">Ebben az esetben a Field Service nem kap készletszintű frissítéseket a Finance and Operations megoldásból.</span><span class="sxs-lookup"><span data-stu-id="77e02-133">In this case, Field Service will not receive inventory-level updates from Finance and Operations.</span></span> <span data-ttu-id="77e02-134">További információért lásd: [Készletátvitelek és szinkronizálása a Field Service alkalmazásból a Finance and Operations alkalmazásba](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) és [A Field Service szolgáltatásokban lévő munkarendelések szinkronizálása a Finance and Operations értékesítési rendeléseivel](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="77e02-134">For additional information, see [Synchronize inventory adjustments from Field Service to Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) and [Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="77e02-135">Field Service CRM megoldás</span><span class="sxs-lookup"><span data-stu-id="77e02-135">Field Service CRM solution</span></span>
<span data-ttu-id="77e02-136">A **Külső termékkészlet** entitás új entitás, amely csak az integráció háttérrendszereként használatos.</span><span class="sxs-lookup"><span data-stu-id="77e02-136">The **External product inventory** entity is only used for back end in to the integration.</span></span> <span data-ttu-id="77e02-137">Ez az entitás Finance and Operations készletszint-értékeit kapja meg az integrációban, majd ezeket az értékeket alakítja át manuális készletnaplókká, amelyek ezután módosítják a készlettermékeket a raktárban.</span><span class="sxs-lookup"><span data-stu-id="77e02-137">This entity receives the inventory level values from Finance and Operations in the integration and then transforms those values to Manual inventory journals, which then changes the Inventory products in the Warehouse.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="77e02-138">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="77e02-138">Prerequisites and mapping setup</span></span>

### <a name="data-integration"></a><span data-ttu-id="77e02-139">Adatintegrálás</span><span class="sxs-lookup"><span data-stu-id="77e02-139">Data integration</span></span>
<span data-ttu-id="77e02-140">A projekt működéséhez gondoskodni kell arról, hogy az integrációs kulcs frissüljön a msdynce_externalproductinventories entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="77e02-140">For the project to work, you need to ensure that the Integration key is updated for msdynce_externalproductinventories.</span></span>
1.  <span data-ttu-id="77e02-141">Nyissa meg az **Adatintegráció > Csatlakozókészletek** menüt.</span><span class="sxs-lookup"><span data-stu-id="77e02-141">Go to **Data integration > Connection sets**.</span></span>
2.  <span data-ttu-id="77e02-142">Válassza ki a használt Csatlakozási beállítást.</span><span class="sxs-lookup"><span data-stu-id="77e02-142">Select the used Connection set.</span></span>
3.  <span data-ttu-id="77e02-143">Győződjön meg arról, hogy az **Integrációs kulcs lapon** a következő kulcsok hozzá vannak adva az msdynce_externalproductinventories entitáshoz:</span><span class="sxs-lookup"><span data-stu-id="77e02-143">On the **Integration key** tab, ensure that the following keys are added to msdynce_externalproductinventories:</span></span>
      - <span data-ttu-id="77e02-144">msdynce_productnumber (Termékszám)</span><span class="sxs-lookup"><span data-stu-id="77e02-144">msdynce_productnumber (Product Number)</span></span>
      - <span data-ttu-id="77e02-145">msdynce_warehouseid (Raktár azonosítója)</span><span class="sxs-lookup"><span data-stu-id="77e02-145">msdynce_warehouseid (Warehouse ID)</span></span>
      
### <a name="data-integration-project"></a><span data-ttu-id="77e02-146">Adatintegrációs projekt</span><span class="sxs-lookup"><span data-stu-id="77e02-146">Data integration project</span></span>
<span data-ttu-id="77e02-147">Használhatja a speciális lekérdezés és szűrés szűrőit annak a vezérléséhez, hogy a kívánt termékek küldjenek raktárszintadatokat a Finance and Operations alkalmazásból a Field Service alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="77e02-147">You can apply filters with Advanced Query and Filtering so that only certain products and warehouses send inventory-level information from Finance and Operations to Field Service.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="77e02-148">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="77e02-148">Template mapping in Data integration</span></span>

### <a name="product-inventory-fin-and-ops-to-field-service-product-inventory"></a><span data-ttu-id="77e02-149">Termékkészlet (a Fin and Op megoldásból a Field Service megoldásba): Termékkészlet</span><span class="sxs-lookup"><span data-stu-id="77e02-149">Product inventory (Fin and Ops to Field Service): Product inventory</span></span>

<span data-ttu-id="77e02-150">[![Sablonleképezés az adatintegrátorban](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span><span class="sxs-lookup"><span data-stu-id="77e02-150">[![Template mapping in Data integration](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span></span>
