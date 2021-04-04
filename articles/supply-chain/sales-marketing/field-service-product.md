---
title: A Supply Chain Management-termékek közvetlen szinkronizálása a Field Service-termékekre
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatot, amelyek a Dynamics 365 Supply Chain Management termékeinek Dynamics 365 Field Service szolgáltatásba történő szinkronizálására használatosak.
author: ChristianRytt
manager: tfehr
ms.date: 04/09/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: d3dc21a39c9866d09e500e2f14ff810bac7d57fe
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5261045"
---
# <a name="synchronize-products-in-supply-chain-management-to-products-in-field-service"></a><span data-ttu-id="7c5f7-103">A Supply Chain Management-termékek közvetlen szinkronizálása a Field Service-termékekre</span><span class="sxs-lookup"><span data-stu-id="7c5f7-103">Synchronize products in Supply Chain Management to products in Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="7c5f7-104">Ez a témakör bemutatja a sablonokat és a mögöttes feladatot, amelyek a Dynamics 365 Supply Chain Management termékeinek közvetlenül a Dynamics 365 Field Service szolgáltatásba történő szinkronizálására használatosak.</span><span class="sxs-lookup"><span data-stu-id="7c5f7-104">This topic discusses the templates and underlying task that are used to synchronize products from Dynamics 365 Supply Chain Management to Dynamics 365  Field Service.</span></span>

<span data-ttu-id="7c5f7-105">A használt **Field Service termékek (Supply Chain Management – Field Service)** sablon A potenciális ügyfelek készpénzre váltása alkalmazásból eredő **Termékek (Supply Chain Management – Sales) – Közvetlen** sablonon alapul.</span><span class="sxs-lookup"><span data-stu-id="7c5f7-105">The used **Field Service Products (Supply Chain Management to Field Service)** template is based on the **Products (Supply Chain Management to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="7c5f7-106">További tudnivalókért lásd: [Termékek (Supply Chain Management – Sales) – Közvetlen](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="7c5f7-106">For more information, see [Products (Supply Chain Management to Sales) – Direct](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span></span>

<span data-ttu-id="7c5f7-107">Ez a témakör csak a **Field Service termékek (Supply Chain Management – Field Service)** és a **Termékek (Supply Chain Management – Sales) – Közvetlen** sablono közötti különbségeket mutatja be.</span><span class="sxs-lookup"><span data-stu-id="7c5f7-107">This topic only describes the differences between the **Field Service Products (Supply Chain Management to Field Service)** and **Products (Supply Chain Management to Sales) – Direct** templates.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="7c5f7-108">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="7c5f7-108">Templates and tasks</span></span>

<span data-ttu-id="7c5f7-109">**A sablon neve az adatintegrációban**</span><span class="sxs-lookup"><span data-stu-id="7c5f7-109">**Name of the template in Data integration**</span></span>

- <span data-ttu-id="7c5f7-110">Field Service-termékek (Supply Chain Management és Field Service között)</span><span class="sxs-lookup"><span data-stu-id="7c5f7-110">Field Service Products (Supply Chain Management to Field Service)</span></span>

<span data-ttu-id="7c5f7-111">**A feladat neve az adatintegrációs projektben**</span><span class="sxs-lookup"><span data-stu-id="7c5f7-111">**Name of the task in the Data integration project**</span></span>

- <span data-ttu-id="7c5f7-112">Termékek – Termékek</span><span class="sxs-lookup"><span data-stu-id="7c5f7-112">Products - Products</span></span>

<span data-ttu-id="7c5f7-113">A **Field Service termékek (Supply Chain Management – Field Service)** sablon tartalmaz egy leképezést, amely be része a **Termékek (Supply Chain Management – Sales) – Közvetlen** sablonnak.</span><span class="sxs-lookup"><span data-stu-id="7c5f7-113">The **Field Service Products (Supply Chain Management to Field Service)** template includes one mapping that isn't included in the **Products (Supply Chain Management to Sales) – Direct** template.</span></span> <span data-ttu-id="7c5f7-114">Ezt a leképezés biztosítja, hogy a szükséges Field Service-re jellemző mező, a **Szolgáltatás-terméktípus** megfelelően van beállítva.</span><span class="sxs-lookup"><span data-stu-id="7c5f7-114">This mapping ensures that the required Field Service-specific field **Service Product Type** is set correctly.</span></span>

```plaintext
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

<span data-ttu-id="7c5f7-115">A következő értékleképezés van használatban.</span><span class="sxs-lookup"><span data-stu-id="7c5f7-115">The following value mapping is used.</span></span>

```plaintext
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

<span data-ttu-id="7c5f7-116">A Supply Chain Management alkalmazásban a **Field Service terméktípus** értéke az **Értékesíthető kiadott termékek** adatentitásban a következőképpen számítódik ki:</span><span class="sxs-lookup"><span data-stu-id="7c5f7-116">In Supply Chain Management, the **Field Service product type** value on the **Sellable released products** data entity is calculated as follows:</span></span>

- <span data-ttu-id="7c5f7-117">**Készlet:** Termék típusa = Termék és cikk modellcsoport, Raktározott termék = Igaz</span><span class="sxs-lookup"><span data-stu-id="7c5f7-117">**Inventory:** Product type = Product and Item model group, Stocked product = True</span></span>
- <span data-ttu-id="7c5f7-118">**Készleten kívül:** Termék típusa = Termék és cikk modellcsoport, Raktározott termék = Hamis</span><span class="sxs-lookup"><span data-stu-id="7c5f7-118">**NonInventory:** Product type = Product and Item model group, Stocked product = False</span></span>
- <span data-ttu-id="7c5f7-119">**Szolgáltatás:** Terméktípus = Szolgáltatás</span><span class="sxs-lookup"><span data-stu-id="7c5f7-119">**Service:** Product type = Service</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="7c5f7-120">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="7c5f7-120">Template mapping in Data integration</span></span>

<span data-ttu-id="7c5f7-121">Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.</span><span class="sxs-lookup"><span data-stu-id="7c5f7-121">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-supply-chain-management-to-field-service-products---products"></a><span data-ttu-id="7c5f7-122">Field Service-termékek (Supply Chain Management és Field Service között): Termékek – Termékek</span><span class="sxs-lookup"><span data-stu-id="7c5f7-122">Field Service Products (Supply Chain Management to Field Service): Products - Products</span></span>

<span data-ttu-id="7c5f7-123">[![Sablonleképezés az adatintegrátorban](./media/FSProduct.png)](./media/FSProduct.png)</span><span class="sxs-lookup"><span data-stu-id="7c5f7-123">[![Template mapping in Data integration](./media/FSProduct.png)](./media/FSProduct.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]