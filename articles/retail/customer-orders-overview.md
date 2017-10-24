---
title: "Vevői rendelések – áttekintés"
description: "Ez a témakör a vevői rendelések a Retail Modern POS (MPOS) modulban történő kezelését ismerteti. A vevői rendelések speciális rendelések néven is ismertek. A témakör a kapcsolódó paramétereket és tranzakciófolyamatokat is tárgyalja."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 260594
ms.assetid: 6fc835ef-d62e-4f23-9d49-50299be642ca
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: f68f9dce544256a2b1a9927f019a676a6845f46d
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="customer-orders-overview"></a><span data-ttu-id="aace4-105">Vevői rendelések – áttekintés</span><span class="sxs-lookup"><span data-stu-id="aace4-105">Customer orders overview</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="aace4-106">Ez a témakör a vevői rendelések a Retail Modern POS (MPOS) modulban történő kezelését ismerteti.</span><span class="sxs-lookup"><span data-stu-id="aace4-106">This topic provides information about customer orders in Retail Modern POS (MPOS).</span></span> <span data-ttu-id="aace4-107">A vevői rendelések speciális rendelések néven is ismertek.</span><span class="sxs-lookup"><span data-stu-id="aace4-107">Customer orders are also known as special orders.</span></span> <span data-ttu-id="aace4-108">A témakör a kapcsolódó paramétereket és tranzakciófolyamatokat is tárgyalja.</span><span class="sxs-lookup"><span data-stu-id="aace4-108">The topic includes a discussion of related parameters and transaction flows.</span></span>

<span data-ttu-id="aace4-109">A sokcsatornás kiskereskedelmi világ számos kiskereskedő biztosít lehetőséget vevői rendelésekre vagy speciális rendelésekre, hogy így elégítsen ki termékkel és teljesítéssel kapcsolatos különböző igényeket.</span><span class="sxs-lookup"><span data-stu-id="aace4-109">In an omni-channel retail world, many retailers provide the option of customer orders, or special orders, to meet various product and fulfillment requirements.</span></span> <span data-ttu-id="aace4-110">Íme néhány tipikus forgatókönyv:</span><span class="sxs-lookup"><span data-stu-id="aace4-110">Here are some typical scenarios:</span></span>

-   <span data-ttu-id="aace4-111">Egy vevő azt szeretné, ha a termékeket egy adott napon egy adott címre szállítanák ki.</span><span class="sxs-lookup"><span data-stu-id="aace4-111">A customer wants products to be delivered to a specific address on a specific date.</span></span>
-   <span data-ttu-id="aace4-112">Egy vevő egy olyan üzetben vagy helyen szeretné átvenni a termékeket, amely eltér attól az üzlettől vagy helytől, ahol az ügyfél megvásárolta az adott termékeket.</span><span class="sxs-lookup"><span data-stu-id="aace4-112">A customer wants to pick up products from a store or location that differs from the store or location where the customer purchased those products.</span></span>
-   <span data-ttu-id="aace4-113">Egy vevő szeretné, ha valaki más venné át a vevő által vásárolt termékeket.</span><span class="sxs-lookup"><span data-stu-id="aace4-113">A customer wants someone else to pick up products that the customer purchased.</span></span>

<span data-ttu-id="aace4-114">A kiskereskedők a készlethiány által okozott elmaradt értékesítések minimálisra csökkentése érdekében is használják a vevői rendeléseket, mivel így az áru más időben vagy helyen is kiszállítható vagy átvehető.</span><span class="sxs-lookup"><span data-stu-id="aace4-114">Retailers also use customer orders to minimize lost sales that stock outages might otherwise cause, because the merchandise can be delivered or picked up at a different time or place.</span></span>

## <a name="set-up-customer-orders"></a><span data-ttu-id="aace4-115">Vevői rendelések beállítása</span><span class="sxs-lookup"><span data-stu-id="aace4-115">Set up customer orders</span></span>
<span data-ttu-id="aace4-116">Íme néhány, a **Kiskereskedelmi paraméterek** oldalon beállítható paraméter, amely megszabja, hogyan teljesülnek a vevői rendelések:</span><span class="sxs-lookup"><span data-stu-id="aace4-116">Here are some of the parameters that can be set on the **Retail parameters** page to define how customer orders are fulfilled:</span></span>

