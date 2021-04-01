---
title: Könyvelési felosztások és naplóbejegyzések szállítói számlákhoz
description: A könyvelési felosztások használatával lehet meghatározni, hogy hogyan lesz az összeg elszámolva, például hogyan lesznek könyvelve a kiadások, adó és költségek a szállítói számlán. Minden összegnek, amelyet könyvelni kell, amikor a szállítói számla naplózva van egy vagy több könyvelési felosztása van.
author: abruer
manager: AnnBe
ms.date: 08/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendEditInvoice
audience: Application User
ms.reviewer: roschlom
ms.custom: 26891
ms.assetid: 93dc608a-b5b4-4ec3-83c2-618e3d80a583
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b0ad3124963dda33f44cf8ba6e6bb466029b2651
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5252193"
---
# <a name="accounting-distributions-and-journal-entries-for-vendor-invoices"></a><span data-ttu-id="9f126-104">Könyvelési felosztások és naplóbejegyzések szállítói számlákhoz</span><span class="sxs-lookup"><span data-stu-id="9f126-104">Accounting distributions and journal entries for vendor invoices</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9f126-105">A könyvelési felosztások használatával lehet meghatározni, hogy hogyan lesz az összeg elszámolva, például hogyan lesznek könyvelve a kiadások, adó és költségek a szállítói számlán.</span><span class="sxs-lookup"><span data-stu-id="9f126-105">Accounting distributions are used to define how an amount will be accounted for, such as how the expense, tax, or charges will be accounted for on a vendor invoice.</span></span> <span data-ttu-id="9f126-106">Minden összegnek, amelyet könyvelni kell, amikor a szállítói számla naplózva van egy vagy több könyvelési felosztása van.</span><span class="sxs-lookup"><span data-stu-id="9f126-106">Every amount that must be accounted for when the vendor invoice is journalized will have one or more accounting distributions.</span></span> 

<a name="accounting-distributions"></a><span data-ttu-id="9f126-107">Könyvelési felosztások</span><span class="sxs-lookup"><span data-stu-id="9f126-107">Accounting distributions</span></span> 
-------------------------

<span data-ttu-id="9f126-108">A következő gombokat használhatja a Szállítói számla oldalon a szállítói számlán szereplő minden összeg könyvelési felosztásának megtekintéséhez és lehetséges módosításához.</span><span class="sxs-lookup"><span data-stu-id="9f126-108">You can use the following buttons in the Vendor invoice page to view, and possibly modify, the accounting distributions for each amount on the vendor invoice.</span></span>
-   <span data-ttu-id="9f126-109">**Összegek felosztása** – Egy bizonyos sorhoz és alsorokhoz, például az adókhoz és díjakhoz tartozó könyvelési felosztások megtekintése és módosítása.</span><span class="sxs-lookup"><span data-stu-id="9f126-109">**Distribute amounts** – View and modify the accounting distributions for an individual line and any child lines, such as taxes or charges.</span></span> <span data-ttu-id="9f126-110">Megtekintheti és módosíthatja a könyvelési felosztásokat az alárendelt sorra vonatkozóan a Forgalmi adó tranzakciók vagy a Költségtranzakciók lapon is.</span><span class="sxs-lookup"><span data-stu-id="9f126-110">You can also view and modify the accounting distributions for the child line directly from the Sales tax transactions page or the Charges transactions page.</span></span>
    -   <span data-ttu-id="9f126-111">Szállítói számla fejléc összegek módosítása, például a költségek vagy a pénznemben megadott kerekítési összegek módosítása.</span><span class="sxs-lookup"><span data-stu-id="9f126-111">Modify vendor invoice header amounts, such as charges or currency rounding amounts.</span></span>
    -   <span data-ttu-id="9f126-112">Szállítói számlasorok összegének módosítása.</span><span class="sxs-lookup"><span data-stu-id="9f126-112">Modify vendor invoice line amounts.</span></span>
