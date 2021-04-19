---
title: Készletátvitelek és -kiigazítások szinkronizálása a Field Service alkalmazásból a Supply Chain Management alkalmazásba
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Supply Chain Management készletkorrekcióinak és átviteleinek közvetlenül a Dynamics 365 Field Service szolgáltatásba történő szinkronizálására használatosak.
author: ChristianRytt
ms.date: 04/30/2019
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
ms.openlocfilehash: 9f3bfe950446a6e87e34c32d2593cba0af84d8e8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838981"
---
# <a name="synchronize-inventory-transfers-and-adjustments-from-field-service-to-supply-chain-management"></a><span data-ttu-id="14ca4-103">Készletátvitelek és -kiigazítások szinkronizálása a Field Service alkalmazásból a Supply Chain Management alkalmazásba</span><span class="sxs-lookup"><span data-stu-id="14ca4-103">Synchronize inventory transfers and adjustments from Field Service to Supply Chain Management</span></span>

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="14ca4-104">Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Supply Chain Management készletkorrekcióinak és átviteleinek közvetlenül a Dynamics 365 Field Service szolgáltatásba történő szinkronizálására használatosak.</span><span class="sxs-lookup"><span data-stu-id="14ca4-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory adjustments and transfers from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="14ca4-105">[![Üzleti folyamatok szinkronizálása a Supply Chain Management és a Field Service között](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span><span class="sxs-lookup"><span data-stu-id="14ca4-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="14ca4-106">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="14ca4-106">Templates and tasks</span></span>
<span data-ttu-id="14ca4-107">A következő sablonokat és alapul szolgáló feladatokat használják a tényleges készletkiigazítások és -átvitelek szinkronizálásához a Field Service szolgáltatásból a Supply Chain Management szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="14ca4-107">The following template and underlying tasks are used to synchronize inventory adjustments and transfers from Field Service to Supply Chain Management.</span></span>

<span data-ttu-id="14ca4-108">**Sablonok az adatintegrációban**</span><span class="sxs-lookup"><span data-stu-id="14ca4-108">**Templates in Data integration**</span></span>
- <span data-ttu-id="14ca4-109">Készletkiigazítás (Field Service-ből Supply Chain Management szolgáltatásba)</span><span class="sxs-lookup"><span data-stu-id="14ca4-109">Inventory Adjustment (Field Service to Supply Chain Management)</span></span>
- <span data-ttu-id="14ca4-110">Készletátvitel (Field Service-ből Supply Chain Management szolgáltatásba)</span><span class="sxs-lookup"><span data-stu-id="14ca4-110">Inventory Transfers (Field Service to Supply Chain Management)</span></span>

<span data-ttu-id="14ca4-111">**Feladatok az adatintegrációs projektekben:**</span><span class="sxs-lookup"><span data-stu-id="14ca4-111">**Tasks in the Data integration projects**</span></span>
- <span data-ttu-id="14ca4-112">Készletkiigazítás</span><span class="sxs-lookup"><span data-stu-id="14ca4-112">Inventory Adjustments</span></span>
- <span data-ttu-id="14ca4-113">Készletátvitelek</span><span class="sxs-lookup"><span data-stu-id="14ca4-113">Inventory Transfers</span></span>

## <a name="table-set"></a><span data-ttu-id="14ca4-114">Táblakészlet</span><span class="sxs-lookup"><span data-stu-id="14ca4-114">Table set</span></span>
| <span data-ttu-id="14ca4-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="14ca4-115">Field Service</span></span>                     | <span data-ttu-id="14ca4-116">Ellátásilánc-kezelés</span><span class="sxs-lookup"><span data-stu-id="14ca4-116">Supply Chain Management</span></span>                          |
|-----------------------------------|----------------------------------------------------|
| <span data-ttu-id="14ca4-117">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="14ca4-117">msdyn_inventoryadjustmentproducts</span></span> | <span data-ttu-id="14ca4-118">Dataverse készletkiigazítási napló fejlécei és sorai</span><span class="sxs-lookup"><span data-stu-id="14ca4-118">Dataverse Inventory adjustment journal headers and lines</span></span> |
| <span data-ttu-id="14ca4-119">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="14ca4-119">msdyn_inventoryadjustmentproducts</span></span> | <span data-ttu-id="14ca4-120">Dataverse készletátviteli napló fejlécei és sorai</span><span class="sxs-lookup"><span data-stu-id="14ca4-120">Dataverse inventory transfer journal headers and lines</span></span>   |

