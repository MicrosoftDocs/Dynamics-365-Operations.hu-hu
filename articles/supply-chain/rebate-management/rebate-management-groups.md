---
title: Visszatérítés-kezelési csoportok
description: Ez a témakör a visszatérítés-kezelési csoportok beállítását írja le. A visszatérítés-kezelési csoportok a visszatérítési számítások során használhatók, és a főrekordhoz csatolhatók.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1f9deeedef504d1b2d0ba3431902c50bc65d62ba
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572697"
---
# <a name="rebate-management-groups"></a>Visszatérítés-kezelési csoportok

[!include [banner](../includes/banner.md)]

A visszatérítés-kezelési számításokat vezérelhetők csoportok szerint. A visszatérítés-kezelési csoportok vevők, szállítók és cikkek számára is létrehozhatók. Ezek főrekordhoz csatolhatók.

## <a name="rebate-management-customer-groups"></a>Visszatérítés-kezelési vevőcsoportok

A vevők egy csoportjának számítása gyakran egy vállalatlánc, például egy áruházlánc vagy egy franchise-cég számára jön létre. Ez a fajta számítás általában visszatérítéshez kapcsolódik.

A levonást gyakran anélkül számítják ki, hogy figyelembe vennék, kinek adták el a feljogosító rendelést. Vannak azonban kivételek. Egy licencbe vevő létrehozhat például egy olyan levonási sémát, amelyben az A vevőcsoport 4 százalékot kap, de a B vevőcsoport csak 3 százalékot.

### <a name="set-up-customer-groups"></a>Vevőcsoportok beállítása

A Visszatérítés-kezelő vevőcsoportokkal való munkához lépjen a **Visszatérítés-kezelés \> Visszatérítés-kezelési csoportok beállítása \> Vevőcsoportok** lehetőségre. A Művelet panel gombjaival lehet szükség szerint csoportokat hozzáadni és eltávolítani. Állítsa be a következő mezőket minden egyes csoportnál:

- **Visszatérítés-kezelési csoport** – Adjon meg egy egyedi nevet a csoportnak.
- **Leírás** – Adja meg a csoport leírását, amely további tájékoztatást ad a használat módjáról.

### <a name="manage-customer-group-assignments"></a>Vevőcsoport-hozzárendelések kezelése

Minden vevő tetszőleges számú visszatérítés-kezelési csoporthoz tartozhat. A csoporttagok megtekintéséhez és hozzárendeléséhez a csoportlistából vagy a vevőlistából indulhat ki.

A kijelölt csoport vevőinek megtekintéséhez, hozzáadásához vagy eltávolításához kövesse az alábbi lépéseket.

1. Lépjen a **Visszatérítés-kezelés \> Visszatérítés-kezelési csoportok beállítása \> Vevőcsoportok** lehetőségre.
1. Jelölje ki a kezelni kívánt csoportot.
1. A Műveleti ablaktáblán válassza ki a **Vevők** lehetőséget. Megjelenik a **Visszatérítés-kezelési csoportok** oldal, és megjelenik azoknak a vevőknek a listája, akik már tagjai a kiválasztott csoportnak.
1. Ha új vevőt szeretne hozzáadni a csoporthoz, a Művelet panelen válassza az **Új** lehetőséget egy új sor rácshoz való hozzáadásához. Ezután az új sorhoz állítsa be a következő mezőt:

    - **Vevői számla** – Válassza ki a vevői számla azonosítóját.

1. Ha el szeretne távolítani egy vevőt a csoportból, jelölje ki a vevőt, majd válassza a Művelet ablaktáblán a **Törlés** lehetőséget.

A kijelölt vevő csoport-hozzárendeléseinek megtekintéséhez, hozzáadásához vagy eltávolításához kövesse az alábbi lépéseket.

1. Nyissa meg a **Kinnlevőségek \> Vevők \> Minden vevő** lehetőséget.
1. Válassza ki azt a vevőt, akit kezelni szeretne.
1. A Művelet ablaktábla **Vevő** lapjának **Visszatérítés-kezelés** csoportjában válassza a **Visszatérítés-kezelési csoportok** elemet. Megjelenik a **Visszatérítés-kezelési csoportok** oldal, és megjelenik azoknak a csoportoknak a listája, amelyekhez a kiválasztott vevő már tartozik.
1. Ha a vevőt új csoporthoz szeretné hozzáadni, a Művelet panelen válassza az **Új** lehetőséget egy új sor rácshoz való hozzáadásához. Ezután az új sorhoz állítsa be a következő mezőt:

    - **Visszatérítés-kezelési csoport** – Válassza ki azt a csoportot, amelyhez hozzá kívánja adnia a vevőt.

