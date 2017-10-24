---
title: "Szállítói számlák áttekintése"
description: "Ez a cikk a szállítói számlákkal kapcsolatos általános információkat tartalmazza. A szállítói számlák a bevételezett termékekért és szolgáltatásokért cserébe igényelt kifizetés kérelmei. A szállítói számlák vonatkozhatnak már folyamatban lévő szolgáltatásokra, vagy bizonyos termékek és szolgáltatások esetén beszerzési rendeléseken is alapulhatnak."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13971
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: de536be7b0d25a1b0f662f64a31be26dbcd10c28
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="vendor-invoices-overview"></a><span data-ttu-id="d18a5-105">Szállítói számlák áttekintése</span><span class="sxs-lookup"><span data-stu-id="d18a5-105">Vendor invoices overview</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="d18a5-106">Ez a cikk a szállítói számlákkal kapcsolatos általános információkat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="d18a5-106">This article provides general information about vendor invoices.</span></span> <span data-ttu-id="d18a5-107">A szállítói számlák a bevételezett termékekért és szolgáltatásokért cserébe igényelt kifizetés kérelmei.</span><span class="sxs-lookup"><span data-stu-id="d18a5-107">Vendor invoices are requests for payment for products and services that were received.</span></span> <span data-ttu-id="d18a5-108">A szállítói számlák vonatkozhatnak már folyamatban lévő szolgáltatásokra, vagy bizonyos termékek és szolgáltatások esetén beszerzési rendeléseken is alapulhatnak.</span><span class="sxs-lookup"><span data-stu-id="d18a5-108">Vendor invoices can represent a bill for ongoing services, or they can be based on purchase orders for specific items and services.</span></span> 

<a name="vendor-invoices"></a><span data-ttu-id="d18a5-109">Szállítói számlák</span><span class="sxs-lookup"><span data-stu-id="d18a5-109">Vendor invoices</span></span>
---------------

<span data-ttu-id="d18a5-110">A beszerzési rendelés szállítói számlája egy olyan számla, amit a szállítóval egyeztetett beszerzési rendelés alapján termékek vagy szolgáltatások kézbesítésekor jön létre.</span><span class="sxs-lookup"><span data-stu-id="d18a5-110">A vendor invoice from a purchase order is an invoice that is produced when products or services are received according to a purchase order that was placed with a vendor.</span></span> <span data-ttu-id="d18a5-111">A szállítói számla fejlécet, valamint a cikkekre vagy szolgáltatásokra vonatkozó egy vagy több sort tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="d18a5-111">The vendor invoice contains a header, and one or more lines for items or services.</span></span> <span data-ttu-id="d18a5-112">A szállítói számlával a ciklus beszerzési rendelésből termékbevételezésre és szállítói számlára léphet tovább.</span><span class="sxs-lookup"><span data-stu-id="d18a5-112">A vendor invoice completes the cycle from purchase order to product receipt to vendor invoice.</span></span> 

<span data-ttu-id="d18a5-113">Annak ellenére, hogy néhány szállítói számla beszerzési rendeléshez kapcsolódik a szállítói számlák tartalmazhatnak olyan sorokat is, amelyek nem tartoznak beszerzési rendeléssorokhoz.</span><span class="sxs-lookup"><span data-stu-id="d18a5-113">Although some vendor invoices are connected to a purchase order, vendor invoices can also contain lines that don't correspond to purchase order lines.</span></span> <span data-ttu-id="d18a5-114">Olyan szállítói számlákat is létrehozhat, amelyek nincsenek hozzárendelve egyetlen beszerzési rendeléshez sem.</span><span class="sxs-lookup"><span data-stu-id="d18a5-114">You can also create vendor invoices that aren't associated with any purchase order.</span></span> <span data-ttu-id="d18a5-115">Ezek a szállítói számlák jelenthetnek folyamatban lévő szolgáltatásokat, például segédprogram számlát, amelyek nem rendelkeznek hivatkozással a beszerzési rendeléshez hozzáadáskor.</span><span class="sxs-lookup"><span data-stu-id="d18a5-115">These vendor invoices might represent ongoing services, such as a utility bill, and you don't have to reference a purchase order when you add them.</span></span> 

