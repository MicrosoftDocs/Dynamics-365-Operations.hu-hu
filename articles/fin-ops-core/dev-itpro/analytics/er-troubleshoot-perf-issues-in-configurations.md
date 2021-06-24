---
title: Hibaelhárítás az ER-konfigurációk teljesítményével kapcsolatban
description: Ez a témakör leírja, hogyan lehet megtalálni és kijavítani a teljesítményproblémákat az elektronikus jelentési (ER) konfigurációkban.
author: NickSelin
ms.date: 06/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner, ERFormatMappingRunJobTable, ERParameters, ERSolutionTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: maximbel
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: d77c2aad904ba911ac19009d6a981ea4153aaa48
ms.sourcegitcommit: 60afcd85b3b5b9e5e8981ebbb57c0161cf05e54b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/09/2021
ms.locfileid: "6216865"
---
# <a name="troubleshooting-performance-issues-in-er-configurations"></a><span data-ttu-id="215b8-103">Hibaelhárítás az ER-konfigurációk teljesítményével kapcsolatban</span><span class="sxs-lookup"><span data-stu-id="215b8-103">Troubleshooting performance issues in ER configurations</span></span>

<span data-ttu-id="215b8-104">Ez a témakör leírja, hogyan lehet megtalálni és kijavítani a teljesítményproblémákat az [Elektronikus jelentés](general-electronic-reporting.md) (ER) [konfigurációkban](general-electronic-reporting.md#Configuration).</span><span class="sxs-lookup"><span data-stu-id="215b8-104">This topic explains how to find and solve performance issues in [Electronic reporting](general-electronic-reporting.md) (ER) [configurations](general-electronic-reporting.md#Configuration).</span></span>

<span data-ttu-id="215b8-105">A teljesítmény vizsgálata általában több lépésből áll.</span><span class="sxs-lookup"><span data-stu-id="215b8-105">Typically, performance investigation consists of several steps.</span></span>

1. <span data-ttu-id="215b8-106">Adatok [gyűjtése](#collecting-data).</span><span class="sxs-lookup"><span data-stu-id="215b8-106">[Collect](#collecting-data) data.</span></span>
2. <span data-ttu-id="215b8-107">Az összegyűjtött adatok elemzése.</span><span class="sxs-lookup"><span data-stu-id="215b8-107">Analyze the collected data.</span></span>
3. <span data-ttu-id="215b8-108">Az elemzés eredményei alapján az ER-konfigurációk használatával lehet [változtatásokat eszközölni](#making-changes), vagy dönthet úgy, hogy további adatokat gyűjt.</span><span class="sxs-lookup"><span data-stu-id="215b8-108">Based on the results of the analysis, use ER configurations to [make changes](#making-changes), or decide to collect more data.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="215b8-109">Hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="215b8-109">Troubleshooting</span></span>

### <a name="analyze-execution-time"></a><span data-ttu-id="215b8-110">Végrehajtási idő elemzése</span><span class="sxs-lookup"><span data-stu-id="215b8-110">Analyze execution time</span></span>

<span data-ttu-id="215b8-111">A végrehajtási idő kiszámíthatatlan tényezőktől függhet, például az azonos környezetben futó egyéb feladatoktól és az adatokat az első alkalommal használó gyorsítótárazástól.</span><span class="sxs-lookup"><span data-stu-id="215b8-111">Execution time can depend on unpredictable factors, such as other tasks that are running in the same environment and caching that uses data when it's called for the first time.</span></span> <span data-ttu-id="215b8-112">Ezért többször meg kell ismételnie a végrehajtást és a méréseket.</span><span class="sxs-lookup"><span data-stu-id="215b8-112">Therefore, you should repeat the execution and measurement several times.</span></span>

<span data-ttu-id="215b8-113">Bizonyos esetekben a teljesítményproblémákat nem a jelentésekhez használt ER-formátumkonfiguráció okozza.</span><span class="sxs-lookup"><span data-stu-id="215b8-113">Sometimes, performance issues aren't caused by an ER format configuration that is used for reporting.</span></span> <span data-ttu-id="215b8-114">Ehelyett az az X++ kód okozza, amely az ER formátumkonfiguráció megnyitására használatos.</span><span class="sxs-lookup"><span data-stu-id="215b8-114">Instead, they are caused by the X++ code that is used to open that ER format configuration.</span></span>

1. <span data-ttu-id="215b8-115">A [Műveletközpontban](#infolog-time) vagy az [eseménynaplóban](#event-log-time) tekintse meg a jelentés végrehajtási idejét.</span><span class="sxs-lookup"><span data-stu-id="215b8-115">In either the [Action center](#infolog-time) or the [event log](#event-log-time), look at the execution time of the report.</span></span>
2. <span data-ttu-id="215b8-116">Hasonlítsa összes a jelentés teljes végrehajtási idejét az eset teljes végrehajtási idejével.</span><span class="sxs-lookup"><span data-stu-id="215b8-116">Compare the execution time of the report with the total execution time in the scenario.</span></span>
3. <span data-ttu-id="215b8-117">Ha a jelentés végrehajtási ideje sokkal kevesebb, mint a teljes végrehajtási idő, vegye figyelembe a jelentés által feldolgozott adatok mennyiségét:</span><span class="sxs-lookup"><span data-stu-id="215b8-117">If the execution time of the report is much less than the total execution time, consider the amount of data that the report processes:</span></span>

    - <span data-ttu-id="215b8-118">Ha a jelentés kis mennyiségű adatot dolgoz fel, akkor a probléma a konfiguráció betöltési idejéhez is kapcsolódhat.</span><span class="sxs-lookup"><span data-stu-id="215b8-118">If the report processes a small amount of data, the issue might involve the loading time of the configuration.</span></span>
    - <span data-ttu-id="215b8-119">Ha a jelentés nagy mennyiségű adatot dolgoz fel, akkor a probléma az X++ előfeldolgozáshoz is kapcsolódhat.</span><span class="sxs-lookup"><span data-stu-id="215b8-119">If the report processes a large amount of data, the issue might involve preprocessing X++.</span></span> <span data-ttu-id="215b8-120">Az eset elemzéséhez használja a [Trace Parser](#analyze-trace-parser-trace) megoldást.</span><span class="sxs-lookup"><span data-stu-id="215b8-120">Use [Trace parser](#analyze-trace-parser-trace) to analyze this case.</span></span>

    <span data-ttu-id="215b8-121">Egyéb esetekhez lásd a következő szakaszokat.</span><span class="sxs-lookup"><span data-stu-id="215b8-121">For other cases, see the next sections.</span></span>

4. <span data-ttu-id="215b8-122">Több, különböző mennyiségű adatot magukban foglaló tesztet futtasson annak megállapításához, hogy a végrehajtás ideje hogyan függ az adatok mennyiségétől.</span><span class="sxs-lookup"><span data-stu-id="215b8-122">Run multiple tests that involve different amounts of data to determine how the execution time depends on the amount of data.</span></span>

### <a name="analyze-trace-parser-traces"></a><a name="analyze-trace-parser-trace"></a><span data-ttu-id="215b8-123">Trace Parser hívásláncok elemzése</span><span class="sxs-lookup"><span data-stu-id="215b8-123">Analyze Trace parser traces</span></span>

<span data-ttu-id="215b8-124">Állítson össze egy kis példát, vagy gyűjtsön több hívásláncot a jelentéskészítés véletlenszerű részeiből.</span><span class="sxs-lookup"><span data-stu-id="215b8-124">Prepare a small example, or collect several traces during random parts of the report generation.</span></span>

<span data-ttu-id="215b8-125">Ezután a [Trace Parser](#trace-parser) megoldásban szabványos általános elemzéseket végezhet, és választ adhat a következő kérdésekre:</span><span class="sxs-lookup"><span data-stu-id="215b8-125">Then, in [Trace parser](#trace-parser), do a standard bottom-to-up analysis, and answer the following questions:</span></span>

- <span data-ttu-id="215b8-126">Melyek a legfontosabb metódusok az időfelhasználás szempontjából?</span><span class="sxs-lookup"><span data-stu-id="215b8-126">What are the top methods in terms of time consumption?</span></span>
- <span data-ttu-id="215b8-127">A teljes időnek mekkora részét használják ezek a metódusok?</span><span class="sxs-lookup"><span data-stu-id="215b8-127">What part of the overall time do those methods use?</span></span>

<span data-ttu-id="215b8-128">Válaszolja meg ugyanezeket a kérdéseket a lekérdezésekhez is.</span><span class="sxs-lookup"><span data-stu-id="215b8-128">Answer the same questions for queries.</span></span>

<span data-ttu-id="215b8-129">Ha látja, hogy a metódusok előtagja "ER", lépjen tovább a következő szakaszra.</span><span class="sxs-lookup"><span data-stu-id="215b8-129">If you see that methods are prefixed with "ER," move on to the next section.</span></span>

<span data-ttu-id="215b8-130">Ha azt látja, hogy a metódusok vagy lekérdezések az alkalmazáscsomagból származnak, akkor fontolja meg az általános optimalizálásokat (például hozzon létre indexeket).</span><span class="sxs-lookup"><span data-stu-id="215b8-130">If you see that methods or queries originated in the application suite, consider generic optimizations (for example, create indexes).</span></span>

<span data-ttu-id="215b8-131">A hívások számának elemzése.</span><span class="sxs-lookup"><span data-stu-id="215b8-131">Analyze the number of calls.</span></span> <span data-ttu-id="215b8-132">Ha a szám jelentősen magasabb a vártnál, akkor célszerű megfontolni a konfiguráció megfelelő csomópontjainak gyorsítótárazását.</span><span class="sxs-lookup"><span data-stu-id="215b8-132">If the number is significantly higher than expected, consider caching the corresponding nodes of the configuration.</span></span>

### <a name="analyze-database-calls"></a><a name="analyze-database-calls"></a><span data-ttu-id="215b8-133">Adatbázishívások elemzése</span><span class="sxs-lookup"><span data-stu-id="215b8-133">Analyze database calls</span></span>

<span data-ttu-id="215b8-134">Készítsen elő kis mennyiségű adatot tartalmazó példát, hogy [ER-nyomkövetést](#electronic-reporting-traces) gyűjthessen össze.</span><span class="sxs-lookup"><span data-stu-id="215b8-134">Prepare an example that has a small amount of data, so that you can collect an [ER trace](#electronic-reporting-traces).</span></span>

<span data-ttu-id="215b8-135">Ezután nyissa meg a hívásláncot az ER modellleképezés-tervezőben, és nézze meg az oldal alját.</span><span class="sxs-lookup"><span data-stu-id="215b8-135">Then open the trace in the ER model mapping designer, and look at the bottom of the page.</span></span> <span data-ttu-id="215b8-136">A következő kérdéseket válaszolja meg:</span><span class="sxs-lookup"><span data-stu-id="215b8-136">Answer the following questions:</span></span>

- <span data-ttu-id="215b8-137">Van ismétlődés a lekérdezésekben?</span><span class="sxs-lookup"><span data-stu-id="215b8-137">Is there any query duplication?</span></span> <span data-ttu-id="215b8-138">Ha van, fontolja meg a következő javítások egyikét:</span><span class="sxs-lookup"><span data-stu-id="215b8-138">If there is, consider one of the following fixes:</span></span>

    - <span data-ttu-id="215b8-139">[Használjon gyorsítótárazást](#use-caching), ha úgy gondolja, hogy egy szülőrekordon belül több hívás van.</span><span class="sxs-lookup"><span data-stu-id="215b8-139">[Use caching](#use-caching) if you think that there are several calls inside one parent record.</span></span>
    - <span data-ttu-id="215b8-140">[Gyorsítótárazott, paraméterezett számított mezőt használjon](#cached-parameterized), ha úgy gondolja, hogy ugyanahhoz a rekordhoz több hívás is van több rekordon belül.</span><span class="sxs-lookup"><span data-stu-id="215b8-140">[Use a cached, parameterized calculated field](#cached-parameterized) if you think that there are calls to the same record inside different records.</span></span>
    - <span data-ttu-id="215b8-141">[Használjon **JOIN** adatforrást](#use-join-datasource), ha az adatbázisból jelentős számú különböző rekordot kell beolvasni.</span><span class="sxs-lookup"><span data-stu-id="215b8-141">[Use a **JOIN** data source](#use-join-datasource) if you have to read to a substantial number of different records from a database.</span></span>

- <span data-ttu-id="215b8-142">A lekérdezések és beolvasási rekordok száma megfelel az adatok teljes összegének?</span><span class="sxs-lookup"><span data-stu-id="215b8-142">Does the number of queries and fetched records correspond to the overall amount of data?</span></span> <span data-ttu-id="215b8-143">Ha például egy dokumentumnak 10 sora van, akkor a statisztikai adatok azt mutatják, hogy a jelentés 10 sort vagy 1000 sort nyer ki?</span><span class="sxs-lookup"><span data-stu-id="215b8-143">For example, if a document has 10 lines, do the statistics show that the report extracts 10 lines or 1,000 lines?</span></span> <span data-ttu-id="215b8-144">Ha jelentős számú lekért rekordja van, fontolja meg a következő javítások egyikét:</span><span class="sxs-lookup"><span data-stu-id="215b8-144">If you have a substantial number of fetched records, consider one of the following fixes:</span></span>

    - <span data-ttu-id="215b8-145">Az SQL-szerveroldalon az adatok feldolgozása [a **WHERE** függvény helyett a **FILTER** függvényt használja](#filter).</span><span class="sxs-lookup"><span data-stu-id="215b8-145">[Use the **FILTER** function instead of the **WHERE** function](#filter) to process data on the SQL Server side.</span></span>
    - <span data-ttu-id="215b8-146">Ugyanazon adatok beolvasásának elkerülése érdekében használjon gyorsítótárazást.</span><span class="sxs-lookup"><span data-stu-id="215b8-146">Use caching to avoid fetching the same data.</span></span>
    - <span data-ttu-id="215b8-147">Az [összegyűjtött adatfüggvények](#collected-data) segítségével elkerülheti, hogy ugyanezeket az adatokat olvassa be az összegzéshez.</span><span class="sxs-lookup"><span data-stu-id="215b8-147">[Use collected data functions](#collected-data) to avoid fetching the same data for summarization.</span></span>

### <a name="analyze-perfview-traces"></a><span data-ttu-id="215b8-148">PerfView-nyomkövetések elemzése</span><span class="sxs-lookup"><span data-stu-id="215b8-148">Analyze PerfView traces</span></span>

<span data-ttu-id="215b8-149">A [PerfView](#perfview) egy tapasztalt fejlesztőknek készült eszköz.</span><span class="sxs-lookup"><span data-stu-id="215b8-149">[PerfView](#perfview) is a tool for experienced developers.</span></span> <span data-ttu-id="215b8-150">A következő lépésekkel kapcsolatos további tudnivalókat lásd a [Wall Clock Time-vizsgálatok alapjai](https://channel9.msdn.com/Series/PerfView-Tutorial/Tutorial-12-Wall-Clock-Time-Investigation-Basics) című részt.</span><span class="sxs-lookup"><span data-stu-id="215b8-150">For more detailed information about the following steps, see [Wall Clock Time Investigation Basics](https://channel9.msdn.com/Series/PerfView-Tutorial/Tutorial-12-Wall-Clock-Time-Investigation-Basics).</span></span>

1. <span data-ttu-id="215b8-151">Híváslánc begyűjtése a szálidő használatával.</span><span class="sxs-lookup"><span data-stu-id="215b8-151">Collect a trace by using thread time.</span></span>
2. <span data-ttu-id="215b8-152">Csak a **runUnattended** parancsot használó a vermeket foglalja bele, így csak a konfigurációt végrehajtó szálra szűrhet.</span><span class="sxs-lookup"><span data-stu-id="215b8-152">Include only stacks that use **runUnattended**, to filter only the thread that has configuration execution.</span></span> <span data-ttu-id="215b8-153">(Adja hozzá a **runUnattended** parancsot az **IncPats** beviteli mezőbe.)</span><span class="sxs-lookup"><span data-stu-id="215b8-153">(Add **runUnattended** to the **IncPats** input box.)</span></span>
3. <span data-ttu-id="215b8-154">Minden processzor, hálózati és zárolt idő le legyen összecsukva.</span><span class="sxs-lookup"><span data-stu-id="215b8-154">Fold all CPU, network, and blocked time.</span></span>
4. <span data-ttu-id="215b8-155">[ER-készletek betöltése a PerfView nézethez](https://download.microsoft.com/download/2/d/0/2d037b0f-ffd1-4d65-b64f-fcdf51f2c81f/ER_PerfViewPresets.xml).</span><span class="sxs-lookup"><span data-stu-id="215b8-155">Load [ER presets for PerfView](https://download.microsoft.com/download/2/d/0/2d037b0f-ffd1-4d65-b64f-fcdf51f2c81f/ER_PerfViewPresets.xml).</span></span>
5. <span data-ttu-id="215b8-156">Válassza ki az **ER** \> **Egyéb előbeállítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="215b8-156">Select **ER** \> **Other preset**.</span></span>
6. <span data-ttu-id="215b8-157">Nézze meg a neveket:</span><span class="sxs-lookup"><span data-stu-id="215b8-157">Look at the names:</span></span>

    - <span data-ttu-id="215b8-158">Valószínűleg a legtöbb időt felhasználó platformkód látható.</span><span class="sxs-lookup"><span data-stu-id="215b8-158">You will probably see the platform code that consumes the most time.</span></span>
    - <span data-ttu-id="215b8-159">Duplán kattinthat (vagy duplán kattinthat) és végighaladhat a **hívókon**.</span><span class="sxs-lookup"><span data-stu-id="215b8-159">You can double-tap (or double-click) and go up through **callees**.</span></span>

        <span data-ttu-id="215b8-160">Ha olyan osztályokat talál, amelyek előtagja "ERExpression", és ezek képletekkel kapcsolatos függvények, akkor a függvény nevét az osztálynév alapján ki lehet következtetni, és az attribútumokat megtekintheti az ER-adattárban.</span><span class="sxs-lookup"><span data-stu-id="215b8-160">If you find classes that have the prefix "ERExpression," and if they are functions that are related to formulas, you can guess the function name based on the class name, and you can look at the ER repo to view the attributes.</span></span>

### <a name="fixes"></a><span data-ttu-id="215b8-161">Javítások</span><span class="sxs-lookup"><span data-stu-id="215b8-161">Fixes</span></span>

- <span data-ttu-id="215b8-162">Ha azt látja, hogy a processzoridő nagy része lekérdezésekben van felhasználva, próbálja meg csökkenteni a lekérdezések számát:</span><span class="sxs-lookup"><span data-stu-id="215b8-162">If you see that most of the CPU time is consumed by queries, try to reduce the number of queries:</span></span>

    - <span data-ttu-id="215b8-163">Ellenőrizze, hogy van-e ismétlődő lekérdezés az [ER-hívásláncban](#analyze-database-calls).</span><span class="sxs-lookup"><span data-stu-id="215b8-163">[Review the ER trace](#analyze-database-calls) for duplicated queries.</span></span>
    - <span data-ttu-id="215b8-164">Nézze meg, hány rekord van beolvasva, és értékelje ki, hogy elméletileg mennyi adat beolvasása szükséges.</span><span class="sxs-lookup"><span data-stu-id="215b8-164">See how many records are fetched, and evaluate how much data should theoretically be fetched.</span></span>

- <span data-ttu-id="215b8-165">Ha azt látja, hogy a legtöbb processzoridőt a használt függvények használják fel, keresse meg azt a helyet a konfigurációban, amely a legtöbb erőforrást használja fel.</span><span class="sxs-lookup"><span data-stu-id="215b8-165">If you see that most of the CPU time is consumed by the functions that are used, try to find the place in the configuration that consumes the most resources.</span></span>
- <span data-ttu-id="215b8-166">Ha azt látja, hogy a processzoridő nagy része az adatgyűjtési függvények használják fel, akkor a modell-leképez oldalán érdemes megfontolni az *SQL-csoportosításra* való lecserélést.</span><span class="sxs-lookup"><span data-stu-id="215b8-166">If you see that most of the CPU time is consumed by data collection functions, consider replacing them with *SQL group by* on the model mapping side.</span></span>

### <a name="collecting-data"></a><a name="collecting-data"></a><span data-ttu-id="215b8-167">Adatgyűjtés</span><span class="sxs-lookup"><span data-stu-id="215b8-167">Collecting data</span></span>

<span data-ttu-id="215b8-168">A környezettől függően többféleképpen lehet összegyűjteni az elérhető adatokat:</span><span class="sxs-lookup"><span data-stu-id="215b8-168">Depending on your environment, there are several ways to collect available data:</span></span>

- <span data-ttu-id="215b8-169">A teljes futási idő lekérdezése:</span><span class="sxs-lookup"><span data-stu-id="215b8-169">Get the total running time:</span></span>

    - <span data-ttu-id="215b8-170">A Műveletközpontból</span><span class="sxs-lookup"><span data-stu-id="215b8-170">From the Action center</span></span>
    - <span data-ttu-id="215b8-171">Az eseménynaplóból</span><span class="sxs-lookup"><span data-stu-id="215b8-171">From the event log</span></span>

- <span data-ttu-id="215b8-172">A végrehajtás profilozása:</span><span class="sxs-lookup"><span data-stu-id="215b8-172">Profile the execution:</span></span>

    - <span data-ttu-id="215b8-173">Az ER eszközök segítségével</span><span class="sxs-lookup"><span data-stu-id="215b8-173">By using ER tools</span></span>
    - <span data-ttu-id="215b8-174">A Trace Parser használatával</span><span class="sxs-lookup"><span data-stu-id="215b8-174">By using Trace parser</span></span>
    - <span data-ttu-id="215b8-175">A PerfView használatával</span><span class="sxs-lookup"><span data-stu-id="215b8-175">By using PerfView</span></span>

#### <a name="collecting-data-in-a-production-environment"></a><span data-ttu-id="215b8-176">Adatok gyűjtése éles környezetben</span><span class="sxs-lookup"><span data-stu-id="215b8-176">Collecting data in a production environment</span></span>

<span data-ttu-id="215b8-177">Bizonyos esetekben a problémák csak működési környezetben reprodukálhatók.</span><span class="sxs-lookup"><span data-stu-id="215b8-177">Sometimes, issues can be reproduced only in a production environment.</span></span> <span data-ttu-id="215b8-178">Az adatok a következő módokon gyűjthetők:</span><span class="sxs-lookup"><span data-stu-id="215b8-178">Data can be collected in the following ways:</span></span>

- <span data-ttu-id="215b8-179">[Trace Parser](../perf-test/trace-trace-tutorial.md) hívásláncok használatával</span><span class="sxs-lookup"><span data-stu-id="215b8-179">By using [Trace parser](../perf-test/trace-trace-tutorial.md) traces</span></span>
- <span data-ttu-id="215b8-180">[ER végrehajtási](trace-execution-er-troubleshoot-perf.md) hívásláncok használatával</span><span class="sxs-lookup"><span data-stu-id="215b8-180">By using [ER execution](trace-execution-er-troubleshoot-perf.md) traces</span></span>
- <span data-ttu-id="215b8-181">A teljes végrehajtási idő alkalmazásával</span><span class="sxs-lookup"><span data-stu-id="215b8-181">By using the total execution time</span></span>

#### <a name="collecting-data-in-a-development-environment"></a><span data-ttu-id="215b8-182">Adatok gyűjtése fejlesztési környezetben</span><span class="sxs-lookup"><span data-stu-id="215b8-182">Collecting data in a development environment</span></span>

<span data-ttu-id="215b8-183">A termelési környezetben használható eszközök mellett számos eszközt használhat fejlesztői környezetben:</span><span class="sxs-lookup"><span data-stu-id="215b8-183">In addition to the tools that can be used in a production environment, there are several tools that you can use in a development environment:</span></span>

- <span data-ttu-id="215b8-184">Eseménynapló (Microsoft-Dynamics-ElectronicReporting).</span><span class="sxs-lookup"><span data-stu-id="215b8-184">Event log (Microsoft-Dynamics-ElectronicReporting).</span></span> <span data-ttu-id="215b8-185">Ez a napló a teljes végrehajtási időt adja vissza.</span><span class="sxs-lookup"><span data-stu-id="215b8-185">This log can give you the total execution time.</span></span>
- <span data-ttu-id="215b8-186">Általános .NET eszközök, például a PerfView.</span><span class="sxs-lookup"><span data-stu-id="215b8-186">Common .NET tools, such as PerfView.</span></span>

<span data-ttu-id="215b8-187">Ezenkívül a fejlesztői környezet nagyobb rugalmasságot nyújt a kísérletek során.</span><span class="sxs-lookup"><span data-stu-id="215b8-187">Additionally, a development environment gives you more flexibility to experiment.</span></span> <span data-ttu-id="215b8-188">A jelentések egyes részeit például kikapcsolhatja, hogy megismerhesse hogyan befolyásolják a végrehajtás idejét.</span><span class="sxs-lookup"><span data-stu-id="215b8-188">For example, you can turn off parts of reports to see how the execution time is affected.</span></span>

### <a name="tools"></a><a name="tools"></a><span data-ttu-id="215b8-189">Eszközök</span><span class="sxs-lookup"><span data-stu-id="215b8-189">Tools</span></span>

#### <a name="execution-time-in-the-action-center"></a><a name="infolog-time"></a><span data-ttu-id="215b8-190">Végrehajtási idő a Műveletközpontban</span><span class="sxs-lookup"><span data-stu-id="215b8-190">Execution time in the Action center</span></span>

<span data-ttu-id="215b8-191">Az ER meg tudja mutatni a konfiguráció végrehajtási idejét a műveletközpontban.</span><span class="sxs-lookup"><span data-stu-id="215b8-191">ER can show the execution time of the configuration in the Action center.</span></span> <span data-ttu-id="215b8-192">Ez a beállítás csak egy adott felhasználóra és egy adott vállalatra, és csak interaktív munkamenetek esetén működik.</span><span class="sxs-lookup"><span data-stu-id="215b8-192">This option works only for a specific user and a specific company, and only for interactive sessions.</span></span> <span data-ttu-id="215b8-193">A funkció elérhetővé tételéhez tegye meg a következő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="215b8-193">To make this feature available, follow these steps.</span></span>

1. <span data-ttu-id="215b8-194">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="215b8-194">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="215b8-195">A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="215b8-195">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="215b8-196">A **Felhasználói paraméterek** párbeszédpanelen állítsa a **Fájlgenerálás idejének megjelenítése** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="215b8-196">In the **User parameters** dialog box, set the **Show file generation time** option to **Yes**.</span></span>

#### <a name="execution-time-in-the-event-log"></a><a name="event-log-time"></a><span data-ttu-id="215b8-197">Végrehajtási idő az eseménynaplóban</span><span class="sxs-lookup"><span data-stu-id="215b8-197">Execution time in the event log</span></span>

1. <span data-ttu-id="215b8-198">Nyissa meg a Windows eseménymegjelenítőt.</span><span class="sxs-lookup"><span data-stu-id="215b8-198">Open Windows Event Viewer.</span></span>
2. <span data-ttu-id="215b8-199">Az **Alkalmazások és szolgáltatások naplóiban** nyissa meg a **Microsoft-Dynamics-ElectronicReporting/Operational** naplót.</span><span class="sxs-lookup"><span data-stu-id="215b8-199">Under **Applications and Services logs**, open **Microsoft-Dynamics-ElectronicReporting/Operational**.</span></span>
3. <span data-ttu-id="215b8-200">Olyan **FormatMapingRun** eseményeket keressen, ahol az **EventID=2**, mivel ezek az események az eltelt időre vonatkozó adatokat tartalmaznak.</span><span class="sxs-lookup"><span data-stu-id="215b8-200">Look for **FormatMapingRun** events where **EventID=2**, because these events contain the information about elapsed time.</span></span>

#### <a name="trace-parser-traces"></a><a name="trace-parser"></a><span data-ttu-id="215b8-201">Trace Parser hívásláncok</span><span class="sxs-lookup"><span data-stu-id="215b8-201">Trace parser traces</span></span> 

<span data-ttu-id="215b8-202">Mivel az ER az X++-ban van megvalósítva, a teljesítmény elemzésére általános X++ eszközök is használhatók.</span><span class="sxs-lookup"><span data-stu-id="215b8-202">Because ER is implemented in X++, you can use common X++ tools to analyze performance.</span></span> <span data-ttu-id="215b8-203">További információ: [Nyomon követés a Trace Parser használatával](../perf-test/trace-trace-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="215b8-203">For more information, see [Take traces by using Trace parser](../perf-test/trace-trace-tutorial.md).</span></span>

<span data-ttu-id="215b8-204">Ez a megközelítés néhány korlátozással jár.</span><span class="sxs-lookup"><span data-stu-id="215b8-204">There are a few limitations to this approach.</span></span> <span data-ttu-id="215b8-205">Mivel az ER egy része C#-ban van megvalósítva, nem minden részlet lesz elérhető.</span><span class="sxs-lookup"><span data-stu-id="215b8-205">Because part of ER is implemented in C#, not all the details will be available.</span></span> <span data-ttu-id="215b8-206">Az adathasználat részletei azonban megtekinthetők.</span><span class="sxs-lookup"><span data-stu-id="215b8-206">However, you can view the data usage details.</span></span> <span data-ttu-id="215b8-207">Ezenkívül a hosszú jelentési futtatásokkal túllépheti a nyomkövetés tárolási korlátait.</span><span class="sxs-lookup"><span data-stu-id="215b8-207">Additionally, long report runs can exceed trace storage limitations.</span></span>

#### <a name="er-traces"></a><a name="electronic-reporting-traces"></a><span data-ttu-id="215b8-208">ER nyomkövetések</span><span class="sxs-lookup"><span data-stu-id="215b8-208">ER traces</span></span>

<span data-ttu-id="215b8-209">Az ER gyűjtheti saját hívásláncait, és rendelkezik a nyomkövetéshez szükséges megjelenítő és elemzési eszközökkel.</span><span class="sxs-lookup"><span data-stu-id="215b8-209">ER can collect its own traces, and it has visualization and analysis tools for those traces.</span></span> <span data-ttu-id="215b8-210">További információkért lásd: [Az ER-formátumok végrehajtásának nyomon követése a teljesítménnyel kapcsolatos problémák elhárítása érdekében](trace-execution-er-troubleshoot-perf.md).</span><span class="sxs-lookup"><span data-stu-id="215b8-210">For more information, see [Trace the execution of ER formats to troubleshoot performance issues](trace-execution-er-troubleshoot-perf.md).</span></span>

#### <a name="perfview"></a><a name="perfview"></a><span data-ttu-id="215b8-211">PerfView</span><span class="sxs-lookup"><span data-stu-id="215b8-211">PerfView</span></span>

<span data-ttu-id="215b8-212">Mivel az X++ és az ER is a .NET platformon van megvalósítva, az általános .NET-eszközök használhatók.</span><span class="sxs-lookup"><span data-stu-id="215b8-212">Because both X++ and ER are implemented on top of the .NET platform, you can use common .NET tools.</span></span> <span data-ttu-id="215b8-213">Használhatja például az ingyenes [PerfView](https://github.com/Microsoft/perfview) eszközt.</span><span class="sxs-lookup"><span data-stu-id="215b8-213">For example, you can use the free [PerfView](https://github.com/Microsoft/perfview) tool.</span></span>

<span data-ttu-id="215b8-214">A parancssorból is lehet adatokat gyűjteni.</span><span class="sxs-lookup"><span data-stu-id="215b8-214">You can also collect data from the command line.</span></span> <span data-ttu-id="215b8-215">A következő Windows PowerShell-parancsfájl például addig gyűjti a végrehajtási időt, amíg a számítógépen le nincs állítva valamilyen formátum-végrehajtás.</span><span class="sxs-lookup"><span data-stu-id="215b8-215">For example, the following Windows PowerShell script collects the execution time until any format execution is stopped on the machine.</span></span>

```powershell
c:\programs\PerfView collect "e:\traces\$(date -format "ddMMyyyy_hhmm").etl" `
    -CircularMB:20000 -ThreadTime `
    -NoNGenRundown `
    -StopOnEtwEvent:Microsoft-Dynamics-ElectronicReporting/FormatMappingRun/Stop
```

<span data-ttu-id="215b8-216">Ez a megközelítés néhány korlátozással jár.</span><span class="sxs-lookup"><span data-stu-id="215b8-216">There are a few limitations to this approach.</span></span> <span data-ttu-id="215b8-217">Rendszergazdai hozzáférés szükséges a számítógéphez.</span><span class="sxs-lookup"><span data-stu-id="215b8-217">You must have administrative access to the machine.</span></span> <span data-ttu-id="215b8-218">Ezenkívül tapasztalt fejlesztőnek kell lennie, mert itt elég meredek a tanulási görbe.</span><span class="sxs-lookup"><span data-stu-id="215b8-218">Additionally, you must be an experienced developer, because there is a steep learning curve.</span></span>

### <a name="making-changes"></a><a name="making-changes"></a><span data-ttu-id="215b8-219">Változások alkalmazása</span><span class="sxs-lookup"><span data-stu-id="215b8-219">Making changes</span></span>

#### <a name="use-caching"></a><a name="use-caching"></a><span data-ttu-id="215b8-220">Gyorsítótárazás használata</span><span class="sxs-lookup"><span data-stu-id="215b8-220">Use caching</span></span>

<span data-ttu-id="215b8-221">Bár a gyorsítótárazás csökkenti az adatok újraolvasásához szükséges időt, memóriát fogyaszt.</span><span class="sxs-lookup"><span data-stu-id="215b8-221">Although caching reduces the amount of time that is required to fetch data again, it costs memory.</span></span> <span data-ttu-id="215b8-222">Gyorsítótárazás használata olyan esetekben, amikor a beolvasott adatok mennyisége nem túl nagy.</span><span class="sxs-lookup"><span data-stu-id="215b8-222">Use caching in cases where the amount of fetched data isn't very large.</span></span> <span data-ttu-id="215b8-223">A további tudnivalókat és a gyorsítótárazás használatát bemutató példát lásd a [modellleképezés javítása a végrehajtási nyomkövetés adatai alapján](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace) részben.</span><span class="sxs-lookup"><span data-stu-id="215b8-223">For more information and an example that shows how to use caching, see [Improve the model mapping based on information from the execution trace](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace).</span></span>

#### <a name="use-a-cached-parameterized-calculated-field"></a><a name="cached-parameterized"></a><span data-ttu-id="215b8-224">Gyorsítótárazott, paraméterezett számított mező használata</span><span class="sxs-lookup"><span data-stu-id="215b8-224">Use a cached, parameterized calculated field</span></span>

<span data-ttu-id="215b8-225">Időnként többször is meg kell keresni az értékeket.</span><span class="sxs-lookup"><span data-stu-id="215b8-225">Sometimes, values must be looked up repeatedly.</span></span> <span data-ttu-id="215b8-226">Ilyen lehet például a fióknév vagy fiókszám.</span><span class="sxs-lookup"><span data-stu-id="215b8-226">Examples include account names and account numbers.</span></span> <span data-ttu-id="215b8-227">Az idő megtakaraítása érdekében létrehozhat egy számított mezőt, amely a legfelső szinten paraméterekkel rendelkezik, majd hozzáadhatja a mezőt a gyorsítótárhoz.</span><span class="sxs-lookup"><span data-stu-id="215b8-227">To help save time, you can create a calculated field that has parameters on the top level, and then add the field to the cache.</span></span>

<span data-ttu-id="215b8-228">Javasoljuk, hogy ezt a megközelítést csak akkor használja, ha a gyorsítótárazott adatok mérete kicsi.</span><span class="sxs-lookup"><span data-stu-id="215b8-228">We recommend that you use this approach only when the size of the cached data is small.</span></span> <span data-ttu-id="215b8-229">További információ: [ER-megoldások teljesítményének javítása paraméterezett SZÁMÍTOTT MEZŐ-adatforrások](er-calculated-field-ds-performance.md) hozzáadásával.</span><span class="sxs-lookup"><span data-stu-id="215b8-229">For more information, see [Improve the performance of ER solutions by adding parameterized CALCULATED FIELD data sources](er-calculated-field-ds-performance.md).</span></span>

#### <a name="use-a-join-data-source"></a><a name="use-join-datasource"></a><span data-ttu-id="215b8-230">Egy JOIN adatforrás használata</span><span class="sxs-lookup"><span data-stu-id="215b8-230">Use a JOIN data source</span></span>

<span data-ttu-id="215b8-231">Az **ÖSSZEKAPCSOLÁS** adatforrás lehetővé teszi több kapcsolódó rekord beolvasását egyetlen lekérdezéssel.</span><span class="sxs-lookup"><span data-stu-id="215b8-231">A **JOIN** data source enables several connected records to be fetched by one query.</span></span> <span data-ttu-id="215b8-232">Nem kell külön lekérdezést használni minden egyes kapcsolódó rekord beolvasásakor.</span><span class="sxs-lookup"><span data-stu-id="215b8-232">A separate query doesn't have to be used to fetch each connected record.</span></span> <span data-ttu-id="215b8-233">Ha például 1000 sora van, és kapcsolat szerint olvassa be az egyes sorokat, akkor 1001 lekérdezése lesz (= 1000 + 1).</span><span class="sxs-lookup"><span data-stu-id="215b8-233">For example, if you have 1,000 lines, and you fetch item data for each line by relation, you will have 1,001 queries (= 1,000 + 1).</span></span> <span data-ttu-id="215b8-234">Egy **ÖSSZEKAPCSOLÁS** adatforrás használata esetén csak egy lekérdezést fog használni ugyanazoknak az adatoknak a beolvasására.</span><span class="sxs-lookup"><span data-stu-id="215b8-234">If you use a **JOIN** data source, you will use only one query to fetch the same data.</span></span> <span data-ttu-id="215b8-235">További információ [Több alkalmazási táblából származó adatok lekéréséhez használja a JOIN adatforrásokat az ER modell-leképezésekben](er-join-data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="215b8-235">For more information, see [Use JOIN data sources in ER model mappings to get data from multiple application tables](er-join-data-sources.md).</span></span>

#### <a name="use-the-filter-function-instead-of-the-where-function"></a><a name="filter"></a><span data-ttu-id="215b8-236">Használja a FILTER függvényt a WHERE függvény helyett</span><span class="sxs-lookup"><span data-stu-id="215b8-236">Use the FILTER function instead of the WHERE function</span></span>

<span data-ttu-id="215b8-237">A **[FILTER](er-functions-list-filter.md)** függvény feltételeket futtat az SQL Server kiszolgálón, míg a **WHERE** függvény minden adatot beolvas a listából, egyszerre egy rekordot beolvasva és alkalmazza a feltételt minden rekordra.</span><span class="sxs-lookup"><span data-stu-id="215b8-237">The **[FILTER](er-functions-list-filter.md)** function runs conditions on SQL Server, whereas the **WHERE** function fetches all data from the list, one record at a time, and applies the condition for each record.</span></span> <span data-ttu-id="215b8-238">Például ki szeretne választani egy rekordot 1000 rekordból.</span><span class="sxs-lookup"><span data-stu-id="215b8-238">For example, you want to select one record out of 1,000 records.</span></span> <span data-ttu-id="215b8-239">Ha a **WHERE** függvényt használja, mind az 1000 rekord be lesz olvasva.</span><span class="sxs-lookup"><span data-stu-id="215b8-239">If you use **WHERE**, all 1,000 records will be fetched.</span></span> <span data-ttu-id="215b8-240">A **FILTER** használata esetén viszont pontosan egy rekordot lesz beolvasva.</span><span class="sxs-lookup"><span data-stu-id="215b8-240">However, if you use **FILTER**, exactly one record will be fetched.</span></span> <span data-ttu-id="215b8-241">A **FILTER** az adatbázis oldalán is használhat indexeket.</span><span class="sxs-lookup"><span data-stu-id="215b8-241">**FILTER** can also use indexes on the database side.</span></span>

#### <a name="using-collected-data-functions-or-an-accumulated-data-data-source"></a><a name="collected-data"></a><span data-ttu-id="215b8-242">Összegyűjtött adatfüggvények vagy összesített adatforrás használata</span><span class="sxs-lookup"><span data-stu-id="215b8-242">Using collected data functions or an accumulated data data source</span></span>

<span data-ttu-id="215b8-243">Ha a konfiguráció rendelkezik egy *csoportosítás* összetevővel, amely összegzi a korábban lekért adatokat jelentés szerint, akkor az összetevő újra be fogja olvasni az összes adatot.</span><span class="sxs-lookup"><span data-stu-id="215b8-243">If your configuration has a *group by* component that summarizes previously fetched data by report, the component will fetch all the data again.</span></span> <span data-ttu-id="215b8-244">Az összegyűjtött adatfüggvények használatával az ER számára lehetővé teszi az adatok összegyűjtését az első beolvasás során.</span><span class="sxs-lookup"><span data-stu-id="215b8-244">By using collected data functions, you enable ER to accumulate data during the first fetch.</span></span> <span data-ttu-id="215b8-245">A további tudnivalókat lásd: [ER formátum konfigurálása számláláshoz és összegzéshez](tasks/er-format-counting-summing-2.md).</span><span class="sxs-lookup"><span data-stu-id="215b8-245">For more information, see [ER Configure format to do counting and summing](tasks/er-format-counting-summing-2.md).</span></span>

#### <a name="rewrite-parts-of-the-configuration-in-x"></a><span data-ttu-id="215b8-246">A konfiguráció részeinek felülírása X++-ban</span><span class="sxs-lookup"><span data-stu-id="215b8-246">Rewrite parts of the configuration in X++</span></span>

<span data-ttu-id="215b8-247">Az ER támogatja a táblák és osztályok metódusának ( például a bővítményeknek) a meghívását.</span><span class="sxs-lookup"><span data-stu-id="215b8-247">ER supports calling methods of tables and classes, including extensions.</span></span> <span data-ttu-id="215b8-248">A jobb teljesítmény érdekében célszerű átírni a modellleképezés egyes részeit az X++ kódban.</span><span class="sxs-lookup"><span data-stu-id="215b8-248">Consider rewriting parts of the model mapping in X++ to help improve performance.</span></span>

<span data-ttu-id="215b8-249">Az ER a következő forrásokból használhat adatokat:</span><span class="sxs-lookup"><span data-stu-id="215b8-249">ER can consume data from the following sources:</span></span>

- <span data-ttu-id="215b8-250">Osztályok (**objektum** és **osztály** adatforrások)</span><span class="sxs-lookup"><span data-stu-id="215b8-250">Classes (**object** and **class** data sources)</span></span>
- <span data-ttu-id="215b8-251">Táblák (**tábla** és **táblarekord** adatforrások)</span><span class="sxs-lookup"><span data-stu-id="215b8-251">Tables (**table** and **table records** data sources)</span></span>

<span data-ttu-id="215b8-252">Az [ER API](er-apis-app73.md#how-to-access-internal-x-objects-by-using-erobjectsfactory) segítségével az előkalkulált adatokat is küldheti a hívó kódból.</span><span class="sxs-lookup"><span data-stu-id="215b8-252">The [ER API](er-apis-app73.md#how-to-access-internal-x-objects-by-using-erobjectsfactory) also provides a way to send precalculated data from the calling code.</span></span> <span data-ttu-id="215b8-253">Az alkalmazáscsomag számos példát tartalmaz erre a megközelítésre.</span><span class="sxs-lookup"><span data-stu-id="215b8-253">The application suite contains numerous examples of this approach.</span></span>
