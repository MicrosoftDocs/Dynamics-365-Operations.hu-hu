---
title: "Vevői feladási profilok"
description: "A vevői feladási profilok a vevői tranzakciók főkönyvbe történő feladását szabályozzák."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: da750645612c2a0a7650edfd933d707618d9f9ce
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="customer-posting-profiles"></a><span data-ttu-id="de933-103">Vevői feladási profilok</span><span class="sxs-lookup"><span data-stu-id="de933-103">Customer posting profiles</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="de933-104">A vevői feladási profilok a vevői tranzakciók főkönyvbe történő feladását szabályozzák.</span><span class="sxs-lookup"><span data-stu-id="de933-104">Customer posting profiles control the posting of customer transactions to the general ledger.</span></span>

<a name="customer-posting-profiles"></a><span data-ttu-id="de933-105">Vevői feladási profilok</span><span class="sxs-lookup"><span data-stu-id="de933-105">Customer posting profiles</span></span>
-------------------------

<span data-ttu-id="de933-106">Vevői feladási profilok lehetővé teszik az Ön számára, hogy a főkönyvi számlákat és dokumentumbeállításokat az összes vevőhöz, vevő csoporthoz vagy egyetlen vevőhöz rendelhesse.</span><span class="sxs-lookup"><span data-stu-id="de933-106">Customer posting profiles enable you to assign general ledger accounts and document settings to all customers, a group of customers or a single customer.</span></span> <span data-ttu-id="de933-107">Ezeket a beállításokat akkor használják értékesítési rendelés, szabadszöveges számlák, készpénz kifizetések, fizetési felszólítások és kamatlevelek létrehozása során.</span><span class="sxs-lookup"><span data-stu-id="de933-107">These settings will be used when you create sales orders, free text invoices, cash payments, collection letters, and interest notes.</span></span> <span data-ttu-id="de933-108">Néhány tranzakcióhoz feladói profilt választhat ki, ami különböző és elsőbbséget élvez azokkal a feladói profilokkal szemben, amelyek a tranzakcióhoz be vannak állítva ezen az oldalon.</span><span class="sxs-lookup"><span data-stu-id="de933-108">For some transactions, you can select a posting profile that differs from and takes precedence over the posting profiles that are set up for transactions in this page.</span></span> 

<span data-ttu-id="de933-109">Az alapértelmezett feladási profil a Főkönyv és Áfa gyorslapon a Kinnlevőségek paramétereinek lapján van megadva.</span><span class="sxs-lookup"><span data-stu-id="de933-109">The default posting profile is defined in the Ledger and Sales Tax fasttab on the Accounts receivable parameters page.</span></span> <span data-ttu-id="de933-110">Az alapértelmezett feladási profil automatikusan szerepel majd az új dokumentumok fejlécén, amelyen meg lehet változtatni egy másik feladási profilra, ha szükséges.</span><span class="sxs-lookup"><span data-stu-id="de933-110">The default posting profile is then included automatically on the header of new documents where you can change it to a different posting profile if needed.</span></span>

<span data-ttu-id="de933-111">A tranzakció feladási definíciók lapon a a tranzakció feladási típussal társíthatja a feladásdefiníciókat.</span><span class="sxs-lookup"><span data-stu-id="de933-111">You can also associate posting definitions with transaction posting types in the Transaction posting definitions page.</span></span> <span data-ttu-id="de933-112">A feladásidefiníciók irányítják a a vevő tranzakciók feladását a főkönyvbe a feladói profilok helyett.</span><span class="sxs-lookup"><span data-stu-id="de933-112">Posting definitions control the posting of customer transactions to the general ledger instead of posting profiles.</span></span>

