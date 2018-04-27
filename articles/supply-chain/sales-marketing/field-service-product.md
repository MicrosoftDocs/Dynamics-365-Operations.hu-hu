---
title: "A Finance and Operations-termékek szinkronizálása a Field Service-termékekre"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatot mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service közötti termékszinkronizálásra használhatók."
author: ChristianRytt
manager: AnnBe
ms.date: 04/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 08cfd2cfa24bef0f0c92126f5d1052a12ceba37a
ms.openlocfilehash: 699830ce6cd993f3dd3fd4ff744ce5a8b9645c32
ms.contentlocale: hu-hu
ms.lasthandoff: 04/11/2018

---

# <a name="synchronize-products-in-finance-and-operations-to-products-in-field-service"></a><span data-ttu-id="214ce-103">A Finance and Operations-termékek szinkronizálása a Field Service-termékekre</span><span class="sxs-lookup"><span data-stu-id="214ce-103">Synchronize products in Finance and Operations to products in Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="214ce-104">Ez a témakör azokat a sablonokat és kapcsolódó feladatot mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service közötti termékszinkronizálásra használhatók.</span><span class="sxs-lookup"><span data-stu-id="214ce-104">This topic discusses the templates and underlying task that are used to synchronize products from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="214ce-105">A használt **Field Service termékek (Fin and Ops – Field Service)** sablon A potenciális ügyfelek készpénzre váltása alkalmazásból eredő **Termékek (Fin and Ops – Sales) – Közvetlen** sablonon alapul.</span><span class="sxs-lookup"><span data-stu-id="214ce-105">The used **Field Service Products (Fin and Ops to Field Service)** template is based on the **Products (Fin and Ops to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="214ce-106">További tudnivalókért lásd: [Termékek (Fin and Ops – Sales) – Közvetlen](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="214ce-106">For more information, see [Products (Fin and Ops to Sales) – Direct](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span></span>

<span data-ttu-id="214ce-107">Ez a témakör csak a **Field Service termékek (Fin and Ops – Field Service)** és a **Termékek (Fin and Ops – Sales) – Közvetlen** sablono közötti különbségeket mutatja be.</span><span class="sxs-lookup"><span data-stu-id="214ce-107">This topic only describes the differences between the **Field Service Products (Fin and Ops to Field Service)** and **Products (Fin and Ops to Sales) – Direct** templates.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="214ce-108">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="214ce-108">Templates and tasks</span></span>

<span data-ttu-id="214ce-109">**A sablon neve az adatintegrációban:**</span><span class="sxs-lookup"><span data-stu-id="214ce-109">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="214ce-110">Field Service termékek (Fin and Ops – Field Service)</span><span class="sxs-lookup"><span data-stu-id="214ce-110">Field Service Products (Fin and Ops to Field Service)</span></span>

<span data-ttu-id="214ce-111">**A feladat neve az adatintegrációs projektben:**</span><span class="sxs-lookup"><span data-stu-id="214ce-111">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="214ce-112">Termékek – Termékek</span><span class="sxs-lookup"><span data-stu-id="214ce-112">Products - Products</span></span>

<span data-ttu-id="214ce-113">A **Field Service termékek (Fin and Ops – Field Service)** sablon egy leképezést tartalmaz, amely nem található meg a **Termékek (Fin and Ops – Sales) – Közvetlen** sablonban.</span><span class="sxs-lookup"><span data-stu-id="214ce-113">The **Field Service Products (Fin and Ops to Field Service)** template includes one mapping that isn't included in the **Products (Fin and Ops to Sales) – Direct** template.</span></span> <span data-ttu-id="214ce-114">Ezt a leképezés biztosítja, hogy a szükséges Field Service-re jellemző mező, a **Szolgáltatás-terméktípus** megfelelően van beállítva.</span><span class="sxs-lookup"><span data-stu-id="214ce-114">This mapping ensures that the required Field Service-specific field **Service Product Type** is set correctly.</span></span>

```
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

<span data-ttu-id="214ce-115">A következő értékleképezés van használatban.</span><span class="sxs-lookup"><span data-stu-id="214ce-115">The following value mapping is used.</span></span>

```
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

<span data-ttu-id="214ce-116">A Finance and Operations alkalmazásban a **Field Service terméktípus** értéke az **Értékesíthető kiadott termékek** adatentitásban a következőképpen számítódik ki:</span><span class="sxs-lookup"><span data-stu-id="214ce-116">In Finance and Operations, the **Field Service product type** value on the **Sellable released products** data entity is calculated as follows:</span></span>

- <span data-ttu-id="214ce-117">**Készlet:** Termék típusa = Termék és cikk modellcsoport, Raktározott termék = Igaz</span><span class="sxs-lookup"><span data-stu-id="214ce-117">**Inventory:** Product type = Product and Item model group, Stocked product = True</span></span>
- <span data-ttu-id="214ce-118">**Készleten kívül:** Termék típusa = Termék és cikk modellcsoport, Raktározott termék = Hamis</span><span class="sxs-lookup"><span data-stu-id="214ce-118">**NonInventory:** Product type = Product and Item model group, Stocked product = False</span></span>
- <span data-ttu-id="214ce-119">**Szolgáltatás:** Terméktípus = Szolgáltatás</span><span class="sxs-lookup"><span data-stu-id="214ce-119">**Service:** Product type = Service</span></span>

