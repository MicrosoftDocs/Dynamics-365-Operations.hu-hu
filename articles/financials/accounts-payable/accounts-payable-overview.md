---
title: "Kötelezettségek konfigurálása"
description: "Ez a cikk azoknak az oldalaknak a leírását tartalmazza, amelyek használatával beállíthatók a Microsoft Dynamics 365 for Finance and Operations rendszer Kötelezettségek moduljának alapvető, illetve választható funkciói. Azokat a beállítási lépéseket is bemutatja, amelyeket a Kötelezettségek beállításának elkezdése előtt kell elvégezni."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/08/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankAccountTable, DeliveryMode, PaymTerm, VendGroup, VendParameters, VendPaymMode, VendTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 24671
ms.assetid: 82561fe7-b2d6-464c-9347-79d0ce0f9743
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: 6a832a30870f77578503bae6eea17ad1d0881d91
ms.contentlocale: hu-hu
ms.lasthandoff: 08/07/2018

---

# <a name="configure-accounts-payable"></a><span data-ttu-id="aeb8a-104">Kötelezettségek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="aeb8a-104">Configure Accounts payable</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aeb8a-105">Ez a cikk azoknak az oldalaknak a leírását tartalmazza, amelyek használatával beállíthatók a Microsoft Dynamics 365 for Finance and Operations rendszer Kötelezettségek moduljának alapvető, illetve választható funkciói.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-105">This article describes the pages that you use to set up basic and optional functionality for Accounts payable in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="aeb8a-106">Azokat a beállítási lépéseket is bemutatja, amelyeket a Kötelezettségek beállításának elkezdése előtt kell elvégezni.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-106">It also describes setup steps that you must complete before you start to set up Accounts payable.</span></span>

<a name="prerequisites-for-accounts-payable-setup"></a><span data-ttu-id="aeb8a-107">Kötelezettségek beállításainak előfeltételei</span><span class="sxs-lookup"><span data-stu-id="aeb8a-107">Prerequisites for Accounts payable setup</span></span>
----------------------------------------

<span data-ttu-id="aeb8a-108">Mielőtt beállítja a Kötelezettségeket el kell végezni az alábbiakat:</span><span class="sxs-lookup"><span data-stu-id="aeb8a-108">Before you can set up Accounts payable, you must complete the following setup:</span></span>

-   <span data-ttu-id="aeb8a-109">A Főkönyvben:</span><span class="sxs-lookup"><span data-stu-id="aeb8a-109">In General ledger:</span></span>
    -   <span data-ttu-id="aeb8a-110">Ha kifizetési naplókat szeretne használni, állítsa be azokat a pénzügyben.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-110">If you plan to use payment journals, set up payment journals.</span></span>
    -   <span data-ttu-id="aeb8a-111">Ha árfolyam-korrekciókat szeretne futtatni, akkor adja meg a pénznemkódokat a Pénznemek oldalon, adja meg az árfolyamtípust az Árfolyamtípus oldalon és adja meg a pénznem árfolyamokat a Pénznem árfolyamok oldalon.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-111">If you plan to run exchange rate adjustments, set up currency codes on the Currencies page, set up exchange rate types on the Exchange rate types page, and set up currency exchange rates on the Currency exchange rates page.</span></span>
-   <span data-ttu-id="aeb8a-112">A Készpénz és bank kezelés szakaszban beállíthatja a kifizetési módokkal használandó bankszámlákat.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-112">In Cash and bank management, set up bank accounts to use with methods of payment.</span></span>

## <a name="setup-pages-for-accounts-payable"></a><span data-ttu-id="aeb8a-113">A Kötelezettségek modul beállítási oldalai</span><span class="sxs-lookup"><span data-stu-id="aeb8a-113">Setup pages for Accounts payable</span></span>

