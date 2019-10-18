---
title: Cikkek átvétele cikkszükségletből származó beszerzési rendelés alapján
description: Ez a cikk bemutatja, hogyan lehet cikkeket átvenni beszerzési rendeléssel egy cikkszükségletből.
author: KimANelson
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage, ProjTable, ProjSalesItemReq, InventItemIdLookupSimple, PurchCreateFromSalesOrder, VendAccountItemLookup, PurchTable, PurchEditLines
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7afdae65c5ae7e3196c6b9f142dd87aec39b5ea3
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174420"
---
# <a name="receive-items-on-purchase-order-from-item-requirement"></a><span data-ttu-id="ec7af-103">Cikkek átvétele cikkszükségletből származó beszerzési rendelés alapján</span><span class="sxs-lookup"><span data-stu-id="ec7af-103">Receive items on purchase order from item requirement</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ec7af-104">Ez a cikk bemutatja, hogyan lehet cikkeket átvenni beszerzési rendeléssel egy cikkszükségletből.</span><span class="sxs-lookup"><span data-stu-id="ec7af-104">This topic explains how to receive items on a purchase order from an item requirement.</span></span>

<span data-ttu-id="ec7af-105">Ha cikktranzakció helyett cikkszükségletet használ, közvetlenül a cikk tényleges felhasználása előttre tervezheti a szállítást, beszerzési rendelést hozhat létre, a cikket szerepeltetheti a kereskedelmi megállapodási keretrendszerben, és a cikkszükségletet szerepeltetheti a gyártástervezésben.</span><span class="sxs-lookup"><span data-stu-id="ec7af-105">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span> 

<span data-ttu-id="ec7af-106">Ez a feladat az USSI-adatkészletet használja.</span><span class="sxs-lookup"><span data-stu-id="ec7af-106">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="ec7af-107">A navigációs ablakban lépjen a **Modulok > Projektvezetés és könyvelés > Projektek > Minden projekt** részre.</span><span class="sxs-lookup"><span data-stu-id="ec7af-107">In the navigation pane, go to **Modules > Project management and accounting > Projects > All projects**.</span></span>
2. <span data-ttu-id="ec7af-108">A listában válassza ki a kívánt sorból a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="ec7af-108">In the list, select the link in the desired row.</span></span>
3. <span data-ttu-id="ec7af-109">A Műveleti ablaktáblán kattintson a **Tervezés** elemre.</span><span class="sxs-lookup"><span data-stu-id="ec7af-109">On the Action Pane, select **Plan**.</span></span>
4. <span data-ttu-id="ec7af-110">Válassza a **Cikkszükséglet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ec7af-110">Select **Item requirements**.</span></span>
5. <span data-ttu-id="ec7af-111">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ec7af-111">Select **New**.</span></span>
6. <span data-ttu-id="ec7af-112">Az új sorban adjon meg, vagy válasszon ki egy értéket a **Cikkszám** mezőben.</span><span class="sxs-lookup"><span data-stu-id="ec7af-112">In the new row, enter or select a value in the **Item number** field.</span></span>
7. <span data-ttu-id="ec7af-113">Adjon meg egy számot a **Mennyiség** mezőben.</span><span class="sxs-lookup"><span data-stu-id="ec7af-113">In the **Quantity** field, enter a number.</span></span>
8. <span data-ttu-id="ec7af-114">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ec7af-114">Select **Save**.</span></span>
9. <span data-ttu-id="ec7af-115">A műveleti ablaktáblán válassza a **Kezelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ec7af-115">On the Action Pane, select **Manage**.</span></span>
10. <span data-ttu-id="ec7af-116">Válassza a **Funkciók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ec7af-116">Select **Functions**.</span></span>
11. <span data-ttu-id="ec7af-117">Válassza a **Beszerzési rendelés létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ec7af-117">Select **Create purchase order**.</span></span>
12. <span data-ttu-id="ec7af-118">Jelölje be **Az összes belefoglalása** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="ec7af-118">Select the **Include all** check box.</span></span>
13. <span data-ttu-id="ec7af-119">A **Szállítószámla** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ec7af-119">In the **Vendor account** field, enter or select a value.</span></span>
14. <span data-ttu-id="ec7af-120">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ec7af-120">Select **OK**.</span></span>
15. <span data-ttu-id="ec7af-121">A navigációs ablaktáblán nyissa meg a **Modulok > Kötelezettségek > beszerzési rendelések > Összes beszerzési rendelés** pontot.</span><span class="sxs-lookup"><span data-stu-id="ec7af-121">In the navigation pane, go to **Modules > Accounts payable > Purchase orders > All purchase orders**.</span></span>
16. <span data-ttu-id="ec7af-122">A listában válassza ki a kívánt sorból a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="ec7af-122">In the list, select the link in the desired row.</span></span>
17. <span data-ttu-id="ec7af-123">A Műveleti ablaktáblán válassza ki a **Beszerzés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ec7af-123">On the Action Pane, select **Purchase**.</span></span>
18. <span data-ttu-id="ec7af-124">Válassza ki a **Megerősítés** elemet.</span><span class="sxs-lookup"><span data-stu-id="ec7af-124">Select **Confirm**.</span></span>
19. <span data-ttu-id="ec7af-125">A Művelet ablaktáblán válassza ki a **Bevételezés** elemet.</span><span class="sxs-lookup"><span data-stu-id="ec7af-125">On the Action Pane, select **Receive**.</span></span>
20. <span data-ttu-id="ec7af-126">Válassza ki a **Termékbevételezés** elemet.</span><span class="sxs-lookup"><span data-stu-id="ec7af-126">Select **Product receipt**.</span></span>
21. <span data-ttu-id="ec7af-127">Írjon be egy értéket a **Termékbevételezés** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ec7af-127">In the **Product receipt** field, type a value.</span></span>
22. <span data-ttu-id="ec7af-128">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ec7af-128">Select **OK**.</span></span>

