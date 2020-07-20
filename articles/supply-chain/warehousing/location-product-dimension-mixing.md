---
title: Hely és termékdimenzió kombinálása
description: Ez a témakör a helyi termékdimenziók kombinálásával kapcsolatban tartalmaz tájékoztatást. Ez a helyprofil funkció segít a helykezelés javításában, ha a termékváltozat vagy dimenziókkal rendelkező termékek kerülnek felhasználásra, például a divatiparban. Ez lehetővé teszi annak eldöntését, hogy a konfigurációk, színek, stílusok és méretek egy adott helyprofil esetében kombinálva vannak-e, illetve hogy csak az ilyen dimenziók egyikét vagy ezek kombinációját lehet ugyanazon a helyen elhelyezni.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 968777b918d59b810a189139fbf4d6fee1b5d3f5
ms.sourcegitcommit: a7a7303004620d2e9cef0642b16d89163911dbb4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2020
ms.locfileid: "3529983"
---
# <a name="location-product-dimension-mixing"></a>Hely és termékdimenzió kombinálása

[!include [banner](../includes/banner.md)]

A helyi termékdimenziók kombinálása helyprofilfunkció segít a helykezelés javításában, ha a termékváltozat vagy dimenziókkal rendelkező termékek kerülnek felhasználásra, például a divatiparban. Ez lehetővé teszi annak eldöntését, hogy a konfigurációk, színek, stílusok és méretek egy adott helyprofil esetében kombinálva vannak-e, illetve hogy csak az ilyen dimenziók egyikét vagy ezek kombinációját lehet ugyanazon a helyen elhelyezni.

## <a name="turn-on-the-location-product-dimension-mixing-feature"></a>A helyi termékdimenzió-kombinálás funkció bekapcsolása

A helyi termékdimenzió-kombinálás használata előtt a funkciót be kall kapcsolni a rendszerében. A rendszergazdák használhatják a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A funkció a következő módon jelenik meg:

- **Modul:** *Raktárkezelés*
- **Funkció neve:** *Helyi termékdimenzió-kombinálás*

## <a name="setup"></a>Beállítás

A raktárban minden helyhez társítani kell egy helyprofilt, amely leírja a hely tulajdonságait. Ennek megfelelően minden olyan hely, amely ugyanazt a helyprofilt használja, lehetővé teheti a cikkdimenziók kombinálását annak beállítása után.

### <a name="configure-location-profiles-to-allow-product-dimension-mixing"></a>A termékdimenzió-kombinálást lehetővé tevő helyprofilok konfigurálása

1. Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Helyprofilok** pontra.
1. A helyprofilok listáján válassza az **ÖMLESZTETT** elemet.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. Az **Általános** gyorslapon adja meg a **Helyi termékdimenziók specifikus kombinálásának engedélyezése** beállítását *Igen* értékre.

    > [!NOTE]
    > Ez a beállítás csak akkor állítható *Igen* értékűre, ha a **Vegyes cikkek engedélyezése** beállítás *Nem* értékre van állítva.

1. Az **Termékdimenzió-kombinálás engedélyezett** gyorslapon adja meg a **Méret** beállítását *Igen* értékre. Az ebben a témakörben leírt esetben a kombinálás csak olyan termékek esetében hajtható végre, amelyeknél különböző **Méret** dimenziók vannak. Más beállítások is elérhetők azonban.
1. Válassza a **Mentés** lehetőséget.

### <a name="create-a-new-product-master-and-product-variants"></a>Új alaptermék és termékváltozatok létrehozása

1. Ugorjon a **Termékinformációk kezelése \> Termékek \> Alaptermékek** lehetőségre.
1. Jelölje be a műveleti ablakban az **Új** lehetőséget az alaptermék létrehozásához.
1. Az **Új termék** párbeszédpanelen adja meg a következő értékeket:

    - **Terméktípus:** *Cikk*
    - **Termék altípusa:** *Alaptermék*
    - **Termék száma:** *B0001*
    - **Termék neve:** *B0001 Méret*
    - **Termékdimenzió-csoport:** *Méret*
    - **Konfigurálási technológia:** *Előre megadott változat*

1. Válassza ki az **OK** lehetőséget.
1. A **Termék részletei** oldalon, az **Általános** gyorslapon adja meg a következő értékeket:

    - **Változatok automatikus létrehozása:** *Igen*
    - **Méret csoport:** *CASUALDHIR*

