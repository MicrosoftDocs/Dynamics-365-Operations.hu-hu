---
title: "Aláírók beállítása nyomtatási űrlapokhoz"
description: "A Cseh Köztársaság, Észtország, Magyarország, Litvánia, Lettország, Lengyelország és Oroszország területén működő jogalanyok esetén beállíthat aláírókat és beosztásokat a dokumentumokat, például számlákat és készpénzutalványokat nyomtató szállítók és vevők számára."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 263464
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 89a4e44144b8cf90e3aa0cabfffb4ed62ef71e40
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-signers-for-print-forms"></a><span data-ttu-id="e9fc2-103">Aláírók beállítása nyomtatási űrlapokhoz</span><span class="sxs-lookup"><span data-stu-id="e9fc2-103">Set up signers for print forms</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="e9fc2-104">A Cseh Köztársaság, Észtország, Magyarország, Litvánia, Lettország, Lengyelország és Oroszország területén működő jogalanyok esetén beállíthat aláírókat és beosztásokat a dokumentumokat, például számlákat és készpénzutalványokat nyomtató szállítók és vevők számára.</span><span class="sxs-lookup"><span data-stu-id="e9fc2-104">For legal entities in Czech Republic, Estonia, Hungary, Lithuania, Latvia, Poland, and Russia, you can set up signers and titles for customers and vendors that print documents such as invoices and cash orders.</span></span>

<a name="set-up-default-values"></a><span data-ttu-id="e9fc2-105">Alapértelmezett értékek beállítása</span><span class="sxs-lookup"><span data-stu-id="e9fc2-105">Set up default values</span></span>
---------------------

