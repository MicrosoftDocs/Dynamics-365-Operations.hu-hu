---
title: Intrastat
description: "Ez a cikk információt biztosít az Intrastat árukereskedelemről és esetenként az Európai Unió (EU) országainak/régióinak szolgáltatásairól szóló jelentésekről. Áttekintést biztosít továbbá a jelentési folyamatot illetően és leírja a szükséges beállításokat és előfeltételeket."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: Intrastat
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 28581
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 50526d278df0a09948a5810f00f4fe2834917742
ms.openlocfilehash: e5445d850e2e5afc201662d8c5343d27bc4ecb05
ms.contentlocale: hu-hu
ms.lasthandoff: 10/03/2017

---

# <a name="intrastat"></a><span data-ttu-id="cd6d4-104">Intrastat</span><span class="sxs-lookup"><span data-stu-id="cd6d4-104">Intrastat</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="cd6d4-105">Ez a cikk információt biztosít az Intrastat árukereskedelemről és esetenként az Európai Unió (EU) országainak/régióinak szolgáltatásairól szóló jelentésekről.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-105">This article provides information about Intrastat reporting for the trade of goods and, in some cases, services among countries/regions of the European Union (EU).</span></span> <span data-ttu-id="cd6d4-106">Áttekintést biztosít továbbá a jelentési folyamatot illetően és leírja a szükséges beállításokat és előfeltételeket.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-106">It provides an overview of the reporting process, and describes the required settings and prerequisites.</span></span>

<span data-ttu-id="cd6d4-107">Az Intrastat az Európai Unió (EU) országai/régiói közötti kereskedelemről adatokat gyűjtő és statisztikákat készítő rendszer.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-107">Intrastat is the system for collecting information and generating statistics about the trade of goods among countries/regions of the European Union (EU).</span></span> <span data-ttu-id="cd6d4-108">Intrastat-jelentés szükséges minden olyan esetben, amikor egy termék egy másik EU ország/régió határát átlépi.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-108">Intrastat reporting is required whenever a product crosses the border of another EU country/region.</span></span> <span data-ttu-id="cd6d4-109">Az Intrastat-jelentés több országban/régióban szolgáltatásokra is vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-109">In several countries/regions, Intrastat reporting also applies to services.</span></span> <span data-ttu-id="cd6d4-110">Az Intrastat-jelentésben kötelező és választható elemek gyűjthetők.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-110">Mandatory and optional elements can be collected in Intrastat reporting.</span></span> <span data-ttu-id="cd6d4-111">A következő elemek kötelezőek: az információszolgáltatásért felelős fél adószáma, a referencia-időszak, a forgalom iránya (beérkezés vagy feladás), a nyolc számjegyű vámtarifakód, a partner tagállam (a partner tagállam a bizományosi ország érkezéskor és a partner tagállam a rendeltetési tagállam a feladáskor), a termékek értéke, a termékek mennyisége (nettó súly és kiegészítő egység) és az ügylet jellege.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-111">The following elements are mandatory: the value-added tax (VAT) number of the party that is responsible for providing information, the reference period, the flow (arrival or dispatch), the eight-digit commodity code, the partner member state (member state of consignment on arrivals and member state of destination on dispatches), the value of the goods, the quantity of the goods (net mass and supplementary unit), and the nature of the transaction.</span></span> <span data-ttu-id="cd6d4-112">Országok/régiók opcionális elemeket is gyűjthetnek különböző feltételek mellett.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-112">Countries/regions can also collect optional elements under various conditions.</span></span> <span data-ttu-id="cd6d4-113">Néhány választható elem: származási ország/régió, a szállítási feltételek, szállítási mód, CN8-nál részletesebb vámtarifaszám, a származási régió kiszállításkor és a rendeltetési régió beérkezéskor, a statisztikai eljárás, a statisztikai érték, az áruk leírása, valamint a be vagy kirakodó kikötő/reptér.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-113">Some optional elements are the country/region of origin, the delivery terms, the mode of transport, a more detailed commodity code than CN8, the region of origin on dispatches and the region of destination on arrivals, the statistical procedure, the statistical value, a description of the goods, and the port/airport of loading/unloading.</span></span>

## <a name="overview-of-the-intrastat-reporting-process"></a><span data-ttu-id="cd6d4-114">Az Intrastat jelentési folyamat áttekintése</span><span class="sxs-lookup"><span data-stu-id="cd6d4-114">Overview of the Intrastat reporting process</span></span>
<span data-ttu-id="cd6d4-115">Az alábbi szakaszok leírják az Intrastat-jelentéshez használt teljes információáramlást.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-115">The following sections describe the overall flow of information that is used for Intrastat reporting.</span></span>

### <a name="1-enter-a-transaction-that-crosses-the-border-of-another-eu-countryregion"></a><span data-ttu-id="cd6d4-116">1. Egy másik EU ország/régió határát átlépő tranzakció megindítása</span><span class="sxs-lookup"><span data-stu-id="cd6d4-116">1. Enter a transaction that crosses the border of another EU country/region</span></span>

