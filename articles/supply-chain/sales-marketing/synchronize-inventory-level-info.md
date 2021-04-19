---
title: Készletszintű információk szinkronizálása a Supply Chain Management alkalmazásból a Field Service alkalmazásba
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Supply Chain Management készletszint-adatainak közvetlenül a Dynamics 365 Field Service szolgáltatásba történő szinkronizálására használatosak.
author: ChristianRytt
ms.date: 05/07/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: c0db0c143abb8ce26a4a3007845050e4ddb02363
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840581"
---
# <a name="synchronize-inventory-level-information-from-supply-chain-management-to-field-service"></a><span data-ttu-id="564d7-103">Készletszintű információk szinkronizálása a Supply Chain Management alkalmazásból a Field Service alkalmazásba</span><span class="sxs-lookup"><span data-stu-id="564d7-103">Synchronize inventory level information from Supply Chain Management to Field Service</span></span> 

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="564d7-104">Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Supply Chain Management készletszint-adatainak közvetlenül a Dynamics 365 Field Service szolgáltatásba történő szinkronizálására használatosak.</span><span class="sxs-lookup"><span data-stu-id="564d7-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory-level information from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="564d7-105">[![Üzleti folyamatok szinkronizálása a Supply Chain Management és a Field Service között](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span><span class="sxs-lookup"><span data-stu-id="564d7-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="564d7-106">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="564d7-106">Templates and tasks</span></span>
<span data-ttu-id="564d7-107">A következő sablonokat és alapul szolgáló feladatokat használják a tényleges készletszint szinkronizálásához a Supply Chain Management és a Field Service között:</span><span class="sxs-lookup"><span data-stu-id="564d7-107">The following template and underlying tasks are used to synchronize inventory on-hand levels from Supply Chain Management to Field Service.</span></span>

<span data-ttu-id="564d7-108">**Sablon az adatintegrációban**</span><span class="sxs-lookup"><span data-stu-id="564d7-108">**Template in Data integration**</span></span>
- <span data-ttu-id="564d7-109">Termékkészlet (Supply Chain Management és Field Service között)</span><span class="sxs-lookup"><span data-stu-id="564d7-109">Product Inventory (Supply Chain Management to Field Service)</span></span>
  
<span data-ttu-id="564d7-110">**Feladat az adatintegrációs projektben**</span><span class="sxs-lookup"><span data-stu-id="564d7-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="564d7-111">Termékkészlet</span><span class="sxs-lookup"><span data-stu-id="564d7-111">Product inventory</span></span>

<span data-ttu-id="564d7-112">A következő szinkronizálási feladatok kötelezők, mielőtt a készletszintek szinkronizálása megtörténhetne:</span><span class="sxs-lookup"><span data-stu-id="564d7-112">The following synchronization tasks are required before synchronization of inventory levels can occur:</span></span>
- <span data-ttu-id="564d7-113">Raktárak (Supply Chain Management és Field Service között)</span><span class="sxs-lookup"><span data-stu-id="564d7-113">Warehouses (Supply Chain Management to Field Service)</span></span> 
- <span data-ttu-id="564d7-114">Készletegységgel rendelkező Field Service-termékek (Supply Chain Management alkalmazásból a Sales alkalmazásba)</span><span class="sxs-lookup"><span data-stu-id="564d7-114">Field Service products with Inventory unit (Supply Chain Management to Sales)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="564d7-115">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="564d7-115">Entity set</span></span>

| <span data-ttu-id="564d7-116">Field Service</span><span class="sxs-lookup"><span data-stu-id="564d7-116">Field Service</span></span>                      | <span data-ttu-id="564d7-117">Ellátásilánc-kezelés</span><span class="sxs-lookup"><span data-stu-id="564d7-117">Supply Chain Management</span></span>                |
|------------------------------------|----------------------------------------|
| <span data-ttu-id="564d7-118">msdynce_externalproductinventories</span><span class="sxs-lookup"><span data-stu-id="564d7-118">msdynce_externalproductinventories</span></span> | <span data-ttu-id="564d7-119">Dataverse aktuális készlet raktár szerint</span><span class="sxs-lookup"><span data-stu-id="564d7-119">Dataverse inventory on-hand by warehouse</span></span>     |

