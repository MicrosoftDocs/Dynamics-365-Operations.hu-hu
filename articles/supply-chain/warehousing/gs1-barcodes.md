---
title: GS1-vonalkódok és QR-kódok
description: Ez a témakör leírja, hogyan kell beállítani a GS1 vonalkódokat és QR-kódokat, hogy a címkék beolvashatók legyenek a raktárban.
author: Mirzaab
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 8f438e18356a6c16cc75bb59153ae7353d984a5a
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500330"
---
# <a name="gs1-bar-codes-and-qr-codes"></a>GS1-vonalkódok és QR-kódok

[!include [banner](../includes/banner.md)]

A raktári dolgozóknak gyakran több feladatot is el kell végezniük, amikor egy mobileszköz szkennerét használják egy tétel, paletta vagy konténer mozgásának regisztrálására. Ezek a feladatok magukban foglalhatják mind a vonalkódok beolvasását, mind az információk manuális bevitelét a mobileszközön. A vonalkódok egy vállalat-specifikus formátumot használnak, amelyet a Microsoft Dynamics 365 Supply Chain Management segítségével határoz meg és kezel.

A GS1 vonalkód és QR-kód formátumokat a szállítási címkékhez azért fejlesztették ki, hogy globális szabványt biztosítsanak a vállalatok közötti adatcseréhez. A GS1 formátumok nemcsak kódolják az adatokat, hanem lehetővé teszik az adatok jelentésének meghatározásához az *alkalmazási azonosítók* előre meghatározott listájának használatát is. A GS1 szabvány meghatározza az adatformátumot és a különböző típusú adatokat, amelyek kódolására használható. A régebbi vonalkódokkal ellentétben a GS1 vonalkódok több adatelemet is tartalmazhatnak. Ezért egyetlen vonalkód beolvasásával többféle termékinformáció, például a tétel és a lejárati dátum is rögzíthető.

A GS1 támogatása a Supply Chain Managementben jelentősen leegyszerűsíti a szkennelési folyamatot a raktárakban, ahol a raklapok és konténerek címkézése GS1 formátumú kódok használatával történik. A raktári dolgozók egyetlen GS1 vonalkód beolvasásával minden szükséges információt kinyerhetnek. A GS1 vonalkódok a többszöri beolvasás és/vagy a kézi adatbevitel szükségességének kiküszöbölésével segítenek csökkenteni a feladatokkal járó időt. Ugyanakkor a pontosságot is javítják.

A logisztikai menedzsereknek kell összeállítaniuk az alkalmazásazonosítók szükséges listáját, és mindegyikhez hozzárendelniük a megfelelő mobileszköz menüpontokat. Az alkalmazási azonosítók ezután a raktárakban globális beállításként használhatók költözési és csomagolási célokra. Ezért az összes szállítási címke egységes formájú lesz.

Eltérő rendelkezés hiányában ebben a témakörben a *vonalkód* kifejezés a vonalkódokra és a QR-kódokra egyaránt vonatkozik.

## <a name="turn-on-the-gs1-feature"></a>Az GS1 funkció bekapcsolása

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Raktárkezelés*
- **Jellemző neve:** *GS1 vonalkódok beolvasása*

## <a name="set-up-global-gs1-options"></a>Globális GS1 opciók beállítása

A **Raktárkezelési paraméterek** oldal néhány olyan beállítást tartalmaz, amelyek globális GS1 opciókat határoznak meg.

A globális GS1 opciók beállításához kövesse az alábbi lépéseket.

1. Lépjen a **Raktárkezelés \> Beállítás \> Raktárkezelési paraméterek** részre.
1. A **Vonalkódok** gyorslapon állítsa be a következő mezőket:

    - **FNC1 karakter** - Megadja azokat a karaktereket, amelyeket a vonalkód elemzésekor előtagként kell értelmezni.
    - **Adatmátrix karakter** - Adja meg azokat a karaktereket, amelyeket előtagként kell értelmezni az adatmátrix elemzésekor.
    - **QR-kód karakter** - Adja meg azokat a karaktereket, amelyeket a QR-kód elemzésekor előtagként kell értelmezni.
    - **Csoportelválasztó** - Adja meg a vonalkód vagy QR-kód különálló részeit azonosító karaktert.
    - **Az azonosító maximális hossza** - Adja meg az alkalmazás azonosítójának megengedett maximális karakterszámát.

