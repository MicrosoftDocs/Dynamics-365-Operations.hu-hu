---
title: Árak, engedmények, szerződések és visszatérítések hibaelhárítása
description: Ez a témakör azt mutatja be, hogyan lehet javítani az árak, engedmények, megállapodások és visszatérítések használata során felmerülő problémákat.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: b83490acdc58c9ee0ffae9480f69a99477913843
ms.sourcegitcommit: 91e101d7a51a8b63bd196ec80e9224e5e6e6fc95
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/22/2020
ms.locfileid: "3834369"
---
# <a name="troubleshoot-prices-discounts-agreements-and-rebates"></a><span data-ttu-id="4b9e0-103">Árak, engedmények, szerződések és visszatérítések hibaelhárítása</span><span class="sxs-lookup"><span data-stu-id="4b9e0-103">Troubleshoot prices, discounts, agreements, and rebates</span></span>

<span data-ttu-id="4b9e0-104">Ez a témakör azt mutatja be, hogyan lehet javítani az árak, engedmények, megállapodások és visszatérítések használata során felmerülő problémákat.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-104">This topic describes how to fix issues that you might encounter while you work with prices, discounts, agreements, and rebates.</span></span>

## <a name="i-cant-link-a-purchase-agreement-to-a-purchase-order-line-after-the-purchase-order-is-created"></a><span data-ttu-id="4b9e0-105">A beszerzési rendelés létrehozása után nem lehet beszerzési szerződést kapcsolni egy beszerzési rendelés sorához.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-105">I can't link a purchase agreement to a purchase order line after the purchase order is created.</span></span>

<span data-ttu-id="4b9e0-106">A beszerzési rendelés létrehozása során lehet beszerzési szerződést kapcsolni a beszerzési rendelés egy sorához.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-106">A purchase agreement must be associated with a purchase order when the purchase order is created.</span></span> <span data-ttu-id="4b9e0-107">Ellenkező esetben a beszerzésirendelés-sorok nem társíthatók a beszerzési szerződés soraival.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-107">Otherwise, purchase order lines can't be associated with purchase agreement lines.</span></span>

## <a name="what-check-triggers-the-update-prices-and-discounts-entered-manually-or-external-document-message"></a><span data-ttu-id="4b9e0-108">Milyen ellenőrzés váltja ki az „Manuálisan megadott árak és engedmények frissítése vagy külső dokumentum” üzenetet?</span><span class="sxs-lookup"><span data-stu-id="4b9e0-108">What check triggers the "Update prices and discounts entered manually or external document" message?</span></span>

<span data-ttu-id="4b9e0-109">A szállítási dátum módosításakor a következő üzenet jelenik meg: „Manuálisan megadott árak és engedmények frissítése vagy külső dokumentum”.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-109">When you change the shipping date, you might receive a message that states, "Update prices and discounts entered manually or external document."</span></span> <span data-ttu-id="4b9e0-110">Ez az üzenet akkor jelenik meg, ha a szállítási dátum megváltozik, egy másik kereskedelmi vagy értékesítési szerződés lesz meghívva, és ez árváltozást okozhat.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-110">You receive this message because, if the shipping date is changed, a different trade or sales agreement might be triggered and cause a price change.</span></span> <span data-ttu-id="4b9e0-111">A szállítási dátum módosítása hatással lehet a raktári ütemezésekre és más kapcsolódó információkra is.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-111">A change to the shipping date can also affect warehouse schedules and other related information.</span></span>

<span data-ttu-id="4b9e0-112">Az üzenet akkor jelenik meg, ha bármely dátum vagy más paraméter módosul.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-112">The message is triggered whenever any of the dates or some other parameters are changed.</span></span> <span data-ttu-id="4b9e0-113">Az üzenet célja, hogy biztosan tisztában legyen azzal, a változtatások miatt előfordulhat az árak módosulása.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-113">The purpose of the message is to make sure that you're aware of price changes that can occur because of those changes.</span></span>

