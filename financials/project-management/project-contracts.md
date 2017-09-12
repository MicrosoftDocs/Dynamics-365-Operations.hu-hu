---
title: "Projektszerződések"
description: "Ez a cikk a különféle projektekhez és finanszírozási forrásokhoz készíthető projektszerződéseket mutatja be példákkal, továbbá ismerteti a szerződéskezelés és a projektmegrendelők felé történő számlázás módszereit a Microsoft Dynamics 365 for Finance and Operations Enterprise edition rendszerben."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjProjectContractsListPage, ProjProjectsListPage
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 23561
ms.assetid: bfd18d9b-d9a6-4e21-bc95-bf4af45f617f
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: d13362acf70edc03a47662c4c3eff680cc04bd8f
ms.contentlocale: hu-hu
ms.lasthandoff: 07/18/2017

---

# <a name="project-contracts"></a><span data-ttu-id="9a62a-103">Projektszerződések</span><span class="sxs-lookup"><span data-stu-id="9a62a-103">Project contracts</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="9a62a-104">Ez a cikk a különféle projektekhez és finanszírozási forrásokhoz készíthető projektszerződéseket mutatja be példákkal, továbbá ismerteti a szerződéskezelés és a projektmegrendelők felé történő számlázás módszereit a Microsoft Dynamics 365 for Finance and Operations Enterprise edition rendszerben.</span><span class="sxs-lookup"><span data-stu-id="9a62a-104">This article describes and provides examples of the project contracts that you can create for various types of projects and funding sources, and how you can manage contracts and invoice project customers in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span>

<span data-ttu-id="9a62a-105">A projektszerződés teljesítésére létrehozott projekt típusa határozza meg a megrendelő felé történő számlakiállítás módszerét.</span><span class="sxs-lookup"><span data-stu-id="9a62a-105">The type of project that you create for a project contract determines the method that is used to invoice project customers.</span></span> <span data-ttu-id="9a62a-106">A projektszerződés és a hozzá kapcsolódó projekt módosítható, de a projekt típusa nem.</span><span class="sxs-lookup"><span data-stu-id="9a62a-106">You can change a project contract and the related project, but you can't change the project type.</span></span> 

<span data-ttu-id="9a62a-107">Projektszerződés használatával egy vagy több projektet számlázhat ki egyszerre.</span><span class="sxs-lookup"><span data-stu-id="9a62a-107">By using a project contract, you can invoice one or more projects at the same time.</span></span> <span data-ttu-id="9a62a-108">A projektszerződés elősegíti annak biztosítását is, hogy a projektstruktúrában szereplő összes részprojektnél konzisztens legyen a számlázási eljárás.</span><span class="sxs-lookup"><span data-stu-id="9a62a-108">The project contract also helps guarantee a consistent invoicing procedure for every subproject in a project structure.</span></span> 

<span data-ttu-id="9a62a-109">Minden számlázandó projektet projektszerződéshez kell társítani.</span><span class="sxs-lookup"><span data-stu-id="9a62a-109">Every project that will be invoiced must be associated with a project contract.</span></span> <span data-ttu-id="9a62a-110">A projektszerződés beállításai az ahhoz társított összes projektre és alprojektre vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="9a62a-110">The settings for a project contract apply to all projects and subprojects that are associated with that project contract.</span></span> 

<span data-ttu-id="9a62a-111">A projektszerződés egy vagy több finanszírozási forrást határozhat meg.</span><span class="sxs-lookup"><span data-stu-id="9a62a-111">A project contract can specify one or more sources of funding.</span></span> <span data-ttu-id="9a62a-112">Ennek köszönhetően a számlázás felosztható több finanszírozó között, finanszírozási korlátot lehet beállítani ahhoz, hogy egy-egy finanszírozási forrásnak ne számlázzanak ki a megszabottnál nagyobb összeget, illetve finanszírozási szabályokat lehet beállítani a kiadások terheléséhez.</span><span class="sxs-lookup"><span data-stu-id="9a62a-112">Therefore, you can split the billing among multiple funders, set up funding limits so that funding sources are not billed more than a specified amount, and configure funding rules for charging expenditures.</span></span>

## <a name="funding-for-project-contracts"></a><span data-ttu-id="9a62a-113">Finanszírozás projektszerződésekre</span><span class="sxs-lookup"><span data-stu-id="9a62a-113">Funding for project contracts</span></span>
<span data-ttu-id="9a62a-114">Egyes projektszerződések megadják, hogy a projektköltségek finanszírozásának felelőssége megoszlik több fél között..</span><span class="sxs-lookup"><span data-stu-id="9a62a-114">Some project contracts specify that multiple parties share the responsibility for funding the project costs.</span></span> <span data-ttu-id="9a62a-115">Íme néhány példa:</span><span class="sxs-lookup"><span data-stu-id="9a62a-115">Here are some examples:</span></span>

-   <span data-ttu-id="9a62a-116">Egy több osztállyal rendelkező nagy vevő azt kéri, hogy egy projekt finanszírozása osztály szerint legyen felosztva.</span><span class="sxs-lookup"><span data-stu-id="9a62a-116">A large customer that has multiple divisions requests that funding of a project be split by division.</span></span>
-   <span data-ttu-id="9a62a-117">Az Ön vállalata egy külső szervezettel osztja meg egy nagy projekt költségeit.</span><span class="sxs-lookup"><span data-stu-id="9a62a-117">Your company shares the costs of a large project with an external organization.</span></span>
-   <span data-ttu-id="9a62a-118">Egy úttal kapcsolatos projektet két közigazgatási terület közösen finanszíroz.</span><span class="sxs-lookup"><span data-stu-id="9a62a-118">A  road project is co-funded by two municipalities.</span></span>
-   <span data-ttu-id="9a62a-119">Egy híddal kapcsolatos projektet valamilyen állami támogatás és egy magánvállalkozás finanszíroz.</span><span class="sxs-lookup"><span data-stu-id="9a62a-119">A bridge project is funded by a government grant and a private corporation.</span></span>

<span data-ttu-id="9a62a-120">A Finance and Operations rendszerben feloszthatja egyetlen tranzakció vagy egy teljes projekt számlázását több vevő, támogatás vagy szervezet között.</span><span class="sxs-lookup"><span data-stu-id="9a62a-120">In Finance and Operations, you can split the billing for a single transaction or an entire project among multiple customers, grants, or organizations.</span></span> 

<span data-ttu-id="9a62a-121">A több finanszírozóval rendelkező projektek esetén finanszírozási forrásnak neveznek minden olyan felet, amely hozzájárul egy speciális finanszírozási projekt finanszírozásához.</span><span class="sxs-lookup"><span data-stu-id="9a62a-121">In projects that have multiple funders, all parties that contribute to the funding of an advanced funding project are called funding sources.</span></span> <span data-ttu-id="9a62a-122">Miután egy vevő, szervezet vagy támogatás finanszírozási forrásként kerül meghatározásra, hozzárendelhető egy vagy több finanszírozási szabályhoz.</span><span class="sxs-lookup"><span data-stu-id="9a62a-122">After a customer, organization, or grant is defined as a funding source, it can be assigned to one or more funding rules.</span></span> <span data-ttu-id="9a62a-123">A finanszírozási szabályok tartalmazzák azon feltételeket, amelyek meghatározzák, hogy hogyan oszlanak fel a költségek egy projekt különböző finanszírozási forrásai között.</span><span class="sxs-lookup"><span data-stu-id="9a62a-123">Funding rules contain the criteria that determines how charges are allocated to the various funding sources for a project.</span></span> 

<span data-ttu-id="9a62a-124">Mivel a raktározott cikkeket, például azokat, amelyek megjelennek beszerzési igényléseken és beszerzési rendeléseken, nem lehet megosztani, a költség összeget sem lehet megosztani több finanszírozási forrás között az elosztás idejében.</span><span class="sxs-lookup"><span data-stu-id="9a62a-124">Because stocked items, such as those that appear on purchase requisitions and purchase orders, can't be split, the cost amount can't be split among multiple funding sources at the time of distribution.</span></span> <span data-ttu-id="9a62a-125">Emiatt a finanszírozási forrás érték marad 0 (nulla) amíg a készletkiadás feladásra kerül.</span><span class="sxs-lookup"><span data-stu-id="9a62a-125">Therefore, the funding source value remains 0 (zero) until the inventory issue is posted.</span></span> <span data-ttu-id="9a62a-126">Amikor a készletkiadás feladásra kerül, a költségösszeg felosztása a projekt számlafelosztási szabályai alapján történik.</span><span class="sxs-lookup"><span data-stu-id="9a62a-126">When the inventory issue is posted, the cost amount is distributed according to the account distribution rules for the project.</span></span>

