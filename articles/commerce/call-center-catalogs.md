---
title: Hívásközpont-katalógusok
description: Ez a témakör a Dynamics 365 Commerce-katalógusok hívásközpont-specifikus funkcióit ismerteti.
author: josaw1
manager: AnnBe
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, RetailCatalogDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 9abe493746719d2e229ef09c2eb5f436b91b2171
ms.sourcegitcommit: 4c6d31f3ebd88212d3d1497a4bba9c64c5300444
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/24/2020
ms.locfileid: "4413009"
---
# <a name="call-center-catalogs"></a>Hívásközpont-katalógusok

[!include [banner](includes/banner.md)]

Ez a témakör a Dynamics 365 Commerce-katalógusok hívásközpont-specifikus funkcióit ismerteti.

A Commerce katalógusfunkciói több célra is használhatók. Kezdetben a katalógusfunkciók a harmadik félhez tartozó elektronikus kereskedelmi integrációk támogatásához jöttek létre. A katalógusbeállítások lehetővé tették a vállalatok számára a termékek és attribútumok csoportosítását, amelyeket egy harmadik félhez tartozó elektronikus kereskedelmi megoldás segítségével közzé lehetett tenni külső felhasználás céljából.

Amikor a hívásközpont csatornatámogatás része lett a rendszernek, a katalóguskoncepció tovább bővült: további lehetőségeket lehet hozzáadni a támogatási és vezérlési funkciókhoz, amelyek a hagyományos, "közvetlenül a fogyasztónak" marketingkatalógusokhoz kapcsolódnak. A "közvetlenül a fogyasztónak" típusú vállalatok gyakran készítenek nyomtatott katalógusokat, amelyeket aztán postán elküldenek a vevők egy vagy több szegmensének. Ezek a katalógusok általában meghatározott promóciókat és ajánlatokat tartalmaznak, amelyekkel a vevők csak akkor élhetnek, amennyiben megadnak egy katalógus-azonosító kódot a rendelés létrehozásakor.

A "közvetlenül a fogyasztónak" marketingvállalatok szorosan követik a vevők válaszait ezekre a katalógusokra, hogy meggyőződhessenek róla, hogy a katalógusok előállítási és postázási költségei megtérülnek. A válaszok nyomon követéséhez hagyományosan egy kód van a katalógus hátoldalára nyomtatva, és ezt a kódot kérik és alkalmazzák akkor, ha a katalógus címzettje telefonon ad le rendelést (illetve most már általában a kódot meg kell adnia a vevőnek, amikor online rendelést ad le). Habár az iparágban több szakkifejezést is használnak a katalóguskövető kód beazonosítására (beleértve a kulcskódot, promóciós kódot, katalóguskódot és forráskódot), mi a Commerce esetén **Forráskód-azonosítóként** hivatkozunk rá.

## <a name="basic-catalog-setup"></a>Alap katalógusbeállítás

Lépjen a **Kiskereskedelem és kereskedelem** \> **Katalógusok és szortimentek** \> **Minden katalógus** ponthoz a katalógus konfigurálásához.

