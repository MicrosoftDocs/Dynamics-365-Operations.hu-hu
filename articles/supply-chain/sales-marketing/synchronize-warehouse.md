---
title: Raktárak szinkronizálása a Supply Chain Management alkalmazásból a Field Service alkalmazásba
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Supply Chain Management raktárainak a Dynamics 365 Field Service szolgáltatásba történő szinkronizálására használatosak.
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
ms.openlocfilehash: 6617b258a85a8f45b89a38f86919b44edc2100da
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215884"
---
# <a name="synchronize-warehouses-from-supply-chain-management-to-field-service"></a><span data-ttu-id="47031-103">Raktárak szinkronizálása a Supply Chain Management alkalmazásból a Field Service alkalmazásba</span><span class="sxs-lookup"><span data-stu-id="47031-103">Synchronize warehouses from Supply Chain Management to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="47031-104">Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Supply Chain Management raktárainak a Dynamics 365 Field Service szolgáltatásba történő szinkronizálására használatosak.</span><span class="sxs-lookup"><span data-stu-id="47031-104">This topic discusses the templates and underlying tasks that are used to synchronize warehouses from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="47031-105">[![Üzleti folyamatok szinkronizálása a Supply Chain Management és a Field Service között](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span><span class="sxs-lookup"><span data-stu-id="47031-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="47031-106">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="47031-106">Templates and tasks</span></span>
<span data-ttu-id="47031-107">A következő sablonokat és alapul szolgáló feladatokat használják a raktárszinkronizálás futtatásához a Supply Chain Management és a Field Service között:</span><span class="sxs-lookup"><span data-stu-id="47031-107">The following template and underlying tasks are used to run synchronization of warehouses from Supply Chain Management to Field Service.</span></span>

<span data-ttu-id="47031-108">**Sablon az adatintegrációban**</span><span class="sxs-lookup"><span data-stu-id="47031-108">**Template in Data integration**</span></span>
- <span data-ttu-id="47031-109">Raktárak (Supply Chain Management és Field Service között)</span><span class="sxs-lookup"><span data-stu-id="47031-109">Warehouses (Supply Chain Management to Field Service)</span></span>

<span data-ttu-id="47031-110">**Feladat az adatintegrációs projektben**</span><span class="sxs-lookup"><span data-stu-id="47031-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="47031-111">Raktár</span><span class="sxs-lookup"><span data-stu-id="47031-111">Warehouse</span></span>

## <a name="entity-set"></a><span data-ttu-id="47031-112">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="47031-112">Entity set</span></span>
| <span data-ttu-id="47031-113">Field Service</span><span class="sxs-lookup"><span data-stu-id="47031-113">Field Service</span></span>    | <span data-ttu-id="47031-114">Ellátásilánc-kezelés</span><span class="sxs-lookup"><span data-stu-id="47031-114">Supply Chain Management</span></span>                 |
|------------------|----------------------------------------|
| <span data-ttu-id="47031-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="47031-115">msdyn_warehouses</span></span> | <span data-ttu-id="47031-116">Raktárak</span><span class="sxs-lookup"><span data-stu-id="47031-116">Warehouses</span></span>                             |

