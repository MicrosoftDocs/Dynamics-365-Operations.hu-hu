---
title: Tárolók csomagolása szállításhoz
description: Ez a témakör ismerteti a csomagolási folyamatot, amellyel a készletcikkek ellenőrzése és tárolókba való csomagolása lehetővé teszi.
author: perlynne
ms.date: 7/13/2022
ms.topic: business-process
ms.search.form: WHSLocationType, WHSLocationProfile, WHSParameters, WHSContainerType, WHSPackProfile, WHSCloseContainerProfile, InventLocationIdLookup, UnitOfMeasureLookup, WHSPack, WHSContainerTable,
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 118b1c79d23cd1b5044ede9aa9c469409cd22166
ms.sourcegitcommit: 9e6a9d644a34158390c6e209e80053ccbdb7d974
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/20/2022
ms.locfileid: "9708783"
---
# <a name="pack-containers-for-shipment"></a>Tárolók csomagolása szállításhoz

[!include [banner](../../includes/banner.md)]

A tároló csomagolási folyamata lehetővé teszi a készleten lévő cikkek érvényesítését és tárolókba való csomagolását. A folyamat során a raktári dolgozók jellemzően az ömlesztett tárolóterületekről válogatják ki a készleten lévő cikkeket, és azokat egy csomagolási területre mozgatják. Több raktári dolgozó ellenőrzi a cikkmennyiségeket és -típusokat, és hozzárendeli őket a megfelelő tárolóméretekhez. Ha egy tároló teljesen be van csomagolva, akkor a tárolót lezárja a rendszer, és átkerül a kiszállítási területre, ahol a szállításra készként történik.

A tárolók olyan fizikai struktúrákat képviselnek, amelyekbe a cikkek csomagolva vannak, és nyomon követhetők a tárolók adatai a rendszerben. Ez az információ jól jöhet a szállítástervezés során, különösen, ha a szállítási költséget a tárolók alapján számítja ki. Szállítás előtt megtekintheti a szállítmányban használt tárolók számát, a használt tárolók típusait és az egyes tárolók fizikai méreteit (például a teljes térfogatot és a súlyt).

A tárolókhoz számos kapcsolódó kimenő raktári képesség használható. További információért tekintse át az alábbi cikkeket:

- [Hullám tárolóra szabása](wave-containerization.md)
- [Kimenő rendezés](outbound-sorting.md)
- [Kis csomagok szállítása](small-parcel-shipping.md)
- [Megerősítés és áthelyezés](confirm-and-transfer.md)
- [Különböző dimenziók beállítása csomagoláshoz és tároláshoz](packing-vs-storage-dimensions.md)
- [Csomagolási munka kimenő tárolók csomagolásához és szállítmányok feldolgozásához](packing-work.md)
- [Tárolók csomagolása a Raktárkezelés mobilalkalmazással](warehouse-app-packing-containers.md)
- [Példa erre – tárolók csomagolása a Raktárkezelés mobilalkalmazással](warehouse-app-pack-containers-scenario.md)
- [Tárolócímkék nyomtatása](print-container-labels.md)

## <a name="set-up-your-warehouse-to-use-manual-packing-operations"></a>Raktár beállítása kézi csomagolási műveletek használatára

A kimenő műveleteket kétféleképpen lehet rendszerezni:

- **Hullám létrehozása és feldolgozása** – a dolgozók a kimenő raktári munka alapján válogatnak ki cikkeket. Ezután közvetlenül a kimenő szállítási helyre szállítják a cikkeket, ahol készen állnak az azonnali szállításra. A folyamat beállításával és használatával kapcsolatos további információ [: Hullám létrehozása és feldolgozása](wave-processing.md).
- **Manuális csomagolás csomagolás csomagoláskor –** ez a művelet egy további műveletet is feldolgoz a kitárolási és a szállítási műveletek között. Ahelyett, hogy a készletet a *kiszállítási* helyre rakják, a dolgozók egy *csomagolási helyre rakják*. Ezután a csomagolóállomáson, **a** webes ügyfél Csomag lapján kezelhetik a csomagolási folyamatot. A folyamat engedélyezéséhez konfigurálnia kell a rendszert az ebben a szakaszban leírt módon.

### <a name="set-up-warehouse-locations-for-packing"></a>Raktári helyek beállítása csomagoláshoz

Legalább egy olyan csomagolási helynek kell lennie, ahol a dolgozók készleten lévő cikkeket fognak helyezni, hogy tárolókba csomagolják őket. A raktári helyek létrehozásáról [a WMS-funkcióval rendelkező raktárak konfigurálása funkcióban található további tájékoztatás](tasks\configure-locations-wms-enabled-warehouse.md). Az alábbi alszakaszok a csomagolási helyek létrehozásáról és beállítását írják le.

