---
title: "Projekt beszerzési rendelései"
description: "Ez a cikk különböző a módszereket ismerteti, amelyekkel beszerzési rendeléseket hozhat létre egy projekthez. A használt módszer attól függ, hogy mi a beszerzési rendelés célja, hogy a cikkek mikor kerülnek felhasználásra, hogy mikor kerül sor a cikkek elszámolására egy projektnél."
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: dae65394a2180ccbf3317a41b635ba97034e541b
ms.contentlocale: hu-hu
ms.lasthandoff: 03/26/2018

---

# <a name="purchase-orders-for-a-project"></a><span data-ttu-id="6db2a-104">Projekt beszerzési rendelései</span><span class="sxs-lookup"><span data-stu-id="6db2a-104">Purchase orders for a project</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="6db2a-105">Ez a cikk különböző a módszereket ismerteti, amelyekkel beszerzési rendeléseket hozhat létre egy projekthez.</span><span class="sxs-lookup"><span data-stu-id="6db2a-105">This article describes the various methods that you can use to create purchase orders for a project.</span></span> <span data-ttu-id="6db2a-106">A használt módszer attól függ, hogy mi a beszerzési rendelés célja, hogy a cikkek mikor kerülnek felhasználásra, hogy mikor kerül sor a cikkek elszámolására egy projektnél.</span><span class="sxs-lookup"><span data-stu-id="6db2a-106">The method that you use depends on the purpose of the purchase order, and when the purchased items are consumed and charged to a project.</span></span>

<span data-ttu-id="6db2a-107">A Microsoft Dynamics 365 for Finance and Operations rendszerben többféleképpen hozhat létre beszerzési rendeléseket egy projekthez.</span><span class="sxs-lookup"><span data-stu-id="6db2a-107">In Microsoft Dynamics 365 for Finance and Operations, you can use multiple methods to create purchase orders for a project.</span></span> <span data-ttu-id="6db2a-108">A használt módszer attól függ, hogy mi a beszerzési rendelés célja, hogy a beszerzett cikkek mikor kerülnek felhasználásra, hogy mikor kerül sor a beszerzett cikkek elszámolására egy projektnél.</span><span class="sxs-lookup"><span data-stu-id="6db2a-108">The method that you use depends on the purpose of the purchase order, when the purchased items are consumed, and when the purchased items are charged to a project.</span></span>

### <a name="methods-for-creating-a-purchase-order"></a><span data-ttu-id="6db2a-109">Beszerzési rendelés létrehozásának módszerei</span><span class="sxs-lookup"><span data-stu-id="6db2a-109">Methods for creating a purchase order</span></span>

