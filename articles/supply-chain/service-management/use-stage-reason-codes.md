---
title: Szakasz okkódjainak használata
description: Okkód használatával jelezheti, hogy miért történt egy szolgáltatásiszint-szerződés visszavonása, vagy egy szervizrendelés miért lépte túl a szolgáltatásiszint-szerződésben megadott időkorlátot.
author: sorenva
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 06c2b6a2b338dbfdbecdeb75e12fa1c20af8e56d
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8669516"
---
# <a name="use-stage-reason-codes"></a>Szakasz okkódjainak használata 

[!include [banner](../includes/banner.md)]


Okkód használatával jelezheti, hogy miért történt egy szolgáltatásiszint-szerződés visszavonása, vagy egy szervizrendelés miért lépte túl a szolgáltatásiszint-szerződésben megadott időkorlátot.

Előírhatja, hogy okkódot kell megadni a szolgáltatásiszint-szerződés visszavonásakor, vagy ha a szervizrendelés túllépi a szolgáltatásiszint-szerződésben megadott időkorlátot.

Ha előírta az okkód használatát, akkor a következő esetekben kötelező az okkód megadása:

  - Ha a szervizrendelés olyan fokozatba került, amelyben leáll a kapcsolódó szolgáltatásiszint-szerződésben beállított határ elérését figyelő időrögzítés.

  - Ha megtörténik a szervizrendelés láttamozása.

  - Ha manuálisan leállítják az időrögzítést.

## <a name="set-up-reason-codes"></a>Okkódok beállítása

1.  Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **Szervizrendelések** \> **Fokozat okkódjai** elemre.

2.  Az **Állapot okkódjai** képernyőn új okkód létrehozásához kattintson az **Új** elemre.

3.  Az **Állapot okkódjai** mezőbe írjon be egy egyedi okkódot a fokozathoz.

4.  A **Leírás** mezőbe írja be a fokozat okkódjának leírását.

5.  A módosítások mentéséhez zárja be a képernyőt.

## <a name="require-reason-codes-when-a-service-level-agreement-is-canceled"></a>Okkódok megkövetelése szolgáltatásiszint-szerződés visszavonása esetén

1.  Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **Szolgáltatáskezelési paraméterek** pontra.

2.  A **Szolgáltatáskezelés paraméterei** képernyőn, kattintson az **Általános** hivatkozásra, és jelölje be az **Okkód visszavonás esetén** jelölőnégyzetet.

## <a name="require-reason-codes-when-the-a-service-order-exceeds-the-time-limit-that-is-set-by-the-service-level-agreement"></a>Okkódok előírása, ha a szervizrendelés túllépi a szolgáltatásiszint-szerződésben beállított időhatárt

1.  Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **Szolgáltatáskezelési paraméterek** pontra.

2.  A **Szolgáltatáskezelés paraméterei** képernyőn, kattintson az **Általános** hivatkozásra, és jelölje be az **Okkód időtúllépés esetén** jelölőnégyzetet.

## <a name="see-also"></a>Lásd még

[Szervizrendeléshez kapcsolódó időrögzítés elindítása és leállítása](start-and-stop-time-recording-on-a-service-order.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]