---
title: "Projekt beszerzési rendelései"
description: "Ez a cikk különböző a módszereket ismerteti, amelyekkel beszerzési rendeléseket hozhat létre egy projekthez. A használt módszer attól függ, hogy mi a beszerzési rendelés célja, hogy a cikkek mikor kerülnek felhasználásra, hogy mikor kerül sor a cikkek elszámolására egy projektnél."
author: twheeloc
manager: AnnBe
ms.date: 08/07/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 45d28110ca93875eb534c69886ac2074ea4fe737
ms.openlocfilehash: d55c999ed1f506a2d9487c8cc94bf0e9cce3bed1
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2017

---

# <a name="purchase-orders-for-a-project"></a><span data-ttu-id="70976-104">Projekt beszerzési rendelései</span><span class="sxs-lookup"><span data-stu-id="70976-104">Purchase orders for a project</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="70976-105">Ez a cikk különböző a módszereket ismerteti, amelyekkel beszerzési rendeléseket hozhat létre egy projekthez.</span><span class="sxs-lookup"><span data-stu-id="70976-105">This article describes the various methods that you can use to create purchase orders for a project.</span></span> <span data-ttu-id="70976-106">A használt módszer attól függ, hogy mi a beszerzési rendelés célja, hogy a cikkek mikor kerülnek felhasználásra, hogy mikor kerül sor a cikkek elszámolására egy projektnél.</span><span class="sxs-lookup"><span data-stu-id="70976-106">The method that you use depends on the purpose of the purchase order, and when the purchased items are consumed and charged to a project.</span></span>

<span data-ttu-id="70976-107">A Microsoft Dynamics 365 for Finance and Operations Enterprise edition rendszerben többféleképpen hozhat létre beszerzési rendeléseket egy projekthez.</span><span class="sxs-lookup"><span data-stu-id="70976-107">In Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, you can use multiple methods to create purchase orders for a project.</span></span> <span data-ttu-id="70976-108">A használt módszer attól függ, hogy mi a beszerzési rendelés célja, hogy a beszerzett cikkek mikor kerülnek felhasználásra, hogy mikor kerül sor a beszerzett cikkek elszámolására egy projektnél.</span><span class="sxs-lookup"><span data-stu-id="70976-108">The method that you use depends on the purpose of the purchase order, when the purchased items are consumed, and when the purchased items are charged to a project.</span></span>

### <a name="methods-for-creating-a-purchase-order"></a><span data-ttu-id="70976-109">Beszerzési rendelés létrehozásának módszerei</span><span class="sxs-lookup"><span data-stu-id="70976-109">Methods for creating a purchase order</span></span>