<span data-ttu-id="4b9e0-114">Az üzenet a kereskedelmi megállapodás értékelése (TAE) figyelmeztetés.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-114">The message is the trade agreement evaluation (TAE) prompt.</span></span> <span data-ttu-id="4b9e0-115">A teljes leírást lásd: [Kereskedelmi szerződés értékelési irányelvei](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper).</span><span class="sxs-lookup"><span data-stu-id="4b9e0-115">For a full description, see [Trade agreement evaluation policies](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper).</span></span>

## <a name="a-purchase-order-receipt-doesnt-include-all-charges"></a><span data-ttu-id="4b9e0-116">A beszerzési rendelés nyugtája nem tartalmaz minden költséget.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-116">A purchase order receipt doesn't include all charges.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="4b9e0-117">A hiba reprodukálása</span><span class="sxs-lookup"><span data-stu-id="4b9e0-117">Reproduce the issue</span></span>

<span data-ttu-id="4b9e0-118">A következő eljárás bemutatja a hiba reprodukálásának egyik módját.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-118">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="4b9e0-119">A **Beszerzés és forrás paraméterei lap** **Szállítás** lapján győződjön meg arról, hogy a **Díjak generálása terméknyugtán** beállítás *Igen* értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-119">On the **Procurement and sourcing parameters** page, on the **Delivery** tab, make sure that the **Generate charges on product receipt** option is set to *Yes*.</span></span>
1. <span data-ttu-id="4b9e0-120">Hozzon létre egy költségeket tartalmazó beszerzési rendelést.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-120">Create a purchase order that includes charges.</span></span>
1. <span data-ttu-id="4b9e0-121">Erősítse meg a beszerzési rendelést.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-121">Confirm the purchase order.</span></span>
1. <span data-ttu-id="4b9e0-122">Fogadja a beszerzési rendelést.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-122">Receive the purchase order.</span></span>
1. <span data-ttu-id="4b9e0-123">Tekintse meg a nyugta összegét, és hasonlítsa össze a várt összeggel.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-123">Look at the receipt total, and compare it to the expected total.</span></span>
1. <span data-ttu-id="4b9e0-124">Figyelje meg, hogy nem minden költség szerepel a beszerzési rendelés nyugtáján.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-124">Notice that not all the charges are included on the purchase order receipt.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="4b9e0-125">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="4b9e0-125">Issue resolution</span></span>

<span data-ttu-id="4b9e0-126">A megoldás a vegyes költségek beállításának módjától függ.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-126">The resolution depends on the way that the miscellaneous charges have been set up.</span></span> <span data-ttu-id="4b9e0-127">A vegyes költségnek az igények teljesítése céljából történő beállításával kapcsolatos további tudnivalókat lásd a következő blogbejegyzésben: a [Vegyes költségek feladása terméknyugta időpontjában](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).</span><span class="sxs-lookup"><span data-stu-id="4b9e0-127">For information about how to set up miscellaneous charges to meet your requirements, see the following blog post: [Post misc. charges at time of product receipt](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).</span></span>

## <a name="trade-agreement-prices-and-discounts-arent-applied-on-sales-or-purchase-order-lines-that-are-imported-through-data-management"></a><span data-ttu-id="4b9e0-128">A kereskedelmi megállapodási árak és engedmények nincsenek alkalmazva az adatkezeléssel importált értékesítési és beszerzési rendelési sorokra.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-128">Trade agreement prices and discounts aren't applied on sales or purchase order lines that are imported through data management.</span></span>

### <a name="issue-description"></a><span data-ttu-id="4b9e0-129">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="4b9e0-129">Issue description</span></span>

<span data-ttu-id="4b9e0-130">Az értékesítési vagy beszerzésirendelés-sorokra vonatkozó kereskedelmi megállapodások nincsenek alkalmazva az adatkezeléssel importált értékesítési és beszerzési rendelési sorokra.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-130">Trade agreements that are applicable to sales or purchase order lines aren't applied on lines that are imported through data management.</span></span> <span data-ttu-id="4b9e0-131">Ugyanezek a kereskedelmi megállapodások azonban olyan értékesítési vagy beszerzésirendelés-sorokra vonatkoznak, amelyek manuálisan jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-131">However, the same trade agreements are applied on sales or purchase order lines that are manually created.</span></span>

