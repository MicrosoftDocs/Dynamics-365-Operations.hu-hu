---
title: "EU-s beérkezési igazolás"
description: "Ez a cikk az európai uniós (EU) beérkezési igazolásokról nyújt tájékoztatást."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustEntryCertificateJour_W, CustParameters, CustTable, SalesTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 11464
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 6e066bd2adbb9f27f3b0850ca25978d0777590d2
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="eu-entry-certificates"></a><span data-ttu-id="e388c-103">EU beérkezési igazolások</span><span class="sxs-lookup"><span data-stu-id="e388c-103">EU entry certificates</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="e388c-104">Ez a cikk az európai uniós (EU) beérkezési igazolásokról nyújt tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="e388c-104">This article provides information about European Union (EU) entry certificates.</span></span>

<span data-ttu-id="e388c-105">Egy európai uniós (EU) beérkezési igazolással kapcsolatban a következő műveleteket hajthatja végre:</span><span class="sxs-lookup"><span data-stu-id="e388c-105">You can complete the following tasks for a European Union (EU) entry certificate:</span></span>

-   <span data-ttu-id="e388c-106">Cikkek vagy szolgáltatások EU-országokba/régiókba való szállításához EU-s beérkezési igazolás létrehozása és kibocsátása szállítólevéllel vagy vevői számlával együtt.</span><span class="sxs-lookup"><span data-stu-id="e388c-106">Create and issue an EU entry certificate together with a packing slip or customer invoice for the delivery of items or services to EU countries/regions.</span></span>
-   <span data-ttu-id="e388c-107">EU-vevő által aláírt EU-s beérkezési igazolás fogadása.</span><span class="sxs-lookup"><span data-stu-id="e388c-107">Receive the EU entry certificate that is signed by an EU customer.</span></span>
-   <span data-ttu-id="e388c-108">Olyan aláírt EU-s beérkezési igazolás feltöltése, amely vagy egy vevőtől vagy egy olyan harmadik féltől származik, amely felelős a cikkek kiszállításáért a vevő számára.</span><span class="sxs-lookup"><span data-stu-id="e388c-108">Upload the signed EU entry certificate that is received either from the customer or from a third party who is responsible for delivering items to the customer.</span></span>
-   <span data-ttu-id="e388c-109">Feltöltött EU-s beérkezési igazolás társítása egy vevői számlához.</span><span class="sxs-lookup"><span data-stu-id="e388c-109">Associate the uploaded EU entry certificate with a customer invoice.</span></span>
-   <span data-ttu-id="e388c-110">A feltöltött EU beérkezési igazolás státuszának frissítése.</span><span class="sxs-lookup"><span data-stu-id="e388c-110">Update the status of the uploaded EU entry certificate.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e388c-111">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="e388c-111">Prerequisites</span></span>
<span data-ttu-id="e388c-112">Az alábbi táblázat bemutatja a munka megkezdése előtt biztosítandó előfeltételeket.</span><span class="sxs-lookup"><span data-stu-id="e388c-112">The following table shows the prerequisites that must be in place before you start.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e388c-113">Kategória</span><span class="sxs-lookup"><span data-stu-id="e388c-113">Category</span></span></th>
<th><span data-ttu-id="e388c-114">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="e388c-114">Prerequisite</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="e388c-115">Ország/régió</span><span class="sxs-lookup"><span data-stu-id="e388c-115">Country/region</span></span></td>
<td><span data-ttu-id="e388c-116">A jogi személy elsődleges címének egy EU tagállamban kell lennie.</span><span class="sxs-lookup"><span data-stu-id="e388c-116">The primary address of the legal entity must be in a EU member state.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e388c-117">Kapcsolódó feladatok beállítása</span><span class="sxs-lookup"><span data-stu-id="e388c-117">Related set up tasks</span></span></td>
<td><ul>
<li><span data-ttu-id="e388c-118">A <strong>Kinnlevőségek paraméterei</strong> képernyőn válassza ki a <strong>Beérkezési igazolások kezelésének engedélyezése</strong> és a <strong>Beérkezési igazolás kiállításának engedélyezése</strong> lehetőségeket.</span><span class="sxs-lookup"><span data-stu-id="e388c-118">On the <strong>Accounts receivable parameters</strong> page, select the <strong>Enable entry certificate management</strong> and <strong>Enable entry certificate issuing</strong> options.</span></span></li>
<li><span data-ttu-id="e388c-119">Az <strong>Ügyfelek</strong> képernyőn, a <strong>Számlázás és szállítás</strong> gyorslapon válassza ki a <strong>Beérkezési igazolás szükséges</strong> lehetőséget, hogy megjelölje, ha EU-s beérkezési igazolás szükséges az ügyfél részére.</span><span class="sxs-lookup"><span data-stu-id="e388c-119">On the <strong>Customers</strong> page, on the <strong>Invoice and delivery</strong> FastTab, select the <strong>Entry certificate required</strong> option to indicate that an EU entry certificate is mandatory for the customer.</span></span> <span data-ttu-id="e388c-120">Jelölje be a <strong>Beérkezési igazolás kiállítása</strong> jelölőnégyzetet a jogi személy EU-s beérkezési igazolásának kiadásához a vevő számára.</span><span class="sxs-lookup"><span data-stu-id="e388c-120">Select the <strong>Issue entry certificate</strong> option to issue an EU entry certificate of the legal entity to the customer.</span></span></li>
<li><span data-ttu-id="e388c-121">A <strong>Kinnlevőségek paraméterei</strong> képernyőn válassza ki a számsorozat kódját a <strong>Beérkezési igazolás</strong> hivatkozáshoz.</span><span class="sxs-lookup"><span data-stu-id="e388c-121">On the <strong>Accounts receivable parameters</strong> page, select a number sequence code for the <strong>Entry certificate</strong> reference.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e388c-122">Kapcsolódó tranzakciók</span><span class="sxs-lookup"><span data-stu-id="e388c-122">Related transactions</span></span></td>
<td><ul>
<li><span data-ttu-id="e388c-123">Vevői fiók létrehozása.</span><span class="sxs-lookup"><span data-stu-id="e388c-123">Create a customer account.</span></span></li>
<li><span data-ttu-id="e388c-124">Hozzon létre egy értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="e388c-124">Create a sales order.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="creating-registering-and-uploading-an-eu-entry-certificate"></a><span data-ttu-id="e388c-125">EU-s beérkezési igazolás létrehozása, regisztrációja és feltöltése</span><span class="sxs-lookup"><span data-stu-id="e388c-125">Creating, registering, and uploading an EU entry certificate</span></span>
<span data-ttu-id="e388c-126">Beérkezési igazolás EU hozhat létre, automatikusan vagy kézzel történjen.</span><span class="sxs-lookup"><span data-stu-id="e388c-126">You can create an EU entry certificate automatically or manually.</span></span> <span data-ttu-id="e388c-127">Amikor egy csomagjegyzéket vagy számlát ad fel egy vevő részére a **Szállítólevél feladása** oldalt vagy a **Számla feladása** oldalt használva, létrejön és nyomtatásra kerül egy EU beérkezési igazolás.</span><span class="sxs-lookup"><span data-stu-id="e388c-127">An EU entry certificate is created and printed automatically when you post a packing slip or invoice for a customer by using the **Packing slip posting** page or the **Posting invoice** page.</span></span> <span data-ttu-id="e388c-128">Az EU-s beérkezési igazolás kézi létrehozásához vagy újranyomtatásához egy vevői számla esetében használja a **Számlanapló** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="e388c-128">To manually create or reprint an EU entry certificate for a customer invoice, use the **Invoice journal** page.</span></span> <span data-ttu-id="e388c-129">Ezenkívül megadhat információkat egy olyan EU beérkezési igazolással kapcsolatban, amelyet egy harmadik fél bocsátott ki a **Beérkezési igazolások naplója** képernyőn keresztül.</span><span class="sxs-lookup"><span data-stu-id="e388c-129">Additionally, you can use the **Entry certificate journal** page to enter details about an EU entry certificate that is issued by a third party.</span></span>

