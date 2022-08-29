---
title: A IoT Intelligencia beépülő modul telepítése az LCS-ben
description: Ez a cikk bemutatja, hogy hogyan telepíthető az Online intelligencia bővítmény a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásba.
author: johanhoffmann
ms.date: 08/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e18b05be1f2ba78c71515e4e76f180355d044b98
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2022
ms.locfileid: "9227834"
---
# <a name="install-the-iot-intelligence-add-in-in-lcs"></a>A IoT Intelligencia beépülő modul telepítése az LCS-ben

[!include [banner](../../includes/banner.md)]
[!INCLUDE [iot-sdi-announcement](../../includes/iot-sdi-announcement.md)]

Ez a cikk bemutatja, hogy hogyan telepíthető az Online intelligencia bővítmény a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásba. Ne felejtse el, hogy a bővítmények nem telepíthetők bemutató/próbaverziós környezetbe. A bővítmény telepítése előtt [létre kell hoznia az Azure-erőforrásokat](iot-azure-setup.md).

Az IoT-intelligenciát kód írása nélkül is be lehet állítani és lehet konfigurálni. Az alapvető lépések a következők.

1. [Azure-erőforrások beállítása](iot-azure-setup.md) – Egy IoT-központ, egy Redis Cache és egy olyan kulcstartó beállítása, amely elérhető a Supply Chain Management alkalmazásból.
2. [Üzenetsémák formátumai az IoT Huboz](iot-schema-format.md)– Állítsa be az eszközök úgy, hogy üzeneteket küldjenek az IoT Hubba, és definiálja a JavaScript Object Notation (JSON) üzenetformátumot.
3. A Funkciókezelés helyen engedélyezze az IoT-intelligencia funkciójelölőt.
4. Az IM-intelligenciához bővítmény telepítése a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban – telepítse a bővítményt az LCS-be, és konfigurálja az Azure-bővítményeket (a jelen cikknek megfelelően).
5. [Metrikák beállítása](iot-metrics-setup.md) – Metrikák beállítása a Supply Chain Management alkalmazásban.
6. [Eset beállítása](iot-scenario-setup.md) – Az eseteket a Supply Chain Management alkalmazásban állíthatja be.

## <a name="set-up-the-lcs-environment"></a>Az LCS-környezet beállítása

1. Nyissa meg az LCS-t, majd nyissa meg a Microsoft Dynamics 365 Supply Chain Management-környezetét.
2. Görgessen le a **Környezeti bővítmények** szakaszhoz.
3. Válassza az **Új bővítmény telepítése** lehetőséget a környezetben engedélyezett bővítmények listájának megjelenítéséhez.
4. A **Telepítendő bővítmény kiválasztása** párbeszédpanelen válassza ki az **IoT Intelligencia** elemet.
5. Adja meg az IoT-központ és a Redis-gyorsítótár adatait a **Bővítmények beállítása** párbeszédpanelen. A szükséges értékek megtalálhatók a kulcstárban, amelyet az [Azure-erőforrások létrehozása](iot-azure-setup.md) részben hozott létre.

    + **Bérlő azonosítója** – Az Azure portálon nyissa meg a kulcstárolót, majd kattintson a bal oldali navigációs ablak **Áttekintés** elemére, és másolja át a **Címtár-azonosító** értékét. Illessze be ezt az értéket a **Bővítmény beállítása** párbeszédpanelbe.
    + **IoT-eseményközponttal kompatibilis végpont kulcstároló URI-azonosítója** – Lépjen a kulcstárolóra, majd a bal oldali navigációs ablakban válassza az **Áttekintés** parancsot, majd másolja át a **DNS-név** értékét. Illessze be ezt az értéket a **Bővítmény beállítása** párbeszédpanelbe.
    + **IoT-eseményközponttal kompatibilis végpont titkos kódjának neve** – Lépjen a kulcstárolóhoz, majd a bal oldali navigációs ablakban válassza ki a **Titkos kód** lehetőséget, majd másolja a titkos kód nevét oda, ahol az IoT-központ eseményközpont-kapcsolati karaktersorozata tárolva van. Illessze be ezt az értéket a **Bővítmény beállítása** párbeszédpanelbe.
    + **Redis-gyorsítótár kulcstároló URI-azonosítója** – Lépjen a kulcstárolóra, majd a bal oldali navigációs ablakban válassza az **Áttekintés** parancsot, majd másolja át a **DNS-név** értékét. Illessze be ezt az értéket a **Bővítmény beállítása** párbeszédpanelbe.
    + **Redis-gyorsítótár végpont titkos kódjának neve** – Lépjen a kulcstárolóhoz, majd a bal oldali navigációs ablakban válassza ki a **Titkos kód** lehetőséget, majd másolja a titkos kód nevét oda, ahol a Redis-gyorsítótár kapcsolati karaktersorozata tárolva van. Illessze be ezt az értéket a **Bővítmény beállítása** párbeszédpanelbe.

6. Jelölje be a jelölőnégyzetet az Általános Szerződési Feltételek elfogadásához.
7. Válassza a **Telepítés** parancsot.
8. Megjelenik egy üzenet, amely azt jelzi, hogy a "Bővítmény sikeresen aktiválva telepítésre." Válassza ki az **OK** lehetőséget.

Az LCS-beállítás befejeződött. A következő lépés a [forgatókönyvek beállítása](iot-scenario-setup.md).

## <a name="uninstall-the-add-in"></a><a id="uninstall-addin"></a>A bővítmény eltávolítása

1. A Supply Chain Management alkalmazásban [tiltsa le a forgatókönyveket](iot-scenario-setup.md#disable-a-scenario).
2. Az LCS-ben lépjen a Supply Chain Management környezet részleteihez.
3. Görgessen le a **Környezeti bővítmények** szakaszhoz.
4. Válassza az **Eltávolítás** lehetőséget az IoT Intelligencia beépülő modul esetén.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]