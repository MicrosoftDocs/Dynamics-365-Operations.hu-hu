---
title: Rendelések várakoztatásának kezelése
description: Ez az eljárás bemutatja, hogyan lehet a vevői értékesítési rendeléseket várakoztatásra tenni, hogyan dolgozhat a várakoztatott rendelések kifizetésével, és hogyan tudja a rendelésvárakoztatásokat eltávolítani.
author: omulvad
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRHoldCodeTable, SalesTableListPage, SalesCreateOrder, SalesTable, MCRHoldCodeTrans, MCRHoldCheckOutOverride, MCRHoldCodeTable, MCRItemListCopying, MCRItemListTable, MCROMHoldList
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9caf6651813f0111b873db1769140d973f1a2e3b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429612"
---
# <a name="manage-order-holds"></a><span data-ttu-id="673e8-103">Rendelések várakoztatásának kezelése</span><span class="sxs-lookup"><span data-stu-id="673e8-103">Manage order holds</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="673e8-104">Ez az eljárás bemutatja, hogyan lehet a vevői értékesítési rendeléseket várakoztatásra tenni, hogyan dolgozhat a várakoztatott rendelések kifizetésével, és hogyan tudja a rendelésvárakoztatásokat eltávolítani.</span><span class="sxs-lookup"><span data-stu-id="673e8-104">This procedure demonstrates how to place customer sales orders on hold, how to work with order hold checkouts, and how to remove order holds.</span></span> <span data-ttu-id="673e8-105">Egy megrendelés különféle okokból kerülhet várakoztatásra.</span><span class="sxs-lookup"><span data-stu-id="673e8-105">An order might be placed on hold for a variety of reasons.</span></span> <span data-ttu-id="673e8-106">Például előfordulhat, hogy egy megrendelés mindaddig várakoztatva van, amíg a vevő címe, vagy a fizetési mód ellenőrzésre nem kerül, vagy amíg a vezető ellenőrzi a vevő hitelkeretét.</span><span class="sxs-lookup"><span data-stu-id="673e8-106">For example, you might hold an order until a customer address or payment method can be verified or until a manager can review the customer's credit limit.</span></span> <span data-ttu-id="673e8-107">Amíg a rendelés várakoztatáson van, a raktár nem tudja feldolgozni szállításra.</span><span class="sxs-lookup"><span data-stu-id="673e8-107">While the order on hold, it cannot be processed by the warehouse for shipping.</span></span> 

<span data-ttu-id="673e8-108">Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja.</span><span class="sxs-lookup"><span data-stu-id="673e8-108">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="set-up-order-holds"></a><span data-ttu-id="673e8-109">Rendelésvárakoztatások beállítása</span><span class="sxs-lookup"><span data-stu-id="673e8-109">Set up order holds</span></span>
1. <span data-ttu-id="673e8-110">Ugorjon az **Navigációs lap > Modulok > Értékesítés és marketing > Beállítás > Értékesítési rendelések > Rendelésvárakoztatási kódok** pontra.</span><span class="sxs-lookup"><span data-stu-id="673e8-110">Go to **Navigation pane > Modules > Sales and marketing > Setup > Sales orders > Order hold codes**.</span></span>
2. <span data-ttu-id="673e8-111">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="673e8-111">Click **New**.</span></span>
3. <span data-ttu-id="673e8-112">A **Várakoztatási kód** mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="673e8-112">In the **Hold code** field, type a value.</span></span> <span data-ttu-id="673e8-113">Írja be például azt, hogy Visszahívás.</span><span class="sxs-lookup"><span data-stu-id="673e8-113">For example, type 'Call back'.</span></span>  
4. <span data-ttu-id="673e8-114">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="673e8-114">In the **Description** field, type a value.</span></span>
    - <span data-ttu-id="673e8-115">Például, Rendelés visszatartva, vevői visszahívásra vár.</span><span class="sxs-lookup"><span data-stu-id="673e8-115">For example, Order held waiting for customer callback.</span></span>  
    - <span data-ttu-id="673e8-116">Opcionálisan bejelölheti a **Foglalások eltávolítása** jelölőnégyzetet, ha el szeretné távolítani a rendelésből a fizikai foglalásokat a várakoztatási kód hozzáadásakor.</span><span class="sxs-lookup"><span data-stu-id="673e8-116">Optionally, select the **Remove reservations** check box to remove any physical reservations from the order when this hold code is added.</span></span>  