> [!NOTE]
> Az előtagok jelzik a rendszernek, hogy a vonalkód a GS1 szabványnak megfelelően titkosított. Egyidejűleg és különböző célokra legfeljebb három előtag **(FNC1 karakter**, **adatmátrix karakter** és **QR-kód karakter**) használható.

## <a name="gs1-application-identifiers"></a>GS1 alkalmazásazonosítók

A GS1 formátumok nemcsak kódolják az adatokat, hanem lehetővé teszik az adatok jelentésének meghatározásához az alkalmazási azonosítók előre meghatározott listájának használatát is. A logisztikai menedzsereknek kell összeállítaniuk az alkalmazásazonosítók szükséges listáját, és mindegyikhez hozzárendelniük a megfelelő mobileszköz menüpontokat. Az azonosítók ezután a raktárakban globális beállításként használhatók költözési és csomagolási célokra. Ezért az összes szállítási címke egységes formájú lesz.

A rendszer az adatokat, különösen az előre meghatározott alkalmazási azonosítókat használja fel a vonatkozó beolvasott információra alkalmazandó szabályok megállapításához.

Minden egyes alkalmazási azonosító jelzi a rendszernek, hogy a beolvasott vonalkódban a következő karaktereket titkosított információblokknak kell tekinteni. Az alkalmazási azonosítók beállítása határozza meg, hogy a rendszer hogyan értelmezze a vonalkódot, és hogyan mentse azt értékként a rendszerben.

A logisztikai vezetők használhatják a szabványos nemzetközi alkalmazásazonosítókat és/vagy létrehozhatják sajátjaikat.

### <a name="load-the-standard-application-identifiers"></a>A szabványos alkalmazásazonosítók betöltése

A gyors kezdéshez betöltheti a gyakori nemzetközi alkalmazásazonosítók listáját. A listát később igény szerint bővítheti vagy szerkesztheti.

A szabványos alkalmazásazonosítók betöltéséhez kövesse az alábbi lépéseket.

1. Menjen a **Raktárkezelés \> Beállítás \> GS1 \> GS1 alkalmazásazonosítók** pontra.
1. A Műveleti ablaktáblán kattintson az **Alapértelmezett beállítás létrehozása** elemre.

> [!WARNING]
> Az **Alapértelmezett beállítás létrehozása** parancs törli az összes jelenleg definiált alkalmazásazonosítót, és a szabványos listával helyettesíti azokat. Az alapértelmezett beállítások betöltése után azonban a listát igény szerint testre szabhatja.

### <a name="set-up-custom-application-identifiers"></a>Egyéni alkalmazásazonosítók beállítása

Ha az Ön vállalata által használt egyes vagy összes alkalmazásazonosító eltér a szabványos kódkészlettől, akkor a semmiből is létrehozhatja saját kódjait, vagy a szabványos kódkészletet az igényeinek megfelelően testre szabhatja.

A GS1 saját alkalmazásazonosítók beállításához és testreszabásához kövesse az alábbi lépéseket.

1. Menjen a **Raktárkezelés \> Beállítás \> GS1 \> GS1 alkalmazásazonosítók** pontra.
1. Tegye a következők egyikét:

    - Új azonosító létrehozása: Válassza a Műveletpanelen az **Új** lehetőséget.
    - Meglévő azonosító szerkesztése: Jelölje ki az azonosítót, majd a Műveletpanelen válassza a **Szerkesztés** lehetőséget.

