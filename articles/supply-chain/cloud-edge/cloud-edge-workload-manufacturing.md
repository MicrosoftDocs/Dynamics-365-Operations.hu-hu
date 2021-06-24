---
title: Gyártásvégrehajtási munkaterhelések felhőalapú és peremhálózati skálázási egységekhez
description: Ez a témakör ismerteti, hogyan működnek a gyártási végrehajtási számítási feladatok felhő- és peremhálózati skálázási egységekkel.
author: cabeln
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: cabeln
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 9cd7dd8b9241171bdfdb3cc1379211a2fe99bbe1
ms.sourcegitcommit: 8d50c905a0c9d4347519549b587bdebab8ffc628
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2021
ms.locfileid: "6183996"
---
# <a name="manufacturing-execution-workloads-for-cloud-and-edge-scale-units"></a><span data-ttu-id="c1b63-103">Gyártási végrehajtás munkaterhelései felhőalapú és peremhálózat-lépték szerinti egységekhez</span><span class="sxs-lookup"><span data-stu-id="c1b63-103">Manufacturing execution workloads for cloud and edge scale units</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> <span data-ttu-id="c1b63-104">A gyártásvégrehajtási munkaterhelés elérhető az előzetes verzióban az adott időpont szerint.</span><span class="sxs-lookup"><span data-stu-id="c1b63-104">The manufacturing execution workload is available in preview at this point in time.</span></span>
> <span data-ttu-id="c1b63-105">Néhány üzleti funkció nem teljes mértékben támogatott a nyilvános előzetes verzióban, ha számítási feladatokat skálázási egységeken használja.</span><span class="sxs-lookup"><span data-stu-id="c1b63-105">Some business functionality isn't fully supported in the public preview when workload scale units are used.</span></span>

<span data-ttu-id="c1b63-106">A gyártásvégrehajtásban a skálázási egységek a következő lehetőségeket biztosítják:</span><span class="sxs-lookup"><span data-stu-id="c1b63-106">In manufacturing execution, scale units deliver the following capabilities:</span></span>

- <span data-ttu-id="c1b63-107">A gépkezelők és az üzemirányítók hozzáférhetnek az üzemeltetési termelési tervhez.</span><span class="sxs-lookup"><span data-stu-id="c1b63-107">Machine operators and shop floor supervisors can access the operational production plan.</span></span>
- <span data-ttu-id="c1b63-108">A gépkezelők diszkrét és folyamatgyártási feladatok futtatásával naprakészen tarthatják a tervet.</span><span class="sxs-lookup"><span data-stu-id="c1b63-108">Machine operators can keep the plan up to date by running discrete and process manufacturing jobs.</span></span>
- <span data-ttu-id="c1b63-109">Az üzemvezető módosíthatja az üzemeltetési tervet.</span><span class="sxs-lookup"><span data-stu-id="c1b63-109">The shop floor supervisor can adjust the operational plan.</span></span>
- <span data-ttu-id="c1b63-110">A dolgozók hozzáférhetnek a munkaidőhöz és a jelenléthez a peremhálózati érkezéskori és távozáskori blokkoláshoz a megfelelő dolgozói fizetésszámítás biztosítása érdekében.</span><span class="sxs-lookup"><span data-stu-id="c1b63-110">Workers can access time and attendance for clock-in and clock-out on the edge, to ensure correct worker pay calculation.</span></span>

<span data-ttu-id="c1b63-111">Ez a témakör ismerteti, hogyan működnek a gyártási végrehajtási számítási feladatok felhő- és peremhálózati skálázási egységekkel.</span><span class="sxs-lookup"><span data-stu-id="c1b63-111">This topic describes how manufacturing execution workloads work with cloud and edge scale units.</span></span>

## <a name="the-manufacturing-lifecycle"></a><span data-ttu-id="c1b63-112">A gyártási életciklus</span><span class="sxs-lookup"><span data-stu-id="c1b63-112">The manufacturing lifecycle</span></span>

