---
title: "Költségvetés-tervezés frissítése"
description: "Jelentős különbségek vannak a költségvetés tervezésében a Microsoft Dynamics AX 2012 és a Microsoft Dynamics 365 for Finance and Operations között. Egyes funkciók nem frissültek, ezért újrakonfigurálást igényelnek. Ez a témakör elmagyarázza, hogy mit kell újrakonfigurálni, és leírja azokat az új funkciókat, amelyeket érdemes kipróbálni a frissítés befejezése után."
author: ryansandness
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.reviewer: robinr
ms.search.scope: Core, Operations
ms.custom: 272923
ms.assetid: 17cdfe74-bdfd-466a-9bdd-c12583f250c7
ms.search.region: Global
ms.author: ryansand
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: a39f516bb6d023ea18492ba3dfe721bd1127c60e
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="upgrade-budget-planning"></a>Költségvetés-tervezés frissítése

[!INCLUDE [banner](../includes/banner.md)]

Jelentős különbségek vannak a költségvetés tervezésében a Microsoft Dynamics AX 2012 és a Microsoft Dynamics 365 for Finance and Operations között. Egyes funkciók nem frissültek, ezért újrakonfigurálást igényelnek. Ez a témakör elmagyarázza, hogy mit kell újrakonfigurálni, és leírja azokat az új funkciókat, amelyeket érdemes kipróbálni a frissítés befejezése után.  

A Microsoft Dynamics 365 for Finance and Operations programban a költségvetés-tervezés számos olyan fejlesztést tartalmaz, amelyek nem voltak elérhetők a Microsoft Dynamics AX 2012-ben. Ez a téma azokat a változásokat mutatja be, amelyeket a frissítő ügyfeleknek végre kell hajtaniuk. Emellett felhívja a figyelmet azokra az új funkciókra is, amelyeket figyelembe kell venni a frissítési folyamat során. A változtatások mértéke miatt a meglévő költségvetési tervek csak akkor nyithatók meg, ha a jelen témakörben felvázolt változtatások megtörténtek. A jelentéseknek azonban továbbra is működniük kell, és nincs szükség hozzájuk plusz módosításokra.

## <a name="overview-of-changes"></a>Változások áttekintése
Számos jelentős változás következett be a Dynamics 365 for Finance and Operations Költségvetés részében. Ezek a változtatások arra szolgálnak, hogy könnyebben konfigurálhatóvá és újrahasználhatóbbá tegyék a költségvetés tervezését, csökkentve az évről évre szükséges karbantartási és beállítási igényt. Az AX 2012 következő területei már nem léteznek a Dynamics 365 for Finance and Operations szolgáltatásban:

-   Költségvetésiterv-sablonok (Költségvetési terv konfigurációja)
-   Költségvetésiterv-mappák (Költségvetési terv konfigurációja)
-   A tervváltozat megszorításai (költségvetés-tervezés konfigurációja)
-   A költségvetés-tervezés szakaszainak szabályai és sablonjai (költségvetés-tervezési folyamat)
-   Munkalapsablonok mátrixmezői
-   Költségvetési terv Microsoft Excel-sablon varázsló

Egyes új elemek nem frissíthetők közvetlenül a korábbi funkcióból. Ezért végre kell hajtania egyes újrakonfigurálásokat ezen új fogalmak kezeléséhez. Az alábbi szakaszok azokat a fogalmakat írják le, amelyek az előző listában szereplő elemek helyébe léptek.

### <a name="columns"></a>Oszlopok

Az oszlopok olyan új koncepciót jelentenek, amely az Excel-sablon egy része és a mátrixmezők helyére lép. Az oszlopok jelenthetnek időszakot, hónapot, negyedévet, vagy a teljes időt. Az időre való hivatkozás dinamikus. Rámutat egy relatív időszakra vagy évre a költségvetési folyamatra való hivatkozással. Az **Előző év január** oszlop hivatkozása például az 1 pénzügyi időszak –1 év. Az oszlop egy költségvetési tervváltozatra jellemző, például a tényleges adatokra vagy a költségvetési kérelemre.

### <a name="layouts"></a>Elrendezések

