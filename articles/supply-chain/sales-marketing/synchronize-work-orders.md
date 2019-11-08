---
title: Munkarendelések szinkronizálása projekttel a Field Service alkalmazásból a Supply Chain Management alkalmazásba
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatot, amelye a Dynamics 365 Field Service munkarendeléseinek a Dynamics 365 Supply Chain Management szolgáltatásban található projektszámaival történő szinkronizálására használatos.
author: ChristianRytt
manager: AnnBe
ms.date: 03/12/2019
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
ms.openlocfilehash: 5c57b8d1e09fd57611accec83ec3da4bc596fd00
ms.sourcegitcommit: 4d6ec2b1a9674712e1efb8c46b919d554f21a2b3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2019
ms.locfileid: "2627551"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-supply-chain-management"></a><span data-ttu-id="f682d-103">Munkarendelések szinkronizálása projekttel a Field Service alkalmazásból a Supply Chain Management alkalmazásba</span><span class="sxs-lookup"><span data-stu-id="f682d-103">Synchronize work orders with project from Field Service to Supply Chain Management</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="f682d-104">Ez a témakör bemutatja a sablonokat és a mögöttes feladatot, amelye a Dynamics 365 Field Service munkarendeléseinek a Dynamics 365 Supply Chain Management szolgáltatásban található projektszámaival történő szinkronizálására használatos.</span><span class="sxs-lookup"><span data-stu-id="f682d-104">This topic discusses the templates and underlying task that are used to synchronize work orders with a project number from Dynamics 365 Field Service to Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="f682d-105">[![Üzleti folyamatok szinkronizálása a Supply Chain Management és a Field Service között](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span><span class="sxs-lookup"><span data-stu-id="f682d-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span></span>

