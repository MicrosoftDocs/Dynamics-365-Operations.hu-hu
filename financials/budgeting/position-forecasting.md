---
title: "Pozíció-előrejelzés"
description: 
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 64413
ms.assetid: 35e791d2-1905-4808-a579-7f181ddddd91
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 62dcc8a9b17ad044ac63080a94593a5f6ae2f182
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="position-forecasting"></a>Pozíció-előrejelzés

[!include[banner](../includes/banner.md)]




A dolgozókhoz kapcsolódó kiadások gyakran a szervezet költségeinek nagy részét alkotják. A pozíció-előrejelzés lehetővé teszi hogy megtervezze ezeket a költségeket, és beleszámolja őket költségvetések tervezetébe.

## <a name="position-forecasting-in-budget-planning"></a>Pozíció-előrejelzés a költségvetési tervben

[![Felső grafika](./media/graphic-top.png)](./media/graphic-top.png) 

A pozíció-előrejelzés három fő összetevőt használ, hogy pontos költségvetési mennyiségeket adjon meg a pozíció-kiadásokhoz. Ezeket az összegeket ezután egy költségvetési tervbe lehet összefoglalni a költségvetési számításokhoz. 

Az elsődleges összetevő az **előre jelzett beosztás**, amely az egy pozícióhoz kapcsolódó összes költségadatot megadja. Egy előre jelzett beosztás több változatát is létrehozhatja úgy, hogy egy másik költségvetési tervváltozatot rendel minden egyes verzióhoz. A különféle változatok lehetővé teszik a költségvetéshez való ismétlődésen alapuló megközelítést, és így több különféle feltételes kimenetelt hasonlíthat össze. Minden előre jelzett beosztás rendelkezik egy neki megfelelő pozícióval a Humán erőforrásoknál.

A **költségvetési költségösszetevő** egy beállítási komponens, amely egy bizonyos, beosztással kapcsolatos költség, mint például fizetési díjalap, munkáltató által fizetett egészségbiztosítás, mobiltelefon engedmények és így tovább. A költségvetési költségösszetevő tartalmazza a fő számlát, amely a költséghez és a számítási opciókhoz használatos. Minden költségvetési költségösszetevő több előre jelzett beosztáshoz rendelhető hozzá. 

A **kompenzációs csoport** opcionális beállítási komponens, amely olyan költségvetési költségösszetevők és fizetési számítások beosztásokra való alkalmazására használatos, amelyek hasonló fizetési tulajdonságokkal rendelkeznek. A kompenzációs csoporthoz tartozhat egy kompenzációs rács is, amely fizetési díjalapokat tartalmaz. Ha a csoport előre jelzett beosztáshoz van hozzárendelve, a szint és a lépés a rácsban hozzá tudja rendelni az előre jelzett beosztás bevételét. Néhány költségösszetevő automatikusan hozzáadódik.

### <a name="position-forecasting-processes"></a>Pozíció-előrejelzési folyamatok

[![graphic1b](./media/graphic1b.png)](./media/graphic1b.png) 

Egy jellemző beosztás-előrejelzési folyamatban először létre kell hozni a beállítási komponenseket (költségvetési költségösszetevők és kompenzációs csoportok). Az előre jelzett beosztások generálása a meglévő beosztások alapján. A helyesbítések ekkor elvégezhetők. Például hozzáadhat vagy bezárhat pozíciókat, megváltoztathatja a fizetési díjalapokat és hozzáadhat béremeléseket. Egy előre jelzett beosztás több változatát is létrehozhatja, hogy könnyebben össze lehessen hasonlítani a különböző költségvetési előrejelzéseket. Ezután beleveheti az előrejelzési pozíciókat a költségvetési tervekbe, és az előrejelzési pozíciókból átviheti az összegeket a költségvetésiterv-sorokba.

Létrehozhat további előre jelzett beosztásverziókat, ahogy a költségvetési terveket felülvizsgálja. Ezek az új verziók adják a felülvizsgálat alapját.

## <a name="position-forecasting-setup"></a>Pozíció-előrejelzés beállítása
[![graphic2](./media/graphic2-1024x327.png)](./media/graphic2.png)

### <a name="budget-cost-elements"></a>Költségvetési költségösszetevők

A költségvetési költségösszetevők előre jelzett beosztás költségrészleteinek meghatározására szolgálnak. Ezek az adatok tartalmazzák a költség típusát, hogy hogyan számoljuk ki a költséget, és azt, hogy a költség több dátumhoz van-e hozzárendelve, amikor az előre jelzett beosztás benne van a költségvetési tervben. 

