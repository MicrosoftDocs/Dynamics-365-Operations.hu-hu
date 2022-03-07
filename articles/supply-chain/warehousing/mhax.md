---
title: Anyagkezelési berendezések interfésze (MHAX)
description: Ez a témakör azt ismerteti, hogyan lehet beállítani az anyagkezelési berendezések interfészét (MHAX), hogy kapcsolódni tudjon a külső fizikai anyagkezelési (MH) rendszerekhez.
author: Mirzaab
ms.date: 03/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMHEParameters, WMHESubscription, WMHEQueueManagerWorkspace, WMHEInboundQueue, WMHEOutboundQueue
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-04
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 7e71ca2877effe671723be53e844e8401714038a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7565208"
---
# <a name="material-handling-equipment-interface-mhax"></a>Anyagkezelési berendezések interfésze (MHAX)

[!include [banner](../../includes/banner.md)]

Az *anyagkezelési berendezések interfészének* (MHAX) segítségével a külső fizikai anyagkezelési (MH) rendszereket egy olyan raktárhoz lehet csatlakoztatni, amelyet a Microsoft Dynamics 365 Supply Chain Management speciális raktárkezelése (WMS) kezel. A WMS és az MH rendszerek közötti interfész két várakozási sorból áll: egy a kimenő események (WMS – MH) és egy a bejövő események (MH – WMS) számára. A WMS rendszer a különféle munkalétrehozási és végrehajtási folyamatok során létrehozott munkasorok alapján hozza létre a kimenő eseményeket. Az MH rendszer ezután rendszeresen lekérdezi, hogy vannak-e új események a WMS rendszerben, és feldolgozza a válaszokat. Miután az MH rendszer befejezte az események kezelését a munkautasításoknak megfelelően, bejövő eseményeket, például munkasorok befejezését és rövid kitárolást küld.

Az alábbi ábra az MHAX-integráció használata során megjelenő különféle elemeket és a folyamatok sorrendjét mutatja be.

![MHAX-összetevők és interakciók.](media/mhax-components.png "MHAX-összetevők és interakciók")

Az előző példában látható műveletek magyarázata:

1. A munka létrehozása vagy a munka végrehajtása során a kimenő események a kimenő várakozási soron jönnek létre.
2. Az MH-berendezés csatlakozik az MH berendezésszolgáltatáshoz, lekérdezi az ahhoz kapcsolódó új eseményeket, és feldolgozza azokat.
3. Ha az MH-berendezések készen állnak a jelentés visszaküldésére, ismét csatlakozik a szolgáltatáshoz és bejövő eseményeket küld el. Ezeket az eseményeket a várakozásisor-feldolgozó azonnal feldolgozza.
4. A bejövő eseményadatok alapján előfordulhat, hogy a várakozásisor-feldolgozó meglévő munkát futtat, módosít vagy új munkát hoz létre.

## <a name="turn-on-the-mhax-feature"></a>Az MHAX funkció bekapcsolása

Az MHAX szolgáltatás használata előtt be kell kapcsolni annak funkcióját és konfigurációs kulcsát.

