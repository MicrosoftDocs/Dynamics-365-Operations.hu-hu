---
title: Visszáru önköltségi ára és visszáru adagazonosítója
description: Hasznos, ha a visszáruk költsége megegyezik a termékeknek az akkori költségével, amikor a termékeket az ügyfélnek eladta. Ehhez használhatja a **Visszáru adagazonosítóját**.
author: ShylaThompson
manager: AnnBe
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReturnTableListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 33cd3d50fe342ba12a17419f4e759c243a60b3e0
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "335140"
---
# <a name="return-cost-price-and-return-lot-id"></a><span data-ttu-id="c482f-104">Visszáru önköltségi ára és visszáru adagazonosítója</span><span class="sxs-lookup"><span data-stu-id="c482f-104">Return cost price and return lot ID</span></span>        

[!include [banner](../includes/banner.md)]



<span data-ttu-id="c482f-105">A készletbe visszavett termékek költsége a termék jelenlegi költségeinek segítségével számítható ki.</span><span class="sxs-lookup"><span data-stu-id="c482f-105">The cost of products that are returned to inventory is calculated by using the current cost of the products.</span></span> <span data-ttu-id="c482f-106">Hasznos lehet azonban, ha a visszáruk költsége megegyezik a termékeknek az akkori költségével, amikor a termékeket az ügyfélnek eladta.</span><span class="sxs-lookup"><span data-stu-id="c482f-106">However, you might want the cost of the returned products to equal the cost of the products at the time when you sold the products to the customer.</span></span> <span data-ttu-id="c482f-107">Ehhez a következőt használhatja: **Értékesítési rendelés** képernyő, **Sor részletei** gyorslap, **Visszáru adagazonosítója** mező.</span><span class="sxs-lookup"><span data-stu-id="c482f-107">You can do this by using the **Return lot ID** field on the **Line details** FastTab in the **Sales order** form.</span></span>

<span data-ttu-id="c482f-108">Vegyük például a következő forgatókönyvet:</span><span class="sxs-lookup"><span data-stu-id="c482f-108">For example, consider the following scenario.</span></span> <span data-ttu-id="c482f-109">Ön kiállít egy számlát a vevőnek.</span><span class="sxs-lookup"><span data-stu-id="c482f-109">You invoice a customer.</span></span> <span data-ttu-id="c482f-110">Ezt követően a vevő visszaküldi Önnek a leszállított termékeket.</span><span class="sxs-lookup"><span data-stu-id="c482f-110">Then, the customer returns the delivered products to you.</span></span> <span data-ttu-id="c482f-111">Ön visszateszi a termékeket a készletbe.</span><span class="sxs-lookup"><span data-stu-id="c482f-111">You return the products to stock.</span></span> <span data-ttu-id="c482f-112">Ebben az esetben, amikor jóváírja a vevőnek a visszaküldött termékeket, az ilyen termékek költséginek kiszámítása a termék jelenlegi költségeinek használatával történik.</span><span class="sxs-lookup"><span data-stu-id="c482f-112">In this case, when you credit the customer for the returned products, the cost of those products is calculated by using the current cost of the products.</span></span> <span data-ttu-id="c482f-113">Ha azonban használja a **Visszáru adagazonosítója** mezőt, a visszaküldött termékek költségének kiszámítása a vevőnek történő eredeti értékesítéshez kapcsolódó számlán feltüntetett költség alapján történik.</span><span class="sxs-lookup"><span data-stu-id="c482f-113">However, if you use the **Return lot ID** field, the cost of the returned products is calculated by using the cost on the invoice of the original sale to the customer.</span></span>

<span data-ttu-id="c482f-114">Ha nem akarja a vevő által visszaküldött termékek jelenlegi költségeit használni a költségszámításhoz, használja a következő módszerek egyikét.</span><span class="sxs-lookup"><span data-stu-id="c482f-114">To use a cost other than the current cost for returns from a customer, use one of the following methods.</span></span>

## <a name="method-1-manually-enter-the-return-cost-price"></a><span data-ttu-id="c482f-115">1. módszer: Manuálisan adja meg a visszáru önköltségi árát</span><span class="sxs-lookup"><span data-stu-id="c482f-115">Method 1: Manually enter the return cost price</span></span>

