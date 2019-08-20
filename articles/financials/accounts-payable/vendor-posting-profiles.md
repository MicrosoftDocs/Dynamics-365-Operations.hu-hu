---
title: Szállítói feladási profilok
description: A szállítói feladási profilok a szállítói tranzakciók főkönyvbe történő feladását szabályozzák.
author: abruer
manager: AnnBe
ms.date: 06/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPosting
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 24691
ms.assetid: 18def866-7655-4f0b-b299-eec83098d23a
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 43450c5f7ab8295b896b591880da9d0bddd955cf
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835337"
---
# <a name="vendor-posting-profiles"></a><span data-ttu-id="01a06-103">Szállítói feladási profilok</span><span class="sxs-lookup"><span data-stu-id="01a06-103">Vendor posting profiles</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="01a06-104">A szállítói feladási profilok a szállítói tranzakciók főkönyvbe történő feladását szabályozzák.</span><span class="sxs-lookup"><span data-stu-id="01a06-104">Vendor posting profiles control the posting of vendor transactions to the general ledger.</span></span>

<a name="vendor-posting-profiles"></a><span data-ttu-id="01a06-105">Szállítói feladási profilok</span><span class="sxs-lookup"><span data-stu-id="01a06-105">Vendor posting profiles</span></span>
-----------------------

<span data-ttu-id="01a06-106">A szállítói feladási profilok lehetővé teszik, hogy a főkönyvi számlákat és dokumentumbeállításokat az összes szállítóhoz, egy szállítói csoporthoz vagy egyetlen szállítóhoz rendelhesse.</span><span class="sxs-lookup"><span data-stu-id="01a06-106">Vendor posting profiles enable you to assign general ledger accounts and document settings to all vendors, a group of vendors, or a single vendor.</span></span> <span data-ttu-id="01a06-107">Ezek a beállítások a beszerzési rendelések, a szállítói számlák és a készpénzes fizetések létrehozásakor használatosak.</span><span class="sxs-lookup"><span data-stu-id="01a06-107">These settings will be used when you create purchase orders, vendor invoices, and cash payments.</span></span> <span data-ttu-id="01a06-108">Néhány tranzakcióhoz feladói profilt választhat ki, és elsőbbséget élvez azokkal a feladói profilokkal szemben, amelyeket ezen az oldalon állít be a tranzakciókhoz, illetve különbözik tőlük.</span><span class="sxs-lookup"><span data-stu-id="01a06-108">For some transactions, you can select a posting profile that differs from and takes precedence over the posting profiles that are set up for transactions on this page.</span></span> <span data-ttu-id="01a06-109">Az alapértelmezett feladási profil a **Főkönyv és áfa** gyorslapon, a **Kötelezettségek paraméterei** lapon van megadva.</span><span class="sxs-lookup"><span data-stu-id="01a06-109">The default posting profile is defined on the **Ledger and Sales Tax** FastTab on the **Accounts payable parameters** page.</span></span> <span data-ttu-id="01a06-110">Az alapértelmezett feladási profil automatikusan szerepel majd az új dokumentumok fejlécén, ahol szükség esetén módosíthatja egy másik feladási profilra.</span><span class="sxs-lookup"><span data-stu-id="01a06-110">The default posting profile is then included automatically on the header of new documents where you can change it to a different posting profile, if needed.</span></span>

<span data-ttu-id="01a06-111">A **Tranzakció-feladásdefiníciók** oldalon a tranzakció feladási típusaihoz társíthatja a feladásdefiníciókat.</span><span class="sxs-lookup"><span data-stu-id="01a06-111">You can also associate posting definitions with transaction posting types on the **Transaction posting definitions** page.</span></span> <span data-ttu-id="01a06-112">A feladásidefiníciók irányítják a a szállítói tranzakciók feladását a főkönyvbe a feladói profilok helyett.</span><span class="sxs-lookup"><span data-stu-id="01a06-112">Posting definitions control the posting of vendor transactions to the general ledger instead of posting profiles.</span></span>

