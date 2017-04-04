---
title: "Munkalebontási struktúrák"
description: 
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ProjWorkBreakdownStructure
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 23861
ms.assetid: 241a0464-0056-4a69-b468-0afbe2d5f3ae
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 1666691ec122e65128b74056817a0c40551f49b5
ms.lasthandoff: 03/31/2017


---

# <a name="work-breakdown-structures"></a>Munkalebontási struktúrák



Munkalebontási struktúrák A munkalebontási struktúra (WBS), a projektben elvégzendő munka leírása. Ez egy feladatokból álló hierarchia, amely a projektcsapat munka-összeállításra vonatkozó elképzeléseit tükrözi, és az egyes komponensek és feladatok méretét, költségét és időtartamát. A WBS-nek három fő célja van:

-   A munka lebontásának vagy összeállításának leírása feladatokban.
-   A projektmunka ütemezése.
-   Minden egyes feladat költségének becslése.

A WBS részletességének mértéke attól függ, hogy milyen mértékű pontosság szükséges a becslésekben, és hogy milyen szintű nyomon követés szükséges ezen becslések figyelembevételével. Azoknál a projekteknél, melyek fokozottan ütemterv- vagy költségérzékenyek, részletesebb WBS-re van szükség, valamint arra, hogy a munka előrehaladása és WBS-hez viszonyított tényleges költségei folyamatosan figyelemmel legyenek kísérve. Az ilyen típusú projekt általában az építőiparban és mérnöki ágazatban gyakori. 

Ezzel szemben a média- és reklámiparban, illetve a szoftverekkel és informatikai infrastruktúrával foglalkozó ágazatokban futó projektek mindig egyediek, ezért a termelékenység relatív a feladatot elvégző személy tapasztalatához és kompetenciájához képest. Ezért ezek az ágazatok egy munkalebontási struktúrát (WBS) használnak ahhoz, hogy megközelítőleg megkapják a projekt értékét, és ezt nem a projekt előrehaladásának részletes nyomon követéséhez használják. 

A munkalebontási struktúra (WBS) létrehozása időigényes folyamat, amely általában hosszabb időt vesz igénybe, és amelyhez sok személy együttműködése és a tőlük érkező információk szükségesek. Ez a témakör leírja a használatát WBS továbbfejlesztett Microsoft Dynamics 365 műveletek becslések és nyomon követési igényeinek.

## <a name="prerequisites-for-creating-a-wbs"></a>A WBS létrehozásának előfeltételei
A WBS létrehozásához létre kell hoznia egy munkaütemezést és meg kell becsülnie a munka költségeit.

### <a name="prerequisites-for-creating-a-work-schedule"></a>Munkaütemezés létrehozásának előfeltételei

A WBS-szolgáltatások teljes ütemezési szolgáltatásait használja, hajtsa végre a következő beállítást:

1.  Alapértelmezett naptár és egy projektnaptár beállítása:
    1.  Kattintson a **projekt igazgatási és számviteli**&gt;**a telepítő**&gt;**ütemezés**. Az **Alapértelmezett Munkanaptár** mezőben adja meg az alapértelmezett naptárt. Ez lesz az alapértelmezett munkanaptár minden új projekt létrehozásakor.
    2.  A konkrét projekteknél lehetősége van módosítani az alapértelmezett naptárat. Kattintson a projekt részletes adatainak lapjára, majd a **Projektcsapat és ütemezés** gyorslapon frissítse az **Ütemezési naptár** mezőt úgy, hogy válasszon ki egy másik naptárat.

2.  Állítsa be a normál munkanapokat és munkaórákat. A projekt számára munkanaptárként beállított naptárat a WBS következő információk meghatározására használja:

-   Munkanapok és ünnepek
-   A napi munkaórák száma

A munkanapok és a munkaidő naptár beállítása, vagy új naptár létrehozásához kattintson a **szervezet felügyelete**&gt;**közös**&gt;**naptárak**.

### <a name="prerequisites-for-estimating-the-cost-of-work"></a>Előfeltételek a munka költségének becsléséhez

A WBS teljes költségbecslési kapacitásának kihasználásához be kell állítania a dolgozók számára a költségeket és az eladási árakat, a munkakategóriákat, a kiadásokat és a díjakat, illetve a cikkeket.