-   <span data-ttu-id="aace4-117">**Letét alapértelmezett százalékos értéke** – annak az összegnek a megadása, amelyet a vevőnek ki kell fizetnie letétként, mielőtt a megrendelést meg lehet erősíteni.</span><span class="sxs-lookup"><span data-stu-id="aace4-117">**Default deposit percentage** – Specify the amount that the customer must pay as a deposit before an order can be confirmed.</span></span> <span data-ttu-id="aace4-118">Az alapértelmezett letét kiszámítása a rendelés százalékának függvényeként történik.</span><span class="sxs-lookup"><span data-stu-id="aace4-118">The default deposit amount is calculated as a percentage of the order value.</span></span> <span data-ttu-id="aace4-119">Jogosultságoktól függően előfordulhat, hogy egy bolti dolgozó felülbírálhatja az összeget a **Letét felülbírálása** funkcióval.</span><span class="sxs-lookup"><span data-stu-id="aace4-119">Depending on privileges, a store associate might be able to override the amount by using **Deposit override**.</span></span>
-   <span data-ttu-id="aace4-120">**Érvénytelenítési díj százalékos értéke** – ha vevői rendelés visszavonásakor díjfizetés szükséges, úgy adja meg ezen díj összegét.</span><span class="sxs-lookup"><span data-stu-id="aace4-120">**Cancellation charge percentage** – If a charge will be applied when a customer order is canceled, specify the amount of that charge.</span></span>
-   <span data-ttu-id="aace4-121">**Érvénytelenítési díj kódja** – ha vevői rendelés visszavonásakor díjfizetés szükséges, ezt a díjat egy díjkód tükrözi az értékesítési rendelésben.</span><span class="sxs-lookup"><span data-stu-id="aace4-121">**Cancellation charge code** – If a charge will be applied when a customer order is canceled, that charge will be reflected under a charge code on the sales order.</span></span> <span data-ttu-id="aace4-122">E paraméter segítségével határozza meg a lemondási díj kódját.</span><span class="sxs-lookup"><span data-stu-id="aace4-122">Use this parameter to define the cancellation charge code.</span></span>
-   <span data-ttu-id="aace4-123">**Szállítási költség kódjának** – a kiskereskedők külön díjat számolhatnak fel az áru szállításáért a vevőnek.</span><span class="sxs-lookup"><span data-stu-id="aace4-123">**Shipping charge code** – Retailers can charge an extra fee for shipping merchandise to a customer.</span></span> <span data-ttu-id="aace4-124">E szállítási költség összege költségkód alatt megjelenik az értékesítési rendelésen.</span><span class="sxs-lookup"><span data-stu-id="aace4-124">The amount of that shipping charge will be reflected under a charge code on the sales order.</span></span> <span data-ttu-id="aace4-125">Használja ezt a paramétert a szállítási költségkód hozzárendeléséhez a szállítási költségekhez a vevői rendelésen.</span><span class="sxs-lookup"><span data-stu-id="aace4-125">Use this parameter to map the shipping charge code to shipping charges on the customer order.</span></span>
-   <span data-ttu-id="aace4-126">**Szállítási költségek visszatérítése** – adja meg, hogy a vevői rendeléshez kapcsolódó szállítási költségek visszatéríthetők-e.</span><span class="sxs-lookup"><span data-stu-id="aace4-126">**Refund shipping charges** – Specify whether shipping charges that are associated with a customer order are refundable.</span></span>
-   <span data-ttu-id="aace4-127">**Maximális összeg jóváhagyás nélkül** – ha a szállítási költségek visszatéríthetők, adja meg a visszárurendeléseken keresztül biztosítható maximális szállításiköltség-visszatérítés összegét.</span><span class="sxs-lookup"><span data-stu-id="aace4-127">**Maximum amount without approval** – If shipping charges are refundable, specify the maximum amount of shipping charge refunds across return orders.</span></span> <span data-ttu-id="aace4-128">Ha ezt az összeget túllépik, a vezető részéről felülbírálás szükséges a visszatérítés folytatásához.</span><span class="sxs-lookup"><span data-stu-id="aace4-128">If this amount is exceeded, manager override is required in order to continue with the refund.</span></span> <span data-ttu-id="aace4-129">Az alábbi esetek kezeléséhez a szállítási költségek visszatérítése túllépheti az eredetileg kifizetett összeget:</span><span class="sxs-lookup"><span data-stu-id="aace4-129">To accommodate the following scenarios, a refund of shipping charges can exceed the amount that was originally paid:</span></span>
    -   <span data-ttu-id="aace4-130">A költségek alkalmazására az értékesítési rendelés fejlécének szintjén kerül sor, és amikor egy termékkör bizonyos mennyiségét visszaküldik, a szállítási költségek a termékekhez engedélyezett maximális visszatérítése és a mennyiség nem határozható meg úgy, hogy az minden kiskereskedelmi vevő számára megfelelő legyen.</span><span class="sxs-lookup"><span data-stu-id="aace4-130">Charges are applied at the level of the sales order header, and when some quantity of a product line is returned, the maximum refund of shipping charges that is allowed for the products and the quantity can't be determined in way that works for all retail customers.</span></span>
    -   <span data-ttu-id="aace4-131">Minden szállítási példánynál felmerülnek szállítási költségek.</span><span class="sxs-lookup"><span data-stu-id="aace4-131">Shipping charges are incurred for every instance of shipping.</span></span> <span data-ttu-id="aace4-132">Ha egy vevő többször küld vissza termékeket, és a kiskereskedő irányelve kimondja, hogy a visszatérítési szállítási költségek költségét a kiskereskedő viseli, a visszatérítési szállítási költségek összege magasabb lesz a tényleges szállítási költségeknél.</span><span class="sxs-lookup"><span data-stu-id="aace4-132">If a customer returns products multiple times, and the retailer’s policy specifies that the retailer will bear the cost of return shipping charges, the return shipping charges will be more than the actual shipping charges.</span></span>