Bizonyos mezők a költségvetési költségösszetevő elem viselkedését határozzák meg. Minden egyes költségvetési költségösszetevő hozzá van rendelve egy költségvetési költség típushoz a **Bevétel**, **Juttatás**, **Adók**, vagy **Más** lehetőségeknél. A költségvetési költségtípusok elsősorban az összesítések kiszámítására szolgálnak. Az **Előre jelzett beosztás felülírása** értékkel adható meg, hogy az összegek az elemen módosíthatók-e az előre jelzett beosztáson. A **Felosztási mód** mező akkor használatos, amikor egy előre jelzett beosztást hozzáad a költségvetési tervhez. A költségösszeget külön költségvetésiterv-sorokra oszthatja, amelyek a különböző dátumokkal rendelkeznek, havi, negyedéves, hetenkénti vagy kéthetenkénti alapon. Egy kezdő dátum kiválasztásával társítható a költség egyetlen összegként az előre jelzett beosztás kezdő dátumára. 

A költségvetési költségösszetevő költségelem költségösszegének számítása érvényességi dátumokat használ, hogy ugyanazt a költségelemet különböző időszakokban lehessen használni. Minden időszakhoz egy főszámla van hozzárendelve, egy százalékaránnyal vagy éves összeggel, amely jelzi a költség összegét. A költségvetési költségösszetevő más összegelemek százalékát vagy egy éves összeget használhat, de mindkettőt nem. Megadhatja egy éves korlátot is. 

Ha a költségösszetevő százalékon alapul, meg kell adnia a költségvetési költségösszetevőket, amelyeket a számítás alapjaként használt.

**Példa** 

Jodi szervezete egy alkalmazott fizetési díjalapjának 5 százalékát biztosítja képzési keretként. Jodi ehhez a költséghez szeretne létrehozni egy költségvetési költségösszetevőt. Létrehoz egy új költségvetési költségösszetevőt, és hozzárendeli a **Juttatás** költségvetési költségtípushoz.

Jodi nem szeretné, hogy a vezetők megváltoztassák a juttatás mennyiségét. Ezért tehát kiválasztja **Költségváltozások tiltása** lehetőséget a **Előre jelzett beosztás felülírása** mezőben. A szervezet azt szeretné, hogy ez a költség minden hónaphoz egyenlő módon legyen hozzárendelve. Ezért Jodi kiválasztja a **Negyedéves** opciót a **Felosztási mód** mezőben. 

Ezután Jodi hozzáad egy költségszámítási sort, beállítja a dátumokat és egy fő számlát és **5,00** értéket ad meg százalékként. Szervezete évi 5000 dolláros felső határral rendelkezik erre a juttatásra. Ezért Jodi ezt az összeget éves korlátként határozza meg. 

Végül a Jodi hozzáad minden kereseti költségösszetevőt, amelyek számítási alapként használatosak a fizetési díjalaphoz. Jodi költségvetési költségösszetevője készen áll a használatra.

### <a name="compensation-groups"></a>Kompenzációs csoportok

A kompenzációs csoportok a hasonló kompenzációs attribútumokkal rendelkező előre jelzett beosztások csoportosítására használhatók. Akkor is használhatók, ha az előre jelzett beosztás bevételeit és éves növekedéseit akarjuk definiálni, illetve ha közös költségvetési költségelemeket akarunk hozzárendelni. 

A kompenzációs csoportok alapvető funkciója, hogy költségvetési költségösszetevők együttesét rendelheti hozzá egy előre jelzett beosztáshoz. Emiatt kompenzációs csoportokat lehet használni közös költségek, például juttatási tervek és adók hozzáadásához. Egy vezetőnek, aki előre jelzett beosztást hoz létre, nem kell tudnia az összes hozzáadandó költségösszetevőről. Ehelyett a költségösszetevőket hozzá lehet adni, ha a kompenzációs csoport ki van jelölve. Az elemeket a kompenzációs csoport beállításához kell hozzáadni, a **Költségvetési költségösszetevők** lapon. 

A kompenzációs csoportok meghatározhatják egy előre jelzett beosztás bevételi arányait is.. Egy csoportot kell felállítania vagy óra, vagy éves fizetés alapján az előre jelzett beosztás bevételének kiszámítására. A **Kompenzációs díjtáblák** lapon a fizetési díjalapok kompenzációs rács határozza meg az előre jelzett beosztáshoz hozzáadott keresetet, hozzárendelt szint és lépés alapján. Ezek a rácsok alapulhatnak a Humán erőforrásokban meglévő kompenzációs rácsokon. Másik lehetőségként létrehozhat új kompenzációs rácsokat is a költségtervezéshez. 