-   Önköltségi és eladási ár, munka, költség és díjkategóriákra beállításához kattintson a **projekt igazgatási és számviteli**&gt;**a telepítő**&gt;**árak**.
-   A cikkek költségének és eladási árának beállításához használja a **Kereskedelmi megállapodások **oldalt minden egyes cikk esetében, a **Felszabadított termékek** listalapon, a Termékinformációk kezelésénél.

## <a name="creating-a-wbs"></a>WBS létrehozása
A WBS létrehozása három tevékenységből áll:

1.  **Munka lebontása** – Munka lebontása kezelhető csoportokra vagy feladatokra.
2.  **Munkaütemezés** – Egy a feladat végrehajtásához szükséges idő megbecslése, feladatfüggőségek beállítása és a feladatok kezdési és záró dátumainak kiválasztása.
3.  **Költség becslés** – Az egyes feladatokhoz költségeinek becslése.

A következő részekben megismerheti, hogyan WBS képességeit segíthet e tevékenységek minden.

### <a name="work-decomposition"></a>Munka lebontása

A munka le- vagy felbontása általában a WBS létrehozásának első lépése. A WBS-funkciók a következő alapvető szerkezeteket munka leállása vagy bomlási támogatja. 

**Projekt gyökérfeladata** A projekt gyökérfeladata a legfelső szintű projektfeladat egy projekt esetében. Minden más projektfeladat ez alatt jön létre. A gyökérfeladat neve mindig a projektnévhez van igazítva. A gyökércsomópont esetében a munka, a dátumok és az időtartam a gyökérfeladat alatti feladatok értékeit foglalják össze. A gyökércsomópont tulajdonságait nem lehet módosítani és törölni.

**Összefoglaló vagy tároló feladatok** Az összefoglaló feladat alatt alfeladatok vagy részfeladatok vannak. Összefoglaló feladat önmagában nem jár munkával vagy költséggel. Ehelyett az összefoglaló feladat esetében a munkát és a költséget a részfeladatok munkájának és költségének összege adja. A részfeladatok legkorábbi kezdő dátuma lesz az összefoglaló feladat kezdődátuma, és a részfeladatok legkésőbbi záró dátuma lesz az összefoglaló feladat záró dátuma. Az összefoglaló feladat neve módosítható, de nem lehet módosítani a munka, a dátumok és az időtartam ütemezési tulajdonságait. Összefoglaló feladat törlése esetén az összes alkotó feladat is törlődik. 

**Levél csomópont feladatok** A levél csomópont feladat képviseli a projekt legrészletesebb munkacsomagját. A levélcsomópont rendelkezik egy becsült munkával, az erőforrások tervezett számával, egy tervezett kezdő és a záró dátummal és időtartammal. 

A következő hierarchiaműveletek végrehajtásával engedélyezheti egy munkahierarchia létrehozását vagy egy projekt esetében a felbontást. 

**Új feladat** Minden újonnan létrehozott feladat automatikusan hozzáadódik a gyökércsomópont alá, és a feladathoz automatikusan egy WBS-szám lesz hozzárendelve. A WBS-szám jelöli a feladat hierarchiaszintjét. A projekt gyökérfeladata alatti első szintű feladatokhoz az 1, 2, 3, stb. számozási terv használatos. Az első szint alatti feladatokhoz az 1.1, 1.2, 1.3, stb. számozási terv használatos. Minden egyes korábbi szint alá hozzáadott szint esetében egy új pontozott számsor adódik hozzá. 

Jelenleg nem szabható testre a WBS-számozás. 

**Feladat beljebb húzása** Ha beljebb húz egy feladatot, akkor az az azt megelőző feladat alárendelt feladata lesz. Az új alárendelt feladat WBS-számát a program automatikusan újraszámítja a fölérendelt feladat WBS-száma alapján. A fölérendelt feladat így összegző vagy tároló feladattá válik, és ezért az alkotó feladatok összesítése lesz. 

> [!NOTE] 
> Ha behúz egy tevékenységhez, amely a francia művelet előtt Levélcsomópont volt feladatok, az újonnan létrehozott összefoglaló tevékenység elveszíti a saját dátumok, erőfeszítés és erőforrások számát. Ezután már az új alkotó feladatok értékeinek összefoglalását használja. 