Az elrendezések az Excel-sablonokat felváltó új elemek. Az elrendezések tartalmazzák az oszlopokat, amelyek meghatározzák, hogy mely költségvetési vagy tényleges adatok és időszakok jelenjenek meg. Az elrendezések az ügyfél és az Excel-bővítmény között is megosztásra kerülnek. Ezért a Dynamics 365 for Finance and Operations ügyfélprogramban az adatok beírásával vagy megtekintésével kapcsolatos felhasználói élmény jobb, mint az AX 2012 felhasználói élménye. Ha adatokat szeretne felvinni a Finance and Operations ügyfélbe, már nem korlátozódik egyetlen forgatókönyv megtekintésére és bevitelére tranzakciós nézetben. Ehelyett az összehasonlító nézet lehetővé teszi, hogy egyszerre több időszakot és fiókot is egyszerre megtekinthessen, és összegeket írhasson be. Az elrendezések úgy is definiálhatók, hogy pénznemet, megjegyzést és egyéb opcionális adatokat adhat meg és tekinthet meg bennük. Az elrendezések segítségével továbbá meghatározhatja, hogy mely főkönyvi dimenziók és dimenzióleírások jelenjenek meg. Az elrendezések emellett forgatókönyv-korlátokat is tartalmaznak, amelyek meghatározzák, hogy a sablonok mely oszlopai szerkeszthetők, illetve mely oszlopok legyenek elérhetők az Excel-ben. Egy elrendezés meghatározását követően sablon jön létre hozzá. Ez a sablon ugyancsak létrehozza a megfelelő Excel-sablont. Ezután szerkesztheti az Excel-sablont, hogy az további képleteket és formázást tartalmazzon, majd feltöltheti újra. Az elrendezéseket ezután a rendszer minden egyes szakaszszabályhoz hozzárendeli a **Költségvetés-tervezési folyamat** oldalon. Ezért az elrendezések helyettesítik a sablonokat, amelyeknek hasonló a hozzárendelésük és használatuk.

### <a name="budget-planning-processes"></a>Költségvetés-tervezési folyamatok

A költségvetés-tervezési eljárások többnyire ugyanazok, mint az AX 2012-ben. A legjelentősebb változás a sablonok elrendezésekre történő cseréje. Ha a folyamatok korábban befejeződtek az AX 2012-ben, akkor azok folyamatban lévő állapotba kerülnek, így változtatásokat hajthat végre rajtuk. Hozzá kell rendelnie az elrendezéseket, hogy minden egyes szakasz szabályához meghatározhassa, hogy mely forgatókönyvek és időtartamok jelenjenek meg, amikor megnyitják a tervet az ügyfélprogramban. Az elrendezések azt is meghatározzák, hogy melyik Excel-sablont nyissa meg a Dynamic 365 for Finance and Operations programon kívül, hogy megtekinthesse a költségvetést. Az **Alapértelmezett számlastruktúra** egy új kötelező mező a költségvetés-tervezés folyamatához. Minden egyes költségvetés-tervezési folyamatnál adja meg a költségvetéshez használt elsődleges fiókstruktúrát.

### <a name="attachments"></a>Mellékletek

Az AX 2012-ben az igazoló dokumentumokat a mellékletek mappájába mentette a rendszer. A korábbi igazoló dokumentumok nem frissülnek. Az igazoló dokumentumok mostantól az adatbázisba kerülnek. Ha ezeket az információkat menteni kell a frissített verzióban, az egyes tervekhez csatolmányként felveheti a végső igazoló dokumentumokat az **Igazolás** gomb megnyomásával a Műveleti ablaktáblán. Az AX 2012-ben Excel-munkafüzetet hozott létre a program minden egyes költségvetési tervhez a sablon alapján. A Finance and Operations programban minden terv megnyitja az elrendezés egy példányát. Az Excel-fájl módosítása azonban nem történik meg. Minden olyan képletet és támogató adatot, amelyet tervenkénti alapon használt, megjegyzésként, igazoló dokumentumként vagy más kiegészítő folyamatként kell megadni.

