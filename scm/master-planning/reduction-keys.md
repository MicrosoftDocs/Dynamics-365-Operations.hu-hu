---
title: "Csökkentési kulcsok"
description: "Ez a cikk az csökkentési kulcs beállítását bemutató példákat tartalmaz. Tartalmaz információkat a különböző csökkentési kulcs beállításokról és azok eredményéről. A csökkentési kulcsot használhatja az előrejelzési követelmények csökkentésének módjának meghatározásához."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqPlanSched
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19251
ms.assetid: aa9e0dfb-6052-4a2e-9378-89507c02fdf2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ce3ff2ac0a5bd9bd342baa05425d7d0957ab8a09
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="reduction-keys"></a>Csökkentési kulcsok

[!include[banner](../includes/banner.md)]


Ez a cikk az csökkentési kulcs beállítását bemutató példákat tartalmaz. Tartalmaz információkat a különböző csökkentési kulcs beállításokról és azok eredményéről. A csökkentési kulcsot használhatja az előrejelzési követelmények csökkentésének módjának meghatározásához.

<a name="example-1-percent---reduction-key-forecast-reduction-principle"></a>1. példa: Százalék – csökkentési kulcs előrejelzés csökkentési elv
---------------------------------------------------------------

Csökkentési kulcs az előrejelzési követelmények csökkentése a százalékok és az időszakok alapján történik, amelyeket a csökkentési kulcs definiál.

1.  A **Csökkentési kulcsok** lapon állítsa be a következő sorokat.
    | Módosítás | Egység  | Százalék |
    |--------|-------|---------|
    | 1      | Hónap | 100     |
    | 2      | Hónap | 75      |
    | 3      | Hónap | 50      |
    | 4      | Hónap | 25      |

2.  Hivatkozás a csökkentési kulcsot a cikk fedezeti csoporthoz.
3.  A **Alaptervek** az oldalon a **Csökkentési elv** mezőben válassza ki **Százalék - csökkentési kulcs**.
4.  Hozzon létre egy havi 1000 darabos értékesítési előrejelzést.

Ha előrejelzési ütemezést január 1-jén futtatja, az igény-előrejelzés követelményeinek felhasználása a százalékokat, amelyek a beállítása a **Csökkentési kulcsok** oldalon. Az alábbi mennyiségi követelések kerülnek az alaptervbe.

| Hónap                | Szükséges darabszám |
|----------------------|---------------------------|
| Január              | 0                         |
| Február             | 250                       |
| Március                | 500                       |
| Április                | 750                       |
| május – december | 1000                     |

## <a name="example-2-transactions--reduction-key-forecast-reduction-principle"></a>2. példa: Tranzakciók csökkentési kulcs előrejelzés csökkentési elv
Csökkentési kulcs az előrejelzési követelmények csökkentése a százalékok és az időszakok alapján történik, amelyeket a csökkentési kulcs definiál.

-   Az **Alaptervek** az oldalon a **Csökkentési elv** mezőben válassza ki **Tranzakciók - csökkentési kulcs**.

A következő értékesítési rendelések léteznek január 1-én.

| Hónap    | Rendelt darabszám |
|----------|--------------------------|
| Január  | 956                      |
| Február | 1,176                    |
| Március    | 451                      |
| Április    | 119                      |

Ugyanazt a havi 1000 darabos értékesítési előrejelzést alkalmazva az alábbi mennyiségi követelések kerülnek az alaptervbe.

| Hónap                | Szükséges darabszám |
|----------------------|---------------------------|
| Január              | 44                        |
| Február             | 0                         |
| Március                | 549                       |
| Április                | 881                       |
| május – december | 1000                     |

## <a name="example-3-transactions--dynamic-period-forecast-reduction-principle"></a>3. példa: Tranzakciók dinamikus periódus előrejelzés csökkentési elv
A legtöbb esetben rendszerek vannak beállítva, hogy a tranzakciók csökkenti az igény-előrejelzés egyedi előrejelzési időszakokon belül: hét, hónap, és így tovább. A csökkentési kulcs határozza meg ezeket az időszakokat. Ugyanakkor két között eltelt idő igény-előrejelzési sort is *Jelenti* egy időszakot.

1.  Hozzon létre egy igény-előrejelzés a következő dátumokat és mennyiségeket.
    | Dátum       | Igény-előrejelzés |
    |------------|-----------------|
    | Január 1.  | 1000           |
    | Január 5.  | 500             |
    | Január 12. | 1000           |

    Ez előrejelzésben, nincs időszak törlése a következő előre jelzett dátum között: az első és második dátum között nincs négy nappal az az időtartam, és a második és harmadik dátum között van az az időtartam hét nap. A különböző kiterjed a dinamikus időszakok lesznek.
2.  Értékesítésirendelés-sorok létrehozása.
    | Dátum                             | Eladási árhoz kapcsolódó mennyiség |
    |----------------------------------|----------------------|
    | December 15-re vonatkozóan az előző év | 500                  |
    | Január 3.                        | 100                  |
    | Január 10.                       | 200                  |

Az előrejelzés csökken a következőképpen történik:

-   Az első értékesítési rendelés nem minden időszakban, így azt nem csökkenti az esetleges előrejelzés.
-   A második értékesítési rendelés helyzet között január 1-én január 5-én csökkenteni fogja az előrejelzéshez tartozó január 1-100.
-   A harmadik értékesítési rendelés helyzet között január 5 és január 12 között csökkenteni fogja az előrejelzéshez tartozó január 5-200.

A következő tervezett rendelés létrejön, az előrejelzés kielégítése céljából.

| Igény-előrejelzés kockája | Mennyiség csökkentése |
|----------------------|------------------|
| Január 1.            | 900              |
| Január 5.            | 300              |
| Január 12.           | 1000            |

Íme összefoglalását **Tranzakciók - dinamikus időszak** csökkentési:

-   Előrejelzési követelmények csökkentése a tényleges tranzakciókat a dinamikus időszak során előforduló. A dinamikus időszak fedezi az aktuális előrejelzési dátumokat és akkor ér véget a következő előrejelzés kezdetén.
-   Ezzel a módszerrel nem használja, vagy a csökkentési kulcs szükséges.
-   Ez a beállítás használata esetén a következő történik:
    -   Ha az előrejelzés teljes mértékben csökken, az előrejelzési követelmények az aktuális előrejelzési válnak, 0 (nulla).
    -   Nincs jövőbeli előrejelzés esetén beírt utolsó előrejelzésből az előrejelzési követelmények csökkentése.
    -   Időkorlátok az előrejelzés-csökkentés-számításban szerepel.
    -   Időkorlátok az előrejelzés-csökkentés-számításban szerepel.
    -   Tényleges rendelési tranzakciók túllépik az előre jelzett követelményeit, ha a fennmaradó tranzakciók nem továbbítja a következő előrejelzési időszak.


<a name="see-also"></a>Lásd még
--------

[Alaptervek](master-plans.md)