**Feladat kijjebb húzása** Egy feladat kijjebb húzása után az már nem lesz a korábban fölérendelt feladat alkotó feladata. Ennek a feladatnak a WBS-számát a program automatikusan újraszámítja, hogy az tükrözze feladat új szintjét a hierarchiában. A feladat korábbi fölérendelt feladata esetében munka, költség, és a dátumok újra lesznek számolva, a korábbi alkotó feladat kizárásával. 

**Felfele mozgás és lefele mozgás** Ha a **Felfele mozgás** és **Lefele mozgás** lehetőségre kattint, módosítja a feladat pozícióját a fölérendelt hierarchiáján belül. A feladat pozíciója nem befolyásolja a feladat munkáját, költségét, dátumát vagy az időtartamát. Azonban a feladat WBS-számát a program automatikusan újraszámítja, hogy az tükrözze feladat új pozícióját.

### <a name="schedule-estimation"></a>Ütemezés becslése

Az ütemezés becslése általában a WBS létrehozásának második lépése. Legjobb gyakorlatként érdemes a feladatok létrehozása után végrehajtani az ütemezés becslését. A **munkalebontási szerkezet** oldal Microsoft Dynamics 365 a művelet két részből áll. A felső ablak az ütemezés becsléséhez készült, az alsó ablak pedig tartalmaz egy **Becsült költségek és bevételek** lapot, amely költségbecslésre használható. 
**Feladatfüggőségek** A WBS-ben létrehozhat előzménykapcsolatot a feladatok között. Ha előzményfeladatokat rendel hozzá egy feladathoz, akkor ez a feladat csak akkor kezdődhet meg, amikor minden előzményfeladatát befejezték. A feladat tervezett kezdési dátuma automatikusan az előzmények legkésőbbi dátuma lesz. 

**Feladat ütemezése a Microsoft Dynamics 365 műveletek** a következő tényezők határozzák meg a levél csomópont feladatok ütemezése:

-   Megelőző tevékenységek
-   Munka
-   Erőforrások száma
-   Kezdő és záró dátumok

Az előzmények nélküli levélcsomópont kezdődátuma automatikusan a projektütemezés kezdő dátumára lesz állítva. Levélcsomópont-feladat időtartamának számítása mindig a kezdő és záró dátum közötti munkanapok száma alapján történik. 

Ütemezési szabályok *** Ha automatikus ütemezési támogatás be van kapcsolva, a következő szabályok vonatkoznak altevékenység csomópont feladat ütemezése:

-   A projekt ütemezési naptára szerint a feladat kezdő és záró dátumainak munkanapnak kell lenniük.
-   Az előzményekkel rendelkező feladat kezdési dátuma automatikusan az előzmények legkésőbbi dátuma lesz.
-   A feladathoz tartozó munkát a program automatikusan számítja ki, a következőképpen:

Emberek × óraszámot a projektnaptárban a rendes munkaidő időtartamát × száma. 

Bizonyos esetekben lehet, hogy el akar majd térni ezektől a szabályoktól. Automatikus ütemezés Microsoft Dynamics 365 automatikusan beállítása vagy javítása minden altevékenység csomópont tulajdonságainak műveletek elkerülése érdekében kikapcsolhatja. Amikor olyan információt ad meg egy feladathoz, melynek eredményeképpen megsérti az ütemezési szabályokat, egy ütemezési hibát jelző ikon jelenik meg a feladatnál. Ha nem szeretné, hogy látszódjanak az ütemezési hibák, kattintson az **Ütemezési hibák megjelenítve** lehetőségre, hogy kikapcsolja a szolgáltatást. 

> [!NOTE] 
> Az értékek egy Összegzés vagy tároló tevékenység továbbra is alkotó feladatok, függetlenül attól, hogy automatikus ütemezési támogatás be van kapcsolva be- vagy kikapcsolása értékeinek összegeként kell kiszámítani. 

**Ütemezési hibák kijavítása** Ha az automatikus ütemezés támogatása be van kapcsolva, nem valószínű, hogy lesznek ütemezési hibák. Azonban ha kikapcsolja az automatikus ütemezés támogatását, és később újra bekapcsolja azt, ütemezési hibát jelző ikonok jelenhetnek meg a WBS-ben. 