## <a name="creating-a-posting-profile"></a><span data-ttu-id="de933-113">Hozzon létre feladási profilt</span><span class="sxs-lookup"><span data-stu-id="de933-113">Creating a posting profile</span></span>
<span data-ttu-id="de933-114">Határozza meg a tranzakciók feladásában használt főkönyvet, ami a kijelölt feladási profilt használja.</span><span class="sxs-lookup"><span data-stu-id="de933-114">Specify the ledger accounts that are used in the posting of transactions that use the selected posting profile.</span></span> <span data-ttu-id="de933-115">Válassza ki a kijelölt feladási profil számlakódját, és amennyiben lehetséges, számla- vagy csoportszámát.</span><span class="sxs-lookup"><span data-stu-id="de933-115">Select an account code and, whenever possible, an account or group number for the selected posting profile.</span></span> <span data-ttu-id="de933-116">A feladási folyamat során a program kiválasztja a tranzakció legmegfelelőbb feladási profilját oly módon, hogy megkeresi a legspecifikusabb számlakód-, számlaszám-, illetve csoportszám-kombinációt az alábbi prioritás szerint:</span><span class="sxs-lookup"><span data-stu-id="de933-116">In the posting process, the most appropriate posting profile for each transaction is located by searching for the most specific account code, account number, or group and number combination in the following priority:</span></span>

| <span data-ttu-id="de933-117">**Számla kód** mezőérték</span><span class="sxs-lookup"><span data-stu-id="de933-117">**Account code** field value</span></span> | <span data-ttu-id="de933-118">**Számla/Csoport száma** mezőérték</span><span class="sxs-lookup"><span data-stu-id="de933-118">**Account/Group number** field value</span></span>            | <span data-ttu-id="de933-119">Keresési prioritás</span><span class="sxs-lookup"><span data-stu-id="de933-119">Search priority</span></span> |
|------------------------------|-------------------------------------------------|-----------------|
| <span data-ttu-id="de933-120">**Tábla**</span><span class="sxs-lookup"><span data-stu-id="de933-120">**Table**</span></span>                    | <span data-ttu-id="de933-121">Konkrét vevőkód</span><span class="sxs-lookup"><span data-stu-id="de933-121">Specific customer account</span></span>                       | <span data-ttu-id="de933-122">1</span><span class="sxs-lookup"><span data-stu-id="de933-122">1</span></span>               |
| <span data-ttu-id="de933-123">**Csoport**</span><span class="sxs-lookup"><span data-stu-id="de933-123">**Group**</span></span>                    | <span data-ttu-id="de933-124">Az a vevőcsoport, amelyet a vevőhöz rendeltek.</span><span class="sxs-lookup"><span data-stu-id="de933-124">Customer group that is assigned to the customer</span></span> | <span data-ttu-id="de933-125">2</span><span class="sxs-lookup"><span data-stu-id="de933-125">2</span></span>               |
| <span data-ttu-id="de933-126">**Minden**</span><span class="sxs-lookup"><span data-stu-id="de933-126">**All**</span></span>                      | <span data-ttu-id="de933-127">Üres</span><span class="sxs-lookup"><span data-stu-id="de933-127">Blank</span></span>                                           | <span data-ttu-id="de933-128">3</span><span class="sxs-lookup"><span data-stu-id="de933-128">3</span></span>               |