<span data-ttu-id="cd6d4-117">Vevői számla, szabadszöveges számla, beszerzési számla, projekt számla, vevői szállítólevél, szállítói termékbevételezés vagy átmozgatási rendelés csak akkor kerül át az Intrastat-naplóba, ha a célország/régió típusa (elküldéskor) vagy a bizományosi ország típusa (érkezéskor) **EU**.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-117">A customer invoice, free text invoice, purchase invoice, project invoice, customer packing slip, vendor product receipt, or transfer order is transferred to the Intrastat journal only if the country/region type of the destination (on dispatches) or consignment (on arrivals) is **EU**.</span></span> <span data-ttu-id="cd6d4-118">Ez a funkció a Microsoft Dynamics 365 for Operations 1611-es verziójában kiterjesztésre került, és lehetővé teszi egy közösségen belüli tranzakciónál berakodási címek megadását.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-118">This feature was extended for Microsoft Dynamics 365 for Operations (1611) and allows you to specify lading addresses for an intra-community transaction.</span></span> <span data-ttu-id="cd6d4-119">Ha egy berakodási cím eltér a szállító céges címétől (vagy visszárurendelés esetén vevő üzleti címétől), az Intrastat-jelentések figyelembe veszik ezt az információt.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-119">If a lading address differs with a vendor business address (or customer business address for return order) the Intrastat reporting will operate with this information.</span></span> <span data-ttu-id="cd6d4-120">Értékesítési rendelés, szabadszöveges számla, beszerzési rendelés, szállítói számla, projekt számla vagy átmozgatási rendelés létrehozásakor bizonyos külkereskedelemhez kapcsolódó mezők alapértelmezett értékkel rendelkeznek a dokumentum fejlécében vagy a sorban.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-120">When you create a sales order, free text invoice, purchase order, vendor invoice, project invoice, or transfer order, some fields that are related to foreign trade have default values in the document header or on the line.</span></span> <span data-ttu-id="cd6d4-121">Az alapértelmezett tranzakciókód a **Külkereskedelmi paraméterek** oldal megfelelő mezőjéből származik.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-121">The default transaction code is taken from the corresponding field on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="cd6d4-122">Az alapértelmezett vámtarifaszám, a származási ország/régió és a származási állam/tartomány a cikkről származik.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-122">The default commodity code, country/region of origin, and state/province of origin are taken from the item.</span></span> <span data-ttu-id="cd6d4-123">Az alapértelmezett értékeket módosíthatja, és más külföldi kereskedelemmel kapcsolatos adatokat is megadhat: a statisztikai eljárást, a szállítási módot és a kikötőt.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-123">You can change the default values and can also fill in other foreign trade–related information: the statistics procedure, transport method, and port.</span></span>

### <a name="2-use-the-intrastat-journal-to-generate-information-about-trade-among-eu-countriesregions"></a><span data-ttu-id="cd6d4-124">2. Az Intrastat-jelentés az EU országok/régiók közötti, kereskedelemmel kapcsolatos információ létrehozására szolgál</span><span class="sxs-lookup"><span data-stu-id="cd6d4-124">2. Use the Intrastat journal to generate information about trade among EU countries/regions</span></span>