**Ütemezési hibák javítása a feladat által** Ha duplán kattint az ütemezés hibát jelző ikonra egy feladatnál, egy párbeszédpanelen megjelenik az összes ütemezési hiba az adott feladat esetében. Eldöntheti, hogy mely ütemezési hibákat javítja a feladathoz. 

**Összes ütemezési hibák javítása** Ha azt szeretné, hogy a Microsoft Dynamics 365 műveletekhez a műveletpanel a WBS összes ütemezési hiba megoldásához kattintson a **összes ütemezési eltéréseket Fix**. 

> [!NOTE] 
> Ez a funkció okozhat a WBS jelentős módosításokat. A hibák a következő sorrendben vannak kijavítva:

1.  A becsült munka módosul az összes feladatnál, így az egyenlő lesz a projektnaptárban meghatározott kapacitással.
2.  Minden feladat kezdő dátuma úgy módosul, hogy a feladat azt követően kezdődik, hogy az összes megelőző feladatát végrehajtották.
3.  Minden feladat kezdő dátuma módosul, hogy a megelőző feladatok kezdődátumai között ne legyenek hézagok.

### <a name="cost-estimation"></a>Költségbecslés

Mint ahogy korábban említettük a dokumentumban, minden levélcsomópont-feladatnál a költségeket a **Becsült költségek és bevételek** lap használatával adja meg, a **Munkalebontási struktúra** oldal alsó ablakában. 

> [!NOTE] 
> A Költségbecslés összegzése vagy tároló tevékenység nem módosítható. Az összefoglaló feladat esetében a költségbecslés megegyezik a levélcsomópontok feladatai esetében az egyes költségbecslések összegével. Minden feladat becsült teljes költsége a következő tranzakciótípusok becsült költségeinek összegeként lesz kiszámítva:

-   Munka
-   Cikk vagy anyag
-   Költségek

A **Díj** tranzakciótípus a díjalapú bevételek becslésére használható. A tranzakció típusában nincs költségösszetevő, és ezért nem számít a költségek becslésekor. 

A **Részszámlázás** tranzakciótípus a szerződéses eladási érték rögzítésére szolgál, rögzített értékű projekt esetében. Ezt a tranzakciótípussal nem is kell figyelembe venni, amikor költségeket becsülik. 

Amikor a munka és az anyagok költségeit, illetve a kiadásokat becsüli az egyes feladatoknál, projektkategóriát kell rendelnie a becsült költséghez. 

**Munkaköltségek becslése** Minden levélcsomópont-feladathoz hozzá kell rendelni egy munkát órákban kifejezve, és egy alapértelmezett kategóriát. Ezért a feladat ütemezésének beállításakor az adott munka költségbecslése automatikusan hozzáadódik a munka tartozó alapértelmezett kategóriájához. A költségbecslés fel van tüntetve az adott feladatnál a **Becsült költségek és bevétel** lapon, a **Sor adatai** rácson. Ha további munka költségbecsléseire van szüksége, ezen a lapon hozzáadhatja őket. Ha csökkenti vagy növeli az órák számát a munkaköltség becslésében, a program automatikusan újraszámítja a feladat ütemezését. 

**Kiadások és anyagköltségek becslése** A **Becsült költségek és bevételek** lap azt is lehetővé teszi, hogy megbecsülje egy feladat kiadásait és anyagi költségeit, ha becslésre van szüksége. 

Önköltségi és eladási ár minden munka vagy költség becslése, a telepítő minden kategóriához, az árképzési táblázatokban megadott sor alapuló **projektek igazgatási és számviteli**&gt;**a telepítő**&gt;**árképzés**. A cikkek esetében a költség és eladási ár alapértelmezett beállításként hozzáadódik a cikkből vagy a kereskedelmi megállapodásokból a **Kiadott termékek** listalapon, a Termékinformációk kezelésénél.

## <a name="tracking-progress-on-the-wbs"></a>Nyomonkövetési folyamat a WBS-en
Egyes ágazatokban nagyon részletesen nyomon követik a projekt előrehaladását a WBS alapján, míg mások a WBS magasabb szintjén követik nyomon az előrehaladást. Ez a szakasz leírja, hogyan használható a WBS-nyomonkövetés a projektkövetelmények teljesítéséhez. 

A Microsoft Dynamics 365 műveletek esetében a projekt WBS három nézete van: a Tervezés nézetben, erőfeszítés követés megtekintése és költség követés megtekintése.

