---
title: "Konszolidáció és megszüntetés áttekintése"
description: "A cikk a konszolidációs és megszüntetési folyamat általános ismertetését tartalmazza. Magában foglalja a gyakori kérdésekre adott válaszokat is."
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerConsolidate
audience: Application User
ms.reviewer: robinr
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13151
ms.assetid: 9d8f55cb-b2cf-4e01-89cf-0e21f5c8ae1f
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 14b294c1b707236c970c3ff177740a242ec1d834
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="consolidation-and-elimination-overview"></a><span data-ttu-id="b0f13-104">Konszolidáció és megszüntetés áttekintése</span><span class="sxs-lookup"><span data-stu-id="b0f13-104">Consolidation and elimination overview</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="b0f13-105">A cikk a konszolidációs és megszüntetési folyamat általános ismertetését tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="b0f13-105">This article provides general information about the consolidation and elimination process.</span></span> <span data-ttu-id="b0f13-106">Magában foglalja a gyakori kérdésekre adott válaszokat is.</span><span class="sxs-lookup"><span data-stu-id="b0f13-106">It includes answers to some frequently asked questions.</span></span>

<span data-ttu-id="b0f13-107">Ha megszűntet adatokat, akkor több leányvállalat pénzügyi eredményei egyesülnek egy konszolidált vállalatként.</span><span class="sxs-lookup"><span data-stu-id="b0f13-107">When you consolidate data, the financial results for multiple subsidiary companies are combined into results for a single, consolidated company.</span></span> <span data-ttu-id="b0f13-108">A lényvállalatok eltérő verziókon vagy rendszereken lehetnek, résztulajdonoltak lehetnek és eltérő pénznemeket használhatnak.</span><span class="sxs-lookup"><span data-stu-id="b0f13-108">Subsidiaries might be on different versions or systems, they might not be fully owned, and they might use different currencies.</span></span> <span data-ttu-id="b0f13-109">Adategyesítéshez több lehetőséget választhat:</span><span class="sxs-lookup"><span data-stu-id="b0f13-109">There are multiple options for consolidating data:</span></span>

-   <span data-ttu-id="b0f13-110">**Online konszolidálás** – Ez a lehetőség, összesíti a napi egyenlegeket a kiválasztott számlák és dimenziók szerint, majd eltároljak azokat a konszolidált vállalatban.</span><span class="sxs-lookup"><span data-stu-id="b0f13-110">**Consolidate online** – This option consolidates daily balances by the selected accounts and dimensions, and stores them in a consolidation company.</span></span>
-   <span data-ttu-id="b0f13-111">**Pénzügyi jelentéskészítés** – Ezzel a lehetőséggel bármikor konszolidálhat tranzakciókat és egyenlegeket.</span><span class="sxs-lookup"><span data-stu-id="b0f13-111">**Financial reporting** – This option enables consolidation of transactions and balances, and can be generated at any time.</span></span> <span data-ttu-id="b0f13-112">Több szinten is létrehozhat hierarchiákat és több jelentés-devizanem is megjeleníthető.</span><span class="sxs-lookup"><span data-stu-id="b0f13-112">Multiple levels of hierarchies can be created, and multiple reporting currencies can be viewed.</span></span>
-   <span data-ttu-id="b0f13-113">**Konszolidálás importálással** – Ez a lehetőség egyenlegeket importál a konszolidációs vállalatba.</span><span class="sxs-lookup"><span data-stu-id="b0f13-113">**Consolidate with import** – This option imports balances into a consolidation company.</span></span>
-   <span data-ttu-id="b0f13-114">**Vállalat egyenlegek exportálása** – Ez a lehetőség export fájlt biztosít vállalati egyenlegekhez.</span><span class="sxs-lookup"><span data-stu-id="b0f13-114">**Export company balances** – This option provides an export file of company balances.</span></span> <span data-ttu-id="b0f13-115">A fájl később importálható a többi példányba vagy más rendszerekbe.</span><span class="sxs-lookup"><span data-stu-id="b0f13-115">The file can then be imported into other instances or systems.</span></span> <span data-ttu-id="b0f13-116">A pénzügyi jelentések használhatók az egyenlegek Microsoft Excel fájlba történő exportálásához.</span><span class="sxs-lookup"><span data-stu-id="b0f13-116">Financial reporting can also be used to export the balances to a Microsoft Excel file.</span></span>

