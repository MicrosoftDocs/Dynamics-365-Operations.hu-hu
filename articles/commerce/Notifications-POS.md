---
title: Rendelési értesítések megjelenítése a pénztárnál (POS)
description: Ez a témakör ismerteti, hogyan lehet engedélyezni a rendelési értesítéseket a pénztárban és az értesítési keretrendszerben.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 04/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations, RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: e663a5dca76d570217b7e02444689a2e2d312c41
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412771"
---
# <a name="show-order-notifications-in-the-point-of-sale-pos"></a>Rendelési értesítések megjelenítése a pénztárnál (POS)

[!include [banner](includes/banner.md)]

A modern kiskereskedelmi környezetben az üzlet munkatársai különböző feladatokat látnak el, például segítenek a vevőknek, beviszik a tranzakciókat, leltáraznak és rendeléseket fogadnak az üzletben. A pénztár (POS) ügyfél egyetlen alkalmazásban teszi lehetővé a munkatársak számára, hogy elvégezzék ezeket a feladatokat és még sok minden mást is. Mivel a nap folyamán különböző feladatokat kell végrehajtani, szükség lehet a munkatársak értesítésére, amikor valami figyelmet igényel. A pénztár értesítési keretrendszere segít azáltal, hogy a kiskereskedőknek szerepköralapú értesítések beállítását teszi lehetővé. A Dynamics 365 for Retail alkalmazás 5. alkalmazásfrissítésétől az értesítések csak pénztárműveleteknél állíthatók be.


Jelenleg a rendszer csak a rendelés teljesítése műveletekhez képes értesítéseket megjeleníteni. Azonban mivel a keretrendszert bővíthetőnek tervezték, a fejlesztők végül írni fognak tudni egy értesítéskezelőt minden művelethez, és a művelet értesítéseit megjeleníthetik a pénztárban.

## <a name="enable-notifications-for-order-fulfillment-operations"></a>A rendelésteljesítési műveletek értesítéseinek engedélyezése

A rendelésteljesítési műveletek értesítéseinek engedélyezéséhez hajtsa végre a következő lépéseket:

1. Lépjen a **Kiskereskedelem és kereskedelem** &gt; **Csatornabeállítás** &gt; **Pénztárbeállítás** &gt; **Pénztár** &gt; **Műveletek** lehetőségre.
2. Keresse meg a **Rendelés teljesítése** műveletet, és jelölje be az **Értesítések engedélyezése** jelölőnégyzetet annak a megadásához, hogy az értesítési keretrendszer figyelje a kezelőt ehhez a művelethez. Ha a kezelő telepítve van, az ehhez a művelethez tartozó értesítések megjelennek a pénztárban.
3. Ugorjon a **Retail és Commerce** &gt; **Alkalmazottak** &gt; **Dolgozók** &gt; elemre a Commerce lapon, és nyissa meg a dolgozóhoz társított pénztárengedélyeket. Bontsa ki az **Értesítések** gyorslapot, adja hozzá a **Rendelés teljesítése** műveletet, és állítsa a **Megjelenítési sorrend** mezőt **1** értékre. Ha egynél több értesítés van beállítva, ezzel a mezővel történik az értesítések elrendezése. Az értesítések, amelyeknek kisebb a **Megjelenítési sorrend** értéke, az olyan értesítések felett jelennek meg, amelyeknek nagyobb az értesítési értéke. Azok az értesítések, amelyeknek a **Megjelenítési sorrend** értéke **1**, legfelül jelennek meg.

    Csak azokhoz a műveletekhez jelennek meg értesítések, amelyeket hozzáadtak az **Értesítések** gyorslapon, és ott csak akkor vehet fel műveleteket, ha az **Értesítések engedélyezése** jelölőnégyzet be van jelölve ezekhez a műveletekhez a **Pénztárműveletek** oldalon. Ezenkívül a művelet értesítései csak akkor jelennek meg dolgozóknak, ha a művelet hozzá van adva a pénztárengedélyekhez az adott dolgozónál.

    > [!NOTE]
    > Az értesítések a felhasználó szintjén felülbírálhatók. Nyissa meg a dolgozó rekordját, válassza ki a **POS-engedélyek** elemet, majd szerkessze a felhasználói értesítés-előfizetéseket.

4. Ugorjon a következő elemre: **Retail és Commerce** &gt; **Csatorna beállítása** &gt; **Pénztárbeállítás** &gt; **Pénztárprofilok** &gt; **Funkcióprofilok**. Az **Értesítési időköz** mezőben adja meg, hogy milyen gyakran kell lekérni az értesítéseket. Egyes értesítéseknél a pénztárnak valós idejű hívást kell végrehajtania a háttérirodai alkalmazás felé. Ezek a hívások fogyasztják a háttérirodai alkalmazás számítási kapacitását. Emiatt az értesítési intervallum beállításakor vegye figyelembe mind az üzleti követelményeket, mind az irodai alkalmazás valós idejű hívásainak hatását. A **0** (nulla) érték kikapcsolja az értesítéseket.
5. Ugorjon a **Kiskereskedelem és kereskedelem** &gt; **Kiskereskedelem és kereskedelem informatika** &gt; **Elosztási ütemezés** pontra. Válassza az **1060** (**személyzet**) ütemezést az értesítési előfizetési beállítások szinkronizálásához, és kattintson a **Futtatás most** elemre. Ezután szinkronizálja az engedélyintervallumot az **1070** (**csatornakonfiguráció**)ütemezés kiválasztásával, és kattintson a **Futtatás most** elemre.