<span data-ttu-id="9a62a-127">Íme néhány lépés, melyet megtehet annak érdekében, hogy megkönnyítse a számlázás felosztását több finanszírozási forrás között:</span><span class="sxs-lookup"><span data-stu-id="9a62a-127">Here are some steps that you can take to make it easier to split the billing among multiple funding sources:</span></span>

-   <span data-ttu-id="9a62a-128">Adja meg, hogy minden tranzakció, melyet egy projektre megadnak, ugyanazon értékesítési pénznemet használja, mint a projektszerződés.</span><span class="sxs-lookup"><span data-stu-id="9a62a-128">Specify that all transactions that are entered for a project use the same sales currency as the project contract.</span></span>
-   <span data-ttu-id="9a62a-129">Állítson fel finanszírozási korlátokat úgy, hogy egy finanszírozási forrás ne legyen egy megadott összegnél többre számlázva egy projekt felé.</span><span class="sxs-lookup"><span data-stu-id="9a62a-129">Set up funding limits, so that a funding source isn't invoiced more than a specified amount toward a project.</span></span>
-   <span data-ttu-id="9a62a-130">Állítson be finanszírozási szabályokat és finanszírozási korlátokat minden dolgozóra, cikkre, kategóriára, kategóriacsoportra és tranzakciótípusra (vagy az összes tranzakciótípusra).</span><span class="sxs-lookup"><span data-stu-id="9a62a-130">Configure funding rules and funding limits for each worker, item, category, category group, and transaction type (or for all transaction types).</span></span>
-   <span data-ttu-id="9a62a-131">Jelöljön ki választható kezdő és záró dátumokat, hogy meghatározza az időszakot, amikor az egyes finanszírozási szabályok érvényesek.</span><span class="sxs-lookup"><span data-stu-id="9a62a-131">Select optional start and end dates to define the period when each funding rule is valid.</span></span>
-   <span data-ttu-id="9a62a-132">Adja meg azt a százalékos értéket, amelyért minden finanszírozási forrást felelős.</span><span class="sxs-lookup"><span data-stu-id="9a62a-132">Specify the percentage that each funding source is responsible for.</span></span>
-   <span data-ttu-id="9a62a-133">Adja meg, hogy melyik finanszírozási forrás felelős kerekítési különbségekért, amelyeket finanszírozás felosztási számítások okoznak.</span><span class="sxs-lookup"><span data-stu-id="9a62a-133">Specify which funding source is responsible for rounding differences that are caused by funding allocation calculations.</span></span>
-   <span data-ttu-id="9a62a-134">Állítson fel szabályokat, amelyek meghatározzák, hogyan kerülnek a projektköltségek számlázásra külső vevőknek és felszámolásra belső szervezetek részére.</span><span class="sxs-lookup"><span data-stu-id="9a62a-134">Set up rules that determine how project costs are invoiced to external customers and charged to internal organizations.</span></span>
-   <span data-ttu-id="9a62a-135">Rögzítse a tranzakciókat egy várakozó finanszírozási számlán, amíg további finanszírozást tud szerezni, vagy amíg úgy dönt, hogy belsőleg viseli a költségeket.</span><span class="sxs-lookup"><span data-stu-id="9a62a-135">Record transactions in an on-hold funding account until additional funding can be obtained, or until you decide to bear the costs internally.</span></span>

<span data-ttu-id="9a62a-136">Annak megállapításához, hogy melyik adócsoportot kell társítani egy tranzakcióhoz, a projektben egy adócsoport-hozzárendelést keresnek.</span><span class="sxs-lookup"><span data-stu-id="9a62a-136">To determine which tax group to associate with a transaction, the project is searched for a tax group assignment.</span></span> <span data-ttu-id="9a62a-137">Ha adócsoport-hozzárendelés nem került létrehozásra projektszinten, a projektszerződésben kell keresni.</span><span class="sxs-lookup"><span data-stu-id="9a62a-137">If no tax group assignment has been made at the project level, the project contract is searched.</span></span>

### <a name="example-multiple-funding-sources-simple"></a><span data-ttu-id="9a62a-138">Példa: Több finanszírozási forrás (egyszerű)</span><span class="sxs-lookup"><span data-stu-id="9a62a-138">Example: Multiple funding sources (simple)</span></span>

<span data-ttu-id="9a62a-139">A következő táblázat esteket ad meg a finanszírozási felosztás kezelésére több finanszírozási forrás között.</span><span class="sxs-lookup"><span data-stu-id="9a62a-139">The following table provides scenarios for managing funding allocation among multiple funding sources.</span></span> <span data-ttu-id="9a62a-140">Ezek az esetek a következő feltevéseken alapulnak:</span><span class="sxs-lookup"><span data-stu-id="9a62a-140">These scenarios are based on the following assumptions:</span></span>

