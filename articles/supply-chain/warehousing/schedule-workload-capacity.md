---
title: Ütemezés terhelési kapacitása
description: Ez a témakör bemutatja, hogyan lehet beállítani és ütemezni a raktárban dolgozók vagy egy teljes raktár terhelési kapacitását.
author: MarkusFogelberg
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSWorkloadCapacity
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fd4225d9e7ad65939c57cb770ba521377c87dea3
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3217264"
---
# <a name="schedule-workload-capacity"></a>Ütemezés terhelési kapacitása

[!include[banner](../includes/banner.md)]

A raktárak esetében lehetősége van terhelési kapacitás ütemezésére, és a jelenlegi és jövőbeli terhelés meghatározására az egyes raktárakat illetően. Akár az egész raktár terhelését, vagy a bejövő és kimenő terhelést külön-külön is meghatározhatja.

A kiválasztott raktárak terhelésének meghatározása érdekében elérhetővé kell tenni a raktárak alapütemezésre vonatkozó adatait. További informáciért lásd: [Alaptervek áttekintése](../master-planning/master-plans.md).

## <a name="schedule-and-view-workloads-for-a-warehouse"></a>Egy adott raktár terhelésének ütemezése és megtekintése

A raktár terhelési kapacitásának ütemezése érdekében hozzon létre terhelési beállítást egy vagy több raktárhoz, majd társítsa a terhelési beállítást egy alaptervvel. A terhelési kapacitás beállítása során meghatározható a súly vagy a mennyiség határértéke a bejövő és kimenő tranzakciókra nézve. Az egyes raktárak esetében több beállítás is létrehozható, ezt követően pedig a beállítás egyéni alaptervekkel társítható. Előfordulhat például, hogy ezzel a megközelítéssel a munkaerő szezonális változásaihoz igazodik.

Ha az alkalmazottak egy adott raktárban a bejövő és kimenő tranzakciókkal is foglalkoznak, a raktározási kapacitás beállítása úgy is konfigurálható, hogy a terhelés kombinált nézetben legyen meghatározva.

A raktárak terhelésének ütemezése és megtekintése érdekében hajtsa végre az alábbi lépéseket:

1. Hozzon létre terhelésikapacitás-beállítást, és határozza meg a terhelési kapacitás határértékeit egy vagy több raktár esetében.
2. Terhelési előrejelzések meghatározása, valamint az előrejelzések hosszának megbecslése érdekében társítsa a terhelésikapacitás-beállítást alaptervvel.

### <a name="create-a-workload-capacity-setup-for-a-warehouse"></a>Terhelésikapacitás-beállítás létrehozása raktár esetében

1. Válassza ki **Készletkezelés** \> **Beállítás** \> **Raktárfigyelés** \> **Terhelési kapacitás**.
2. Jelölje be a műveleti ablakban az **Új** lehetőséget a terhelési kapacitás beállításának létrehozásához.
3. Kattintson a képernyő **Raktárak** gyorslapján található **Új** elemre, majd adja meg az értékeket a raktár terhelésikapacitás-beállításhoz történő társítása érdekében.
4. Jelölje be a **Kombinált bejövő és kimenő terhelést** jelölőnégyzetet, ha a **Terhelési kapacitás** jelentés jelenítse meg a bejövő és kimenő tranzakciók teljes terhelését egy nézetben.
5. A **Tranzakciótípusok** gyorslapon jelölje be azokat a bejövő és kimenő tranzakciótípusokat, amelyekre a terhelési határértékek vonatkozni fognak.

    > [!NOTE]
    > Legalább egy tranzakciótípust ki kell jelölnie mind a bejövő, mind a kimenő terhelésekre nézve.

#### <a name="define-limits-for-volume-or-weight"></a>Térfogat vagy tömeg korlátjának meghatározása

Raklapok, mennyiség vagy súly esetében is megadhat határértékeket attól függően, hogy milyen korlátozások vonatkoznak a raktárban dolgozó munkaerőre. A megadott határértékek szerepelnek a terhelési kapacitás előrejelzésében, amelyek a **Terhelési kapacitás** jelentésben tekinthetők meg.

A cikkekhez szükséges mennyiséggel és súllyal kapcsolatos adatok előrejelzéséhez minden termék esetében meg kell adni a raklapok szabványos típusát, a készletcikk mennyiségét, valamint egy készletcikk súlyát. A szükséges mezők a következő mezőcsoportokban érhetők el a **Készlet kezelése** gyorslapján a **Kiadott termék részletei** lapnak:

- Kezelés
- Tényleges dimenziók
- Tömeg mérése

Ha ez az információ nincs megfelelően megadva, a rendszer üzenetet küld a **Terhelési kapacitás** jelentés létrehozásakor. A jelentésből lekérdezhetők azok az adatok, amelyek hiányoznak és szükségesek a jövőbeli terhelés előrejelzéséhez.

### <a name="associate-a-workload-capacity-setup-with-a-master-plan"></a>Terhelésikapacitás-beállítás társítása alaptervvel

1. Válassza ki ezt: **Készletkezelés** \> **Időszakos** \> **Terhelés ütemezése**.
2. Az **Alapterv** mezőben jelölje ki a terhelés előrejelzéseihez használni kívánt alaptervet.
3. Adja meg a **Napok száma** mezőben a terhelés-előrejelzés által érintett napok számát.
4. Válassza ki a **Munkaterhelés** mezőben az alaptervvel társítandó terhelésbeállítást.

### <a name="view-workload-capacity"></a>Terhelési kapacitás megtekintése

1. Válassza ezt: **Készletkezelés** \> **Lekérdezések és jelentések** \> **Fizikai leltárjelentés** \> **Terhelési kapacitás**.
2. Adja meg az **Oszlopok száma** mezőben a jelentésben megjelenítendő oszlopok számát.
3. A **Rendelés típusa** mezőben válassza ki a **Tervezett és visszaigazolt**, **Tervezett** vagy **Visszaigazolt** annak a meghatározásához, hogy milyen típusú rendelések legyenek feltüntetve a jelentésben.
4. Válassza ki a **Terhelés típusa** mezőben a terhelés típusát annak meghatározása érdekében, hogy a terhelési kapacitást mennyiség vagy súly esetében kell-e előre jelezni.
5. Válassza ki a **Terhelési kapacitás** mezőben a terhelésikapacitás-beállítást.
