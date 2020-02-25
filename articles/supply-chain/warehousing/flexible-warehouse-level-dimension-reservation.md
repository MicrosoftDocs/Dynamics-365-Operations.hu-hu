---
title: Rugalmas raktárszintű dimenziófoglalási irányelv
description: Ez a témakör azt mutatja be, hogy a készletfoglalási irányelv, amely lehetővé teszi, hogy a kötegelt nyomon követésű termékeket értékesítő és a logisztikát a WMS-kompatibilis műveletekekként futtató vállalatok lefoglaljanak bizonyos kötegeket ügyfelek értékesítési rendeléseihez, még akkor is, ha a foglalási hierarchia a termékekhez kapcsolódóan nem engedélyezi a meghatározott kötegek foglalását.
author: omulvad
manager: AnnBe
ms.date: 02/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReservationHierarchy
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2020-01-15
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: c0baf96315dd9fe6bc1984d337fd1c50ae47016a
ms.sourcegitcommit: 4e62c22b53693c201baa646a8f047edb5a0a2747
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/07/2020
ms.locfileid: "3031043"
---
# <a name="flexible-warehouse-level-dimension-reservation-policy"></a><span data-ttu-id="24930-103">Rugalmas raktárszintű dimenziófoglalási irányelv</span><span class="sxs-lookup"><span data-stu-id="24930-103">Flexible warehouse-level dimension reservation policy</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="24930-104">Amikor egy „kötegalatti\[hely\]” típusú készlet foglalási hierarchiája termékekhez van társítva, a kötegelt nyomon követéssel ellátott termékeket értékesítő és a logisztikai műveleteiket a Microsoft Dynamics 365 raktározási rendszerrel (WMS) kompatibilisként futtató vállalatok nem foglalhatják le az illető termékek konkrét kötegeit ügyfelek értékesítési rendeléseihez.</span><span class="sxs-lookup"><span data-stu-id="24930-104">When an inventory reservation hierarchy of the "Batch-below\[location\]" type is associated with products, businesses that sell batch-tracked products and run their logistics as operations that are enabled for the Microsoft Dynamics 365 Warehouse Management System (WMS) can't reserve specific batches of those products for customer sales orders.</span></span> <span data-ttu-id="24930-105">Ez a témakör bemutatja azt a készletfoglalási irányelvet, amely alapján a vállalatok meghatározott kötegeket foglalhatnak le, még akkor is, ha a termékek a „kötegalatti\[hely\]” foglalási hierarchiával vannak társítva.</span><span class="sxs-lookup"><span data-stu-id="24930-105">This topic describes the inventory reservation policy that lets these businesses reserve specific batches, even when the products are associated with a "Batch-below\[location\]" reservation hierarchy.</span></span>

## <a name="inventory-reservation-hierarchy"></a><span data-ttu-id="24930-106">Készletfoglalási hierarchia</span><span class="sxs-lookup"><span data-stu-id="24930-106">Inventory reservation hierarchy</span></span>

<span data-ttu-id="24930-107">Ez a szakasz összegzi a meglévő készletfoglalási hierarchiát.</span><span class="sxs-lookup"><span data-stu-id="24930-107">This section summarizes the existing inventory reservation hierarchy.</span></span> <span data-ttu-id="24930-108">A program a kötegelt nyomon követéssel és a sorozatszámmal kezelt cikkek kezelési módjára koncentrál.</span><span class="sxs-lookup"><span data-stu-id="24930-108">It focuses on the way that batch-tracked and serial-tracked items are handled.</span></span>

<span data-ttu-id="24930-109">A készletfoglalási hierarchia azt írja elő, hogy a tárolási dimenziókat illetően az igény szerinti rendelés a hely, a raktár és a készlet állapotának kötelező dimenzióit hordozza. A raktári logika felelős azért, hogy a kívánt mennyiségekhez helyet rendeljen, és lefoglalja azt.</span><span class="sxs-lookup"><span data-stu-id="24930-109">The inventory reservation hierarchy dictates that, as far as storage dimensions are concerned, the demand order carries the mandatory dimensions of site, warehouse, and inventory status, whereas the warehouse logic is responsible for assigning a location to the requested quantities and reserving the location.</span></span> <span data-ttu-id="24930-110">Más szóval az igény szerinti rendelés és a raktári műveletek közötti interakciókban várhatóan az igény szerinti rendelése jelzi, hogy honnan kell szállítani a rendelést (azaz a helyet és a raktárat).</span><span class="sxs-lookup"><span data-stu-id="24930-110">In other words, in the interactions between the demand order and the warehouse operations, the demand order is expected to indicate where the order must be shipped from (that is, what site and warehouse).</span></span> <span data-ttu-id="24930-111">A raktár ezután saját logikájára alapozva megkeresi a szükséges mennyiséget a raktár területén.</span><span class="sxs-lookup"><span data-stu-id="24930-111">The warehouse then relies on its logic to find the required quantity in the warehouse premises.</span></span>

<span data-ttu-id="24930-112">Ha azonban az üzlet műveleti modelljét szeretné tükrözni, a nyomonkövetési dimenziók esetén (köteg-és sorozatszámok) nagyobb rugalmasságra van szükség.</span><span class="sxs-lookup"><span data-stu-id="24930-112">However, to reflect the operational model of the business, tracking dimensions (batch and serial numbers) are subject to more flexibility.</span></span> <span data-ttu-id="24930-113">A készletfoglalási hierarchia olyan esetekhez használható, amelyekben teljesülnek az alábbi feltételek:</span><span class="sxs-lookup"><span data-stu-id="24930-113">An inventory reservation hierarchy can accommodate scenarios where the following conditions apply:</span></span>

- <span data-ttu-id="24930-114">A vállalat a raktári műveletei alapján kezeli a köteg-vagy sorozatszámmal ellátott mennyiségek kiválasztását, miután a mennyiségeket a rendszer megtalálta a raktározási tárolóhelyen.</span><span class="sxs-lookup"><span data-stu-id="24930-114">The business relies on its warehouse operations to manage picking of quantities that have batch or serial numbers after the quantities have been found in the warehousing storage space.</span></span> <span data-ttu-id="24930-115">Ezt a modellt gyakran nevezzük *kötegalatti\[helynek\]*.</span><span class="sxs-lookup"><span data-stu-id="24930-115">This model is often referred to as *Batch-below\[location\]*.</span></span> <span data-ttu-id="24930-116">Ezt általában akkor használják, ha a termék köteg- vagy sorozatszám-azonosítója nem fontos azoknak a vevőknek, akik a rendelést tették az értékesítő vállalatnál.</span><span class="sxs-lookup"><span data-stu-id="24930-116">It's typically used when a product's batch or serial number identification isn't important to the customers who place the demand with the selling company.</span></span>
- <span data-ttu-id="24930-117">Ha a köteg-vagy sorozatszámok a vevői rendelési specifikáció részei, és a program rögzíti azokat az igény szerinti rendelésen, akkor a raktári műveleteket, amelyek megkeresik a raktárban lévő mennyiségeket, az egyes igényelt számokkal korlátozni lehet, és azok nem módosíthatók.</span><span class="sxs-lookup"><span data-stu-id="24930-117">If batch or serial numbers are part of a customer's order specification, and they are recorded on the demand order, the warehouse operations that find the quantities in the warehouse are constrained by the specific requested numbers and aren't allowed to change them.</span></span> <span data-ttu-id="24930-118">Ezt a modellt nevezzük *kötegfeletti\[helynek\]*.</span><span class="sxs-lookup"><span data-stu-id="24930-118">This model is referred to as *Batch-above\[location\]*.</span></span>

<span data-ttu-id="24930-119">Ezekben az esetekben a kihívás az, hogy csak egyetlen készletfoglalási hierarchiát lehet hozzárendelni az egyes kiadott termékekhez.</span><span class="sxs-lookup"><span data-stu-id="24930-119">In these scenarios, the challenge is that only one inventory reservation hierarchy can be assigned to each released product.</span></span> <span data-ttu-id="24930-120">Ezért ahhoz, hogy WMS kezelje a nyomon követett cikkeket, miután a hierarchia-hozzárendelés meghatározza, hogy mikor kell lefoglalni a köteg-vagy sorozatszámot (vagy az igény szerinti rendelés fogadásakor, vagy a raktári kitárolási munka során), ez az időzítés nem módosítható ad hoc módon.</span><span class="sxs-lookup"><span data-stu-id="24930-120">Therefore, for the WMS to handle tracked items, after the hierarchy assignment determines when the batch or serial number should be reserved (either when the demand order is taken or during the warehouse picking work), this timing can't be changed on an ad-hoc basis.</span></span>

## <a name="flexible-reservation-for-batch-tracked-items"></a><span data-ttu-id="24930-121">Rugalmas foglalás a kötegelten nyomon követett cikkeknél</span><span class="sxs-lookup"><span data-stu-id="24930-121">Flexible reservation for batch-tracked items</span></span>

### <a name="business-scenario"></a><span data-ttu-id="24930-122">Üzleti eset</span><span class="sxs-lookup"><span data-stu-id="24930-122">Business scenario</span></span>

<span data-ttu-id="24930-123">Ebben a helyzetben a vállalat egy készletstratégiát alkalmaz, amelyben a késztermékeket a kötegszámokkal követi nyomon.</span><span class="sxs-lookup"><span data-stu-id="24930-123">In this scenario, a company uses an inventory strategy where finished goods are tracked by batch numbers.</span></span> <span data-ttu-id="24930-124">Ez a vállalat is a WHS terhelést használja.</span><span class="sxs-lookup"><span data-stu-id="24930-124">This company also uses the WHS workload.</span></span> <span data-ttu-id="24930-125">Mivel ez a terhelés jól felszerelt logikával rendelkezik a raktári kitárolási és fuvarozási műveletek tervezéséhz és lefuttatásához kötegelésre engedélyezett elemek esetén, a kész cikkek többsége a „kötegalatti\[hely\]” készletfoglalási hierarchiához van társítva.</span><span class="sxs-lookup"><span data-stu-id="24930-125">Because this workload has well-equipped logic for planning and running warehouse picking and shipping operations for batch-enabled items, most of the finished items are associated with a "Batch-below\[location\]" inventory reservation hierarchy.</span></span> <span data-ttu-id="24930-126">Ennek a működési beállításnak az az előnye, hogy a döntéseket (amelyek valójában foglalási döntések) arról, hogy mely kötegeket kell kiválasztania, és hová kell tenni őket a raktárban, elhalasztják, amíg el nem kezdődnek a raktári kitárolási műveletek.</span><span class="sxs-lookup"><span data-stu-id="24930-126">The advantage of this type of operational setup is that decisions (which are effectively reservation decisions) about which batches to pick and where to put them in the warehouse are postponed until the warehouse picking operations start.</span></span> <span data-ttu-id="24930-127">Nem akkor jönnek létre, amikor az ügyfél rendel.</span><span class="sxs-lookup"><span data-stu-id="24930-127">They aren't made when the customer's order is placed.</span></span>

<span data-ttu-id="24930-128">Bár a „kötegalatti\[hely\]” foglalási hierarchia jól szolgálja a vállalat üzleti céljait, a vállalatok ügyfeleinek többsége termékek újrarendelésekor ugyanazt a köteget kéri, amelyet már egyszer megvásárolt.</span><span class="sxs-lookup"><span data-stu-id="24930-128">Although the "Batch-below\[location\]" reservation hierarchy serves the company's business goals well, many of the company's established customers require the same batch that they previously purchased when they reorder products.</span></span> <span data-ttu-id="24930-129">A vállalatnak ezért rugalmasságra van szüksége a kötegelt foglalási szabályok kezelésében, hogy az ugyanazon tétel vevői igényének függvényében a következők történjenek:</span><span class="sxs-lookup"><span data-stu-id="24930-129">Therefore, the company is looking for flexibility in the way that the batch reservation rules are handled, so that, depending on the customers' demand for the same item, the following behaviors occur:</span></span>

- <span data-ttu-id="24930-130">A kötegszám rögzíthető és lefoglalható, amikor a rendelést az értékesítési feldolgozó átveszi, és a raktári műveletek és/vagy más igények során nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="24930-130">A batch number can be recorded and reserved when the order is taken by the sales processor, and it can't be changed during warehouse operations and/or taken by other demands.</span></span> <span data-ttu-id="24930-131">Ez a viselkedés segít annak biztosításában, hogy a megrendelt kötegszámot szállítsák az ügyfélnek.</span><span class="sxs-lookup"><span data-stu-id="24930-131">This behavior helps guarantee that the batch number that was ordered is shipped to the customer.</span></span>
- <span data-ttu-id="24930-132">Ha a kötegszám nem fontos a vevő számára, akkor a raktári műveletek a kitárolási munka során meghatározhatják a kötegszámot az után, hogy az értékesítési rendelés regisztrálása és a foglalás megtörtént.</span><span class="sxs-lookup"><span data-stu-id="24930-132">If the batch number isn't important to the customer, the warehouse operations can determine a batch number during picking work, after sales order registration and reservation have been done.</span></span>

### <a name="allowing-reservation-of-a-specific-batch-on-the-sales-order"></a><span data-ttu-id="24930-133">Konkrét köteg foglalásának engedélyezése az értékesítési rendelésen</span><span class="sxs-lookup"><span data-stu-id="24930-133">Allowing reservation of a specific batch on the sales order</span></span>

<span data-ttu-id="24930-134">A „kötegalatti\[hely\]” foglalási hierarchiához társított cikkek kötegelt foglalási viselkedésében szükséges rugalmasság elérése érdekében a **Készletfoglalási hierarchiák lapon** a készletkezelőnek be kell jelölnie az **Foglalás engedélyezése igény szerinti foglalásra** jelölőnyégyzetet a **Köteg száma** szinten.</span><span class="sxs-lookup"><span data-stu-id="24930-134">To accommodate the desired flexibility in the batch reservation behavior for items that are associated with a "Batch-below\[location\]" inventory reservation hierarchy, inventory managers must select the **Allow reservation on demand order** check box for the **Batch number** level on the **Inventory reservation hierarchies** page.</span></span>

![A készletfoglalási hierarchia rugalmassá tétele](media/Flexible-inventory-reservation-hierarchy.png)

<span data-ttu-id="24930-136">Ha a hierarchiában kiválasztja a **Kötegszám** szintjét, akkor a program automatikusan kijelöli az illető szint fölötti és a **Hely** szintjén található összes dimenziót.</span><span class="sxs-lookup"><span data-stu-id="24930-136">When the **Batch number** level in the hierarchy is selected, all dimensions above that level and up through the **Location** level will be automatically selected.</span></span> <span data-ttu-id="24930-137">(Alapértelmezetten szerint a **Hely** szint fölötti összes dimenzió előre be van jelölve.) Ez a viselkedés azt a logikát jelzi, amely szerint a kötegszám és a hely közötti tartományban található összes dimenziót a program automatikusan lefoglalja, miután a felhasználó lefoglalt egy meghatározott kötegszámot a rendelési sorban.</span><span class="sxs-lookup"><span data-stu-id="24930-137">(By default, all dimensions above the **Location** level are preselected.) This behavior reflects the logic where all dimensions in the range between the batch number and location are also automatically reserved after you reserve a specific batch number on the order line.</span></span>

