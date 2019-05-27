---
title: Készletátvitelek és -kiigazítások szinkronizálása a Field Service alkalmazásból a Finance and Operations alkalmazásba
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Microsoft Dynamics 365 for Finance and Operations készletkorrekcióinak és átviteleinek közvetlenül a Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.
author: ChristianRytt
manager: AnnBe
ms.date: 04/30/2019
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
ms.openlocfilehash: e94fa87c2f8b66574d6c5b2930cebf2e1b144fea
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1536296"
---
# <a name="synchronize-inventory-adjustments-from-field-service-to-finance-and-operations"></a><span data-ttu-id="6d3d8-103">Készletátvitelek és szinkronizálása a Field Service alkalmazásból a Finance and Operations alkalmazásba</span><span class="sxs-lookup"><span data-stu-id="6d3d8-103">Synchronize inventory adjustments from Field Service to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="6d3d8-104">Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Microsoft Dynamics 365 for Finance and Operations készletkorrekcióinak és átviteleinek közvetlenül a Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.</span><span class="sxs-lookup"><span data-stu-id="6d3d8-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory adjustments and transfers from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="6d3d8-105">[![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span><span class="sxs-lookup"><span data-stu-id="6d3d8-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="6d3d8-106">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="6d3d8-106">Templates and tasks</span></span>
<span data-ttu-id="6d3d8-107">A következő sablon és a mögöttes feladatok, amelyek a Microsoft Dynamics 365 for Field Service készletkorrekcióinak és átviteleinek közvetlenül a Microsoft Dynamics 365 for Finance and Operations szolgáltatásba történő szinkronizálására használatosak.</span><span class="sxs-lookup"><span data-stu-id="6d3d8-107">The following template and underlying tasks are used to synchronize inventory adjustments and transfers from Microsoft Dynamics 365 for Field Service to Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="6d3d8-108">**Sablonok az adatintegrációban**</span><span class="sxs-lookup"><span data-stu-id="6d3d8-108">**Templates in Data integration**</span></span>
- <span data-ttu-id="6d3d8-109">Készletkiigazítás (a Field Service megoldásból a Fin and Ops megoldásba)</span><span class="sxs-lookup"><span data-stu-id="6d3d8-109">Inventory Adjustment (Field Service to Fin and Ops)</span></span>
- <span data-ttu-id="6d3d8-110">Készletátvitelek (a Field Service megoldásból a Fin and Ops megoldásba)</span><span class="sxs-lookup"><span data-stu-id="6d3d8-110">Inventory Transfers (Field Service to Fin and Ops)</span></span>

<span data-ttu-id="6d3d8-111">**Feladatok az adatintegrációs projektekben:**</span><span class="sxs-lookup"><span data-stu-id="6d3d8-111">**Tasks in the Data integration projects**</span></span>
- <span data-ttu-id="6d3d8-112">Készletkiigazítás</span><span class="sxs-lookup"><span data-stu-id="6d3d8-112">Inventory Adjustments</span></span>
- <span data-ttu-id="6d3d8-113">Készletátvitelek</span><span class="sxs-lookup"><span data-stu-id="6d3d8-113">Inventory Transfers</span></span>

