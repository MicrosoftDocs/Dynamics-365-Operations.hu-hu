---
title: Raktárak szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Microsoft Dynamics 365 for Finance and Operations raktárainak a Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
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
ms.openlocfilehash: ae99624076eecda2969961d0361d1adf42c6c5f3
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835670"
---
# <a name="synchronize-warehouses-from-finance-and-operations-to-field-service"></a><span data-ttu-id="fb05f-103">Raktárak szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba</span><span class="sxs-lookup"><span data-stu-id="fb05f-103">Synchronize warehouses from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="fb05f-104">Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Microsoft Dynamics 365 for Finance and Operations raktárainak a Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.</span><span class="sxs-lookup"><span data-stu-id="fb05f-104">This topic discusses the templates and underlying tasks that are used to synchronize warehouses from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="fb05f-105">[![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span><span class="sxs-lookup"><span data-stu-id="fb05f-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="fb05f-106">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="fb05f-106">Templates and tasks</span></span>
<span data-ttu-id="fb05f-107">A következő sablonok és a mögöttes tevékenységek használatosak a raktárak szinkronizálásához a Microsoft Dynamics 365 for Finance and Operations alkalmazásból a Microsoft Dynamics 365 for Field Service alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="fb05f-107">The following template and underlying tasks are used to run synchronization of warehouses from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="fb05f-108">**Sablon az adatintegrációban**</span><span class="sxs-lookup"><span data-stu-id="fb05f-108">**Template in Data integration**</span></span>
- <span data-ttu-id="fb05f-109">Raktárak (a Fin and Ops megoldásból a Field Service megoldásba)</span><span class="sxs-lookup"><span data-stu-id="fb05f-109">Warehouses (Fin and Ops to Field Service)</span></span>

<span data-ttu-id="fb05f-110">**Feladat az adatintegrációs projektben**</span><span class="sxs-lookup"><span data-stu-id="fb05f-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="fb05f-111">Raktár</span><span class="sxs-lookup"><span data-stu-id="fb05f-111">Warehouse</span></span>

## <a name="entity-set"></a><span data-ttu-id="fb05f-112">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="fb05f-112">Entity set</span></span>
| <span data-ttu-id="fb05f-113">Field Service</span><span class="sxs-lookup"><span data-stu-id="fb05f-113">Field Service</span></span>    | <span data-ttu-id="fb05f-114">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="fb05f-114">Finance and Operations</span></span>                 |
|------------------|----------------------------------------|
| <span data-ttu-id="fb05f-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="fb05f-115">msdyn_warehouses</span></span> | <span data-ttu-id="fb05f-116">Raktárak</span><span class="sxs-lookup"><span data-stu-id="fb05f-116">Warehouses</span></span>                             |