Az érvényességi dátum és a lejárati dátumok a kompenzációs díjtáblákon lehetővé teszik, hogy tetszőleges időben módosítsa a fizetési díjalapokat. Ez a funkció akkor hasznos, ha egy szerződési egység mindenkire egyenlően vonatkozó növekedést tárgyalt ki a költségvetési ciklus közepén. Ebben az esetben a már létező tábla lejárati dátumát módosítjuk az árfolyam-módosítás időpontja előtti napra, és az új dátumon kezdődő új árfolyamtáblát veszünk fel. Amikor létrehoz egy új árfolyamtáblát, ha kiválasztja az **Új kompenzációs rács létrehozása egy meglévőből** lehetőséget, az emberi erőforrások készletéből közül választhat egy meglévő árfolyamtáblát. A létrehozott díjtáblában a **Tömeges módosítás** opció lehetővé teszi, hogy egy százalékos vagy fix összegű emelést vagy csökkenést alkalmazzon a rács összes díjalapjára. 

A **Növelési ütemezés** és a **Növelés dátuma** mezők a kompenzációs csoporton akkor használhatók, ha béremeléseket kell létrehozni, mivel a beosztások egy lépéssel a következőre lépnek. Az éves fizetésemelés erre tipikus példa. A növelési ütemezés határozza meg, hogy a beosztás évfordulója vagy egy közös dátum szolgál a lépcsőzetes növekedés alapjául. A növekedési ütemezés a kompenzációs csoportban szereplő összes előre jelzett beosztásra vonatkozik. 

A kompenzációs csoporton kijelölt kereseti költségösszetevőt akkor kell használni, ha a csoportban keresetet hoz létre az előre jelzett pozíciókhoz, beleértve az alapfizetést és a lépcsőzetes növekedést. A **Fix kompenzációs terv** mező a kompenzációs csoportot egy fix kompenzációs tervhez köti az Emberi erőforrások modulban. Ez a hivatkozás rendelheti hozzá egy dolgozó fix kompenzációs információit egy előre jelzett beosztáshoz, és így pontosabbá teheti a költségvetés tervezését. Ne feledje, hogy a kompenzációs rács (szintek és lépések) a kompenzációs csoportra vonatkozó szerkezete meg kell, hogy egyezzen a fix kompenzációs terv szerkezetével. Ellenkező esetben a rendszer nem tudja helyesen összekapcsolni a kompenzációs csoportot és a fix kompenzációs tervet.

## <a name="creating-forecast-positions"></a>Előre jelzett beosztások létrehozása
[![graphic3](./media/graphic3-1024x327.png)](./media/graphic3.png)

### <a name="creating-forecast-positions-for-existing-positions"></a>Előre jelzett beosztások létrehozása létező beosztásokhoz

A legpontosabb költségtervezési tervezés érdekében létrehozhat előre jelzett beosztásokat létező beosztásokból származó részletes adatok használatával a Microsoft Dynamics 365 for Operations rendszerben, függetlenül attól, hogy a beosztás jelenleg be van-e töltve vagy nem. 

A **Meglévő beosztások hozzáadása** funkció a szervezet minden beosztását megjeleníti. Az**Ekkor** dátum beállításával módosíthatja a beosztások listáját, hogy azokat beosztásokat tartalmazza, amelyek egy bizonyos napon a múltban vagy gyakoribb esetekben a jövőben (például a következő költségvetési ciklus elején) léteztek/léteznek. Válasszon ki egy költségvetés-tervezési folyamat és a költségvetési tervváltozatot, válasszon ki a listában szereplő beosztásokat, majd kattintson az **OK** gombra, így előre jelzett beosztásokat létrehozva a kiválasztott beosztások számára. Vegye figyelembe, hogy a költségvetés-tervezési folyamatban és tervváltozatban minden meglévő pozícióhoz csak egy előre jelzett beosztást hozhat létre. Azonban más költségvetési tervváltozatok hozzárendelésével további verziókat is létrehozhat. 

Ha költségvetési költségösszetevők lettek hozzárendelve a beosztáshoz az Emberi erőforrások modulban, ezek a költségvetési költségösszetevők az előre jelzett beosztáshoz is hozzá vannak rendelve és az alapértelmezett összegeket használják. A **Hozzárendelt dolgozó** mező az előre jelzett beosztáson arra a dolgozóra van beállítva, aki a beosztáshoz hozzá van rendelve, ha hozzá van rendelve egy dolgozó. Ez a mező egy egyszerű szövegmező. Nincs közvetlen kapcsolat létrehozva. 