<span data-ttu-id="e9fc2-106">Aláírók megadásához egy vállalat által kinyomtatott dokumentumokhoz használja a **Tisztviselők** oldalt.</span><span class="sxs-lookup"><span data-stu-id="e9fc2-106">To set up signers for the documents that a company prints, use the **Officials** page.</span></span> <span data-ttu-id="e9fc2-107">Beállíthat aláírókat és a beosztásaikat mind a vállalat, mind a vevők vagy szállítók számára, a dokumentum típusától függően.</span><span class="sxs-lookup"><span data-stu-id="e9fc2-107">You can set up signers and their titles both for the company and for customers or vendors, depending on the document type.</span></span> <span data-ttu-id="e9fc2-108">Az alábbi táblázat ismerteti a **Tisztviselők** oldalon elérhető lapokat.</span><span class="sxs-lookup"><span data-stu-id="e9fc2-108">The following table describes the tabs on the **Officials** page.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9fc2-109">Lap</span><span class="sxs-lookup"><span data-stu-id="e9fc2-109">Tab</span></span></th>
<th><span data-ttu-id="e9fc2-110">Leírás</span><span class="sxs-lookup"><span data-stu-id="e9fc2-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="e9fc2-111">Általános</span><span class="sxs-lookup"><span data-stu-id="e9fc2-111">General</span></span></td>
<td><span data-ttu-id="e9fc2-112">Adjon hozzá beosztásokat és kapcsolódó információkat az aláírókhoz (igazgató és főkönyvelő), akik az összes típusú dokumentumot aláírhatják.</span><span class="sxs-lookup"><span data-stu-id="e9fc2-112">Add positions and related information for signers (Director and Chief accountant) who can sign print documents of all types.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e9fc2-113">Főkönyv</span><span class="sxs-lookup"><span data-stu-id="e9fc2-113">Ledger</span></span></td>
<td><span data-ttu-id="e9fc2-114">Adjon hozzá beosztásokat és kapcsolódó információkat az aláírókhoz, akik a következő, pénzforgalomhoz kapcsolódó belső pénzügyi dokumentumokat írhatják alá:</span><span class="sxs-lookup"><span data-stu-id="e9fc2-114">Add the position and related information for signers who can sign the following internal financial documents that are related to cash flow:</span></span>
<ul>
<li><span data-ttu-id="e9fc2-115">Pénztárbizonylatok</span><span class="sxs-lookup"><span data-stu-id="e9fc2-115">Cash slips</span></span></li>
<li><span data-ttu-id="e9fc2-116">Előzetes jelentés</span><span class="sxs-lookup"><span data-stu-id="e9fc2-116">Advance report</span></span></li>
<li><span data-ttu-id="e9fc2-117">Pénztárbizonylati oldal</span><span class="sxs-lookup"><span data-stu-id="e9fc2-117">Page of cash book</span></span></li>
<li><span data-ttu-id="e9fc2-118">Számlálási kivonat</span><span class="sxs-lookup"><span data-stu-id="e9fc2-118">Count statement</span></span></li>
<li><span data-ttu-id="e9fc2-119">Halasztások*</span><span class="sxs-lookup"><span data-stu-id="e9fc2-119">Deferrals*</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e9fc2-120">Értékesítési rendelések</span><span class="sxs-lookup"><span data-stu-id="e9fc2-120">Sales orders</span></span></td>
<td><span data-ttu-id="e9fc2-121">Adjon hozzá beosztásokat és kapcsolódó információkat az aláírókhoz, akik a következő, vevőkhöz kapcsolódó, kimenő elsődleges dokumentumokat írhatják alá:</span><span class="sxs-lookup"><span data-stu-id="e9fc2-121">Add positions and related information for signers who can sign the following outgoing primary documents that are related to customers:</span></span>
<ul>
<li><span data-ttu-id="e9fc2-122">Kifizetendő számla*</span><span class="sxs-lookup"><span data-stu-id="e9fc2-122">Invoice for payment*</span></span></li>
<li><span data-ttu-id="e9fc2-123">Számla</span><span class="sxs-lookup"><span data-stu-id="e9fc2-123">Invoice</span></span></li>
<li><span data-ttu-id="e9fc2-124">Számviteli számla*</span><span class="sxs-lookup"><span data-stu-id="e9fc2-124">Facture*</span></span></li>
<li><span data-ttu-id="e9fc2-125">Számla - jóváírás</span><span class="sxs-lookup"><span data-stu-id="e9fc2-125">Invoice - credit-note</span></span></li>
<li><span data-ttu-id="e9fc2-126">Számviteli számla - jóváírás*</span><span class="sxs-lookup"><span data-stu-id="e9fc2-126">Facture - credit-note*</span></span></li>
<li><span data-ttu-id="e9fc2-127">Adótranzakció - pénzügyi dokumentum (ügyfél)*</span><span class="sxs-lookup"><span data-stu-id="e9fc2-127">Tax transaction facture (client)*</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e9fc2-128">Beszerzési rendelések</span><span class="sxs-lookup"><span data-stu-id="e9fc2-128">Purchase orders</span></span></td>
<td><span data-ttu-id="e9fc2-129">Adjon hozzá beosztásokat és kapcsolódó információkat az aláírókhoz, akik a következő, szállítókhoz kapcsolódó, bejövő elsődleges dokumentumokat írhatják alá:</span><span class="sxs-lookup"><span data-stu-id="e9fc2-129">Add positions and related information for signers who can sign the following incoming primary documents that are related to vendors:</span></span>
<ul>
<li><span data-ttu-id="e9fc2-130">Számla</span><span class="sxs-lookup"><span data-stu-id="e9fc2-130">Invoice</span></span></li>
<li><span data-ttu-id="e9fc2-131">Számviteli számla*</span><span class="sxs-lookup"><span data-stu-id="e9fc2-131">Facture*</span></span></li>
<li><span data-ttu-id="e9fc2-132">Számla - jóváírás</span><span class="sxs-lookup"><span data-stu-id="e9fc2-132">Invoice - credit-note</span></span></li>
<li><span data-ttu-id="e9fc2-133">Számviteli számla - jóváírás*</span><span class="sxs-lookup"><span data-stu-id="e9fc2-133">Facture - credit-note*</span></span></li>
<li><span data-ttu-id="e9fc2-134">Kifizetendő számla*</span><span class="sxs-lookup"><span data-stu-id="e9fc2-134">Invoice for payment*</span></span></li>
<li><span data-ttu-id="e9fc2-135">Adótranzakció - pénzügyi dokumentum (szállító)*</span><span class="sxs-lookup"><span data-stu-id="e9fc2-135">Tax transaction facture (vendor)*</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e9fc2-136">Készletcikk kezelése</span><span class="sxs-lookup"><span data-stu-id="e9fc2-136">Inventory item management</span></span></td>
<td><span data-ttu-id="e9fc2-137">Adjon hozzá beosztásokat és kapcsolódó információkat az aláírókhoz, akik a következő raktározási bizonylatokat írhatják alá, amikor materiális eszköz kiadására kerül sor vevő részére vagy bevételezésére szállítótól:</span><span class="sxs-lookup"><span data-stu-id="e9fc2-137">Add positions and related information for signers who can sign the following warehouse documents when tangible assets are issued to a customer or received from a vendor:</span></span>
<ul>
<li><span data-ttu-id="e9fc2-138">Kiadási bizonylat értékesítési rendeléshez (M-15)*</span><span class="sxs-lookup"><span data-stu-id="e9fc2-138">Issue slip for sales order (M-15)*</span></span></li>
<li><span data-ttu-id="e9fc2-139">Bevételezési</span><span class="sxs-lookup"><span data-stu-id="e9fc2-139">Rmb.</span></span> <span data-ttu-id="e9fc2-140">pénztárbizonylat / befizetési utalvány</span><span class="sxs-lookup"><span data-stu-id="e9fc2-140">slip/Receipt order</span></span></li>
<li><span data-ttu-id="e9fc2-141">Kiadási bizonylat átmozgatási rendeléshez (M-15)*</span><span class="sxs-lookup"><span data-stu-id="e9fc2-141">Issue slip for transfer order (M-15)*</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e9fc2-142">\* (Ez az dokumentumtípus csak a oroszországi elsődleges címmel rendelkező jogi személyek számára elérhető.)</span><span class="sxs-lookup"><span data-stu-id="e9fc2-142">\* This document type is available only for legal entities that have their primary address in Russia.</span></span> <span data-ttu-id="e9fc2-143">Az alábbi táblázat ismerteti a **Tisztviselők** oldalon elérhető mezőket.</span><span class="sxs-lookup"><span data-stu-id="e9fc2-143">The following table describes the fields on the **Officials** page.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9fc2-144">Mező</span><span class="sxs-lookup"><span data-stu-id="e9fc2-144">Field</span></span></th>
<th><span data-ttu-id="e9fc2-145">Leírás</span><span class="sxs-lookup"><span data-stu-id="e9fc2-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="e9fc2-146">Pozíció</span><span class="sxs-lookup"><span data-stu-id="e9fc2-146">Position</span></span></td>
<td><span data-ttu-id="e9fc2-147">Válassza ki az aláíró beosztását.</span><span class="sxs-lookup"><span data-stu-id="e9fc2-147">Select the signer’s post title.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e9fc2-148">Név</span><span class="sxs-lookup"><span data-stu-id="e9fc2-148">Name</span></span></td>
<td><span data-ttu-id="e9fc2-149">Válassza ki az aláíró nevét.</span><span class="sxs-lookup"><span data-stu-id="e9fc2-149">Select the signer’s name.</span></span> <span data-ttu-id="e9fc2-150">A listán szereplő nevek vagy a Kapcsolattartók táblából, vagy az Alkalmazottak táblából származnak az aláíró típusától függően (ez azt jelenti, attól függően, hogy az <strong>A mi</strong> jelölőnégyzet be van-e jelölve).</span><span class="sxs-lookup"><span data-stu-id="e9fc2-150">The names in the list come from either the Contacts table or the Employees table, depending on the type of signer (that is, depending on whether the <strong>Our</strong> check box is selected).</span></span> <span data-ttu-id="e9fc2-151">Ha az aláíró neve nem szerepel a listában, manuálisan adja meg az aláíró teljes nevét.</span><span class="sxs-lookup"><span data-stu-id="e9fc2-151">If the signer's name isn't in the list, manually enter the signer’s full name.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e9fc2-152">Beosztás</span><span class="sxs-lookup"><span data-stu-id="e9fc2-152">Job title</span></span></td>
<td><span data-ttu-id="e9fc2-153">Válassza ki az aláíró munkabeosztását.</span><span class="sxs-lookup"><span data-stu-id="e9fc2-153">Select the signer’s job title.</span></span> <span data-ttu-id="e9fc2-154">Ha az aláíró beosztása nem szerepel a listában, manuálisan adja meg az aláíró beosztását.</span><span class="sxs-lookup"><span data-stu-id="e9fc2-154">If the signer’s title isn't in the list, manually enter the signer’s title.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e9fc2-155">Számlakód</span><span class="sxs-lookup"><span data-stu-id="e9fc2-155">Account code</span></span></td>
<td><span data-ttu-id="e9fc2-156">Válassza ki, hogy az aláíró aláírhatja-e a kiválasztott dokumentumtípus összes dokumentumát, vagy csak egy adott vevő vagy szállító dokumentumait.</span><span class="sxs-lookup"><span data-stu-id="e9fc2-156">Select whether the signer can sign all documents of the selected document type, or only documents for a specific customer or vendor.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e9fc2-157">Számlakapcsolat</span><span class="sxs-lookup"><span data-stu-id="e9fc2-157">Account relation</span></span></td>
<td><span data-ttu-id="e9fc2-158">Válassza ki a vevői vagy szállítói számlát, amely a kijelölt számlakódhoz kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="e9fc2-158">Select the customer or vendor account that is related to the selected account code.</span></span> <span data-ttu-id="e9fc2-159">Ez a mező csak akkor érhető el, ha a <strong>Rekord</strong> lehetőséget választja a <strong>Számlakód</strong> mezőben.</span><span class="sxs-lookup"><span data-stu-id="e9fc2-159">This field is available only if you select <strong>Record</strong> in the <strong>Account code</strong> field.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e9fc2-160">A mi</span><span class="sxs-lookup"><span data-stu-id="e9fc2-160">Our</span></span></td>
<td><span data-ttu-id="e9fc2-161">A bejelölt jelölőnégyzet azt jelzi, hogy a pozíció belső.</span><span class="sxs-lookup"><span data-stu-id="e9fc2-161">A selected check box indicates that the position is internal.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e9fc2-162">Hozzárendelés raktárhoz</span><span class="sxs-lookup"><span data-stu-id="e9fc2-162">Association with warehouse</span></span></td>
<td><span data-ttu-id="e9fc2-163">Válassza ki, hogy az aláíró az összes raktárhoz hozzá van-e rendelve, vagy csak egy adott raktárhoz.</span><span class="sxs-lookup"><span data-stu-id="e9fc2-163">Select whether the signer is assigned to all warehouses or only a specific warehouse.</span></span> <span data-ttu-id="e9fc2-164">Az alábbi lehetőségek közül választhat:</span><span class="sxs-lookup"><span data-stu-id="e9fc2-164">The following options are available:</span></span>
<ul>
<li><span data-ttu-id="e9fc2-165"><strong>Minden</strong> – az aláíró az összes raktárhoz hozzá van rendelve.</span><span class="sxs-lookup"><span data-stu-id="e9fc2-165"><strong>All</strong> – The signer is assigned to all warehouses.</span></span></li>
<li><span data-ttu-id="e9fc2-166"><strong>Rekord</strong> – az aláíró adott raktárhoz van hozzárendelve.</span><span class="sxs-lookup"><span data-stu-id="e9fc2-166"><strong>Record</strong> – The signer is assigned to a specific warehouse.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e9fc2-167">Raktár</span><span class="sxs-lookup"><span data-stu-id="e9fc2-167">Warehouse</span></span></td>
<td><span data-ttu-id="e9fc2-168">Válassza ki a raktárkódot, amely megfelel annak a raktárnak, amelyhez az aláíró hozzá van rendelve.</span><span class="sxs-lookup"><span data-stu-id="e9fc2-168">Select the warehouse code that corresponds to the warehouse that the signer is assigned to.</span></span> <span data-ttu-id="e9fc2-169">Ez a mező csak akkor érhető el, ha a <strong>Rekord</strong> lehetőséget választja a <strong>Hozzárendelés raktárhoz</strong> mezőben.</span><span class="sxs-lookup"><span data-stu-id="e9fc2-169">This field is available only if you select <strong>Record</strong> in the <strong>Association with warehouse</strong> field.</span></span></td>
</tr>
</tbody>
</table>

