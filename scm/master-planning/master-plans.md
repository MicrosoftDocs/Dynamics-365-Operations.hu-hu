---
title: Alaptervek
description: "A vállalat napi munkaműveleteinek támogatásához, a különböző figyelni kívánt tervezési stratégiák szimulálásához és vállalati (például a belső teljesítménnyel és a vevői elégedettséggel kapcsolatos) alapszabályok megvalósításához használjon különféle alapterveket."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqParameters, ReqPlanSched
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 7911
ms.assetid: a116b7de-3d6d-4321-87ba-5a5d99c2f64e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 29bb560c11e63938bea73ed8471c27563b546f8f
ms.lasthandoff: 03/31/2017


---

# <a name="master-plans"></a>Alaptervek

[!include[banner](../includes/banner.md)]


A vállalat napi munkaműveleteinek támogatásához, a különböző figyelni kívánt tervezési stratégiák szimulálásához és vállalati (például a belső teljesítménnyel és a vevői elégedettséggel kapcsolatos) alapszabályok megvalósításához használjon különféle alapterveket. 

Az alapterveket az **Alaptervek** oldalon lehet konfigurálni.

A terveknek két típusa létezik:
-   **Statikus terv** – Az alaptervezés számításai az aktuális adatokat használják az új nettó szükségletek létrehozásához. Ez a terv a következő alaptervfuttatásig változatlan marad. Ez egy olyan működési terv, amelyet a vállalati személyzet különböző tagjai, például a beszerzők vagy a termeléstervezők használhatnak a döntéseik alapjául, és amely alapján végrehajthatják a napi feladataikat és tevékenységeiket.
-   **Dinamikus terv** – Ez a terv ugyanabból a nettó szükségleti tervből indul ki, amelyet az alaptervezés hozott létre. A dinamikus tervet azonban az alapütemezés minden változása esetén frissíteni lehet. Ez akkor fordulhat elő, amikor például új értékesítési rendelést hoz létre. Ez lehetővé teszi a változó rendeléshálózat és a cikkek rendelkezésre állásának a figyelését, anélkül, hogy zavarná a mások munkafolyamataihoz használt statikus tervet.

A vállalat dönthet úgy, hogy csak egy dinamikus tervet használ, vagy hogy mind statikus, mind dinamikus terveket alkalmaz. Ezenkívül be lehet állítani, hogy egy adott alapterv egy bizonyos stratégiát tükrözzön, vagy egy bizonyos probléma megoldására szolgáljon. Példák a következők:
-   Magasabb készletszintek beállítása a készlethiány elkerülése érdekében.
-   Hosszabb biztonsági időtartalék beállítása a megbízhatatlan szállítók elleni védekezés érdekében.

Beállíthatja, hogy a kezdő dinamikus terv az alaptervezés minden futtatása alkalmával az új szükségleti tervnek megfelelően frissüljön. Ezeket a beállításokat az **Alaptervezés paraméterei** oldalon adhatja meg.



<a name="see-also"></a>Lásd még
--------

[Fedezeti beállítások](coverage-settings.md)

[Alaptervezés taktikai és operatív tervezésének elválasztása](http://blogs.msdn.com/b/axmfg/archive/2012/10/12/separating-tactical-and-operative-planning-for-master-scheduling.aspx)

[Alaptervezés: Statikus és dinamikus alaptervet vagy csak egy tervet használjon?](https://community.dynamics.com/ax/b/msdynaxlessonslearned/archive/2014/01/16/master-planning-use-a-static-and-dynamic-master-plan-or-use-one-plan)