### <a name="planning-view"></a>Tervezési nézet

A Tervezés nézet jeleníti meg az ütemezés tervezett vagy alapbecslését és a költség-információt. Noha nincsenek a projekt-WBS verziójának és kiindulásának nyomon követésére szolgáló funkciók, az ebben a nézetben szereplő értékek képviselik a kiindulási verziót. Az Ütemezés becslése és a Költségbecslés részek ebben a témakörben ezt a nézetet írják le, és hogy hogyan használható WBS létrehozására.

### <a name="effort-tracking-view"></a>Munkakövetési nézet

A Munkakövetési nézet megjeleníti a WBS-es feladatok folyamatának követését. Összehasonlítja a feladat halmozott tényleges ráfordított óráit a tervezett munkaórákkal. A következő képletek adják meg az értékeket a Munkakövetési nézetben:

-   Végrehajtási százalék = Tényleges munka a mai napig ÷ Tervezett munka a feladathoz
-   Fennmaradó munkamennyiség (más néven becslés--végre \[stb\]) = tervezett tevékenységi – tényleges annak érdekében, hogy a dátum
-   Becslés befejezéskor (EAC) = Hátralevő munka + Tényleges munka a mai napig
-   Előre jelzett munkaeltérés = Tervezett munka – EAC

A Munkakövetési nézet jeleníti meg az előre jelzett munkaeltérést a feladatban, attól függően, hogy az EAC több vagy kevesebb, mint a tervezett munka:

-   Ha az EAC meghaladja a tervezett munkát, az előrejelzés szerint a feladat több időt vesz igénybe, mint eredetileg tervezték, és le van maradva az ütemezéshez képest.
-   Ha az EAC kisebb, mint a tervezett munka, az előrejelzés szerint a feladat kevesebb időt vesz igénybe, mint eredetileg tervezték, és előbb jár az ütemezéshez képest.

**A munka újbóli előrejelzése a projektvezető által** Esetenként a projektmenedzsernek vagy más személyeknek, akik a projekt előrehaladását követik nyomon, újra felül kell vizsgálniuk a feladat eredeti becsléseit. Lehet, hogy egy feladat az eredeti előrejelzéshez képest gyorsabban vagy lassabban halad előre, különféle okokból kifolyólag. Például csökkent a hatókör, vagy a dolgozók tapasztalata kevesebb, mint az eredetileg tervezett. A prognózisok a projektvezető becslései, a projekt aktuális állapota alapján. Általában nem kell módosítania a kiindulási számokat, mert a projekt kiindulási pontja jól közzétett dokumentumban, a projektütemezésben és a költségbecslésben jelenik meg, amelyhez a projektben érdekelt összes fél hozzájárult. 

Két módon, hogy a projektmenedzserek módosíthatják a munka feladatok:

-   Módosítsa a hátralevő munkát, amely automatikus frissítésre van beállítva a feladatban a tényleges fennmaradó munkával kapcsolatban.
-   Módosítsa a százalékos előrehaladást, amely automatikus frissítésre van beállítva a feladatban a tényleges előrehaladással kapcsolatban.

Mind a két megközelítés a feladat ETC-jének, EAC-jának, százalékos előrehaladásának és az Előre jelzett munkaeltérésnek az újraszámítását eredményezheti. Az EAC, ETC és a százalékos haladási érték is újra lesz számítva az összefoglaló feladatoknál, és az előre jelzett munkaeltérés frissül. 

**Módosított munka az összefoglaló feladatoknál** Módosíthatja az összefoglaló vagy tároló feladathoz tartozó munkát. Függetlenül attól, hogy módosítja-e ezeket az értékeket a hátralevő munka vagy a végrehajtási százalék használatával az összefoglaló tevékenységeknél, a számítások automatikusan a következő sorrendben jelennek meg:

1.  Az EAC, az ETC és a tevékenység százalékos haladási értéke lesz kiszámolva.
2.  Az új EAC az alárendelt feladatok között oszlik el, ugyanabban az arányban, mint az eredeti EAC mennyiség.
3.  Az új EAC minden levélcsomópont-feladat esetében külön ki lesz számítva.
4.  A hátralevő munka és a végrehajtási százalék újra lesz számítva minden érintett alárendelt feladat esetében, az új EAC-érték alapján. A feladatok munkaeltérése is frissül.
5.  Az EAC az összefoglaló tevékenységek esetében is újra lesz számítva a levélcsomópontokból.

