---
title: Számlák feldolgozása
description: Ez a témakör a kelet-európai számlafeldolgozással kapcsolatban tartalmaz tájékoztatást.
author: v-kikozl
manager: AnnBe
ms.date: 07/21/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters, VendParameters
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-kikozl
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 945b082528109f6f8c9292d2388749bebd4cfba4
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/02/2019
ms.locfileid: "1852488"
---
# <a name="invoice-processing"></a><span data-ttu-id="11127-103">Számlák feldolgozása</span><span class="sxs-lookup"><span data-stu-id="11127-103">Invoice processing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="11127-104">Ez a témakör röviden leír néhány országspecifikus forgatókönyvet, például a közösségi általános forgalmi adó (áfa) és a halasztott áfa vonatkozásában.</span><span class="sxs-lookup"><span data-stu-id="11127-104">This topic briefly describes some country-specific scenarios, such as intra-community value-added tax (VAT) and deferred tax.</span></span> <span data-ttu-id="11127-105">Egyes európai országok számára a jogi követelmények befolyásolják a számlázási folyamatot.</span><span class="sxs-lookup"><span data-stu-id="11127-105">Legal requirements for some European countries affect the invoicing process.</span></span> <span data-ttu-id="11127-106">Ez a témakör a vevői és szállítói számlák feldolgozásáról is információkkal szolgál az említett országokban.</span><span class="sxs-lookup"><span data-stu-id="11127-106">This topic provides also an information about how customer and vendor invoices are processed for these countries.</span></span> 
<table>
<thead>
<tr>
<th><span data-ttu-id="11127-107">Eset</span><span class="sxs-lookup"><span data-stu-id="11127-107">Scenario</span></span></th>
<th><span data-ttu-id="11127-108">Országok</span><span class="sxs-lookup"><span data-stu-id="11127-108">Countries</span></span></th>
<th><span data-ttu-id="11127-109">A funkciómódosítások leírása</span><span class="sxs-lookup"><span data-stu-id="11127-109">Description of the functionality changes</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="11127-110"> Kinnlevőségek és kötelezettségek áfadátumai</span><span class="sxs-lookup"><span data-stu-id="11127-110">Accounts receivable and Accounts payable dates for VAT</span></span></td>
<td><span data-ttu-id="11127-111">Cseh Köztársaság, Lengyelország</span><span class="sxs-lookup"><span data-stu-id="11127-111">Czech Republic, Poland</span></span></td>
<td>
<p><span data-ttu-id="11127-112">Az Európai Unió (EU) országaiból beszerzett áruk esetében áfa-önértékelési kötelezettség áll fenn:</span><span class="sxs-lookup"><span data-stu-id="11127-112">When goods are purchased from European Union (EU) countries, there is an obligation of self-assessment of VAT:</span></span></p>
<ul>
<li><span data-ttu-id="11127-113">A kimeneti áfát abban az áfaidőszakban kell megfizetni, amelyben a számlát kiállították (bizonylatdátum).</span><span class="sxs-lookup"><span data-stu-id="11127-113">The output VAT must be paid in a VAT period where the invoice was issued (document date).</span></span></li>
<li><span data-ttu-id="11127-114">A bejövő áfa nem vonható le a bizonylat bevételezése előtt (áfaregisztráció dátuma).</span><span class="sxs-lookup"><span data-stu-id="11127-114">The input VAT can’t be deducted before the document receipt (VAT register date).</span></span></li>
</ul>
<p><span data-ttu-id="11127-115">Ebben az esetben a következő beállításokat kell megadni a forgatókönyv támogatására:</span><span class="sxs-lookup"><span data-stu-id="11127-115">The following settings should be configured to support this scenario:</span></span></p>
<ul>
<li><span data-ttu-id="11127-116">A <strong>Kötelezettségek paraméterei</strong> oldalon engedélyezze a <strong>Közösségi áfa</strong> és a <strong>Bizonylat dátuma közösségen belüli áfához</strong> paramétereket.</span><span class="sxs-lookup"><span data-stu-id="11127-116">On the <strong>Accounts payable parameters</strong> page, enable the <strong>Intra-community VAT</strong> and <strong>Document date for intra-community VAT</strong> parameters.</span></span></li>
<li><span data-ttu-id="11127-117">Állítson be két áfakódot, egyet, amelynek pozitív az százalékos áfaértéke, és egy másikat, amelynek negatív a százalékos áfaértéke.</span><span class="sxs-lookup"><span data-stu-id="11127-117">Set up two sales tax codes, one that has a positive sales tax percentage and one that has a negative sales tax percentage.</span></span></li>
<li><span data-ttu-id="11127-118">Állítson be egy áfacsoportot, amely a pozitív és negatív áfakódokat is tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="11127-118">Set up a sales tax group that includes both the positive and negative sales tax codes.</span></span> <span data-ttu-id="11127-119">A negatív áfakód esetében a <strong>Közösségen belüli áfa</strong> paraméter beállítása legyen <strong>Igen</strong>.</span><span class="sxs-lookup"><span data-stu-id="11127-119">For the negative sales tax code, set the <strong>Intracommunity VAT</strong> parameter to <strong>Yes</strong>.</span></span></li>
</ul>
<p><span data-ttu-id="11127-120">A sikeres beállítás után a beszerzéseknek két feladott áfatranzakciója lesz:</span><span class="sxs-lookup"><span data-stu-id="11127-120">After successful setup, purchases will have two posted sales tax transactions:</span></span></p>
<ul>
<li><span data-ttu-id="11127-121">A pozitív tranzakció, amelynél az irány a <strong>visszaigényelhető áfa</strong>, és az áfajegyzék dátuma megegyezik a számla feladási dátuma lap dátumával.</span><span class="sxs-lookup"><span data-stu-id="11127-121">A positive transaction that has a direction of <strong>sales tax receivable</strong> and a VAT register date that equals the date from the invoice posting page.</span></span></li>
<li><span data-ttu-id="11127-122">A negatív tranzakció, amelynél az irány a <strong>befizetendő áfa</strong>, és az áfajegyzék dátuma megegyezik a bizonylat dátumával.</span><span class="sxs-lookup"><span data-stu-id="11127-122">A negative transaction that has a direction of <strong>sales tax payable</strong> and a VAT register date that equals the document date.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="11127-123">Értékesítési bizonylat dátumának módosítása.</span><span class="sxs-lookup"><span data-stu-id="11127-123">Modify a sales document date.</span></span></td>
<td><span data-ttu-id="11127-124">Az összes közép-kelet-európai ország</span><span class="sxs-lookup"><span data-stu-id="11127-124">All Eastern European countries</span></span></td>
<td><p><span data-ttu-id="11127-125">Módosíthatja a projektszámla <strong>Dokumentumdátum</strong> mezőjét.</span><span class="sxs-lookup"><span data-stu-id="11127-125">You can modify the <strong>Document date</strong> field on a project invoice.</span></span> <span data-ttu-id="11127-126">Ez a dátum megjelenik a nyomtatott számlán.</span><span class="sxs-lookup"><span data-stu-id="11127-126">This date appears on the printed invoice.</span></span></p>
<p><span data-ttu-id="11127-127"><strong>Dokumentumdátum</strong> mező a <strong>Számla feladása</strong> és a <strong>Szabadszöveges számla</strong> oldalakon is van.</span><span class="sxs-lookup"><span data-stu-id="11127-127">There is also a <strong>Document date</strong> field on the <strong>Posting invoice</strong> and <strong>Free text invoice</strong> pages.</span></span> <span data-ttu-id="11127-128">Számlák feladása után a dokumentum dátuma megjelenik a számla fejlécében.</span><span class="sxs-lookup"><span data-stu-id="11127-128">After you post an invoice, the document date appears on the invoice header.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="11127-129">Dokumentum dátuma az árfolyamokhoz</span><span class="sxs-lookup"><span data-stu-id="11127-129">Document date for exchange rates</span></span></td>
<td><span data-ttu-id="11127-130">Lengyelország, Magyarország, Cseh Köztársaság</span><span class="sxs-lookup"><span data-stu-id="11127-130">Poland, Hungary, Czech Republic</span></span></td>
<td>
<p><span data-ttu-id="11127-131">A jogszabályok eltérő szabályokat adnak meg az érvényes árfolyamok kiválasztásához az üzleti tranzakciók számára.</span><span class="sxs-lookup"><span data-stu-id="11127-131">Legislation provides different rules for selecting valid exchange rates for business transactions.</span></span> <span data-ttu-id="11127-132">Az <strong>Árfolyam dátuma</strong> mezőben a <strong>Kinnlevőségek paraméterei</strong> és a <strong>Kötelezettségek paraméterei</strong> lapon, kiválaszthatja a dátumot, amely a könyvelési pénznemben szereplő összegekre használandó a beszerzési és értékesítési bizonylatok számításánál.</span><span class="sxs-lookup"><span data-stu-id="11127-132">In the <strong>Exchange rate date</strong> field on the <strong>Accounts receivable parameters</strong> and <strong>Accounts payable parameters</strong> pages, you can select the date that should be used for amounts in the accounting currency calculation on purchase and sales documents.</span></span> <span data-ttu-id="11127-133">Adatbevitel közben a rendszer beolvassa a tranzakció átváltási árfolyamát ennek a paraméternek az alapján.</span><span class="sxs-lookup"><span data-stu-id="11127-133">During data entry, the system retrieves the exchange rate for the transaction, based on this parameter.</span></span></p>
<blockquote>[!NOTE]<br><span data-ttu-id="11127-134">Az <strong>Árfolyam dátuma</strong> mező beállításakor a <strong>Bizonylat dátuma (csak EU-kereskedelemben)</strong> lehetőségre, a rendszer az áfacsoportot használja.</span><span class="sxs-lookup"><span data-stu-id="11127-134">When you set the <strong>Exchange rate date</strong> field to <strong>Document date (for EU trade only)</strong>, the system uses the sales tax group.</span></span> <span data-ttu-id="11127-135">Az áfacsoportra nézve van egy <strong>EU-kereskedelem</strong> paraméter az <strong>Általános</strong> lapon. Ha az <strong>EU-kereskedelem</strong> beállítás <strong>Igen</strong> az áfacsoport esetében, és a bizonylat fejlécében létezik ez az áfacsoport, a rendszer beolvassa az átváltási árfolyamot a bizonylat dátuma alapján.</span><span class="sxs-lookup"><span data-stu-id="11127-135">For the sales tax group, there is a <strong>EU trade</strong> parameter on the <strong>General</strong> tab. If the <strong>EU trade</strong> option is set to <strong>Yes</strong> for the sales tax group, and if this sales tax group exists on the header of the document, the system retrieves the exchange rate based on the document date.</span></span> <span data-ttu-id="11127-136">Ha az <strong>EU-kereskedelem</strong> beállítás <strong>Nem</strong> az áfacsoport esetében, a rendszer a bizonylat feladási dátuma alapján olvassa be az árfolyamot.</span><span class="sxs-lookup"><span data-stu-id="11127-136">If the <strong>EU trade</strong> option is set to <strong>No</strong> for this sales tax group, the system retrieves the exchange rate based on the posting date of the document.</span></span></blockquote>
</td>
</tr>
<tr>
<td><span data-ttu-id="11127-137">Ügyletek dátumai, áfaregisztrálási dátumok, valamint a bizonylatok és az áfa dátumellenőrzése</span><span class="sxs-lookup"><span data-stu-id="11127-137">Trade dates, VAT register dates, and document and VAT date control</span></span></td>
<td><span data-ttu-id="11127-138">Lengyelország, Magyarország, Cseh Köztársaság</span><span class="sxs-lookup"><span data-stu-id="11127-138">Poland, Hungary, Czech Republic</span></span></td>
<td>
<p><span data-ttu-id="11127-139">Az eladási dátum és a dokumentum kézhezvételi dátuma kötelező az áfabevalláshoz:</span><span class="sxs-lookup"><span data-stu-id="11127-139">The sales date and the document receipt date are required for VAT reporting:</span></span></p>
<ul>
<li><span data-ttu-id="11127-140">Az eladási dátum a kinnlevőséget teljesítő tranzakció dátuma.</span><span class="sxs-lookup"><span data-stu-id="11127-140">The sales date is the fulfilment date of the transaction in Accounts receivable.</span></span></li>
<li><span data-ttu-id="11127-141">A bizonylat kézhezvételi dátuma feljogosít áfacsökkentési kérelemre a kötelezettségekből.</span><span class="sxs-lookup"><span data-stu-id="11127-141">The document receipt date is a date that demonstrates the rights to claim a VAT deduction in Accounts payable.</span></span> <span data-ttu-id="11127-142">Minden kapott bizonylathoz dátum tartozik ellenőrzési célokból.</span><span class="sxs-lookup"><span data-stu-id="11127-142">Each document that is received has a date for audit purposes.</span></span></li>
</ul>
<p><span data-ttu-id="11127-143">A magyar dátum határidők funkció, a cseh kitöltési dátumok és a lengyel áfatételjegyzék dátum funkció teljesíti azt a követelményt, amely az adóinformáció jelentésére vonatkozik a postázási dátumtól eltérő dátum esetében.</span><span class="sxs-lookup"><span data-stu-id="11127-143">The Hungarian functionality for date deadlines, the Czech Republic functionality for fulfill dates, and the Polish functionality for the VAT register date include the requirement for tax information reporting that is based on a date that differs from the posting date.</span></span></p>
<p><span data-ttu-id="11127-144">Az <strong>Áfatételjegyzék dátuma</strong> mező támogatja a követelményt, és több mint 20 oldalon jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="11127-144">The <strong>Date of VAT register</strong> field supports this requirement and appears on more than 20 pages.</span></span> <span data-ttu-id="11127-145">Az oldalak közé tartoznak többek között a következők: naplók, értékesítési rendelések, beszerzési rendelések, szabadszöveges számlák, szállítóiszámla-naplók és projektszámlák.</span><span class="sxs-lookup"><span data-stu-id="11127-145">These pages include journals, sales orders, purchase orders, free-text invoices, vendor invoice journals, and project invoices.</span></span> <span data-ttu-id="11127-146">A dokumentumok frissítése vagy feladása során minden adó feladásra kerül az áfatételjegyzék megfelelő dátumának használatával, és a dátum felkerül az olyan oldalakra, mint a vevői és a szállítói számlanaplók.</span><span class="sxs-lookup"><span data-stu-id="11127-146">When you update or post the documents, all taxes are posted by using the corresponding date of the VAT register, and the date is included on pages such as the customer and vendor invoice journals pages.</span></span></p>
<p><span data-ttu-id="11127-147">Kimondottan Csehország esetében a <strong>Áfatételjegyzék dátuma</strong> mező üresen hagyható a feladás közben, halasztott áfa esetén.</span><span class="sxs-lookup"><span data-stu-id="11127-147">Specifically, for the Czech Republic, the <strong>VAT register date</strong> field can be blank during posting, in the event of postponed VAT posting.</span></span> <span data-ttu-id="11127-148">Ellenkező esetben a mező kötelező, és meg kell adni.</span><span class="sxs-lookup"><span data-stu-id="11127-148">Otherwise, the field is mandatory and must be filled in.</span></span></p>
<p><span data-ttu-id="11127-149">Dátumellenőrzési paraméterek adhatók meg a <strong>Áfacsoportok</strong> lapon:</span><span class="sxs-lookup"><span data-stu-id="11127-149">Date validation parameters can be set on the <strong>Sales tax groups</strong> page:</span></span></p>
<ul>
<li><span data-ttu-id="11127-150">Az <strong>Áfatételjegyzék kitöltésének dátuma</strong> és az <strong>Értékesítési dátum kitöltése</strong> paraméterek a megfelelő dátumok esetében az alapértelmezés szerint használt feltöltési módot jelentik.</span><span class="sxs-lookup"><span data-stu-id="11127-150">The <strong>Date of VAT register filling</strong> and <strong>Sales date filling</strong> parameters are used as a default filling method for appropriate dates.</span></span> <span data-ttu-id="11127-151">Manuális bevitel és több automatikus beviteli módszert is elérhető.</span><span class="sxs-lookup"><span data-stu-id="11127-151">Manual input and several automated input methods are also available.</span></span></li>
<li><span data-ttu-id="11127-152">A <strong>Kötelező értékesítési dátum</strong> mező jelzi, hogy az értékesítési dátumot meg kell-e adni egy értékesítési számla feladása előtt.</span><span class="sxs-lookup"><span data-stu-id="11127-152">The <strong>Mandatory sales date</strong> field indicates whether the sales date must be entered before a sales invoice is posted.</span></span></li>
</ul>
<p><span data-ttu-id="11127-153">Az <strong>Áfatételjegyzék-tranzakciók</strong> lapon a feladott áfatranzakciókhoz kitöltheti az üres áfatételjegyzék-dátumokat.</span><span class="sxs-lookup"><span data-stu-id="11127-153">On the <strong>VAT Register transactions</strong> page, you can fill in blank dates for the VAT register for posted tax transactions.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="11127-154">Halasztott adót tartalmazó áfatételjegyzék-dátumok</span><span class="sxs-lookup"><span data-stu-id="11127-154">VAT register dates that include deferred tax</span></span></td>
<td><span data-ttu-id="11127-155">Magyarország</span><span class="sxs-lookup"><span data-stu-id="11127-155">Hungary</span></span></td>
<td>
<p><span data-ttu-id="11127-156">A magyar adójogszabályok a számlák létrehozásakor megkövetelik, hogy a számla kiállítása vagy a teljesítés legyen, vagy legkésőbb a teljesítése utáni 15. nap.</span><span class="sxs-lookup"><span data-stu-id="11127-156">Hungary tax regulations require that invoices be created at either the time of fulfilment or no later than 15 days after fulfilment.</span></span></p>
<p><span data-ttu-id="11127-157">A teljesítés dátuma az a dátum, amikor a megrendelt szolgáltatásokat teljesítették, vagy amikor leszállították a megrendelt cikkeket.</span><span class="sxs-lookup"><span data-stu-id="11127-157">The fulfilment date is either the date when the ordered services were provided or the date when ordered items were delivered.</span></span> <span data-ttu-id="11127-158">A bizonylatok feladásakor vagy frissítésekor az összes adó feladása a megfelelő áfatételjegyzék-dátum használatával történik, és a dátum megjelenik a megfelelő oldalakon.</span><span class="sxs-lookup"><span data-stu-id="11127-158">When you update or post the documents, all taxes are posted by using the corresponding date of the VAT register, and the date appears on relevant pages.</span></span> <span data-ttu-id="11127-159">Ezenkívül a vonatkozó előírások szerint meg kell felelni a következő feltételeknek a szolgáltatások folyamatos leszállításakor (például bérlet, lízing, tanácsadás vagy fűtés):</span><span class="sxs-lookup"><span data-stu-id="11127-159">Additionally, regulations require that VAT on continuous delivery of services, such as renting, leasing, consulting, and heating, meet the following criteria:</span></span></p>
<ul>
<li><span data-ttu-id="11127-160">Az áfát a számla dátumán erre a célra kijelölt főkönyvi számlára kell könyvelni.</span><span class="sxs-lookup"><span data-stu-id="11127-160">VAT must be posted to a dedicated general ledger account on the invoice date.</span></span></li>
<li><span data-ttu-id="11127-161">Az áfát át kell adni a speciális számlák az áfa kinnlevőségek vagy a kötelezettségek számlára, és szerepelnie kell az áfabevallásban az esedékesség napján.</span><span class="sxs-lookup"><span data-stu-id="11127-161">VAT must be transferred from the special accounts to a sales tax receivable account or a payable account, and must be included in the VAT report on the due date.</span></span></li>
</ul>
<p><span data-ttu-id="11127-162">Ezeknek a követelményeknek a támogatása érdekében a főkönyvi feladások átvihetők a halasztott bejövő adó számlára és a halasztott kimenő adó számlára.</span><span class="sxs-lookup"><span data-stu-id="11127-162">To support these requirements, you can transfer General ledger postings to the Deferred incoming tax account and the Deferred outgoing tax account.</span></span> <span data-ttu-id="11127-163">Azonban először meg kell felelni a következő előfeltételeknek:</span><span class="sxs-lookup"><span data-stu-id="11127-163">However, you must first complete the following prerequisites:</span></span></p>
<ul>
<li><span data-ttu-id="11127-164">A halasztott áfa fizetendő és a halasztott áfa kinnlevőségek főkönyvi számlákat be kell állítani a főkönyvi feladási csoportokban.</span><span class="sxs-lookup"><span data-stu-id="11127-164">Set up the Deferred VAT Payable and Deferred VAT Receivable ledger accounts in ledger posting groups.</span></span></li>
<li><span data-ttu-id="11127-165">Engedélyezni kell a <strong>Halasztott áfa</strong> cikkáfacsoportok paramétert.</span><span class="sxs-lookup"><span data-stu-id="11127-165">Enable the <strong>Deferred VAT</strong> parameter for item sales tax groups.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="11127-166"> Kötelező ÁFA-dátum</span><span class="sxs-lookup"><span data-stu-id="11127-166">Mandatory VAT date</span></span></td>
<td><span data-ttu-id="11127-167">Lengyelország</span><span class="sxs-lookup"><span data-stu-id="11127-167">Poland</span></span></td>
<td>
<p><span data-ttu-id="11127-168">Előírhatja, hogy az áfatételjegyzék dátuma szerepeljen a beszerzési és értékesítési tranzakciórekordokban.</span><span class="sxs-lookup"><span data-stu-id="11127-168">You can require that the date of the VAT register be included in purchase and sales transaction records.</span></span> <span data-ttu-id="11127-169">Emiatt az áfatételjegyzék dátuma rögzíthető a tranzakció feladása előtt.</span><span class="sxs-lookup"><span data-stu-id="11127-169">Therefore, the date of the VAT register can be captured before a transaction is posted.</span></span> <span data-ttu-id="11127-170">A funkció segítségével elkerülheti, hogy több tranzakciót kelljen kezelni az időszak végén.</span><span class="sxs-lookup"><span data-stu-id="11127-170">This functionality helps you avoid having to handle multiple transactions at the end of the period.</span></span></p>
<p><span data-ttu-id="11127-171">Az <strong>Áfatételjegyzék dátuma</strong> mezőt kötelezővé teheti a vevői vagy szállítói tranzakciók feladása alkalmával.</span><span class="sxs-lookup"><span data-stu-id="11127-171">You can make the <strong>Date of VAT register</strong> field mandatory when customer or vendor transactions are posted.</span></span> <span data-ttu-id="11127-172">A mező kötelezővé tételéhez engedélyezze az <strong>Áfadátum megadása kötelező</strong> beállítást a kapcsolódó vevői vagy szállítói számlára.</span><span class="sxs-lookup"><span data-stu-id="11127-172">To make this field mandatory, enable the <strong>VAT date is required</strong> option for the related customer or vendor account.</span></span></p>
</td>
</tr>
</tbody>
</table>