<span data-ttu-id="aeb8a-114">A következő oldalak segítségével minden egyes jogi személyeknél beállíthatja a Kötelezettségek modul alapvető funkcióit.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-114">Use the following pages to set up the basic functionality of Accounts payable for each legal entity.</span></span> <span data-ttu-id="aeb8a-115">Az oldalak a javasolt beállítási sorrendben vannak felsorolva.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-115">The pages are listed in the recommended order of setup.</span></span> <span data-ttu-id="aeb8a-116">A beállítás egyszerűsítése érdekében az első létrehozott rekordból sablonokat hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-116">To make the setup process easier, you can create templates from the first records that you create.</span></span> <span data-ttu-id="aeb8a-117">A sablonban az értékek általában több mezőben találhatók, hogy láthatók legyenek a tulajdonságok, amelyeket a szervezet alkalmazni kíván egy adott szállító típushoz.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-117">In a template, values are typically entered in many fields to reflect the features that the organization wants to implement for a particular type of vendor.</span></span>
1.  <span data-ttu-id="aeb8a-118">A Fizetési feltételek oldalon adja meg a fizetés feltételeit, amelyeket értékesítési rendelésekhez, beszerzési rendelésekhez, vevőkhöz és szállítókhoz kíván hozzárendelni és amelyek meghatározzák a számlák határidejét.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-118">On the Terms of payment page, define the terms of payment that you assign to sales orders, purchase orders, customers, and vendors, and that determine invoice due dates.</span></span> <span data-ttu-id="aeb8a-119">További információkért lásd: [Szállítói kifizetési díjak meghatározása](tasks/define-vendor-payment-fees.md).</span><span class="sxs-lookup"><span data-stu-id="aeb8a-119">For more information, see [Define vendor payment fees](tasks/define-vendor-payment-fees.md).</span></span>
2.  <span data-ttu-id="aeb8a-120">A Fizetési módok – szállítók oldalon hozzon létre és frissítse az információkat, hogyan fizet a szervezet a beszállítóknak.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-120">On the Methods of payment - vendors page, create and maintain information about how the organization pays its vendors.</span></span>
3.  <span data-ttu-id="aeb8a-121">A Szállítói csoportok oldalon hozzon létre és frissítse az információkat a szállítókkal kapcsolatban, akik fontos paraméterekkel rendelkeznek feladással, kiegyenlítéssel, fizetéssel és előrejelzéssel kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-121">On the Vendor groups page, create and maintain groups of vendors that share important parameters for posting, settlement and payment, reporting, and forecasting.</span></span>
4.  <span data-ttu-id="aeb8a-122">A Szállítói feladási profilok oldalon adja meg hogyan kerüljenek postázásra a szállítói tranzakciók a főkönyvbe.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-122">On the Vendor posting profiles page, define how vendor transactions are posted to the general ledger.</span></span>
5.  <span data-ttu-id="aeb8a-123">A Kötelezettség paraméterek oldalon adjon meg alapértelmezett beállításokat amelyek alkalmazhatók, ha egy specifikusabb eset nincs meghatározva, paraméterek különböző funkciókhoz, és különböző számsorok Kötelezettségekhez.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-123">On the Accounts payable parameters page, set up default settings that are applied if a more specific setting isn't specified, parameters for various kinds of functionality, and the various number sequences for Accounts payable.</span></span>
6.  <span data-ttu-id="aeb8a-124">Az Űrlap beállítása oldalon adja meg a különböző dokumentumok formátumát, amelyek kapcsolódnak a szállítóhoz és amelyet a szervezet használ a szállítói bevételezések követéséhez és adjon meg okokat a fizetési folyamatnál a szállítóknak.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-124">On the Form setup page, define the format of various documents that are related to vendors, and that the organization uses to keep track of receipts from vendors and enter reasons for the flow of payments to vendors.</span></span>
7.  <span data-ttu-id="aeb8a-125">A Szállítók oldalon hozzon létre és frissítse a szállítói számlákat, továbbá az adóhatóságokat amelyek áfabevallásra kötelezik a szervezetet.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-125">On the Vendors page, create and maintain vendor accounts, and also the tax authorities that your organization reports sales taxes to.</span></span>

## <a name="optional-setup-pages-for-accounts-payable"></a><span data-ttu-id="aeb8a-126">A Kötelezettségek modul opcionális beállítási oldalai</span><span class="sxs-lookup"><span data-stu-id="aeb8a-126">Optional setup pages for Accounts payable</span></span>
<span data-ttu-id="aeb8a-127">Az alapvető funkciók mellett a Kötelezettségeknek egyéb funkcióit is megadhatja.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-127">In addition to the basic functionality, Accounts payable has other functionality that you can set up.</span></span>

<span data-ttu-id="aeb8a-128">A következő beállítási oldalak funkciók szerint vannak csoportosítva.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-128">The additional setup pages are organized by functionality.</span></span>

<span data-ttu-id="aeb8a-129">**Irányelvek**</span><span class="sxs-lookup"><span data-stu-id="aeb8a-129">**Policies**</span></span>
-   <span data-ttu-id="aeb8a-130">A Szállítói számla irányelvek oldalon adja meg a szállítói számla irányelveket.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-130">On the Vendor invoice policy page, set up vendor invoice policies.</span></span>

