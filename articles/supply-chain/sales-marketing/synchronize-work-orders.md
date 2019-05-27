---
title: Projektszámmal rendelkező munkarendelések szinkronizálása a Field Service alkalmazásból a Finance and Operations alkalmazásba
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatot, amelye a Microsoft Dynamics 365 for Field Service munkarendeléseinek a Microsoft Dynamics 365 for Finance and Operations szolgáltatásban található projektszámaival történő szinkronizálására használatos.
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
ms.openlocfilehash: 5ca01b085315d916a18c512af28fc7534ce76ee8
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1536733"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a><span data-ttu-id="94186-103">Projektszámmal rendelkező munkarendelések szinkronizálása a Field Service alkalmazásból a Finance and Operations alkalmazásba</span><span class="sxs-lookup"><span data-stu-id="94186-103">Synchronize work orders with project from Field Service to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="94186-104">Ez a témakör bemutatja a sablonokat és a mögöttes feladatot, amelye a Microsoft Dynamics 365 for Field Service munkarendeléseinek a Microsoft Dynamics 365 for Finance and Operations szolgáltatásban található projektszámaival történő szinkronizálására használatos.</span><span class="sxs-lookup"><span data-stu-id="94186-104">This topic discusses the templates and underlying task that are used to synchronize work orders with a project number from Microsoft Dynamics 365 for Field Service to Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="94186-105">[![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span><span class="sxs-lookup"><span data-stu-id="94186-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span></span>