<span data-ttu-id="c1b63-113">Ahogy az alábbi ábra is mutatja, a gyártási életciklus három fázisra oszlik: *Tervezés*, *Végrehajtás* és *Véglegesítés*.</span><span class="sxs-lookup"><span data-stu-id="c1b63-113">As the following illustration shows, the manufacturing lifecycle is divided into three phases: *Plan*, *Execute*, and *Finalize*.</span></span>

<span data-ttu-id="c1b63-114">[![Gyártási végrehajtási fázisok egyetlen környezet használata során](media/mes-phases.png "Gyártási végrehajtási fázisok egyetlen környezet használata során")](media/mes-phases-large.png)</span><span class="sxs-lookup"><span data-stu-id="c1b63-114">[![Manufacturing execution phases when a single environment is used](media/mes-phases.png "Manufacturing execution phases when a single environment is used")](media/mes-phases-large.png)</span></span>

<span data-ttu-id="c1b63-115">A _Tervezés_ fázis tartalmazza a termékdefiníciót, a tervezést, a rendelés létrehozását és ütemezését, valamint a kiadást.</span><span class="sxs-lookup"><span data-stu-id="c1b63-115">The _Plan_ phase includes product definition, planning, order creation and scheduling, and release.</span></span> <span data-ttu-id="c1b63-116">A kiadási lépés a _Terv_ fázisról a _Végrehajtás_ fázisra való áttérést jelzi.</span><span class="sxs-lookup"><span data-stu-id="c1b63-116">The release step indicates the transition from the _Plan_ phase to the _Execute_ phase.</span></span> <span data-ttu-id="c1b63-117">A termelési rendelés kiadásakor a termelési rendelési feladatok láthatók lesznek a termelési szinten, és készen állnak a végrehajtásra.</span><span class="sxs-lookup"><span data-stu-id="c1b63-117">When a production order is released, the production order jobs will be visible on the production floor and ready for execution.</span></span>

<span data-ttu-id="c1b63-118">Ha egy termelési feladat befejezettként van megjelölve, a _Végrehajtás_ fázisról a _Véglegesítés_ fázisra kerül.</span><span class="sxs-lookup"><span data-stu-id="c1b63-118">When a production job is marked as completed, it moves from the _Execute_ phase to the _Finalize_ phase.</span></span> <span data-ttu-id="c1b63-119">A _Véglegesítés_ fázisban a *Végrehajtás* fázis regisztrációi egy jóváhagyási munkafolyamaton mennek keresztül, ahol kiszámították, jóváhagyták és átvitték őket.</span><span class="sxs-lookup"><span data-stu-id="c1b63-119">In the _Finalize_ phase, the registrations from the *Execute* phase go through an approval workflow, where they are calculated, approved, and transferred.</span></span> <span data-ttu-id="c1b63-120">Ezen a ponton a gyártási rendelés befejeződött.</span><span class="sxs-lookup"><span data-stu-id="c1b63-120">At that point, the production order is completed.</span></span> <span data-ttu-id="c1b63-121">Ezért a munkavállalók fizetésének alapja létrejön.</span><span class="sxs-lookup"><span data-stu-id="c1b63-121">Therefore, the basis for the workers' pay is generated.</span></span>

## <a name="splitting-the-execute-phase-into-a-separate-workload"></a><span data-ttu-id="c1b63-122">A Végrehajtás fázis felosztása külön munkaterhelésre</span><span class="sxs-lookup"><span data-stu-id="c1b63-122">Splitting the Execute phase into a separate workload</span></span>

<span data-ttu-id="c1b63-123">Ahogy a következő ábra is mutatja, skálázási egységek használata esetén a _Végrehajtás_ fázis külön számítási feladatként van felosztva.</span><span class="sxs-lookup"><span data-stu-id="c1b63-123">As the following illustration shows, when scale units are used, the _Execute_ phase is split out as a separate workload.</span></span>