<span data-ttu-id="aeb8a-131">**Számlaegyeztetés**</span><span class="sxs-lookup"><span data-stu-id="aeb8a-131">**Invoice matching**</span></span>

-   <span data-ttu-id="aeb8a-132">A Számlaösszegek tűréshatárai oldalon adja meg a számlaösszegek toleranciáit.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-132">On the Invoice totals tolerances page, set up tolerances for invoice totals.</span></span>
-   <span data-ttu-id="aeb8a-133">Az Egyeztetési irányelv oldalon adja meg a kétirányú és háromirányú egyeztetési irányelveket.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-133">On the Matching policy page, set up two-way and three-way matching policies.</span></span>
-   <span data-ttu-id="aeb8a-134">Az Ár tűréshatárok oldalon adja meg az egységárak toleranciáit.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-134">On the Price tolerances page, set up tolerances for unit prices.</span></span>
-   <span data-ttu-id="aeb8a-135">A Cikkárak toleranciacsoportok oldalon adjon meg toleranciacsoportokat a cikkárakhoz.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-135">On the Item price tolerance groups page, set up tolerance groups for item prices.</span></span>
-   <span data-ttu-id="aeb8a-136">A Szállítói árak toleranciacsoportok oldalon adjon meg toleranciacsoportokat a szállítói árakhoz.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-136">On the Vendor price tolerance groups page, set up  tolerance groups for vendor prices.</span></span>
-   <span data-ttu-id="aeb8a-137">A Díj tűréshatárok oldalon adja meg a díjak toleranciáit.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-137">On the Charges tolerances page, set up tolerances for charges.</span></span>

<span data-ttu-id="aeb8a-138">**Munkafolyamat**</span><span class="sxs-lookup"><span data-stu-id="aeb8a-138">**Workflow**</span></span>

-   <span data-ttu-id="aeb8a-139">A Kötelezettségek munkafolyamatai oldalon adjon meg munkafolyamat konfigurációkat naplójóváhagyásokhoz és beszerzési igénylésekhez.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-139">On the Accounts payable workflows page, set up workflow configurations for journal approvals and purchase requisitions.</span></span>

<span data-ttu-id="aeb8a-140">**Okok**</span><span class="sxs-lookup"><span data-stu-id="aeb8a-140">**Reasons**</span></span>

-   <span data-ttu-id="aeb8a-141">A Szállítói okok oldalon adjon meg okkódokat.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-141">On the Vendor reasons page, set up reason codes.</span></span>

<span data-ttu-id="aeb8a-142">**Költségek**</span><span class="sxs-lookup"><span data-stu-id="aeb8a-142">**Charges**</span></span>

-   <span data-ttu-id="aeb8a-143">A Költségkódok oldalon adjon meg kódokat a költségekhez, amelyeket a beszerzési rendelésben használ.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-143">On the Charges code page, set up codes for the charges that are used in purchase orders.</span></span>
-   <span data-ttu-id="aeb8a-144">A Szállító költségcsoportja oldalon hozzon létre és frissítse a szállítók költségcsoportjait.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-144">On the Vendor charges group page, create and maintain charges groups for vendors.</span></span>
-   <span data-ttu-id="aeb8a-145">A Cikk-költésgcsoportok oldalon hozza létre és frissítse a cikkek költségcsoportjait.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-145">On the Item charge groups page, create and maintain charges groups for items.</span></span>
-   <span data-ttu-id="aeb8a-146">Az Automatikus díjak oldalon adja meg a költségeket amelyek automatikusan a rendelésekhez adódnak.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-146">On the Auto charges page, define the charges that are automatically assigned to orders.</span></span>

<span data-ttu-id="aeb8a-147">**Kiegészítő cikkek**</span><span class="sxs-lookup"><span data-stu-id="aeb8a-147">**Supplementary items**</span></span>

-   <span data-ttu-id="aeb8a-148">A Kiegészítő cikkcsoportok – Szállító oldalon hozza létre és frissítse a szállítók kiegészítő cikkcsoportjait.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-148">On the Supplementary item groups - Vendor page, create and maintain supplementary item groups for vendors.</span></span>
-   <span data-ttu-id="aeb8a-149">A Kiegészítő cikkcsoportok – Készlet oldalonhozza létre és frissítse a cikkek kiegészítő cikkcsoportjait.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-149">On the Supplementary item groups - Inventory page, create and maintain supplementary item groups for items.</span></span>

<span data-ttu-id="aeb8a-150">**Kiosztás**</span><span class="sxs-lookup"><span data-stu-id="aeb8a-150">**Distribution**</span></span>

