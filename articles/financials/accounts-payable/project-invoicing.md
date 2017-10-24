---
title: "Projekt számlázása:"
description: "Ez a cikk az Idő- és anyagelszámolású projektek, illetve a Rögzített árú projektek projektszámlázásáról nyújt áttekintést. Számlajavaslatokkal (előzetes számlák), számlaellenőrzéssel, részszámlázással, szállítói számlázással és jóváírásokkal kapcsolatos információkat tartalmaz."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjInvoiceCashFlow, ProjInvoiceControl, ProjInvoiceListPage, ProjInvoiceProposalDetail, ProjInvoiceProposalListPage
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 23111
ms.assetid: 1812d6f2-8b34-4258-8f5f-dcf12281547f
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 57d62293311ec7143b691d4220fa0357d6ba9ef1
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="project-invoicing"></a><span data-ttu-id="925c9-104">Projekt számlázása:</span><span class="sxs-lookup"><span data-stu-id="925c9-104">Project invoicing</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="925c9-105">Ez a cikk az Idő- és anyagelszámolású projektek, illetve a Rögzített árú projektek projektszámlázásáról nyújt áttekintést.</span><span class="sxs-lookup"><span data-stu-id="925c9-105">This article provides an overview of project invoicing for Time and material projects and Fixed-price projects.</span></span> <span data-ttu-id="925c9-106">Számlajavaslatokkal (előzetes számlák), számlaellenőrzéssel, részszámlázással, szállítói számlázással és jóváírásokkal kapcsolatos információkat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="925c9-106">It includes information about invoice proposals (preliminary invoices), invoice control, on-account invoicing, vendor invoicing, and credit notes.</span></span>

<span data-ttu-id="925c9-107">A projekt típusa határozza meg, hogy melyik számlázási eljárást kell alkalmazni.</span><span class="sxs-lookup"><span data-stu-id="925c9-107">The project type determines which invoicing procedure should be applied.</span></span> <span data-ttu-id="925c9-108">Kizárólag a két külső projekttípus, az Idő- és anyagelszámolású, illetve a Rögzített árú projektek számlázhatók.</span><span class="sxs-lookup"><span data-stu-id="925c9-108">Only the two external project types, Time and material and Fixed-price, can be invoiced.</span></span> <span data-ttu-id="925c9-109">Az Idő- és anyagelszámolású projektek és a Rögzített árú projektek mindig projektszerződéshez kapcsolódnak.</span><span class="sxs-lookup"><span data-stu-id="925c9-109">Time and material projects and Fixed-price projects are always attached to a project contract.</span></span>

-   <span data-ttu-id="925c9-110">**Rögzített árú projektek** – A vevői számla összege a számlázási ütemezésen alapul.</span><span class="sxs-lookup"><span data-stu-id="925c9-110">**Fixed-price projects** – The customer invoice amount is based on invoice billing schedules.</span></span> <span data-ttu-id="925c9-111">A számlázás egy részszámlázási beállítás szerint történik, amelyet számlázási ütemezésnek is neveznek.</span><span class="sxs-lookup"><span data-stu-id="925c9-111">Invoicing is done through an on-account setup, which is also referred to as a billing schedule.</span></span> <span data-ttu-id="925c9-112">A rögzített árú projektekről projektenként vagy projektszerződésenként készíthető számla.</span><span class="sxs-lookup"><span data-stu-id="925c9-112">Fixed-price projects can be invoiced per project or per project contract.</span></span>
-   <span data-ttu-id="925c9-113">**Idő- és anyagelszámolású projektek** – A vevői számla összege a projekteknél megadott tranzakciósorok alapján alakul.</span><span class="sxs-lookup"><span data-stu-id="925c9-113">**Time and material projects** – The customer invoice amount is based on transaction lines that are entered on projects.</span></span> <span data-ttu-id="925c9-114">A tranzakciók projektenként vagy projektszerződésenként számlázhatók.</span><span class="sxs-lookup"><span data-stu-id="925c9-114">Transactions can be invoiced per project or per project contract.</span></span>

<span data-ttu-id="925c9-115">Háromféle módon tud idő- és anyagelszámolású projekteket és Rögzített árú projektet társítani számlaprojekthez:</span><span class="sxs-lookup"><span data-stu-id="925c9-115">There are three ways to attach Time and material projects and Fixed-price projects to the invoice projects:</span></span>