#### <a name="set-up-location-types-for-packing"></a>Helytípusok beállítása csomagoláshoz

Meg kell határoznia a csomagolási *helyek* helytípusát. A szűrési beállításokként használt helytípusokkal szabályozhatja a különböző raktárkezelési folyamatokat is. Az egyes helytípusok neve általában leír valamit arról, hogyan kell használni azt a helytípust. Az itt beállított helytípust társítva kell lennie minden olyan helyhez, amely csomagolási műveletekhez használatos.

A következő lépések szerint állíthatja be a helytípust.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Helytípusok** pontra.
1. A munkaablak új helytípusának **a** rácshoz való hozzáadásához válassza az Új lehetőséget.
1. Állítsa be a következő mezőket az új helytípushoz:

    - **Helytípus** – adja meg a helytípus nevét. Minden névnek egyedinek kell lennie, és le kell írnia valamit arról, hogyan kell használni a helytípust.
    - **Leírás** – adja meg a helytípus rövid leírását.

#### <a name="inform-the-system-about-the-packing-location-type"></a>A csomagolási hely típusának értesítése a rendszerről

Miután létrehozott egy helytípust, be kell állítania, hogy a rendszer felismerje csomagolási műveletekhez használt helytípusként.

A következő lépések szerint állíthatja be a csomagolási műveletekhez használt helytípust.

1. Ugrás a Raktárkezelés **beállítása – \>\> Raktárkezelési paraméterek**
2. A Helytípusok **gyorslap** **Általános** lapján állítsa a Csomagolás helytípus mezőt arra a helytípusra, **amely** a csomagolási hulladék azonosítására használható.

> [!NOTE]
> Ha egy verzióról frissít, Microsoft Dynamics AX akkor a rendszer eltávolítja a Csomagolás alatt állapotút a szállítmányból és a *rakományból*, mert az nem volt egységesen működik, és ezek felesleges adatokat okoztak. Ennek megfelelően **a Csomagjegyzék lapjain** **található** "Szállításban" és "Rakományok" elavult. A csomagolni kell tárolókat a hely szintjén követi nyomon a nyomon.
>
> A korábbi **verziókban** **·** **a** csomagolási helyet a Raktárkezelési paraméterek lap Csomagolás lapján található Csomagolási hely profilazonosító mező használatával adhatja meg a helyprofilt.*·* Az aktuális **verzióban** **·** **a** Raktárkezelési paraméterek lap Általános lapján található Csomagolás helytípus mező használatával lehet megadni a *hely* típusát, amint azt a jelen cikk ismerteti. Az új mező jobban igazodik az előkészítő helyek és a végső szállítási helyek azonosításához használt folyamathoz.
>
> Bár továbbra is **használhatja** a régi profilazonosítót a csomagolási hely mezőhöz, javasoljuk, **hogy** inkább az új Csomagolási hely típus mezőt használja, mivel a régi mezőre végül elavult lesz.
>
> Ha törli a csomagolási hely **régi** profilazonosítójának beállítását, majd menti az oldalt, a mező véglegesen letiltva marad. Olyan telepítés esetén, ahol **még** nem használta a csomagolási hely profilazonosítóját, mindig letiltva lesz. Miután a csomagolási hely **profilazonosító** mezőjének beállítását beállította, az ebben a cikkben ismertetett beállítások segítségével állíthatja be és azonosíthatja a csomagolási helyet.

#### <a name="set-up-location-profiles-for-packing-locations"></a>Csomagolási helyek helyprofiljainak beállítása

Minden *helyprofilban* olyan információkat és szabályokat határoz meg, amelyek a kapcsolódó helyekre érvényesek. Mivel csomagolási műveletekhez legalább egy hely szükséges, a helytípuson felül létre kell hoznia hozzá egy helyprofilt. Minden profilt számos hely használhatja. A csomagoláshoz használt helyeket be kell állítani az engedélytáblák nyomon követésére.

A következő lépések szerint állíthatja be a csomagolási hely helyprofilját.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Helyprofilok** pontra.
1. Válasszon ki egy létező profilt a listaablakból, **vagy válassza az Új** lehetőséget a munkaablakban új létrehozásához.
1. Az új vagy kiválasztott profil fejlécében állítsa be a következő mezőket:

    - **Helyprofil azonosítója** – adja meg a profil egyedi azonosítóját.
    - **Név** – adja meg a profil jól leíró nevét.