### <a name="reason-for-the-issue"></a><span data-ttu-id="4b9e0-132">A probléma oka</span><span class="sxs-lookup"><span data-stu-id="4b9e0-132">Reason for the issue</span></span>

<span data-ttu-id="4b9e0-133">Ha az adatkezelésen keresztül importált beszerzésirendelés-sorok már tartalmazzák az árak adatait, akkor a kereskedelmi megállapodás nem lesz újraértékelve ezekhez a sorokhoz.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-133">If purchase order lines that are imported via data management already include price information, the trade agreement won't be reevaluated for those lines.</span></span> <span data-ttu-id="4b9e0-134">Ha például a **Sorengedmény százaléka** vagy az ár-és az engedményértékeket bármelyike egy sorhoz be van állítva, akkor a kereskedelmi megállapodásokat nem keresi a program ehhez a sorhoz.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-134">For example, if **Line discount percentage** or any of the price and discount values is set for a line, then trade agreements will not be looked up for that line.</span></span>

### <a name="issue-workaround"></a><span data-ttu-id="4b9e0-135">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="4b9e0-135">Issue workaround</span></span>

<span data-ttu-id="4b9e0-136">Ez a viselkedés várható, és az értékesítési rendelésekhez és a beszerzési rendelésekhez hasonló.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-136">This behavior is expected, and is similar for both sales orders and purchase orders.</span></span>

<span data-ttu-id="4b9e0-137">Megoldásként importálja a beszerzési rendelés sorait az áradatok megadása nélkül.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-137">As a workaround, import the purchase order lines without setting any price information.</span></span> <span data-ttu-id="4b9e0-138">A kereskedelmi megállapodások ekkor alkalmazva lesznek, és a beszerzési rendelési sorok a meghatározott kereskedelmi megállapodások alapján lesznek frissítve.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-138">The trade agreements will then be applied, and the purchase order lines will be updated based on the defined trade agreements.</span></span>

## <a name="a-vendor-rebate-isnt-cumulated-based-on-invoices"></a><span data-ttu-id="4b9e0-139">A szállítói visszatérítés nem halmozott a számlák alapján.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-139">A vendor rebate isn't cumulated based on invoices.</span></span>

### <a name="issue-description"></a><span data-ttu-id="4b9e0-140">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="4b9e0-140">Issue description</span></span>

<span data-ttu-id="4b9e0-141">Ha a feladott számlák különböző esedékességi dátummal rendelkeznek, akkor ezek a számlák nem tükröződnek a belőlük létrejövő szállítói visszatérítésekben.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-141">If invoices that are posted have different due dates, those invoices aren't reflected in vendor rebates that are generated from them.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="4b9e0-142">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="4b9e0-142">Issue resolution</span></span>

<span data-ttu-id="4b9e0-143">Tervezése alapján a program nem veszi figyelembe a határidőt a szállítói visszatérítés kiszámításakor.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-143">By design, the due date isn't considered when the vendor rebate is calculated.</span></span> <span data-ttu-id="4b9e0-144">Fontolja meg a rendszer testreszabását úgy, hogy a fizetési határidő és a számlához való viszonya jobban látható legyen a szállító tényleges visszatérítése kapcsán.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-144">Consider customizing the system so that the due date and the relation to the invoice are more apparent with respect to the actual vendor rebate.</span></span>

## <a name="unit-prices-on-purchase-orders-arent-calculated-based-on-the-unit-conversion"></a><span data-ttu-id="4b9e0-145">A beszerzési rendeléseken szereplő egységárak számítása nem a mértékegység-átváltás alapján történik.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-145">Unit prices on purchase orders aren't calculated based on the unit conversion.</span></span>

### <a name="issue-description"></a><span data-ttu-id="4b9e0-146">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="4b9e0-146">Issue description</span></span>