-   <span data-ttu-id="9a62a-141">A prioritási beállítások hatással vannak a finanszírozás felosztására, egyéb finanszírozási szabályok feltételeinek alkalmazása előtt.</span><span class="sxs-lookup"><span data-stu-id="9a62a-141">Priority settings are factored into the allocation of funds before other funding rule criteria are applied.</span></span>
-   <span data-ttu-id="9a62a-142">Dátumtartomány nem lett megadva annak meghatározására, hogy mikor érvényes a finanszírozási szabály.</span><span class="sxs-lookup"><span data-stu-id="9a62a-142">No date range has been specified to define the period d when the funding rule is valid.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9a62a-143"><strong>Eset</strong></span><span class="sxs-lookup"><span data-stu-id="9a62a-143"><strong>Scenario</strong></span></span></td>
<td><span data-ttu-id="9a62a-144"><strong>Finanszírozási forrás</strong></span><span class="sxs-lookup"><span data-stu-id="9a62a-144"><strong>Funding source</strong></span></span></td>
<td><span data-ttu-id="9a62a-145"><strong>Felosztási százalék</strong></span><span class="sxs-lookup"><span data-stu-id="9a62a-145"><strong>Allocation percentage</strong></span></span></td>
<td><span data-ttu-id="9a62a-146"><strong>Finanszírozás-felosztási prioritás</strong></span><span class="sxs-lookup"><span data-stu-id="9a62a-146"><strong>Allocation priority</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9a62a-147">Célszerű a költségeket egy finanszírozási forráshoz kiosztani amíg az alapjai kimerülnek, majd egy második finanszírozási forráshoz kiosztani a költségeket amíg annak alapjai kimerülnek, végül a fennmaradó költségeket egy harmadik finanszírozási forráshoz kiosztani.</span><span class="sxs-lookup"><span data-stu-id="9a62a-147">You want to allocate costs to one funding source until its funds are exhausted, allocate costs to a second funding source until its funds are exhausted, and finally allocate the remaining costs to a third funding source.</span></span></td>
<td><ul>
<li><span data-ttu-id="9a62a-148">Finanszírozási　forrás　1</span><span class="sxs-lookup"><span data-stu-id="9a62a-148">Funding　source　1</span></span></li>
<li><span data-ttu-id="9a62a-149">Finanszírozási　forrás　2</span><span class="sxs-lookup"><span data-stu-id="9a62a-149">Funding　source　2</span></span></li>
<li><span data-ttu-id="9a62a-150">Finanszírozási　forrás　3</span><span class="sxs-lookup"><span data-stu-id="9a62a-150">Funding　source　3</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="9a62a-151">100%</span><span class="sxs-lookup"><span data-stu-id="9a62a-151">100%</span></span></li>
<li><span data-ttu-id="9a62a-152">100%</span><span class="sxs-lookup"><span data-stu-id="9a62a-152">100%</span></span></li>
<li><span data-ttu-id="9a62a-153">100%</span><span class="sxs-lookup"><span data-stu-id="9a62a-153">100%</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="9a62a-154">1</span><span class="sxs-lookup"><span data-stu-id="9a62a-154">1</span></span></li>
<li><span data-ttu-id="9a62a-155">2</span><span class="sxs-lookup"><span data-stu-id="9a62a-155">2</span></span></li>
<li><span data-ttu-id="9a62a-156">3</span><span class="sxs-lookup"><span data-stu-id="9a62a-156">3</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9a62a-157">Célszerű egy finanszírozási forráshoz kiosztani a költségek 75 százalékát és 25 százalékot egy második finanszírozási forráshoz.</span><span class="sxs-lookup"><span data-stu-id="9a62a-157">You want to allocate 75 percent of costs to one funding source and 25 percent to a second funding source.</span></span> <span data-ttu-id="9a62a-158">Amikor ezen finanszírozási források közül bármelyik ki van merítve, célszerű a fennmaradó költségösszeget egy harmadik finanszírozási forrásból fizetni.</span><span class="sxs-lookup"><span data-stu-id="9a62a-158">When either of those funding sources is exhausted, you want to pay the remaining costs from a third funding source.</span></span></td>
<td><ul>
<li><span data-ttu-id="9a62a-159">Finanszírozási　forrás　1</span><span class="sxs-lookup"><span data-stu-id="9a62a-159">Funding　source　1</span></span></li>
<li><span data-ttu-id="9a62a-160">Finanszírozási　forrás　2</span><span class="sxs-lookup"><span data-stu-id="9a62a-160">Funding　source　2</span></span></li>
<li><span data-ttu-id="9a62a-161">Finanszírozási　forrás　3</span><span class="sxs-lookup"><span data-stu-id="9a62a-161">Funding　source　3</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="9a62a-162">75%</span><span class="sxs-lookup"><span data-stu-id="9a62a-162">75%</span></span></li>
<li><span data-ttu-id="9a62a-163">25%</span><span class="sxs-lookup"><span data-stu-id="9a62a-163">25%</span></span></li>
<li><span data-ttu-id="9a62a-164">100%</span><span class="sxs-lookup"><span data-stu-id="9a62a-164">100%</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="9a62a-165">1</span><span class="sxs-lookup"><span data-stu-id="9a62a-165">1</span></span></li>
<li><span data-ttu-id="9a62a-166">1</span><span class="sxs-lookup"><span data-stu-id="9a62a-166">1</span></span></li>
<li><span data-ttu-id="9a62a-167">2</span><span class="sxs-lookup"><span data-stu-id="9a62a-167">2</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9a62a-168">Célszerű egy finanszírozási forráshoz kiosztani a költségek 75 százalékát és 25 százalékot egy második finanszírozási forráshoz.</span><span class="sxs-lookup"><span data-stu-id="9a62a-168">You want to allocate 75 percent of costs to one funding source and 25 percent to a second funding source.</span></span> <span data-ttu-id="9a62a-169">Amikor ezen finanszírozási források közül bármelyik ki van merítve, célszerű a fennmaradó költségösszeget egy harmadik finanszírozási forrás és egy negyedik finanszírozási forrás között felosztani.</span><span class="sxs-lookup"><span data-stu-id="9a62a-169">When either of those funding sources is exhausted, you want to split the remaining costs between a third funding source and a fourth funding source.</span></span></td>
<td><ul>
<li><span data-ttu-id="9a62a-170">Finanszírozási　forrás　1</span><span class="sxs-lookup"><span data-stu-id="9a62a-170">Funding　source　1</span></span></li>
<li><span data-ttu-id="9a62a-171">Finanszírozási　forrás　2</span><span class="sxs-lookup"><span data-stu-id="9a62a-171">Funding　source　2</span></span></li>
<li><span data-ttu-id="9a62a-172">Finanszírozási　forrás　3</span><span class="sxs-lookup"><span data-stu-id="9a62a-172">Funding　source　3</span></span></li>
<li><span data-ttu-id="9a62a-173">Finanszírozási　forrás　4</span><span class="sxs-lookup"><span data-stu-id="9a62a-173">Funding　source　4</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="9a62a-174">75%</span><span class="sxs-lookup"><span data-stu-id="9a62a-174">75%</span></span></li>
<li><span data-ttu-id="9a62a-175">25%</span><span class="sxs-lookup"><span data-stu-id="9a62a-175">25%</span></span></li>
<li><span data-ttu-id="9a62a-176">50%</span><span class="sxs-lookup"><span data-stu-id="9a62a-176">50%</span></span></li>
<li><span data-ttu-id="9a62a-177">50%</span><span class="sxs-lookup"><span data-stu-id="9a62a-177">50%</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="9a62a-178">1</span><span class="sxs-lookup"><span data-stu-id="9a62a-178">1</span></span></li>
<li><span data-ttu-id="9a62a-179">1</span><span class="sxs-lookup"><span data-stu-id="9a62a-179">1</span></span></li>
<li><span data-ttu-id="9a62a-180">2</span><span class="sxs-lookup"><span data-stu-id="9a62a-180">2</span></span></li>
<li><span data-ttu-id="9a62a-181">2</span><span class="sxs-lookup"><span data-stu-id="9a62a-181">2</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9a62a-182">Célszerű egy finanszírozási forráshoz kiosztani a költségek első 25 százalékát és a maradékot egy második finanszírozási forráshoz.</span><span class="sxs-lookup"><span data-stu-id="9a62a-182">You want to allocate the first 25 percent of costs to one funding source and the rest to a second funding source.</span></span></td>
<td><ul>
<li><span data-ttu-id="9a62a-183">Finanszírozási　forrás　1</span><span class="sxs-lookup"><span data-stu-id="9a62a-183">Funding　source　1</span></span></li>
<li><span data-ttu-id="9a62a-184">Finanszírozási　forrás　2</span><span class="sxs-lookup"><span data-stu-id="9a62a-184">Funding　source　2</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="9a62a-185">25%</span><span class="sxs-lookup"><span data-stu-id="9a62a-185">25%</span></span></li>
<li><span data-ttu-id="9a62a-186">100%</span><span class="sxs-lookup"><span data-stu-id="9a62a-186">100%</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="9a62a-187">1</span><span class="sxs-lookup"><span data-stu-id="9a62a-187">1</span></span></li>
<li><span data-ttu-id="9a62a-188">2</span><span class="sxs-lookup"><span data-stu-id="9a62a-188">2</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="example-multiple-funding-sources-complex"></a><span data-ttu-id="9a62a-189">Példa: Több finanszírozási forrás (összetett)</span><span class="sxs-lookup"><span data-stu-id="9a62a-189">Example: Multiple funding sources (complex)</span></span>

<span data-ttu-id="9a62a-190">Három finanszírozási forrása van, amelyeket a következő sorrendben kíván használni:</span><span class="sxs-lookup"><span data-stu-id="9a62a-190">You have three funding sources that you want to use in the following order:</span></span>

1.  <span data-ttu-id="9a62a-191">Használja a 2-es számú finanszírozási forrást és a 3-as számú finanszírozási forrást egyenlően amíg a 2-es számú finanszírozási forrás kimerül.</span><span class="sxs-lookup"><span data-stu-id="9a62a-191">Use funding source 2 and funding source 3 equally until funding source 2 is exhausted.</span></span>
2.  <span data-ttu-id="9a62a-192">Használja tovább a 3-as számú finanszírozási forrást amíg az kimerül.</span><span class="sxs-lookup"><span data-stu-id="9a62a-192">Continue to use funding source 3 until it is exhausted.</span></span>
3.  <span data-ttu-id="9a62a-193">Használja az 1-es számú finanszírozási forrást miután a 3-as számú finanszírozási forrás kimerül.</span><span class="sxs-lookup"><span data-stu-id="9a62a-193">Use funding source 1 after funding source 3 is exhausted.</span></span>

<span data-ttu-id="9a62a-194">Ezen cél eléréséhez a következőket kell tennie:</span><span class="sxs-lookup"><span data-stu-id="9a62a-194">To accomplish this goal, you must do the following:</span></span>