## <a name="entity-flow"></a><span data-ttu-id="564d7-120">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="564d7-120">Entity flow</span></span>
<span data-ttu-id="564d7-121">Készletszintadatok küldése a Finance and Operations alkalmazásból a Field Service alkalmazásba a kiválasztott termékekre.</span><span class="sxs-lookup"><span data-stu-id="564d7-121">Inventory-level information from Finance and Operation is sent to Field Service for selected products.</span></span> <span data-ttu-id="564d7-122">A készletszintadatok magukban foglalják a következőket:</span><span class="sxs-lookup"><span data-stu-id="564d7-122">The inventory-level information includes:</span></span> 
- <span data-ttu-id="564d7-123">A készletben található mennyiség (aktuális rögzített és ténylegesen a raktárban található mennyiség)</span><span class="sxs-lookup"><span data-stu-id="564d7-123">On hand quantity (current recorded physical quantity located in the warehouse)</span></span>
- <span data-ttu-id="564d7-124">A rendelési mennyiség (teljes rögzített mennyiség rendelésen, például értékesítési rendelések)</span><span class="sxs-lookup"><span data-stu-id="564d7-124">On order quantity (total recorded quantity on order, such as sales orders)</span></span>
- <span data-ttu-id="564d7-125">Megrendelt mennyiség (teljes rögzített megrendelt mennyiség, például beszerzési rendelések)</span><span class="sxs-lookup"><span data-stu-id="564d7-125">Ordered quantity (total recorded ordered quantity, such as purchase orders)</span></span>

<span data-ttu-id="564d7-126">Ezt az információt a rendszer kiadott termékenként rögzíti minden egyes raktárhoz, és a változások nyomon követés alapján szinkronizálja a készletszint megváltozásakor.</span><span class="sxs-lookup"><span data-stu-id="564d7-126">This information is captured per released product for each warehouse and synchronized based on change tracking, when the inventory level changes.</span></span>

<span data-ttu-id="564d7-127">A Field Service megoldásban az integrációs megoldás készletnaplókat hoz létre a különbözethez, hogy a Field Service szintjei megfeleljenek a Supply Chain Management szintjeinek.</span><span class="sxs-lookup"><span data-stu-id="564d7-127">In Field Service, the integration solution creates inventory journals for the delta, so that the levels in Field Service match the levels in Supply Chain Management.</span></span>

<span data-ttu-id="564d7-128">A Supply Chain Management a készletszintek alapjaként szolgál.</span><span class="sxs-lookup"><span data-stu-id="564d7-128">Supply Chain Management will act as the master for inventory levels.</span></span> <span data-ttu-id="564d7-129">Tehát, ezért fontos az integráció beállítása a munkarendelések, az átvitelek és a kiigazítások esetében a Field Service megoldásból a Supply Chain Management megoldásba, ha a funkció használatban van a Field Service szolgáltatásban, a készletszintek szinkronizálásával együtt a Supply Chain Management megoldásból.</span><span class="sxs-lookup"><span data-stu-id="564d7-129">Therefore it is important to set up integration for work orders, transfers, and adjustments from Field Service to Supply Chain Management if this functionality is used in Field Service, together with synchronization of inventory levels from Supply Chain Management.</span></span>

<span data-ttu-id="564d7-130">Az olyan termékeket és raktárakat, ahol a készletszintek alapja a Supply Chain Management, a speciális lekérdezés és szűrés (Power Query) segítségével lehet vezérelni.</span><span class="sxs-lookup"><span data-stu-id="564d7-130">The products and warehouses where inventory levels are mastered from Supply Chain Management can be controlled with the Advanced Query and Filtering (Power Query).</span></span>