## <a name="table-flow"></a><span data-ttu-id="14ca4-121">Táblafolyamat</span><span class="sxs-lookup"><span data-stu-id="14ca4-121">Table flow</span></span>
<span data-ttu-id="14ca4-122">A Field Service alkalmazásban végzett készletkiigazítások és átvitelek szinkronizálva lesznek a Supply Chain Management alkalmazásba, miután a **Feladása állapota** **Létrehozottról** **Feladottra** lesz módosítva.</span><span class="sxs-lookup"><span data-stu-id="14ca4-122">Inventory adjustments and transfers made in Field Service will synchronize to Supply Chain Management after the **Post status** changes from **Created** to **Posted**.</span></span> <span data-ttu-id="14ca4-123">Amikor ez megtörténik a kiigazítás vagy átmozgatási rendelés zárolva lesz, és csak olvasható.</span><span class="sxs-lookup"><span data-stu-id="14ca4-123">When this occurs, the adjustment or the transfer order will be locked and become read only.</span></span> <span data-ttu-id="14ca4-124">Ez azt jelenti, átviteleket és a kiigazításokat is fel lehet adni a Supply Chain Management rendszerbe, de nem lehet azokat módosítani.</span><span class="sxs-lookup"><span data-stu-id="14ca4-124">This means that adjustments and transfers can be posted in Supply Chain Management, but cannot be modified.</span></span> <span data-ttu-id="14ca4-125">A Supply Chain Management alkalmazásban beállíthat egy kötegelt feladatot, hogy az automatikusan beküldje a kiigazításokat és átviteli készletnaplókat az integrációba.</span><span class="sxs-lookup"><span data-stu-id="14ca4-125">In Supply Chain Management, you can set up a batch job to automatically post the adjustments and transfer inventory journals that have been generated during the integration.</span></span> <span data-ttu-id="14ca4-126">Tekintse meg kötegelt feladat engedélyezésének előfeltételeit.</span><span class="sxs-lookup"><span data-stu-id="14ca4-126">See the following prerequisites for details on how to enable the batch job.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="14ca4-127">Field Service CRM megoldás</span><span class="sxs-lookup"><span data-stu-id="14ca4-127">Field Service CRM solution</span></span> 
<span data-ttu-id="14ca4-128">A **Készletegység** oszlopot hozzá kell adni a **Termék** táblához.</span><span class="sxs-lookup"><span data-stu-id="14ca4-128">The **Inventory unit** column has been added to the **Product** table.</span></span> <span data-ttu-id="14ca4-129">Ez az oszlop szükséges, mivel az Értékesítési és készletegység nem mindig ugyanaz a Supply Chain Management alkalmazásban és a Supply Chain Management raktárkészletéhez szükséges a készletegység.</span><span class="sxs-lookup"><span data-stu-id="14ca4-129">This column is needed because the Sales and Inventory unit is not always the same in Supply Chain Management, and the Inventory Unit is needed for the Warehouse Inventory in Supply Chain Management.</span></span>
<span data-ttu-id="14ca4-130">Amikor beállít egy terméket egy Raktárkiigazítási termékhez a Készletkiigazításokhoz és a Készletátvitelekhez is az egység a Termékkészlet termékértékből lesz lekérve.</span><span class="sxs-lookup"><span data-stu-id="14ca4-130">When you set the product on an Inventory adjustment product for both Inventory adjustments and Inventory transfers, the unit will be fetched from the inventory product value.</span></span> <span data-ttu-id="14ca4-131">Ha egy érték megtalálható az **Egység** oszlop zárolva lesz a készletkiigazítás termékben.</span><span class="sxs-lookup"><span data-stu-id="14ca4-131">If a value is found, the **Unit** column will be locked on the Inventory adjustment product.</span></span>

<span data-ttu-id="14ca4-132">A **Feladás állapota** oszlop hozzá lett adva a **Készletkiigazítás** és a **Készletátvitel** táblához is.</span><span class="sxs-lookup"><span data-stu-id="14ca4-132">The **Post status** column has been added to both the **Inventory adjustment** table and the **Inventory transfer** table.</span></span> <span data-ttu-id="14ca4-133">Ezzel az oszloppal szűrhető, hogy mikor lett egy kiigazítás vagy átvitel elküldve a Supply Chain Management alkalmazásnak.</span><span class="sxs-lookup"><span data-stu-id="14ca4-133">This column is used as a filter when an adjustment or transfer is sent to Supply Chain Management.</span></span> <span data-ttu-id="14ca4-134">Ezen oszlop alapértelmezett értéke Létrehozott (1), de nincs elküldve a Supply Chain Management számára.</span><span class="sxs-lookup"><span data-stu-id="14ca4-134">The default for this column is Created (1), however it is not sent to Supply Chain Management.</span></span> <span data-ttu-id="14ca4-135">Ha Feladva (2) értékre módosítja, akkor át lesz küldve a Supply Chain Management alkalmazásnak, de többé nem módosíthat semmit a kiigazítás vagy átvitel terén, és nem adhat hozzá új sorokat.</span><span class="sxs-lookup"><span data-stu-id="14ca4-135">When you update the value to Posted (2), it is sent to Supply Chain Management, but after that you will no longer be able to change the adjustment or transfer or add new lines.</span></span>

