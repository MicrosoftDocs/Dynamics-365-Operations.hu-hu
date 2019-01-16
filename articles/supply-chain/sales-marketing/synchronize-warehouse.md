---
title: "Raktárak szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service közötti raktárszinkronizálásra használhatók."
author: ChristianRytt
manager: AnnBe
ms.date: 10/10/2018
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
ms.openlocfilehash: eb8ba6051777e27bd44504a8160118e8096b1435
ms.contentlocale: hu-hu
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-warehouses-from-finance-and-operations-to-field-service"></a><span data-ttu-id="def4a-103">Raktárak szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba</span><span class="sxs-lookup"><span data-stu-id="def4a-103">Synchronize warehouses from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="def4a-104">Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service közötti raktárszinkronizálásra használhatók.</span><span class="sxs-lookup"><span data-stu-id="def4a-104">This topic discusses the templates and underlying tasks that are used to synchronize warehouses from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="def4a-105">[![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span><span class="sxs-lookup"><span data-stu-id="def4a-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="def4a-106">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="def4a-106">Templates and tasks</span></span>
<span data-ttu-id="def4a-107">A következő sablon és a kapcsolódó feladatok a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service közötti raktárszinkronizálás futtatására használhatók.</span><span class="sxs-lookup"><span data-stu-id="def4a-107">The following template and underlying tasks are used to run synchronization of warehouses from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="def4a-108">**A sablon neve az adatintegrációban:**</span><span class="sxs-lookup"><span data-stu-id="def4a-108">**Name of the template in Data integration:**</span></span>
- <span data-ttu-id="def4a-109">Raktárak (a Finance and Operations megoldásból a Field Service megoldásba)</span><span class="sxs-lookup"><span data-stu-id="def4a-109">Warehouses (Finance and Operations to Field Service)</span></span>

<span data-ttu-id="def4a-110">**A feladatok nevei az adatintegrációs projektben:**</span><span class="sxs-lookup"><span data-stu-id="def4a-110">**Names of the tasks in the Data integration project:**</span></span>
- <span data-ttu-id="def4a-111">Raktár</span><span class="sxs-lookup"><span data-stu-id="def4a-111">Warehouse</span></span>

## <a name="entity-set"></a><span data-ttu-id="def4a-112">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="def4a-112">Entity set</span></span>
| <span data-ttu-id="def4a-113">Field Service</span><span class="sxs-lookup"><span data-stu-id="def4a-113">Field Service</span></span>    | <span data-ttu-id="def4a-114">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="def4a-114">Finance and Operations</span></span>                 |
|------------------|----------------------------------------|
| <span data-ttu-id="def4a-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="def4a-115">msdyn_warehouses</span></span> | <span data-ttu-id="def4a-116">Raktárak</span><span class="sxs-lookup"><span data-stu-id="def4a-116">Warehouses</span></span>                             |