-   <span data-ttu-id="9f126-113">**Felosztások megtekintése** – A dokumentumban szereplő összes sorhoz tartozó könyvelési felosztás megtekintése.</span><span class="sxs-lookup"><span data-stu-id="9f126-113">**View distributions** – View the accounting distributions for all lines on the document.</span></span> <span data-ttu-id="9f126-114">A könyvelési felosztásokat ebből a nézetből nem módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="9f126-114">You cannot modify the accounting distributions from this view.</span></span>
    -   <span data-ttu-id="9f126-115">A fejléc és a sorösszegek áttekintése.</span><span class="sxs-lookup"><span data-stu-id="9f126-115">View header and line amounts.</span></span>

<span data-ttu-id="9f126-116">Ha a szállítói számla beszerzési rendelésre hivatkozik, a könyvelési felosztások feloszthatók és módosíthatók a nem raktározott cikket tartalmazó sorokra.</span><span class="sxs-lookup"><span data-stu-id="9f126-116">If the vendor invoice references a purchase order, you can split and modify the accounting distributions for lines that contain an item that is not stocked.</span></span> <span data-ttu-id="9f126-117">Ha egy szállítói számlasor nem hivatkozik egy beszerzési rendeléssorra, egy könyvelési felosztást ki is törölhet.</span><span class="sxs-lookup"><span data-stu-id="9f126-117">If the vendor invoice line does not reference a purchase order line, you can also delete an accounting distribution.</span></span> <span data-ttu-id="9f126-118">Nem oszthat fel vagy törölhet sorokat, költségek, adók, és sorengedmények esetében.</span><span class="sxs-lookup"><span data-stu-id="9f126-118">You cannot split or delete lines for charges, taxes, and line discounts.</span></span> <span data-ttu-id="9f126-119">Módosíthatja a főkönyvi számlát, de az összegeket vagy százalékokat nem módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="9f126-119">You can modify the ledger account, but you cannot change the amounts or percentages.</span></span>
> [!NOTE]                                                                                                                                 
> <span data-ttu-id="9f126-120">Ha a szülő-sor nem raktározott cikket tartalmaz és a könyvelési felosztások fel vannak osztva, a gyermek sor automatikusan fel lesz osztva, hogy egyezzen a szülő sor pénzügyi dimenzióival.</span><span class="sxs-lookup"><span data-stu-id="9f126-120">If the parent line contains an item that is not stocked and the accounting distributions are split, the child line will be split automatically to match the financial dimensions of the parent line.</span></span> <span data-ttu-id="9f126-121">A könyvelési felosztásokat a gyermek sorhoz nem lehet tovább osztani vagy törölni, de a gyermek sor beállításától függően esetleg módosíthatja a főkönyvi számlát a gyermek-sor könyvelési felosztásaihoz.</span><span class="sxs-lookup"><span data-stu-id="9f126-121">The accounting distributions for the child line cannot be additionally split or deleted, but depending on the setup of the child line, you might be able to modify the ledger account for the accounting distributions of the child line.</span></span>

