---
title: Raktári munka ellenőrzése munkasablonok és helyutasítások használatával
description: A témakör ismerteti a munkasablonok és helyutasítások segítségével meghatározhatja, hogy hol és hogyan lehet munkavégzés a raktárban.
author: perlynne
manager: AnnBe
ms.date: 09/21/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocDirFailure, WHSLocDirHint, WHSLocDirTable, WHSLocDirTableUOM, WHSRFMenuItem, WHSWork, WHSWorkClass, WHSWorkPool, WHSWorkTemplateTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 72921
ms.assetid: 377ab8af-5b0c-4b5e-a387-06ac1e1820c0
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9a5292e88fe022482ab9c6c5a8f016745946988
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/24/2019
ms.locfileid: "2026934"
---
# <a name="control-warehouse-work-by-using-work-templates-and-location-directives"></a>Raktári munka ellenőrzése munkasablonok és helyutasítások használatával

[!include [banner](../includes/banner.md)]

A témakör ismerteti a munkasablonok és helyutasítások segítségével meghatározhatja, hogy hol és hogyan lehet munkavégzés a raktárban.

A Dynamics 365 Supply Chain Management programban beállított munkasablonok determinálják az utasításokat, amiket a raktári dolgozók a mobileszközeikre kapnak. Ezek határozzák meg a különböző raktári folyamatokat és feladatokat. A munkasablonok határozzák meg, hogy miként történik a munka minden egyes raktári folyamat esetében. A helyutasítás hozzárendelése a munkasablonhoz elősegíti, hogy a munka a raktárak meghatározott területein történjen.

## <a name="work-templates"></a>Munkasablonok
A **Munkasablonok** lapon megadhatja a műveleteket, amiket el kell végezni a raktárban. Általában a raktári műveletek két egymást követő műveletből állnak: egy raktári dolgozó felveszi az aktuális készletet az egyik helyen, majd lerakja a készletet egy másik helyen. 

A munkasablonok fejlécből és társított sorokból állnak. Minden munkasablon egy adott *Munkarendelés-típus*eleme. Számos munkarendelés-típushoz tartoznak forrásdokumentumok, mint például a beszerzési és értékesítési rendelések. Azonban más munkarendelési-típusok különböző raktári folyamatot képviselnek, például a ciklikus leltározás. A *Munkagyűjtő azonosító* segítségével a munkát csoportokba rendezheti. 

A munkafejléc-definíció beállításainak használatával lehet megállapítani, hogy mikor kell létrehozni az új munkákat. Például megadhatja a kitárolási sorok maximális számát, valamint a várható maximális kitárolási időt. Ezt követően ha az értékesítési rendeléshez szükséges munka meghaladja valamelyik értéket, a munka két részre lesz osztva. 

A munkasorok a munka feldolgozásához szükséges fizikai tevékenységnek felelnek meg. Például egy kimenő raktári folyamathoz tartozhat egy munkasor, ami a cikkek raktáron belüli felvételéről szól, valamint egy másik sor, ami a cikkek átmeneti területre való szállításáról szól. Lehet egy további sor a cikkek előkészítő területről való felvételéről, valamint még egy sor, a rakodási folyamat részeként, a cikkek teherautóra helyezéséről. Beállíthat *Utasításkód* értéket a munkasablon sorban. Az utasításkód egy helyutasításhoz kapcsolódik, ezáltal segít biztosítani, hogy a raktári munka a megfelelő helyen legyen feldolgozva a raktárban. 

Beállíthat egy lekérdezést, amivel szabályozza, hogy egy adott munkasablon mikor legyen használva. Például korlátozhatja, hogy egy adott sablon csak egy bizonyos raktárban legyen használható. Másik lehetőségként rendelkezhet több, a kimenő értékesítési rendelés feldolgozásához használatos sablonnal, az értékesítési forrástól függően. A rendszer a **Sorszám** mezőt használja, hogy meghatározza az elérhető munkasablonok sorrendjét. Ezért ha van egy adott lekérdezése egy adott munkasablonhoz, adjon neki alacsony sorozatszámot. Az a lekérdezés a többi, általánosabb lekérdezés előtt lesz kiértékelve. 