## <a name="entity-flow"></a><span data-ttu-id="def4a-117">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="def4a-117">Entity flow</span></span>
<span data-ttu-id="def4a-118">A Finance and Operations megoldásban létrehozott és kezelt raktárak a Common Data Service (CDS) adatintegrációs projekten keresztül szinkronizálhatók a Field Service megoldásba.</span><span class="sxs-lookup"><span data-stu-id="def4a-118">Warehouses that are created and maintained in Finance and Operations can be synchronized to Field Service via a Common Data Service (CDS) Data integration project.</span></span> <span data-ttu-id="def4a-119">A Field Service megoldásba szinkronizáló kívánt raktárak a speciális lekérdezés és szűrés segítségével vezérelhetők a projekten.</span><span class="sxs-lookup"><span data-stu-id="def4a-119">The desired warehouses that synchronize to Field Service can be controlled with the Advanced query and filtering on the project.</span></span> <span data-ttu-id="def4a-120">A Finance and Operations megoldásból szinkronizáló raktárak a Field Service megoldásban vannak létrehoz úgy, hogy a Külső karbantartású mező Igen értékre van állítva, valamint a rekord csak olvashatóra van állítva.</span><span class="sxs-lookup"><span data-stu-id="def4a-120">Warehouses that synchronize from Finance and Operations are created in Field Service with the field Is maintained externally set to Yes and the record is made read only.</span></span>
<span data-ttu-id="def4a-121">Field Service CRM-megoldás A Field Service és a Finance and Operations közötti integrálás támogatásához további funkciók szükségesek a Field Service CRM megoldásból.</span><span class="sxs-lookup"><span data-stu-id="def4a-121">Field Service CRM solution To support the integration between Field Service and Finance and Operations, additional functionality from the Field Service CRM solution is required.</span></span> <span data-ttu-id="def4a-122">A megoldás a következő változásokat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="def4a-122">The solution includes the following changes.</span></span>
<span data-ttu-id="def4a-123">A **Külső karbantartású** mező hozzá lett adva a **Raktár (msdyn_warehouses)** entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="def4a-123">The field **Is Maintained Externally** has been added to the **Warehouse (msdyn_warehouses)** entity.</span></span> <span data-ttu-id="def4a-124">Ennek a mezőnek a segítségével ellenőrizheti, hogy a raktár kezelése az Operations megoldásból történik, vagy csak a Field Service szolgáltatásban létezik.</span><span class="sxs-lookup"><span data-stu-id="def4a-124">This field helps to identify If the Warehouse is handled from Operations or if It only exists in Field Service.</span></span>
- <span data-ttu-id="def4a-125">Igen – A raktár a Finance and Operations szolgáltatásból származik, és nem lesz szerkeszthető a Sales szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="def4a-125">Yes – The warehouse originated from Finance and Operations and won't be editable in Sales.</span></span>
- <span data-ttu-id="def4a-126">Nem – A raktár megadása közvetlenül a Field Service megoldásban történt, és itt is tartják karban.</span><span class="sxs-lookup"><span data-stu-id="def4a-126">No – The warehouse was entered directly in Field Service and is maintained here.</span></span>

<span data-ttu-id="def4a-127">A **Külső karbantartású** mező segítségével szabályozhatja a készletszintek, a kiigazítások, az átvitelek és a munkarendelések használatának szinkronizálását.</span><span class="sxs-lookup"><span data-stu-id="def4a-127">The **Is Externally Maintained** field helps control the synchronization of inventory levels, adjustments, transfers and usage on work orders.</span></span> <span data-ttu-id="def4a-128">Csak a **Külső karbantartású** = Igen beállítású raktárak használhatók közvetlen szinkronizáláshoz ugyanabba a raktárba a másik rendszerben.</span><span class="sxs-lookup"><span data-stu-id="def4a-128">Only warehouses with **Is Externally Maintained** = Yes can be used to synchronize directly to the same warehouse in the other system.</span></span> 

<span data-ttu-id="def4a-129">Megjegyzés: Lehetőség van több raktár létrehozására a Field Service megoldásban (ahol a **Külsőleg karbantartott** = Nem), majd a leképezésükre egy raktárba a Finance and Operations megoldásban, a speciális lekérdezési és szűrési funkcióval.</span><span class="sxs-lookup"><span data-stu-id="def4a-129">Note: It is possible to create multiple warehouses in Field Services (with **Is Externally Maintained** = No) and then map them to a single warehouse in Finance and Operations, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="def4a-130">Ez olyan helyzetekben használt, amikor azt szeretnénk, hogy a Field Service kezelje a részletes készletszintet, és csak frissítéseket küldjön a Finance and Operations megoldásba.</span><span class="sxs-lookup"><span data-stu-id="def4a-130">This is used in situations where you want Field service to master the detailed inventory level and just send updates to Finance and Operations.</span></span> <span data-ttu-id="def4a-131">Ebben az esetben a Field Service nem kap készletszint-frissítéseket a Finance and Operations megoldásból.</span><span class="sxs-lookup"><span data-stu-id="def4a-131">In this case Field service will not receive inventory level updates from Finance and Operations.</span></span> <span data-ttu-id="def4a-132">További információért lásd: Készletátvitelek és szinkronizálása a Field Service alkalmazásból a Finance and Operations alkalmazásba és A Field Service szolgáltatásokban lévő munkarendelések szinkronizálása a Finance and Operations értékesítési rendeléseivel.</span><span class="sxs-lookup"><span data-stu-id="def4a-132">See additional information in Synchronize inventory adjustments from Field Service to Finance and Operations and Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="def4a-133">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="def4a-133">Prerequisites and mapping setup</span></span>
### <a name="in-the-data-integration-project"></a><span data-ttu-id="def4a-134">Az adatintegrációs projektben</span><span class="sxs-lookup"><span data-stu-id="def4a-134">In the Data Integration project</span></span>
<span data-ttu-id="def4a-135">A raktárak szinkronizálás előtt ellenőrizze, hogy frissítése a speciális lekérdezés és szűrést a projekten, hogy csak azokat a raktárakat foglalja magában, amelyeket át akar vinni a Field Service megoldásból Finance and Operations megoldásba.</span><span class="sxs-lookup"><span data-stu-id="def4a-135">Before synchronization of the warehouses make sure to update the Advanced query and filtering on the project to only include the warehouses that you want to bring from Finance and Operations to Field Service.</span></span> <span data-ttu-id="def4a-136">Vegye figyelembe, hogy szüksége lesz a raktárra a Field Service megoldásban az alkalmazásához a munkarendeléseken, a kiigazításokon és az átviteleken.</span><span class="sxs-lookup"><span data-stu-id="def4a-136">Note that you will need the warehouse in Field Service to apply it on work orders, adjustments and transfers.</span></span>  

