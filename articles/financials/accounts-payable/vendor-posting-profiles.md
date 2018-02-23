---
title: "Szállítói feladási profilok"
description: "A szállítói feladási profilok a szállítói tranzakciók főkönyvbe történő feladását szabályozzák."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 24691
ms.assetid: 18def866-7655-4f0b-b299-eec83098d23a
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 95d5bf26c22238753586cf4a7aaf5c26f061a705
ms.openlocfilehash: 8d9a27ecb99265674211a5ec768fe55040b8f5fe
ms.contentlocale: hu-hu
ms.lasthandoff: 02/23/2018

---

# <a name="vendor-posting-profiles"></a><span data-ttu-id="e5e3c-103">Szállítói feladási profilok</span><span class="sxs-lookup"><span data-stu-id="e5e3c-103">Vendor posting profiles</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="e5e3c-104">A szállítói feladási profilok a szállítói tranzakciók főkönyvbe történő feladását szabályozzák.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-104">Vendor posting profiles control the posting of vendor transactions to the general ledger.</span></span>

<a name="vendor-posting-profiles"></a><span data-ttu-id="e5e3c-105">Szállítói feladási profilok</span><span class="sxs-lookup"><span data-stu-id="e5e3c-105">Vendor posting profiles</span></span>
-----------------------

<span data-ttu-id="e5e3c-106">Szállítói feladási profilok lehetővé teszik az Ön számára, hogy a főkönyvi számlákat és dokumentumbeállításokat az összes szállítóhoz, vevő csoporthoz vagy egyetlen szállítóhoz rendelhesse.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-106">Vendor posting profiles enable you to assign general ledger accounts and document settings to all vendors, a group of vendors or a single vendor.</span></span> <span data-ttu-id="e5e3c-107">Ezek a beállítások a beszerzési rendelések, a szállítói számlák és a készpénzes fizetés létrehozásakor használalják.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-107">These settings will be used when you create purchase orders, vendor invoices and cash payments.</span></span> <span data-ttu-id="e5e3c-108">Néhány tranzakcióhoz feladói profilt választhat ki, ami különböző és elsőbbséget élvez azokkal a feladói profilokkal szemben, amelyek a tranzakcióhoz be vannak állítva ezen az oldalon.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-108">For some transactions, you can select a posting profile that differs from and takes precedence over the posting profiles that are set up for transactions in this page.</span></span> <span data-ttu-id="e5e3c-109">Az alapértelmezett feladási profil a Főkönyv és Áfa gyorslapon a Kötelezettségek paramétereinek lapján van megadva.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-109">The default posting profile is defined in the Ledger and Sales Tax fasttab on the Accounts payable parameters page.</span></span> <span data-ttu-id="e5e3c-110">Az alapértelmezett feladási profil automatikusan szerepel majd az új dokumentumok fejlécén, amelyen meg lehet változtatni egy másik feladási profilra, ha szükséges.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-110">The default posting profile is then included automatically on the header of new documents where you can change it to a different posting profile if needed.</span></span>

<span data-ttu-id="e5e3c-111">A tranzakció feladási definíciók lapon a a tranzakció feladási típussal társíthatja a feladásdefiníciókat.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-111">You can also associate posting definitions with transaction posting types in the Transaction posting definitions page.</span></span> <span data-ttu-id="e5e3c-112">A feladásidefiníciók irányítják a a szállítói tranzakciók feladását a főkönyvbe a feladói profilok helyett.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-112">Posting definitions control the posting of vendor transactions to the general ledger instead of posting profiles.</span></span>

## <a name="creating-a-posting-profile"></a><span data-ttu-id="e5e3c-113">Hozzon létre feladási profilt</span><span class="sxs-lookup"><span data-stu-id="e5e3c-113">Creating a posting profile</span></span>
### <a name="setup"></a><span data-ttu-id="e5e3c-114">**Beállítás**</span><span class="sxs-lookup"><span data-stu-id="e5e3c-114">**Setup**</span></span>