-   <span data-ttu-id="aeb8a-151">A Szállítás feltételei oldalon hozza létre és frissítse egy cikktranszfer feltételeit az eladótól a vevőhöz.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-151">On the Terms of delivery page, create and maintain the conditions for an item's transfer from seller to buyer.</span></span>
-   <span data-ttu-id="aeb8a-152">A Szállítási módok oldalon hozza létre és frissítse a szállítási módok amelyek akkor használatosak amikor egy rendelést az eladótól a vevőnek szállítanak.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-152">On the Modes of delivery page, create and maintain the methods of transport that are used when an order is delivered from the seller to the buyer.</span></span>
-   <span data-ttu-id="aeb8a-153">A Célkódok oldalon hozza létre és frissítse az azonosítókhoz és a szállítási célok leírásához.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-153">On the Destination codes page, create and maintain identifiers and descriptions for delivery destinations.</span></span>

<span data-ttu-id="aeb8a-154">**Képernyők**</span><span class="sxs-lookup"><span data-stu-id="aeb8a-154">**Forms**</span></span>

-   <span data-ttu-id="aeb8a-155">Az Adatlap megjegyzései oldalon hozza létre a szabványos szöveget, ami megjelenik az egyes oldalakon.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-155">On the Form notes page, create the standard text that appears on various pages.</span></span>
-   <span data-ttu-id="aeb8a-156">A Képernyő-elrendezés paraméterei oldalon hozzon létre elrendezést igénylésekhez, bevételezési listákhoz, szállítólevelekhez és számlákhoz.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-156">On the Form sorting parameters page, set up the sorting order for requisitions, receipt lists, packing slips, and invoices.</span></span>
-   <span data-ttu-id="aeb8a-157">A Nyomatatáskezelési oldalon adjon meg nyomtatáskezelési információkat az eredeti és másolt oldalakhoz.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-157">On the Print management setup page, set up print management information for originals and copies of pages.</span></span>

<span data-ttu-id="aeb8a-158">**Kifizetések**</span><span class="sxs-lookup"><span data-stu-id="aeb8a-158">**Payments**</span></span>

-   <span data-ttu-id="aeb8a-159">A Készpénzfizetési engedmény oldalon adja meg és kezelje a készpénzfizetési engedmények megadásával kapcsolatos feltételeket.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-159">On the Cash discounts page, set up and manage the terms for obtaining cash discounts.</span></span> <span data-ttu-id="aeb8a-160">A készpénzfizetési engedmények kódjai a szállítókhoz kapcsolódnak, és a beszerzési rendelésekre vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-160">The cash discount codes are linked to vendors and are applied to purchase orders.</span></span>
-   <span data-ttu-id="aeb8a-161">A Fizetési ütemezések oldalon adjon meg fizetési ütemezéseket, amelyeket a szállítóknak történő részletfizetések kezeléséhez használ.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-161">On the Payment schedules page, set up the payment schedules that are used to manage installment payments to vendors.</span></span>
-   <span data-ttu-id="aeb8a-162">A Fizetési napok oldalon adja meg a fizetési napokat, amelyeket a határidők számításához használ, és adja meg a hét vagy hónap sepcifikus fizetési napjait.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-162">On the Payment days page, define the payment days that are used to calculate due dates, and specify payment days for a specific day of the week or month.</span></span>
-   <span data-ttu-id="aeb8a-163">A Fizetési díj oldalonhozza létre és frissítse a szállítókhoz társított fizetési díjakat.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-163">On the Payment fee page, create and maintain the payment fees that are associated with vendors.</span></span>
-   <span data-ttu-id="aeb8a-164">A Fizetési rendelkezés oldalon hozza létre és frissítse a fizetési rendelkezéseket.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-164">On the Payment instruction page, create and maintain payment instructions.</span></span>

<span data-ttu-id="aeb8a-165">**Statisztika**</span><span class="sxs-lookup"><span data-stu-id="aeb8a-165">**Statistics**</span></span>

-   <span data-ttu-id="aeb8a-166">A Korosítási időszak definíciók oldalon adja meg a felhasználó által megadott intervallumokat amelyek a szállítói számlák elosztásának esedékességéhez használatosak.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-166">On the Aging period definitions page, set up user-defined intervals that are used to analyze the maturity distribution of vendor accounts.</span></span>
-   <span data-ttu-id="aeb8a-167">Az Üzletág oldalon hozzon létre üzletágkódokat (LOB) amelyek szállítókhoz rendelhetők.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-167">On the Line of business page, create the line of business (LOB) codes that are assigned to vendors.</span></span>