## <a name="entity-set"></a><span data-ttu-id="6d3d8-114">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="6d3d8-114">Entity set</span></span>
| <span data-ttu-id="6d3d8-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="6d3d8-115">Field Service</span></span>                     | <span data-ttu-id="6d3d8-116">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="6d3d8-116">Finance and Operations</span></span>                             |
|-----------------------------------|----------------------------------------------------|
| <span data-ttu-id="6d3d8-117">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="6d3d8-117">msdyn_inventoryadjustmentproducts</span></span> |   <span data-ttu-id="6d3d8-118">CDS készletkiigazítási napló fejlécei és sorai</span><span class="sxs-lookup"><span data-stu-id="6d3d8-118">CDS Inventory adjustment journal headers and lines</span></span> |
| <span data-ttu-id="6d3d8-119">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="6d3d8-119">msdyn_inventoryadjustmentproducts</span></span> | <span data-ttu-id="6d3d8-120">CDS készletátviteli napló fejlécei és sorai</span><span class="sxs-lookup"><span data-stu-id="6d3d8-120">CDS inventory transfer journal headers and lines</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="6d3d8-121">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="6d3d8-121">Entity flow</span></span>
<span data-ttu-id="6d3d8-122">A Field Service alkalmazásban végzett készletkiigazítások és átvitelek szinkronizálva lesznek a Finance and Operations alkalmazásba, miután a **Feladása állapota** **Létrehozottról** **Feladottra** lesz módosítva.</span><span class="sxs-lookup"><span data-stu-id="6d3d8-122">Inventory adjustments and transfers made in Field Service will synchronize to Finance and Operations after the **Post status** changes from **Created** to **Posted**.</span></span> <span data-ttu-id="6d3d8-123">Amikor ez megtörténik a kiigazítás vagy átmozgatási rendelés zárolva lesz, és csak olvasható.</span><span class="sxs-lookup"><span data-stu-id="6d3d8-123">When this occurs, the adjustment or the transfer order will be locked and become read only.</span></span> <span data-ttu-id="6d3d8-124">Ez azt jelenti, átviteleket és a kiigazításokat is fel lehet adni a Finance and Operations rendszerbe, de nem lehet azokat módosítani.</span><span class="sxs-lookup"><span data-stu-id="6d3d8-124">This means that adjustments and transfers can be posted in Finance and Operations, but cannot be modified.</span></span> <span data-ttu-id="6d3d8-125">A Finance and Operations alkalmazásban beállíthat egy kötegelt feladatot, hogy az automatikusan beküldje a kiigazításokat és átviteli készletnaplókat az integrációba.</span><span class="sxs-lookup"><span data-stu-id="6d3d8-125">In Finance and Operations, you can set up a batch job to automatically post the adjustments and transfer inventory journals that have been generated during the integration.</span></span> <span data-ttu-id="6d3d8-126">Tekintse meg kötegelt feladat engedélyezésének előfeltételeit.</span><span class="sxs-lookup"><span data-stu-id="6d3d8-126">See the following prerequisites for details on how to enable the batch job.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="6d3d8-127">Field Service CRM megoldás</span><span class="sxs-lookup"><span data-stu-id="6d3d8-127">Field Service CRM solution</span></span> 
<span data-ttu-id="6d3d8-128">A **Készletegység** mezőt hozzá kell adni a **Termék** entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="6d3d8-128">The **Inventory unit** field has been added to the **Product** entity.</span></span> <span data-ttu-id="6d3d8-129">Ez a mező szükséges, mivel az Értékesítési és készletegység nem mindig ugyanaz a Finance and Operations alkalmazásban és az Finance and Operations raktárkészletéhez szükséges a készletegység.</span><span class="sxs-lookup"><span data-stu-id="6d3d8-129">This field is needed because the Sales and Inventory unit is not always the same in Finance and Operations, and the Inventory Unit is needed for the Warehouse Inventory in Finance and Operations.</span></span>
<span data-ttu-id="6d3d8-130">Amikor beállít egy terméket egy Raktárkiigazítási termékhez a Készletkiigazításokhoz és a Készletátvitelekhez is az egység a Termékkészlet termékértékből lesz lekérve.</span><span class="sxs-lookup"><span data-stu-id="6d3d8-130">When you set the product on an Inventory adjustment product for both Inventory adjustments and Inventory transfers, the unit will be fetched from the inventory product value.</span></span> <span data-ttu-id="6d3d8-131">Ha egy érték megtalálható az **Egység** mező zárolva lesz a készletkiigazítás termékben</span><span class="sxs-lookup"><span data-stu-id="6d3d8-131">If a value is found, the **Unit** field will be locked on the Inventory adjustment product.</span></span>

<span data-ttu-id="6d3d8-132">A **Feladás állapota** mező hozzá lett adva a **Készletkiigazítás** és a **Készletátvitel** entitáshoz is.</span><span class="sxs-lookup"><span data-stu-id="6d3d8-132">The **Post status** field has been added to both the **Inventory adjustment** entity and the **Inventory transfer** entity.</span></span> <span data-ttu-id="6d3d8-133">Ezzel a mezővel szűrhető, hogy mikor lett egy kiigazítás vagy átvitel elküldve a Finance and Operations alkalmazásnak.</span><span class="sxs-lookup"><span data-stu-id="6d3d8-133">This field is used as a filter when an adjustment or transfer is sent to Finance and Operations.</span></span> <span data-ttu-id="6d3d8-134">Ezen mező alapértelmezett értéke Létrehozott (1), de nincs elküldve a Finance and Operations számára.</span><span class="sxs-lookup"><span data-stu-id="6d3d8-134">The default for this field is Created (1), however it is not sent to Finance and Operations.</span></span> <span data-ttu-id="6d3d8-135">Ha Feladva (2) értékre módosítja, akkor át lesz küldve a Finance and Operations alkalmazásnak, de többé nem módosíthat semmit a kiigazítás vagy átvitel terén, és nem adhat hozzá új sorokat.</span><span class="sxs-lookup"><span data-stu-id="6d3d8-135">When you update the value to Posted (2), it is sent to Finance and Operations, but after that you will no longer be able to change the adjustment or transfer or add new lines.</span></span>