1. Ha meg szeretné tekinteni az előre megadott változatokat, a Művelet ablaktáblán válassza ki a **Termékváltozatok** lehetőséget.

    Megjelenik a **Termékváltozatok** lap, amelyen megtekintheti a méretcsoport konfigurációjától származó változatok listáját.

### <a name="release-products-to-the-usmf-company"></a>Termékek kiadása az USMF vállalatnak

1. A Művelet ablaktáblán válassza ki a **Termékek kiadása** elemet.
1. A **Kiadandó termékek kiválasztása** oldalon ellenőrizze, hogy a *B0001* termékszám szerepel-e a listán, majd válassza a **Következő** lehetőséget.
1. A kiadandó termékváltozatok megerősítéséhez válassza a **Következő** lehetőséget.
1. A **Kiadási célként jelölt vállalatok** oldalon válassza ki az *USMF* elemet, majd válassza a **Következő** lehetőséget a kiválasztás jóváhagyásához.
1. A **Kiválasztás jóváhagyása** oldalon válassza a **Befejezés** parancsot a kiadás befejezéséhez.

    A „Művelet befejezve” üzenet jelenik meg.

### <a name="update-a-released-product-in-the-usmf-company"></a>Kiadott termék frissítése az USMF vállalatban

1. Győződjön meg róla, hogy be van jelentkezve az **USMF** vállalatba.
1. Lépjen a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre a kiadott termék létrehozásának befejezéséhez.
1. Keresse meg, és válassza ki a *B0001* cikkszámot a **Kiadott termék részletei** oldal megnyitásához.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. Győződjön meg arról, hogy az **Általános** gyorslapon a **Cikkmodellcsoport** mező értéke *FIFO*.
1. A Művelet panel **Termék** lapján, a **Beállítás** csoportban válassza a **Dimenziócsoportok** lehetőséget.
1. Adja meg az alábbi értékeket:

    - **Tárolásidimenzió-csoport:** *Áru*
    - **Nyomonkövetésidimenzió-csoport:** *Nincs*

1. Válassza ki az **OK** lehetőséget.
1. A Művelet panel **Termék** lapján, a **Beállítás** csoportban válassza a **Foglalási hierarchia** lehetőséget.
1. Állítsa be a **Foglalási hierarchia** mezőt az *Alapértelmezett* értékre, majd kattintson az **OK** gombra.
1. Az **Általános** gyorslap **Adminisztráció** részében figyelje meg, hogy a kiválasztások frissítve lettek-e.
1. A **Beszerzés** gyorslap **Ár** mezőjébe írja be a *10* értéket.
1. A **Költségek kezelése** gyorslapon, a **Cikkcsoport** mezőben adja meg az *Audio* értéket.
1. A **Beszerzés** gyorslap **Ár** mezőjébe írja be a *10* értéket.
1. A **Raktár** gyorslap **Egységszekvenciacsoport-azonosító** mezőjében adja meg az *ea* értéket.
1. Válassza a **Mentés** lehetőséget.

### <a name="create-a-location-directive"></a>Helyutasítási műveletek

1. Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.
1. A bal oldali ablaktáblában állítsa a **Munkarendelés típusa** mezőt a *Munkarendelések* értékre.
1. A listából válassza ki azt a helyutasítást, amely a *24 PO Közvetlen* névvel rendelkezik.
1. A **Helyutasítások műveletei** gyorslapon válassza az **Új** parancsot, ha egy sort szeretne hozzáadni a rácshoz.
1. Az új sorban állítsa be a következő értékeket:

    - **Sorszám:** *1*

        Az új sornak a korábban meglévő sor előtt kell lennie. A módosításhoz használja a **Mozgatás felfelé** és **Mozgatás lefelé** gombokat az eszköztáron, vagy módosítsa a meglévő sor **Sorszám** beállítását *2* értékre.

    - **Név:** *Betárolás az ÖMLESZTETT helyprofilhoz*
    - **Rögzített hely használata:** *Rögzített és nem rögzített helyek*
    - **Negatív készlet engedélyezése:** *Törölje a jelet a jelölőnégyzetből (=No)*
    - **Köteg engedélyezve:** *Törölje a jelet a jelölőnégyzetből (=No)*
    - **Stratégia:** *Nincs*