## <a name="transaction-flow-for-customer-orders"></a><span data-ttu-id="aace4-133">Tranzakció folyamata vevői rendeléseknél</span><span class="sxs-lookup"><span data-stu-id="aace4-133">Transaction flow for customer orders</span></span>
### <a name="create-a-customer-order-in-retail-modern-pos"></a><span data-ttu-id="aace4-134">Vevői rendelés létrehozása Retail Modern POS-ben</span><span class="sxs-lookup"><span data-stu-id="aace4-134">Create a customer order in Retail Modern POS</span></span>

1.  <span data-ttu-id="aace4-135">Vevő hozzáadása a tranzakcióhoz</span><span class="sxs-lookup"><span data-stu-id="aace4-135">Add a customer to the transaction.</span></span>
2.  <span data-ttu-id="aace4-136">Adjon hozzá termékeket a kosárhoz.</span><span class="sxs-lookup"><span data-stu-id="aace4-136">Add products to the cart.</span></span>
3.  <span data-ttu-id="aace4-137">Kattintson a **Vevői rendelés létrehozása** elemre, majd válassza ki a rendelés típusát.</span><span class="sxs-lookup"><span data-stu-id="aace4-137">Click **Create customer order**, and then select the order type.</span></span> <span data-ttu-id="aace4-138">A rendelés típusa lehet **Vevői rendelés** vagy **Ajánlat**.</span><span class="sxs-lookup"><span data-stu-id="aace4-138">The order type can be either **Customer order** or **Quote**.</span></span>
4.  <span data-ttu-id="aace4-139">Kattintson a **Kijelölt szállítása** vagy az **Összes szállítása** elemre a termékek a vevői fiókban szereplő egyik címre történő kiszállításához, adja meg a kért szállítási dátumot, és adja meg a szállítási költségeket.</span><span class="sxs-lookup"><span data-stu-id="aace4-139">Click **Ship selected** or **Ship all** to ship the products to an address on the customer account, specify the requested shipping date, and specify shipping charges.</span></span>
5.  <span data-ttu-id="aace4-140">Kattintson a **Kijelölt felvétele** vagy az **Összes felvétele** elemre a jelenlegi vagy egy másik boltból adott napon átvételre kerülő termékek kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="aace4-140">Click **Pick up selected** or **Pick-up all** to select products that will be picked up from the current store or a different store on a specific date.</span></span>
6.  <span data-ttu-id="aace4-141">Szedje be a letét összegét, ha letétre szükség van.</span><span class="sxs-lookup"><span data-stu-id="aace4-141">Collect the deposit amount, if a deposit is required.</span></span>

