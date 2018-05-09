--- 
title: "Rendelések várakoztatásának kezelése"
description: "Ez az eljárás bemutatja, hogyan lehet a vevői értékesítési rendeléseket várakoztatásra tenni, hogyan dolgozhat a várakoztatott rendelések kifizetésével, és hogyan tudja a rendelésvárakoztatásokat eltávolítani."
author: omulvad
manager: AnnBe
ms.date: 01/09/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 957e2ca47fd493121c6497677a0d958618cc5561
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="manage-order-holds"></a><span data-ttu-id="fac62-103">Rendelések várakoztatásának kezelése</span><span class="sxs-lookup"><span data-stu-id="fac62-103">Manage order holds</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fac62-104">Ez az eljárás bemutatja, hogyan lehet a vevői értékesítési rendeléseket várakoztatásra tenni, hogyan dolgozhat a várakoztatott rendelések kifizetésével, és hogyan tudja a rendelésvárakoztatásokat eltávolítani.</span><span class="sxs-lookup"><span data-stu-id="fac62-104">This procedure demonstrates how to place customer sales orders on hold, how to work with order hold checkouts, and how to remove order holds.</span></span> <span data-ttu-id="fac62-105">Egy megrendelés különféle okokból kerülhet várakoztatásra.</span><span class="sxs-lookup"><span data-stu-id="fac62-105">An order might be placed on hold for a variety of reasons.</span></span> <span data-ttu-id="fac62-106">Például előfordulhat, hogy egy megrendelés mindaddig várakoztatva van, amíg a vevő címe, vagy a fizetési mód ellenőrzésre nem kerül, vagy amíg a vezető ellenőrzi a vevő hitelkeretét.</span><span class="sxs-lookup"><span data-stu-id="fac62-106">For example, you might hold an order until a customer address or payment method can be verified or until a manager can review the customer’s credit limit.</span></span> <span data-ttu-id="fac62-107">Amíg a rendelés várakoztatáson van, a raktár nem tudja feldolgozni szállításra.</span><span class="sxs-lookup"><span data-stu-id="fac62-107">While the order on hold, it cannot be processed by the warehouse for shipping.</span></span> 

<span data-ttu-id="fac62-108">Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja.</span><span class="sxs-lookup"><span data-stu-id="fac62-108">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="set-up-order-holds"></a><span data-ttu-id="fac62-109">Rendelésvárakoztatások beállítása</span><span class="sxs-lookup"><span data-stu-id="fac62-109">Set up order holds</span></span>
1. <span data-ttu-id="fac62-110">Ugorjon az Értékesítés és marketing > Beállítás > Értékesítési rendelések > Rendelésvárakoztatási kódok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="fac62-110">Go to Sales and marketing > Setup > Sales orders > Order hold codes.</span></span>
2. <span data-ttu-id="fac62-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="fac62-111">Click New.</span></span>
3. <span data-ttu-id="fac62-112">A Várakoztatási kód mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="fac62-112">In the Hold code field, type a value.</span></span>
    * <span data-ttu-id="fac62-113">Írja be például azt, hogy Visszahívás.</span><span class="sxs-lookup"><span data-stu-id="fac62-113">For example, type Call back.</span></span>  
4. <span data-ttu-id="fac62-114">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="fac62-114">In the Description field, type a value.</span></span>
    * <span data-ttu-id="fac62-115">Például, Rendelés visszatartva, vevői visszahívásra vár.</span><span class="sxs-lookup"><span data-stu-id="fac62-115">For example, Order held waiting for customer callback.</span></span>  
    * <span data-ttu-id="fac62-116">Opcionálisan bejelölheti a Foglalások eltávolítása jelölőnégyzetet, ha el szeretné távolítani a rendelésből a fizikai foglalásokat a várakoztatási kód hozzáadásakor.</span><span class="sxs-lookup"><span data-stu-id="fac62-116">Optionally, select the Remove reservations check box to remove any physical reservations from the order when this hold code is added.</span></span>  
5. <span data-ttu-id="fac62-117">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="fac62-117">Click Save.</span></span>

## <a name="place-order-on-hold"></a><span data-ttu-id="fac62-118">Rendelés várakoztatásra állítása</span><span class="sxs-lookup"><span data-stu-id="fac62-118">Place order on hold</span></span>
1. <span data-ttu-id="fac62-119">Lépjen az Értékesítés és marketing > Értékesítési rendelések > Minden értékesítési rendelés menüpontba.</span><span class="sxs-lookup"><span data-stu-id="fac62-119">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="fac62-120">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="fac62-120">Click New.</span></span>
3. <span data-ttu-id="fac62-121">A Vevőszámla mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="fac62-121">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="fac62-122">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="fac62-122">Click OK.</span></span>
5. <span data-ttu-id="fac62-123">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="fac62-123">In the Item number field, enter or select a value.</span></span>
6. <span data-ttu-id="fac62-124">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="fac62-124">In the Quantity field, enter a number.</span></span>
7. <span data-ttu-id="fac62-125">A Művelet panelen kattintson az Értékesítési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="fac62-125">On the Action Pane, click Sales order.</span></span>
8. <span data-ttu-id="fac62-126">Kattintson a Rendelésvárakoztatások lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="fac62-126">Click Order holds.</span></span>
9. <span data-ttu-id="fac62-127">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="fac62-127">Click New.</span></span>
10. <span data-ttu-id="fac62-128">A Várakoztatási kód mezőjében válassza ki a korábbi részfeladatban létrehozott kódot.</span><span class="sxs-lookup"><span data-stu-id="fac62-128">In the Hold code field, select the code you have created in the previous subtask.</span></span>
11. <span data-ttu-id="fac62-129">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="fac62-129">Click Save.</span></span>
12. <span data-ttu-id="fac62-130">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="fac62-130">Close the page.</span></span>
13. <span data-ttu-id="fac62-131">Lépjen az Értékesítés és marketing > Értékesítési rendelések > Minden értékesítési rendelés menüpontba.</span><span class="sxs-lookup"><span data-stu-id="fac62-131">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
14. <span data-ttu-id="fac62-132">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="fac62-132">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="fac62-133">Az aktuálisan várakoztatásra állított rendeléseknél be van jelölve a „Nem feldolgozandó” és a „Várakoztatott” mező.</span><span class="sxs-lookup"><span data-stu-id="fac62-133">Orders that are currently on hold have the "Do not process" and "Hold" fields marked.</span></span>    
15. <span data-ttu-id="fac62-134">A Művelet panelen kattintson a Kitárolás és csomagolás elemre.</span><span class="sxs-lookup"><span data-stu-id="fac62-134">On the Action Pane, click Pick and pack.</span></span>

