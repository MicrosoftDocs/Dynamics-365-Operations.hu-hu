---
title: Vevők korosítási jelentése
description: A vevők korosítási jelentése a vevőktől esedékes egyenlegeket jeleníti meg időintervallum vagy korosítási időszak alapján rendezve.
author: JodiChristiansen
manager: AnnBe
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 384e44ef07771a174aaed4f8fb893e75b0206da7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5236986"
---
# <a name="customer-aging-report"></a><span data-ttu-id="e52c4-103">Vevők korosítási jelentése</span><span class="sxs-lookup"><span data-stu-id="e52c4-103">Customer aging report</span></span> 

<span data-ttu-id="e52c4-104">A **vevők korosítási** jelentése a vevőktől esedékes egyenlegeket jeleníti meg időintervallum vagy korosítási időszak alapján rendezve.</span><span class="sxs-lookup"><span data-stu-id="e52c4-104">The **Customer aging** report displays the balances that are due from customers, sorted by date interval, or aging period.</span></span>

<span data-ttu-id="e52c4-105">Ennek a jelentésnek a létrehozásakor a következő alapértelmezett paraméterek jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="e52c4-105">When you generate this report, the following default parameters are displayed.</span></span> <span data-ttu-id="e52c4-106">Ezekkel a paraméterekkel szűrheti a jelentésben megjelenített adatokat.</span><span class="sxs-lookup"><span data-stu-id="e52c4-106">You can use these parameters to filter the data that will be displayed on the report.</span></span> <span data-ttu-id="e52c4-107">További tudnivalókért lásd: [Gyűjtemények beállítása](set-up-collections.md).</span><span class="sxs-lookup"><span data-stu-id="e52c4-107">For more information, see [Set up collections](set-up-collections.md).</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e52c4-108">Mező</span><span class="sxs-lookup"><span data-stu-id="e52c4-108">Field</span></span></p></th>
<th><p><span data-ttu-id="e52c4-109">Leírás</span><span class="sxs-lookup"><span data-stu-id="e52c4-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e52c4-110"><strong>Számlázási osztály</strong></span><span class="sxs-lookup"><span data-stu-id="e52c4-110"><strong>Billing classification</strong></span></span></p></td>
<td><p><span data-ttu-id="e52c4-111">Válasszon ki egy vagy több számlázási osztályt, amelyeket a jelentésben kíván szerepeltetni.</span><span class="sxs-lookup"><span data-stu-id="e52c4-111">Select one or more billing classifications to include on the report.</span></span></p>
<div class="alert">

<span data-ttu-id="e52c4-112">**Megjegyzés:** ez a vezérlő csak akkor érhető el, ha az <STRONG>állami szektor</STRONG> konfigurációs kulcs be van állítva.</span><span class="sxs-lookup"><span data-stu-id="e52c4-112">**Note:** This control is available only if the <STRONG>Public Sector</STRONG> configuration key is selected.</span></span></P>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e52c4-113"><strong>Számlázási osztály nélküli tranzakciók belefoglalása</strong></span><span class="sxs-lookup"><span data-stu-id="e52c4-113"><strong>Include transactions without a billing classification</strong></span></span></p></td>
<td><p><span data-ttu-id="e52c4-114">Ha ez a jelölőnégyzet be van jelölve, akkor minden olyan tranzakció megjelenik a jelentésben, amely nem rendelkezik számlázási osztállyal.</span><span class="sxs-lookup"><span data-stu-id="e52c4-114">If this check box is selected, all transactions that do not have a billing classification assigned to them will be displayed on the report.</span></span></p>
<div class="alert">

<span data-ttu-id="e52c4-115">**Megjegyzés:** ez a vezérlő csak akkor érhető el, ha az <STRONG>állami szektor</STRONG> konfigurációs kulcs be van állítva.</span><span class="sxs-lookup"><span data-stu-id="e52c4-115">**Note:** This control is available only if the <STRONG>Public sector</STRONG> configuration key is selected.</span></span></P>