-   <span data-ttu-id="925c9-116">**Részszámla készítése** – Az idő- és anyagelszámolású, valamint a Rögzített árú projektekről részszámla is készíthető.</span><span class="sxs-lookup"><span data-stu-id="925c9-116">**On-account invoicing** – Time and material projects and Fixed-price projects can be invoiced on account.</span></span> <span data-ttu-id="925c9-117">A két projekttípus eltérő részszámlázási beállítást tesz szükségessé.</span><span class="sxs-lookup"><span data-stu-id="925c9-117">Two types of on-account setup are required, one for each project type.</span></span>
-   <span data-ttu-id="925c9-118">**Számla készítése az időszakos szakaszban** – az időszakos szolgáltatásokkal a tranzakciók több projekten keresztül is számlázhatók.</span><span class="sxs-lookup"><span data-stu-id="925c9-118">**Invoicing in the periodic section** – Through the periodic functions, transactions can be invoiced across projects.</span></span> <span data-ttu-id="925c9-119">Az ismétlési funkciók segítségével áttekintés kapható a számlázandó tranzakciókról.</span><span class="sxs-lookup"><span data-stu-id="925c9-119">The periodic functions provide an overview of transactions that must be invoiced.</span></span>
-   <span data-ttu-id="925c9-120">**Jóváírások használata a számlázás során** – Idő és anyagelszámolású és Rögzített árú projektekhez is készíthető jóváírás.</span><span class="sxs-lookup"><span data-stu-id="925c9-120">**By using credit notes in invoicing** – A credit note can be created for both Time and material projects and Fixed-price projects.</span></span>

## <a name="invoice-proposals"></a><span data-ttu-id="925c9-121">Számlajavaslatok</span><span class="sxs-lookup"><span data-stu-id="925c9-121">Invoice proposals</span></span>
<span data-ttu-id="925c9-122">Mielőtt létrehozná egy projekt vevői számláját, létrehozhat egy előzetes számlát, más néven számlajavaslatot.</span><span class="sxs-lookup"><span data-stu-id="925c9-122">Before you create a customer invoice for a project, you can create a preliminary invoice, or invoice proposal.</span></span> <span data-ttu-id="925c9-123">A számlajavaslatban tudja kiválasztani, hogy a projektszámlán mely projekttranzakciók szerepeljenek.</span><span class="sxs-lookup"><span data-stu-id="925c9-123">In an invoice proposal, you can select project transactions to include in a project invoice.</span></span> <span data-ttu-id="925c9-124">A projektszámla feladása, illetve a vevő vagy a finanszírozási forrás részére történő megküldése előtt át tudja nézni a számla részletes adatait.</span><span class="sxs-lookup"><span data-stu-id="925c9-124">You can then review the invoice details before you post the project invoice and send it to the customer or other funding source.</span></span>

### <a name="creating-invoice-proposals"></a><span data-ttu-id="925c9-125">Számlajavaslatok létrehozása</span><span class="sxs-lookup"><span data-stu-id="925c9-125">Creating invoice proposals</span></span>

<span data-ttu-id="925c9-126">A számlajavaslatokat manuálisan, az adott projekt tranzakcióinak kiválasztásával hozhatja létre.</span><span class="sxs-lookup"><span data-stu-id="925c9-126">You can create invoice proposals by manually selecting from a list of transactions for a specified project.</span></span> <span data-ttu-id="925c9-127">Alternatív megoldásként felállíthat olyan számlázási szabályokat, amelyek automatikusan generálnak számlajavaslatot.</span><span class="sxs-lookup"><span data-stu-id="925c9-127">You can also set up billing rules that specify when to automatically create an invoice proposal.</span></span> <span data-ttu-id="925c9-128">Például felállíthat egy olyan számlázási szabályt, amely számlajavaslatokat hoz létre, amikor a projekt 25%-a, 50 %-a, 75%-a, illetve 100%-a elkészült.</span><span class="sxs-lookup"><span data-stu-id="925c9-128">For example, you can create a billing rule to create an invoice proposal when work on a project is 25 percent, 50 percent, 75 percent, and 100 percent completed.</span></span> 

<span data-ttu-id="925c9-129">A következő tranzakciókhoz tud létrehozni számlajavaslatot:</span><span class="sxs-lookup"><span data-stu-id="925c9-129">You can create invoice proposals for the following transactions:</span></span>