## <a name="set-up-a-number-sequence-code-for-officials"></a><span data-ttu-id="e9fc2-170">Állítsa be a hivatalnokok számsorozatkódját</span><span class="sxs-lookup"><span data-stu-id="e9fc2-170">Set up a number sequence code for officials</span></span>
<span data-ttu-id="e9fc2-171">Hivatalnokokhoz számsorozatkódot a **Számsorozatok** részben rendelhet hozzá a **Jogi személyek** oldalon.</span><span class="sxs-lookup"><span data-stu-id="e9fc2-171">You can assign a number sequence code for officials in the **Number sequences** section of the **Legal entities** page.</span></span> <span data-ttu-id="e9fc2-172">Válasszon ki egy számsorozatkódot a **Hivatalnokok munkamenet-azonosítója** hivatkozáshoz.</span><span class="sxs-lookup"><span data-stu-id="e9fc2-172">Select a number sequence code for the **Officials session ID** reference.</span></span>

## <a name="modify-signers-in-primary-documents"></a><span data-ttu-id="e9fc2-173">Elsődleges dokumentumok aláíróinak módosítása</span><span class="sxs-lookup"><span data-stu-id="e9fc2-173">Modify signers in primary documents</span></span>
<span data-ttu-id="e9fc2-174">A Hivatalnokok funkció az előre definiált alapértelmezett aláírókat a Hivatalnokok táblából mutatja.</span><span class="sxs-lookup"><span data-stu-id="e9fc2-174">The Officials functionality shows the default predefined signers from the Officials table.</span></span> <span data-ttu-id="e9fc2-175">A **Számla feladása** oldalon a **Hivatalnokok** lapon módosíthatja az aláíró nevét és beosztását az elsődleges dokumentumon a következő dokumentumtípusoknál:</span><span class="sxs-lookup"><span data-stu-id="e9fc2-175">On the **Posting invoice** page, on the **Officials** tab, you can modify a signer’s name and title on the primary document for the following document types:</span></span>

-   <span data-ttu-id="e9fc2-176">Vevői számla</span><span class="sxs-lookup"><span data-stu-id="e9fc2-176">Customer invoice</span></span>
-   <span data-ttu-id="e9fc2-177">Szállítói számla</span><span class="sxs-lookup"><span data-stu-id="e9fc2-177">Vendor invoice</span></span>
-   <span data-ttu-id="e9fc2-178">Átmozgatási rendelések szállítása</span><span class="sxs-lookup"><span data-stu-id="e9fc2-178">Ship transfer order</span></span>
-   <span data-ttu-id="e9fc2-179">Készpénzutalvány</span><span class="sxs-lookup"><span data-stu-id="e9fc2-179">Cash order</span></span>

<span data-ttu-id="e9fc2-180">**Megjegyzés:** Könyvelt bizonylatoknál a hivatalnokokat nem lehet szerkeszteni.</span><span class="sxs-lookup"><span data-stu-id="e9fc2-180">**Note:** After a document is posted, officials can't be edited.</span></span>