<span data-ttu-id="94186-106">A használt **Mukerdnelések projektekkel (Fin and Ops – Field and Ops)** sablon a **Munkarendelések (Field Service – Fin and Ops)** sablonon alapul.</span><span class="sxs-lookup"><span data-stu-id="94186-106">The used **Work Orders with Project (Field Service to Fin and Ops)** template is based on the **Work Orders (Field Service to Fin and Ops)** template.</span></span> <span data-ttu-id="94186-107">További információért, lásd: [A Field Service szolgáltatásokban lévő munkarendelések szinkronizálása a Finance and Operations értékesítési rendeléseivel](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order)</span><span class="sxs-lookup"><span data-stu-id="94186-107">For more information, see [Synchronize work orders in Field Service to sales orders in Finance and Operations](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

<span data-ttu-id="94186-108">Ez a témakör csak a két sablonok eltéréseit írja le:</span><span class="sxs-lookup"><span data-stu-id="94186-108">This topic only describes the differences between the two templates:</span></span>
- <span data-ttu-id="94186-109">**Munkarendelések projektszámmal (a Field Service alkalmazásból a Fin and Ops alkalmazásba)**</span><span class="sxs-lookup"><span data-stu-id="94186-109">**Work Orders with Project (Field Service to Fin and Ops)**</span></span>
- <span data-ttu-id="94186-110">**Munkarendelések (a Field Service alkalmazásból a Fin and Ops alkalmazásba)**</span><span class="sxs-lookup"><span data-stu-id="94186-110">**Work Orders (Field Service to Fin and Ops)**</span></span>

<span data-ttu-id="94186-111">A fő különbség, hogy ez a sablon tartalmazza a munkarendeléshez hozzárendelt projektszámot a Field Service megoldásban, ami biztosítja, hogy a Finance and Operations megoldásban létrehozott értékesítési rendelés tartalmazza a projektszámot, és hogy megtörténhessen a számlázás a kapcsolódó projektben.</span><span class="sxs-lookup"><span data-stu-id="94186-111">The main difference is that this template includes mapping of the project number asigned to the Work order in Field Service, ensuring that the Sales order created in Finance and Operations include the project number and that invoicing can happen on the related project.</span></span> <span data-ttu-id="94186-112">Emellett a sablon használja a speciális lekérdezés és szűrést.</span><span class="sxs-lookup"><span data-stu-id="94186-112">Besides this the template use Advanced Query and Filtering.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="94186-113">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="94186-113">Templates and tasks</span></span>

<span data-ttu-id="94186-114">**A sablon neve az adatintegrációban:**</span><span class="sxs-lookup"><span data-stu-id="94186-114">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="94186-115">Munkarendelések projektszámmal (a Field Service alkalmazásból a Fin and Ops alkalmazásba)</span><span class="sxs-lookup"><span data-stu-id="94186-115">Work Orders with Project (Field Service to Fin and Ops)</span></span>

<span data-ttu-id="94186-116">**A feladat neve az adatintegrációs projektben:**</span><span class="sxs-lookup"><span data-stu-id="94186-116">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="94186-117">WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="94186-117">WorkOrderHeader</span></span>
- <span data-ttu-id="94186-118">WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="94186-118">WorkOrderHeaderProject</span></span>
- <span data-ttu-id="94186-119">WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="94186-119">WorkOrderProduct</span></span>
- <span data-ttu-id="94186-120">WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="94186-120">WorkOrderService</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="94186-121">Field Service CRM megoldás</span><span class="sxs-lookup"><span data-stu-id="94186-121">Field Service CRM solution</span></span>
<span data-ttu-id="94186-122">A **Külső projekt** mezőt hozzáadtuk a munkarendelés entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="94186-122">The **External Project** field has been added to the Work Order entity.</span></span> <span data-ttu-id="94186-123">Ez a mező egy keresés és vásárlás, felcímkézi a Munkarendelést egy projekttel, majd az értékesítési rendelés kapcsolódik egy projekthez a Finance and Operations megoldáson belül.</span><span class="sxs-lookup"><span data-stu-id="94186-123">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Finance and Operations.</span></span> <span data-ttu-id="94186-124">Miután a **Rendszer állapota** Nyitott – folyamatban (690,970,000) állapotból magasabb állapba kerül, a **Külső projekt** mezőt a rendszer zárolja, és nem lehet felvenni, törölni vagy módosítani az értéket.</span><span class="sxs-lookup"><span data-stu-id="94186-124">Ones the **System Status** changes from Open – In Progress(690,970,000) to a higher status the **External Project** field will be locked and you can't add, remove or change the value.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="94186-125">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="94186-125">Template mapping in Data integration</span></span>

<span data-ttu-id="94186-126">Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.</span><span class="sxs-lookup"><span data-stu-id="94186-126">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderheader"></a><span data-ttu-id="94186-127">Munkarendelések projektszámmal (a Field Service alkalmazásból a Fin and Ops alkalmazásba): WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="94186-127">Work Orders with Project (Field Service to Fin and Ops): WorkOrderHeader</span></span>

<span data-ttu-id="94186-128">[![Sablonleképezés az adatintegrátorban](./media/FSWOP1.png)](./media/FSWOP1.png)</span><span class="sxs-lookup"><span data-stu-id="94186-128">[![Template mapping in Data integration](./media/FSWOP1.png)](./media/FSWOP1.png)</span></span>

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderheaderproject"></a><span data-ttu-id="94186-129">Munkarendelések projekttel(a Field Service alkalmazásból a Fin and Ops alkalmazásba): WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="94186-129">Work Orders with Project (Field Service to Fin and Ops): WorkOrderHeaderProject</span></span>

<span data-ttu-id="94186-130">[![Sablonleképezés az adatintegrátorban](./media/FSWOP2.png)](./media/FSWOP2.png)</span><span class="sxs-lookup"><span data-stu-id="94186-130">[![Template mapping in Data integration](./media/FSWOP2.png)](./media/FSWOP2.png)</span></span>

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderproduct"></a><span data-ttu-id="94186-131">Munkarendelések projekttel (a Field Service alkalmazásból a Fin and Ops alkalmazásba): WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="94186-131">Work Orders with Project (Field Service to Fin and Ops): WorkOrderProduct</span></span>

<span data-ttu-id="94186-132">[![Sablonleképezés az adatintegrátorban](./media/FSWOP3.png)](./media/FSWOP3.png)</span><span class="sxs-lookup"><span data-stu-id="94186-132">[![Template mapping in Data integration](./media/FSWOP3.png)](./media/FSWOP3.png)</span></span>

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderservice"></a><span data-ttu-id="94186-133">Munkarendelések projekttel (a Field Service alkalmazásból a Fin and Ops alkalmazásba): WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="94186-133">Work Orders with Project (Field Service to Fin and Ops): WorkOrderService</span></span>

<span data-ttu-id="94186-134">[![Sablonleképezés az adatintegrátorban](./media/FSWOP4.png)](./media/FSWOP4.png)</span><span class="sxs-lookup"><span data-stu-id="94186-134">[![Template mapping in Data integration](./media/FSWOP4.png)](./media/FSWOP4.png)</span></span>