### <a name="edit-an-existing-customer-order"></a><span data-ttu-id="aace4-142">Meglévő vevői rendelés szerkesztése</span><span class="sxs-lookup"><span data-stu-id="aace4-142">Edit an existing customer order</span></span>

1.  <span data-ttu-id="aace4-143">A kezdőlapon kattintson a **Rendelés keresése** elemre.</span><span class="sxs-lookup"><span data-stu-id="aace4-143">On the home page, click **Find an order**.</span></span>
2.  <span data-ttu-id="aace4-144">Keresse meg és válassza ki a szerkesztendő rendelést.</span><span class="sxs-lookup"><span data-stu-id="aace4-144">Find and select the order to edit.</span></span> <span data-ttu-id="aace4-145">A lap alján kattintson a **Szerkesztés** elemre.</span><span class="sxs-lookup"><span data-stu-id="aace4-145">At the bottom of the page, click the **Edit**.</span></span>

### <a name="pick-up-an-order"></a><span data-ttu-id="aace4-146">Rendelés felvétele</span><span class="sxs-lookup"><span data-stu-id="aace4-146">Pick up an order</span></span>

1.  <span data-ttu-id="aace4-147">A kezdőlapon kattintson a **Rendelés keresése** elemre.</span><span class="sxs-lookup"><span data-stu-id="aace4-147">On the home page, click **Find an order**.</span></span>
2.  <span data-ttu-id="aace4-148">Válassza ki a felveendő rendelést.</span><span class="sxs-lookup"><span data-stu-id="aace4-148">Select the order to pick up.</span></span> <span data-ttu-id="aace4-149">A lap alján kattintson a **Kitárolás és csomagolás** elemre.</span><span class="sxs-lookup"><span data-stu-id="aace4-149">At the bottom of the page, click **Picking and packing**.</span></span>
3.  <span data-ttu-id="aace4-150">Kattintson a **Felvétel** elemre.</span><span class="sxs-lookup"><span data-stu-id="aace4-150">Click **Pick up**.</span></span>

### <a name="cancel-an-order"></a><span data-ttu-id="aace4-151">Rendelés visszavonása</span><span class="sxs-lookup"><span data-stu-id="aace4-151">Cancel an order</span></span>

1.  <span data-ttu-id="aace4-152">A kezdőlapon kattintson a **Rendelés keresése** elemre.</span><span class="sxs-lookup"><span data-stu-id="aace4-152">On the home page, click **Find an order**.</span></span>
2.  <span data-ttu-id="aace4-153">Válassza ki a visszavonni kívánt megrendelést.</span><span class="sxs-lookup"><span data-stu-id="aace4-153">Select the order to cancel.</span></span> <span data-ttu-id="aace4-154">A lap alján kattintson az **Érvénytelenítés** elemre.</span><span class="sxs-lookup"><span data-stu-id="aace4-154">At the bottom of the page, click **Cancel**.</span></span>

#### <a name="create-a-return-order"></a><span data-ttu-id="aace4-155">Visszárurendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="aace4-155">Create a return order</span></span>

1.  <span data-ttu-id="aace4-156">A kezdőlapon kattintson a **Rendelés keresése** elemre.</span><span class="sxs-lookup"><span data-stu-id="aace4-156">On the home page, click **Find an order**.</span></span>
2.  <span data-ttu-id="aace4-157">Válassza ki a visszaküldeni kívánt rendelést, válassza a rendeléshez tartozó számlát, és válassza ki a visszaküldendő áruhoz tartozó terméksort .</span><span class="sxs-lookup"><span data-stu-id="aace4-157">Select the order to return, select the invoice for the order, and then select the product line for the merchandise to return.</span></span>
3.  <span data-ttu-id="aace4-158">A lap alján kattintson a **Visszárurendelés** elemre.</span><span class="sxs-lookup"><span data-stu-id="aace4-158">At the bottom of the page, click the **Return order**.</span></span>

