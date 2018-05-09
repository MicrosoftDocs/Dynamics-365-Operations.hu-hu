--- 
title: "Az áruk bevételezésének rögzítése a beszerzési rendelésen"
description: "Ez az eljárás bemutatja Önnek, hogyan rögzíthet árubeérkezést közvetlenül egy beszerzési rendelésre."
author: FrankDahl
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
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 3a9c87b8790ed6cfe4139180f1f1785db04e7431
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a><span data-ttu-id="ee213-103">Az áruk bevételezésének rögzítése a beszerzési rendelésen</span><span class="sxs-lookup"><span data-stu-id="ee213-103">Record the receipt of goods on the purchase order</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ee213-104">Ez az eljárás bemutatja Önnek, hogyan rögzíthet árubeérkezést közvetlenül egy beszerzési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="ee213-104">This procedure shows you how to record receipt of goods directly on a purchase order.</span></span> <span data-ttu-id="ee213-105">Ezen kívül lehetséges az is, hogy rögzítsen árubeérkezést a raktárban, amit majd később rögzíthet a beszerzési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="ee213-105">It’s also possible to register product receipt in the warehouse, and then later record it on the purchase order.</span></span> <span data-ttu-id="ee213-106">A feladatot általában a beszerzési ügynök, vagy a fizetendő számla koordinátor végzi el.</span><span class="sxs-lookup"><span data-stu-id="ee213-106">This task is typically done by a purchasing agent or an accounts payable coordinator.</span></span> <span data-ttu-id="ee213-107">Az útmutatóban mutatott példa használható az USMF demo adatok cégben.</span><span class="sxs-lookup"><span data-stu-id="ee213-107">The example shown in this guide can be used in the USMF demo data company.</span></span> <span data-ttu-id="ee213-108">A példa tartalmazza az egyszerű beszerzési rendelés létrehozásához szükséges lépéseket, így feladat segédletként használhatja a folyamat során.</span><span class="sxs-lookup"><span data-stu-id="ee213-108">The example includes steps to create a simple purchase order so that you can play the procedure as a task guide.</span></span> <span data-ttu-id="ee213-109">Ha az eljárás alatt a saját adatait használta, az Árubeérkeztetés részfeladattal kellett volna kezdenie.</span><span class="sxs-lookup"><span data-stu-id="ee213-109">If you were using the procedure on your own data, you would start at the Record receipt of goods subtask.</span></span>


## <a name="prepare-a-new-purchase-order-for-receipt-of-goods"></a><span data-ttu-id="ee213-110">Új beszerzési rendelés készítése áru bevételezéshez</span><span class="sxs-lookup"><span data-stu-id="ee213-110">Prepare a new purchase order for receipt of goods</span></span>
1. <span data-ttu-id="ee213-111">Ugorjon a Beszerzés és forrás > Beszerzési rendelés > Összes beszerzési rendelés pontra.</span><span class="sxs-lookup"><span data-stu-id="ee213-111">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="ee213-112">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ee213-112">Click New.</span></span>
3. <span data-ttu-id="ee213-113">Írja be az „IS-101” értéket a Szállítói számla mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ee213-113">In the Vendor account field, enter US-101.</span></span>
4. <span data-ttu-id="ee213-114">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="ee213-114">Click OK.</span></span>
5. <span data-ttu-id="ee213-115">Adja meg a „M0001” értéket a Cikkszám mezőben.</span><span class="sxs-lookup"><span data-stu-id="ee213-115">In the Item number field, enter M0001.</span></span>
6. <span data-ttu-id="ee213-116">Adja meg az „5” értéket a Mennyiség mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ee213-116">In the Quantity field, enter 5.</span></span>
7. <span data-ttu-id="ee213-117">A Művelet panelen kattintson a Beszerzés elemre.</span><span class="sxs-lookup"><span data-stu-id="ee213-117">On the Action Pane, click Purchase.</span></span>
8. <span data-ttu-id="ee213-118">Kattintson a Megerősítés gombra.</span><span class="sxs-lookup"><span data-stu-id="ee213-118">Click Confirm.</span></span>

## <a name="record-receipt-of-goods"></a><span data-ttu-id="ee213-119">Áruk bevételezésének rögzítése</span><span class="sxs-lookup"><span data-stu-id="ee213-119">Record receipt of goods</span></span>
1. <span data-ttu-id="ee213-120">A Művelet panelen kattintson a Bevételezés elemre.</span><span class="sxs-lookup"><span data-stu-id="ee213-120">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="ee213-121">Kattintson a Termékbevételezés elemre.</span><span class="sxs-lookup"><span data-stu-id="ee213-121">Click Product receipt.</span></span>
    * <span data-ttu-id="ee213-122">A Mennyiség mező segítségével kiválaszthat különböző lehetőségeket ahhoz a mennyiséghez, amelyet szeretne beérkeztetni.</span><span class="sxs-lookup"><span data-stu-id="ee213-122">The Quantity field allows you to select different options for the quantity that you want to receive.</span></span> <span data-ttu-id="ee213-123">Például, ha a mennyiség korábban már regisztrálva lett a raktárban, akkor kiválaszthatja, hogy ez Regisztrált mennyiség.</span><span class="sxs-lookup"><span data-stu-id="ee213-123">For example, if a quantity has previously been registered in the warehouse, you can select Registered quantity.</span></span>  <span data-ttu-id="ee213-124">Ebben a példában használja a Rendelt mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="ee213-124">For this example, use the value Ordered quantity.</span></span>   
3. <span data-ttu-id="ee213-125">Írjon be egy értéket a Termék bevételezés mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ee213-125">In the Product receipt field, type any value.</span></span>
    * <span data-ttu-id="ee213-126">Ezzel a mezővel lehet megadni olyan hivatkozást, ami bizonylatként lesz használva a termék bevételezési naplójához.</span><span class="sxs-lookup"><span data-stu-id="ee213-126">This field is used to enter a reference that will be used as voucher for the product receipt journal.</span></span>  
4. <span data-ttu-id="ee213-127">Bontsa ki a Sorok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="ee213-127">Expand the Lines section.</span></span>
5. <span data-ttu-id="ee213-128">Állítsa a mennyiséget 4 értékre.</span><span class="sxs-lookup"><span data-stu-id="ee213-128">Set Quantity to '4'.</span></span>
    * <span data-ttu-id="ee213-129">Itt is manuálisan adhatja meg a mennyiséget, ami a rendelés minden sorához tartozó bevételezett mennyiség.</span><span class="sxs-lookup"><span data-stu-id="ee213-129">Here you are able to manually specify the quantity that is being received for each line on the order.</span></span>  
6. <span data-ttu-id="ee213-130">Csukja össze Sorok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="ee213-130">Collapse the Lines section.</span></span>
7. <span data-ttu-id="ee213-131">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="ee213-131">Click OK.</span></span>
    * <span data-ttu-id="ee213-132">Az áruk most már beérkezettként szerepelnek a beszerzési rendelésen és egy termékbevételezési napló lett létrehozva ennek a dokumentálására.</span><span class="sxs-lookup"><span data-stu-id="ee213-132">The goods have now been recorded as received on the purchase order, and a product receipt journal has been created as document to reflect this.</span></span> <span data-ttu-id="ee213-133">A Termék-bevételezési művelet segítségével áttekintheti a beszerzési rendeléshez létrehozott naplókat, és láthatja, hogy mi érkezett és mikor.</span><span class="sxs-lookup"><span data-stu-id="ee213-133">You can use the Product receipt action to review the journals created with the purchase order, and see what was received, and when.</span></span>  