<span data-ttu-id="de933-129">Ha azt szeretné, hogy a vevői tranzakciók feladási profiljai megegyezzenek, akkor csak egy feladási profilt állítson be az összes számla kód mezőben.</span><span class="sxs-lookup"><span data-stu-id="de933-129">If you want all customer transactions to have the same posting profile, set up only one posting profile with All in the Account code field.</span></span> <span data-ttu-id="de933-130">Határozza meg a következő értékeket a feladási profil beállításához:</span><span class="sxs-lookup"><span data-stu-id="de933-130">Specify the following values to set up your posting profile:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="de933-131">Mező</span><span class="sxs-lookup"><span data-stu-id="de933-131">Field</span></span></th>
<th><span data-ttu-id="de933-132">Leírás</span><span class="sxs-lookup"><span data-stu-id="de933-132">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="de933-133"><strong>Feladási sablon</strong></span><span class="sxs-lookup"><span data-stu-id="de933-133"><strong>Posting profile</strong></span></span></td>
<td><span data-ttu-id="de933-134">Adjon meg egy kódot a feladási profilhoz.</span><span class="sxs-lookup"><span data-stu-id="de933-134">Enter a code for the posting profile.</span></span> <span data-ttu-id="de933-135">Például létrehozhat két feladói profilt, hogy a vevő egyenlegek hogy lekérdezze egy nemzeti pénznemet és egy külföldi valutát használó számlát a vevői egyenlegekhez.</span><span class="sxs-lookup"><span data-stu-id="de933-135">For example, you could create two posting profiles to obtain one account for customer balances in the national currency and another for customer balances in a foreign currency.</span></span> <span data-ttu-id="de933-136">Hívhatja az egyik számlát "Nemzeti", a másikat "Külföldi" számlának.</span><span class="sxs-lookup"><span data-stu-id="de933-136">You could call one account National and the other Foreign.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="de933-137"><strong>Leírás</strong></span><span class="sxs-lookup"><span data-stu-id="de933-137"><strong>Description</strong></span></span></td>
<td><span data-ttu-id="de933-138">Adja meg a feladói profil leírását.</span><span class="sxs-lookup"><span data-stu-id="de933-138">Enter a description of the posting profile.</span></span> <span data-ttu-id="de933-139">Ez csak a feladási profi pontosabb azonosítására szolgál, amikor ezen a lapon megtekinti.</span><span class="sxs-lookup"><span data-stu-id="de933-139">This is only used to better identify the posting profile when you view it in this page.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="de933-140"><strong>Számlakód</strong></span><span class="sxs-lookup"><span data-stu-id="de933-140"><strong>Account code</strong></span></span></td>
<td><span data-ttu-id="de933-141">Adja meg, hogy a feladási profil egyetlen vevőre, vagy egy vevőcsoportra vagy az összes vevőre vonatkozik:</span><span class="sxs-lookup"><span data-stu-id="de933-141">Specify whether the posting profile applies to a single customer, a group of customers, or all customers:</span></span>
<ul>
<li><span data-ttu-id="de933-142"><strong>Asztal</strong>– A feladási profilok egyetlen vevőre vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="de933-142"><strong>Table</strong> – The posting profile applies to a single customer.</span></span> <span data-ttu-id="de933-143">Válassza ki a vevőszámlát a Számla/Csoport szám mezőben.</span><span class="sxs-lookup"><span data-stu-id="de933-143">Select the customer account in the Account/Group number field.</span></span></li>
<li><span data-ttu-id="de933-144"><strong>Csoport</strong>– A feladási profilok vevő csoportra vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="de933-144"><strong>Group</strong> – The posting profile applies to a customer group.</span></span> <span data-ttu-id="de933-145">Válassza ki a vevő csoportot a Számla/Csoport szám mezőben.</span><span class="sxs-lookup"><span data-stu-id="de933-145">Select the customer group in the Account/Group number field.</span></span></li>
<li><span data-ttu-id="de933-146"><strong>Összes</strong>– A feladási profilok az összes vevőre vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="de933-146"><strong>All</strong> – The posting profile applies to all customers.</span></span> <span data-ttu-id="de933-147">Hagyja üresen a Számla/Csoport száma mezőt.</span><span class="sxs-lookup"><span data-stu-id="de933-147">Leave the Account/Group number field blank.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="de933-148"><strong>Számla/csoport száma</strong></span><span class="sxs-lookup"><span data-stu-id="de933-148"><strong>Account/Group number</strong></span></span></td>
<td><span data-ttu-id="de933-149">Ha az Asztal lehetőséget bejelölte a Számla kód mezőben, akkor adja meg annak a feladási profilhoz rendelt vevő számlaszámát.</span><span class="sxs-lookup"><span data-stu-id="de933-149">If Table is selected in the Account code field, select the account number of the customer who is associated with the posting profile.</span></span> <span data-ttu-id="de933-150">Ha a Csoport lehetőséget választotta, válassza ki a vevőcsoportot.</span><span class="sxs-lookup"><span data-stu-id="de933-150">If Group is selected, select the customer group.</span></span> <span data-ttu-id="de933-151">Ha az Összes lehetőséget választotta, hagyja ezt a mezőt üresen.</span><span class="sxs-lookup"><span data-stu-id="de933-151">If All is selected, leave this field blank.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="de933-152"><strong>Összegzett számla</strong></span><span class="sxs-lookup"><span data-stu-id="de933-152"><strong>Summary account</strong></span></span></td>
<td><span data-ttu-id="de933-153">Adja meg a főkönyvi számlát, amelyet a feladási profilban szereplő vevő(k) összesítési számlájaként kíván használni.</span><span class="sxs-lookup"><span data-stu-id="de933-153">Select the ledger account that will be used as the customer summary account for the customers who are associated with the posting profile.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="de933-154"><strong>Számla kiegyenlítése</strong></span><span class="sxs-lookup"><span data-stu-id="de933-154"><strong>Settle account</strong></span></span></td>
<td><span data-ttu-id="de933-155">Válassza ki a pénzforgalmi előrejelzéshez használt likviditási főkönyvi számlát.</span><span class="sxs-lookup"><span data-stu-id="de933-155">Select the liquidity ledger account that is used for cash flow forecasts.</span></span> <span data-ttu-id="de933-156">Ez a mező csak akkor jelenik meg, ha a készpénzforgalmi előrejelzések engedélyezettek.</span><span class="sxs-lookup"><span data-stu-id="de933-156">This field will only appear if cash flow forecasts are enabled.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="de933-157"><strong>Áfaelőlegek</strong></span><span class="sxs-lookup"><span data-stu-id="de933-157"><strong>Sales tax prepayments</strong></span></span></td>
<td><span data-ttu-id="de933-158">Válassza ki az előre törlesztett kifizetések forgalmi adójának számlaszámát.</span><span class="sxs-lookup"><span data-stu-id="de933-158">Select the account for sales tax for payments that are received in advance.</span></span>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><span data-ttu-id="de933-159"><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Megjegyzés</span><span class="sxs-lookup"><span data-stu-id="de933-159"><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Note</span></span>" alt="Note" id="alert_note" class="cl_IC101471" /><span data-ttu-id="de933-160"><strong>Megjegyzés</strong></span><span class="sxs-lookup"><span data-stu-id="de933-160"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="de933-161">Használja a Számla Kinnlevőségek paraméterei lapot a feladási profil meghatározásához, amikor a kifizetés előlegként van megjelölve.</span><span class="sxs-lookup"><span data-stu-id="de933-161">Use the Accounts receivable parameters page to specify the posting profile to use when a payment is marked as a prepayment.</span></span></td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><span data-ttu-id="de933-162"><strong>Kötelezettségek az engedményszámlához</strong></span><span class="sxs-lookup"><span data-stu-id="de933-162"><strong>Liabilities for discount account</strong></span></span></td>
<td><span data-ttu-id="de933-163">Válassza ki a Főkönyvi számlát az engedmény kötelezettségeihez.</span><span class="sxs-lookup"><span data-stu-id="de933-163">Select the ledger account for liabilities of discount.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="de933-164"><strong>Fizetésifelszólítás-sorozat</strong></span><span class="sxs-lookup"><span data-stu-id="de933-164"><strong>Collection letter sequence</strong></span></span></td>
<td><span data-ttu-id="de933-165">Válassza ki a fizetési felszólítások sorozatának azonosítóját ahhoz a vevőhöz, akit a feladási profilhoz rendelt.</span><span class="sxs-lookup"><span data-stu-id="de933-165">Select the identifier of the collection letter sequence to use for customers to whom the posting profile is assigned.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="de933-166"><strong>Kamatkód</strong></span><span class="sxs-lookup"><span data-stu-id="de933-166"><strong>Interest code</strong></span></span></td>
<td><span data-ttu-id="de933-167">Válassza ki a feladási profiloz rendelt vevő kamatszámításához használni kívánt számla kódot.</span><span class="sxs-lookup"><span data-stu-id="de933-167">Select the interest code to use for the calculation of interest for customers to whom the posting profile is assigned.</span></span></td>
</tr>
</tbody>
</table>