## <a name="entity-flow"></a><span data-ttu-id="fb05f-117">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="fb05f-117">Entity flow</span></span>
<span data-ttu-id="fb05f-118">A Finance and Operations megoldásban létrehozott és kezelt raktárak a Common Data Service (CDS) adatintegrációs projekten keresztül szinkronizálhatók a Field Service megoldásba.</span><span class="sxs-lookup"><span data-stu-id="fb05f-118">Warehouses that are created and maintained in Finance and Operations can be synchronized to Field Service via a Common Data Service (CDS) Data integration project.</span></span> <span data-ttu-id="fb05f-119">A Field Service megoldásba szinkronizálni kívánt raktárak a speciális lekérdezés és szűrés segítségével vezérelhetők a projekten.</span><span class="sxs-lookup"><span data-stu-id="fb05f-119">The warehouses that you want to synchronize to Field Service can be controlled with the Advanced query and filtering on the project.</span></span> <span data-ttu-id="fb05f-120">A Finance and Operations megoldásból szinkronizáló raktárak a Field Service megoldásban vannak létrehoz úgy, hogy a **Külső karbantartású mező** **Igen** értékre van állítva, valamint a rekord csak olvashatóra van állítva.</span><span class="sxs-lookup"><span data-stu-id="fb05f-120">Warehouses that synchronize from Finance and Operations are created in Field Service with the **Is maintained externally** field set to **Yes** and the record is read only.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="fb05f-121">Field Service CRM megoldás</span><span class="sxs-lookup"><span data-stu-id="fb05f-121">Field Service CRM solution</span></span>
<span data-ttu-id="fb05f-122">A Field Service és a Finance and Operations közötti integrálás támogatásához további funkciók szükségesek a Field Service CRM megoldásból.</span><span class="sxs-lookup"><span data-stu-id="fb05f-122">To support the integration between Field Service and Finance and Operations, additional functionality from the Field Service CRM solution is required.</span></span> <span data-ttu-id="fb05f-123">A megoldásban **Külső karbantartású** mező hozzá lett adva a **Raktár (msdyn_warehouses)** entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="fb05f-123">In the solution, the **Is Maintained Externally** field has been added to the **Warehouse (msdyn_warehouses)** entity.</span></span> <span data-ttu-id="fb05f-124">Ennek a mezőnek a segítségével ellenőrizheti, hogy a raktár kezelése a Finance and Operations megoldásból történik, vagy csak a Field Service szolgáltatásban létezik.</span><span class="sxs-lookup"><span data-stu-id="fb05f-124">This field helps to identify if the warehouse is handled from Finance and Operations or if it only exists in Field Service.</span></span> <span data-ttu-id="fb05f-125">A beállítások a mezőben a következők lehetnek:</span><span class="sxs-lookup"><span data-stu-id="fb05f-125">The settings for this field include:</span></span>
- <span data-ttu-id="fb05f-126">**Igen** – A raktár a Finance and Operations szolgáltatásból származik, és nem lesz szerkeszthető a Sales szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="fb05f-126">**Yes** – The warehouse originated from Finance and Operations and won't be editable in Sales.</span></span>
- <span data-ttu-id="fb05f-127">**Nem** – A raktár megadása közvetlenül a Field Service megoldásban történt, és itt is tartják karban.</span><span class="sxs-lookup"><span data-stu-id="fb05f-127">**No** – The warehouse was entered directly in Field Service and is maintained here.</span></span>

<span data-ttu-id="fb05f-128">A **Külső karbantartású** mező segítségével szabályozhatja a készletszintek, a kiigazítások, az átvitelek és a munkarendelések használatának szinkronizálását.</span><span class="sxs-lookup"><span data-stu-id="fb05f-128">The **Is Externally Maintained** field helps control the synchronization of inventory levels, adjustments, transfers, and usage on work orders.</span></span> <span data-ttu-id="fb05f-129">Csak a **Külső karbantartású** = **Igen** beállítású raktárak használhatók közvetlen szinkronizáláshoz ugyanabba a raktárba a másik rendszerben.</span><span class="sxs-lookup"><span data-stu-id="fb05f-129">Only warehouses with **Is Externally Maintained** set to **Yes** can be used to synchronize directly to the same warehouse in the other system.</span></span> 