<span data-ttu-id="c1b63-124">[![Gyártási végrehajtási fázisok skálázási egységek használata esetén](media/mes-phases-workloads.png "Gyártási végrehajtási fázisok skálázási egységek használata esetén")](media/mes-phases-workloads-large.png)</span><span class="sxs-lookup"><span data-stu-id="c1b63-124">[![Manufacturing execution phases when scale units are used](media/mes-phases-workloads.png "Manufacturing execution phases when scale units are used")](media/mes-phases-workloads-large.png)</span></span>

<span data-ttu-id="c1b63-125">A modell most egy egypéldányos telepítésből egy olyan modellre kerül, amely a központon és a skálázási egységeken alapul.</span><span class="sxs-lookup"><span data-stu-id="c1b63-125">The model now goes from a single-instance installation to a model that is based on the hub and scale units.</span></span> <span data-ttu-id="c1b63-126">A _Tervezés_ és a _Véglegesítés_ fázisok háttérirodai műveletekként futnak a központban, és a gyártási végrehajtási számítási feladat a skálázási egységeken fut.</span><span class="sxs-lookup"><span data-stu-id="c1b63-126">The _Plan_ and _Finalize_ phases run as back-office operations on the hub, and the manufacturing execution workload runs on the scale units.</span></span> <span data-ttu-id="c1b63-127">Az adatok átvitele aszinkron módon történik a központ és a skálázási egységek között.</span><span class="sxs-lookup"><span data-stu-id="c1b63-127">Data is transferred asynchronously between the hub and scale units.</span></span>

<span data-ttu-id="c1b63-128">Amikor egy termelési rendelést kiadnak a központban, a termelési feladatok feldolgozásához szükséges összes adat átkerül a skálázási egységbe.</span><span class="sxs-lookup"><span data-stu-id="c1b63-128">When a production order is released on the hub, all data that is required to process production jobs is transferred to the scale unit.</span></span> <span data-ttu-id="c1b63-129">Ezek az adatok tartalmazzák a termelési rendeléseket, a termelési útvonalakat, az anyagjegyzékeket és a termékeket.</span><span class="sxs-lookup"><span data-stu-id="c1b63-129">This data includes production orders, production routes, bills of materials, and products.</span></span> <span data-ttu-id="c1b63-130">A termelési rendeléshez nem kapcsolódó adatok (például közvetett tevékenységek, távolléti kódok és termelési paraméterek) szintén átkerülnek a központból a skálázási egységre.</span><span class="sxs-lookup"><span data-stu-id="c1b63-130">Data that isn't related to a production order (such as indirect activities, absence codes, and production parameters) is also transferred from the hub to the scale unit.</span></span> <span data-ttu-id="c1b63-131">Rendszerint a központból származó és a skálázási egységbe átvitt adatok csak a központon hozhatók létre vagy frissíthetők.</span><span class="sxs-lookup"><span data-stu-id="c1b63-131">As a rule, data that originates from the hub and that is transferred to the scale unit can be created or updated only on the hub.</span></span> <span data-ttu-id="c1b63-132">Például egy új távolléti kód vagy közvetett tevékenység nem hozható létre a skálázási egységben, amely csak a regisztrációhoz használható.</span><span class="sxs-lookup"><span data-stu-id="c1b63-132">For example, a new absence code or indirect activity can't be created on the scale unit&mdash;they can be used only for registration.</span></span> <span data-ttu-id="c1b63-133">A skálázási egységen a végrehajtás során végzett regisztrációk ezután átkerülnek a központba, ahol a munkaidő- és jelenlét-jóváhagyás, a készlet és a pénzügyi frissítések feldolgozása történik.</span><span class="sxs-lookup"><span data-stu-id="c1b63-133">The registrations that are made on the scale unit during execution are then transferred to the hub, where time and attendance approval, inventory, and financial updates are processed.</span></span>