<span data-ttu-id="cd6d4-125">Statisztikai okokból az EU országok/régiók közötti, kereskedelemmel kapcsolatos információkat minden hónapban létre kell hozni.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-125">For statistical purposes, you generate information about trade among EU countries/regions every month.</span></span> <span data-ttu-id="cd6d4-126">Tranzakciók átvihetők a szabadszöveges számlából, a vevői számlából, vevői szállítólevélből, szállítói számlából, szállítói szállítólevélből, projektszámlából vagy átmozgatási rendelésből, a **Külkereskedelmi paraméterek** oldalon felállított átviteli feltételek szerint.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-126">You can transfer transactions from a free text invoice, customer invoice, customer packing slip, vendor invoice, vendor packing slip, project invoice, or transfer order, according to the transfer criteria that are set up on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="cd6d4-127">Másik lehetőségként a tranzakciók manuálisan is bevihetők.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-127">Alternatively, you can enter transactions manually.</span></span> <span data-ttu-id="cd6d4-128">Ha frissítés szükséges, az átvitt tranzakciók manuálisan frissíthetők az Intrastat-naplóban.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-128">You can manually update transferred transactions in the Intrastat journal, if any updates are required.</span></span> <span data-ttu-id="cd6d4-129">Bizonyos feltételek fennállása esetén, amelyek a **Az Intrastat tömörítése** lapon találhatóak, az Intrastat-naplóban található tranzakciók tömöríthetők.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-129">Under specific conditions that are set up on the **Compression of Intrastat** page, you can compress the transactions in the Intrastat journal.</span></span> <span data-ttu-id="cd6d4-130">Egyes országokban/régiókban kis tranzakciós küszöb alkalmazható.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-130">Some countries/regions let you apply a small transaction threshold.</span></span> <span data-ttu-id="cd6d4-131">Ezután a meghatározott árukód alatti küszöbérték alatt lévő tranzakciók jelentése lehetővé válik.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-131">You can then report transactions that are below that threshold under the specified commodity code.</span></span> <span data-ttu-id="cd6d4-132">Az árukódok a megfelelő Intrastat-napló soraiban frissíthetők a **Minimális limit** beállítás alapján, amely a **Külkereskedelmi paraméterek** lapon található.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-132">You can update the commodity code on the corresponding Intrastat journal lines, based on the **Minimum limit** setting on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="cd6d4-133">Ezek a tranzakciók tömöríthetőek is, **Az Intrastat tömörítése** beállítás alapján.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-133">You can also compress those transactions, based on the **Compression of Intrastat** setting.</span></span> <span data-ttu-id="cd6d4-134">A tranzakció befejezettsége ellenőrizhető az Intrastat-naplóban, a **Beállításának ellenőrzése** beállításnál a **Külkereskedelmi paraméterek** lapon.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-134">You can validate the completeness of the transactions in the Intrastat journal, based on the **Check setup** setting on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="cd6d4-135">A megfelelő mezők adatai a teljesség érdekében ellenőrizhetők: ország/régió, állam vagy tartomány, súly, vámtarifaszám, tranzakciókód, kiegészítő egység, port, eredet, szállítási feltételek, szállítási mód és adómentességi szám.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-135">The data in corresponding fields might be validated for completeness: country/region, state or province, weight, commodity code, transaction code, additional unit, port, origin, terms of delivery, transport method, and tax exempt number.</span></span> <span data-ttu-id="cd6d4-136">A befejezetlen tranzakciók érvénytelenként lesznek megjelölve.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-136">Transactions that aren't completed will be marked as not valid.</span></span>

### <a name="3-use-the-intrastat-journal-to-report-information-about-trade-among-eu-countriesregions"></a><span data-ttu-id="cd6d4-137">3. Az EU országok/régiók közötti kereskedelemmel kapcsolatos információ jelentésére az Intrastat-jelentés használatos.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-137">3. Use the Intrastat journal to report information about trade among EU countries/regions</span></span>

<span data-ttu-id="cd6d4-138">Statisztikai okokból az EU országok/régiók közötti kereskedelemmel kapcsolatos információk jelentése minden hónapban szükséges.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-138">For statistical purposes, you report information about trade among EU countries/regions every month.</span></span> <span data-ttu-id="cd6d4-139">Az Intrastat-jelentés kinyomtatható a **Jelentésformátum-hozzárendelés** beállítások alapján, amelyek a **Külkereskedelmi paraméterek** lapon találhatóak.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-139">You can print the Intrastat report, based on the **Report format mapping** settings on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="cd6d4-140">Elektronikus fájl is létrehozható a **Fájlformátum-hozzárendelés** beállítások alapján, amelyek a **Külkereskedelmi paraméterek** lapon találhatóak.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-140">You can also generate an electronic file, based on the **File format mapping** settings on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="cd6d4-141">Az Intrastat-jelentésekkel kapcsolatos további információért lásd az Intrastat-jelentésekkel kapcsolatos feladatrögzítéseket, ahol a szükséges előfeltételek is megtalálhatók:</span><span class="sxs-lookup"><span data-stu-id="cd6d4-141">For more information about Intrastat reporting, including required prerequisites, see the Intrastat reporting task recordings:</span></span>

