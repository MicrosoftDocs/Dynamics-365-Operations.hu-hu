---
title: Javítsa ki a "Nem elegendő kapacitás nem található" ütemezési motor hibát és véges kapacitást.
description: Ez a cikk a "Termelési rendelés nem %1 ütemező" okokkal és megoldásokkal kapcsolatban tartalmaz tájékoztatást. Nem található elegendő kapacitás" ütemezési motorhibát.
author: t-benebo
ms.date: 7/29/2021
ms.topic: article
ms.search.form: ProdTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-19
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d4f54c06a07b3cdd0b8fe2cc52614189ff31ba7f
ms.sourcegitcommit: 6b209919de39c15e0ebe4abc9cbcd30618f2af0b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/11/2022
ms.locfileid: "9135599"
---
# <a name="fix-the-not-enough-capacity-could-be-found-scheduling-engine-error"></a>A „Nem található elegendő kapacitás" ütemezési motorhiba megoldása

[!include [banner](../includes/banner.md)]

Az ütemezés futtatásakor következő hibaüzenet jelenhet meg:

> A(z) %1 termelési rendelés nem ütemezhető. Nem található elegendő kapacitás.

Számos oka lehet annak, hogy az ütemezési motor leállhat, és ezt a hibaüzenetet adja ki. Ez a témakör olyan irányelveket tartalmaz, amelyek segítenek megtalálni a hiba okát, majd enyhíteni azt.

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
1. A műveletpanel Erőforrás **lapján, a** **·** **Nézet** csoportban jelölje ki a Kapacitásterhelés vagy a Kapacitásterhelés lehetőséget grafikus formában, **és ellenőrizze, hogy van-e rendelkezésre álló kapacitás.**

Az erőforráscsoport rendelkezésre álló kapacitásának ellenőrzéséhez hajtsa végre a következő lépéseket.

1. Menjen a **Szervezeti felügyelet \> Erőforrások \> Erőforráscsoportok** lapra, és válassza ki az erőforráscsoportot, amely arra a rendelésre vonatkozik, amely nem ütemezhető.
1. A műveletpanel Erőforráscsoport lapján, **·** **·** **a Nézet csoportban jelölje ki a Kapacitásterhelés vagy a Kapacitásterhelés lehetőséget grafikus formában,** és ellenőrizze, hogy rendelkezésre áll-e szabad kapacitás.**·**

## <a name="master-planning-books-a-resource-when-the-resource-calendar-is-closed"></a>Alaptervezési könyvek egy erőforrás számára az erőforrásnaptár zárása után

A műveletütemezés használata esetén az alaptervezés az elsődleges erőforráscsoport naptára szerint tervezi meg a kapacitást. A másodlagos műveletet az elsődleges művelettel egyidejűleg könyvzi, és nem veszi figyelembe a másodlagos művelet naptárát és kapacitását. Emiatt a termelési rendelés ütemezése lezárt naptárhoz vagy olyan időponthoz vezethet, amikor a másodlagos művelet nem érhető el (naptár lezárva, nincs kapacitás).

A feladatütemezés használata esetén a rendelés ütemezője során az alaptervezés figyelembe veszi mind az elsődleges, mind a másodlagos művelet kapacitását és naptárát. A rendelés ütemezése csak akkor lehetséges, ha a műveletek erőforrásainak naptárai nyitottak és rendelkezésre állnak.

## <a name="maximum-job-lead-time-is-too-short"></a>A feladat maximális átfutási ideje túl rövid.

Az ütemezési motor **nem** fog tudni rendelést ütemezni, ha a telephelyhez beállított maximális átfutási idő kevesebb, mint az alapértelmezett rendelési és fedezeti beállításokban megadott cikk átfutási ideje.

A webhely maximális átfutási ideje beállításának megtekintéséhez vagy szerkesztéséhez nyissa meg a Gyártásvezérlés **beállítása** gyártásvezérlési paramétereket **, és nyissa meg az Általános \>\> lapot.** **·**

A cikkek alapértelmezett rendelési beállításainak megtekintéséhez vagy szerkesztéséhez hajtsa végre a következő lépéseket:

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Keresse meg és válassza ki a listában a kívánt terméket.
1. A munkaablakban nyissa meg a Készlet kezelése **lapot**, és válassza az Alapértelmezett rendelési **beállításokat**.
1. Bontsa ki **a** Készlet gyorsét, **és szükség szerint tekintse meg vagy módosítsa a készlet átfutási ideje** beállítását.

Egy cikk fedezeti beállításainak megtekintéséhez vagy szerkesztéséhez hajtsa végre a következő lépéseket:

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Keresse meg és válassza ki a listában a kívánt terméket.
1. A műveletpanelen nyissa meg a Terv **lapot**, és válassza a Cikkfedezet **lehetőséget**.
1. Nyissa meg az Átfutási **idő** lapot, és tekintse meg **vagy módosítsa a termelés időértékét**.

## <a name="excessive-quantity-of-required-resources"></a>Szükséges erőforrások túlságosan nagy mennyisége

Az ütemezés során a motor megpróbálja az útvonalművelethez beállított szükséges erőforrásmennyiséget a műveleti erőforrásigénynek megfelelően megfeleltetni a megfelelő erőforrásoknak. Ha túl nagy erőforrásmennyiséget ad meg, az útvonal elérhetetlenné válik, ami ütemezési hibát fog okozza.

A következő eljárással lehet ellenőrizni a kiválasztott termékre, útvonalra és útvonalműveletre vonatkozó megadott mennyiséget és a szükséges erőforrásokat:

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Keresse meg és válassza ki a kívánt terméket a rácsban.
1. A munkaablakban nyissa meg a Mérnöki **lapot**, és válassza az Útvonal **lehetőséget**.
1. A rácsban megkeresheti és kiválaszthatja a kívánt útvonalat.
1. A lap alján található **Áttekintés** lap megnyitása.
1. Művelet kiválasztása a kijelölt útvonalműveletek listájából.
1. A **Megfelelő erőforrások kiválasztása** egy párbeszédpanel megnyitásához, ahol megtekintheti a kiválasztott útvonalműveletre vonatkozó erőforrásokat.
1. Az Erőforrás-terhelés **lap** megnyitása Az **itt** látható Mennyiség mező mutatja a kiválasztott útvonalművelethez szükséges erőforrásmennyiséget. Szükség szerint tekintse meg és/vagy szerkessze a nézetet.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
