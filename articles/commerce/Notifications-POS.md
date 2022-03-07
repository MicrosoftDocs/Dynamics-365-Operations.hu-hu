---
title: Rendelési értesítések megjelenítése a pénztárnál (POS)
description: Ez a témakör ismerteti, hogyan lehet engedélyezni a rendelési értesítéseket a pénztárban és az értesítési keretrendszerben.
author: ShalabhjainMSFT
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations, RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7166afdb43c7e835170c5768a0767f2943222b19c00c7d0aaf067263845651f8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6714138"
---
# <a name="show-order-notifications-in-the-point-of-sale-pos"></a>Rendelési értesítések megjelenítése a pénztárnál (POS)

[!include [banner](includes/banner.md)]

Az üzlet alkalmazottai az üzletben különféle feladatokhoz rendelhetők hozzá, például a rendelések teljesítése, a készlet bevételezése vagy a leltár elvégzése. A pénztár (POS) ügyfél egyetlen alkalmazásban teszi lehetővé a munkatársak tájékoztatását ezekről a feladatokról. A pénztár értesítési keretrendszere segít azáltal, hogy a kiskereskedőknek szerepköralapú értesítések beállítását teszi lehetővé. A Dynamics 365 Retail alkalmazásban az 5. alkalmazásfrissítéssel kezdődően az értesítések csak pénztárműveleteknél állíthatók be.

A rendszer a *rendelésteljesítési* műveletre vonatkozó értesítéseket is meg tudja jeleníteni, és a Commerce rendszer 10.0.18-as verziójától kezdve a *rendelés-visszahívási* művelethez is meg tud jeleníteni értesítéseket. Azonban mivel a keretrendszert bővíthetőnek tervezték, a fejlesztők képesek egy [értesítéskezelőt írni](dev-itpro/extend-pos-notification.md) minden művelethez, és a művelet értesítéseit megjeleníthetik a pénztárban.

## <a name="enable-notifications-for-order-fulfillment-or-recall-order-operations"></a>A rendelésteljesítési vagy rendelés-visszahívási műveletek értesítéseinek engedélyezése

A rendelésteljesítési vagy rendelés-visszahívási műveletek értesítéseinek engedélyezéséhez hajtsa végre a következő lépéseket.

1. Lépjen a **Kiskereskedelem és kereskedelem \> Csatornabeállítás \> Pénztárbeállítás \> Pénztár \> Műveletek** lehetőségre.
1. Keresse meg a **Rendelés teljesítése** műveletet vagy a **Rendelés visszahívása** műveletet, majd jelölje be az adott művelethez kapcsolódó **Értesítések engedélyezése** jelölőnégyzetet annak a megadásához, hogy az értesítési keretrendszer figyelje a kezelőt ehhez a művelethez. Ha a kezelő telepítve van, az ehhez a művelethez tartozó értesítések megjelennek a pénztárban.
1. Nyissa meg a következőt: **Retail és Commerce \> Alkalmazottak \> Dolgozók**.
1. Válassza a **Commerce** lapot, válasszon ki egy dolgozósort, majd válassza ki a **POS-engedélyek** lehetőséget. Válassza ki az **Értesítések** gyorslapot a kibontáshoz, majd adja hozzá azokat a műveleteket, amelyekhez értesítéseket engedélyezett. Ha egy dolgozó egyetlen értesítését konfigurálja, győződjön meg arról, hogy a **Rendelés megjelenítése** értéke **1** legyen. Ha egynél több műveletet konfigurál, a **Megjelenítési sorrend** beállításával jelezze, milyen sorrendben kell megjeleníteni az értesítéseket. 

      Az értesítések csak az **Értesítések** gyorslapon hozzáadott műveletekhez kapcsolódóan jelennek meg. Csak akkor adhat hozzá műveleteket, ha az **Értesítések engedélyezése** jelölőnégyzet be van jelölve az ilyen műveletek esetében a **POS műveletek** oldalon. Ezenkívül a művelet értesítései csak akkor jelennek meg dolgozóknak, ha a művelet hozzá van adva a pénztárengedélyekhez az adott dolgozónál.

    > [!NOTE]
    > Az értesítések a felhasználó szintjén felülbírálhatók. Ehhez nyissa meg a dolgozó rekordját, válassza ki a **POS-engedélyek** elemet, majd szerkessze a felhasználói értesítés-előfizetéseket.

