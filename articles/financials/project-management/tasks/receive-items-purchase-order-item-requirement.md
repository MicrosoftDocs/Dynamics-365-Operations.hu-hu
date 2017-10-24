--- 
title: "Cikkek átvétele cikkszükségletből származó beszerzési rendelés alapján"
description: "Ez az eljárás bemutatja, hogyan lehet cikkeket átvenni beszerzési rendeléssel egy cikkszükségletből."
author: KimANelson
manager: AnnBe
ms.date: 02/13/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 0fa70da5e06d1bc82fb9d2419bb0a7c8dd0da467
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="receive-items-on-purchase-order-from-item-requirement"></a><span data-ttu-id="9b01a-103">Cikkek átvétele cikkszükségletből származó beszerzési rendelés alapján</span><span class="sxs-lookup"><span data-stu-id="9b01a-103">Receive items on purchase order from item requirement</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9b01a-104">Ez az eljárás bemutatja, hogyan lehet cikkeket átvenni beszerzési rendeléssel egy cikkszükségletből.</span><span class="sxs-lookup"><span data-stu-id="9b01a-104">This procedure shows how to receive items on a purchase order from an item requirement.</span></span>

<span data-ttu-id="9b01a-105">Ha cikktranzakció helyett cikkszükségletet használ, közvetlenül a cikk tényleges felhasználása előttre tervezheti a szállítást, beszerzési rendelést hozhat létre, a cikket szerepeltetheti a kereskedelmi megállapodási keretrendszerben, és a cikkszükségletet szerepeltetheti a gyártástervezésben.</span><span class="sxs-lookup"><span data-stu-id="9b01a-105">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span> 

<span data-ttu-id="9b01a-106">Ez a feladat az USSI-adatkészletet használja.</span><span class="sxs-lookup"><span data-stu-id="9b01a-106">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="9b01a-107">Ugorjon a Projektvezetés és könyvelés > Projektek > Minden projekt pontra.</span><span class="sxs-lookup"><span data-stu-id="9b01a-107">Go to Project management and accounting > Projects > All projects.</span></span>
2. <span data-ttu-id="9b01a-108">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="9b01a-108">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="9b01a-109">A Művelet panelen kattintson a Terv elemre.</span><span class="sxs-lookup"><span data-stu-id="9b01a-109">On the Action Pane, click Plan.</span></span>
4. <span data-ttu-id="9b01a-110">Kattintson a cikkszükségletek elemre.</span><span class="sxs-lookup"><span data-stu-id="9b01a-110">Click Item requirements.</span></span>
5. <span data-ttu-id="9b01a-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9b01a-111">Click New.</span></span>
6. <span data-ttu-id="9b01a-112">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="9b01a-112">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="9b01a-113">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9b01a-113">In the Item number field, enter or select a value.</span></span>
8. <span data-ttu-id="9b01a-114">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="9b01a-114">In the Quantity field, enter a number.</span></span>
9. <span data-ttu-id="9b01a-115">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="9b01a-115">Click Save.</span></span>
10. <span data-ttu-id="9b01a-116">A Művelet panelen kattintson a Kezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="9b01a-116">On the Action Pane, click Manage.</span></span>
11. <span data-ttu-id="9b01a-117">Kattintson a Funkciók elemre.</span><span class="sxs-lookup"><span data-stu-id="9b01a-117">Click Functions.</span></span>
12. <span data-ttu-id="9b01a-118">Kattintson a Beszerzési rendelés létrehozása elemre.</span><span class="sxs-lookup"><span data-stu-id="9b01a-118">Click Create purchase order.</span></span>
13. <span data-ttu-id="9b01a-119">Jelölje be a Szerepeljen jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="9b01a-119">Select the Include check box.</span></span>
14. <span data-ttu-id="9b01a-120">A Szállítószámla mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9b01a-120">In the Vendor account field, enter or select a value.</span></span>
15. <span data-ttu-id="9b01a-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9b01a-121">Click OK.</span></span>
16. <span data-ttu-id="9b01a-122">Nyissa meg a következőt: Kötelezettségek > Beszerzési rendelések > Minden beszerzési rendelés.</span><span class="sxs-lookup"><span data-stu-id="9b01a-122">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
17. <span data-ttu-id="9b01a-123">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="9b01a-123">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="9b01a-124">A Művelet panelen kattintson a Beszerzés elemre.</span><span class="sxs-lookup"><span data-stu-id="9b01a-124">On the Action Pane, click Purchase.</span></span>
19. <span data-ttu-id="9b01a-125">Kattintson a Megerősítés gombra.</span><span class="sxs-lookup"><span data-stu-id="9b01a-125">Click Confirm.</span></span>
20. <span data-ttu-id="9b01a-126">A Művelet panelen kattintson a Bevételezés elemre.</span><span class="sxs-lookup"><span data-stu-id="9b01a-126">On the Action Pane, click Receive.</span></span>
21. <span data-ttu-id="9b01a-127">Kattintson a Termékbevételezés elemre.</span><span class="sxs-lookup"><span data-stu-id="9b01a-127">Click Product receipt.</span></span>
22. <span data-ttu-id="9b01a-128">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="9b01a-128">In the list, mark the selected row.</span></span>
23. <span data-ttu-id="9b01a-129">Írjon be egy értéket a Termékbevételezés mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9b01a-129">In the Product receipt field, type a value.</span></span>
24. <span data-ttu-id="9b01a-130">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9b01a-130">Click OK.</span></span>

