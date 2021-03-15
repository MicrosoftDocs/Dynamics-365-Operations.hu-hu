---
title: Raktári alkalmazás eseményei
description: Ez a témakör a raktári alkalmazáson belüli események feldolgozását mutatja be, melyet a raktári alkalmazás eseményüzeneteinek egy kötegelt feladat részeként való feldolgozására használhatnak.
author: perlynne
manager: tfehr
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileDeviceQueueEvent
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 66a5ca8a679563b59ca23992f7e0b4ee6fab470b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993803"
---
# <a name="warehouse-app-event-processing"></a>Raktári alkalmazás eseményeinek feldolgozása

[!include [banner](../includes/banner.md)]

A Supply Chain Management modulban futtatott kötegelt feladatok felhasználhatják a raktári alkalmazás által kiadott feldolgozási eseményekhez küldött várólistához tartozó adatokat annak érdekében, hogy a jelzett eseményekre szükséges módon lehessen reagálni. Ez a funkció a dolgozók által, az alkalmazással végrehajtott bizonyos művelettípusokra válaszul megfelelő eseményeket adnak a várólistához. Ez történik például akkor, amikor a **Raktári alkalmazásból átmozgatási rendelések létrehozása és feldolgozása** funkciót használják, és az átmozgatási rendelés fejléce és sorai a háttérben jönnek létre és frissülnek, mialatt a rendszer a **Raktári alkalmazás eseményeinek feldolgozása** kötegelt feladatot futtatja.

## <a name="enable-the-process-warehouse-app-events-feature"></a>A Raktári alkalmazás eseményeinek feldolgozása funkció engedélyezése

A funkció használata előtt engedélyeznie kell a saját rendszerében. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) oldalt a funkció állapotának ellenőrzéséhez, és szükség esetén engedélyezéséhez. A Raktári alkalmazás eseményeinek feldolgozása funkció a következő felsorolásban szerepel:

- **Modul:** Raktárkezelés
- **Funkció neve** – Raktári alkalmazás eseményeinek feldolgozása

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

A raktári alkalmazás által létrehozott esemény-várólistát és eseményüzeneteket a **Raktárkezelés \> Lekérdezések és jelentések \> Mobileszköznaplók \> Raktári alkalmazás eseményei** menüpontba lépve tekintheti meg.

## <a name="the-standard-event-queue-process"></a>A szokásos esemény-várólista folyamata

A raktári alkalmazások eseményeinek várólistája általában a következő folyamatban használható:

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