Kattintson a **Kibontás szintig** lehetőségre a Munkakövetési nézetben, hogy milyen szinten szeretné nyomon követni és fenntartani a WBS-t. A WBS automatikusan erre a szintre bomlik ki a Munkakövetési nézet megnyitásakor.

### <a name="cost-tracking-view"></a>Költségkövetési nézet

A Költségkövetési nézet jeleníti meg a tevékenység költségfelhasználásának nyomon követését. Ebben a nézetben a feladatra a záró dátumig fordított tényleges költség a feladat tervezett költségével lesz összehasonlítva. A következő képletek adják meg az értékeket a Költségkövetési nézetben:

-   Felhasznált költség százaléka = Tényleges költség a mai napig ÷ A feladat tervezett költsége
-   CTC = Tervezett költség – Tényleges költség a mai napig
-   EAC = CTC + Tényleges költség a mai napig
-   Előrejelzett költségeltérés = Tervezett költség – EAC

A Költségkövetési nézet jeleníti meg az előre jelzett költségeltérést a feladatban, attól függően, hogy az EAC több vagy kevesebb, mint a tervezett költség:

-   Ha az EAC meghaladja a tervezett költséget, az előrejelzés szerint a feladat több pénzbe kerül, mint eredetileg tervezték, és túllóg a költségvetésen.
-   Ha az EAC kevesebb, mint a tervezett költség, az előrejelzés szerint a feladat kevesebb pénzbe kerül, mint eredetileg tervezték, és a költségvetés alatt van.

**A költség újbóli előrejelzése a projektvezető által** A Projektvezetőknek a CTC-t kell használniuk a feladat eredeti költségbecsléséhez. A projektmenedzser módosíthatja a CTC-értéket arra a költségre, amely a feladat befejezéséhez szükséges. Ha módosítja a CTC-értéket, a feladat CTC-je, az EAC, a felhasznált költség százaléka és a feladat előre jelzett költségeltérése újra lesz számítva. Az EAC, az ETC és a felhasznált költség százalékos értéke is újra lesz számítva az összefoglaló feladatoknál, és az előre jelzett költségeltérés frissül. 

> [!NOTE] 
> Amikor megváltoztat erőkifejtés erőfeszítés követés nézetben, a feladat CTC, BECSÉ, tevékenység WBS költség százaléka fogyasztott, és a tervezett költségeltérés összes újraszámít a nyomon követési nézetet költség. Azonban költség felülvizsgálata nem befolyásolja a Munkakövetési nézet értékeit, mert a tranzakció típusa (munka, anyag vagy költség) vagy a projektkategória szerinti költség nincs módosítva. 

**Összefoglaló feladatok költség-előrejelzésének felülvizsgálata** Módosíthatja az összefoglaló tevékenységek költségeit, és a számítások automatikusan a következő sorrendben jelennek meg:

1.  Az EAC, a CTC és a feladatra felhasznált költség százaléka újra lesz számítva.
2.  Az új EAC az alárendelt feladatok között oszlik el, ugyanabban az arányban, mint az eredeti EAC.
3.  Új EAC kiszámítása az egyes feladatokhoz.
4.  A CTS és a felhasznált költség százaléka újra ki lesz számítva az érintett alárendelt feladatok esetében, az EAC-érték alapján. A feladatok költségeltérése is frissül.
5.  Az összes összefoglaló tevékenység EAC-ját a program újraszámítja a módosítás alapján.

Kattintson a **Kibontás szintig** lehetőségre a Költségkövetési nézetben annak beállításához, hogy milyen szinten szeretné nyomon követni és fenntartani a WBS-t. A WBS erre a szintre bomlik ki a Költségkövetési nézet megnyitásakor.

### <a name="earned-value-management"></a>Jelenérték-kezelés

A létrehozottérték-módszer (EVM) segítségével nyomon követheti a projekt előrehaladását. Megtekintheti a jelenérték mérőszámait a projektvezető Szerepkör főoldalán. A létrehozott érték diagram-összetevő megmutatja a tervezett érték és a tényleges költség időbeli értékeit. Az aktuális dátum szerinti jelenérték pontként jelenik meg. A jelenérték időbeli adatai most nem érhetők el. 

