---
title: "Év végi zárás"
description: "Ez a témakör a szükséges beállításokat és az év végi főkönyvi szoros folyamat futtatásához szükséges lépéseket ismerteti."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerClosingSheet
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 926ee087a0e0c4743f29315b1d82c7d37e95be28
ms.openlocfilehash: 22233cfa1df79076c8ea42f75ea309bac990d574
ms.lasthandoff: 03/31/2017


---

# <a name="year-end-close"></a>Év végi zárás

Ez a témakör a szükséges beállításokat és az év végi főkönyvi szoros folyamat futtatásához szükséges lépéseket ismerteti. 

A pénzügyi év végén az év végi feldolgozás lezárása nyitó egyenlegek átvitele az új év kell futtatni. A legtöbb szervezet több alkalommal futtathatja szoros végi. Először is kap az egyenlegek helyezi át az új pénzügyi év. Zárja be az év végi is majd újra kell futtatni, mint sok időre szükség, az egyenlegek helyesbítő tételeket az új pénzügyi év történő áthelyezése. 

Az év végi alatt zárja be a folyamatot, lehetséges, a létrehozott tranzakciók két típusa van. Egy nyitó tranzakció mindig jön létre, és a nyitó egyenlegük az új pénzügyi év létrehozásához használatos. A nyitó tranzakció mérleg főkönyvi számlaegyenlegeket jeleníti meg az új pénzügyi év, és a felhalmozott eredmény főkönyvi számla eredmény főkönyvi számlaegyenlegek az új pénzügyi év egyenlege. A záró tranzakció szükség ahhoz, hogy az eredmény nulla, a pénzügyi év zárható le számlaegyenleg jön létre.

## <a name="prepare-to-run-the-year-end-close"></a>Az év végi közel futtatásához
Mielőtt futtatná a szoros év végi, ellenőrzése a következő beállításait: 

A **Fő számla** lapon:

-   Ellenőrizze a **fő típusa** megfelelően minden fő számla van megadva. A fő számla típusa határozza meg, hogy a fő számla egyenlegének hozzák előre egy nyitóegyenleget, vagy a felhalmozott eredmény nyitóegyenlegének zárt a nyitó tranzakció szolgál.
-   A **fiókot** mező használható a fő számla egyenlegének átvitele egy új fő számla zárja be az év során. Az új fő számla szerepel a **fiókot** mezőben. Általában ez lesz a fő számla mérleg a fő számla inaktiválásra kerül, és egy új fő számla szolgál az új pénzügyi év.

A a **főkönyvi paraméterek** a lap **pénzügyi év zárása**:

-   A **év tranzakciók törlése zárja be a** kapcsolóval adhatja meg, hogy a rendszer által létrehozott nyitó tranzakció a közel előző év végi törli-e, ha az év végi közel futtassa újra. Ha ez a beállítás értéke **Igen**, a korábbi nyitó tranzakció törlődik, és egy új nyitó tranzakció a jelenlegi egyenlegek alapján jön létre. Ha ez a beállítás értéke **nem**, a korábbi nyitó tranzakció marad, és egy további nyitó tranzakció jön létre, helyezze át az egyenlegek előre az előző év végi lezárása után feladott tranzakciók módosítása.
-   A **záró tranzakciók létrehozása átvitel közben** kapcsolóval záró tranzakciók létrehozása a pénzügyi év, annak érdekében, hogy az eredménykimutatás számlák egyenlegeinek nullára zárható. Ha ez a beállítás értéke **Igen**, a nyitó tranzakciók és a záró tranzakció jön létre. Ha ez a beállítás értéke **nem**, csak a nyitó tranzakció jön létre az egyenlegek átvitele a következő pénzügyi évre. A nyereség és veszteség számlaegyenlegeknek az üzleti év végén maradnak.
-   A **a pénzügyi év állapotának átállítása véglegesen lezárt** beállítás segítségével állítsa be a pénzügyi év véglegesen lezárt állapot. Óvatosan ezt a beállítást, mert véglegesen lezárt állapotú összes időszak nem nyitható meg újra, az üzleti évre könyvel helyesbítések megelőzése. A legjobb gyakorlat kell kapcsolni ezt a **nem**.
-   A **bizonylat számát meg kell adni** kapcsolóval adja meg a bizonylatszámot szükség-e az év végi szoros feldolgozás futtatásakor. A legjobb megoldás csak egy bizonylatszám könnyen azonosítható a nyitó tranzakció.

