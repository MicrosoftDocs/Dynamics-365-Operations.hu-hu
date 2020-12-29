---
title: Az áruk bevételezésének rögzítése a beszerzési rendelésen
description: Ez a témakör azt ismerteti, hogyan rögzíthet árubeérkezést közvetlenül egy beszerzési rendelésnél.
author: mkirknel
manager: tfehr
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bd8ca2cbd24f326c4eaf9cd39e32de0eca81149d
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4429946"
---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a><span data-ttu-id="87aa3-103">Az áruk bevételezésének rögzítése a beszerzési rendelésen</span><span class="sxs-lookup"><span data-stu-id="87aa3-103">Record the receipt of goods on the purchase order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="87aa3-104">Ez a témakör azt ismerteti, hogyan rögzíthet árubeérkezést közvetlenül egy beszerzési rendelésnél.</span><span class="sxs-lookup"><span data-stu-id="87aa3-104">This topic explains how to record receipt of goods directly on a purchase order.</span></span> <span data-ttu-id="87aa3-105">Ezen kívül lehetséges az is, hogy rögzítsen árubeérkezést a raktárban, amit majd később rögzíthet a beszerzési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="87aa3-105">It's also possible to register product receipt in the warehouse, and then later record it on the purchase order.</span></span> <span data-ttu-id="87aa3-106">A feladatot általában a beszerzési ügynök, vagy a fizetendő számla koordinátor végzi el.</span><span class="sxs-lookup"><span data-stu-id="87aa3-106">This task is typically done by a purchasing agent or an accounts payable coordinator.</span></span> <span data-ttu-id="87aa3-107">Az útmutatóban mutatott példa használható az USMF demo adatok cégben.</span><span class="sxs-lookup"><span data-stu-id="87aa3-107">The example shown in this guide can be used in the USMF demo data company.</span></span> <span data-ttu-id="87aa3-108">A példa tartalmazza az egyszerű beszerzési rendelés létrehozásához szükséges lépéseket, így feladat segédletként használhatja a folyamat során.</span><span class="sxs-lookup"><span data-stu-id="87aa3-108">The example includes steps to create a simple purchase order so that you can play the procedure as a task guide.</span></span> <span data-ttu-id="87aa3-109">Ha az eljárás alatt a saját adatait használja, az **Árubeérkeztetés** részfeladattal kell kezdenie.</span><span class="sxs-lookup"><span data-stu-id="87aa3-109">If you were using the procedure on your own data, you would start at the **Record receipt of goods** subtask.</span></span>


## <a name="prepare-a-new-purchase-order-for-receipt-of-goods"></a><span data-ttu-id="87aa3-110">Új beszerzési rendelés készítése áru bevételezéshez</span><span class="sxs-lookup"><span data-stu-id="87aa3-110">Prepare a new purchase order for receipt of goods</span></span>
1. <span data-ttu-id="87aa3-111">Ugorjon a **Navigációs ablaktábla > Modulok > Beszerzés és forrás > Beszerzési rendelések > Összes beszerzési rendelés** elemre.</span><span class="sxs-lookup"><span data-stu-id="87aa3-111">Go to **Navigation pane > Modules > Procurement and sourcing > Purchase orders > All purchase orders**.</span></span>
2. <span data-ttu-id="87aa3-112">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87aa3-112">Select **New**.</span></span>
3. <span data-ttu-id="87aa3-113">Adja meg az `US-101` értéket a **Szállítói számla** mezőben.</span><span class="sxs-lookup"><span data-stu-id="87aa3-113">In the **Vendor account** field, enter `US-101`.</span></span>
4. <span data-ttu-id="87aa3-114">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87aa3-114">Select **OK**.</span></span>
5. <span data-ttu-id="87aa3-115">Adja meg az `M0001` értéket a **Cikkszám** mezőben.</span><span class="sxs-lookup"><span data-stu-id="87aa3-115">In the **Item number** field, enter `M0001`.</span></span>
6. <span data-ttu-id="87aa3-116">Adja meg az `5` értéket a **Mennyiség** mezőben.</span><span class="sxs-lookup"><span data-stu-id="87aa3-116">In the **Quantity** field, enter `5`.</span></span>
7. <span data-ttu-id="87aa3-117">A Műveleti ablaktáblán válassza ki a **Beszerzés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87aa3-117">On the Action Pane, select **Purchase**.</span></span>
8. <span data-ttu-id="87aa3-118">Válassza ki a **Megerősítés** elemet.</span><span class="sxs-lookup"><span data-stu-id="87aa3-118">Select **Confirm**.</span></span>

