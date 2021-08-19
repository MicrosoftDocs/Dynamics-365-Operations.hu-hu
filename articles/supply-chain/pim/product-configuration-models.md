---
title: Termékkonfigurálási modellek áttekintése
description: Ez a cikk a termékkonfigurálási modellekkel kapcsolatos szakkifejezéseket és fogalmakat határozza meg. A termékkonfigurálási modellek általános termékszerkezet felépítését teszik lehetővé, amely számos termékváltozat konfigurálásához használható egyetlen termékhez.
author: cvocph
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PCProductConfigurationModelDetails, PCProductConfigurationModelListPage, PCModalWaitDialog, PCTemplateConfigurationManager, PCConfigurationUIGrouping
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "4031"
- intro-internal
ms.assetid: 70b968e8-e550-4731-823d-d713b8910f7b
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 48cabc174cd46d95631010692da5972c182b36167d520cfefd9742b4b522ca73
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722367"
---
# <a name="product-configuration-models-overview"></a>Termékkonfigurálási modellek áttekintése

[!include [banner](../includes/banner.md)]

Ez a cikk a termékkonfigurálási modellekkel kapcsolatos szakkifejezéseket és fogalmakat határozza meg. A termékkonfigurálási modellek általános termékszerkezet felépítését teszik lehetővé, amely számos termékváltozat konfigurálásához használható egyetlen termékhez.

