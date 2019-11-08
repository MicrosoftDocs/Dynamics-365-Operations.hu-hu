---
title: Áfa számítása az általános naplósorokhoz
description: Ez a témakör azt mutatja be, hogy hogyan történik az ÁFA számítása a főkönyvi naplósorokban a különböző típusú számlákhoz (szállító, vevő, főkönyv és projekt).
author: EricWang
manager: Ann Beebe
ms.date: 08/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: dd1df355d39065d6959915cc916987d3c58b15a6
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2019
ms.locfileid: "2570194"
---
# <a name="sales-tax-calculation-on-general-journal-lines"></a><span data-ttu-id="db2ff-103">Áfa számítása az általános naplósorokhoz</span><span class="sxs-lookup"><span data-stu-id="db2ff-103">Sales tax calculation on general journal lines</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="db2ff-104">Ez a témakör azt mutatja be, hogy hogyan történik az ÁFA számítása a főkönyvi naplósorokban a különböző típusú számlákhoz (szállító, vevő, főkönyv és projekt).</span><span class="sxs-lookup"><span data-stu-id="db2ff-104">This topic explains how sales taxes are calculated for different types of accounts (vendor, customer, ledger, and project) on general journal lines.</span></span>

<span data-ttu-id="db2ff-105">A folyamat három lépésből állhat:</span><span class="sxs-lookup"><span data-stu-id="db2ff-105">The process can be divided into three steps:</span></span>

- <span data-ttu-id="db2ff-106">Az áfa irányának meghatározása.</span><span class="sxs-lookup"><span data-stu-id="db2ff-106">Determine the sales tax direction.</span></span>

- <span data-ttu-id="db2ff-107">Annak az áfa-összegnek a meghatározása, amely az ideiglenes forgalmi adó táblába kerül.</span><span class="sxs-lookup"><span data-stu-id="db2ff-107">Determine the sales tax amount that will be stored a temporary sales tax table.</span></span>

- <span data-ttu-id="db2ff-108">Az áfa összegének és számlájának meghatározása a bizonylaton.</span><span class="sxs-lookup"><span data-stu-id="db2ff-108">Determine the sales tax amount and account on the voucher.</span></span>

## <a name="determine-the-sales-tax-direction"></a><span data-ttu-id="db2ff-109">Az áfa irányának meghatározása</span><span class="sxs-lookup"><span data-stu-id="db2ff-109">Determine the sales tax direction</span></span>

<span data-ttu-id="db2ff-110">Az ÁFA irányának meghatározási módja a bizonylaton szereplő számla típusától függ.</span><span class="sxs-lookup"><span data-stu-id="db2ff-110">The way that the sales tax direction is determined depends on the type of account in the voucher.</span></span> <span data-ttu-id="db2ff-111">Az ÁFA irányát a számlatípus és az áfakód kombinációja határozza meg.</span><span class="sxs-lookup"><span data-stu-id="db2ff-111">The sales tax direction is determined by the combination of account type and sales tax code.</span></span> <span data-ttu-id="db2ff-112">A következő szakaszok részletezik a lehetőségeket.</span><span class="sxs-lookup"><span data-stu-id="db2ff-112">The following sections the possibilities in more detail.</span></span> 

### <a name="account-type-is-project"></a><span data-ttu-id="db2ff-113">Számla típusa projekt</span><span class="sxs-lookup"><span data-stu-id="db2ff-113">Account type is Project</span></span>

<span data-ttu-id="db2ff-114">Ha egy bizonylat olyan naplósorral rendelkezik, amelyben a számlatípus a **Projekt**, akkor a bizonylat minden naplója ugyanarra az adózási irányra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="db2ff-114">If a voucher has journal line where the account type is **Project**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="db2ff-115">Az alábbi ábra bemutatja a szabályt.</span><span class="sxs-lookup"><span data-stu-id="db2ff-115">The following illustration shows the rule.</span></span> <span data-ttu-id="db2ff-116">A következő pontok a lehetséges adóügyi irányokat mutatják a projekt számlái esetében.</span><span class="sxs-lookup"><span data-stu-id="db2ff-116">The following points show the possible tax directions for project accounts.</span></span>