Új katalógus létrehozásakor először a katalógust hozzá kell rendelnie egy vagy több csatornához. Ezt a **Kereskedelmi csatornák** gyorslapon teheti meg a **Katalógusbeállítások** űrlapon. Kattintson a **Hozzáadás** lehetőségre, és válasszon ki egy vagy több csatornát. Csak a kiválasztott csatorna [szortimenthez](https://docs.microsoft.com/dynamics365/unified-operations/retail/assortments) kapcsolt elemeket használhatja a katalógus létrehozásakor.

Ha termékeket szeretne hozzáadni a katalógushoz, ki kell választania a navigációs hierarchiát. A navigációs hierarchia célja a katalógus a kategóriaszerkezetének támogatása. Választania kell egyet a **Katalógus** oldal **Kereskedelmi csatornák** gyorslapon a kiválasztott csatornákhoz kapcsolt navigációs hierarchiák közül. Ha egy navigációs csatorna korábban nem volt hozzákapcsolva egy csatornához, lépjen a **Kiskereskedelem és kereskedelem** \> **Csatorna beállítása** \> **Csatornakategóriák és termékattribútumok** lehetőséghez, ahol hozzákapcsolhat egy alapértelmezett navigációs hierarchiát minden egyes csatornához.

Az **Katalógusok** menülap **Katalógusbeállítások** lapján kattintson a **Termék hozzáadása** lehetőségre a katalógushoz hozzáadandó termékek konfigurálásához, vagy jelöljön ki egy csomópontot a navigációs hierarchiában (a csomópont kijelölésével megváltozik a képernyőbemutató, és lehetővé teszi a termékek közvetlen hozzáadását egy kategóriához a katalóguson belül).

Kattintson a legfelső csomópontra a katalógus hierarchiában, ha vissza szeretne térni a fő katalógusfejléc nézethez. Ha szükséges, állítsa be az érvénybe lépési és lejárati dátumokat az **Általános** FastTabon.

A katalógust közzé kell tenni ahhoz, hogy használható legyen. Kattintson a **Katalógus érvényesítése** lehetőségre a **Katalógusok** menün az érvényesítés feldolgozásához. Ez szükséges művelet, és ezzel ellenőrizheti, hogy pontos-e a szükséges beállítás. Az érvényesítés részleteinek megtekintéséhez kattinson az **Eredmények megtekintése** lehetőségre. Ha hibákat talál, helyesbítse az adatokat, és futtassa újra az érvényesítést, mindaddig, amíg sikeres nem lesz a folyamat.

Az érvényesítés jóváhagyása után kattintson a **Munkafolyamat** lehetőségre a menün a jóváhagyási munkafolyamat indításához. Kattintson a **Küldés** elemre a **Munkafolyamat** menün a folyamat végrehajtásához. Adja meg a lépéseket és az engedélyezett felhasználókat a munkafolyamathoz a **Kiskereskedelem és kereskedelem** \> **Központ beállítása** \> **Kereskedelmi munkafolyamatok** pontban. A munkafolyamat meghatározza a lépéseket, amelyek ahhoz szükségesek, hogy a katalógus **Jóváhagyva** állapotúvá váljon. Ha a katalógus **Jóváhagyva** állapotú, kattintson a **Közzététel** lehetőségre a **Katalógusok** menün a folyamat befejezéséhez. Miután a katalógus **Közzétett** állapotúvá válik, felhasználható a hívásközpont rendelésbeviteléhez és a katalógusfolyamatok küldéséhez.

## <a name="use-catalogs-to-drive-sales-order-pricing-and-promotions"></a>Katalógusok használata értékesítési rendelés árképzéséhez és promóciókhoz

A hívásközponthoz használt katalógus definiálásának fő oka, hogy meghatározott árakat és promóciókat állíthassunk be az adott katalógushoz. Azok a vevők, akik ebből a katalógusból rendelnek, ezekre az árakra és promóciókra jogosultak a hívásközpont rendelésbevitelénél, ha a katalógus **forráskód-azonosítóját** megadják a rendelés fejlécében vagy a rendeléssorokban.

Az adott katalógushoz kapcsolódó árak beállításához válassza az **Árcsoportok** lehetőséget a **Katalógusok** fülön, és kapcsoljon hozzá egy vagy több árcsoportot a katalógushoz. Az összes kereskedelmi megállapodás, ármódosítási napló és speciális kedvezmény (küszöbérték szerinti, mennyiségi és kombinációs kedvezmény), amely ugyanahhoz az árcsoporthoz kapcsolódik, alkalmazásra kerül, ha a vevők ebből a katalógusból rendelnek.

A **Forráskódok** FastTabon kattintson a **Hozzáadás** lehetőségre, és adjon hozzá egy vagy több **Forráskód-azonosítót** az adott a katalógushoz. Ez az a kód, amely az értékesítési rendelés fejlécében (és soraiban) alkalmazásra kerül a hívásközpont rendelésbevitele során. A kód segítségével kapcsolják össze az értékesítési rendelést a katalógussal, majd végül az árcsoportokkal és a korábban beállított speciális árakkal és promóciókkal.

## <a name="use-the-source-id-to-track-costs-and-response-rates"></a>A forrásazonosító használata a költségek és a válaszarány nyomon követésére

A **forráskód-azonosító** meghatározásakor tetszés szerint hozzárendelheti az azonosítót egy **célpiac-azonosítóhoz**. A **Célpiac-azonosítót** a **Kiskereskedelem és kereskedelem** \> **Vevők** \> **Célpiac** pontban határozhatja meg. A célpiac a felhasználó által meghatározott szegmenshez tartozó vevők és/vagy potenciális vevők listája. A vevő vagy a potenciális vevő adatainak hozzákapcsolása a forráskód-azonosítóhoz lehetővé teszi a katalógus címzettjeinek jobb átláthatóságát. Ha egy vevő hozzá van kapcsolva egy célpiachoz, a célpiac pedig hozzá van kapcsolva egy aktív forráskód-azonosítóhoz/katalógushoz, a hívásközpont felhasználói láthatják, hogy a vevő milyen katalógusokat kapott, ha kiválasztják a **Forráskódok** menüpontot az **Ügyfélszolgálat** oldalon található **Vevők** menülapon. A rendelésbevitel során a hívásközpont felhasználói a vevő számára küldött konkrét katalógusokat is láthatják a rendelésbevitel fejlécében található **Forrás** legördülő listában. Ha módosítják a szűrőt **Összesről** **Megcélzottra**, a felhasználók láthatják a vevő számára küldött aktív katalógusokat. Ez akkor hasznos, ha a vevő megfeledkezett a katalógusról, nem találja vagy nem tudja elolvasni a katalóguskódot, amikor betelefonál értékesítési rendelés leadása céljából.

Egy katalógushoz több forráskód-azonosítót is hozzá lehet kapcsolni. Ez gyakran szükséges, ha egy vállalat különböző szegmensek szerint szeretné nyomon követni a válaszarányt. A vállalat egyedi katalóguskódot rendel hozzá a különböző vevőszegmensekhez, amely lehetővé teszi, hogy a válaszarányt nyomon kövessék egészen a szegmens szintjéig egy adott katalóguseseményen belül.

Ha kiválaszt egy adott **Forráskód-azonosító** rekordot, majd a **Részletek** lehetőségre kattint a **Forráskódok** FastTabon, további mezőkhöz férhet hozzá, ahol értékesítési előrejelzéseket, levelezési költségeket és levelezési dátumokat rögzíthet. Ezek az adatok abban az esetben hasznosak, ha a katalógus hatékonyságára vonatkozó részletes elemzést végez. A felhasználók idővel visszatérhetnek erre az oldalra, és a **Forráskód-elemzés** és **Promóciók összehasonlítása** gombok segítségével az aktuális értékesítési adatokon alapuló elemzési jelentéseket hozhatnak létre, és összehasonlíthatják a költségeket és költségvetéseket a tényleges adatokkal.

## <a name="configure-catalog-specific-order-and-item-scripts"></a>Katalógusspecifikus rendelési és cikkforgatókönyvek konfigurálása

A hívásközpont felhasználója értékesítési rendelés létrehozásakor használhatja a képernyőn megjelenő forgatókönyveket. Ezek a szöveges forgatókönyvek további információkat tartalmazhatnak, amelyeket a felhasználónak közölnie kell a vevővel, vagy lehetnek belső megjegyzések/emlékeztetők, amelyeket a hívásközpont felhasználójának át kell tekintenie és amelyekre reagálnia kell az értékesítési rendelés létrehozásakor.

Gyakran célszerű különböző forgatókönyvcsoportokat alkalmazni a különböző katalógusokhoz. A **Forgatókönyvek** FastTabon előre definiált forgatókönyveket kapcsolhat az adott katalógushoz. Az **Időzítés** mezőben határozható meg, hogy a parancsfájl a rendelés elején (amint a rendelés fejlécében megadják a forráskód-azonosítót), vagy a rendelés végén (az értékesítési rendelést összegző űrlapon) jelenjen-e meg.

Ha kiválasztanak egy csomópontot a katalógus hierarchiájában és a **Termékek** FastTabon található adatokkal dolgoznak, a felhasználók katalógus- vagy cikkspecifikus forgatókönyveket is hozzákapcsolhatnak a **Forgatókönyvek** művelettel.

## <a name="configure-catalog-specific-up-sell-and-cross-sell-items"></a>Katalógusspecifikus értéknövelő/párhuzamosan értékesített cikkek konfigurálása

A termékek beállításaiból értéknövelő/párhuzamosan értékesített javaslatokat csatolhat egy cikkhez, de bizonyos esetekben előfordulhat, hogy a vállalat speciális értéknövelő/párhuzamosan értékesített cikkeket akar promótálni azoknak a vevőknek, akik egy adott terméket rendelnek meg egy adott katalógusból. A **Termékek** FastTabon jelöljön ki egy cikket, és kattintson az **Értéknövelő/párhuzamosan értékesített cikkek** elemre a termékek értéknövelt vagy párhuzamosan értékesítettként történő beállításához azon felhasználók számára, akik a kijelölt cikket vásárolják meg a katalógusból. A hívásközponti rendelésbevitel során a hagyományos termékkonfiguráció során a cikkhez beállított szokásos értéknövelő/párhuzamos értékesített termékek helyett a katalógusspecifikus értéknövelő/párhuzamos értékesített cikkek jelennek meg a képernyőn.

Az értéknövelő/párhuzamosan értékesített cikkek esetén kihasználhatjuk a forgatókönyv funkció előnyeit is, azaz konkrét üzeneteket jeleníthetünk meg a felhasználónak, amikor az értéknövelő/párhuzamosan értékesített cikkek megjelennek a rendelésbevitel során. A kifejezetten egy katalógustermékhez konfigurált értéknövelő/párhuzamosan értékesített termékekhez kötődő forgatókönyvek csak akkor jelennek meg, ha a hívásközponti rendelésbevitelnél alkalmazzák az adott katalógus forráskódját.

## <a name="catalog-page-analysis"></a>Katalógusoldal-elemzés

A **Katalógusok** lapon lehetősége van **Katalógusoldalak** konfigurálására. Ez a funkció lehetővé teszi, hogy meghatározzon bizonyos lapokat és laptípusokat a nyomtatott katalógus és a kapcsolódó költségek számára.

A katalógusban szereplő termékek konfigurálásakor használja a **Termékoldal elrendezése** műveletet a cikkre vonatkozó konkrét lapok, lapon elfoglalt terület (százalékban) és a lapon szereplő adatok elhelyezésének meghatározásához. Ezeknek az adatoknak a beállítása segítségével a felhasználók kihasználja a **Katalógusterület-elemzési jelentés** előnyeit. A jelentés megtekintéséhez lépjen a **Kiskereskedelem és kereskedelem** \> **Hívásközponti jelentések** \> **Katalógusterület-elemzés** jelentéshez. Ez a jelentés elemzi a katalógus szerinti értékesítéseket (azokat az értékesítési rendeléseket, ahol a katalógus forrásazonosítója össze volt kötve a rendelés fejlécével vagy sorával) és a kapcsolódó lapszázalékot és költségeket egy hagyományos közvetlen marketing **Négyzethüvelyk-elemzés** jelentés biztosításához.

## <a name="catalog-requests"></a>Katalóguskérések

Miután konfigurálta és közzétette a katalógusokat a Commerce rendszerben, használhatja a **Katalógus küldése** funkciót. Ez a funkció a **Vevőkeresés** és az **Ügyfélszolgálat** lapokon érhető el. Miután a **Vevőkeresés** pontban kiválasztotta a vevőrekordot, vagy a kiválasztott vevőkhöz tartozó számla megtekintésekor az **Ügyfélszolgálat** résznél, a felhasználó rákattinthat a **Katalógus küldése** lehetőségre, és ekkor megnyílik egy párbeszédpanel, amelyen a felhasználó választhat egy minden közzétett és aktív katalógust tartalmazó listáról. A felhasználó kiválaszthatja a katalógust és a mennyiséget, és az elküldendő forráskód-azonosítót. Ha rákattintanak a **Küldés** gombra, a rendszer eltárolja a kérelmet, amelyet ezután a **Katalóguskérelem** jelentést kinyomtatva lehet kezelni. A jelentés megtekintéséhez lépjen a **Kiskereskedelem és kereskedelem** \> **Hívásközponti jelentések** \> **Katalóguskérések – jelentés** jelentéshez. Itt megtekintheti a listát az összes katalóguskérésről, illetve annak a vevőnek a nevét és címadatait, aki kérte a katalógust. Ezt a jelentést felhasználhatja belső célokra,vagy az adatokat továbbíthatja egy harmadik félnek, amely a katalógus vevőhöz való fizikai eljuttatásának külső folyamatait támogatja.

## <a name="additional-features"></a>További szolgáltatások

A **Katalógusok** lapon lehetősége van a **Fizetési ütemezés** és az **Ingyenes termékek** konfigurálására. Ha a hívásközponti rendelésbevitele során alkalmazzák a katalógushoz kapcsolt forráskód-azonosítót, a vevő jogosult lesz az ingyenes termékekre vagy az adott katalógushoz tartozó, megadott fizetési ütemezés felhasználására. Ha szükség van arra, hogy a vevőt korlátozzuk rá, hogy a rendszerben szereplő összes aktív fizetési ütemezés helyett csak a katalógusához kapcsolt fizetési ütemezések közül választhasson, a **Csak katalóguskonstrukciók engedélyezése** jelölőnégyzetet be kell jelölni egy vagy több meghatározott forráskód-azonosító esetén a korlátozás érvényesítéséhez.

## <a name="additional-notes"></a>További megjegyzések

Jelenleg ha egy forráskód-azonosítót alkalmaznak egy értékesítési rendelésre a hívásközpontban, arra használják, hogy katalógusspecifikus árak, promóciók, forgatókönyvek és értéknövelő/párhuzamosan értékesített cikkek hajtóereje legyen. A rendszer nem tiltja és nem akadályozza meg a katalógusban nem szereplő termékek értékesítési rendelés során történő rendelését. Ha egy katalógusban nem szereplő cikket rendelnek, a rendszer először a hívásközponti csatornában meghatározott **Árcsoportot** használja (**Kiskereskedelem és kereskedelem** \> **Csatornák** \> **Hívásközpontok** \> **Összes hívásközpont**) a cikk árához vagy a promóciókhoz. Ha nem talál konkrét árat a csatornában, a termék alap eladási árát használja.


[!INCLUDE[footer-include](../includes/footer-banner.md)]