Ha egy költségvetési költségösszetevő be van jelölve, a fix kompenzációs éves összeget a kiválasztott költségösszetevővel kell hozzárendelni az előre jelzett beosztáshoz, feltéve ha a hozzárendelt dolgozó fix kompenzációs tervvel rendelkezik. Ha a dolgozó nem rendelkezik egy rögzített komp tervvel, vagy ha nincs dolgozó hozzárendelve, az alapértelmezett összeg használatos a költségvetési költségösszetevőhöz. 

Ha a **Kompenzációs csoport hozzárendelése** beállítás az **Igen** lehetőségre van beállítva, ha a beosztáshoz hozzárendelt dolgozó egy kompenzációs csoporthoz kötött lépcsős fix kompenzációs tervvel rendelkezik (ahogyan már korábban kitértünk rá), a dolgozó szintje és lépcsője az előre jelzett beosztáshoz rendelődik hozzá, a kompenzációs csoporttal együtt. A kompenzációs csoportból származó kereseti költségvetési költség hozzáadódik az előre jelzett beosztáshoz és a kompenzációs csoportból származó szinten és lépcsőn lévő fizetési díjalap használatos. 

A **Kompenzációs csoport hozzárendelése** lehetőség beállítása elsőbbséget élvez a **Költségvetési költségösszetevő hozzárendelése** beállítással szemben. A két beállítás használható egyszerre. 

[![graphic4](./media/graphic4.png)](./media/graphic4.png) 

Egy másik lehetőség egy évforduló hozzárendelése. A kijelölt dátum (módosított kezdési dátum, a dolgozó kezdési dátuma, a foglalkoztatás kezdő dátuma vagy a szolgálati idő dátuma) a hozzárendelt dolgozótól az előre jelzett beosztás évfordulójaként lesz beállítva és tájékoztatásra szolgál a fizetésemelések létrehozásakor.

### <a name="creating-new-forecast-positions"></a>Új előre jelzett beosztások létrehozása

Új előre jelzett beosztások kétféleképpen hozhatók létre: egy meglévő előre jelzett beosztás másolásával, és egy teljesen új előre jelzett beosztás létrehozásával. 

Amikor egy előre jelzett beosztás be van jelölve, válassza a **Bejelölt előre jelzett beosztás másolása** lehetőséget egy új előre jelzett beosztás létrehozásához, amelynek az előre jelzett állapota **Tervezett**. Ennek az előre jelzett beosztásnak az összes adata megegyezik a lemásolt előre jelzett beosztás adataival, kivéve a hozzárendelt dolgozót és a költségvetési költségösszetevőkkel kapcsolatos esetleges megjegyzéseket. Vegye figyelembe, hogy a megfelelő új beosztás a Humán erőforrásokban is létrejön. Ez a beosztás az **Előrejelzés által létrehozva** leírást tartalmazza. 

Teljesen új előre jelzett beosztást is létrehozhat. Válasszon ki egy meglévő munkát, valamint a költségvetés-tervezési folyamatot és a költségvetési tervváltozatot. Ezután még további kívánt részleteket is megadhat. Az új beosztás ebben az esetben is létrejön a Humán erőforrások modulban is.

## <a name="working-with-forecast-positions"></a>Előre jelzett beosztásokkal való munka
[![graphic5](./media/graphic5-1024x327.png)](./media/graphic5.png)

### <a name="multiple-versions-of-a-forecast-position"></a>Az előre jelzett beosztás több verziója

Az előre jelzett beosztásokat módosíthatja vagy a költségvetési ciklus ismert változásainak alkalmazására, vagy javasolt módosítások modellezésére. Általános gyakorlat egy előre jelzett beosztások kiindulási csoportjának létrehozása, ezekből másolat készítése, majd a modellek különféle változások modellálására való alkalmazása. Ezek a példányok egy külön költségvetési tervváltozathoz vannak hozzárendelve, de mindaddig, amíg módosításokat nem eszközölünk, megegyeznek az eredeti előre jelzett beosztásokkal, amelyekről a másolat készült. Az eredeti példányok és másolatok ugyanazon a beosztáson osztoznak a Humán erőforrásokban. 

A **Másolás a tervváltozatba** funkció ezt a szolgáltatást biztosítja. Ne feledje, hogy minden egyes Humán erőforrás beosztásnak csak egy előre jelzett beosztása lehet minden egyes költségvetési tervváltozatban.