1. Állítsa be a következő mezőket az új vagy kiválasztott azonosítóhoz:

    - **Alkalmazás azonosítója** - Adja meg az alkalmazás azonosítójának azonosító kódját. Ez a kód általában kétjegyű egész szám, de lehet hosszabb is. Tizedes értékek esetén az utolsó számjegy a tizedesjegyek számát jelzi. További információért lásd a lista későbbi részében a **Tizedesjegyek** jelölőnégyzet leírását.
    - **Leírás** - Adja meg az azonosító rövid leírását.
    - **Rögzített hosszúság** - Jelölje be ezt a jelölőnégyzetet, ha az alkalmazás azonosítójával beolvasott értékek rögzített karakterszámúak. Törölje ezt a jelölőnégyzetet, ha az értékek hossza változó. Ebben az esetben az érték végét a **raktárkezelési paraméterek** lapon megadott csoportelválasztó karakterrel kell jeleznie.
    - **Hosszúság** - Adja meg az alkalmazásazonosító használatával beolvasott értékekben megjelenő karakterek maximális számát. Ha a **Rögzített hosszúság** jelölőnégyzet be van jelölve, akkor pontosan ennyi karaktert várunk el.
    - **Típus** - Válassza ki az alkalmazásazonosító használatával beolvasott érték típusát *(numerikus*, *alfanumerikus* vagy *dátum*). A dátumok esetében az elvárt formátum: ÉÉÉÉÉHHNN (szóközök és kötőjelek nélkül).
    - **Decimális** - Jelölje be ezt a jelölőnégyzetet, ha az érték tartalmaz egy tizedesvesszőt. Ha ez a négyzet be van jelölve, a rendszer az alkalmazás azonosítójának utolsó számjegyét használja a tizedesjegyek számának meghatározásához. Ha például az alkalmazás azonosítója *3205*, akkor az érték jobb szélső öt számjegyét úgy értelmezi, hogy az a tizedesvessző után következik.

> [!NOTE]
> A **raktárkezelési paraméterek** lapon megadott csoportelválasztó nem kötelező, ha az alkalmazásazonosító által követett értéknek rögzített hosszúsága van, vagy ha a hossza maximalizált (azaz ha a hossza megegyezik az alkalmazásazonosítóhoz beállított **Hosszúság** értékkel).

## <a name="establish-the-generic-gs1-setup"></a>Az általános GS1 beállítás létrehozása

Az általános GS1 beállítás közös megfeleltetések gyűjteményét hozza létre. Ezek a hozzárendelések a mobilalkalmazás minden releváns beviteli mezőjét hozzárendelik ahhoz az alkalmazásazonosítóhoz, amely szabályozza, hogy a beolvasott vonalkódok értékeit hogyan kell értelmezni és tárolni az adott mezőben. Alapértelmezés szerint ezek a beállítások minden beolvasásra vonatkoznak az összes mobileszköz összes menüpontjára. Ezek azonban egy vagy több konkrét mezőre vonatkozóan felülírhatók egy adott menüponthoz rendelt GS1 házirenddel.

Az általános GS1 beállítás egyszerre csak egy érték beolvasását teszi lehetővé. Ezért ha több mező értékét szeretné egyetlen beolvasásból betölteni, akkor a megfelelő menüpontokhoz GS1 házirendet kell beállítania.

A GS1 irányelvekkel kapcsolatos további információkért lásd a következő szakaszt.

### <a name="load-the-standard-generic-gs1-setup"></a>A szabványos általános GS1 beállítások betöltése

A **GS1 általános beállítási** oldal lehetővé teszi a mobileszköz mezői és az alapértelmezett beállítás által létrehozott szabványos alkalmazásazonosítók közötti szabványos megfeleltetések betöltését.

Az általános GS1 beállítás létrehozásához lépjen a **Raktárkezelés \> Beállítás \> GS1 \> GS1 általános beállítás** pontra. Ezután válassza az **Alapértelmezett beállítás létrehozása** lehetőséget, hogy automatikusan hozzárendeljen egy megfelelő alkalmazásazonosítót minden egyes mezőhöz, amelyet jellemzően a mobileszközök menüpontjai használnak.