<span data-ttu-id="b0f13-117">Az eltávolításokat többféleképpen lehet jelenteni:</span><span class="sxs-lookup"><span data-stu-id="b0f13-117">Eliminations can be reported in multiple ways:</span></span>

-   <span data-ttu-id="b0f13-118">Az eltávolítási szabályok a rendszerben adhatók meg, és a konszolidációs folyamat során kerülnek feldolgozásra egy eltávolítási javaslat alapján.</span><span class="sxs-lookup"><span data-stu-id="b0f13-118">Elimination rules can be set up in the system, and then processed during the consolidation process or through an elimination proposal.</span></span> <span data-ttu-id="b0f13-119">A szabályok bármelyik vállalat számára feladhatók, amelyeket kiválasztottak **Pénzügyi eltávolítási folyamatokhoz** a jogi személy beállításoknál.</span><span class="sxs-lookup"><span data-stu-id="b0f13-119">The rules can be posted to any company that has **Use for financial elimination process** selected in the legal entity setup.</span></span>
-   <span data-ttu-id="b0f13-120">Egy külön vállalat hozható létre és használható, hogy manuálisan meghatározhatók és feladhatók legyenek az eltávolítási tranzakciók.</span><span class="sxs-lookup"><span data-stu-id="b0f13-120">A separate company can be created and used to manually determine and post elimination transactions.</span></span> <span data-ttu-id="b0f13-121">Ez a vállalat használható a konszolidációs folyamatban vagy a pénzügyi jelentésben.</span><span class="sxs-lookup"><span data-stu-id="b0f13-121">This company can be used in the consolidation process or in financial reporting.</span></span>
-   <span data-ttu-id="b0f13-122">A vállaltközi tevékenység meghatározásához használt számlák és pénzügyi dimenziók sor vagy oszlopdefinícióval szűrhetők a Pénzügyi jelentésben, és teljes részletességű képességek használhatók.</span><span class="sxs-lookup"><span data-stu-id="b0f13-122">The accounts and financial dimensions that are used to determine intercompany activity can be filtered on a row definition or column definition in Financial reporting, and full drill-down capabilities can be used.</span></span> <span data-ttu-id="b0f13-123">A számított oszlop vagy sor ezután felhasználható számlák és pénzügyi dimenziók eltávolítására a konszolidált végösszegből.</span><span class="sxs-lookup"><span data-stu-id="b0f13-123">A calculated column or row can then be used to remove the accounts and financial dimensions from the consolidated total.</span></span>

<span data-ttu-id="b0f13-124">Sok összevonási eset lehetséges és minden módszer máshogy tudja kezelni ezeket az eseteket.</span><span class="sxs-lookup"><span data-stu-id="b0f13-124">There are many consolidation scenarios, and each method can handle the scenarios in different ways.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="b0f13-125">Gyakori kérdések</span><span class="sxs-lookup"><span data-stu-id="b0f13-125">Frequently asked questions</span></span>
1.  <span data-ttu-id="b0f13-126">Szeretnék eltávolításokat az adatbázisba feladni.</span><span class="sxs-lookup"><span data-stu-id="b0f13-126">I prefer to post eliminations in a database.</span></span> <span data-ttu-id="b0f13-127">Mik a lehetőségeim?</span><span class="sxs-lookup"><span data-stu-id="b0f13-127">What are my options?</span></span>

<span data-ttu-id="b0f13-128">Több lehetőség is létezik.</span><span class="sxs-lookup"><span data-stu-id="b0f13-128">You have multiple options.</span></span> <span data-ttu-id="b0f13-129">Használhatja az **Online konszolidálás** lehetőséget, majd az eltávolításokat bevonhatja javaslatként a folyamatba.</span><span class="sxs-lookup"><span data-stu-id="b0f13-129">You can use the **Consolidate online** option, and include eliminations during the process or as a proposal.</span></span> <span data-ttu-id="b0f13-130">A tranzakciók a konszolidációs vállalatba kerülnek feladásra.</span><span class="sxs-lookup"><span data-stu-id="b0f13-130">The transactions will be posted in the consolidation company.</span></span> <span data-ttu-id="b0f13-131">Azt is megteheti, hogy elkülönít egy vállalatot, amelyben manuálisan hozza létre az eltávolításokat, majd ezt a vállalatot a Pénzügyi jelentéshez használja az eltávolítási folyamatban.</span><span class="sxs-lookup"><span data-stu-id="b0f13-131">Alternatively, you can have a separate company that you manually create the eliminations in, and then use that company in Financial reporting or in the consolidation process.</span></span>

