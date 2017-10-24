---
title: "Lean manufacturing (áttekintés)"
description: "A cikk a Microsoft Dynamics 365 for Finance and Operations lean manufacturing funkcióinak áttekintését és leírását nyújtja."
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanBoardTransferJob, KanbanBoardWorkCell, KanbanJobSchedulingListPage, LeanProductionFlow
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19371
ms.assetid: 026c5605-6be7-4fdb-a6f2-8e37a806796c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 34ce76fa0102d25161ca9db508f4286fee62902c
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="lean-manufacturing-overview"></a><span data-ttu-id="c6fe3-103">Lean manufacturing (áttekintés)</span><span class="sxs-lookup"><span data-stu-id="c6fe3-103">Lean manufacturing overview</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="c6fe3-104">A cikk a Microsoft Dynamics 365 for Finance and Operations, Enterprise kiadás lean manufacturing funkcióinak áttekintését és leírását nyújtja.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-104">This article provides an overview and description of the lean manufacturing features in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span>

<span data-ttu-id="c6fe3-105">A lean gyártás olyan eszközöket kínál, amelyeket használhat lean műveletek modellezéséhez.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-105">Lean manufacturing offers tools that you can use to model lean operations.</span></span> <span data-ttu-id="c6fe3-106">Ezek az eszközök támogatják és elősegítik az alábbi koncepciókat és üzleti tevékenységeket:</span><span class="sxs-lookup"><span data-stu-id="c6fe3-106">These tools support and promote the following concepts and business activities:</span></span>
-   <span data-ttu-id="c6fe3-107">Hozzon létre egy lean manufacruring alapítványt a gyártási és logisztikai folyamatok létrehozásával mint termelési folyamatok.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-107">Create a lean manufacturing foundation by modeling manufacturing and logistics processes as production flows.</span></span>
-   <span data-ttu-id="c6fe3-108">Valósítson meg egy lean pull rendszert kanbanok használatával, melyek jelzik a keresleti követelményeket.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-108">Implement a lean pull system by using kanbans to signal demand requirements.</span></span>
-   <span data-ttu-id="c6fe3-109">Kanbanfeladatok ellenőrzése és karbantartása.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-109">Monitor and maintain kanban jobs.</span></span>

<span data-ttu-id="c6fe3-110">A lean manufacturing architektúra a Finance and Operations programban tartalmazza a termelési folyamatokat, tevékenységeket és kanbanszabályokat.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-110">The lean manufacturing architecture in Finance and Operations consists of production flows, activities, and kanban rules.</span></span> <span data-ttu-id="c6fe3-111">Ezek a struktúrák teljes mértékben integráltak a Finance and Operations folyamataival.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-111">These structures are fully integrated with Finance and Operations processes.</span></span> <span data-ttu-id="c6fe3-112">Használhatja a lean manufacturing legetőséget vegyes módú gyártási környezetben, ahol különféle készletek, termelések és forrásstratégiák vannak.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-112">You can use lean manufacturing in a mixed-mode manufacturing environment that combines various supply, production, and sourcing strategies.</span></span> <span data-ttu-id="c6fe3-113">Ezek a stratégiák tartalmazzák a termelési rendeléseket, kötegrendeléseket feldolgozóiparoknak, beszerzési rendeléseket és transzferrendeléseket.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-113">These strategies include production orders, batch orders for process industries, purchase orders, and transfer orders.</span></span>
| <span data-ttu-id="c6fe3-114">**Fontos**</span><span class="sxs-lookup"><span data-stu-id="c6fe3-114">**Important**</span></span>                                                                                                                                                                                                                                                                |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="c6fe3-115">A Finance and Operations rendszert használhatja a lean manufacturing kanbanokkal történő végrehajtásának támogatásához.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-115">You can use Finance and Operations to support the implementation of lean manufacturing with kanbans.</span></span> <span data-ttu-id="c6fe3-116">Ugyanakkor a lean irányelvek sikeres alkalmazása a használt belső üzleti folyamatokon és a tényleges termelési feltételeken és környezeten múlik.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-116">However, a successful implementation of lean principles depends on the internal business processes that you use, and the actual production conditions and environment.</span></span> |