-   <span data-ttu-id="9a62a-195">Állítson be finanszírozási korlátokat a 2-es számú finanszírozási forrásra és a 3-as számú finanszírozási forrásra a megfelelő összegekkel.</span><span class="sxs-lookup"><span data-stu-id="9a62a-195">Set up funding limits for funding source 2 and funding source 3, for their respective amounts.</span></span>
-   <span data-ttu-id="9a62a-196">Hozza létre a következő finanszírozási szabályokat:</span><span class="sxs-lookup"><span data-stu-id="9a62a-196">Create the following funding rules:</span></span>
    -   <span data-ttu-id="9a62a-197">Szabály 1 (1-es prioritás): Ossza ki a tranzakciók 50 százalékát a 2-es finanszírozási forráshoz és 50 százalékát a 3-as finanszírozási forráshoz.</span><span class="sxs-lookup"><span data-stu-id="9a62a-197">Rule 1 (Priority 1): Allocate 50 percent of transactions to funding source 2 and 50 percent to funding source 3.</span></span>
    -   <span data-ttu-id="9a62a-198">Szabály 2 (2-es prioritás): Ossza ki a tranzakciók 100 százalékát a 3-as finanszírozási forráshoz.</span><span class="sxs-lookup"><span data-stu-id="9a62a-198">Rule 2 (Priority 2): Allocate 100 percent of transactions to funding source 3.</span></span>
    -   <span data-ttu-id="9a62a-199">Szabály 3 (3-es prioritás): Ossza ki a tranzakciók 100 százalékát az 1-es finanszírozási forráshoz.</span><span class="sxs-lookup"><span data-stu-id="9a62a-199">Rule 3 (Priority 3): Allocate 100 percent of transactions to funding source 1.</span></span>

<span data-ttu-id="9a62a-200">Ez a beállítás azért működik, mert a tranzakciók összevetésre kerülnek a szabályokkal és korlátozásokkal, hogy meghatározzák, hogy bármelyikük vonatkozik-e a tranzakcióra.</span><span class="sxs-lookup"><span data-stu-id="9a62a-200">This setup works because transactions are checked against rules and limits to determine whether any of them apply to the transaction.</span></span> <span data-ttu-id="9a62a-201">Ha semmilyen korlát vagy szabály sem vonatkozik kifejezetten a tranzakcióra, az Összes tranzakció szabály lép érvénybe.</span><span class="sxs-lookup"><span data-stu-id="9a62a-201">If no specific rules or limits apply to the transaction, the All transactions rule applies.</span></span> <span data-ttu-id="9a62a-202">Az Összes tranzakció szabály megfeleltet minden tranzakciót.</span><span class="sxs-lookup"><span data-stu-id="9a62a-202">The All transactions rule matches all transactions.</span></span> 

<span data-ttu-id="9a62a-203">Ha található olyan szabály, amely megfeleltethető a tranzakcióval, a szabályban kiosztott százalék kerül alkalmazásra, de csak azután, hogy a megfeleltetések összevetésre kerülnek bármilyen beállított korlátokkal.</span><span class="sxs-lookup"><span data-stu-id="9a62a-203">If a rule is found that matches a transaction, the percentage that has been allocated in that rule is applied first, but only after the matches are checked against any limits that have been set up.</span></span> <span data-ttu-id="9a62a-204">Ha korlátba ütközés történik, és egy finanszírozási forrás alapjai kimerültek, a finanszírozási korláthoz társított finanszírozási szabály figyelmen kívül hagyható, és a program a következő érvényes szabályt keresi meg.</span><span class="sxs-lookup"><span data-stu-id="9a62a-204">If a limit has been met, and a funding source’s funds are exhausted, the funding rule that is associated with the funding limit is disregarded, and the program checks for the next rule that applies.</span></span> 

<span data-ttu-id="9a62a-205">Bizonyos esetekben csak a tranzakció egy részét lehet egy szabály alapján felosztani.</span><span class="sxs-lookup"><span data-stu-id="9a62a-205">In some cases, only part of a transaction can be allocated under a rule.</span></span> <span data-ttu-id="9a62a-206">Ez előfordulhat azért, mert korlátba ütközés történik, amikor a tranzakció felosztásra kerül.</span><span class="sxs-lookup"><span data-stu-id="9a62a-206">This might happen because a limit is reached when the transaction is allocated.</span></span> <span data-ttu-id="9a62a-207">Ebben az esetben csak egy bizonyos pénzösszeg kerül felosztásra az adott szabály szerint, például 50 százalék minden finanszírozási forráshoz.</span><span class="sxs-lookup"><span data-stu-id="9a62a-207">In this case, only a certain amount is allocated according to that rule, such as 50 percent to each funding source.</span></span> <span data-ttu-id="9a62a-208">Ez a helyzet az ebben a szakaszban korábban ismertetett 1-es szabályban.</span><span class="sxs-lookup"><span data-stu-id="9a62a-208">This is the case in rule 1, which is described earlier in this section.</span></span> <span data-ttu-id="9a62a-209">A maradék a sorban következő szabály szerint kerül felosztásra.</span><span class="sxs-lookup"><span data-stu-id="9a62a-209">The remainder is allocated according to the next rule in the sequence.</span></span> 

