---
title: Funkciókezelés áttekintése
description: Ez a témakör bemutatja a funkciókezelés szolgáltatást, valamint azt, hogy hogyan használhatja azt.
author: ChrisGarty
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: IT Pro, Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: 2164c07d1a179a0aa15611b742084d872f41bbfc
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270813"
---
# <a name="feature-management-overview"></a>Funkciókezelés áttekintése

[!include [banner](../../includes/banner.md)]

Minden kiadásban új szolgáltatások és frissítések jelennek meg. A funkció-kezelési élmény olyan munkaterületet tartalmaz, amelyen megtekintheti az egyes kiadásokban elérhetővé tett szolgáltatások listáját. Alapértelmezés szerint az új szolgáltatások ki vannak kapcsolva. A munkaterületen bekapcsolhatja a szolgáltatásokat, és megtekintheti a rájuk vonatkozó dokumentációt.

## <a name="the-feature-management-workspace"></a>A Funkciókezelés munkaterület használata.

A **Funkciókezelés** munkaterületet úgy nyithatja meg, hogy kijelöli az irányítópult megfelelő csempéjét. Megjelenik egy lap, amelyen megtekintheti az összes funkciót az összes kiadáshoz, amelyeket támogat a Funkciókezelés élmény. Idővel a Microsoft javítja A Funkciókezelés élményét, így további funkciókat is kínál majd, amelyek segítik a funkciók kezelését.

A funkciólista a következő információkat tartalmazza:

- **Funkció neve** – A hozzáadott funkció leírása.
- **Engedélyezett állapot** – A jel azt jelzi, hogy egy funkció be van-e kapcsolva (pipa), még nem lett bekapcsolva (üres), bekapcsolásra ütemezett (óra), kötelezően be lett kapcsolva (zár), a bekapcsolás előtt ellenőrzendő (figyelmeztetés) vagy nem engedélyezhető (X). A látható beállítást minden jogi személyhez használja a rendszer. Ne felejtse el, hogy ha a funkció be is van kapcsolva, a biztonság szabályozza azt. Ennélfogva a funkció csak azoknak a felhasználóknak érhető el, akik hozzáférhetnek a biztonsági szerepkörük alapján. Csak olyan jogi személyekben érhető el, amelyekhez a felhasználó hozzáfér.
- **Engedélyezési dátum** – Az a dátum, amikor a funkciót bekapcsolták, vagy ütemezve van a bekapcsolásra.
- **Funkció hozzáadása** – Az a dátum, amikor a funkciót hozzáadták a környezethez. A program automatikusan beírja ezt a dátumot, amikor a havi kiadási ciklus során frissíti a környezetet.
- **Modul** – Az új funkció által érintett modul.

Ha kiválaszt egy funkciót, akkor a részleteket ablaktáblában, a szolgáltatások listájának jobb oldalán megjelennek a további információk. A ablaktábla tetején látható a funkció neve, a funkció hozzáadásának dátuma, a funkció által érintett modul, valamint egy **További információk** hivatkozás. Erre a hivatkozásra kattintva megtekintheti a funkció dokumentációját. Ha a dokumentáció nem érhető el, akkor egy ideiglenes oldalra kerül. A részleteket tartalmazó ablaktábla tartalmaz egy **Megjegyzések** mezőt is, amelybe felveheti a saját megjegyzéseit a funkcióval kapcsolatosan.

A **Funkciókezelés** munkaterület több lapot is tartalmaz, amelyek mindegyikén a funkciók listája látható.

- **Új** – Ez a lap a legutóbbi havi frissítés óta hozzáadott összes funkciót jeleníti meg. Ha kihagyott egy havi frissítést, akkor a lap megjeleníti a legutóbbi frissítés óta hozzáadott összes új funkciót. A legújabb funkciók a lista tetején jelennek meg. Az új funkciók száma összesen a lap felső részén található csempén jelenik meg.
- **Nincs engedélyezve** – Ezen a lapon látható az összes olyan funkció, amely még nem lett bekapcsolva. A legújabb funkciók a lista tetején jelennek meg. Az új, még nem bekapcsolt funkciók száma összesen a lap felső részén található csempén jelenik meg.
- **Ütemezve** – Ezen a lapon látható az összes olyan funkció, amelynek bekapcsolását egy jövőbeli dátumra ütemeztek. A legkorábbi dátumra ütemezett szolgáltatások jelennek meg a lista tetején. Az ütemezett új funkciók száma összesen a lap felső részén található csempén jelenik meg.
- **Összes** – Ezen a lapon látható az összes funkció. A legújabb funkciók a lista tetején jelennek meg.

