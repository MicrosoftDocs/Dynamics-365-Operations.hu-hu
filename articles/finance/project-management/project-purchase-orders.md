---
title: Projekt beszerzési rendelései
description: Ez a cikk különböző a módszereket ismerteti, amelyekkel beszerzési rendeléseket hozhat létre egy projekthez. A használt módszer attól függ, hogy mi a beszerzési rendelés célja, hogy a cikkek mikor kerülnek felhasználásra, hogy mikor kerül sor a cikkek elszámolására egy projektnél.
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a4975b9f9e20906fb1259e36a07d8ef3db4f4fee
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174558"
---
# <a name="purchase-orders-for-a-project"></a><span data-ttu-id="79191-104">Projekt beszerzési rendelései</span><span class="sxs-lookup"><span data-stu-id="79191-104">Purchase orders for a project</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="79191-105">Ez a cikk különböző a módszereket ismerteti, amelyekkel beszerzési rendeléseket hozhat létre egy projekthez.</span><span class="sxs-lookup"><span data-stu-id="79191-105">This article describes the various methods that you can use to create purchase orders for a project.</span></span> <span data-ttu-id="79191-106">A használt módszer attól függ, hogy mi a beszerzési rendelés célja, hogy a cikkek mikor kerülnek felhasználásra, hogy mikor kerül sor a cikkek elszámolására egy projektnél.</span><span class="sxs-lookup"><span data-stu-id="79191-106">The method that you use depends on the purpose of the purchase order, and when the purchased items are consumed and charged to a project.</span></span>

### <a name="methods-for-creating-a-purchase-order"></a><span data-ttu-id="79191-107">Beszerzési rendelés létrehozásának módszerei</span><span class="sxs-lookup"><span data-stu-id="79191-107">Methods for creating a purchase order</span></span>

<span data-ttu-id="79191-108">A következő módszerek valamelyikét használhatja egy beszerzési rendelés létrehozásához a Projektvezetés és könyvelés modulban.</span><span class="sxs-lookup"><span data-stu-id="79191-108">You can use one of the following methods to create a purchase order in Project management and accounting.</span></span> <span data-ttu-id="79191-109">A beszerzési rendelés célja meghatározza, hogy mikor történik meg a beszerzési rendelés felhasználása, és így azt is, hogy mikor kerül sor a cikkek elszámolására egy projektnél.</span><span class="sxs-lookup"><span data-stu-id="79191-109">The purpose of the purchase order determines when the purchase order is consumed and, therefore, when items are charged to a project.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79191-110">Mód</span><span class="sxs-lookup"><span data-stu-id="79191-110">Method</span></span></th>
<th><span data-ttu-id="79191-111">Cél</span><span class="sxs-lookup"><span data-stu-id="79191-111">Purpose</span></span></th>
<th><span data-ttu-id="79191-112">Cikkek felhasználása</span><span class="sxs-lookup"><span data-stu-id="79191-112">Consumption of items</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="79191-113">Beszerzési rendelés létrehozása közvetlenül egy projektből.</span><span class="sxs-lookup"><span data-stu-id="79191-113">Create a purchase order directly from a project.</span></span></td>
<td><span data-ttu-id="79191-114">Ezzel a módszerrel a külső szállítótól egy projektben történő felhasználására szerezhet be cikkeket.</span><span class="sxs-lookup"><span data-stu-id="79191-114">Use this method to purchase items from an external vendor for consumption on a project.</span></span> <span data-ttu-id="79191-115">A beszerzési rendelést két módon hozhatja létre:</span><span class="sxs-lookup"><span data-stu-id="79191-115">You can create the purchase order in two ways:</span></span>
<ul>
<li><span data-ttu-id="79191-116">Magából a projektből.</span><span class="sxs-lookup"><span data-stu-id="79191-116">From the project itself.</span></span> <span data-ttu-id="79191-117">Ilyenkor eleve definiálva van a beszerzési rendelés projektje.</span><span class="sxs-lookup"><span data-stu-id="79191-117">In this case, the project is already defined for the purchase order.</span></span></li>
<li><span data-ttu-id="79191-118">A projekt beszerzési rendelés kikeresésével.</span><span class="sxs-lookup"><span data-stu-id="79191-118">By navigating to the project purchase order.</span></span> <span data-ttu-id="79191-119">Ki kell választani a létrehozandó beszerzési rendelés szállítóját és projektjét is.</span><span class="sxs-lookup"><span data-stu-id="79191-119">You must select both the vendor and the project to create the purchase order for.</span></span></li>
</ul></td>
<td><span data-ttu-id="79191-120">A cikkek felhasználása a szállítói számla frissítésekor történik.</span><span class="sxs-lookup"><span data-stu-id="79191-120">Items are consumed when the vendor invoice is updated.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="79191-121">Beszerzési rendelés létrehozása egy értékesítési rendelés alapján.</span><span class="sxs-lookup"><span data-stu-id="79191-121">Create a purchase order from a sales order.</span></span></td>
<td><span data-ttu-id="79191-122">Akkor használja ezt a módszert cikkek beszerzésére, amikor egy értékesítési rendelést hoz létre egy projektben.</span><span class="sxs-lookup"><span data-stu-id="79191-122">Use this method to purchase items when you create a sales order from a project.</span></span></td>
<td><span data-ttu-id="79191-123">A cikkek felhasználása az értékesítési rendelés vevőnek való számlázása esetén történik meg.</span><span class="sxs-lookup"><span data-stu-id="79191-123">Items are consumed when the sales order is invoiced to the customer.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="79191-124">Beszerzési rendelés létrehozása cikkszükségletből.</span><span class="sxs-lookup"><span data-stu-id="79191-124">Create a purchase order from an item requirement.</span></span></td>
<td><span data-ttu-id="79191-125">Akkor használja ezt a módszert cikkek beszerzésére, amikor cikkszükségletet hoz létre egy projektből.</span><span class="sxs-lookup"><span data-stu-id="79191-125">Use this method to purchase items when you create an item requirement from a project.</span></span></td>
<td><span data-ttu-id="79191-126">A cikkek felhasználása akkor történik meg, amikor a cikkszükséglet csomagjegyzéke frissül.</span><span class="sxs-lookup"><span data-stu-id="79191-126">Items are consumed when the item requirement packing slip is updated.</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE] 
> <span data-ttu-id="79191-127">Ha frissíti a szállítói számlát vagy a szállítólevelet, a program figyelmezteti, hogy a cikkszükséglet szállítólevelét is frissítse.</span><span class="sxs-lookup"><span data-stu-id="79191-127">When you update the vendor invoice or packing slip, you're prompted to update the packing slip on the item requirement.</span></span>

<span data-ttu-id="79191-128">További tudnivalókért lásd: [Cikkek átvétele cikkszükségletből származó beszerzési rendelés alapján](tasks/receive-items-purchase-order-item-requirement.md).</span><span class="sxs-lookup"><span data-stu-id="79191-128">For more information, see [Receive items on purchase order from item requirement](tasks/receive-items-purchase-order-item-requirement.md).</span></span>

