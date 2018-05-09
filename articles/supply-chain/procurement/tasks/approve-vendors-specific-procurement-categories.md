--- 
title: "Szállítók jóváhagyása konkrét beszerzési kategóriákra vonatkozóan"
description: "Amikor egy beszerzési igénylést hoznak létre, lehet szükséges lesz egy engedélyezett vagy preferált szállító kiválasztása, attól függően, hogy a beszerzési irányelvek hogy vannak beállítva."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 26aa675e51957596cce9a1147df1fa300fcfe351
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="approve-vendors-for-specific-procurement-categories"></a><span data-ttu-id="6cc64-103">Szállítók jóváhagyása konkrét beszerzési kategóriákra vonatkozóan</span><span class="sxs-lookup"><span data-stu-id="6cc64-103">Approve vendors for specific procurement categories</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6cc64-104">Amikor egy beszerzési igénylést hoznak létre, lehet szükséges lesz egy engedélyezett vagy preferált szállító kiválasztása, attól függően, hogy a beszerzési irányelvek hogy vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="6cc64-104">When a purchase requisition is created, there may be a requirement to select an approved or preferred vendor, depending on how the purchasing policies are set up.</span></span> <span data-ttu-id="6cc64-105">Ez az eljárás bemutatja, hogyan adja meg, hogy a szállító jóváhagyott vagy preferált egy adott beszerzési kategóriához.</span><span class="sxs-lookup"><span data-stu-id="6cc64-105">This procedure shows you how to specify that a vendor is approved or preferred for a specific procurement category.</span></span> <span data-ttu-id="6cc64-106">Ezt a feladatot általában egy beszerzési szakember végzi el.</span><span class="sxs-lookup"><span data-stu-id="6cc64-106">This task would usually be carried out by a procurement professional.</span></span> <span data-ttu-id="6cc64-107">Az USMF bemutatócég adataiban használhatja ezt az eljárást.</span><span class="sxs-lookup"><span data-stu-id="6cc64-107">You can use this procedure in demo data company USMF.</span></span>

1. <span data-ttu-id="6cc64-108">Ugrás a Beszerzés és forrás > Beszállítók > Minden szállító pontra.</span><span class="sxs-lookup"><span data-stu-id="6cc64-108">Go to Procurement and sourcing > Vendors > All vendors.</span></span>
2. <span data-ttu-id="6cc64-109">Válassza ki a szállítót, amelyet be szeretne állítani a kategóriához jóváhagyott vagy preferált szállítóként.</span><span class="sxs-lookup"><span data-stu-id="6cc64-109">Select the vendor that you want to set as an approved or preferred vendor for a category.</span></span>
3. <span data-ttu-id="6cc64-110">A Művelet panelen kattintson az Általános elemre.</span><span class="sxs-lookup"><span data-stu-id="6cc64-110">On the Action Pane, click General.</span></span>
4. <span data-ttu-id="6cc64-111">Kattintson a Kategóriákra.</span><span class="sxs-lookup"><span data-stu-id="6cc64-111">Click Categories.</span></span>
5. <span data-ttu-id="6cc64-112">Kattintson a Kategória hozzáadására.</span><span class="sxs-lookup"><span data-stu-id="6cc64-112">Click Add category.</span></span>
6. <span data-ttu-id="6cc64-113">A Kategória mezőben válassza ki az OFFICE AND DESK ACCESSORIES (OFFICE AND DESK ACCESSORIES) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6cc64-113">In the Category field, select OFFICE AND DESK ACCESSORIES (OFFICE AND DESK ACCESSORIES).</span></span>
7. <span data-ttu-id="6cc64-114">A Szállítói kategória állapot mezőben válassza ki az „Elsődleges” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6cc64-114">In the Vendor category status field, select 'Preferred'.</span></span>
    * <span data-ttu-id="6cc64-115">Lehetőség van arra, hogy egy kategóriához több mint egy elsődleges szállítót határozzon meg.</span><span class="sxs-lookup"><span data-stu-id="6cc64-115">It’s possible to specify more than one preferred vendor for a category.</span></span>  
8. <span data-ttu-id="6cc64-116">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="6cc64-116">Click Save.</span></span>
9. <span data-ttu-id="6cc64-117">Ugorjon a Beszerzés és forrás > Beszerzési kategóriák pontra.</span><span class="sxs-lookup"><span data-stu-id="6cc64-117">Go to Procurement and sourcing > Procurement categories.</span></span>
10. <span data-ttu-id="6cc64-118">A fán válassza a „CORP PROCUREMENT CATEGORIES\OFFICE AND DESK ACCESSORIES” pontot.</span><span class="sxs-lookup"><span data-stu-id="6cc64-118">In the tree, select 'CORP PROCUREMENT CATEGORIES\OFFICE AND DESK ACCESSORIES'.</span></span>
11. <span data-ttu-id="6cc64-119">Bontsa ki a Szállító szakaszt.</span><span class="sxs-lookup"><span data-stu-id="6cc64-119">Expand the Vendors section.</span></span>
    * <span data-ttu-id="6cc64-120">Ellenőrizze, hogy a kiválasztott szállító jelenik-e meg az Office és asztali kellékek kategória elsődleges szállítójaként.</span><span class="sxs-lookup"><span data-stu-id="6cc64-120">Check if the vendor that you selected  appears as a preferred vendor for the Office and desk accessories category.</span></span> <span data-ttu-id="6cc64-121">Ha feladat útmutatójaként használata ezt az eljárást, előfordulhat, hogy rá kell kattintania a Feloldás gombra, hogy letudja görgetni a szállítók listáját.</span><span class="sxs-lookup"><span data-stu-id="6cc64-121">If you’re running this procedure as a task guide, you may have to click the Unlock button to be able to scroll down to the list of vendors.</span></span>  <span data-ttu-id="6cc64-122">Ezen az oldalon lehetséges elsődleges és jóváhagyott szállítók hozzáadása.</span><span class="sxs-lookup"><span data-stu-id="6cc64-122">It’s also possible to add preferred and approved vendors on this page.</span></span>  
12. <span data-ttu-id="6cc64-123">A fán, nyissa ki az „OFFICE AND DESK ACCESSORIES” pontot.</span><span class="sxs-lookup"><span data-stu-id="6cc64-123">In the tree, expand 'OFFICE AND DESK ACCESSORIES'.</span></span>
13. <span data-ttu-id="6cc64-124">A fában válassza a „Scissors” pontot.</span><span class="sxs-lookup"><span data-stu-id="6cc64-124">In the tree, select 'Scissors'.</span></span>
14. <span data-ttu-id="6cc64-125">Válassza a Nem lehetőséget a Szállítók öröklése szülőkategóriától: mezőben.</span><span class="sxs-lookup"><span data-stu-id="6cc64-125">Select No in the Inherit vendors from parent category: field.</span></span>
15. <span data-ttu-id="6cc64-126">Válassza az Igen lehetőséget a Szállítók öröklése szülőkategóriától: mezőben.</span><span class="sxs-lookup"><span data-stu-id="6cc64-126">Select Yes in the Inherit vendors from parent category: field.</span></span>


