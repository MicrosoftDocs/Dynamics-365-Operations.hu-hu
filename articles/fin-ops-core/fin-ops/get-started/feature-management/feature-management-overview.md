---
title: Funkciókezelés áttekintése
description: Ez a témakör bemutatja a funkciókezelés szolgáltatást, valamint azt, hogy hogyan használhatja azt.
author: Peakerbl
ms.date: 07/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: IT Pro, Application user
ms.reviewer: sericks
ms.custom: intro-internal
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: 9b51e848a965589ef0a14e5b880f213d18abc53097c18eed51320d7443a3b5f0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741608"
---
# <a name="feature-management-overview"></a>Funkciókezelés áttekintése

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../../includes/preview-banner.md)]

Minden kiadásban új szolgáltatások és frissítések jelennek meg. A funkció-kezelési élmény olyan munkaterületet tartalmaz, amelyen megtekintheti az egyes kiadásokban elérhetővé tett szolgáltatások listáját. Ezután a munkaterületet használhatja a funkciók dokumentációjának megtekintésére, valamint a funkciók engedélyezésére vagy letiltására.

## <a name="the-feature-management-workspace"></a>A Funkciókezelés munkaterület használata.

A **Funkciókezelés** munkaterületet úgy nyithatja meg, hogy kijelöli az irányítópult megfelelő csempéjét. Megjelenik egy lap, amelyen megtekintheti az összes funkciót az összes kiadáshoz, amelyeket támogat a Funkciókezelés élmény. 

A funkciólista a következő információkat tartalmazza:

- **Funkció neve** – A hozzáadott funkció leírása.
- **Állapot** - Egy szimbólum jelzi, hogy egy funkció be van-e kapcsolva (pipa), ki van-e kapcsolva (üres), be van-e ütemezve (óra), kötelező-e (lakat), bekapcsolás előtt figyelmet igényel-e (figyelmeztető szimbólum), vagy nem kapcsolható be (X). A látható beállítást minden jogi személyhez használja a rendszer. Ne felejtse el, hogy ha a funkció be is van kapcsolva, a biztonság szabályozza azt. Ezért a funkció csak azon felhasználók számára lesz elérhető, akiknek biztonsági szerepkörük alapján hozzáférésük van hozzá. Csak olyan jogi személyekben érhető el, amelyekhez a felhasználó hozzáfér.
- **Engedélyezési dátum** – Az a dátum, amikor a funkciót bekapcsolták, vagy ütemezve van a bekapcsolásra.
- **Funkció hozzáadása** – Az a dátum, amikor a funkciót hozzáadták a környezethez. A program automatikusan beírja ezt a dátumot, amikor a havi kiadási ciklus során frissíti a környezetet.
- **A funkció állapota** - A funkció aktuális életciklus állapota: **Előnézet**, **Felszabadítva** (üresen jelenik meg), **Alapértelmezés szerint bekapcsolva**, és **Kötelező**. Az állapotokkal később részletesebben foglalkozunk ebben a témakörben. 
- **Modul** – Az új funkció által érintett modul.

> [!NOTE]
> A **Funkcióállapot** oszlop a 10.0.21-es verziótól szerepel.

Ha kiválaszt egy funkciót, akkor a részleteket ablaktáblában, a szolgáltatások listájának jobb oldalán megjelennek a további információk. A ablaktábla tetején látható a funkció neve, a funkció hozzáadásának dátuma, a funkció által érintett modul, valamint egy **További információk** hivatkozás. Erre a hivatkozásra kattintva megtekintheti a funkció dokumentációját. Ha a dokumentáció nem érhető el, akkor egy ideiglenes oldalra kerül. A részleteket tartalmazó ablaktábla tartalmaz egy **Megjegyzések** mezőt is, amelybe felveheti a saját megjegyzéseit a funkcióval kapcsolatosan.

A **Funkciókezelés** munkaterület több lapot is tartalmaz, amelyek mindegyikén a funkciók listája látható.

