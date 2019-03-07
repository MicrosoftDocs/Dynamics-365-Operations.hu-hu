---
title: Készletegységgel rendelkező termékek szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatot, amelyek a Microsoft Dynamics 365 for Finance and Operations raktáregységeinek a Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
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
ms.openlocfilehash: 5d3767c1a499f3d888d8fc2ce06c2837442e39f0
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "359244"
---
# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a><span data-ttu-id="a9e62-103">Készletegységgel rendelkező termékek szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba</span><span class="sxs-lookup"><span data-stu-id="a9e62-103">Synchronize products with inventory unit from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="a9e62-104">Ez a témakör bemutatja a sablonokat és a mögöttes feladatot, amelyek a Microsoft Dynamics 365 for Finance and Operations raktáregységeinek a Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.</span><span class="sxs-lookup"><span data-stu-id="a9e62-104">This topic discusses the templates and underlying task that are used to synchronize products with inventory unit from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="a9e62-105">[![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span><span class="sxs-lookup"><span data-stu-id="a9e62-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span></span>

<span data-ttu-id="a9e62-106">A használt **Field Service termékek (Finance and Operations – Field Service)** sablon A potenciális ügyfelek készpénzre váltása alkalmazásból eredő **Termékek (Finance and Operations – Sales) – Közvetlen** sablonon alapul.</span><span class="sxs-lookup"><span data-stu-id="a9e62-106">The used **Field Service Products (Finance and Operations to Field Service)** template is based on the **Products (Finance and Operations to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="a9e62-107">További tudnivalókért lásd: [Termékek (Finance and Operations – Sales) – Közvetlen](products-template-mapping-direct.md).</span><span class="sxs-lookup"><span data-stu-id="a9e62-107">For more information, see [Products (Finance and Operations to Sales) – Direct](products-template-mapping-direct.md).</span></span>

<span data-ttu-id="a9e62-108">Ez a témakör csak a **Field Service termékek (Finance and Operations – Field Service)** és a **Field Service termékek (Finance and Operations – Field Serivce)** sablonok közötti különbségeket mutatja be.</span><span class="sxs-lookup"><span data-stu-id="a9e62-108">This topic only describes the differences between the **Field Service Products (Finance and Operations to Field Service)** and **Field Service Products (Finance and Operations to Field Service)** templates.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="a9e62-109">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="a9e62-109">Templates and tasks</span></span>

<span data-ttu-id="a9e62-110">**A sablon neve az adatintegrációban:**</span><span class="sxs-lookup"><span data-stu-id="a9e62-110">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="a9e62-111">Készletegységgel rendelkező Field Service termékek (a Finance and Operations alkalmazásból a Sales alkalmazásba)</span><span class="sxs-lookup"><span data-stu-id="a9e62-111">Field Service Products with Inventory unit (Finance and Operations to Sales)</span></span>

<span data-ttu-id="a9e62-112">**A feladat neve az adatintegrációs projektben:**</span><span class="sxs-lookup"><span data-stu-id="a9e62-112">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="a9e62-113">Termékek</span><span class="sxs-lookup"><span data-stu-id="a9e62-113">Products</span></span>

<span data-ttu-id="a9e62-114">A **Field Service termékek készletegységgel (Finance and Operations – Field Service)** sablon tartalmaz egy megfeleltetést, amely nem szerepel a **Field Service termékek (Finance and Operations – Field Serivce)** sablonban.</span><span class="sxs-lookup"><span data-stu-id="a9e62-114">The **Field Service Products with Inventory unit (Finance and Operations to Field Service)** template includes one mapping that isn't included in the **Field Service Products (Finance and Operations to Field Service)** template.</span></span> <span data-ttu-id="a9e62-115">Ez a hozzárendelés gondoskodik arról, hogy szerepeljen a készletszint-szinkronizáláshoz szükséges készletegység.</span><span class="sxs-lookup"><span data-stu-id="a9e62-115">This mapping ensures that the Inventory unit needed for inventory level synchronization is included.</span></span>

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="a9e62-116">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="a9e62-116">Template mapping in Data integration</span></span>

<span data-ttu-id="a9e62-117">Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.</span><span class="sxs-lookup"><span data-stu-id="a9e62-117">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-with-inventory-unit-finance-and-operations-to-field-service-products"></a><span data-ttu-id="a9e62-118">Készletegységgel rendelkező Field Service termékek (Finance and Operations – Field Service): termékek</span><span class="sxs-lookup"><span data-stu-id="a9e62-118">Field Service Products with Inventory unit (Finance and Operations to Field Service): Products</span></span>

<span data-ttu-id="a9e62-119">[![Sablonleképezés az adatintegrátorban](./media/FSProduct1.png)](./media/FSProduct1.png)</span><span class="sxs-lookup"><span data-stu-id="a9e62-119">[![Template mapping in Data integration](./media/FSProduct1.png)](./media/FSProduct1.png)</span></span>
