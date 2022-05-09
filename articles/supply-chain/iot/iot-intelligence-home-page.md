---
title: IoT-intelligencia kezdőlapja
description: Ez a témakör az IoT-intelligenciával kapcsolatos információkra mutató hivatkozásokat tartalmaz.
author: tonyafehr
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: tfehr
ms.custom: intro-internal
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2020-04-25
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5c587f4e6a1dd58a7b8c238fc5afb16774828b2a
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644386"
---
# <a name="iot-intelligence-home-page"></a>IoT-intelligencia kezdőlapja

[!include [banner](../../includes/banner.md)]

> [!IMPORTANT]
> Ez a funkció a jelenleg csak a következő országokban és régiókban érhető el:
>
> - US (Amerikai Egyesült Államok)
> - EU (Európai Unió)
> - AU (Ausztrália)
> - CA (Kanada)
> - UK (Egyesült Királyság)

Az IoT-intelligencia a Microsoft Dynamics 365 Supply Chain Management bővítménye. Integrálja az eszközök internetes hálózata (IoT) jeleit a Supply Chain Management adataival, hogy használható információkat hozzon létre.

A IoT-intelligencia a következő eseteket támogatja:

- **Termelési késések** – Ez az eset a tényleges ciklusidőt hasonlítja össze a tervezett ciklusidővel. A Supply Chain Management értesíti, ha a termelés nincs ütemben, így bevatkozással elérhető a maximális üzemi hatékonyság, és így elkerülhető a rendelési késés.
- **Berendezés leállása** – Ez az eset a mért üzemidőt hasonlítja össze a felhasználó által megadott paraméterekkel. A Supply Chain Management figyelmezteti, ha egy leállási küszöbértéket túllépnek, így lépéseket tehet, például a termelési munkarendelések újraütemezését vagy karbantartási munkarendelés létrehozását.
- **Termékminőség** – Ez a eset összehasonlítja a szenzorértékeket, mint például a páratartalom és a hőmérséklet, és összeveti a felhasználó által megadott minőségi mérőszámokkal. A Supply Chain Management értesíti, ha eltérés történik, így beavatkozhat, hogy fenntartsa a miőségi szabványokat minimálira csökkentse a hulladék mennyiségét.

Az alábbi ábra az Azure IoT Hub, IoT-intelligencia és a Supply Chain Management együttműködését mutatja be.

![IoT Hub, IoT-intelligencia és Supply Chain Management.](media/iot_intelligence.png)

<!-- KFM: hide setup info for now

## Setup

You can set up and configure IoT Intelligence without writing any code. Here are the basic steps.

1. [Set up Azure resources](iot-azure-setup.md) – Create an IoT hub, a Redis cache, and a key vault that can be accessed from Supply Chain Management.
2. [Message schema formats for IoT Hub](iot-schema-format.md) – Configure your devices to send messages to IoT Hub, and define the JavaScript Object Notation (JSON) message format.
3. In Feature Management, enable the IoT Intelligence feature flag. 
4. [Install the IoT Intelligence add-in in Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md) – Install the add-in in LCS, and configure the Azure secrets.
5. [Set up metrics](iot-metrics-setup.md) – Set up metrics in Supply Chain Management.
6. [Scenario setup](iot-scenario-setup.md) – Set up the scenarios in Supply Chain Management.

-->

## <a name="tracking-and-maintenance"></a>Követés és karbantartás

- [Forgatókönyvek figyelése a Dynamics 365 Supply Chain Management alkalmazásban](iot-management.md#monitor-scenarios)
- [Forgatókönyv letiltása](iot-scenario-setup.md#disable-a-scenario)
- [Futó IoT Intelligencia forgatókönyv módosítása](iot-management.md#modify-a-running-iot-intelligence-scenario)
- [Szimulációs lehetőségek](iot-management.md#simulation-options)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]