1. Lépjen a **Rendszerfelügyelet \> Munkaterületek \> Funkciókezelés** részre.
2. A **[Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** munkaterületen kapcsolja be az *Anyagkezelési berendezések interfésze* nevű szolgáltatást.
3. Állítsa a rendszert karbantartási módba a [Karbantartási mód](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md) alatt leírtak szerint.
4. Lépjen a **Rendszerfelügyelet \> Beállítás \> Licenckonfiguráció** elemre.
5. Bontsa ki a **Kereskedelem \> Raktár és szállításkezelés** lehetőséget, majd jelölje be az **Anyagkezelési berendezések interfésze** jelölőnégyzetét.
6. Kapcsolja ki a karbantartási módot a [Karbantartási mód](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md) alatt leírtak szerint.

## <a name="set-mhax-parameters"></a>A MHAX-paraméterek beállítása

A funkció konfigurálása érdekében néhány általános paramétert be kell állítania az **Anyagkezelési eszközök interfészének paraméterei** oldalon.

1. Lépjen az **Anyagkezelési berendezések interfésze \> Beállítás \> Anyagkezelési berendezések interfészének paraméterei** lehetőségre.
2. Az **Általános** lapon állítsa be a következő mezőket:

    - **Felhasználói azonosító** – válasszon ki egy dolgozót. Ennek a dolgozónak a segítségével futtathatja a bejövő várakozási soron feldolgozott összes munkaműveletet (kitárolások és betárolások).
    - **Bejövő üzenet azonosítójának engedélyezése** – ha ez a beállítás *Igen*, ismétlődő bejövő üzenetazonosító érkezése esetén a rendszer elutasítja az üzenetet, és egy hibaüzenet jelenik meg, jelezve, hogy az üzenet már létezik. Ha ez a beállítás *Nem*, az ismétlődő bejövő üzenetazonosítókat a rendszer engedélyezi.

3. A **Számsorozatok** lapon válassza ki azokat a rendszerszintű számsorozatokat, amelyek alapján egyedi azonosítókat kell létrehozni a bejövő várakozási sorok cikkei, a kimenő várakozási sorok cikkei és a munkasorpárok számára.

## <a name="outbound-events"></a>Kimenő események

A rendszer a munka létrehozása vagy a munka végrehajtása során meghatározott pontokon határozza meg, hogy generáljon-e kimenő eseményeket, hogy elküldje az MH rendszernek. Ha a raktári feldolgozás egy meghatározott pontjára be van állítva egy előfizetés, akkor a rendszer az előfizetés beállításainak megfelelően generálja az eseményt.

### <a name="structure-of-outbound-events"></a>Kimenő események szerkezete

Egy kimenő várakozási sor azonosítója minden kimenő eseményt egyedileg azonosít. A kimenő tranzakció típusa határozza meg az esemény típusát. Az eseményben a rendszer a raktár és az eseményt generáló előfizetés azonosítóját is rögzíti.

Az MH rendszerbe való adatátvitelhez a kimenő esemény 10 adatmezőt tartalmaz (**data01** és **data10** között). Ezek az adatmezők egy az egyhez (1:1) hozzárendelést tartalmaznak meglévő adatbázismezőkhöz. Pontosabban a munkasorok és a munkafejléctáblák mezőiből nyeri ki őket. A mezők szabadon kiválaszthatók. Ezeket az előfizetés létrehozásakor kell beállítani.

Azon 10 adatmező mellett, amelyek 1:1-hez hozzárendeléssel rendelkeznek a meglévő adatbázismezőkre, az esemény egy további adatmezőt is tartalmazhat, amit *hasznos adat* néven is ismernek. A mező tartalmát egy egyéni X++ kód generálja, amely *hasznosadat-generátorként* ismert. Minden használható hasznosadat-generátor be van állítva az előfizetésben.

Annak biztosítására, hogy az MH rendszer minden kimenő várakozásisor-azonosítót csak egyszer fogadjon, egy állapotmezővel megadhatja, hogy egy esemény készen áll-e a külső rendszernek való elküldése vagy már megtörtént-e az elküldés.

### <a name="outbound-queue-subscriptions"></a>Kimenő várakozási sor előfizetései

Az események létrehozása előtt be kell állítani egy előfizetést, amely eldönti, hogy az MHAX szolgáltatás létrehoz-e eseményeket, és ha igen, hogyan. A generált eseményeket a rendszer az előfizetés azonosítója alapján címkézi. Emiatt több MH rendszer tud ugyanahhoz a WMS rendszerhez kapcsolódni, ugyanakkor elkülönítik az eseményeket. Amikor az MHAX szolgáltatásból lekérdezik az új eseményeket, az események beolvasására rendelkezésre álló lehetőségek egyike az előfizetés.

Előfizetés létrehozásához használja az **Anyagkezelési berendezések interfésze \> Beállítás \> Előfizetések** lehetőséget. Minden előfizetésnél a következő paraméterek érhetők el:

- **Előfizetés azonosítója** – az előfizetést azonosító egyedi név.
- **Leírás** – Adja meg az előfizetés szöveges leírását.
- **Raktár** – meghatározott raktárak, amelyek alapján az eseményeket szűrni kell.
- **Kimenő tranzakciótípus** – az előfizetés által tartalmazott események típusa.
- **Hasznosadat-generátor** – választható kódkiterjesztés, amely további adatokat is megadhat a kimenő esemény **Hasznos adat** mezőjében.

Az egyes előfizetésekhez társítható lekérdezés. Ez a lekérdezés szűri a munkasorokat és a fejléceket, hogy tovább korlátozza azt a munkát, amely az előfizetést használja események generálására. Ha lekérdezést szeretne hozzáadni egy előfizetéshez, jelölje be a megfelelő előfizetéshez kapcsolódó **Lekérdezés futtatása** jelölőnégyzetet az **Előfizetések** lapon, majd válassza a **Lekérdezés szerkesztése** lehetőséget a műveleti ablaktáblán. Megjelenik a Supply Chain Management szokásos lekérdezéstervezője.

Ezenkívül az előfizetés egy *előfizetési hozzárendelést* is tartalmaz, amely szükség esetén a munkafejléc vagy a munkasor mezőit a kimenő esemény 10 szabad adatmezőjéhez rendeli hozzá. Ha információkat szeretne visszaküldeni az MHAX szolgáltatásnak, rendszerint a munkasor rekordazonosítóját vagy a *munkasorpárok azonosítóját*. (A munkasorpár azonosítója egy olyan új tulajdonság, amely lehetővé teszi a rendszer számára, hogy egyetlen visszáruparancsot használjon a ki- és berakodási sorok feldolgozásához.) A többi mező a használati esettől függ. Néhány példa a témakör későbbi részében található.

Előfizetési hozzárendelés beállításához válassza ki a kívánt előfizetést az **Előfizetések** oldalon, majd válassza ki az **Előfizetés hozzárendelése** lehetőséget a műveleti ablaktáblán. A megjelenő **Előfizetés hozzárendelése** párbeszédpanelen szükség esetén minden egyes elérhető adatmezőhöz társíthat egy táblát és egy mezőt.

### <a name="outbound-event-types"></a>Kimenő eseménytípusok

Ez a szakasz a rendelkezésre álló különböző eseménytípusokat írja le. (Az eseménytípusok más néven *tranzakciótípusok*.) Bemutatja azt is, hogy mikor hozták létre az egyes eseménytípusokat a WMS rendszerben.

#### <a name="work-creation-events"></a>Munkalétrehozási események

A munkalétrehozási események azután jönnek létre, hogy az alkalmazás létrehozta a munkát. Ez a viselkedés a legtöbb munkalétrehozási folyamatra vonatkozik, különösen a kitárolási és feltöltési munka létrehozására. Ha a munkát *Nyitott* állapotban hozták létre, az általában azt jelzi, hogy a munka futtatásra kész egy dolgozó számára, akkor létrejön egy munkalétrehozási esemény. Ezenkívül a program munkalétrehozási eseményeket generál alapvető áthelyezési munkához (nem pedig mozgatás sablon szerint), annak ellenére, hogy a munka nem nyitott munkaként jött létre.

Ennek a viselkedésnek az egyik fontos kivétele a ciklikus leltározási munka, amely jelenleg nem támogatott. Az MH rendszerben található leltárak kívül esnek az MHAX hatáskörén, és a leltárak eredményeit készletleltározási naplóba kell importálni.

A munka létrehozása után az MHAX szolgáltatás feldolgozza a létrehozott munkasorokat, és hozzárendel egy munkasorpár-azonosítót az egyes munkafejlécek generált munkasoraihoz. A cél az összes kiválasztott munkasor csoportosítása az egymást követő munkákkal egy munkasorpár-azonosító alá. (A csoportok a munkasablonok kirakodási/berakodási párjainak felelnek meg.) Ezzel a módszerrel egyetlen azonosító használható a kapcsolódó ki- és berakodási sorok munkabefejezésének jelentéséhez. A csoportosítási folyamat az első sortól indul, majd ugyanazzal az azonosítóval folytatja a munkát, amíg nem kap két egymást követő be- és kirakodási munkasort. A futtatási azonosító azon pár berakodási sorához van hozzárendelve. Ezt követően a pár kitárolási sorától kezdődően a rendszer új azonosítót használ. Ez a folyamat addig folytatódik, amíg fel nem dolgoz minden sort, amely a munkafejléchez tartozik.

A munkalétrehozási események különleges funkciója, ha a **Zárolt hullám** beállítás a munkafejlécben *Igen* beállítású, akkor a generált események állapota *Zárolva* lesz a szokásos *Kész* állapot helyett, amely az MH rendszernek való elküldésükkör használatos. A munkafejlécben a **Zárolt hullám** jelzője arra utal, hogy a munkafejléc még nem áll készen a dolgozók futtatására, például a befejezetlen feltöltési munka miatt. Ha törli a **Zárolt hullám** jelölőt, a rendszer feloldja a korábban létrehozott események zárolását, és elérhetővé válnak az MH rendszer számára a várakozási sorról való lekérésre.

#### <a name="work-initiation-events"></a>Munkakezdeményezési események

A munkakezdeményezési események akkor aktiválódnak, amikor a munka állapota a munka frissítése során *Nyitott* állapotról *Folyamatban* állapotúra változik.

#### <a name="work-completion-events"></a>Munkabefejezési események

A munkabefejezési események akkor aktiválódnak, amikor a munka állapota a munka frissítése során *Folyamatban* állapotról *Lezárva* állapotúra változik.

#### <a name="work-cancellation-events"></a>Munkavisszavonási események

A munkavisszavonási események akkor aktiválódnak, amikor a munka állapota a munka frissítése során a *Visszavonva* állapotot kivéve bármilyen állapotról *Visszavonva* állapotúra változik. Ezenkívül minden, a munkafejléchez kapcsolódó esemény törlődik az előfizetések várakozási soráról. Így a külső rendszerek nem tudják feldolgozni a nem kötelező eseményeket.

#### <a name="pickput-completion-events"></a>Ki-/betárolási befejezési események

A ki-/betárolási események akkor aktiválódnak, amikor a ki-/betárolási sor állapota a munkasor frissítése során *Folyamatban* állapotról *Lezárva* állapotúra változik.

### <a name="monitor-the-outbound-queue"></a>A kimenő várakozási sor ellenőrzése

A kimenő várakozási sor ellenőrzésére használja az **Anyagkezelési berendezések interfésze \> Közös \> Kimenő várakozási sor** lehetőséget. A **Kimenő várakozási sor** felsorolja a kimenő várakozási sor összes elemét és a várakozási sor állapotát. Válassza ki a várakozási sor egy elemét a részletek megtekintéséhez. Ezek közé tartozik a cikk tranzakciótípusa, a használt előfizetés és az egyes adatmezők értékei (**data01** és **data10** között), valamint a hasznos adat.

### <a name="clean-up-the-outbound-queue"></a>A kimenő várakozási sor tisztítása

A kimenő várakozási sor végül megtelik már elküldött cikkekkel. Ezeket a cikkeket az **Anyagkezelési berendezések interfésze \> Időszakos feladatok \> Tisztítás \> Kimenő várakozási sor tisztítása** elem használatával távolíthatja el.

## <a name="inbound-events"></a>Bejövő események

Ez a szakasz leírja, hogy milyen típusú bejövő eseményekről készít jelentést az MH rendszer a WMS rendszernek. Bemutatja azt is, hogy az adatokat az MH rendszernek kell szolgáltatnia, valamint hogy az egyes bejövő események mit tesznek a WMS rendszerben.

### <a name="structure-of-inbound-events"></a>Bejövő események szerkezete

Bejövő esemény beküldése esetén a külső rendszernek legfeljebb 10 paramétert (**data01** és **data10** között) kell rendelkezésre bocsátania a bejövő tranzakciótípus számára. Az opcionális ellenőrzés során meggyőződhet arról, hogy az MHAX szolgáltatás nem kapta meg ugyanazt a bejövő eseményt egynél többször. Az érvényesség-ellenőrzés engedélyezéséhez minden bejövő eseménynek egyedi üzenetazonosítóval kell rendelkeznie. Ha ismétlődő üzenetazonosítót kap, és a **Bejövő üzenet azonosítója** beállítás *Igen* értékre van állítva az **Anyagkezelési eszközök interfészének paraméterei** oldalon, a rendszer elutasítja az üzenetet. Egy hibaüzenet jelzi, hogy az üzenet már létezik.

A rendszer a bejövő adatmezőkön kívül egyedi bejövő várakozásisor-azonosítót rendel az eseményhez.

### <a name="inbound-event-types"></a>Bejövő eseménytípusok

Ez a szakasz a támogatott bejövő eseménytípusokat (tranzakciótípusokat) és a feldolgozandó eseményekhez szükséges adatokat ismerteti.

#### <a name="work-confirm-events"></a>Munkamegerősítési események

A munkamegerősítési eseményekhez a bejövő adatmezőkben a következő adatokat kell szerepeltetni:

- **data01** – a munkasorpár azonosítója.
- **data02** – a munkasor rekordazonosítója (`RecId` értéke).

    > [!NOTE]
    > *Vagy* a **data01** mezőnek *vagy* a **data02** mezőnek kötelező jelen lennie.

- **data03** – a kiválasztható azonosítótábla azonosítója.
- **data04** – a munkafejléc cél azonosítótábla azonosítója.

Ha meg van jelölve a munkasorpár azonosítója, a munkasorpár-azonosítóval megjelölt és *Nyitott* vagy *Folyamatban* állapotú kitárolási, betárolási vagy egyéni munkasorok futtatása egymás után történik. Ha meg van nyitva egy munkasor rekordazonosítója (`RecId` érték), a munkasornak *Nyitott* vagy *Folyamatban* állapotú ki kitárolási, betárolási vagy egyéni munkasornak kell lennie.

Az azonosítótáblával vezérelt helyekről származó kitárolási sorokhoz szükséges, hogy a **data03** megadja azt az azonosítótáblát, amelyből a kitárolás történik, tekintet nélkül arra, hogy a sorokat a munkasor rekordazonosítója vagy a munkasorpár azonosítója megjelöli-e. A **data04** mezőnek meg kell adnia a munkafejléc kitároláshoz szükséges cél azonosítótábláját.

A betárolási sorok nem fogadnak el további információkat. A futtatás alapja csak az aktuális munkasor helye és a munka cél azonosítótáblája. Ha a betárolást másik helyre kell tenni, módosítsa a munkasor helyét a témakör későbbi, [Események felülbírálása](#override-events) szakaszának leírása szerint.

Az egyéni munkasorok nem igényelnek (vagy támogatnak) további információkat a bejövő eseményben.

#### <a name="short-pick-events"></a>Rövid kitárolási események

A rövid kitárolási eseményekhez a bejövő adatmezőkben a következő adatokat kell szerepeltetni:

- **data02** – a munka rekordazonosítója (`RecId` értéke).
- **data03** – a kiválasztható azonosítótábla azonosítója.
- **data04** – A kitárolandó mennyiség.
- **data05** – a rövid kitárolás kivételkódja.
- **data06** – a munkafejléc cél azonosítótáblájának azonosítója.

> [!NOTE]
> A **data01** mező nem használható rövid kitárolási eseményekhez.

Ez az esemény hasonlít a munka visszaigazolási eseményére, de csak kitárolási sorokra vonatkozik.

#### <a name="override-events"></a><a id="override-events"></a>Események felülbírálása

Az események felülbírálásához a bejövő adatmezőkben a következő adatokat kell szerepeltetni:

- **data01** – a munka rekordazonosítója (`RecId` értéke).
- **data02** – az új helyazonosító.

A munkasor állapotának *Nyitott* vagy *Folyamatban* állapotúnak kell lennie, és az új helynek léteznie kell.

#### <a name="license-plate-receipt-events"></a>Azonosítótábla-bevételezési események

Az azonosítótábla-bevételezési eseményekhez a bejövő adatmezőkben a következő adatokat kell szerepeltetni:

- **data01** – a bevételezni kívánt bejövő azonosítótábla azonosítója.

A rendszer a **data01** mező értékeként átadott azonosítótábla alapján elvégez egy azonosítótábla- bevételezési műveletet.

### <a name="monitor-the-inbound-queue"></a>A bejövő várakozási sor ellenőrzése

A bejövő várakozási sor ellenőrzésére használja az **Anyagkezelési berendezések interfésze \> Közös \> Bejövő várakozási sor** lehetőséget. A **Bejövő várakozási sor** felsorolja a bejövő várakozási sor összes elemét és a várakozási sor állapotát. Válassza ki a várakozási sor egy elemét a részletek megtekintéséhez. Ezek közé tartozik a cikk tranzakciótípusa, az üzenetazonosító és az egyes adatmezők értékei (**data01** és **data10** között).

Ha hiba vagy más típusú naplóelem történt a bejövő események feldolgozása közben, akkor ellenőrizheti a naplót a műveleti ablaktáblán a **Hibanapló** kiválasztásával.

### <a name="inbound-event-processing"></a>Bejövő eseményfeldolgozás

A bejövő eseményeket a rendszer először az adatbázisba írja, majd azonnal (szinkronban) futtatja őket. Ha a feldolgozás során hiba történik, az esemény akkor is a várakozási sorba kerül, de az állapot *Hibás* lesz. A MHAX szolgáltatás hibaüzenetet küld az MH rendszernek, és menti a hibanaplót a bejövő eseményrekordban későbbi vizsgálat céljából.

A *Hibás* állapotú események később is feldolgozhatók, ha a hibát kijavították. Az újrafeldolgozáshoz kövesse az alábbi lépések egyikét:

- Lépjen az **Anyagkezelési berendezések interfésze \> Közös \> Bejövő várakozási sor** lehetőségre. Válassza ki a megfelelő bejövő várakozási sort, majd válassza az **Újrafeldolgozás** lehetőséget a műveleti ablaktáblán.
- Lépjen az **Anyagkezelési berendezések interfésze \> Közös \> Hibás bejövő várakozási sor újrafeldolgozása** lehetőségre. Megjelenik egy szabványos kötegelt feladat párbeszédpanelje. Itt beállíthat egy rekordszűrőt, és ütemezhet vagy futtathat egy kötegelt feladatot a várakozási sor újrafeldolgozásához.

A munkaműveletek (ki- és betárolások) futtatása azon dolgozó használatával történik, akit a **Felhasználói azonosító** mezőben választott ki az **Anyagkezelési berendezések interfészeinek paraméterei** oldalon választott ki.

### <a name="clean-up-the-inbound-queue"></a>A bejövő várakozási sor tisztítása

A bejövő várakozási sor végül megtelik már feldolgozott cikkekkel. Ezeket a cikkeket az **Anyagkezelési berendezések interfésze \> Időszakos feladatok \> Tisztítás \> Bejövő várakozási sor tisztítása** elem használatával távolíthatja el.

## <a name="get-a-quick-overview-by-using-the-queue-manager"></a>Gyors áttekintés a sorkezelő használatával

A bejövő és kimenő várakozási sorokhoz kapcsolódó valamennyi tevékenység gyors áttekintéséhez használja az **Anyagkezelési berendezések interfésze \> Munkaterületek \> Várakozásisor-kezelő** lehetőséget. A **Várakozásisor-kezelő** oldal olyan lap- és csempekészleteket tartalmaz, amelyek a várakozási sorok ellenőrzésére és felfedezésére használhatók. Hasznos hivatkozásokat is tartalmaz a témakörben említett legtöbb oldallal kapcsolatban.

## <a name="connect-to-the-mhax-service"></a>Csatlakozás a MHAX szolgáltatáshoz

A MHAX egyéni szolgáltatásként működik. Ezért SOAP- és REST-hívásokon keresztül érhető el. A SOAP- és REST-végpontok címei itt találhatók:

- **SOAP:** `https://base_environment_URL/soap/services/WMHEServices`
- **REST:** `https://base_environment_URL/api/services/WMHEServices/WMHEService`

## <a name="retrieve-messages-from-the-outbound-queue"></a>Üzenetek beolvasása a kimenő várakozási sorból

Az üzenetek kimenő várakozási sorból való beolvasásához használja a következő módszerek egyikét:

- Használja a `readOutboundSubscriptionQueue` lehetőséget az események előfizetési azonosító alapján történő beolvasásához.
- Használja a `readOutboundWarehouseQueue` lehetőséget az események eseménytípus és raktárazonosító alapján több előfizetésen keresztül történő beolvasásához.
