---
title: Rendelésteljesítés beállítása az üzletek esetében
description: Ez a témakör az üzletben való rendelésteljesítés beállításáról nyújt áttekintést.
author: rubencdelgado
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: rubendel
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 118517fe0d7208113bd361a0295ff00cacd14f3d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412768"
---
# <a name="set-up-order-fulfillment-for-stores"></a>Rendelésteljesítés beállítása az üzletek esetében

[!include [banner](includes/banner.md)]

## <a name="overview"></a>Áttekintés

Számos kiskereskedő szeretné optimalizálni a rendelésteljesítést a rendelések teljesítésének engedélyezésével az üzletek számára. A rendelésteljesítés az üzlet szintjén segíthet megkönnyíteni a túlkészletezési helyzeteket az egyes üzletek esetében, vagy logisztikai szempontból lehet szükség rá, amennyiben egy üzletnek extra kapacitása van, vagy a vevőhöz közelebb van szállítási távolság szempontjából. A szükséglet megoldása érdekében egy egységes rendelésteljesítési művelet érhető el pénztárban.

Az adott üzletben teljesítendő rendelésekél a rendelési fejlécben vagy a rendelés soraiban az üzlet raktára van hozzárendelve.

A rendelés teljesítése művelet a pénztárban egységes munkaterületet biztosít a pénztárban, amely a rendelések feldolgozására használható. Itt szerepel minden, a rendelés elfogadása, a megjelölése szállítottként vagy az üzleten belüli felvétel kezdeményezése.

## <a name="set-up-the-order-fulfillment-operation"></a>A rendelés teljesítési művelet beállítása

A rendelésteljesítés, [Művelet azonosítója 928](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-operations), használható az üzletben való rendelésteljesítés munkaterület elérésére a pénztárban.

Kövesse a [Művelet hozzáadása a gombrácshoz](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts) lépéseit annak a megadásához, hogy melyik paramétert kell használni a rendelésteljesítés meghívásakor a pénztárnál. Miután megadta a rendelésteljesítés műveleteket, alapértelmezés szerint a **Minden rendelés** van kiválasztva. Ha ez a paraméter van beállítva, a művelet felsorolja az aktuális üzletben teljesítésre váró összes rendeléssort. Ugyancsak rendelkezésre áll a **Szállítandó rendelések**, amely egy gombhoz rendelhető, és akkor használható, amikor a felhasználó csak az üzletből kiszállított rendeléseket szeretné megtekinteni. Végül rendelkezésre áll a **Rendelések átvételre** is. Amikor meghívják a pénztárnál, csak azokat a rendeléseket listázza, amelyeket az üzletben lehet átvenni. A különböző paraméterek különböző gombokhoz rendelhetők, többféle módot adva a felhasználónak a rendelésteljesítés megtekintésére.

### <a name="enable-users-to-access-order-fulfillment-at-the-point-of-sale"></a>A rendelésteljesítéshez való hozzáférés engedélyezése a felhasználók számára a pénztárnál.

A rendelés teljesítése művelet gyárilag nem rendelkezik saját engedéllyel, de a jövőben felhasználók fel használhatják a **Rendelés beolvasásának engedélyezése** engedélyt a művelet meghívásához a pénztárban.

Az üzlet szintjén egy beállítás érhető el annak a meghatározásához, hogy egy rendelési sort manuálisan el kell-e fogadni a pénztárból. Ha nincs beállítva ez a beállítás, a rendeléssorokat alapértelmezés szerint elfogadja a rendszer. Ha ez a beállítás be van kapcsolva, a felhasználóknak a pénztárnál rendelkezniük kell a **Rendelés elfogadásának engedélyezése** engedéllyel, hogy elfogadhassák a rendeléseket a pénztárból.

### <a name="enable-manual-order-acceptance"></a>Rendelés kézi elfogadásának engedélyezése

Alapértelmezés szerint az üzlethez társított rendeléssorok jelölése **Elfogadva**. Ez azt jelenti, hogy azt feltételezzük, hogy a kijelölt üzletből lesznek teljesítve, és a további hozzárendelés nem szükséges. Bizonyos esetekben a kiskereskedők manuálisan szeretnék elfogadni a rendeléseket, mielőtt teljesíthetővé válnának. Ha például egy üzlet hiányos személyzettel rendelkezik és nem tudja teljesíteni a rendeléseket, az üzletvezető csak annyi rendelést fogad el feldolgozására, amennyit egy adott napon megfelelően feldolgozhatónak tart. Amíg el nem fogadják a rendelést, a háttériroda módosítással hozzárendelheti egy másik üzlethez. Ezzel a módszerrel a rendeléselfogadás azt is lehetővé teszi, hogy jelezze, hogy egy rendelést elfogadott egy üzlet, teljesítve lesz.

Üzletben való átvétel rendelési sorai **Függő** megjelölésűek, és nem kell elfogadni őket.