## <a name="configuring-an-upgraded-environment-from-ax-2012"></a>Frissített környezet konfigurálása az AX 2012-ből
A frissített rendszer beállításaira vonatkozó konfiguráció meghatározásához a következő példa egy frissített költségvetési folyamatot használ az AX 2012 demóadatokból. Az oszlopok alapértelmezett konfigurációs adatainak létrehozása a frissítési folyamatban való segítséghez jött létre. Frissítheti vagy törölheti az alapértelmezett adatokat, ha nem felelnek meg a konfigurációs követelményeknek. **Megjegyzés:** Új kötelező mezők is vannak, amelyeknek beállítása nem a rendszerben történik. Ha elakad egy oldalon, például a **Költségvetés-tervezési konfiguráció** oldalon, és nem tud elnavigálni, bezárhatja a böngészőt, majd újra megnyithatja egy másik oldalon, hogy a megfelelő sorrendben megadhassa a részleteket. Vannak kötelező mezők, amelyek még nincsenek beállítva. Ennélfogva a problémák mindaddig előfordulhatnak, amíg mindent nem konfigurált, és minden szükséges mezőt be nem állított. Ez a témakör azt ismerteti, hogy miként kell ezeket a mezőket beállítani. Az alábbiakban néhány ilyen kötelező mező látható:

-   **Költségvetés-tervezési folyamat** oldal: **Alapértelmezett számlastruktúra** mező
-   **Költségvetés-tervezési folyamat** oldal: **Elrendezés** mező a **Költségvetés-tervezési szakaszok szabályai és elrendezései** gyorslapon

### <a name="define-columns-and-layouts"></a>Oszlopok és elrendezések meghatározása

1. A **Költségvetés-tervezési konfiguráció** oldalon kattintson az **Oszlopok** lapra. A frissítés részeként az új oszlopok automatikusan létrejönnek a költségvetési terv sorai alapján. Az oszlopok dinamikus dátumokat használnak, ahol az idő és az év eltolódik a költségvetési tervezés folyamatában meghatározott pénzügyi évvel. **Megjegyzés:** Teljesítményokokból a frissítés során feltételezzük, hogy az összes költségvetési ciklus naptári évet, nem pénzügyi évet jelent. Pénzügyi évek használata esetén módosítania kell az oszlopok elrendezését a pénzügyi évhez való igazítás érdekében. Például az AX 2012 rendszerben a következő elemek léteztek:
   -   Költségvetési tervek forgatókönyvei: Tényleges adatok, Kiindulás, Költségvetési kérelem, Költségvetés jóváhagyva
   -   Költségvetési terv sorai 2017 minden forgatókönyvéhez, valamint Tényleges adatok 2017-re és 2016-ra

   A következő oszlopok jönnek létre a Finance and Operations programban:

   | Oszlop neve    | Költségvetési tervváltozat | Oszlop időszaka | Év eltolása |
   |----------------|----------------------|--------------------|-------------|
   | Jan 1. eset | Tényadatok              | 1                  | 0           |
   | Jan 2. eset | Kiindulás             | 1                  | 0           |
   | Jan 3. eset | Költségvetési kérelem       | 1                  | 0           |
   | Jan 4. eset | Jóváhagyott költségvetés      | 1                  | 0           |
   | Jan 5. eset | Tényadatok              | 1                  | -1          |
   | Feb 1. eset | Tényadatok              | 1                  | 0           |
   | ...            | ...                  | ...                | ...         |

   Ebben a példában egy **Jan 1. eset** nevű oszlop jön létre a legfrissebb költségvetési terv tranzakciós adataihoz, amely megtalálható ott, ahol tranzakciók vannak januárban. Hasonló oszlop jön létre minden olyan forgatókönyvhöz, amely adatokkal rendelkezik. Miután oszlopok léteznek az adott év minden időszakára vonatkozóan, az előző évekhez oszlopok jönnek létre.
2. Módosíthatja az oszlopneveket és -leírásokat, valamint bármely más részletet, akár manuálisan az ügyfélprogramban, akár tömeges frissítésekkel az Excel-bővítményen keresztül, amely a költségvetési terv oszlopainak adatentitására mutat. Az előzőleg a mátrixmezőkhöz beállított szűrők beállítása mostantól az oszlopokon belül történik.
3. Új költségvetési terv elrendezésének létrehozása. Az elrendezés több oszlopra mutat az Excelben és az ügyfélprogramban megjelenő nézet meghatározásához. Az elrendezés először azt kéri, hogy megadjon egy főkönyvdimenzió-készletet annak meghatározásához, hogy mely pénzügyi dimenziók adhatók meg. Miután megadta a dimenziókészletet, kattintson a **Leírások** lehetőségre, hogy kiválassza az elrendezésbe foglalni kívánt dimenzióleírásokat.
4. Az **Elrendezéselemek** gyorslapon kattintson a **Hozzáadás** lehetőségre, amellyel metaadatokat adhat minden egyes sorhoz, például pénznemet, megjegyzést vagy költségvetési osztályt, amely különbséget tesz a bevételi és költségsorok között. Ezután adjon hozzá oszlopokat az időtartamhoz, továbbá azokat a forgatókönyveket, amelyek erre a költségvetési ciklusra és szakaszra vonatkoznak. Ezeket a módosításokat kézzel is végrehajthatja az ügyfélprogramban vagy az Excel-bővítményen keresztül, amely a költségvetési terv elrendezéselemeinek adatentitására mutat.
5. Minden egyes elrendezési elem esetén válassza ki, hogy az oszlop szerkeszthető legye-e, és hogy az oszlop az Excel-munkafüzetben is megjelenjen-e az elrendezésnél. **Megjegyzés:** Az előzményterveinknél érdemes fontolóra venni egy olyan elrendezést, amely 12 havi oszlopot tartalmaz minden olyan költségvetési terv esetében, amely az adott folyamathoz tartozik.