## <a name="turn-on-a-feature"></a>Funkció bekapcsolása

Ha egy funkció nincs bekapcsolva, az **Engedélyezés most** gomb látható a részletek ablaktáblán. Ezt a gombot használhatja a funkció bekapcsolásához.

- Válassza ki a bekapcsolni kívánt funkciót, majd a részletek ablaktáblán válassza az **Engedélyezés most** lehetőséget. A funkció be van kapcsolva.

Néhány funkció nem kapcsolható ki a bekapcsolás után. Ha a bekapcsolni kívánt funkció nem kapcsolható ki, egy figyelmeztetés jelenik meg. Ezen a ponton választhatja **Mégsem** lehetőséget a művelet visszavonásához és a szolgáltatás kikapcsolásának fenntartásához. Ha azonban az **Engedélyezés** lehetőséget választja a bekapcsoláshoz, és engedélyezi a funkciót, akkor nem fogja tudni kikapcsolni később.

Bizonyos funkciók esetében a bekapcsolás előtt további információkat biztosító üzenetek jelennek meg. Ezeket a funkciókat sárga figyelmeztető jel jelöli. Alaposan tanulmányozza át a további információkat, hogy megtudja, mi történik a funkció bekapcsolása esetén. A funkciót azonban bármikor bekapcsolhatja az **Engedélyezés** lehetőséggel.

Bizonyos funkciók esetében üzenet jelenik meg, hogy a funkció engedélyezéséhez valamilyen műveletet kell végrehajtani. Ezeket a funkciókat piros X jel jelöli. A funkció engedélyezéséhez el kell végezni a leírásban említett műveleteket. Ha egy funkció például nem használható egy konfigurációs kulcs letiltása nélkül, akkor először le kell tiltani a kulcsot, és utána kell engedélyezni a funkciót a Funkció kezelése részen.

Miután a funkció be van kapcsolva, a részletek ablaktáblán megjelenik egy üzenet a **További információ** hivatkozása alatt. Ez az üzenet vagy azt jelzi, hogy a funkció be van kapcsolva, vagy a jövőbeli dátumot jelzi, amikor a funkció engedélyezve lesz a jövőben. Mindig akkor jelenik meg, amikor kiválasztja a funkciót a szolgáltatások listájában.

A jövőre ütemezett bekapcsolású funkciók az **Ütemezett** lapon jelennek meg. A megadott dátum napján éjfélkor egy kötegfolyamat kapcsolja be őket, a rendszerdátum által képviselt időzóna alapján.

## <a name="reschedule-a-feature"></a>Funkció újraütemezése

Ha egy funkció a jövőre vonatkozóan van bekapcsolásra ütemezve, az **Ütemezés** gomb látható a részletek ablaktáblán. Ezzel a gombbal módosíthatja az **Engedélyezés dátuma** értékét egy másik dátumra.

1. Válassza ki az ütemezett funkciót, amelyet át szeretne ütemezni, majd a részletek ablaktáblán válassza az **Ütemezés** lehetőséget.
2. A megjelenő párbeszédpanelen az **Engedélyezés dátuma** mezőben adja meg azt az új dátumot, amikor a funkciót be kell kapcsolni.
3. Válassza az **Engedélyezés** lehetőséget a funkció újraütemezéséhez, vagy a **Letiltás** lehetőséget az ütemezés megszüntetéséhez.

## <a name="turn-off-a-feature"></a>Funkció kikapcsolása

Ha egy funkció már be van kapcsolva, a **Letiltás** gomb látható a részletek ablaktáblán. Ezt a gombot használhatja a funkció kikapcsolásához. A **Letiltás** gomb nem érhető el, ha a funkciót annak bekapcsolása után nem lehet kikapcsolni.

- Válassza ki a kikapcsolni kívánt funkciót, majd a részletek ablaktáblán válassza a **Letiltás** lehetőséget. A funkció ki van kapcsolva, és az **Engedélyezés dátuma** mező kiürült.