<span data-ttu-id="d18a5-116">Számos módja van a szállítói számla bevitelének:</span><span class="sxs-lookup"><span data-stu-id="d18a5-116">There are several ways to enter a vendor invoice:</span></span>

-   <span data-ttu-id="d18a5-117">A szállítói számlajegyzék használatával gyorsan adhat meg számlákat amelyek nem rendelkeznek hivatkozással egy beszerzési rendeléshez, így elhatárolhatja a kiadást.</span><span class="sxs-lookup"><span data-stu-id="d18a5-117">The vendor invoice register lets you quickly enter invoices that don't reference a purchase order, so that you can accrue the expense.</span></span> <span data-ttu-id="d18a5-118">Szállítói számla jóváhagyási napló használatával kiválaszthat számlákat és feladhatja azokat a szállítói egyenlegbe a könyvelt összeg sztornírozásához.</span><span class="sxs-lookup"><span data-stu-id="d18a5-118">By using the vendor invoice approval journal, you can select those invoices and post them to the vendor balance to reverse the accrual.</span></span>
-   <span data-ttu-id="d18a5-119">A szállítói számlanapló használatával gyorsan megadhat egy lépésben számlákat amelyek nem hivatkoznak a beszerzési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="d18a5-119">The vendor invoice journal lets you quickly enter invoices that don't reference a purchase order, in a single step.</span></span>
-   <span data-ttu-id="d18a5-120">A szállítói gyűjtőszámlával a szállítói számlajegyzékkel gyorsan megadhat számlákat a költség elhatárolásához.</span><span class="sxs-lookup"><span data-stu-id="d18a5-120">Together with the vendor invoice pool, the vendor invoice register lets you quickly enter invoices to accrue the expense.</span></span> <span data-ttu-id="d18a5-121">Megnyithatja a kapcsolódó beszerzési rendeléseket később a számla kiadási számlára történő feladásához.</span><span class="sxs-lookup"><span data-stu-id="d18a5-121">You can open the associated purchase orders later to post the invoice against the expense account.</span></span>
-   <span data-ttu-id="d18a5-122">A **Nyitott szállítói számlák** és a **Függőben lévő szállítói számlák** lapok lehetővé teszik a szállítói számlák létrehozását a visszaigazolt beszerzési rendelésekből.</span><span class="sxs-lookup"><span data-stu-id="d18a5-122">The **Open vendor invoices** and **Pending vendor invoices** pages let you create vendor invoices from confirmed purchase orders.</span></span>

<span data-ttu-id="d18a5-123">Az alábbi vitafórumon további információkat tudhat meg a **Nyitott szállítói számlák** vagy a **Függőben lévő szállítói számlák** oldalak használatáról, ha szállítói számlát szeretne létrehozni egy beszerzési rendelésből.</span><span class="sxs-lookup"><span data-stu-id="d18a5-123">The following discussion provide more information about how to use the **Open vendor invoices** or **Pending vendor invoices** page to create a vendor invoice from a purchase order.</span></span>

## <a name="understanding-invoice-line-quantities"></a><span data-ttu-id="d18a5-124">Számlasor mennyiségek ismertetése</span><span class="sxs-lookup"><span data-stu-id="d18a5-124">Understanding invoice line quantities</span></span>
<span data-ttu-id="d18a5-125">Ha szállítói számlát egy kapcsolódó beszerzési rendelésből nyit meg, akkor számlasorok jönnek létre a beszerzési rendelésből.</span><span class="sxs-lookup"><span data-stu-id="d18a5-125">When you open a vendor invoice from a related purchase order, invoice lines are created from the purchase order.</span></span> <span data-ttu-id="d18a5-126">Alapértelmezés szerint a termékbevételezési mennyiségből származik.</span><span class="sxs-lookup"><span data-stu-id="d18a5-126">By default, the quantities are taken from the product receipt quantity.</span></span> <span data-ttu-id="d18a5-127">Azonban a következő alapértelmezett viselkedések bármelyikét használhatja:</span><span class="sxs-lookup"><span data-stu-id="d18a5-127">However, you can use any of the following default behaviors:</span></span>