## <a name="modeling-manufacturing-and-logistics-processes-as-production-flows"></a><span data-ttu-id="c6fe3-117"> Termelési és logisztikai folyamatok modellezése termelési folyamatokként</span><span class="sxs-lookup"><span data-stu-id="c6fe3-117">Modeling manufacturing and logistics processes as production flows</span></span>
<span data-ttu-id="c6fe3-118">Hozzon létre egy lean manufacruring alapítványt a gyártási és logisztikai folyamatok létrehozásával mint termelési folyamatok.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-118">To create a lean manufacturing foundation, model the manufacturing and logistics processes as production flows.</span></span> <span data-ttu-id="c6fe3-119">Ez a tevékenységhez a következő feladatokból áll:</span><span class="sxs-lookup"><span data-stu-id="c6fe3-119">This activity consists of the following tasks:</span></span>
1.  <span data-ttu-id="c6fe3-120">Azonosítsa a folyamatokat amelyeket meg akar valósítani lean feltöltési stratégiaként, után modellezze le ezeket a folyamatokat termelési folyamatokként.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-120">Identify the processes for which you want to implement a lean replenishment strategy, and then model these processes as production flows.</span></span> <span data-ttu-id="c6fe3-121">Ezután elemezheti és egyszerűsítheti a folyamatokat.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-121">You can then analyze and streamline the processes.</span></span> <span data-ttu-id="c6fe3-122">A lean megvalósítás egyik célja a selejt csökkentése az alapanyagok és információk áramlásának javításával.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-122">One of the goals of a lean implementation is to reduce waste by improving the flow of material and information.</span></span>
2.  <span data-ttu-id="c6fe3-123">Határozza meg a termelési folyamatot olyan tevékenységek sorozataként amelyek leírják az alapanyagok áramlását.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-123">Define a production flow as a sequence of activities that describes the flow of material.</span></span> <span data-ttu-id="c6fe3-124">Egy átmozgatási tevékenység meghatározza a termék vagy termékek mozgását egyik helyről a másikra.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-124">A transfer activity defines the movement of a product or products from one location to another.</span></span> <span data-ttu-id="c6fe3-125">A folyamattevékenység meghatároz egy hozzáadott érték műveletet, amelyet egy termékhez van hozzárendelve.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-125">A process activity defines a value-added operation that is applied to a product.</span></span>
3.  <span data-ttu-id="c6fe3-126">Hozzon létre egy termelési folyamat verziót, ami meghatározza a taktidőhöz szükséges követelményeket.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-126">Create a version of the production flow that defines the requirements for takt time.</span></span> <span data-ttu-id="c6fe3-127">Ezekkel a követelményekkel számolhatók a termelési folyamatban az egyes tevékenységek ciklusidői.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-127">These requirements are used to calculate the cycle times of each activity in the production flow.</span></span> <span data-ttu-id="c6fe3-128">A termelési folyamat többféle verzióját is létrehozhatja, majd ezekkel javíthat a folyamatokon.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-128">You can create multiple versions of production flows, and then use these versions to improve processes.</span></span>

## <a name="using-kanbans-to-signal-demand-requirements"></a><span data-ttu-id="c6fe3-129"> Kanbanok használata szükség követelmények jelzéséhez</span><span class="sxs-lookup"><span data-stu-id="c6fe3-129">Using kanbans to signal demand requirements</span></span>
<span data-ttu-id="c6fe3-130">A húzó rendszer csak szükség esetén termel.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-130">A pull system produces goods only when goods are needed.</span></span> <span data-ttu-id="c6fe3-131">Ez az eljárás csökkenti a felesleges készleteket és a szállítás átfutási idejét.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-131">This practice reduces delivery lead times and excess inventory.</span></span> <span data-ttu-id="c6fe3-132">Használhat kanbanokat tervezéshez, követéshez és folyamat követelményekhez amelyek termelési folyamatokon alapulnak.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-132">You can use kanbans to plan, track, and process requirements that are based on production flows.</span></span> <span data-ttu-id="c6fe3-133">Kanban keretrendszer létrehozásához hozzon létre kanbanszabályokat, amelyek meghatározzák mikor jönnek létre kanbanok és hogyan teljesülnek a követelmények.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-133">To create a kanban framework, create kanban rules that define when kanbans are created, and how the requirements are fulfilled.</span></span> <span data-ttu-id="c6fe3-134">Kétféle kanbanszabályt lehet létrehozni.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-134">You can create two types of kanban rules.</span></span> <span data-ttu-id="c6fe3-135">A gyártási szabályok folyamat kanbanfeladatokat hoznak létre, a kanbanszabályok visszavonása pedig transzfer kanbanfeladatokat hoz létre.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-135">Manufacturing rules create process kanban jobs, and withdrawal kanban rules create transfer kanban jobs.</span></span> <span data-ttu-id="c6fe3-136">A következő feltöltési stratégiákat lehet beállítani:</span><span class="sxs-lookup"><span data-stu-id="c6fe3-136">You can set up the following replenishment strategies:</span></span>
-   <span data-ttu-id="c6fe3-137">**Fix mennyiség** a kanbanszabályok rögzített számú anyagkezelési egységre vonatkoznak, amely azt jelenti, hogy az aktív kanbanok száma állandó.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-137">**Fixed quantity** kanban rules are related to a fixed number of handling units, which means that the numbers of active kanbans are constant.</span></span> <span data-ttu-id="c6fe3-138">Amikor egy kanbanból származó összes terméket felhasználnak, és a kezelési egységeket kézzel kiürítik, létrejön egy azonos típusú új kanban.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-138">Whenever all the products from a Kanban are consumed and the handling units are manually emptied, a new kanban of the same type is created.</span></span> <span data-ttu-id="c6fe3-139">Ha rögzített mennyiségű kanbanszabályt hoz létre, kiszámíthatja az optimális kanbanmennyiségeket és a használt termékmennyiségeket.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-139">When you create fixed quantity kanban rules, you can calculate the optimal kanban quantities and the product quantities that are used.</span></span> <span data-ttu-id="c6fe3-140">A számítás figyelembe veszi a számla-előrejelzést, tényleges igényt a nyitott rendelésekből, cikkek feltöltésének átfutási idejét és a korábbi igényeket.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-140">The calculation takes into account forecast, actual demand from open orders, lead time to replenish items, and historical demands.</span></span>
-   <span data-ttu-id="c6fe3-141">**Ütemezett** Kanbanszabályok az alaptervezet által számított igényeket teljesítik.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-141">**Scheduled** kanban rules replenish requirements that are calculated by master planning.</span></span> <span data-ttu-id="c6fe3-142">Az alaptervezet tervezett kanbanokat hoz létre, amelyek kanbanként lehet megerősíteni.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-142">Master planning generates planned kanbans that can be firmed to kanbans.</span></span>
-   <span data-ttu-id="c6fe3-143">**Esemény** Kanbanszabályok azon igények teljesítésére, melyeket az értékesítési rendelés vonalak, a gyártási anyagjegyzék vonalak vagy a minimális készlet beállítások tartalmaznak.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-143">**Event** kanban rules replenish requirements that originate from sales order lines, production BOM lines, kanban lines, or minimum inventory settings.</span></span> <span data-ttu-id="c6fe3-144">Ha eseménykanbanok jönnek létre, akkor forrás szükségletekhez kerülnek rögzítésre.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-144">When event kanbans are generated, they are pegged to the source requirements.</span></span>