## <a name="distributing-amounts"></a><span data-ttu-id="9f126-122">Összegek elosztása</span><span class="sxs-lookup"><span data-stu-id="9f126-122">Distributing amounts</span></span>
<span data-ttu-id="9f126-123">Szállítói számla bevitelekor minden összeg felosztása a következőképpen történik.</span><span class="sxs-lookup"><span data-stu-id="9f126-123">When you enter a vendor invoice, each amount will be distributed as follows.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f126-124">Szállítói számlasor típusa</span><span class="sxs-lookup"><span data-stu-id="9f126-124">Type of vendor invoice line</span></span></th>
<th><span data-ttu-id="9f126-125">Prioritási sorrend, amely meghatározza, hogy honnan jelenjen meg a fő számla</span><span class="sxs-lookup"><span data-stu-id="9f126-125">Order of priority that determines where the main account is displayed from</span></span></th>
<th><span data-ttu-id="9f126-126">Prioritási sorrend, amely meghatározza, hogy mely alapértelmezett pénzügyi dimenzió jelenik meg</span><span class="sxs-lookup"><span data-stu-id="9f126-126">Order of priority that determines which default financial dimension is displayed</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9f126-127">Raktározott termék</span><span class="sxs-lookup"><span data-stu-id="9f126-127">Stocked product</span></span></td>
<td><ol>
<li><span data-ttu-id="9f126-128">Könyvelési felosztások a beszerzési rendelési sorhoz.</span><span class="sxs-lookup"><span data-stu-id="9f126-128">The accounting distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="9f126-129">A Fő számla mezője, a Feladás lap termékre vonatkozó Beszerzési kiadás lehetőségének kijelölésekor.</span><span class="sxs-lookup"><span data-stu-id="9f126-129">The Main account field when Purchase expenditure for product is selected in the Posting page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="9f126-130">Ha a számlasor beszerzési rendelés-sorra hivatkozik, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</span><span class="sxs-lookup"><span data-stu-id="9f126-130">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="9f126-131">Alapértelmezett pénzügyi dimenzió értékeinek használata a szállítói számlán.</span><span class="sxs-lookup"><span data-stu-id="9f126-131">Use the default financial dimension values on the vendor invoice.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9f126-132">Beszerzési kategória vagy termék, amelyet nem tartanak készleten</span><span class="sxs-lookup"><span data-stu-id="9f126-132">A procurement category or a product that is not stocked</span></span></td>
<td><ol>
<li><span data-ttu-id="9f126-133">A könyvelési felosztás a beszerzési rendelési sorhoz, ha a szállítói számlasor hivatkozik a beszerzési rendelési sorra.</span><span class="sxs-lookup"><span data-stu-id="9f126-133">The accounting distribution for the purchase order line, if the vendor invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="9f126-134">A Fő számla mezője, a Feladás lap kiadásra vonatkozó Beszerzési kiadás lehetőségének kijelölésekor.</span><span class="sxs-lookup"><span data-stu-id="9f126-134">The Main account field when Purchase expenditure for expense is selected in the Posting page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="9f126-135">Ha a számlasor beszerzési rendelés-sorra hivatkozik, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</span><span class="sxs-lookup"><span data-stu-id="9f126-135">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="9f126-136">Ha a fő számla felosztási számla, akkor használja az alapértelmezett értéket a felosztási számla meghatározásából.</span><span class="sxs-lookup"><span data-stu-id="9f126-136">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="9f126-137">Alapértelmezett pénzügyi dimenzió értékeinek használata a szállítói számlán.</span><span class="sxs-lookup"><span data-stu-id="9f126-137">Use the default financial dimension values on the vendor invoice.</span></span></li>
<li><span data-ttu-id="9f126-138">Használja a pénzügyi dimenzió értéket a szállítói számlasorból.</span><span class="sxs-lookup"><span data-stu-id="9f126-138">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="9f126-139">Használja az alapértelmezett pénzügyi dimenzió értékeket a fő számláról a Számlatükör oldalon.</span><span class="sxs-lookup"><span data-stu-id="9f126-139">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9f126-140">Tárgyi eszköz</span><span class="sxs-lookup"><span data-stu-id="9f126-140">Fixed asset</span></span></td>
<td><ol>
<li><span data-ttu-id="9f126-141">A könyvelési felosztás a beszerzési rendelési sorhoz, ha a szállítói számlasor hivatkozik a beszerzési rendelési sorra.</span><span class="sxs-lookup"><span data-stu-id="9f126-141">The accounting distribution for the purchase order line, if the vendor invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="9f126-142">Ha a Beszerzés ki van jelölve a Tranzakció típusa mező a Szállítói számla képernyőn, ha a Fő számla mező, amikor a Tárgyi eszköz feladási profilok lapján a Beszerzés van kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="9f126-142">If Acquisition is selected in the Transaction type field in the Vendor invoice form, the Main account field when Acquisition is selected in the Fixed asset posting profiles page.</span></span></li>
<li><span data-ttu-id="9f126-143">Ha a Beszerzés módosítás ki van jelölve a Tranzakció típusa mezőben, a Fő számla mező, amikor a Tárgyi eszköz feladási profilok lapján a Beszerzés módosítás van kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="9f126-143">If Acquisition adjustment is selected in the Transaction type field, the Main account field when Acquisition adjustment is selected in the Fixed asset posting profiles page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="9f126-144">Használja a könyvelési felosztást a beszerzési rendelési sorra, ha a számlasor hivatkozik a beszerzési rendelési sorra.</span><span class="sxs-lookup"><span data-stu-id="9f126-144">Use the account distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="9f126-145">Használja a pénzügyi dimenzió értéket a szállítói számlasorból.</span><span class="sxs-lookup"><span data-stu-id="9f126-145">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="9f126-146">Használja az alapértelmezett pénzügyi dimenzió értékeket a fő számláról a Számlatükör oldalon.</span><span class="sxs-lookup"><span data-stu-id="9f126-146">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9f126-147">A szállítói számlasoron meghatározott projekt</span><span class="sxs-lookup"><span data-stu-id="9f126-147">Project defined on the vendor invoice line</span></span></td>
<td><ol>
<li><span data-ttu-id="9f126-148">Könyvelési felosztás a beszerzési rendelési sorra, ha a számlasor hivatkozik a beszerzési rendelési sorra.</span><span class="sxs-lookup"><span data-stu-id="9f126-148">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="9f126-149">Ha az Egyenleg van megadva a Költségek feladásánál - cikkmező a Projektcsoportok lapon, a Fő számlák mezője, amikor a Költség van megadva a Főkönyvi feladás beállítása oldalon.</span><span class="sxs-lookup"><span data-stu-id="9f126-149">If Balance is selected in the Post costs - item field in the Project groups page, the Main account field when Cost is selected in the Ledger posting setup page.</span></span></li>
<li><span data-ttu-id="9f126-150">Ha az Eredmény van megadva a Költségek feladásánál - cikkmező a Projektcsoportok lapon, a Fő számlák mezője, amikor a Költség - cikk van megadva a Főkönyvi feladás beállítása oldalon.</span><span class="sxs-lookup"><span data-stu-id="9f126-150">If Profit and loss is selected in the Post costs - item field in the Project groups page, the Main account field when Cost - item is selected in the Ledger posting setup page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="9f126-151">Ha a számlasor beszerzési rendelés-sorra hivatkozik, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</span><span class="sxs-lookup"><span data-stu-id="9f126-151">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9f126-152">Sorengedmény</span><span class="sxs-lookup"><span data-stu-id="9f126-152">Line discount</span></span></td>
<td><ol>
<li><span data-ttu-id="9f126-153">Könyvelési felosztás a beszerzési rendelési sorra, ha a számlasor hivatkozik a beszerzési rendelési sorra.</span><span class="sxs-lookup"><span data-stu-id="9f126-153">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="9f126-154">A Fő számlák mezője, amikor Feladás lapján az Engedmény van kijelölve.</span><span class="sxs-lookup"><span data-stu-id="9f126-154">The Main account field when Discount is selected in the Posting page.</span></span></li>
<li><span data-ttu-id="9f126-155">Ha a fő számla az engedményhez nincs meghatározva a feladási profilon, a beszerzési rendelési soron a kiterjesztett ár könyvelési felosztását kell megtekinteni.</span><span class="sxs-lookup"><span data-stu-id="9f126-155">If a main account for a discount is not defined on the posting profile, the accounting distribution of the extended price on the purchase order line.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="9f126-156">Ha a számlasor hivatkozik a beszerzési rendelés-sorra, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</span><span class="sxs-lookup"><span data-stu-id="9f126-156">If the invoice line references a purchase order line, use the accounting distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="9f126-157">Használja a pénzügyi dimenziókat a kiterjesztett árhoz tartozó könyvelési felosztásokból a szállítói számlán.</span><span class="sxs-lookup"><span data-stu-id="9f126-157">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="9f126-158">Használja a pénzügyi dimenzió értékeket a szállítói számlasorhoz.</span><span class="sxs-lookup"><span data-stu-id="9f126-158">Use the financial dimension values for the vendor invoice line.</span></span></li>
<li><span data-ttu-id="9f126-159">Használja az alapértelmezett pénzügyi dimenzió értékeket a fő számláról a Számlatükör oldalon.</span><span class="sxs-lookup"><span data-stu-id="9f126-159">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9f126-160">Beszerzési költség, amely megjelenik a beszerzési rendelési sor Ár és engedmény lapján</span><span class="sxs-lookup"><span data-stu-id="9f126-160">Purchase charge, which is entered on the Price and discount tab of the purchase order line</span></span></td>
<td><ol>
<li><span data-ttu-id="9f126-161">Könyvelési felosztás a beszerzési rendelési sorra, ha a számlasor hivatkozik a beszerzési rendelési sorra.</span><span class="sxs-lookup"><span data-stu-id="9f126-161">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="9f126-162">A kiterjesztett ár könyvelési felosztása a beszerzési rendelési soron.</span><span class="sxs-lookup"><span data-stu-id="9f126-162">The accounting distribution of the extended price on the purchase order line.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="9f126-163">Ha a számlasor beszerzési rendelés-sorra hivatkozik, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</span><span class="sxs-lookup"><span data-stu-id="9f126-163">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="9f126-164">Használja a pénzügyi dimenziókat a kiterjesztett árhoz tartozó könyvelési felosztásokból a szállítói számlán.</span><span class="sxs-lookup"><span data-stu-id="9f126-164">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9f126-165">Sorköltség</span><span class="sxs-lookup"><span data-stu-id="9f126-165">Line charge</span></span></td>
<td><ol>
<li><span data-ttu-id="9f126-166">Könyvelési felosztás a beszerzési rendelési sorra, ha a számlasor hivatkozik a beszerzési rendelési sorra.</span><span class="sxs-lookup"><span data-stu-id="9f126-166">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="9f126-167">Ha a Főkönyvi számla van megadva a terhelési Típus mezőben a Költségek kód képernyőn, a terhelési Számla mező a Költségkód oldalon.</span><span class="sxs-lookup"><span data-stu-id="9f126-167">If Ledger account is selected in the debit Type field in the Charges code form, the debit Account field in the Charges code page.</span></span></li>
<li><span data-ttu-id="9f126-168">Ha a Cikk van kiválasztva a tartozási Típus mezőben a Költségkód képernyőn, a könyvelési felosztás a kiterjesztett árra a beszerzési rendeléssoron.</span><span class="sxs-lookup"><span data-stu-id="9f126-168">If Item is selected in the debit Type field in the Charges code form, the accounting distribution for the extended price on the purchase order line.</span></span></li>
<li><span data-ttu-id="9f126-169">Ha a Vevő/szállító van megadva a terhelési Típus mezőben a Költségek kód képernyőn, a követelési Számla mező a Költségkód oldalon.</span><span class="sxs-lookup"><span data-stu-id="9f126-169">If Customer/Vendor is selected in the debit Type field in the Charges code form, the credit Account field in the Charges code page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="9f126-170">Ha a számlasor beszerzési rendelés-sorra hivatkozik, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</span><span class="sxs-lookup"><span data-stu-id="9f126-170">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="9f126-171">Használja a pénzügyi dimenziókat a kiterjesztett árhoz tartozó könyvelési felosztásokból a szállítói számlán.</span><span class="sxs-lookup"><span data-stu-id="9f126-171">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="9f126-172">Használja a pénzügyi dimenzió értéket a szállítói számlasorból.</span><span class="sxs-lookup"><span data-stu-id="9f126-172">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="9f126-173">Használja az alapértelmezett pénzügyi dimenzió értékeket a fő számláról a Számlatükör oldalon.</span><span class="sxs-lookup"><span data-stu-id="9f126-173">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9f126-174">Adó, a következő feltétellel:</span><span class="sxs-lookup"><span data-stu-id="9f126-174">Tax, with the following condition:</span></span>
<ul>
<li><span data-ttu-id="9f126-175">Az Egyesült Államok adózási szabályainak alkalmazása lehetőség beállítása van kiválasztva a Főkönyvi paraméterek lapon.</span><span class="sxs-lookup"><span data-stu-id="9f126-175">The Apply U.S. taxation rules option is selected in the General ledger parameters page.</span></span></li>
</ul></td>
<td><ol>
<li><span data-ttu-id="9f126-176">Könyvelési felosztás a beszerzési rendelési sorra, ha a számlasor hivatkozik a beszerzési rendelési sorra.</span><span class="sxs-lookup"><span data-stu-id="9f126-176">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="9f126-177">A kiterjesztett ár vagy a költség könyvelési felosztása.</span><span class="sxs-lookup"><span data-stu-id="9f126-177">The accounting distribution of the extended price or charge.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="9f126-178">Ha a számlasor beszerzési rendelés-sorra hivatkozik, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</span><span class="sxs-lookup"><span data-stu-id="9f126-178">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="9f126-179">Használja a pénzügyi dimenziókat a kiterjesztett árhoz tartozó könyvelési felosztásokból a szállítói számlán.</span><span class="sxs-lookup"><span data-stu-id="9f126-179">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="9f126-180">Használja a pénzügyi dimenzió értéket a szállítói számlasorból.</span><span class="sxs-lookup"><span data-stu-id="9f126-180">Use the financial dimension values from the vendor invoice line.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9f126-181">Adó, a következő feltételekkel:</span><span class="sxs-lookup"><span data-stu-id="9f126-181">Tax, with the following conditions:</span></span>
<ul>
<li><span data-ttu-id="9f126-182">Az Egyesült Államok adózási szabályainak alkalmazása lehetőség ki van törölve a Főkönyvi paraméterek lapon.</span><span class="sxs-lookup"><span data-stu-id="9f126-182">The Apply U.S. taxation rules option is cleared in the General ledger parameters page.</span></span></li>
<li><span data-ttu-id="9f126-183">Az Importadó mező az áfacsoportnál bejelölve, a Forgalmiadó-csoportok lapon.</span><span class="sxs-lookup"><span data-stu-id="9f126-183">The Use tax field for the sales tax group is cleared in the Sales tax groups page.</span></span></li>
</ul></td>
<td><ol>
<li><span data-ttu-id="9f126-184">Visszaigényelhető adó esetén a Visszaigényelhető áfa mező a Főkönyvi feladási csoportok lapon.</span><span class="sxs-lookup"><span data-stu-id="9f126-184">If the tax amount is recoverable, the Sales tax receivable field in the Ledger posting groups page.</span></span></li>
<li><span data-ttu-id="9f126-185">Ha az adó összege nem visszatéríthető, a kiterjesztett ár vagy a könyvelési felosztás a költséghez.</span><span class="sxs-lookup"><span data-stu-id="9f126-185">If the tax amount is not recoverable, the extended price or the accounting distribution for the charge.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="9f126-186">Ha a számlasor beszerzési rendelés-sorra hivatkozik, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</span><span class="sxs-lookup"><span data-stu-id="9f126-186">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="9f126-187">Használja a pénzügyi dimenziókat a kiterjesztett árból vagy a költséghez tartozó könyvelési felosztásokból a szállítói számlasoron.</span><span class="sxs-lookup"><span data-stu-id="9f126-187">Use the financial dimensions from the extended price or the accounting distributions for the charge on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="9f126-188">Használja a pénzügyi dimenzió értéket a szállítói számlasorból.</span><span class="sxs-lookup"><span data-stu-id="9f126-188">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="9f126-189">Használja az alapértelmezett pénzügyi dimenzió értékeket a fő számláról a Számlatükör oldalon.</span><span class="sxs-lookup"><span data-stu-id="9f126-189">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9f126-190">Adó, a következő feltételekkel:</span><span class="sxs-lookup"><span data-stu-id="9f126-190">Tax, with the following conditions:</span></span>
<ul>
<li><span data-ttu-id="9f126-191">Az Egyesült Államok adózási szabályainak alkalmazása lehetőség ki van törölve a Főkönyvi paraméterek lapon.</span><span class="sxs-lookup"><span data-stu-id="9f126-191">The Apply U.S. taxation rules option is cleared in the General ledger parameters page.</span></span></li>
<li><span data-ttu-id="9f126-192">Az Importadó mező az áfacsoportnál be van jelölve a Forgalmiadó-csoportok lapon.</span><span class="sxs-lookup"><span data-stu-id="9f126-192">The Use tax field for the sales tax group is selected in the Sales tax groups page.</span></span></li>
</ul></td>
<td><ol>
<li><span data-ttu-id="9f126-193">Visszaigényelhető adó esetén a Visszaigényelhető áfa mező a Főkönyvi feladási csoportok lapon.</span><span class="sxs-lookup"><span data-stu-id="9f126-193">If the tax amount is recoverable, the Sales tax receivable field in the Ledger posting groups page.</span></span></li>
<li><span data-ttu-id="9f126-194">Ha az adó nem igényelhető vissza, az Importadó költsége mező így néz ki a Főkönyvi feladási csoportok lapon.</span><span class="sxs-lookup"><span data-stu-id="9f126-194">If the tax amount is not recoverable, the Use tax expense field in the Ledger posting groups page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="9f126-195">Ha a számlasor beszerzési rendelés-sorra hivatkozik, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</span><span class="sxs-lookup"><span data-stu-id="9f126-195">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="9f126-196">Használja a pénzügyi dimenziókat a kiterjesztett árból vagy a költséghez tartozó könyvelési felosztásokból a szállítói számlasoron.</span><span class="sxs-lookup"><span data-stu-id="9f126-196">Use the financial dimensions from the extended price or the accounting distributions for the charge on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="9f126-197">Használja a pénzügyi dimenzió értéket a szállítói számlasorból.</span><span class="sxs-lookup"><span data-stu-id="9f126-197">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="9f126-198">Használja az alapértelmezett pénzügyi dimenzió értékeket a fő számláról a Számlatükör oldalon.</span><span class="sxs-lookup"><span data-stu-id="9f126-198">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9f126-199">Fejlécdíj</span><span class="sxs-lookup"><span data-stu-id="9f126-199">Header charge</span></span></td>
<td><ol>
<li><span data-ttu-id="9f126-200">Ha a Főkönyvi számla van megadva a terhelési Típus mezőben a Költségek kód képernyőn, a terhelési Számla mező a Költségkód oldalon.</span><span class="sxs-lookup"><span data-stu-id="9f126-200">If Ledger account is selected in the debit Type field in the Charges code form, the debit Account field in the Charges code page.</span></span></li>
<li><span data-ttu-id="9f126-201">Ha a Vevő/szállító van megadva a terhelési Típus mezőben a Költségek kód képernyőn, a követelési Számla mező a Költségkód oldalon.</span><span class="sxs-lookup"><span data-stu-id="9f126-201">If Customer/Vendor is selected in the debit Type field in the Charges code form, the credit Account field in the Charges code page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="9f126-202">Ha a számlasor beszerzési rendelés-sorra hivatkozik, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</span><span class="sxs-lookup"><span data-stu-id="9f126-202">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="9f126-203">Ha a fő számla felosztási számla, akkor használja az alapértelmezett értéket a felosztási számla meghatározásából.</span><span class="sxs-lookup"><span data-stu-id="9f126-203">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="9f126-204">Használja a pénzügyi dimenzió alapértelmezett sablon értékeket a szállítói számla fejlécéből.</span><span class="sxs-lookup"><span data-stu-id="9f126-204">Use the financial dimension default template values from the vendor invoice header.</span></span></li>
<li><span data-ttu-id="9f126-205">Használja a pénzügyi dimenzió értéket a szállítói számlasorból.</span><span class="sxs-lookup"><span data-stu-id="9f126-205">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="9f126-206">Használja az alapértelmezett pénzügyi dimenzió értékeket a fő számláról a Számlatükör oldalon.</span><span class="sxs-lookup"><span data-stu-id="9f126-206">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9f126-207">Fejléc-engedmény</span><span class="sxs-lookup"><span data-stu-id="9f126-207">Header discount</span></span></td>
<td><ol>
<li><span data-ttu-id="9f126-208">A Fő számla mezője a Szállítói számla engedményének feladási típusához a Számlák automatikus tranzakciókhoz lapon.</span><span class="sxs-lookup"><span data-stu-id="9f126-208">The Main account field for the Vendor invoice discount posting type in the Accounts for automatic transactions page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="9f126-209">Ha a számlasor beszerzési rendelés-sorra hivatkozik, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</span><span class="sxs-lookup"><span data-stu-id="9f126-209">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="9f126-210">Használja a pénzügyi dimenziókat a kiterjesztett árhoz tartozó könyvelési felosztásokból a szállítói számlán.</span><span class="sxs-lookup"><span data-stu-id="9f126-210">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="9f126-211">Használja a pénzügyi dimenzió értéket a szállítói számlasorból.</span><span class="sxs-lookup"><span data-stu-id="9f126-211">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="9f126-212">Használja az alapértelmezett pénzügyi dimenzió értékeket a fő számláról a Számlatükör oldalon.</span><span class="sxs-lookup"><span data-stu-id="9f126-212">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
</tbody>
</table>