<span data-ttu-id="9a62a-210">Az alábbi táblázat ezt az esetet részletesebben megvizsgálja.</span><span class="sxs-lookup"><span data-stu-id="9a62a-210">The following table examines this scenario in more detail.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9a62a-211"><strong>Fókusz</strong></span><span class="sxs-lookup"><span data-stu-id="9a62a-211"><strong>Focus</strong></span></span></td>
<td><span data-ttu-id="9a62a-212"><strong>Részletek</strong></span><span class="sxs-lookup"><span data-stu-id="9a62a-212"><strong>Details</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9a62a-213">Finanszírozási szabályok</span><span class="sxs-lookup"><span data-stu-id="9a62a-213">Funding rules</span></span></td>
<td><ul>
<li><span data-ttu-id="9a62a-214">Szabály 1 (1-es prioritás): Összes tranzakció.</span><span class="sxs-lookup"><span data-stu-id="9a62a-214">Rule 1 (Priority 1): All transactions.</span></span> <span data-ttu-id="9a62a-215">Rendelje hozzá a 2 számú finanszírozási forrást 50 %-kal, és a 3 számú finanszírozási forrást 50 %-kal.</span><span class="sxs-lookup"><span data-stu-id="9a62a-215">Allocate funding source 2 at 50% and funding source 3 at 50%.</span></span></li>
<li><span data-ttu-id="9a62a-216">Szabály 2 (2-es prioritás): Összes tranzakció.</span><span class="sxs-lookup"><span data-stu-id="9a62a-216">Rule 2 (Priority 2): All transactions.</span></span> <span data-ttu-id="9a62a-217">Rendelje hozzá a 3 számú finanszírozási forrást 100%-kal.</span><span class="sxs-lookup"><span data-stu-id="9a62a-217">Allocate funding source 3 at 100%.</span></span></li>
<li><span data-ttu-id="9a62a-218">Szabály 3 (2-es prioritás): Összes tranzakció.</span><span class="sxs-lookup"><span data-stu-id="9a62a-218">Rule 3 (Priority 2): All transactions.</span></span> <span data-ttu-id="9a62a-219">Rendelje hozzá a 1 számú finanszírozási forrást 100%-kal.</span><span class="sxs-lookup"><span data-stu-id="9a62a-219">Allocate funding source 1 at 100%.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9a62a-220">Finanszírozási korlátozások</span><span class="sxs-lookup"><span data-stu-id="9a62a-220">Funding limits</span></span></td>
<td><ul>
<li><span data-ttu-id="9a62a-221">Finanszírozási forrás 1 korlát = 10000.00</span><span class="sxs-lookup"><span data-stu-id="9a62a-221">Funding source 1 limit = 10,000.00</span></span></li>
<li><span data-ttu-id="9a62a-222">Finanszírozási forrás 2 korlát = 500.00</span><span class="sxs-lookup"><span data-stu-id="9a62a-222">Funding source 2 limit = 500.00</span></span></li>
<li><span data-ttu-id="9a62a-223">Finanszírozási forrás 3 korlát = 750.00</span><span class="sxs-lookup"><span data-stu-id="9a62a-223">Funding source 3 limit = 750.00</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9a62a-224">Tranzakció 1</span><span class="sxs-lookup"><span data-stu-id="9a62a-224">Transaction 1</span></span></td>
<td><span data-ttu-id="9a62a-225"><strong>A tranzakció összege:</strong> 100,00<strong>Finanszírozás:</strong> A tranzakció fizetése csak az 1-es szabálynak megfelelően történik, mert a tranzakció csak az 1-es szabály alkalmazása után kerül teljes kifizetésre.</span><span class="sxs-lookup"><span data-stu-id="9a62a-225"><strong>Transaction amount:</strong> 100.00<strong>Funding:</strong> The transaction is paid according to rule 1 only, because the transaction is fully paid after rule 1 is applied.</span></span> <span data-ttu-id="9a62a-226">A tranzakció egyenlően kerül finanszírozásra a 2-es finanszírozási forrás és a 3-as finanszírozási forrás között.</span><span class="sxs-lookup"><span data-stu-id="9a62a-226">The transaction is funded equally between funding source 2 and funding source 3.</span></span>
<ul>
<li><span data-ttu-id="9a62a-227">2-es finanszírozási forrás: 50.00</span><span class="sxs-lookup"><span data-stu-id="9a62a-227">Funding source 2: 50.00</span></span></li>
<li><span data-ttu-id="9a62a-228">3-as finanszírozási forrás: 50.00</span><span class="sxs-lookup"><span data-stu-id="9a62a-228">Funding source 3: 50.00</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9a62a-229">Tranzakció 2</span><span class="sxs-lookup"><span data-stu-id="9a62a-229">Transaction 2</span></span></td>
<td><span data-ttu-id="9a62a-230"><strong>A tranzakció összege:</strong> 5000,00<strong>Finanszírozás:</strong> A tranzakció kifizetése mindhárom szabály alapján történik.<strong>1-es szabály</strong>
</span><span class="sxs-lookup"><span data-stu-id="9a62a-230"><strong>Transaction amount:</strong> 5,000.00<strong>Funding:</strong> The transaction is paid according to all three rules.<strong>Rule 1</strong>
</span></span><ul>
<li><span data-ttu-id="9a62a-231">2-es finanszírozási forrás: 450.00</span><span class="sxs-lookup"><span data-stu-id="9a62a-231">Funding source 2: 450.00</span></span></li>
<li><span data-ttu-id="9a62a-232">3-as finanszírozási forrás: 450.00</span><span class="sxs-lookup"><span data-stu-id="9a62a-232">Funding source 3: 450.00</span></span></li>
</ul><span data-ttu-id="9a62a-233">
<strong>2-es szabály</strong>
</span><span class="sxs-lookup"><span data-stu-id="9a62a-233">
<strong>Rule 2</strong>
</span></span><ul>
<li><span data-ttu-id="9a62a-234">3-as finanszírozási forrás: 250.00 (= 750.00 – 50.00 – 450.00)</span><span class="sxs-lookup"><span data-stu-id="9a62a-234">Funding source 3: 250.00 (= 750.00 – 50.00 – 450.00)</span></span></li>
</ul><span data-ttu-id="9a62a-235">
<strong>3-as szabály</strong>
</span><span class="sxs-lookup"><span data-stu-id="9a62a-235">
<strong>Rule 3</strong>
</span></span><ul>
<li><span data-ttu-id="9a62a-236">1-es finanszírozási forrás: 3,850.00 (= 5,000.00 – 450.00 – 450.00 – 250.00)</span><span class="sxs-lookup"><span data-stu-id="9a62a-236">Funding source 1: 3,850.00 (= 5,000.00 – 450.00 – 450.00 – 250.00)</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9a62a-237">Az egyes finanszírozási források részére kiosztott összes alap</span><span class="sxs-lookup"><span data-stu-id="9a62a-237">Total funds that are distributed for each funding source</span></span></td>
<td><ul>
<li><span data-ttu-id="9a62a-238">1-as finanszírozási forrás: 3,850.00</span><span class="sxs-lookup"><span data-stu-id="9a62a-238">Funding source 1: 3,850.00</span></span></li>
<li><span data-ttu-id="9a62a-239">2-as finanszírozási forrás: 500.00</span><span class="sxs-lookup"><span data-stu-id="9a62a-239">Funding source 2: 500.00</span></span></li>
<li><span data-ttu-id="9a62a-240">3-as finanszírozási forrás: 750.00</span><span class="sxs-lookup"><span data-stu-id="9a62a-240">Funding source 3: 750.00</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="billing-rules"></a><span data-ttu-id="9a62a-241">Számlázási szabályok</span><span class="sxs-lookup"><span data-stu-id="9a62a-241">Billing rules</span></span>
<span data-ttu-id="9a62a-242">Olyan projektszerződést választott tárgyaljanak egy vevő, ha definiálni, mikor és hogyan lehet számlát a vevő, a munka a projekt.</span><span class="sxs-lookup"><span data-stu-id="9a62a-242">When you negotiate a project contract with a customer, you define how and when you can invoice the customer for work on a project.</span></span> <span data-ttu-id="9a62a-243">Miután beállította a projektszerződést és a projektet, beállíthat számlázási szabályokat a projekthez.</span><span class="sxs-lookup"><span data-stu-id="9a62a-243">After you set up the project contract and the project, you can set up billing rules for the project.</span></span> <span data-ttu-id="9a62a-244">Számlázási szabályok vannak megadva a projektszerződés projekt feltételei alapján.</span><span class="sxs-lookup"><span data-stu-id="9a62a-244">Billing rules are based on the project terms that are specified in the project contract.</span></span> <span data-ttu-id="9a62a-245">A létrehozható számlázási szabály a projektszerződés feltételeitől és annak a projektnek a típusától – például vagy Mérföldkő – függ, amelyhez hozzárendeli a számlázási szabályt.</span><span class="sxs-lookup"><span data-stu-id="9a62a-245">The billing rules that you can create depend on the terms of the project contract and the project type, such as Time and material or Fixed-price, that you associate with the billing rule.</span></span> <span data-ttu-id="9a62a-246">Egy projektszerződéshez több számlázási szabályt is létrehozhat.</span><span class="sxs-lookup"><span data-stu-id="9a62a-246">You can create more than one billing rule for a project contract.</span></span> <span data-ttu-id="9a62a-247">A számlázási szabály hozzárendelése az azonos projektszerződéshez társított több projekt is, és hasonló számlázási feltételeket kell.</span><span class="sxs-lookup"><span data-stu-id="9a62a-247">You can also assign a billing rule to multiple projects that are associated with the same project contract and have similar billing terms.</span></span> 

<span data-ttu-id="9a62a-248">A következő típusú ármegállapodások hozhatók létre:</span><span class="sxs-lookup"><span data-stu-id="9a62a-248">You can set up the following types of billing rules:</span></span>

-   <span data-ttu-id="9a62a-249">**Szállítási egység** – Vevői számla kiállítása a szállítási egység befejezésekor.</span><span class="sxs-lookup"><span data-stu-id="9a62a-249">**Unit of delivery** – Invoice a customer when you complete a unit of delivery.</span></span> <span data-ttu-id="9a62a-250">A szerződés szállítási egységei határozhatja meg.</span><span class="sxs-lookup"><span data-stu-id="9a62a-250">You define the units of delivery in the contract.</span></span>
-   <span data-ttu-id="9a62a-251">**Haladás** – Vevői számla kiállítása a projekt adott százalékának befejezésekor.</span><span class="sxs-lookup"><span data-stu-id="9a62a-251">**Progress** – Invoice a customer when you complete a specified percentage of the project.</span></span> <span data-ttu-id="9a62a-252">Állíthat be a számlázási szabály szeretné automatikusan kiszámítani az elvégzett munka százalékos, vagy manuálisan ki lehet számítani az elvégzett munka és az összeg a vevőnek való számlázáshoz százaléka.</span><span class="sxs-lookup"><span data-stu-id="9a62a-252">You can set up a billing rule to automatically calculate the percentage of work completed, or you can manually calculate the percentage of work completed and the amount to invoice the customer.</span></span>
-   <span data-ttu-id="9a62a-253">**Mérföldkő** – Vevői számla kiállítása a projekt mérföldkő teljes összegéről egy mérföldkő elérésekor.</span><span class="sxs-lookup"><span data-stu-id="9a62a-253">**Milestone** – Invoice a customer for the full amount of a project milestone when the milestone is reached.</span></span>
-   <span data-ttu-id="9a62a-254">**Díj**– Vevői számla kiállítása a szolgáltatásokra, valamint kezelési díj, amely jellemzően a szolgáltatások költségének bizonyos százaléka.</span><span class="sxs-lookup"><span data-stu-id="9a62a-254">**Fee** – Invoice a customer for your services plus a management fee, which is typically a percentage of the cost of services.</span></span>
-   <span data-ttu-id="9a62a-255">**Idő és anyag** – Vevői számla kiállítása a projekteken használt idő és anyagok értékére.</span><span class="sxs-lookup"><span data-stu-id="9a62a-255">**Time and material** – Invoice a customer for the value of time and materials that are used on a project.</span></span>