1. Ugorjon a következő elemre: **Retail és Commerce \>  Csatorna beállítása \> Pénztárbeállítás \>  Pénztárprofilok \> Funkcióprofilok**. Az **Értesítési időköz** mezőben adja meg, hogy milyen gyakran kell lekérni az értesítéseket. Egyes értesítéseknél a pénztárnak valós idejű hívást kell végrehajtania a háttérirodai alkalmazás felé. Ezek a hívások fogyasztják a háttérirodai alkalmazás számítási kapacitását. Emiatt az értesítési intervallum beállításakor vegye figyelembe mind az üzleti követelményeket, mind az irodai alkalmazás valós idejű hívásainak hatását. A **0** (nulla) érték kikapcsolja az értesítéseket.
1. Ugorjon a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem informatika \> Elosztási ütemezés** pontra. Válassza az **1060** (**személyzet**) ütemezést az értesítési előfizetési beállítások szinkronizálásához, és kattintson a **Futtatás most** elemre. Ezután szinkronizálja az engedélyintervallumot az **1070** (**csatornakonfiguráció**)ütemezés kiválasztásával, és kattintson a **Futtatás most** elemre.

## <a name="view-notifications-in-the-pos"></a>Értesítések megtekintése a pénztárban

Miután befejezte az előző lépéseket, a dolgozók meg tudják tekinteni az értesítéseket a pénztárban. Az értesítés megtekintéséhez válassza a pénztár jobb felső sarkában található értesítés ikont. Megjelenik egy értesítési panel, amely megjeleníti a dolgozóhoz konfigurált műveletekkel kapcsolatos értesítéseket. 

A **rendelésteljesítési** műveletben az értesítési panelnek a következő csoportokat kell megjelenítenie:

- **Átvétel az üzletben** – Ebben a csoportban azon egyes rendelési sorok száma jelenik meg, amelyeknél az átvétel az aktuális üzlethez van ütemezve. Kiválaszthatja a csoportban lévő számot a **Rendelés teljesítése** művelet szűrővel történő megnyitásához, hogy csak azok az aktív rendelési sorok jelenjenek meg, amelyeket az aktuális üzletből történő felvételhez állítottak be.
- **Szállítás üzletből** – ez a csoport a felhasználó aktuális üzletében konfigurált egyedi rendeléssorok számát jeleníti meg. Kiválaszthatja a csoportban lévő számot a **Rendelés teljesítése** művelet szűrt nézetének megnyitásához, hogy csak azok az aktív rendelési sorok jelenjenek meg, amelyeket az aktuális üzletből történő szállításhoz állítottak be.

A **rendelés visszahívása** műveletben az értesítési panelnek a következő csoportokat kell megjelenítenie:

- **Teljesítendő rendelések** – ez a csoport megjeleníti a felhasználó aktuális üzletének felvételi vagy szállítási teljesítése érdekében konfigurált rendelések számát. A csoportban látható szám kiválasztásával a **Rendelés visszahívása** műveletet szűrt nézettel nyithatja meg, amely csak azokat a nyitott rendeléseket jeleníti meg, amelyeket a felhasználó aktuális üzletének teljesítenie kell az üzletben való felvétel vagy az üzletből való szállítás forgatókönyvekhez.
- **Átveendő megrendelések** – Ebben a csoportban azon rendelések száma jelenik meg, amelyeknél az átvétel az aktuális üzlethez van ütemezve. A csoportban látható szám kiválasztásával a **Rendelés visszahívása** műveletet szűrt nézettel nyithatja meg, amely csak azokat a nyitott rendeléseket jeleníti meg, amelyeket a felhasználó aktuális üzletének kell teljesítenie kell az üzletben való felvételhez.
- **Szállítandó rendelések** – ez a csoport a felhasználó aktuális üzletéből szállítható rendelések számát mutatja. A csoportban látható szám kiválasztásával a **Rendelés visszahívása** műveletet szűrt nézettel nyithatja meg, amely csak azokat a nyitott rendeléseket jeleníti meg, amelyeket a felhasználó aktuális üzletének kell teljesítenie kell az üzletből való szállításhoz.