### <a name="creating-an-eu-entry-certificate-automatically-or-manually"></a><span data-ttu-id="e388c-130">EU-s beérkezési igazolás automatikus vagy kézi létrehozása</span><span class="sxs-lookup"><span data-stu-id="e388c-130">Creating an EU entry certificate automatically or manually</span></span>

<span data-ttu-id="e388c-131">Létrehozhat egy EU-s beérkezési igazolást automatikusan a szállítólevél használatával a **Minden értékesítési rendelés** képernyőn vagy az **Értékesítési rendelés** képernyőn található számla használatával.</span><span class="sxs-lookup"><span data-stu-id="e388c-131">You can create an EU entry certificate automatically by using a packing slip on the **All sales orders** page or by using an invoice on the **Sales order** page.</span></span> <span data-ttu-id="e388c-132">Az EUs- beérkezési igazolás kézi létrehozásához használhatja a **Számlanapló** képernyő egyik számláját.</span><span class="sxs-lookup"><span data-stu-id="e388c-132">To manually create an EU entry certificate, you can use an invoice on the **Invoice journal** page.</span></span> <span data-ttu-id="e388c-133">Mielőtt azonban manuális létrehozhatná az EU-s beérkezési igazolást, meg kell változtatnia egy számla igazolási státuszát.</span><span class="sxs-lookup"><span data-stu-id="e388c-133">However, you must change the certification status of the invoice before you manually create an EU entry certificate.</span></span>

### <a name="registering-an-eu-entry-certificate"></a><span data-ttu-id="e388c-134">EU beérkezési igazolás regisztrálása</span><span class="sxs-lookup"><span data-stu-id="e388c-134">Registering an EU entry certificate</span></span>