-   <span data-ttu-id="cd6d4-142">Uniós Intrastat-nyilatkozat létrehozása,</span><span class="sxs-lookup"><span data-stu-id="cd6d4-142">Generate an EU Intrastat declaration,</span></span>
-   <span data-ttu-id="cd6d4-143">Tranzakciók átvitele az Intrastatba,</span><span class="sxs-lookup"><span data-stu-id="cd6d4-143">Transfer transactions to the Intrastat,</span></span>
-   <span data-ttu-id="cd6d4-144">Berakodási cím megadása egy Közösségen belüli tranzakcióhoz.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-144">Specifying lading address for an intra-community transaction.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cd6d4-145">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="cd6d4-145">Prerequisites</span></span>
<span data-ttu-id="cd6d4-146">Az alábbi táblázatlista mutatja az Intrastat-jelentés előfeltételeit.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-146">The following table lists the prerequisites for Intrastat reporting.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cd6d4-147">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="cd6d4-147">Prerequisite</span></span></th>
<th><span data-ttu-id="cd6d4-148">Leírás</span><span class="sxs-lookup"><span data-stu-id="cd6d4-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="cd6d4-149">Címbeállítás</span><span class="sxs-lookup"><span data-stu-id="cd6d4-149">Address setup</span></span></td>
<td><span data-ttu-id="cd6d4-150">Állítsa be a Nemzetközi Szabványügyi Szervezet (ISO) kódjait az országokhoz/régiókhoz.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-150">Set up International Organization for Standardization (ISO) codes for countries/regions.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cd6d4-151">Jogi személy</span><span class="sxs-lookup"><span data-stu-id="cd6d4-151">Legal entity</span></span></td>
<td><span data-ttu-id="cd6d4-152">Állítsa be az adószámokat az importhoz/exporthoz, az ágazatiszám-kiterjesztést importhoz/exporthoz, és a jogi személyhez hozzárendelt Intrastat kódot.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-152">Set up tax exempt numbers for import/export, the branch number extension for import/export, and the Intrastat code that is assigned to the legal entity.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cd6d4-153">Termékkategória hierarchiája (értékesítési hierarchia, beszerzési hierarchia)</span><span class="sxs-lookup"><span data-stu-id="cd6d4-153">Product category hierarchy (sales hierarchy, procurement hierarchy)</span></span></td>
<td><span data-ttu-id="cd6d4-154">Rendelje hozzá az Intrastat vámtarifakódokat a kategória-csomópontokhoz a <strong>Vámtarifakódok</strong> lapon, amely <strong>Kategóriahierarchia</strong> oldalon található.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-154">Assign the Intrastat commodity codes to the category nodes on the <strong>Commodity codes</strong> tab of the <strong>Category hierarchy</strong> page.</span></span> <span data-ttu-id="cd6d4-155">Ha vámtarifakódot rendel egy szülőkategória-csomóponthoz, a kód a gyermekkategória-csomópontokra is vonatkozni fog.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-155">When you assign a commodity code to a parent category node, that code is applicable to all child category nodes.</span></span> <span data-ttu-id="cd6d4-156">A kiválasztott vámtarifakódok elérhetőek lesznek <strong>Kijelölt</strong> nézetben, amennyiben kiválaszt egy vámtarifakódot a megjelent termék részleteiben, és az értékesítési rendelés, a beszerzési rendelés, és átmozgatási rendelés sorban.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-156">The selected commodity codes will be available in the <strong>Selected</strong> view when you select a commodity code in the released product details, and on sales order, purchase order, and transfer order lines.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cd6d4-157">Megjelent termék részletei</span><span class="sxs-lookup"><span data-stu-id="cd6d4-157">Released product details</span></span></td>
<td><span data-ttu-id="cd6d4-158">Állítsa be a kiadott termékekre vonatkozó alábbi külkereskedelmi adatokat:</span><span class="sxs-lookup"><span data-stu-id="cd6d4-158">Set up the following foreign trade data for released products:</span></span>
<ul>
<li><span data-ttu-id="cd6d4-159"><strong>Vámtarifakód</strong> – Válassza ki a hozzárendelt termékkategóriából származó kiválasztott vámtarifakódok listájából vagy az Intrastat vámtarifakódok teljes listájából.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-159"><strong>Commodity code</strong> – Select from either the list of selected commodities that is retrieved from assigned product categories or the full list of Intrastat commodity codes.</span></span></li>
<li><span data-ttu-id="cd6d4-160"><strong>Az statisztikai költségek százalékos értéke</strong></span><span class="sxs-lookup"><span data-stu-id="cd6d4-160"><strong>Statistical charges percentage</strong></span></span></li>
<li><span data-ttu-id="cd6d4-161"><strong>Származási ország/régió</strong> – Válassza ki az alapértelmezett országot/régiót, ahol az árukat beszerezték vagy előállították.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-161"><strong>Country/region of origin</strong> – Select the default country/region where the goods were completely obtained or produced.</span></span></li>
<li><span data-ttu-id="cd6d4-162"><strong>Származási/rendeltetési állam/tartomány</strong> – Válassza ki az alapértelmezett célállamot/céltartományt az érkezéshez és a származási államot/tartományt az elküldéshez.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-162"><strong>State/province of origin/destination</strong> – Select the default state/province of destination for arrivals and the state/province of origin for dispatches.</span></span></li>
<li><span data-ttu-id="cd6d4-163"><strong>Nettó súly (kg)</strong></span><span class="sxs-lookup"><span data-stu-id="cd6d4-163"><strong>Net weight in kg</strong></span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cd6d4-164">Vevők</span><span class="sxs-lookup"><span data-stu-id="cd6d4-164">Customers</span></span></td>
<td><span data-ttu-id="cd6d4-165">Állítsa be a vevő EU országbeli/régióbeli szállítási címét.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-165">Set up the customer delivery address in the EU country/region.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cd6d4-166">Szállítók</span><span class="sxs-lookup"><span data-stu-id="cd6d4-166">Vendors</span></span></td>
<td><span data-ttu-id="cd6d4-167">Állítsa be a szállító EU országbeli/régióbeli címét.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-167">Set up the vendor address in the EU country/region.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cd6d4-168">Vegyes költségek</span><span class="sxs-lookup"><span data-stu-id="cd6d4-168">Miscellaneous charges</span></span></td>
<td><span data-ttu-id="cd6d4-169">Állítsa be a vegyes költségek kódját, hogy a számlaösszeg, a statisztikai összeg vagy mindkettő tartalmazza azt.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-169">Set up the miscellaneous charges code to include in the invoice amount, the statistical amount, or both.</span></span> <span data-ttu-id="cd6d4-170">A <strong>Költségkódok</strong> oldalon, a <strong>Külkereskedelem</strong> lapon, engedélyezze az <strong>Intrastat számlaérték</strong> -et, hogy a költségek összegét is tartalmazza a számlaérték, és engedélyezze <strong>Intrastat statisztikai érték</strong> -et, hogy a költségek összegét is tartalmazza a statisztikai érték.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-170">On the <strong>Charges codes</strong> page, on the <strong>Foreign trade</strong> tab, enable <strong>Intrastat invoice value</strong> to include the charges amount in the invoice value, and enable <strong>Intrastat statistical value</strong> to include the charges amount in the statistical value.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cd6d4-171">Elektronikus jelentés</span><span class="sxs-lookup"><span data-stu-id="cd6d4-171">Electronic reporting</span></span></td>
<td><span data-ttu-id="cd6d4-172">Állítsa be az elektronikus jelentéskészítési konfigurációkat az Intrastat adatok egy olyan elektronikus fájlba történő exportálásához, amelynek formátuma megegyezik a hatóságok által kérttel, és az Intrastat fájlok felhasználóbarát, olvasható megtekintéséhez (például Microsoft Excelben).</span><span class="sxs-lookup"><span data-stu-id="cd6d4-172">Set up electronic reporting configurations to export Intrastat data in an electronic file that has the format that is requested by the relevant authorities, and to preview Intrastat data in a user-friendly, readable format (for example, in Microsoft Excel).</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cd6d4-173">Raktárkészlet-nyilvántartás</span><span class="sxs-lookup"><span data-stu-id="cd6d4-173">Warehousing</span></span></td>
<td><span data-ttu-id="cd6d4-174">Társítsa a szállítói számlákat a raktárkódokkal adómentességi szám kitöltésére az átmozgatási rendelés átvitelekor.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-174">Associate vendor accounts with warehouse codes for filling tax exempt number when transferring Transfer order.</span></span></td>
</tr>
</tbody>
</table>

