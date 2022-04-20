---
title: GS1 vonalkódok
description: Ez a témakör leírja, hogyan kell beállítani a GS1 vonalkódokat és QR-kódokat, hogy a címkék beolvashatók legyenek a raktárban.
author: Mirzaab
ms.date: 03/21/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 083748d4aecf551fd326b6c3cbf6d92cf3daf717
ms.sourcegitcommit: d475dea4cf13eae2f0ce517542c5173bb9d52c1c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547816"
---
# <a name="gs1-bar-codes"></a>GS1 vonalkódok

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- Preview until 10.0.25 GA -->

A raktári dolgozóknak gyakran több feladatot is el kell végezniük, amikor egy mobileszköz szkennerét használják egy tétel, paletta vagy konténer mozgásának regisztrálására. Ezek a feladatok magukban foglalhatják mind a vonalkódok beolvasását, mind az információk manuális bevitelét a mobileszközön. A vonalkódok egy vállalat-specifikus formátumot használnak, amelyet a Microsoft Dynamics 365 Supply Chain Management segítségével határoz meg és kezel.

A GS1 vonalkódok szállítási címkékhez úgy vannak kialakítottak, hogy globális szabványt kínálnak a vállalatok közötti adatcseréhez. Ezek lineáris (1D) szimbólumformátumban (vonalkódformátumban) is elérhetők, például A GS1-128 és 2D szimbólumként, például a GS1 DataMatrix és a GS1 QR kódban. A GS1 vonalkódok nemcsak az adatok kódolását, hanem az *alkalmazásazonosítók* előre meghatározott listájának használatát is lehetővé t használják az adatok jelentésének meghatározására. A GS1 szabvány meghatározza az adatformátumot és a különböző típusú adatokat, amelyek kódolására használható. A régebbi vonalkódszavaitól eltérően a GS1 vonalkódoknak több adateleme is lehet. Ezért egyetlen vonalkód beolvasásával többféle termékinformáció, például a tétel és a lejárati dátum is rögzíthető.

Az Ellátásilánc-kezelés GS1-támogatásával egyszerűen le lehet egyszerűsíteni a raktárak beolvasását, ahol a raklapok és a tárolók GS1 formátumú vonalkódok alapján vannak megcímkézve. A raktári dolgozók egyetlen GS1 vonalkód beolvasásával minden szükséges információt kinyerhetnek. A GS1 vonalkódok a többszöri beolvasás és/vagy a kézi adatbevitel szükségességének kiküszöbölésével segítenek csökkenteni a feladatokkal járó időt. Ugyanakkor a pontosságot is javítják.

A logisztikai menedzsereknek kell összeállítaniuk az alkalmazásazonosítók szükséges listáját, és mindegyikhez hozzárendelniük a megfelelő mobileszköz menüpontokat. Az alkalmazási azonosítók ezután a raktárakban globális beállításként használhatók költözési és csomagolási célokra. Ezért az összes szállítási címke egységes formájú lesz.

Eltérő rendelkezés *hiányában* ez a témakör a "vonalkód" kifejezés segítségével lineáris (1D) és 2D vonalkódra is hivatkozhat.

## <a name="the-gs1-bar-code-format"></a>A GS1 vonalkódformátum