<span data-ttu-id="f682d-106">A használt **Munkarendelések projektekkel (Field Service-ből a Supply Chain Management szolgáltatásba)** sablon a **Munkarendelések (Field Service-ből a Supply Chain Management szolgáltatásba)** sablonon alapul.</span><span class="sxs-lookup"><span data-stu-id="f682d-106">The used **Work Orders with Project (Field Service to Supply Chain Management)** template is based on the **Work Orders (Field Service to Supply Chain Management)** template.</span></span> <span data-ttu-id="f682d-107">További információért, lásd: [A Field Service szolgáltatásokban lévő munkarendelések szinkronizálása a Supply Chain Management értékesítési rendeléseivel](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order)</span><span class="sxs-lookup"><span data-stu-id="f682d-107">For more information, see [Synchronize work orders in Field Service to sales orders in Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

<span data-ttu-id="f682d-108">Ez a témakör csak a két sablonok eltéréseit írja le:</span><span class="sxs-lookup"><span data-stu-id="f682d-108">This topic only describes the differences between the two templates:</span></span>
- <span data-ttu-id="f682d-109">**Munkarendelések projekttel (a Field Service alkalmazásból a Supply Chain Management alkalmazásba)**</span><span class="sxs-lookup"><span data-stu-id="f682d-109">**Work Orders with Project (Field Service to Supply Chain Management)**</span></span>
- <span data-ttu-id="f682d-110">**Munkarendelések (a Field Service alkalmazásból a Supply Chain Management alkalmazásba)**</span><span class="sxs-lookup"><span data-stu-id="f682d-110">**Work Orders (Field Service to Supply Chain Management)**</span></span>

<span data-ttu-id="f682d-111">A fő különbség, hogy ez a sablon tartalmazza a munkarendeléshez társított projektszám leképezését a Field Service megoldásban, ami biztosítja, hogy a Supply Chain Management megoldásban létrehozott értékesítési rendelés tartalmazza a projektszámot, és hogy megtörténhessen a számlázás a kapcsolódó projektben.</span><span class="sxs-lookup"><span data-stu-id="f682d-111">The main difference is that this template includes mapping of the project number assigned to the Work order in Field Service, ensuring that the Sales order created in Supply Chain Management include the project number and that invoicing can happen on the related project.</span></span> <span data-ttu-id="f682d-112">Emellett a sablon használja a speciális lekérdezés és szűrést.</span><span class="sxs-lookup"><span data-stu-id="f682d-112">Besides this the template use Advanced Query and Filtering.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="f682d-113">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="f682d-113">Templates and tasks</span></span>

<span data-ttu-id="f682d-114">**A sablon neve az adatintegrációban:**</span><span class="sxs-lookup"><span data-stu-id="f682d-114">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="f682d-115">Munkarendelések projekttel (a Field Service alkalmazásból a Supply Chain Management alkalmazásba)</span><span class="sxs-lookup"><span data-stu-id="f682d-115">Work Orders with Project (Field Service to Supply Chain Management)</span></span>

<span data-ttu-id="f682d-116">**A feladat neve az adatintegrációs projektben:**</span><span class="sxs-lookup"><span data-stu-id="f682d-116">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="f682d-117">WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="f682d-117">WorkOrderHeader</span></span>
- <span data-ttu-id="f682d-118">WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="f682d-118">WorkOrderHeaderProject</span></span>
- <span data-ttu-id="f682d-119">WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="f682d-119">WorkOrderProduct</span></span>
- <span data-ttu-id="f682d-120">WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="f682d-120">WorkOrderService</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="f682d-121">Field Service CRM megoldás</span><span class="sxs-lookup"><span data-stu-id="f682d-121">Field Service CRM solution</span></span>
<span data-ttu-id="f682d-122">A **Külső projekt** mezőt hozzáadtuk a munkarendelés entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="f682d-122">The **External Project** field has been added to the Work Order entity.</span></span> <span data-ttu-id="f682d-123">Ez a mező egy keresőmező, és a munkarendelés egy projekttel való felcímkézése által az értékesítési rendelés kapcsolódik egy projekthez a Supply Chain Management megoldáson belül.</span><span class="sxs-lookup"><span data-stu-id="f682d-123">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Supply Chain Management.</span></span> <span data-ttu-id="f682d-124">Amikor a **Rendszer állapota** Nyitott – folyamatban (690,970,000) állapotból magasabb állapba kerül, a **Külső projekt** mezőt a rendszer zárolja, és nem lehet felvenni, törölni vagy módosítani az értéket.</span><span class="sxs-lookup"><span data-stu-id="f682d-124">When the **System Status** changes from Open – In Progress(690,970,000) to a higher status, the **External Project** field will be locked and you can't add, remove, or change the value.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="f682d-125">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="f682d-125">Template mapping in Data integration</span></span>

<span data-ttu-id="f682d-126">Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.</span><span class="sxs-lookup"><span data-stu-id="f682d-126">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheader"></a><span data-ttu-id="f682d-127">Munkarendelések projekttel (a Field Service alkalmazásból a Supply Chain Management alkalmazásba): WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="f682d-127">Work Orders with Project (Field Service to Supply Chain Management): WorkOrderHeader</span></span>

<span data-ttu-id="f682d-128">[![Sablonleképezés az adatintegrátorban](./media/FSWOP1.png)](./media/FSWOP1.png)</span><span class="sxs-lookup"><span data-stu-id="f682d-128">[![Template mapping in Data integration](./media/FSWOP1.png)](./media/FSWOP1.png)</span></span>

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheaderproject"></a><span data-ttu-id="f682d-129">Munkarendelések projekttel (a Field Service alkalmazásból a Supply Chain Management alkalmazásba): WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="f682d-129">Work Orders with Project (Field Service to Supply Chain Management): WorkOrderHeaderProject</span></span>

<span data-ttu-id="f682d-130">[![Sablonleképezés az adatintegrátorban](./media/FSWOP2.png)](./media/FSWOP2.png)</span><span class="sxs-lookup"><span data-stu-id="f682d-130">[![Template mapping in Data integration](./media/FSWOP2.png)](./media/FSWOP2.png)</span></span>

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderproduct"></a><span data-ttu-id="f682d-131">Munkarendelések projekttel (a Field Service alkalmazásból a Supply Chain Management alkalmazásba): WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="f682d-131">Work Orders with Project (Field Service to Supply Chain Management): WorkOrderProduct</span></span>

<span data-ttu-id="f682d-132">[![Sablonleképezés az adatintegrátorban](./media/FSWOP3.png)](./media/FSWOP3.png)</span><span class="sxs-lookup"><span data-stu-id="f682d-132">[![Template mapping in Data integration](./media/FSWOP3.png)](./media/FSWOP3.png)</span></span>

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderservice"></a><span data-ttu-id="f682d-133">Munkarendelések projekttel (a Field Service alkalmazásból a Supply Chain Management alkalmazásba): WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="f682d-133">Work Orders with Project (Field Service to Supply Chain Management): WorkOrderService</span></span>

<span data-ttu-id="f682d-134">[![Sablonleképezés az adatintegrátorban](./media/FSWOP4.png)](./media/FSWOP4.png)</span><span class="sxs-lookup"><span data-stu-id="f682d-134">[![Template mapping in Data integration](./media/FSWOP4.png)](./media/FSWOP4.png)</span></span>