## <a name="setup"></a><span data-ttu-id="cd6d4-175">Beállítás</span><span class="sxs-lookup"><span data-stu-id="cd6d4-175">Setup</span></span>
<span data-ttu-id="cd6d4-176">Az alábbi szakaszok leírják az Intrastat-jelentéshez szükséges beállításokat.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-176">The following sections describe the settings that are required for Intrastat reporting.</span></span>

### <a name="set-up-all-required-intrastat-related-lists"></a><span data-ttu-id="cd6d4-177">Állítsa be az összes szükséges Intrastattal kapcsolatos listát</span><span class="sxs-lookup"><span data-stu-id="cd6d4-177">Set up all required Intrastat-related lists</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cd6d4-178">Lista</span><span class="sxs-lookup"><span data-stu-id="cd6d4-178">List</span></span></th>
<th><span data-ttu-id="cd6d4-179">További információk</span><span class="sxs-lookup"><span data-stu-id="cd6d4-179">Additional information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="cd6d4-180">Árucikk-kódok</span><span class="sxs-lookup"><span data-stu-id="cd6d4-180">Commodity codes</span></span></td>
<td><span data-ttu-id="cd6d4-181">Állítson be <strong>Vámtarifakód</strong> típusú kategóriahierarchiát és adja meg az összes vámtarifakódot a kombinált nomenklatúra-lista alapján.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-181">Set up a category hierarchy of type <strong>Commodity code</strong>, and enter all commodity codes according to the combined nomenclature list.</span></span> <span data-ttu-id="cd6d4-182">Minden árucikknél a következő adatokat adja meg:</span><span class="sxs-lookup"><span data-stu-id="cd6d4-182">For each commodity, you set up the following information:</span></span>
<ul>
<li><span data-ttu-id="cd6d4-183">Árucikk megnevezése és vámtarifaszám</span><span class="sxs-lookup"><span data-stu-id="cd6d4-183">The name of the commodity and the commodity code</span></span></li>
<li><span data-ttu-id="cd6d4-184">Könnyen megjegyezhető név és/vagy a lefordított név</span><span class="sxs-lookup"><span data-stu-id="cd6d4-184">The friendly name and/or translated name</span></span></li>
<li><span data-ttu-id="cd6d4-185">A további (kiegészítő) egységek jelentésének beállításai a <strong>Külkereskedelem</strong> lapon. A kiegészítő egységet az egységlistában választhatja ki.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-185">Settings for reporting additional (supplementary) units on the <strong>Foreign trade</strong> tab. You can select the additional unit in the unit list.</span></span> <span data-ttu-id="cd6d4-186">Megadhatja az is, hogy a kiválasztott kiegészítő egység mellett az áruk súlyát is jelenteni kell-e.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-186">You can also specify whether the weight of commodities must be reported in addition to the selected additional unit.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cd6d4-187">Tranzakciókódok</span><span class="sxs-lookup"><span data-stu-id="cd6d4-187">Transaction codes</span></span></td>
<td><span data-ttu-id="cd6d4-188">Állítsa be a tranzakció jellegét a saját országa/régiója követelményei szerint.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-188">Set up the nature of the transaction according to your country's/region's requirements.</span></span> <span data-ttu-id="cd6d4-189">Minden egyes beállított tranzakciókódhoz be kell állítania az átmozgatási rendelés és eladási/beszerzési rendelés számlaösszegének és statisztikai összegének kiszámítására vonatkozó szabályokat.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-189">For each transaction code that you set up, you must set up the rules for calculating invoice amounts and statistical amounts for transfer orders and sales/purchase orders.</span></span>
<ul>
<li><span data-ttu-id="cd6d4-190">Átmozgatási rendeléseknél a számlaösszeg és statisztikai összeg kiszámítására a következő szabályokat állítsa be:</span><span class="sxs-lookup"><span data-stu-id="cd6d4-190">For transfer orders, you set up one of the following rules for calculating invoice amounts and statistical amounts:</span></span>
<ul>
<li><span data-ttu-id="cd6d4-191"><strong>Üres</strong> – Az összeg 0 (nulla) lesz.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-191"><strong>Empty</strong> – The amount will be 0 (zero).</span></span></li>
<li><span data-ttu-id="cd6d4-192"><strong>Pénzügyi önköltség</strong> – Az összeg meg fog egyezni a pénzügyi költséggel.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-192"><strong>Financial cost amount</strong> – The amount will be equal to the financial cost.</span></span></li>
<li><span data-ttu-id="cd6d4-193"><strong>Teljes költség</strong> – Az összeg meg fog egyezni a tranzakció teljes költségével.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-193"><strong>Total cost</strong> – The amount will be equal to the total cost of the transaction.</span></span></li>
<li><span data-ttu-id="cd6d4-194"><strong>Manuális</strong> – Az összeg meg fog egyezni az átmozgatási rendelés sorában manuálisan megadott az összeggel.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-194"><strong>Manual</strong> – The amount will be equal to the amount that is manually specified on the transfer order line.</span></span></li>
</ul></li>
<li><span data-ttu-id="cd6d4-195">Értékesítési rendeléseknél és beszerzési rendeléseknél a számlaösszeg és statisztikai összeg kiszámítására a következő szabályokat állítsa be:</span><span class="sxs-lookup"><span data-stu-id="cd6d4-195">For sales orders and purchase orders, you set up one of the following rules for calculating invoice amounts and statistical amounts:</span></span>
<ul>
<li><span data-ttu-id="cd6d4-196"><strong>Üres</strong> – Az összeg 0 (nulla) lesz.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-196"><strong>Empty</strong> – The amount will be 0 (zero).</span></span></li>
<li><span data-ttu-id="cd6d4-197"><strong>Számlaösszeg</strong> – Az összeg meg fog egyezni az árucikkért számlázott összeggel.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-197"><strong>Invoice amount</strong> – The amount will be equal to the amount that is invoiced for the commodity.</span></span></li>
<li><span data-ttu-id="cd6d4-198"><strong>Alapösszeg</strong> – Az összeg meg fog egyezni a számlázandó összeggel, bármilyen engedmény alkalmazása előtt.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-198"><strong>Base amount</strong> – The amount will be equal to the amount that would be invoiced before any discount is applied.</span></span></li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cd6d4-199">Szállítási módok</span><span class="sxs-lookup"><span data-stu-id="cd6d4-199">Transport methods</span></span></td>
<td><span data-ttu-id="cd6d4-200">Állítsa be a szállítási módot a saját országa/régiója követelményei szerint.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-200">Set up the transport mode according to your country's/region's requirements.</span></span> <span data-ttu-id="cd6d4-201">Minden szállítási módhoz állíthat be egy alapértelmezett szállítási módot a <strong>Külkereskedelmi</strong> lapon.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-201">For each delivery mode, you can set up a default transport method on the <strong>Foreign trade</strong> tab.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cd6d4-202">Kikötők</span><span class="sxs-lookup"><span data-stu-id="cd6d4-202">Ports</span></span></td>
<td><span data-ttu-id="cd6d4-203">Állítsa be a berakodás/kirakodás kikötőjét/repülőterét, ha az országa/régiója gyűjti ezeket az adatokat.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-203">Set up the port/airport of loading/unloading if this information is collected by your country/region.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cd6d4-204">Statisztikai eljárások</span><span class="sxs-lookup"><span data-stu-id="cd6d4-204">Statistics procedures</span></span></td>
<td><span data-ttu-id="cd6d4-205">Állítsa be a statisztikai eljárást, ha országa/régiója gyűjti ezeket az adatokat.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-205">Set up the statistical procedure if this information is collected by your country/region.</span></span></td>
</tr>
</tbody>
</table>