-   <span data-ttu-id="d18a5-128">**Most bevételezett mennyiség** – Használja részleges szállítmányokhoz ezt a lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d18a5-128">**Receive now quantity** – Use this option for partial shipments.</span></span> <span data-ttu-id="d18a5-129">A **Mennyiség** mezőben az alapértelmezett érték a **Fogadás** mennyiség mezőjéből származik, a beszerzési rendelésből.</span><span class="sxs-lookup"><span data-stu-id="d18a5-129">The default value in the **Quantity** field is taken from the **Receive now** quantity field on the purchase order.</span></span>
-   <span data-ttu-id="d18a5-130">**Rendelt mennyiség** – Használja teljes szállítmányokhoz ezt a lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d18a5-130">**Ordered quantity** – Use this option for complete shipments.</span></span> <span data-ttu-id="d18a5-131">A **Mennyiség** alapértelmezett értéke a beszerzési rendelés **Megrendelt** mennyiség mezőjéből származik.</span><span class="sxs-lookup"><span data-stu-id="d18a5-131">The default value in the **Quantity** field is taken from the **Ordered** quantity field on the purchase order.</span></span>
-   <span data-ttu-id="d18a5-132">**Regisztrált mennyiség** – Használja ezt a lehetőséget, ha a cikkhez regisztráció szükséges a megadott a **Cikkmodell csoportok** oldalon.</span><span class="sxs-lookup"><span data-stu-id="d18a5-132">**Registered quantity** – Use this option if the item requires registration, as specified on the **Item model groups** page.</span></span> <span data-ttu-id="d18a5-133">A **Mennyiség** mezőben szereplő alapértelmezett érték a regisztrált fizikai módosítási mennyiség.</span><span class="sxs-lookup"><span data-stu-id="d18a5-133">The default value in the **Quantity** field is the physical update quantity that has been registered.</span></span>
-   <span data-ttu-id="d18a5-134">**Termékbevételezési mennyiség** – Akkor válassza, ha a rendelés már átesett termékbevételezésen.</span><span class="sxs-lookup"><span data-stu-id="d18a5-134">**Product receipt quantity** – Use this option if a product receipt has already been received for the order.</span></span> <span data-ttu-id="d18a5-135">A **Mennyiség** mezőben szereplő alapértelmezett érték a termékbevételezéseken elérhető teljes mennyiség.</span><span class="sxs-lookup"><span data-stu-id="d18a5-135">The default value in the **Quantity** field is taken from the total quantity of available product receipts.</span></span>
-   <span data-ttu-id="d18a5-136">**Regisztrált mennyiség és szolgáltatások** – Akkor használja, ha az érkeztetési naplóban raktározott cikkek vagy a nem raktározott cikkek regisztrált mennyiségek.</span><span class="sxs-lookup"><span data-stu-id="d18a5-136">**Registered quantity and services** – Use this option if quantities have been registered in arrival journals for stocked items or items that aren't stocked.</span></span> <span data-ttu-id="d18a5-137">Ez a beállítás a szolgáltatásokat is tartalmazza, függetlenül attól, hogy regisztrálva vannak-e.</span><span class="sxs-lookup"><span data-stu-id="d18a5-137">This option also includes services, regardless of whether they are registered.</span></span>