<span data-ttu-id="9a62a-256">Bármilyen típusú számlázási szabályokra megadhat egy visszatartási százalékot, amely a vevői számlákból kerül levonásra, amíg a projekt el nem éri az egyezményes fokozatot.</span><span class="sxs-lookup"><span data-stu-id="9a62a-256">For all types of billing rules, you can specify a retention percentage that is deducted from customer invoices until a project reaches an agreed-upon stage.</span></span> <span data-ttu-id="9a62a-257">A kifizetési visszatartás százaléka megadva a projektszerződés.</span><span class="sxs-lookup"><span data-stu-id="9a62a-257">The payment retention percentage is specified in the project contract.</span></span> <span data-ttu-id="9a62a-258">Az összeg kiszámítása a vevői számla sorainak teljes értékén alapul, és abból kerül levonásra.</span><span class="sxs-lookup"><span data-stu-id="9a62a-258">The amount is calculated based on, and subtracted from, the total value of the lines in a customer invoice.</span></span> 

<span data-ttu-id="9a62a-259">Az **Idő és anyag** és **Haladás** számlázási szabályokkal hozzárendelhet számlázható kategóriákat.</span><span class="sxs-lookup"><span data-stu-id="9a62a-259">For **Time and material** and **Progress** billing rules, you can assign chargeable categories.</span></span> <span data-ttu-id="9a62a-260">A számlázható kategóriák a vevői számlákba belefoglalandó tranzakciók.</span><span class="sxs-lookup"><span data-stu-id="9a62a-260">Chargeable categories indicate the transactions that should be included in customer invoices.</span></span> 

<span data-ttu-id="9a62a-261">Ha készen áll a vevői számlát, az összeg a projekt számlázásához kiszámítja a számlázási szabályokkal, és a projektszámla-javaslat jön létre.</span><span class="sxs-lookup"><span data-stu-id="9a62a-261">When you are ready to invoice the customer, the amount to invoice for the project is calculated based on the billing rules, and a project invoice proposal is generated.</span></span> 

<span data-ttu-id="9a62a-262">A következő részek példákat mutatnak arra, hogyan lehet beállítani és kezelni számlázási szabályokat egy projektre.</span><span class="sxs-lookup"><span data-stu-id="9a62a-262">The following sections provide examples that show how to set up and manage billing rules for a project.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-the-number-of-units-delivered"></a><span data-ttu-id="9a62a-263">Példa: Számlázási szabály létrehozása a szállított cikkek száma alapján</span><span class="sxs-lookup"><span data-stu-id="9a62a-263">Example: Create a billing rule that is based on the number of units delivered</span></span>

<span data-ttu-id="9a62a-264">A szervezete egy megállapodást köt összesen öt képzési foglalkozás biztosítására egy vevő alkalmazottainak, képzési foglalkozásonként 10 000 költséggel.</span><span class="sxs-lookup"><span data-stu-id="9a62a-264">Your organization enters into an agreement to provide a total of five training sessions to a customer’s employees at a cost of 10,000 per training session.</span></span> <span data-ttu-id="9a62a-265">Minden képzési foglalkozás után számláz a vevőnek.</span><span class="sxs-lookup"><span data-stu-id="9a62a-265">You invoice the customer after each training session.</span></span> 

<span data-ttu-id="9a62a-266">Amikor beállítja a számlázási szabályokat a szerződésre, a következő értékeket használja:</span><span class="sxs-lookup"><span data-stu-id="9a62a-266">When you set up the billing rules for the contract, you use the following values:</span></span>

-   <span data-ttu-id="9a62a-267">A szállítási mértékegysége egy képzési munkamenet.</span><span class="sxs-lookup"><span data-stu-id="9a62a-267">The unit of delivery is one training session.</span></span>
-   <span data-ttu-id="9a62a-268">Az Egységár képzési munkamenet egy 10 000.</span><span class="sxs-lookup"><span data-stu-id="9a62a-268">The unit price is 10,000 per training session.</span></span>
-   <span data-ttu-id="9a62a-269">Egységek száma összesen öt képzéseken.</span><span class="sxs-lookup"><span data-stu-id="9a62a-269">The total number of units is five training sessions.</span></span>

<span data-ttu-id="9a62a-270">Egy képzési foglalkozás befejezése után létrehozhat számlát 10000 összeggel az első szállított egységre, és elküldheti a számlát a vevőnek.</span><span class="sxs-lookup"><span data-stu-id="9a62a-270">When you have completed one training session, you can create an invoice for 10,000, for the first unit that was delivered, and send the invoice to the customer.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-a-specified-percentage-of-project-completion-manual-calculation"></a><span data-ttu-id="9a62a-271">Példa: Számlázási szabály létrehozása a projekt feldolgozottságának megadott százaléka alapján (manuális számítás)</span><span class="sxs-lookup"><span data-stu-id="9a62a-271">Example: Create a billing rule that is based on a specified percentage of project completion (manual calculation)</span></span>

<span data-ttu-id="9a62a-272">A termék, amelyet a vevő fejleszt részének hozzanak a vevővel kötött megállapodás belép a szervezethez, a szoftver tanácsadó cég.</span><span class="sxs-lookup"><span data-stu-id="9a62a-272">Your organization, a software consulting firm, enters into an agreement with a customer to develop part of a product that the customer is developing.</span></span> <span data-ttu-id="9a62a-273">Szervezete vállalja, hogy hat hónapos időszak alatt leszállítja a programkódot a termékhez.</span><span class="sxs-lookup"><span data-stu-id="9a62a-273">Your organization agrees to deliver the software code over a period of six months.</span></span> <span data-ttu-id="9a62a-274">A vevő pedig elfogadja, a munka a szervezet összesen 100 000 kifizetésére.</span><span class="sxs-lookup"><span data-stu-id="9a62a-274">The customer agrees to pay your organization a total of 100,000 for the work.</span></span> <span data-ttu-id="9a62a-275">Létrehoz egy számlázási szabályt a vevő számlázásra, mely a szerződésben meghatározott, a projekten elvégzett munka százalékos értéken alapul.</span><span class="sxs-lookup"><span data-stu-id="9a62a-275">You create a billing rule to invoice the customer based on the percentage of work that is completed on the project, as specified in the contract.</span></span>

-   <span data-ttu-id="9a62a-276">Az első hónap végén meg fognak felelni az elvégzett munka százalékos meghatározásához a vevővel.</span><span class="sxs-lookup"><span data-stu-id="9a62a-276">At the end of the first month, you meet with the customer to determine the percentage of work completed.</span></span> <span data-ttu-id="9a62a-277">Miután Ön és a vevő áttekinti a projektet, Ön úgy dönt, hogy a projekt 15 százalékban befejezett.</span><span class="sxs-lookup"><span data-stu-id="9a62a-277">After you and the customer review the project, you decide that the project is 15 percent completed.</span></span>
-   <span data-ttu-id="9a62a-278">Létrehoz egy számlát 15 000 összeggel (100 000-nek a 15 százaléka), és elküldi a vevőnek.</span><span class="sxs-lookup"><span data-stu-id="9a62a-278">You create an invoice for 15,000 (15 percent of 100,000) and send it to the customer.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-a-specified-percentage-of-project-completion-automatic-calculation"></a><span data-ttu-id="9a62a-279">Példa: Számlázási szabály létrehozása a projekt feldolgozottságának megadott százaléka alapján (automatikus számítás)</span><span class="sxs-lookup"><span data-stu-id="9a62a-279">Example: Create a billing rule that is based on a specified percentage of project completion (automatic calculation)</span></span>