1. Az **Általános** gyorslapon állítsa be a következő mezőket:

    - **Helyformátum** – az aktuális helyhez használni kívánt helyformátum kiválasztása. A helyformátumok olyan elnevezési rendszert kínálnak, amely egyedi és konzisztens neveket hoz létre a raktárakban használt különböző hely rekeszpozíciókhoz. Ha még nem rendelkezik a kívánt formátummal, **\>\>\> létrehozhatja a Raktárkezelés beállítása raktári helyformátumok segítségével.** A további tudnivalókért lásd: [Helyek konfigurálása WMS szolgáltatással rendelkező raktárban](tasks/configure-locations-wms-enabled-warehouse.md).
    - **Helytípus** – a **cikk** korábbi leírásában leírtak szerint válassza ki a csomagolási hely típusaként megadott helytípust a Raktárkezelés paraméterei oldalon.
    - **Azonosítótábla követésének használata** – csomagolási helyek esetén állítsa Ezt a beállítást Igen *beállításra*. A rendszernek nyomon kell követnie az adatokat a csomagolási helyeken, hogy szabályozni tudja a csomagolási folyamatot.
    - **Negatív készlet engedélyezése** – csomagolási helyeknél állítsa ezt a beállítást Nem *beállításra*.
    - **Vegyes cikkek engedélyezése** – a csomagolási helyeknél állítsa Ezt a beállítást Igen *beállításra*. Erre a beállításra azért van szükség, mert jellemzően sok különböző cikkszám van egyszerre a csomagolási helyekre hozva.
    - **Vegyes készletállapotok engedélyezése** – csomagolási helyeknél állítsa Ezt a beállítást Igen *beállításra*. Ez a beállítás kötelező, mert a különböző készletállapottal cikkeket általában egyszerre kell a csomagolási helyekre hozni.
    - **Vegyes készletkötelyek engedélyezése** – a csomagolási helyeknél állítsa Ezt a beállítást Igen *beállításra*. Ez a beállítás automatikusan Igen, *ha a Vegyes cikkek* engedélyezése beállítás Igen **beállítású**.*·*

#### <a name="set-up-packing-locations"></a>Csomagolási helyek beállítása

Legalább egy olyan helynek kell *lennie*, ahol a dolgozók olyan készleten lévő cikkeket fognak helyezzenek, amelyek tárolókba kell csomagolni.

A következő lépések szerint adatokat adhat hozzá a csomagolási helyhez.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Helyek pontra**.
1. A munkaablak új hely **hozzáadásához** válassza az Új lehetőséget.
1. Az új hely következő mezőinek beállítása:

    - **Raktár** – adja meg azt a raktárt, ahol a csomagolási helynek léteznie kell.
    - **Hely** – adja meg az új hely nevét.
    - **Helyprofil azonosítója** – győződjön meg róla, hogy az előző szakaszban létrehozott azonosítót adja meg.

## <a name="set-up-the-packing-process"></a>A csomagolási folyamat beállítása

Ez a szakasz leírja, hogyan kell konfigurálni azokat a beállításokat, amelyek engedélyezik a csomagolási folyamatot, és lehetővé teszik a dolgozók számára a készlet tárolókba való csomagolását.

### <a name="set-up-container-packing-policies"></a><a name="packing-policy"></a>Konténerek csomagolási házirendjeinek beállítása

Minden *tároló csomagolási szabálya* meghatározza a tárolók feldolgozásának a folyamatát. Minden alkalommal, amikor új tárolót hoz létre, ki kell választania egy tárolóra vonatkozó csomagolási házirendet is.

Tárolók csomagolási irányelvének beállításához kövesse az alábbi lépéseket.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Tárolók \> Tárolócsomagolási házirendek** pontra.
1. Válasszon ki egy létező házirendet a listaablakból, **vagy** az Új gombra kattintva hozzon létre egy újat a munkaablakban.
1. Az új vagy kiválasztott házirend fejlécében állítsa be a következő mezőket:

    - **Tároló csomagolási irányelve** – adja meg a házirend egyedi nevét.
    - **Leírás** – adja meg a házirend jól leíró nevét.

