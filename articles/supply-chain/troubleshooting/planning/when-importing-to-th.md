---
title: A program akkor is kéri, hogy mentse a cikkfedezeti beállításokat, ha nem hajtott végre módosításokat
description: A program akkor is kéri, hogy mentse a cikkfedezeti beállításokat, ha nem hajtott végre módosításokat.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: DataManagementWorkspace_
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: angarmas
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 3dfa974740420433af1e1b37630b22509510c91b
ms.sourcegitcommit: 3c15a26e9708adc9a75082dc551f0a3a0a7d89f4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049470"
---
# <a name="youre-prompted-to-save-item-coverage-settings-even-though-you-made-no-changes"></a>A program akkor is kéri, hogy mentse a cikkfedezeti beállításokat, ha nem hajtott végre módosításokat

Tudásbáziscikk száma: 4615588

## <a name="symptoms"></a>Tünetek

Bizonyos helyzetekben előfordulhat, hogy a **Cikkfedezet** oldal megnyitásakor a következő üzenet jelenik meg, miután importálta a cikkeket a *Cikkfedezet V2* entitáson keresztül:

> Menti a módosításokat a bezárás előtt?

Ez az üzenet akkor is megjelenik, ha nem hajtott végre módosításokat.

## <a name="resolution"></a>Megoldás

A **Cikkfedezet** oldal olyan összetett alapértelmezési logikát használ, ami azt okozhatja, hogy az üzenet megjelenik az adatbázisban a közelmúltban végrehajtott közvetlen módosítások (például entitások importálása) után. Ha az `AREGENERALSETTINGSOVERRIDDEN` entitásmező értéke például *Nem*, de új vagy módosított értékeket adó fájlt importál a mezőkhöz (például `PRODUCTCOVERAGEGROUPID` és/vagy `VENDORACCOUNTNUMBER`). Mivel ebben az esetben az `AREGENERALSETTINGSOVERRIDDEN` mező értéke *Nem*, az értékek automatikusan törlődnek a **Cikkfedezet** oldal importálás utáni első megnyitásakor. Ha az üzenetmező megjelenésekor menti a módosításokat, azok az adatbázisban tárolódnak. Ellenkező esetben az oldal következő megnyitásakor ugyanez az üzenet jelenik meg.

Ha meg szeretné akadályozni ezt a viselkedést, de szerepeltetni szeretné az értékeket a mezőkhöz (például `PRODUCTCOVERAGEGROUPID`) az entitásimportáláson keresztül, akkor az importáláskor az `AREGENERALSETTINGSOVERRIDDEN` értékeként az *Igent* adja meg.