### <a name="update-budget-planning-processes-to-use-the-appropriate-layout-for-each-budget-stage"></a>Frissítse a költségvetés-tervezési folyamatokat annak érdekében, hogy a megfelelő elrendezést használja minden egy költségvetés-szakasz esetén

1.  A **Költségvetés-tervezési folyamat** oldalon válassza ki a konfigurálandó folyamatot.
2.  Kattintson a Műveleti ablak **Szerkesztés** elemére.
3.  Adja meg az alapértelmezett számlastruktúrát ehhez a költségvetési folyamathoz. Az **Alapértelmezett számlastruktúra** egy új kötelező mező.
4.  A **Költségvetés-tervezési szakaszok szabályai és elrendezései** gyorslapon, az **Elrendezés** mezőben válassza ki az elrendezést, amelyet korábban már konfigurált, és ami megfelelő ebben a szakaszban.
5.  Folytassa ugyanazon vagy különböző elrendezések kiválasztását a különböző költségvetési tervezési szakaszoknál, majd mentse el a módosításokat.

## <a name="additional-features-to-consider-in-your-budgeting-process"></a>További szolgáltatások, amelyet figyelembe kell vennie a költségvetés-tervezési folyamat során
### <a name="budget-planning-workspace"></a>Költségvetés-tervezési munkaterület

Ez a munkaterület mind a költségvetés-tulajdonos, mind az egyéni költségvetési hozzájárulók számára készült. Hivatkozást tartalmaz minden olyan költségvetési dokumentumhoz, amely a figyelmét igényli. Jelentésekkel és kulcsfontosságú teljesítménymutatókkal (KPI-k) is rendelkezik a költségvetési folyamatról. A költségvetési adminisztrátor meghatározhatja az aktuális költségvetés-tervezési folyamatot a **Költségvetési paraméterek** oldalon. A **Munkaterület beállításai** lapon, a **Költségvetés-tervezés** gyorslap tartalmaz egy olyan mezőt, ahol kiválaszthatja a költségvetés-tervezési folyamatot.

### <a name="alternate-layouts"></a>Alternatív elrendezések

Az alternatív elrendezések egy olyan új funkciót jelentenek, amely lehetővé teszi a tervek különböző elrendezésekben történő megjelenítését. Egy vagy több elrendezés választható. Ezután egy költségvetési tervet havi elrendezésben vagy negyedéves elrendezésben tekinthet meg. Alternatív elrendezéseket határozhat meg a **Költségvetés-tervezési szakaszok szabályai és elrendezései** gyorslapon, a **Költségvetés-tervezési folyamat** oldalon.

### <a name="budget-milestones"></a>Költségvetési mérföldkövek

A költségvetési folyamat részeként létfontosságú a kulcsdátumok és a határidők tudomásul vétele. Mostantól konfigurálhatja a dátumokat, hogy azok leírásokkal rendelkezzenek. A költségvetési felhasználók ezeket a leírásokat látják, amikor a költségvetéseket megnyitják, hogy szerkeszthessék vagy megtekinthessék a hozzájuk rendelt elemeket.

### <a name="copy-from-budget-plan-allocation"></a>Másolás költségvetési tervből – felosztás

Az új felosztási módszer lehetővé teszi, hogy szülőtervből gyermektervre terjesszen át elemeket anélkül, hogy azokat a hierarchiában köztes szinteken kellene átvezetnie. Ez a módszer különösen az olyan ügyfeleknél hasznos, akik korábban pénzügyi dimenziót hoztak létre csak a költségvetés elosztására és jóváhagyásaira.