<span data-ttu-id="d18a5-138">Ha a jogi személy számlaegyeztetést használ, akkor megtekintheti a mennyiségegyeztetés eredményeit a **Termékbevételezés mennyiségi egyeztetése** oszlopban.</span><span class="sxs-lookup"><span data-stu-id="d18a5-138">If your legal entity uses invoice matching, you can view the results of the quantity matching in the **Product receipt quantity match** column.</span></span> <span data-ttu-id="d18a5-139">Használhatja az **Egyezetés részletei** menü parancsot is az **Ellenőrzés** fülön a mennyiségegyeztetés eredményeinek megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="d18a5-139">You can also use the **Matching details** menu command on the **Review** tab to view the results of the quantity matching.</span></span>

## <a name="adding-a-line-that-wasnt-on-the-purchase-order"></a><span data-ttu-id="d18a5-140">Új sor hozzáadása amely nem volt megnyitva a beszerzési rendelésen</span><span class="sxs-lookup"><span data-stu-id="d18a5-140">Adding a line that wasn't on the purchase order</span></span>
<span data-ttu-id="d18a5-141">Hozzáadhat új sorokat, amelyek nem voltak a szállítói számla beszerzési rendelésében.</span><span class="sxs-lookup"><span data-stu-id="d18a5-141">You can add a new line that wasn't on the purchase order to the vendor invoice.</span></span> <span data-ttu-id="d18a5-142">Ki kell választania egy cikkszámot vagy beszerzési kategóriát.</span><span class="sxs-lookup"><span data-stu-id="d18a5-142">You must select an item number or procurement category.</span></span> <span data-ttu-id="d18a5-143">Ezután hozzáadhatja mennyiségeket, árakat és összegeket a sorhoz.</span><span class="sxs-lookup"><span data-stu-id="d18a5-143">You can then add quantities, prices, and amounts to the line.</span></span> <span data-ttu-id="d18a5-144">A sor csak az egyeztetési irányelvek számlaösszegeiben fog szerepelni.</span><span class="sxs-lookup"><span data-stu-id="d18a5-144">The line will be included only in matching policies for invoice totals.</span></span>

## <a name="submitting-a-vendor-invoice-for-review"></a><span data-ttu-id="d18a5-145">Szállítói számla küldése ellenőrzésre</span><span class="sxs-lookup"><span data-stu-id="d18a5-145">Submitting a vendor invoice for review</span></span>
<span data-ttu-id="d18a5-146">A szervezet használhat meghatározott munkafolyamatokat a szállítói számlák ellenőrzési eljárásához.</span><span class="sxs-lookup"><span data-stu-id="d18a5-146">Your organization might use workflows to manage the review process for vendor invoices.</span></span> <span data-ttu-id="d18a5-147">A munkafolyamat előírhatja a számlafejléc, a számlasor vagy mindkettő ellenőrzését.</span><span class="sxs-lookup"><span data-stu-id="d18a5-147">Workflow review can be required for the invoice header, the invoice line, or both.</span></span> <span data-ttu-id="d18a5-148">A munkafolyamat vezérlőelemei a fejlécre vagy a sorra vonatkoznak, attól függően, hogy hol van a fókusz, amikor a vezérlőelemre kattint.</span><span class="sxs-lookup"><span data-stu-id="d18a5-148">The workflow controls apply to the header or the line, depending on where the focus is when you click the control.</span></span> <span data-ttu-id="d18a5-149">A **Feladás** gomb helyett a **Küldés** gomb jelenik meg, amelyet használhat szállítói számla feladásához az ellenőrzési folyamat során.</span><span class="sxs-lookup"><span data-stu-id="d18a5-149">Instead of the **Post** button, you will see a **Submit** button that you can use to send the vendor invoice through the review process.</span></span>

## <a name="matching-vendor-invoices-to-product-receipts"></a><span data-ttu-id="d18a5-150">Szállítói számlák egyeztetése a termékbevételezésekkel</span><span class="sxs-lookup"><span data-stu-id="d18a5-150">Matching vendor invoices to product receipts</span></span>
<span data-ttu-id="d18a5-151">Megadhatja és mentheti a szállítói számlák adatait, és a számlasorokat egyeztetheti a termékbevételezési sorokkal.</span><span class="sxs-lookup"><span data-stu-id="d18a5-151">You can enter and save information for vendor invoices, and you can match invoice lines to product receipt lines.</span></span> <span data-ttu-id="d18a5-152">Részleges mennyiségeket is egyeztethet a soroknál.</span><span class="sxs-lookup"><span data-stu-id="d18a5-152">You can also match partial quantities for a line.</span></span> 