2.  <span data-ttu-id="b0f13-132">Az eltávolítási eredmények jelentéseire több pénznemben van szükség.</span><span class="sxs-lookup"><span data-stu-id="b0f13-132">We need our consolidated results in multiple reporting currencies.</span></span>

<span data-ttu-id="b0f13-133">A **Pénzügyi jelentéskészítés** lehetőségben korlátlan számú pénznemet használhat.</span><span class="sxs-lookup"><span data-stu-id="b0f13-133">The **Financial reporting** option has unlimited reporting currencies.</span></span> <span data-ttu-id="b0f13-134">Az adatok lefordításra kerülnek a jelentés létrehozásakor a fő számlában megadott árfolyamtípus és pénznem átváltási módszer alapján.</span><span class="sxs-lookup"><span data-stu-id="b0f13-134">The data is translated during report generation, based on the exchange rate type and currency translation method that are set on the main account.</span></span> <span data-ttu-id="b0f13-135">Azonban az **Online konszolidálás** lehetőség csak egy jelentési pénznemmel rendelkezik, konszolidált vállalatok szükségesek az egyes jelentési pénznemekhez ha ezt a lehetőséget választja.</span><span class="sxs-lookup"><span data-stu-id="b0f13-135">However, because the **Consolidate online** option has only one reporting currency, a consolidated company is required for each reporting currency if you use that option.</span></span> <span data-ttu-id="b0f13-136">A **Pénzügyi jelentéskészítés** lehetőség az ajánlott módszer.</span><span class="sxs-lookup"><span data-stu-id="b0f13-136">The **Financial reporting** option is the recommended method.</span></span>

3.  <span data-ttu-id="b0f13-137">Az egyes vállalatokkal kapcsolatos részletek megjelenítése tranzakciós szinten.</span><span class="sxs-lookup"><span data-stu-id="b0f13-137">I want to see transaction-level detail for each company.</span></span>

<span data-ttu-id="b0f13-138">A **Pénzügyi jelentéskészítés** lehetőség a megfelelő választás, mert a tranzakciós szintű részletek annyi vállalathoz tekinthetők meg, amennyi a jelentési fa definíciójában van megadva.</span><span class="sxs-lookup"><span data-stu-id="b0f13-138">The **Financial reporting** option is the solution, because transaction-level detail can be viewed for as many companies as are included in the reporting tree definition.</span></span>

4.  <span data-ttu-id="b0f13-139">Költségvetés tervezést vagy költségvetés-ellenőrzést használunk, amit konszolidálni kell.</span><span class="sxs-lookup"><span data-stu-id="b0f13-139">We are using budget planning or budget control, and it must be consolidated.</span></span>
<span data-ttu-id="b0f13-140">A **Pénzügyi jelentéskészítés** lehetőség a megoldás minden költségvetés-tervezési vagy költségvetés-ellenőrzési adat konszolidálására.</span><span class="sxs-lookup"><span data-stu-id="b0f13-140">The **Financial reporting** option is the solution to consolidate any budget planning or budget control data.</span></span>

5.  <span data-ttu-id="b0f13-141">A leányvállalatok az egész világban vannak szétszórva, és több számlatükörrel rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="b0f13-141">Our subsidiaries are spread throughout the world, and we have multiple charts of accounts.</span></span> <span data-ttu-id="b0f13-142">Mi a legjobb módszer az adatok konszolidálására?</span><span class="sxs-lookup"><span data-stu-id="b0f13-142">What is the best method for consolidating our data?</span></span>