A a **pénzügyi naptár** oldalon:

-   A következő pénzügyi évre az év végi közel futtatása előtt léteznie kell. A következő pénzügyi évre van szükség a nyitó egyenlegek létrehozása a nyitó időszakban.

A a **főkönyvi naptár** oldalon:

-   Választható lehetőség: Alatt lezárt üzleti évre vonatkozó minden pénzügyi időszak végén beállítható úgy, hogy **visszatartott** új tranzakciók bevitele megakadályozásához. Ha helyesbítő tételeket azonosítanak, On hold időszakok megnyitható könyvel helyesbítő tételeket, hogy akkor is, ha a Bezárás év végi már lefutott.

## <a name="define-year-end-close-templates"></a>Év végi szoros sablonok meghatározása
A rendszer beállítása után a közeli év végi futtatható. A a **év végi lezárása** lap, egy sablont kell meghatározni, az a csoport, amelyhez az év végi lezárása folyamat jogalanyok fog futni. A sablont felhasználja zárjon be minden év végén, de módosítható, ha a vállalat megváltozik. 

Először határozza meg a **csoport neve** sablont, és válassza ki a pénzügyi naptár. A csoport nevét meg kell határozni a jogi személyek csoportja.  Például a sablonokat is kell állítani alapján a földrajzi elhelyezkedés képezik, a létrehozott Észak-amerikai jogi személyek, EMEA jogi személyek és jogi személyek APAC külön csoportokat. 

Ezután a jogalanyok lehet hozzáadni a sablont. Jogi személyek hozzáadhatók egy szervezeti hierarchia kijelölésével vagy a jogi személy kijelölésével. Egy szervezeti hierarchia be van jelölve, ha csak jogi személyek a hierarchián belül, amelyek a kijelölt pénzügyi év bekerül a sablonba. Jogi személyek hozzáadása a sablon használatakor csak jogi személy ugyanazt a pénzügyi naptárat is adható. Ugyanazt a pénzügyi naptárat szükség, mert az év végi közel van a pénzügyi év, amelynek naptár naptár a működését. 

A jogi személyek a felvétele után határozza meg a felhalmozott eredmény nyitóegyenlegének fő számlák minden jogi személyhez. A **zárja be az előző év záró dátuma** mező frissül minden egyes futtatásakor az év végén közel a jogi személy. 

A **pénzügyi dimenzió** lap segítségével meghatározható, hogy mely dimenziók lesz a nyitó tranzakció. Ne feledje, hogy a definiálás alatt álló beállítások csak a kijelölt jogi személy szempontjából fontos a **jogi személyek** rács. A telepítő a rácsban minden jogi személyhez ismétlődnek. 

A **mérleg dimenziók át** segítségével meghatározható, hogy a pénzügyi dimenziók a mérlegszámlákra feladott tranzakciókat a nyitó tranzakció kell fenntartani. Értéket kell megadni a legjobb gyakorlat **Igen**. A **át a nyereség és veszteség dimenziók** segítségével meghatározható, hogy mely tranzakciók feladott nyereség és veszteség számlára a pénzügyi dimenziók átkerül a felhalmozott eredmény nyitóegyenlegének fő számla. Először azonosítsa a kijelölt jogi személy szempontjából fontos a pénzügyi dimenziók. Ide tartozik minden olyan pénzügyi dimenziók feladni az év során még akkor is, ha a pénzügyi dimenzió nem tartozik aktív számlastruktúrában. Ezután meg kell határozni minden egyes dimenzióra, vagy **egy közeli** vagy **zárja be az összes**.  Az alapértelmezett érték a **zárjon be minden**, amely megtartja az eredeti pénzügyi dimenzió feladott tranzakciók közötti értéket, és ezeket használja, a létrehozása a nyitó egyenlegének a visszatartottnyereség-számlát. Nyitó egyenlegek külön felhalmozott létrejön az egyes pénzügyi dimenzióértékek egyedi kombinációja. Ha **egy közeli** van jelölve, a pénzügyi dimenzió szerint könyvelt minden tranzakció lesz összegezve a nyitó egyenleg után mezőben megadott dimenzió érték a felhalmozott eredmény **szoros egyetlen**. Tegyük fel például, hogy a pénzügyi év összes tranzakció lett elküldve a fő számla - részleg számláinak szerkezetéről. A részleg a sablonon alapuló pénzügyi dimenzió **szoros egyetlen** van jelölve a beírt érték pedig 100. Ha a teljes bevétel, 200, 300 és 400 részlegek feladott összes tranzakció $100,000, egy nyitó egyenleg készült Retained eredmény – 100. Ha **egy közeli** és a pénzügyi dimenzió értéket üresen hagyja, minden tranzakciót könyvel felhalmozott éppen üres dimenzió értékkel rendelkező. 

