---
title: Készletegységgel rendelkező termékek szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatot, amelyek a Microsoft Dynamics 365 for Finance and Operations raktáregységeinek a Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.
author: ChristianRytt
manager: AnnBe
ms.date: 03/12/2019
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
ms.openlocfilehash: 8e421be79fde6103be6344040b6ae6cda0626c5a
ms.sourcegitcommit: d9ed934a142b88340d268fd2bd3753475a3712b0
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/12/2019
ms.locfileid: "836302"
---
# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a><span data-ttu-id="f74e7-103">Készletegységgel rendelkező termékek szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba</span><span class="sxs-lookup"><span data-stu-id="f74e7-103">Synchronize products with inventory unit from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="f74e7-104">Ez a témakör bemutatja a sablonokat és a mögöttes feladatot, amelyek a Microsoft Dynamics 365 for Finance and Operations raktáregységeinek a Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.</span><span class="sxs-lookup"><span data-stu-id="f74e7-104">This topic discusses the templates and underlying task that are used to synchronize products with inventory unit from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="f74e7-105">[![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span><span class="sxs-lookup"><span data-stu-id="f74e7-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span></span>

<span data-ttu-id="f74e7-106">A használt **Field Service termékek készletegységgel (Finance and Operations – Field Service)** sablon a **Field Service termékek (Finance and Operations – Field Serivce)** sablonon alapul.</span><span class="sxs-lookup"><span data-stu-id="f74e7-106">The used **Field Service Products with Inventory unit (Finance and Operations to Field Service)** template is based on the **Field Service Products (Finance and Operations to Field Service)** template.</span></span> <span data-ttu-id="f74e7-107">További tudnivalókért lásd: [Field Service termékek (Finance and Operations – Field Service)](field-service-product.md).</span><span class="sxs-lookup"><span data-stu-id="f74e7-107">For more information, see [Field Service Products (Finance and Operations to Field Service)](field-service-product.md).</span></span>

<span data-ttu-id="f74e7-108">Ez a témakör csak a két sablonok eltéréseit írja le:</span><span class="sxs-lookup"><span data-stu-id="f74e7-108">This topic only describes the differences between the two templates:</span></span> 
- <span data-ttu-id="f74e7-109">**Készletegységgel rendelkező Field Service termékek (a Finance and Operations alkalmazásból a Sales alkalmazásba)**</span><span class="sxs-lookup"><span data-stu-id="f74e7-109">**Field Service Products with Inventory unit (Finance and Operations to Sales)**</span></span>
- <span data-ttu-id="f74e7-110">**Field Service termékek (Finance and Operations – Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="f74e7-110">**Field Service Products (Finance and Operations to Field Service)**</span></span> 

## <a name="templates-and-tasks"></a><span data-ttu-id="f74e7-111">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="f74e7-111">Templates and tasks</span></span>

<span data-ttu-id="f74e7-112">**A sablon neve az adatintegrációban:**</span><span class="sxs-lookup"><span data-stu-id="f74e7-112">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="f74e7-113">Készletegységgel rendelkező Field Service termékek (a Finance and Operations alkalmazásból a Sales alkalmazásba)</span><span class="sxs-lookup"><span data-stu-id="f74e7-113">Field Service Products with Inventory unit (Finance and Operations to Sales)</span></span>

<span data-ttu-id="f74e7-114">**A feladat neve az adatintegrációs projektben:**</span><span class="sxs-lookup"><span data-stu-id="f74e7-114">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="f74e7-115">Termékek</span><span class="sxs-lookup"><span data-stu-id="f74e7-115">Products</span></span>

<span data-ttu-id="f74e7-116">A **Field Service termékek készletegységgel (Finance and Operations – Field Service)** sablon tartalmaz egy megfeleltetést, amely nem szerepel a **Field Service termékek (Finance and Operations – Field Serivce)** sablonban.</span><span class="sxs-lookup"><span data-stu-id="f74e7-116">The **Field Service Products with Inventory unit (Finance and Operations to Field Service)** template includes one mapping that isn't included in the **Field Service Products (Finance and Operations to Field Service)** template.</span></span> <span data-ttu-id="f74e7-117">Ez a hozzárendelés gondoskodik arról, hogy szerepeljen a készletszint-szinkronizáláshoz szükséges készletegység.</span><span class="sxs-lookup"><span data-stu-id="f74e7-117">This mapping ensures that the Inventory unit needed for inventory level synchronization is included.</span></span>

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="f74e7-118">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="f74e7-118">Template mapping in Data integration</span></span>

<span data-ttu-id="f74e7-119">Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.</span><span class="sxs-lookup"><span data-stu-id="f74e7-119">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-with-inventory-unit-finance-and-operations-to-field-service-products"></a><span data-ttu-id="f74e7-120">Készletegységgel rendelkező Field Service termékek (Finance and Operations – Field Service): termékek</span><span class="sxs-lookup"><span data-stu-id="f74e7-120">Field Service Products with Inventory unit (Finance and Operations to Field Service): Products</span></span>

<span data-ttu-id="f74e7-121">[![Sablonleképezés az adatintegrátorban](./media/FSProduct1.png)](./media/FSProduct1.png)</span><span class="sxs-lookup"><span data-stu-id="f74e7-121">[![Template mapping in Data integration](./media/FSProduct1.png)](./media/FSProduct1.png)</span></span>