<span data-ttu-id="9a62a-280">Az Ön szervezete, egy szoftver fejlesztési vállalkozás megegyezik, hogy egy bérlista könyvelési csomagot fejleszt a vevőnek 30 000-ért.</span><span class="sxs-lookup"><span data-stu-id="9a62a-280">Your organization, a software development firm, agrees to develop a payroll accounting package for a customer for 30,000.</span></span> <span data-ttu-id="9a62a-281">A vevő pedig elfogadja, a munkáért a szervezetnek a teljesített munka százaléka alapján fizet.</span><span class="sxs-lookup"><span data-stu-id="9a62a-281">The customer agrees to pay your organization based on the percentage of work completed.</span></span> <span data-ttu-id="9a62a-282">Úgy becsli, hogy a projektköltségek 20 000-et tesznek majd ki.</span><span class="sxs-lookup"><span data-stu-id="9a62a-282">You estimate that the project costs are 20,000.</span></span> <span data-ttu-id="9a62a-283">A projektszerződés megadja azon munka kategóriákat, amelyeket a számlázási folyamatban használ.</span><span class="sxs-lookup"><span data-stu-id="9a62a-283">The project contract specifies the categories of work that you use in the billing process.</span></span> <span data-ttu-id="9a62a-284">Be lehet állítani olyan számlázási szabályokat, amelyek alapján az egyes kategóriákban elvégzett munka százaléka után járó számlaösszegek kiszámítása automatikusan történik.</span><span class="sxs-lookup"><span data-stu-id="9a62a-284">You set up billing rules that automatically calculate the invoice amounts for the percentage of work that is completed for each category.</span></span> <span data-ttu-id="9a62a-285">Az egyes levelezési kategóriák alkategóriáinak beállítása:</span><span class="sxs-lookup"><span data-stu-id="9a62a-285">You set up a budget for each category:</span></span>

-   <span data-ttu-id="9a62a-286">**Fejlesztés** – 15 000 költség és 20 000 bevétel.</span><span class="sxs-lookup"><span data-stu-id="9a62a-286">**Development** – Cost of 15,000 and revenue of 20,000</span></span>
-   <span data-ttu-id="9a62a-287">**Telepítés** – 5 000 költség és 10 000 bevétel</span><span class="sxs-lookup"><span data-stu-id="9a62a-287">**Installation** – Cost of 5,000 and revenue of 10,000</span></span>

<span data-ttu-id="9a62a-288">Vevői számla létrehozásakor először a számlaösszeg automatikusan kiszámítja a következő adatokat:</span><span class="sxs-lookup"><span data-stu-id="9a62a-288">When you create a customer invoice for the first time, the invoice amount is automatically calculated based on the following information:</span></span>

-   <span data-ttu-id="9a62a-289">A dolgozó a projekt havonta után elküldi a projekt munkaidő-kimutatás.</span><span class="sxs-lookup"><span data-stu-id="9a62a-289">After a month, the worker on the project submits a timesheet for the project.</span></span> <span data-ttu-id="9a62a-290">A dolgozó munkaóráinak költsége pedig 5000 fejlesztési 1000 telepítésre.</span><span class="sxs-lookup"><span data-stu-id="9a62a-290">The cost of the worker’s hours is 5,000 for development and 1,000 for installation.</span></span> <span data-ttu-id="9a62a-291">A fejlesztési munka 33 százalékosan befejezett (5000 tényleges költség/15 000 tervezett költség), és a telepítési munka 20 százalékosan teljes befejezett (1000 tényleges költség/5000 tervezett költség).</span><span class="sxs-lookup"><span data-stu-id="9a62a-291">The development work is 33 percent completed (5,000 actual cost/15,000 budget cost), and the installation work is 20 percent completed (1,000 actual cost/5,000 budget cost).</span></span>
-   <span data-ttu-id="9a62a-292">A számla összege 8 667, melyet a program automatikusan számít ki (20 000-nek a 33 százaléka + 10 000-nek a 20 százaléka).</span><span class="sxs-lookup"><span data-stu-id="9a62a-292">The invoice amount of 8,667 is automatically calculated (33 percent of 20,000 + 20 percent of 10,000).</span></span>
-   <span data-ttu-id="9a62a-293">Létrehoz egy számlát 8 667 összeggel, és elküldi a vevőnek.</span><span class="sxs-lookup"><span data-stu-id="9a62a-293">You create an invoice for 8,667 and send it to the customer.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-agreed-upon-milestones"></a><span data-ttu-id="9a62a-294">Példa: Számlázási szabály létrehozása egyezményes mérföldkövek alapján</span><span class="sxs-lookup"><span data-stu-id="9a62a-294">Example: Create a billing rule that is based on agreed-upon milestones</span></span>

<span data-ttu-id="9a62a-295">Az Ön szervezete, egy vezetési tanácsadó cég megegyezik, hogy piackutatást végez egy vevői termékre, amelyet a vevő értékesíteni tervez.</span><span class="sxs-lookup"><span data-stu-id="9a62a-295">Your organization, a management consulting firm, agrees to conduct market research for a consumer product that the customer plans to sell.</span></span> <span data-ttu-id="9a62a-296">Az ügyfél elfogadja az ajánlatot, és márciustól kezdődően három hónapon át igénybe veszi a szolgáltatást, amiért 50 000-et fizet a szervezetnek.</span><span class="sxs-lookup"><span data-stu-id="9a62a-296">The customer agrees to use your services for a period of three months, starting in March, and agrees to pay your organization 50,000.</span></span> <span data-ttu-id="9a62a-297">A projekt három mérföldkőből áll:</span><span class="sxs-lookup"><span data-stu-id="9a62a-297">The project has three milestones:</span></span>

-   <span data-ttu-id="9a62a-298">1. mérföldkő: Fogyasztói adatok gyűjtése - március 31.</span><span class="sxs-lookup"><span data-stu-id="9a62a-298">Milestone 1: Collect consumer data – March 31</span></span>
-   <span data-ttu-id="9a62a-299">2. mérföldkő: A fogyasztói adatok elemzése - április 30.</span><span class="sxs-lookup"><span data-stu-id="9a62a-299">Milestone 2: Analyze consumer data – April 30</span></span>
-   <span data-ttu-id="9a62a-300">3. mérföldkő: A termék piacképességi vizsgálatának bemutatása - május 31.</span><span class="sxs-lookup"><span data-stu-id="9a62a-300">Milestone 3: Present a product viability proposal – May 31</span></span>

<span data-ttu-id="9a62a-301">A vevő megegyezik, hogy 10 000-et fizet a szervezetének az első mérföldkőre, 20 000-et a másodikra és 20 000-et a harmadik mérföldkőre.</span><span class="sxs-lookup"><span data-stu-id="9a62a-301">The customer agrees to pay your organization 10,000 for the first milestone, 20,000 for the second milestone, and 20,000 for the third milestone.</span></span> 

<span data-ttu-id="9a62a-302">Amikor létrehozza a projektszerződést, megegyezik, hogy a vevőt a befejezett mérföldkő alapján számlázza.</span><span class="sxs-lookup"><span data-stu-id="9a62a-302">When you set up the project contract, you agree to bill the customer based on the milestone that has been completed.</span></span> <span data-ttu-id="9a62a-303">Az időszakok beállítása az alábbi két lépésből áll:</span><span class="sxs-lookup"><span data-stu-id="9a62a-303">The billing rule setup includes the following steps:</span></span>

-   <span data-ttu-id="9a62a-304">A projekt mérföldköveit meghatározása.</span><span class="sxs-lookup"><span data-stu-id="9a62a-304">Define the project milestones.</span></span>
-   <span data-ttu-id="9a62a-305">Adja meg az egyes mérföldkövek elérésekor a vevőnek számlázandó összegeket.</span><span class="sxs-lookup"><span data-stu-id="9a62a-305">Define the amount to invoice the customer when each milestone is completed.</span></span>

