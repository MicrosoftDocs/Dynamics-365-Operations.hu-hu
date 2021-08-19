---
title: Ütemezés végtelen kapacitással
description: Ez a témakör a tervezési optimalizálás korlátlan kapacitásütemezésével kapcsolatban tartalmaz tájékoztatást. Az aktuális funkciókorlátozásokat is leírja.
author: crytt
ms.date: 6/9/2021
ms.topic: article
ms.search.form: RouteInventProd
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fc40dc2bcf1969e4c566b624a9425638e69ab2a17892f035aeabb74068aadd14
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718972"
---
# <a name="scheduling-with-infinite-capacity"></a>Ütemezés végtelen kapacitással

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

A *Tervezés optimalizálása végtelen kapacitásütemezéssel* szolgáltatás bemutatja az útvonal-információkon alapuló ütemezést. Lehetővé teszi feladatok ütemezését az útvonal-beállítások széles tartománya alapján. A tervezésoptimalizálás ütemezése a gyakran használt útvonal-beállításokat, többek között az útvonalművelet-sorrendet vagy az útvonalművelet-erőforrásokra vonatkozó követelményeket foglalja magában.

## <a name="turn-on-the-infinite-capacity-scheduling-feature"></a>A korlátlan kapacitásütemezési funkció bekapcsolása

Ha a rendszer még nem tartalmazza az ebben a témakörben leírt funkciókat, nyissa meg a [Funkciókezelés](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet, és a kapcsolja be a *Tervezés optimalizálása végtelen kapacitásütemezéssel* funkciót.

## <a name="added-functionality"></a>Hozzáadott funkcionalitás

A *Tervezés optimalizálása végtelen kapacitásütemezéssel* szolgáltatás lehetővé teszi az útvonal-információkon alapuló ütemezést. Ennek megfelelően az útvonal-beállítás felhasználható a termelési folyamatok ütemezésére. Bár ennek a funkciónak vannak korlátai, amelyekkel a beépített alaptervezés nem rendelkezik, a gyártási helyzetekben szükséges leggyakoribb funkciókat támogatja.

A funkció az *egyszerű útvonalakat* és az *útvonalhálózatokat* egyaránt figyelembe veszi. Egy útvonalművelet **Következő** mezőjének használatával összetett útvonalakat állíthat be, amelyek több kezdőponttal és több párhuzamosan futó művelettel kapcsolatosak. A rendszer az ütemezés során az ilyen típusú összetett útvonalszerkezeteket veszi figyelembe.

Ezenkívül a funkció támogatja az útvonalak *párhuzamos műveleteit* is. Az útvonalműveletek **Prioritás** mezőjében az *elsődleges* és a *másodlagos* beállítás megadhatja azt az útvonalszerkezetet, ahol az egyik útvonalművelet elsődleges, a másik pedig másodlagos. A rendszer az ütemezés során ebben az esetben az ilyen típusú összetett útvonalszerkezeteket veszi figyelembe.

Az ütemezési folyamat során a rendszer figyelembe veszi a műveletekhez meghatározott *erőforrásigényeket* is. A rendszer az erőforrásigényekkel határozza meg, hogy mely erőforrások szükségesek a művelet végrehajtásához. A *Végtelen kapacitás ütemezése a tervezési optimalizáláshoz* funkció jelenleg a következő erőforrás-követelménytípusokat támogatja:

- Erőforrás típusa
- Erőforrás
- Erőforráscsoport
- Képesség

> [!NOTE]
> Az emberi erőforrásokkal kapcsolatos követelmények, például a szakértelem vagy a tanúsítványkövetelmények még nem támogatottak.

A funkció a **beállítási idő** és a **futási idő** üzemeltetési tulajdonságait is támogatja. Amikor ezeket a tulajdonságokat egy útvonalművelethez beállítja, az ütemezési folyamat létrehozza a megfelelő beállítási és folyamat feladatokat.

Összegzésként a Tervezési optimalizálás ütemezése támogatja a leggyakrabban használt eseteket. Létrehozhatja az útvonalat, hozzáadhat elsődleges és másodlagos műveleteket, meghatározhat következő műveleteket, erőforrás-követelményeket adhat hozzá, valamint beállítási és futási időt adhat hozzá. A rendszer ezt követően figyelembe veszi ezt az információt az ütemezés során.

## <a name="limitations"></a>Korlátozások

A tervezési optimalizálási ütemezés használata esetén a következő korlátozások érvényesek:

- A funkció csak a feladatütemezést támogatja. A műveletütemezéshez kapcsolódó beállítások az ütemezés során nem számítanak, az alaptervek ütemezési módszerétől függetlenül.
- A funkció csak a végtelen kapacitást támogatja.
- A funkció nem támogatja az erőforrás-terhelési funkciókat.
- A funkció nem veszi figyelembe az útvonalselejtezést.
- A szolgáltatás csak elsődleges erőforrás-kijelölésként támogatja az *időtartamot*.

Ne feledje, hogy a *Végtelen kapacitás ütemezése a tervezési optimalizáláshoz* funkció folyamatosan tökéletesített. A Microsoft várhatóan a későbbi verziókban további ütemezési beállításokat fog támogatni.