## <a name="creating-a-posting-profile"></a><span data-ttu-id="01a06-113">Hozzon létre feladási profilt</span><span class="sxs-lookup"><span data-stu-id="01a06-113">Creating a posting profile</span></span>
### <a name="setup"></a><span data-ttu-id="01a06-114">**Beállítás**</span><span class="sxs-lookup"><span data-stu-id="01a06-114">**Setup**</span></span>

<span data-ttu-id="01a06-115">Határozza meg a tranzakciók feladásában használt főkönyvet, ami a kijelölt feladási profilt használja.</span><span class="sxs-lookup"><span data-stu-id="01a06-115">Specify the ledger accounts that are used in the posting of transactions that use the selected posting profile.</span></span> <span data-ttu-id="01a06-116">Válassza ki a kijelölt feladási profil számlakódját, és amennyiben lehetséges, számla- vagy csoportszámát.</span><span class="sxs-lookup"><span data-stu-id="01a06-116">Select an account code and, whenever possible, an account or group number for the selected posting profile.</span></span> <span data-ttu-id="01a06-117">A feladási folyamat során a program kiválasztja az egyes tranzakciók legmegfelelőbb feladási profilját oly módon, hogy megkeresi a legspecifikusabb számlakód-, számlaszám-, illetve csoportszám-kombinációt az alábbi prioritás szerint.</span><span class="sxs-lookup"><span data-stu-id="01a06-117">In the posting process, the most appropriate posting profile for each transaction is located by searching for the most specific account code, account number, or group and number combination in the following priority.</span></span>

| <span data-ttu-id="01a06-118">**Számla kód** mezőérték</span><span class="sxs-lookup"><span data-stu-id="01a06-118">**Account code** field value</span></span> | <span data-ttu-id="01a06-119">**Számla/Csoport száma** mezőérték</span><span class="sxs-lookup"><span data-stu-id="01a06-119">**Account/Group number** field value</span></span>        | <span data-ttu-id="01a06-120">Keresési prioritás</span><span class="sxs-lookup"><span data-stu-id="01a06-120">Search priority</span></span> |
|------------------------------|---------------------------------------------|-----------------|
| <span data-ttu-id="01a06-121">**Tábla**</span><span class="sxs-lookup"><span data-stu-id="01a06-121">**Table**</span></span>                    | <span data-ttu-id="01a06-122">Konkrét szállítói számla</span><span class="sxs-lookup"><span data-stu-id="01a06-122">Specific vendor account</span></span>                     | <span data-ttu-id="01a06-123">1</span><span class="sxs-lookup"><span data-stu-id="01a06-123">1</span></span>               |
| <span data-ttu-id="01a06-124">**Csoport**</span><span class="sxs-lookup"><span data-stu-id="01a06-124">**Group**</span></span>                    | <span data-ttu-id="01a06-125">A szállítóhoz rendelt szállítócsoport</span><span class="sxs-lookup"><span data-stu-id="01a06-125">Vendor group that is assigned to the vendor</span></span> | <span data-ttu-id="01a06-126">2</span><span class="sxs-lookup"><span data-stu-id="01a06-126">2</span></span>               |
| <span data-ttu-id="01a06-127">**Összes**</span><span class="sxs-lookup"><span data-stu-id="01a06-127">**All**</span></span>                      | <span data-ttu-id="01a06-128">Üres</span><span class="sxs-lookup"><span data-stu-id="01a06-128">Blank</span></span>                                       | <span data-ttu-id="01a06-129">3</span><span class="sxs-lookup"><span data-stu-id="01a06-129">3</span></span>               |

