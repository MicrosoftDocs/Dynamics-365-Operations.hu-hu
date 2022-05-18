---
title: Az IoT-központ üzeneteinek sémaformátumai
description: Ez a témakör azt mutatja be, hogyan kell megtervezni egy üzenetsémát, hogy használhassa az IoT-intelligenciát.
author: johanhoffmann
ms.date: 04/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-04-25
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 60d5bc4eacdd7e7d713490998bd1d20c9271ad02
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8673942"
---
# <a name="schema-formats-for-iot-hub-messages"></a>Az IoT-központ üzeneteinek sémaformátumai

[!include [banner](../../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan kell megtervezni egy üzenetsémát, hogy használhassa az IoT-intelligenciát.

## <a name="message-requirements"></a>Üzenetkövetelmények

Az IoT-intelligenciában az üzenetek megfigyelésére a következő szabályok érvényesek:

+ Az üzenetsémáknak JavaScript Object Notation (JSON) formátumúnak kell lennie.
+ Egy UNIX **időbélyegző** tulajdonságnak, ahol az érték ezredmásodpercben (ms) van kifejezve, jelen kell lennie az Microsoft Azure IoT Hub üzenetben.
+ A program csak akkor követi nyomon az üzeneteket, ha az eset beállításaiban meghatározott összes tulajdonságot tartalmazzák. Ha például **azonosító**, **időbélyeg** és **érték** tulajdonságokat ad meg, a rendszer a következő üzenetet figyeli.

    ```json
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True
    }
    ```

    Ez az üzenet nem figyelt, mert hiányzik az **érték** tulajdonság.

    ```json
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
    }
    ```

+ Az IoT-intelligencia figyelmen kívül hagyja az üzenet olyan tulajdonságait, amelyek nincsenek megadva az eset konfigurációjában. Ha például **azonosító**, **időbélyeg** és **érték** tulajdonságokat ad meg, az IoT-intelligencia a következő üzeneteket figyeli.

    ```json
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True
    },
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True,
        "machine" : "Machine1225",
    },
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True,
         "activity": "PartOut"
    },
    ```

+ Az IoT-intelligencia csendes módon figyelmen kívül hagyja az eset konfigurációs feltételeinek nem megfelelő üzeneteket.
+ Többféle üzenetsémát határozhat meg és használhat.
+ Nem kell minden típusú üzenetsémát definiálni. Csak az IoT-intelligenciával használatos sémákat kell definiálni.

## <a name="id-value-pair-schema"></a>Azonosító-érték pár séma

Az azonosító-érték pár az IoT-intelligencia üzenetsémák gyakori közös mintája. Az azonosítóérték párok használatával gondoskodik arról, hogy az üzenetsémák minden esetben azonosak legyenek. Például egy üzenet jelenik meg a **Berendezés leállása** vagy **Termelési késleltetések** esetre.

```json
{
    "id": "IoTInt.Machine1225.PartOut",
    "timestamp": 1576016821614,
    "value": True
}
```

A **Termékminőségi** helyzetre vonatkozó üzenet.

```json
{
    "id": "IoTInt.Machine1225.Temperature",
    "timestamp": 1576016821614,
    "value": 105
}
```

A megelőző üzenetek mind **azonosító**, mind **érték** tulajdonságokat tartalmaznak. Az **azonosító** értékeket az eset beállítása során a **Jeladatok értékei** táblába lehet hozzárendelni. A **Berendezés leállása** eset esetén a Következő érték lesz leképezve: **IoTInt.Machine1225.PartOut**. A **Termék minősége** eset esetén a Következő érték lesz leképezve: **IoTInt.Machine1225.Temperature**.

További részletek a [Azure IoT Hub dokumentáció](/azure/iot-hub/) részben találhatók.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]