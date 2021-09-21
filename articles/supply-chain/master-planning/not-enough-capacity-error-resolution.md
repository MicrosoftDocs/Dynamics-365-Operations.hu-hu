---
title: A „Nem található elegendő kapacitás" ütemezési motorhiba megoldása
description: 'Ez a témakör a információt nyújt az okoról és megoldásokról ehhez: „A(z) %1 termelési rendelés nem ütemezhető. Nem található elegendő kapacitás" ütemezési motorhibát.'
author: crytt
ms.date: 7/29/2021
ms.topic: article
ms.search.form: ProdTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-19
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 37c990067a0c175d93ecf298866041f4d2afc1bc
ms.sourcegitcommit: ab1455c67f6ee6ca36bec148bea0dbb0f7704eda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/26/2021
ms.locfileid: "7428933"
---
# <a name="fix-the-not-enough-capacity-could-be-found-scheduling-engine-error"></a>A „Nem található elegendő kapacitás" ütemezési motorhiba megoldása

[!include [banner](../includes/banner.md)]

Az ütemezés futtatásakor következő hibaüzenet jelenhet meg:

> A(z) %1 termelési rendelés nem ütemezhető. Nem található elegendő kapacitás.

Számos oka lehet annak, hogy az ütemezési motor leállhat, és ezt a hibaüzenetet adja ki. Ez a témakör útmutatást biztosít, amely segít megtalálni a hiba okát, majd enyhíteni azt.

## <a name="review-the-applicable-resources"></a>A vonatkozó erőforrások áttekintése

Hiba léphet fel, ha egyetlen erőforrás sem felel meg a termelési rendelés telephelyén érvényes műveleti követelményeinek.

Kövesse az alábbi lépéseket a vonatkozó erőforrások áttekintéshez.

1. Lépjen a **Gyártásvezérlés \> Termelési rendelések \> Összes termelési rendelés** pontra, és nyissa meg vagy válassza ki a nem ütemezhető termelési rendelést.
1. A Műveleti ablaktáblán a **Termelési rendelés** lapon a **Termelés részletei** csoportban válassza az **Útvonal** lehetőséget.
1. A **Termelési útvonal** lapon válassza ki a műveletet, majd a műveleti ablakban válassza ki a **Vonatkozó erőforrásokat**.
1. A **Vonatkozó erőforrások** párbeszédpanelen állítsa be a **Követelmények használata ehhez:** mezőt *Műveletek ütemezése* vagy *Feladat ütemezése* lehetőségre, a használt ütemezés típusától függően.
1. Győződjön meg róla, hogy rendelkezésre állnak erőforrások a termelési rendelés telephelyén.

## <a name="review-the-calendars-that-are-associated-with-resources"></a>Az erőforrásokhoz társított naptárak áttekintése

Hiba akkor fordulhat elő, ha nincs naptár társítva az erőforráshoz vagy erőforráscsoporthoz, vagy ha a társított naptár nincs megfelelően beállítva (például nincsenek munkaidői, vagy ha a hatékonyság százalékos értéke 0 \[nulla\]).

A következő lépések szerint ellenőrizze, hogy van-e naptár társítva az erőforráshoz vagy erőforráscsoporthoz.

1. Lépjen a **Gyártásvezérlés \> Termelési rendelések \> Összes termelési rendelés** pontra, és nyissa meg vagy válassza ki a nem ütemezhető termelési rendelést.
1. A Műveleti ablaktáblán a **Termelési rendelés** lapon a **Termelés részletei** csoportban válassza az **Útvonal** lehetőséget.
1. A **Termelési útvonal** lapon válassza ki a műveletet, majd a műveleti ablakban válassza ki a **Vonatkozó erőforrásokat**.
1. Válassza ki az erőforrást a **Vonatkozó erőforrások** párbeszédpanelen, majd válassza az **Erőforrás megtekintése** lehetőséget. Másik lehetőségként jelölje ki és tartsa lenyomva (vagy kattintson a jobb gombbal) az **Erőforráscsoport** mezőben, majd válassza a **Részletek megtekintése** lehetőséget.
1. Az **Erőforrások** lapon vagy az **Erőforráscsoportok** lapon, a **Naptárak** gyorslapon győződjön meg arról, hogy van naptár társítva az erőforráshoz vagy erőforráscsoporthoz.

> [!NOTE]
> Ha a műveletütemezés során hiba történik, akkor minden vonatkozó erőforráscsoporthoz meg kell győződnie arról, hogy van-e naptár társítva.

A naptár beállításainak ellenőrzéshez kövesse az alábbi lépéseket.