> [!NOTE]
> <span data-ttu-id="24930-138">A **Foglalás engedélyezése igény szerinti rendelésnél** jelölőnégyzet csak a raktári hely dimenzió alatti foglalási hierarchia szintjére vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="24930-138">The **Allow reservation on demand order** check box applies only to reservation hierarchy levels that are below the warehouse location dimension.</span></span>
>
> <span data-ttu-id="24930-139">A **Kötegszám** a hierarchia egyetlen olyan szintje, amely nyitott a rugalmas foglalási irányelv számára.</span><span class="sxs-lookup"><span data-stu-id="24930-139">**Batch number** is the only level in the hierarchy that is open for the flexible reservation policy.</span></span> <span data-ttu-id="24930-140">Más szóval nem jelölheti be a **Foglalás engedélyezése igény szerinti rendelésnél** jelölőnégyzetet a **Hely**, **Rendszámtábla** vagy **Sorozatszám** szinteken.</span><span class="sxs-lookup"><span data-stu-id="24930-140">In other words, you can't select the **Allow reservation on demand order** check box for the **Location**, **License plate**, or **Serial number** level.</span></span>
>
> <span data-ttu-id="24930-141">Ha a foglalási hierarchiában szerepel a sorozatszám dimenzió (amelynek mindig a **Kötegszám** szint alatt kell lennie), és ha bekapcsolta a kötegszám-specifikus foglalást,, a rendszer továbbra is a sorozatszám szerinti foglalási és kitárolási műveleteket fogja kezelni a „sorszámalatti\[hely\]” foglalási irányelvre vonatkozó szabályok alapján.</span><span class="sxs-lookup"><span data-stu-id="24930-141">If your reservation hierarchy includes the serial number dimension (which must always be below the **Batch number** level), and if you've turned on batch-specific reservation for the batch number, the system will continue to handle serial number reservation and picking operations, based on the rules that apply to the "Serial-below\[location\]" reservation policy.</span></span>

<span data-ttu-id="24930-142">A telepítés során bármikor engedélyezheti a kötegspecifikus foglalást egy létező „kötegalatti\[hely\]” foglalási hierarchiában a telepítésben.</span><span class="sxs-lookup"><span data-stu-id="24930-142">At any point, you can allow batch-specific reservation for an existing "Batch-below\[location\]" reservation hierarchy in your deployment.</span></span> <span data-ttu-id="24930-143">A módosítás nem fogja érinteni a módosítás előtt létrehozott foglalásokat és nyitott raktári munkákat.</span><span class="sxs-lookup"><span data-stu-id="24930-143">This change won't affect any reservations and open warehouse work that were created before the change occurred.</span></span> <span data-ttu-id="24930-144">Azonban a **Foglalás engedélyezése az igény szerinti rendelésnél** jelölőnégyzetet nem lehet törölni, ha az adott foglalási hierarchiához társított egy vagy több cikk esetén a **Foglalt rendelt**, **Foglalt tényleges** vagy **Megrendelve** típusú problémák készlettranzakciói léteznek.</span><span class="sxs-lookup"><span data-stu-id="24930-144">However, the **Allow reservation on demand order** check box can't be cleared if inventory transactions of the **Reserved ordered**, **Reserved physical**, or **Ordered** issue type exist for one or more items that are associated with that reservation hierarchy.</span></span>

> [!NOTE]
> <span data-ttu-id="24930-145">Ha egy elem meglévő foglalási hierarchiája nem teszi lehetővé a köteg megadását a rendelésen, akkor újra hozzárendelheti azt egy olyan foglalási hierarchiához, amely lehetővé teszi a köteg megadását, feltéve, hogy a hierarchia szintjének szerkezete mindkét hierarchiában ugyanaz.</span><span class="sxs-lookup"><span data-stu-id="24930-145">If an item's existing reservation hierarchy doesn't allow batch specification on the order, you can reassign it to a reservation hierarchy that does allow batch specification, provided that the hierarchy level structure is the same in both hierarchies.</span></span> <span data-ttu-id="24930-146">Az ismételt hozzárendeléshez használja a **Cikkek foglalási hierarchiájának módosítása** funkciót.</span><span class="sxs-lookup"><span data-stu-id="24930-146">Use the **Change reservation hierarchy for items** function to do the reassignment.</span></span> <span data-ttu-id="24930-147">Ez a módosítás akkor lehet fontos, ha el akarja kerülni a rugalmas kötegelt rendelést a kötegelt nyomonkövetésű cikkek egy csoportja esetén, azonban engedélyezni akarja azt a termékportfólió többi eleme számára.</span><span class="sxs-lookup"><span data-stu-id="24930-147">This change might be relevant when you want to prevent flexible batch reservation for a subset of batch-tracked items but allow it for the rest of the product portfolio.</span></span>

<span data-ttu-id="24930-148">Függetlenül attól, hogy bejelölte-e a **Foglalás engedélyezése igény szerinti rendelésnél** jelölőnégyzetet, ha a rendelési sorban nem szeretne lefoglalni egy konkrét kötegszámot, az alapértelmezett, „kötegalatti\[hely\]” foglalási hierarchia esetében érvényes raktárműveleti logika lép érvénybe.</span><span class="sxs-lookup"><span data-stu-id="24930-148">Regardless of whether you've selected the **Allow reservation on demand order** check box, if you don't want to reserve a specific batch number for the item on an order line, default warehouse operations logic that is valid for a "Batch-below\[location\]" reservation hierarchy will still apply.</span></span>

### <a name="reserve-a-specific-batch-number-for-a-customer-order"></a><span data-ttu-id="24930-149">Konkrét kötegszám foglalása egy vevői rendeléshez</span><span class="sxs-lookup"><span data-stu-id="24930-149">Reserve a specific batch number for a customer order</span></span>

<span data-ttu-id="24930-150">Ha egy kötegelt nyomonkövetésű elem „kötegalatti\[hely\]” típusú készle foglalási hierarchiája úgy van beállítva, hogy engedélyezze az értékesítési rendeléseken a konkrét kötegszám foglalását, akkor az értékesítési rendelések feldolgozói a vevői igényektől függően a következő módokon vehetik fel a vevői rendeléseket ugyanarra a tételre:</span><span class="sxs-lookup"><span data-stu-id="24930-150">After a batch-tracked item's "Batch-below\[location\]" inventory reservation hierarchy is set up to allow reservation of specific batch numbers on sales orders, sales order processors can take customer orders for the same item in one of the following ways, depending on the customer's request:</span></span>

- <span data-ttu-id="24930-151">**Rendelés részleteinek megadása a kötegszám megadása nélkül** – ezt a megközelítést akkor kell használni, ha a termékköteg megadása nem fontos a vevő számára.</span><span class="sxs-lookup"><span data-stu-id="24930-151">**Enter order details without specifying a batch number** – This approach should be used when the product's batch specification isn't important to the customer.</span></span> <span data-ttu-id="24930-152">Az ilyen típusú rendelések kezelésével kapcsolatos összes meglévő folyamat változatlan marad.</span><span class="sxs-lookup"><span data-stu-id="24930-152">All existing processes that are associated with handling an order of this type in the system remain unchanged.</span></span> <span data-ttu-id="24930-153">A felhasználók részéről nem szükséges további megfontolás.</span><span class="sxs-lookup"><span data-stu-id="24930-153">No additional considerations are required on the part of users.</span></span>
- <span data-ttu-id="24930-154">**Rendelés részleteinek megadása és egy konkrét kötegszám lefoglalása** – ezt a megközelítést akkor kell használni, ha a vevő egy konkrét köteget kér.</span><span class="sxs-lookup"><span data-stu-id="24930-154">**Enter order details and reserve a specific batch number** – This approach should be used when the customer requests a specific batch.</span></span> <span data-ttu-id="24930-155">A vevők általában akkor kérnek egy konkrét köteget, ha egy korábban vásárolt terméket rendelnek újra.</span><span class="sxs-lookup"><span data-stu-id="24930-155">Typically, customers will request a specific batch when they are reordering a product that they previously purchased.</span></span> <span data-ttu-id="24930-156">Ezt a típusú kötegspecifikus foglalást nevezik *Rendelésben véglegesített foglalásnak*.</span><span class="sxs-lookup"><span data-stu-id="24930-156">This type of batch-specific reservation is referred to as *order-committed reservation*.</span></span>

<span data-ttu-id="24930-157">A következő szabályok érvényesek a mennyiségek feldolgozásakor, ha a köteg számát egy konkrét rendeléshez kötötték:</span><span class="sxs-lookup"><span data-stu-id="24930-157">The following set of rules is valid when quantities are processed, and a batch number is committed to a specific order:</span></span>

- <span data-ttu-id="24930-158">Ha engedélyezni szeretné egy konkrét kötegszám foglalását a „kötegalatti\[hely\]” foglalási hierarchiában, a rendszernek a hely dimenzióig minden dimenziót le kell foglalnia.</span><span class="sxs-lookup"><span data-stu-id="24930-158">To allow reservation of a specific batch number for an item under the "Batch-below\[location\]" reservation policy, the system must reserve all dimensions up through location.</span></span> <span data-ttu-id="24930-159">Ez a tartomány általában a rendszámtábla dimenziót tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="24930-159">This range typically includes the license plate dimension.</span></span>
- <span data-ttu-id="24930-160">A hely irányelvei nem használatosak, amikor olyan értékesítési sorhoz hozza létre a kitárolási munkát, amely rendelésben véglegesített kötegfoglalást használ.</span><span class="sxs-lookup"><span data-stu-id="24930-160">Location directives aren't used when picking work is created for a sales line that uses order-committed batch reservation.</span></span>
- <span data-ttu-id="24930-161">A rendelésben véglegesített kötegfoglaláshoz tartozó munka raktári feldolgozása során sem a felhasználó, sem a rendszer nem módosíthatja a kötegszámot.</span><span class="sxs-lookup"><span data-stu-id="24930-161">During warehouse processing of work for order-committed batches, neither the user nor the system is allowed to change the batch number.</span></span> <span data-ttu-id="24930-162">(Ez a feldolgozás tartalmazza a kivételek kezelését.)</span><span class="sxs-lookup"><span data-stu-id="24930-162">(This processing includes exception handling.)</span></span>

<span data-ttu-id="24930-163">A következő példa bemutatja a végpontok közötti áramlást.</span><span class="sxs-lookup"><span data-stu-id="24930-163">The following example shows the end-to-end flow.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="24930-164">Példaforgatókönyv</span><span class="sxs-lookup"><span data-stu-id="24930-164">Example scenario</span></span>

<span data-ttu-id="24930-165">Ebben a példában a bemutatóadatokat kell telepíteni, és az **USMF** demó-adatvállalatot kell használnia.</span><span class="sxs-lookup"><span data-stu-id="24930-165">For this example, demo data must be installed, and you must use the **USMF** demo data company.</span></span>

### <a name="set-up-an-inventory-reservation-hierarchy-to-allow-batch-specific-reservation"></a><span data-ttu-id="24930-166">Hozzon létre egy készletfoglalási hierarchiát, hogy lehetővé tegye a kötegspecifikus foglalást</span><span class="sxs-lookup"><span data-stu-id="24930-166">Set up an inventory reservation hierarchy to allow batch-specific reservation</span></span>

1. <span data-ttu-id="24930-167">Nyissa meg a **Raktárkezelés** \> **Beállítás** \> **Készlet \> Foglalási hierarchia** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="24930-167">Go to **Warehouse management** \> **Setup** \> **Inventory \> Reservation hierarchy**.</span></span>
2. <span data-ttu-id="24930-168">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="24930-168">Select **New**.</span></span>
3. <span data-ttu-id="24930-169">Adja meg a feladat egyedi nevét a **Név** mezőben (pl. **BatchFlex**).</span><span class="sxs-lookup"><span data-stu-id="24930-169">In the **Name** field, enter a name (for example, **BatchFlex**).</span></span>
4. <span data-ttu-id="24930-170">A **Leírás** mezőben adjon meg egy leírást (például: **Rugalmas alatti kötteg**).</span><span class="sxs-lookup"><span data-stu-id="24930-170">In the **Description** field, enter a description (for example, **Batch below flexible**).</span></span>
5. <span data-ttu-id="24930-171">A **Kijelölve** mezőben válassza ki a **Sorozatszám** és a **Tulajdonos** lehetőségeket, majd a bal nyílgombra kattintva helyezze át őket a **Rendelkezésre áll** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="24930-171">In the **Selected** field, select **Serial number** and **Owner**, and then select the left arrow button to move them to the **Available** field.</span></span>
6. <span data-ttu-id="24930-172">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="24930-172">Select **OK**.</span></span>
7. <span data-ttu-id="24930-173">A **Kötegszám** dimenzió szintjének sorában jelölje be a **Foglalás engedélyezése igény szerinti rendelésnél** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="24930-173">In the row for the **Batch number** dimension level, select the **Allow reservation on demand order** check box.</span></span> <span data-ttu-id="24930-174">A **Rendszámtábla** és a **Hely** szintje automatikusan be van jelölve, és a jelölőnégyzetek nem törölhetők.</span><span class="sxs-lookup"><span data-stu-id="24930-174">The **License plate** and **Location** levels are automatically selected, and you can't clear the check boxes for them.</span></span>
8. <span data-ttu-id="24930-175">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="24930-175">Select **Save**.</span></span>

### <a name="create-a-new-released-product"></a><span data-ttu-id="24930-176">Új kiadott termék létrehozása</span><span class="sxs-lookup"><span data-stu-id="24930-176">Create a new released product</span></span>

1. <span data-ttu-id="24930-177">Adja meg a termék három alapadat-paraméterét az alábbi értékeket használva:</span><span class="sxs-lookup"><span data-stu-id="24930-177">Set the product's three master data parameters by using these values:</span></span>

    - <span data-ttu-id="24930-178">A **Tárolási dimenziócsoport** mezőben válassza a **Raktár** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="24930-178">In the **Storage dimension group** field, select **Ware**.</span></span>
    - <span data-ttu-id="24930-179">A **Nyomon követési dimenziócsoport** mezőben válassza a **Batch-Phy** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="24930-179">In the **Tracking dimension group** field, select **Batch-Phy**.</span></span>
    - <span data-ttu-id="24930-180">A **Foglalási hierarchia** mezőben válassza ki a **BatchFlex** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="24930-180">In the **Reservation hierarchy** field, select **BatchFlex**.</span></span>