<span data-ttu-id="4b9e0-147">Amikor egy egység megváltozik egy beszerzési rendelésen, a kereskedelmi megállapodás árai nem lesznek újraszámítva a mértékegység-átváltás definíciói szerint.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-147">When a unit is changed on a purchase order, trade agreement prices aren't recalculated according to unit conversion definitions.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="4b9e0-148">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="4b9e0-148">Issue resolution</span></span>

<span data-ttu-id="4b9e0-149">Az árak mindig a kereskedelmi megállapodásokból (vagy a rendszerben szereplő egyéb áraktól, például az értékesítési megállapodások vagy a cikkek áraiból) vannak lekérve, és egy mértékegységhez vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-149">Prices are always obtained from trade agreements (or other price settings in the system, such as sales agreements or item prices), and they are set for a unit.</span></span>

<span data-ttu-id="4b9e0-150">Ha egy rendelési sorban módosul az egység, a rendszer az új árat keres az egységhez, és ezt az árat alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-150">If the unit is changed on an order line, the system looks for a price for the new unit and applies that price.</span></span> <span data-ttu-id="4b9e0-151">Ha nem talál árat a egységhez, akkor a rendszer nem alkalmaz árat.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-151">If no price is found for the unit, the system doesn't apply a price.</span></span> <span data-ttu-id="4b9e0-152">A mértékegység-átalakítás nem használható az ár másik egységbe történő átszámítására.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-152">The unit conversion can't be used to recalculate the price into another unit.</span></span> <span data-ttu-id="4b9e0-153">Elméletileg a tíz dobozt tartalmazó egység ára nem biztos, hogy tízszerese egy doboz árának.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-153">Theoretically, the price for one box of ten might not equal ten times the price of one box.</span></span>

### <a name="issue-workaround"></a><span data-ttu-id="4b9e0-154">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="4b9e0-154">Issue workaround</span></span>

<span data-ttu-id="4b9e0-155">A probléma megkerülésének egyik módja annak ellenőrzése, hogy vannak-e kereskedelmi megállapodások azokhoz az egységekhez, amelyek várhatóan használva lesznek a cikk rendelési soraihoz.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-155">One way to work around this issue is to make sure that there are trade agreements for the units that you expect will be used on order lines for the item.</span></span>

## <a name="currency-conversion-issues-occur-with-trade-agreements"></a><span data-ttu-id="4b9e0-156">Pénznem-átváltási problémák tapasztalhatók a kereskedelmi megállapodásoknál.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-156">Currency conversion issues occur with trade agreements.</span></span>

<span data-ttu-id="4b9e0-157">A kereskedelmi megállapodás árait nem számítja újra a program a beszerzési rendelés pénzneme használatával, ha az eltérő.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-157">Trade agreement prices aren't recalculated according to the currency when the currency differs on a purchase order.</span></span>

<span data-ttu-id="4b9e0-158">Az *Általános pénznem* funkció lehetővé teszi az árak és engedmények definiálását egy pénznemben.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-158">The *Generic currency* feature lets you define prices and discounts in only one currency.</span></span> <span data-ttu-id="4b9e0-159">Ezt követően a szükséges módon konvertálhat más pénznemekre.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-159">You can then convert to other currencies as you require.</span></span> <span data-ttu-id="4b9e0-160">Ezenkívül az átváltás után a funkcióval automatikusan alkalmazhat intelligens kerekítést.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-160">Furthermore, after the conversion is done, the feature can automatically apply smart rounding.</span></span>

## <a name="when-i-open-the-purchase-agreement-page-in-a-line-view-mode-i-cant-personalize-the-page-by-adding-the-price-unit-field-in-the-overview-of-the-line"></a><span data-ttu-id="4b9e0-161">Amikor a Beszerzési szerződés lapját egy sor nézet módban nyitom meg, akkor nem lehet személyre szabni a lapot az Egységár mező hozzáadásával a sor áttekintésében.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-161">When I open the Purchase agreement page in a line view mode, I can't personalize the page by adding the Price unit field in the overview of the line.</span></span>