Egy munkafolyamat leállításához, vagy felfüggesztéséhez használhatja a **Munka leállítása** beállítást a munkasorból. Ebben az esetben a munkát végző dolgozónak nem kell végrehajtania a következő munkát a sorban. A következő lépéshez, az egyik dolgozónak ki kell választania a munkát újra. Elkülönítheti a feladatokat munkán belül, különböző *Munkaosztály-azonosító* használatával a munkasablon soraiban.

## <a name="location-directives"></a>Helyutasítások
A helyutasítások olyan szabályok, amik segítik a kitárolási és betárolási helyek meghatározását, készletmozgatás esetében. Például egy értékesítési rendelés tranzakciójába a helyutasítás azt határozza meg, ahol a cikkek kitárolása történik, valamint ahol a cikkeket betárolják. A helyutasítások fejlécből és társított sorokból állnak, valamint a **Helyutasítások** oldalon hozhatja létre őket. 

A fejlécben minden egyes helyutasításhoz társul egy *Munkarendelés típus*, amely megadja, hogy melyik készlet-tranzakció típushoz lesz használva az utasítás, mint például értékesítési rendelések, feltöltések vagy nyersanyag kitárolások. A *Munkatípus* meghatározza, hogy a helyutasítás kitároláshoz vagy betároláshoz lesz használva, vagy egyéb raktári folyamathoz, például leltárhoz vagy a készlet állapotának változtatásához. Ki kell töltenie a *Hely* és a *Raktár*mezőket. Az *Utasításkód*, amit a fejlécen ad meg, a helyutasítás egy vagy több munkasablonhoz rendelésére is használható. 

A munkasablonoknál beállíthat egy lekérdezést, ami meghatározza, hogy mikor legyen használva egy bizonyos helyutasítás. Például megadhatja, hogy ha elektronikus kereskedelem az értékesítési rendelés eredete, a készlet a raktár egy bizonyos területéről legyen felvéve. A rendszer a **Sorszám** mezőt használja, hogy meghatározza az elérhető helyutasítások sorrendjét. 

A helyutasítási sorok további korlátozásokat szabnak meg a helykeresés szabályaival kapcsolatban. Megadhat egy minimális és egy maximális mennyiséget, amire az utasítás vonatkozik, valamint megadhatja, hogy az utasítás csak egy adott készletegységre vonatkozzon. Például ha a mértékegység a raklap a raklapon található cikkeket adott helyre lehet vinni. Megadhatja azt is, hogy a mennyiség el lehet-e osztva több hely között. A helyutasítási műveletek fejléchez hasonlóan minden helyutasítás sorművelete rendelkezik egy sorszámmal, amely meghatározza a sorok értékelési sorrendjét. 

A helyutasítások rendelkeznek egy további részletességi szinttel, ez a: *helyutasítási műveletek*. Több helyutasítási műveletet is megadhat minden sornak. Még egyszer, a sorozatszám meghatározza a műveletek értékelésének sorrendjét. Ezen a szinten megadhat egy lekérdezést, hogy megadja, hogyan legyen megtalálva a legjobb hely a raktárban. Emellett használható előre definiált **Stratégia** beállítás, az optimális hely megtalálásához.

## <a name="location-directives-configuration-details"></a>Helyutasítások konfigurációs részletei 

 ### <a name="sequence-number"></a>Sorszám
 
Ez a szám megmutatja, hogyan történik a helyutasítás feldolgozása a kijelölt rendelés típusához. A menü  **Feljebb** és **Lejjebb** pontjaival módosítható.
 
 ### <a name="work-type"></a>Munka típusa
 