### 

### <a name="table-restrictions"></a><span data-ttu-id="de933-168">**Táblakorlátozások**</span><span class="sxs-lookup"><span data-stu-id="de933-168">**Table restrictions**</span></span>

<span data-ttu-id="de933-169">Azokhoz a tranzakciókhoz, amelyeket a feladási profil kiválasztott, meghatározzák, hogy a tranzakció automatikusan ki van-e egyenlítve, a kamat ki van-e számítva, és a fizetési felszólítások ki vannak-e állítva.</span><span class="sxs-lookup"><span data-stu-id="de933-169">For transactions that have the selected posting profile, specify whether transactions will be settled automatically, interest will be calculated, and collection letters will be issued.</span></span> <span data-ttu-id="de933-170">Kiválaszthatja a kijelölt feladási profillal rendelkező tranzakciók zárásakor használatos számlát.</span><span class="sxs-lookup"><span data-stu-id="de933-170">You can also select the account that is used when transactions that have the selected posting profile are closed.</span></span>

<span data-ttu-id="de933-171">Határozza meg a következő értékeket a feladási profil beállításához:</span><span class="sxs-lookup"><span data-stu-id="de933-171">Specify the following values to set up your posting profile:</span></span>

| <span data-ttu-id="de933-172">Mező</span><span class="sxs-lookup"><span data-stu-id="de933-172">Field</span></span>                 | <span data-ttu-id="de933-173">Leírás</span><span class="sxs-lookup"><span data-stu-id="de933-173">Description</span></span>                                                                                                                                                                                                                                        |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="de933-174">**Elszámolás**</span><span class="sxs-lookup"><span data-stu-id="de933-174">**Settlement**</span></span>        | <span data-ttu-id="de933-175">Válassza ki a váltót a feladási profillal rendelkező tranzakciók automatikus elszámolásának engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="de933-175">Select this toggle to enable automatic settlement of transactions that have this posting profile.</span></span> <span data-ttu-id="de933-176">Ha ez a váltó nincs bejelölve, manuálisan kell rendeznie a tranzakciókat a Nyitott tranzakciók kiegyenlítése oldalon vagy a Vevő kifizetések megadása oldalon.</span><span class="sxs-lookup"><span data-stu-id="de933-176">If this toggle is cleared, you must manually settle transactions by using the Settle open transactions page or the Enter customer payments page.</span></span> |
| <span data-ttu-id="de933-177">**Érdeklődési terület**</span><span class="sxs-lookup"><span data-stu-id="de933-177">**Interest**</span></span>          | <span data-ttu-id="de933-178">Válassza ki ezt a váltót, ha a kamatot ki kell számítani ezen profilt használó vevő számljának fennmaradó egyenlegei esetében.</span><span class="sxs-lookup"><span data-stu-id="de933-178">Select this toggle if interest should be calculated on outstanding balances for customer accounts that use this profile.</span></span> <span data-ttu-id="de933-179">Ha a váltó nincs bejelölve, akkor az ilyen vevők esetében nem számít kamatot a program.</span><span class="sxs-lookup"><span data-stu-id="de933-179">If this toggle is cleared, interest will not be calculated for these customers.</span></span>                                           |
| <span data-ttu-id="de933-180">**Fizetési felszólítás**</span><span class="sxs-lookup"><span data-stu-id="de933-180">**Collection letter**</span></span> | <span data-ttu-id="de933-181">Válassza ki ezt a váltót, ha a fizetési felszólításokat ezen profilt használó vevő számljához kell létrehozni.</span><span class="sxs-lookup"><span data-stu-id="de933-181">Select this toggle if collection letters should be generated for customer accounts that use this profile.</span></span> <span data-ttu-id="de933-182">Ha a váltó nincs bejelölve, a program nem számít fizetési felszóltásokat ezen vevők esetében.</span><span class="sxs-lookup"><span data-stu-id="de933-182">If this toggle is cleared, collection letters will not be generated for these customers.</span></span>                                                 |
| <span data-ttu-id="de933-183">**Zárás**</span><span class="sxs-lookup"><span data-stu-id="de933-183">**Close**</span></span>             | <span data-ttu-id="de933-184">Válasszon ki egy másik feladási profilt, amelyre váltani szeretne a jelen feladási profilt használó tranzakciók bezárásakor.</span><span class="sxs-lookup"><span data-stu-id="de933-184">Select a posting profile to change to when transactions that have this posting profile are closed.</span></span> <span data-ttu-id="de933-185">Egy tranzakció akkor minősül bezártnak, ha a teljes kiegyenlítése megtörtént.</span><span class="sxs-lookup"><span data-stu-id="de933-185">A transaction is regarded as closed when it has been settled in full.</span></span>                                                                           |



<span data-ttu-id="de933-186">További információkért lásd: [Vevői kifizetések áttekintése](../cash-bank-management/tasks/customer-payment-overview.md).</span><span class="sxs-lookup"><span data-stu-id="de933-186">For more information, see [Customer payment overview](../cash-bank-management/tasks/customer-payment-overview.md).</span></span>