<span data-ttu-id="4b9e0-162">A szerződési keretrendszer néhány megosztott mezője nem vonható be a személyre szabásokba.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-162">Some shared fields in the agreement framework can't be included in personalizations.</span></span> <span data-ttu-id="4b9e0-163">Ez a korlátozás az alkalmazott adatmodell miatt következik be.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-163">This limitation occurs because of the data model that is implemented.</span></span> <span data-ttu-id="4b9e0-164">Ezért nem lehet személyre szabni az **Egységár** mezőt.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-164">Therefore, you can't personalize the **Price unit** field.</span></span>

## <a name="the-maximum-limit-from-a-purchase-agreement-isnt-effective-on-a-purchase-requisition"></a><span data-ttu-id="4b9e0-165">A beszerzési szerződésből származó maximális határérték nem érvényes egy beszerzési igénylésre.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-165">The maximum limit from a purchase agreement isn't effective on a purchase requisition.</span></span>

### <a name="issue-description"></a><span data-ttu-id="4b9e0-166">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="4b9e0-166">Issue description</span></span>

<span data-ttu-id="4b9e0-167">Amikor egy beszerzési igénylés egy beszerzési szerződéshez van kapcsolva, a beszerzési szerződés maximálisan megengedett határértéke nem érvényes a beszerzési igénylésre.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-167">When a purchase requisition is linked to a purchase agreement, the maximum limit from the purchase agreement isn't effective on the purchase requisition.</span></span> <span data-ttu-id="4b9e0-168">A program helyesen írja be az alapértelmezett árat, de a beszerzési megállapodásban szereplő maximális korlátozásnál többet is lehetséges rendelni a beszerzési igénylésben.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-168">The default price information is correctly entered, but more than the maximum limit from the purchase agreement can be ordered in the purchase requisition.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="4b9e0-169">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="4b9e0-169">Issue resolution</span></span>

<span data-ttu-id="4b9e0-170">Ez a viselkedés várható.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-170">This behavior is expected.</span></span> <span data-ttu-id="4b9e0-171">Mivel az igényléseket nem mindig hagyják jóvá, egy mennyiséget vagy összeget nem szabad lefoglalni a beszerzési szerződésen.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-171">Because requisitions aren't always approved, a quantity or amount should not be reserved on the purchase agreement.</span></span> <span data-ttu-id="4b9e0-172">Ennélfogva nem fogja elérni a beszerzési szerződés maximális határértékét.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-172">Therefore, you won't meet the maximum limit from the purchase agreement.</span></span>

## <a name="trade-agreements-can-be-created-from-rejected-rfqs-therefore-the-system-doesnt-prevent-trade-agreement-journals-from-being-created-if-the-rfq-line-hasnt-been-accepted"></a><span data-ttu-id="4b9e0-173">A kereskedelmi megállapodásokat elutasított ajánlatkérésből létre lehet hozni.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-173">Trade agreements can be created from rejected RFQs.</span></span> <span data-ttu-id="4b9e0-174">Ezért a rendszer nem akadályozza meg a kereskedelmi megállapodási naplók létrehozását, ha a ajánlatkérés sor nem lett elfogadva.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-174">Therefore, the system doesn't prevent trade agreement journals from being created if the RFQ line hasn't been accepted.</span></span>

<span data-ttu-id="4b9e0-175">Az ajánlatkérésre adott válaszokhoz kereskedelmi megállapodásokat hozhat létre, függetlenül attól, hogy elfogadták vagy elutasították azokat.</span><span class="sxs-lookup"><span data-stu-id="4b9e0-175">You can create trade agreements for any replies for a request for quotation (RFQ), regardless of whether they were accepted or rejected.</span></span> <span data-ttu-id="4b9e0-176">További információkért lásd: [Ajánlatkérések (RFQ-k) áttekintése](request-quotations.md).</span><span class="sxs-lookup"><span data-stu-id="4b9e0-176">For more information, see [Requests for quotation (RFQs) overview](request-quotations.md).</span></span>

