---
title: Az alaptervek áttekintése
description: A vállalat napi munkaműveleteinek támogatásához, a különböző figyelni kívánt tervezési stratégiák szimulálásához és vállalati (például a belső teljesítménnyel és a vevői elégedettséggel kapcsolatos) alapszabályok megvalósításához használjon különféle alapterveket.
author: t-benebo
ms.date: 05/28/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ReqParameters, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "7911"
- intro-internal
ms.assetid: a116b7de-3d6d-4321-87ba-5a5d99c2f64e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1b3d30d9ef2f08c2cb7b2ca022ff1a816567a247
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/23/2022
ms.locfileid: "8468755"
---
# <a name="master-plans-overview"></a>Az alaptervek áttekintése

[!include [banner](../includes/banner.md)]

A vállalat napi munkaműveleteinek támogatásához, a különböző figyelni kívánt tervezési stratégiák szimulálásához és vállalati (például a belső teljesítménnyel és a vevői elégedettséggel kapcsolatos) alapszabályok megvalósításához használjon különféle alapterveket.

Az alapterveket az **Alaptervek** oldalon lehet konfigurálni.

A terveknek két típusa létezik:

- **Statikus terv** – Az alaptervezés számításai az aktuális adatokat használják az új nettó szükségletek létrehozásához. Ez a terv a következő alaptervfuttatásig, vagy amíg manuálisan nem módosítja a tervet, változatlan marad. Ez egy olyan működési terv, amelyet a vállalati személyzet különböző tagjai, például a beszerzők vagy a termeléstervezők használhatnak a döntéseik alapjául, és amely alapján végrehajthatják a napi tevékenységeiket.
- **Dinamikus terv** – Ez a terv ugyanabból a nettó szükségleti tervből indul ki, amelyet az alaptervezés hozott létre. A dinamikus tervet azonban az alapütemezés minden változása esetén frissíteni lehet. Ez akkor fordulhat elő, amikor például új értékesítési rendelést hoz létre. Ez lehetővé teszi a változó rendeléshálózat és a cikkek rendelkezésre állásának a figyelését, anélkül, hogy zavarná a mások munkafolyamataihoz használt statikus tervet.

A vállalat dönthet úgy, hogy csak egy dinamikus tervet használ, vagy hogy mind statikus, mind dinamikus terveket alkalmaz. Ezenkívül be lehet állítani, hogy egy adott alapterv egy bizonyos stratégiát tükrözzön, vagy egy bizonyos probléma megoldására szolgáljon. Példák a következők:

- Magasabb készletszintek beállítása a készlethiány elkerülése érdekében.
- Hosszabb biztonsági időtartalék beállítása a megbízhatatlan szállítók elleni védekezés érdekében.

Beállíthatja, hogy a kezdő dinamikus terv az alaptervezés minden futtatása alkalmával az új szükségleti tervnek megfelelően frissüljön. Ezeket a beállításokat az **Alaptervezés paraméterei** oldalon adhatja meg.

## <a name="additional-resources"></a>További erőforrások

- [Fedezeti beállítások](coverage-settings.md)
- [Alaptervezés taktikai és operatív tervezésének elválasztása](https://community.dynamics.com/ax/b/dynamicsaxmanufacturingrdteamblog/posts/separating-tactical-and-operative-planning-for-master-scheduling)
- [Alaptervezés: Statikus és dinamikus alaptervet vagy csak egy tervet használjon?](https://community.dynamics.com/ax/b/msdynaxlessonslearned/archive/2014/01/16/master-planning-use-a-static-and-dynamic-master-plan-or-use-one-plan)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