<span data-ttu-id="d18a5-153">Szállítói számlát létrehozhat a termékbevételezési sorokban az adott napig bevételezett cikkek alapján akkor is, ha még nem érkezett meg egy meghatározott beszerzési rendelés összes cikke.</span><span class="sxs-lookup"><span data-stu-id="d18a5-153">You can create a vendor invoice that is based on the product receipt line items that have been received to date, even if all the items for a particular purchase order haven't yet been received.</span></span> <span data-ttu-id="d18a5-154">Például ezt olyankor teheti meg, amikor egy szállító havonta egy számlát küld, amely a szállító által az adott hónapban kézbesített összes szállítást fedezi.</span><span class="sxs-lookup"><span data-stu-id="d18a5-154">For example, you might use this option if a vendor sends one invoice per month that covers all the deliveries that the vendor shipped during that month.</span></span> <span data-ttu-id="d18a5-155">Mindegyik termékbevételezés a beszerzési rendelésen szereplő cikkek egy-egy részleges vagy teljes szállításának felel meg.</span><span class="sxs-lookup"><span data-stu-id="d18a5-155">Each product receipt represents a partial or complete delivery of the items on the purchase order.</span></span> 

<span data-ttu-id="d18a5-156">A számla feladásakor a **Számlahátralék** mennyisége minden cikkre vonatkozóan frissül a kiválasztott termékbevételezéseken fogadott mennyiségekkel.</span><span class="sxs-lookup"><span data-stu-id="d18a5-156">When you post the invoice, the **Invoice remainder** quantity for each item is updated with the total of the received quantities from the selected product receipts.</span></span> <span data-ttu-id="d18a5-157">Ha a beszerzési rendelésen található összes cikknél 0 (nulla) a **Számlahátralék** és a **Fennmaradó szállítása** értéke, a beszerzési rendelés **Számlázott** állapotú lesz.</span><span class="sxs-lookup"><span data-stu-id="d18a5-157">If both the **Invoice remainder** quantity and the **Deliver remainder** quantity for all items on the purchase order are 0 (zero), the status of the purchase order is changed to **Invoiced**.</span></span> <span data-ttu-id="d18a5-158">Ha a számlához tartozó **Számlahátralék** mennyisége nem 0, akkor a beszerzési rendelés állapota változatlan marad, és további számlákat lehet hozzá rögzíteni.</span><span class="sxs-lookup"><span data-stu-id="d18a5-158">If the **Invoice remainder** quantity isn't 0, the status of the purchase order remains unchanged, and additional invoices can be entered for it.</span></span>

<span data-ttu-id="d18a5-159">Ez a lehetőség azt feltételezi, hogy legalább egy termékbevételezést feladtak a beszerzési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="d18a5-159">This option assumes that at least one product receipt has been posted for the purchase order.</span></span> <span data-ttu-id="d18a5-160">A szállítói számla ezeken a termékbevételezéseken alapul, és azok mennyiségeit tükrözi.</span><span class="sxs-lookup"><span data-stu-id="d18a5-160">The vendor invoice is based on these product receipts and reflects the quantities from them.</span></span> <span data-ttu-id="d18a5-161">A számla pénzügyi adatai a számla feladásakor megadott információkon alapulnak.</span><span class="sxs-lookup"><span data-stu-id="d18a5-161">The financial information for the invoice is based on the information that is entered when you post the invoice.</span></span>