-   <span data-ttu-id="925c9-130">Órák, kiadások és egyéb projekttranzakciók</span><span class="sxs-lookup"><span data-stu-id="925c9-130">Hours, expenses, and other project transactions</span></span>
-   <span data-ttu-id="925c9-131">A vevőktől korábbi projektszámlákon visszatartott összegek</span><span class="sxs-lookup"><span data-stu-id="925c9-131">Amounts that are withheld by customers on previous project invoices</span></span>
-   <span data-ttu-id="925c9-132">Jóváírások</span><span class="sxs-lookup"><span data-stu-id="925c9-132">Credit notes</span></span>
-   <span data-ttu-id="925c9-133">Egy vevő által a projekt megkezdése előtt kifizetett összegek</span><span class="sxs-lookup"><span data-stu-id="925c9-133">Amounts that a customer paid to you before a project is started</span></span>

<span data-ttu-id="925c9-134">A rendszerben díjtranzakciókat is létre tud hozni egy számlajavaslatban.</span><span class="sxs-lookup"><span data-stu-id="925c9-134">You can create fee transactions in an invoice proposal.</span></span> <span data-ttu-id="925c9-135">Lehetőség van az eladási ár, az óra, a költség, a cikk és a díjtranzakciók módosítására is.</span><span class="sxs-lookup"><span data-stu-id="925c9-135">You can also modify the sales price on hour, expense, item, and fee transactions.</span></span> <span data-ttu-id="925c9-136">A számlajavaslat feladásakor a frissített árak és a tranzakciók hozzáadódnak a projektjelentésekhez és a tranzakció előzményeihez.</span><span class="sxs-lookup"><span data-stu-id="925c9-136">When you post an invoice proposal, the updated prices and transactions are added to project reports and the transaction history.</span></span> 

<span data-ttu-id="925c9-137">Amennyiben egy projekthez több vevői számlát szeretne létrehozni, ezekhez egyesével kell számlajavaslatot generálnia.</span><span class="sxs-lookup"><span data-stu-id="925c9-137">To create multiple customer invoices for a project, you must create an invoice proposal for each invoice.</span></span> <span data-ttu-id="925c9-138">Például tranzakciótípus alapján is létrehozhat számlákat.</span><span class="sxs-lookup"><span data-stu-id="925c9-138">For example, you can create invoices based on transaction type.</span></span> <span data-ttu-id="925c9-139">Amennyiben az egyik számlán órákat, egy másikon pedig cikkeket akar megadni, akkor létre kell hoznia egy számlajavaslatot az óratranzakciók számára, és egy másikat a díjtranzakciókhoz.</span><span class="sxs-lookup"><span data-stu-id="925c9-139">To specify hours on one customer invoice and items on another, you must create separate invoice proposals for hour transactions and fee transactions.</span></span> 

<span data-ttu-id="925c9-140">Ha egy projekt egynél több finanszírozási forráshoz tartozik, akkor önálló számlajavaslatot hozhat létre az összes finanszírozási forrás részére.</span><span class="sxs-lookup"><span data-stu-id="925c9-140">If a project has more than one funding source, you can create a separate invoice proposal for each funding source.</span></span> <span data-ttu-id="925c9-141">A **Finanszírozási szabály felosztásai** lapon meghatározhatja a tranzakciós összeg, az egyes finanszírozási forrásokhoz rendelendő százalékát, valamint a kerekítési különbségek feladásához használatos forrást.</span><span class="sxs-lookup"><span data-stu-id="925c9-141">On the **Funding rule allocations** page, you can define the percentage of the transaction amount to allocate to each funding source, and the source to post rounding differences.</span></span>

### <a name="creating-customer-invoices-from-invoice-proposals"></a><span data-ttu-id="925c9-142">Vevői számlák létrehozása számlajavaslatokból</span><span class="sxs-lookup"><span data-stu-id="925c9-142">Creating customer invoices from invoice proposals</span></span>

<span data-ttu-id="925c9-143">Miután létrehozta és feladta a számlajavaslatot, automatikusan ltérejön egy vevői számla a javaslatban szereplő tranzakciókból.</span><span class="sxs-lookup"><span data-stu-id="925c9-143">After you create and post an invoice proposal, a customer invoice is automatically created for the transactions that are included in the invoice proposal.</span></span> 