1. Ha el szeretne távolítani egy vevőt a csoportból, jelölje ki a csoportot, majd válassza a Művelet ablaktáblán a **Törlés** lehetőséget.

## <a name="rebate-management-vendor-groups"></a>Visszatérítés-kezelési szállítócsoportok

A szállítók egy csoportjának számítása gyakran a szállítási pontok egy csoportjához jön létre. Ez a fajta számítás általában visszatérítéshez kapcsolódik.

### <a name="set-up-vendor-groups"></a>Szállítói csoportok beállítása

A Visszatérítés-kezelési szállítócsoportokkal való munkához lépjen a **Visszatérítés-kezelés \> Visszatérítés-kezelési csoportok beállítása \> Szállítócsoportok** lehetőségre. A Művelet panel gombjaival lehet szükség szerint csoportokat hozzáadni és eltávolítani. Állítsa be a következő mezőket minden egyes csoportnál:

- **Visszatérítés-kezelési csoport** – Adjon meg egy egyedi nevet a csoportnak.
- **Leírás** – Adja meg a csoport leírását, amely további tájékoztatást ad a használat módjáról.

### <a name="manage-vendor-group-assignments"></a>Szállítócsoport-hozzárendelések kezelése

Minden szállító tetszőleges számú visszatérítés-kezelési csoporthoz tartozhat. A csoporttagok megtekintéséhez és hozzárendeléséhez a csoportlistából vagy a szállítólistából indulhat ki.

A kijelölt csoport szállítóinak megtekintéséhez, hozzáadásához vagy eltávolításához kövesse az alábbi lépéseket.

1. Lépjen a **Visszatérítés-kezelés \> Visszatérítés-kezelési csoportok beállítása \> Szállítócsoportok** lehetőségre.
1. Jelölje ki a kezelni kívánt csoportot.
1. A Művelet panelen válassza a **Szállítók** lehetőséget. Megjelenik a **Visszatérítés-kezelési csoportok** oldal, és megjelenik azoknak a szállítóknak a listája, akik már tagjai a kiválasztott csoportnak.
1. Ha az új szállítót a csoporthoz szeretné hozzáadni, a Művelet panelen válassza az **Új** lehetőséget egy új sor rácshoz való hozzáadásához. Ezután az új sorhoz állítsa be a következő mezőt:

    - **Szállítói számla** – Válassza ki a szállítói számla azonosítóját.

1. Ha el szeretne távolítani egy szállítót a csoportból, jelölje ki a szállítót, majd válassza a Művelet ablaktáblán a **Törlés** lehetőséget.

A kijelölt szállító csoport-hozzárendeléseinek megtekintéséhez, hozzáadásához vagy eltávolításához kövesse az alábbi lépéseket.

1. Nyissa meg a következőt: **Kötelezettségek \> Szállítók \> Minden szállító**.
1. Válassza ki azt a szállítót, akit kezelni szeretne.
1. A Művelet ablaktábla **Szállító** lapjának **Visszatérítés-kezelés** csoportjában válassza a **Visszatérítés-kezelési csoportok** elemet. Megjelenik a **Visszatérítés-kezelési csoportok** oldal, és megjelenik azoknak a csoportoknak a listája, amelyekhez a kiválasztott szállító már tartozik.
1. Ha a szállítót új csoporthoz szeretné hozzáadni, a Művelet panelen válassza az **Új** lehetőséget egy új sor rácshoz való hozzáadásához. Ezután az új sorhoz állítsa be a következő mezőt:

    - **Visszatérítés-kezelési csoport** – Válassza ki azt a csoportot, amelyhez hozzá kívánja adnia a szállítót.

1. Ha el szeretne távolítani egy szállítót a csoportból, jelölje ki a csoportot, majd válassza a Művelet ablaktáblán a **Törlés** lehetőséget.

## <a name="item-rebate-groups"></a>Cikk visszatérítési csoportjai

A cikkek csoportosítása nagyobb rugalmasságot biztosít a visszatérítések és levonások kiszámításakor. Ez a megközelítés gyakran hatékonyabb módja a vevők és szállítók számára visszatérítések és levonások beállításának.

### <a name="set-up-item-groups"></a>Cikkcsoportok beállítása