<span data-ttu-id="db2ff-117">• Ha az áfakód importadó, akkor a forgalmi adó iránya importadó.</span><span class="sxs-lookup"><span data-stu-id="db2ff-117">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="db2ff-118">• Ha az áfakód adómentes, akkor a forgalmi adó iránya adómentes vásárlás.</span><span class="sxs-lookup"><span data-stu-id="db2ff-118">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="db2ff-119">• Ha az áfakód közösségen belüli áfa, akkor a forgalmi adó iránya fizetendő áfa.</span><span class="sxs-lookup"><span data-stu-id="db2ff-119">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="db2ff-120">• Ha az áfakód fordított áfa, akkor a forgalmi adó iránya fizetendő áfa.</span><span class="sxs-lookup"><span data-stu-id="db2ff-120">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="db2ff-121">Ellenkező esetben az áfa iránya a visszaigényelhető áfa.</span><span class="sxs-lookup"><span data-stu-id="db2ff-121">Otherwise, sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="db2ff-122">A következő ábra grafikusan illusztrálja a szabályt.</span><span class="sxs-lookup"><span data-stu-id="db2ff-122">The following diagram illustrates the rule graphically.</span></span>

![A projektekhez tartozó számlák adózási irányának lehetőségei](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-vendor"></a><span data-ttu-id="db2ff-124">Számla típusa szállító</span><span class="sxs-lookup"><span data-stu-id="db2ff-124">Account type is Vendor</span></span>

<span data-ttu-id="db2ff-125">Ha egy bizonylat olyan naplósorral rendelkezik, amelyben a számlatípus a **Szállító**, akkor a bizonylat minden naplója ugyanarra az adózási irányra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="db2ff-125">If a voucher has journal line where the account type is **Vendor**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="db2ff-126">A következő pontok a lehetséges adóügyi irányokat mutatják a szállító számlái esetében.</span><span class="sxs-lookup"><span data-stu-id="db2ff-126">The following points show the possible tax directions for vendor accounts.</span></span> 

<span data-ttu-id="db2ff-127">• Ha az áfakód adómentes, akkor a forgalmi adó iránya adómentes vásárlás.</span><span class="sxs-lookup"><span data-stu-id="db2ff-127">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="db2ff-128">• Ha az áfakód közösségen belüli áfa, akkor a forgalmi adó iránya visszaigényelhető áfa.</span><span class="sxs-lookup"><span data-stu-id="db2ff-128">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="db2ff-129">• Ha az áfakód fordított áfa, akkor a forgalmi adó iránya visszaigényelhető áfa.</span><span class="sxs-lookup"><span data-stu-id="db2ff-129">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Receivable.</span></span>


<span data-ttu-id="db2ff-130">Ellenkező esetben az áfa iránya a fizetendő áfa.</span><span class="sxs-lookup"><span data-stu-id="db2ff-130">Otherwise, sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="db2ff-131">A következő ábra grafikusan illusztrálja a szabályt.</span><span class="sxs-lookup"><span data-stu-id="db2ff-131">The following diagram illustrates the rule graphically.</span></span>

![A szállítóhoz tartozó számlák adózási irányának lehetőségei](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-customer"></a><span data-ttu-id="db2ff-133">Számla típusa ügyfél</span><span class="sxs-lookup"><span data-stu-id="db2ff-133">Account type is Customer</span></span>

<span data-ttu-id="db2ff-134">Ha egy bizonylat olyan naplósorral rendelkezik, amelyben a számlatípus a **Ügyfél**, akkor a bizonylat minden naplója ugyanarra az adózási irányra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="db2ff-134">If a voucher has journal line where the account type is **Customer**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="db2ff-135">A következő pontok a lehetséges adóügyi irányokat mutatják az ügyfél számlái esetében.</span><span class="sxs-lookup"><span data-stu-id="db2ff-135">The following points show the possible tax directions for customer accounts.</span></span>

<span data-ttu-id="db2ff-136">• Ha az áfakód importadó, akkor a forgalmi adó iránya importadó.</span><span class="sxs-lookup"><span data-stu-id="db2ff-136">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="db2ff-137">• Ha az áfakód adómentes, akkor a forgalmi adó iránya adómentes vásárlás.</span><span class="sxs-lookup"><span data-stu-id="db2ff-137">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="db2ff-138">• Ha az áfakód közösségen belüli áfa, akkor a forgalmi adó iránya fizetendő áfa.</span><span class="sxs-lookup"><span data-stu-id="db2ff-138">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="db2ff-139">• Ha az áfakód fordított áfa, akkor a forgalmi adó iránya fizetendő áfa.</span><span class="sxs-lookup"><span data-stu-id="db2ff-139">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="db2ff-140">Ellenkező esetben az áfa iránya a visszaigényelhető áfa.</span><span class="sxs-lookup"><span data-stu-id="db2ff-140">Otherwise, sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="db2ff-141">A következő ábra grafikusan illusztrálja a szabályt.</span><span class="sxs-lookup"><span data-stu-id="db2ff-141">The following diagram illustrates the rule graphically.</span></span>

![Az ügyfélhez tartozó számlák adózási irányának lehetőségei](media/Sales-Tax-Direction-Customer.jpg)

### <a name="account-type-is-ledger"></a><span data-ttu-id="db2ff-143">Számla típusa Főkönyv</span><span class="sxs-lookup"><span data-stu-id="db2ff-143">Account type is Ledger</span></span>

<span data-ttu-id="db2ff-144">A következő ábra bemutatja azt a szabályt, amelyet akkor kell alkalmazni, ha egy bizonylathoz csak olyan naplósorok vannak, amelyeknél a számla típusa **Főkönyv**.</span><span class="sxs-lookup"><span data-stu-id="db2ff-144">The following illustration shows the rule that applies when a voucher has only journal lines where the account type is **Ledger**.</span></span> <span data-ttu-id="db2ff-145">A következő pontok a lehetséges adóügyi irányokat mutatják a főkönyvi számlák esetében.</span><span class="sxs-lookup"><span data-stu-id="db2ff-145">The following points show the possible tax directions for ledger accounts.</span></span>

<span data-ttu-id="db2ff-146">• Ha az áfakód importadó, akkor a forgalmi adó iránya importadó.</span><span class="sxs-lookup"><span data-stu-id="db2ff-146">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="db2ff-147">• Ha az áfakód adómentes, akkor a forgalmi adó iránya adómentes vásárlás.</span><span class="sxs-lookup"><span data-stu-id="db2ff-147">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="db2ff-148">Ellenkező esetben, ha a napló összege tartozik (pozitív), akkor az áfa iránya a visszaigényelhető áfa. Ha a napló összege követel (negatív), akkor a forgalmi adó iránya fizetendő.</span><span class="sxs-lookup"><span data-stu-id="db2ff-148">Otherwise, if the journal amount is debit (positive) ,sales tax direction is Sales Tax Receivable; if the journal amount is credit (negative) ,sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="db2ff-149">A következő ábra grafikusan illusztrálja a szabályt.</span><span class="sxs-lookup"><span data-stu-id="db2ff-149">The following diagram illustrates the rule graphically.</span></span>

![A főkönyvi számlák adózási irányának lehetőségei](media/Sales-Tax-Direction-Ledger.jpg)

#### <a name="override-the-sales-tax-direction"></a><span data-ttu-id="db2ff-151">Az áfa irányának felülírása</span><span class="sxs-lookup"><span data-stu-id="db2ff-151">Override the sales tax direction</span></span>

<span data-ttu-id="db2ff-152">Az áfa irányát felülbírálhatja, ha a bizonylat csak olyan sorokat tartalmaz, amelyekben a számla típusa **Főkönyv**.</span><span class="sxs-lookup"><span data-stu-id="db2ff-152">You can override the sales tax direction when the voucher contains only lines where the account type is **Ledger**.</span></span>

<span data-ttu-id="db2ff-153">Nyissa meg a **Főkönyv \> Számlatükör \> Számlák \> Főszámlák**, és válassza ki a **Jogi személy felülbírálások** gyorslapját.</span><span class="sxs-lookup"><span data-stu-id="db2ff-153">Go to **General ledger \> Chart of accounts \> Accounts \> Main accounts**, and select the **Legal entity overrides** FastTab.</span></span>

## <a name="determine-the-sales-tax-amount"></a><span data-ttu-id="db2ff-154">Az áfa összegének meghatározása.</span><span class="sxs-lookup"><span data-stu-id="db2ff-154">Determine the sales tax amount</span></span>

<span data-ttu-id="db2ff-155">Ez a szakasz bemutatja az áfa összeg jel kiszámításának módját.</span><span class="sxs-lookup"><span data-stu-id="db2ff-155">This section describes how the sales tax amount sign is calculated.</span></span>

![Áfatranzakciók lap](media/sales-tax-amount-sign.jpg)

<span data-ttu-id="db2ff-157">A következő táblázat bemutatja az általános szabályt, amely meghatározza az áfa összegének az ideiglenes áfa táblába történő megjelölését.</span><span class="sxs-lookup"><span data-stu-id="db2ff-157">The following table shows the generic rule for determining the sign of sales tax amounts in the temporary sales tax table.</span></span>

| <span data-ttu-id="db2ff-158">Naplósor összege</span><span class="sxs-lookup"><span data-stu-id="db2ff-158">Journal line amount</span></span> | <span data-ttu-id="db2ff-159">Áfa iránya</span><span class="sxs-lookup"><span data-stu-id="db2ff-159">Sales tax direction</span></span>  | <span data-ttu-id="db2ff-160">Áfaösszeg jel</span><span class="sxs-lookup"><span data-stu-id="db2ff-160">Sales tax amount sign</span></span> |
|---------------------|----------------------|-----------------------|
| <span data-ttu-id="db2ff-161">Pozitív</span><span class="sxs-lookup"><span data-stu-id="db2ff-161">Positive</span></span>            | <span data-ttu-id="db2ff-162">Visszaigényelhető áfa</span><span class="sxs-lookup"><span data-stu-id="db2ff-162">Sales Tax Receivable</span></span> | <span data-ttu-id="db2ff-163">Pozitív</span><span class="sxs-lookup"><span data-stu-id="db2ff-163">Positive</span></span>              |
| <span data-ttu-id="db2ff-164">Pozitív</span><span class="sxs-lookup"><span data-stu-id="db2ff-164">Positive</span></span>            | <span data-ttu-id="db2ff-165">Fizetendő áfa</span><span class="sxs-lookup"><span data-stu-id="db2ff-165">Sales Tax Payable</span></span>    | <span data-ttu-id="db2ff-166">Negatív</span><span class="sxs-lookup"><span data-stu-id="db2ff-166">Negative</span></span>              |
| <span data-ttu-id="db2ff-167">Negatív</span><span class="sxs-lookup"><span data-stu-id="db2ff-167">Negative</span></span>            | <span data-ttu-id="db2ff-168">Visszaigényelhető áfa</span><span class="sxs-lookup"><span data-stu-id="db2ff-168">Sales Tax Receivable</span></span> | <span data-ttu-id="db2ff-169">Negatív</span><span class="sxs-lookup"><span data-stu-id="db2ff-169">Negative</span></span>              |
| <span data-ttu-id="db2ff-170">Negatív</span><span class="sxs-lookup"><span data-stu-id="db2ff-170">Negative</span></span>            | <span data-ttu-id="db2ff-171">Fizetendő áfa</span><span class="sxs-lookup"><span data-stu-id="db2ff-171">Sales Tax Payable</span></span>    | <span data-ttu-id="db2ff-172">Pozitív</span><span class="sxs-lookup"><span data-stu-id="db2ff-172">Positive</span></span>              |

<span data-ttu-id="db2ff-173">Speciális szabály van az olyan bizonylatokhoz, amelyeknél csak **Projekt** vagy **Főkönyv** sor van, amikor a **Főkönyv** sorban be van jelölve egy áfacsoport vagy egy cikkáfacsoport.</span><span class="sxs-lookup"><span data-stu-id="db2ff-173">There is a special rule for vouchers that have only **Project** or **Ledger** lines, when a sales tax group or item sales tax group is selected on the **Ledger** line.</span></span> <span data-ttu-id="db2ff-174">Ezt a szabályt a független áfaszámítási funkciónak a főkönyvi naplókhoz való engedélyezése vezérli.</span><span class="sxs-lookup"><span data-stu-id="db2ff-174">This rule is controlled by Enable independent sales tax calculation feature for general journals.</span></span> <span data-ttu-id="db2ff-175">Ha ez a funkció le van tiltva, akkor a **Főkönyv** sor áfaösszege a **projekt** sorában szereplő tartozik/követel irányt használja.</span><span class="sxs-lookup"><span data-stu-id="db2ff-175">When this feature is turned off, the tax amount of the **Ledger** line uses the debit/credit direction of the **Project** line.</span></span> <span data-ttu-id="db2ff-176">Ha ez a funkció be van kapcsolva, akkor a **Főkönyv** sor áfaösszege a saját tartozik/követel irányát használja.</span><span class="sxs-lookup"><span data-stu-id="db2ff-176">When the feature is turned on, the tax amount of the **Ledger** line uses its own debit/credit direction.</span></span> <span data-ttu-id="db2ff-177">A következő táblázatokban mindegyik eset szabálya látható.</span><span class="sxs-lookup"><span data-stu-id="db2ff-177">The following tables show the rule for each scenario.</span></span> 

<span data-ttu-id="db2ff-178">**Szabály, amikor a funkció be van kapcsolva**</span><span class="sxs-lookup"><span data-stu-id="db2ff-178">**Rule when the feature is turned on**</span></span>

| <span data-ttu-id="db2ff-179">A projekt naplósor összege</span><span class="sxs-lookup"><span data-stu-id="db2ff-179">Journal line amount of project</span></span> | <span data-ttu-id="db2ff-180">Áfa iránya</span><span class="sxs-lookup"><span data-stu-id="db2ff-180">Sales tax direction</span></span>  | <span data-ttu-id="db2ff-181">Áfaösszeg jel</span><span class="sxs-lookup"><span data-stu-id="db2ff-181">Sales tax amount sign</span></span> |
|--------------------------------|----------------------|-----------------------|
| <span data-ttu-id="db2ff-182">Pozitív</span><span class="sxs-lookup"><span data-stu-id="db2ff-182">Positive</span></span>                       | <span data-ttu-id="db2ff-183">Visszaigényelhető áfa</span><span class="sxs-lookup"><span data-stu-id="db2ff-183">Sales Tax Receivable</span></span> | <span data-ttu-id="db2ff-184">Pozitív</span><span class="sxs-lookup"><span data-stu-id="db2ff-184">Positive</span></span>              |
| <span data-ttu-id="db2ff-185">Negatív</span><span class="sxs-lookup"><span data-stu-id="db2ff-185">Negative</span></span>                       | <span data-ttu-id="db2ff-186">Visszaigényelhető áfa</span><span class="sxs-lookup"><span data-stu-id="db2ff-186">Sales Tax Receivable</span></span> | <span data-ttu-id="db2ff-187">Negatív</span><span class="sxs-lookup"><span data-stu-id="db2ff-187">Negative</span></span>              |

<span data-ttu-id="db2ff-188">**Szabály, amikor a funkció ki van kapcsolva**</span><span class="sxs-lookup"><span data-stu-id="db2ff-188">**Rule when the feature is turned off**</span></span>

| <span data-ttu-id="db2ff-189">A főkönyv naplósor összege</span><span class="sxs-lookup"><span data-stu-id="db2ff-189">Journal line amount of ledger</span></span>  | <span data-ttu-id="db2ff-190">Áfa iránya</span><span class="sxs-lookup"><span data-stu-id="db2ff-190">Sales tax direction</span></span>  | <span data-ttu-id="db2ff-191">Áfaösszeg jel</span><span class="sxs-lookup"><span data-stu-id="db2ff-191">Sales tax amount sign</span></span> |
|--------------------------------|----------------------|-----------------------|
| <span data-ttu-id="db2ff-192">Pozitív</span><span class="sxs-lookup"><span data-stu-id="db2ff-192">Positive</span></span>                       | <span data-ttu-id="db2ff-193">Visszaigényelhető áfa</span><span class="sxs-lookup"><span data-stu-id="db2ff-193">Sales Tax Receivable</span></span> | <span data-ttu-id="db2ff-194">Pozitív</span><span class="sxs-lookup"><span data-stu-id="db2ff-194">Positive</span></span>              |
| <span data-ttu-id="db2ff-195">Negatív</span><span class="sxs-lookup"><span data-stu-id="db2ff-195">Negative</span></span>                       | <span data-ttu-id="db2ff-196">Visszaigényelhető áfa</span><span class="sxs-lookup"><span data-stu-id="db2ff-196">Sales Tax Receivable</span></span> | <span data-ttu-id="db2ff-197">Negatív</span><span class="sxs-lookup"><span data-stu-id="db2ff-197">Negative</span></span>              |

## <a name="determine-the-sales-tax-amount-and-account-on-the-voucher"></a><span data-ttu-id="db2ff-198">Az áfa összegének és számlájának meghatározása a bizonylaton</span><span class="sxs-lookup"><span data-stu-id="db2ff-198">Determine the sales tax amount and account on the voucher</span></span>

<span data-ttu-id="db2ff-199">Az áfa feladása alkalmával a fő számlát a főkönyvi feladási csoport profiljából olvassa be a rendszer.</span><span class="sxs-lookup"><span data-stu-id="db2ff-199">When you post sales taxes, the main account is retrieved from the ledger posting group profile.</span></span> <span data-ttu-id="db2ff-200">Ha a forgalmi adók visszaigényelhetők, akkor a rendszer a profilban megadott visszaigényelhető áfa számlát használja.</span><span class="sxs-lookup"><span data-stu-id="db2ff-200">When sales taxes are receivable, the system uses the Sales Tax Receivable account that is specified in the profile.</span></span> <span data-ttu-id="db2ff-201">Ha a forgalmi adók fizetendők, akkor a rendszer a profilban megadott fizetendő áfa számlát használja.</span><span class="sxs-lookup"><span data-stu-id="db2ff-201">For sales taxes that are payable, the system uses Sales Tax Payable account that is specified in the profile.</span></span>

<span data-ttu-id="db2ff-202">A következő táblázat az általános szabályt mutatja be.</span><span class="sxs-lookup"><span data-stu-id="db2ff-202">The following table shows the generic rule.</span></span>

| <span data-ttu-id="db2ff-203">Áfa iránya</span><span class="sxs-lookup"><span data-stu-id="db2ff-203">Sales tax direction</span></span>  | <span data-ttu-id="db2ff-204">Áfaösszeg jel</span><span class="sxs-lookup"><span data-stu-id="db2ff-204">Sales tax amount sign</span></span> | <span data-ttu-id="db2ff-205">Áfaszámla</span><span class="sxs-lookup"><span data-stu-id="db2ff-205">Sales tax account</span></span>      | <span data-ttu-id="db2ff-206">Bizonylat összege</span><span class="sxs-lookup"><span data-stu-id="db2ff-206">Amount on voucher</span></span> |
|----------------------|-----------------------|------------------------|-------------------|
| <span data-ttu-id="db2ff-207">Visszaigényelhető áfa</span><span class="sxs-lookup"><span data-stu-id="db2ff-207">Sales Tax Receivable</span></span> | <span data-ttu-id="db2ff-208">Pozitív</span><span class="sxs-lookup"><span data-stu-id="db2ff-208">Positive</span></span>              | <span data-ttu-id="db2ff-209">Adó kinnlevőségek számla</span><span class="sxs-lookup"><span data-stu-id="db2ff-209">Tax Receivable Account</span></span> | <span data-ttu-id="db2ff-210">Pozitív (tartozik)</span><span class="sxs-lookup"><span data-stu-id="db2ff-210">Positive (Debit)</span></span>  |
| <span data-ttu-id="db2ff-211">Visszaigényelhető áfa</span><span class="sxs-lookup"><span data-stu-id="db2ff-211">Sales Tax Receivable</span></span> | <span data-ttu-id="db2ff-212">Negatív</span><span class="sxs-lookup"><span data-stu-id="db2ff-212">Negative</span></span>              | <span data-ttu-id="db2ff-213">Kinnlevőségek számla</span><span class="sxs-lookup"><span data-stu-id="db2ff-213">Tax Receivable Account</span></span> | <span data-ttu-id="db2ff-214">Negatív (követel)</span><span class="sxs-lookup"><span data-stu-id="db2ff-214">Negative(Credit)</span></span>  |
| <span data-ttu-id="db2ff-215">Fizetendő áfa</span><span class="sxs-lookup"><span data-stu-id="db2ff-215">Sales Tax Payable</span></span>    | <span data-ttu-id="db2ff-216">Pozitív</span><span class="sxs-lookup"><span data-stu-id="db2ff-216">Positive</span></span>              | <span data-ttu-id="db2ff-217">Adó kötelezettségek számla</span><span class="sxs-lookup"><span data-stu-id="db2ff-217">Tax Payable Account</span></span>    | <span data-ttu-id="db2ff-218">Negatív (követel)</span><span class="sxs-lookup"><span data-stu-id="db2ff-218">Negative(Credit)</span></span>  |
| <span data-ttu-id="db2ff-219">Fizetendő áfa</span><span class="sxs-lookup"><span data-stu-id="db2ff-219">Sales Tax Payable</span></span>    | <span data-ttu-id="db2ff-220">Negatív</span><span class="sxs-lookup"><span data-stu-id="db2ff-220">Negative</span></span>              | <span data-ttu-id="db2ff-221">Adó kötelezettségek számla</span><span class="sxs-lookup"><span data-stu-id="db2ff-221">Tax Payable Account</span></span>    | <span data-ttu-id="db2ff-222">Pozitív (tartozik)</span><span class="sxs-lookup"><span data-stu-id="db2ff-222">Positive (Debit)</span></span>  |