A termékkonfigurációs modelleket egy általános termékszerkezet megjelenítésére hozzák létre. Egy termékkonfigurációs modell beállítása után konfigurálhat egy egyedi termékváltozatot, amelynek egyedi anyagjegyzéke (BOM) és egyedi útvonala van. A termékkonfigurációs modellek a különböző termékváltozatok közti kapcsolatok és korlátozások kezeléséhez együttesen használnak deklaratív megszorításokat és imperatív számításokat. Konfigurálhatja a cikkeket az értékesítési rendeléseken, az értékesítési ajánlatokon, a beszerzési rendeléseken és a termelési rendeléseken. Az alábbi táblázat ismerteti a táblamegszorítás alapú szakkifejezéseket és fogalmakat.
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Összetevők</td>
<td>A termékkonfigurációs modell fő építőelemei az összetevők. Az összetevők a <strong>Megszorításon alapuló termékkonfigurációs modell adatai</strong> oldalon, fastruktúrában jelennek meg. Az összetevők a következő elemeket tartalmazhatják:
<ul>
<li>Attribútumok</li>
<li>Megszorítások</li>
<li>Számítások</li>
<li>Részösszetevők</li>
<li>Felhasználói követelmények</li>
<li>Anyagjegyzéksorok</li>
<li>Útvonalműveletek</li>
</ul></td>
</tr>
<tr class="even">
<td>Attribútumok</td>
<td>Az attribútumok ismertetik a termékkonfigurációs modell összes jellemzőjét. Az attribútumok segítségével adja meg egy egyedi termék konfigurálásakor választható jellemzőket. Az attribútumokat a megszorításokban és a feltételekben kell használni. Az attribútumok létrehozása és termékkonfigurációs modellhez való hozzáadása esetén a kapcsolódó attribútumtípusok hivatkozottak. Be lehet állítani egy attribútum alapértelmezett értékét. A termékkonfigurációs modell beállításánál a konfigurációs felhasználói felületen az alapértelmezett érték jelenik meg. Megadhatja, hogy az attribútum kötelező, írásvédett vagy rejtett legyen-e.
<ul>
<li><strong>Kötelező</strong> – Meg kell adni az attribútum értéket a termék konfigurálásánál.</li>
<li><strong>Csak olvasható</strong> – Az attribútum értéke megjelenik a konfigurációs munkamenet során, de nem módosítható.</li>
<li><strong>Rejtett</strong> – Az attribútum értéke szerepel a megszorításokban és a feltételekben, de nem jelenik meg a konfigurációs munkamenet során.</li>
</ul>
Egy feltételt is megadhat az attribútumokhoz. Ha a feltétel teljesül, meg kell adni a kötelező attribútum értékét. A feltételek olyan kifejezések, melyeknek teljesülniük kell az attribútumok, az AJ-sorok és az útvonalműveletek esetén, hogy azok bekerüljenek egy termékkonfigurációs modellbe. A feltételekben hivatkozott minden attribútum kötelezővé válik. Azt javasoljuk, hogy kötelezőnek jelölje be az attribútumokat az <strong>Attribútumok</strong> lapon. Ez megkönnyítheti a kötelező attribútumok azonosítását. Az attribútumértékek fontos részét képezik a konfigurációk újbóli használatának. A rendszer az attribútumok értékeinek segítségével állapítja meg, hogy létezik-e olyan konfiguráció, amely megfelel a felhasználó által a konfigurációs munkamenet során elvégzett beállításoknak.</td>
</tr>
<tr class="odd">
<td>Attribútumtípusok</td>
<td>Az attribútumtípusok határozzák meg a termékkonfigurációs modellben attribútumoknak használt adatok típusát. A következő attribútumtípusok használhatók:
<ul>
<li><strong>Egész</strong>, tartománnyal vagy anélkül</li>
<li><strong>Decimális</strong></li>
<li><strong>Szöveg</strong>, rögzített listával vagy anélkül</li>
<li><strong>Logikai</strong></li>
</ul>
Ha az attribútum típusa <strong>Logikai</strong>, tartományba eső <strong>Egész</strong> vagy rögzített listájú <strong>Szöveg</strong>, az értékek halmaza egy termékkonfigurációs modell beállításakor érhető el. <strong>Megjegyzés:</strong> A Termékkonfiguráció-feloldó csak a következő attribútumtípusokat ismeri fel: <strong>Logikai</strong>, rögzített listájú <strong>Szöveg</strong> valamint tartományba eső <strong>Egész</strong>. Ezért csak ezek az attribútumtípusok szerepelhetnek a kifejezések megszorításaiban és a feltételeiben.</td>
</tr>
<tr class="even">
<td>Megszorítások</td>
<td>A megszorítások írják le a termékmodell konfigurálásának korlátozásait. A megszorítások használata garantálja, hogy csak az érvényes értékeket lehessen kiválasztani a termék konfigurálása során. A megszorítások kifejezést vagy táblázatot korlátozhatnak:
<ul>
<li>A kifejezés megszorításai csak olyan összetevőnél használhatók, melyhez hozzá vannak kapcsolva. Egy összetevőre vonatkozó kifejezés megszorításai az összetevők részösszetevőinek attribútumaira is hivatkozhatnak. A megszorításokat a Termékkonfiguráció-feloldó oldja meg, megszorítások írásakor a feloldási szintaktikát kell használnia. További tudnivalók: lásd a kifejezésmegszorítások és táblamegszorítások témakörének hivatkozását.</li>
<li>A táblamegszorításokat a konfigurációs termékmodell összetevőire való alkalmazás előtt definiálni kell. A táblázatok megszorításai felhasználó által definiáltak vagy rendszer definiáltak is lehetnek. Egy táblázat felhasználó által definiált megszorítása egy olyan mátrix, mely az attribútumtípusok által definiált attribútumértékek kombinációinak halmaza leírására használható. Például hangszórók gyártása esetén a felhasználó által definiált táblamegszorításnál az oszlopok a hangszórók borítását és rácsát tartalmazhatják.</li>
</ul>
<strong>Példa</strong> A hangszórók négyféle borításban érhetőek el: Fekete, Tölgyfa, Rózsafa, Fehér. A hangszórók a három első rács egyikével rendelkezhetnek: fekete, fém vagy fehér. A fekete szín minden rácshoz elérhető, de a többi szín különleges rácsokra korlátozódik. Az alábbi táblázat egy példát mutat a <strong>Táblamegszorítás szerkesztése</strong> oldal <strong>Megengedett kombinációk</strong> lapján megjelenő információkra.
<table>
<thead>
<tr class="header">
<th>Hangszóró borítása</th>
<th>Elülső rács</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Fekete</td>
<td>Fekete</td>
</tr>
<tr class="even">
<td>Fekete</td>
<td>Fém</td>
</tr>
<tr class="odd">
<td>Fekete</td>
<td>Fehér</td>
</tr>
<tr class="even">
<td>Tölgyfa</td>
<td>Fekete</td>
</tr>
<tr class="odd">
<td>Rózsafa</td>
<td>Fehér</td>
</tr>
<tr class="even">
<td>Fehér</td>
<td>Fekete</td>
</tr>
<tr class="odd">
<td>Fehér</td>
<td>Fehér</td>
</tr>
</tbody>
</table>
Egy rendszer által definiált táblamegszorítás egy attribútumtípus és egy mező közötti leképezést jelöl egy Supply Chain Management táblában. Egy rendszer által meghatározott táblamegszorítás dinamikusan kapcsolja az attribútumtípust a mezőhöz. A kapcsolat lehetővé teszi, hogy egy termékkonfigurációs modell attribútuma a Supply Chain Management tábla mezőjének adatát mutassa.</td>
</tr>
<tr class="odd">
<td>Számítások</td>
<td>A számítások kiegészítik a megszorításokat. Számítások használatával aritmetikai műveleteket végezhet a <strong>Decimális</strong> és <strong>Egész</strong> típusú attribútumokon, vagy logikai műveleteket hajthat végre rögzített listájú <strong>Szöveg</strong> és <strong>Logikai</strong> típusú attribútumok bevonásával. Az egyes számítások célattribútummal rendelkeznek, amely a számítási kifejezés eredményét tárolja. A számítási kifejezés a kifejezésszerkesztő használatával építhető fel.</td>
</tr>
<tr class="even">
<td>Részösszetevők</td>
<td>A részösszetevők a termékkonfigurációs modell fastruktúráját tükrözik. A részösszetevők a termékkonfigurációs modell szerkezetének létrehozásához használhatók. A részösszetevők meglévő összetevőkre hivatkoznak. Emiatt a részösszetevők megkönnyítik az összetevők több termékkonfigurációs modellben való újrafelhasználását. Egy részösszetevőhöz tartozó <strong>Anyagjegyzéksor részletes adatai</strong> oldalon kiválaszthatja a részösszetevő egyedi értékét. Kiválaszthat egy attribútumot is, amelynek értékét a termékkonfigurációs modell beállításánál lehet megadni. Egy termék összetevőként vagy részösszetevőként való befoglalásához a következő adatokat kell megadnia a <strong>Termék létrehozása</strong> képernyőn, amikor létrehozza a terméket:
<ul>
<li>A <strong>Terméktípus</strong> mezőben válassza a <strong>Cikk</strong> lehetőséget.</li>
<li>A <strong>Termékaltípus</strong> mezőben válassza az <strong>Alaptermék</strong> lehetőséget.</li>
<li>A <strong>Konfigurációs technológia</strong> mezőben válassza a <strong>Megszorításon alapuló konfiguráció</strong> lehetőséget.</li>
</ul>
A <strong>Megjelent termék részletei</strong> oldal <strong>Általános</strong> lapján nézheti meg, hogy a kiadott termék használható-e összetevőként vagy részösszetevőként. Ha <strong>Megszorításon alapuló konfiguráció</strong> van kiválasztva a <strong>Konfigurációs technológia</strong> mezőben, a termék használható összetevőként vagy részösszetevőként. A részösszetevők elrejthetők, hogy azok ne jelenjenek meg a felhasználónak a konfigurációs munkamenet során. Az attribútumok, a részösszetevők és a részösszetevőkhöz kapcsolódó felhasználói követelmények is rejtve maradnak.</td>
</tr>
<tr class="odd">
<td>Felhasználói követelmények</td>
<td>A felhasználói követelmények a felhasználói követelmények, valamint bizonyos összetevők és attribútumok közötti absztrakcióját képviselik. Felhasználó követelmény nem rendelhető hozzá cikkhez. Például egy vevő házimozi rendszert szeretne vásárolni. Az értékesítő megkérdezheti a helyiség méretét, ahová a vevő a rendszert telepíteni tervezi annak meghatározásához, hogy hány wattra van szükség. Ebben a példában a szoba mérete lehet egy felhasználó követelmény, amely segít meghatározni egy adott összetevő attribútumának megfelelő értékét. A felhasználó követelmények elrejthetők, hogy azok ne jelenjenek meg a felhasználónak a konfigurációs munkamenet során. Az attribútumok, a részösszetevők és a felhasználói követelményhez kapcsolódó felhasználói követelmények is rejtve maradnak. Írhat egy olyan feltételt, mely ellenőrzi, hogy elrejthető-e egy felhasználó követelmény. A feltételt az Optimization Modeling Language (OML) szintaxisa alapján kell megírnia.</td>
</tr>
<tr class="even">
<td>Anyagjegyzéksorok</td>
<td>Az anyagjegyzéksorok az összetevők egyes anyagait jelenítik meg a termékkonfigurációs modellben. Az <strong>Anyagjegyzéksor részletes adatai</strong> oldalon bármely cikk kiválasztható. Az anyagjegyzéksorhoz feltétel adható, így az egyedi termékváltozathoz kijelölt anyagjegyzéksorok a felhasználó választása alapján változhatnak a termékkonfigurációs modell beállításakor. A feltételek olyan kifejezések, melyeknek teljesülniük kell az attribútumok, az AJ-sorok és az útvonalműveletek esetén, hogy azok bekerüljenek egy termékkonfigurációs modellbe. Az <strong>Anyagjegyzéksor részletes adatai</strong> oldalon kiválaszthat egy egyedi értéket. Hozzárendelhet egy attribútumot is, amelynek értékét a termékkonfigurációs modell beállításánál lehet megadni.</td>
</tr>
<tr class="odd">
<td>Útvonalműveletek</td>
<td>Az <strong>Útvonalművelet részletes adatai</strong> oldalon kiválaszthat egy egyedi értéket. Hozzárendelhet egy attribútumot is, amelynek értékét a termékkonfigurációs modell beállításánál lehet megadni. A feltételeket a kifejezésmegszorításokhoz hasonlóan kell megírni. A feltételek olyan kifejezések, melyeknek teljesülniük kell az attribútumok, az AJ-sorok és az útvonalműveletek esetén, hogy azok bekerüljenek egy termékkonfigurációs modellbe.</td>
</tr>
</tbody>
</table>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]