> [!WARNING]
> Ha már létezik bármilyen általános GS1 beállítás, az **alapértelmezett beállítás létrehozása** parancs teljesen törli azt, és betölti a szabványos beállítást.

### <a name="customize-the-standard-generic-gs1-setup"></a>A szabványos általános GS1 beállítás testreszabása

Az általános GS1 beállítás testreszabásához kövesse az alábbi lépéseket.

1. Menjen a **Raktárkezelés \> Beállítás \> GS1 \> GS1 általános beállítás**.
1. Tegye a következők egyikét:

    - Új leképezés létrehozása: Válassza a Műveletpanelen az **Új** lehetőséget.
    - Meglévő leképezés szerkesztése: Jelölje ki a leképezést, majd a Műveletpanelen válassza a **Szerkesztés** lehetőséget.

1. Állítsa be a következő mezőket az új vagy kiválasztott leképezéshez:

    - **Mező** - Válassza ki vagy adja meg a mobilalkalmazás beviteli mezőjét, amelyhez a bejövő értéket rendelni kell. Az érték nem az a megjelenített név, amelyet a dolgozók látnak. Ehelyett a kulcs neve az, amely a mezőhöz van rendelve a mögöttes kódban. Az alapértelmezett beállítás olyan mezők gyűjteményét biztosítja, amelyek valószínűleg hasznosak lehetnek, és intuitív kulcsneveket tartalmaz minden mezőhöz, valamint megfelelő programozott funkciókat. Előfordulhat azonban, hogy meg kell beszélnie a fejlesztő partnereivel, hogy megtalálja a megfelelő választékot a megvalósításhoz.
    - **Alkalmazásazonosító** - Válassza ki az alkalmazandó alkalmazásazonosítót, a **GS1 alkalmazásazonosítók** oldalon meghatározottak szerint. Az azonosító határozza meg, hogy a vonalkódot hogyan értelmezik és tárolják a megnevezett mező értékeként. Az alkalmazás azonosítójának kiválasztása után a **Leírás** mezőben megjelenik az alkalmazás leírása.

## <a name="set-up-gs1-policies-that-you-can-assign-to-mobile-device-menu-items"></a>GS1 házirendek beállítása, amelyeket hozzárendelhet a mobilkészülék menüpontjaihoz

A GS1 szabvány célja, hogy a dolgozók egyetlen vonalkód egyszeri beolvasásakor több értéket is betölthessenek. E cél eléréséhez a logisztikai vezetőknek olyan GS1-irányelveket kell beállítaniuk, amelyek megmondják a rendszernek, hogyan értelmezze a többértékű vonalkódokat. Később házirendeket rendelhet a mobileszközök menüpontjaihoz, hogy szabályozza, hogyan értelmezzenek egy vonalkódot, amikor a dolgozók beolvassák azt egy adott menüpont használata közben.

Ha egy menüponthoz nincs GS1-irányelv hozzárendelve, a rendszer csak egyetlen értéket tud rögzíteni. Ezt az értéket a GS1 általános beállítása szerint a dolgozó által a szkenneléskor kiválasztott mobilalkalmazás bemenetére kell alkalmazni. Ha a menüponthoz GS1 házirend van hozzárendelve, a rendszer továbbra is az általános GS1 beállításokat használja az első vonalkód értékének a kiválasztott mezőhöz való hozzárendeléséhez. Ezután azonban a vonatkozó házirendben meghatározottak szerint további mezőértékeket is rögzíthet.

### <a name="load-the-standard-specific-gs1-policies"></a>A GS1 szabványspecifikus irányelvek betöltése

A gyors kezdéshez betölthet egy GS1 irányelvkészletet. A házirendeket később igény szerint bővítheti vagy szerkesztheti.

A szabványos alkalmazásazonosítók betöltéséhez kövesse az alábbi lépéseket.

1. Menjen a **Raktárkezelés \> Beállítás \> GS1 \> GS1 házirend** pontra.
1. A Műveleti ablaktáblán kattintson az **Alapértelmezett beállítás létrehozása** elemre.