2. <span data-ttu-id="24930-181">Hozzon létre két kötegszámot, például **B11** és **B22**.</span><span class="sxs-lookup"><span data-stu-id="24930-181">Create two batch numbers, such as **B11** and **B22**.</span></span>
3. <span data-ttu-id="24930-182">Az alábbi értékek használatával adjon hozzá cikkmennyiségeket az aktuális készlethez.</span><span class="sxs-lookup"><span data-stu-id="24930-182">Add item quantities to on-hand stock by using the following values.</span></span>

    | <span data-ttu-id="24930-183">Raktár</span><span class="sxs-lookup"><span data-stu-id="24930-183">Warehouse</span></span> | <span data-ttu-id="24930-184">Köteg száma</span><span class="sxs-lookup"><span data-stu-id="24930-184">Batch number</span></span> | <span data-ttu-id="24930-185">Helyszín</span><span class="sxs-lookup"><span data-stu-id="24930-185">Location</span></span> | <span data-ttu-id="24930-186">Azonosítótábla</span><span class="sxs-lookup"><span data-stu-id="24930-186">License plate</span></span> | <span data-ttu-id="24930-187">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="24930-187">Quantity</span></span> |
    |-----------|--------------|----------|---------------|----------|
    | <span data-ttu-id="24930-188">24</span><span class="sxs-lookup"><span data-stu-id="24930-188">24</span></span>        | <span data-ttu-id="24930-189">B11</span><span class="sxs-lookup"><span data-stu-id="24930-189">B11</span></span>          | <span data-ttu-id="24930-190">BULK-001</span><span class="sxs-lookup"><span data-stu-id="24930-190">BULK-001</span></span> | <span data-ttu-id="24930-191">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="24930-191">None</span></span>          | <span data-ttu-id="24930-192">10</span><span class="sxs-lookup"><span data-stu-id="24930-192">10</span></span>       |
    | <span data-ttu-id="24930-193">24</span><span class="sxs-lookup"><span data-stu-id="24930-193">24</span></span>        | <span data-ttu-id="24930-194">B11</span><span class="sxs-lookup"><span data-stu-id="24930-194">B11</span></span>          | <span data-ttu-id="24930-195">FL-001</span><span class="sxs-lookup"><span data-stu-id="24930-195">FL-001</span></span>   | <span data-ttu-id="24930-196">LP11</span><span class="sxs-lookup"><span data-stu-id="24930-196">LP11</span></span>          | <span data-ttu-id="24930-197">10</span><span class="sxs-lookup"><span data-stu-id="24930-197">10</span></span>       |
    | <span data-ttu-id="24930-198">24</span><span class="sxs-lookup"><span data-stu-id="24930-198">24</span></span>        | <span data-ttu-id="24930-199">B22</span><span class="sxs-lookup"><span data-stu-id="24930-199">B22</span></span>          | <span data-ttu-id="24930-200">FL-002</span><span class="sxs-lookup"><span data-stu-id="24930-200">FL-002</span></span>   | <span data-ttu-id="24930-201">LP22</span><span class="sxs-lookup"><span data-stu-id="24930-201">LP22</span></span>          | <span data-ttu-id="24930-202">10</span><span class="sxs-lookup"><span data-stu-id="24930-202">10</span></span>       |

### <a name="enter-sales-order-details"></a><span data-ttu-id="24930-203">Értékesítési rendelés adatainak bevitele</span><span class="sxs-lookup"><span data-stu-id="24930-203">Enter sales order details</span></span>

1. <span data-ttu-id="24930-204">Ugorjon az **Értékesítés és marketing** \> **Értékesítési rendelések** \> **Minden értékesítési** rendelés pontra.</span><span class="sxs-lookup"><span data-stu-id="24930-204">Go to **Sales and marketing** \> **Sales orders** \> **All sales orders**.</span></span>
2. <span data-ttu-id="24930-205">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="24930-205">Select **New**.</span></span>
3. <span data-ttu-id="24930-206">Az értékesítési rendelés fejlécében a **Vevői számla** mezőbe írja be az **US-003**értéket.</span><span class="sxs-lookup"><span data-stu-id="24930-206">On the sales order header, in the **Customer account** field, enter **US-003**.</span></span>
4. <span data-ttu-id="24930-207">Adjon hozzá egy sort az új elemhez, és adja meg a **10** mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="24930-207">Add a line for the new item, and enter **10** as the quantity.</span></span> <span data-ttu-id="24930-208">Győződjön meg arról, hogy a **Raktár** mező értéke **24** legyen.</span><span class="sxs-lookup"><span data-stu-id="24930-208">Make sure that the **Warehouse** field is set to **24**.</span></span>
5. <span data-ttu-id="24930-209">Válassza ki az **Értékesítési rendelés sorai** gyorslapot, válassza a **Készlet** elemet majd a **Karbantartás** csoportban válassza a **Köteg lefoglalása** elemet.</span><span class="sxs-lookup"><span data-stu-id="24930-209">On the **Sales order lines** FastTab, select **Inventory**, and then, in the **Maintain** group, select **Batch reservation**.</span></span> <span data-ttu-id="24930-210">A **Köteg lefoglalása** lapon látható a rendelési sor foglalásra használható kötegeinek listája.</span><span class="sxs-lookup"><span data-stu-id="24930-210">The **Batch reservation** page shows a list of batches that are available for reservation for the order line.</span></span> <span data-ttu-id="24930-211">Ebben a példában a mennyiség **20** a **B11** kötegszámra, és **10** a **B22** kötegszámra.</span><span class="sxs-lookup"><span data-stu-id="24930-211">For this example, it shows a quantity of **20** for batch number **B11** and a quantity of **10** for batch number **B22**.</span></span> <span data-ttu-id="24930-212">Figyelem, el, hogy a **Köteg lefoglalása** lap nem érhető el a sorból, ha a sorban szereplő tételt „kötegalatti\[hely\]” foglalási hierarchiához társították, hacsak nem úgy állították be, hogy engedélyezze a kötegspecifikus foglalást.</span><span class="sxs-lookup"><span data-stu-id="24930-212">Note that the **Batch reservation** page cannot be accessed from a line if the item on that line is associated with "Batch-below\[location\]" reservation hierarchy unless it is set up to allow batch-specific reservation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="24930-213">Ha egy értékesítési rendeléshez szeretne egy konkrét köteget foglalni, akkor a **Köteg lefoglalása** lapot kell használnia.</span><span class="sxs-lookup"><span data-stu-id="24930-213">To reserve a specific batch for a sales order, you must use the **Batch reservation** page.</span></span>
    >
    > <span data-ttu-id="24930-214">Ha közvetlenül az értékesítési rendelés sorában adja meg a köteg számát, akkor a rendszer úgy viselkedik, mintha egy konkrét kötegértéket adott volna meg olyan cikkeknél, amelyek a „kötegalatti\[hely\]” foglalási irányelv szerint működnek.</span><span class="sxs-lookup"><span data-stu-id="24930-214">If you enter the batch number directly on the sales order line, the system will behave as though you entered a specific batch value for an item that is subject to the "Batch-below\[location\]" reservation policy.</span></span> <span data-ttu-id="24930-215">A sor mentésekor figyelmeztető üzenetet fog kapni.</span><span class="sxs-lookup"><span data-stu-id="24930-215">When you save the line, you will receive a warning message.</span></span> <span data-ttu-id="24930-216">Ha megerősíti, hogy a kötegszám megadásának közvetlenül a rendelési sorban kell történnie, akkor a sort nem a szokásos raktárkezelési logika kezeli.</span><span class="sxs-lookup"><span data-stu-id="24930-216">If you confirm that the batch number should be specified directly on the order line, the line won't be handled by the regular warehouse management logic.</span></span>
    >
    > <span data-ttu-id="24930-217">Ha lefoglalja a mennyiséget a **Foglalás** oldalon, a program nem foglal le konkrét köteget, és a sor raktári műveleteinek végrehajtása a „kötegalatti\[hely\]” foglalási irányelv esetén alkalmazandó szabályokat fogja követni.</span><span class="sxs-lookup"><span data-stu-id="24930-217">If you reserve the quantity from the **Reservation** page, no specific batch will be reserved, and the execution of warehouse operations for the line will follow the rules that are applicable under the "Batch-below\[location\]" reservation policy.</span></span>

    <span data-ttu-id="24930-218">Ez a lap általában ugyanúgy működik és ugyanúgy kell kezelni, mint az olyan cikkeknél, amelyek társított foglalási hierarchiája „kötegfölötti\[hely\]” típusú.</span><span class="sxs-lookup"><span data-stu-id="24930-218">In general, this page works and is interacted with in the same way that it works and is interacted with for items that have an associated reservation hierarchy of the "Batch-above\[location\]" type.</span></span> <span data-ttu-id="24930-219">Léteznek azonban a következő kivételek:</span><span class="sxs-lookup"><span data-stu-id="24930-219">However, the following exceptions apply:</span></span>

    - <span data-ttu-id="24930-220">A **Forrássorhoz vállalt kötegszámok** gyorslapon láthatók az illető foglalási sorhoz lefoglalt kötegszámok.</span><span class="sxs-lookup"><span data-stu-id="24930-220">The **Batch numbers committed to source line** FastTab shows the batch numbers that are reserved for the order line.</span></span> <span data-ttu-id="24930-221">A rácsban lévő kötegértékek a rendelési sor teljes teljesítési ciklusa során láthatók, ideértve a raktár feldolgozási állapotát.</span><span class="sxs-lookup"><span data-stu-id="24930-221">The batch values in the grid will be shown throughout the fulfilment cycle of the order line, including the warehouse processing stages.</span></span> <span data-ttu-id="24930-222">Ezzel szemben az **Áttekintés** gyorslapon a szabályos rendelési sor foglalása (azaz a **Hely** szintje fölötti dimenziókra elvégzett foglalás) jelenik meg a rácsban addig a pontig, amikor a raktári munka létrejön.</span><span class="sxs-lookup"><span data-stu-id="24930-222">By contrast, on the **Overview** FastTab, regular order line reservation (that is, reservation that is done for the dimensions above the **Location** level) is shown in the grid up to the point when warehouse work is created.</span></span> <span data-ttu-id="24930-223">A munkaegység ezt követően átveszi a sor foglalását, és az már nem jelenik meg a lapon.</span><span class="sxs-lookup"><span data-stu-id="24930-223">The work entity then takes over the line reservation, and the line reservation no longer appears on the page.</span></span> <span data-ttu-id="24930-224">A **Forrássorhoz vállalt kötegszámok** gyorslap biztosítja, hogy az értékesítési rendelés feldolgozója a köteg életciklusa során a számlázásig bármikor megtekintheti a vevői rendeléshez társított kötegszámokat.</span><span class="sxs-lookup"><span data-stu-id="24930-224">The **Batch numbers committed to source line** FastTab helps guarantee that the sales order processor can view the batch numbers that were committed to the customer's order at any point during its lifecycle, up through invoicing.</span></span>
    - <span data-ttu-id="24930-225">Egy konkrét köteg lefoglalásán felül a felhasználó manuálisan is kiválaszthatja a köteg meghatározott helyét és a rendszámtáblát, nem kell hagynia, hogy a rendszer automatikusan kiválassza azokat.</span><span class="sxs-lookup"><span data-stu-id="24930-225">In addition to reserving a specific batch, a user can manually select the batch's specific location and license plate instead of letting the system automatically select them.</span></span> <span data-ttu-id="24930-226">Ez a funkció a rendelésben véglegesített kötegfoglalás mechanizmus működésével kapcsolatos.</span><span class="sxs-lookup"><span data-stu-id="24930-226">This capability is related to the design of the order-committed batch reservation mechanism.</span></span> <span data-ttu-id="24930-227">Amint azt említettük, ha egy konkrét kötegszámot foglal egy cikk esetén a „kötegalatti\[hely\]” foglalási hierarchiában, a rendszernek a hely dimenzióig minden dimenziót le kell foglalnia.</span><span class="sxs-lookup"><span data-stu-id="24930-227">As was mentioned earlier, when a batch number is reserved for an item under the "Batch-below\[location\]" reservation policy, the system must reserve all dimensions up through location.</span></span> <span data-ttu-id="24930-228">Ennélfogva a raktári munka ugyanazokat a tárolási dimenziókat fogja tartalmazni, amelyeket a rendelésekkel dolgozó felhasználók lefoglaltak, és nem biztos, hogy mindig a raktári kitárolási munkához kényelmes vagy éppen lehetséges tárolási helyet mutatja.</span><span class="sxs-lookup"><span data-stu-id="24930-228">Therefore, warehouse work will carry the same storage dimensions that were reserved by the users who worked with the orders, and it might not always represent the item storage placement that is convenient, or even possible, for picking operations.</span></span> <span data-ttu-id="24930-229">Ha a rendelést feldolgozók ismerik a raktári megkötéseket, akkor megtörténhet, hogy manuálisan szeretnének bizonyos helyeket és rendszámtáblákat kiválasztani, amikor egy köteget foglalnak le.</span><span class="sxs-lookup"><span data-stu-id="24930-229">If order processors are aware of the warehouse constraints, they might want to manually select the specific locations and license plates when they reserve a batch.</span></span> <span data-ttu-id="24930-230">Ebben az esetben a felhasználónak a lap fejlécén található **Dimenziók megjelenítése** lehetőséget kell használnia, és a helyet és a rendszámtáblát fel kell vennie az **Áttekintés** gyorslap rácsára.</span><span class="sxs-lookup"><span data-stu-id="24930-230">In this case, the user must use the **Display dimensions** functionality on the page header, and must add the location and license plate in the grid on the **Overview** FastTab.</span></span>

6. <span data-ttu-id="24930-231">A **Köteg foglalása** lapon válassza ki a **B11** köteg sorát, majd válassza a **Sor foglalása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="24930-231">On the **Batch reservation** page, select the line for batch **B11**, and then select **Reserve line**.</span></span> <span data-ttu-id="24930-232">Nincs kijelölt logika a helyek és a rendszámtáblák hozzárendelésére az automatikus foglalás során.</span><span class="sxs-lookup"><span data-stu-id="24930-232">There is no designated logic for assigning locations and license plates during automatic reservation.</span></span> <span data-ttu-id="24930-233">A mennyiséget a **Foglalás** mezőbe manuálisan is beviheti.</span><span class="sxs-lookup"><span data-stu-id="24930-233">You can manually enter the quantity in the **Reservation** field.</span></span> <span data-ttu-id="24930-234">Figyelje meg, hogy a **Forrássorhoz vállalt kötegszámok** gyorslapon a **B11** köteg mellett a **Vállalt** szó látható.</span><span class="sxs-lookup"><span data-stu-id="24930-234">Notice that, on the **Batch numbers committed to source line** FastTab, batch **B11** is shown as **Committed**.</span></span>

    ![Meghatározott kötegszám vállalása egy értékesítési rendelés sorába a Köteg foglalása oldalon](media/Batch-reservation-form-with-order-committed-reservation.png)

    > [!NOTE]
    > <span data-ttu-id="24930-236">Az értékesítési rendelés sorában szereplő mennyiség lefoglalása több köteg esetén is megtehető.</span><span class="sxs-lookup"><span data-stu-id="24930-236">Reservation of the quantity on a sales order line can be done across multiple batches.</span></span> <span data-ttu-id="24930-237">Hasonlóképpen, ugyanannak a kötegnek a lefoglalása több hely és rendszámtábla esetén is megtehető (ha a rendszámtáblákat engedélyezték az illető helyekre).</span><span class="sxs-lookup"><span data-stu-id="24930-237">Likewise, reservation of the same batch can be done against multiple locations and license plates (if license plates are enabled for the locations).</span></span>
    >
    > <span data-ttu-id="24930-238">A konkrét köteg foglalási mennyisége is lehet részleges az illető minőségi rendelés sorában.</span><span class="sxs-lookup"><span data-stu-id="24930-238">Reservation of a specific batch for the quantity on a sales order line can also be partial.</span></span> <span data-ttu-id="24930-239">Például a teljes, 100 egységnyi mennyiség lefoglalható úgy, hogy egy adott köteg 20 egységre legyen vállalva, míg 80 egységet a hely és a raktár szintjén kell lefoglalni bármely, rendelkezésre álló köteghez.</span><span class="sxs-lookup"><span data-stu-id="24930-239">For example, the total quantity of 100 units can be reserved so that a specific batch is committed to 20 units, whereas 80 units are reserved at the site and warehouse levels for any available batch.</span></span> <span data-ttu-id="24930-240">Ebben az esetben a WMS két különálló munkasorral fogja kezelni a kitárolási műveleteket.</span><span class="sxs-lookup"><span data-stu-id="24930-240">In this case, the WMS will handle picking operations by using two separate work lines.</span></span>