<span data-ttu-id="b0f13-143">Több lehetőség közül választhat, amikor több számlatükröt kell kezelnie.</span><span class="sxs-lookup"><span data-stu-id="b0f13-143">You have multiple options when you must handle multiple charts of accounts.</span></span> <span data-ttu-id="b0f13-144">Használhatja az **Online konszolidálás** lehetőséget, majd válassza ki, hogy a fő számlán megadott konszolidációs számlát vagy a konszolidációs számlacsoportot használja.</span><span class="sxs-lookup"><span data-stu-id="b0f13-144">You can use the **Consolidate online** option, and then choose to use either the consolidation account that is defined on the main account or a consolidation account group.</span></span> <span data-ttu-id="b0f13-145">Emellett használhatja a **Pénzügyi jelentéskészítés** lehetőséget is, megadhat több linket pénzügyi dimenziókhoz a sordefinícióban és leképezheti a számlákat.</span><span class="sxs-lookup"><span data-stu-id="b0f13-145">You can also use the **Financial reporting** option, include multiple links to the financial dimensions in the row definition, and map the accounts.</span></span>

6.  <span data-ttu-id="b0f13-146">Többszintű konszolidáció szükséges.</span><span class="sxs-lookup"><span data-stu-id="b0f13-146">We require multiple levels of consolidation.</span></span> <span data-ttu-id="b0f13-147">Ez azt jelenti, hogy először az összes európai leányvállalat konszolidációja megy végbe brit fontban (GBP).</span><span class="sxs-lookup"><span data-stu-id="b0f13-147">In other words, we first consolidate all our European subsidiaries to the British pound (GBP).</span></span> <span data-ttu-id="b0f13-148">Ezután létrejönnek az adatok és átváltásra kerül a konszolidált összeg dollárra (USD).</span><span class="sxs-lookup"><span data-stu-id="b0f13-148">We then take that data and translate the consolidated amount to US dollars.</span></span> <span data-ttu-id="b0f13-149">Hogy lehet ezt megtenni?</span><span class="sxs-lookup"><span data-stu-id="b0f13-149">How can we do this?</span></span>

<span data-ttu-id="b0f13-150">Ha többszintű konszolidáció szükséges, miközben az egyes szintek különböző pénznemeket használnak, akkor az **Online konszolidálás** lehetőséget kell választani.</span><span class="sxs-lookup"><span data-stu-id="b0f13-150">When multiple levels of consolidation are required, and different currencies are used at each level, you must use the **Consolidate online** option.</span></span> <span data-ttu-id="b0f13-151">Több konszolidációs vállalat is létrehozható amelyeknek különböző a könyvelési és jelentési pénzneme.</span><span class="sxs-lookup"><span data-stu-id="b0f13-151">Multiple consolidation companies must be created that differ in their accounting and reporting currencies.</span></span> <span data-ttu-id="b0f13-152">A konszolidációt többször kell futtatni.</span><span class="sxs-lookup"><span data-stu-id="b0f13-152">The consolidation must then be run multiple times.</span></span> <span data-ttu-id="b0f13-153">A **Pénzügyi jelentéskészítés** lehetőség mindig átváltja az egyes forrásvállalatok könyvelési pénznemét a választott pénznemre.</span><span class="sxs-lookup"><span data-stu-id="b0f13-153">The **Financial reporting** option always translates from each source company's accounting currency to the selected currency.</span></span>

7.  <span data-ttu-id="b0f13-154">A leányvállalatok más rendszerben vannak.</span><span class="sxs-lookup"><span data-stu-id="b0f13-154">We have subsidiaries on a different system.</span></span> <span data-ttu-id="b0f13-155">Hogyan konszolidálhatók?</span><span class="sxs-lookup"><span data-stu-id="b0f13-155">How can we consolidate them?</span></span>

<span data-ttu-id="b0f13-156">Használja a **Konszolidálás importálással** lehetőséget az egyenlegek konszolidációs vállalatba foglalásához.</span><span class="sxs-lookup"><span data-stu-id="b0f13-156">Use the **Consolidate with import** option to bring the balances into a consolidation company.</span></span>

8.  <span data-ttu-id="b0f13-157">Néhány leányvállalatot csak részben birtoklunk.</span><span class="sxs-lookup"><span data-stu-id="b0f13-157">Some of our subsidiaries are not fully owned.</span></span> <span data-ttu-id="b0f13-158">Mi a legjobb módszer ezeknek a konszolidálására?</span><span class="sxs-lookup"><span data-stu-id="b0f13-158">What is the best method for consolidating them?</span></span>