<span data-ttu-id="e5e3c-115">Határozza meg a tranzakciók feladásában használt főkönyvet, ami a kijelölt feladási profilt használja.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-115">Specify the ledger accounts that are used in the posting of transactions that use the selected posting profile.</span></span> <span data-ttu-id="e5e3c-116">Válassza ki a kijelölt feladási profil számlakódját, és amennyiben lehetséges, számla- vagy csoportszámát.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-116">Select an account code and, whenever possible, an account or group number for the selected posting profile.</span></span> <span data-ttu-id="e5e3c-117">A feladási folyamat során a program kiválasztja a tranzakció legmegfelelőbb feladási profilját oly módon, hogy megkeresi a legspecifikusabb számlakód-, számlaszám-, illetve csoportszám-kombinációt az alábbi prioritás szerint:</span><span class="sxs-lookup"><span data-stu-id="e5e3c-117">In the posting process, the most appropriate posting profile for each transaction is located by searching for the most specific account code, account number, or group and number combination in the following priority:</span></span>

| <span data-ttu-id="e5e3c-118">**Számla kód** mezőérték</span><span class="sxs-lookup"><span data-stu-id="e5e3c-118">**Account code** field value</span></span> | <span data-ttu-id="e5e3c-119">**Számla/Csoport száma** mezőérték</span><span class="sxs-lookup"><span data-stu-id="e5e3c-119">**Account/Group number** field value</span></span>        | <span data-ttu-id="e5e3c-120">Keresési prioritás</span><span class="sxs-lookup"><span data-stu-id="e5e3c-120">Search priority</span></span> |
|------------------------------|---------------------------------------------|-----------------|
| <span data-ttu-id="e5e3c-121">**Tábla**</span><span class="sxs-lookup"><span data-stu-id="e5e3c-121">**Table**</span></span>                    | <span data-ttu-id="e5e3c-122">Konkrét szállítói számla</span><span class="sxs-lookup"><span data-stu-id="e5e3c-122">Specific vendor account</span></span>                     | <span data-ttu-id="e5e3c-123">1</span><span class="sxs-lookup"><span data-stu-id="e5e3c-123">1</span></span>               |
| <span data-ttu-id="e5e3c-124">**Csoport**</span><span class="sxs-lookup"><span data-stu-id="e5e3c-124">**Group**</span></span>                    | <span data-ttu-id="e5e3c-125">Az a szállítócsoport, amelyhez a szállító van rendelve.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-125">vendor group that is assigned to the vendor</span></span> | <span data-ttu-id="e5e3c-126">2</span><span class="sxs-lookup"><span data-stu-id="e5e3c-126">2</span></span>               |
| <span data-ttu-id="e5e3c-127">**Minden**</span><span class="sxs-lookup"><span data-stu-id="e5e3c-127">**All**</span></span>                      | <span data-ttu-id="e5e3c-128">Üres</span><span class="sxs-lookup"><span data-stu-id="e5e3c-128">Blank</span></span>                                       | <span data-ttu-id="e5e3c-129">3</span><span class="sxs-lookup"><span data-stu-id="e5e3c-129">3</span></span>               |