<span data-ttu-id="c6fe3-145">A kanbanok létrehozásakor egy vagy több kanbanfeladat generálódik a kanbanfolyamat tevékenységek alapján, melyek a kanbanszabályokban definiáltak.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-145">When kanbans are created, one or more kanban jobs are generated based on the kanban flow activities that are defined in the kanban rules.</span></span>

## <a name="monitoring-and-maintaining-kanban-jobs"></a><span data-ttu-id="c6fe3-146">Kanbanfeladatok ellenőrzése és karbantartása.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-146">Monitoring and maintaining kanban jobs</span></span>
<span data-ttu-id="c6fe3-147">A lean manufacturing segítségével látható a termelési és logisztikai tevékenységek pillanatnyi állapota, amelyet a kanbanszabályok vezérelnek.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-147">Lean manufacturing provides visibility into the current status of manufacturing and logistics activities that are governed by the kanban rules.</span></span> <span data-ttu-id="c6fe3-148">Ennek eredményeként az alábbi feladatokat tervezheti és priorizálhatja:</span><span class="sxs-lookup"><span data-stu-id="c6fe3-148">As a result, you can plan and prioritize the following tasks:</span></span>

-   <span data-ttu-id="c6fe3-149">Tekintse át az aktív kanbanfeladat ütemezést.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-149">Gain an overview of the current kanban job schedule.</span></span>
-   <span data-ttu-id="c6fe3-150">Kanbanfeladatok tervezése és újraütemezése.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-150">Plan and reschedule kanban jobs.</span></span>
-   <span data-ttu-id="c6fe3-151">Kövesse nyomon és regisztrálja a kanbanfeladatok állapotát.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-151">Track and register the status of kanban jobs.</span></span>