<span data-ttu-id="925c9-144">Számlajavaslat feladása előtt ahhoz tud hozzáadni, illetve abból törölni tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="925c9-144">Before you post an invoice proposal, you can add transactions to it or delete transactions from it.</span></span> <span data-ttu-id="925c9-145">Például eltávolíthatja a projektbe feladott költségtranzakciókat, amelyek nem számlázhatók a vevőnek.</span><span class="sxs-lookup"><span data-stu-id="925c9-145">For example, you can remove expense transactions that were posted to a project, but that are not chargeable to the customer.</span></span> 

<span data-ttu-id="925c9-146">Ha a szervezet előírja, hogy a számlajavaslatokat feladás előtt ellenőrizni kell, akkor a számlajavaslatot adott esetben a „Projekt számlajavaslatainak áttekintése” munkafolyamaton keresztül kell jóváhagyni feladás előtt.</span><span class="sxs-lookup"><span data-stu-id="925c9-146">If your organization requires that invoice proposals be reviewed before they are posted, the invoice proposal might need to be approved through the "Review project invoice proposals" workflow before it is posted.</span></span>

## <a name="on-account-invoicing"></a><span data-ttu-id="925c9-147">Részszámla készítése</span><span class="sxs-lookup"><span data-stu-id="925c9-147">On-account invoicing</span></span>
<span data-ttu-id="925c9-148">A részszámlán a projekt kapcsán megadott összeg az időzítésen, a projekt előrehaladottságának százalékán és egyéb számlázási feltételeken múlik, amelyek a kapcsolódó projektszerződésben vannak meghatározva.</span><span class="sxs-lookup"><span data-stu-id="925c9-148">The amount that you enter for a project in an on-account invoice is based on the timing, percentage of completion, and other billing conditions that are specified in the related project contract.</span></span> <span data-ttu-id="925c9-149">Az összeg nem a projektbe feladott órák, cikkek, kiadások és díjak alapján kerül kiszámításra.</span><span class="sxs-lookup"><span data-stu-id="925c9-149">The amount is not calculated based on the hours, items, expenses, or fees that are posted to the project.</span></span> 

<span data-ttu-id="925c9-150">A rendszerben előbb létre kell hoznia egy részszámlázási tranzakciót az idő- és anyagelszámolású vagy a rögzített árú projekthez, mielőtt a projektszámlához hozzáadhatná az adott részszámlázási tranzakciót.</span><span class="sxs-lookup"><span data-stu-id="925c9-150">You must create an on-account transaction for a Time and material project or a Fixed-price project before you can add that on-account transaction to a project invoice.</span></span> <span data-ttu-id="925c9-151">A részszámlázási tranzakcióban adja meg a vevőnek számlázandó összeget.</span><span class="sxs-lookup"><span data-stu-id="925c9-151">On the on-account transaction, enter the amount to invoice a customer.</span></span> <span data-ttu-id="925c9-152">Az összeg projektszámlájának létrehozása előtt hozzon létre egy előzetes számlát (számlajavaslatot).</span><span class="sxs-lookup"><span data-stu-id="925c9-152">To create a project invoice for the amount, create a preliminary invoice (invoice proposal).</span></span> <span data-ttu-id="925c9-153">A számlajavaslatban válassza ki a részszámla-tranzakciót.</span><span class="sxs-lookup"><span data-stu-id="925c9-153">In the invoice proposal, select the on-account transaction.</span></span> <span data-ttu-id="925c9-154">A számlajavaslatban megtekintheti a részszámla információit, mielőtt létrehozza hozzá a projektszámlát.</span><span class="sxs-lookup"><span data-stu-id="925c9-154">You can review the on-account information in the invoice proposal before you create a project invoice for it.</span></span>

### <a name="fixed-price-projects"></a><span data-ttu-id="925c9-155">Rögzített árú projektek</span><span class="sxs-lookup"><span data-stu-id="925c9-155">Fixed-price projects</span></span>

<span data-ttu-id="925c9-156">Rögzített árú projektek esetén a részszámlázási tranzakciók alapja lehet közösen meghatározott mérföldkövek, szállítási egység vagy a projektszerződésben meghatározott folyamatalapú számlázás.</span><span class="sxs-lookup"><span data-stu-id="925c9-156">For Fixed-price projects, on-account transactions are based on an agreed-upon milestone, unit of delivery, or progress billing arrangement that is specified in a project contract.</span></span> <span data-ttu-id="925c9-157">Külön sor jön létre a projektvevőtől elvárt minden egyes fizetéshez.</span><span class="sxs-lookup"><span data-stu-id="925c9-157">One line is created for each payment that must be received from the project customer.</span></span> <span data-ttu-id="925c9-158">Nincs szükség levonásokra.</span><span class="sxs-lookup"><span data-stu-id="925c9-158">No deductions are required.</span></span>