<a name="distributing-taxes"></a><span data-ttu-id="9f126-213">Adó elosztása</span><span class="sxs-lookup"><span data-stu-id="9f126-213">Distributing taxes</span></span>
------------------

<span data-ttu-id="9f126-214">Az adókra vonatkozó könyvelési felosztások nem hozhatók létre, amíg az adókat ki nem számítja.</span><span class="sxs-lookup"><span data-stu-id="9f126-214">Accounting distributions for taxes cannot be created until taxes are calculated.</span></span> <span data-ttu-id="9f126-215">Forgalmi adó kiszámításához fejezzen be egyet a következő feladatok közül a Szállítói számla lapon:</span><span class="sxs-lookup"><span data-stu-id="9f126-215">To calculate sales taxes, you must complete one of the following tasks in the Vendor invoice page:</span></span>
-   <span data-ttu-id="9f126-216">Számla végösszegének megtekintése.</span><span class="sxs-lookup"><span data-stu-id="9f126-216">View the invoice total.</span></span>
-   <span data-ttu-id="9f126-217">Az áfa megtekintése.</span><span class="sxs-lookup"><span data-stu-id="9f126-217">View the sales tax.</span></span>
-   <span data-ttu-id="9f126-218">Analitikus napló megtekintése.</span><span class="sxs-lookup"><span data-stu-id="9f126-218">View the subledger journal.</span></span>
-   <span data-ttu-id="9f126-219">Könyvelési felosztások megtekintése a teljes szállítói számlához.</span><span class="sxs-lookup"><span data-stu-id="9f126-219">View accounting distributions for the complete vendor invoice.</span></span>
-   <span data-ttu-id="9f126-220">Helyezze a szállítói számlát várakoztatásra.</span><span class="sxs-lookup"><span data-stu-id="9f126-220">Place the vendor invoice on hold.</span></span>
-   <span data-ttu-id="9f126-221">Szállítói számla feladása.</span><span class="sxs-lookup"><span data-stu-id="9f126-221">Post the vendor invoice.</span></span>