<span data-ttu-id="e5e3c-130">Ha azt szeretné, hogy a szállítói tranzakciók feladási profiljai megegyezzenek, akkor csak egy feladási profilt állítson be az összes számla kód mezőben.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-130">If you want all vendor transactions to have the same posting profile, set up only one posting profile with All in the Account code field.</span></span> <span data-ttu-id="e5e3c-131">Határozza meg a következő értékeket a feladási profil beállításához:</span><span class="sxs-lookup"><span data-stu-id="e5e3c-131">Specify the following values to set up your posting profile:</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="e5e3c-132">Mező</span><span class="sxs-lookup"><span data-stu-id="e5e3c-132">Field</span></span></th>
<th><span data-ttu-id="e5e3c-133">Leírás</span><span class="sxs-lookup"><span data-stu-id="e5e3c-133">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="e5e3c-134"><strong>Feladási sablon</strong></span><span class="sxs-lookup"><span data-stu-id="e5e3c-134"><strong>Posting profile</strong></span></span></td>
<td><span data-ttu-id="e5e3c-135">Adjon meg egy kódot a feladási profilhoz.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-135">Enter a code for the posting profile.</span></span> <span data-ttu-id="e5e3c-136">Létrehozhat például két feladási profilt, hogy legyen egy nemzeti pénznemet és egy külföldi valutát használó számla a szállítói egyenlegekhez.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-136">For example, you could create two posting profiles to obtain one account for vendor balances in the national currency and another for vendor balances in a foreign currency.</span></span> <span data-ttu-id="e5e3c-137">Hívhatja az egyik számlát "Nemzeti", a másikat "Külföldi" számlának.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-137">You could call one account National and the other Foreign.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e5e3c-138"><strong>Leírás</strong></span><span class="sxs-lookup"><span data-stu-id="e5e3c-138"><strong>Description</strong></span></span></td>
<td><span data-ttu-id="e5e3c-139">Adja meg a feladói profil leírását.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-139">Enter a description of the posting profile.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e5e3c-140"><strong>Számlakód</strong></span><span class="sxs-lookup"><span data-stu-id="e5e3c-140"><strong>Account code</strong></span></span></td>
<td><span data-ttu-id="e5e3c-141">Adja meg, hogy a feladási profil egy adott szállítóra, egy szállítócsoportra vagy az összes szállítóra vonatkozzon-e:</span><span class="sxs-lookup"><span data-stu-id="e5e3c-141">Specify whether the posting profile applies to a specific vendor, a group of vendors, or all vendors:</span></span>
<ul>
<li><span data-ttu-id="e5e3c-142"><strong>Asztal</strong>– A feladási profilok egyetlen szállítóra vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-142"><strong>Table</strong> – The posting profile applies to a single vendor.</span></span> <span data-ttu-id="e5e3c-143">Válassza ki a szállító számlát a Számla/Csoport szám mezőben.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-143">Select the vendor account in the Account/Group number field.</span></span></li>
<li><span data-ttu-id="e5e3c-144"><strong>Csoport</strong>– A feladási profilok szállító csoportra vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-144"><strong>Group</strong> – The posting profile applies to a vendor group.</span></span> <span data-ttu-id="e5e3c-145">Válassza ki a szállító csoportot a Számla/Csoport szám mezőben.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-145">Select the vendor group in the Account/Group number field.</span></span></li>
<li><span data-ttu-id="e5e3c-146"><strong>Összes</strong>– A feladási profilok az összes szállítóra vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-146"><strong>All</strong> – The posting profile applies to all vendors.</span></span> <span data-ttu-id="e5e3c-147">Hagyja üresen a Számla/Csoport száma mezőt.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-147">Leave the Account/Group number field blank.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e5e3c-148"><strong>Számla/csoport száma</strong></span><span class="sxs-lookup"><span data-stu-id="e5e3c-148"><strong>Account/Group number</strong></span></span></td>
<td><span data-ttu-id="e5e3c-149">Ha az Asztal lehetőséget bejelölte a Számla kód mezőben, akkor adja meg annak a feladási profilhoz rendelt szállító számlaszámát.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-149">If Table is selected in the Account code field, select the account number of the vendor that is associated with the posting profile.</span></span> <span data-ttu-id="e5e3c-150">Ha a Csoport lehetőséget választotta, válasszon egy szállítói csoportot.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-150">If Group is selected, select a vendor group.</span></span> <span data-ttu-id="e5e3c-151">Ha az Összes lehetőséget választotta, hagyja ezt a mezőt üresen.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-151">If All is selected, leave this field blank.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e5e3c-152"><strong>Összegzett számla</strong></span><span class="sxs-lookup"><span data-stu-id="e5e3c-152"><strong>Summary account</strong></span></span></td>
<td><span data-ttu-id="e5e3c-153">Válassza ki azt a főkönyvi sámlát, amit a szállító összegző számlajaként használ, amikhez a feladási profil kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-153">Select the ledger account that will be used as the summary account for the vendors that the posting profile relates to.</span></span>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><span data-ttu-id="e5e3c-154"><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Megjegyzés</span><span class="sxs-lookup"><span data-stu-id="e5e3c-154"><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Note</span></span>" alt="Note" id="alert_note" class="cl_IC101471" /><span data-ttu-id="e5e3c-155"><strong>Megjegyzés</strong></span><span class="sxs-lookup"><span data-stu-id="e5e3c-155"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="e5e3c-156">A használt feladási definíciók váltóit választotta ki a főkönyvi paraméterek lapon, a tranzakció szállítói számlákra vonatkozó feladásdefiníciót használja az összegző számla helyett.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-156">If the Use posting definitions toggle is selected in the General ledger parameters page, the transaction posting definition for vendor invoices is used instead of the summary account.</span></span></td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e5e3c-157"><strong>Számla kiegyenlítése</strong></span><span class="sxs-lookup"><span data-stu-id="e5e3c-157"><strong>Settle account</strong></span></span></td>
<td><span data-ttu-id="e5e3c-158">Válassza ki a pénzforgalmi előrejelzéshez használt likviditási főkönyvi számlát.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-158">Select the liquidity ledger account that is used for cash flow forecasts.</span></span> <span data-ttu-id="e5e3c-159">Ez a mező csak akkor érhető el, ha engedélyezve van a pénzforgalmi előrejelzés.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-159">This fields is only available when cash flow forecasting is enabled.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e5e3c-160"><strong>Áfaelőlegek</strong></span><span class="sxs-lookup"><span data-stu-id="e5e3c-160"><strong>Sales tax prepayments</strong></span></span></td>
<td><span data-ttu-id="e5e3c-161">Válassza ki az előre törlesztett adó kifizetések számlaszámát.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-161">Select the account for sales tax payments that are received in advance.</span></span>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><span data-ttu-id="e5e3c-162"><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Megjegyzés</span><span class="sxs-lookup"><span data-stu-id="e5e3c-162"><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Note</span></span>" alt="Note" id="alert_note" class="cl_IC101471" /><span data-ttu-id="e5e3c-163"><strong>Megjegyzés</strong></span><span class="sxs-lookup"><span data-stu-id="e5e3c-163"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="e5e3c-164">A feladási profil, amely akkor használatos, ha be van jelölve a kifizetés előlegként az előlegnapló-bizonylattal rendelkező Feladási profil mezőben a Főkönyvben és a Kötelezettségek paramétereinek áfa területén.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-164">The posting profile that is used when the payment is marked as a prepayment is selected in the Posting profile with prepayment journal voucher field in the Ledger and sales tax area of the Accounts payable parameters page.</span></span></td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e5e3c-165"><strong>Beérkezés</strong></span><span class="sxs-lookup"><span data-stu-id="e5e3c-165"><strong>Arrival</strong></span></span></td>
<td><span data-ttu-id="e5e3c-166">Válassza ki a főkönyvi számlát, amelyre a nem jóváhagyott szállítói számlákkal kapcsolatos információkat feladja.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-166">Select the ledger account that information about unapproved vendor invoices is posted to.</span></span> <span data-ttu-id="e5e3c-167">Az adat a számlajegyzék-naplóban szerepel.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-167">The information is entered in the Invoice register journal.</span></span> <span data-ttu-id="e5e3c-168">Például, egy felhasználó alapvető adatokat ad meg szállítói számlákról, amikor megkapta a számlajegyzéket.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-168">For example, a user enters very basic information about vendor invoices when they are received in the invoice register.</span></span> <span data-ttu-id="e5e3c-169">A számlajegyzék feladásakor a tranzakciók az itt és az Ellenszámla mezőben megadott számlára kerülnek.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-169">When the invoice register is posted, the transactions are posted to the account that is entered here and in the Offset account field.</span></span> <span data-ttu-id="e5e3c-170">A számlák jóváhagyását követően a kötelezettség átkerül a Beérkezés számláról a szállítói összegző számlára.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-170">When the invoices are approved, the debt is transferred from the Arrival account to the vendor summary account.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e5e3c-171"><strong>Ellenszámla</strong></span><span class="sxs-lookup"><span data-stu-id="e5e3c-171"><strong>Offset account</strong></span></span></td>
<td><span data-ttu-id="e5e3c-172">Válassza ki a számlajegyzék segítségével frissített, nem jóváhagyott szállítói számlák kiegyenlítéséhez használt főkönyvet.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-172">Select the ledger account that is used for offsetting unapproved vendor invoices that are updated by using the invoice register.</span></span> <span data-ttu-id="e5e3c-173">Az ellenszámla a beérkezés számlákra feladott tranzakciók ellenszámlájaként viselkedik.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-173">The offset account acts as the offset account for transactions that are posted to arrival accounts.</span></span> <span data-ttu-id="e5e3c-174">Ezért a számla tartalmazza a még nem jóváhagyott szállítói beszerzéseket.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-174">Therefore, the account contains vendor purchases that have not yet been approved.</span></span></td>
</tr>
</tbody>
</table>
 