## <a name="record-receipt-of-goods"></a><span data-ttu-id="87aa3-119">Áruk bevételezésének rögzítése</span><span class="sxs-lookup"><span data-stu-id="87aa3-119">Record receipt of goods</span></span>
1. <span data-ttu-id="87aa3-120">A Művelet ablaktáblán válassza ki a **Bevételezés** elemet.</span><span class="sxs-lookup"><span data-stu-id="87aa3-120">On the Action Pane, select **Receive**.</span></span>
2. <span data-ttu-id="87aa3-121">Válassza ki a **Termékbevételezés** elemet.</span><span class="sxs-lookup"><span data-stu-id="87aa3-121">Select **Product receipt**.</span></span> <span data-ttu-id="87aa3-122">A **Mennyiség** mező segítségével kiválaszthat különböző lehetőségeket ahhoz a mennyiséghez, amelyet szeretne beérkeztetni.</span><span class="sxs-lookup"><span data-stu-id="87aa3-122">The **Quantity** field allows you to select different options for the quantity that you want to receive.</span></span> <span data-ttu-id="87aa3-123">Ha például a mennyiség korábban már regisztrálva lett a raktárban, akkor kiválaszthatja a **Regisztrált mennyiség** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87aa3-123">For example, if a quantity has previously been registered in the warehouse, you can select **Registered quantity**.</span></span> <span data-ttu-id="87aa3-124">Ebben a példában használja a **Megrendelt mennyiség** elemet.</span><span class="sxs-lookup"><span data-stu-id="87aa3-124">For this example, use the value **Ordered quantity**.</span></span>
3. <span data-ttu-id="87aa3-125">Bontsa ki az **Áttekintés** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="87aa3-125">Expand the **Overview** section.</span></span>
4. <span data-ttu-id="87aa3-126">Adjon meg egy értéket a **Termékbevételezés** mezőben.</span><span class="sxs-lookup"><span data-stu-id="87aa3-126">In the **Product receipt** field, type any value.</span></span> <span data-ttu-id="87aa3-127">Ezzel a mezővel lehet megadni olyan hivatkozást, ami bizonylatként lesz használva a termék bevételezési naplójához.</span><span class="sxs-lookup"><span data-stu-id="87aa3-127">This field is used to enter a reference that will be used as voucher for the product receipt journal.</span></span>  
5. <span data-ttu-id="87aa3-128">Bontsa ki a **Sorok** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="87aa3-128">Expand the **Lines** section.</span></span>
6. <span data-ttu-id="87aa3-129">Állítsa a **Mennyiség** lehetőséget „4-re”.</span><span class="sxs-lookup"><span data-stu-id="87aa3-129">Set **Quantity** to '4'.</span></span> <span data-ttu-id="87aa3-130">Itt is manuálisan adhatja meg a mennyiséget, ami a rendelés minden sorához tartozó bevételezett mennyiség.</span><span class="sxs-lookup"><span data-stu-id="87aa3-130">Here you are able to manually specify the quantity that is being received for each line on the order.</span></span>  
7. <span data-ttu-id="87aa3-131">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87aa3-131">Select **OK**.</span></span> <span data-ttu-id="87aa3-132">Az áruk most már beérkezettként szerepelnek a beszerzési rendelésen és egy termékbevételezési napló lett létrehozva ennek a dokumentálására.</span><span class="sxs-lookup"><span data-stu-id="87aa3-132">The goods have now been recorded as received on the purchase order, and a product receipt journal has been created as document to reflect this.</span></span> <span data-ttu-id="87aa3-133">A Termék-bevételezési művelet segítségével áttekintheti a beszerzési rendeléshez létrehozott naplókat, és láthatja, hogy mi érkezett és mikor.</span><span class="sxs-lookup"><span data-stu-id="87aa3-133">You can use the Product receipt action to review the journals created with the purchase order, and see what was received, and when.</span></span>  