- **Új** – Ez a lap a legutóbbi havi frissítés óta hozzáadott összes funkciót jeleníti meg. Ha kihagyott egy havi frissítést, akkor a lap megjeleníti a legutóbbi frissítés óta hozzáadott összes új funkciót. A legújabb funkciók a lista tetején jelennek meg. Az új funkciók száma összesen a lap felső részén található csempén jelenik meg.
- **Nincs engedélyezve** - Ez a lap mutatja az összes olyan funkciót, amely nincs bekapcsolva. A legújabb funkciók a lista tetején jelennek meg. Ezenkívül az oldal tetején egy csempe mutatja a jelenleg kikapcsolt új funkciók számát.
- **Ütemezve** – Ezen a lapon látható az összes olyan funkció, amelynek bekapcsolását egy jövőbeli dátumra ütemeztek. A legkorábbi dátumra ütemezett szolgáltatások jelennek meg a lista tetején. Ezenkívül az oldal tetején egy csempe mutatja az ütemezett funkciók teljes számát.
- **Összes** – Ezen a lapon látható az összes funkció. A legújabb funkciók a lista tetején jelennek meg.

## <a name="feature-states"></a>Funkcióállapotok
A funkciók több állapot között is átmehetnek, a funkciókezelésben történő bevezetéstől amíg végül kötelezővé válnak a termékben. Ez a szakasz az érvényes funkcióállapotokat ismerteti.

### <a name="preview-features-optional"></a>Előzetes funkciók (opcionális)

A termékfejlesztő csapatok dönthetnek úgy, hogy egy új funkciót kezdetben előzetes funkcióként indítanak el. Az előzetes funkciók alapértelmezés szerint nincsenek engedélyezve, és opcionálisak. A tulajdonos termékfejlesztő csapat a funkciókat a sikeres előnézeti időszakot követően frissíti kiadottra.