### <a name="table-restrictions"></a><span data-ttu-id="e5e3c-175">**Táblakorlátozások**</span><span class="sxs-lookup"><span data-stu-id="e5e3c-175">**Table restrictions**</span></span>

<span data-ttu-id="e5e3c-176">Azokhoz a tranzakciókhoz, amelyeket a feladási profil kiválasztott, meghatározzák, hogy a tranzakció automatikusan ki van-e egyenlítve, a kamat ki van-e számítva, és a fizetési felszólítások ki vannak-e állítva.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-176">For transactions that have the selected posting profile, specify whether transactions will be settled automatically, interest will be calculated, and collection letters will be issued.</span></span> <span data-ttu-id="e5e3c-177">Kiválaszthatja a kijelölt feladási profillal rendelkező tranzakciók zárásakor használatos számlát.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-177">You can also select the account that is used when transactions that have the selected posting profile are closed.</span></span>

<span data-ttu-id="e5e3c-178">Határozza meg a következő értékeket a feladási profil beállításához:</span><span class="sxs-lookup"><span data-stu-id="e5e3c-178">Specify the following values to set up your posting profile:</span></span>

| <span data-ttu-id="e5e3c-179">Mező</span><span class="sxs-lookup"><span data-stu-id="e5e3c-179">Field</span></span>          | <span data-ttu-id="e5e3c-180">Leírás</span><span class="sxs-lookup"><span data-stu-id="e5e3c-180">Description</span></span>                                                                                                                                                                                                    |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="e5e3c-181">**Elszámolás**</span><span class="sxs-lookup"><span data-stu-id="e5e3c-181">**Settlement**</span></span> | <span data-ttu-id="e5e3c-182">Válassza ki ezt a lehetőséget a feladási profillal rendelkező tranzakciók automatikus elszámolásának engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-182">Select this option to enable automatic settlement of transactions that have this posting profile.</span></span> <span data-ttu-id="e5e3c-183">Ha ez a lehetőség nincs bejelölve, manuálisan kell rendeznie a tranzakciókat a Nyitott tranzakciók kiegyenlítése oldalon vagy a Vevő kifizetések megadása oldalon.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-183">If this option is cleared, you must manually settle transactions by using the Settle open transactions page.</span></span> |
| <span data-ttu-id="e5e3c-184">**Mégse**</span><span class="sxs-lookup"><span data-stu-id="e5e3c-184">**Cancel**</span></span>     | <span data-ttu-id="e5e3c-185">Válassza ki ezt a lehetőséget, ha szeretné érvényteleníteni a feladási profillal rendelkező tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-185">Select this option if you want to be able to cancel transactions that have this posting profile.</span></span>                                                                                                               |
| <span data-ttu-id="e5e3c-186">**Zárás**</span><span class="sxs-lookup"><span data-stu-id="e5e3c-186">**Close**</span></span>      | <span data-ttu-id="e5e3c-187">Válasszon ki egy másik feladási profilt, amelyre váltani szeretne a jelen feladási profilt használó tranzakciók bezárásakor.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-187">Select a posting profile to change to when transactions that have this posting profile are closed.</span></span> <span data-ttu-id="e5e3c-188">Egy tranzakció akkor minősül bezártnak, ha a teljes kiegyenlítése megtörtént.</span><span class="sxs-lookup"><span data-stu-id="e5e3c-188">A transaction is regarded as closed when it has been settled in full.</span></span>                                       |