<span data-ttu-id="aeb8a-168">**Adó 1099**</span><span class="sxs-lookup"><span data-stu-id="aeb8a-168">**Tax 1099**</span></span>

-   <span data-ttu-id="aeb8a-169">A **1099-es mezők** oldalon ellenőrizze és frissítse a minimális mennyiségeket, amelyeket jelenteni kell az adóhatóságnak (IRS), a legfrissebb követelményeik alapján.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-169">On the **1099 fields** page, verify and update the minimum amounts that must be reported to the Internal Revenue Service (IRS), based on the latest IRS requirements.</span></span>

## <a name="optional-setup-for-other-modules"></a><span data-ttu-id="aeb8a-170">**Opcionális beállítások egyéb modulokhoz**</span><span class="sxs-lookup"><span data-stu-id="aeb8a-170">**Optional setup for other modules**</span></span>
<span data-ttu-id="aeb8a-171">**Szervezeti adminisztráció**</span><span class="sxs-lookup"><span data-stu-id="aeb8a-171">**Organization administration**</span></span>

-   <span data-ttu-id="aeb8a-172">A Számsorozatok oldalon adjon meg szám-szekvenciacsoportokat számlaszámokhoz.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-172">On the Number sequences page, set up number sequence groups for invoice numbers.</span></span>
-   <span data-ttu-id="aeb8a-173">A következő oldalakon címeket kell beállítani:</span><span class="sxs-lookup"><span data-stu-id="aeb8a-173">On the following pages, set up address information:</span></span>
    -   <span data-ttu-id="aeb8a-174">Címbeállítás</span><span class="sxs-lookup"><span data-stu-id="aeb8a-174">Address setup</span></span>
    -   <span data-ttu-id="aeb8a-175">NAF-kódok</span><span class="sxs-lookup"><span data-stu-id="aeb8a-175">NAF codes</span></span>
    -   <span data-ttu-id="aeb8a-176">Irányítószámok importálása</span><span class="sxs-lookup"><span data-stu-id="aeb8a-176">Import ZIP/postal codes</span></span>

<span data-ttu-id="aeb8a-177">**Főkönyv**</span><span class="sxs-lookup"><span data-stu-id="aeb8a-177">**General ledger**</span></span>

-   <span data-ttu-id="aeb8a-178">A Pénzügyi dimenziók oldalon adjon meg pénzügyi dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-178">On the Financial dimensions page, set up financial dimensions.</span></span>
-   <span data-ttu-id="aeb8a-179">Az alábbi oldalakon adjon meg adóinformációkat:</span><span class="sxs-lookup"><span data-stu-id="aeb8a-179">On the following pages, set up tax information:</span></span>
    -   <span data-ttu-id="aeb8a-180">Áfakódok</span><span class="sxs-lookup"><span data-stu-id="aeb8a-180">Sales tax codes</span></span>
    -   <span data-ttu-id="aeb8a-181">Áfacsoportok</span><span class="sxs-lookup"><span data-stu-id="aeb8a-181">Sales tax groups</span></span>
    -   <span data-ttu-id="aeb8a-182">Cikkáfacsoportok</span><span class="sxs-lookup"><span data-stu-id="aeb8a-182">Item sales tax groups</span></span>
    -   <span data-ttu-id="aeb8a-183">Számlacsoport</span><span class="sxs-lookup"><span data-stu-id="aeb8a-183">Account group</span></span>
    -   <span data-ttu-id="aeb8a-184">Áfamentességi kódok</span><span class="sxs-lookup"><span data-stu-id="aeb8a-184">Sales tax exempt codes</span></span>
    -   <span data-ttu-id="aeb8a-185">Áfailletékességek</span><span class="sxs-lookup"><span data-stu-id="aeb8a-185">Sales tax jurisdictions</span></span>
    -   <span data-ttu-id="aeb8a-186">Adóhatóságok</span><span class="sxs-lookup"><span data-stu-id="aeb8a-186">Sales tax authorities</span></span>
    -   <span data-ttu-id="aeb8a-187">Áfakiegyenlítési időszakok</span><span class="sxs-lookup"><span data-stu-id="aeb8a-187">Sales tax settlement periods</span></span>

<span data-ttu-id="aeb8a-188">**Készpénz- és bankkezelés**</span><span class="sxs-lookup"><span data-stu-id="aeb8a-188">**Cash and bank management**</span></span>

-   <span data-ttu-id="aeb8a-189">A Fizetés célkódok oldalon adja meg a Központi bank célkódját.</span><span class="sxs-lookup"><span data-stu-id="aeb8a-189">On the Payment purpose codes page, set up the Central Bank purpose code.</span></span>