<span data-ttu-id="c482f-116">Alapértelmezés szerint, amikor cikkeket ad hozzá egy visszárurendeléshez, a cikkek visszakerülnek készletbe, az aktuális önköltségi áron.</span><span class="sxs-lookup"><span data-stu-id="c482f-116">By default, when you add items to a return order, the items are returned to inventory at the current cost price.</span></span> <span data-ttu-id="c482f-117">Ahhoz, hogy másik önköltségi árat adjon meg a visszáruhoz, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="c482f-117">To specify a different return cost price, follow these steps.</span></span>

1.  <span data-ttu-id="c482f-118">Kattintson a következőkre: **Értékesítés és marketing** \> **Közös** \> **Visszárurendelések** \> **MInden visszárurendelés**.</span><span class="sxs-lookup"><span data-stu-id="c482f-118">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span>

2.  <span data-ttu-id="c482f-119">A **Műveleti ablaktáblán** az **Új** csoportban kattintson a **Visszárurendelés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c482f-119">On the **Action Pane**, in the **New** group, click **Return order**.</span></span>

3.  <span data-ttu-id="c482f-120">A **Visszárurendelés létrehozása** képernyőn válasszon ki egy vevőkódot, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="c482f-120">In the **Create return order** form, select a customer account, and then click **OK**.</span></span>

4.  <span data-ttu-id="c482f-121">A **Visszárurendelések - RMA szám: %1, %2** képernyőn válasszon ki egy cikket, majd adja meg a negatív mennyiséget a **Mennyiség** mezőben.</span><span class="sxs-lookup"><span data-stu-id="c482f-121">In the **Return order - RMA number: %1, %2** form, select an item, and then enter a negative quantity in the **Quantity** field.</span></span>

5.  <span data-ttu-id="c482f-122">Kattintson a **Soradatok** gyorslapra.</span><span class="sxs-lookup"><span data-stu-id="c482f-122">Click the **Line details** FastTab.</span></span>

6.  <span data-ttu-id="c482f-123">Adjon meg egy értéket az **Általános** lap **Visszáru önköltségi ára** mezőjében.</span><span class="sxs-lookup"><span data-stu-id="c482f-123">On the **General** tab, enter a value in the **Return cost price** field.</span></span> <span data-ttu-id="c482f-124">A rendszer ezt az értéket használja, amikor az áruk visszakerülnek a készletbe.</span><span class="sxs-lookup"><span data-stu-id="c482f-124">This value is used when the goods are returned to inventory.</span></span> <span data-ttu-id="c482f-125">Ha nem ad meg értéket, akkor a rendszer az aktuális önköltségi árat használja, amikor az áruk visszakerülnek a készletbe.</span><span class="sxs-lookup"><span data-stu-id="c482f-125">If you do not enter a value, the current cost price is used when the goods are returned to inventory.</span></span>

## <a name="method-2-automatically-generate-the-cost-price-based-on-the-customer-invoice-line"></a><span data-ttu-id="c482f-126">2. módszer: az önköltségi ár automatikus létrehozása a vevőiszámla-sor alapján</span><span class="sxs-lookup"><span data-stu-id="c482f-126">Method 2: Automatically generate the cost price based on the customer invoice line</span></span>

<span data-ttu-id="c482f-127">Ez az elsődlegesen ajánlott módszer a visszárusorok létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="c482f-127">This is the preferred method to use to create return lines.</span></span> <span data-ttu-id="c482f-128">Ahhoz, hogy a terméknek az akkori költségét használja, amikor a termékeket az ügyfélnek eladta, hozzon létre egy visszárurendelést, és adjon meg egy értékesítési sort a visszáruhoz.</span><span class="sxs-lookup"><span data-stu-id="c482f-128">To use the cost of the products at the time when you sold the products to the customer, create a return order and specify a sales line to return.</span></span>

1.  <span data-ttu-id="c482f-129">Kattintson a következőkre: **Értékesítés és marketing** \> **Közös** \> **Visszárurendelések** \> **MInden visszárurendelés**.</span><span class="sxs-lookup"><span data-stu-id="c482f-129">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span>

2.  <span data-ttu-id="c482f-130">A **Műveleti ablaktáblán** az **Új** csoportban kattintson a **Visszárurendelés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c482f-130">On the **Action Pane**, in the **New** group, click **Return order**.</span></span>