A jelenérték-diagramon az időfázis hetek vagy hónapok szerint jelenik meg. Ez a szakasz az EVM három pillérét mutatja be: tervezett érték, létrehozott érték és a tényleges költség. 

**Tervezett érték** Az EVM-elmélet kimondja, hogy az tervezett értéktáblázat jelzi, hogy a projektcsapat milyen tempóban tervezte az értéklétrehozást a projekten belül. 

Microsoft Dynamics 365 műveletekhez használja a 0:100 szabály megszerzéséhez, amikor azt rajzolja fel a tervezett érték. A szabály alapján a feladat értékét a feladat záró dátuma szerint kell beírni a feladathoz. Addig nincs megadva érték, amíg a feladat 100%-ig el nem készül. 

A Projektvezetés és könyvelés részben a levélcsomópontok záró dátumát és a tervezett költséget adja meg. Ha a tervezett érték diagramja hetek szerint jelenik meg, a tervezett érték az összes levélcsomópont-feladat esetében hetek szerint lesz összesítve a projekt időtartama alatt. 

**Jelenérték** Az EVM-elmélet kimondja, hogy a jelenérték-táblázat jelzi, hogy a projektcsapat ténylegesen milyen tempóban hoz létre értéket a projekten belül. 

Microsoft Dynamics 365 műveletekhez használja a szabály megszerzéséhez, amikor a parcellák létrehozott érték 0:100. A szabály alapján a feladat értékét a feladat záró dátuma szerint kell beírni a feladathoz. Addig nincs megadva érték, amíg a feladat 100%-ig el nem készül. 

Jelenérték összeg számítása során minden egyes feladat előrehaladási százaléka számít. A 0:100 kereseti szabály szerint csak egy adott időszakban végrehajtott feladatok lesznek figyelembe véve a jelenérték kiszámításakor, az adott időszak vége alapján. A projekt jelenértékét az összes, a diagram létrehozásakor befejezett feladat vonatkozásában számítja ki a rendszer. 

> [!NOTE] 
> WBS nyomon követési rendszere jelenleg nem rendelkezik adatstruktúrákat tárolja a történelmi fejlődés százalékos feladatokra. Emiatt a jelenérték csak a kocka feldolgozásának időpontjára vonatkozóan jelenthető. A kockát rendszeresen fel kell dolgozni, hogy frissüljenek a létrehozott érték adatai a Szerepkör oldalon. 

**Tényleges költség** Az EVM-elmélet kimondja, hogy a tényleges költség kijelzése mutatja, hogy milyen arányban költik el a pénzt a projektre. 

A projekthez rendelt tranzakciók a tényleges költségsor kijelzésére használhatók. A költségek dátum szerint lesznek összefoglalva. Ezt az adatot ezután a tényleges költségek hetek vagy hónapok szerinti grafikus megjelenítésére használják a létrehozott érték táblázatában.

### <a name="how-to-use-the-concepts-of-planned-value-earned-value-and-actual-cost"></a>Hogyan használjuk a tervezett érték, jelenérték és tényleges költség koncepciókat

**Ütemezési eltérés** A tervezés során egy előrejelzést kell készítenie a munka számára, egy idővonalon. Ennek megfelelően tervezett érték a projekttervezők szerinti tempó, amellyel a munka végrehajtható a projekten. Ha a projekt folyamatban van, majd a munka befejeződik, a projekt értéket hoz létre. Jelenérték és a tervezett érték összehasonlításával meg lehet tekinteni, hogy hogyan halad a munka egy projekt tekintetében. Az összehasonlítás eredményét ütemezési eltérésnek hívják. 

Ha a tervezett időszak értéke nagyobb, mint a létrehozott érték, a projektben elvégzett munka mennyisége kevesebb, mint a tervezett munkamennyiség. A projekt ezért elmarad az ütemtervtől. Mivel a tervezett értéket és a jelenértéket pénzben fejezik ki, a lemaradást is pénzben adják meg. 

Ha a tervezett időszak értéke kevesebb, mint a létrehozott érték, a projektben elvégzett munka mennyisége több, mint a tervezett munkamennyiség. A projekt ezért az ütemterv előtt jár. Ez az idő is pénzügyi értékkel rendelkezik.