## <a name="subledger-journals-for-vendor-invoices"></a><span data-ttu-id="9f126-222">Szállítói számlákhoz tartozó analitikus naplók</span><span class="sxs-lookup"><span data-stu-id="9f126-222">Subledger journals for vendor invoices</span></span>
<span data-ttu-id="9f126-223">Szállítói számla feladása előtt meg lehet tekinteni a számla teljes könyvelési bejegyzését, amely tartalmazza a terheléseket és követeléseket, annak igazolására, hogy a számla a megfelelő számlákra van elküldve.</span><span class="sxs-lookup"><span data-stu-id="9f126-223">Before you post a vendor invoice, you can view the full accounting entry of the invoice, which includes debits and credits, to verify that the invoice is being posted to the correct accounts.</span></span> <span data-ttu-id="9f126-224">A teljes könyvelési bejegyzésnek ezt a nézetét analitikus naplónak hívják.</span><span class="sxs-lookup"><span data-stu-id="9f126-224">This view of the full accounting entry is called a subledger journal.</span></span> 

<span data-ttu-id="9f126-225">Ha az analitikus napló bejegyzése helytelen, amikor megtekinti azt a szállítói számla naplózása előtt, az analitikus napló bejegyzése nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="9f126-225">If the subledger journal entry is incorrect when you preview it before you journalize the vendor invoice, you cannot modify the subledger journal entry.</span></span> <span data-ttu-id="9f126-226">Ehelyett módosítania kell a könyvelési felosztásokat vagy a feladási profilt.</span><span class="sxs-lookup"><span data-stu-id="9f126-226">Instead, you must modify the accounting distributions or the posting profile.</span></span> <span data-ttu-id="9f126-227">A könyvelési felosztásokat a könyvelési tétel, a tartozás tétel vagy a jóváírás egy részének meghatározására használják.</span><span class="sxs-lookup"><span data-stu-id="9f126-227">The accounting distributions are used to define one side of the accounting entry, the debit or the credit.</span></span> <span data-ttu-id="9f126-228">Az ellentételező analitikus naplószámla bejegyzése a feladási profilok használatával, például a szállítói számlából vagy adóból jön létre.</span><span class="sxs-lookup"><span data-stu-id="9f126-228">The offsetting subledger journal account entry is created by using the posting profiles, such as from the vendor account or tax.</span></span>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]