Miután a funkció ki van kapcsolva, a részletek ablaktáblán megjelenik egy üzenet a **További információ** hivatkozása alatt. Ez az üzenet azt jelzi, hogy a funkció még nincs bekapcsolva. Mindig akkor jelenik meg, amikor kiválasztja a funkciót a szolgáltatások listájában. A funkciók, amely még nem lettek bekapcsolva, a **Nem engedélyezett** lapon jelennek meg.

## <a name="features-that-must-be-turned-on"></a>Funkciók, amelyeket be kell kapcsolni

Néha a frissítés során kritikus fontosságú funkciók érkeznek, amelyeket be kell kapcsolni a frissítés során. Ezek a funkciók automatikusan be lesznek kapcsolva az **Engedélyezés dátuma** mezőben megadott dátumon. Ezeknél a funkcióknál a részletek ablaktáblán megjelenik egy üzenet a **További információ** hivatkozása alatt. Ez az üzenet vagy azt jelzi, hogy a funkció be van kapcsolva, vagy a dátumot jelzi, amikor a funkció be lesz kapcsolva a jövőben. Mindig akkor jelenik meg, amikor kiválasztja a funkciót a szolgáltatások listájában.

## <a name="enable-all-features"></a>Az összes funkció engedélyezése

Alapértelmezés szerint a környezethez hozzáadott összes funkció ki van kapcsolva. Az összes funkció **Az összes engedélyezése** gombbal engedélyezhető. 

**Az összes engedélyezése** gombra kattintáskor megjelenik egy beállítás, ahol meg kell adni a következő adatokat:
- Az olyan funkciók listája, amelyeknek az engedélyezését jóvá kell hagyni. Ha engedélyezni szeretné a listában szereplő funkciókat, válassza az **Igen** lehetőséget a **Megerősítést igénylő funkciók engedélyezése** gombnál.
- Megjelenik az olyan funkciók listája, amelyek nem engedélyezhetők. Ezek nem engedélyezhető funkciók

Az összes olyan funkció, amely engedélyezhető, engedélyezve lesz. Ha egy funkció jövőbeli engedélyezésre ütemezett, az ütemezés nem módosul. 

## <a name="turn-on-all-features-automatically"></a>Az összes funkció automatikus bekapcsolása

Alapértelmezés szerint a környezethez hozzáadott összes funkció ki van kapcsolva, hacsak nem kötelező funkciók. Ha viszont automatikusan be kívánja kapcsolni az összes új funkciót, akkor a munkaterület címe alatti legördülő lista segítségével módosíthatja, hogy mi történik az új szolgáltatások hozzáadásakor.

- Válassza az `Enable new features automatically` lehetőséget az összes új funkció bekapcsolásához, amikor hozzáadják őket a környezetéhez.
- Válassza az `Do not enable new features automatically` lehetőséget alapértelmezésként az összes új funkció kikapcsolásához, amikor hozzáadják őket a környezetéhez.


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

- Ha az **Engedélyezett** mező értékét **Igen** értékre módosítja, akkor a funkció be van kapcsolva, és az **Engedélyezés dátuma** mező az aktuális dátumra van állítva.
- Ha az **Engedélyezett** mező értékét **Nem** értékre módosítja, vagy az **EnableDate** mezőt üresen hagyja, akkor a funkció ki van kapcsolva, és az **Engedélyezés dátuma** mező törlődik. Nem lehet kikapcsolni a kötelező funkciókat vagy egy olyan funkciót, amely nem kapcsolható ki, ha be van kapcsolva.
- Ha az **EnableDate** mező értékét a jövőbeli dátumra módosítja, akkor a szolgáltatás erre a dátumra van ütemezve.
- Ha az **Engedélyezett** mező értékét **Igen** értékre módosítja, és az **EnableDate** mező értékét egy jövőbeli dátumra állítja, akkor a funkció az adott dátumra lesz ütemezve. 
- Ha az **Engedélyezett** mező értékét **Nem** értékre módosítja, de az **EnableDate** mező értékét egy jövőbeli dátumra állítja, akkor a funkció az adott dátumra lesz ütemezve.
- Ha egy funkció be van kapcsolva, és olyan **EnableDate** -mezőt ad hozzá, amely a jövőbeli dátumra van állítva, akkor a funkció továbbra is be van kapcsolva. A funkció újraütemezéséhez az **Engedélyezett** mezőt **Nem** értékre kell állítani.

## <a name="feature-management-and-flighting"></a>Funkciókezelés és tesztelés