## <a name="entity-flow"></a><span data-ttu-id="47031-117">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="47031-117">Entity flow</span></span>
<span data-ttu-id="47031-118">A Supply Chain Management megoldásban létrehozott és kezelt raktárak a Common Data Service (CDS) adatintegrációs projekten keresztül szinkronizálhatók a Field Service megoldásba.</span><span class="sxs-lookup"><span data-stu-id="47031-118">Warehouses that are created and maintained in Supply Chain Management can be synchronized to Field Service via a Common Data Service (CDS) Data integration project.</span></span> <span data-ttu-id="47031-119">A Field Service megoldásba szinkronizálni kívánt raktárak a speciális lekérdezés és szűrés segítségével vezérelhetők a projekten.</span><span class="sxs-lookup"><span data-stu-id="47031-119">The warehouses that you want to synchronize to Field Service can be controlled with the Advanced query and filtering on the project.</span></span> <span data-ttu-id="47031-120">A Supply Chain Management megoldásból szinkronizálódó raktárak a Field Service megoldásban úgy jönnek létre, hogy a **Külsőleg karbantartva** mező **Igen** értékre van állítva, valamint a rekord csak olvasható.</span><span class="sxs-lookup"><span data-stu-id="47031-120">Warehouses that synchronize from Supply Chain Management are created in Field Service with the **Is maintained externally** field set to **Yes** and the record is read only.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="47031-121">Field Service CRM megoldás</span><span class="sxs-lookup"><span data-stu-id="47031-121">Field Service CRM solution</span></span>
<span data-ttu-id="47031-122">A Field Service és a Supply Chain Management közötti integrálás támogatásához további funkciók szükségesek a Field Service CRM megoldásból.</span><span class="sxs-lookup"><span data-stu-id="47031-122">To support the integration between Field Service and Supply Chain Management, additional functionality from the Field Service CRM solution is required.</span></span> <span data-ttu-id="47031-123">A megoldásban **Külső karbantartású** mező hozzá lett adva a **Raktár (msdyn_warehouses)** entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="47031-123">In the solution, the **Is Maintained Externally** field has been added to the **Warehouse (msdyn_warehouses)** entity.</span></span> <span data-ttu-id="47031-124">Ennek a mezőnek a segítségével ellenőrizheti, hogy a raktár kezelése a Supply Chain Management megoldásból történik, vagy csak a Field Service szolgáltatásban létezik.</span><span class="sxs-lookup"><span data-stu-id="47031-124">This field helps to identify if the warehouse is handled from Supply Chain Management or if it only exists in Field Service.</span></span> <span data-ttu-id="47031-125">A beállítások a mezőben a következők lehetnek:</span><span class="sxs-lookup"><span data-stu-id="47031-125">The settings for this field include:</span></span>
- <span data-ttu-id="47031-126">**Igen** – A raktár a Supply Chain Management szolgáltatásból származik, és nem lesz szerkeszthető a Sales szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="47031-126">**Yes** – The warehouse originated from Supply Chain Management and won't be editable in Sales.</span></span>
- <span data-ttu-id="47031-127">**Nem** – A raktár megadása közvetlenül a Field Service megoldásban történt, és itt is tartják karban.</span><span class="sxs-lookup"><span data-stu-id="47031-127">**No** – The warehouse was entered directly in Field Service and is maintained here.</span></span>

<span data-ttu-id="47031-128">A **Külső karbantartású** mező segítségével szabályozhatja a készletszintek, a kiigazítások, az átvitelek és a munkarendelések használatának szinkronizálását.</span><span class="sxs-lookup"><span data-stu-id="47031-128">The **Is Externally Maintained** field helps control the synchronization of inventory levels, adjustments, transfers, and usage on work orders.</span></span> <span data-ttu-id="47031-129">Csak a **Külső karbantartású** = **Igen** beállítású raktárak használhatók közvetlen szinkronizáláshoz ugyanabba a raktárba a másik rendszerben.</span><span class="sxs-lookup"><span data-stu-id="47031-129">Only warehouses with **Is Externally Maintained** set to **Yes** can be used to synchronize directly to the same warehouse in the other system.</span></span> 

