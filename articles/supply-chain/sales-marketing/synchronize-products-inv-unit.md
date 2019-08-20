---
title: Készletegységgel rendelkező termékek szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatot, amelyek a Microsoft Dynamics 365 for Finance and Operations raktáregységeinek a Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.
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
ms.openlocfilehash: 78e8d8fa609b015cf2fceaf498279fe091325dbb
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835694"
---
# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a><span data-ttu-id="99dfc-103">Készletegységgel rendelkező termékek szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba</span><span class="sxs-lookup"><span data-stu-id="99dfc-103">Synchronize products with inventory unit from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="99dfc-104">Ez a témakör bemutatja a sablonokat és a mögöttes feladatot, amelyek a Microsoft Dynamics 365 for Finance and Operations raktáregységeinek a Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.</span><span class="sxs-lookup"><span data-stu-id="99dfc-104">This topic discusses the templates and underlying task that are used to synchronize products with inventory unit from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="99dfc-105">[![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span><span class="sxs-lookup"><span data-stu-id="99dfc-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span></span>

<span data-ttu-id="99dfc-106">A használt **Field Service termékek készletegységgel (Fin and Ops – Field Service)** sablon a **Field Service termékek (Fin and Ops – Field Serivce)** sablonon alapul.</span><span class="sxs-lookup"><span data-stu-id="99dfc-106">The used **Field Service Products with Inventory unit (Fin and Ops to Field Service)** template is based on the **Field Service Products (Fin and Ops to Field Service)** template.</span></span> <span data-ttu-id="99dfc-107">További tudnivalókért lásd: [Field Service termékek (Finance and Operations – Field Service)](field-service-product.md).</span><span class="sxs-lookup"><span data-stu-id="99dfc-107">For more information, see [Field Service Products (Finance and Operations to Field Service)](field-service-product.md).</span></span>

<span data-ttu-id="99dfc-108">Ez a témakör csak a két sablonok eltéréseit írja le:</span><span class="sxs-lookup"><span data-stu-id="99dfc-108">This topic only describes the differences between the two templates:</span></span> 
- <span data-ttu-id="99dfc-109">**Készletegységgel rendelkező Field Service termékek (a Fin and Ops alkalmazásból a Sales alkalmazásba)**</span><span class="sxs-lookup"><span data-stu-id="99dfc-109">**Field Service Products with Inventory unit (Fin and Ops to Sales)**</span></span>
- <span data-ttu-id="99dfc-110">**Field Service termékek (Fin and Ops – Field Service)**</span><span class="sxs-lookup"><span data-stu-id="99dfc-110">**Field Service Products (Fin and Ops to Field Service)**</span></span> 

## <a name="templates-and-tasks"></a><span data-ttu-id="99dfc-111">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="99dfc-111">Templates and tasks</span></span>

<span data-ttu-id="99dfc-112">**A sablon neve az adatintegrációban:**</span><span class="sxs-lookup"><span data-stu-id="99dfc-112">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="99dfc-113">Készletegységgel rendelkező Field Service termékek (a Fin and Ops alkalmazásból a Sales alkalmazásba)</span><span class="sxs-lookup"><span data-stu-id="99dfc-113">Field Service Products with Inventory unit (Fin and Ops to Sales)</span></span>

<span data-ttu-id="99dfc-114">**A feladat neve az adatintegrációs projektben:**</span><span class="sxs-lookup"><span data-stu-id="99dfc-114">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="99dfc-115">Termékek</span><span class="sxs-lookup"><span data-stu-id="99dfc-115">Products</span></span>

<span data-ttu-id="99dfc-116">A **Field Service termékek készletegységgel (Fin and Ops – Field Service)** sablon tartalmaz egy megfeleltetést, amely nem szerepel a **Field Service termékek (Fin and Ops – Field Serivce)** sablonban.</span><span class="sxs-lookup"><span data-stu-id="99dfc-116">The **Field Service Products with Inventory unit (Fin and Ops to Field Service)** template includes one mapping that isn't included in the **Field Service Products (Fin and Ops to Field Service)** template.</span></span> <span data-ttu-id="99dfc-117">Ez a hozzárendelés gondoskodik arról, hogy szerepeljen a készletszint-szinkronizáláshoz szükséges készletegység.</span><span class="sxs-lookup"><span data-stu-id="99dfc-117">This mapping ensures that the Inventory unit needed for inventory level synchronization is included.</span></span>

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="99dfc-118">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="99dfc-118">Template mapping in Data integration</span></span>

<span data-ttu-id="99dfc-119">Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.</span><span class="sxs-lookup"><span data-stu-id="99dfc-119">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-with-inventory-unit-fin-and-ops-to-field-service-products"></a><span data-ttu-id="99dfc-120">Készletegységgel rendelkező Field Service termékek (Fin and Ops – Field Service): termékek</span><span class="sxs-lookup"><span data-stu-id="99dfc-120">Field Service Products with Inventory unit (Fin and Ops to Field Service): Products</span></span>

<span data-ttu-id="99dfc-121">[![Sablonleképezés az adatintegrátorban](./media/FSProduct1.png)](./media/FSProduct1.png)</span><span class="sxs-lookup"><span data-stu-id="99dfc-121">[![Template mapping in Data integration](./media/FSProduct1.png)](./media/FSProduct1.png)</span></span>
