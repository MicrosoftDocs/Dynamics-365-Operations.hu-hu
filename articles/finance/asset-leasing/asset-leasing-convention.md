---
title: Eszközlízingelési konvenciók
description: Ez a témakör a lízingbe adott eszközökre vonatkozó konvenciókat írja le.
author: moaamer
manager: Ann Beebe
ms.date: 1/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetLease
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2021-1-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: ea89d54f1ce3a1e971d41623bf44f909f7dfdf09
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/06/2021
ms.locfileid: "5131287"
---
# <a name="asset-leasing-conventions"></a>Eszközlízingelési konvenciók

[!include [banner](../includes/banner.md)]

Ez a témakör a lízingbe adott eszközökre vonatkozó konvenciókat írja le. A lízingelési konvenciók segítségével lehet meghatározni egy lízingkönyv kezdő dátumát. Ha a lízingmegállapodás értéke **Nincs**, a kezdő dátum megegyezik a lízing kezdő dátumának dátumával (amely a **Lízing kezdő dátuma** mező értéke). Ha a lízingmegállapodás beállítása **Teljes hónap**, a kezdési dátum annak a hónapnak az első napja, amelybe a lízing kezdő dátuma esik.

A kezdő dátum határozza meg a kötelezettség amortizációja és az eszköz értékcsökkenése ütemezésének időszakának kezdő dátumát. A kamatráfordítási és értékcsökkenési kiadások feladása a megfelelő ütemezések időszakának záró dátumával történik. A kezdeti megjelenítés és a naplóbejegyzés kiigazításának feladása a kezdő dátum napján kezdődik.

> [!NOTE]
> A lízingelési konvenciókkal kapcsolatos funkciót be kell kapcsolni a Funkciókezelés segítségével. A **Funkciókezelés** munkaterületen keresse meg és válassza ki az **Eszközkezelési lízingelési konvenciók** funkciót, majd válassza ki az **Engedélyezés most** lehetőséget.

A lízingelési konvenciókat a lízingeszköz-könyv beállításaihoz rendeli hozzá a program.

A következő lépéseket követve tekintse meg vagy rendelje hozzá a lízingelési konvenciót.

1. Nyissa meg az **Eszközlízing \> Beállítás \> Lízingkönyvek** lehetőséget.
2. A **Lízingelési konvenció** mezőben válassza a következő értékek egyikét:

    | Lízingmegállapodás | Leírás |
    |--------------------|-------------|
    | None               | A kötelezettség amortizációjának és az eszköz értékcsökkenésének ütemezése a lízing kezdő dátumával kezdődik, mivel a kezdő dátum megegyezik a lízing kezdő dátumával. A záró dátum egy hónappal később van. Ez a lízingelési konvenció nem garantálja a kamat feladását minden hónap utolsó napján. |
    | Teljes hónap         | Olyan lízingek esetén, amelyek kezdő dátuma a hónap bármely napján esedékes, a kötelezettség amortizációjának és az eszköz értékcsökkenésének ütemezései az adott hónap első napján kezdik el a kiadásokat elhatárolni. Ez a lízingelési konvenció gondoskodik arról, hogy a kamatot minden hónap utolsó napján elhatárolják az egész hónapra. |

3. Válassza a **Mentés** lehetőséget.

Lízing létrehozásakor minden egyes könyv kezdő dátumát a program automatikusan beírja a lízinghez megadott kezdő dátum és a könyvhöz megadott lízingelési konvenció alapján.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]