3.  <span data-ttu-id="c482f-131">A **Visszárurendelés létrehozása** képernyőn válasszon ki egy vevőkódot, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="c482f-131">In the **Create return order** form, select a customer account, and then click **OK**.</span></span>

4.  <span data-ttu-id="c482f-132">A **Visszárurendelések - RMA-szám: %1, %2** képernyőn, a **Műveleti panelen** kattintson az **Értékesítési rendelés megkeresése** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c482f-132">In the **Return order - RMA number: %1, %2** form, on the **Action Pane**, click **Find sales order**.</span></span>

5.  <span data-ttu-id="c482f-133">Az **Értékesítési rendelés megkeresése** képernyőn válassza ki a számlasort a visszáruhoz, és kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="c482f-133">In the **Find sales order** form, select the invoice line to return, and then click **OK**.</span></span>
    
    <span data-ttu-id="c482f-134">A **Sor adatai** gyorslapon, az **Általános** lapon, a **Visszáruadag-azonosító** mezőben látható az eredeti értékesítési sorban szereplő érték.</span><span class="sxs-lookup"><span data-stu-id="c482f-134">On the **Line details** FastTab, on the **General** tab, the **Return lot ID** field displays the value from the original sales line.</span></span> <span data-ttu-id="c482f-135">Ezenkívül a **Visszáru önköltségi ára** mezőben látható az eredeti értékesítési sorból származó költségérték.</span><span class="sxs-lookup"><span data-stu-id="c482f-135">Additionally, the **Return cost price** field displays the cost value from the original sales line.</span></span>

## <a name="cost-calculation-example"></a><span data-ttu-id="c482f-136">Költségszámítási példa</span><span class="sxs-lookup"><span data-stu-id="c482f-136">Cost calculation example</span></span>

<span data-ttu-id="c482f-137">Amikor egy visszárurendelési sor **Visszáruadag-azonosító** mezőjét használja a visszáru önköltségi árának meghatározásához, a rendszer a visszárurendelés sorában szereplő költséget alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="c482f-137">When you use the **Return lot ID** field on a return order line to specify the return cost price, the cost on the return order line is used.</span></span> <span data-ttu-id="c482f-138">A készletzárási vagy újraszámítási funkció használata esetén a költség az eredeti értékesítési soron módosul.</span><span class="sxs-lookup"><span data-stu-id="c482f-138">If you run the inventory close or recalculation functionality, the cost is adjusted on the original sales line.</span></span> <span data-ttu-id="c482f-139">A visszárurendelés sorában szereplő költség automatikusan úgy módosul, hogy megegyezzen a darabonkénti költség.</span><span class="sxs-lookup"><span data-stu-id="c482f-139">The cost on the return order line is automatically adjusted to reflect the same cost per piece.</span></span>

1.  <span data-ttu-id="c482f-140">Hozzon létre, és adjon ki egy teméket, amelynek az elnevezése Teszt.</span><span class="sxs-lookup"><span data-stu-id="c482f-140">Create and release a product that is named Test.</span></span> <span data-ttu-id="c482f-141">A **Kiadott termék részletei** képernyőn adja meg a következő információkat.</span><span class="sxs-lookup"><span data-stu-id="c482f-141">In the **Released product details** form, specify the following information:</span></span>
    
    1.  <span data-ttu-id="c482f-142">A **Költségek kezelése** gyorslapon, a **Cikkcsoport** mezőben válassza ki a **Részek** csoportot.</span><span class="sxs-lookup"><span data-stu-id="c482f-142">On the **Manage costs** FastTab, in the **Item group** field, select the **Parts** group.</span></span>
    
    2.  <span data-ttu-id="c482f-143">Az **Általános** gyorslap **Cikkmodellcsoport** mezőjében válassza ki a **DEF** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c482f-143">On the **General** FastTab, in the **Item model group** field, select **DEF**.</span></span>
    
    3.  <span data-ttu-id="c482f-144">A **Beszerzés** gyorslap **Ár** mezőjében a cikk önköltségi árához írja be: 10.00.</span><span class="sxs-lookup"><span data-stu-id="c482f-144">On the **Purchase** FastTab, in the **Price** field, type 10.00 as the cost price of the item.</span></span>
    
    4.  <span data-ttu-id="c482f-145">A **Műveleti panelen** kattintson a **Dimenziócsoportok** elemre.</span><span class="sxs-lookup"><span data-stu-id="c482f-145">On the **Action Pane**, click **Dimension groups**.</span></span> <span data-ttu-id="c482f-146">A **Tárolásidimenzió-csoport** mezőben válassza a **Csak hely és raktár** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c482f-146">In the **Storage dimension group** field, select **Site and Warehouse only**.</span></span> <span data-ttu-id="c482f-147">A **Nyomonkövetésidimenzió-csoport** mezőben válassza a **Nincsenek aktív nyomon követési dimenziók** elemet.</span><span class="sxs-lookup"><span data-stu-id="c482f-147">In the **Tracking dimension group** field, select **No active tracking dimensions**.</span></span>