> [!NOTE]
> <span data-ttu-id="47031-130">Megjegyzés: Lehetőség van több raktár létrehozására a Field Service megoldásban (ahol a **Külsőleg karbantartott** = Nem), majd a leképezésükre egy raktárba a speciális lekérdezési és szűrési funkcióval.</span><span class="sxs-lookup"><span data-stu-id="47031-130">It is possible to create multiple warehouses in Field Service (with **Is Externally Maintained** = No) and then map them to a single warehouse, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="47031-131">Ez olyan helyzetekben használt, amikor azt szeretnénk, hogy a Field Service kezelje a részletes készletszintet, és mindössze frissítéseket küldjön a Supply Chain Management megoldásba.</span><span class="sxs-lookup"><span data-stu-id="47031-131">This is used in situations where you want Field Service to master the detailed inventory level and just send updates to Supply Chain Management.</span></span> <span data-ttu-id="47031-132">Ebben az esetben a Field Service nem kap készletszintű frissítéseket a Supply Chain Management megoldásból.</span><span class="sxs-lookup"><span data-stu-id="47031-132">In this case, Field Service will not receive inventory-level updates from Supply Chain Management.</span></span> <span data-ttu-id="47031-133">További információért lásd: [Készletátvitelek és szinkronizálása a Field Service alkalmazásból a Finance and Operations alkalmazásba](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) és [A Field Service szolgáltatásokban lévő munkarendelések szinkronizálása a Finance and Operations értékesítési rendeléseivel](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="47031-133">For additional information, see [Synchronize inventory adjustments from Field Service to Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) and [Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="47031-134">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="47031-134">Prerequisites and mapping setup</span></span>
### <a name="data-integration-project"></a><span data-ttu-id="47031-135">Adatintegrációs projekt</span><span class="sxs-lookup"><span data-stu-id="47031-135">Data Integration project</span></span>
<span data-ttu-id="47031-136">A raktárak szinkronizálása előtt mindenképpen frissítse a speciális lekérdezést és szűrést a projekten, hogy csak azokat a raktárakat foglalja magában, amelyeket át akar vinni a Supply Chain Management megoldásból a Field Service megoldásba.</span><span class="sxs-lookup"><span data-stu-id="47031-136">Before synchronizing the warehouses, make sure to update the Advanced query and filtering on the project to only include the warehouses that you want to bring from Supply Chain Management to Field Service.</span></span> <span data-ttu-id="47031-137">Vegye figyelembe, hogy szüksége lesz a raktárra a Field Service megoldásban az alkalmazásához a munkarendeléseken, a kiigazításokon és az átviteleken.</span><span class="sxs-lookup"><span data-stu-id="47031-137">Note that you will need the warehouse in Field Service to apply it on work orders, adjustments, and transfers.</span></span>  

<span data-ttu-id="47031-138">Ügyeljen arra, hogy az **integrációs kulcs** létezzen ehhez: **msdyn_warehouses**:</span><span class="sxs-lookup"><span data-stu-id="47031-138">To ensure that the **Integration key** exists for **msdyn_warehouses**:</span></span>
1. <span data-ttu-id="47031-139">Lépjen az Adatintegrációra.</span><span class="sxs-lookup"><span data-stu-id="47031-139">Go to Data Integration.</span></span>
2. <span data-ttu-id="47031-140">Válassza ki a **Csatlakozás beállítása** fület.</span><span class="sxs-lookup"><span data-stu-id="47031-140">Select the **Connection Set** tab.</span></span>
3. <span data-ttu-id="47031-141">Válassza ki a munkarendelés szinkronizálásához használt csatlakozási beállítást.</span><span class="sxs-lookup"><span data-stu-id="47031-141">Select the connection set used for work order synchronization.</span></span>
4. <span data-ttu-id="47031-142">Válassza ki az **Integrációs kulcs** fület.</span><span class="sxs-lookup"><span data-stu-id="47031-142">Select the **Integration key** tab.</span></span>
5. <span data-ttu-id="47031-143">Keresse meg a msdyn_warehouses elemet, és erősítse meg, hogy a **msdyn_name (név)** van hozzáadva.</span><span class="sxs-lookup"><span data-stu-id="47031-143">Find msdyn_warehouses and confirm that the key **msdyn_name (name)** is added.</span></span> <span data-ttu-id="47031-144">Ha nem látható, kattintson a **Kulcs hozzáadása** elemre a hozzáadáshoz, majd kattintson a **Mentés** elemre a lap tetején.</span><span class="sxs-lookup"><span data-stu-id="47031-144">If it is not shown, add it by clicking **Add key** and then click **Save** at the top of the page.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="47031-145">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="47031-145">Template mapping in Data integration</span></span>

<span data-ttu-id="47031-146">Az alábbi ábrán látható a sablonleképezés az Adatintegrálásban.</span><span class="sxs-lookup"><span data-stu-id="47031-146">The following illustration shows the template mapping in Data integration.</span></span>

### <a name="warehouses-supply-chain-management-to-field-service-warehouse"></a><span data-ttu-id="47031-147">Raktárak (Supply Chain Management és Field Service között): Raktár</span><span class="sxs-lookup"><span data-stu-id="47031-147">Warehouses (Supply Chain Management to Field Service): Warehouse</span></span>

<span data-ttu-id="47031-148">[![Sablonleképezés az adatintegrátorban](./media/Warehouse1.png)](./media/Warehouse1.png)</span><span class="sxs-lookup"><span data-stu-id="47031-148">[![Template mapping in Data integration](./media/Warehouse1.png)](./media/Warehouse1.png)</span></span>
