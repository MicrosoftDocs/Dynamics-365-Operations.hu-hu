---
title: "Tárgyi eszközök értékcsökkenésére vonatkozó szabályok"
description: "Ez a témakör a tárgyi eszközök értékcsökkenésére vonatkozó szabályokokról nyújt áttekintést."
author: saraschi2
manager: AnnBe
ms.date: 03/14/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13891
ms.assetid: 36d1112d-921c-4fff-abe0-0ff2429848d3
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: c69fd798c2e978935a63b079fb11c68d8555594c
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---

# <a name="fixed-asset-depreciation-conventions"></a>Tárgyi eszközök értékcsökkenésére vonatkozó szabályok

[!include [banner](../includes/banner.md)]

Az értékcsökkenési szabályok segítségével meghatározható, hogy mikor és hogyan kerüljön sor az értékcsökkenés számítására a tárgyi eszköz beszerzésének évében és abban az évben, amikor a tárgyi eszközt kivezetik.

A értékcsökkenési szabályok hozzárendelhetők tárgyieszköz-csoport könyvének beállításaihoz. Ebben az esetben a társított értékcsökkenési szabályok szolgálnak alapértelmezett értékként a tárgyieszköz-könyvek létrehozásakor. Értékcsökkenési szabályok egyéni tárgyieszköz-könyvhöz is beállíthatók.


|  Értékcsökkenési szabály  |                                                                                                                                                                                                                                                                                                                                                                                                     Leírás                                                                                                                                                                                                                                                                                                                                                                                                     |
|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|           Nincs            |                                                                                                                                                                                                                                                                                                                                                                     Tárgyi eszközök értékcsökkentése az <strong>aktiválástól</strong> kezdve indul.                                                                                                                                                                                                                                                                                                                                                                      |
|         Félév         |                                                                                                                                                                                                                                                                                                     Az értéktárgy értékcsökkenéseének első és az utolsó évében fél éves értékcsökkenés levonására kerül sor. Az elszámolási időszak minden más évében az értékcsökkenés teljes évét levonjuk.                                                                                                                                                                                                                                                                                                      |
|        Teljes hónap         |                                                                                                                                                                                                                                                        Az eszközök, amelyek <strong>aktiválása</strong> a hónap valamely napján történik, az adott hónap első napján kezdenek el értékcsökkenni. A hónap során bármikor kivont eszközök az előző hónap utolsó napján minősülnek kivontnak értékcsökkenés szempontjából.                                                                                                                                                                                                                                                         |
|        Negyedév közepe        |                                                                                                           Ahhoz, hogy kiszámítsa az értékcsökkenési leírást a vagyontárgy aktiválásának évére, szorozza meg a teljes évre vonatkozó értékcsökkenést az eszköz aktiválásának negyedévére jutó, a következő táblázatban látható százalékos értékkel.<table><thead><tr><th>Negyedév</th><th>Százalék</th></tr></thead><tbody><tr><td>Első</td><td>87,5</td></tr><tr><td>Második</td><td>62,5</td></tr><tr><td>Harmadik</td><td>37,5</td></tr><tr><td>Negyedik</td><td>12,5</td></tr></tbody></table>A kivezetési negyedévben (vagy a teljes mértékben értékcsökkentett negyedévben) fél évi értékcsökkenést alkalmazunk.                                                                                                            |
| Hónap közepe (hó elseje)  | A hónap első felében (1. és 15. nap között) <strong>aktivált</strong> eszközöknél az értékcsökkentés az <strong>aktiválás</strong> hónapjának első napján indul. A hónap második felében (16. nap és a hónap vége között) <strong>aktivált</strong> eszközöknél az értékcsökkentés az <strong>aktiválás</strong> hónapját követő hónap első napján indul. A hónap első felében (1. és 15. nap között) kivont eszközök az előző hónap utolsó napján minősülnek kivontnak értékcsökkenés szempontjából. A hónap második felében (16. nap és a hónap vége között) kivont eszközök a kivonás hónapjának utolsó napján minősülnek kivontnak értékcsökkenés szempontjából. |
| Hónap közepe (hó 15-e) |                                                                                                                                                        Ahhoz, hogy kiszámítsa az értékcsökkenési leírást az eszköz aktiválásának évében, szorozza meg a teljes éves értékcsökkenést egy törttel. A tört számlálója (felső szám) azon teljes hónapok száma, amelyekben az eszköz aktív az év során, plusz 1/2 (vagy 0,5). A nevező (alsó szám) 12. Ha az elszámolási időszak vége előtt vezeti ki az eszközt, használja ugyanezt a módszert a kivezetési évre vonatkozó értékcsökkenési leírás kiszámításához.                                                                                                                                                        |
| Félév (évkezdet) |                                                                                                                                                                                                                                                          Az év első felében <strong>aktivált</strong> eszközök értékcsökkenése az év (teljes év) első napján indul. Az év második felében <strong>aktivált</strong> eszközök értékcsökkenése az év középső napján indul.                                                                                                                                                                                                                                                          |
|   Félév (következő év)   |                                                            Az év első felében <strong>aktivált</strong> eszközök értékcsökkenése az év (teljes év) első napján indul. Az év második felében <strong>aktivált</strong> eszközök értékcsökkenése a következő év első napján indul. Az év első felében kivont eszközök az előző év utolsó napján minősülnek kivontnak értékcsökkenés szempontjából. A folyó évre vonatkozó értékcsökkenést vissza kell vonni vagy ki kell igazítani. Az év második felében kivont eszközök a kivonás évének utolsó napján számítanak kivontnak értékcsökkenési szempontból.                                                            |