### <a name="modifying-forecast-positions"></a>Előre jelzett beosztások módosítása

Az előre jelzett beosztásokon végrehajtott módosítások ezekre az előre jelzett beosztásokra korlátozódnak. A módosítások nem befolyásolják a Humán erőforrásokban beosztásrekordokat. A legtöbb módosítás szintén az éppen szerkesztett az előre jelzett beosztásra vonatkozik. Más szóval a változások csak a hozzárendelt költségvetés-tervezési folyamatra és a költségvetési tervváltozatra vonatkoznak. Kivételnek minősülnek azok a mezőmódosítások, amelyeket a beosztásnál a rendszer megoszt a folyamatok és változatok között is. Ezek a mezők magukba foglalják az **Általános** lapon és a **Pénzügyi dimenziók** lapon található mezőket. A mezők változásakor az új értékek az összes költségvetés-tervezési esetben vonatkoznak a beosztásra. Ezért ezek a mezők lehetővé teszik, hogy az összes verziót gyorsan frissítse.

#### <a name="budget-cost-elements"></a>Költségvetési költségösszetevők

A költségvetési költségösszetevők adják a költségvetési tervek számára a fő információkat: a költségvetési összeget és a fő számlát. A költségvetési összeg az az összeg, amely egy előre jelzett beosztás tervbe vételekor el lesz küldve a költségvetési tervbe. A költségvetési összeg ki van számítva, és nem lehet közvetlenül módosítani. Ez az összeg vagy az éves összeg, vagy az éves összeg alapelemei alapján százalékosan kiszámolt érték (a költségvetési költségösszetevő beállításainak megfelelően). Ezután az összeg fel lesz szorozva az elem dátumtartományában lévő napok számával (kezdő dátum, záró dátum), és a **Teljes munkaidőssel egyenértékű** (FTE) értékkel is, az előre jelzett beosztásnál. 

Például egy költségvetési költségsorelem 2017. január 1. és 2017. június 30. között, amelynek éves összege 100 000, az FTE értéke **0,50** a következőképp lesz kiszámítva: 100 000 x (181 nap ÷ 365 nap) x 0,50 = 24.794,52. 

A költségvetési költségösszetevő sorokat újra kell számolni, ha megváltozik az FTE-érték az előre jelzett beosztásnál. A sorokat is újra kell számítani az aktiválási dátumok vagy a visszavonási dátumok változásakor. Ezeknek a dátumoknak a módosítása frissítést idézhet elő a költségvetési költségösszetevő kezdő és záró dátumaiban, amelyeknek az előre jelzett beosztás időszakán belül kell lenniük. Ha újraszámításra van szükség, az **Újraszámítás** gomb elérhetővé válik, és az „Újraszámolás szükséges” üzenet jelenik meg. Újraszámítás akkor is szükséges lehet, ha egy költségvetési költségösszetevőt ad hozzá vagy távolít el.

**Példa** 

A szervezet két lehetőséget fontolgat egy könyvelői beosztás költségeinek csökkentéséhez. Egy lehetőség a beosztás megszüntetése évközben. A másik lehetőség a beosztás átállítása részmunkaidőre az egész évre. Brad létrehozott egy előre jelzett beosztást a létező könyvelői beosztásra a kiindulási változatban. Ezt a kiindulási előre jelzett beosztást átmásolja az A változatba, a visszavonás dátumát május 31-re állítja be, és újraszámítja a költségeket. Ezután Brad a kiindulási előre jelzett beosztást a B változatba másolja, az FTE értéket **0,50** értékre módosítja, és újraszámol. Brad így három verzióval rendelkezik, amelyek mindegyikének megvan a saját összes költsége, amelyek hozzá vannak rendelve az opcióihoz.

#### <a name="assigning-a-compensation-group"></a>Kompenzációs csoport hozzárendelése

Amikor először hozzárendel egy kompenzációs csoportot egy előre jelzett beosztáshoz, az alapértelmezett költségvetési költségösszetevők a kompenzációs csoportból hozzáadódnak. Ha a költségösszetevők már hozzá vannak rendelve az előre jelzett beosztáshoz, akkor ezek a költségösszetevők maradnak. Ha egy kompenzációs csoport már hozzá van rendelve és módosul, a meglévő költségvetési költségösszetevők törlődnek, és a kompenzációs csoportnak megfelelően a készlet cserélődik. 