</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e52c4-116"><strong>Korosítás kezdete</strong></span><span class="sxs-lookup"><span data-stu-id="e52c4-116"><strong>Aging as of</strong></span></span></p></td>
<td><p><span data-ttu-id="e52c4-117">Adja meg az aktuális korosítási időszakhoz használt dátumot.</span><span class="sxs-lookup"><span data-stu-id="e52c4-117">Enter the date used on the current aging bucket.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e52c4-118"><strong>Egyenleg ezen a dátumon:</strong></span><span class="sxs-lookup"><span data-stu-id="e52c4-118"><strong>Balance as of</strong></span></span></p></td>
<td><p><span data-ttu-id="e52c4-119">Adja meg azt a dátumot, amelyhez a vevői egyenlegeket látni szeretné.</span><span class="sxs-lookup"><span data-stu-id="e52c4-119">Enter the date to view the customer balances for.</span></span> <span data-ttu-id="e52c4-120">Ezt a tranzakciók esetén fordulónapként is nevezik.</span><span class="sxs-lookup"><span data-stu-id="e52c4-120">This is also known as a cutoff date for transactions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e52c4-121"><strong>Kezdés dátuma</strong></span><span class="sxs-lookup"><span data-stu-id="e52c4-121"><strong>Start date</strong></span></span></p></td>
<td><p><span data-ttu-id="e52c4-122">A jelentésen megjelenő, az első időszakban vagy korosítási időszakban lévő dátum megadása.</span><span class="sxs-lookup"><span data-stu-id="e52c4-122">Enter a date that is in the first period interval or aging period to include on the report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e52c4-123"><strong>Feltételek</strong></span><span class="sxs-lookup"><span data-stu-id="e52c4-123"><strong>Criteria</strong></span></span></p></td>
<td><p><span data-ttu-id="e52c4-124">Válassza ki a jelentés alapjául szolgáló dátumtípust.</span><span class="sxs-lookup"><span data-stu-id="e52c4-124">Select the type of date to base the report on.</span></span></p>
<ul>
<li><p><span data-ttu-id="e52c4-125"><strong>Tranzakció dátuma</strong> – A kiválasztott tranzakció feladási dátuma.</span><span class="sxs-lookup"><span data-stu-id="e52c4-125"><strong>Transaction date</strong> – The posting date of the transactions.</span></span> <span data-ttu-id="e52c4-126">Ez lehet például egy számlázási dátum, amely az esedékességi dátum kiszámításának alapját képezi.</span><span class="sxs-lookup"><span data-stu-id="e52c4-126">For example, this might be an invoice date that is the basis for the calculation of the due date.</span></span></p></li>
<li><p><span data-ttu-id="e52c4-127"><strong>Esedékességi dátum</strong> –  A tranzakcióknak a fizetési feltételeken alapuló esedékességi dátuma.</span><span class="sxs-lookup"><span data-stu-id="e52c4-127"><strong>Due date</strong> – The due date of the transactions, based on the terms of payment.</span></span></p></li>
<li><p><span data-ttu-id="e52c4-128"><strong>Dokumentumdátum</strong>  – A felhasználó által megadott dokumentumdátum, amely az esedékességi dátum kiszámításának alapjául szolgál.</span><span class="sxs-lookup"><span data-stu-id="e52c4-128"><strong>Document date</strong> – A user-defined document date that is the basis for the calculation of the due date.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e52c4-129"><strong>Korosítási időszak definíciója</strong></span><span class="sxs-lookup"><span data-stu-id="e52c4-129"><strong>Aging period definition</strong></span></span></p></td>
<td><p><span data-ttu-id="e52c4-130">Válassza ki a korosítási időszak definícióját.</span><span class="sxs-lookup"><span data-stu-id="e52c4-130">Select an aging period definition.</span></span> <span data-ttu-id="e52c4-131">Az <strong>Intervallum</strong> mező korosítási időszak választásakor nem használható.</span><span class="sxs-lookup"><span data-stu-id="e52c4-131">The <strong>Interval</strong> field is not used if you select an aging period definition.</span></span></p>
<p><span data-ttu-id="e52c4-132">A kinyomtatott jelentésben nem használhatók a 6 korosítási időszaknál hosszabb korosítási időszakdefiníciók.</span><span class="sxs-lookup"><span data-stu-id="e52c4-132">Aging period definitions that have more than six aging periods cannot be used on the printed report.</span></span></p>
<div class="alert">

