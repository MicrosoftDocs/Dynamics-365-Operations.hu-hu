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
ms.openlocfilehash: 6b6c179052cdb9d1ca808d9cba089163bde0d5d5
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/10/2021
ms.locfileid: "7782681"
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

+ **Termelési késések** – Ez az eset a tényleges ciklusidőt hasonlítja össze a tervezett ciklusidővel. A Supply Chain Management értesíti, ha a termelés nincs ütemben, így bevatkozással elérhető a maximális üzemi hatékonyság, és így elkerülhető a rendelési késés.
+ **Berendezés leállása** – Ez az eset a mért üzemidőt hasonlítja össze a felhasználó által megadott paraméterekkel. A Supply Chain Management figyelmezteti, ha egy leállási küszöbértéket túllépnek, így lépéseket tehet, például a termelési munkarendelések újraütemezését vagy karbantartási munkarendelés létrehozását.
+ **Termékminőség** – Ez a eset összehasonlítja a szenzorértékeket, mint például a páratartalom és a hőmérséklet, és összeveti a felhasználó által megadott minőségi mérőszámokkal. A Supply Chain Management értesíti, ha eltérés történik, így beavatkozhat, hogy fenntartsa a miőségi szabványokat minimálira csökkentse a hulladék mennyiségét.

Az alábbi ábra az Azure IoT Hub, IoT-intelligencia és a Supply Chain Management együttműködését mutatja be.

![IoT Hub, IoT-intelligencia és Supply Chain Management.](media/iot_intelligence.png)

## <a name="setup"></a>Beállítás

Az IoT-intelligenciát kód írása nélkül is be lehet állítani és lehet konfigurálni. Az alapvető lépések a következők.

1. [Azure-erőforrások beállítása](iot-azure-setup.md) – Egy IoT-központ, egy Redis Cache és egy olyan kulcstartó beállítása, amely elérhető a Supply Chain Management alkalmazásból.
2. [Üzenetsémák formátumai az IoT Huboz](iot-schema-format.md)– Állítsa be az eszközök úgy, hogy üzeneteket küldjenek az IoT Hubba, és definiálja a JavaScript Object Notation (JSON) üzenetformátumot.
3. A Funkciókezelés helyen engedélyezze az IoT-intelligencia funkciójelölőt. 
4. [A Microsoft Dynamics LCS (Lifecycle Services) Szolgáltatásban telepítse az IoT-intelligencia bővítményt](iot-lcs-setup.md) – Telepítse a bővítményt az LCS-be, és konfigurálja az Azure-titkos kódjait.
5. [Metrikák beállítása](iot-metrics-setup.md) – Metrikák beállítása a Supply Chain Management alkalmazásban.
6. [Eset beállítása](iot-scenario-setup.md) – Az eseteket a Supply Chain Management alkalmazásban állíthatja be.

## <a name="tracking-and-maintenance"></a>Követés és karbantartás

+ [Forgatókönyvek figyelése a Dynamics 365 Supply Chain Management alkalmazásban](iot-management.md#monitor-scenarios)
+ [Forgatókönyv letiltása](iot-scenario-setup.md#disable-a-scenario)
+ [A bővítmény eltávolítása](iot-lcs-setup.md#uninstall-addin)
+ [Futó IoT Intelligencia forgatókönyv módosítása](iot-management.md#modify-a-running-iot-intelligence-scenario)
+ [Szimulációs lehetőségek](iot-management.md#simulation-options)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]