1. Menjen a **Szervezeti felügyelet \> Beállítás \> Naptárak \> Naptárak** lapra, és válassza ki az erőforráshoz vagy erőforráscsoporthoz társított naptárat.
1. A Műveleti ablaktáblán kattintson a **Munkaidők** elemre.
1. A **Munkaidők** lapon győződjön meg arról, hogy a lap nem üres. Emellett a releváns napokra vonatkozóan ellenőrizze, hogy a **Vezérlő** mező ne legyen *Lezárt* értékre állítva, hogy léteznek munkaidők, és hogy a **Hatékonyság százalékérték** mező értéke nem *0* (nulla).

Ha a naptár az alapnaptárhoz van társítva, akkor az alapnaptár beállításait is át kell tekintse.

> [!NOTE]
> Műveletütemezésekor az erőforráscsoport naptára az egyes műveletek kezdő és befejező időpontjának és dátumának meghatározására szolgál. Azt is korlátozza, hogy a rendszer mennyi időt ütemezhet egy adott műveletre egy adott erőforráscsoport egy adott napja számára. Ha például egy adott erőforráscsoport munkaidői egy adott napon 8:00 és 14:00 között vannak, akkor az erőforráscsoporthoz egy művelet által betárolt munkaterhelés nem haladhatja meg a nyolc órába beférő munkaterhelést, függetlenül az adott erőforráscsoport adott napi elérhető kapacitásának mennyiségétől. A rendelkezésre álló kapacitás azonban tovább korlátozhatja a terhelést.

## <a name="review-the-scheduling-parameters"></a>Az ütemezési paraméterek ellenőrzése

A jó teljesítmény érdekében az ütemezési motor csak bizonyos időmennyiségre és bizonyos számú ütemezési ütközések esetén keres erőforrást.

Az ütemezési paraméterek ellenőrzéshez kövesse az alábbi lépéseket.

1. Lépjen a **Szervezeti adminisztráció \> Beállítás \> Ütemezési paraméterek** pontra.
1. Tegye a következők egyikét:

    - Ha az **Ütemezési időtúllépés engedélyezve van** beállítás értéke *Nem*, lépjen tovább a 3. lépésre.
    - Ha az **Ütemezési időtúllépés engedélyezve van** beállítás értéke *Igen*, növelje meg a **Maximális ütemezési idő sorozatonként** mező értékét, hogy több feldolgozási idő álljon rendelkezésre a befejezéshez.

1. Tegye a következők egyikét:

    - Ha az **Ütemezési optimalizálási időtúllépés engedélyezve van** beállítás értéke *Nem*, lépjen tovább a 4. lépésre.
    - Ha az **Ütemezési optimalizálási időtúllépés engedélyezve van** beállítás értéke *Igen*, növelje meg a **Optimalizálási próbálkozások időtúllépése** mező értékét, hogy több feldolgozási idő álljon rendelkezésre a befejezéshez.

1. Ha bármely beállítást módosított a lapon, ütemezze újra a rendelést, hogy újra próbálkozzon.

## <a name="review-capacity"></a>Kapacitás áttekintése

A hiba akkor fordulhat elő, ha véges ütemezést hajt végre, de nincs szabad kapacitás.

A korlátlan kapacitásütemezés végrehajtásához hajtsa végre ezeket a lépéseket.

1. Lépjen a **Gyártásvezérlés \> Termelési rendelések \> Összes termelési rendelés** pontra, és nyissa meg vagy válassza ki a nem ütemezhető termelési rendelést.
1. A Műveleti ablaktábla **Ütemezés** lapján, a **Termelési rendelés** csoportban válassza a **Műveletek ütemezése** vagy a **Feladatok ütemezése** lehetőséget.
1. A **Műveletek ütemezése** vagy **Feladatok ütemezése** párbeszédpanelen állítsa a **Véges kapacitás** beállítást *Nem* beállításra.
1. Válassza az **OK** lehetőséget a rendelés ütemezéséhez.

Az erőforrás rendelkezésre álló kapacitásának ellenőrzéséhez hajtsa végre a következő lépéseket.

1. Menjen a **Szervezeti felügyelet \> Erőforrások \> Erőforrások** lapra, és válassza ki az erőforrást, amely arra a rendelésre vonatkozik, amely nem ütemezhető.
1. A műveleti ablaktábla **Erőforrás** lapján a **Megtekintés** csoportban válassza a **Kapacitásterhelés** vagy a **Kapacitásterhelés grafikusan** elemet, és győződjön meg róla, hogy van elérhető kapacitás.

Az erőforráscsoport rendelkezésre álló kapacitásának ellenőrzéséhez hajtsa végre a következő lépéseket.

1. Menjen a **Szervezeti felügyelet \> Erőforrások \> Erőforráscsoportok** lapra, és válassza ki az erőforráscsoportot, amely arra a rendelésre vonatkozik, amely nem ütemezhető.
1. A műveleti ablaktábla **Erőforráscsoport** lapján a **Megtekintés** csoportban válassza a **Kapacitásterhelés** vagy a **Kapacitásterhelés grafikusan** elemet, és győződjön meg róla, hogy van elérhető kapacitás.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