<span data-ttu-id="e388c-135">Ha regisztráció szükséges, regisztrálhat egy olyan EU beérkezési igazolást, amelyet egy harmadik fél bocsátott ki a**Beérkezési igazolások naplója** képernyőn keresztül.</span><span class="sxs-lookup"><span data-stu-id="e388c-135">If registration is required, you can use the **Entry certificate journal** page to register an EU entry certificate that is issued by a third party.</span></span>

### <a name="uploading-a-received-eu-entry-certificate"></a><span data-ttu-id="e388c-136">Átvett EU-s beérkezési igazolás feltöltése</span><span class="sxs-lookup"><span data-stu-id="e388c-136">Uploading a received EU entry certificate</span></span>

<span data-ttu-id="e388c-137">EU-vevő által aláírt, fogadott EU-s beérkezési igazolás feltöltéséhez használja a **Mellékletek** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="e388c-137">Use the **Attachments** page to upload a received EU entry certificate that is signed by an EU customer.</span></span> <span data-ttu-id="e388c-138">Miután az igazolás feltöltésre került, hozzátársíthatja egy számlához a cikkek leszállításának bizonyítékaként.</span><span class="sxs-lookup"><span data-stu-id="e388c-138">After the certificate is uploaded, you can associate it with an invoice as proof that the items were delivered.</span></span> <span data-ttu-id="e388c-139">Ez a bizonyíték szükséges, ha olyan számlát kell kiadnia, amely nem tartalmazza az áfát, és könyvvizsgálat során is használják.</span><span class="sxs-lookup"><span data-stu-id="e388c-139">This proof is required if you must issue an invoice that doesn't include value-added tax (VAT), and it's also used during auditing.</span></span>

### <a name="optional-updating-the-certification-status-and-printing-status-of-an-invoice"></a><span data-ttu-id="e388c-140">Opcionális: A tanúsítvány állapotának és a számla nyomtatási állapotának frissítése</span><span class="sxs-lookup"><span data-stu-id="e388c-140">Optional: Updating the certification status and printing status of an invoice</span></span>

<span data-ttu-id="e388c-141">Frissítheti a beérkezési igazolás állapotát és a vevői számla nyomtatási állapotát a **Számlanapló** képernyő használatával.</span><span class="sxs-lookup"><span data-stu-id="e388c-141">You can update the entry certification status and printing status of a customer invoice by using the **Invoice journal** page.</span></span>

## <a name="technical-information-for-system-administrators"></a><span data-ttu-id="e388c-142">Technikai információk rendszergazdáknak.</span><span class="sxs-lookup"><span data-stu-id="e388c-142">Technical information for system administrators</span></span>
<span data-ttu-id="e388c-143">Ha nincs hozzáférése a feladat végrehajtásához használt lapokhoz, akkor forduljon a rendszergazdához, és adja meg azokat az információkat, amelyek a következő táblázatban szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="e388c-143">If you don't have access to the pages that are used to complete this task, contact your system administrator, and provide the information that is shown in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e388c-144">Kategória</span><span class="sxs-lookup"><span data-stu-id="e388c-144">Category</span></span></th>
<th><span data-ttu-id="e388c-145">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="e388c-145">Prerequisite</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="e388c-146">Biztonsági szerepkörök és feladatok</span><span class="sxs-lookup"><span data-stu-id="e388c-146">Security roles and duties</span></span></td>
<td><span data-ttu-id="e388c-147">Ha EU-s beérkezési igazolást szeretne beállítani és létrehozni cikkek vagy szolgáltatások esetén, a következő feladatköröket tartalmazó biztonsági szerepkör tagjának kell lennie:</span><span class="sxs-lookup"><span data-stu-id="e388c-147">To set up and create EU entry certificates for items or services, you must be a member of a security role that includes the following duties:</span></span>
<ul>
<li><span data-ttu-id="e388c-148"><strong>Kinnlevőség-adminisztrátor</strong> (CustInvoiceAccountsReceivableClerk)</span><span class="sxs-lookup"><span data-stu-id="e388c-148"><strong>Accounts receivable clerk</strong> (CustInvoiceAccountsReceivableClerk)</span></span></li>
<li><span data-ttu-id="e388c-149"><strong>Ügyfélszolgálati munkatárs</strong> (TradeCustomerServiceRepresentative)</span><span class="sxs-lookup"><span data-stu-id="e388c-149"><strong>Customer service representative</strong> (TradeCustomerServiceRepresentative)</span></span></li>
<li><span data-ttu-id="e388c-150"><strong>Értékesítési adminisztrátor</strong> (TradeSalesClerk)</span><span class="sxs-lookup"><span data-stu-id="e388c-150"><strong>Sales clerk</strong> (TradeSalesClerk)</span></span></li>
<li><span data-ttu-id="e388c-151"><strong>Szállítási adminisztrátor</strong> (InventShippingClerk)</span><span class="sxs-lookup"><span data-stu-id="e388c-151"><strong>Shipping clerk</strong> (InventShippingClerk)</span></span></li>
</ul></td>
</tr>
</tbody>
</table>






