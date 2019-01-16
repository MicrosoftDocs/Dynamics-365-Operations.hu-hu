---
title: "Készletátvitelek és -kiigazítások szinkronizálása a Field Service alkalmazásból a Finance and Operations alkalmazásba"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a készletátvitelek és -kiigazítások szinkronizálására használhatók a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service között."
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
ms.openlocfilehash: 79a1cfac3fa94223cc9af73e758ce95fd47065c9
ms.contentlocale: hu-hu
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-inventory-adjustments-from-field-service-to-finance-and-operations"></a><span data-ttu-id="a19af-103">Készletátvitelek és szinkronizálása a Field Service alkalmazásból a Finance and Operations alkalmazásba</span><span class="sxs-lookup"><span data-stu-id="a19af-103">Synchronize inventory adjustments from Field Service to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="a19af-104">Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a készletátvitelek és -kiigazítások szinkronizálására használhatók a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service között.</span><span class="sxs-lookup"><span data-stu-id="a19af-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory adjustments and transfers from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="a19af-105">[![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span><span class="sxs-lookup"><span data-stu-id="a19af-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="a19af-106">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="a19af-106">Templates and tasks</span></span>
<span data-ttu-id="a19af-107">A következő sablon és a kapcsolódó feladatok a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service közötti aktuális készletkorrekciók szinkronizálásának futtatására használhatók.</span><span class="sxs-lookup"><span data-stu-id="a19af-107">The following template and underlying tasks are used to run synchronization of inventory adjustments and transfers from Microsoft Dynamics 365 for Field Service to Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="a19af-108">**A sablonok neve az adatintegrációban:**</span><span class="sxs-lookup"><span data-stu-id="a19af-108">**Name of the templates in Data integration:**</span></span>
- <span data-ttu-id="a19af-109">Készletkiigazítás (a Field Service megoldásból a Finance and Operations megoldásba)</span><span class="sxs-lookup"><span data-stu-id="a19af-109">Inventory Adjustment (Field Service to Finance and Operations)</span></span>
- <span data-ttu-id="a19af-110">Készletátvitelek (a Field Service megoldásból a Finance and Operations megoldásba)</span><span class="sxs-lookup"><span data-stu-id="a19af-110">Inventory Transfers (Field Service to Finance and Operations)</span></span>

<span data-ttu-id="a19af-111">**A feladatok nevei az adatintegrációs projektekben:**</span><span class="sxs-lookup"><span data-stu-id="a19af-111">**Names of the tasks in the Data integration projects:**</span></span>
- <span data-ttu-id="a19af-112">Készletkiigazítás</span><span class="sxs-lookup"><span data-stu-id="a19af-112">Inventory Adjustments</span></span>
- <span data-ttu-id="a19af-113">Készletátvitelek</span><span class="sxs-lookup"><span data-stu-id="a19af-113">Inventory Transfers</span></span>

## <a name="entity-set"></a><span data-ttu-id="a19af-114">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="a19af-114">Entity set</span></span>
| <span data-ttu-id="a19af-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="a19af-115">Field Service</span></span>                     | <span data-ttu-id="a19af-116">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a19af-116">Finance and Operations</span></span>                             |
|-----------------------------------|----------------------------------------------------|
| <span data-ttu-id="a19af-117">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="a19af-117">msdyn_inventoryadjustmentproducts</span></span> |   <span data-ttu-id="a19af-118">CDS készletkiigazítási napló fejlécei és sorai</span><span class="sxs-lookup"><span data-stu-id="a19af-118">CDS Inventory adjustment journal headers and lines</span></span> |
| <span data-ttu-id="a19af-119">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="a19af-119">msdyn_inventoryadjustmentproducts</span></span> | <span data-ttu-id="a19af-120">CDS készletátviteli napló fejlécei és sorai</span><span class="sxs-lookup"><span data-stu-id="a19af-120">CDS inventory transfer journal headers and lines</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="a19af-121">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="a19af-121">Entity flow</span></span>
<span data-ttu-id="a19af-122">A Field Service alkalmazásban végzett készletkiigazítások és átvitelek szinkronizálva lesznek a Finance and Operations alkalmazásba, miután a **Feladása állapota** Létrehozottról Feladottra lesz módosítva.</span><span class="sxs-lookup"><span data-stu-id="a19af-122">Inventory adjustments and transfers made in Field Service will synchronize to Finance and Operations, once the **Post status** is changed from Created to Posted.</span></span> <span data-ttu-id="a19af-123">Ekkor a korrekciós vagy átviteli rendelés zárolva lesz és írásvédetté válik, mivel a korrekciók vagy átvitelek beküldhetők a Finance and Operations számára, ezért ezeket nem lehet módosítani.</span><span class="sxs-lookup"><span data-stu-id="a19af-123">When this happen the adjustment or transfer order will be locked and become read-only, as adjustments and transfers might be posted in Finance and Operations and therefor can't be modified.</span></span>
<span data-ttu-id="a19af-124">A Finance and Operations alkalmazásban beállíthat egy kötegelt feladatot, hogy automatikusan beküldje a kiigazításokat és átviteli készletnaplókat az integrációba.</span><span class="sxs-lookup"><span data-stu-id="a19af-124">In Finance and Operations you can setup a batch job to automatically post the adjustments and transfer inventory journals generated with the integration.</span></span> <span data-ttu-id="a19af-125">A kötegelt feladat engedélyezésének előfeltétel alább találja.</span><span class="sxs-lookup"><span data-stu-id="a19af-125">See prerequisite below for details on how to enable the batch job.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="a19af-126">Field Service CRM megoldás</span><span class="sxs-lookup"><span data-stu-id="a19af-126">Field Service CRM solution</span></span> 
<span data-ttu-id="a19af-127">A Készletegység mezőt hozzá kell adni a Termékentitáshoz.</span><span class="sxs-lookup"><span data-stu-id="a19af-127">The Inventory Unit field has been added to the Product entity.</span></span> <span data-ttu-id="a19af-128">Ez a mező szükséges, hiszen az értékesítési és készletegység nem mindig ugyanaz az Operations alkalmazásban és az Operations raktárkészletéhez szükséges a készletegység.</span><span class="sxs-lookup"><span data-stu-id="a19af-128">This field is needed since the Sales and Inventory Unit is not always the same in Operations, and for the Warehouse Inventory in operations we need the Inventory Unit.</span></span>
<span data-ttu-id="a19af-129">Amikor beállít egy Terméket egy Raktárkiigazítási termékhez a Készletkiigazításokhoz és a Készletátvitelekhez is az egység a Termékkészlet termékértékből lesz lekérve.</span><span class="sxs-lookup"><span data-stu-id="a19af-129">When you set the Product on an Inventory Adjustment Product for both Inventory Adjustments and Inventory Transfers the Unit will be fetched from the Products Inventory Product value.</span></span> <span data-ttu-id="a19af-130">Ha egy érték megtalálható az egység mező zárolva lesz a készletkiigazítás termékben</span><span class="sxs-lookup"><span data-stu-id="a19af-130">If a value is found the Unit field will be locked on the Inventory Adjustment Product</span></span>

<span data-ttu-id="a19af-131">A feladás állapota mező hozzá lett adva a Készletkiigazítás és a Készletátvitel entitáshoz is.</span><span class="sxs-lookup"><span data-stu-id="a19af-131">The Post Status field has been added to both the Inventory Adjustment entity and the Inventory Transfer entity.</span></span> <span data-ttu-id="a19af-132">Ezzel a mezővel szűrhető, hogy mikor lett a kiigazítás vagy átvitel elküldve az Operations alkalmazásnak.</span><span class="sxs-lookup"><span data-stu-id="a19af-132">This field is used as a filter for when a adjustment or transfer is sent to Operations.</span></span> <span data-ttu-id="a19af-133">A mező alapértelmezett Létrehozott(1), ekkor az nincs átküldve az Operations alkalmazásnak.</span><span class="sxs-lookup"><span data-stu-id="a19af-133">The field is defaulted to Created (1) and its then not sent over to Operations.</span></span> <span data-ttu-id="a19af-134">Ha Feladva (2) értékre módosítja, akkor át lesz küldve az Operations alkalmazásnak, de többé nem módosíthat semmit a Kiigazítás vagy Átvitel terén, és nem adhat hozzá új sorokat.</span><span class="sxs-lookup"><span data-stu-id="a19af-134">Ones you change is to Posted (2) It is sent over to operations, but you will then no longer be able to change anything in the Adjustment or Transfer or add any new lines to it.</span></span>
<span data-ttu-id="a19af-135">A Számsorozat mező hozzá lett adva a Készletkiigazítás termékentitáshoz.</span><span class="sxs-lookup"><span data-stu-id="a19af-135">The Number Sequence field has been added to the Inventory Adjustment Product entity.</span></span> <span data-ttu-id="a19af-136">Ezt a mezőt segít abban, hogy az integrációnak egyedi száma legyen, hogy az integráció tudja, hogy mikor végezzen létrehozást, és mikor végezzen frissítést.</span><span class="sxs-lookup"><span data-stu-id="a19af-136">This field helps the integration to have a Unique number, so the integration knows when to do creates and when to do updates.</span></span> <span data-ttu-id="a19af-137">Az első Készletkiigazítási terméket létrehozásakor az létrehoz egy új rekordot a P2C AutoNumbe entitásban, hogy megtartsa a számsorozatot és a használt előtagot.</span><span class="sxs-lookup"><span data-stu-id="a19af-137">When you create your first Inventory Adjustment Product it will create a new record in the P2C AutoNumber entity to maintain the number series and the prefix that is used.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="a19af-138">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="a19af-138">Prerequisites and mapping setup</span></span>

### <a name="in-finance-and-operations"></a><span data-ttu-id="a19af-139">A Finance and Operations alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="a19af-139">In Finance and Operations</span></span>
<span data-ttu-id="a19af-140">Az integráció által generált integrációs készletnaplókat automatikusan kötegelt feladatként fel lehet adni.</span><span class="sxs-lookup"><span data-stu-id="a19af-140">The integration inventory journals generated by the integration can automatically be posted with a batch job.</span></span> <span data-ttu-id="a19af-141">Ez a következő helyről engedélyezhető: Készletkezelés > Ismétlődő feladatok > CDS-integráció > Integrációs készlet naplóinak feladása</span><span class="sxs-lookup"><span data-stu-id="a19af-141">This is enabled from: Inventory management > Periodic tasks > CDS integration > Post integration inventory journals</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="a19af-142">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="a19af-142">Template mapping in Data integration</span></span>

<span data-ttu-id="a19af-143">Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.</span><span class="sxs-lookup"><span data-stu-id="a19af-143">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="inventory-adjustment-field-service-to-finance-and-operations-inventory-adjustment"></a><span data-ttu-id="a19af-144">Készletkiigazítás (a Field Service megoldásból a Finance and Operations megoldásba): Készletkiigazítás</span><span class="sxs-lookup"><span data-stu-id="a19af-144">Inventory Adjustment (Field Service to Finance and Operations): Inventory Adjustment</span></span>

<span data-ttu-id="a19af-145">[![Sablonleképezés az adatintegrátorban](./media/FSAdj1.png)](./media/FSAdj1.png)</span><span class="sxs-lookup"><span data-stu-id="a19af-145">[![Template mapping in Data integration](./media/FSAdj1.png)](./media/FSAdj1.png)</span></span>


### <a name="inventory-transfer-field-service-to-finance-and-operations-inventory-transfer"></a><span data-ttu-id="a19af-146">Készletátvitel (a Field Service megoldásból a Finance and Operations megoldásba): Készletátvitel</span><span class="sxs-lookup"><span data-stu-id="a19af-146">Inventory Transfer (Field Service to Finance and Operations): Inventory Transfer</span></span>

<span data-ttu-id="a19af-147">[![Sablonleképezés az adatintegrátorban](./media/FSTrans1.png)](./media/FSTrans1.png)</span><span class="sxs-lookup"><span data-stu-id="a19af-147">[![Template mapping in Data integration](./media/FSTrans1.png)](./media/FSTrans1.png)</span></span>