<span data-ttu-id="01a06-130">Ha azt szeretné, hogy a szállítói tranzakciók feladási profiljai megegyezzenek, akkor csak egy feladási profilt állítson be **Összes** értékkel a **Számlakód** mezőben.</span><span class="sxs-lookup"><span data-stu-id="01a06-130">If you want all vendor transactions to have the same posting profile, set up only one posting profile with **All** in the **Account code** field.</span></span> <span data-ttu-id="01a06-131">Adja meg a következő értékeket a feladási profil beállításához.</span><span class="sxs-lookup"><span data-stu-id="01a06-131">Specify the following values to set up your posting profile.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="01a06-132">Mező</span><span class="sxs-lookup"><span data-stu-id="01a06-132">Field</span></span></th>
<th><span data-ttu-id="01a06-133">Leírás</span><span class="sxs-lookup"><span data-stu-id="01a06-133">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="01a06-134"><strong>Feladási profil</strong></span><span class="sxs-lookup"><span data-stu-id="01a06-134"><strong>Posting profile</strong></span></span></td>
<td><span data-ttu-id="01a06-135">Adjon meg egy kódot a feladási profilhoz.</span><span class="sxs-lookup"><span data-stu-id="01a06-135">Enter a code for the posting profile.</span></span> <span data-ttu-id="01a06-136">Létrehozhat például két feladási profilt, hogy legyen egy nemzeti pénznemet és egy külföldi valutát használó számla a szállítói egyenlegekhez.</span><span class="sxs-lookup"><span data-stu-id="01a06-136">For example, you could create two posting profiles to obtain one account for vendor balances in the national currency and another for vendor balances in a foreign currency.</span></span> <span data-ttu-id="01a06-137">Hívhatja az egyik számlát "Nemzeti", a másikat "Külföldi" számlának.</span><span class="sxs-lookup"><span data-stu-id="01a06-137">You could call one account National and the other Foreign.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="01a06-138"><strong>Leírás</strong></span><span class="sxs-lookup"><span data-stu-id="01a06-138"><strong>Description</strong></span></span></td>
<td><span data-ttu-id="01a06-139">Adja meg a feladói profil leírását.</span><span class="sxs-lookup"><span data-stu-id="01a06-139">Enter a description of the posting profile.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="01a06-140"><strong>Számlakód</strong></span><span class="sxs-lookup"><span data-stu-id="01a06-140"><strong>Account code</strong></span></span></td>
<td><span data-ttu-id="01a06-141">Adja meg, hogy a feladási profil egy adott szállítóra, egy szállítócsoportra vagy az összes szállítóra vonatkozzon-e:</span><span class="sxs-lookup"><span data-stu-id="01a06-141">Specify whether the posting profile applies to a specific vendor, a group of vendors, or all vendors:</span></span>
<ul>
<li><span data-ttu-id="01a06-142"><strong>Asztal</strong>– A feladási profilok egyetlen szállítóra vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="01a06-142"><strong>Table</strong> – The posting profile applies to a single vendor.</span></span> <span data-ttu-id="01a06-143">Válassza ki a szállítói számlát a <strong>Számla/csoport száma</strong> mezőben.</span><span class="sxs-lookup"><span data-stu-id="01a06-143">Select the vendor account in the <strong>Account/Group number</strong> field.</span></span></li>
<li><span data-ttu-id="01a06-144"><strong>Csoport</strong>– A feladási profilok szállító csoportra vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="01a06-144"><strong>Group</strong> – The posting profile applies to a vendor group.</span></span> <span data-ttu-id="01a06-145">Válassza ki a szállítói csoportot a <strong>Számla/csoport száma</strong> mezőben.</span><span class="sxs-lookup"><span data-stu-id="01a06-145">Select the vendor group in the <strong>Account/Group number</strong> field.</span></span></li>
<li><span data-ttu-id="01a06-146"><strong>Összes</strong>– A feladási profilok az összes szállítóra vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="01a06-146"><strong>All</strong> – The posting profile applies to all vendors.</span></span> <span data-ttu-id="01a06-147">Hagyja üresen a <strong>Számla/csoport száma</strong> mezőt.</span><span class="sxs-lookup"><span data-stu-id="01a06-147">Leave the <strong>Account/Group number</strong> field blank.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="01a06-148"><strong>Számla/csoport száma</strong></span><span class="sxs-lookup"><span data-stu-id="01a06-148"><strong>Account/Group number</strong></span></span></td>
<td><span data-ttu-id="01a06-149">Ha a <strong>Tábla</strong> lehetőséget választja ki a <strong>Számlakód</strong> mezőben, akkor válassza ki a feladási profilhoz társított szállító számlaszámát.</span><span class="sxs-lookup"><span data-stu-id="01a06-149">If <strong>Table</strong> is selected in the <strong>Account code</strong> field, select the account number of the vendor that is associated with the posting profile.</span></span> <span data-ttu-id="01a06-150">Ha a <strong>Csoport</strong> lehetőséget választja, válasszon egy szállítói csoportot.</span><span class="sxs-lookup"><span data-stu-id="01a06-150">If <strong>Group</strong> is selected, select a vendor group.</span></span> <span data-ttu-id="01a06-151">Ha az <strong>Összes</strong> lehetőséget választja, hagyja ezt a mezőt üresen.</span><span class="sxs-lookup"><span data-stu-id="01a06-151">If <strong>All</strong> is selected, leave this field blank.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="01a06-152"><strong>Összegzett számla</strong></span><span class="sxs-lookup"><span data-stu-id="01a06-152"><strong>Summary account</strong></span></span></td>
<td><span data-ttu-id="01a06-153">Válassza ki azt a főkönyvi sámlát, amit a szállító összegző számlajaként használ, amikhez a feladási profil kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="01a06-153">Select the ledger account that will be used as the summary account for the vendors that the posting profile relates to.</span></span> <span data-ttu-id="01a06-154">A <strong>Manuális bevitel tiltása</strong> paraméter meg lesz jelölve ehhez a fő számlához.</span><span class="sxs-lookup"><span data-stu-id="01a06-154">The <strong>Do not allow manual entry</strong> parameter for this main account will be marked.</span></span> <span data-ttu-id="01a06-155">Ha ezt követően eltávolítja ezt a számlát a feladási profilból, ellenőrizze a <strong>Manuális bevitel tiltása</strong> beállítást a <strong>Fő számla</strong> oldalon.</span><span class="sxs-lookup"><span data-stu-id="01a06-155">If you subsequently remove this account from the posting profile, validate the <strong>Do not allow manual entry</strong> setting on the <strong>Main accounts</strong> page.</span></span> 
<p><span data-ttu-id="01a06-156"><strong>Megjegyzés:</strong> Ha a <strong>Feladásdefiníciók használata</strong> beállítást kiválasztja a <strong>Főkönyvi paraméterek</strong> oldalon, a rendszer a tranzakciók szállítói számlákhoz tartozó feladásdefinícióját használja majd, nem az összegző számlák definícióját.</span><span class="sxs-lookup"><span data-stu-id="01a06-156"><strong>Note:</strong> If the <strong>Use posting definitions</strong> option is selected on the <strong>General ledger parameters</strong> page, the transaction posting definition for vendor invoices is used instead of the summary account.</span></span></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="01a06-157"><strong>Számla kiegyenlítése</strong></span><span class="sxs-lookup"><span data-stu-id="01a06-157"><strong>Settle account</strong></span></span></td>
<td><span data-ttu-id="01a06-158">Válassza ki a pénzforgalmi előrejelzéshez használt likviditási főkönyvi számlát.</span><span class="sxs-lookup"><span data-stu-id="01a06-158">Select the liquidity ledger account that is used for cash flow forecasts.</span></span> <span data-ttu-id="01a06-159">Ez a mező csak akkor érhető el, ha engedélyezve van a pénzforgalmi előrejelzés.</span><span class="sxs-lookup"><span data-stu-id="01a06-159">This fields is only available when cash flow forecasting is enabled.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="01a06-160"><strong>Áfaelőlegek</strong></span><span class="sxs-lookup"><span data-stu-id="01a06-160"><strong>Sales tax prepayments</strong></span></span></td>
<td><span data-ttu-id="01a06-161">Válassza ki az előre törlesztett adó kifizetések számlaszámát.</span><span class="sxs-lookup"><span data-stu-id="01a06-161">Select the account for sales tax payments that are received in advance.</span></span>
<p><span data-ttu-id="01a06-162"><strong>Megjegyzés:</strong> Azt a feladási profilt, amely akkor használatos, ha a fizetés előlegként van megjelölve, a <strong>Feladás</strong> profilban kell kiválasztani, a <strong>Kötelezettségek paraméterei</strong> oldal <strong>Főkönyv és áfa</strong> területének <strong>Előlegnapló-bizonylat</strong> mezőjében.</span><span class="sxs-lookup"><span data-stu-id="01a06-162"><strong>Note:</strong> The posting profile that is used when the payment is marked as a prepayment is selected in the <strong>Posting</strong> profile with <strong>Prepayment journal voucher</strong> field in the <strong>Ledger and sales tax</strong> area on the <strong>Accounts payable parameters</strong> page.</span></span></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="01a06-163"><strong>Beérkezés</strong></span><span class="sxs-lookup"><span data-stu-id="01a06-163"><strong>Arrival</strong></span></span></td>
<td><span data-ttu-id="01a06-164">Válassza ki a főkönyvi számlát, amelyre a nem jóváhagyott szállítói számlákkal kapcsolatos információkat feladja.</span><span class="sxs-lookup"><span data-stu-id="01a06-164">Select the ledger account that information about unapproved vendor invoices is posted to.</span></span> <span data-ttu-id="01a06-165">Az adat a számlajegyzék-naplóban szerepel.</span><span class="sxs-lookup"><span data-stu-id="01a06-165">The information is entered in the Invoice register journal.</span></span> <span data-ttu-id="01a06-166">Például, egy felhasználó alapvető adatokat ad meg szállítói számlákról, amikor megkapta a számlajegyzéket.</span><span class="sxs-lookup"><span data-stu-id="01a06-166">For example, a user enters very basic information about vendor invoices when they are received in the invoice register.</span></span> <span data-ttu-id="01a06-167">A számlajegyzék feladásakor a tranzakciók az itt és az <strong>Ellenszámla</strong> mezőben megadott számlára kerülnek.</span><span class="sxs-lookup"><span data-stu-id="01a06-167">When the invoice register is posted, the transactions are posted to the account that is entered here and in the <strong>Offset account</strong> field.</span></span> <span data-ttu-id="01a06-168">A számlák jóváhagyását követően a kötelezettség átkerül a beérkezési számláról a szállítói összegző számlára.</span><span class="sxs-lookup"><span data-stu-id="01a06-168">When the invoices are approved, the debt is transferred from the arrival account to the vendor summary account.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="01a06-169"><strong>Ellenszámla</strong></span><span class="sxs-lookup"><span data-stu-id="01a06-169"><strong>Offset account</strong></span></span></td>
<td><span data-ttu-id="01a06-170">Válassza ki a számlajegyzék segítségével frissített, nem jóváhagyott szállítói számlák kiegyenlítéséhez használt főkönyvet.</span><span class="sxs-lookup"><span data-stu-id="01a06-170">Select the ledger account that is used for offsetting unapproved vendor invoices that are updated by using the invoice register.</span></span> <span data-ttu-id="01a06-171">Az ellenszámla a beérkezés számlákra feladott tranzakciók ellenszámlájaként viselkedik.</span><span class="sxs-lookup"><span data-stu-id="01a06-171">The offset account acts as the offset account for transactions that are posted to arrival accounts.</span></span> <span data-ttu-id="01a06-172">Ezért a számla tartalmazza a még nem jóváhagyott szállítói beszerzéseket.</span><span class="sxs-lookup"><span data-stu-id="01a06-172">Therefore, the account contains vendor purchases that have not yet been approved.</span></span></td>
</tr>
</tbody>
</table>


