---
title: Készletegységgel rendelkező termékek szinkronizálása a Supply Chain Management alkalmazásból a Field Service alkalmazásba
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatot, amelyek a Dynamics 365 Supply Chain Management raktáregységeinek a Dynamics 365 Field Service szolgáltatásba történő szinkronizálására használatosak.
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
ms.openlocfilehash: 911c5cc79ae359bbb77d31f366ccfeabf282a33e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429662"
---
# <a name="synchronize-products-with-inventory-unit-from-supply-chain-management-to-field-service"></a><span data-ttu-id="53784-103">Készletegységgel rendelkező termékek szinkronizálása a Supply Chain Management alkalmazásból a Field Service alkalmazásba</span><span class="sxs-lookup"><span data-stu-id="53784-103">Synchronize products with inventory unit from Supply Chain Management to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="53784-104">Ez a témakör bemutatja a sablonokat és a mögöttes feladatot, amelyek a Dynamics 365 Supply Chain Management raktáregységeinek a Dynamics 365 Field Service szolgáltatásba történő szinkronizálására használatosak.</span><span class="sxs-lookup"><span data-stu-id="53784-104">This topic discusses the templates and underlying task that are used to synchronize products with inventory unit from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="53784-105">[![Üzleti folyamatok szinkronizálása a Supply Chain Management és a Field Service között](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span><span class="sxs-lookup"><span data-stu-id="53784-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span></span>

<span data-ttu-id="53784-106">A használt **Field Service termékek készletegységgel (Supply Chain Management – Field Service)** sablon a **Field Service termékek (Supply Chain Management – Field Serivce)** sablonon alapul.</span><span class="sxs-lookup"><span data-stu-id="53784-106">The used **Field Service Products with Inventory unit (Supply Chain Management to Field Service)** template is based on the **Field Service Products (Supply Chain Management to Field Service)** template.</span></span> <span data-ttu-id="53784-107">További információért, lásd: [Termékek szinkronizálása a Supply Chain Management szolgáltatásban a Field Service szolgáltatás termékeivel](field-service-product.md).</span><span class="sxs-lookup"><span data-stu-id="53784-107">For more information, see [Synchronize products in Supply Chain Management to products in Field Service](field-service-product.md).</span></span>

<span data-ttu-id="53784-108">Ez a témakör csak a két sablonok eltéréseit írja le:</span><span class="sxs-lookup"><span data-stu-id="53784-108">This topic only describes the differences between the two templates:</span></span> 
- <span data-ttu-id="53784-109">**Készletegységgel rendelkező Field Service-termékek (Supply Chain Management alkalmazásból a Sales alkalmazásba)**</span><span class="sxs-lookup"><span data-stu-id="53784-109">**Field Service Products with Inventory unit (Supply Chain Management to Sales)**</span></span>
- <span data-ttu-id="53784-110">**Field Service-termékek (Supply Chain Management és Field Service között)**</span><span class="sxs-lookup"><span data-stu-id="53784-110">**Field Service Products (Supply Chain Management to Field Service)**</span></span> 

## <a name="templates-and-tasks"></a><span data-ttu-id="53784-111">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="53784-111">Templates and tasks</span></span>

<span data-ttu-id="53784-112">**A sablon neve az adatintegrációban:**</span><span class="sxs-lookup"><span data-stu-id="53784-112">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="53784-113">Készletegységgel rendelkező Field Service-termékek (Supply Chain Management alkalmazásból a Sales alkalmazásba)</span><span class="sxs-lookup"><span data-stu-id="53784-113">Field Service Products with Inventory unit (Supply Chain Management to Sales)</span></span>

<span data-ttu-id="53784-114">**A feladat neve az adatintegrációs projektben:**</span><span class="sxs-lookup"><span data-stu-id="53784-114">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="53784-115">Termékek</span><span class="sxs-lookup"><span data-stu-id="53784-115">Products</span></span>

<span data-ttu-id="53784-116">A **Készletegységgel rendelkező Field Service termékek (Supply Chain Management to Field Service)** sablon egy leképezést tartalmaz, amely nem szerepel a **Field Service termékek (Supply Chain Management – Field Serivce)** sablonban.</span><span class="sxs-lookup"><span data-stu-id="53784-116">The **Field Service Products with Inventory unit (Supply Chain Management to Field Service)** template includes one mapping that isn't included in the **Field Service Products (Supply Chain Management to Field Service)** template.</span></span> <span data-ttu-id="53784-117">Ez a hozzárendelés gondoskodik arról, hogy szerepeljen a készletszint-szinkronizáláshoz szükséges készletegység.</span><span class="sxs-lookup"><span data-stu-id="53784-117">This mapping ensures that the Inventory unit needed for inventory level synchronization is included.</span></span>

```plaintext
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="53784-118">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="53784-118">Template mapping in Data integration</span></span>

<span data-ttu-id="53784-119">Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.</span><span class="sxs-lookup"><span data-stu-id="53784-119">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-with-inventory-unit-supply-chain-management-to-field-service-products"></a><span data-ttu-id="53784-120">Készletegységgel rendelkező Field Service termékek (Supply Chain Management – Field Service): termékek</span><span class="sxs-lookup"><span data-stu-id="53784-120">Field Service Products with Inventory unit (Supply Chain Management to Field Service): Products</span></span>

<span data-ttu-id="53784-121">[![Sablonleképezés az adatintegrátorban](./media/FSProduct1.png)](./media/FSProduct1.png)</span><span class="sxs-lookup"><span data-stu-id="53784-121">[![Template mapping in Data integration](./media/FSProduct1.png)](./media/FSProduct1.png)</span></span>
