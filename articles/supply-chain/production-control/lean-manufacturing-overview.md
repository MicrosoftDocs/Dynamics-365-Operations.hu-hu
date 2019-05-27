---
title: Lean manufacturing (áttekintés)
description: A cikk a Dynamics 365 for Finance and Operations lean manufacturing funkcióinak áttekintését és leírását nyújtja.
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardTransferJob, KanbanBoardWorkCell, KanbanJobSchedulingListPage, LeanProductionFlow
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19371
ms.assetid: 026c5605-6be7-4fdb-a6f2-8e37a806796c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c6db940548018c9d6bbb31891c21f7c334ba8956
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562392"
---
# <a name="lean-manufacturing-overview"></a>Lean manufacturing (áttekintés)

[!include [banner](../includes/banner.md)]

A cikk a Microsoft Dynamics 365 for Finance and Operations lean manufacturing funkcióinak áttekintését és leírását nyújtja.

A lean gyártás olyan eszközöket kínál, amelyeket használhat lean műveletek modellezéséhez. Ezek az eszközök támogatják és elősegítik az alábbi koncepciókat és üzleti tevékenységeket:
-   Hozzon létre egy lean manufacruring alapítványt a gyártási és logisztikai folyamatok létrehozásával mint termelési folyamatok.
-   Valósítson meg egy lean pull rendszert kanbanok használatával, melyek jelzik a keresleti követelményeket.
-   Kanbanfeladatok ellenőrzése és karbantartása.

A lean manufacturing architektúra a Finance and Operations programban tartalmazza a termelési folyamatokat, tevékenységeket és kanbanszabályokat. Ezek a struktúrák teljes mértékben integráltak a Finance and Operations folyamataival. Használhatja a lean manufacturing legetőséget vegyes módú gyártási környezetben, ahol különféle készletek, termelések és forrásstratégiák vannak. Ezek a stratégiák tartalmazzák a termelési rendeléseket, kötegrendeléseket feldolgozóiparoknak, beszerzési rendeléseket és transzferrendeléseket.

| **Fontos**                                                                                                                                                                                                                                                                |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| A Finance and Operations rendszert használhatja a lean manufacturing kanbanokkal történő végrehajtásának támogatásához. Ugyanakkor a lean irányelvek sikeres alkalmazása a használt belső üzleti folyamatokon és a tényleges termelési feltételeken és környezeten múlik. |

## <a name="modeling-manufacturing-and-logistics-processes-as-production-flows"></a> Termelési és logisztikai folyamatok modellezése termelési folyamatokként
Hozzon létre egy lean manufacruring alapítványt a gyártási és logisztikai folyamatok létrehozásával mint termelési folyamatok. Ez a tevékenységhez a következő feladatokból áll:
1.  Azonosítsa a folyamatokat amelyeket meg akar valósítani lean feltöltési stratégiaként, után modellezze le ezeket a folyamatokat termelési folyamatokként. Ezután elemezheti és egyszerűsítheti a folyamatokat. A lean megvalósítás egyik célja a selejt csökkentése az alapanyagok és információk áramlásának javításával.
2.  Határozza meg a termelési folyamatot olyan tevékenységek sorozataként amelyek leírják az alapanyagok áramlását. Egy átmozgatási tevékenység meghatározza a termék vagy termékek mozgását egyik helyről a másikra. A folyamattevékenység meghatároz egy hozzáadott érték műveletet, amelyet egy termékhez van hozzárendelve.
3.  Hozzon létre egy termelési folyamat verziót, ami meghatározza a taktidőhöz szükséges követelményeket. Ezekkel a követelményekkel számolhatók a termelési folyamatban az egyes tevékenységek ciklusidői. A termelési folyamat többféle verzióját is létrehozhatja, majd ezekkel javíthat a folyamatokon.