## <a name="view-notifications-in-the-pos"></a>Értesítések megtekintése a pénztárban

Miután befejezte az előző lépéseket, a dolgozók meg tudják tekinteni az értesítéseket a pénztárban. Az értesítés megtekintéséhez nyomja meg a pénztár jobb felső sarkában található értesítés ikont. Megjelenik az értesítési központ a rendelésteljesítési művelethez tartozó értesítésekkel. Az értesítési központnak a rendelésteljesítési műveletben a következő csoportokat kell megjelenítenie:

- **Átvétel az üzletben** – Ebben a csoportban azoknak a megrendeléseknek a száma jelenik meg, amelyeknél a szállítási mód az **Átvétel**, és az átvétel az aktuális üzlethez van ütemezve. Nyomja meg a számot a csoporton, hogy megnyissa a **Rendelés teljesítése** oldalt. Ebben az esetben az oldal szűrve lesz, hogy csak az aktuális boltból átvételre beállított, aktív rendeléseket jelenítse meg.
- **Szállítás az üzletből** – Ebben a csoportban azoknak a megrendeléseknek a száma jelenik meg, amelyeknél a szállítási mód a **Szállítás**, és a szállítás az aktuális üzletből van ütemezve. Nyomja meg a számot a csoporton, hogy megnyissa a **Rendelés teljesítése** oldalt. Ebben az esetben az oldal szűrve lesz, hogy csak az aktuális boltból szállításra beállított, aktív rendeléseket jelenítse meg.

Amikor új rendelések vannak teljesítésre az üzlethez társítva, az értesítési ikon megváltozik, hogy jelezze az új értesítéseket, és a megfelelő csoportok száma frissülni fog. Bár a csoportok rendszeres időközönként frissülnek, a pénztárfelhasználó kézzel is bármikor frissítheti a csoportokat, a csoport melletti **Frissítés** gomb kiválasztásával. Végül, ha egy csoportnak új eleme van, amelyet az aktuális dolgozó még nem tekintett meg, a csoport égő szimbólumot jelenít meg az új tartalmat jelezve.

## <a name="enable-live-content-on-pos-buttons"></a>Élő tartalom engedélyezése a pénztár gombjain

A pénztárgombok most már egy számlálót is megjeleníthetnek, amelynek a segítségével a dolgozó egyszerűen azonosíthatja az azonnali figyelmet igénylő feladatokat. A szám megjelenítéséhez a pénztárgombon hajtsa végre az ebben a témakörben korábban ismertetett értesítésbeállítást (vagyis engedélyezni kell az értesítéseket egy művelethez, szükséges az értesítési időköz beállítása, és a POS-engedélycsoportot frissíteni kell a dolgozóhoz). Ezenkívül meg kell nyitni a gombrácstervezőt, meg kell tekinteni a gomb tulajdonságait, és be kell jelölni az **Élő tartalom engedélyezése** jelölőnégyzetet. A **Tartalom igazítása** mezőben kiválaszthatja, hogy a gomb jobb felső sarkában jelenjen meg a számláló (**Jobb felső**) vagy a közepén (**Középen**).

> [!NOTE]
> Az élő tartalom csak akkor engedélyezhető a műveletekhez, ha az **Értesítések engedélyezése** jelölőnégyzet be van jelölve hozzájuk a **POS-műveletek** oldalon, az ebben a témakörben korábban ismertetett módon.

A következő ábrán az élő tartalom beállítása látható a rácsgombtervezőben.

![Élő tartalom beállítása a rácsgombtervezőben](./media/ButtonGridDesigner.png "Élő tartalom beállítása a rácsgombtervezőben")

Ha meg szeretné jeleníteni az értesítések számát egy gombnyomással, gondoskodni kell arról, hogy a megfelelő képernyő-elrendezés frissítve legyen. A pénztár által használt képernyő-elrendezés meghatározásához jelölje be a **Beállítások** ikont a jobb felső sarokban, és jegyezze fel a **Képernyő-elrendezés azonosítója** és **Elrendezés felbontása** adatokat. Most, az Edge böngésző használatával menjen a **Képernyőelrendezés** oldalra a rendszerben, keresse meg a fent azonosított **Képernyő-elrendezés azonosítója** és **Elrendezés felbontása** adatokat, majd jelölje be az **Élő tartalom engedélyezése** jelölőnégyzetet. Nyissa meg a **Retail és Commerce \> Retail és Commerce IT \> Elosztási ütemezés** menüpontot, és futtassa az 1090 (Pénztárgépek) feladatot az elrendezésmódosítások szinkronizálásához.


![A pénztár által használt képernyő-elrendezés keresése](./media/Choose_screen_layout.png "Képernyő-elrendezés keresése")

A következő ábra bemutatja a **Jobb felső** és a **Középen** kiválasztásának hatását a **Tartalom igazítása** mezőben, különböző méretű gombok esetében.

![Élő tartalom a pénztár gombjain](./media/ButtonsWithLiveContent.png "Élő tartalom a pénztár gombjain")