## <a name="manage-order-holds"></a><span data-ttu-id="fac62-135">Rendelések várakoztatásának kezelése</span><span class="sxs-lookup"><span data-stu-id="fac62-135">Manage order holds</span></span>
1. <span data-ttu-id="fac62-136">Ugorjon az Értékesítés és marketing > Értékesítési rendelések > Nyitott rendelések > Rendelésvárakoztatások elemre.</span><span class="sxs-lookup"><span data-stu-id="fac62-136">Go to Sales and marketing > Sales orders > Open orders > Order holds.</span></span>
    * <span data-ttu-id="fac62-137">A Rendelésvárakoztatások oldal olyan munkaterületként működik, amely a jelenlegi és a feldolgozott várakoztatások áttekintését nyújtja, és ahol elvégezhető a várakoztatások és a társított értékesítési rendelések kezelése.</span><span class="sxs-lookup"><span data-stu-id="fac62-137">Order holds page functions as a workbench where you can get an overview of all the current and processed holds, and handle them and associated sales orders.</span></span>      
2. <span data-ttu-id="fac62-138">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="fac62-138">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="fac62-139">Kattintson a Várakoztatás kivétele lehetőségre a Művelet panelen.</span><span class="sxs-lookup"><span data-stu-id="fac62-139">On the Action Pane, click Hold checkout.</span></span>
4. <span data-ttu-id="fac62-140">Kattintson a Kivétel elemre.</span><span class="sxs-lookup"><span data-stu-id="fac62-140">Click Check out.</span></span>
5. <span data-ttu-id="fac62-141">A listában szüntesse meg a kiválasztott sor megjelölését.</span><span class="sxs-lookup"><span data-stu-id="fac62-141">In the list, unmark the selected row.</span></span>
    * <span data-ttu-id="fac62-142">A Felelős mező most már megjeleníti a felhasználói azonosítót.</span><span class="sxs-lookup"><span data-stu-id="fac62-142">The Checkout out to field now shows your user ID.</span></span>   
6. <span data-ttu-id="fac62-143">Kattintson a Kivétel törlése elemre.</span><span class="sxs-lookup"><span data-stu-id="fac62-143">Click Clear checkout.</span></span>
7. <span data-ttu-id="fac62-144">Kattintson a Várakoztatás megszüntetése lehetőségre a Művelet panelen.</span><span class="sxs-lookup"><span data-stu-id="fac62-144">On the Action Pane, click Clear hold.</span></span>
    * <span data-ttu-id="fac62-145">Ha készen áll a várakoztatás eltávolítására és a rendelés feldolgozásának folytatására a teljesítés következő lépésével, törölnie kell a várakoztatást.</span><span class="sxs-lookup"><span data-stu-id="fac62-145">When you are ready to remove the hold and allow the order to proceed to the next fulfilment step, you must clear the hold.</span></span> <span data-ttu-id="fac62-146">Ha a rendelésen nem szükséges módosításokat végrehajtani, lefuttathatja a Várakoztatás megszüntetése műveletet.</span><span class="sxs-lookup"><span data-stu-id="fac62-146">If the order requires no changes, you can run the Clear holds action.</span></span> <span data-ttu-id="fac62-147">Ha azonban a várakoztatás törlésekor a rendelést frissíteni kell, a Törlés és módosítás műveletet használhatja.</span><span class="sxs-lookup"><span data-stu-id="fac62-147">However, you can use the Clear and modify action if, when clearing a hold, the order has to be updated.</span></span>      
    * <span data-ttu-id="fac62-148">A Törlés és küldés művelet csak a Hívásközpont funkció használata esetén alkalmazható.</span><span class="sxs-lookup"><span data-stu-id="fac62-148">The Clear and submit action is only applicable when you use Call center functionality.</span></span>  
8. <span data-ttu-id="fac62-149">Kattintson a Várakoztatások megszüntetése elemre.</span><span class="sxs-lookup"><span data-stu-id="fac62-149">Click Clear holds.</span></span>
    * <span data-ttu-id="fac62-150">Ezzel törölte a várakoztatást a rendelésből, és eltávolította az aktív várakoztatások listájáról.</span><span class="sxs-lookup"><span data-stu-id="fac62-150">The hold has now been cleared from the order and removed from the list of Active holds.</span></span> <span data-ttu-id="fac62-151">Minden várakoztatás megtekintéséhez, vagy egy részhalmazuk megtekintéséhez egy bizonyos állapot szerint, módosítsa a Megjelenítés mező értékét.</span><span class="sxs-lookup"><span data-stu-id="fac62-151">To see all the holds or their subset according to a specific status, change the value in the Show field.</span></span>     