## <a name="manufacturing-execution-tasks-that-can-be-run-on-workloads"></a><span data-ttu-id="c1b63-134">Számítási feladatokon futtatható gyártási végrehajtási feladatok</span><span class="sxs-lookup"><span data-stu-id="c1b63-134">Manufacturing execution tasks that can be run on workloads</span></span>

<span data-ttu-id="c1b63-135">A következő gyártási végrehajtási feladatok jelenleg futtathatók a számítási feladatokon, ha skálázási egységeket használnak:</span><span class="sxs-lookup"><span data-stu-id="c1b63-135">The following manufacturing execution tasks can currently be run on workloads when scale units are used:</span></span>

- <span data-ttu-id="c1b63-136">Érkezéskori blokkolás, bejelentkezés, távozáskori blokkolás és távollét</span><span class="sxs-lookup"><span data-stu-id="c1b63-136">Clock-in, log-in, clock-out, and absence</span></span>
- <span data-ttu-id="c1b63-137">Feladat kezdete</span><span class="sxs-lookup"><span data-stu-id="c1b63-137">Start job</span></span>
- <span data-ttu-id="c1b63-138">Csomagfeladatok</span><span class="sxs-lookup"><span data-stu-id="c1b63-138">Bundle jobs</span></span>
- <span data-ttu-id="c1b63-139">Jelentés az előrehaladásról</span><span class="sxs-lookup"><span data-stu-id="c1b63-139">Report progress</span></span>
- <span data-ttu-id="c1b63-140">Selejt jelentése</span><span class="sxs-lookup"><span data-stu-id="c1b63-140">Report scrap</span></span>
- <span data-ttu-id="c1b63-141">Közvetett tevékenység</span><span class="sxs-lookup"><span data-stu-id="c1b63-141">Indirect activity</span></span>
- <span data-ttu-id="c1b63-142">Szünet</span><span class="sxs-lookup"><span data-stu-id="c1b63-142">Break</span></span>
- <span data-ttu-id="c1b63-143">Készként jelentés és berakodása (a raktár végrehajtási terhelésének a skálázási egységen való futtatására is szükség van, lásd még a [Készként jelentés és betárolás skálázási egységen](#RAF))</span><span class="sxs-lookup"><span data-stu-id="c1b63-143">Report as finished and putaway (requires that you also run the warehouse execution workload on your scale unit, see also [Report as finished and putaway on a scale unit](#RAF))</span></span>

## <a name="working-with-manufacturing-execution-workloads-on-the-hub"></a><span data-ttu-id="c1b63-144">Gyártási végrehajtási számítási feladatok használata a központban</span><span class="sxs-lookup"><span data-stu-id="c1b63-144">Working with manufacturing execution workloads on the hub</span></span>

<span data-ttu-id="c1b63-145">Általában a gyártási végrehajtási számítási feladatok futtatásához szükséges folyamatok automatikusan futnak, hogy a központ és az összes skálázási egység szükség szerint szinkronban maradjon.</span><span class="sxs-lookup"><span data-stu-id="c1b63-145">Usually, the processes that are required to run manufacturing execution workloads run automatically to keep the hub and all the scale units in sync, as needed.</span></span> <span data-ttu-id="c1b63-146">Ha azonban problémája van, manuálisan aktiválhatja a számítási feladatokból kapott nyers regisztrációk feldolgozását, és/vagy ellenőrizheti a regisztrációs feldolgozási naplót.</span><span class="sxs-lookup"><span data-stu-id="c1b63-146">However, if you're having trouble, you can manually trigger the processing of raw registrations that are received from workloads and/or check the registration processing log.</span></span>

### <a name="manually-process-raw-registrations"></a><span data-ttu-id="c1b63-147">Nyers regisztrációk manuális feldolgozása</span><span class="sxs-lookup"><span data-stu-id="c1b63-147">Manually process raw registrations</span></span>

<span data-ttu-id="c1b63-148">A Supply Chain Management szolgáltatásban a kötegelt feladatok automatikusan futnak a számítási feladatokból beérkezett összes regisztráció feldolgozásához.</span><span class="sxs-lookup"><span data-stu-id="c1b63-148">A batch job in Supply Chain Management runs automatically to process all the registrations that have been received from the workloads.</span></span> <span data-ttu-id="c1b63-149">Ez a feladat létrehozza a szükséges termelési naplókat és naplóbejegyzéseket, amikor a regisztrációfeldolgozás a számítási feladatokon végzett feladathoz történik.</span><span class="sxs-lookup"><span data-stu-id="c1b63-149">This job creates the required production journals and logbook entries when a registration is processed for a completed job on the workload.</span></span>

<span data-ttu-id="c1b63-150">Bár a feladat általában automatikusan fut, manuálisan bármikor futtathatja, ha bejelentkezik a központba, és a **Termelésvezérlés \> Időszakos feladatok  \> Háttérirodai munkaterhelés-kezelés \> Nyers regisztrációk feldolgozása** pontra lép.</span><span class="sxs-lookup"><span data-stu-id="c1b63-150">Although the job usually runs automatically, you can run it manually at any time by signing in to the hub and going to **Production control \> Periodic tasks \> Backoffice workload management \> Process raw registrations**.</span></span>

### <a name="check-the-raw-registration-processing-log"></a><span data-ttu-id="c1b63-151">A nyers regisztrációs feldolgozási napló ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="c1b63-151">Check the raw registration processing log</span></span>

<span data-ttu-id="c1b63-152">A regisztrációs feldolgozási napló áttekintéséhez jelentkezzen be a központba, és lépjen a **Termelésvezérlés \> Időszakos feladatok \> Háttérirodai munkaterhelés-kezelés \> Nyers regisztrációs feldolgozási napló** pontba.</span><span class="sxs-lookup"><span data-stu-id="c1b63-152">To review the registration processing log, sign in to the hub, and go to **Production control \> Periodic tasks \> Backoffice workload management \> Raw registration processing log**.</span></span> <span data-ttu-id="c1b63-153">A **Nyers regisztrációs feldolgozási napló** lap a feldolgozott nyers regisztrációk listáját és az egyes regisztrációk állapotát jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="c1b63-153">The **Raw registration processing log** page shows a list of processed raw registrations and the status of each registration.</span></span>

<span data-ttu-id="c1b63-154">![A nyers regisztrációs feldolgozási napló oldala](media/mes-processing-log.png "A nyers regisztrációs feldolgozási napló oldala")</span><span class="sxs-lookup"><span data-stu-id="c1b63-154">![Raw registration processing log page](media/mes-processing-log.png "Raw registration processing log page")</span></span>

<span data-ttu-id="c1b63-155">A lista bármely regisztrációján úgy dolgozhat, hogy kijelöli, majd a műveletpanelen az alábbi gombok egyikét választja:</span><span class="sxs-lookup"><span data-stu-id="c1b63-155">You can work on any registration in the list by selecting it and then selecting one of the following buttons on the Action Pane:</span></span>

- <span data-ttu-id="c1b63-156">**Feldolgozás** – A kijelölt regisztráció manuális feldolgozása.</span><span class="sxs-lookup"><span data-stu-id="c1b63-156">**Process** – Manually process the selected registration.</span></span> <span data-ttu-id="c1b63-157">Ez a művelet akkor lehet hasznos, ha a _Nyers regisztrációk feldolgozása_ feladat nem fut, vagy ha nem sikerült.</span><span class="sxs-lookup"><span data-stu-id="c1b63-157">This action can be useful if the _Process raw registrations_ job hasn't run, or if it failed.</span></span>
- <span data-ttu-id="c1b63-158">**Megszakítás** – A kijelölt regisztráció visszavonása.</span><span class="sxs-lookup"><span data-stu-id="c1b63-158">**Cancel** – Cancel the selected registration.</span></span>

## <a name="working-with-manufacturing-execution-workloads-on-a-scale-unit"></a><span data-ttu-id="c1b63-159">Gyártási végrehajtási számítási feladatok használata a skálázási egységen</span><span class="sxs-lookup"><span data-stu-id="c1b63-159">Working with manufacturing execution workloads on a scale unit</span></span>

<span data-ttu-id="c1b63-160">Általában a gyártási végrehajtási számítási feladatok futtatásához szükséges folyamatok automatikusan futnak, hogy a központ és az összes skálázási egység szükség szerint szinkronban maradjon.</span><span class="sxs-lookup"><span data-stu-id="c1b63-160">Usually, the processes that are required to run manufacturing execution workloads run automatically to keep the hub and all the scale units in sync, as needed.</span></span> <span data-ttu-id="c1b63-161">Ha azonban problémája van, ellenőrizheti a skálázási egységen feldolgozott rendelések előzményeit, vagy manuálisan futtathatja a _Gyártási központból a skálázási egységbe irányuló üzenetfeldolgozó_ feladatot.</span><span class="sxs-lookup"><span data-stu-id="c1b63-161">However, if you're having trouble, you can check the history of orders that have been processed on a scale unit or manually run the _Manufacturing hub to scale unit message processor_ job.</span></span>

### <a name="view-the-history-of-manufacturing-jobs-that-have-been-processed-on-a-scale-unit"></a><span data-ttu-id="c1b63-162">A skálázási egységen feldolgozott gyártási feladatok előzményeinek megtekintése</span><span class="sxs-lookup"><span data-stu-id="c1b63-162">View the history of manufacturing jobs that have been processed on a scale unit</span></span>

<span data-ttu-id="c1b63-163">A skálázási egységen feldolgozott gyártási feladatok előzményeinek áttekintéséhez jelentkezzen be a skálázási egység gépébe, és lépjen a **Termelésvezérlés \> Időszakos feladatok \> Háttérirodai számítási feladatok kezelése \> Gyártási feladatok feldolgozási előzményei** pontra.</span><span class="sxs-lookup"><span data-stu-id="c1b63-163">To review the history of manufacturing jobs that have been processed on a scale unit, sign in to the scale unit machine, and go to **Production control \> Periodic tasks \> Backoffice workload management \> Manufacturing jobs processing history**.</span></span> <span data-ttu-id="c1b63-164">A **Gyártási feladatok feldolgozási előzményei** lap a skálázási egység termelési rendeléseinek feldolgozási előzményeit jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="c1b63-164">The **Manufacturing jobs processing history** page shows the processing history of the production orders on the scale unit.</span></span> <span data-ttu-id="c1b63-165">A lista bármely termelési rendelésén úgy dolgozhat, hogy kijelöli, majd a műveletpanelen az alábbi gombok egyikét választja:</span><span class="sxs-lookup"><span data-stu-id="c1b63-165">You can work on any production order in the list by selecting it and then selecting one of the following buttons on the Action Pane:</span></span>

- <span data-ttu-id="c1b63-166">**Feldolgozás** – A kijelölt termelési rendelés manuális feldolgozása.</span><span class="sxs-lookup"><span data-stu-id="c1b63-166">**Process** – Manually process the selected production order.</span></span>
- <span data-ttu-id="c1b63-167">**Megszakítás** – A kijelölt termelési rendelés visszavonása.</span><span class="sxs-lookup"><span data-stu-id="c1b63-167">**Cancel** – Cancel the selected production order.</span></span>

### <a name="manufacturing-hub-to-scale-unit-message-processor-job"></a><span data-ttu-id="c1b63-168">Gyártási központból a skálázási egységbe irányuló üzenetfeldolgozó</span><span class="sxs-lookup"><span data-stu-id="c1b63-168">Manufacturing hub to scale unit message processor job</span></span>

<span data-ttu-id="c1b63-169">A _Gyártási központból a skálázási egységbe irányuló üzenetfeldolgozó_ feladat feldolgozza a központból a skálázási egységbe érkező adatokat.</span><span class="sxs-lookup"><span data-stu-id="c1b63-169">The _Manufacturing hub to scale unit message processor_ job processes data from the hub to the scale unit.</span></span> <span data-ttu-id="c1b63-170">Ez a feladat automatikusan elindul, amikor a gyártási végrehajtási számítási feladat telepítve van.</span><span class="sxs-lookup"><span data-stu-id="c1b63-170">This job is automatically started when the manufacturing execution workload is deployed.</span></span> <span data-ttu-id="c1b63-171">Azonban manuálisan is futtathatja, ha a **Termelésvezérlés \> Időszakos feladatok \> Háttérirodai munkaterhelés-kezelés \> Gyártási központból a skálázási egységbe irányuló üzenetfeldolgozó** pontba lép.</span><span class="sxs-lookup"><span data-stu-id="c1b63-171">However, you can run it manually at any time by going to **Production control \> Periodic tasks \> Backoffice workload management \> Manufacturing hub to scale unit message processor**.</span></span>

<a name="RAF"></a>

## <a name="report-as-finished-and-putaway-on-a-scale-unit"></a><span data-ttu-id="c1b63-172">Készként jelentés és berakodás egy skálaegységre</span><span class="sxs-lookup"><span data-stu-id="c1b63-172">Report as finished and putaway on a scale unit</span></span>

<!-- KFM: 
This section describes how to enable the abilities to report as finished and then putaway finished items when you are using to a scale unit.

### Enable and use report as finished and putaway on a scale unit -->

<span data-ttu-id="c1b63-173">A jelenlegi kiadásban a készre jelentés és betárolási műveletek (késztermékekhez, társtermékekhez és melléktermékekhez) támogatva vannak a [raktári végrehajtási terheléshez](cloud-edge-workload-warehousing.md) (nem a gyártási végrehajtási terheléshez).</span><span class="sxs-lookup"><span data-stu-id="c1b63-173">In the current release, report as finished and putaway operations (for finished products, co-products, and by-products) are supported by the [warehouse execution workload](cloud-edge-workload-warehousing.md) (not the manufacturing execution workload).</span></span> <span data-ttu-id="c1b63-174">Ennek megfelelően ahhoz, hogy egy skálaegységhez kapcsolódva használni tudja ezt a funkciót, a következőket kell tenni:</span><span class="sxs-lookup"><span data-stu-id="c1b63-174">Therefore, to use this functionality when connected to a scale unit, you must do the following:</span></span>

- <span data-ttu-id="c1b63-175">A raktári végrehajtási számítási feladatot és a gyártási végrehajtási számítási feladatot is telepítse a skálaegységre.</span><span class="sxs-lookup"><span data-stu-id="c1b63-175">Install both the warehouse execution workload and the manufacturing execution workload on your scale unit.</span></span>
- <span data-ttu-id="c1b63-176">A Warehouse Management mobilalkalmazás használatával készként jelenthető, és feldolgozható a berakodási munka.</span><span class="sxs-lookup"><span data-stu-id="c1b63-176">Use the Warehouse Management mobile app to report as finished and process the putaway work.</span></span> <span data-ttu-id="c1b63-177">A termelési üzem végrehajtási felülete jelenleg nem támogatja ezeket a folyamatokat.</span><span class="sxs-lookup"><span data-stu-id="c1b63-177">The production floor execution interface does not currently support these processes.</span></span>

<!-- KFM: API details needed

### Customize report as finished and putaway functionality

 -->

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
