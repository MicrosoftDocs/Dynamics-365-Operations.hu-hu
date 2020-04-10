---
title: Szállítók jóváhagyása konkrét beszerzési kategóriákra vonatkozóan
description: Ez a témakör azt mutatja be, hogyan lehet jóváhagyni a Dynamics 365 Supply Chain Management megoldásban szállítókat az egyes beszerzési kategóriákhoz.
author: mkirknel
manager: AnnBe
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, DirPartyEcoResCategory, EcoResCategorySingleLookup, ProcCategoryHierarchyManagement
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 135b3a6bea2c0a8940550299504139551c9c3559
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3147503"
---
# <a name="approve-vendors-for-specific-procurement-categories"></a><span data-ttu-id="61509-103">Szállítók jóváhagyása konkrét beszerzési kategóriákra vonatkozóan</span><span class="sxs-lookup"><span data-stu-id="61509-103">Approve vendors for specific procurement categories</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="61509-104">Ez a témakör azt mutatja be, hogyan lehet jóváhagyni a Dynamics 365 Supply Chain Management megoldásban szállítókat az egyes beszerzési kategóriákhoz.</span><span class="sxs-lookup"><span data-stu-id="61509-104">This topic explains how to approve vendors for specific procurement categories in Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="61509-105">Amikor egy beszerzési igénylést hoznak létre, lehet szükséges lesz egy engedélyezett vagy preferált szállító kiválasztása, attól függően, hogy a beszerzési irányelvek hogy vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="61509-105">When a purchase requisition is created, there may be a requirement to select an approved or preferred vendor, depending on how the purchasing policies are set up.</span></span> <span data-ttu-id="61509-106">Ez az eljárás bemutatja, hogyan adja meg, hogy a szállító jóváhagyott vagy preferált egy adott beszerzési kategóriához.</span><span class="sxs-lookup"><span data-stu-id="61509-106">This procedure shows you how to specify that a vendor is approved or preferred for a specific procurement category.</span></span> <span data-ttu-id="61509-107">Ezt a feladatot általában egy beszerzési szakember végzi el.</span><span class="sxs-lookup"><span data-stu-id="61509-107">This task would usually be carried out by a procurement professional.</span></span> <span data-ttu-id="61509-108">Az USMF bemutatócég adataiban használhatja ezt az eljárást.</span><span class="sxs-lookup"><span data-stu-id="61509-108">You can use this procedure in demo data company USMF.</span></span>

1. <span data-ttu-id="61509-109">A Navigációs ablaktáblán válassza a **Modulok > Beszerzés és forrás > Szállítók > Összes beszállító** elemet.</span><span class="sxs-lookup"><span data-stu-id="61509-109">In the navigation pane, go to **Modules > Procurement and sourcing > Vendors > All vendors**.</span></span>
2. <span data-ttu-id="61509-110">Válassza ki a szállítót, amelyet be szeretne állítani a kategóriához jóváhagyott vagy preferált szállítóként.</span><span class="sxs-lookup"><span data-stu-id="61509-110">Select the vendor that you want to set as an approved or preferred vendor for a category.</span></span>
3. <span data-ttu-id="61509-111">A Művelet ablaktáblán válassza ki az **Általános** elemet.</span><span class="sxs-lookup"><span data-stu-id="61509-111">On the Action Pane, select **General**.</span></span>
4. <span data-ttu-id="61509-112">Válassza a **Kategóriák** elemet.</span><span class="sxs-lookup"><span data-stu-id="61509-112">Select **Categories**.</span></span>
5. <span data-ttu-id="61509-113">Válassza a **Kategória hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="61509-113">Select **Add category**.</span></span>
6. <span data-ttu-id="61509-114">A **Kategória** mezőben válassza ki az **OFFICE AND DESK ACCESSORIES (OFFICE AND DESK ACCESSORIES)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="61509-114">In the **Category** field, select **OFFICE AND DESK ACCESSORIES (OFFICE AND DESK ACCESSORIES)**.</span></span>
7. <span data-ttu-id="61509-115">A **Szállítói kategória állapot** mezőben válassza ki az **Elsődleges** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="61509-115">In the **Vendor category status** field, select **Preferred**.</span></span> <span data-ttu-id="61509-116">Lehetőség van arra, hogy egy kategóriához több mint egy elsődleges szállítót határozzon meg.</span><span class="sxs-lookup"><span data-stu-id="61509-116">It's possible to specify more than one preferred vendor for a category.</span></span>  
8. <span data-ttu-id="61509-117">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="61509-117">Select **Save**.</span></span>
9. <span data-ttu-id="61509-118">A navigációs ablaktáblában menjen a **Modulok > Beszerzés és forrás > Beszerzési kategóriák** menübe.</span><span class="sxs-lookup"><span data-stu-id="61509-118">In the navigation pane, go to **Modules > Procurement and sourcing > Procurement categories**.</span></span>
10. <span data-ttu-id="61509-119">A fán válassza a **CORP PROCUREMENT CATEGORIES\OFFICE AND DESK ACCESSORIES** pontot.</span><span class="sxs-lookup"><span data-stu-id="61509-119">In the tree, select **CORP PROCUREMENT CATEGORIES\OFFICE AND DESK ACCESSORIES**.</span></span>
11. <span data-ttu-id="61509-120">Bontsa ki a **Szállító** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="61509-120">Expand the **Vendors** section.</span></span> <span data-ttu-id="61509-121">Ellenőrizze, hogy a kiválasztott szállító jelenik-e meg az Office és asztali kellékek kategória elsődleges szállítójaként.</span><span class="sxs-lookup"><span data-stu-id="61509-121">Check if the vendor that you selected appears as a preferred vendor for the Office and desk accessories category.</span></span> <span data-ttu-id="61509-122">Ha feladat útmutatójaként használata ezt az eljárást, előfordulhat, hogy ki kell választania a **Feloldás** gombot, hogy letudja görgetni a szállítók listáját.</span><span class="sxs-lookup"><span data-stu-id="61509-122">If you're running this procedure as a task guide, you may have to select the **Unlock** button to be able to scroll down to the list of vendors.</span></span>  <span data-ttu-id="61509-123">Ezen az oldalon lehetséges elsődleges és engedélyezett szállítók hozzáadása.</span><span class="sxs-lookup"><span data-stu-id="61509-123">It's also possible to add preferred and approved vendors on this page.</span></span>  
12. <span data-ttu-id="61509-124">A fában bontsa ki az **OFFICE AND DESK ACCESSORIES** elemet, és válassza az **ollót**.</span><span class="sxs-lookup"><span data-stu-id="61509-124">In the tree, expand **OFFICE AND DESK ACCESSORIES** and select **Scissors**.</span></span>
13. <span data-ttu-id="61509-125">Válassza a **Nem** lehetőséget a **Szállítók öröklése szülőkategóriától:** mezőben.</span><span class="sxs-lookup"><span data-stu-id="61509-125">Select **No** in the **Inherit vendors from parent category:** field.</span></span>
14. <span data-ttu-id="61509-126">Válassza az **Igen** lehetőséget a **Szállítók öröklése szülőkategóriától:** mezőben.</span><span class="sxs-lookup"><span data-stu-id="61509-126">Select **Yes** in the **Inherit vendors from parent category:** field.</span></span>

