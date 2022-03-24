---
title: Igény szerinti szinkronizálás a Supply Chain Management árképzés motorral
description: Ez a témakör azt mutatja be, hogyan lehet használni a Microsoft Dynamics 365 Supply Chain Management Microsoft Dynamics 365 értékesítésből származó árképzési motorját.
author: RamaKrishnamoorthy
ms.date: 03/10/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 6b0cc8f403be866ff00b89a33f6c59089c987bb0
ms.sourcegitcommit: 9c19898e1f41495f804c7f07e2636b53a098c4c1
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/10/2022
ms.locfileid: "8402830"
---
# <a name="sync-on-demand-with-the-supply-chain-management-pricing-engine"></a>Igény szerinti szinkronizálás a Supply Chain Management árképzés motorral

[!include [banner](../../includes/banner.md)]

A Microsoft Dynamics 365 Supply Chain Management tartalmaz egy árképzési motort, amely a kereskedelmi megállapodásokat, árlistákat, törzsvásárlói programokat, promóciókat és kedvezményeket kezel. Az árképzési motor összetett szabályokat használ egy adott árajánlat vagy rendelés legjobb árának megállapításához. Két írásos típus használata esetén vagy statikus árképzést, **·** **·** Microsoft Dynamics vagy az Ellátásilánc-kezelés árképzési motorját kell használni a 365-ös értékesítés ajánlati és rendelési lapjain.

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a>A Supply Chain Management árképzési motorjának használata a Sales alkalmazásban

1. Az Sales alkalmazásban területen nyissa meg a **Sales \> Rendelések** elemet.
1. Válassza az **Új** lehetőséget egy új rendelés létrehozásához vagy válasszon egy meglévő rendelést a **Saját rendelések** listából.
1. Adjon hozzá egy új rendelési sort.
1. Ha új rendelést hoz létre, **válassza az Árrendelés** lehetőséget a munkaablakban. Ha egy meglévő rendelést frissít e, akkor a műveleti ablaktáblán válassza az **Újraszámítás** elemet.
1. A program automatikusan kitölti a következő oszlopokat:

    - Részletes összeg
    - Engedmény (%)
    - Kedvezmény
    - Szállítás előtti összeg
    - Szállítási összeg
    - Adó összesen
    - Teljes összeg

> [!NOTE]
> Hasonló folyamat alkalmazható az ajánlatok létrehozásakor is.

## <a name="how-it-works"></a>Hogyan működik?

Amikor rendelést hoz létre az Értékesítésben, a rendelés azonnal szinkronizálva lesz az Ellátásilánc-kezelés alkalmazással, az Értékesítés mezőben megadott értékekkel. Amikor az **Értékesítés** **mezőben** az Árrendelést vagy az Árajánlat lehetőséget választja, az Ellátásilánc-kezelés az egyes rendeléssorok árát és a teljes rendelést az Ellátásilánc-kezelésben meghatározott kereskedelmi megállapodási szabályok alapján számítja ki. A program ezt követően szinkronizálja az új számított értékeket az Értékesítés funkcióval.

## <a name="set-trade-agreement-evaluation-options-in-supply-chain-management"></a>Kereskedelmi megállapodás értékelési beállításainak megadása az Ellátásilánc-kezelésben

Beállíthatja, hogy az ellátásilánc-kezelés figyelembe vegye vagy figyelmen kívül hagyja a kereskedelmi megállapodásokat, amikor az értékesítésben létrehozott rendelés árát számítja. A beállításhoz hajtsa végre a következő lépéseket.