<span data-ttu-id="e52c4-133">**Megjegyzés:** Az elévülési időszakokat a <STRONG>Korosítási időszakdefiníció</STRONG> oldalon állíthatók be.</span><span class="sxs-lookup"><span data-stu-id="e52c4-133">**Note:** You can set up aging periods on the <STRONG>Aging period definitions</STRONG> page.</span></span></P>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e52c4-134"><strong>Korosítási időszak leírásának nyomtatása</strong></span><span class="sxs-lookup"><span data-stu-id="e52c4-134"><strong>Print aging period description</strong></span></span></p></td>
<td><p><span data-ttu-id="e52c4-135">Válassza az <strong>Igen</strong> lehetőséget, ha azt szeretné, hogy a jelentés minden korosítási időszak oszlopának tetején megjelenjen a korosítási időszak leírása.</span><span class="sxs-lookup"><span data-stu-id="e52c4-135">Select <strong>Yes</strong> to include aging period descriptions at the top of each aging period column on the report.</span></span> <span data-ttu-id="e52c4-136">Válassza a <strong>Nem</strong> lehetőséget, ha a jelentést oszlopfejlécek nélkül szeretné kinyomtatni.</span><span class="sxs-lookup"><span data-stu-id="e52c4-136">Select <strong>No</strong> to print the report without column headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e52c4-137"><strong>Intervallum</strong></span><span class="sxs-lookup"><span data-stu-id="e52c4-137"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="e52c4-138">Határozza meg a használni kívánt időszakot a napok vagy hónapok számának megadásával minden egyes időszakhoz.</span><span class="sxs-lookup"><span data-stu-id="e52c4-138">Define the period to use by entering the number of the day or month units in each period.</span></span> <span data-ttu-id="e52c4-139">Például a korosítási adatok hét alapján történő megtekintéséhez írja a 7 értéket ebbe a mezőbe, és válassza a <strong>Nap</strong> lehetőséget a <strong>Nap/hónap</strong> mezőben.</span><span class="sxs-lookup"><span data-stu-id="e52c4-139">For example, to view aging information by week, enter 7 in this field and select <strong>Day</strong> in the <strong>Day/Mth</strong> field.</span></span></p>
<div class="alert">

<span data-ttu-id="e52c4-140">**Megjegyzés:** A mezőben megadott információkat csak akkor veszi figyelembe a program, ha nem választott korosítási időszakdefiníciót.</span><span class="sxs-lookup"><span data-stu-id="e52c4-140">**Note:** The information that you enter in this field is used only if you have not selected an aging period definition.</span></span> <span data-ttu-id="e52c4-141">Ellenkező esetben a program a korosítási időszakdefiníción határozza meg a nyomtatási irányt.</span><span class="sxs-lookup"><span data-stu-id="e52c4-141">Otherwise, the printing direction is defined on the aging period definition.</span></span></P>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e52c4-142"><strong>Nap/hó</strong></span><span class="sxs-lookup"><span data-stu-id="e52c4-142"><strong>Day/Mth</strong></span></span></p></td>
<td><p><span data-ttu-id="e52c4-143">Annak az egységnek (<strong>Nap</strong> vagy <strong>Hónap</strong>) a kiválasztása, amelyet az <strong>Intervallum</strong> mező periódusának meghatározásakor használ.</span><span class="sxs-lookup"><span data-stu-id="e52c4-143">Select the unit, either <strong>Day</strong> or <strong>Month</strong>, that is used to define the period in the <strong>Interval</strong> field.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e52c4-144"><strong>Nyomtatás iránya</strong></span><span class="sxs-lookup"><span data-stu-id="e52c4-144"><strong>Printing direction</strong></span></span></p></td>
<td><p><span data-ttu-id="e52c4-145">Válassza ki, hogy ki szeretné-e számítani az egyenlegeket, és ki szeretné-e nyomtatni a korosítási jelentéseket a múltbeli vagy a jövőbeli időszakok vonatkozásában.</span><span class="sxs-lookup"><span data-stu-id="e52c4-145">Select whether to calculate balances and print the aging report for past or future periods.</span></span> <span data-ttu-id="e52c4-146">A dátumok kiértékelése az <strong>Egyenleg úgy mint...</strong> mezőben megadott dátumhoz viszonyítással történik.</span><span class="sxs-lookup"><span data-stu-id="e52c4-146">The dates are evaluated relative to the date that is selected in the <strong>Balance as on</strong> field.</span></span> <span data-ttu-id="e52c4-147">Válassza a <strong>Vissza</strong> lehetőséget az elmúlt időszakokra vonatkozó adatok megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="e52c4-147">Select <strong>Backward</strong> to show information for past periods.</span></span> <span data-ttu-id="e52c4-148">A jövőbeni adatok megjelenítéséhez válassza a <strong>Tovább</strong> lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e52c4-148">Select <strong>Forward</strong> to show information for future periods.</span></span></p>
<div class="alert"><span data-ttu-id="e52c4-149">
  
