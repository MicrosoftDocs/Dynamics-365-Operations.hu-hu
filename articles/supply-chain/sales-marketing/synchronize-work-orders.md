---
title: "Munkarendelések szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatot mutatja be, melyek a projektszámmal rendelkező munkarendelések Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service közötti szinkronizálására használhatók."
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
ms.openlocfilehash: f5bd6b8c554688d0d1b2bfd93a34a60a95412bf3
ms.contentlocale: hu-hu
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a><span data-ttu-id="215c7-103">Projektszámmal rendelkező munkarendelések szinkronizálása a Field Service alkalmazásból a Finance and Operations alkalmazásba</span><span class="sxs-lookup"><span data-stu-id="215c7-103">Synchronize work orders with project from Field Service to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="215c7-104">Ez a témakör azokat a sablonokat és kapcsolódó feladatot mutatja be, melyek a projektszámmal rendelkező munkarendelések Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service közötti szinkronizálására használhatók.</span><span class="sxs-lookup"><span data-stu-id="215c7-104">This topic discusses the templates and underlying task that are used to synchronize work orders with a project number from Microsoft Dynamics 365 for Field Service to Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="215c7-105">[![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span><span class="sxs-lookup"><span data-stu-id="215c7-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span></span>

<span data-ttu-id="215c7-106">A használt **Field Service termékek (Finance and Operations – Field Service)** sablon A potenciális ügyfelek készpénzre váltása alkalmazásból eredő **Termékek (Finance and Operations – Sales) – Közvetlen** sablonon alapul.</span><span class="sxs-lookup"><span data-stu-id="215c7-106">The used **Field Service Products (Finance and Operations to Field Service)** template is based on the **Products (Finance and Operations to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="215c7-107">További tudnivalókért lásd: [Termékek (Finance and Operations – Sales) – Közvetlen](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="215c7-107">For more information, see [Products (Finance and Operations to Sales) – Direct](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span></span>

<span data-ttu-id="215c7-108">Ez a témakör csak a **Field Service termékek (Finance and Operations – Field Service)** és a **Field Service termékek (Finance and Operations – Field Serivce)** sablonok közötti különbségeket mutatja be.</span><span class="sxs-lookup"><span data-stu-id="215c7-108">This topic only describes the differences between the **Field Service Products (Finance and Operations to Field Service)** and **Field Service Products (Finance and Operations to Field Service)** templates.</span></span>

<span data-ttu-id="215c7-109">A fő különbség, hogy ez a sablon tartalmazza a munkarendeléshez hozzárendelt projektszámot a Field Service megoldásban, ami biztosítja, hogy a Finance and Operations megoldásban létrehozott értékesítési rendelés tartalmazza a projektszámot, és hogy megtörténhessen a számlázás a kapcsolódó projektben.</span><span class="sxs-lookup"><span data-stu-id="215c7-109">The main difference is that this template include mapping of the project number asigned to the Work order in Field Service, ensuring that the Sales order created in Finance and Operations include the project number and that invoicing can happen on the related project.</span></span> <span data-ttu-id="215c7-110">Emellett a sablon használja a speciális lekérdezés és szűrést.</span><span class="sxs-lookup"><span data-stu-id="215c7-110">Besides this the template use Advanced Query and Filtering.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="215c7-111">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="215c7-111">Templates and tasks</span></span>

<span data-ttu-id="215c7-112">**A sablon neve az adatintegrációban:**</span><span class="sxs-lookup"><span data-stu-id="215c7-112">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="215c7-113">Munkarendelések projektszámmal (a Field Service alkalmazásból a Finance and Operations alkalmazásba)</span><span class="sxs-lookup"><span data-stu-id="215c7-113">Work Orders with Project (Field Service to Finance and Operations)</span></span>

<span data-ttu-id="215c7-114">**A feladat neve az adatintegrációs projektben:**</span><span class="sxs-lookup"><span data-stu-id="215c7-114">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="215c7-115">WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="215c7-115">WorkOrderHeader</span></span>
- <span data-ttu-id="215c7-116">WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="215c7-116">WorkOrderHeaderProject</span></span>
- <span data-ttu-id="215c7-117">WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="215c7-117">WorkOrderProduct</span></span>
- <span data-ttu-id="215c7-118">WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="215c7-118">WorkOrderService</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="215c7-119">Field Service CRM megoldás</span><span class="sxs-lookup"><span data-stu-id="215c7-119">Field Service CRM solution</span></span>
<span data-ttu-id="215c7-120">A **Külső projekt** mezőt hozzáadtuk a munkarendelés entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="215c7-120">The **External Project** field has been added to the Work Order entity.</span></span> <span data-ttu-id="215c7-121">Ez a mező egy keresés és vásárlás, felcímkézi a Munkarendelést egy projekttel, majd az értékesítési rendelés kapcsolódik egy projekthez a Finance and Operations megoldáson belül.</span><span class="sxs-lookup"><span data-stu-id="215c7-121">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Finance and Operations.</span></span> <span data-ttu-id="215c7-122">Miután a **Rendszer állapota** Nyitott – folyamatban (690,970,000) állapotból magasabb állapba kerül, a **Külső projekt** mezőt a rendszer zárolja, és nem lehet felvenni, törölni vagy módosítani az értéket.</span><span class="sxs-lookup"><span data-stu-id="215c7-122">Ones the **System Status** changes from Open – In Progress(690,970,000) to a higher status the **External Project** field will be locked and you can't add, remove or change the value.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="215c7-123">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="215c7-123">Template mapping in Data integration</span></span>

<span data-ttu-id="215c7-124">Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.</span><span class="sxs-lookup"><span data-stu-id="215c7-124">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheader"></a><span data-ttu-id="215c7-125">Munkarendelések projektszámmal (a Field Service alkalmazásból a Finance and Operations alkalmazásba): WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="215c7-125">Work Orders with Project (Field Service to Finance and Operations): WorkOrderHeader</span></span>

<span data-ttu-id="215c7-126">[![Sablonleképezés az adatintegrátorban](./media/FSWOP1.png)](./media/FSWOP1.png)</span><span class="sxs-lookup"><span data-stu-id="215c7-126">[![Template mapping in Data integration](./media/FSWOP1.png)](./media/FSWOP1.png)</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheaderproject"></a><span data-ttu-id="215c7-127">Munkarendelések projektszámmal (a Field Service alkalmazásból a Finance and Operations alkalmazásba): WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="215c7-127">Work Orders with Project (Field Service to Finance and Operations): WorkOrderHeaderProject</span></span>

<span data-ttu-id="215c7-128">[![Sablonleképezés az adatintegrátorban](./media/FSWOP2.png)](./media/FSWOP2.png)</span><span class="sxs-lookup"><span data-stu-id="215c7-128">[![Template mapping in Data integration](./media/FSWOP2.png)](./media/FSWOP2.png)</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderproduct"></a><span data-ttu-id="215c7-129">Munkarendelések projektszámmal (a Field Service alkalmazásból a Finance and Operations alkalmazásba): WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="215c7-129">Work Orders with Project (Field Service to Finance and Operations): WorkOrderProduct</span></span>

<span data-ttu-id="215c7-130">[![Sablonleképezés az adatintegrátorban](./media/FSWOP3.png)](./media/FSWOP3.png)</span><span class="sxs-lookup"><span data-stu-id="215c7-130">[![Template mapping in Data integration](./media/FSWOP3.png)](./media/FSWOP3.png)</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderservice"></a><span data-ttu-id="215c7-131">Munkarendelések projektszámmal (a Field Service alkalmazásból a Finance and Operations alkalmazásba): WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="215c7-131">Work Orders with Project (Field Service to Finance and Operations): WorkOrderService</span></span>

<span data-ttu-id="215c7-132">[![Sablonleképezés az adatintegrátorban](./media/FSWOP4.png)](./media/FSWOP4.png)</span><span class="sxs-lookup"><span data-stu-id="215c7-132">[![Template mapping in Data integration](./media/FSWOP4.png)](./media/FSWOP4.png)</span></span>