Ez a végrehajtandó munka típusa. A rendelkezésre álló munka típusa a készlet tranzakció típusán alapul, amelyet kiválasztott a **Munkarendelés típusa** mezőben.
-   **Betárolás** – A **Betárolással** azonos munkatípus azt jelenti, higy a helyutasítás megkeresi a legideálisabb helyet a készlet elhelyezésére vagy kikeresésére a rendszerbe érkező készlet esetében; a fogadás, termelés vagy a készlet módosításával. Fel lehet használni arra is, hogy definiáljon egy helyet egy köztes szinten vagy a végső öböl ajtó szállítási helyére.
-   **Betárolás** – A **Kitárolás** munkatípusa azt jelenti, hogy a raktár megkeresi a legideálisabb helyet a készlet fizikai lefoglalásához (munka létrehozása). A kitárolás még akkor is végrehajtható (a kitárolási munkasor bezárható), ha a munka nem fejeződött be. A felhasználó végrehajthatja a fizikai kitárolást, ami a kitárolás egy lépése. A felhasználó ezután megszakíthatja a folyamatot egy mobileszközről, és később befejezheti a munkát. Azonban a munkafejléc bezárása akkor történik meg, ha befejeződött a végső betárolás. 
-   **Számlálás, Kiigazítások, Egyéni, Készletállapot-változás, Azonosítótábla felépítése, nyomtatás, Állapotváltozás, Csomagolás beágyazott azonosítótáblákhoz** – Ezek nem használhatók a helyutasítások beállításakor. Ez egy enum, tehát nincs szűrés a munkafolyamat típusához. 

### <a name="directive-code"></a>Utasításkód

A munkasablon, illetve a feltöltési sablon társítása irányelv kódjának kiválasztása. Az **Utasításkód** képernyőn új kódokat hozhat létre, amelyeknek használata egy munkasablon-feltöltési sablon és egy helyutasítás közötti kapcsolatoknál használható. Ez használható arra is, hogy kapcsolatot hozzon létre bármely munkasablonsor és helyutasítás között (például az öböl ajtaja vagy egy köztes hely).

Ne feledje, hogy ha be van állítva kód, akkor a munka létrehozásakor a rendszer nem sorrendben keres rá a helyutasításra, hanem az utasítás kódja alapján. Ez azt jelenti, hogy pontosabban megadhatja, hogy milyen helysablont kell használni egy munkasablon adott lépéseként, például az anyagok előkészítése során. 

### <a name="site"></a>Telephely

A hely kötelező mező, mert a helymeghatározási irányelvnek szüksége van a helyre és a raktárra, amelyre érvényes. 

### <a name="warehouse"></a>Raktár

A raktár kötelező mező, mert a helymeghatározási irányelvnek szüksége van a helyre és a raktárra, amelyre érvényes.

### <a name="multiple-sku"></a>Több raktározási egység

Ez lehetővé teszi, hogy több raktározási egység (SKU) legyen egy helyen, például az öböl ajtajánál. **Több raktározási egység** kiválasztása esetén a betárolási hely megadása a munkában történik (ami várható), de csak több tétel betárolását képes kezelni (ha a munka különböző raktározási egységeket tartalmaz kitárolásra és betárolásra, és nem csak egy raktározási egységet betárolásra). Ha nem választja ki a **Több raktározási egység** elemet, akkor a betárolási hely csak akkor van megadva, ha a betárolásnál csak egyféle raktározási egység szerepel. Mindkét művelet használatához két sort kell megadnia; egyet a több raktározási egység bekapcsolásával és egyet a több raktározási egység kikapcsolásával. Ezeknek azonos szerkezettel és beállításokkal kell rendelkezniük. A betárolási műveletekhez olyan helyutasítások szükségesek, amelyek azonosak; még akkor is, ha Ön nem tesz különbséget az egy vagy több raktározási egység között munkaazonosítónál. Be kell állítania a kitárolást is, ha egynél több tétel szerepel a rendelésében.

### <a name="sequence-number"></a>Sorszám

Adja meg a sorrendet, ahogyan a helyutasítási sor feldolgozása történik a kijelölt munkatétel típusához. Szükség szerint módosíthatja a sorrendet a **Feljebb** és a **Lejjebb** lehetőség kiválasztásával.

### <a name="fromto-quantity"></a>„-tól/-ig” mennyiség

Ez lehetővé teszi a mennyiségtartományának megadását olyankor, amikor a középső-rács sorrendet kell kiválasztani. A „-tól/-ig” tartományt a megfelelő egységben adhatja meg.

### <a name="unit"></a>Egység

Megadhat egy minimális és egy maximális mennyiséget, amire az utasítás vonatkozik, valamint megadhatja, hogy az utasítás csak egy adott készletegységre vonatkozzon. A sor egység mezője csak a mennyiség értékelésénél használatos.