### <a name="generating-budget-plans-from-new-budget-sources"></a>Költségvetési tervek létrehozása új forrásadatokból

Az alábbi opciókat vettük fel időszakos folyamatokként. Ezek a beállítások lehetővé teszik, hogy költségvetési tervet hozzon létre kiindulási pontként egy másik modul meglévő adatainak felhasználásával:

-   Költségvetési terv létrehozása igény-előrejelzés alapján
-   Költségvetési terv létrehozása ellátási előrejelzésből
-   Költségvetési terv létrehozása projekt alapján
-   Költségvetési terv létrehozása költségvetésijegyzékből

### <a name="more-complete-tracking-of-amounts"></a>Összegek részletesebb nyomon követése

Az AX 2012-ben a költségvetési tervezésnél csak egy tervösszeg szerepelt, amelynek tárolása minden egyes értéknél megtörtént. A Finance and Operations programban kibővítettük az adatmodellt. Most már minden egyes értékhez könyvelési pénznem, tranzakciós pénznem és jelentési pénznem is tartozik. A frissítés során az új oszlopok automatikusan kitöltésre kerülnek a meglévő adatokkal.

### <a name="do-not-convert-currency-in-aggregation"></a>Pénznem átváltásának mellőzése összesítéskor

Általában amikor gyermektervet összesít a szülőszinttel, az összegeket automatikusan átváltja a rendszer a tranzakció pénzneméről a szervezet könyvelési pénznemére. Amikor a **Pénznem átváltásának mellőzése összesítéskor** beállítást **Nem** értékre állítja, az összesített összegek az eredeti pénznemben maradnak. Így ez a beállítás lehetővé teszi, hogy pontosabb korrekciók jöjjenek létre, amelyeket érintenek az árfolyam-ingadozások.

### <a name="looking-back-from-a-budget-plan-to-other-modules-that-contributed-to-the-budget"></a>Visszatekintés egy költségvetési tervből a költségvetéshez hozzájáruló egyéb modulokba

Költségvetési tervek generálhatók a kereslet vagy a kínálat előrejelzéseiből, a projektekből és más területekből. A dimenziókészlet szerint költségvetési tervek lekérdezés számos lehetőséget tartalmaz, amelyek lehetővé teszik a költségvetési terv adatainak azonosítását.

### <a name="overwrite-or-append-to-plan-for-allocation-schedules"></a>Az elosztási ütemtervek megtervezése felülírással vagy hozzáfűzéssel

Ha az elosztandó összegeknek több forrása van, akkor megadhatja, hogy az összegek egymáshoz adódjanak. Ebben az esetben az összegek nem írják felül a meglévő összegeket. Ehelyett hozzáadódnak a meglévő összegekhez.

### <a name="default-financial-dimension-set-for-budget-planning-configuration"></a>Alapértelmezett pénzügyi dimenzió a költségvetés-tervezés beállításához

A **Költségvetés-tervezési konfiguráció** oldal mostantól tartalmaz egy mezőt, ahol megadhatja az alapértelmezett pénzügyi dimenziókészletet. Annak ellenére, hogy a mező nem kötelező mező, szükséges lehet bizonyos lekérdezések elvégzéséhez. Szükség lehet rá olyankor is, amikor a jelentések csoportosítással vagy szűréssel szeretné csoportosítani a jelentéseket dimenziók szerint.

### <a name="data-entities"></a>Adatentitások

Számos adatentitás adódott hozzá a költségvetés-tervezés gyors implementálása érdekében. Az entitások lehetővé teszik, hogy számos változtatást Excelben is elvégezhessen. Ennek köszönhetően nem kell egyenként létrehoznia az elemeket az ügyfélen keresztül. Íme az új adatentitások listája:

-   Entitásnév
-   Költségvetési paraméterek
-   Költségvetési terv paramétere
-   Költségvetési tervváltozatok
-   Költségvetési terv szakaszai
-   Költségvetési terv munkafolyamat-szakasza
-   Költségvetési terv felosztási ütemezései
-   Költségvetésiterv-szakasz felosztásai
-   Költségvetési terv prioritásai
-   Költségvetési terv oszlopai
-   Költségvetési terv elrendezésének elemei