7. <span data-ttu-id="24930-241">Kattintson a **Termékinformációk kezelése** \> **Termékek** \> **Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="24930-241">Go to **Product information management** \> **Products** \> **Released products**.</span></span> <span data-ttu-id="24930-242">Válassza ki a kívánt elemet, majd válassza a **Készletkezelés** \> **Nézet** \> **Tranzakciók** elemet.</span><span class="sxs-lookup"><span data-stu-id="24930-242">Select your item, and then select **Manage inventory** \> **View** \> **Transactions**.</span></span>

    ![Rendelésben véglegesített foglalás készlettranzakció-típusként](media/Inventory-transactions-for-order-committed-reservation.png)

8. <span data-ttu-id="24930-244">Tekintse át az értékesítési rendelés sorfoglalásához kapcsolódó készlettranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="24930-244">Review the item's inventory transactions that are related to the sales order line reservation.</span></span>

    - <span data-ttu-id="24930-245">Egy olyan tranzakció, amelyben a **Referencia** mező értéke **Értékesítési rendelés**, és a **Kiadás** mező értéke **Foglalt tényleges** értékre van állítva, a **Hely** szint fölötti készletdimenziók sorának foglalását jelenti.</span><span class="sxs-lookup"><span data-stu-id="24930-245">A transaction where the **Reference** field is set to **Sales order** and the **Issue** field is set to **Reserved physical** represents the order line reservation for the inventory dimensions above the **Location** level.</span></span> <span data-ttu-id="24930-246">A cikkek foglalási hierarchiája szerint ezek a dimenziók a telep, a raktár és a készletállapot.</span><span class="sxs-lookup"><span data-stu-id="24930-246">According to the item's inventory reservation hierarchy, those dimensions are site, warehouse, and inventory status.</span></span>
    - <span data-ttu-id="24930-247">Egy olyan tranzakció, amelyben a **Referencia** mező értéke **Rendelésben véglegesített foglalás**, és a **Kiadás** mező értéke **Foglalt tényleges** értékre van állítva, konkrét köteg és a fölötte levő összes készletdimenzió sorának foglalását jelenti.</span><span class="sxs-lookup"><span data-stu-id="24930-247">A transaction where the **Reference** field is set to **Order-committed reservation** and the **Issue** field is set to **Reserved physical** represents the order line reservation for the specific batch and all inventory dimensions above it.</span></span> <span data-ttu-id="24930-248">A cikkek foglalási hierarchiája szerint ezek a dimenziók a kötegszám és hely.</span><span class="sxs-lookup"><span data-stu-id="24930-248">According to the item's inventory reservation hierarchy, those dimensions are batch number and location.</span></span> <span data-ttu-id="24930-249">Ebben a példában a hely **Bulk-001**.</span><span class="sxs-lookup"><span data-stu-id="24930-249">In this example, the location is **Bulk-001**.</span></span>

9. <span data-ttu-id="24930-250">Az értékesítési rendelés fejlécében válassza ki a **Raktár** \> **Műveletek** \> **Kiadás raktárba** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="24930-250">On the sales order header, select **Warehouse** \> **Actions** \> **Release to warehouse**.</span></span> <span data-ttu-id="24930-251">A rendelési sor mostantól hullámos, és létrejön a terhelés és a munka.</span><span class="sxs-lookup"><span data-stu-id="24930-251">The order line is now waved, and a load and work are created.</span></span>

### <a name="review-and-process-warehouse-work-that-has-order-committed-batch-numbers"></a><span data-ttu-id="24930-252">A rendeléshez véglegesített kötegszámokkal rendelkezó raktári munka áttekintése és feldolgozása</span><span class="sxs-lookup"><span data-stu-id="24930-252">Review and process warehouse work that has order-committed batch numbers</span></span>