> [!NOTE]
> <span data-ttu-id="fb05f-130">Megjegyzés: Lehetőség van több raktár létrehozására a Field Service megoldásban (ahol a **Külsőleg karbantartott** = Nem), majd a leképezésükre egy raktárba a Finance and Operations megoldásban, a speciális lekérdezési és szűrési funkcióval.</span><span class="sxs-lookup"><span data-stu-id="fb05f-130">It is possible to create multiple warehouses in Field Service (with **Is Externally Maintained** = No) and then map them to a single warehouse in Finance and Operations, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="fb05f-131">Ez olyan helyzetekben használt, amikor azt szeretnénk, hogy a Field Service kezelje a részletes készletszintet, és csak frissítéseket küldjön a Finance and Operations megoldásba.</span><span class="sxs-lookup"><span data-stu-id="fb05f-131">This is used in situations where you want Field Service to master the detailed inventory level and just send updates to Finance and Operations.</span></span> <span data-ttu-id="fb05f-132">Ebben az esetben a Field Service nem kap készletszintű frissítéseket a Finance and Operations megoldásból.</span><span class="sxs-lookup"><span data-stu-id="fb05f-132">In this case, Field Service will not receive inventory-level updates from Finance and Operations.</span></span> <span data-ttu-id="fb05f-133">További információért lásd: [Készletátvitelek és szinkronizálása a Field Service alkalmazásból a Finance and Operations alkalmazásba](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) és [A Field Service szolgáltatásokban lévő munkarendelések szinkronizálása a Finance and Operations értékesítési rendeléseivel](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="fb05f-133">For additional information, see [Synchronize inventory adjustments from Field Service to Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) and [Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="fb05f-134">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="fb05f-134">Prerequisites and mapping setup</span></span>
### <a name="data-integration-project"></a><span data-ttu-id="fb05f-135">Adatintegrációs projekt</span><span class="sxs-lookup"><span data-stu-id="fb05f-135">Data Integration project</span></span>
<span data-ttu-id="fb05f-136">A raktárak szinkronizálása előtt ellenőrizze, hogy frissítése a speciális lekérdezés és szűrést a projekten, hogy csak azokat a raktárakat foglalja magában, amelyeket át akar vinni a Field Service megoldásból Finance and Operations megoldásba.</span><span class="sxs-lookup"><span data-stu-id="fb05f-136">Before synchronizing the warehouses, make sure to update the Advanced query and filtering on the project to only include the warehouses that you want to bring from Finance and Operations to Field Service.</span></span> <span data-ttu-id="fb05f-137">Vegye figyelembe, hogy szüksége lesz a raktárra a Field Service megoldásban az alkalmazásához a munkarendeléseken, a kiigazításokon és az átviteleken.</span><span class="sxs-lookup"><span data-stu-id="fb05f-137">Note that you will need the warehouse in Field Service to apply it on work orders, adjustments, and transfers.</span></span>  

<span data-ttu-id="fb05f-138">Ügyeljen arra, hogy az **integrációs kulcs** létezzen ehhez: **msdyn_warehouses**:</span><span class="sxs-lookup"><span data-stu-id="fb05f-138">To ensure that the **Integration key** exists for **msdyn_warehouses**:</span></span>
1. <span data-ttu-id="fb05f-139">Lépjen az Adatintegrációra.</span><span class="sxs-lookup"><span data-stu-id="fb05f-139">Go to Data Integration.</span></span>
2. <span data-ttu-id="fb05f-140">Válassza ki a **Csatlakozás beállítása** fület.</span><span class="sxs-lookup"><span data-stu-id="fb05f-140">Select the **Connection Set** tab.</span></span>
3. <span data-ttu-id="fb05f-141">Válassza ki a munkarendelés szinkronizálásához használt csatlakozási beállítást.</span><span class="sxs-lookup"><span data-stu-id="fb05f-141">Select the connection set used for work order synchronization.</span></span>
4. <span data-ttu-id="fb05f-142">Válassza ki az **Integrációs kulcs** fület.</span><span class="sxs-lookup"><span data-stu-id="fb05f-142">Select the **Integration key** tab.</span></span>
5. <span data-ttu-id="fb05f-143">Keresse meg a msdyn_warehouses elemet, és erősítse meg, hogy a **msdyn_name (név)** van hozzáadva.</span><span class="sxs-lookup"><span data-stu-id="fb05f-143">Find msdyn_warehouses and confirm that the key **msdyn_name (name)** is added.</span></span> <span data-ttu-id="fb05f-144">Ha nem látható, kattintson a **Kulcs hozzáadása** elemre a hozzáadáshoz, majd kattintson a **Mentés** elemre a lap tetején.</span><span class="sxs-lookup"><span data-stu-id="fb05f-144">If it is not shown, add it by clicking **Add key** and then click **Save** at the top of the page.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="fb05f-145">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="fb05f-145">Template mapping in Data integration</span></span>

<span data-ttu-id="fb05f-146">Az alábbi ábrán látható a sablonleképezés az Adatintegrálásban.</span><span class="sxs-lookup"><span data-stu-id="fb05f-146">The following illustration shows the template mapping in Data integration.</span></span>

### <a name="warehouses-fin-and-ops-to-field-service-warehouse"></a><span data-ttu-id="fb05f-147">Raktárak (a Fin and Ops megoldásból a Field Service megoldásba): Raktár</span><span class="sxs-lookup"><span data-stu-id="fb05f-147">Warehouses (Fin and Ops to Field Service): Warehouse</span></span>

<span data-ttu-id="fb05f-148">[![Sablonleképezés az adatintegrátorban](./media/Warehouse1.png)](./media/Warehouse1.png)</span><span class="sxs-lookup"><span data-stu-id="fb05f-148">[![Template mapping in Data integration](./media/Warehouse1.png)](./media/Warehouse1.png)</span></span>
