---
title: Kifizetési ütemezések beállítása TDS-felosztással
description: Ez a témakör elmagyarázza, hogyan állíthatja be a fizetési ütemezéseket a Forrásnál levont adóval (TDS) történő felosztással.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 63628e84da4e430df236f3afa89110b652110fcb
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2022
ms.locfileid: "8726605"
---
# <a name="set-up-payment-schedules-with-tds-allocation"></a>Kifizetési ütemezések beállítása TDS-felosztással

[!include [banner](../includes/banner.md)]

Ez a témakör elmagyarázza, hogyan állíthatja be a fizetési ütemezéseket a Forrásnál levont adóval (TDS) történő felosztással.

1. Ugrás a **Kötelezettségek \> Kifizetés beállítása \> Kifizetés ütemezése** elemre.

    [![Kifizetési ütemezések oldal.](./media/apac-ind-TDS-27.png)](./media/apac-ind-TDS-27.png)

2. A Műveletablakban válassza az **Új** lehetőséget a kifizetési ütemezés létrehozásához, és adja meg a szükséges adatokat.
3. A **Felosztás** mezőben válassza ki a fizetési ütemezéshez szükséges fizetési mód felosztásának módját:

    - Teljes
    - Rögzített összeg
    - Rögzített mennyiség
    - Meghatározott

    Az **Adóelőleg-felosztás** mező a fizetési ütemezés TDS-felosztási módját mutatja. Ha a **Felosztás** mezőben az **Összes** lehetőséget választja, az **Adóelőleg-felosztás** mező automatikusan az **Összes** mezőre lesz állítva. Ha a **Fix összeg**, **Fix mennyiség** vagy a **Meghatározott** lehetőséget választja a **Felosztás** mezőben, az **Adóelőleg-felosztás** mező automatikusan **Arányosra** lesz beállítva.

    > [!NOTE]
    > Ha az **Adóelőleg-felosztás** mező az **Összes** értékre van állítva, a fizetési részletek kiszámítása a bruttó összeg alapján történik, amely tartalmazza a TDS-összegét. Ha az **Adóelőleg-felosztás** mező az **Arányosan** értékre van állítva, a fizetési részletek kiszámítása a nettó számla alapján történik, a TDS-összeg levonását követően.

4. Adja meg a többi kötelező adatot, majd zárja be az oldalt.