1. Az Áttekintés **lapon** állítsa be a következő mezőket. Ezek a mezők határozzák meg, hogy milyen műveleteket kell tenni a tároló lezárása során, hogy a munka létrehozásakor vagy nélkül kell-e műveleteket használni, és mikor kell a tárolót ki adni a csomagoló állomásról.

    - **Raktár** – válassza ki azt a raktárt, ahol a csomagolási irányelv vonatkozik.
    - **Végső szállítmány alapértelmezett helye** – a lezárás után adja meg a tároló preferált helyét. Ez a mező csak akkor érhető el, ha **a** Tároló-kiadás irányelvmezője *a Végleges kiszállítási helyen való elérhetővé tenni beállításra van beállítva*.
    - **Rendezés alapértelmezett helye** – ez a mező a kimenő [rendezési képességekkel](outbound-sorting.md) használatos.
    - **Súlyegység** – válassza ki a tárolók lezáráskor és jegyzékbe állítva való jegyzékbe állítva használt alapértelmezett mértékegységét. Ez a mértékegység általában a csomagolóállomáson használt mérleg által használt mértékegység. Ez a mező a munka létrehozásával vagy anélküli irányelvekre vonatkozik.
    - **Tárolózárási irányelv** – válasszon a következő lehetőségek közül annak meghatározásához, hogy mi történik a tároló lezárásakor:

        - *Automatikus kiadás* – a rendszer a tárolót a csomagoló állomásról kiadottnak fogja tekinteni, **és** a rendszer kiváltja a Tároló-kiadási irányelv mezőben megadott műveletet.
        - *Késleltetett kiadás* – a tároló nem lesz azonnal kiadva a csomagolóállomásról. A raktári dolgozónak manuálisan kell kiadnia.
        - *Nem kötelező* – amíg egy dolgozó lezárja a tárolót, eldöntheti, hogy ki kell-e szabadítani a tárolót.

        Ha a csomagolóállomás elsősorban olyan tárolókat kezel, amelyek közvetlenül a vevőkhöz szállítják, akkor a leg természetesebb megoldás a tárolók azonnali kiadása. Ha a csomagolóállomás kezeli a több tárolóból vagy raklapból álló szállítmányokat, akkor valószínűleg jobb, ha elhalasztja a kiadást, amíg a teljes szállítmányt vagy raklapot be nem csomagolták, és készen nem állnak a felvételre.

    - **Tároló-kiadási** irányelv – válasszon a következő lehetőségek közül annak meghatározásához, hogy mi történik a tárolónak a csomagolási helyről való kiadásakor:

        - *Elérhetővé tenni a végső szállítási helyen* – a tároló frissítése a végső szállítási helyre. Ha ezt a lehetőséget választja, **az** Alapértelmezett hely a végső szállítmány mezőben adja meg a tároló preferált helyét a lezárás után.
        - *Tároló csomagolóállomásról* való áthelyezésére szolgáló munka létrehozása – olyan munka létrehozása, amely a tárolót a csomagolóállomásról az előkészítő területre vagy közvetlenül a ajtóba mozgatja. A Munkasablon **mezőben** lehet megadni a tároló munkához létrehozásakor alkalmazandó munkasablont.
        - *Tároló hozzárendelése kimenő rendezési pozícióhoz* – ez a beállítás a [kimenő rendezési képességekkel](outbound-sorting.md) használatos.

        A legtöbb esetben ajánlott a tárolók áthelyezését szolgáló munka létrehozása, mivel ez a megközelítés jobban képviseli a raktár tényleges manuális folyamatait. Egyszerű helyzetekben, vagy olyan helyzetekben, amikor a csomagolóállomás közvetlenül az ajtó területén található, akkor előnyösebb, ha a tároló azonnal elérhető lesz a végső kiszállítási helyen.

    - **Munkasablon** – a tárolóhoz létrehozott munka létrehozásakor alkalmazandó munkasablon kiválasztása. Ez a mező csak akkor **érhető** *el*, ha a *Tároló-kiadás házirend mezőjében a Csomagolóállomásról áthelyezhető tároló olyan munka van beállítva, amely egy Csomagolt tároló kitárolás nevű munkarendelés-típushoz kapcsolódik.* A további tudnivalókat lásd: [Munkasablonok és Hely irányelvek](control-warehouse-location-directives.md).

    A további lépésekben a jegyzékfájlokkal kapcsolatos beállításokat kell *konfigurálni*. A jegyzékbe történő berakodás egy tároló, tárolócsoport vagy szállítmány súlyának, valamint a szállítmányszolgáltatótól kapott követési azonosítónak a megadására szolgáló folyamat. Dynamics 365 Supply Chain Management A<a0/<a0/<a2/<a2/<a2/<a3 Ehelyett a raktári dolgozóknak ki kell nyomtatniuk a szállítmányozási szolgáltatótól kapott címkéket, majd be kell olvasniuk a nyomkövetési számot a jegyzékfájl-eljárás befejezésekor.

    Mivel a jegyzékbe vevőnként és szállítmányonként is eltérőek a követelmények, ezért a csomagolási irányelvek nagy rugalmasságot engedik meg a munkafolyamatban. A tárolókhoz, tárolócsoportokhoz és szállítmányokhoz bármilyen kombinációban be lehet állítani jegyzékfájlokat.

    Ha többszintű jegyzékfájl-eljárást használ, a dolgozóknak minden tárolót jegyzékbe kell helyezniük, mielőtt a kapcsolódó tárolócsoportot jegyzékbe állítják, és minden tárolócsoportot jegyzékbe kell helyezniük, mielőtt a kapcsolódó szállítmányt jegyzékbe állítják.

