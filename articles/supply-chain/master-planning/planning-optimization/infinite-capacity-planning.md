---
title: Ütemezés végtelen kapacitással
description: Ez a cikk a tervezési optimalizálás korlátlan kapacitásütemezésével kapcsolatban tartalmaz tájékoztatást. Az aktuális funkciókorlátozásokat is leírja.
author: t-benebo
ms.date: 08/09/2022
ms.topic: article
ms.search.form: RouteInventProd
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: c6e0190899abb544b559bb5f26ba974155989c3a
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335315"
---
# <a name="scheduling-with-infinite-capacity"></a>Ütemezés végtelen kapacitással

[!include [banner](../../includes/banner.md)]

A *Tervezés optimalizálása végtelen kapacitásütemezéssel* szolgáltatás bemutatja az útvonal-információkon alapuló ütemezést. Lehetővé teszi feladatok ütemezését az útvonal-beállítások széles tartománya alapján. A tervezésoptimalizálás ütemezése a gyakran használt útvonal-beállításokat, többek között az útvonalművelet-sorrendet vagy az útvonalművelet-erőforrásokra vonatkozó követelményeket foglalja magában.

## <a name="turn-the-infinite-capacity-scheduling-feature-on-or-off"></a>A korlátlan kapacitásütemezési funkció be- és kikapcsolása

A funkció használatához be kell kapcsolva lennie a rendszeren. Az Ellátásilánc-kezelés 10.0.29-es verziója szerint a funkció alapértelmezés szerint be van kapcsolva. A rendszergazdák úgy *kapcsolhatják*[be és kapcsolják ki ezt a funkciót, hogy a Szolgáltatáskezelés munkaterület Korlátlan kapacitásütemezési tervezési optimalizálási szolgáltatását](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) keresi.

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
>
> - Ha az erőforrás és/vagy az erőforráscsoport végtelen kapacitásra van állítva, az alaptervezés végtelen kapacitásnak fogja venni őket.
> - Az emberi erőforrásokkal kapcsolatos követelmények, például a szakértelem vagy a tanúsítványkövetelmények még nem támogatottak.

A funkció a **beállítási idő** és a **futási idő** üzemeltetési tulajdonságait is támogatja. Amikor ezeket a tulajdonságokat egy útvonalművelethez beállítja, az ütemezési folyamat létrehozza a megfelelő beállítási és folyamat feladatokat.

Összegzésként a Tervezési optimalizálás ütemezése támogatja a leggyakrabban használt eseteket. Létrehozhatja az útvonalat, hozzáadhat elsődleges és másodlagos műveleteket, meghatározhat következő műveleteket, erőforrás-követelményeket adhat hozzá, valamint beállítási és futási időt adhat hozzá. A rendszer ezt követően figyelembe veszi ezt az információt az ütemezés során.

## <a name="limitations"></a>Korlátozások

A tervezési optimalizálási ütemezés használata esetén a következő korlátozások érvényesek:

- A funkció csak a végtelen kapacitást támogatja.
- A funkció nem támogatja az erőforrás-terhelési funkciókat.
- A funkció nem veszi figyelembe az útvonalselejtezést.
- A szolgáltatás csak elsődleges erőforrás-kijelölésként támogatja az *időtartamot*.

Ne feledje, hogy a *Végtelen kapacitás ütemezése a tervezési optimalizáláshoz* funkció folyamatosan tökéletesített. A Microsoft várhatóan a későbbi verziókban további ütemezési beállításokat fog támogatni.