5. <span data-ttu-id="673e8-117">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="673e8-117">Click **Save**.</span></span>

## <a name="place-order-on-hold"></a><span data-ttu-id="673e8-118">Rendelés várakoztatásra állítása</span><span class="sxs-lookup"><span data-stu-id="673e8-118">Place order on hold</span></span>
1. <span data-ttu-id="673e8-119">Ugorjon az **Navigációs lap > Modulok > Értékesítés és marketing > Értékesítési rendelések > Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="673e8-119">Go to **Navigation pane > Modules > Sales and marketing > Sales orders > All sales orders**.</span></span>
2. <span data-ttu-id="673e8-120">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="673e8-120">Click **New**.</span></span>
3. <span data-ttu-id="673e8-121">A **Vevőszámla** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="673e8-121">In the **Customer account** field, enter or select a value.</span></span>
4. <span data-ttu-id="673e8-122">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="673e8-122">Click **OK**.</span></span>
5. <span data-ttu-id="673e8-123">Az **Cikkszám** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="673e8-123">In the **Item number** field, enter or select a value.</span></span>
6. <span data-ttu-id="673e8-124">Adjon meg egy számot a **Mennyiség** mezőben.</span><span class="sxs-lookup"><span data-stu-id="673e8-124">In the **Quantity** field, enter a number.</span></span>
7. <span data-ttu-id="673e8-125">A **Művelet panelen** kattintson az **Értékesítési rendelés** elemre.</span><span class="sxs-lookup"><span data-stu-id="673e8-125">On the **Action Pane**, click **Sales order**.</span></span>
8. <span data-ttu-id="673e8-126">Kattintson a **Rendelésvárakoztatások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="673e8-126">Click **Order holds**.</span></span>
9. <span data-ttu-id="673e8-127">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="673e8-127">Click **New**.</span></span>
10. <span data-ttu-id="673e8-128">A **Várakoztatási kód** mezőjében válassza ki a korábbi részfeladatban létrehozott kódot.</span><span class="sxs-lookup"><span data-stu-id="673e8-128">In the **Hold code** field, select the code you have created in the previous subtask.</span></span>
11. <span data-ttu-id="673e8-129">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="673e8-129">Click **Save**.</span></span>
12. <span data-ttu-id="673e8-130">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="673e8-130">Close the page.</span></span>
13. <span data-ttu-id="673e8-131">Lépjen az **Értékesítés és marketing > Értékesítési rendelések > Minden értékesítési rendelés** menüpontba.</span><span class="sxs-lookup"><span data-stu-id="673e8-131">Go to **Sales and marketing > Sales orders > All sales orders**.</span></span>
14. <span data-ttu-id="673e8-132">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="673e8-132">In the list, mark the selected row.</span></span> <span data-ttu-id="673e8-133">Az aktuálisan várakoztatásra állított rendeléseknél be van jelölve a „Nem feldolgozandó” és a „Várakoztatott” mező.</span><span class="sxs-lookup"><span data-stu-id="673e8-133">Orders that are currently on hold have the "Do not process" and "Hold" fields marked.</span></span>
15. <span data-ttu-id="673e8-134">A műveleti ablaktáblán kattintson a **Választás** elemre, majd válassza ki a csomag elemet.</span><span class="sxs-lookup"><span data-stu-id="673e8-134">On the Action Pane, click **Pick and pack**.</span></span>

