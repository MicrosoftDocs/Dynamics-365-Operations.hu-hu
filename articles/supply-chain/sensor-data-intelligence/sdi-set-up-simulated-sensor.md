---
title: Szimulált készlet beállítása teszteléshez
description: Ez a témakör azt ismerteti, hogyan lehet beállítani egy olyan szimulátort, amely fizikai eszköz telepítése nélkül tesztelheti a intelligens adatintelligencia teszteket.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: edfa20bec7438124844f8b6afa91ca4941b6bb56
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/08/2022
ms.locfileid: "9429014"
---
# <a name="set-up-a-simulated-sensor-for-testing"></a>Szimulált készlet beállítása teszteléshez

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Ha fizikai tárgyak telepítése nélkül szeretné tesztelni a Intelligens adatintelligencia szolgáltatást, *a Pi Azure Azure Online szimulátor* szolgáltatás segítségével emulálhatja a életjeleket, és elküldheti őket az Internet of Things (ITató) megoldáshoz Microsoft Azure. A szimulátorról bővebben lásd [a Pin Pi online szimulátor összekapcsolása az Azure Azure IOt központtal (Node.js) való kapcsolatot](/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started).

## <a name="create-a-device-in-azure-iot-hub"></a>Eszköz létrehozása az Azure Azure-központban

Előbb be kell állítania egy eszközt, hogy hitelesítse az Azure IOnT-központnak küldhető jelzőt.

1. Az Azure szolgáltatásban ugrás annak az erőforráscsoportnak az erőforráscsoportja számára, amely a Belső adatintelligencia szolgáltatásban való használatra van létrehozva. (További tájékoztatás: [Az Azure platformra telepített Ionét-megoldás](sdi-deploy-iot-solution-on-azure.md).)
1. Az erőforráslistán keresse meg **azt a rekordot, amelyben a Típus** mező *beállítása Az ionközpont*. A Név **oszlopban** válassza ki az erőforrás részletes adatait tartalmazó lapot.
1. Válassza az Eszközök lehetőséget **a bal oldali navigációs ablakban**.
1. Az Eszközök **lapon** válassza az Eszköz hozzáadása **lehetőséget**.
1. Az Eszköz **létrehozása lapon** állítsa be a következő mezőket:

    - **Eszközazonosító** – adja meg az új eszköz nevét (*például I-Ion-eszköz*).
    - **Hitelesítés típusa** – válassza a szimmetrikus *kulcsokat*.
    - **Kulcsok automatikus létrehozása** – jelölje be ezt a jelölőnégyzetet.
    - **Az eszköz csatlakoztatása Egy Olyan Központhoz, amely az Eszközt használja** – válassza az Engedélyezés *lehetőséget*.

1. Az Eszközök **lapra** való visszatéréshez **válassza a Mentés** lehetőséget.
1. Az új eszköz megkeresve a listában. Válassza ki az **eszközazonosító** oszlopban azt a nevet, amelybe a részletes adatokat tartalmazó lapot meg kell nyitni. Ha nem látja az új eszközt a listában, frissítse az oldalt.
1. Az elsődleges kapcsolati **karakterlánc értékének** másolása (például a Másolás a vágólapra **gomb** használatával). Erre az értékre a későbbiekben lesz szüksége, amikor beállítják a Pinán pi ionokátor-szimulátort a életjeleket emulálják. Ezért most fontolja meg egy szövegfájlba történő beillesztését.

## <a name="add-the-azure-connection-string-to-the-raspberry-pi-iot-simulator"></a>Az Azure-kapcsolati karakterlánc hozzáadása a Pi és Azszony-szimulátorhoz

A következő lépések szerint add hozzá a csatlakozási karakterláncot az Azure Azure-központi eszközről a Parancsfájl szolgáltatás parancsfájlja számára.

1. [A Pin Pi Ion szimulátor megnyitása](https://azure-samples.github.io/raspberry-pi-web-simulator/)
1. A kódszerkesztő ablakban keresse meg a következő parancsot tartalmazó sort.

    `const connectionString = '[Your IoT hub device connection string]';`

1. A súgószöveg,beleértve a zárójeleket is, **cseréje** az előző szakaszba másolt elsődleges kapcsolati karakterlánc értékre. Az eredmény az alábbi példához hasonlóan jelenik meg.

    `const connectionString = 'HostName=XXX;DeviceId=YYY;SharedAccessKey=ZZZ';`

## <a name="add-sensor-ids-and-values-to-the-payload-in-the-raspberry-pi-iot-simulator"></a>Bővítmény-értékeket és értékeket ad hozzá a rakományhoz a Pi Pi pi szimulátorban.

Ezzel be kell állítania a Pi Pi Pi szimulátort szimulált mérőmérőivel és a rakományként küldött értékekkel.

- Keresse meg és szerkessze a függvényt a Pi Pi Pi szimulátor `getMessage` kódszerkesztőjével, és módosítsa úgy, hogy megegyezzon a következő kóddal. (A mérők a sorokban vannak beállítva `cb()` .)

    ```cpp
    function getMessage(cb) {
        messageId++;
        sensor.readSensorData()
        .then(function (data) {
            cb(JSON.stringify({ value: 1, sensorId: 'MachineStatus' }), false);
            cb(JSON.stringify({ value: 70, sensorId: 'Quality' }), false);
            cb(JSON.stringify({ value: 1, sensorId: 'AssetMaintenance' }), false);
            cb(JSON.stringify({ value: 1, sensorId: 'ProductionDelay' }), false);
            cb(JSON.stringify({ value: 20, sensorId: 'AssetDowntime' }), false);
        })
        .catch(function (err) {
            console.error('Failed to read out sensor data: ' + err);
        });
    }
    ```

    > [!IMPORTANT]
    > A Pi Pi szimulátor kódszerkesztője által definiált fogatizék-kódoknak meg kell egyezniük az Ellátásilánc-kezelés eszközben később az esetekhez majd megadott szabálysértés-kóddal. Az előző példakód az emberi olvasásra is használható mérőszámokat használja. A tényleges helyzetben azonban a gyári gyártó által biztosított globálisan egyedi azonosító (GUID) értékek lesznek. Az ebben a példakódban használt, az emberi olvasásra is használható biztonsági kódok a termékminőségi helyzet, az eszköz-karbantartási helyzet, [...](sdi-scenario-product-quality.md)[...](sdi-scenario-asset-maintenance.md)[a](sdi-scenario-production-delays.md) termelés késleltetési esete és a gép állapotának esete esetében használatosak.[...](sdi-scenario-equipment-downtime.md) Ezért akkor használja ezt a kódot, ha végig fogja dolgozni ezeket az eseteket.

## <a name="edit-the-interval-for-sending-sensor-signals"></a>Jelzők küldési időközének szerkesztése

Most be kell állítania azt az intervallumot, amelynél a333777-szimulátornak küldenie kell a emulált életjeleket.

1. A Pi Pi Pi szimulátor kódszerkesztőben keresse meg a következő függvényhívást.

    `setInterval(sendMessage, 2000);`

2. Alapértelmezés szerint a Pi IOnó szimulátor 2000 ezredmásodpercben (két másodpercben) küld egy rádiójelet. Az érték szükség szerint módosítható.

## <a name="run-the-raspberry-pi-iot-simulator"></a>A Pin Pi-szimulátor futtatása

- A **futtatás** lehetőséget választva elindíthatja a szimulátort, és megkezdheti a szimulált szimulációs adatokat küldeni.