A rendelésteljesítések és a rendelés-visszavonási értesítések esetében egyaránt amikor a folyamat új rendeléseket vesz át, az értesítési ikon megváltozik, hogy jelezze az új értesítéseket, és a megfelelő csoportok száma frissülni fog. Bár a csoportok rendszeres időközönként frissülnek, a pénztárfelhasználó kézzel is bármikor frissítheti a csoportokat a csoport melletti **Frissítés** gomb kiválasztásával. Végül, ha egy csoportnak új eleme van, amelyet az aktuális dolgozó még nem tekintett meg, a csoport égő szimbólumot jelenít meg az új tartalmat jelezve.

## <a name="enable-live-content-on-pos-buttons"></a>Élő tartalom engedélyezése a pénztár gombjain

A pénztárgombok most már egy számlálót is megjeleníthetnek, amelynek a segítségével a dolgozó egyszerűen azonosíthatja az azonnali figyelmet igénylő feladatokat. A szám megjelenítéséhez a pénztárgombon hajtsa végre az ebben a témakörben korábban ismertetett értesítésbeállítást (vagyis engedélyezni kell az értesítéseket egy művelethez, szükséges az értesítési időköz beállítása, és a POS-engedélycsoportot frissíteni kell a dolgozóhoz). Ezenkívül meg kell nyitni a gombrácstervezőt, meg kell tekinteni a gomb tulajdonságait, és be kell jelölni az **Élő tartalom engedélyezése** jelölőnégyzetet. A **Tartalom igazítása** mezőben kiválaszthatja, hogy a gomb jobb felső sarkában jelenjen meg a számláló (**Jobb felső**) vagy a közepén (**Középen**).

> [!NOTE]
> Az élő tartalom csak akkor engedélyezhető a műveletekhez, ha az **Értesítések engedélyezése** jelölőnégyzet be van jelölve hozzájuk a **POS-műveletek** oldalon, az ebben a témakörben korábban ismertetett módon.

A következő ábrán az élő tartalom beállítása látható a rácsgombtervezőben.

![Élő tartalom beállítása a rácsgombtervezőben.](./media/ButtonGridDesigner.png "Élő tartalom beállítása a rácsgombtervezőben")

Ha meg szeretné jeleníteni az értesítések számát egy gombnyomással, gondoskodni kell arról, hogy a megfelelő képernyő-elrendezés frissítve legyen. A pénztár által használt képernyő-elrendezés meghatározásához jelölje be a **Beállítások** ikont a jobb felső sarokban, és jegyezze fel a **Képernyő-elrendezés azonosítója** és **Elrendezés felbontása** adatokat. Most, az Edge böngésző használatával menjen a **Képernyőelrendezés** oldalra a rendszerben, keresse meg a fent azonosított **Képernyő-elrendezés azonosítója** és **Elrendezés felbontása** adatokat, majd jelölje be az **Élő tartalom engedélyezése** jelölőnégyzetet. Nyissa meg a **Retail és Commerce \> Retail és Commerce IT \> Elosztási ütemezés** menüpontot, és futtassa az 1090 (Pénztárgépek) feladatot az elrendezésmódosítások szinkronizálásához.

![A pénztár által használt képernyő-elrendezés keresése.](./media/Choose_screen_layout.png "Képernyő-elrendezés keresése")

A következő ábra bemutatja a **Jobb felső** és a **Középen** kiválasztásának hatását a **Tartalom igazítása** mezőben, különböző méretű gombok esetében.

![Élő tartalom a pénztár gombjain.](./media/ButtonsWithLiveContent.png "Élő tartalom a pénztár gombjain")

[!INCLUDE[footer-include](../includes/footer-banner.md)]
