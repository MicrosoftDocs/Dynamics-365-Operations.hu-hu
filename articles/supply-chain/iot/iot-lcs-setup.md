---
title: A IoT Intelligencia beépülő modul telepítése az LCS-ben
description: Ez a témakör bemutatja, hogyan telepítheti az IoT Intelligencia beépülő modult a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban.
author: robinarh
manager: AnnBe
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: ''
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 04333b3659f090b15cc0d0ee216f14dabc588883
ms.sourcegitcommit: 261b70ea358b2c231e20f320ed8bd6adc1e7d715
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/19/2020
ms.locfileid: "3386521"
---
# <a name="install-the-iot-intelligence-add-in-in-lcs"></a>A IoT Intelligencia beépülő modul telepítése az LCS-ben

[!include [banner](../../includes/banner.md)]

Ez a témakör bemutatja, hogyan telepítheti az IoT Intelligencia beépülő modult a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban. A bővítmény telepítése előtt [létre kell hoznia az Azure-erőforrásokat](iot-azure-setup.md).

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

1. A Supply Chain Management alkalmazásban [tiltsa le a forgatókönyveket](iot-scenario-setup.md#how-to-disable-a-scenario).
2. Az LCS-ben lépjen a Supply Chain Management környezet részleteihez.
3. Görgessen le a **Környezeti bővítmények** szakaszhoz.
4. Válassza az **Eltávolítás** lehetőséget az IoT Intelligencia beépülő modul esetén.