<span data-ttu-id="14ca4-136">A **Számsorozat** oszlop hozzá lett adva a **Készletkiigazítási termék** táblához.</span><span class="sxs-lookup"><span data-stu-id="14ca4-136">The **Number sequence** column has been added to the **Inventory adjustment product** table.</span></span> <span data-ttu-id="14ca4-137">Ez az oszlop gondoskodik arról, hogy az integrációnak egyedi száma legyen, hogy az integráció létrehozhassa és frissíthesse a kiigazítást.</span><span class="sxs-lookup"><span data-stu-id="14ca4-137">This column ensures that the integration has a unique number, so the integration can create and update the adjustment.</span></span> <span data-ttu-id="14ca4-138">Az első készletkiigazítási termék létrehozásakor az létrehoz egy új rekordot a **P2C AutoNumber** táblában, hogy megtartsa a számsorozatot és a használt előtagot.</span><span class="sxs-lookup"><span data-stu-id="14ca4-138">When you create your first inventory adjustment product, it will create a new record in the **P2C AutoNumber** table to maintain the number series and the prefix that is used.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="14ca4-139">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="14ca4-139">Prerequisites and mapping setup</span></span>

### <a name="supply-chain-management"></a><span data-ttu-id="14ca4-140">Ellátásilánc-kezelés</span><span class="sxs-lookup"><span data-stu-id="14ca4-140">Supply Chain Management</span></span>
<span data-ttu-id="14ca4-141">Az integráció által generált integrációs készletnaplókat automatikusan kötegelt feladat használatával is fel lehet adni.</span><span class="sxs-lookup"><span data-stu-id="14ca4-141">The integration inventory journals generated by the integration can automatically be posted using a batch job.</span></span> <span data-ttu-id="14ca4-142">Ez a következő helyről engedélyezhető: **Készletkezelés > Ismétlődő feladatok > Dataverse-integráció > Integrációs készlet naplóinak feladása**.</span><span class="sxs-lookup"><span data-stu-id="14ca4-142">This is enabled from **Inventory management > Periodic tasks > Dataverse integration > Post integration inventory journals**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="14ca4-143">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="14ca4-143">Template mapping in Data integration</span></span>

<span data-ttu-id="14ca4-144">Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.</span><span class="sxs-lookup"><span data-stu-id="14ca4-144">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="inventory-adjustment-field-service-to-supply-chain-management-inventory-adjustment"></a><span data-ttu-id="14ca4-145">Készletkiigazítás (Field Service alkalmazásból a Supply Chain Management alkalmazásba): Készletkiigazítás</span><span class="sxs-lookup"><span data-stu-id="14ca4-145">Inventory adjustment (Field Service to Supply Chain Management): Inventory adjustment</span></span>

<span data-ttu-id="14ca4-146">[![Sablonleképezés az adatintegrátorban](./media/FSAdj1.png)](./media/FSAdj1.png)</span><span class="sxs-lookup"><span data-stu-id="14ca4-146">[![Template mapping in Data integration](./media/FSAdj1.png)](./media/FSAdj1.png)</span></span>


### <a name="inventory-transfer-field-service-to-supply-chain-management-inventory-transfer"></a><span data-ttu-id="14ca4-147">Készletűtvitel (Field Service alkalmazásból a Supply Chain Management alkalmazásba): Készletátvitel</span><span class="sxs-lookup"><span data-stu-id="14ca4-147">Inventory transfer (Field Service to Supply Chain Management): Inventory transfer</span></span>

<span data-ttu-id="14ca4-148">[![Sablonleképezés az adatintegrátorban](./media/FSTrans1.png)](./media/FSTrans1.png)</span><span class="sxs-lookup"><span data-stu-id="14ca4-148">[![Template mapping in Data integration](./media/FSTrans1.png)](./media/FSTrans1.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]