### <a name="time-and-material-projects"></a><span data-ttu-id="925c9-159">Idő- és anyagelszámolású projektek</span><span class="sxs-lookup"><span data-stu-id="925c9-159">Time and material projects</span></span>

<span data-ttu-id="925c9-160">Az idő- és anyagelszámolású projektek esetén részszámlajavaslattal számlázhat ki egy előleget a vevőnek vagy más finanszírozási forrásnak.</span><span class="sxs-lookup"><span data-stu-id="925c9-160">For Time and material projects, you can bill a customer or other funding source for a prepayment amount by using an on-account invoice proposal.</span></span> <span data-ttu-id="925c9-161">A részszámlázási tranzakciókat egy sorként adja meg.</span><span class="sxs-lookup"><span data-stu-id="925c9-161">Enter on-account transactions as one line.</span></span> <span data-ttu-id="925c9-162">Opcionális lehetőségként megadhat további sorokat azoknak a levonásoknak, amelyek ellentételezik a vevő által már esetlegesen kifizetett előlegeket.</span><span class="sxs-lookup"><span data-stu-id="925c9-162">You can optionally enter additional lines as deductions to offset any prepayments that the customer has already made.</span></span> <span data-ttu-id="925c9-163">Levonássorok létrehozásához írjon mínusz jelet az összeg elé.</span><span class="sxs-lookup"><span data-stu-id="925c9-163">To create deduction lines, precede the amount with a minus sign.</span></span>

## <a name="invoice-control"></a><span data-ttu-id="925c9-164">Számlaellenőrzés</span><span class="sxs-lookup"><span data-stu-id="925c9-164">Invoice control</span></span>
<span data-ttu-id="925c9-165">A számlaellenőrzés funkció segítségével tudja nyomon követni mind a számlázott, mind a számlanélküli tranzakciókat, valamint azokat az árajánlatokkal összevetni, annak érdekében, hogy az ajánlatkérési szakasztól a lezárásig végig tudja követni a projektjeit.</span><span class="sxs-lookup"><span data-stu-id="925c9-165">You can use invoice control to track both invoiced and non-invoiced transactions, and to analyze those transactions against quotations for an end-to-end view of your projects from the quotation stage to completion.</span></span> <span data-ttu-id="925c9-166">Megtekintheti, hogy mely tranzakciók kerültek elszámolásra egy adott projekthez, illetve, hogy mely sorok kerültek számlázásra.</span><span class="sxs-lookup"><span data-stu-id="925c9-166">You can see which transactions have been charged to a specific project and which lines have been invoiced.</span></span> <span data-ttu-id="925c9-167">Megtekintheti az egyes tranzakciókat is, hogy a feladásuk után módosíthassa őket.</span><span class="sxs-lookup"><span data-stu-id="925c9-167">You can also view individual transactions, so that you can adjust them after they are posted.</span></span>

## <a name="invoicing-fixed-price-projects"></a><span data-ttu-id="925c9-168">Rögzített árú projektek számlázása</span><span class="sxs-lookup"><span data-stu-id="925c9-168">Invoicing Fixed-price projects</span></span>
<span data-ttu-id="925c9-169">Rögzített árú projektek számlázásához meg kell határoznia egy számlázási ütemezést, illetve be kell fejeznie a számlázási eljárást.</span><span class="sxs-lookup"><span data-stu-id="925c9-169">To invoice a Fixed-price project, you must define a billing schedule and complete the invoicing procedure.</span></span>

### <a name="billing-schedule"></a><span data-ttu-id="925c9-170">Számlázási ütemezés</span><span class="sxs-lookup"><span data-stu-id="925c9-170">Billing schedule</span></span>

<span data-ttu-id="925c9-171">A rögzített árú projekteket számlázási ütemezés alapján tudja leszámlázni.</span><span class="sxs-lookup"><span data-stu-id="925c9-171">You can invoice Fixed-price projects on a billing schedule.</span></span> <span data-ttu-id="925c9-172">A számlázási ütemezés meghatározása a projekt egy vagy több mérföldköve alapján történik.</span><span class="sxs-lookup"><span data-stu-id="925c9-172">The billing schedule is defined in terms of one or more milestones for the project.</span></span> <span data-ttu-id="925c9-173">Minden egyes mérföldkő kapcsán tud megadni konkrét dátumot, értékesítési pénznemet, eladási árat és a tevékenységet.</span><span class="sxs-lookup"><span data-stu-id="925c9-173">For each milestone, you can define a specific date, sales currency, sales price, and activity.</span></span> 