Amikor kiválaszt egy kompenzációs szintet és lépést, egy kereseti költségvetési költségösszetevő (a kompenzációs csoport meghatározása) adódik hozzá. Az éves összeg számítása a kiválasztott szint és lépcső értéke és a kompenzációs csoportban az éves órák (vagy éves fizetés esetén a teljes összeg a szinten és lépcsőn) alapján történik. Ez az összeg ismét a költségösszetevő sorának dátumtartományával és az előre jelzett beosztás FTE-értékével lesz kiszámítva.

#### <a name="generating-increases"></a>Emelések létrehozása

Éves emeléseket (naptári évenként egyet) automatikusan lehet létrehozni az előre jelzett beosztások számára, amelyekhez egylépéses kompenzációs csoport van hozzárendelve. Kattintson az **Emelés készítése** lehetőségre egy kereseti költségvetési költségösszetevő hozzáadásához a következő legmagasabb lépésnél. Az új kereseti költségvetési költségösszetevő kezdő dátuma a tervezett emelési dátum, amely az előre jelzett beosztáson jelenik meg. Ezt a dátumot a kompenzációs csoportból a következő két módszer egyikével állíthatja be. Ha a kompenzációs csoport növekedési ütemezése **Általános dátum** lehetőségre van állítva, a növekedés dátuma a kompenzációs csoporton szerepel. Ha a növekedési ütemezés az **Évforduló dátuma** lehetőségre van beállítva, az előre jelzett beosztáson az évforduló dátummezője használatos, és a költségvetési ciklus az évet látja el. Ha több naptári év szerepel egy költségvetési ciklusban, több emelés lesz hozzáadva. 

Az aktuális kereset költségvetési költségösszetevő záró dátuma a növekedési dátumot megelőző napra frissül. Az újraszámítási folyamat automatikusan működik az emelések létrehozásakor. Ezért nem kell manuálisan újraszámolnia. 

Ha másodszor rákattint az **Emelések készítése** lehetőségre, a folyamat újból futtatva lesz, de nem lesz több rekord hozzáadva. Naptári évenként csak egy emelés jön létre.

#### <a name="changes-from-other-pages"></a>Módosítások egyéb lapokról

Előre jelzett beosztások frissítései más területekről is származhatnak, például a költségvetési költségösszetevőből és a kompenzációs csoport beállítási oldalaiból. A tömeges frissítési eljárással is módosíthatja az előre jelzett beosztásokat. 

Két beállítás érhető el a**Költségvetési költségösszetevő** telepítőoldalán: **Hozzáadás beosztásokhoz** és **Beosztások frissítése**. A **Hozzáadás beosztásokhoz** opció kiválasztott előre jelzett beosztásokhoz adja hozzá a költségvetési költségösszetevőt. Ha az összetevő már hozzá van rendelve egy előre jelzett beosztáshoz, az előrejelzési pozíciót kihagyja a program. A **Beosztások frissítése** opció az aktuális értékeket alkalmazza (a fő számla, százalék, éves összeg, és így tovább) a kijelölt előre jelzett beosztásokra. 

Minden folyamathoz tartozik egy hasonló lap, ahol kiválaszthatja az előre jelzett beosztásokat. A **Hozzáadás beosztásokhoz** lap megmutatja az összes előrejelzési pozíciót, amelyek közül lehet választani, míg a **Beosztások frissítése** oldal csak azokat az előrejelzési pozíciókat mutatja, amelyek már rendelkeznek hozzárendelt költségvetési költségösszetevővel. (Tehát a **Beosztások frissítése** oldal lehetőséget nyújt arra, hogy megtudja, melyik előrejelzési pozícióhoz van már csatolva költségösszetevő.) Az előre jelzett beosztásokat áthelyezheti egy felső rácsból egy alsóbb rácsba, hogy belevegye őket a frissítésbe. 

Vegye figyelembe, hogy a **Dátumok módosítása** funkció a **Költségszámítás** lapon azonnal megváltoztatja a költségvetési költségösszetevő kezdő és záró dátumát az előre jelzett beosztásokon. Nincsenek választható opciók. 

A **Kompenzációs csoport** oldalon a **Beosztásdíjak frissítése** funkció az aktuális kompenzációs díjtáblázatokat alkalmazza a csoporthoz hozzárendelt előre jelzett beosztásokra. A díjak frissülnek, és további költségösszetevő-sorok adódnak hozzá az esetleges új díjtábla-sorok miatt (dátumok alapján). Azonban a költségvetési költségösszetevők és az emelési dátumok nem frissülnek. Választhat, hogy melyik költségvetés-tervezési folyamat és költségvetési tervváltozat frissüljön. Emiatt lehetséges az egyik változat frissítése és az egyéb helyzetek változatlanul hagyása az összehasonítás céljából. 