1. A tároló jegyzékfájl **gyorsfájlján** állítsa be a következő mezőket:

    - **Automatikus jegyzékfájl a tároló lezárásakor** – a jegyzékfájl-adatok tárolózárási *folyamat részeként való alkalmazásához állítsa Igen* beállításra. Ha nem használ szállítási integrációt, manuálisan kell rögzíteni az adatokat.
    - **Tárolóra vonatkozó jegyzékfájl-követelmények** – válasszon a következő lehetőségek közül:

        - *Nincs* – nem használ jegyzékfájl-folyamatot.
        - *Kézi* – a csomagolási munkafolyamat kötelezően jegyzékbe ástat. A rendszer mindaddig nem engedélyezi a tárolók zárása vagy felszabadításat, amíg be nem fejeződik a jegyzékfájl.
        - *Szállításkezelés* – a jegyzékbe ékezés a szállításkezelő (TMS) díjmotorokkal történik. Mivel ez a beállítás egyéni fejlesztést igényel egy adott szállítmányozási motor megvalósításához, az aktuális verzióban nem fog működni.

    - **Tároló tartalmának** nyomtatása – *a* tároló tartalomjelentésének automatikus nyomtatása Igen beállítással a tárolókat lezártként regisztrálva lehet. A jelentés igény szerint is kinyomtatható.

1. Válasszon a **következő lehetőségek közül** a Tárolócsoport jegyzékfájlja **gyorsfájl** jegyzékfájlja tárolócsoport mezőjében:

    - *Nincs* – a tárolócsoport jegyzékfájlja nem fog követelményként szerepelni a csomagolási munkafolyamatban.
    - *Kézi* – a tárolócsoport jegyzékfájlja követelményként fog szerepelni a csomagolási munkafolyamatban. A csoportba foglalt összes tárolót le kell zárni, és csak ezt után lehet jegyzékbe venni. Akkor válassza ezt a lehetőséget, ha kötelező megadnia egy jegyzékfájlt minden olyan tárolócsoporthoz, amely a csomagoló állomásra van csomagolva. Ezt a beállítást általában akkor kell választani, ha a tárolók egy raklapra vannak csomagolva, és a teljes raklap jegyzékbe van stb.

    > [!NOTE]
    > A jelenlegi verzió nem támogatja a tárolócsoportokhoz a jegyzékfájl-jelentéseket, és a tárolócsoportokhoz nincs TMS-motortámogatás.

1. Állítsa be **a következő mezőket a Szállítmány jegyzékfájl** gyorsmezőiben:

    - **Szállítmány követelményének jegyzékbeba** része – válasszon a következő lehetőségek közül:

        - *Nincs* – a szállítmány jegyzékfájlja nem fog követelményként szerepelni a csomagolási munkafolyamatban.
        - *Kézi* – a szállítmány jegyzékfájlja követelményként fog szerepelni a csomagolási munkafolyamatban. A szállítmány tárolói mindaddig nem adták ki, amíg be nem fejeződik a jegyzékfájl.
        - *Szállításkezelés* – a jegyzékbe ékezés a TMS-díjmotorokkal történik. Mivel ez a beállítás egyéni fejlesztést igényel egy adott szállítmányozási motor megvalósításához, az aktuális verzióban nem fog működni.

        A szállítmányok jegyzékfájlját engedélyezni kell, ha a csomagoló állomásra csomagolt teljes szállítmányhoz ki kell kitöltötte a jegyzékfájlt. Általában akkor használatos, amikor egy összesített jegyzékfájlra van szükség, még akkor is, ha a szállítmány több tárolóból vagy tárolócsoportból áll.

    - **Szállítólevél nyomtatása** – a csomagjegyzéknek a *szállítmány jegyzékfájl részeként való automatikus nyomtatása Igen* beállítással. A csomagjegyzék igény szerint is nyomtatható.