<span data-ttu-id="925c9-174">Beállíthatja például az alábbi számlázási ütemezést:</span><span class="sxs-lookup"><span data-stu-id="925c9-174">For example, you can set up the following billing schedule:</span></span>

-   <span data-ttu-id="925c9-175">20 százalék a projektszerződés aláírásakor</span><span class="sxs-lookup"><span data-stu-id="925c9-175">20 percent when the project contract is signed</span></span>
-   <span data-ttu-id="925c9-176">30 százalék az első szállítás alkalmával</span><span class="sxs-lookup"><span data-stu-id="925c9-176">30 percent on first delivery</span></span>
-   <span data-ttu-id="925c9-177">15 százalék a második szállítás alkalmával</span><span class="sxs-lookup"><span data-stu-id="925c9-177">15 percent on second delivery</span></span>
-   <span data-ttu-id="925c9-178">35 százalék a végső szállításkor</span><span class="sxs-lookup"><span data-stu-id="925c9-178">35 percent on final delivery</span></span>

### <a name="invoicing-procedure"></a><span data-ttu-id="925c9-179">A számlázás folyamata</span><span class="sxs-lookup"><span data-stu-id="925c9-179">Invoicing procedure</span></span>

<span data-ttu-id="925c9-180">Ha készen állnak a számlázásra a mérföldkőhöz kapcsolódó kifizetések, a részszámlázott összegek számlázására vonatkozó eljárást kell használnia.</span><span class="sxs-lookup"><span data-stu-id="925c9-180">When the milestone payments are ready to be invoiced, you use the procedure for invoicing on-account amounts.</span></span>

## <a name="vendor-invoicing"></a><span data-ttu-id="925c9-181">Szállítói számlázás</span><span class="sxs-lookup"><span data-stu-id="925c9-181">Vendor invoicing</span></span>
<span data-ttu-id="925c9-182">Ha megrendel egy cikket egy szállítótól és a cikket egy projekthez rendeli, a cikk kapcsán a beszerzési rendeléshez kiválasztott sortulajdonság határozza meg, hogy a rendszer kiszámlázza-e a beszerzett cikket egy vevő felé, vagy sem.</span><span class="sxs-lookup"><span data-stu-id="925c9-182">When you order an item from a vendor and assign the item to a project, the line property that you select for the purchase order line for that item determines whether the purchased item is invoiced to a customer.</span></span> <span data-ttu-id="925c9-183">Ha alapértelmezett sortulajdonságokat állít be, úgy azok a cikk kapcsán megjelennek a beszerzési rendeléssoron (Soradatok &gt; Projekt &gt; Sortulajdonság).</span><span class="sxs-lookup"><span data-stu-id="925c9-183">If you set up default line properties, they are displayed for the item on the purchase order line (Line details &gt; Project &gt; Line property).</span></span> <span data-ttu-id="925c9-184">A sortulajdonságot kétféleképpen tudja módosítani:</span><span class="sxs-lookup"><span data-stu-id="925c9-184">There are two ways to modify the line property:</span></span>

-   <span data-ttu-id="925c9-185">A cikk számlázása a projekt vevője felé: Állítsa a cikkre vonatkozó sortulajdonságot számlázandó értékre a beszerzési megrendelésben, majd állítsa ki a számlát a vevő felé a helyes projektszámlázási módszer alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="925c9-185">Invoice the project's customer for the item: Set the line property for the item to a chargeable value on the purchase order, and then invoice the customer by using the correct project invoicing method.</span></span>
-   <span data-ttu-id="925c9-186">Ne a projekt vevőjének számlázza le a cikket: azaz ne jelölje be a **Számlázható** sortulajdonságot a cikkre vonatkozó beszerzési rendeléssoron.</span><span class="sxs-lookup"><span data-stu-id="925c9-186">Don’t invoice the project's customer for the item: Don’t select the **Chargeable** line property on the purchase order line for the item.</span></span> <span data-ttu-id="925c9-187">Ezután le tudja számlázni a beszerzési rendelést, és nincs további teendője ezzel kapcsolatosan.</span><span class="sxs-lookup"><span data-stu-id="925c9-187">You can then invoice the purchase order, and no further action is required.</span></span>