<span data-ttu-id="c6fe3-152">Az alábbi lista leírja a specializált kanbantáblákat:</span><span class="sxs-lookup"><span data-stu-id="c6fe3-152">The following list describes the specialized kanban boards:</span></span>
-   <span data-ttu-id="c6fe3-153">Kanban feladat ütemezése – áttekintése nyújt a kanbanfeladatokhoz.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-153">Kanban job scheduling – Provides an overview of the kanban jobs.</span></span> <span data-ttu-id="c6fe3-154">A tábla a kanbanfeladatokat és az állapotukat jeleníti meg egy vagy több munkacellában.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-154">The board displays kanban jobs and their status for one or multiple work cells.</span></span> <span data-ttu-id="c6fe3-155">A feladatok a tervezési időszakok (napok vagy hetek) szerint vannak listázva, amit a termelési folyamatmodellben határoztak meg.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-155">The jobs are listed according to the planning periods (days or weeks) that are defined in the production flow model.</span></span> <span data-ttu-id="c6fe3-156">A tábla az egyes tervezési időszakra vonatkozó fogyasztást is megjeleníti, így nyomon követheti az ütemezett terhelést.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-156">The board also displays the capacity consumption for each planning period, so that you can monitor the scheduled load.</span></span> <span data-ttu-id="c6fe3-157">Megváltoztathatja a kanbanfeladatok állapotát, újraütemezhet kanbanfeladatokat eltérő tervezési időszakokhoz és végrehajthat egyéb feladatokat.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-157">You can change the status of kanban jobs, reschedule kanban jobs to different planning periods, and perform other tasks.</span></span>
-   <span data-ttu-id="c6fe3-158">Kanbantábla az átviteli feladatokhoz – Ez a tábla az aktuális átviteli feladatokról nyújt áttekintést.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-158">Kanban board for transfer jobs – This board provides an overview of the current transfer jobs.</span></span> <span data-ttu-id="c6fe3-159">Frissíthet és regisztrálhat kitárolási listákat, elindíthat és befejezhet transzferfeladatokat és végrehajthat egyéb feladatokat.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-159">You can update and register picking lists, start and complete transfer jobs, and perform other tasks.</span></span>
-   <span data-ttu-id="c6fe3-160">Kanbantábla feldolgozási feladathoz – Ez a tábla a normális termelési folyamat támogatásához lett tervezve, áttekintést nyújt az aktuális helyzethez egy vagy több munkacellában.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-160">Kanban board for process jobs – This board is designed to support the normal production flow and give an overview of the current situation in one or multiple work cells.</span></span> <span data-ttu-id="c6fe3-161">Erről a tábláról a kanbanok priorizálhatók, kitárolhatók és gyárthatók.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-161">From this board Kanbans can be prioritized, picked, or manufactured.</span></span> <span data-ttu-id="c6fe3-162">Továbbá a tábla segíti a vonalkód beolvasását kanbanok jelentéséhez.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-162">The board is also designed to support barcode scanning for the reporting of Kanbans.</span></span>

## <a name="kanban-jobs-and-integration-with-finance-and-operations-processes"></a><span data-ttu-id="c6fe3-163">Kanbanfeladatok és a Finance and Operations folyamatainak integrálása</span><span class="sxs-lookup"><span data-stu-id="c6fe3-163">Kanban jobs and integration with Finance and Operations processes</span></span>
<span data-ttu-id="c6fe3-164">A Kanbanfeladatok teljes mértékben integráltak a jelenlegi készlettranzakciós folyamatokkal a Finance and Operations rendszerben.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-164">Kanban jobs are fully integrated with current processes for inventory transactions in Finance and Operations.</span></span>
-   <span data-ttu-id="c6fe3-165">Végrehajthat kitárolási tevékenységeket olyan alapanyag feltöltéséhez, amly a kanbanfeladatok követelményeinek teljesítéséhez használatos.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-165">You can perform picking activities to replenish material that is used to fulfill the requirements of kanban jobs.</span></span>
-   <span data-ttu-id="c6fe3-166">Nyomtathat kanban kártyákat, körbejáró kártyákat és kitárolási listákat kanbanok támogatásához.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-166">You can print kanban cards, circulating kanban cards, and picking lists to support the use of kanbans.</span></span> <span data-ttu-id="c6fe3-167">Ezek a dokumentumok képviselik, jegyzik és nyomon követik a kanbanfeladatokat a raktárban és a termelési szinten.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-167">These documents are used to represent, track, and register kanban jobs in the warehouse and on the production floor.</span></span>
-   <span data-ttu-id="c6fe3-168">Használhat vonalkód beolvasást a kitárolási és átviteli tevékenységek regisztrálásához a készletben.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-168">You can register the picking and transfer activities in inventory by scanning bar codes.</span></span>

<span data-ttu-id="c6fe3-169">Továbbá a Lean manufacturing támogatja a beszerzési és számlázási folyamatokat azokhoz a szolgáltatásokhoz, melyek alvállalkozói termelési tevékenységekhez kapcsolódnak.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-169">In addition, lean manufacturing supports the purchasing and invoicing processes for services that are referenced by subcontracted activities.</span></span>
-   <span data-ttu-id="c6fe3-170">Hozzárendelhet beszerzési szerződés sorokat és szolgáltatásokat alvállalkozói tevékenységekhez.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-170">You can assign purchase agreement lines and services to subcontracted activities.</span></span>
-   <span data-ttu-id="c6fe3-171">Létrehozhat időszakos beszerzési rendeléseket és bevételezési jelentéseket a szolgáltatások beszerzésének és számlázásának támogatásához.</span><span class="sxs-lookup"><span data-stu-id="c6fe3-171">You can create periodic purchase orders and receipt advices to support the purchase and invoicing of the services.</span></span>