### <a name="set-up-rules-for-compressing-intrastat-transactions"></a><span data-ttu-id="cd6d4-206">Állítsa be az Intrastat tranzakciók tömörítésére vonatkozó szabályokat</span><span class="sxs-lookup"><span data-stu-id="cd6d4-206">Set up rules for compressing Intrastat transactions</span></span>

<span data-ttu-id="cd6d4-207">Az **Az Intrastat tömörítése** lapon kiválaszthatja a tömörítéshez használni kívánt mezőket.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-207">On the **Compression of Intrastat** page, you can select the fields to use for compression.</span></span> <span data-ttu-id="cd6d4-208">Minden tranzakció amely ugyanazokat az értékkombinációkat tartalmazza az Intrastat-napló kiválasztott mezőihez, egy tranzakcióba lesz tömörítve az Intrastat-napló Tömörítés funkciójának futtatásakor.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-208">All transactions that have the same combination of values for the selected fields in the Intrastat journal will be compressed into a single transaction when you run the Compress function in the Intrastat journal.</span></span>

### <a name="set-up-foreign-trade-parameters"></a><span data-ttu-id="cd6d4-209">Külkereskedelmi paraméterek beállítása</span><span class="sxs-lookup"><span data-stu-id="cd6d4-209">Set up foreign trade parameters</span></span>