Előre jelzett beosztások kiválasztásával, majd a **Tömeges frissítés**opcióra kattintással egyszerre egynél több előre jelzett beosztás adható hozzá vagy módosítható. Több lehetőség érhető el: Egy beállítás a **Pénzügyi dimenziók** lapon egy kicsit különbözik a többitől és a költségvetési költségösszetevőkhöz kapcsolódik. Költségvetési költségösszetevők hozzáadhatók a **Költségvetési alapértékek** mező beállításával **Igen** lehetőségre. Ha nincs költségvetési költségösszetevő kiválasztva, de a **Költségvetési alapértékek** értéke **Igen**, minden költségvetési költségösszetevő, amely jelenleg hozzá van rendelve, törlődik. 

Az újraszámítási folyamat automatikusan végbemegy minden előre jelzett beosztásnál, amely módosult.

## <a name="bringing-forecast-positions-into-budget-plans"></a>Előre jelzett beosztások költségvetési tervekbe építése

[![graphic6](./media/graphic6-1024x327.png)](./media/graphic6.png)

Az előre jelzett beosztások létrehozásának és módosításának célja, hogy hozzáadjuk őket költségvetési tervekhez, hogy azok a lehető legpontosabb költségvetési mennyiségeket tartalmazzák. Kétféleképpen lehet előre jelzett beosztást költségvetési tervhez hozzáadni. A költségvetési terven vagy egy generáló vagy egy kiválasztó folyamat használható.

### <a name="generating-a-budget-plan-from-forecast-positions"></a>Költségvetési terv létrehozása előrejelzési pozíciók alapján

A **Költségvetési terv létrehozása előrejelzési pozíciók alapján** funkció létrehozza vagy frissíti a költségvetési terveket, így azok az előre jelzett beosztások költségvetési összegét és FTE-számolásait tartalmazzák. Az előre jelzett beosztás költségvetési összegei lesznek a költségvetési terv sorának összegei, és a pénzügyi dimenzió értékei és érvénybe lépési dátumai szerint vannak összesítve. Ez a létrehozó folyamat rendeli hozzá a az előre jelzett beosztást a költségvetési terv sorához. A beosztást úgy tudja megtekinteni, ha az előre jelzett beosztást sorként belefoglalja a költségvetési terv elrendezésébe, vagy a **Költségvetésiterv-sorok** lekérdezést használja. Ennek a hozzárendelésnek a kihagyásához állítsa be a **Beosztás belefoglalása a költségvetésiterv-sorba** lehetőséget **Nem** opcióra. 

Kiválaszthatja, hogy a költségvetési terv FTE változat tartalmazza a költségvetési tervben az FTE-k számát. Csak olyan mennyiségtípusú változatokat választhat ki, amelyek szerepelnek a cél költségvetési terv elrendezésében. Ha kiválaszt egy FTE-változatot, egy FTE fő számlát is meg kell adnia. A rendszer ezt a számlát használja a mennyiségalapú költségvetésiterv-sorok létrehozásához. 

A forrásban kiválasztott költségvetés-tervezési folyamat és költségvetési tervváltozat határozzák meg a célváltozat költségvetés-tervezési folyamatát és változatát. Mivel ezek a jellemzők az előre jelzett beosztásokhoz vannak hozzárendelve, azoknak szinkronban kell lenniük a költségvetési tervvel. Ezért ezek a jellemzők a célon nem szerkeszthetők. 

Más létrehozási folyamatoknál három művelet áll rendelkezésre:

-   **Új költségvetési terv létrehozása** – Új terv létrehozása, amely a **Cél** szakaszban kiválasztott jellemzőkkel rendelkezik.
-   **A meglévő költségvetési tervváltozat cseréje** – A cél költségvetési tervben minden adat törlése a kiválasztott költségvetési tervváltozatban és új sorok létrehozása, amelyek a kiválasztott előre jelzett beosztás adatait tartalmazzák.
-   A **Meglévő költségvetési tervváltozat frissítése, és új adatok hozzáfűzése** – A célterv meglévő sorainak frissítése a forrássoroknak megfelelő céltervben, és új sorok hozzáadása új adatok rögzítéséhez. Az összepárosítás a főkönyvi számlán, dátumon, költségvetési osztályon és egyéb értékeken alapul, mint például az előre jelzett beosztás. Minden, a forrás beosztásszámmal azonos beosztásszámot tartalmazó sor helyére a forrás új sorai kerülnek.

