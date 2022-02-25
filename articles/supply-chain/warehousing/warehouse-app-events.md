---
title: Raktári alkalmazás eseményei
description: Ez a témakör a raktári alkalmazáson belüli események feldolgozását mutatja be, melyet a raktári alkalmazás eseményüzeneteinek egy kötegelt feladat részeként való feldolgozására használhatnak.
author: perlynne
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileDeviceQueueEvent
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 8c92bf179006d668f8673e9abc3419a10e644184
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103263"
---
# <a name="warehouse-app-event-processing"></a>Raktári alkalmazás eseményeinek feldolgozása

[!include [banner](../includes/banner.md)]

A Supply Chain Management modulban futtatott kötegelt feladatok felhasználhatják a Raktárkezelés mobilalkalmazás által kiadott feldolgozási eseményekhez küldött várólistához tartozó adatokat annak érdekében, hogy a jelzett eseményekre szükséges módon lehessen reagálni. Ez a funkció a dolgozók által, az alkalmazással végrehajtott bizonyos művelettípusokra válaszul megfelelő eseményeket adnak a várólistához. Ez történik például akkor, amikor a *Raktári alkalmazásból átmozgatási rendelések létrehozása és feldolgozása* funkciót használják, és az átmozgatási rendelés fejléce és sorai a háttérben jönnek létre és frissülnek, mialatt a rendszer a **Raktári alkalmazás eseményeinek feldolgozása** kötegelt feladatot futtatja.

## <a name="turn-the-process-warehouse-app-events-feature-on-or-off"></a>A Raktári alkalmazásesemények feldolgozása funkció be- és kikapcsolása

Az Ellátásilánc-kezelés 10.0.25-ös verziója szerint ez a funkció alapértelmezés szerint be van kapcsolva. A rendszergazdák úgy *kapcsolhatják*[be és kapcsolják ki ezt a funkciót, hogy a Szolgáltatáskezelési munkaterület Raktári események feldolgozása szolgáltatását keresi](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a>Kötegelt feladat létrehozása a raktári alkalmazás eseményeinek feldolgozásához

### <a name="process-warehouse-app-events"></a>Raktári alkalmazás eseményeinek feldolgozása

Ütemezett kötegelt feladat beállítása a raktári alkalmazás eseményeinek feldolgozásához, az átmozgatási rendelés létrehozása és sor frissítése céljából.

1. Lépjen a **Raktárkezelés \> Ismétlődő feladatok \> Raktári alkalmazás eseményeinek feldolgozása** menüpontra.
1. Megjelenik a Raktári alkalmazás eseményeinek feldolgozása párbeszédpanel. Nyissa meg a **Futtatás a háttérben** gyorslapot, majd állítsa a **Kötegelt feldolgozást** **Igen** értékre.
1. A **Futtatás a háttérben** gyorslapon válassz az **Ismétlődés** elemet.
1. Megnyílik az **Ismétlődés meghatározása** párbeszédpanel. Az üzleti tevékenységének megfelelően állítsa be a futási ütemezést.
1. Az **OK** gomb kiválasztásával visszatérhet a **Raktári alkalmazás eseményeinek feldolgozása** párbeszédpanelhez.
1. Válassza az **OK** gombot a **Raktári alkalmazás eseményeinek feldolgozása** párbeszédpanelen a kötegelt feladat kötegelt várólistájához adásához.

## <a name="query-warehouse-app-events"></a>A raktári alkalmazás eseményeinek lekérdezése

A Raktárkezelés mobilalkalmazás által létrehozott esemény-várólistát és eseményüzeneteket a **Raktárkezelés \> Lekérdezések és jelentések \> Mobileszköznaplók \> Raktári alkalmazás eseményei** menüpontba lépve tekintheti meg.

## <a name="the-standard-event-queue-process"></a>A szokásos esemény-várólista folyamata

A raktári alkalmazás eseményeinek várólistája általában a következő folyamatban használható:

1. Egy esemény jelenik meg a várólistán egy eseményüzenettel. Az új üzenet kezdetben **Várakozó** eseményállapottal rendelkezik, amely azt jelenti, hogy a **Raktári alkalmazás eseményeinek feldolgozása** kötegelt feladat nem veszi fel és dolgozza fel ezt az üzenetet.
1. Amint az üzenet **Várólistán** állapotra vált át, a **Raktári alkalmazás eseményeinek feldolgozása** kötegelt feladat felveszi és feldolgozza az eseményt.
1. A kötegelt feladat az eseményállapotokat **Befejezett** vagy **Sikertelen** állapotra változtatja attól függően, hogy a kért folyamat végrehajtható volt-e.
1. Amikor az összes kapcsolódó eseményüzenet **Befejezett** állapotra vált át, a program törli az eseményt a várólistából.

 Részletesebb példáért lásd: [Átmozgatási rendelés létrehozása a raktári alkalmazás folyamatából](create-transfer-order-from-warehouse-app.md).

## <a name="handle-event-errors"></a>Eseményhibák kezelése

A raktári események feldolgozása részeként a kért üzenettevékenység nem kaphat folyamatot a kötegelt feladatból. Ebben az esetben az eseményüzenet **Sikertelen** állapotra vált át. A **Kötegnapló** adataival megtudhatja, hogy miért és milyen lépéseket kell tenni a problémák orvoslására.

Részletesebb példáért lásd: [Átmozgatási rendelés létrehozása a raktári alkalmazásból](create-transfer-order-from-warehouse-app.md).

Sikertelen raktári alkalmazáson belüli eseményüzenet alaphelyzetbe állítása:

1. Lépjen a **Raktárkezelés \> Lekérdezések és jelentések \> Mobileszközök naplói \> Raktári alkalmazás eseményei** menüpontba.
1. A **Raktári alkalmazás eseményüzenetei** gyorsfülön megkeresheti és kiválaszthatja azt a kapcsolódó eseményt, amely **Sikertelen** állapotot mutat az **Eseményállapot** oszlopban.
1. Válassza ki az **Alaphelyzetbe állítás** elemet a **Raktári alkalmazás eseményüzenetei** eszköztárból.
1. Folytassa a munkát mindaddig, amíg az összes fontos üzenetet alaphelyzetbe nem állítja.

A **Sikertelen** eseményüzenetet a **Raktári alkalmazás eseményüzenetei eszköztár** **Törlés** opciójával is el lehet távolítani.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]