1. <span data-ttu-id="24930-253">Az **Értékesítési rendelés sorai** gyorslapon válassza ki a **Raktár** \> **Munka készletes adatai** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="24930-253">On the **Sales order lines** FastTab, select **Warehouse** \> **Work details**.</span></span>

    <span data-ttu-id="24930-254">Az értékesítési rendelés soraihoz lefoglalt kötegelt mennyiségek kitárolási műveletét kezelő munka jellemzői:</span><span class="sxs-lookup"><span data-stu-id="24930-254">The work that handles the picking operation for batch quantities that are committed to the sales order line has the following characteristics:</span></span>

    - <span data-ttu-id="24930-255">A munka létrehozásához a rendszer munkasablonokat használ, de nem rendelkezik hellyel kapcsolatos irányelvekkel.</span><span class="sxs-lookup"><span data-stu-id="24930-255">To create work, the system uses work templates but not location directives.</span></span> <span data-ttu-id="24930-256">A program a munkasablonokhoz meghatározott összes szabványos beállítást, például a kitárolási sorok maximális számát vagy egy konkrét mértékegységet alkalmazni fogja, hogy meghatározza, hogy mikor kell új munkát létrehozni.</span><span class="sxs-lookup"><span data-stu-id="24930-256">All the standard settings that are defined for work templates, such as a maximum number of pick lines or a specific unit of measure, will be applied to determine when new work should be created.</span></span> <span data-ttu-id="24930-257">A kitárolási helyek azonosítására szolgáló hely irányelvvel kapcsolatos szabályokat azonban nem veszi figyelembe, mivel a rendelésben véglegesített foglalás már megadja az összes készlet dimenziót.</span><span class="sxs-lookup"><span data-stu-id="24930-257">However, the rules that are associated with location directives for identifying pick locations aren't considered, because the order-committed reservation already specifies all the inventory dimensions.</span></span> <span data-ttu-id="24930-258">Ezek a készletdimenziók tartalmazzák a raktárak tárolási szintjén levő dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="24930-258">Those inventory dimensions include the dimensions at the warehouse storage level.</span></span> <span data-ttu-id="24930-259">Ezért a munka a hellyel kapcsolatos irányelvek egyeztetése nélkül örökli ezeket a dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="24930-259">Therefore, the work inherits those dimensions without having to consult location directives.</span></span>
    - <span data-ttu-id="24930-260">A kötegszám nem jelenik meg a kitárolási sorban (szemben a társított „kötegfölötti\[hely\]” foglalási hierarchiát tartalmazó cikkek esetében létrejövő munkasorokkal). Ehelyett a Kezdő kötegszám és az összes többi tárolási dimenzió látható a munkasorban a társított készlettranzakciók alapján hivatkozott munkakészlet-tranzakcióban.</span><span class="sxs-lookup"><span data-stu-id="24930-260">The batch number isn't shown on the pick line (as is the case for the work line that is created for an item that has an associated "Batch-above\[location\]" reservation hierarchy.) Instead, the "from" batch number and all other storage dimensions are shown on the work line's work inventory transaction that is referenced from the associated inventory transactions.</span></span>

        ![Raktári készlet tranzakciója olyan munkához, amely rendelésben véglegesített foglalásból származik](media/Work-inventory-transactions-for-order-committed-reservation.png)

    - <span data-ttu-id="24930-262">Miután létrehozta a munkát, a program eltávolítja a cikk azon készlettranzakcióját, amely esetén a **Referencia** mező beállítása **Rendelésben véglegesített foglalás**.</span><span class="sxs-lookup"><span data-stu-id="24930-262">After work is created, the item's inventory transaction where the **Reference** field is set to **Order-committed reservation** is removed.</span></span> <span data-ttu-id="24930-263">Az a készlettranzakció, amelyben a **Referencia** mező beállása **Munka**, most a tényleges foglalást tárolja az összes mennyiség raktárdimenziója esetén.</span><span class="sxs-lookup"><span data-stu-id="24930-263">The inventory transaction where the **Reference** field is set to **Work** now holds the physical reservation on all the quantity's inventory dimensions.</span></span>

        <span data-ttu-id="24930-264">A raktári műveletek a szokásos módon folytathatják a munka végrehajtásának kezelését.</span><span class="sxs-lookup"><span data-stu-id="24930-264">Warehouse operations can proceed to handle execution of the work in the usual manner.</span></span> <span data-ttu-id="24930-265">A mobileszközön érkező utasítások azonban arra utasítják a dolgozót, hogy jelöljön ki egy konkrét kötegszámot.</span><span class="sxs-lookup"><span data-stu-id="24930-265">However, the instructions on the mobile device will instruct the worker to pick a specific batch number.</span></span> <span data-ttu-id="24930-266">Olyan raktárakban, ahol a helyek rendszámtábla alapján vezéreltek, miután a dolgozó elér egy olyan helyet, ahol ugyanazt a köteget több rendszámtáblán tárolják, kiválaszthatja bármelyik rendszámtáblát, amelyik még nincs lefoglalva (például egy másik rendelésben véglegesített foglalást vagy olyan munkát, amely az adott típusú foglalásból származik.)</span><span class="sxs-lookup"><span data-stu-id="24930-266">In warehouse environments where locations are license plate–controlled, after a worker reaches a location that stores the same batch on multiple license plates, he or she can pick from any license plate that isn't already reserved (for example, by another order-committed reservation or work that originates from a reservation of that type.)</span></span>

        <span data-ttu-id="24930-267">Ha kiderül, hogy a munkasorban megadott helyről történő kitárolás nem praktikus, a raktári kezelők a következő műveletek egyikét alkalmazhatják az adott köteg kitárolásának egy kényelmesebb helyre történő átirányítására:</span><span class="sxs-lookup"><span data-stu-id="24930-267">If it turns out to be impractical to pick from the location that is specified on the work line, the warehouse operators can use one of the following actions to redirect picking of the specific batch from a more convenient location:</span></span>

        - <span data-ttu-id="24930-268">Szabványos **Hely felülbírálása** művelet mobileszközről (feltéve, hogy az illető raktári munkás esetén a **Kitárolási hely felülbírálásának engedélyezése** beállítása engedélyezett)</span><span class="sxs-lookup"><span data-stu-id="24930-268">The standard **Override location** action on a mobile device (provided that the warehouse worker's **Allow pick location override** setting is enabled)</span></span>
        - <span data-ttu-id="24930-269">A **Hely módosítása** művelet a **Munkalista részletei** oldalon.</span><span class="sxs-lookup"><span data-stu-id="24930-269">The **Change location** action on the **Work list details** page.</span></span> 

2. <span data-ttu-id="24930-270">Fejezze be a kitárolást és a munka elhelyezését a mobileszközön.</span><span class="sxs-lookup"><span data-stu-id="24930-270">On the mobile device, finish picking and putting the work.</span></span>

    <span data-ttu-id="24930-271">A **B11** kötegszámhoz tartozó menniységet (**10**) kitárolták az értékesítési rendelési sorra, és elhelyezték a **Baydoor** helyen.</span><span class="sxs-lookup"><span data-stu-id="24930-271">The quantity of **10** for batch number **B11** is now picked for the sales order line and put in the **Baydoor** location.</span></span> <span data-ttu-id="24930-272">Ezen a ponton készen áll a teherautóra történő berakásra, és a vevő címére történő feladásra.</span><span class="sxs-lookup"><span data-stu-id="24930-272">At this point, it's ready to be loaded onto the truck and dispatched to the customer's address.</span></span>

## <a name="exception-handling-of-warehouse-work-thas-has-order-committed-batch-numbers"></a><span data-ttu-id="24930-273">A rendeléshez véglegesített kötegszámokkal rendelkezó raktári munka kivételkezelése</span><span class="sxs-lookup"><span data-stu-id="24930-273">Exception handling of warehouse work thas has order-committed batch numbers</span></span>

<span data-ttu-id="24930-274">A rendeléshez véglegesített kötegszámokkal kitárolási raktári munkájának a kivételkezelése és műveletei ugyanazok, mint a normális munkának.</span><span class="sxs-lookup"><span data-stu-id="24930-274">Warehouse work for picking order-committed batch numbers is subject to the same standard warehouse exception handling and actions as regular work.</span></span> <span data-ttu-id="24930-275">Általában a nyitott munka vagy munkasor érvényteleníthető, megszakítható, mert egy felhasználói hely megtelt, a kitárolása lehet rövid, és egy mozgás miatt módosítható.</span><span class="sxs-lookup"><span data-stu-id="24930-275">In general, the open work or work line can be canceled, it can be interrupted because a user location is full, it can be short-picked, and it can be updated because of a movement.</span></span> <span data-ttu-id="24930-276">Hasonlóképpen a már elvégzett munka kitárolt mennyisége is csökkenthető, illetve a munka visszafordítható.</span><span class="sxs-lookup"><span data-stu-id="24930-276">Likewise, the picked quantity of work that has already been completed can be reduced, or the work can be reversed.</span></span>

<span data-ttu-id="24930-277">A program a következő kulcsfontosságú szabályt alkalmazza az összes ilyen kivételkezelési műveletre: a vevő számára lefoglalt kötegszám nem cserélhető ki egy másik kötegszámra, de a tárolási dimenziói (hely és rendszámtábla) módosíthatók akár egy a felhasználó általi manuális vagy a rendszer általi automatikus frissítéssel.</span><span class="sxs-lookup"><span data-stu-id="24930-277">The following key rule is applied to all these exception handling actions: the batch number that was reserved for the customer can never be replaced with a different batch number, but its storage dimensions (location and license plate) can be changed through either a manual update by the user or an automatic update by the system.</span></span> <span data-ttu-id="24930-278">Az automatikus frissítés a tárolási dimenziók ugyanazon véletlen hozzárendelése alapján történik, amelyeket egy konkrét köteg automatikus visszafordításakor alkalmaznak, ha nincsenek megadva tárolási dimenziók.</span><span class="sxs-lookup"><span data-stu-id="24930-278">The automatic update is based on the same random assignment of storage dimensions that applied when a specific batch was automatically reserved but no storage dimensions were specified.</span></span>

### <a name="example-scenario"></a><span data-ttu-id="24930-279">Példaforgatókönyv</span><span class="sxs-lookup"><span data-stu-id="24930-279">Example scenario</span></span>

<span data-ttu-id="24930-280">Példa erre a helyzetre olyan eset, amikor a korábban elvégzett munka kitárolását a **Kitárolt mennyiség csökkentése** funkció használatával visszavonják.</span><span class="sxs-lookup"><span data-stu-id="24930-280">An example of this scenario is a situation where previously completed work is being unpicked by using the **Reduce picked quantity** function.</span></span> <span data-ttu-id="24930-281">Ez a példa a témakör előző példájának folytatása.</span><span class="sxs-lookup"><span data-stu-id="24930-281">This example continues the previous example in this topic.</span></span>

1. <span data-ttu-id="24930-282">Lépjen a **Raktárkezelés** \> **Rakományok** \> **Aktív rakományok** elemhez.</span><span class="sxs-lookup"><span data-stu-id="24930-282">Go to **Warehouse management** \> **Loads** \> **Active loads**.</span></span>
2. <span data-ttu-id="24930-283">Válassza ki az értékesítési rendelés szállítmányával együtt létrehozott terhelést.</span><span class="sxs-lookup"><span data-stu-id="24930-283">Select the load that was created in connection with the shipment of your sales order.</span></span>
3. <span data-ttu-id="24930-284">A **Terhelési rendelés sorai** gyorslapon válassza ki a **Kitárolt mennyiség csökkentése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="24930-284">From the **Load order lines** FastTab, select **Reduce picked quantity**.</span></span>
4. <span data-ttu-id="24930-285">A **Kitárolt mennyiség csökkentése** lapon az **Áthelyezés helyre** mezőben válassza az **FL-001** elemet.</span><span class="sxs-lookup"><span data-stu-id="24930-285">On the **Reduce picked quantity** page, in the **Move to location** field, select **FL-001**.</span></span>
5. <span data-ttu-id="24930-286">Az **Áthelyezés azonosítótáblára** mezőben válassza az **LP33** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="24930-286">In the **Move to license plate** field, select **LP33**.</span></span>
6. <span data-ttu-id="24930-287">A rácsban a **Visszatárolandó készletmennyiség** mezőbe írja be a **10** értéket.</span><span class="sxs-lookup"><span data-stu-id="24930-287">In the grid, in the **Inventory quantity to unpick** field, enter **10**.</span></span>
7. <span data-ttu-id="24930-288">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="24930-288">Select **OK**.</span></span>

<span data-ttu-id="24930-289">A visszatárolási művelet eredményei:</span><span class="sxs-lookup"><span data-stu-id="24930-289">Here are the results of the unpicking action:</span></span>

- <span data-ttu-id="24930-290">A korábban lezárt munka állapotát a rendszer **Visszavonva** értékre állítja.</span><span class="sxs-lookup"><span data-stu-id="24930-290">The status of the previously closed work is set to **Canceled**.</span></span>
- <span data-ttu-id="24930-291">Új, **Készletmozgás** típusú munka jön létre a **B11** kötegszám esetén visszatárolt mennyiséghez (**10**).</span><span class="sxs-lookup"><span data-stu-id="24930-291">New work of the **Inventory movement** type is created for the unpicked quantity of **10** for batch number **B11**.</span></span> <span data-ttu-id="24930-292">Ez a munka a **Baydoor** helyről az **FL-001** helyen található **LP33** rendszámtáblához való mozgást jelzi.</span><span class="sxs-lookup"><span data-stu-id="24930-292">This work represents the movement from the **Baydoor** location to license plate **LP33** in location **FL-001**.</span></span> <span data-ttu-id="24930-293">Az rendszer átállítja az állapotot erre: **Lezárva**.</span><span class="sxs-lookup"><span data-stu-id="24930-293">The status is set to **Closed**.</span></span>
- <span data-ttu-id="24930-294">A rendszer újra lefoglalja az eredetileg megrendelt kötegszámot, és hozzárendeli a helyet és a rendszámtábla azonosítóit.</span><span class="sxs-lookup"><span data-stu-id="24930-294">The system re-reserves the batch number that was originally ordered, and assigns the location and license plate IDs.</span></span> <span data-ttu-id="24930-295">(Ez a folyamat egyenértékű a rendeléssor **Sor foglalása** funkciójának futtatásával egy adott kötegszám esetén).</span><span class="sxs-lookup"><span data-stu-id="24930-295">(This process is equivalent to running the **Reserve line** function for the order line for a given batch number).</span></span> <span data-ttu-id="24930-296">Ennek eredményekétten a **B11** köteg a **Köteg lefoglalása** oldal **Forrássorhoz vállalt kötegszámok** gyorslapján vállaltként jelenik meg, és a **Foglalás** mező a **B11** kötegszám esetén a **10** mennyiséget tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="24930-296">As a result, batch **B11** is shown as committed on the **Batch numbers committed to source line** FastTab of the **Batch reservation** page, and the **Reservation** field contains a quantity of **10** for batch number **B11**.</span></span> <span data-ttu-id="24930-297">Ezenkívül a **Hely** mező értéke **FL-001**, és a **Rendszámtábla** mező értéke **LP11**.</span><span class="sxs-lookup"><span data-stu-id="24930-297">Additionally, the **Location** field is set to **FL-001**, and the **License plate** field is set to **LP11**.</span></span> <span data-ttu-id="24930-298">(Hozzáadhatja ezeket a mezőket a rácshoz, ha nem láthatók.)</span><span class="sxs-lookup"><span data-stu-id="24930-298">(You can add these fields to the grid if they aren't visible.)</span></span>

<span data-ttu-id="24930-299">Az alábbi táblázatokban egy áttekintés látható, amely bemutatja, hogy a rendszer hogyan kezeli a konkrét raktári műveletekhez rendelt rendelésben véglegesített kötegfoglalásokat.</span><span class="sxs-lookup"><span data-stu-id="24930-299">The following tables provide an overview that shows how the system handles order-committed batch reservation for specific warehouse actions.</span></span> <span data-ttu-id="24930-300">A táblázatok tartalmának értelmezéséhez tételezzük fel, hogy minden egyes raktári művelet egy már létező raktári munka kontextusában fut, amely egy rendelésben véglegesített kötegfoglalásból származi, vagy hogy az egyes raktározási műveletek végrehajtása hatással van az adott típusú munkára.</span><span class="sxs-lookup"><span data-stu-id="24930-300">To interpret the content in the tables, assume that each warehouse action is run in the context of existing warehouse work that originates from an order-committed batch reservation, or that execution of each warehouse action affects work of that type.</span></span>

> [!NOTE]
> <span data-ttu-id="24930-301">Ezekben a táblázatokban a Kötegelt mennyiség elérhető oszlop jelzi, hogy az aktuális rendelésben véglegesített foglalások számára már lefoglalt, vagy az ugyanolyan típusú foglalásokból származó raktári munka által már lefoglalt mennyiség mellett rendelkezésre áll-e a kötegelt mennyiség.</span><span class="sxs-lookup"><span data-stu-id="24930-301">In these tables, the "Batch quantity is available" column indicates whether a batch quantity is available in addition to the quantity that is either already reserved for the current order-committed reservations or already reserved by the warehouse work that originates from reservations of that type.</span></span>

#### <a name="override-the-pick-location-on-the-open-work"></a><span data-ttu-id="24930-302">Kitárolási hely felülbírálása nyitott munkában</span><span class="sxs-lookup"><span data-stu-id="24930-302">Override the pick location on the open work</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="24930-303">Fő beállítási paraméterek</span><span class="sxs-lookup"><span data-stu-id="24930-303">Key setup parameter</span></span></th>
<th><span data-ttu-id="24930-304">Kötegelt mennyiség elérhető</span><span class="sxs-lookup"><span data-stu-id="24930-304">Batch quantity is available</span></span></th>
<th><span data-ttu-id="24930-305">Kulcsfontosságú felhasználói lépések</span><span class="sxs-lookup"><span data-stu-id="24930-305">Key user steps</span></span></th>
<th><span data-ttu-id="24930-306">Raktári munka</span><span class="sxs-lookup"><span data-stu-id="24930-306">Warehouse work</span></span></th>
<th><span data-ttu-id="24930-307">Rendelésben véglegesített kötegfoglalás</span><span class="sxs-lookup"><span data-stu-id="24930-307">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="24930-308">A <strong>Kitárolási hely felülbírálásának engedélyezése</strong> beállítás az illető munkás esetén engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="24930-308">The <strong>Allow pick location override</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="24930-309">Igen</span><span class="sxs-lookup"><span data-stu-id="24930-309">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="24930-310">Válassza ki a <strong>Hely felülbírálása</strong> menüpontot a Warehouse Mobile App (WMA) alkalmazásban a kitárolási munka megkezdésekor.</span><span class="sxs-lookup"><span data-stu-id="24930-310">Select the <strong>Override location</strong> menu item on the Warehouse Mmobile App (WMA) when you start picking work.</span></span></li>
<li><span data-ttu-id="24930-311">Válassza a <strong>Javaslás</strong> lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="24930-311">Select <strong>Suggest</strong>.</span></span></li>
<li><span data-ttu-id="24930-312">Erősítse meg, hogy a kötegelt mennyiség elérhetősége alapján új helyet javasolt.</span><span class="sxs-lookup"><span data-stu-id="24930-312">Confirm the new location that is suggested based on batch quantity availability.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="24930-313">Az aktuális munkában a következő műveletek történnek:</span><span class="sxs-lookup"><span data-stu-id="24930-313">On the current work, the following actions occur:</span></span>
<ul>
<li><span data-ttu-id="24930-314">A kitárolási hely sora módosul az új hely értékére.</span><span class="sxs-lookup"><span data-stu-id="24930-314">The location on the pick line is updated to the new location.</span></span> <span data-ttu-id="24930-315">(Ha a hely rendszámtábla által vezérelt, akkor a rendszer véletlenszerűen hozzárendel egy rendszámtáblát a munkakészlet-tranzakcióhoz, és a dolgozó kiválaszthatja bármelyik rendszámot, amelyik rendelkezik a rendelkezésre álló mennyiséggel.)</span><span class="sxs-lookup"><span data-stu-id="24930-315">(If the location is license plate–controlled, a random license plate is assigned to the work inventory transaction, and the worker can pick from any license plate that has available quantity.)</span></span></li>
<li><span data-ttu-id="24930-316">Ha a mennyiség egynél több rendszámtábla esetében is elérhető az új helyen, a rendszer az eredeti kitárolási sort szétosztja több sorra, hogy minden rendszámtáblának megfeleltesse a mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="24930-316">If the quantity is found on more than one license plate in the new location, the original pick line is split into multiple lines to match each license plate.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="24930-317">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="24930-317">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="24930-318">Nem</span><span class="sxs-lookup"><span data-stu-id="24930-318">No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="24930-319">Válassza ki a <strong>Hely felülbírálása</strong> menüpontot a WMA alkalmazásban a kitárolási munka megkezdésekor.</span><span class="sxs-lookup"><span data-stu-id="24930-319">Select the <strong>Override location</strong> menu item on the WMA when you start picking work.</span></span></li>
<li><span data-ttu-id="24930-320">Adja meg a helyet manuálisan.</span><span class="sxs-lookup"><span data-stu-id="24930-320">Manually enter a location.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="24930-321">A <strong>Hely felülbírálása</strong> művelet végrehajtása nem lehetséges.</span><span class="sxs-lookup"><span data-stu-id="24930-321">The <strong>Override location</strong> action isn't possible.</span></span> <span data-ttu-id="24930-322">Nem sikerült, és a program hibát jelez.</span><span class="sxs-lookup"><span data-stu-id="24930-322">It fails, and an error is thrown.</span></span></td>
<td><span data-ttu-id="24930-323">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="24930-323">Not applicable</span></span></td>
</tr>
</tbody>
</table>

#### <a name="full-button--split-a-work-line-because-of-overflow-on-the-user-location"></a><span data-ttu-id="24930-324">Teljes gomb – munkasor megosztása a felhasználó helyén történő túlcsordulás miatt</span><span class="sxs-lookup"><span data-stu-id="24930-324">Full button – Split a work line because of overflow on the user location</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="24930-325">Fő beállítási paraméterek</span><span class="sxs-lookup"><span data-stu-id="24930-325">Key setup parameter</span></span></th>
<th><span data-ttu-id="24930-326">Kötegelt mennyiség elérhető</span><span class="sxs-lookup"><span data-stu-id="24930-326">Batch quantity is available</span></span></th>
<th><span data-ttu-id="24930-327">Kulcsfontosságú felhasználói lépések</span><span class="sxs-lookup"><span data-stu-id="24930-327">Key user steps</span></span></th>
<th><span data-ttu-id="24930-328">Raktári munka</span><span class="sxs-lookup"><span data-stu-id="24930-328">Warehouse work</span></span></th>
<th><span data-ttu-id="24930-329">Rendelésben véglegesített kötegfoglalás</span><span class="sxs-lookup"><span data-stu-id="24930-329">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="24930-330">A <strong>Munka felosztásának engedélyezése</strong> beállítás engedélyezve van a mobileszköz menüjében.</span><span class="sxs-lookup"><span data-stu-id="24930-330">The <strong>Allow splitting of work</strong> option is enabled on the mobile device menu item.</span></span></td>
<td><span data-ttu-id="24930-331">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="24930-331">Not applicable</span></span></td>
<td>
<ol>
<li><span data-ttu-id="24930-332">Válassza ki a <strong>Teljes</strong> menüpontot a WMA alkalmazásban a kitárolási munka feldolgozásakor.</span><span class="sxs-lookup"><span data-stu-id="24930-332">Select the <strong>Full</strong> menu item on the WMA when you process picking work.</span></span></li>
<li><span data-ttu-id="24930-333">A <strong>Mennyiség kitárolása</strong> mezőbe írja be a szükséges kitárolás egy részleges mennyiségét, hogy jelezze a teljes mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="24930-333">In the <strong>Pick Qty</strong> field, enter a partial quantity of the required pick to indicate the full capacity.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="24930-334">Az aktuális munkában a mennyiséget a rendszer frissíti arra a fennmaradó mennyiségre, amelyet ki kell tárolni.</span><span class="sxs-lookup"><span data-stu-id="24930-334">On the current work, the quantity is updated to the remaining quantity that must be picked.</span></span></li>
<li><span data-ttu-id="24930-335">A kitárolt mennyiséghez új munka jön létre és zárul le.</span><span class="sxs-lookup"><span data-stu-id="24930-335">New work for the picked quantity is created and closed.</span></span></li>
</ul></td>
<td><span data-ttu-id="24930-336">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="24930-336">Not applicable</span></span></td>
</tr>
</tbody>
</table>

#### <a name="reduce-the-picked-quantity-of-completed-work-from-a-load"></a><span data-ttu-id="24930-337">A teljesített munka kitárolt mennyiségének csökkentése (rakományból)</span><span class="sxs-lookup"><span data-stu-id="24930-337">Reduce the picked quantity of completed work (from a load)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="24930-338">Fő beállítási paraméterek</span><span class="sxs-lookup"><span data-stu-id="24930-338">Key setup parameter</span></span></th>
<th><span data-ttu-id="24930-339">Kötegelt mennyiség elérhető</span><span class="sxs-lookup"><span data-stu-id="24930-339">Batch quantity is available</span></span></th>
<th><span data-ttu-id="24930-340">Kulcsfontosságú felhasználói lépések</span><span class="sxs-lookup"><span data-stu-id="24930-340">Key user steps</span></span></th>
<th><span data-ttu-id="24930-341">Raktári munka</span><span class="sxs-lookup"><span data-stu-id="24930-341">Warehouse work</span></span></th>
<th><span data-ttu-id="24930-342">Rendelésben véglegesített kötegfoglalás</span><span class="sxs-lookup"><span data-stu-id="24930-342">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="24930-343">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="24930-343">Not applicable</span></span></td>
<td><span data-ttu-id="24930-344">Igen</span><span class="sxs-lookup"><span data-stu-id="24930-344">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="24930-345">A rakomány sorából nyissa meg a <strong>Kitárolt mennyiség csökkentése</strong> oldalt.</span><span class="sxs-lookup"><span data-stu-id="24930-345">Open the <strong>Reduce picked quantity</strong> page from the load line.</span></span></li>
<li><span data-ttu-id="24930-346">Adja meg a teljes visszatárolandó mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="24930-346">Enter the full quantity to unpick.</span></span></li>
<li><span data-ttu-id="24930-347">Válassza ki az „áthelyezési” helyet/rendszámtáblát.</span><span class="sxs-lookup"><span data-stu-id="24930-347">Select a "move to" location/license plate.</span></span></li>
</ol>
</td>
<td>
<ul> 
<li><span data-ttu-id="24930-348">A rendszer érvényteleníti a rakomány sorához társított munkát.</span><span class="sxs-lookup"><span data-stu-id="24930-348">Work that is associated with the load line is canceled.</span></span></li>
<li><span data-ttu-id="24930-349">A készletmozgáshoz új munka jön létre és zárul le.</span><span class="sxs-lookup"><span data-stu-id="24930-349">New work for the inventory movement is created and closed.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="24930-350">A mennyiséget a rendszer ismét lefoglalja ugyanarra a kötegre.</span><span class="sxs-lookup"><span data-stu-id="24930-350">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="24930-351">A rendszer véletlenszerűen hozzárendel egy helyet és egy rendszámtáblát (ha a hely rendszám alapján vezérelt) ott, ahol a mennyiség rendelkezésre áll.</span><span class="sxs-lookup"><span data-stu-id="24930-351">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="24930-352">Nem</span><span class="sxs-lookup"><span data-stu-id="24930-352">No</span></span></td>
<td><span data-ttu-id="24930-353">Lásd az előző sort.</span><span class="sxs-lookup"><span data-stu-id="24930-353">See the previous row.</span></span></td>
<td><span data-ttu-id="24930-354">Lásd az előző sort.</span><span class="sxs-lookup"><span data-stu-id="24930-354">See the previous row.</span></span></td>
<td><span data-ttu-id="24930-355">A program újra lefoglalja a mennyiséget ugyanarra a kötegre, és ugyanarra a helyre és rendszámtáblára (ha a hely rendszám alapján vezérelt), amelyet a kitároláskor bevittek.</span><span class="sxs-lookup"><span data-stu-id="24930-355">The quantity is re-reserved for the same batch, and for the same location and license plate (if the location is license plate–controlled) that were entered during unpicking.</span></span></td>
</tr>
</tbody>
</table>

#### <a name="move-an-item-within-a-warehouse"></a><span data-ttu-id="24930-356">Cikkek áthelyezése raktáron belül</span><span class="sxs-lookup"><span data-stu-id="24930-356">Move an item within a warehouse</span></span>

> [!NOTE]
> <span data-ttu-id="24930-357">Ez a raktári művelet csak a **Munka-létrehozási folyamat** típusú mozgásra vonatkozik, a sablon szerinti mozgásra nem.</span><span class="sxs-lookup"><span data-stu-id="24930-357">This warehouse action is applicable only to movement of the **Work creation process** type, not to movement by template.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="24930-358">Fő beállítási paraméterek</span><span class="sxs-lookup"><span data-stu-id="24930-358">Key setup parameter</span></span></th>
<th><span data-ttu-id="24930-359">Kötegelt mennyiség elérhető</span><span class="sxs-lookup"><span data-stu-id="24930-359">Batch quantity is available</span></span></th>
<th><span data-ttu-id="24930-360">Kulcsfontosságú felhasználói lépések</span><span class="sxs-lookup"><span data-stu-id="24930-360">Key user steps</span></span></th>
<th><span data-ttu-id="24930-361">Raktári munka</span><span class="sxs-lookup"><span data-stu-id="24930-361">Warehouse work</span></span></th>
<th><span data-ttu-id="24930-362">Rendelésben véglegesített kötegfoglalás</span><span class="sxs-lookup"><span data-stu-id="24930-362">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="24930-363">A <strong>Készlet mozgatásának engedélyezése társított munkával</strong> lehetőség a dolgozó esetén engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="24930-363">The <strong>Allow movement of inventory with associated work</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="24930-364">Igen</span><span class="sxs-lookup"><span data-stu-id="24930-364">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="24930-365">Kezdje meg a mozgatást a WMA alkalmazáson.</span><span class="sxs-lookup"><span data-stu-id="24930-365">Start a movement on the WMA.</span></span></li>
<li><span data-ttu-id="24930-366">Adja meg Innen és Ide helyeket.</span><span class="sxs-lookup"><span data-stu-id="24930-366">Enter "from" and "to" locations.</span></span></li>
</ol></td>
<td>
<ul>
<li><span data-ttu-id="24930-367">Az áthelyezés által érintett összes létező munkánál a kitárolási hely módosul az új Ide helyre.</span><span class="sxs-lookup"><span data-stu-id="24930-367">On all existing work that is affected by the move, the pick location is updated to the new "to" location.</span></span></li>
<li><span data-ttu-id="24930-368">A készletmozgáshoz új munka jön létre és zárul le.</span><span class="sxs-lookup"><span data-stu-id="24930-368">New work for the inventory movement is created and closed.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="24930-369">A program az adott helyről származó mennyiségmozgatás által érintett összes meglévő foglalást ismételten lefoglalja ugyanarra a kötegre.</span><span class="sxs-lookup"><span data-stu-id="24930-369">All existing reservations that are affected by the quantity movement from the given location are re-reserved for the same batch.</span></span> <span data-ttu-id="24930-370">A rendszer véletlenszerűen hozzárendel egy helyet és egy rendszámtáblát (ha a hely rendszám alapján vezérelt) ott, ahol a mennyiség rendelkezésre áll.</span><span class="sxs-lookup"><span data-stu-id="24930-370">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="24930-371">Nem</span><span class="sxs-lookup"><span data-stu-id="24930-371">No</span></span></td>
<td><span data-ttu-id="24930-372">Lásd az előző sort.</span><span class="sxs-lookup"><span data-stu-id="24930-372">See the previous row.</span></span></td>
<td><span data-ttu-id="24930-373">Lásd az előző sort.</span><span class="sxs-lookup"><span data-stu-id="24930-373">See the previous row.</span></span></td>
<td><span data-ttu-id="24930-374">A program az adott helyről származó mennyiségmozgatás által érintett összes meglévő foglalást ismételten lefoglalja ugyanarra a kötegre, és az új Ide helyre és rendszámtáblára (ha a hely rendszám által vezérelt).</span><span class="sxs-lookup"><span data-stu-id="24930-374">All existing reservations that are affected by the quantity movement from the given location are re-reserved for the same batch, and for the new "to" location and license plate (if the location is license plate–controlled).</span></span></td>
</tr>
</tbody>
</table>

#### <a name="reverse-the-picked-quantity-of-completed-work-from-a-load-or-a-wave"></a><span data-ttu-id="24930-375">A teljesített munka kitárolt mennyiségének sztornírozása (rakományból vagy hullámból)</span><span class="sxs-lookup"><span data-stu-id="24930-375">Reverse the picked quantity of completed work (from a load or a wave)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="24930-376">Fő beállítási paraméterek</span><span class="sxs-lookup"><span data-stu-id="24930-376">Key setup parameter</span></span></th>
<th><span data-ttu-id="24930-377">Kötegelt mennyiség elérhető</span><span class="sxs-lookup"><span data-stu-id="24930-377">Batch quantity is available</span></span></th>
<th><span data-ttu-id="24930-378">Kulcsfontosságú felhasználói lépések</span><span class="sxs-lookup"><span data-stu-id="24930-378">Key user steps</span></span></th>
<th><span data-ttu-id="24930-379">Raktári munka</span><span class="sxs-lookup"><span data-stu-id="24930-379">Warehouse work</span></span></th>
<th><span data-ttu-id="24930-380">Rendelésben véglegesített kötegfoglalás</span><span class="sxs-lookup"><span data-stu-id="24930-380">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='6'><span data-ttu-id="24930-381">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="24930-381">Not applicable</span></span></td>
<td><span data-ttu-id="24930-382">Igen</span><span class="sxs-lookup"><span data-stu-id="24930-382">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="24930-383">Nyissa meg a <strong>Munka sztornírozása</strong> oldalt.</span><span class="sxs-lookup"><span data-stu-id="24930-383">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="24930-384">A kérelem oldalán válassza ki <strong>A cikkek az aktuális helyen maradnak</strong> beállítást.</span><span class="sxs-lookup"><span data-stu-id="24930-384">On the request page, select the <strong>Leave items at current location</strong> option.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="24930-385">A rendszer érvényteleníti a rakományhoz társított összes munkát.</span><span class="sxs-lookup"><span data-stu-id="24930-385">All work that is associated with the load is canceled.</span></span></td>
<td><span data-ttu-id="24930-386">A mennyiséget a rendszer ismét lefoglalja ugyanarra a kötegre.</span><span class="sxs-lookup"><span data-stu-id="24930-386">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="24930-387">A rendszer véletlenszerűen hozzárendel egy helyet és egy rendszámtáblát (ha a hely rendszám alapján vezérelt) ott, ahol a mennyiség rendelkezésre áll.</span><span class="sxs-lookup"><span data-stu-id="24930-387">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="24930-388">Nem</span><span class="sxs-lookup"><span data-stu-id="24930-388">No</span></span></td>
<td><span data-ttu-id="24930-389">Lásd az előző sort.</span><span class="sxs-lookup"><span data-stu-id="24930-389">See the previous row.</span></span></td>
<td><span data-ttu-id="24930-390">Lásd az előző sort.</span><span class="sxs-lookup"><span data-stu-id="24930-390">See the previous row.</span></span></td>
<td><span data-ttu-id="24930-391">A program újra lefoglalja a mennyiséget ugyanarra a kötegre, illetve azon helyre és rendszámtáblára esetében, ahol a mennyiség a sztornírozás után megmaradt.</span><span class="sxs-lookup"><span data-stu-id="24930-391">The quantity is re-reserved for the same batch, and for the location and license plate where the quantity was left upon reversal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="24930-392">Igen</span><span class="sxs-lookup"><span data-stu-id="24930-392">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="24930-393">Nyissa meg a <strong>Munka sztornírozása</strong> oldalt.</span><span class="sxs-lookup"><span data-stu-id="24930-393">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="24930-394">A kérelem oldalán válassza ki a <strong>Cikkek hozzárendelése ehhez a helyhez</strong> beállítást.</span><span class="sxs-lookup"><span data-stu-id="24930-394">On the request page, select the <strong>Assign items to this location</strong> option.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="24930-395">Az aktuális munkát a rendszer érvényteleníti.</span><span class="sxs-lookup"><span data-stu-id="24930-395">The current work is canceled.</span></span></li>
<li><span data-ttu-id="24930-396">A készletmozgáshoz új munka jön létre és zárul le.</span><span class="sxs-lookup"><span data-stu-id="24930-396">New work for the inventory movement is created and closed.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="24930-397">A mennyiséget a rendszer ismét lefoglalja ugyanarra a kötegre.</span><span class="sxs-lookup"><span data-stu-id="24930-397">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="24930-398">A rendszer véletlenszerűen hozzárendel egy helyet és egy rendszámtáblát (ha a hely rendszám alapján vezérelt) ott, ahol a mennyiség rendelkezésre áll.</span><span class="sxs-lookup"><span data-stu-id="24930-398">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="24930-399">Nem</span><span class="sxs-lookup"><span data-stu-id="24930-399">No</span></span></td>
<td><span data-ttu-id="24930-400">Lásd az előző sort.</span><span class="sxs-lookup"><span data-stu-id="24930-400">See the previous row.</span></span></td>
<td><span data-ttu-id="24930-401">Lásd az előző sort.</span><span class="sxs-lookup"><span data-stu-id="24930-401">See the previous row.</span></span></td>
<td><span data-ttu-id="24930-402">A program újra lefoglalja a mennyiséget ugyanarra a kötegre, illetve azon helyre és rendszámtáblára esetében, ahova a mennyiséget a sztornírozás után hozzárendelték.</span><span class="sxs-lookup"><span data-stu-id="24930-402">The quantity is re-reserved for the same batch, and for the location and license plate that the quantity was assigned to upon reversal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="24930-403">Igen/Nem</span><span class="sxs-lookup"><span data-stu-id="24930-403">Yes/No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="24930-404">Nyissa meg a <strong>Munka sztornírozása</strong> oldalt.</span><span class="sxs-lookup"><span data-stu-id="24930-404">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="24930-405">A kérelem oldalán válassza ki a <strong>Cikkek áthelyezése erre a helyre</strong> beállítást.</span><span class="sxs-lookup"><span data-stu-id="24930-405">On the request page, select the <strong>Move items to this location</strong> option.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="24930-406">A sztornírozás nem támogatott.</span><span class="sxs-lookup"><span data-stu-id="24930-406">Reversal isn't supported.</span></span></td>
<td><span data-ttu-id="24930-407">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="24930-407">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="24930-408">Igen/Nem</span><span class="sxs-lookup"><span data-stu-id="24930-408">Yes/No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="24930-409">Nyissa meg a <strong>Munka sztornírozása</strong> oldalt.</span><span class="sxs-lookup"><span data-stu-id="24930-409">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="24930-410">A kérelem oldalán válassza ki a <strong>Cikkek mozgatása helyutasítások alapján</strong> beállítást.</span><span class="sxs-lookup"><span data-stu-id="24930-410">On the request page, select the <strong>Move items based on location directives</strong> option.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="24930-411">A sztornírozás nem támogatott.</span><span class="sxs-lookup"><span data-stu-id="24930-411">Reversal isn't supported.</span></span> </td>
<td><span data-ttu-id="24930-412">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="24930-412">Not applicable</span></span></td>
</tr>
</tbody>
</table>

#### <a name="short-pick-a-quantity--register-the-quantity-as-physically-not-found-at-the-locationlicense-plate-while-you-perform-picking-work"></a><span data-ttu-id="24930-413">Egy mennyiség rövid kitárolása – a kitárolási munka végrehajtása közben a mennyiség fizikailag nem fellelhetőként történő regisztrálása a helynél/rendszámnál</span><span class="sxs-lookup"><span data-stu-id="24930-413">Short-pick a quantity – Register the quantity as physically not found at the location/license plate while you perform picking work</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="24930-414">Fő beállítási paraméterek</span><span class="sxs-lookup"><span data-stu-id="24930-414">Key setup parameter</span></span></th>
<th><span data-ttu-id="24930-415">Kötegelt mennyiség elérhető</span><span class="sxs-lookup"><span data-stu-id="24930-415">Batch quantity is available</span></span></th>
<th><span data-ttu-id="24930-416">Kulcsfontosságú felhasználói lépések</span><span class="sxs-lookup"><span data-stu-id="24930-416">Key user steps</span></span></th>
<th><span data-ttu-id="24930-417">Raktári munka</span><span class="sxs-lookup"><span data-stu-id="24930-417">Warehouse work</span></span></th>
<th><span data-ttu-id="24930-418">Rendelésben véglegesített kötegfoglalás</span><span class="sxs-lookup"><span data-stu-id="24930-418">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="24930-419">A <strong>Rövid kitárolás</strong> típusra munkakivétel ven beállítva, amelynek értelmében <strong>Cikk újbóli felosztása</strong> = <strong>Egyik sem</strong>, <strong>Készlethelyesbítés</strong> = <strong>Igen</strong>, és <strong>Foglalások eltávolítása</strong> = <strong>Nem</strong>.</span><span class="sxs-lookup"><span data-stu-id="24930-419">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>None</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>No</strong>.</span></span></td>
<td><span data-ttu-id="24930-420">Igen</span><span class="sxs-lookup"><span data-stu-id="24930-420">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="24930-421">Válassza ki a <strong>Rövid kitárolás</strong> menüpontot a WMA alkalmazásban a kitárolási munka futtatásakor.</span><span class="sxs-lookup"><span data-stu-id="24930-421">Select the <strong>Shortpick</strong> menu item on the WMA when you run picking work.</span></span></li>
<li><span data-ttu-id="24930-422">Írja be a <strong>0</strong> (nulla) értéket a <strong>Kitárolási mennyiség</strong> mezőbe.</span><span class="sxs-lookup"><span data-stu-id="24930-422">In the <strong>Pick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="24930-423">Az <strong>Ok</strong> mezőbe írja be a következőt: <strong>Nincs újrafelosztás</strong>.</span><span class="sxs-lookup"><span data-stu-id="24930-423">In the <strong>Reason</strong> field, enter <strong>No reallocation</strong>.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="24930-424">A rendszer lezárja az aktuális munkát, a kitárolt mennyiség 0 (nulla).</span><span class="sxs-lookup"><span data-stu-id="24930-424">The current work is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="24930-425">A program létrehoz egy <strong>Számlálás</strong> típusú és <strong>Eladva</strong> kibocsátási típusú, készlettranzakciót, amely a módosítást reprezentálja.</span><span class="sxs-lookup"><span data-stu-id="24930-425">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="24930-426">A mennyiséget a rendszer ismét lefoglalja ugyanarra a kötegre.</span><span class="sxs-lookup"><span data-stu-id="24930-426">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="24930-427">A rendszer véletlenszerűen hozzárendel egy helyet és egy rendszámtáblát (ha a hely rendszám alapján vezérelt) ott, ahol a mennyiség rendelkezésre áll.</span><span class="sxs-lookup"><span data-stu-id="24930-427">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="24930-428">Nem</span><span class="sxs-lookup"><span data-stu-id="24930-428">No</span></span></td>
<td><span data-ttu-id="24930-429">Lásd az előző sort.</span><span class="sxs-lookup"><span data-stu-id="24930-429">See the previous row.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="24930-430">A rövid kitárolási művelet nem sikerült, és a program hibát jelez.</span><span class="sxs-lookup"><span data-stu-id="24930-430">The short-picking action fails, and an error is thrown.</span></span></li>
<li><span data-ttu-id="24930-431">Az aktuális munka nyitva marad.</span><span class="sxs-lookup"><span data-stu-id="24930-431">The current work remains open.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="24930-432">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="24930-432">Not applicable</span></span></td>
</tr>
<tr>
<td rowspan='2'><span data-ttu-id="24930-433">A <strong>Rövid kitárolás</strong> típusra munkakivétel ven beállítva, amelynek értelmében <strong>Cikk újbóli felosztása</strong> = <strong>Egyik sem</strong>, <strong>Készlethelyesbítés</strong> = <strong>Igen</strong>, és <strong>Foglalások eltávolítása</strong> = <strong>Igen</strong>.</span><span class="sxs-lookup"><span data-stu-id="24930-433">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>None</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>Yes</strong>.</span></span></td>
<td><span data-ttu-id="24930-434">Igen</span><span class="sxs-lookup"><span data-stu-id="24930-434">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="24930-435">Válassza ki a <strong>Rövid kitárolás</strong> menüpontot a WMA alkalmazásban a kitárolási munka futtatásakor.</span><span class="sxs-lookup"><span data-stu-id="24930-435">Select the <strong>Shortpick</strong> menu item on the WMA when you run picking work.</span></span></li>
<li><span data-ttu-id="24930-436">Írja be a <strong>0</strong> (nulla) értéket a <strong>Kitárolási mennyiség</strong> mezőbe.</span><span class="sxs-lookup"><span data-stu-id="24930-436">In the <strong>Pick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="24930-437">Az <strong>Ok</strong> mezőbe írja be a következőt: <strong>Nincs újrafelosztás</strong>.</span><span class="sxs-lookup"><span data-stu-id="24930-437">In the <strong>Reason</strong> field, enter <strong>No reallocation</strong>.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="24930-438">A rendszer lezárja az aktuális munkát, a kitárolt mennyiség 0 (nulla).</span><span class="sxs-lookup"><span data-stu-id="24930-438">The current work is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="24930-439">A program létrehoz egy <strong>Számlálás</strong> típusú és <strong>Eladva</strong> kibocsátási típusú, készlettranzakciót, amely a módosítást reprezentálja.</span><span class="sxs-lookup"><span data-stu-id="24930-439">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="24930-440">A program a röviden kitárolt helyről származó mennyiségmódosítás által érintett összes meglévő foglalást ismételten lefoglalja ugyanarra a kötegre.</span><span class="sxs-lookup"><span data-stu-id="24930-440">All existing reservations that are affected by the quantity adjustment in the short-picked location are re-reserved for the same batch.</span></span> <span data-ttu-id="24930-441">A rendszer véletlenszerűen hozzárendel egy helyet és egy rendszámtáblát (ha a hely rendszám alapján vezérelt) ott, ahol a mennyiség rendelkezésre áll.</span><span class="sxs-lookup"><span data-stu-id="24930-441">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="24930-442">Nem</span><span class="sxs-lookup"><span data-stu-id="24930-442">No</span></span></td>
<td><span data-ttu-id="24930-443">Lásd az előző sort.</span><span class="sxs-lookup"><span data-stu-id="24930-443">See the previous row.</span></span></td>
<td><span data-ttu-id="24930-444">Lásd az előző sort.</span><span class="sxs-lookup"><span data-stu-id="24930-444">See the previous row.</span></span></td>
<td><span data-ttu-id="24930-445">A program a röviden kitárolt helyről származó mennyiségmódosítás által érintett összes meglévő foglalást eltávolítja.</span><span class="sxs-lookup"><span data-stu-id="24930-445">All existing reservations that are affected by the quantity adjustment in the short-picked location are removed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="24930-446">A <strong>Rövid kitárolás</strong> típusra munkakivétel ven beállítva, amelynek értelmében <strong>Cikk újbóli felosztása</strong> = <strong>Manuális</strong>, <strong>Készlethelyesbítés</strong> = <strong>Igen</strong>, és <strong>Foglalások eltávolítása</strong> = <strong>Nem/Igen</strong>.</span><span class="sxs-lookup"><span data-stu-id="24930-446">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Manual</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>No/Yes</strong>.</span></span> <span data-ttu-id="24930-447">Ezenkívül a <strong>Cikk újbóli manuális felosztásának engedélyezése</strong> beállítás a dolgozó esetén engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="24930-447">Additionally, the <strong>Allow manual item reallocation</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="24930-448">Igen</span><span class="sxs-lookup"><span data-stu-id="24930-448">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="24930-449">Válassza ki a <strong>Rövid kitárolás</strong> menüpontot a WMA alkalmazásban a kitárolási munka futtatásakor.</span><span class="sxs-lookup"><span data-stu-id="24930-449">Select the <strong>Shortpick</strong> menu item on the WMA when you run picking work.</span></span></li>
<li><span data-ttu-id="24930-450">Írja be a <strong>0</strong> (nulla) értéket a <strong>Rövid kitárolási mennyiség</strong> mezőbe.</span><span class="sxs-lookup"><span data-stu-id="24930-450">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="24930-451">Az <strong>Ok</strong> mezőben válassza ki a <strong>Rövid kitárolást manuális újrafelosztással</strong> lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="24930-451">In the <strong>Reason</strong> field, select <strong>Short Picking with manual reallocation</strong>.</span></span></li>
<li><span data-ttu-id="24930-452">Válassza ki a helyet vagy a rendszámtábla a listából.</span><span class="sxs-lookup"><span data-stu-id="24930-452">Select the location/license plate in the list.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="24930-453">Az aktuális munkában a következő műveletek történnek:</span><span class="sxs-lookup"><span data-stu-id="24930-453">On the current work, the following actions occur:</span></span>
<ul>
<li><span data-ttu-id="24930-454">A rendszer lezárja a kitárolási sort, a kitárolt mennyiség 0 (nulla).</span><span class="sxs-lookup"><span data-stu-id="24930-454">The pick line is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="24930-455">A rendszer érvényteleníti a betárolási sort.</span><span class="sxs-lookup"><span data-stu-id="24930-455">The put line is canceled.</span></span></li>
<li><span data-ttu-id="24930-456">Új kitárolási sor jön létre.</span><span class="sxs-lookup"><span data-stu-id="24930-456">A new pick line is created.</span></span> <span data-ttu-id="24930-457">Ez a felhasználó által kiválasztott helyet/rendszámtáblát használja.</span><span class="sxs-lookup"><span data-stu-id="24930-457">It uses the location/license plate that the user selected.</span></span></li>
<li><span data-ttu-id="24930-458">Új betárolási sor jön létre.</span><span class="sxs-lookup"><span data-stu-id="24930-458">A new put line is created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="24930-459">A program létrehoz egy <strong>Számlálás</strong> típusú és <strong>Eladva</strong> kibocsátási típusú, készlettranzakciót, amely a módosítást reprezentálja.</span><span class="sxs-lookup"><span data-stu-id="24930-459">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="24930-460">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="24930-460">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="24930-461">A <strong>Rövid kitárolás</strong> típusra munkakivétel ven beállítva, amelynek értelmében <strong>Cikk újbóli felosztása</strong> = <strong>Manuális</strong>, <strong>Készlethelyesbítés</strong> = <strong>Igen</strong>, és <strong>Foglalások eltávolítása</strong> = <strong>Nem</strong>.</span><span class="sxs-lookup"><span data-stu-id="24930-461">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Manual</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>No</strong>.</span></span> <span data-ttu-id="24930-462">Ezenkívül a <strong>Cikk újbóli manuális felosztásának engedélyezése</strong> beállítás a dolgozó esetén engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="24930-462">Additionally, the <strong>Allow manual item reallocation</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="24930-463">Nem</span><span class="sxs-lookup"><span data-stu-id="24930-463">No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="24930-464">Válassza ki a <strong>Rövid kitárolás</strong> menüpontot a WMA alkalmazásban a kitárolási munka futtatásakor.</span><span class="sxs-lookup"><span data-stu-id="24930-464">Select the <strong>Shortpick</strong> menu item on the WMA when you run picking work.</span></span></li>
<li><span data-ttu-id="24930-465">Írja be a <strong>0</strong> (nulla) értéket a <strong>Rövid kitárolási mennyiség</strong> mezőbe.</span><span class="sxs-lookup"><span data-stu-id="24930-465">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="24930-466">Az <strong>Ok</strong> mezőben válassza ki a <strong>Rövid kitárolást manuális újrafelosztással</strong> lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="24930-466">In the <strong>Reason</strong> field, select <strong>Short Picking with manual reallocation</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="24930-467">A rövid kitárolási művelet nem sikerült, és a program hibát jelez.</span><span class="sxs-lookup"><span data-stu-id="24930-467">The short-picking action fails, and an error is thrown.</span></span></td>
<td><span data-ttu-id="24930-468">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="24930-468">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="24930-469">A <strong>Rövid kitárolás</strong> típusra munkakivétel ven beállítva, amelynek értelmében <strong>Cikk újbóli felosztása</strong> = <strong>Manuális</strong>, <strong>Készlethelyesbítés</strong> = <strong>Igen</strong>, és <strong>Foglalások eltávolítása</strong> = <strong>Igen</strong>.</span><span class="sxs-lookup"><span data-stu-id="24930-469">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Manual</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>Yes</strong>.</span></span> <span data-ttu-id="24930-470">Ezenkívül a <strong>Cikk újbóli manuális felosztásának engedélyezése</strong> beállítás a dolgozó esetén engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="24930-470">Additionally, the <strong>Allow manual item reallocation</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="24930-471">Nem</span><span class="sxs-lookup"><span data-stu-id="24930-471">No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="24930-472">Válassza ki a <strong>Rövid kitárolás</strong> menüpontot a WMA alkalmazásban a kitárolási munka futtatásakor.</span><span class="sxs-lookup"><span data-stu-id="24930-472">Select the <strong>Shortpick</strong> menu item on the WMA when you run picking work.</span></span></li>
<li><span data-ttu-id="24930-473">Írja be a <strong>0</strong> (nulla) értéket a <strong>Rövid kitárolási mennyiség</strong> mezőbe.</span><span class="sxs-lookup"><span data-stu-id="24930-473">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="24930-474">Az <strong>Ok</strong> mezőben válassza ki a <strong>Rövid kitárolást manuális újrafelosztással</strong> lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="24930-474">In the <strong>Reason</strong> field, select <strong>Short Picking with manual reallocation</strong>.</span></span></li>
<li><span data-ttu-id="24930-475">Válassza ki a helyet vagy a rendszámtábla a listából.</span><span class="sxs-lookup"><span data-stu-id="24930-475">Select the location/license plate in the list.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="24930-476">Az aktuális munkában a következő műveletek történnek:</span><span class="sxs-lookup"><span data-stu-id="24930-476">On the current work, the following actions occur:</span></span>
<ul>
<li><span data-ttu-id="24930-477">A rendszer lezárja a kitárolási sort, a kitárolt mennyiség 0 (nulla).</span><span class="sxs-lookup"><span data-stu-id="24930-477">The pick line is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="24930-478">A rendszer érvényteleníti a betárolási sort.</span><span class="sxs-lookup"><span data-stu-id="24930-478">The put line is canceled.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="24930-479">A program létrehoz egy <strong>Számlálás</strong> típusú és <strong>Eladva</strong> kibocsátási típusú, készlettranzakciót, amely a módosítást reprezentálja.</span><span class="sxs-lookup"><span data-stu-id="24930-479">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="24930-480">A program a röviden kitárolt helyről/rendszámtáblából származó mennyiségmódosítás által érintett összes meglévő foglalást eltávolítja.</span><span class="sxs-lookup"><span data-stu-id="24930-480">All existing reservations that are affected by the quantity adjustment in the short-picked location/license plate are removed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="24930-481">A <strong>Rövid kitárolás</strong> típusra munkakivétel ven beállítva, amelynek értelmében <strong>Cikk újbóli felosztása</strong> = <strong>Autonatikus</strong>, <strong>Készlethelyesbítés</strong> = <strong>Igen/Nem</strong>, és <strong>Foglalások eltávolítása</strong> = <strong>Igen/Nem</strong>.</span><span class="sxs-lookup"><span data-stu-id="24930-481">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Automatic</strong>, <strong>Adjust inventory</strong> = <strong>Yes/No</strong>, and <strong>Remove reservations</strong> = <strong>Yes/No</strong>.</span></span></td>
<td><span data-ttu-id="24930-482">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="24930-482">Not applicable</span></span></td>
<td>
<ol>
<li><span data-ttu-id="24930-483">Válassza ki a <strong>Rövid kitárolás</strong> menüpontot a WMA alkalmazásban a kitárolási munka futtatásakor.</span><span class="sxs-lookup"><span data-stu-id="24930-483">Select the <strong>Shortpick</strong> menu item on the WMA when you run picking work.</span></span></li>
<li><span data-ttu-id="24930-484">Írja be a <strong>0</strong> (nulla) értéket a <strong>Rövid kitárolási mennyiség</strong> mezőbe.</span><span class="sxs-lookup"><span data-stu-id="24930-484">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="24930-485">Az <strong>Ok</strong> mezőben válassza ki a <strong>Rövid kitárolást automatikus újrafelosztással</strong> lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="24930-485">In the <strong>Reason</strong> field, select <strong>Short Picking with automatic reallocation</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="24930-486">Az automatikus újrafelosztással kapcsolatos rövid kitárolás nem támogatott.</span><span class="sxs-lookup"><span data-stu-id="24930-486">Short-picking that involves automatic reallocation isn't supported.</span></span></td>
<td><span data-ttu-id="24930-487">Az automatikus újrafelosztással kapcsolatos rövid kitárolás nem támogatott.</span><span class="sxs-lookup"><span data-stu-id="24930-487">Short-picking that involves automatic reallocation isn't supported.</span></span></td>
</tr>
</tbody>
</table>

#### <a name="change-the-inventory-status"></a><span data-ttu-id="24930-488">A készletállapot módosítása</span><span class="sxs-lookup"><span data-stu-id="24930-488">Change the inventory status</span></span>

> [!NOTE]
> <span data-ttu-id="24930-489">Ez a raktári művelet több belépési pontról is elvégezhető.</span><span class="sxs-lookup"><span data-stu-id="24930-489">This warehouse action can be performed from multiple entry points.</span></span> <span data-ttu-id="24930-490">Az itt látható példa a **Készletállapot-változás** műveletet használja az **Aktuális készlet hely szerint** oldalon.</span><span class="sxs-lookup"><span data-stu-id="24930-490">The example that is shown here uses **Inventory status change** action on the **On-hand by location** page.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="24930-491">Fő beállítási paraméterek</span><span class="sxs-lookup"><span data-stu-id="24930-491">Key setup parameter</span></span></th>
<th><span data-ttu-id="24930-492">Kötegelt mennyiség elérhető</span><span class="sxs-lookup"><span data-stu-id="24930-492">Batch quantity is available</span></span></th>
<th><span data-ttu-id="24930-493">Kulcsfontosságú felhasználói lépések</span><span class="sxs-lookup"><span data-stu-id="24930-493">Key user steps</span></span></th>
<th><span data-ttu-id="24930-494">Raktári munka</span><span class="sxs-lookup"><span data-stu-id="24930-494">Warehouse work</span></span></th>
<th><span data-ttu-id="24930-495">Rendelésben véglegesített kötegfoglalás</span><span class="sxs-lookup"><span data-stu-id="24930-495">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="24930-496">A <strong>Raktár</strong> lapon a <strong>Raktár</strong> rekordban a <strong>Foglalások és jelölések eltávolítása</strong> mező értéke <strong>Foglalások</strong> vagy <strong>Jelölések és foglalások</strong>.</span><span class="sxs-lookup"><span data-stu-id="24930-496">On the <strong>Warehouse</strong> tab, in the <strong>Warehouse</strong> record, the <strong>Remove reservations and markings</strong> field is set to <strong>Reservations</strong> or <strong>Markings and reservations</strong>.</span></span></td>
<td><span data-ttu-id="24930-497">Igen</span><span class="sxs-lookup"><span data-stu-id="24930-497">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="24930-498">Válasszon ki egy konkrét helyet.</span><span class="sxs-lookup"><span data-stu-id="24930-498">Select a specific location.</span></span></li>
<li><span data-ttu-id="24930-499">Válasszon ki egy sort, amely rendelkezik egy adott cikkel, hellyel és rendszámtáblábal (ha a hely rendszám alapján vezérelt).</span><span class="sxs-lookup"><span data-stu-id="24930-499">Select a line that has a specific item, location, and license plate (if the location is license plate–controlled).</span></span></li>
<li><span data-ttu-id="24930-500">Válassza a <strong>Készletállapot-változás</strong> lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="24930-500">Select <strong>Inventory status change</strong>.</span></span></li>
<li><span data-ttu-id="24930-501">Állítsa a <strong>Készlet állapota</strong> mező értékét erre: <strong>Zárolás</strong>.</span><span class="sxs-lookup"><span data-stu-id="24930-501">Set the <strong>Inventory status</strong> field to <strong>Blocking</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="24930-502">A készlet állapotának módosításai nem engedélyezettek a munkára fenntartott mennyiségek esetében.</span><span class="sxs-lookup"><span data-stu-id="24930-502">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="24930-503">A mennyiséget a rendszer ismét lefoglalja ugyanarra a kötegre.</span><span class="sxs-lookup"><span data-stu-id="24930-503">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="24930-504">A rendszer véletlenszerűen hozzárendel egy helyet és egy rendszámtáblát (ha a hely rendszám alapján vezérelt) ott, ahol a mennyiség rendelkezésre áll.</span><span class="sxs-lookup"><span data-stu-id="24930-504">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></li>
<li><span data-ttu-id="24930-505">Létrejön a készlet állapota dimenziójának módosítását jelképező két <strong>Készletállapot-változás</strong> típusú készlettranzakció.</span><span class="sxs-lookup"><span data-stu-id="24930-505">Two inventory transactions of the <strong>Inventory status change</strong> type are created to represent the change in the inventory status dimension.</span></span></li>
<li><span data-ttu-id="24930-506">Létrejön egy <strong>Készletzárolás</strong> típusú és egy <strong>Lefoglalt tényleges</strong> kiadási típusú készlettranzakció, amelyek a zárolt mennyiség lefoglalását hivatottak jelképezni.</span><span class="sxs-lookup"><span data-stu-id="24930-506">An inventory transaction of the <strong>Inventory blocking</strong> type and the <strong>Reserved physical</strong> issue type is created to represent the reservation of the blocked quantity.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="24930-507">Nem</span><span class="sxs-lookup"><span data-stu-id="24930-507">No</span></span></td>
<td><span data-ttu-id="24930-508">Lásd az előző sort.</span><span class="sxs-lookup"><span data-stu-id="24930-508">See the previous row.</span></span></td>
<td><span data-ttu-id="24930-509">A készlet állapotának módosításai nem engedélyezettek a munkára fenntartott mennyiségek esetében.</span><span class="sxs-lookup"><span data-stu-id="24930-509">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="24930-510">A foglalást a program eltávolítja.</span><span class="sxs-lookup"><span data-stu-id="24930-510">The reservation is removed.</span></span></li>
<li><span data-ttu-id="24930-511">Létrejön a készlet állapota dimenziójának módosítását jelképező két <strong>Készletállapot-változás</strong> típusú készlettranzakció.</span><span class="sxs-lookup"><span data-stu-id="24930-511">Two inventory transactions of the <strong>Inventory status change</strong> type are created to represent the change in the inventory status dimension.</span></span></li>
<li><span data-ttu-id="24930-512">Létrejön egy <strong>Készletzárolás</strong> típusú és egy <strong>Lefoglalt tényleges</strong> kiadási típusú készlettranzakció, amelyek a zárolt mennyiség lefoglalását hivatottak jelképezni.</span><span class="sxs-lookup"><span data-stu-id="24930-512">An inventory transaction of the <strong>Inventory blocking</strong> type and the <strong>Reserved physical</strong> issue type is created to represent the reservation of the blocked quantity.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td rowspan='2'><span data-ttu-id="24930-513">A <strong>Raktár</strong> lapon a <strong>Raktár</strong> rekordban a <strong>Foglalások és jelölések eltávolítása</strong> mező értéke <strong>Nincs</strong>.</span><span class="sxs-lookup"><span data-stu-id="24930-513">On the <strong>Warehouse</strong> tab, in the <strong>Warehouse</strong> record, the <strong>Remove reservations and markings</strong> field is set to <strong>None</strong>.</span></span></td>
<td><span data-ttu-id="24930-514">Igen</span><span class="sxs-lookup"><span data-stu-id="24930-514">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="24930-515">Válasszon ki egy konkrét helyet.</span><span class="sxs-lookup"><span data-stu-id="24930-515">Select a specific location.</span></span></li>
<li><span data-ttu-id="24930-516">Válasszon ki egy sort, amely rendelkezik egy adott cikkel, hellyel és rendszámtáblábal (ha a hely rendszám alapján vezérelt).</span><span class="sxs-lookup"><span data-stu-id="24930-516">Select a line that has a specific item, location, and license plate (if the location is license plate–controlled).</span></span></li>
<li><span data-ttu-id="24930-517">Válassza a <strong>Készletállapot-változás</strong> lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="24930-517">Select <strong>Inventory status change</strong>.</span></span></li>
<li><span data-ttu-id="24930-518">Állítsa a <strong>Készlet állapota</strong> mező értékét erre: <strong>Zárolás</strong>.</span><span class="sxs-lookup"><span data-stu-id="24930-518">Set the <strong>Inventory status</strong> field to <strong>Blocking</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="24930-519">A készlet állapotának módosításai nem engedélyezettek a munkára fenntartott mennyiségek esetében.</span><span class="sxs-lookup"><span data-stu-id="24930-519">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td><span data-ttu-id="24930-520">A mennyiséget a rendszer ismét lefoglalja ugyanarra a kötegre.</span><span class="sxs-lookup"><span data-stu-id="24930-520">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="24930-521">A rendszer véletlenszerűen hozzárendel egy helyet és egy rendszámtáblát (ha a hely rendszám alapján vezérelt) ott, ahol a mennyiség rendelkezésre áll.</span><span class="sxs-lookup"><span data-stu-id="24930-521">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="24930-522">Nem</span><span class="sxs-lookup"><span data-stu-id="24930-522">No</span></span></td>
<td><span data-ttu-id="24930-523">Lásd az előző sort.</span><span class="sxs-lookup"><span data-stu-id="24930-523">See the previous row.</span></span></td>
<td><span data-ttu-id="24930-524">A készlet állapotának módosításai nem engedélyezettek a munkára fenntartott mennyiségek esetében.</span><span class="sxs-lookup"><span data-stu-id="24930-524">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td><span data-ttu-id="24930-525">A készlet állapotának változtatásai nem engedélyezettek.</span><span class="sxs-lookup"><span data-stu-id="24930-525">Inventory status changes aren't allowed.</span></span></td>
</tr>
</tbody>
</table>

## <a name="limitations"></a><span data-ttu-id="24930-526">Korlátozások</span><span class="sxs-lookup"><span data-stu-id="24930-526">Limitations</span></span>

- <span data-ttu-id="24930-527">A rugalmas raktárszintű dimenziófoglalási funkció nem támogatja a következő szolgáltatásokat:</span><span class="sxs-lookup"><span data-stu-id="24930-527">The flexible warehouse-level dimension reservation functionality doesn't support the following features:</span></span>

    - <span data-ttu-id="24930-528">Tényleges súly kezelése</span><span class="sxs-lookup"><span data-stu-id="24930-528">Catch weight management</span></span>
    - <span data-ttu-id="24930-529">Tényleges negatív készlet</span><span class="sxs-lookup"><span data-stu-id="24930-529">Physical negative inventory</span></span>
    - <span data-ttu-id="24930-530">Foglalás megrendelt ellátással szemben</span><span class="sxs-lookup"><span data-stu-id="24930-530">Reservation against ordered supply</span></span>
    - <span data-ttu-id="24930-531">Átmozgatási rendelések és nyersanyag kitárolása</span><span class="sxs-lookup"><span data-stu-id="24930-531">Transfer orders and raw material picking</span></span>

- <span data-ttu-id="24930-532">A tároló utasítási egység szerinti csomagolásra vonatkozó összevonási szabályának emgvannak a korlátai.</span><span class="sxs-lookup"><span data-stu-id="24930-532">The container consolidation rule for packing by directive unit has limitations.</span></span> <span data-ttu-id="24930-533">A rendelésben véglegesített foglalások esetében azt javasoljuk, hogy ne használjon olyan tárolóépítési sablonokat, amelyek **Csomagolás utasításegység szerint** mezőjét engedélyezték.</span><span class="sxs-lookup"><span data-stu-id="24930-533">For order-committed reservations, we recommend that you not use container build templates where the **Pack by directive unit** field is enabled.</span></span> <span data-ttu-id="24930-534">A jelenlegi rendszer a raktári munka létrehozásakor nem használ helyutasításokat.</span><span class="sxs-lookup"><span data-stu-id="24930-534">In the current design, location directives aren't used when warehouse work is created.</span></span> <span data-ttu-id="24930-535">Ennek megfelelően a rendszer csak az egységszekvencia-csoport (a készletegységben) legkisebb egységét alkalmazza a tárolóra bontási hullámlépés során.</span><span class="sxs-lookup"><span data-stu-id="24930-535">Therefore, only the lowest unit in the unit sequence group (the inventory unit) is applied during the containerization wave step.</span></span>