> [!NOTE]
> Az előnézeti funkciók egyedi előnézeti [feltételek](https://go.microsoft.com/fwlink/?linkid=2105274) hatálya alá tartoznak. 

### <a name="released-features-optional"></a>Kiadott funkciók (opcionális)

Ezeknek a jellemzőknek a **Funkcióállapot** oszlopa üres. A kezdetben kiadásra kerülő funkciók alapértelmezés szerint nincsenek bekapcsolva, és engedélyezésük opcionális. Az előnézetből frissített funkciók megtartják engedélyezési státuszukat.

### <a name="on-by-default-features-optional"></a>Alapértelmezés szerint bekapcsolt funkciók (opcionális)

Az **Alapértelmezés szerint bekapcsolt** állapotra frissített funkciók alapértelmezés szerint be vannak kapcsolva, de letilthatók. Miután a letiltható funkciók legalább hat hónapig **Kiadott** állapotban voltak, a következő nagy kiadásban várhatóan átkerülnek ebbe az állapotba. Az **Alapértelmezés szerint bekapcsolt** állapotba átváltott funkciók várhatóan a kiadáshoz tartozó [Újdonságok](../whats-new-changed.md) témakörben lesznek közölve. A frissítést a tulajdonos termékcsapat kezdeményezi.

> [!NOTE]
> Mivel ezek a funkciók automatikusan lesznek engedélyezve, fontos annak meghatározása, hogy a szervezete készen áll-e a funkciók átvételére, vagy több időre van szükség. Ha több időre van szükség, szükség lehet ezen funkciók ideiglenes letiltására. Vegye figyelembe, hogy egy funkció **Alapértelmezés szerint bekapcsolt** állapotba történő átváltása általában a funkció **Kötelező**-vé tétele előtt a fő verzióban történik. Ekkor már nem lesz lehetősége a funkció letiltására. 

### <a name="released-features-mandatory"></a>Kiadott funkciók (kötelező)

A **Kiadott** a funkciók végső állapota. Azt jelzi, hogy a funkciók be vannak kapcsolva, és nem lehet letiltani őket a Microsoft értesítése nélkül. A választható funkciók várhatóan két nagyobb kiadás után válnak kötelezővé. A kritikus funkciók kivételes jelleggel kötelezően bevezethetők.

## <a name="example-of-expected-feature-lifecycles"></a>Példa a funkciók várható életciklusára

A letiltható funkciók, amelyek az áprilisi kiadás előtt vagy annak részeként kerültek kiadott és opcionális funkcióként hozzáadásra, várhatóan a következő októberi kiadásban **Alapértelmezés szerint bekapcsolt** állapotba kerülnek. A következő év áprilisában várhatóan **Kötelező**-vé válnak.

Azok a funkciók, amelyeket nem lehet letiltani, és amelyeket az áprilisi kiadás előtt vagy annak részeként adtak hozzá kiadott és opcionális funkcióként, várhatóan a következő év áprilisában válnak **Kötelező**-vé.

## <a name="enable-a-feature"></a>Egy funkció engedélyezése

Ha egy funkció nincs bekapcsolva, a részleteket tartalmazó ablaktáblán megjelenik az **Engedélyezés most** gomb. Ezt a gombot használhatja a funkció engedélyezéséhez.

Néhány funkció nem tiltható le, miután engedélyezte azokat. Ha a funkció, amelyet be akar kapcsolni, nem engedélyezhető, figyelmeztetést kap. Ekkor választhatja a **Mégse** lehetőséget a művelet törléséhez és a funkció kikapcsolva hagyásához. Ha azonban a funkció engedélyezéséhez az **Engedélyezés** lehetőséget választja, később már nem tudja letiltani.

Egyes funkciók engedélyezése előtt további információkat tartalmazó üzenet jelenik meg. Ezeket a funkciókat sárga figyelmeztető jel jelöli. Figyelmesen olvassa el a kiegészítő információkat, hogy megértse, mi történik, ha a funkciót engedélyezi. A funkció engedélyezéséhez azonban továbbra is választhatja az **Engedélyezés** lehetőséget.

Bizonyos funkciók esetében üzenet jelenik meg, hogy a funkció engedélyezéséhez valamilyen műveletet kell végrehajtani. Ezeket a funkciókat piros X jel jelöli. A funkció engedélyezéséhez el kell végezni a leírásban említett műveleteket. Ha egy funkció például nem használható egy konfigurációs kulcs letiltása nélkül, akkor először le kell tiltani a kulcsot, és utána kell engedélyezni a funkciót a Funkció kezelése részen.

Miután egy funkciót engedélyeztek, a részleteket tartalmazó ablaktáblában a **További információk** link alatt megjelenik egy üzenet. Ez az üzenet vagy azt közli, hogy a funkciót engedélyezték, vagy azt a jövőbeli dátumot jelzi, amikor a funkciót ütemezés szerint engedélyezni fogják. Mindig akkor jelenik meg, amikor kiválasztja a funkciót a szolgáltatások listájában.

Az ütemezett, jövőben engedélyezendő funkciók az **Ütemezett** lapon jelennek meg. A kötegelt folyamat a megadott napon éjfélkor fogja engedélyezni őket a rendszer dátuma szerinti időzóna alapján.

## <a name="reschedule-a-feature"></a>Funkció újraütemezése

Ha egy funkció a jövőre vonatkozóan van engedélyezésre ütemezve, az **Ütemezés** gomb látható a részletek ablaktáblán. Ezzel a gombbal módosíthatja az **Engedélyezés dátuma** értékét egy másik dátumra.

1. Válassza ki az ütemezett funkciót, amelyet át szeretne ütemezni, majd a részletek ablaktáblán válassza az **Ütemezés** lehetőséget.
2. A megjelenő párbeszédpanelen az **Engedélyezés dátuma** mezőben adja meg azt az új dátumot, amikor a funkciót engedélyezni kell.
3. Válassza az **Engedélyezés** lehetőséget a funkció újraütemezéséhez, vagy a **Letiltás** lehetőséget az ütemezés megszüntetéséhez.

## <a name="disable-a-feature"></a>Egy funkció letiltása

Ha egy funkció már engedélyezve van, a **Letiltás** gomb látható a részletek ablaktáblán. Ezt a gombot használhatja a funkció letiltásához. A **Letiltás** gomb nem érhető el, ha a funkciót nem lehet letiltani. 

Miután a funkció le van tiltva, a részletek ablaktáblán megjelenik egy üzenet a **További információ** hivatkozás alatt. Ez az üzenet azt jelzi, hogy a funkció nem engedélyezett. Mindig akkor jelenik meg, amikor kiválasztja a funkciót a szolgáltatások listájában. A funkciók, amelyek még nem lettek engedélyezve, a **Nem engedélyezett** lapon jelennek meg.

## <a name="features-that-must-be-enabled"></a>Funkciók, amelyeket engedélyezni kell.

Néha kritikus fontosságú funkció érkezik, amelyet automatikusan engedélyezni kell a frissítés során. Ezek a funkciók automatikusan engedélyezve lesznek az **Engedélyezés dátuma** mezőben megadott időpontban. Ezeknél a funkcióknál a részletek ablaktáblán megjelenik egy üzenet a **További információ** hivatkozása alatt. Ez az üzenet vagy azt jelzi, hogy a funkció engedélyezve van, vagy azt jelzi, hogy a funkció mikor lesz engedélyezve a jövőben. Mindig akkor jelenik meg, amikor kiválasztja a funkciót a szolgáltatások listájában.

## <a name="enable-all-features"></a>Az összes funkció engedélyezése

Az összes funkció **Az összes engedélyezése** gombbal engedélyezhető. 

Az **Összes engedélyezése** gombra kattintáskor megjelenik egy beállítás, ahol meg kell adni a következő adatokat:

- Az olyan funkciók listája, amelyeknek az engedélyezését jóvá kell hagyni. Ha engedélyezni szeretné a listában szereplő funkciókat, válassza az **Igen** lehetőséget a **Megerősítést igénylő funkciók engedélyezése** gombnál.
- Megjelenik az olyan funkciók listája, amelyek nem engedélyezhetők. Ezek nem engedélyezhető funkciók

Az összes olyan funkció, amely engedélyezhető, engedélyezve lesz. Ha egy funkció jövőbeli engedélyezésre ütemezett, az ütemezés nem módosul. 

## <a name="enable-all-features-automatically"></a>Az összes funkció automatikus engedélyezése

Ha automatikusan engedélyezni kívánja az összes új funkciót, akkor a munkaterület címe alatti legördülő lista segítségével módosíthatja, hogy mi történjen az új funkciók hozzáadásakor.

- Válassza az **Új funkciók automatikus engedélyezése** lehetőséget az összes új funkció automatikus engedélyezéséhez, amikor hozzáadják őket a környezetéhez.
- Válassza a **Ne engedélyezze automatikusan az új funkciókat** lehetőséget, ha az összes alkalmazható új funkciót alapértelmezés szerint ki kell kapcsolni, amikor a környezethez hozzáadják.

Ha minden funkciót automatikusan engedélyez, azzal engedélyezi az olyan funkciókat, amelyek engedélyezve lesznek **Az összes engedélyezése** gombra kattintáskor. Az olyan funkciók nem lesznek engedélyezve, amelyek engedélyezéséhez valamilyen jóváhagyásra vagy műveletre van szükség.

## <a name="check-for-updates"></a>Frissítések keresése

A rendszer az egyes frissítések után funkciókat ad a környezethez. A **Frissítések keresése** gombra kattintva manuálisan is kereshet frissítéseket. A frissítés után a rendszerhez hozzáadott funkciók bekerülnek a funkciók listájába. Ha például a kiadás után engedélyezve van egy tesztelt funkció, kereshet frissítéseket, és a funkció bekerül a listába.

## <a name="assigning-roles"></a>Szerepkörök hozzárendelése

A **Funkciókezelés** munkaterületet rendszeradminisztrátorok és a Funkciókezelő vagy Funkciómegtekintő szerepkörhöz rendelt felhasználók is megnyithatják. Ez a két szerepkör a Funkciókezelési gyakorlat támogatására jött létre. A szolgáltatáskezelő szerepkörben lévő felhasználók bármilyen funkciót be-és kikapcsolhatnak. Ezenkívül a funkcióhoz tartozó **Megjegyzések** mezőt is módosíthatják. A funkciómegtekintő szerepkör felhasználói csak megtekinthetik a **Funkciókezelés** munkaterületet. Nem kapcsolhatnak be és ki funkciókat.

A funkciókezelő szerepkör és a funkciómegtekintő szerepkör nem bírálja felül a felhasználó által megadott biztonságot. Ők csak azt szabályozzák, hogy a felhasználó ki- és bekapcsolhatja-e a funkciókat. Nem biztosítanak hozzáférést magukhoz a funkciókhoz.

## <a name="features-that-use-configuration-keys"></a>A konfigurációs kulcsokat használó funkciók

Ha egy funkció konfigurációs kulcsot használ, de a konfigurációs kulcs nincs bekapcsolva, akkor a **Funkciókezelés** munkaterület nem jeleníti meg a funkciót a választható funkciók listáján. Miután bekapcsolta a konfigurációs kulcsot, frissítenie kell a funkciók listáját a **Frissítések ellenőrzése** menüelem használatával. Ez a funkció aztán megjelenik a funkciók listájában.

Ha kikapcsolja a konfigurációs kulcsot, akkor a funkció nem törlődik a funkciók listájából.

## <a name="data-entities"></a>Adatentitások

A **Funkciókezelés** nevű adatentitás segítségével exportálhatja a Funkciókezelési beállításokat egy környezetből, majd importálhatja őket más környezetbe. Ez az entitás csak a meglévő funkciókat frissíti. Az entitás üzleti logikája azt is segít szavatolni, hogy a **Funkciókezelés** munkaterületen ugyanazokat a szabályokat alkalmazza a program, amikor az importálás megtörtént. Például a kötelező funkció beállítását nem lehet felülbírálni úgy, hogy a dátumot eltávolítja az importálás során.

A következő példák azt mutatják be, hogy mi történik, ha a **Funkciókezelés** entitást használja az adatok importálásához.

- Ha az **Engedélyezett** mező értékét **Igen** értékre módosítja, akkor a funkció engedélyezett lesz, és az **Engedélyezés dátuma** mező az aktuális dátumra lesz állítva.
- Ha az **Engedélyezett** mező értékét **Nem** értékre módosítja, vagy az **EnableDate** mezőt üresen hagyja, akkor a funkció le lesz tiltva, és az **Engedélyezés dátuma** mező törlődik. Nem lehet letiltani a kötelező funkciókat vagy egy olyan funkciót, amely nem tiltható le az engedélyezése után.
- Ha az **EnableDate** mező értékét a jövőbeli dátumra módosítja, akkor a szolgáltatás erre a dátumra van ütemezve.
- Ha az **Engedélyezett** mező értékét **Igen** értékre módosítja, és az **EnableDate** mező értékét egy jövőbeli dátumra állítja, akkor a funkció az adott dátumra lesz ütemezve. 
- Ha az **Engedélyezett** mező értékét **Nem** értékre módosítja, de az **EnableDate** mező értékét egy jövőbeli dátumra állítja, akkor a funkció az adott dátumra lesz ütemezve.
- Ha egy funkció engedélyezve van, és olyan **EnableDate** mezőt ad hozzá, amely a jövőbeli dátumra van állítva, akkor a funkció továbbra is engedélyezett lesz. A funkció újraütemezéséhez az **Engedélyezett** mezőt **Nem** értékre kell állítani.

## <a name="feature-management-and-flighting"></a>Funkciókezelés és tesztelés

A funkciókezelés funkcióval szabályozhatja az egyes kiadásokban szállított funkciókat. A tesztelés lehetővé teszi a Microsoft Teams számára, hogy korlátozott számú ügyfél számára adjanak ki funkciókat, így a szolgáltatások tesztelése és ellenőrzése nem érinti az összes ügyfelet. A funkciókezelés nem szabályozza a funkciók tesztelését.

## <a name="using-feature-management-to-turn-on-isv-features-or-custom-features"></a>A Funkciókezelés használata az ISV-funkciók és az egyéni funkciók bekapcsolásához

A funkciókezelés jelenleg nem érhető el a független szoftvergyártók (ISV-k) funkcióihoz és egyéni funkciókhoz. A Microsoft azonban további funkciókat ad hozzá a Funkciókezelés fejlesztéséhez. A fejlesztések befejezését követően a Microsoft minden funkció számára elérhetővé teszi a Funkciókezelést, és útmutatást nyújt a funkciók használatához szükséges frissítéshez.

## <a name="frequently-asked-questions-faq"></a>Gyakori kérdések (GYIK)

### <a name="when-are-features-added-removed-or-changed"></a>Mikor vannak hozzáadva, eltávolítva vagy módosítva a szolgáltatások? 
A szolgáltatások hozzáadása, eltávolítása és módosítása a kód módosításával történik a tulajdonos termékcsapat részéről. A környezeteket frissíteni kell a változtatások fogadásához.

### <a name="does-a-feature-become-mandatory-automatically"></a>Automatikusan kötelezővé válik egy funkció? 
Nem, egy funkció nem válik automatikusan kötelezővé. A tulajdonos termékcsapatnak kódmódosítást kell végeznie.

### <a name="why-isnt-there-a-specific-mandatory-enabled-date"></a>Miért nem létezik konkrét „kötelezően engedélyezett dátum”? 
A frissítések kiadásának ütemezése változó, a környezet frissítésének ütemezése is változó, és az ügyfelek dönthetnek úgy, hogy kihagynak egyes frissítéseket. Ennek eredményeképpen nehéz meghatározni adott dátumokat. 

### <a name="wheres-the-documentation-for-features-that-are-mandatory"></a>Hol található a kötelező szolgáltatások dokumentációját? 
Ez a dokumentáció az egyes Dynamics 365 alkalmazáscsoportoktól származik. Gyakran előfordul, hogy ezek a szolgáltatások az [Ügyfél funkcióinak frissítései](/dynamics365-release-plan/2021wave1/finance-operations/finance-operations-crossapp-capabilities/updates-client-feature-states) vagy az [Eltávolított vagy elavult funkciók között](../../../dev-itpro/migration-upgrade/deprecated-features.md) említettek. 

### <a name="is-there-an-in-product-notification-or-signal-that-a-feature-is-going-to-be-mandatory-enabled"></a>Megjelenik a termékben értesítés vagy jelzés, hogy a funkció engedélyezése kötelező lesz? 
A szolgáltatás kötelezővé tételéhez kapcsolódó értesítési mechanizmus jelenleg nem létezik.

### <a name="do-features-ever-get-enabled-without-the-customer-knowing-about-it"></a>Van-e olyan funkció, amely a vevő tudta nélkül is engedélyezve lesz válik? 
Igen, a funkciók a vevő tudta nélkül engedélyezhetők a következő helyzetekben:
- Egy funkció **Alapértelmezés szerint be** van kapcsolva. Ebben az állapotban a funkciót továbbra is le lehet tiltani. 
- Egy funkció **Kötelező** értékre módosul. Ez a változás csak nagyobb kiadással együtt történik meg. A kritikus funkciókat kivételes jelleggel bármely frissítéskor **Kötelező** állapotra lehet áthelyezni.

### <a name="what-is-feature-flighting-and-how-does-it-relate-to-feature-management"></a>Mi az a funkciótesztelés, és hogyan kapcsolódik a funkciókezeléshez? 
A funkciótesztelések valós idejű be-és ki kapcsolók, amelyeket a Microsoft vezérel. Eltérnek a Funkciókezelés által biztosított ügyfélvezérléstől. 
- A privát előzetes funkciók nem jelennek meg a Funkciókezelés modulban mindaddig, amíg nem lettek tesztelve. A termelésben a vevőnek bele kell egyeznie e a részvételbe egy speciális programban, hogy ez bekövetkezzen.
- A nyilvános előzetes verzió és a kiadott (általában elérhető) funkciók megjelennek meg a funkciókezelés modulban, hacsak tesztelésük nincs kikapcsolva. A tesztelés funkció kikapcsolása általában egy végső megoldás, ha a termékcsapat egy kritikus problémát talál, és általában az ügyfél szintjén van alkalmazva.

### <a name="do-features-ever-get-flighted-off-without-the-customer-knowing-about-it"></a>Van-e olyan funkció, amely a vevő tudta nélkül is ki van kapcsolva? 
Igen, ha egy funkció hatással van egy környezet működésére, és nem rendelkezik funkcionális hatással, akkor alapértelmezés szerint engedélyezve lehet.

### <a name="how-can-feature-enablement-be-checked-in-code"></a>Milyen módon ellenőrizhető a funkció engedélyezése a kódban?
A **isFeatureEnabled** módszert alkalmazza a **FeatureStateProvider** osztályon úgy, hogy a funkcióosztály egy példányát átadja a számára. Példa: 

```xpp
if (FeatureStateProvider::isFeatureEnabled(BatchContentionPreventionFeature::instance()))
```

### <a name="how-can-feature-enablement-be-checked-in-metadata"></a>Milyen módon ellenőrizhető a funkció engedélyezése a metaadatokban?
A **FeatureClass** tulajdonsággal jelezheti, hogy néhány metaadatot társítottak egy funkcióhoz. A funkcióhoz használt osztálynevet használhatja, például **BatchContentionPreventionFeature**. Ezek a metaadatok csak az adott funkcióban láthatók. A **FeatureClass** tulajdonság a menükben, a menüelemekben, a sorszámozott értékekben és a tábla/nézet mezőkben érhető el.

### <a name="what-is-a-feature-class"></a>Mi a funkcióosztály?
A Funkciókezelő funkcióit a program *funkcióosztályokként* definiálja. A funkcióosztályok **IFeatureMetadata**-kat hajtanak végre, és a funkcióosztály attribútumát használják a Funkciókezelő munkaterületen való azonosításukhoz. A rendelkezésre álló funkcióosztályokra számos példa van, amelyeknek a kódban való engedélyezését a **FeatureStateProvider** API-val, a metaadatokban pedig a **FeatureClass** tulajdonsággal ellenőrizheti. Példa: 

```xpp
[ExportAttribute(identifierStr(Microsoft.Dynamics.ApplicationPlatform.FeatureExposure.IFeatureMetadata))]
internal final class BankCurrencyRevalGlobalEnableFeature implements IFeatureMetadata
```

### <a name="what-is-the-ifeaturelifecycle-implemented-by-some-feature-classes"></a>Mit jelent az egyes funkcióosztályok által végrehajtott IFeatureLifecycle?
Az IFeatureLifecycle a Microsoft egyik belső mechanizmusa a funkció életciklusa szakaszának jelzésére. A funkciók a következők lehetnek:
- `PrivatePreview` – Tesztcsomagra van szükség ahhoz, hogy látható legyen.
- `PublicPreview` – Alapértelmezés szerint megjelenik, de figyelmeztetés jelzi, hogy a funkció előnézetben van.
- `Released` – Teljesen kiadva.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