## <a name="asynchronous-transaction-flow-for-customer-orders"></a><span data-ttu-id="aace4-159">Tranzakció aszinkron folyamata vevői rendeléseknél</span><span class="sxs-lookup"><span data-stu-id="aace4-159">Asynchronous transaction flow for customer orders</span></span>
<span data-ttu-id="aace4-160">Vevői rendelések pénztári (POS) kliensből szinkron vagy aszinkron üzemmódban hozhatók létre.</span><span class="sxs-lookup"><span data-stu-id="aace4-160">Customer orders can be created from the point of sale (POS) client in either synchronous mode or asynchronous mode.</span></span>

### <a name="enable-customer-orders-to-be-created-in-asynchronous-mode"></a><span data-ttu-id="aace4-161">Vevői rendelések aszinkron módban történő létrehozásának engedélyezése</span><span class="sxs-lookup"><span data-stu-id="aace4-161">Enable customer orders to be created in asynchronous mode</span></span>

1.  <span data-ttu-id="aace4-162">Kattintson a **Kiskereskedelem** &gt; **Csatorna beállítása** &gt; **Pénztárbeállítás** &gt; **Pénztárprofil** &gt; **Funkcióprofilok** elemre.</span><span class="sxs-lookup"><span data-stu-id="aace4-162">Click **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS profile** &gt; **Functionality profiles**.</span></span>
2.  <span data-ttu-id="aace4-163">Az **Általános** gyorslapon állítsa a **Vevői rendelés létrehozása aszinkron módban** lehetőséget **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="aace4-163">On the **General** FastTab, set the **Create customer order in async mode** option to **Yes**.</span></span>

<span data-ttu-id="aace4-164">Ha a **Vevői rendelés létrehozása aszinkron módban** beállítása **Igen**, a vevői rendelések mindig aszinkron módban jönnek létre, akkor is, ha a Retail Transaction Service (RTS) elérhető.</span><span class="sxs-lookup"><span data-stu-id="aace4-164">When the **Create customer order in async mode** option is set to **Yes**, customer orders are always created in asynchronous mode, even if Retail Transaction Service (RTS) is available.</span></span> <span data-ttu-id="aace4-165">Ha ennél a beállításnál **Nem** értéket ad meg, a vevői rendelések mindig szinkron módban jönnek létre az RTS segítségével.</span><span class="sxs-lookup"><span data-stu-id="aace4-165">If you set this option to **No**, customer orders are always created in synchronous mode by using RTS.</span></span> <span data-ttu-id="aace4-166">Vevői rendelések aszinkron módban történő létrehozásakor ezeket a rendszer lekéri és kiskereskedelmi lekérési (P) feladatként beilleszti.</span><span class="sxs-lookup"><span data-stu-id="aace4-166">When customer orders are created in asynchronous mode, they are pulled and inserted into Retail by Pull (P) jobs.</span></span> <span data-ttu-id="aace4-167">A megfelelő vevői rendelések a **Rendelések szinkronizálása** manuális futtatásakor vagy kötegelt feldolgozás révén jönnek létre a Kiskereskedelem modulban.</span><span class="sxs-lookup"><span data-stu-id="aace4-167">The corresponding sales orders are created in Retail when **Synchronize orders** is run either manually or through a batch process.</span></span>

<a name="see-also"></a><span data-ttu-id="aace4-168">Lásd még</span><span class="sxs-lookup"><span data-stu-id="aace4-168">See also</span></span>
--------

[<span data-ttu-id="aace4-169">Hibrid vevői rendelések</span><span class="sxs-lookup"><span data-stu-id="aace4-169">Hybrid customer orders</span></span>](hybrid-customer-orders.md)




