---
title: Beszerzési kategóriák hierarchiájának beállítása
description: Ez az eljárás bemutatja az új csomópontok létrehozását a beszerzési kategóriák hierarchiájában, és azt, hogyan kell konfigurálni a beszerzési folyamatban használt beszerzési kategóriát.
author: mkirknel
manager: AnnBe
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d7010a1c612b9b3884c675f578657d951da06c38
ms.sourcegitcommit: 25fe679b73663fda6b5b3c32646026d0993a9f00
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/12/2019
ms.locfileid: "1995282"
---
# <a name="set-up-a-procurement-category-hierarchy"></a><span data-ttu-id="18f64-103">Beszerzési kategóriák hierarchiájának beállítása</span><span class="sxs-lookup"><span data-stu-id="18f64-103">Set up a procurement category hierarchy</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="18f64-104">Ez az eljárás bemutatja az új csomópontok létrehozását a beszerzési kategóriák hierarchiájában, és azt, hogyan kell konfigurálni a beszerzési folyamatban használt beszerzési kategóriát.</span><span class="sxs-lookup"><span data-stu-id="18f64-104">This procedure shows you how to create new nodes in a procurement category hierarchy and how to configure a procurement category to be used in a procurement process.</span></span> <span data-ttu-id="18f64-105">Ezeket a feladatokat jellemzően egy beszerzési vezető végzi el.</span><span class="sxs-lookup"><span data-stu-id="18f64-105">These tasks would typically be carried out by a Purchasing manager.</span></span> <span data-ttu-id="18f64-106">Az eljárás megkezdése előtt kell lennie egy Beszerzés típusú kategóriahierarchiának.</span><span class="sxs-lookup"><span data-stu-id="18f64-106">Before you can start this procedure, there must be a category hierarchy of type Procurement.</span></span> <span data-ttu-id="18f64-107">Ha bemutató adatokat használ, ezt az eljárást az USMF vállalatban futtathatja.</span><span class="sxs-lookup"><span data-stu-id="18f64-107">If you're using a demo data company, you can run this procedure in the USMF company.</span></span>


## <a name="add-a-new-procurement-category"></a><span data-ttu-id="18f64-108">Új beszerzési kategória hozzáadása</span><span class="sxs-lookup"><span data-stu-id="18f64-108">Add a new procurement category</span></span>
1. <span data-ttu-id="18f64-109">Menjen a **Navigációs ablaktábla > Modulok > Beszerzés és forrás > Bizomány > Beszerzési kategóriák** menübe.</span><span class="sxs-lookup"><span data-stu-id="18f64-109">Go to **Navigation pane > Modules > Procurement and sourcing > Consignment > Procurement categories**.</span></span>
2. <span data-ttu-id="18f64-110">A Műveleti ablaktáblában kattintson a **Kategóriahierarchia szerkesztése** elemre.</span><span class="sxs-lookup"><span data-stu-id="18f64-110">On the action pane, select **Edit category hierarchy**.</span></span> <span data-ttu-id="18f64-111">Az aktuális beszerzési kategóriák hierarchiája az oldal bal oldalán jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="18f64-111">The current procurement category hierarchy is displayed in the left side of the page.</span></span> <span data-ttu-id="18f64-112">Ezzel módosítja a hierarchiát.</span><span class="sxs-lookup"><span data-stu-id="18f64-112">You  are about to modify the hierarchy.</span></span>  
3. <span data-ttu-id="18f64-113">A Műveleti ablaktáblában kattintson a **Új kategória-csomópont** elemre.</span><span class="sxs-lookup"><span data-stu-id="18f64-113">On the action pane, select **New category node**.</span></span> <span data-ttu-id="18f64-114">A rendszer alapértelmezés szerint kiválasztja a felső csomópontot.</span><span class="sxs-lookup"><span data-stu-id="18f64-114">The system selects the top node by default.</span></span> <span data-ttu-id="18f64-115">Ha ezzel az eljárással a feladatot útmutatóként futtatja, kattintson a zárolás feloldása gombra, és válasszon másik szülő-csomópontot, amelybe az új csomópontot szeretné beilleszteni.</span><span class="sxs-lookup"><span data-stu-id="18f64-115">If you are running this procedure as a task guide, you can click the Unlock button and select another parent node to insert your new node into.</span></span> <span data-ttu-id="18f64-116">Ezt követően zárolja újra a feladatútmutatót, és kattintson az Új kategória-csomópontra.</span><span class="sxs-lookup"><span data-stu-id="18f64-116">Once that is done, lock the task guide again and then click New category node.</span></span>  
4. <span data-ttu-id="18f64-117">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="18f64-117">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="18f64-118">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="18f64-118">In the **Description** field, type a value.</span></span>
6. <span data-ttu-id="18f64-119">Írjon be egy értéket a **Barátságos név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="18f64-119">In the **Friendly name** field, type a value.</span></span> <span data-ttu-id="18f64-120">A baráti név nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="18f64-120">The friendly name is optional.</span></span> <span data-ttu-id="18f64-121">A kategória keresésekben a kategórianévvel együtt fog megjelenni.</span><span class="sxs-lookup"><span data-stu-id="18f64-121">It will be displayed in category lookups together with the category name.</span></span>  
7. <span data-ttu-id="18f64-122">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="18f64-122">Select **Save**.</span></span>

## <a name="add-products-to-your-new-procurement-category"></a><span data-ttu-id="18f64-123">Termékek hozzáadása az új beszerzési kategóriához</span><span class="sxs-lookup"><span data-stu-id="18f64-123">Add products to your new procurement category</span></span>
1. <span data-ttu-id="18f64-124">Ugorjon a **Beszerzés és forrás > Bizomány >Beszerzési kategóriák** pontra.</span><span class="sxs-lookup"><span data-stu-id="18f64-124">Go to **Procurement and sourcing > Consignment > Procurement categories**.</span></span> <span data-ttu-id="18f64-125">Jelölje ki az éppen hozzáadott csomópontot.</span><span class="sxs-lookup"><span data-stu-id="18f64-125">Select the node you just added.</span></span> <span data-ttu-id="18f64-126">Ha ezt a folyamatot feladat-útmutatóként használja, szükség lehet a feladat-útmutató feloldására a csomópont kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="18f64-126">If you’re running this procedure as a task guide you might need to unlock the task guide to select the node.</span></span>  
2. <span data-ttu-id="18f64-127">Váltsa át a **Termékek** szakasz kibontását.</span><span class="sxs-lookup"><span data-stu-id="18f64-127">Toggle the expansion of the **Products** section.</span></span>
3. <span data-ttu-id="18f64-128">Kattintson a **Hozzáadás** gombra a termékek hozzárendeléséhez a beszerzési kategóriához.</span><span class="sxs-lookup"><span data-stu-id="18f64-128">Select **Add** to associate products with the procurement category.</span></span>
4. <span data-ttu-id="18f64-129">Válassza ki azokat a termékeket, amelyet hozzá szeretné adni a beszerzési kategóriához.</span><span class="sxs-lookup"><span data-stu-id="18f64-129">Select the products you want to add to the procurement category.</span></span>
5. <span data-ttu-id="18f64-130">Kattintson a nyílra a termékek **Kiválasztott** táblához való hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="18f64-130">Select the arrow to add the products to the **Selected** table.</span></span>
6. <span data-ttu-id="18f64-131">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="18f64-131">Select **OK**.</span></span>