<STRONG>Megjegyzés:</STRONG> A mezőben megadott információkat csak akkor veszi figyelembe a program, ha nem választott korosítási időszakdefiníciót.</span><span class="sxs-lookup"><span data-stu-id="e52c4-149">
  
<STRONG>Note:</STRONG> The information that you enter in this field is used only if you have not selected an aging period definition.</span></span></P>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e52c4-150"><strong>Részletek</strong></span><span class="sxs-lookup"><span data-stu-id="e52c4-150"><strong>Details</strong></span></span></p></td>
<td><p><span data-ttu-id="e52c4-151">Ezzel a jelölőnégyzettel beállíthatja, hogy a jelentésen a megjelenő egyenlegekhez tartozó tranzakciók is listázva legyenek-e rajta.</span><span class="sxs-lookup"><span data-stu-id="e52c4-151">Select to list the transactions that are included in the balances that are shown on the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e52c4-152"><strong>Összegek feltüntetése a tranzakció pénznemében</strong></span><span class="sxs-lookup"><span data-stu-id="e52c4-152"><strong>Include amounts in transaction currency</strong></span></span></p></td>
<td><p><span data-ttu-id="e52c4-153">Jelölje ki ahhoz, hogy az összegek a tranzakció pénznemében megjelenjenek a könyvelési pénznemben megadott összegek mellett.</span><span class="sxs-lookup"><span data-stu-id="e52c4-153">Select to include amounts in the transaction currency in addition to amounts in the accounting currency.</span></span> <span data-ttu-id="e52c4-154">Ha ez a jelölőnégyzet nincs bejelölve, a jelentésben szereplő összegek csak a könyvelési pénznemben jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="e52c4-154">If this check box is not selected, the amounts on the report are displayed only in the accounting currency.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e52c4-155"><strong>Negatív egyenleg</strong></span><span class="sxs-lookup"><span data-stu-id="e52c4-155"><strong>Negative balance</strong></span></span></p></td>
<td><p><span data-ttu-id="e52c4-156">Akkor jelölje be, ha a negatív egyenleggel rendelkező vevői számlákat is figyelembe szeretné venni.</span><span class="sxs-lookup"><span data-stu-id="e52c4-156">Select to include customer accounts that have negative balances.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e52c4-157"><strong>Nulla egyenlegű számlák kizárása</strong></span><span class="sxs-lookup"><span data-stu-id="e52c4-157"><strong>Exclude zero balance accounts</strong></span></span></p></td>
<td><p><span data-ttu-id="e52c4-158">Akkor jelölje be, ha a nullás egyenleggel rendelkező vevői számlákat is figyelembe szeretné venni.</span><span class="sxs-lookup"><span data-stu-id="e52c4-158">Select to exclude customer accounts that have a zero balance.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e52c4-159"><strong>Kifizetés pozicionálása</strong></span><span class="sxs-lookup"><span data-stu-id="e52c4-159"><strong>Payment positioning</strong></span></span></p></td>
<td><p><span data-ttu-id="e52c4-160">Akkor jelölje be, ha meg szeretné jeleníteni a kiegyenlítetlen kifizetéseket.</span><span class="sxs-lookup"><span data-stu-id="e52c4-160">Select to display payments that have not been settled.</span></span> <span data-ttu-id="e52c4-161">Ezek a jelentés első oszlopában láthatók.</span><span class="sxs-lookup"><span data-stu-id="e52c4-161">These are displayed in the first column of the report.</span></span></p></td>
</tr>
</tbody>
</table>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]