A funkciókezelés funkcióval szabályozhatja az egyes kiadásokban szállított funkciókat. A tesztelés lehetővé teszi a Microsoft Teams számára, hogy korlátozott számú ügyfél számára adjanak ki funkciókat, így a szolgáltatások tesztelése és ellenőrzése nem érinti az összes ügyfelet. A funkciókezelés nem szabályozza a funkciók tesztelését.

## <a name="new-features-are-optional-for-12-months"></a>Az új szolgáltatások nem kötelezőek 12 hónapig.

Ha egy új, nem kritikus funkció van telepítve, akkor egy 12 hónapos időszakra nem kötelező. Ez lehetővé teszi az Ön és a szervezet számára, hogy előre tervezze meg a funkció felvételének idejét, és tesztelje a napi műveletein. További információkat az [Egyverziós szolgáltatásfrissítések GYIK](../one-version.md#what-about-new-features) oldalon találhat.

## <a name="using-feature-management-to-turn-on-isv-features-or-custom-features"></a>A Funkciókezelés használata az ISV-funkciók és az egyéni funkciók bekapcsolásához

A funkciókezelés jelenleg nem érhető el a független szoftvergyártók (ISV-k) funkcióihoz és egyéni funkciókhoz. A Microsoft azonban további funkciókat ad hozzá a Funkciókezelés fejlesztéséhez. A fejlesztések befejezését követően a Microsoft minden funkció számára elérhetővé teszi a Funkciókezelést, és útmutatást nyújt a funkciók használatához szükséges frissítéshez.

## <a name="frequently-asked-questions-faq"></a>Gyakori kérdések (GYIK)

### <a name="when-are-features-added-removed-or-changed"></a>Mikor vannak hozzáadva, eltávolítva vagy módosítva a szolgáltatások? 
A szolgáltatások hozzáadása, eltávolítása és módosítása a kód módosításával történik. A változtatások fogadásához frissíteni kell a környezeteket.

### <a name="does-a-feature-become-mandatory-automatically"></a>Automatikusan kötelezővé válik egy funkció? 
Nem, egy funkció kötelezővé válása nem egy automatikus művelet. A termékcsopatoknak kód módosítását el kell végezniük.

### <a name="when-do-features-become-mandatory"></a>Mikor válnak kötelezővé funkciók? 
Az alapelv az, hogy minden új funkció egy 12 hónapos időszakban választható és addig nem szükséges semmilyen módosításkezelés, amíg nem engedélyezi a funkciót. A termékcsoportok eldönthetik, hogy az adott időszak lejártát követően kötelezővé teszik-e a szolgáltatást. 

### <a name="why-isnt-there-a-specific-mandatory-enabled-date"></a>Miért nem létezik konkrét „kötelezően engedélyezett dátum”? 
A frissítések kiadásának ütemezése változó, a környezet frissítésének ütemezése is változó, és az ügyfelek dönthetnek úgy, hogy kihagynak egyes frissítéseket. Ennek eredményeképpen nehéz meghatározni adott dátumokat. 

### <a name="wheres-the-documentation-for-features-that-are-mandatory"></a>Hol található a kötelező szolgáltatások dokumentációját? 
Ez a dokumentáció az egyes Dynamics 365 alkalmazáscsoportoktól származik. Gyakran előfordul, hogy ezek a szolgáltatások az [Ügyfél funkcióinak frissítései](/dynamics365-release-plan/2021wave1/finance-operations/finance-operations-crossapp-capabilities/updates-client-feature-states) vagy az [Eltávolított vagy elavult funkciók között](../../../dev-itpro/migration-upgrade/deprecated-features.md) említettek. 

### <a name="is-there-an-in-product-notification-or-signal-that-a-feature-is-going-to-be-mandatory-enabled"></a>Megjelenik a termékben értesítés vagy jelzés, hogy a funkció engedélyezése kötelező lesz? 
A szolgáltatás kötelezővé tételéhez kapcsolódó értesítési mechanizmus jelenleg nem létezik.

### <a name="do-features-ever-get-enabled-without-the-customer-knowing-about-it"></a>Van-e olyan funkció, amely a vevő tudta nélkül is engedélyezve lesz válik? 
Igen, ha a funkcióknak nincs működési hatásuk, akkor alapértelmezés szerint engedélyezve lehetnek.

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