### <a name="set-up-container-types"></a>Tárolótípusok beállítása

A kézi csomagolási folyamat során a cikkeket csak azt megelőzően kell létrehozni a tárolókat, hogy a cikkek ebbe a csomagolásba csomagolhatóak. Minden tárolónak olyan tárolótípuson kell *alapulni*, amely meghatározza a tároló maximális fizikai térfogatát és súlyát.

A következő lépések szerint hozhat létre tárolótípust.

1. Ugrás a Raktárkezelés **– \> Tárolók \> beállítása típusú \> tárolókhoz**
1. A műveletpanel új tárolótípus **hozzáadásához** válassza az Új lehetőséget.
1. Állítsa be a következő mezőket az új tárolótípushoz:

    - **Tárolótípus kódja** – adja meg a tárolótípus egyedi azonosítóját.
    - **Leírás** – adja meg az új tárolótípus leírását.
    - **Tárasúly** – adja meg a tároló tényleges vagy becsült súlyát.
    - **Maximális nettó tömeg** – adja meg a maximális súlyt, amit a tároló képes berakodni.

1. A Tároló dimenziók szakasz Hossz, **Szélesség**, **·** **·** **Magasság és Térfogat** mezőjébe írja be magát a tároló fizikai méreteit.**·**
1. A Maximumok **szakasz** Hossz, **Szélesség**, **·** **·** **Magasság** és Térfogat mezőjébe írja be a tároló számára kezelhető maximális fizikai méreteket.
1. További attribútumokat is meghatározhat olyan tárolótípusokhoz, amelyek más, tárolókat tartalmazó műveletekhez kapcsolódnak. További információ a Tárolóra ásás [tudnivalókban található](wave-containerization.md).

> [!NOTE]
> A kézi csomagolási folyamathoz **a** **·** **rendszer csak a Maximális nettó tömeg mező értékét és a Maximumok szakasz Térfogat mezőjének értékét** használja.

### <a name="set-up-packing-profiles"></a>Csomagolási profilok beállítása

*A csomagolási* folyamathoz csomagolási profilok szükségesek. Alapértelmezés szerint kiválasztható vagy beállítható, amikor a **Csomagolás lapon csomagolási műveletet indít** el.

Csomagolási profil beállításához kövesse az alábbi lépéseket:

1. Ugorjon a **Raktárkezelés \> Beállítás \> Csomagolás \> Csomagolási profilok** pontra.
1. Válasszon ki egy létező profilt a listaablakból, **vagy válassza az Új** lehetőséget a munkaablakban új létrehozásához.
1. Az új vagy kiválasztott profil fejlécében állítsa be a következő mezőket:

    - **Csomagolási profil azonosítója** – adja meg a profil rövid azonosítóját.
    - **Leírás** – adja meg a csomagolási profil leírását.
    - **Tároló csomagolási irányelve** – válassza ki a profilra vonatkozó csomagolási házirendet. A további tudnivalókat lásd a Cikk tároló [csomagolási](#packing-policy) irányelveinek beállítása című részében.
    - **Tárolóazonosító mód** – annak beállítása, hogy a tároló létrehozásakor automatikusan létre legyen-e hozva egy tárolóazonosító, vagy manuálisan kell létrehozni.
    - **Tárolótípus** – az új tárolók létrehozásakor alapértelmezés szerint használt tárolótípus kiválasztása.
    - **Tároló automatikus létrehozása** a tároló bezárásakor – jelölje be ezt a jelölőnégyzetet, ha automatikusan létre kell hoznia egy új tárolót, ha az előző tárolót lezárták, és egy vagy több sor megmarad az aktuális szállítmányban.

### <a name="set-up-warehouse-workers"></a>Raktári dolgozók beállítása

**·** *Minden* felhasználónak vagy dolgozónak, aki a webes ügyfél Csomag lapján vagy a Raktárkezelés mobilalkalmazás Csomagolási tevékenység kódjával csomagolja a tárolókat, egy olyan felhasználói fiókkal kell rendelkezik, amely ahhoz a dolgozó-/*személyrekordhoz van társítva, amelybe a* szükséges biztonsági hozzáférési jogok kapcsolódnak. (A felhasználók beállításának további tudnivalókat lásd: [Új felhasználók létrehozása](../../fin-ops-core/dev-itpro/sysadmin/tasks/create-new-users.md).)

A következő lépések szerint állíthatja be a dolgozó vagy *személy rekordját a* csomagolási folyamathoz.

1. Ugrás a **Raktárkezelés \> Beállítás \> Dolgozó** elemre.
1. Munkafelhasználó hozzáadásához a munkaablakban **válassza az Új** lehetőséget.
1. A Dolgozó **mező** beállítása arra **a meglévő dolgozói rekordra, amely az Emberi** erőforrások modulban meg van adva ahhoz a felhasználóhoz, aki a csomagolási folyamatot el fogja látni.
1. A **Profil** gyorslapon állítsa be a következő mezőket:

    - **Tároló csomagolási irányelve** – Olyan tárolóra vonatkozó csomagolási házirend kiválasztása, amely meghatározza a tárolóknak a csomagolóállomáson való feldolgozásának módját. A kiválasztott tároló csomagolási irányelve előre ki lesz választva a dolgozóhoz a csomagolóállomás megnyitásakor. A további tudnivalókat lásd a következő post post: [Továbbfejlesztett csomagolási funkciók](https://cloudblogs.microsoft.com/dynamics365/no-audience/2016/12/01/improved-packing-functionality-dynamics-365-for-operations-1611).
    - **Csomagolási profil azonosítója** – válasszon egy csomagolásiprofil-azonosítót, amely meghatározza a használni kívánt csomagolási házirendet és tárolóbeállításokat. Ha a kiválasztott csomagolási profil azonosítója tároló csomagolási irányelvhez van társítva, **akkor** ezen a lapon nem módosíthatja a Tároló csomagolási irányelv mezőjének beállítását.

1. Az Alapértelmezett **csomagolóállomás** gyorsoldalon válassza ki a dolgozóra vonatkozó alapértelmezett helyet, raktárat és helyet.
1. Ha a dolgozó a Raktárkezelés mobilalkalmazás segítségével fogja kezelni és regisztrálni a tárolóra rakodó munkát, **a** Felhasználók gyorssávban állítson be egy vagy több fiókot, amelyek használatával a dolgozó bejelentkezhet az alkalmazásba. A további tudnivalókat lásd [a mobileszköz-felhasználói fiókokban](mobile-device-work-users.md).

## <a name="example-scenario"></a><a name="scenario"></a>Példaforgatókönyv

Ez a szakasz egy olyan példát mutat be, amely bemutatja, hogyan lehet rendelést létrehozni és csomagolni a cikkeket.

### <a name="make-sample-data-available"></a>A mintaadatok elérhetővé tétele

Ha ezt a forgatókönyvet az itt megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos [demóadatok](../../fin-ops-core/fin-ops/get-started/demo-data.md) telepítve vannak. Emellett az **USMF** jogi személyt is ki kell választani a kezdés előtt.

Ez az eset a termelési rendszeren használt funkció használatának útmutatásaként is használható. Ebben az esetben azonban az itt leírt mindegyik beállítás esetében be kell helyettesítenie a saját értékeit.

### <a name="sign-in-as-a-user-that-can-do-packing-work"></a>Jelentkezzen be felhasználóként, aki csomagolási munkát tud dolgozni

Jelentkezzen be az Ellátásilánc-kezelés szolgáltatásba egy olyan felhasználói fiók használatával, amely rendelkezik a tárolók csomagolásához szükséges engedélyekkel. A user *Demo Funderburk* a bemutatóadatok közé tartozik, és rendelkezik a szükséges engedélyekkel. Ennek a felhasználónak rendszergazdai azonosítója *van*.

### <a name="create-a-sales-order-and-complete-the-work"></a>Értékesítési rendelés létrehozása és a munka befejezése

Kövesse ezeket a lépéseket egy értékesítési rendelés létrehozásához, és hajtsa végre a megrendelt cikkeknek a csomagolóállomásra való áthelyezését.

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen, a **Vevői számla** mezőben válassza ki azt az *US-005* értéket.
1. Az **OK** gombbal zárja be a párbeszédpanelt.
1. Az új értékesítési rendelés megnyílik, és egyetlen, üres sort tartalmaz az Értékesítésirendelés-sorok **gyorsábraban**. Állítsa be a következő értékeket az új rendelési sorhoz:

    - **Cikkszám:** *A0001*
    - **Mennyiség:** *2*
    - **Telephely:** *6*
    - **Raktár:** *62*

1. Amíg a rendeléssor ki van választva, válassza **\>** **a** Készletfoglalás lehetőséget az Értékesítésirendelés-sorok gyorspult eszköztárán.
1. A **Foglalás** oldalon, a Művelet panelen válassza ki az **Adag foglalása** lehetőséget, hogy lefoglalja a kiválasztott sor teljes mennyiségét a raktárban.
1. Zárja be a **Foglalás** lapot, hogy visszatérjen az értékesítési rendeléshez.
1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.

    Egy üzenet jelzi a rendelés szállítmány- és hullám-adóit.

1. Amíg a rendeléssor ki van választva, válassza **ki a Raktári** \> **·** **munka** részleteit az Értékesítésirendelés-sorok gyorspult eszköztárán. Ha a hullámok futtatására kötegelt feldolgozást használ, lehet, hogy kis időt kell várnia a munka munkához való létrehozására.
1. A Munka **lap** Munka ablaktábla Munka **lapján** válassza a Kész **munka lehetőséget**.
1. A Munka kitöltése **lapon** állítsa a Felhasználói **azonosító** *mezőt 62-re.*
1. A műveletpanelen válassza a Munka érvényesítése **lehetőséget**.
1. Ha a munka érvényességét jelző üzenet jelenik meg, **·** *a* Készleten lévő cikkek kitárolási folyamatának befejezéséhez és a Csomag helyre való elküldához válassza a Kész munka lehetőséget.
1. Jegyezze fel **a** felső rácsban a munkához megjelenő szállítmányazonosító értékét.

### <a name="pack-the-ordered-items-into-a-container"></a>A megrendelt cikkek csomagolása egy tárolóba

A készlet cikkei már a csomagolási területre vannak hozva, és készen állnak a tárolókba való csomagolásra. A következő lépések szerint hozzon létre egy új tárolót a rendszerben, és csomagolja be.

1. Nyissa meg a **Raktárkezelés \> Csomagolási és tárolólétrehozás \> Csomagolás** menüt.
1. A **Csomagolóállomás kiválasztása** párbeszédpanelen adja meg a következő értékeket:

    - **Telephely:** *6*
    - **Raktár:** *62*
    - **Hely:** *Csomag*
    - **Csomagolási profil azonosítója:** *WH62*

1. Válassza ki az **OK** lehetőséget.
1. A Csomag **lap** Azonosítótábla **vagy** szállítmány mezőben adja meg a korábban említett szállítmányazonosítót. Most a Nyitott sorok gyorstáraban **látnia** kell a még ki nem csomagolt cikkeket.
1. A műveletpanelen válassza ki **az Új tárolót**, ha tárolót hoz létre a rendszerben.
1. Az új **tároló párbeszédpanel** azonosítójában állítsa **a Tárolótípus** *mezőt SmallBox típusú mezőre*.
1. A **tároló létrehozásához kattintson az OK** gombra.
1. A **Csomag lapra való visszatéréshez** kattintson az **OK** gombra. A **Nyitott tárolók** gyorsábra most a **létrehozott** tároló tárolóazonosító-értékét jeleníti meg.
1. Erre az esetre csak az egyik megrendelt cikk csomagolja be most. Ezért a Cikk csomagolása **gyorscsoporton** állítsa be a következő értékeket:

    - **Mennyiség:** *1.00*
    - **Azonosító:** *<a0001*

    Közvetlenül az azonosító értékének **kiválasztása** után a lap frissíti a Nyitott sorok és az Összes sor gyorslap értékét annak jelzésére, **·** **hogy** egy cikk be van csomagolva. Az A0001 cikk két darabja *közül az egyiket kell csomagolni*.

1. A műveleti ablaktáblán kattintson az **Tároló bezárása** elemre.
1. A Tároló **bezárása párbeszédpanelen** válassza **a** Rendszer tömegének beszúrása lehetőséget, ha ki kell töltenie az alapértelmezett **bruttó tömeg** értékét.
1. A **tároló az OK** gombra való bezáráshoz.

> [!TIP]
> A tárolók a környezet alapján többféleképpen is megtekinthetők. Például szállítmány csomagolása során gyakran hasznos lehet vagy a szállítmány részét tartalmazó tárolók, vagy az összes olyan tároló megtekintése, amely fizikailag egy csomagolóállomáson van. A **Csomagolóállomás** lapon olyan gombok vannak, amelyek használatával megtekinthető egy csomagoló állomás minden nyitott és lezárt tárolója. Ezek a nézetek nem korlátozódnak egy adott szállítmányra. Nagyon hasznosak lehetnek abban a helyzetben, amikor egy dolgozó egy tárolót csomagol, egy másik pedig jegyzékbe tudja helyezni és feloldja a tárolót.
>
> Az összes tároló összesített nézete is elérhető. Ez a nézet elsősorban olyan felhasználók számára hasznos, akik egyetlen csomagolóállomás környezetében dolgoznak. A látható hely a Raktárkezelés – Csomagolás **\> és tárolóra \> tároló tárolóknál található**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