### <a name="table-restrictions"></a><span data-ttu-id="01a06-173">**Táblakorlátozások**</span><span class="sxs-lookup"><span data-stu-id="01a06-173">**Table restrictions**</span></span>

<span data-ttu-id="01a06-174">Azokhoz a tranzakciókhoz, amelyeket a feladási profil kiválasztott, meghatározzák, hogy a tranzakció automatikusan ki van-e egyenlítve, a kamat ki van-e számítva, és a fizetési felszólítások ki vannak-e állítva.</span><span class="sxs-lookup"><span data-stu-id="01a06-174">For transactions that have the selected posting profile, specify whether transactions will be settled automatically, interest will be calculated, and collection letters will be issued.</span></span> <span data-ttu-id="01a06-175">Kiválaszthatja a kijelölt feladási profillal rendelkező tranzakciók zárásakor használatos számlát.</span><span class="sxs-lookup"><span data-stu-id="01a06-175">You can also select the account that is used when transactions that have the selected posting profile are closed.</span></span>

<span data-ttu-id="01a06-176">Adja meg a következő értékeket a feladási profil beállításához</span><span class="sxs-lookup"><span data-stu-id="01a06-176">Specify the following values to set up your posting profile</span></span>

| <span data-ttu-id="01a06-177">Mező</span><span class="sxs-lookup"><span data-stu-id="01a06-177">Field</span></span>          | <span data-ttu-id="01a06-178">Leírás</span><span class="sxs-lookup"><span data-stu-id="01a06-178">Description</span></span>                                                                                                                                                                                                    |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="01a06-179">**Kiegyenlítés**</span><span class="sxs-lookup"><span data-stu-id="01a06-179">**Settlement**</span></span> | <span data-ttu-id="01a06-180">Válassza ki ezt a lehetőséget a feladási profillal rendelkező tranzakciók automatikus elszámolásának engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="01a06-180">Select this option to enable automatic settlement of transactions that have this posting profile.</span></span> <span data-ttu-id="01a06-181">Ha ez a lehetőség nincs bejelölve, manuálisan kell rendeznie a tranzakciókat a **Nyitott tranzakciók kiegyenlítése** oldalon.</span><span class="sxs-lookup"><span data-stu-id="01a06-181">If this option is cleared, you must manually settle transactions by using the **Settle open transactions** page.</span></span> |
| <span data-ttu-id="01a06-182">**Mégse**</span><span class="sxs-lookup"><span data-stu-id="01a06-182">**Cancel**</span></span>     | <span data-ttu-id="01a06-183">Válassza ki ezt a lehetőséget, ha szeretné érvényteleníteni a feladási profillal rendelkező tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="01a06-183">Select this option if you want to be able to cancel transactions that have this posting profile.</span></span>                                                                                                               |
| <span data-ttu-id="01a06-184">**Zárás**</span><span class="sxs-lookup"><span data-stu-id="01a06-184">**Close**</span></span>      | <span data-ttu-id="01a06-185">Válasszon ki egy másik feladási profilt, amelyre váltani szeretne a jelen feladási profilt használó tranzakciók bezárásakor.</span><span class="sxs-lookup"><span data-stu-id="01a06-185">Select a posting profile to change to when transactions that have this posting profile are closed.</span></span> <span data-ttu-id="01a06-186">Egy tranzakció akkor minősül bezártnak, ha a teljes kiegyenlítése megtörtént.</span><span class="sxs-lookup"><span data-stu-id="01a06-186">A transaction is regarded as closed when it has been settled in full.</span></span>                                       |