## <a name="manage-order-holds"></a><span data-ttu-id="673e8-135">Rendelések várakoztatásának kezelése</span><span class="sxs-lookup"><span data-stu-id="673e8-135">Manage order holds</span></span>
1. <span data-ttu-id="673e8-136">Ugorjon az **Értékesítés és marketing > Értékesítési rendelések > Nyitott rendelések > Rendelésvárakoztatások** elemre.</span><span class="sxs-lookup"><span data-stu-id="673e8-136">Go to **Sales and marketing > Sales orders > Open orders > Order holds**.</span></span> <span data-ttu-id="673e8-137">A **Rendelésvárakoztatások** oldal olyan munkaterületként működik, amely a jelenlegi és a feldolgozott várakoztatások áttekintését nyújtja, és ahol elvégezhető a várakoztatások és a társított értékesítési rendelések kezelése.</span><span class="sxs-lookup"><span data-stu-id="673e8-137">**Order holds** page functions as a workbench where you can get an overview of all the current and processed holds, and handle them and associated sales orders.</span></span>     
2. <span data-ttu-id="673e8-138">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="673e8-138">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="673e8-139">Kattintson a **Várakoztatás kivétele** lehetőségre a **Művelet** panelen.</span><span class="sxs-lookup"><span data-stu-id="673e8-139">On the **Action Pane**, click **Hold checkout**.</span></span>
4. <span data-ttu-id="673e8-140">Kattintson a **Kivétel** elemre.</span><span class="sxs-lookup"><span data-stu-id="673e8-140">Click **Check out**.</span></span>
5. <span data-ttu-id="673e8-141">A listában szüntesse meg a kiválasztott sor megjelölését.</span><span class="sxs-lookup"><span data-stu-id="673e8-141">In the list, unmark the selected row.</span></span> <span data-ttu-id="673e8-142">A **Felelős** mező most már megjeleníti a felhasználói azonosítót.</span><span class="sxs-lookup"><span data-stu-id="673e8-142">The **Checkout out to** field now shows your user ID.</span></span>   
6. <span data-ttu-id="673e8-143">Kattintson a **Kivétel törlése** elemre.</span><span class="sxs-lookup"><span data-stu-id="673e8-143">Click **Clear checkout**.</span></span>
7. <span data-ttu-id="673e8-144">Kattintson a **Várakoztatás megszüntetése** lehetőségre a **Művelet** panelen.</span><span class="sxs-lookup"><span data-stu-id="673e8-144">On the **Action Pane**, click **Clear hold**.</span></span>
    - <span data-ttu-id="673e8-145">Ha készen áll a várakoztatás eltávolítására és a rendelés feldolgozásának folytatására a teljesítés következő lépésével, törölnie kell a várakoztatást.</span><span class="sxs-lookup"><span data-stu-id="673e8-145">When you are ready to remove the hold and allow the order to proceed to the next fulfilment step, you must clear the hold.</span></span> <span data-ttu-id="673e8-146">Ha a rendelésen nem szükséges módosításokat végrehajtani, lefuttathatja a Várakoztatás megszüntetése műveletet.</span><span class="sxs-lookup"><span data-stu-id="673e8-146">If the order requires no changes, you can run the Clear holds action.</span></span> <span data-ttu-id="673e8-147">Ha azonban a várakoztatás törlésekor a rendelést frissíteni kell, a Törlés és módosítás műveletet használhatja.</span><span class="sxs-lookup"><span data-stu-id="673e8-147">However, you can use the Clear and modify action if, when clearing a hold, the order has to be updated.</span></span>      
    - <span data-ttu-id="673e8-148">A **Törlés és küldés** művelet csak a Hívásközpont funkció használata esetén alkalmazható.</span><span class="sxs-lookup"><span data-stu-id="673e8-148">The **Clear and submit** action is only applicable when you use Call center functionality.</span></span>  
8. <span data-ttu-id="673e8-149">Kattintson a **Várakoztatások megszüntetése** elemre.</span><span class="sxs-lookup"><span data-stu-id="673e8-149">Click **Clear holds**.</span></span> <span data-ttu-id="673e8-150">Ezzel törölte a várakoztatást a rendelésből, és eltávolította az aktív várakoztatások listájáról.</span><span class="sxs-lookup"><span data-stu-id="673e8-150">The hold has now been cleared from the order and removed from the list of Active holds.</span></span> <span data-ttu-id="673e8-151">Minden várakoztatás megtekintéséhez, vagy egy részhalmazuk megtekintéséhez egy bizonyos állapot szerint, módosítsa a Megjelenítés mező értékét.</span><span class="sxs-lookup"><span data-stu-id="673e8-151">To see all the holds or their subset according to a specific status, change the value in the Show field.</span></span>     