<span data-ttu-id="d18a5-162">További informáiók: [A szállítói számlák rögzítése és összevetése a bevételezett mennyiséggel](../accounts-receivable/tasks/record-vendor-invoice-match-against-received-quantity.md)</span><span class="sxs-lookup"><span data-stu-id="d18a5-162">For more information, see [Record vendor invoice and match against received quantity](../accounts-receivable/tasks/record-vendor-invoice-match-against-received-quantity.md).</span></span>

## <a name="working-with-multiple-invoices"></a><span data-ttu-id="d18a5-163">Több számla használata</span><span class="sxs-lookup"><span data-stu-id="d18a5-163">Working with multiple invoices</span></span>

<span data-ttu-id="d18a5-164">Dolgozhat egyszerre több számlával, és fel is adhatja azokat egyszerre.</span><span class="sxs-lookup"><span data-stu-id="d18a5-164">You can work with multiple invoices at the same time and post them all at the same time.</span></span> <span data-ttu-id="d18a5-165">Ha több számlát kell létrehoznia, akkor használja a **Függőben lévő szállítói számlák** oldalt.</span><span class="sxs-lookup"><span data-stu-id="d18a5-165">If you must create multiple invoices, use the **Pending vendor invoices** page.</span></span> <span data-ttu-id="d18a5-166">Ha több szállítói számlát kell feladni és nyomtatni, akkor használja a számla-jóváhagyási napló oldal.t</span><span class="sxs-lookup"><span data-stu-id="d18a5-166">If you must post and print multiple vendor invoices, use the invoice approval journal page.</span></span> <span data-ttu-id="d18a5-167">Ha számla-jóváhagyási naplót használ, legalább egy termékbevételezést feladtak, és a beszerzési rendelés számláját fel kell adni a számlajegyzékbe.</span><span class="sxs-lookup"><span data-stu-id="d18a5-167">If you're using the invoice approval journal, at least one product receipt must be posted for the purchase order, and an invoice for the purchase order must be posted in an invoice register.</span></span> <span data-ttu-id="d18a5-168">A számla pénzügyi adatai a számlajegyzékbe feladott számláról származnak.</span><span class="sxs-lookup"><span data-stu-id="d18a5-168">The financial information for the invoice comes from the invoice that was posted in the register.</span></span>


<span data-ttu-id="d18a5-169">További tudnivalók:</span><span class="sxs-lookup"><span data-stu-id="d18a5-169">For more information see:</span></span>

 - [<span data-ttu-id="d18a5-170">Szállítói számla irányelveinek beállítása</span><span class="sxs-lookup"><span data-stu-id="d18a5-170">Set up vendor invoice policies</span></span>](../accounts-receivable/tasks/set-up-vendor-invoice-policies.md) 

 - [<span data-ttu-id="d18a5-171">Fő számlaadatok a kötelezettségekbe egy szállítói számla használatával</span><span class="sxs-lookup"><span data-stu-id="d18a5-171">Key invoice data into accounts payable using a vendor invoice</span></span>](tasks/key-invoice-data-ap-system-vendor-invoice.md)
 
 - [<span data-ttu-id="d18a5-172">Fő számlaadatok a kötelezettségekbe jóváhagyási napló használatával</span><span class="sxs-lookup"><span data-stu-id="d18a5-172">Key invoice data into accounts payable using an approval journal</span></span>](tasks/key-invoice-data-into-ap-system-approval-journal.md)
  
 - [<span data-ttu-id="d18a5-173">A legfontosabb számlaadatok a kötelezettségkezelési rendszerbe számlagyűjtő használatával</span><span class="sxs-lookup"><span data-stu-id="d18a5-173">Key invoice data into the AP system using invoice pool</span></span>](tasks/key-invoice-data-into-ap-system-invoice-pool.md)
 
 - [<span data-ttu-id="d18a5-174">Szállítói számla rögzítése a számlanaplóban</span><span class="sxs-lookup"><span data-stu-id="d18a5-174">Record a vendor invoice in the invoice journal</span></span>](tasks/record-vendor-invoice-invoice-journal.md)