A GS1 Általános specifikációk határozzák meg, hogy mely szimbólumokat lehet használni a GS1 vonalkódokkal, és hogyan kell a vonalkódba kódolni az adatokat. Ez a szakasz a témakör rövid bevezetőjében található. A teljes részleteket lásd [a GS1 általános specifikációkban](https://www.gs1.org/docs/barcodes/GS1_General_Specifications.pdf), amelyek a GS1 által közzétettek. A GS1 specifikációs dokumentumot rendszeresen frissítik, és a GS1 általános specifikációk 22.0-s kiadásában naprakészek.

A GS1 vonalkódok a következő szimbólumokat használják:

- **Lineáris vagy 1D vonalkódok** – GS1-128 és GS1 DataBar
- **2D vonalkód** – GS1 DataMatrix, GS1 QR code és GS1 Dotcode

Ne feledje, hogy a GS1 és a GS1-128 speciális eset a normál Code-128 lineáris vonalkód, a GS1 DataMatrix és a GS1 QR-kód különleges esete. A GS1 verzió és a nem GS1 verzió közötti különbség egy speciális karakter (FNC1) jelenléte a vonalkódadatok között. Az FNC1 karakter jelenléte azt jelzi, hogy a vonalkódban szereplő adatokat a GS1 szabvány szerint kell értelmezni.

A vonalkódban található adatok több adatelemből áll, amelyek mindegyikét a mező elején egy alkalmazásazonosító azonosítja. A vonalkód alatt általában az adatok is olvasható formátumban jelennek meg, zárójelben az alkalmazásazonosító. Íme egy példa: `(01) 09521101530001 (17) 210119 (10) AB-123`. Ez a vonalkód három elemet tartalmaz:

- **01- es** alkalmazásazonosító – a cikk GS1 globális kereskedelmi cikkszáma (GTIN-száma).
- **17- es alkalmazásazonosító** – a lejárat dátuma.
- **10- es** alkalmazásazonosító – a köteg száma.

Az adatok mindegyik eleméhez vagy előre meghatározott hosszúságú, vagy változó hosszúságúak lehetnek. Az előre megadott hosszúságú alkalmazásazonosítók listája rögzített. Minden más alkalmazásazonosító változó hosszúságú, és a GS1 alkalmazásazonosító listája határozza meg az adatok maximális hosszát és formátumát. Például a 01-es alkalmazásazonosító előre meghatározott, 16 karakterből áll (maga az alkalmazásazonosítóból 2, a GTIN-hez pedig 14), a 17-es azonosítóba pedig egy előre definiált 8 karakterből áll (kettő maga az alkalmazásazonosító, majd hat a dátumra). A 10-es alkalmazásazonosítónak azonban két száma van maga az alkalmazásazonosító, és legfeljebb 20 alfanumerikus karakter.

Az elemek összerakása esetén egy elem változó hosszúságú elemet követ, egy elválasztó karaktert kell használni. Ez az elválasztó lehet egy speciális FNC1 karakter vagy egy csoportelválasztó karakter (olyan nem nyomtatható karakter, amely ASCII-kódot és 1D hexadecimális kódot tartalmaz). Az elválasztó nem használható az utolsó elem után. Bár az előre megadott hosszúságú elemek után nem szabad használni az elválasztót, a jelenlét nem kritikus hiba.

A 01-es, 17-es és 10-es alkalmazásazonosítókat tartalmazó vonalkód előző példájának vonalkód-adataiban a Kód-128, QR-kód vagy DataMatrix `<FNC1>`**`01`**`09521101530001`**`17`**`210119`**`10`**`AB-123` szimbólum adatai úgy lesznek kódolva, hogy (az alkalmazásazonosítók félkövér formátumban jelennek meg). Az a legjobb megoldás, ha minden változó hosszúságú elemet a végére kell tenni, hogy ne legyen szükség további csoportelválasztó karakterre. A vonalkód elemeinek sorrendje azonban eltérő lehet, az elválasztót pedig kötelező megadni. Példa: `<FNC1>`**`01`**`09521101530001`**`10`**`AB-123<GS>`**`17`**`210119`

### <a name="dates-and-decimal-numbers"></a>Dátumok és tizedesjegyek

A dátumok mindig *YYMMDD* formátumban vannak ábrázolva, ahol az év századát a GS1 előírásai határozzák meg. Csak az elmúlt 49 évtől a jövőben 50 évig (az aktuális évhez képest) lehet ábrázolni a dátumokat.

Egyes adatelemek tizedesjegyeket tartalmaznak. Például 3100, 3101, ... A 3105 kilogrammban mért nettó tömeg. Mivel ezek az alkalmazásazonosítók előre meghatározott hossza 10, a mennyiséghez hat szám érhető el. A tizedespont pozícióját az alkalmazásazonosító utolsó száma adja meg. Ebből következően ez a pályázati azonosítók *310n-ként is ábrázolható*. Mivel a GS1 szabvány szerint mindig legalább egy számnak kell lennie a tizedesponttól balra, legfeljebb öt tizedesjegy megengedett.

Íme néhány példa *, amelyek azt mutatják, hogyan fogja 123456* különböző alkalmazásazonosítók (félkövér betűkkel):

- **`3100`**`123456`&rarr; 123456 (egész)
- **`3101`**`123456`&rarr; 12345.6 (egy tizedesjegy)
- **`3102`**`123456`&rarr; 1234,56 (két tizedesjegy)
- **`3103`**`123456`&rarr; 123.456 (három tizedesjegy)
- **`3104`**`123456`&rarr; 12.3456 (négy tizedesjegy)
- **`3105`**`123456`&rarr; 1.23456 (öt tizedesjegy)

## <a name="scanning-gs1-bar-codes-in-supply-chain-management"></a>GS1 vonalkódok beolvasása az ellátásilánc-kezelésben

A GS1 vonalkódok beolvasása során a raktári dolgozók egy mobileszközre beépített vagy ahhoz csatlakoztatott leolvasót használhatnak. A leolvasó ezután billentyűzetes események sorozatában továbbítja a vonalkódot a Raktárkezelés mobilalkalmazásba. Ez a működési mód billentyű *vagy* billentyűparancs néven is *ismert*. A mobileszköz ezt követően a kapott szöveget továbbítja az Ellátásilánc-kezelésnek. Amikor a rendszer bemeneti adatokat fogad, először meghatározza, hogy az adatok valamelyik olyan konfigurált előtaggal kezdődik-e, amely azt jelzi, hogy az adat ténylegesen GS1 vonalkód ([lásd a Globális GS1](#set-gs1-options) beállítások szakaszt). Ha a beolvasott adatok valamelyik előtaggal kezdődnek, akkor a rendszer egy GS1 elemzőt használ az adatok elemzőjeként, és az alkalmazásazonosítók alapján kinyeri az egyes adatelemeket. Az adatok elemeztét követően vagy az aktuális beviteli mező, vagy több mező ki lesz töltve a beolvasott adatokkal.

### <a name="configuration-of-bar-code-scanner-hardware-and-software"></a>Vonalkódolvasó hardverének és szoftverének konfigurálása

Ahhoz, hogy az ellátásilánc-kezelés helyesen felismerje és dekódolja a GS1 vonalkódokat, a hardverolvasót vagy a támogató szoftvert a következő műveletek elvégzésére kell konfigurálni:

- Előtag hozzáadása a beolvasott vonalkódhoz, hogy a rendszer felismerje a GS1 vonalkódot.
- A nem nyomtatható ASCII-csoportelválasztó karakter (ASCII-kód, 29-es vagy 1D-s hexadecimális kód) átalakítása nyomtatható karakterre, például tizedre (~).

Bár a beolvasott vonalkódhoz bármilyen előtag hozzáadható, az egyik lehetőség egy ISO/IEC 15424-es szimbólumazonosító, *más néven UM azonosító hozzáadása*. Ez a három karakterből `]` áll, és egy karakterből áll, amely azonosítja az alkalmazott szimbólumot, majd egy számot tartalmaz, amely további módosítóként használható. Például a 128-as kódhoz ad `]C1` meg 128-as vonalkódot (`C` a karakter miatt), `1` a módosító pedig azt, hogy az adatok első pozíciójában egy FNC1 karakter található. A 128-as kód azonban olyan vonalkód, `]C0` amely az adatok első karaktereként bármilyen egyéb karaktert tartalmaz.

A következő öt szimbólumazonosító megfelel a GS1 vonalkódnak, amelyek alkalmazásazonosító elemeket tartalmaznak:

- `]C1`– 128-as`C` kód, FNC1 karakterrel az első pozícióban (`1` más néven GS1-128).
- `]e0`– GS1 DataBar.
- `]d2`– DataMatrix (`d`) ECC 200 és FNC1 után az első (`2`, más néven GS1 DataMatrix) pozícióban.
- `]Q3`– QR-kód (`Q`) 2. modell szimbóluma, az FNC1 az első pozícióban (`3` más néven GS1 QR-kód).
- `]J1`– GS1 DotCode.

Ha ezeket az azonosítókat használja, akkor a nem GS1 vonalkódokkal való kompatibilitáshoz konfigurálni kell a leolvasókat vagy a beolvasási szoftvereket úgy, hogy eltávolítsák azokat az azonosítókat, amelyek nem felelnek meg a GS1 azonosítóknak. Ha például beolvas egy "normál" 39-es kódkódot, `]A0` akkor a program hozzáadja az előtagot. Mivel a rendszer ezt az előtagot nem fogja érteni a GS1 előtagok egyikeként, adatokat fog értelmezni, és váratlan eredményeket hoz létre.

> [!NOTE]
> A kényelmet szolgálja, 2.0.17.0 a raktárkezelés mobilalkalmazás verziószáma és későbbi része eltávolítja az előző listában nem szereplő ESETLEGESFIX előtagokat. Ez a viselkedés olyan eseteket támogat, ahol be lehet állítani, hogy a leolvasó hozzáadja az OMSZ előtagot, de ne távolítsa el a nem kívánt előtagokat.

### <a name="single-and-multiple-field-scanning"></a>Egy és több mező beolvasása

Miután az adatokat a vonalkód alapján elemezte, át lesz ásva a mobileszköz folyamatvezérlőibe. A feldolgozásra két módszer van:

- **Egymezős beolvasás** – ez a módszer csak azt a mezőt tölti ki, amelybe a vonalkód beolvasva lett. Ha például akkor olvassa `<FNC1>`**`01`**`09521101530001`**`17`**`210119`**`10`**`AB-123`**be** a vonalkódot, amikor a kurzor a Cikk mezőben található, akkor ebbe a mezőbe a vonalkód GTIN-kódja `09521101530001` lesz megadva. Ha ugyanannak a vonalkódnak a beolvasása közben **a** kurzor a Kötegazonosító mezőben található, `AB-123` akkor a program beírta a vonalkód kötegszámát. Ez a mód minden folyamat minden mezőjére működik, és csak a GS1 általános beállítását kell konfigurálni. Ha egy vonalkód több elemet tartalmaz, akkor is többször kell beolvasni, mivel egyszerre csak egy vonalkód-elem kerül be a mobileszköz-folyamatba. Ezt a viselkedést a GS1 általános beállítások vezérlik, [az általános GS1 beállítási szakaszban leírtaknak megfelelő módon](#generic-gs1-setup).
- **Több mező beolvasása** – ez a módszer az egyik vonalkód leolvasása esetén több mezőt is kitölt, további adatokkal a mobileszköz folyamatának állapotában. A házirend például úgy van beállítva, hogy a 01-es `ItemId` alkalmazásazonosítót a vezérlőbe és a 10-es `InventBatchId` alkalmazásazonosítót a mezőbe nyomja. Ebben az esetben a vonalkód beolvasása esetén `<FNC1>`**`01`**`09521101530001`**`17`**`210119`**`10`**`AB-123` mindkét változó adatai ugyanakkor lesznek eltolva. A rendszer tehát nem kéri a cikk és/vagy a köteg számát a folyamat során. Ezt a viselkedést a menüelemekhez kapcsolódó GS1-irányelvek vezérlik, [amint azt a GS1](#policies-for-menus) irányelveinek beállítása mobileszköz menüelemekre szakasz ismerteti.

> [!WARNING]
> A GS1 alapértelmezett irányelveinek tesztelése nem várt viselkedés nélküli működést történt. A menüelemekhez kapcsolt GS1-irányelvek testreszabása azonban nem várt viselkedést okozhat, mivel előfordulhat, hogy a folyamat bizonyos adatok adott időpontban nem lesz elérhető.

## <a name="turn-on-the-gs1-feature"></a>Az GS1 funkció bekapcsolása

Ahhoz, hogy használhassa a funkciót, először aktiválnia kell a rendszerében. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Raktárkezelés*
- **Funkció neve:** *GS1 vonalkódok beolvasása*

### <a name="turn-on-the-enhanced-parser-for-gs1-barcodes-feature"></a>A GS1 vonalkódok továbbfejlesztett elemző funkciója

GS1 vonalkódok használata esetén javasoljuk, *hogy a GS1 vonalkódok továbbfejlesztett elemző funkcióját is* engedélyezze. Ez a funkció a GS1 vonalkód-elemző jobb implementációját biztosítja. Hozzáadja a következő fejlesztéseket:

- A GS1 Általános specifikáció algoritmusát követi, amely a szimbólumadatok elemzési adatait tartalmazza, és ellenőrzi, hogy a szimbólum adatai a specifikációnak megfelelően érvényesek-e.
- Ehhez nem szükséges az azonosítóértékek maximális hosszát beállítani, és a **konfigurált** alkalmazásazonosítókból származó leghosszabb előtag-egyezést kell használni.
- Az n betű segítségével könnyebben konfigurálhatja a tizedes *alkalmazás azonosítóit, hogy az esetleges* számok megegyeznek. Külön alkalmazásazonosító (3101 *, 3102*, *3103* stb.) helyett csak egy alkalmazásazonosítót (*310n*)*is be lehet* állítani.
- Kijavít egy problémát, ahol a hibásan kódolt adatokat mezőadatokként értelmezi a rendszer.
- Külön osztályként jön létre, amely más környezetben újra felhasználható, és lehetővé teszi, hogy a beolvasott adatokat módosítani lehessen a folyamatmezők kitöltése előtt.

## <a name="set-up-global-gs1-options"></a><a name="set-gs1-options"></a>Globális GS1 opciók beállítása

A **Raktárkezelési paraméterek** oldal néhány olyan beállítást tartalmaz, amelyek globális GS1 opciókat határoznak meg.

A globális GS1 opciók beállításához kövesse az alábbi lépéseket.

1. Lépjen a **Raktárkezelés \> Beállítás \> Raktárkezelési paraméterek** részre.
1. A **Vonalkódok** gyorslapon állítsa be a következő mezőket:

    - **FNC1 Karakter**, **Datamatrix** karakter és **QR-kód** karakter – adja meg azokat a karaktereket, amelyeket az egyes GS1 vonalkódtípusokkal kapcsolatban előtagként kell értelmezni.
    - **Csoportelválasztó** – adja meg azt a karaktert, amely az ASCII-csoport elválasztó karakterét helyettesíti.
    - **Az azonosító maximális hossza** - Adja meg az alkalmazás azonosítójának megengedett maximális karakterszámát. Ez a mező nem kötelező, ha *a rendszerben be van kapcsolva az Enhanced GS1 Parser* funkció.

> [!NOTE]
> Az előtagok megszakódolják a rendszert, hogy a vonalkód kódolása a GS1 szabvány szerint történt. Egyidejűleg és különböző célokra legfeljebb három előtag **(FNC1 karakter**, **adatmátrix karakter** és **QR-kód karakter**) használható.

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

    - **Alkalmazás azonosítója** - Adja meg az alkalmazás azonosítójának azonosító kódját. Ez a kód általában kétjegyű egész szám, de lehet hosszabb is. Tizedes értékek esetén az utolsó számjegy a tizedesjegyek számát jelzi. További információért lásd a lista későbbi részében a **Tizedesjegyek** jelölőnégyzet leírását. *Ha engedélyezve van a* GS1 *vonalkódok továbbfejlesztett elemzője funkció, egyetlen alkalmazásazonosítót hozhat létre az összes tizedesjegyváltozathoz az n* betűvel az alkalmazásazonosító utolsó karaktereként. Beállíthatja például, hogy csak egy alkalmazásazonosítót (*310n*) állítson be a tizedesjegyek száma helyett (*3101*, *3102*, *3103* stb.).
    - **Leírás** - Adja meg az azonosító rövid leírását.
    - **Rögzített hosszúság** - Jelölje be ezt a jelölőnégyzetet, ha az alkalmazás azonosítójával beolvasott értékek rögzített karakterszámúak. Törölje ezt a jelölőnégyzetet, ha az értékek hossza változó. Ebben az esetben az érték végét a **raktárkezelési paraméterek** lapon megadott csoportelválasztó karakterrel kell jeleznie.
    - **Hosszúság** - Adja meg az alkalmazásazonosító használatával beolvasott értékekben megjelenő karakterek maximális számát. Ha a **Rögzített hosszúság** jelölőnégyzet be van jelölve, akkor pontosan ennyi karaktert várunk el.
    - **Típus** - Válassza ki az alkalmazásazonosító használatával beolvasott érték típusát *(numerikus*, *alfanumerikus* vagy *dátum*). A dátumok és [számok vonalkódadatokban való ábrázolása mikéntjeggyel kapcsolatban a Dátumok és tizedesjegyek szakaszban található további](#dates-and-decimal-numbers) tájékoztatás.
    - **Decimális** - Jelölje be ezt a jelölőnégyzetet, ha az érték tartalmaz egy tizedesvesszőt. Ha ez a négyzet be van jelölve, a rendszer az alkalmazás azonosítójának utolsó számjegyét használja a tizedesjegyek számának meghatározásához. A dátumok és [számok vonalkódadatokban való ábrázolása mikéntjeggyel kapcsolatban a Dátumok és tizedesjegyek szakaszban található további](#dates-and-decimal-numbers) tájékoztatás.

> [!WARNING]
> **Bár** a rendszer lehetővé teszi, hogy beállítsa minden alkalmazásazonosító Rögzített hossz jelölőnégyzetét, csak az alkalmazásazonosítóknak csak az a részhalmazához használható, amelyek előre megadott hosszúságúak a GS1 általános specifikációk szerint. A továbbfejlesztett GS1 elemző már tartalmazza az előre megadott hosszúságú alkalmazásazonosítók listáját.

> [!NOTE]
> A **Raktárkezelési** **paraméterek** lapon megadott Csoportelválasztó értéke nem kötelező, ha rögzített hosszúságú egy alkalmazásazonosítót követő érték.

## <a name="establish-the-generic-gs1-setup"></a><a name="generic-gs1-setup"></a>Az általános GS1 beállítás létrehozása

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

## <a name="set-up-gs1-policies-to-be-to-mobile-device-menu-items"></a><a name="policies-for-menus"></a> GS1-irányelvek beállítása mobileszközök menüpontokként

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

> [!WARNING]
> Előfordulhat, hogy a GS1 egyes irányelvei nem működnek minden használt mobileszközön. Az egyéni GS1 irányelvek konfigurálásakor a mobileszköz áramlását különböző információk felhasználásával kell tesztelni, amelyek a folyamat különböző pontjain leolvasva vannak, ily módon meghatározhatja, hogy a folyamat a várt módon megfelelő lesz-e.

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
1. Jelölje ki **a Cikk** mezőt, és olvassa be a következő vonalkódot: `]C10100000012345678~3030~10b1~17220215`

A példában megadott beállítások miatt a rendszer a következőképpen elemzi a beolvasott vonalkódot.

| Mezőkulcs | Pályázat azonosítója | Érték | Bankjegy |
|---|---|---|---|
| ItemId | 01 | 00000012345678 | Mivel a dolgozó a **Tétel** mezőt szkennelte be, a vonalkód első értéke kerül hozzárendelésre ehhez a mezőhöz. A leképezés a GS1 általános beállításából származik. |
| Mennyiség | 30 | 30 | Mivel egyetlen beolvasás során több mezőérték kerül rögzítésre, ez a hozzárendelés és az összes többi hozzárendelés a **beszerzés fogadás** menüponthoz rendelt GS1 házirendből származik. Ez az érték a beérkezett mennyiség. |
| InventBatchId | 10 | b1 | Ez az érték a tétel azonosítója. |
| ExpDate | 17 | 220215 | A dátumformátum YYMMDD. Ezért a lejárat időpontja 2022. február 15. |

Ezután a bizonylat regisztrálásra kerül, és az egyszeri beolvasás után a megfelelő adatbázis-értékek bevitelére kerül sor.