1. Az új sort továbbra is kijelölve, válassza a rács fölötti **Lekérdezés szerkesztése** elemet.
1. A lekérdezés párbeszédpanelen, a **Tartomány** lapon a **Hozzáadás** gombbal adjon hozzá egy sort a rácshoz.
1. Az új sorban állítsa be a következő értékeket:

    - **Tábla:** *Helyek*
    - **Származtatott tábla:** *Helyek*
    - **Mező:** *Hely profilazonosítója*
    - **Feltételek:** *BULK*

1. Válassza ki az **OK** lehetőséget.
1. A **Helyutasítások** oldalon, a műveleti ablaktáblán válassza a **Mentés** lehetőséget.

> [!NOTE]
> Ha a **Helyutasítási műveletek** gyorslap **Stratégia** mezőjében, ha a *Konszolidáció* helystratégiát használja, a **Termékdimenzió-kombinálás engedélyezett** gyorslap beállítását a **Helyprofilok** részen a rendszer felülbírálja, és a cikkek ugyanazon a helyen kerülnek elhelyezésre akkor is, ha ezt a viselkedést a beállítás nem engedélyezi.

### <a name="create-a-mobile-device-menu-item"></a>Mobileszköz-menüpont létrehozása

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
1. A művelet ablaktáblán válassza az **Új** parancsot a rendezéshez használandó menüelem létrehozásához.
1. A fejlécben állítsa be a következő értékeket:

    - **Menüelem neve:** *Beszerzési rendelési sor bevételezése*
    - **Cím:** *Beszerzési rendelési sor bevételezése*
    - **Mód:** *Munka*
    - **Meglévő munka használata:** *Nem*

1. Az **Általános** gyorslapon állítsa be a következő értékeket:

    - **Munkalétrehozási folyamat:** *Beszerzési rendelési sor bevételezése és eltárolása*
    - **Azonosítótábla létrehozása:** *Igen*

1. Válassza a **Mentés** lehetőséget.

### <a name="configure-the-mobile-device-menu"></a>A mobileszköz menüjének konfigurálása

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz menü** elemre.
1. A menük listáján válassza a **Bejövő** elemet.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. A **Rendelkezésre álló menük és menüelemek** listájában keresse meg és válassza ki a **Beszerzési rendelési sor bevételezése** menüelemet.
1. Válassza a jobbra mutató nyílgombot a **Beszerzési rendelési sor bevételezése** menüelem **Menüstruktúra** listában való elhelyezéséhez. Ily módon hozzáadja az új menüelemet a kijelölt menühöz.
1. Válassza a **Mentés** lehetőséget.

## <a name="scenario"></a>Forgatókönyv

Ez a forgatókönyv azt mutatja be, hogyan lehet ugyanazon a helyen két különböző termékváltozatot elhelyezni, amikor a helyprofil nem engedélyezi a vegyes cikkeket, de a *Helyi termékdimenzió-kombinálás* funkció engedélyezve van. Ebben az esetben a **Méret** változatot kell használni feltételként.

Kezdés előtt győződjön meg arról, hogy a *24*. raktárban üres helyek szerepelnek, amelyek az *ÖMLESZTETT* helyprofilt használják.

### <a name="create-a-purchase-order"></a>Beszerzési rendelés létrehozása

Olyan beszerzési rendelést hoz létre, amelynek három sora van: két sor ugyanannak a termékazonosítónak, de eltérő **Méret** változatokhoz, és egy harmadik sor egy másik termékhez, amely nem tartalmaz változatokat.

1. Nyissa meg a következőt: **Kötelezettségek \> Beszerzési rendelések \> Minden beszerzési rendelés**.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az **Beszerzési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - **Szállítói számla:** *1001*
    - **Raktár:** *24*

1. Válassza ki az **OK** lehetőséget.
1. A beszerzési rendelés létrejön, és a program új sort ad hozzá a **Beszerzésirendelés-sorok** gyorslapon. Jegyezze fel a beszerzési rendelés számát.
1. Az új sorban állítsa be a következő értékeket:

    - **Cikkszám:** *B0001*
    - **Méret** *L*
    - **Mennyiség:** *2*