<span data-ttu-id="9a62a-306">Amikor az első mérföldkő március 31-én befejeződik, a mérföldkövet befejezettnek jelöli, majd létrehoz egy számlát 10 000 összeggel és elküldi a vevőnek.</span><span class="sxs-lookup"><span data-stu-id="9a62a-306">When the first milestone is completed on March 31, you mark the milestone as completed, and then create an invoice for 10,000 and send it to the customer.</span></span> <span data-ttu-id="9a62a-307">Mérföldkőre számla nem hozható létre mindaddig, amíg a mérföldkövet befejezettként meg nem jelöli.</span><span class="sxs-lookup"><span data-stu-id="9a62a-307">You can’t create an invoice for a milestone until you have marked the milestone as completed.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-services-plus-a-management-fee"></a><span data-ttu-id="9a62a-308">Példa: Számlázási szabály létrehozása szolgáltatások, valamint egy kezelési díj alapján</span><span class="sxs-lookup"><span data-stu-id="9a62a-308">Example: Create a billing rule that is based on services plus a management fee</span></span>

<span data-ttu-id="9a62a-309">Az Ön szervezete, egy vezetési tanácsadó cég megegyezik, hogy piackutatást végez egy vevői termék piacképességének vizsgálatára, amelyet a vevő, egy kiskereskedelmi vállalat fejleszt.</span><span class="sxs-lookup"><span data-stu-id="9a62a-309">Your organization, a management consulting firm, agrees to conduct market research to evaluate the viability of a product that the customer, a retail company, is developing.</span></span> <span data-ttu-id="9a62a-310">A szerződés feltételei rögzítik, hogy Ön a három legjobb vezetői tanácsadóinak szolgáltatásait biztosítja, akik a kutatást lebonyolítják adott idő- és anyagköltség mellett.</span><span class="sxs-lookup"><span data-stu-id="9a62a-310">The terms of the agreement specify that you will provide the services of your top three management consultants, who will conduct the research on a time-and-materials basis.</span></span> <span data-ttu-id="9a62a-311">A vevő vállalja, hogy óránként 100-at fizet, továbbá 10 százalékos kezelési költséget a tanácsadási órákért, melyek a projekthez kerülnek számlázásra..</span><span class="sxs-lookup"><span data-stu-id="9a62a-311">The customer agrees to pay 100 per hour, plus a 10 percent management fee for the consulting hours that are charged to the project.</span></span> 

<span data-ttu-id="9a62a-312">A projektszerződés létrehozásakor hozzon létre egy számlázási szabályt 10 százalék kezelési díj hozzáadásához a projekthez felszámított tanácsadási órákra.</span><span class="sxs-lookup"><span data-stu-id="9a62a-312">When you set up the project contract, create a billing rule to add a 10 percent management fee to the consulting hours that are charged to the project.</span></span> 

<span data-ttu-id="9a62a-313">A vevő számára számlát hoz létre, amikor a vevőnek számlázott kezelési díj 10 százalék és tanácsadási órák költségét.</span><span class="sxs-lookup"><span data-stu-id="9a62a-313">When you create an invoice for the customer, the customer is billed a 10 percent management fee plus the cost of the consulting hours.</span></span> <span data-ttu-id="9a62a-314">Például ha három tanácsadó összesen 200 órát dolgozott a projekten, egy számla kerül létrehozásra 22 000 összeggel, az alábbi számítás alapján:</span><span class="sxs-lookup"><span data-stu-id="9a62a-314">For example, if the three consultants worked a total of 200 hours on the project, an invoice for 22,000 is created based on the following calculation:</span></span>

-   <span data-ttu-id="9a62a-315">200 órát óránkénti 100 = 20 000</span><span class="sxs-lookup"><span data-stu-id="9a62a-315">200 hours at 100 per hour = 20,000</span></span>
-   <span data-ttu-id="9a62a-316">10 százalékos kezelési díja = 2 000</span><span class="sxs-lookup"><span data-stu-id="9a62a-316">10 percent management fee = 2,000</span></span>
-   <span data-ttu-id="9a62a-317">Teljes számlaösszeg = 22 000</span><span class="sxs-lookup"><span data-stu-id="9a62a-317">Total invoice amount = 22,000</span></span>

<span data-ttu-id="9a62a-318">Ha díjak adóköteles egy vevőnek, és a projektszerződés áfacsoport lehetőséget választja, az áfacsoport automatikusan bekerül a számlázási szabály díjak.</span><span class="sxs-lookup"><span data-stu-id="9a62a-318">If fees are taxable to a customer, and you select a sales tax group in the project contract, the sales tax group is automatically entered in a billing rule for fees.</span></span>

### <a name="example-create-a-billing-rule-for-the-value-of-time-and-materials"></a><span data-ttu-id="9a62a-319">Példa: Számlázási szabály létrehozása idő és anyagok értékére</span><span class="sxs-lookup"><span data-stu-id="9a62a-319">Example: Create a billing rule for the value of time and materials</span></span>

<span data-ttu-id="9a62a-320">Az Ön szervezete, egy szoftver tanácsadó cég megegyezik, hogy öt technikai tanácsadót biztosít egy szoftverfejlesztési projekthez egy vevő számára a következő hat hónapra.</span><span class="sxs-lookup"><span data-stu-id="9a62a-320">Your organization, a software consulting firm, agrees to provide five technical consultants to work on a software development project for a customer for the next six months.</span></span> <span data-ttu-id="9a62a-321">A vevő vállalja, hogy 150-et fizet minden konzultációs óráért, továbbá az irodai kellékek költségét.</span><span class="sxs-lookup"><span data-stu-id="9a62a-321">The customer agrees to pay 150 for each consulting hour, plus the cost of office supplies.</span></span> <span data-ttu-id="9a62a-322">A szervezet számla küldése a vevőnek minden hónap végén.</span><span class="sxs-lookup"><span data-stu-id="9a62a-322">Your organization sends an invoice to the customer at the end of each month.</span></span> 

<span data-ttu-id="9a62a-323">Amikor létrehozza a projektszerződést, megegyezik, hogy a vevőt minden egyes hónapban számlázza a projektre használt időre és anyagokra.</span><span class="sxs-lookup"><span data-stu-id="9a62a-323">When you set up the project contract, you agree to bill the customer each month for time and materials on the project.</span></span> <span data-ttu-id="9a62a-324">Hoz létre a számlázási szabály, amely a következő információkat tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="9a62a-324">You create a billing rule that includes the following information:</span></span>

-   <span data-ttu-id="9a62a-325">A szerződési időszak hat hónap.</span><span class="sxs-lookup"><span data-stu-id="9a62a-325">The contract period is six months.</span></span>
-   <span data-ttu-id="9a62a-326">A tanácsadási idő óránkénti 150 díjjal kerül számításra.</span><span class="sxs-lookup"><span data-stu-id="9a62a-326">Consulting time is calculated at a rate of 150 per hour.</span></span>
-   <span data-ttu-id="9a62a-327">Az irodai kellékek önköltségi áron kerülnek számlázásra, és a projekt teljes költsége nem lehet nagyobb, mint 10 000.</span><span class="sxs-lookup"><span data-stu-id="9a62a-327">Office supplies are invoiced at cost, and the total cost for the project must not exceed 10,000.</span></span>
-   <span data-ttu-id="9a62a-328">Vevői számla létrehozása a projekt során minden naptári hónap végén.</span><span class="sxs-lookup"><span data-stu-id="9a62a-328">You create a customer invoice at the end of each calendar month during the project.</span></span>

<span data-ttu-id="9a62a-329">Az első hónapban 800 órák összesen rögzítésre kerülnek a tanácsadók a projekt szerint.</span><span class="sxs-lookup"><span data-stu-id="9a62a-329">During the first month, a total of 800 hours are recorded by the consultants on the project.</span></span> <span data-ttu-id="9a62a-330">A projekthez számlázott irodai kellékek költsége 2 000.</span><span class="sxs-lookup"><span data-stu-id="9a62a-330">The cost of office supplies that are charged to the project is 2,000.</span></span> <span data-ttu-id="9a62a-331">Tehát a hónap végén 122 000-re hoz létre számlát, amely úgy kerül kiszámításra, hogy 800 óra, óránkénti 150-el, továbbá 2000 az irodai kellékért.</span><span class="sxs-lookup"><span data-stu-id="9a62a-331">Therefore, at the end of the month, you create an invoice for 122,000, which is calculated as 800 hours at 150 per hour, plus 2,000 for office supplies.</span></span>