Amikor ellenőrzi, hogy a helyutasítássor alkalmazható-e, ez azon a mennyiségen alapul, amely a megfelelő egységben található, ami a helyutasítássorban meg van adva. Minden alkalommal, amikor a rendszer eléri a helyutasítás sorát, megpróbálja átalakítani a kereseti egységet a sorban meghatározott egységekkel. Ha a mértékegység-átváltás nem létezik, a következő sornál folytatódik. 

### <a name="locate-quantity"></a>Mennyiség megkeresése

Ezt az opciót csak a raktárba való berakodás/mennyiségmegkeresés során lehet használni. Csak a betárolási munkatípusnál használható. Az érvényes értékek:

-   **Azonosítótábla mennyisége** – Annak eldöntésekor, hogy a mennyiség a „-tól” és „-ig” tartományon belül van-e, használja a fogadott azonosítótáblán lévő mennyiséget.
-   **Egységekre bontott mennyiség** – Annak eldöntésekor, hogy a mennyiség a „-tól” és „-ig” tartományon belül van-e, használja az adott tranzakció során egységekre bontott mennyiséget.
-   **Fennmaradó mennyiség** – Annak eldöntésekor, hogy a mennyiség a „-tól” és „-ig” tartományon belül van-e, használja a jelenleg beadott beszerzési rendelésen még bevételezendő mennyiséget.
-   **Várható mennyiség** – Annak eldöntésekor, hogy a mennyiség a „-tól” és „-ig” tartományon belül van-e, használja a beszerzési rendelésen lévő összesített mennyiséget, tekintet nélkül az eddig befogadott mennyiségre.

### <a name="restrict-by-unit"></a>Korlátozás egység szerint

Ez lehetővé teszi, hogy egy helyutasítássor adott mértékegységre vagy több mértékegységre vonatkozzon. Ha egy mennyiség foglalásakor csak meghatározott raklapokról szeretne foglalni, akkor középső rács sorozata „PL”-re korlátozza az adott sorozatot, hogy a raklapnál kisebb egy mennyiség sem választja ki a sorozatot. Válassza ki a **Korlátozás egység szerint** pontot az egységek beállításához. A sort egynél több egységre is korlátozhatja. Ez csak a kitárolási típusú munkák helyutasításainál működik. 

### <a name="round-up-to-unit"></a>Felkerekítés egységre

Ez a mező együttműködik a **Korlátozás egység szerint** mezővel. Ha a **Korlátozás egység szerint** helyutasítás beállítása „mező”, akkor a **Felkerekítés egységre** elem azt jelzi, hogy a nyersanyag kitárolására vonatkozó utasításból generált munkát fel kell kerekítenie egy anyagkezelési egység többszörösére (ennek megadása a **Korlátozás egység szerint** beállításban történik). Ne feledje, hogy ez a módszer csak a nyersanyag kitárolásánál és csak a kitárolás típusú helyutasítások használatával működik.

### <a name="locate-packing-qty"></a>Csomagolási mennyiség keresése

Ha egy csomagolási mennyiség van meghatározva egy értékesítési rendelésen, átmozgatási rendelésen vagy termelési rendelésen keresztül, ez korlátozza a rendszert, hogy csak olyan helyeket válasszon ki, ahol a csomagolás mennyisége megtalálható. Ez csak a kitárolási típusú munkák helyutasításainál működik.

### <a name="allow-split"></a>Felosztás engedélyezése

Ez adja meg, hogy egy helyutasítás feloszthatja-e a beérkező vagy lefolgalt mennyiséget több raktár között, vagy a teljes mennyiségnek egy helyen kell lennie, illetve azt egyetlen helyen kell lefoglalni a munka létrehozásához. 

### <a name="sequence-number"></a>Sorszám

Ez a szám az a sorrend, ahogyan a helyutasítás feldolgozása történik a kijelölt munkatétel típusához. A sorrendet módosíthatja ha szükséges. Azonban legyen körültekintő a sorszámok használatakor, hiszen a feldolgozás mindig sorban történik. 

### <a name="name"></a>Név

