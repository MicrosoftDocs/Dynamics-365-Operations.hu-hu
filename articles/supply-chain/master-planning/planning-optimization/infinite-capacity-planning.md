---
title: Ütemezés végtelen kapacitással
description: Ez a témakör a tervezési optimalizálás korlátlan kapacitásütemezésével kapcsolatban tartalmaz tájékoztatást. Az aktuális funkciókorlátozásokat is leírja.
author: ChristianRytt
ms.date: 09/21/2021
ms.topic: article
ms.search.form: RouteInventProd
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 9c1eef91bcf7d1ce6379e87417be5a8b3be069e5
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7575632"
---
# <a name="scheduling-with-infinite-capacity"></a>Ütemezés végtelen kapacitással

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

A *Tervezés optimalizálása végtelen kapacitásütemezéssel* szolgáltatás bemutatja az útvonal-információkon alapuló ütemezést. Lehetővé teszi feladatok ütemezését az útvonal-beállítások széles tartománya alapján. A tervezésoptimalizálás ütemezése a gyakran használt útvonal-beállításokat, többek között az útvonalművelet-sorrendet vagy az útvonalművelet-erőforrásokra vonatkozó követelményeket foglalja magában.

## <a name="turn-on-the-infinite-capacity-scheduling-feature"></a>A korlátlan kapacitásütemezési funkció bekapcsolása

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a [funkciókezelési](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Alaptervezés modul*
- **Funkció neve:** *Végtelen kapacitásütemezés a tervezési optimalizáláshoz*

Ezzel a funkcióval kapcsolatos további tudnivalókat lásd: [Ütemezés erőforrás-kijelöléssel képesség alapján](capability-based-scheduling.md).

## <a name="added-functionality"></a>Hozzáadott funkcionalitás

A *Tervezés optimalizálása végtelen kapacitásütemezéssel* szolgáltatás lehetővé teszi az útvonal-információkon alapuló ütemezést. Ennek megfelelően az útvonal-beállítás felhasználható a termelési folyamatok ütemezésére. Bár ennek a funkciónak vannak korlátai, amelyekkel a beépített alaptervezés nem rendelkezik, a gyártási helyzetekben szükséges leggyakoribb funkciókat támogatja.

A funkció az *egyszerű útvonalakat* és az *útvonalhálózatokat* egyaránt figyelembe veszi. Egy útvonalművelet **Következő** mezőjének használatával összetett útvonalakat állíthat be, amelyek több kezdőponttal és több párhuzamosan futó művelettel kapcsolatosak. A rendszer az ütemezés során az ilyen típusú összetett útvonalszerkezeteket veszi figyelembe.

Ezenkívül a funkció támogatja az útvonalak *párhuzamos műveleteit* is. Az útvonalműveletek **Prioritás** mezőjében az *elsődleges* és a *másodlagos* beállítás megadhatja azt az útvonalszerkezetet, ahol az egyik útvonalművelet elsődleges, a másik pedig másodlagos. A rendszer az ütemezés során ebben az esetben az ilyen típusú összetett útvonalszerkezeteket veszi figyelembe.

Az ütemezési folyamat során a rendszer figyelembe veszi a műveletekhez meghatározott *erőforrásigényeket* is. A rendszer az erőforrásigényekkel határozza meg, hogy mely erőforrások szükségesek a művelet végrehajtásához. A *Végtelen kapacitás ütemezése a tervezési optimalizáláshoz* funkció jelenleg a következő erőforrás-követelménytípusokat támogatja:

- Erőforrás típusa
- Erőforrás
- Erőforráscsoport
- Képesség (További tudnivalókat lásd: [Ütemezés erőforrás-kijelöléssel képesség alapján](capability-based-scheduling.md).)

> [!NOTE]
> Az emberi erőforrásokkal kapcsolatos követelmények, például a szakértelem vagy a tanúsítványkövetelmények még nem támogatottak.

A funkció a **beállítási idő** és a **futási idő** üzemeltetési tulajdonságait is támogatja. Amikor ezeket a tulajdonságokat egy útvonalművelethez beállítja, az ütemezési folyamat létrehozza a megfelelő beállítási és folyamat feladatokat.

Összegzésként a Tervezési optimalizálás ütemezése támogatja a leggyakrabban használt eseteket. Létrehozhatja az útvonalat, hozzáadhat elsődleges és másodlagos műveleteket, meghatározhat következő műveleteket, erőforrás-követelményeket adhat hozzá, valamint beállítási és futási időt adhat hozzá. A rendszer ezt követően figyelembe veszi ezt az információt az ütemezés során.

## <a name="limitations"></a>Korlátozások

A tervezési optimalizálási ütemezés használata esetén a következő korlátozások érvényesek:

- A funkció csak a végtelen kapacitást támogatja.
- A funkció nem támogatja az erőforrás-terhelési funkciókat.
- A funkció nem veszi figyelembe az útvonalselejtezést.
- A szolgáltatás csak elsődleges erőforrás-kijelölésként támogatja az *időtartamot*.

Ne feledje, hogy a *Végtelen kapacitás ütemezése a tervezési optimalizáláshoz* funkció folyamatosan tökéletesített. A Microsoft várhatóan a későbbi verziókban további ütemezési beállításokat fog támogatni.