> [!WARNING]
> Az **Alapértelmezett beállítás létrehozása** parancs törli az összes jelenleg definiált házirendet, és a szabványos házirend-készlettel helyettesíti azokat. Az alapértelmezett beállítások betöltése után azonban a házirendeket igény szerint testre szabhatja.

### <a name="set-up-custom-specific-gs1-policies"></a>Egyedi GS1 házirendek beállítása

A GS1 házirendek beállításához és testreszabásához kövesse az alábbi lépéseket.

1. Menjen a **Raktárkezelés \> Beállítás \> GS1 \> GS1 házirend** pontra.
1. Tegye a következők egyikét:

    - Új házirend létrehozása: Válassza a Műveletpanelen az **Új** lehetőséget.
    - Meglévő házirend szerkesztése: Jelölje ki a házirendet a listarácson.

1. Az új vagy kiválasztott házirend fejlécében állítsa be a következő mezőket:

    - **Házirend neve** - Adja meg a házirend nevét.
    - **Leírás** - Adja meg a házirend rövid leírását.

1. A fejléc alatti gyorslapon képezze le a mezőneveket az aktuális házirendhez szükséges alkalmazásazonosítókhoz. Az eszköztáron található gombok segítségével tetszőleges sorokat adhat hozzá vagy távolíthat el. Az egyes sorokhoz állítsa be a következő mezőket:

    - **Mező** - Válassza ki vagy adja meg a mobilalkalmazás beviteli mezőjét, amelyhez a bejövő értéket rendelni kell. Az érték nem az a megjelenített név, amelyet a dolgozók látnak. Ehelyett a kulcs neve az, amely a mezőhöz van rendelve a mögöttes kódban. Az alapértelmezett beállítás olyan mezők gyűjteményét biztosítja, amelyek valószínűleg hasznosak lehetnek, és intuitív kulcsneveket tartalmaz minden mezőhöz, valamint megfelelő programozott funkciókat. Előfordulhat azonban, hogy meg kell beszélnie a fejlesztő partnereivel, hogy megtalálja a megfelelő választékot a megvalósításhoz.
    - **Alkalmazásazonosító** - Válassza ki az alkalmazandó alkalmazásazonosítót, a **GS1 alkalmazásazonosítók** oldalon meghatározottak szerint. Az azonosító határozza meg, hogy a vonalkódot hogyan értelmezik és tárolják a megnevezett mező értékeként. Az alkalmazás azonosítójának kiválasztása után a **Leírás** mezőben megjelenik az alkalmazás leírása.
    - **Rendezés** - Minden többértékű vonalkód tartalmaz egy sor alkalmazási azonosítót, amelyek mindegyikét egy-egy érték követi. A vonatkozó GS1-irányelv meghatározza, hogy az egyes adatbázis-mezőkhöz melyik alkalmazás-azonosítót kell hozzárendelni. Ha azonban egy vonalkód többször használja ugyanazt az alkalmazásazonosítót, a rendszer az alkalmazásazonosítók kódban való megjelenésének sorrendjét használja a mezőkhöz való hozzárendeléshez. Azon sorok esetében, amelyeknek egy vagy több másik sorral közös az alkalmazásazonosítója, használja ezt a mezőt annak megállapítására, hogy az egyező sorok milyen sorrendben kerülnek feldolgozásra. A legalacsonyabb rendezési értékkel rendelkező sor kerül először feldolgozásra.

> [!NOTE]
> Az egynél több azonos alkalmazásazonosítót tartalmazó vonalkódok esetében a **Rendezés** mezőt *kell* használnia a mezők sorrendjének megállapításához.

## <a name="assign-gs1-policies-to-mobile-device-menu-items"></a>GS1 házirendek hozzárendelése a mobileszközök menüpontjaihoz