<span data-ttu-id="b0f13-159">Ezekhez a leányvállalatokhoz több lehetőség van.</span><span class="sxs-lookup"><span data-stu-id="b0f13-159">You have multiple options for partially owned subsidiaries.</span></span> <span data-ttu-id="b0f13-160">A **Pénzügyi jelentéskészítés** lehetőséggel megadhatja a jelentési fa definícióját és a tulajdoni viszonyokat.</span><span class="sxs-lookup"><span data-stu-id="b0f13-160">By using the **Financial reporting** option, you can define a reporting tree definition and the ownership.</span></span> <span data-ttu-id="b0f13-161">Továbbá használhat számított oszlopot vagy sort, hogy megjelenítse a részlegesen birtokolt összeget.</span><span class="sxs-lookup"><span data-stu-id="b0f13-161">You can also use a calculated row or column to represent the partially owned amount.</span></span> <span data-ttu-id="b0f13-162">Még a kisebbségi kamatot is megjelenítheti a jelentés külön sorában.</span><span class="sxs-lookup"><span data-stu-id="b0f13-162">You can even show the minority interest as its own row on a report.</span></span> <span data-ttu-id="b0f13-163">Használhatja az **Online konszolidálás** lehetőséget is.</span><span class="sxs-lookup"><span data-stu-id="b0f13-163">You can also use the **Consolidate online** option.</span></span> <span data-ttu-id="b0f13-164">A **Jogi személyek** lap tartalmaz egy **Tulajdonos** oszlopot, ahol megadhatja az anyavállalat által birtokolt százalékot.</span><span class="sxs-lookup"><span data-stu-id="b0f13-164">The **Legal entities** tab has an **Ownership** column, where you can define the percentage that is owned by the parent company.</span></span>

9.  <span data-ttu-id="b0f13-165">A szervezetnek meg kell jelenítenie a konszolidációkat üzleti egységenként vagy a szervezeti hierarchiákat kívánja használni.</span><span class="sxs-lookup"><span data-stu-id="b0f13-165">Our organization must show consolidations by business unit or wants to use the organization hierarchies.</span></span>

<span data-ttu-id="b0f13-166">A **Pénzügyi jelentéskészítés** lehetőség a megoldás.</span><span class="sxs-lookup"><span data-stu-id="b0f13-166">The **Financial reporting** option is the solution.</span></span> <span data-ttu-id="b0f13-167">A szervezeti hierarchiák amelyek jogi személyekkel vagy pénzügyi dimenziókkal rendelkeznek jelenthetők a Pénzügyi jelentéskészítéssel.</span><span class="sxs-lookup"><span data-stu-id="b0f13-167">Organization hierarchies that have legal entities or financial dimensions in them can be reported on in Financial reporting.</span></span> <span data-ttu-id="b0f13-168">Létrehozhatja a saját, többszintű hierarchiáját a jelentési fa definíciójának segítségével, ami jogi személyek és dimenzióértékek kombinációjából áll.</span><span class="sxs-lookup"><span data-stu-id="b0f13-168">You can also create your own multilevel hierarchies by using a reporting tree definition that has a combination of legal entities and dimension values.</span></span>

10. <span data-ttu-id="b0f13-169">A rendszernek egynél több példánya létezik.</span><span class="sxs-lookup"><span data-stu-id="b0f13-169">We have more than one instance of the system.</span></span>

<span data-ttu-id="b0f13-170">A **Vállalati egyenlegek exportálása** lehetőséggel exportálhat egy példányból, majd használja a **Konszolidálás importálással** lehetőséget a másik példányban, hogy konszolidálja az adatokat.</span><span class="sxs-lookup"><span data-stu-id="b0f13-170">By using the **Export company balances** option to export from one instance and then using the **Consolidate with import** option on the other instance, you can consolidate the data.</span></span>


<span data-ttu-id="b0f13-171">További tudnivalókért lásd: [Devizaátértékelés konszolidációs vállalatban](..\general-ledger\currency-revaluation-consolidation-company.md).</span><span class="sxs-lookup"><span data-stu-id="b0f13-171">For more information, see [Currency revalution in a consolidation company](..\general-ledger\currency-revaluation-consolidation-company.md).</span></span>