<span data-ttu-id="6d3d8-136">A **Számsorozat** mező hozzá lett adva a **Készletkiigazítás termékentitáshoz**.</span><span class="sxs-lookup"><span data-stu-id="6d3d8-136">The **Number sequence** field has been added to the **Inventory adjustment product** entity.</span></span> <span data-ttu-id="6d3d8-137">Ez a mező gondoskodik arról, hogy az integrációnak egyedi száma legyen, hogy az integráció létrehozhassa és frissíthesse a kiigazítást.</span><span class="sxs-lookup"><span data-stu-id="6d3d8-137">This field ensures that the integration has a unique number, so the integration can create and update the adjustment.</span></span> <span data-ttu-id="6d3d8-138">Az első készletkiigazítási termék létrehozásakor az létrehoz egy új rekordot a **P2C AutoNumbe** entitásban, hogy megtartsa a számsorozatot és a használt előtagot.</span><span class="sxs-lookup"><span data-stu-id="6d3d8-138">When you create your first inventory adjustment product, it will create a new record in the **P2C AutoNumber** entity to maintain the number series and the prefix that is used.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="6d3d8-139">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="6d3d8-139">Prerequisites and mapping setup</span></span>

### <a name="finance-and-operations"></a><span data-ttu-id="6d3d8-140">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="6d3d8-140">Finance and Operations</span></span>
<span data-ttu-id="6d3d8-141">Az integráció által generált integrációs készletnaplókat automatikusan kötegelt feladat használatával is fel lehet adni.</span><span class="sxs-lookup"><span data-stu-id="6d3d8-141">The integration inventory journals generated by the integration can automatically be posted using a batch job.</span></span> <span data-ttu-id="6d3d8-142">Ez a következő helyről engedélyezhető: **Készletkezelés > Ismétlődő feladatok > CDS-integráció > Integrációs készlet naplóinak feladása**.</span><span class="sxs-lookup"><span data-stu-id="6d3d8-142">This is enabled from **Inventory management > Periodic tasks > CDS integration > Post integration inventory journals**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="6d3d8-143">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="6d3d8-143">Template mapping in Data integration</span></span>

<span data-ttu-id="6d3d8-144">Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.</span><span class="sxs-lookup"><span data-stu-id="6d3d8-144">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="inventory-adjustment-field-service-to-fin-and-ops-inventory-adjustment"></a><span data-ttu-id="6d3d8-145">Készletkiigazítás (a Field Service megoldásból a Fin and Ops megoldásba): Készletkiigazítás</span><span class="sxs-lookup"><span data-stu-id="6d3d8-145">Inventory adjustment (Field Service to Fin and Ops): Inventory adjustment</span></span>

<span data-ttu-id="6d3d8-146">[![Sablonleképezés az adatintegrátorban](./media/FSAdj1.png)](./media/FSAdj1.png)</span><span class="sxs-lookup"><span data-stu-id="6d3d8-146">[![Template mapping in Data integration](./media/FSAdj1.png)](./media/FSAdj1.png)</span></span>


### <a name="inventory-transfer-field-service-to-fin-and-ops-inventory-transfer"></a><span data-ttu-id="6d3d8-147">Készletátvitel (a Field Service megoldásból a Fin and Ops megoldásba): Készletátvitel</span><span class="sxs-lookup"><span data-stu-id="6d3d8-147">Inventory transfer (Field Service to Fin and Ops): Inventory transfer</span></span>

<span data-ttu-id="6d3d8-148">[![Sablonleképezés az adatintegrátorban](./media/FSTrans1.png)](./media/FSTrans1.png)</span><span class="sxs-lookup"><span data-stu-id="6d3d8-148">[![Template mapping in Data integration](./media/FSTrans1.png)](./media/FSTrans1.png)</span></span>