1. Jelentkezzen be az ellátásilánc-kezelési környezetbe.
1. Lépjen a **Kinnlevőségek \> Beállítások \> Kinnlevőségek paraméterei** pontra.
1. Adja hozzá **vagy** **·** **távolítsa** el a manuális beviteli irányelv sorát az Árak lap Kereskedelmi megállapodás kiértékelési gyorslapján. Az irányelv jelenléti vagy távolléte szabályozza, hogy az Ellátásilánc-kezelés árképzési motorja automatikusan felülbírálja-e az Értékesítésben megadott eladási árat.

    - Ha a kereskedelmi **megállapodás értékelési** *beállítása nem* **tartalmazza** a manuális beviteli házirendet, akkor az ellátásilánc-kezelés lesz az alapár. Ha **egy** **felhasználó** az Értékesítés munkaablakban az Árrendelést vagy az Ár árajánlatot választja, akkor a rendszer meghívták az Ellátásilánc-kezelés árképzési motort, és felülírja az Értékesítés mezőben megadott eladási árat, hacsak nem egyenlő az Ellátásilánc-kezelésben kiszámított eladási árral.
    - Ha a kereskedelmi **megállapodás kiértékelési** *beállításai* **között** manuális bejegyzési irányelv található, akkor az értékesítés az alapár. Az Értékesítés mezőben megadott eladási árat nem lehet automatikusan felülírni, amikor **egy** **felhasználó** az Értékesítés munkaablakában az Árrendelés vagy az Ár árajánlat lehetőséget választja.
    - Az Egységenkénti **ár** és/**·** *vagy Engedmény értéke 0* (nulla) értékű rendeléssorok és ajánlati sorok speciális esetként vannak kezelve. Ha a kereskedelmi megállapodás megfelelő ára elérhető, az Ellátásilánc-kezelés *mindig* alkalmazza ezeket a mezőket, függetlenül **a kereskedelmi megállapodás értékelési beállításaitól**.

    Az esetekről az alábbi eseteket láthatja példaként.

## <a name="example-scenario-1-trade-agreement-evaluation-without-the-manual-entry-option"></a>1. eset – példa: Kereskedelmi megállapodás kiértékelése a manuális beviteli beállítás nélkül

Ebben az esetben az Ellátásilánc-kezelés eszközben a kereskedelmi megállapodás kiértékelési beállításai nem **tartalmazzák a manuális** beviteli házirendet *.* **·** Egy értékesítési felhasználó olyan rendelési sort ír be, amely nem nulla eladási árral rendelkezik az Értékesítés csoportban, és az Ellátásilánc-kezelés eszközben nincs megadva eladási ár a cikkhez.

1. Az Értékesítésben a **felhasználó** létrehoz egy 1 USD (USD) egységár értékű rendeléssort.
1. A rendelési sor szinkronizálva van az Ellátásilánc-kezelés alkalmazással egy értékesítési 1 USD.
1. Az Értékesítés beállításnál a felhasználó a munkaablakban **az** Árrendelés lehetőséget választja.
1. Az ellátásilánc-kezelés megkeresi a megfelelő árakat és engedményeket, majd kiszámítja az összesítéseket. Mivel a cikknek nincs eladási ára az Ellátásilánc-kezelésben, a számítás úgy frissíti a sort, hogy az eladási ára 0 USD.
1. A sor új eladási ára vissza lesz szinkronizálva az Értékesítés értékhez.
1. Az eredmény egy rendelési sor az Értékesítésben, amely eladási ára 0 USD.

## <a name="example-scenario-2-trade-agreement-evaluation-with-the-manual-entry-option"></a>2. példa: Kereskedelmi megállapodás kiértékelése a Manuális bevitel beállítással

Ebben az esetben az Ellátásilánc-kezelés **·** *eszközben a kereskedelmi megállapodás kiértékelési beállításai tartalmazzák* a manuális **beviteli házirendet**. Az értékesítési felhasználó olyan rendelési sort ír be, amely nem nulla eladási árat ír be az Értékesítés értékbe. Az Ellátásilánc-kezelés egy kereskedelmi megállapodást tartalmaz, amely a megrendelt cikkre 2 USD eladási árat állít be.

1. Az Értékesítések mezőben **a** felhasználó rendeléssort hoz létre egy olyan cikkhez, amelynél az egységár 1 USD.
1. A rendelési sor szinkronizálva van az Ellátásilánc-kezelés alkalmazással egy értékesítési 1 USD.
1. Az Értékesítés beállításnál a felhasználó a munkaablakban **az** Árrendelés lehetőséget választja.
1. Mivel az **ellátásilánc-kezelésben** **a** kereskedelmi megállapodás értékelési beállításai tartalmazzák a manuális beviteli házirendet, az eladási ár nem változik akkor sem, ha egy vonatkozó kereskedelmi megállapodás másik eladási árat ad meg.
1. Az eladási ár változatlan marad az értékesítés és az ellátásilánc-kezelés során.

## <a name="example-scenario-3-trade-agreement-evaluation-for-an-item-that-has-a-sales-price-of-zero-in-sales"></a>3. példa: Kereskedelmi megállapodás kiértékelése egy olyan cikkre, amelynél nulla az eladási ár az Értékesítésben

Ebben az esetben az Ellátásilánc-kezelés **·** *eszközben a kereskedelmi megállapodás kiértékelési beállításai tartalmazzák* a manuális **beviteli házirendet**. Az Értékesítési felhasználó egy olyan rendelési sort ír be, amelyhez 0 (nulla) eladási ár van meg az Értékesítés értékben. Az Ellátásilánc-kezelés egy kereskedelmi megállapodást tartalmaz, amely a megrendelt cikkre 2 USD eladási árat állít be.

1. Az Értékesítésben **a** **felhasználó** létrehoz egy olyan rendeléssort, amelynél az egységenkénti ár értéke 0 USD sorengedmény értéke pedig 0 USD.
1. A rendelési sor szinkronizálva van az Ellátásilánc-kezelés alkalmazással egy értékesítési 0 USD.
1. Mivel a kapott rendeléssor eladási ára 0 (nulla), az Ellátásilánc-kezelés hívja az árképzési motort annak ellenére, **hogy** engedélyezve van a Manuális bevitel beállítás. Az árképzési motor a kereskedelmi megállapodás 2 USD eladási árát adja eredményül, és frissíti az ellátásilánc-kezelésben megadott rendeléssort.
1. A frissített eladási ár még nincs szinkronizálva az Értékesítés rendelési sárral.
1. Az Értékesítés beállításnál a felhasználó a munkaablakban **az** Árrendelés lehetőséget választja.
1. Az Ellátásilánc-kezelésben a rendeléssor megtartja az értékesítési 2 USD, amely most az Értékesítéssel szinkronizálva lesz. Ennek megfelelően **az Értékesítés rendelési sor** egységenkénti árának értéke automatikusan módosul 0 USD árról 2 USD.
1. Az Értékesítés mezőben a felhasználó a **rendelés új sorengedmény-** 0.50 USD. Az értékesítés most kiszámítja, hogy **a sor kiterjesztett** 1.50 USD.
1. A rendelési sor szinkronizálva van az Ellátásilánc-kezelés alkalmazással egy **sorengedmény**-0.50 USD.
1. Az Értékesítés beállításnál a felhasználó a munkaablakban **az** Árrendelés lehetőséget választja.
1. Az Értékesítés sorhoz nem változnak árak és engedmények.

## <a name="limitations"></a>Korlátozások

Amikor az Értékesítés oszlopai ki vannak töltve, a következő korlátozások érvényesek:

- A Supply Chain Management alkalmazásben végzett költség-és költség-felosztási beállítások nem lesznek másolva a Sales alkalmazásba.
- Az árképzés nem veszi figyelembe a különleges kiskereskedelmi árazást, ami a Supply Chain Management értékesítési rendelés sora oldalán van meghatározva a **Kiskereskedelmi csatorna** oszlopban.
- A rendszer nem veszi figyelembe a Supply Chain Management **Promóciós engedmény kezelése** részében meghatározott engedményeket.
- Az árképzés nem veszi figyelembe az értékesítési szerződéseket.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
