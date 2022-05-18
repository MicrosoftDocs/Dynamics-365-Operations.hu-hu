---
title: A IoT Intelligencia metrikáinak beállítása
description: Ez a témakör azt mutatja be, hogyan lehet metrikákat beállítani az IoT Intelligenciához.
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
ms.openlocfilehash: b67292e45746ee45460141b4be32f2f8f14076ad
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8674337"
---
# <a name="set-up-metrics-for-iot-intelligence"></a>A IoT Intelligencia metrikáinak beállítása

[!include [banner](../../includes/banner.md)]

## <a name="configure-metrics"></a>Metrikák konfigurálása

Ha meg szeretné tekinteni az üzeneteit a Microsoft Dynamics 365 Supply Chain Management alkalmazásban, a következő lépésekkel be kell állítania a metrikákat.

1. A Redis Cache kapcsolati karakterláncainak másolása:

    1. Az Azure portálon lépjen a Redis Cache elemhez.
    2. Ugrás a **Beállítások** \> **Hozzáférési kulcsok** elemre.
    3. Másolja az **Elsődleges kapcsolati karakterlánc** mező értékét.

2. A Supply Chain Management alkalmazásban lépjen a **Gyártásvezérlés \> Beállítás \> IoT Intelligencia \> Forgatókönyvparaméterek** lehetőségre.
3. A **Forgatókönyv paraméterei** oldal **Idősorok** lapján, a **Redis metrikus üzleti kapcsolati karakterlánc** mezőjébe másolja be a korábban másolt kapcsolati sztringet. Ez a lépés lehetővé teszi az Azure IoT Hub mérőszámainak vizuális megjelenítését a Supply Chain Management alkalmazásban. Amikor beilleszti az értéket a mezőbe, az a következőként jelenik meg: **\*\*\*\*\*\***.

    > [!NOTE]
    > Minden alkalommal, amikor frissít egy Redis Cache kapcsolati karakterláncot, frissítenie kell ezt a mezőt is.

4. Ugrás a **Gyártásvezérlés \> Lekérdezések és jelentések \> IoT intelligencia \> Metrikus kulcs** helyre.
5. A **Metrikus kulcsok** lapon válassza a **Frissítés** lehetőséget.
6. Figyelje meg, hogy a **Metrikus kulcsok frissítése** párbeszédpanelen a mezőben be van jelölve a **Futtatás a háttérben** beállítás. Válassza ki az **OK** lehetőséget.

A program beolvassa és hozzáadja a Redis Cache-ben található összes Metrikakulcsot a **Metrikakulcsok** listájához. A metrikaértékek csak a [forgatókönyvek engedélyezése](iot-scenario-setup.md) után jelennek meg.

## <a name="configure-the-resource-status-time-series"></a>Az Erőforrás-állapot idősorozatának konfigurálása

Az **Erőforrás-állapot** idősorozatának konfigurálásához hajtsa végre a következő lépéseket.

1. A Supply Chain Management alkalmazásban menjen a **Gyártásvezérlés \> Gyártásvégrehajtás \> Erőforrásának állapota** részbe.
2. Az **Erőforrás állapota** oldalon válassza a **Konfigurálás** lehetőséget.
2. A **Konfigurálás** párbeszédpanel **Erőforrás** listájában válassza ki a figyelni kívánt elemet.
3. Az **1. idősorozat** elemnél válassza a **Szerkesztés** gombot.
4. Az **Idősor kiválasztása** párbeszédpanelen válasszon ki egy metrikát a rácsban. (Használhatja **A metrikakulcsok frissítése** hivatkozást is a metrikakulcsoknak ezen a párbeszédpanelen való frissítéséhez.)
5. Az **OK** gombbal térjen vissza a **Konfigurálás** párbeszédpanelhez.
6. Adjon meg egy megjelenítendő nevet.
7. A Mező **Adatok megjelenítése innen** mezőben válasszon ki egy időkeretet.
8. Válassza ki az **OK** lehetőséget.

Megjelenik a diagram.

## <a name="delete-a-metric-key"></a>Metrikakulcs törlése

1. A Supply Chain Management alkalmazásban ugorjon a **Gyártásvezérlés \> Lekérdezések és jelentések \> IoT intelligencia \> Metrikakulcs** helyre.
2. A **Metrikakulcsok** lapon válassza ki a törölni kívánt metrikakulcsot.
3. Válassza a **Törlés** lehetőséget.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]