1. Válassza ki a rács felett a **Sor hozzáadása** lehetőséget egy második beszerzési rendelési sor hozzáadásához, és állítsa be a következő értékeket:

    - **Cikkszám:** *B0001*
    - **Méret** *XL*
    - **Mennyiség:** *2*

1. Válassza ki a **Sor hozzáadása** lehetőséget egy harmadik sor hozzáadásához, és állítsa be a következő értékeket:

    - **Cikkszám:** *A0001*
    - **Mennyiség:** *1*

1. Válassza a **Mentés** lehetőséget.

### <a name="receive-purchase-order-lines-in-the-warehouse-app"></a>Beszerzési rendelési sorok fogadása a raktározási alkalmazásban

1. Jelentkezzen be a raktározási alkalmazásba olyan felhasználóként, aki a *24*. raktárban engedélyezve van.
1. Válassza ki a **Bejövő** menüt.
1. Válassza ki a **Beszerzési rendelési sor bevételezése** lehetőséget.
1. Válassza ki a **PONUM** mezőt, majd adja meg a beszerzési rendelés számát.
1. Hagyja jóvá a bejegyzést a lap alján látható jóváhagyás gombra (✔) kattintva.
1. Adja meg a sor számát a bevételezett beszerzési rendelésből. Válassza ki a **LINENUM** mezőt, majd a számbillentyűzeten adja meg az *1* értéket.
1. Hagyja jóvá a bejegyzést.
1. Írja be a fogadásra kerülő mennyiséget. Nyomja meg kétszer a pluszjelet (**+**) a **Mennyiség** mező értékének *2*-re.
1. Regisztrálja a bejegyzését a lap alján látható (✔) gombot megnyomva, majd hagyja jóvá a bejegyzést ismét a (✔) gombot megnyomva.
1. Tekintse meg a **Beszerzési rendelések: Betárolás** oldalon látható információkat. Ez a lap az elraktározáshoz létrehozott munkát jeleníti meg (1. munka).

    Az a hely, ahol a bevételezett cikkek eltárolásra kerülnek, az azonosítótábla, a cikk, a méret és az éppen befejezett **Beszerzési rendelési sor bevételezése** feladat mennyisége jelenik meg.

1. Erősítse meg az elraktározási munkát.
1. Ismételje meg a 4–11. lépést a 2. beszerzésirendelés-sor esetében. A 8. lépésben azonban adja meg az *1* mennyiséget.

    Az új elraktározási munka (2. munka) ugyanarra a helyre jön létre, mint az 1. munka.

1. Ismételje meg a 4–11. lépést a 2. beszerzésirendelés-sor esetében. A 8. lépésben adja meg a fennmaradó *1* mennyiséget.

    Az új elraktározási munka (3. munka) ugyanarra a helyre jön létre, mint az 1. munka és a 2. munka. Ennek oka az, hogy a rendszer a *Konszolidációs* helyutasítási stratégiát használja, és a **Termékdimenzió-kombinálás engedélyezett** gyorslap az *Ömlesztett* **Helyprofilok** beállításban lehetővé teszi a **Méret** változat kombinálását egy helyen.

1. Ismételje meg a 4–11. lépést a 3. beszerzésirendelés-sor esetében. A 8. lépésben adja meg az *1* mennyiséget az *A0001* cikkszámhoz.

    Az új elraktározási munka (4. munka) egy másik helyre jön létre, mint az 1. és 2. beszerzésirendelés-sorokhoz használt hely. Ennek oka az, hogy a hely profilja nem engedélyezi a vegyes termékeket, de lehetővé teszi ugyanannak az alapterméknek a vegyes dimenzióit.

1. Válassza ki a lap tetején látható Menü gombot (néha hamburgernek vagy a hamburgergombnak is nevezik), majd válassza ki a **Mégse** lehetőséget a **Beszerzési rendelési sor bevételezése** részből való kilépéshez.

> [!TIP]
> Ezt az esetet megismételheti, de ez alkalommal állítsa be a **Méret** - *Nem* értéket a **Termékdimenzió-kombinálás engedélyezése** gyorslapon, az *ÖMLESZTETT* **Helyprofilok** részen, hogy a cikkdimenziók egyikét se lehessen kombinálni. Ebben az esetben a beszerzési rendelés beérkezésekor a program az egyes termékváltozatokat új helyre helyezi.