## <a name="credit-notes"></a><span data-ttu-id="925c9-188">Jóváírások</span><span class="sxs-lookup"><span data-stu-id="925c9-188">Credit notes</span></span>
<span data-ttu-id="925c9-189">Ha egy vevőszámlán negatív összeg szerepel, akkor a program jóváírásként kezeli a számlát.</span><span class="sxs-lookup"><span data-stu-id="925c9-189">When an amount on a customer invoice has a negative value, the invoice is classified as a credit note.</span></span> <span data-ttu-id="925c9-190">A dokumentum nyomtatásakor az a „Jóváírás” címet viseli.</span><span class="sxs-lookup"><span data-stu-id="925c9-190">When the document is printed, it has the title "Credit note."</span></span> 

<span data-ttu-id="925c9-191">Ha egy korábban számlázott összeg visszatérítése céljából jóváírást hoz létre, először ki kell választania a jóváírandó számlázott összeget.</span><span class="sxs-lookup"><span data-stu-id="925c9-191">When you create a credit note to credit an amount that was previously invoiced, you must first select the invoiced amount for crediting.</span></span> <span data-ttu-id="925c9-192">Ezután ugyanazokkal a lépésekkel hozhatja létre a jóváírást, amelyeket a rendes vevőszámlák létrehozására használ.</span><span class="sxs-lookup"><span data-stu-id="925c9-192">You then create a credit note by following the same procedure that you would use to create an ordinary customer invoice.</span></span> <span data-ttu-id="925c9-193">Más szóval ki kell választania azokat a tranzakciókat, amelyeket korábban feladott egy vevőszámlára, majd létre kell hoznia és fel kell adnia egy jóváírási javaslatot.</span><span class="sxs-lookup"><span data-stu-id="925c9-193">In other words, you select the transactions that were previously posted on a customer invoice, and then create and post a credit note proposal.</span></span> 

<span data-ttu-id="925c9-194">Egyazon a dokumentumon jóváírásra kijelölt tranzakciókat, jóváírási tranzakciókat, illetve feladott tranzakciókat is szerepeltethet.</span><span class="sxs-lookup"><span data-stu-id="925c9-194">The same document can include transactions that are selected for crediting, credit transactions, and transactions that have been posted.</span></span> <span data-ttu-id="925c9-195">A dokumentum besorolása számla vagy jóváírás lehet, annak függvényében, hogy a végösszeg pozitív vagy negatív.</span><span class="sxs-lookup"><span data-stu-id="925c9-195">The document is classified as either an invoice or a credit note, depending on whether the total amount is positive or negative.</span></span> 

<span data-ttu-id="925c9-196">Kiszámlázott összeg jóváírásához először ki kell választania a jóváírandó számlázott összeget, majd létre kell hoznia egy jóváírást.</span><span class="sxs-lookup"><span data-stu-id="925c9-196">To credit an invoiced amount, you first select the invoiced amount to credit and then create a credit note.</span></span> <span data-ttu-id="925c9-197">Ezután ugyanazokkal a lépésekkel hozhatja létre a jóváírást, amelyeket a vevői számlák létrehozására használ.</span><span class="sxs-lookup"><span data-stu-id="925c9-197">You create a credit note by following the same procedure that you would use to generate a customer invoice.</span></span> 

<span data-ttu-id="925c9-198">Létrehozhat negatív összegű számlát, ami így jóváírásnak minősülő számla lesz.</span><span class="sxs-lookup"><span data-stu-id="925c9-198">You can create an invoice that has a negative amount, which becomes an invoice that is classified as a credit note.</span></span> <span data-ttu-id="925c9-199">Jóváírás létrehozásához és nyomtatásához ki kell választania azokat a tranzakciókat, amelyeket korábban feladott egy vevői számlára, majd módosítania kell a tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="925c9-199">To create and print a credit note, you must select the transactions that were previously posted for a customer invoice, and then modify the transactions.</span></span> <span data-ttu-id="925c9-200">Amennyiben a jogi személy elsődleges címe nem Németországban van, úgy a számla neve „Javító számla” lesz.</span><span class="sxs-lookup"><span data-stu-id="925c9-200">Unless the primary address of the legal entity is in Germany, the title of the invoice will be "Corrective invoice."</span></span>