2.  <span data-ttu-id="c482f-148">Hozzon létre egy beszerzési rendelést a Tesztcikk 10 darabjára, 6,00/darab áron, majd adjon fel egy számlát a beszerzési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="c482f-148">Create a purchase order for 10 pieces of the Test item at 6.00 per piece, and then post an invoice for the purchase order.</span></span>
    
    <span data-ttu-id="c482f-149">Hozzon létre egy második beszerzési rendelést a Tesztcikk 10 darabjára, 8,00/darab áron, majd adjon fel egy számlát a beszerzési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="c482f-149">Create a second purchase order for 10 pieces of the Test item at 8.00 per piece, and then post an invoice for the purchase order.</span></span>

3.  <span data-ttu-id="c482f-150">Adjon fel egy számlát az értékesítési rendeléshez azzal a céllal, hogy eladjon öt darab Tesztcikket.</span><span class="sxs-lookup"><span data-stu-id="c482f-150">Post an invoice for a sales order to sell five pieces of the Test item.</span></span>
    
    <span data-ttu-id="c482f-151">Ebben az esetben az értékesítésirendelés-soron 35,00 összegű költség szerepel (5 darab \* 7,00/darab átlagos költséggel számolva).</span><span class="sxs-lookup"><span data-stu-id="c482f-151">In this case, the sales order line is costed at 35.00 (5 pieces \* 7.00 average cost per piece).</span></span>

4.  <span data-ttu-id="c482f-152">Hozzon létre visszárurendelést a vevő számára.</span><span class="sxs-lookup"><span data-stu-id="c482f-152">Create a return order for the customer.</span></span> <span data-ttu-id="c482f-153">Az **Értékesítési rendelés megkeresése** képernyőn válassza ki a számlasort, és kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="c482f-153">In the **Find sales order** form, select the invoice line, and then click **OK**.</span></span>

5.  <span data-ttu-id="c482f-154">A **Visszárurendelések - RMA szám: %1, %2** képernyőn győződjön meg róla, hogy létrejön a visszáru-rendelés a Tesztcikk visszaküldéséhez.</span><span class="sxs-lookup"><span data-stu-id="c482f-154">In the **Return order - RMA number: %1, %2** form, verify that a return order is generated to return the Test item.</span></span> <span data-ttu-id="c482f-155">A visszáru-rendelés mennyisége 5,00-re van beállítva.</span><span class="sxs-lookup"><span data-stu-id="c482f-155">The quantity of the return order is set to -5.00.</span></span>
    
    <span data-ttu-id="c482f-156">A **Visszáruadag-azonosító** mezőben megjelenik az adagazonosító.</span><span class="sxs-lookup"><span data-stu-id="c482f-156">The **Return lot ID** field displays a lot ID.</span></span> <span data-ttu-id="c482f-157">Ez az adagazonosító annak a cikknek az eredeti értékesítési rendeléséből jön, amelyet értékesítettek a vevőnek.</span><span class="sxs-lookup"><span data-stu-id="c482f-157">This lot ID is taken from the original sales order of the item that was sold to the customer.</span></span> <span data-ttu-id="c482f-158">A **Visszáru önköltségi ára** mezőben látható az eredeti értékesítési sorból származó önköltségi ár.</span><span class="sxs-lookup"><span data-stu-id="c482f-158">The **Return cost price** field displays the cost price from the original sales line.</span></span>