A rendeléssorok manuális elfogadásának bekapcsolásához navigáljon a **Retail és Commerce** \> **Csatornák** \> **Áruházak** \> **Minden kiskereskedelmi üzlet** elemre. Válassza ki az üzletet, és kattintson az áruház-azonosítóra az áruház részletes adatainak megtekintéséhez. Kattintson a **Szerkesztés** lehetőségre. Az **Általános** gyorslapon keresse meg a **Rendelésteljesítés** alfejlécet, és módosítása a **Manuális elfogadás** beállítását **Nem** értékről **Igen** értékre.

### <a name="enable-reject-order-line-capability"></a>Rendeléssor elutasítása funkció engedélyezése

A pénztárnál a rendeléssorokat is lehet elutasítani. Egy rendeléssor elutasítása azt jelzi, hogy nem teljesítik az adott üzletben a rendelést, és visszaküldik a rendeléssort ismételt hozzárendeléshez egy másik üzlethez és raktárhoz. A rendeléssor elutasításának engedélyezését a **Rendelés elutasításának engedélyezése** engedéllyel lehet megtenni a dolgozóhoz társított pénztárengedély-csoportban. Egy sor elutasításakor a kiskereskedők kötelezővé teheti a dolgozóknak az elutasítás okának megadását. Ez az infókódokon keresztül érhető el, az **Inforkód tevékenysége** típus, **Rendelésteljesítés** infokódok használatával, és az infókód hozzárendelésével a **Rendeléssor elutasítása** elemhez a csatornához társított funkcióprofilban.

> [!NOTE]
> Csak az **Infokód tevékenysége** típusú **Rendelésteljesítés** infókódokat lehet hozzárendelni a **Rendeléssor elutasítása** művelethez.

### <a name="synchronize-changes-to-the-channel-database"></a>A csatorna-adatbázist érintő módosítások szinkronizálása

Miután a művelet hozzá lett rendelve egy gombrácshoz, megtörtént a megfelelő engedélyek hozzárendelése, és a csatorna konfigurálása, a módosításokat szinkronizálni kell a csatorna-adatbázissal. Ehhez navigáljon a **Kiskereskedelem és kereskedelem** \> **Kiskereskedelem és kereskedelem informatika** \> **Elosztási ütemezés** pontra. Válassza az „1090-Registers” lehetőséget a gombrácsmódosítások szinkronizálásához, és kattintson a **Futtatás most** elemre. Ezután szinkronizálja az engedélyváltozásokat a „1060-Staff” kiválasztásával, és a **Futtatás most** elemre kattintással. Ezután szinkronizálja a csatornaváltozásokat a „1070-Channel configuration” kiválasztásával, és a **Futtatás most** elemre kattintással. Végül szinkronizálja az elutasítás okához újonnan létrehozott infókódot az „1110-Global configuration” kiválasztásával, majd kattintson **Futtatás most** elemre.

## <a name="use-order-fulfillment-at-the-point-of-sale"></a>Rendelésteljesítés használata a pénztárnál

Nyissa meg a pénztárat, és válassza ki a rendelés teljesítése műveletet. A konfigurációtól függően az összes rendelési sor, illetve az átvételre váró vagy a szállításra váró rendelési sorok jelennek meg.

### <a name="order-fulfillment-view"></a>Rendelésteljesítés nézet

A rendelésteljesítés nézetben az üzletben való teljesítés rendeléssorai jelennek meg, és a következő oszlopokat tartalmazza:

- Rendelés száma
- Termékszám
- Leírás
- Megrendelt mennyiség
- Kért szállítási dátum
- Vevő neve
- Teljesítési állapot

Egy adott rendeléssorhoz tartozó további információk megtekintéséhez jelölje ki a rendelési sort, és nyissa meg az úszó menüt, amely közvetlenül a bejelentkezett felhasználó/műszakinformációk alatt jelenik meg a pénztár fejlécében. Ez a menü 2 lapot tartalmazza: egyet a sor részletes adatainak, és egy másikat a rendelés adatainak. A sor részletei lap a következő információkat tartalmazza:

- Megrendelt mennyiség
- Fennmaradó mennyiség, amely szállításra/átvételre vár
- Kitárolt mennyiség
- Csomagolt mennyiség
- Számlázott mennyiség (már átvett vagy leszállított)
- Szállítás módja
- Szállítási cím

A részletek úszó menünek van még egy lapja, amely még több rendelésszintű részletet tartalmaz, többek között:

- Vevő neve
- Vevő azonosítója
- Rendelés száma
- Rendelés összesen
- Rendelésegyenleg

A rendelésteljesítési nézet alján egy műveleti ablak található. Ez tartalmaz minden műveletet, amelyet a rendelési soron végre lehet hajtani. Ha egy művelet nem áll rendelkezésre a sor állapota alapján, a művelet nem lesz elérhető.

Alapértelmezés szerint a rendelések állapota **Elfogadott** lesz. A rendelés állapota oszlopként tekinthető meg a rendelési sorok listájában. Ha a **Manuális elfogadás** van beállítva a csatorna szintjén, az összes szállításra váró sor **Függőben** megjelöléssel jelenik meg, és el kell fogadnia őket, mielőtt teljesíthetők lennének. Az üzletben való átvétele váró rendelések alapértelmezés szerint **Függőben** állapotúak, és nem kell elfogadni őket.

