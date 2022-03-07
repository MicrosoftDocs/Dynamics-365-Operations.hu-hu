---
title: IoT Intelligencia figyelése és kezelése
description: Ez a témakör azt mutatja be, hogyan lehet felügyelni és kezelni az IoT Intelligencia alkalmazást.
author: robinarh
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 94665b3646456b689a8e65e94b098e86e467d5e3
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813075"
---
# <a name="monitor-and-manage-iot-intelligence"></a>IoT Intelligencia figyelése és kezelése

[!include [banner](../../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet felügyelni és kezelni az IoT Intelligencia alkalmazást.

## <a name="monitor-scenarios-in-microsoft-dynamics-365-supply-chain-management"></a><a id="monitor-scenarios"></a>A Microsoftnál Dynamics 365 Supply Chain Management forgatókönyveinek figyelése

A IoT Intelligencia feldolgozását több helyen is nyomon követheti:

+ **Modulok \> Gyártásvezérlés \> Lekérdezések és jelentések \> IoT Intelligencia \> Értesítések** – A feloldatlan értesítések listájának megjelenítése.
+ **Modulok \> Gyártásvezérlés \> Lekérdezések és jelentések \> IoT Intelligencia \> Lezárt értesítések** – A megoldott vagy elvetett értesítések listájának megjelenítése.
+ **Modulok \> Gyártásvezérlés \> Lekérdezések és jelentések \> IoT Intelligencia \> Mérőszám-kulcsok** – Az **Erőforrás állapota** idősorozat-diagramok mérőszám-kulcsainak megtekintése.
+ **Modulok \> Gyártásvezérlés \> Gyártásvégrehajtás \> Erőforrás állapota** – Adott mérőszámok nyomon követése a **Konfigurálás** párbeszédpanel segítségével. Ha egy forgatókönyv kivételt észlel, akkor az értesítés a kivétel részleteit jeleníti meg.
+ **Munkaterületek \> Termelési szint kezelése \> Értesítések** – A feloldatlan értesítések listájának megjelenítése.

## <a name="modify-a-running-iot-intelligence-scenario"></a>Futó IoT Intelligencia forgatókönyv módosítása

Ha egy forgatókönyv fut, akkor ezeket a változtatásokat hajthatja végre:

+ Új érzékelőséma-definíciók hozzáadása.
+ Új jeladatértékek kiválasztása.
+ A meglévő jeladatértékek kiválasztásának törlése.
+ Új jeladatértékek hozzáadása és leképezése.
+ Küszöbértékek frissítése.

Ha egy forgatókönyv fut, akkor ezek a változtatások tiltottak:

+ Az engedélyezett forgatókönyv által jelenleg fogyasztott sémadefiníciók törlése vagy módosítása.
+ Az engedélyezett forgatókönyv kiválasztott sémaelérési útjainak módosítása.

## <a name="simulation-options"></a>Szimulációs lehetőségek

Szimulálhatja a gyári gépek jeleit. További részletekért lásd ezeket a témaköröket:

+ [IoT DevKit AZ3166 csatlakoztatása az Azure IoT-központhoz](https://docs.microsoft.com/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-get-started)
+ [Raspberry Pi online szimulátor csatlakoztatása az Azure IoT-központhoz (Node.js)](https://docs.microsoft.com/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started)
+ [Eszközszimulációs megoldás gyorsító – áttekintés](https://docs.microsoft.com/azure/iot-accelerators/iot-accelerators-device-simulation-overview)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]