6.  <span data-ttu-id="c482f-159">Rögzítse a visszaadott cikkek bevételezését.</span><span class="sxs-lookup"><span data-stu-id="c482f-159">Register the receipt of the returned items.</span></span>

7.  <span data-ttu-id="c482f-160">Adjon fel egy szállítólevelet a visszaküldött cikkekhez.</span><span class="sxs-lookup"><span data-stu-id="c482f-160">Post a packing slip for the returned items.</span></span>

8.  <span data-ttu-id="c482f-161">Számla feladása egy visszárurendeléshez.</span><span class="sxs-lookup"><span data-stu-id="c482f-161">Post an invoice for the return order.</span></span> <span data-ttu-id="c482f-162">A **Minden értékesítési rendelés** listaoldalon jelöljön ki egy értékesítési rendelést, amelynél a rendelés típusa **Visszaküldött rendelés**.</span><span class="sxs-lookup"><span data-stu-id="c482f-162">On the **All sales orders** list page, select a sales order for which **Returned order** is the order type.</span></span>

9.  <span data-ttu-id="c482f-163">Nyissa meg a **Készlettranzakciók** képernyőjét.</span><span class="sxs-lookup"><span data-stu-id="c482f-163">Open the **Inventory transactions** form.</span></span> <span data-ttu-id="c482f-164">Győződjön meg róla, hogy a visszáru költsége 7,00/darabonkénti áron van elszámolva a **Visszáru önköltségi ára** mezőben lévő értéket használva, és a **Költségösszeg** mezőben összesen 35,00 szerepel.</span><span class="sxs-lookup"><span data-stu-id="c482f-164">Verify that the return is costed at 7.00 per piece by using the value in the **Return cost price** field, for a total of 35.00 in the **Cost amount** field.</span></span> <span data-ttu-id="c482f-165">A **Készlettranzakciók** képernyőt a **Visszárurendelések - RMA szám: %1, %2** képernyőn nyithatja meg.</span><span class="sxs-lookup"><span data-stu-id="c482f-165">You can open the **Inventory transactions** form from the **Return order - RMA number: %1, %2** form.</span></span> <span data-ttu-id="c482f-166">A **Sorok** rácsban kattintson a **Készlet** \> **Tranzakciók** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c482f-166">In the **Lines** grid, click **Inventory** \> **Transactions**.</span></span>

10. <span data-ttu-id="c482f-167">A készlet- és raktárkezelő modulban használja a **Zárás és módosítás** képernyőt a **3. Bezárás** eljárás lefuttatásához.</span><span class="sxs-lookup"><span data-stu-id="c482f-167">In Inventory and warehouse management, use the **Closing and adjustment** form to run the **3. Close** procedure.</span></span>
    
    <span data-ttu-id="c482f-168">Ez a művelet módosítja a költséget az eredeti értékesítési sorban, amelynek -35.00 volt a költségszámítása (5 darab \*7,00) és-30.00 (5 darab \*6,00).</span><span class="sxs-lookup"><span data-stu-id="c482f-168">This action adjusts the cost on the original sales line that was costed at -35.00 (5 pieces \* 7.00) to -30.00 (5 pieces \* 6.00).</span></span> <span data-ttu-id="c482f-169">Ennek oka az, hogy a készletmodell-csoport az Elsőként be, elsőként ki (FIFO) módszert használja, és darabonként 6,00 a FIFO-költség az első beszerzési rendelésből.</span><span class="sxs-lookup"><span data-stu-id="c482f-169">This is because the inventory model group uses First in, First out (FIFO), and 6.00 per piece is the FIFO cost from the first purchase order.</span></span> <span data-ttu-id="c482f-170">Ezenkívül a művelet módosítja a költséget a visszárusoron úgy, hogy az megfeleljen az eredeti értékesítési soron lévő darabonként költségnek.</span><span class="sxs-lookup"><span data-stu-id="c482f-170">Additionally, the action adjusts the cost on the return sales line to match the cost per piece on the original sales line.</span></span> <span data-ttu-id="c482f-171">Emiatt a visszárusor költsége 35,00-ről 30,00-ra módosul.</span><span class="sxs-lookup"><span data-stu-id="c482f-171">Therefore, the cost of the return line is adjusted from 35.00 to 30.00.</span></span>