### <a name="order-fulfillment-line-actions"></a>Rendelésteljesítési sortevékenységek

- **Szerkesztés** – Ha egy rendelés állapota függőben, akkor szükség esetén módosítható pénztárnál. A már részlegesen kitárolt, csomagolt vagy számlázott rendelések nem szerkeszthetők a rendelésteljesítési nézetből.
- **Elfogadás** – Ha a **Manuális elfogadás** van konfigurálva a csatorna szintjén, a sorokat először el kell fogadni, mielőtt végighaladhatnának a rendelésteljesítési folyamaton.
- **Kitárolás** – A kitárolási beállítás több műveletet is támogat. Először, a **Kitárolás** frissíti a rendelési sor állapotát, hogy mások az üzletben ne próbálják meg kitárolni ugyanazt a sort. Ezt követően a **Kitárolási lista nyomtatása** kinyomtatja a kijelölt sor vagy sorok a kitárolási listáját, és frissíti az állapotukat a **Kitárolásba**. A kitárolási listaformátumok a nyugtaformátumok részeként vannak szabályozva. A nyugtaprofilok beállítási módjával kapcsolatos további tudnivalókat lásd: [Nyugta minták és nyomtatás](https://docs.microsoft.com/dynamics365/unified-operations/retail/receipt-templates-printing). Végül a **Megjelölés kitároltként** azt jelzi, hogy a sor ki van tárolva. A **Megjelölés kitároltként** kezdeményezi a megfelelő háttérirodai készlettranzakciókat. A kitárolási műveletek egyszerre több rendelés rendelési soraira, illetve az összes szállítási módra nézve elvégezhetők.
- **Elutasítás** – A sorokat vagy a részleges sorokat el lehet utasítani. Ez lehetővé teszi a társítás megváltoztatását a háttérirodáról egy másik üzletre vagy raktárra. A sorok csak akkor utasíthatók el, ha még nem lettek felvéve vagy csomagolva. Az olyan sorok elutasításához, amelyet már felvettek vagy csomagoltak, a háttérirodából kell visszavonni a felvételt vagy a csomagolást.
- **Csomag** – A csomag beállítás két műveletet támogat: a **Szállítólevél nyomtatása** szállítólevelet nyomtat ki a kiválasztott sorokhoz, a **Megjelölés csomagoltként** pedig megjelöli a sorokat csomagoltként, és a sorokat kiszállítottként jelöli meg a háttérirodában. Csak az ugyanazon rendeléshez tartozó és ugyanolyan szállítási módú sorokat lehet egyszerre csomagolni. A szállítólevél-formátumok a nyugtaformátumok részeként vannak szabályozva. A nyugtaprofilok beállítási módjával kapcsolatos további tudnivalókat lásd: [Nyugta minták és nyomtatás](https://docs.microsoft.com/dynamics365/unified-operations/retail/receipt-templates-printing).
- **Szállítás** – A szállítási művelet megjelöli a kijelölt sorokat **Szállítva** állapottal a háttérirodában. Miután a sort teljes egészében kiszállították, többé már nem jelenik meg a megrendelés teljesítési nézetében.
- **Átvétel** – Az átvételi művelet hozzáadja a sorokat a tranzakciónézethez átvételre. Ha vannak olyan egyéb sorok a rendelésen, amelyeket jelenleg nem vesznek át, ezek nulla mennyiséggel adódnak hozzá a tranzakciónézethez. Miután a sort teljes egészében átvették, többé már nem jelenik meg a rendelésteljesítési nézetében.

### <a name="order-fulfillment-filtering"></a>Rendelésteljesítés szűrése

A rendelésteljesítés a pénztárban magában foglalja a szűrés lehetőségét, segítséget nyújtva a felhasználónak ahhoz, hogy könnyen megtalálja azt, amire szüksége van. A szűrőket a **Pénztár** képernyő alsó részén lehet módosítani a műveleti ablaktáblán. Alapértelmezés szerint a **Szállítás típusa** szűrő van alkalmazva, attól függően, hogy hogyan van beállítva a működés. Ha a működés a **Minden rendelés** paraméterrel van beállítva, akkor a rendszer ezt a szűrőt alkalmazza a rendelésteljesítés megnyitásakor. Ugyanez vonatkozik az **Átvétel az üzletben** és a **Szállítás az üzletből** paraméterekre is. A rendelésteljesítés nézetre a következő egyéb szűrőket lehet alkalmazni:

- Vevőszám
- Vevő neve
- Vevő e-mail címe
- Rendelés száma
- Szállítás módja
- Bevételezési szám
- Csatornahivatkozás azonosítója
- Kiindulási üzletszám
- Sor állapota
- Létrehozás dátuma
- Szállítási időpont
- Kézhezvételi dátum


[!INCLUDE[footer-include](../includes/footer-banner.md)]