A Visszatérítés-kezelési cikkcsoportokkal való munkához lépjen a **Visszatérítés-kezelés \> Visszatérítés-kezelési csoportok beállítása \> Cikkcsoportok** lehetőségre. A Művelet panel gombjaival lehet szükség szerint csoportokat hozzáadni és eltávolítani. Állítsa be a következő mezőket minden egyes csoportnál:

- **Visszatérítés-kezelési csoport** – Adjon meg egy egyedi nevet a csoportnak.
- **Leírás** – Adja meg a csoport leírását, amely további tájékoztatást ad a használat módjáról.

### <a name="manage-item-group-assignments"></a>Cikkcsoport-hozzárendelések kezelése

Minden cikk tetszőleges számú visszatérítés-kezelési csoporthoz tartozhat. A csoporttagok megtekintéséhez és hozzárendeléséhez a csoportlistából vagy a cikklistából indulhat ki. A kategóriahierarchia alapján is hozzáadhat cikkeket.

A kijelölt csoport cikkeinek megtekintéséhez, hozzáadásához vagy eltávolításához kövesse az alábbi lépéseket.

1. Lépjen a **Visszatérítés-kezelés \> Visszatérítés-kezelési csoportok beállítása \> Cikkcsoportok** lehetőségre.
1. Jelölje ki a kezelni kívánt csoportot.
1. A Művelet ablaktáblán kattintson a **Cikkek** elemre. Megjelenik a **Visszatérítés-kezelési csoportok** oldal, és megjelenik azoknak a cikkeknek a listája, amelyek már tagjai a kiválasztott csoportnak.
1. Ha új cikket szeretne hozzáadni a csoporthoz, a Művelet panelen válassza az **Új** lehetőséget egy új sor rácshoz való hozzáadásához. Ezután az új sorhoz állítsa be a következő mezőt:

    - **Cikkszámla** – Válassza ki a cikkszámla azonosítóját.

1. Ha el szeretne távolítani egy cikket a csoportból, jelölje ki a cikket, majd válassza a Művelet ablaktáblán a **Törlés** lehetőséget.

A kijelölt cikk csoport-hozzárendeléseinek megtekintéséhez, hozzáadásához vagy eltávolításához kövesse az alábbi lépéseket.

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Válassza ki azt a cikket, amelyet kezelni szeretne.
1. A Művelet ablaktábla **Termék** lapjának **Visszatérítés-kezelés** csoportjában válassza a **Visszatérítés-kezelési csoportok** elemet. Megjelenik a **Visszatérítés-kezelési csoportok** oldal, és megjelenik azoknak a csoportoknak a listája, amelyekhez a kiválasztott cikk már tartozik.
1. Ha a cikket új csoporthoz szeretné hozzáadni, a Művelet panelen válassza az **Új** lehetőséget egy új sor rácshoz való hozzáadásához. Ezután az új sorhoz állítsa be a következő mezőt:

    - **Visszatérítés-kezelési csoport** – Válassza ki azt a csoportot, amelyhez hozzá kívánja adnia a cikket.

1. Ha el szeretne távolítani egy cikket a csoportból, jelölje ki a csoportot, majd válassza a Művelet ablaktáblán a **Törlés** lehetőséget.

Ha a kategóriahierarchia alapján szeretne cikkeket hozzáadni egy csoporthoz, kövesse az alábbi lépéseket.

1. Lépjen a **Visszatérítés-kezelés \> Visszatérítés-kezelési csoportok beállítása \> Cikkcsoportok** lehetőségre.
1. Jelölje ki a kezelni kívánt csoportot.
1. A Művelet ablaktáblán kattintson a **Cikkek hozzáadása** elemre.
1. A **Cikkek hozzáadása** párbeszédpanel **Kategóriahierarchia** mezőjében jelöljön ki egy legfelső szintű kategóriát.
1. A cikkhierarchia a bal oldali ablaktáblában nyílik meg. Válassza ki a keresett hierarchiaszintet. 
1. A kijelölt hierarchia és hierarchiaszint elemei most a jobb oldali ablaktáblában vannak felsorolva. Az ablaktábla kezeléséhez kövesse az alábbi lépéseket:

    - A hozzáadni kívánt cikkek mellett jelölje be a jelölőnégyzetet.
    - Jelölje be a rácsfejléc jelölőnégyzetét a felsorolt elemek kijelöléséhez.
    - A **Kijelölt megjelenítése** gombra kattintva szűrheti a rácsot, hogy csak az eddig kiválasztott cikkeket mutassa. A teljes listához való visszatéréshez kattintson ismét a gombra.

1. Az **OK** gombra kattintva alkalmazhatja a cikk-kijelöléseket a kiválasztott csoportra.