**Költségeltérés** Mivel a létrehozott érték a költségárat használja szorzóként, a létrehozott érték a projekten elvégzett munka költségét jelzi. A projekt előrehaladtával a tranzakciónapló számon tartja a projektre ténylegesen elköltött pénz mennyiségét. A létrehozott érték és a tényleges költség összehasonlításával megnézheti, hogy mennyi pénz lett elköltve ahhoz képest, hogy mennyi pénzt keresett. Az összehasonlítás eredményét költségeltérésnek hívják. 

Esetén időtartamra töltött tényleges költsége nagyobb, mint a jelenérték több pénzt töltött, mint az elért. A projekt ezért túllépi a költségvetést. 

Ha a tényleges kiadott költség egy időszakra kevesebb, mint a létrehozott érték, akkor több pénzt keresett, mint amennyit elköltött. A projekt ezért a költségvetés alatt van.

## <a name="wbs-templates"></a>WBS-sablonok
A WBS-sablonok funkciók segítségével projektek szabványos sablonokat hozhat létre. Ha a cég által kínált projektek sok ismételhető munkával járnak, vegye figyelembe a WBS-sablon létrehozását. 

WBS-sablont létrehozhat egy meglévő projekt WBS-éből, hogy a tudás és a legjobb gyakorlatok, melyeket a tervezés során összegyűjtött, hasonló projektekben is felhasználhatók legyenek a jövőben. Azonban előfordul, hogy nincs értelme annak, hogy a teljes WBS-t elmentsük sablonként. Ezért a projekt WBS-ének részeiből is létrehozhat sablonokat.

### <a name="saving-a-projects-wbs-as-a-template"></a>Projekt WBS-ének mentése sablonként

Miután létrehozott egy sablont, azt importálhatja egy új projekt WBS-ébe a gyökércsomópont alatt, vagy a projekt WBS-ében bármely feladat alatt.

### <a name="importing-a-wbs-template-into-a-projects-wbs"></a>WBS-sablon importálása egy projekt WBS-ébe

Feladatok importálásakor a sablonban található feladatok annak a feladatnak a kezdő dátuma szerint vannak csoportosítva, amely alá importálva vannak. Importálás során a sablonfeladatokon lévő előzménykapcsolatok segítségével lehet kiszámítani az importált tevékenységek kezdő dátumát. A célprojekt normál munkanaptárát az importált tevékenységek záró dátumának kiszámítására használja a rendszer, hogy a munkanapok és a normál munkaórák, amelyek a jelenlegi projekt munkanaptárában vannak, megmaradjanak. 

A becsült sorokon lévő költségösszegek és eladási árak garantálják, hogy az árak, amelyek a projekt vagy a projektszerződés szerint meg vannak határozva, érvényes dátumokkal rendelkezzenek.

### <a name="differences-between-a-projects-wbs-and-a-wbs-template"></a>A projekt-WBS és a WBS-sablon közötti különbségek

-   A WBS-sablonokban lévő feladatoknak nincs kezdési és záró dátuma.

A munka- és a szabadnapok nincsenek beállítva WBS-sablonoknál.

-   A WBS sablonjai mindig használják az ütemezési naptárat, amely az összes projekt alapértelmezett naptáraként van beállítva.

Az alapértelmezett ütemezési naptár segítségével csak a normál munkanap órái állapíthatók meg.

-   WBS-sablonba nincsenek bemásolva az előzménykapcsolatok.

Mivel WBS-sablonok nem rendelkeznek a dátumokkal, ezért a kezdő dátum logikája, amely egy előzmény záró dátumán alapul, nem szükséges.

-   A munka-költség becslési sor automatikusan létrejön, amikor feladatot hoznak létre a WBS-sablonban. Az eladási ár és a költségösszeg a kijelölt dolgozótól lesz átmásolva.

Kiadások és cikk-költségek létrehozhatók manuálisan, ugyanúgy, mint a projekt WBS-ében.

-   Ütemezési hibák jelennek meg, ha eltérés van a következő formulától:

Munka = Erőforrások száma × Időtartam × Órák száma egy normál munkanapon belül 

Egyszerre kijavíthat minden ütemezési hibát, ha a **Minden ütemezési hiba kijavítása** lehetőségre kattint. 

Azt is megteheti, hogy külön-külön javítja ki az ütemezési hibákat úgy, hogy az egyes feladatoknál rákattint a figyelmeztető ikonra.