<span data-ttu-id="70976-110">A következő módszerek valamelyikét használhatja egy beszerzési rendelés létrehozásához a Projektvezetés és könyvelés modulban.</span><span class="sxs-lookup"><span data-stu-id="70976-110">You can use one of the following methods to create a purchase order in Project management and accounting.</span></span> <span data-ttu-id="70976-111">A beszerzési rendelés célja meghatározza, hogy mikor történik meg a beszerzési rendelés felhasználása, és így azt is, hogy mikor kerül sor a cikkek elszámolására egy projektnél.</span><span class="sxs-lookup"><span data-stu-id="70976-111">The purpose of the purchase order determines when the purchase order is consumed and, therefore, when items are charged to a project.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70976-112">Mód</span><span class="sxs-lookup"><span data-stu-id="70976-112">Method</span></span></th>
<th><span data-ttu-id="70976-113">Cél</span><span class="sxs-lookup"><span data-stu-id="70976-113">Purpose</span></span></th>
<th><span data-ttu-id="70976-114">Cikkek felhasználása</span><span class="sxs-lookup"><span data-stu-id="70976-114">Consumption of items</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="70976-115">Beszerzési rendelés létrehozása közvetlenül egy projektből.</span><span class="sxs-lookup"><span data-stu-id="70976-115">Create a purchase order directly from a project.</span></span></td>
<td><span data-ttu-id="70976-116">Ezzel a módszerrel a külső szállítótól egy projektben történő felhasználására szerezhet be cikkeket.</span><span class="sxs-lookup"><span data-stu-id="70976-116">Use this method to purchase items from an external vendor for consumption on a project.</span></span> <span data-ttu-id="70976-117">A beszerzési rendelést két módon hozhatja létre:</span><span class="sxs-lookup"><span data-stu-id="70976-117">You can create the purchase order in two ways:</span></span>
<ul>
<li><span data-ttu-id="70976-118">Magából a projektből.</span><span class="sxs-lookup"><span data-stu-id="70976-118">From the project itself.</span></span> <span data-ttu-id="70976-119">Ilyenkor eleve definiálva van a beszerzési rendelés projektje.</span><span class="sxs-lookup"><span data-stu-id="70976-119">In this case, the project is already defined for the purchase order.</span></span></li>
<li><span data-ttu-id="70976-120">A projekt beszerzési rendelés kikeresésével.</span><span class="sxs-lookup"><span data-stu-id="70976-120">By navigating to the project purchase order.</span></span> <span data-ttu-id="70976-121">Ki kell választani a létrehozandó beszerzési rendelés szállítóját és projektjét is.</span><span class="sxs-lookup"><span data-stu-id="70976-121">You must select both the vendor and the project to create the purchase order for.</span></span></li>
</ul></td>
<td><span data-ttu-id="70976-122">A cikkek felhasználása a szállítói számla frissítésekor történik.</span><span class="sxs-lookup"><span data-stu-id="70976-122">Items are consumed when the vendor invoice is updated.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="70976-123">Beszerzési rendelés létrehozása egy értékesítési rendelés alapján.</span><span class="sxs-lookup"><span data-stu-id="70976-123">Create a purchase order from a sales order.</span></span></td>
<td><span data-ttu-id="70976-124">Akkor használja ezt a módszert cikkek beszerzésére, amikor egy értékesítési rendelést hoz létre egy projektben.</span><span class="sxs-lookup"><span data-stu-id="70976-124">Use this method to purchase items when you create a sales order from a project.</span></span></td>
<td><span data-ttu-id="70976-125">A cikkek felhasználása az értékesítési rendelés vevőnek való számlázása esetén történik meg.</span><span class="sxs-lookup"><span data-stu-id="70976-125">Items are consumed when the sales order is invoiced to the customer.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="70976-126">Beszerzési rendelés létrehozása cikkszükségletből.</span><span class="sxs-lookup"><span data-stu-id="70976-126">Create a purchase order from an item requirement.</span></span></td>
<td><span data-ttu-id="70976-127">Akkor használja ezt a módszert cikkek beszerzésére, amikor cikkszükségletet hoz létre egy projektből.</span><span class="sxs-lookup"><span data-stu-id="70976-127">Use this method to purchase items when you create an item requirement from a project.</span></span></td>
<td><span data-ttu-id="70976-128">A cikkek felhasználása akkor történik meg, amikor a cikkszükséglet csomagjegyzéke frissül.</span><span class="sxs-lookup"><span data-stu-id="70976-128">Items are consumed when the item requirement packing slip is updated.</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE] 
> <span data-ttu-id="70976-129">Ha frissíti a szállítói számlát vagy a szállítólevelet, a program figyelmezteti, hogy a cikkszükséglet szállítólevelét is frissítse.</span><span class="sxs-lookup"><span data-stu-id="70976-129">When you update the vendor invoice or packing slip, you're prompted to update the packing slip on the item requirement.</span></span>

<span data-ttu-id="70976-130">További tudnivalókért lásd: [Cikkek átvétele cikkszükségletből származó beszerzési rendelés alapján](tasks/receive-items-purchase-order-item-requirement.md).</span><span class="sxs-lookup"><span data-stu-id="70976-130">For more information, see [Receive items on purchase order from item requirement](tasks/receive-items-purchase-order-item-requirement.md).</span></span>


