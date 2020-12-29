---
title: Karbantartási ütemezés
description: Ez a cikk az Eszközkezelés karbantartási ütemezését ismerteti.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectCalendarCreateWO, EntAssetObjectCalendarListPagePoolsOpen, EntAssetObjectCalendarListPage, EntAssetObjectCalendarListPagePreviewPart, EntAssetObjectCalendarEdit, EntAssetObjectCalendarAdjust, EntAssetObjectCalendarDiscard, EntAssetObjectCalendarInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 351e088ece0512fee1bb5f9dad020f32f7728fe4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429549"
---
# <a name="maintenance-schedule"></a>Karbantartási ütemezés

[!include [banner](../../includes/banner.md)]

 

A karbantartási ütemezésben az elvárt és végrehajtandó megelőző karbantartási tervek, a karbantartási kérések és karbantartási körök találhatók. Lehetséges, hogy néhány ütemezési sort munkarendelésekké alakítottak.

A karbantartási ütemezés négy nézete némileg különbözik, attól függően, hogy melyik karbantartási ütemezési sort szeretné megtekinteni.

| Menüelem                  | A tartalmak leírása                                                                                                                                             |
|----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Összes karbantartási ütemezés       | A karbantartási ütemezés minden sora látható.     |
| Saját eszközütemezés        | Ebben a listában a karbantartási ütemezés összes olyan sora látható, amely olyan munkavégzési helyszíneken telepített eszközöket tartalmaz, ahova Ön dolgozóként kapcsolódik (ezt a [Karbantartási dolgozók és dolgozói csoportok](../setup-for-objects/workers-and-worker-groups.md) részen kell beállítani). |
| Karbantartási ütemezési sorok megnyitása | Ebben a listában a „Létrehozva” állapotú karbantartási ütemezési sorok láthatók. Ez az állapot azt jelenti, hogy ezek a sorok még nem lettek munkarendeléssé alakítva vagy elvetve.                                            |
| Karbantartási ütemezési gyűjtők megnyitása | Ebben a listában láthatók a munkarendelési gyűjtőhöz kapcsolódó karbantartási ütemezési sorok.                                                                                                                  |

>[!NOTE]
>Ha a karbantartási ütemezés egy sora több munkarendelési gyűjtőben is szerepel (lásd: [Munkarendelés-gyűjtők](../work-orders/work-order-pools.md)), akkor minden gyűjtőhöz egy rekord jelenik meg a **Nyitott karbantartási ütemezési csoportok** részen. Ez a munkarendelés-gyűjtők szűrési beállításainak optimalizálására szolgál.

Karbantartási ütemezés megnyitása:

1. Kattintson az **Eszközkezelés** > **Közös** > **Karbantartási ütemezés** > **Összes karbantartási ütemezés** vagy **Nyitott karbantartási ütemezési sorok** vagy **Nyitott karbantartási ütemezési csoportok** elemre.

2. A karbantartási ütemezés frissítéséhez kattintson a **Karbantartási terv** vagy a **Karbantartási körök** elemre. 

3. A karbantartási ütemezési sor szerkesztéséhez jelölje ki a sort, és kattintson a **Szerkesztés** elemre. Egyszerűen frissítheti például a szolgáltatási szintet vagy a feladatért felelős dolgozót. A karbantartási ütemezésnek csak azok a sorai szerkeszthetők, amelyek még nem kapcsolódnak munkarendeléshez.

4. A karbantartási ütemezési sor törléséhez jelölje ki a sort a listaoldalon, és kattintson a **Törlés** gombra.

5. A karbantartási ütemezési sor elvetéséhez jelölje ki a sort a listaoldalon, és kattintson az **Elvetés** gombra. Ez a funkció akkor hasznos, ha például egy eszköz egy 2000 km-es és egy 10 000 km-es karbantartási tervvel is rendelkezik. Ekkor érdemes lehet elvetni a 2000 km-es karbantartási tervből létrehozott sort, ha az egyezik a 10 000 (vagy 20 000 vagy 30 000) km-es terv sorával. Ha egy karbantartási tervhez kapcsolódó karbantartási ütemezési sort elvet, akkor az a sor többet nem fog megjelenni az adott karbantartási terv ütemezésekor.

6. Ha azt szeretné, hogy minden kiválasztott sor szerepeljen ugyanabban a munkarendelési gyűjtőben, akkor válassza ki a karbantartási ütemezés több sorát az **Összes karbantartási ütemezés** részen, és kattintson a **Munkarendelés-gyűjtő** elemre.

7. Ha több sorhoz szeretné végrehajtani ugyanazt a módosítást, akkor válassza ki a karbantartási ütemezés több sorát az **Összes karbantartási ütemezés** vagy a **Nyitott karbantartási ütemezési sorok** vagy a **Nyitott karbantartási ütemezési csoportok** részen, majd kattintson az **Ütemezés kiigazítása** elemre. A kiválasztott karbantartási ütemezési soroknál módosíthatja a várt kezdési és befejezési dátumot, a szolgáltatási szintet, valamint a karbantartási dolgozók felelős csoportját vagy a felelős karbantartási dolgozót.

- Amikor egy karbantartási ütemezési sor egy munkarendeléshez kapcsolódik, a munkarendelés azonosítója jelenik meg a **Munkarendelés** mezőben.  
- A **Minden eszköz** részletes nézet > **Eszköz karbantartási tervei** gyorslapon kiválaszthatja az eszköz karbantartási terveit. Ha később törli az eszközhöz kapcsolódó karbantartási terv egyik sorát az **Összes eszköz** részen, akkor automatikusan törlődik a karbantartási terv összes „Létrehozott” állapotú sora, amely az adott karbantartási terv alapján jött létre. Lásd még: [Eszköz létrehozása](../objects/create-an-object.md).

Az alábbi ábra az **Összes karbantartási ütemezés** listaoldalt mutatja.

![1. ábra](media/16-preventive-maintenance.png)