> [!NOTE]
> <span data-ttu-id="564d7-131">Megjegyzés: Lehetőség van több raktár létrehozására a Field Services megoldásban (ahol a **Külsőleg karbantartott = Nem**), majd a leképezésükre egy raktárba a Supply Chain Management megoldásban, a speciális lekérdezési és szűrési funkcióval.</span><span class="sxs-lookup"><span data-stu-id="564d7-131">It is possible to create multiple warehouses in Field Services (with **Is Externally Maintained = No**) and then map them to a single warehouse in Supply Chain Management, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="564d7-132">Ez olyan helyzetekben használt, amikor azt szeretnénk, hogy a Field Service kezelje a részletes készletszintet, és csak frissítéseket küldjön a Supply Chain Management megoldásba.</span><span class="sxs-lookup"><span data-stu-id="564d7-132">This is used in situations where you want Field Service to master the detailed inventory level and only send updates to Supply Chain Management.</span></span> <span data-ttu-id="564d7-133">Ebben az esetben a Field Service nem kap készletszintű frissítéseket a Supply Chain Management megoldásból.</span><span class="sxs-lookup"><span data-stu-id="564d7-133">In this case, Field Service will not receive inventory-level updates from Supply Chain Management.</span></span> <span data-ttu-id="564d7-134">További információért lásd: [Készletátvitelek és szinkronizálása a Field Service alkalmazásból a Supply Chain Management alkalmazásba](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) és [A Field Service szolgáltatásokban lévő munkarendelések szinkronizálása a Supply Chain Management értékesítési rendeléseivel](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="564d7-134">For additional information, see [Synchronize inventory adjustments from Field Service to Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) and [Synchronize work orders in Field Service to sales orders linked to project in Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="564d7-135">Field Service CRM megoldás</span><span class="sxs-lookup"><span data-stu-id="564d7-135">Field Service CRM solution</span></span>
<span data-ttu-id="564d7-136">A **Külső termékkészlet** entitás új entitás, amely csak az integráció háttérrendszereként használatos.</span><span class="sxs-lookup"><span data-stu-id="564d7-136">The **External product inventory** entity is only used for back end in to the integration.</span></span> <span data-ttu-id="564d7-137">Ez az entitás Supply Chain Management készletszint-értékeit kapja meg az integrációban, majd ezeket az értékeket alakítja át manuális készletnaplókká, amelyek ezután módosítják a készlettermékeket a raktárban.</span><span class="sxs-lookup"><span data-stu-id="564d7-137">This entity receives the inventory level values from Supply Chain Management in the integration and then transforms those values to Manual inventory journals, which then changes the Inventory products in the Warehouse.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="564d7-138">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="564d7-138">Prerequisites and mapping setup</span></span>

### <a name="data-integration"></a><span data-ttu-id="564d7-139">Adatintegrálás</span><span class="sxs-lookup"><span data-stu-id="564d7-139">Data integration</span></span>
<span data-ttu-id="564d7-140">A projekt működéséhez gondoskodni kell arról, hogy az integrációs kulcs frissüljön a msdynce_externalproductinventories entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="564d7-140">For the project to work, you need to ensure that the Integration key is updated for msdynce_externalproductinventories.</span></span>
1.  <span data-ttu-id="564d7-141">Nyissa meg az **Adatintegráció > Csatlakozókészletek** menüt.</span><span class="sxs-lookup"><span data-stu-id="564d7-141">Go to **Data integration > Connection sets**.</span></span>
2.  <span data-ttu-id="564d7-142">Válassza ki a használt Csatlakozási beállítást.</span><span class="sxs-lookup"><span data-stu-id="564d7-142">Select the used Connection set.</span></span>
3.  <span data-ttu-id="564d7-143">Győződjön meg arról, hogy az **Integrációs kulcs lapon** a következő kulcsok hozzá vannak adva az msdynce_externalproductinventories entitáshoz:</span><span class="sxs-lookup"><span data-stu-id="564d7-143">On the **Integration key** tab, ensure that the following keys are added to msdynce_externalproductinventories:</span></span>
      - <span data-ttu-id="564d7-144">msdynce_productnumber (Termékszám)</span><span class="sxs-lookup"><span data-stu-id="564d7-144">msdynce_productnumber (Product Number)</span></span>
      - <span data-ttu-id="564d7-145">msdynce_warehouseid (Raktár azonosítója)</span><span class="sxs-lookup"><span data-stu-id="564d7-145">msdynce_warehouseid (Warehouse ID)</span></span>
      
### <a name="data-integration-project"></a><span data-ttu-id="564d7-146">Adatintegrációs projekt</span><span class="sxs-lookup"><span data-stu-id="564d7-146">Data integration project</span></span>
<span data-ttu-id="564d7-147">Használhatja a speciális lekérdezés és szűrés szűrőit annak a vezérléséhez, hogy a kívánt termékek küldjenek raktárszintadatokat a Supply Chain Management alkalmazásból a Field Service alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="564d7-147">You can apply filters with Advanced Query and Filtering so that only certain products and warehouses send inventory-level information from Supply Chain Management to Field Service.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="564d7-148">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="564d7-148">Template mapping in Data integration</span></span>

### <a name="product-inventory-supply-chain-management-to-field-service-product-inventory"></a><span data-ttu-id="564d7-149">Termékkészlet (Supply Chain Management alkalmazásból a Field Service alkalmazásba): Termékkészlet</span><span class="sxs-lookup"><span data-stu-id="564d7-149">Product inventory (Supply Chain Management to Field Service): Product inventory</span></span>

<span data-ttu-id="564d7-150">[![Sablonleképezés az adatintegrátorban](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span><span class="sxs-lookup"><span data-stu-id="564d7-150">[![Template mapping in Data integration](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]