### <a name="selecting-forecast-positions"></a>Előrejelzési pozíciók kiválasztása

Előre jelzett beosztás költségvetési összegeket közvetlenül a költségvetési tervhez is hozzáadhat. Használja a **Beosztások hozzáadása** funkciót a költségvetésiterv-sorok felett a szerepeltetni kívánt előrejelzési pozíciók kiválasztásához. 

A költségvetési terv esetek, amelyeket forrásként választani lehet, a terv elrendezésében szereplő esetekre korlátozódnak. Egy beállítás használatával a **Cél** lapon meghatározhatja, hogy az FTE-eset és a fő számla elérhető legyen az FTE-számolások felvételéhez, de ne legyen szükséges. 

Ez a kiválasztási folyamat úgy viselkedik, mint a **Meglévő költségvetési tervváltozat frissítése és új adatok hozzáfűzése** opció egy létrehozási folyamatban. Az összes meglévő költségvetésiterv-sor, ahol az előre jelzett beosztás hozzá van adva, el lesz távolítva és új sorokkal lesz helyettesítve, az előre jelzett beosztás jelenlegi helyzete alapján.

#### <a name="date-options"></a>Dátumbeállítások

A létrehozási folyamat és a kiválasztási művelet esetében is a költségvetési költségösszetevő sorának kezdő dátuma határozza meg a megfelelő költségvetési terv sorának érvényességi dátumát. A **Felosztási módszer** mező a költségvetési költségösszetevő beállítási lapján határozza meg az elosztási módszert:

-   **Kezdő dátum** – A költségvetési költségösszetevő kezdési dátuma lesz a költségvetési terv sorának érvényességi dátuma.
-   **Havi** – A költségvetési összeg egyenletesen lesz elosztva a dátumtartomány hónapjainak számával, hogy egy olyan havi összeg jöjjön létre, amely minden hónap első napján lesz hozzárendelve. Ha az első időszak részhónap, az összeg az adott hónap azon napjainak száma által lesz meghatározva, amikor az adott hónapban aktív a költség, és az eredmény lesz hozzárendelve a kezdődátumhoz. Utolsó hónapra vonatkozó összeg a teljes költségvetési összeg és az összes többi hónap összege közötti különbség. Ezért egy kerekítés hatással lehet az utolsó hónap összegére.
-   **Negyedéves** – Ez a módszer megegyezik a **Havi** módszerrel, de a számítások három hónapos időszakokra vonatkoznak.
-   **Heti** – A logika hasonlít a **Havi** és a **Negyedéves** metódusok logikájára. A költségvetési összeg egyenletesen lesz elosztva a dátumtartomány heteinek számával, hogy egy olyan heti összeg jöjjön létre, amely minden hét első napján lesz hozzárendelve. Ha az első időszak részhét, az összeg az adott hét azon napjainak száma által lesz meghatározva, amikor az adott héten aktív a költség, és az eredmény lesz hozzárendelve a kezdődátumhoz. Utolsó hétre vonatkozó összeg a teljes költségvetési összeg és az összes többi hét összege közötti különbség. Ezért egy kerekítés hatással lehet az utolsó hét összegére.
-   **Kéthetes** – Ez a módszer megegyezik a **Heti** módszerrel, de a számítások kéthetes időszakokra vonatkoznak.

#### <a name="changing-budget-plan-lines-that-have-forecast-positions"></a>Az előre jelzett beosztásokkal rendelkező költségvetésiterv-sorok módosítása

A költségvetésiterv-sorok megjelenítik a költségvetési összegek forrását (az előre jelzett beosztás számát), de nincsenek összekapcsolva. Ezért az előre jelzett beosztás módosításai nem láthatók a költségvetésiterv-soron, és az előre jelzett beosztásban megjelennek a költségvetési terv sorának módosításai. Ha módosít egy előre jelzett beosztást, és szeretné, hogy a frissítések megjelenjenek költségvetési tervben, újra be kell vinnie a tervbe az előre jelzett beosztást. Ne feledje azonban, hogy ez a folyamat eltávolítja az összes olyan sort, amelyhez ez az előre jelzett beosztás hozzá van rendelve. Ezért az ezekben a sorokban végrehajtott összes módosítás törlődik. 

Ha meg akarja tekinteni, hogy mely költségvetési tervekben szerepel egy előre jelzett beosztás, akkor létrehozhatja az **Előre jelzett beosztások költségvetési terv szerint** jelentést. Másik lehetőség, hogy az előre jelzett beosztáson megnyitja a **Társított költségvetési tervek** adatterületet a tervek megtekintéséhez.