Adja meg az új helyutasításművelet nevét. Győződjön meg róla, hogy specifikus, amikor megad egy nevet.

### <a name="fixed-location-usage"></a>Rögzített hely használata 

-   **Rögzített és nem rögzített helyek** – A helyutasítás minden helyet figyelembe vesz.
-   **Csak a termék rögzített helyei** – A helyutasítás csak a rögzített helyeket veszi figyelembe termékváltozatok esetén.
-   **Csak a termékváltozat rögzített helyei** – A helyutasítás csak a rögzített helyeket veszi figyelembe termékváltozatok esetén.

### <a name="allow-negative-inventory"></a>Negatív készlet engedélyezése

A bejelölésével engedélyezi a negatív készlet megadását a kiválasztott raktárhelyhez a helyutasításokban. 

### <a name="batch-enabled"></a>Kötegelt engedélyezve 

Jelölje be ezt a jelölőnégyzetet kötegstratégiák használatához az olyan cikkeknél, ahol engedélyezve van a köteg. Olyan sor elérésekor, ahol a **kötegelt engedélyezve** beállítás szerepel egy nem kötegelt cikknél, a folyamat folytatódik a következő műveletsorral. 

### <a name="strategy"></a>Stratégia

-   **Konszolidálás** – Ez a beállítás szerepel adott helyen lévő cikkek konszolidálására, amikor hasonló cikkek rendelkezésre állnak. Ez csak a betárolási típusú munkák helyutasításainál használható. A betárolás közös beállítása az első műveletsoron fog konszolidálódni, majd a második próbálkozás konszolidáció nélkül történik. A konszolidálás hatékonyabbá teszi a későbbi kitárolást.
-   **Csomagolási mennyiség egyeztetése** – Ez a beállítás segítségével győződjön meg róla, hogy egy kitárolási hely van-e a megadott csomagolási mennyiség. Ez csak a kitárolási típusú munkák helyutasításainál használható. 
-   **FEFO-köteg lefoglalása** – Stratégia a megadott készlet helyének a köteg lejárati dátuma alapján történő meghatározásására és köteglefoglalási célra történő felosztására szolgáló funkció. Ez a beállítás csak a köteg engedélyezett cikkek használhatja. Ez csak a kitárolási típusú munkák helyutasításánál használható. 
-   **Felkerekítés a teljes azonosítótáblára** – Ez a beállítás a azonosítótábla (at) mennyiséget ki kell választani a cikkekhez hozzárendelt egyeztetendő készletmennyiség Felkerekítés szolgál. Ezt a stratégiát csak a kitárolási típus helyutasításának feltöltésére használhatja. 
-   **Üres hely, amely nem rendelkezik bejövő munkával** – Ezt a stratégiát az üres helyek keresésére használja. A hely üresnek minősül, ha nincs fizikailag megjelenő készlete vagy bejövő munkája. Ezt a stratégiát csak a helyutasítási típusnál használhatja. 

### <a name="example-of-the-use-of-location-directives"></a>Példa a helyutasítás használatához

Ehhez a példához egy olyan beszerzési rendelési folyamatot veszünk alapul, ahol a helyutasításnak szabad területet kell találnia egy raktáron belül, azoknak a készletcikkeknek, amiket most regisztráltak a bevételezési területen. Először szabad kapacitást kell találnia a raktár területén, az aktuális készlet konszolidálásával. Ha a konszolidáció nem lehetséges, üres helyet kell találnia. 

Ebben az esetben két helyutasítási műveletet kell megadni. A sorozat első művelete a **Konszolidálás** stratégiája, a másodiknak az **Üres hely bejövő munka nélkül** stratégiáját használjuk. Hacsak nem ad meg műveletet a túlcsordulás kezelésére, két végkifejlet lehetséges akkor, ha nincs több kapacitása a raktárnak: a munka létrehozható, habár nem lesz hely meghatározva, vagy a munka-létrehozási folyamat sikertelenül zárul. Az eredményt a **Helyutasítási hibák** lap beállításai határozzák meg, ahol eldöntheti, hogy beállítja-e a **Munka leállítása, ha a helyutasítások sikertelenek** lehetőséget minden Munkarendelés-típushoz.