A szoros év végi számla struktúrák nem csatlakozhat. Ennek oka, hogy a fiók struktúrák módosíthatja a pénzügyi év során, és nem mindig lehet megállapítani a vonatkozó számla szerkezete miatt ezeket a változtatásokat.  Nyitó tranzakciók létrehozásakor az egyenlegek lesz előbbre kell hozni a pénzügyi dimenziók az év vége szoros sablon meghatározottak szerint. A kezdő egyenlegek tételek már nem lehetnek pénzügyi dimenziók már nem érvényesek az aktuális számla szerkezet folyószámla szerkezete és szegmens kombinációkban. Ha a szervezet pénzügyi dimenzió zárni esetében a felhalmozott megszerzéséhez nyitó egyenleg, a pénzügyi dimenziót **szoros egyetlen**, és hagyja üresen a dimenzióérték.

## <a name="run-the-year-end-close-process"></a>Az év végi szoros folyamat futtatása
Az év végi szoros sablonok létrehozása után az év végi szoros folyamat kezdeményezte kiválasztása **futtatni a pénzügyi év** meg a műveletpanelen. Jelölje be az összes vagy egy jogi személy, amelynek az év végi futtatásához zárjuk be a sablon része. Ha a pénzügyi év első alkalommal fut az év végén bezárja, valószínűleg választja a jogi személyek esetében a jogi személyek nyitó egyenlegek létrehozása. Ha futtatjuk az év végi zárja be újra, csak a jogi személyek, amelynek helyesbítő tételeket könyvelte a folyamat futtatásához választhatja. 

Válassza ki a pénzügyi év, amely szeretné futtatni az év végi szoros feldolgozása ellen. Ha egynél több záró időszak áll rendelkezésre a pénzügyi év utolsó időszakáig az **időszak neve** a mező aktívvá válik, hogy melyik a záró tranzakciók záró időszakban választhat, ha van állítva a záró tranzakció létrehozásához. 

Adja meg a bizonylat száma, amelyek vagy nem lehet szükség, attól függően, a telepítő általában főkönyvi paraméterekben. Ugyanaz a bizonylatszám lesz az év végi szoros feldolgozása kijelölt jogi személyek számára. A bizonylatszámot nem jön létre egy számsorozatot használó. Adja meg a bizonylatszámot, a legjobb megoldás még akkor is, ha nem kötelező. Bizonylat számának megadásával megkönnyíti az új pénzügyi év a nyitó tranzakció található. Ha nincs meg a bizonylatszámot, akkor a bizonylat a nyitó tranzakció üres lesz. 

Ha szeretné a kijelölt pénzügyi évhez egy előző év végén közel fordított **visszavonás előző közel**, **Igen**. Zárja be az év végi sztorníroz a rendszer, de a folyamat bármikor futtathatja kell. Év végi zárja be, ha a **zárja be az előző év záró dátuma** nem lesz elérhető. 

Az év végi szoros alapértelmezett futtatását kötegelt módban. A folyamat futtatását kötegelt módban a felhasználó más tevékenységekkel való visszatéréshez a legjobb. Az év vége szoros folyamat befejezése után a **zárja be az előző év záró dátuma** a munkamenet dátuma frissül.

További tudnivalókért lásd: [zárja be a főkönyvi időszak végén](close-general-ledger-at-period-end.md).