<span data-ttu-id="6db2a-110">A következő módszerek valamelyikét használhatja egy beszerzési rendelés létrehozásához a Projektvezetés és könyvelés modulban.</span><span class="sxs-lookup"><span data-stu-id="6db2a-110">You can use one of the following methods to create a purchase order in Project management and accounting.</span></span> <span data-ttu-id="6db2a-111">A beszerzési rendelés célja meghatározza, hogy mikor történik meg a beszerzési rendelés felhasználása, és így azt is, hogy mikor kerül sor a cikkek elszámolására egy projektnél.</span><span class="sxs-lookup"><span data-stu-id="6db2a-111">The purpose of the purchase order determines when the purchase order is consumed and, therefore, when items are charged to a project.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6db2a-112">Mód</span><span class="sxs-lookup"><span data-stu-id="6db2a-112">Method</span></span></th>
<th><span data-ttu-id="6db2a-113">Cél</span><span class="sxs-lookup"><span data-stu-id="6db2a-113">Purpose</span></span></th>
<th><span data-ttu-id="6db2a-114">Cikkek felhasználása</span><span class="sxs-lookup"><span data-stu-id="6db2a-114">Consumption of items</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="6db2a-115">Beszerzési rendelés létrehozása közvetlenül egy projektből.</span><span class="sxs-lookup"><span data-stu-id="6db2a-115">Create a purchase order directly from a project.</span></span></td>
<td><span data-ttu-id="6db2a-116">Ezzel a módszerrel a külső szállítótól egy projektben történő felhasználására szerezhet be cikkeket.</span><span class="sxs-lookup"><span data-stu-id="6db2a-116">Use this method to purchase items from an external vendor for consumption on a project.</span></span> <span data-ttu-id="6db2a-117">A beszerzési rendelést két módon hozhatja létre:</span><span class="sxs-lookup"><span data-stu-id="6db2a-117">You can create the purchase order in two ways:</span></span>
<ul>
<li><span data-ttu-id="6db2a-118">Magából a projektből.</span><span class="sxs-lookup"><span data-stu-id="6db2a-118">From the project itself.</span></span> <span data-ttu-id="6db2a-119">Ilyenkor eleve definiálva van a beszerzési rendelés projektje.</span><span class="sxs-lookup"><span data-stu-id="6db2a-119">In this case, the project is already defined for the purchase order.</span></span></li>
<li><span data-ttu-id="6db2a-120">A projekt beszerzési rendelés kikeresésével.</span><span class="sxs-lookup"><span data-stu-id="6db2a-120">By navigating to the project purchase order.</span></span> <span data-ttu-id="6db2a-121">Ki kell választani a létrehozandó beszerzési rendelés szállítóját és projektjét is.</span><span class="sxs-lookup"><span data-stu-id="6db2a-121">You must select both the vendor and the project to create the purchase order for.</span></span></li>
</ul></td>
<td><span data-ttu-id="6db2a-122">A cikkek felhasználása a szállítói számla frissítésekor történik.</span><span class="sxs-lookup"><span data-stu-id="6db2a-122">Items are consumed when the vendor invoice is updated.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6db2a-123">Beszerzési rendelés létrehozása egy értékesítési rendelés alapján.</span><span class="sxs-lookup"><span data-stu-id="6db2a-123">Create a purchase order from a sales order.</span></span></td>
<td><span data-ttu-id="6db2a-124">Akkor használja ezt a módszert cikkek beszerzésére, amikor egy értékesítési rendelést hoz létre egy projektben.</span><span class="sxs-lookup"><span data-stu-id="6db2a-124">Use this method to purchase items when you create a sales order from a project.</span></span></td>
<td><span data-ttu-id="6db2a-125">A cikkek felhasználása az értékesítési rendelés vevőnek való számlázása esetén történik meg.</span><span class="sxs-lookup"><span data-stu-id="6db2a-125">Items are consumed when the sales order is invoiced to the customer.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6db2a-126">Beszerzési rendelés létrehozása cikkszükségletből.</span><span class="sxs-lookup"><span data-stu-id="6db2a-126">Create a purchase order from an item requirement.</span></span></td>
<td><span data-ttu-id="6db2a-127">Akkor használja ezt a módszert cikkek beszerzésére, amikor cikkszükségletet hoz létre egy projektből.</span><span class="sxs-lookup"><span data-stu-id="6db2a-127">Use this method to purchase items when you create an item requirement from a project.</span></span></td>
<td><span data-ttu-id="6db2a-128">A cikkek felhasználása akkor történik meg, amikor a cikkszükséglet csomagjegyzéke frissül.</span><span class="sxs-lookup"><span data-stu-id="6db2a-128">Items are consumed when the item requirement packing slip is updated.</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE] 
> <span data-ttu-id="6db2a-129">Ha frissíti a szállítói számlát vagy a szállítólevelet, a program figyelmezteti, hogy a cikkszükséglet szállítólevelét is frissítse.</span><span class="sxs-lookup"><span data-stu-id="6db2a-129">When you update the vendor invoice or packing slip, you're prompted to update the packing slip on the item requirement.</span></span>

<span data-ttu-id="6db2a-130">További tudnivalókért lásd: [Cikkek átvétele cikkszükségletből származó beszerzési rendelés alapján](tasks/receive-items-purchase-order-item-requirement.md).</span><span class="sxs-lookup"><span data-stu-id="6db2a-130">For more information, see [Receive items on purchase order from item requirement](tasks/receive-items-purchase-order-item-requirement.md).</span></span>


