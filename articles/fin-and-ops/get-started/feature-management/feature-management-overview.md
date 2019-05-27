---
title: Funkciókezelés áttekintése
description: Ez a témakör bemutatja a funkciókezelés szolgáltatást, valamint azt, hogy hogyan használhatja azt.
author: mikefalkner
manager: AnnBe
ms.date: 04/18/2019
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
ms.openlocfilehash: e75e42926db22d4fccda86c755b12d9d121a9c0e
ms.sourcegitcommit: be447fc81bc874982bc0185fcb4d87d99bd742c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/08/2019
ms.locfileid: "1538691"
---
# <a name="feature-management-overview"></a>Funkciókezelés áttekintése

[!include[banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

A Microsoft Dynamics 365 for Finance and Operations minden kiadásában új szolgáltatások és frissítések jelennek meg. A funkció-kezelési élmény olyan munkaterületet tartalmaz, amelyen megtekintheti az egyes kiadásokban elérhetővé tett szolgáltatások listáját. Alapértelmezés szerint az új szolgáltatások ki vannak kapcsolva. A munkaterületen bekapcsolhatja a szolgáltatásokat, és megtekintheti a rájuk vonatkozó dokumentációt.

## <a name="the-feature-management-workspace"></a>A Funkciókezelés munkaterület használata.

A **Funkciókezelés** munkaterületet úgy nyithatja meg, hogy kijelöli az irányítópult megfelelő csempéjét. Megjelenik egy lap, amelyen megtekintheti az összes funkciót az összes kiadáshoz, amelyeket támogat a Funkciókezelés élmény. Idővel a Microsoft javítja A Funkciókezelés élményét, így további funkciókat is kínál majd, amelyek segítik a funkciók kezelését.

A funkciólista a következő információkat tartalmazza:

- **Funkció neve** – A hozzáadott funkció leírása.
- **Engedélyezett állapot** – Egy szimbólum azt jelzi, hogy engedélyezve van-e a funkció (pipa),nincs engedélyezve (üres) ütemezve van engedélyezésre (óra), vagy kötelezően engedélyezve van (lakat). Az itt megjelenített beállítás minden jogi személynél használatos. Ne felejtse el, hogy ha a funkció be is van kapcsolva, a biztonság szabályozza azt. Ennélfogva a funkció csak azoknak a felhasználóknak érhető el, akik hozzáférhetnek a biztonsági szerepkörük alapján. Csak olyan jogi személyek számára érhető el, amelyekhez a felhasználó hozzáfér.
- **Engedélyezés dátuma** – Az a dátum, amikor a funkció be lett kapcsolva, vagy be lesz kapcsolva, ha a dátum jövőbeli dátum.
- **Funkció hozzáadása** – Az a dátum, amikor a funkciót hozzáadták a környezethez. A program automatikusan beírja ezt a dátumot, amikor a havi kiadási ciklus során frissíti a környezetet.
- **Modul** – Az új funkció által érintett modul.

Ha kiválaszt egy funkciót, akkor a részleteket ablaktáblában, a szolgáltatások listájának jobb oldalán megjelennek a további információk. A ablaktábla tetején látható a funkció neve, a funkció hozzáadásának dátuma, a funkció által érintett modul, valamint egy **További információk** hivatkozás. Erre a hivatkozásra kattintva megtekintheti a funkció dokumentációját. Ha a dokumentáció nem érhető el, akkor egy ideiglenes oldalra kerül. A részleteket tartalmazó ablaktábla tartalmaz egy **Megjegyzések** mezőt is, amelybe felveheti a saját megjegyzéseit a funkcióval kapcsolatosan.

A **Funkciókezelés** munkaterület több lapot is tartalmaz, amelyen a funkciók listája látható. 
- **Új** – A legutóbbi havi frissítés óta hozzáadott összes funkciót jeleníti meg. Ha kihagyott havi frissítést, akkor a legutóbbi frissítés óta érkezett minden új funkciót tartalmaz. A legújabb funkciók a lista tetején jelennek meg. Az új funkciók száma összesen a lap felső részén található csempén jelenik meg.
- **Nincs engedélyezve** – Az összes nem engedélyezett funkció megjelenítése. A legújabb funkciók a lista tetején jelennek meg. Az új funkciók száma összesen a lap felső részén található csempén jelenik meg.
- **Ütemezve** – Az összes olyan funkció megjelenítése, amelyet a jövőbeli dátumra ütemeztek. A legkorábbi dátumra ütemezett szolgáltatások jelennek meg a lista tetején. Az új funkciók száma összesen a lap felső részén található csempén jelenik meg.
- **Mind** – Az összes funkció megjelenítése. A legújabb funkciók a lista tetején jelennek meg.


## <a name="enable-a-feature"></a>Egy funkció engedélyezése

Ha egy funkció nincs engedélyezve az **Engedélyezés** gomb látható a részletek ablaktáblán. Ezt a gombot használhatja a funkció engedélyezéséhez.

1. Válassza ki az engedélyezni kívánt funkciót, majd a részletek ablaktáblán válassza az **Engedélyezés**lehetőséget.
2. Megjelenik egy csúszka, amelyen megadhatja, hogy a funkció mikor legyen engedélyezve. Alapértelmezés szerint ez a dátum az aktuális dátum.
3. Válassza az **Engedélyezés** lehetőséget a funkció engedélyezéséhez.

Néhány funkció nem tiltható le, miután engedélyezte azokat. Ha az engedélyezni kívánt funkció nem tiltható le, egy figyelmeztetés jelenik meg. Ezen a ponton választhatja **Mégsem** lehetőséget a művelet visszavonásához és a szolgáltatás letiltásának fenntartásához. Ha azonban az **Engedélyezés** lehetőséget választja, és engedélyezi a funkciót, akkor nem fogja tudni kikapcsolni később.

Miután a funkció engedélyezve van, a részletek ablaktáblán megjelenik egy üzenet a **További információ** hivatkozása alatt. Ez az üzenet vagy azt jelzi, hogy a funkció engedélyezve van, vagy azt jelzi, hogy a funkció mikor lesz engedélyezve a jövőben. Ha a jövőbeli dátumot adott meg, akkor a funkció az **Ütemezett** listán jelenik meg. Ez az üzenet mindig akkor jelenik meg, amikor kiválasztja a funkciót a szolgáltatások listájában. A jövőbeli időpontra ütemezett funkciókat a rendszer a rendszer dátumának megfelelő időzóna alapján egy kötegelt feldolgozással éjfélkor fogja engedélyezni. 

## <a name="reschedule-a-feature"></a>Funkció újraütemezése

Ha egy funkció a jövőre vonatkozóan van engedélyezve az **Újraütemezés** gomb látható a részletek ablaktáblán. Ezzel a gombbal módosíthatja az **Engedélyezés dátumát** egy másik dátumra.

1. Válassza ki az ütemezett funkciót, amelyet át szeretne ütemezni, majd a részletek ablaktáblán válassza az **Átütemezés**lehetőséget.
2. Megjelenik egy csúszka, amelyen megadhatja, hogy a funkció mikor legyen engedélyezve. 
3. Válassza az **Engedélyezés** lehetőséget a funkció újraütemezéséhez, vagy a **Letiltás** lehetőséget az ütemezés megszüntetéséhez.

## <a name="disable-a-feature"></a>Egy funkció letiltása

Ha egy funkció már engedélyezve van a **Letiltás** gomb látható a részletek ablaktáblán. Ezt a gombot használhatja a funkció letiltásához. A **Letiltás** gomb nem érhető el, ha a funkciót annak engedélyezése után nem lehet letiltani.

- Válassza ki a kikapcsolni kívánt funkciót, majd a részletek ablaktáblán válassza a **Letiltás** lehetőséget.

- A funkció le van tiltva, és a dátum törlődik.

Miután a funkció le van tiltva, a részletek ablaktáblán megjelenik egy üzenet a **További információ** hivatkozása alatt. Ez az üzenet azt jelzi, hogy a funkció még nincs engedélyezve, és a **Nem engedélyezett** listán fog megjelenni. Az üzenet mindig akkor jelenik meg, amikor kiválasztja a funkciót a szolgáltatások listájában.

## <a name="features-that-must-be-enabled"></a>Funkciók, amelyeket engedélyezni kell.

Előfordulhat, hogy a frissítés során kritikus funkciók érkeznek, amelyeket engedélyezni kell a frissítés során. A rendszer automatikusan engedélyezi az **Engedélyezés dátuma**helyen. A részletek ablaktáblán megjelenik egy üzenet a **További információk** hivatkozás alatt. Ez az üzenet arról ad tájékoztatást, hogy a funkció engedélyezve van, vagy automatikusan engedélyezve lesz az **Engedélyezés dátumán**. Mindig akkor jelenik meg, amikor kiválasztja a funkciót a szolgáltatások listájában.

## <a name="assigning-roles"></a>Szerepkörök hozzárendelése

A **Funkciókezelés** munkaterületet rendszeradminisztrátorok és a szolgáltatáskezelő és szolgáltatásmegtekintő szerepkörhöz rendelt felhasználók, amely szerepkörök a szolgáltatáskezelés élményének támogatásához lettek létrehozva felhasználók nyithatják meg. A szolgáltatáskezelő szerepkörben lévő felhasználók bármilyen funkciót be-és kikapcsolhatnak. Ezenkívül a funkcióhoz tartozó megjegyzések szakaszt is módosíthatják. A funkciómegtekintő szerepkör felhasználói csak megtekinthetik a **Funkciókezelés** munkaterületet. Nem kapcsolhatnak be és ki funkciókat.

A funkciókezelő szerepkör és a funkciómegtekintő szerepkör nem bírálja felül a felhasználó által megadott biztonságot. A szerepkörök csak a szolgáltatások engedélyezésének elérését szabályozza. Nem biztosít hozzáférést magukhoz a funkciókhoz.

## <a name="using-feature-management-to-enable-isv-features-or-custom-features"></a>A szolgáltatáskezelés használata az ISV-funkciók és az egyéni funkciók engedélyezéséhez

A funkciókezelési folyamat jelenleg nem érhető el az ISV-funkciók és az egyéni funkciók esetében. További funkcionalitást teszünk elérhetővé a funkciókezelés javítása érdekében, és a fejlesztések befejezését követően minden funkcióhoz megnyílik a funkciókezelés, és konkrét útmutatást kap arra vonatkozóan, hogyan frissítheti a funkciót a használatához.

## <a name="feature-management-and-flighting"></a>Funkciókezelés és tesztelés

A funkciókezelés funkcióval szabályozhatja az egyes verziókban szállított szolgáltatásokat. A tesztelés lehetővé teszi a Microsoft teams számára, hogy korlátozott számú ügyfél számára adjanak ki szolgáltatásokat, így a szolgáltatások tesztelése és validálása nem érinti az összes ügyfelet. A funkciókezelése nem szabályozza a szolgáltatások tesztelését.
