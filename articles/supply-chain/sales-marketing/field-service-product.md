---
title: A Supply Chain Management-termékek közvetlen szinkronizálása a Field Service-termékekre
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatot, amelyek a Dynamics 365 Supply Chain Management termékeinek Dynamics 365 Field Service szolgáltatásba történő szinkronizálására használatosak.
author: ChristianRytt
manager: AnnBe
ms.date: 04/09/2018
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
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: c87e4cbfa375ef99d00c9a145c190af78e912d56
ms.sourcegitcommit: d8a2301eda0e5d0a6244ebbbe4459ab6caa88a95
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029405"
---
# <a name="synchronize-products-in-supply-chain-management-to-products-in-field-service"></a><span data-ttu-id="47f33-103">A Supply Chain Management-termékek közvetlen szinkronizálása a Field Service-termékekre</span><span class="sxs-lookup"><span data-stu-id="47f33-103">Synchronize products in Supply Chain Management to products in Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="47f33-104">Ez a témakör bemutatja a sablonokat és a mögöttes feladatot, amelyek a Dynamics 365 Supply Chain Management termékeinek közvetlenül a Dynamics 365 Field Service szolgáltatásba történő szinkronizálására használatosak.</span><span class="sxs-lookup"><span data-stu-id="47f33-104">This topic discusses the templates and underlying task that are used to synchronize products from Dynamics 365 Supply Chain Management to Dynamics 365  Field Service.</span></span>

<span data-ttu-id="47f33-105">A használt **Field Service termékek (Supply Chain Management – Field Service)** sablon A potenciális ügyfelek készpénzre váltása alkalmazásból eredő **Termékek (Supply Chain Management – Sales) – Közvetlen** sablonon alapul.</span><span class="sxs-lookup"><span data-stu-id="47f33-105">The used **Field Service Products (Supply Chain Management to Field Service)** template is based on the **Products (Supply Chain Management to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="47f33-106">További tudnivalókért lásd: [Termékek (Supply Chain Management – Sales) – Közvetlen](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="47f33-106">For more information, see [Products (Supply Chain Management to Sales) – Direct](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span></span>

<span data-ttu-id="47f33-107">Ez a témakör csak a **Field Service termékek (Supply Chain Management – Field Service)** és a **Termékek (Supply Chain Management – Sales) – Közvetlen** sablono közötti különbségeket mutatja be.</span><span class="sxs-lookup"><span data-stu-id="47f33-107">This topic only describes the differences between the **Field Service Products (Supply Chain Management to Field Service)** and **Products (Supply Chain Management to Sales) – Direct** templates.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="47f33-108">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="47f33-108">Templates and tasks</span></span>

<span data-ttu-id="47f33-109">**A sablon neve az adatintegrációban**</span><span class="sxs-lookup"><span data-stu-id="47f33-109">**Name of the template in Data integration**</span></span>

- <span data-ttu-id="47f33-110">Field Service-termékek (Supply Chain Management és Field Service között)</span><span class="sxs-lookup"><span data-stu-id="47f33-110">Field Service Products (Supply Chain Management to Field Service)</span></span>

<span data-ttu-id="47f33-111">**A feladat neve az adatintegrációs projektben**</span><span class="sxs-lookup"><span data-stu-id="47f33-111">**Name of the task in the Data integration project**</span></span>

- <span data-ttu-id="47f33-112">Termékek – Termékek</span><span class="sxs-lookup"><span data-stu-id="47f33-112">Products - Products</span></span>

<span data-ttu-id="47f33-113">A **Field Service termékek (Supply Chain Management – Field Service)** sablon tartalmaz egy leképezést, amely be része a **Termékek (Supply Chain Management – Sales) – Közvetlen** sablonnak.</span><span class="sxs-lookup"><span data-stu-id="47f33-113">The **Field Service Products (Supply Chain Management to Field Service)** template includes one mapping that isn't included in the **Products (Supply Chain Management to Sales) – Direct** template.</span></span> <span data-ttu-id="47f33-114">Ezt a leképezés biztosítja, hogy a szükséges Field Service-re jellemző mező, a **Szolgáltatás-terméktípus** megfelelően van beállítva.</span><span class="sxs-lookup"><span data-stu-id="47f33-114">This mapping ensures that the required Field Service-specific field **Service Product Type** is set correctly.</span></span>

```Text
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

<span data-ttu-id="47f33-115">A következő értékleképezés van használatban.</span><span class="sxs-lookup"><span data-stu-id="47f33-115">The following value mapping is used.</span></span>

```Text
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

<span data-ttu-id="47f33-116">A Supply Chain Management alkalmazásban a **Field Service terméktípus** értéke az **Értékesíthető kiadott termékek** adatentitásban a következőképpen számítódik ki:</span><span class="sxs-lookup"><span data-stu-id="47f33-116">In Supply Chain Management, the **Field Service product type** value on the **Sellable released products** data entity is calculated as follows:</span></span>

- <span data-ttu-id="47f33-117">**Készlet:** Termék típusa = Termék és cikk modellcsoport, Raktározott termék = Igaz</span><span class="sxs-lookup"><span data-stu-id="47f33-117">**Inventory:** Product type = Product and Item model group, Stocked product = True</span></span>
- <span data-ttu-id="47f33-118">**Készleten kívül:** Termék típusa = Termék és cikk modellcsoport, Raktározott termék = Hamis</span><span class="sxs-lookup"><span data-stu-id="47f33-118">**NonInventory:** Product type = Product and Item model group, Stocked product = False</span></span>
- <span data-ttu-id="47f33-119">**Szolgáltatás:** Terméktípus = Szolgáltatás</span><span class="sxs-lookup"><span data-stu-id="47f33-119">**Service:** Product type = Service</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="47f33-120">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="47f33-120">Template mapping in Data integration</span></span>

<span data-ttu-id="47f33-121">Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.</span><span class="sxs-lookup"><span data-stu-id="47f33-121">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-supply-chain-management-to-field-service-products---products"></a><span data-ttu-id="47f33-122">Field Service-termékek (Supply Chain Management és Field Service között): Termékek – Termékek</span><span class="sxs-lookup"><span data-stu-id="47f33-122">Field Service Products (Supply Chain Management to Field Service): Products - Products</span></span>

<span data-ttu-id="47f33-123">[![Sablonleképezés az adatintegrátorban](./media/FSProduct.png)](./media/FSProduct.png)</span><span class="sxs-lookup"><span data-stu-id="47f33-123">[![Template mapping in Data integration](./media/FSProduct.png)](./media/FSProduct.png)</span></span>