## <a name="using-kanbans-to-signal-demand-requirements"></a> Kanbanok használata szükség követelmények jelzéséhez
A húzó rendszer csak szükség esetén termel. Ez az eljárás csökkenti a felesleges készleteket és a szállítás átfutási idejét. Használhat kanbanokat tervezéshez, követéshez és folyamat követelményekhez amelyek termelési folyamatokon alapulnak. Kanban keretrendszer létrehozásához hozzon létre kanbanszabályokat, amelyek meghatározzák mikor jönnek létre kanbanok és hogyan teljesülnek a követelmények. Kétféle kanbanszabályt lehet létrehozni. A gyártási szabályok folyamat kanbanfeladatokat hoznak létre, a kanbanszabályok visszavonása pedig transzfer kanbanfeladatokat hoz létre. A következő feltöltési stratégiákat lehet beállítani:
-   **Fix mennyiség** a kanbanszabályok rögzített számú anyagkezelési egységre vonatkoznak, amely azt jelenti, hogy az aktív kanbanok száma állandó. Amikor egy kanbanból származó összes terméket felhasználnak, és a kezelési egységeket kézzel kiürítik, létrejön egy azonos típusú új kanban. Ha rögzített mennyiségű kanbanszabályt hoz létre, kiszámíthatja az optimális kanbanmennyiségeket és a használt termékmennyiségeket. A számítás figyelembe veszi a számla-előrejelzést, tényleges igényt a nyitott rendelésekből, cikkek feltöltésének átfutási idejét és a korábbi igényeket.
-   **Ütemezett** Kanbanszabályok az alaptervezet által számított igényeket teljesítik. Az alaptervezet tervezett kanbanokat hoz létre, amelyek kanbanként lehet megerősíteni.
-   **Esemény** Kanbanszabályok azon igények teljesítésére, melyeket az értékesítési rendelés vonalak, a gyártási anyagjegyzék vonalak vagy a minimális készlet beállítások tartalmaznak. Ha eseménykanbanok jönnek létre, akkor forrás szükségletekhez kerülnek rögzítésre.

A kanbanok létrehozásakor egy vagy több kanbanfeladat generálódik a kanbanfolyamat tevékenységek alapján, melyek a kanbanszabályokban definiáltak.

## <a name="monitoring-and-maintaining-kanban-jobs"></a>Kanbanfeladatok ellenőrzése és karbantartása.
A lean manufacturing segítségével látható a termelési és logisztikai tevékenységek pillanatnyi állapota, amelyet a kanbanszabályok vezérelnek. Ennek eredményeként az alábbi feladatokat tervezheti és priorizálhatja:

-   Tekintse át az aktív kanbanfeladat ütemezést.
-   Kanbanfeladatok tervezése és újraütemezése.
-   Kövesse nyomon és regisztrálja a kanbanfeladatok állapotát.

Az alábbi lista leírja a specializált kanbantáblákat:
-   Kanban feladat ütemezése – áttekintése nyújt a kanbanfeladatokhoz. A tábla a kanbanfeladatokat és az állapotukat jeleníti meg egy vagy több munkacellában. A feladatok a tervezési időszakok (napok vagy hetek) szerint vannak listázva, amit a termelési folyamatmodellben határoztak meg. A tábla az egyes tervezési időszakra vonatkozó fogyasztást is megjeleníti, így nyomon követheti az ütemezett terhelést. Megváltoztathatja a kanbanfeladatok állapotát, újraütemezhet kanbanfeladatokat eltérő tervezési időszakokhoz és végrehajthat egyéb feladatokat.
-   Kanbantábla az átviteli feladatokhoz – Ez a tábla az aktuális átviteli feladatokról nyújt áttekintést. Frissíthet és regisztrálhat kitárolási listákat, elindíthat és befejezhet transzferfeladatokat és végrehajthat egyéb feladatokat.
-   Kanbantábla feldolgozási feladathoz – Ez a tábla a normális termelési folyamat támogatásához lett tervezve, áttekintést nyújt az aktuális helyzethez egy vagy több munkacellában. Erről a tábláról a kanbanok priorizálhatók, kitárolhatók és gyárthatók. Továbbá a tábla segíti a vonalkód beolvasását kanbanok jelentéséhez.

## <a name="kanban-jobs-and-integration-with-finance-and-operations-processes"></a>Kanbanfeladatok és a Finance and Operations folyamatainak integrálása
A Kanbanfeladatok teljes mértékben integráltak a jelenlegi készlettranzakciós folyamatokkal a Finance and Operations rendszerben.
-   Végrehajthat kitárolási tevékenységeket olyan alapanyag feltöltéséhez, amly a kanbanfeladatok követelményeinek teljesítéséhez használatos.
-   Nyomtathat kanban kártyákat, körbejáró kártyákat és kitárolási listákat kanbanok támogatásához. Ezek a dokumentumok képviselik, jegyzik és nyomon követik a kanbanfeladatokat a raktárban és a termelési szinten.
-   Használhat vonalkód beolvasást a kitárolási és átviteli tevékenységek regisztrálásához a készletben.

Továbbá a Lean manufacturing támogatja a beszerzési és számlázási folyamatokat azokhoz a szolgáltatásokhoz, melyek alvállalkozói termelési tevékenységekhez kapcsolódnak.
-   Hozzárendelhet beszerzési szerződés sorokat és szolgáltatásokat alvállalkozói tevékenységekhez.
-   Létrehozhat időszakos beszerzési rendeléseket és bevételezési jelentéseket a szolgáltatások beszerzésének és számlázásának támogatásához.





