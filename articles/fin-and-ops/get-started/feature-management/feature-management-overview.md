---
title: Funkciókezelés áttekintése
description: Ez a témakör bemutatja a funkciókezelés szolgáltatást, valamint azt, hogy hogyan használhatja azt.
author: mikefalkner
manager: AnnBe
ms.date: 07/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: IT Pro, Application user
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: 21eaf2fdcadf8fe9f91438a97a88cc3bddab8286
ms.sourcegitcommit: d0fa8d0140fa81029527edb317623c1a7737c593
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2019
ms.locfileid: "1862938"
---
# <a name="feature-management-overview"></a>Funkciókezelés áttekintése

[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

A Microsoft Dynamics 365 for Finance and Operations minden kiadásában új szolgáltatások és frissítések jelennek meg. A funkció-kezelési élmény olyan munkaterületet tartalmaz, amelyen megtekintheti az egyes kiadásokban elérhetővé tett szolgáltatások listáját. Alapértelmezés szerint az új szolgáltatások ki vannak kapcsolva. A munkaterületen bekapcsolhatja a szolgáltatásokat, és megtekintheti a rájuk vonatkozó dokumentációt.

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

- Válassza ki a bekapcsolni kívánt funkciót, majd a részletek ablaktáblán válassza az **Engedélyezés most**lehetőséget. A funkció be van kapcsolva.

Néhány funkció nem kapcsolható ki a bekapcsolás után. Ha a bekapcsolni kívánt funkció nem kapcsolható ki, egy figyelmeztetés jelenik meg. Ezen a ponton választhatja **Mégsem** lehetőséget a művelet visszavonásához és a szolgáltatás kikapcsolásának fenntartásához. Ha azonban az **Engedélyezés** lehetőséget választja a bekapcsoláshoz, és engedélyezi a funkciót, akkor nem fogja tudni kikapcsolni később.

Bizonyos funkciók esetében a bekapcsolás előtt további információkat biztosító üzenetek jelennek meg. Ezeket a funkciókat sárga figyelmeztető jel jelöli. Alaposan tanulmányozza át a további információkat, hogy megtudja, mi történik a funkció bekapcsolása esetén. A funkciót azonban bármikor bekapcsolhatja az **Engedélyezés** lehetőséggel.

Bizonyos funkciók esetében üzenet jelenik meg, hogy a funkció engedélyezéséhez valamilyen műveletet kell végrehajtani. Ezeket a funkciókat piros X jel jelöli. A funkció engedélyezéséhez el kell végezni a leírásban említett műveleteket. Ha egy funkció például nem használható egy konfigurációs kulcs letiltása nélkül, akkor először le kell tiltani a kulcsot, és utána kell engedélyezni a funkciót a Funkció kezelése részen.

Miután a funkció be van kapcsolva, a részletek ablaktáblán megjelenik egy üzenet a **További információ** hivatkozása alatt. Ez az üzenet vagy azt jelzi, hogy a funkció be van kapcsolva, vagy a jövőbeli dátumot jelzi, amikor a funkció engedélyezve lesz a jövőben. Mindig akkor jelenik meg, amikor kiválasztja a funkciót a szolgáltatások listájában.

A jövőre ütemezett bekapcsolású funkciók az **Ütemezett** lapon jelennek meg. A megadott dátum napján éjfélkor egy kötegfolyamat kapcsolja be őket, a rendszerdátum által képviselt időzóna alapján.

## <a name="reschedule-a-feature"></a>Funkció újraütemezése

Ha egy funkció a jövőre vonatkozóan van bekapcsolásra ütemezve, az **Ütemezés** gomb látható a részletek ablaktáblán. Ezzel a gombbal módosíthatja az **Engedélyezés dátuma** értékét egy másik dátumra.

1. Válassza ki az ütemezett funkciót, amelyet át szeretne ütemezni, majd a részletek ablaktáblán válassza az **Ütemezés**lehetőséget.
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

- Válassza az **Összes új funkció alapértelmezett módon engedélyezve** lehetőséget az összes új funkció bekapcsolásához, amikor hozzáadják őket a környezetéhez.
- Válassza az **Összes új funkció alapértelmezett módon letiltva** lehetőséget az összes új funkció kikapcsolásához, amikor hozzáadják őket a környezetéhez.

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

- Ha az **Engedélyezett** mező értékét **Igen**értékre módosítja, akkor a funkció be van kapcsolva, és az **Engedélyezés dátuma** mező az aktuális dátumra van állítva.
- Ha az **Engedélyezett** mező értékét **Nem** értékre módosítja, vagy az **EnableDate** mezőt üresen hagyja, akkor a funkció ki van kapcsolva, és az **Engedélyezés dátuma** mező törlődik. Nem lehet kikapcsolni a kötelező funkciókat vagy egy olyan funkciót, amely nem kapcsolható ki, ha be van kapcsolva.
- Ha az **EnableDate** mező értékét a jövőbeli dátumra módosítja, akkor a szolgáltatás erre a dátumra van ütemezve.
- Ha az **Engedélyezett** mező értékét **Igen** értékre módosítja, és az **EnableDate** mező értékét egy jövőbeli dátumra állítja, akkor a funkció az adott dátumra lesz ütemezve. 
- Ha az **Engedélyezett** mező értékét **Nem** értékre módosítja, de az **EnableDate** mező értékét egy jövőbeli dátumra állítja, akkor a funkció az adott dátumra lesz ütemezve.
- Ha egy funkció be van kapcsolva, és olyan **EnableDate** -mezőt ad hozzá, amely a jövőbeli dátumra van állítva, akkor a funkció továbbra is be van kapcsolva. A funkció újraütemezéséhez az **Engedélyezett** mezőt **Nem** értékre kell állítani.

## <a name="feature-management-and-flighting"></a>Funkciókezelés és tesztelés

A funkciókezelés funkcióval szabályozhatja az egyes kiadásokban szállított funkciókat. A tesztelés lehetővé teszi a Microsoft Teams számára, hogy korlátozott számú ügyfél számára adjanak ki funkciókat, így a szolgáltatások tesztelése és ellenőrzése nem érinti az összes ügyfelet. A funkciókezelés nem szabályozza a funkciók tesztelését.

## <a name="using-feature-management-to-turn-on-isv-features-or-custom-features"></a>A Funkciókezelés használata az ISV-funkciók és az egyéni funkciók bekapcsolásához

A funkciókezelés jelenleg nem érhető el a független szoftvergyártók (ISV-k) funkcióihoz és egyéni funkciókhoz. A Microsoft azonban további funkciókat ad hozzá a Funkciókezelés fejlesztéséhez. A fejlesztések befejezését követően a Microsoft minden funkció számára elérhetővé teszi a Funkciókezelést, és útmutatást nyújt a funkciók használatához szükséges frissítéshez.