<span data-ttu-id="cd6d4-210">Használja a **Külkereskedelmi paraméterek** lapot az alábbi táblázatban található adatok beállításához.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-210">Use the **Foreign trade parameters** page to set up the parameters in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cd6d4-211">Lap</span><span class="sxs-lookup"><span data-stu-id="cd6d4-211">Tab</span></span></th>
<th><span data-ttu-id="cd6d4-212">Paraméterek</span><span class="sxs-lookup"><span data-stu-id="cd6d4-212">Parameters</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="cd6d4-213">Általános</span><span class="sxs-lookup"><span data-stu-id="cd6d4-213">General</span></span></td>
<td><ul>
<li><span data-ttu-id="cd6d4-214"><strong>Általános</strong> – Adja meg a következő információkat:</span><span class="sxs-lookup"><span data-stu-id="cd6d4-214"><strong>General</strong> – Specify the following information:</span></span>
<ul>
<li><span data-ttu-id="cd6d4-215">Az értékesítési rendelésekre, beszerzési rendelésekre, jóváírásokra és átmozgatási rendelésre vonatkozó alapértelmezett tranzakciós kódok.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-215">The default transaction codes for sales orders, purchase orders, credit notes, and transfer orders.</span></span> <span data-ttu-id="cd6d4-216">A jóváírásokhoz beállított tranzakciós kódok a tényleges áruk visszatérítési kódjaiként is használatosak és használatosak az eltérő tényleges visszatérítések és jóváírási helyesbítés összevetésére.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-216">The transaction code that is set up for credit notes is also used as the code for physical goods return and is used for deviating physical returns versus correction credit notes.</span></span></li>
<li><span data-ttu-id="cd6d4-217">Az Intrastat-jelentés készítésért felelős alkalmazott.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-217">The employee who is responsible for preparing Intrastat reports.</span></span></li>
</ul></li>
<li><span data-ttu-id="cd6d4-218"><strong>Minimumhatár</strong> – Adja meg a küszöbérték alatt lévő tranzakciók frissítési beállításait:</span><span class="sxs-lookup"><span data-stu-id="cd6d4-218"><strong>Minimum limit</strong> – Specify the settings for updating transactions that are below the threshold:</span></span>
<ul>
<li><span data-ttu-id="cd6d4-219">A küszöbösszeg és küszöbsúly</span><span class="sxs-lookup"><span data-stu-id="cd6d4-219">The threshold amount and weight</span></span></li>
<li><span data-ttu-id="cd6d4-220">A küszöbérték alatt lévő tranzakcióra alkalmazandó vámtarifakód</span><span class="sxs-lookup"><span data-stu-id="cd6d4-220">The commodity code to apply to transactions that are under the threshold</span></span></li>
</ul></li>
<li><span data-ttu-id="cd6d4-221"><strong>Átvitel</strong> – Adja meg a tranzakciók Intrastat-naplóba való átvitelének feltételeit.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-221"><strong>Transfer</strong> – Specify the criteria for transferring transactions to the Intrastat journal.</span></span> <span data-ttu-id="cd6d4-222">Megadhatja, hogy a tranzakciók csak akkor kerüljenek átvitelre, amikor a cikkek megfelelnek egy, vagy az összes alábbi feltételnek.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-222">You can specify that transactions are transferred only when the items meet one or all of the following criteria:</span></span>
<ul>
<li><span data-ttu-id="cd6d4-223">A cikk nem szolgáltatási tétel.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-223">The items aren't service items.</span></span></li>
<li><span data-ttu-id="cd6d4-224">A cikk rendelkezik vámtarifakóddal.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-224">The items have a commodity code.</span></span></li>
<li><span data-ttu-id="cd6d4-225">A cikk rendelkezik súllyal.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-225">The items have a weight.</span></span></li>
<li><span data-ttu-id="cd6d4-226">Cikkek rendelkezik kiegészítő egységekkel.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-226">The items have additional units.</span></span></li>
</ul></li>
<li><span data-ttu-id="cd6d4-227"><strong>Beállítások ellenőrzése</strong> – Adja meg Intrastat-adatok befejezettségének ellenőrzésére vonatkozó szabályokat.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-227"><strong>Check setup</strong> – Specify the rules for validating the completeness of Intrastat data.</span></span> <span data-ttu-id="cd6d4-228">Kiválaszthatja, hogy mely adatok ellenőrzöttek.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-228">You can select which data is validated.</span></span></li>
<li><span data-ttu-id="cd6d4-229"><strong>Kerekítési szabályok</strong> – Adja meg az Intrastat-jelentésben szereplő összegek és súlyok kerekítésére vonatkozó következő beállításokat:</span><span class="sxs-lookup"><span data-stu-id="cd6d4-229"><strong>Rounding rules</strong> – Specify the following settings for rounding amounts and weights in Intrastat reporting:</span></span>
<ul>
<li><span data-ttu-id="cd6d4-230">A kerekítési szabály (pontosság)</span><span class="sxs-lookup"><span data-stu-id="cd6d4-230">The rounding rule (precision)</span></span></li>
<li><span data-ttu-id="cd6d4-231">A kerekítés módja: felfelé, lefelé vagy normál</span><span class="sxs-lookup"><span data-stu-id="cd6d4-231">The rounding method: up, down, or normal</span></span></li>
<li><span data-ttu-id="cd6d4-232">Az értékekre és súlyokra vonatkozó a tizedesjegyek száma</span><span class="sxs-lookup"><span data-stu-id="cd6d4-232">The number of decimal places for amounts and weights</span></span></li>
<li><span data-ttu-id="cd6d4-233">Útmutató az 1 kilogrammnál (kg) kisebb súlyokra vonatkozó kerekítéshez: legfeljebb 1 kg, normál vagy nincs kerekítés</span><span class="sxs-lookup"><span data-stu-id="cd6d4-233">Instructions for rounding weights that are less than 1 kilogram (kg): up to 1 kg, normal, or no rounding</span></span></li>
</ul></li>
<li><span data-ttu-id="cd6d4-234"><strong>Elektronikus jelentés</strong> – Adja meg a hivatkozásokat az elektronikus jelentéskészítés konfigurációihoz, így létrehozhat elektronikus fájlokat és jelentést.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-234"><strong>Electronic reporting</strong> – Specify references to electronic reporting configurations, so that you can generate an electronic file and report.</span></span></li>
<li><span data-ttu-id="cd6d4-235"><strong>Vámtarifakódok hierarchiája</strong> – Adja meg a kategóriahierarchiáját annak a <strong>Vámtarifakód</strong> típusnak amely az Intrastat CN8 vámtarifakódot jelöli.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-235"><strong>Commodity code hierarchy</strong> – Specify the category hierarchy of the <strong>Commodity code</strong> type that represents Intrastat commodity code CN8.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cd6d4-236">Az ügynök kapcsolattartási adatai</span><span class="sxs-lookup"><span data-stu-id="cd6d4-236">Agent contact information</span></span></td>
<td><span data-ttu-id="cd6d4-237">Adja meg az ügynök nevét, címét, adószámát, telefonszámát és faxszámát.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-237">Specify the agent's name, address, tax exempt number, telephone number, and fax number.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cd6d4-238">Ország vagy régió tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="cd6d4-238">Country/region properties</span></span></td>
<td><span data-ttu-id="cd6d4-239">Állítsa az aktuális jogi személy országát/régióját a következőre: <strong>Belföldi</strong>.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-239">Set the country/region of the current legal entity to <strong>Domestic</strong>.</span></span> <span data-ttu-id="cd6d4-240">Állítsa az EU kereskedelemben aktuális jogi személlyel résztvevő EU országok/régiók országok/régióját a következőre: <strong>EU</strong>.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-240">Set the country/region of EU countries/regions that participate in EU trade with the current legal entity to <strong>EU</strong>.</span></span> <span data-ttu-id="cd6d4-241">Az egyes országokhoz/régiókhoz, külkereskedelmi célból, adja meg az országkódot/régiókódot.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-241">For each country/region, you also identify country/region code for foreign trade purposes.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cd6d4-242">Számsorozat</span><span class="sxs-lookup"><span data-stu-id="cd6d4-242">Number sequence</span></span></td>
<td><span data-ttu-id="cd6d4-243">Adja meg a számsorozatot az Intrastat-naplóhoz.</span><span class="sxs-lookup"><span data-stu-id="cd6d4-243">Specify the number sequence for the Intrastat journal.</span></span></td>
</tr>
</tbody>
</table>

 