Alapértelmezés szerint minden mobilkészülék menüpontja olyan beviteli mezőkkel rendelkezik, ahol a dolgozók egyetlen értéket szkennelhetnek be, az általános GS1 beállításoknak megfelelően. Ha azt szeretné, hogy a dolgozók egynél több mezőértéket is beolvashassanak egyetlen beolvasás során bármely mobileszköz menüpontjához, akkor az alábbi lépésekkel GS1-házirendet kell hozzárendelnie.

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
1. Menüpont létrehozása vagy megnyitása.
1. Az **Általános** gyorslapon állítsa be a **GS1 házirend** mezőt a menüpontra vonatkozó házirendre.

## <a name="gs1-setup-example"></a>GS1 beállítási példa

Ez a példa egy olyan rendszerre vonatkozik, ahol a GS1 opciók a következő módon vannak beállítva:

- A **Raktárkezelési paraméterek** lapon a következő globális beállítások kerülnek meghatározásra:

  - **FNC1 karakter:** *\]C1*
  - **Csoportszeparátor:** *\~*

- A **GS1 alkalmazás-azonosítók** oldalon a következő alkalmazás-azonosítók relevánsak e példa szempontjából.

    | Alkalmazásazonosító | Leírás | Rögzített hossz | Hossz | Típus | Decimális |
    |---|---|---|---|---|---|
    | 01 | GTIN | Kiválasztott | 14 | Numerikus | Törölve |
    | 10 | Köteg száma | Törölve | 20 | Alfanumerikus | Törölve |
    | 17 | Lejárati dátum | Kiválasztott | 6 | Dátum | Törölve |
    | 30 | Átvételi mennyiség | Törölve | 8 | Numerikus | Törölve |

- A **GS1 általános beállítási** lapon az általános GS1 házirend alábbi beállításai vonatkoznak erre a példára.

    | Mező | Alkalmazásazonosító | Leírás |
    |---|---|---|
    | ItemId | 01 | GTIN |

- A **GS1 házirend** oldalon van egy policy, ahol a **Policy név** mezőben a *Vásárlás fogadás* szerepel. Ez a szabályzat a következő sorokat tartalmazza.

    | Mező | Alkalmazásazonosító | Leírás | Rendezés |
    |---|---|---|---|
    | ExpDate | 17 | Lejárati dátum | 0 |
    | InventBatchId | 10 | Köteg száma | 0 |
    | Mennyiség | 30 | Átvételi mennyiség | 0 |

- A **Mobileszköz menüpontok** oldalon van egy menüpont, amelynek a neve *Vásárlás fogadás*. A **GS1 házirend** mezője *Vásárlás fogadás* értékre van beállítva.

Miután egy rendeléshez tartozó áru megérkezik a raktárba, a dolgozó a következő lépéseket követi.

1. A mobilkészüléken válassza a **Vásárlás fogadás** menüpontot.
1. Adja meg a megrendelés számát.
1. Válassza ki a **Tétel** mezőt, és olvassa be a következő vonalkódot: *\]C10100000012345678\~3030\~10b1\~17220215*.

A példában megadott beállítások miatt a rendszer a következőképpen elemzi a beolvasott vonalkódot.

| Mezőkulcs | Pályázat azonosítója | Érték | Bankjegy |
|---|---|---|---|
| ItemId | 01 | 00000012345678 | Mivel a dolgozó a **Tétel** mezőt szkennelte be, a vonalkód első értéke kerül hozzárendelésre ehhez a mezőhöz. A leképezés a GS1 általános beállításából származik. |
| Mennyiség | 30 | 30 | Mivel egyetlen beolvasás során több mezőérték kerül rögzítésre, ez a hozzárendelés és az összes többi hozzárendelés a **beszerzés fogadás** menüponthoz rendelt GS1 házirendből származik. Ez az érték a beérkezett mennyiség. |
| InventBatchId | 10 | b1 | Ez az érték a tétel azonosítója. |
| ExpDate | 17 | 220215 | A dátumformátum YYMMDD. Ezért a lejárat időpontja 2022. február 15. |

Ezután a bizonylat regisztrálásra kerül, és az egyszeri beolvasás után a megfelelő adatbázis-értékek bevitelére kerül sor.