<span data-ttu-id="def4a-137">Ügyeljen arra, hogy az **integrációs kulcs** létezzen ehhez: **msdyn_warehouses**</span><span class="sxs-lookup"><span data-stu-id="def4a-137">Ensure the **Integration key** exist for **msdyn_warehouses**</span></span>
1. <span data-ttu-id="def4a-138">Lépjen az Adatintegrációra</span><span class="sxs-lookup"><span data-stu-id="def4a-138">Go to Data Integration</span></span>
2. <span data-ttu-id="def4a-139">Válassza ki a **Csatlakozás beállítása** fület</span><span class="sxs-lookup"><span data-stu-id="def4a-139">Select **Connection Set** tab</span></span>
3. <span data-ttu-id="def4a-140">Válassza ki a munkarendelés szinkronizálásához használt csatlakozási beállítást.</span><span class="sxs-lookup"><span data-stu-id="def4a-140">Select the Connection set used for Work order synchronization</span></span>
4. <span data-ttu-id="def4a-141">Válassza ki az **Integrációs kulcs** fület</span><span class="sxs-lookup"><span data-stu-id="def4a-141">Select **Integration key** tab</span></span>
5. <span data-ttu-id="def4a-142">Keresse meg a msdyn_warehouses elemet, és ügyeljen arra, hogy a **msdyn_name (név)** legyen hozzáadva.</span><span class="sxs-lookup"><span data-stu-id="def4a-142">Find msdyn_warehouses and check that the key **msdyn_name (name)** is added.</span></span> <span data-ttu-id="def4a-143">Ha nem látható, kattintson a **Kulcs hozzáadása** elemre a hozzáadáshoz, majd kattintson a **Mentés** elemre a lap tetején.</span><span class="sxs-lookup"><span data-stu-id="def4a-143">If it is not shown, add it by click **Add key** and click **Save** in the top of the page</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="def4a-144">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="def4a-144">Template mapping in Data integration</span></span>

<span data-ttu-id="def4a-145">Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.</span><span class="sxs-lookup"><span data-stu-id="def4a-145">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="warehouses-finance-and-operations-to-field-service-warehouse"></a><span data-ttu-id="def4a-146">Raktárak (a Finance and Operations megoldásból a Field Service megoldásba): Raktár</span><span class="sxs-lookup"><span data-stu-id="def4a-146">Warehouses (Finance and Operations to Field Service): Warehouse</span></span>

<span data-ttu-id="def4a-147">[![Sablonleképezés az adatintegrátorban](./media/Warehouse1.png)](./media/Warehouse1.png)</span><span class="sxs-lookup"><span data-stu-id="def4a-147">[![Template mapping in Data integration](./media/Warehouse1.png)](./media/Warehouse1.png)</span></span>

