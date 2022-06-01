---
title: Termék- és vevőkeresés a pénztárban (POS)
description: Ez a témakör áttekintést nyújt a Dynamics 365 Commerce termék- és vevőkeresési funkcióján végrehajtott fejlesztésekről.
author: ShalabhjainMSFT
ms.date: 05/25/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: Retail April 2017 update
ms.openlocfilehash: 460c7d3b00421ba43414f7343887edf9b8adad9c
ms.sourcegitcommit: 9dd2d32fc303023a509d58ec7b5935f89d1e9c6d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/26/2022
ms.locfileid: "8806427"
---
# <a name="product-search-and-customer-search-in-the-point-of-sale-pos"></a>Termék- és vevőkeresés a pénztárban (POS)

[!include [banner](includes/banner.md)]

A modern pénztár (MPOS) és a felhőpénztár (CPOS) könnyen használható termék- és vevőkeresési funkciót biztosítanak. Mivel a keresési sáv mindig látható az MPOS és a CPOS ablakok tetején, így az alkalmazottak gyorsan megtalálhatják a termékeket és a vevőket.

Az alkalmazottak az aktuális üzlethez kapcsolódó szortimentekben és katalógusokban kereshetnek termékeket. Emelletta vállalatban található üzletekhez kapcsolódó szortimentekben és katalógusokban is kereshetnek. Ezért a pénztárosok értékesíthetnek és visszaküldhetnek az üzlet szortiment kívül eső termékeket. Ehhez hasonlóan az alkalmazottak kereshetnek a jelenlegi vagy a vállalat bármely más üzletével társított vevőket. Ezenkívül az alkalmazottak kereshetnek a fölérendelt szervezet bármely másik vállalatához társított vevőket.

## <a name="product-search"></a>Termékkeresés

A termékek keresése alapértelmezés szerint az üzletszortiment alapján történik. Az ilyen típusú keresés *helyi termékkeresés* néven ismert. Azonban az alkalmazottak egyszerűen átválthatnak bármelyik az aktuális üzlethez társított katalógusra, illetve keresést végezhetnek másik üzletben. Az ilyen típusú keresés *távoli termékkeresés* néven ismert. A katalógus megváltoztatásához válassza a **Kategóriák** gombot a lap bal oldalán. A megjelenő ablak tetején válassza a **Katalógus módosítása** gombot, és a tallózáshoz válasszon a rendelkezésre álló katalógusok közül. A rendszer megkeresi a termékeket a kijelölt katalógusban.

A **Katalógus módosítása** oldalon az alkalmazottak egyszerűen kiválaszthatnak minden üzletet, illetve végezhetnek keresést termékekre minden üzletben.

![A katalógus módosítása.](./media/Changecatalog.png "A katalógus módosítása")

A helyi termékkeresés a következő terméktulajdonságokon belül történik:

- Termékszám
- Terméknév
- Leírás
- Dimenziók
- Vonalkód
- Keresési név

### <a name="additional-local-product-search-capabilities-conventional-sql-full-text-search"></a>További helyi termékkeresési lehetőségek (SQL teljes szöveges keresés) 

- A több kulcsszavas keresésnél (például a keresési kifejezések használatával végzett keresésnél), a kiskereskedők beállíthatják, hogy a keresési találatok közé a *bármelyik* keresési feltételnek megfelelő találatok vagy csak az *összes* keresési feltételeknek megfelelő találatok kerüljenek-e be. A funkció beállítása a pénztári funkcióprofilban, a **Termékkeresés** nevű új csoportban érhető el. Az alapértelmezett beállítás **Bármelyik keresési kifejezés egyeztetése**. Ez a beállítás egyúttal az ajánlott beállítás is. A **Bármely keresési kifejezésnek megfelel** beállítás használatakor minden olyan termék megjelenik a találatok között, amely egy vagy több teljes vagy részleges keresési kifejezést tartalmaz. Ezeket az eredményeket a rendszer automatikusan sorrendbe rendezi azon olyan termékek növekvő sorrendjében, amelyeknél a legtöbb a kulcsszóegyezés (teljes vagy részleges).

    Az **Az összes keresési kifejezés egyeztetése** beállítás csak a minden a keresési feltételnek (egészben vagy részlegesen) megfelelő termékeket adja vissza. Ez a beállítás akkor hasznos, ha a a terméknevek hosszúak, és az alkalmazottak csak korlátozott számú terméket akarnak látni a keresési eredmények között. Azonban az ilyen típusú keresésre két korlátozás vonatkozik:

    - A keresés az egyes terméktulajdonságok alapján történik. Például csak azokat a termékeket adja vissza, amelyeknél az összes keresett kulcsszó szerepel legalább egy terméktulajdonságnál.
    - A dimenziók között nincs keresés.
> [!NOTE]
> A pénztár funkció következő **Bármelyik keresési kifejezés egyeztetése**/**Összes keresési kifejezés egyeztetése** funkciói csak a **helyi** termékkeresési élményekre hagyományos SQL teljes szöveges keresés érvényes. Ez a konfiguráció nincs hatással a felhőalapú keresési élményekre. Az új keresőmotor saját speciális algoritmussal rendelkezik, amely támogatja a keresés relevanciáját a termékkeresési eredményekhez. 

- A kiskereskedők a termékkeresést most úgy is beállíthatják, hogy keresési javaslatok jelenjenek meg a terméknevek beírása közben. A funkció egy új beállítása a pénztári funkcióprofilban, a **Termékkeresés** nevű csoportban érhető el. A beállítás neve **Keresési javaslatok mutatása gépelés közben**. A funkció segítségével az alkalmazottak gyorsan megtalálhatják a terméket, amelyet keresnek, mivel nem kell manuálisan beírniuk a teljes nevét.
- A termékkeresési algoritmus mostantól a **Keresési név** terméktulajdonságban is keresi a keresési kifejezéseket.

![Termékjavaslatok.](./media/Productsuggestions.png "Termékjavaslatok")

## <a name="customer-search"></a>Ügyfélkeresés

A vevőkereséssel különböző célokkal kereshetők vevők. Például lehet, hogy a pénztáros szeretné megnézni egy vevő kívánságlistáját vagy beszerzési előzményeit, vagy hozzá akarja adni a vevőt egy tranzakcióhoz. A keresési algoritmus egyezteti a keresési kifejezéseket és a következő vevőtulajdonságokban szereplő értékeket:

- Név
- E-mail cím
- Telefonszám
- Hűségkártya száma
- Cím
- Számlaszám

Ezek közül a tulajdonságok közül a név használható a legrugalmasabban a több kulcsszavas keresésekhez, mivel az algoritmus minden olyan vevőt visszaad, amely esetében egyezés van a keresett kulcsszavakkal. A legtöbb kulcsszónak megfelelő vevők az eredmények tetején jelennek meg. Ez a viselkedés segít a pénztárosoknak olyan helyzetekben, amikor teljes névre keresnek, de a kezdeti adatbeviteli során fel lett cserélve a vezetéknév és a keresztnév. A megfelelő teljesítmény érdekében azonban minden egyéb tulajdonság esetében megmarad a keresési kulcsszavak sorrendje. Ha tehát a keresési kulcsszavak sorrendje és az adatok tárolási sorrendje különbözik, akkor a rendszer nem ad vissza eredményt.

Alapértelmezés szerint a vevő keresése az üzlethez társított vevői címjegyzékekben történik. Az ilyen típusú keresés *helyi vevőkeresés* néven ismert. Azonban az alkalmazottak kereshetnek vevőt globálisan is. Más szavakkal kereshetnek a vállalat üzletei és az összes többi jogi személy között. Az ilyen típusú keresés *távoli vevőkeresés* néven ismert.

Globális kereséshez, az alkalmazottak választhatják az **Eredmények szűrése** gombot az oldal alján, majd a **Keresés az összes üzletben** paramétert a következő ábrán látható módon. Ebben az esetben nem csak a vevők szerepelnek a találatok között. Ehelyett a központ bármely címjegyzékében szereplő összes fél, típusától függetlenül, szintén megjelenik. Ezek a felek a dolgozók, a szállítók, kapcsolattartók és a versenytársak.

> [!NOTE]
> A távoli vevőkereséshez legalább négy karaktert meg kell adni, hogy legyen találat.

A vevőkód nem jelenik meg a más jogi személyektől lekérdezett vevők esetében, mert a jelenlegi vállalatnál nem jött létre vevőkód ezekhez a felekhez. Ha azonban az alkalmazott megnyitja a vevő adatlapot, a rendszer automatikusan létrehozza a vevőkódot az adott félnek, és az üzlet vevői címjegyzékét is társítja a vevővel. Így a vevő a későbbiekben végzett helyi keresésekben is látható lesz.

![Globális vevők keresése.](./media/Globalcustomersearch.png "Globális vevők keresése")

### <a name="additional-local-customer-search-capabilities"></a>További helyi vevőkeresési funkciók

Amikor a felhasználó egy telefonszámot keres, a rendszer figyelmen kívül hagyja a különleges karaktereket (például a szóközöket, kötőjeleket és zárójeleket), amelyeket a vevő létrehozásakor esetleg hozzáadtak. Ezért a pénztárosoknak nem kell többé a telefonszámformátum miatt aggódniuk, amikor keresnek. Ha például egy vevő telefonszámát 123-456-7890 formában rögzítették, a pénztáros kereshet a vevőre az **123-456-7890** vagy az **1234567890** beírásával, ill. részlegesen a telefonszám első néhány számának részbeni megadásával.

> [!NOTE]
> A vevő több telefonszámmal és több e-mail-címmel is rendelkezhet. A vevőkeresési algoritmus ezekben a másodlagos e-mail-címekben és telefonszámokban is keres, de a vevőkeresési eredmények oldalon csak az elsődleges e-mail-cím és a telefonszám jelenik meg. Ez némi zavart okozhat, mivel a visszaküldött vevőeredmények nem mutatják a keresett e-mail-címet vagy telefonszámot. A jövőbeli kiadásban a vevőkeresési eredmények képernyőjén igyekszünk megmutatni ezeket az adatokat.

A hagyományos vevőkeresés időigényes lehet, mivel több mező között keres. Ehelyett a pénztárosok kereshetnek a vevő egyik tulajdonságra, például a névre, az e-mail-címre vagy a telefonszámra. A vevőkeresési algoritmus által használt tulajdonságok együttes neve: *vevőkeresési feltételek*. A rendszergazda egyszerűen konfigurálhat egy vagy több kritériumot olyan rövidítésként, amelyek megjelennek a pénztárban. Mivel a keresés egyetlen feltétel korlátozódik, csak a releváns keresési eredmények jelennek meg, és a teljesítmény sokkal nagyobb, mint a szokásos vevő keresés teljesítménye. Az alábbi ábra mutatja a pénztár vevőkeresési rövidítéseit.

![Vevők keresése – parancsikonok.](./media/SearchShortcutsPOS.png "Vevők keresése – parancsikonok")

Keresési feltételek parancsikonokként történő beállításához a rendszergazda nyissa meg a **Kereskedelmi paraméterek** oldalt a Commerce szolgáltatásban, majd a **Pénztári keresési feltételek** fülön válassza ki a feltételeket, amelyeket szeretne parancsikonokként megjeleníteni.

![Keresési rövidítések konfigurálása.](./media/ConfigureShortcutsAX.png "Keresési rövidítések konfigurálása")

> [!NOTE]
> Ha túl sok rövidítést ad hozzá, a pénztár keresés sávjának legördülő menüje zsúfolttá fog válni, ami hatással lehet a keresés használhatóságára az alkalmazott számára. Javasoljuk, hogy csak annyi rövidítést adjon hozzá, amennyire szüksége van.

A **Megjelenítési sorrend** mező határozza meg, hogy melyik rövidítések jelennek meg a pénztárban. A látható feltételek alapból rendelkezésre álló tulajdonságok, amelyeket a vevőkeresési algoritmus a vevők keresésére használ. A partnerek azonban egyedi tulajdonságokat is hozzáadhatnak keresési rövidítésként. Ha egyéni tulajdonságokat kíván keresési rövidítésként hozzáadni, a rendszergazdának ki kell terjesztenie az ügyfélkeresési feltételekhez használt kiterjeszthető felsorolást (enum), majd meg kell jelölnie a partner egyedi tulajdonságait rövidítésekként. A partnerek felelősek azon kód megírásáért, amely találatokat biztosít, amikor amikor egyéni rövidítéseiket keresésekre használják.

A parancsikonok fordítását akkor kell megadni, ha a pénztárban meg szeretné adni a parancsikonokat. Ha a csatorna nyelve eltér a rendszer alapértelmezett nyelvtől, akkor mindegyik parancsikon fordítását a várt nyelven kell definiálni. A fordításokat úgy adhatja meg, hogy az egyes parancsikonok **fordítását** kiválasztja. 

> [!NOTE]
> Az egyéni tulajdonság, amelyet hozzáadnak a felsoroláshoz, nem befolyásolja a normál vevői keresési algoritmust. Más szóval a vevőkereső algoritmus nem keres az egyéni tulajdonságban. A felhasználók csak akkor használhatják az egyéni tulajdonságokat keresésre, ha az adott tulajdonság hozzá van adva rövidítésként, vagy ha az alapértelmezett keresési algoritmust felülbírálják.

A kiskereskedők a pénztárban is beállíthatják az alapértelmezett vevőkeresési módot a **Keresés az összes üzletben** lehetőségre. Ez akkor lehet hasznos, ha azonnal kell keresni a pénztáron kívül létrehozott vevők között (például az elosztási feladat futtatása előtt). Ehhez a kiskereskedőnek be kell kapcsolnia az **Alapértelmezett vevőkeresési mód** lehetőséget a pénztár funkcióprofilban. Miután a beállítás értéke **Igen**, minden vevőkeresési kísérlet valós idejű hívást indít a központba.

A teljesítménnyel kapcsolatos váratlan problémák megelőzése érdekében ezt a beállítást a **CUSTOMERSEARCH_ENABLE_DEFAULTSEARCH_FLIGHTING** tesztelési jelző mögé rejtettük. Így a felhasználói felület **Alapértelmezett vevőkeresési mód** beállításának megjelenítéséhez a kiskereskedőnek támogatási jegyben kell kérnie a felhasználói tesztelést (UAT) és a termelési környezet használatát. Miután megkapjuk a jegyet, a mérnöki csapat segít a kiskereskedőnek, hogy nem termelési környezetben történő teszteléssel tudja felmérni a teljesítményt, és végre tudja hajtani a szükséges optimalizációt.

## <a name="cloud-powered-customer-search"></a>Felhőalapú vevőkeresés

Az Azure Cognitive Search szolgáltatást használó ügyfélkeresési funkció nyilvános előzetes verziója megjelent a Commerce 10.0.18 kiadás részeként. A teljesítmény javítása mellett a szolgáltatás felhasználói a részletgazdagság és jobb relevanciafunkciók nyújtotta előnyöket is élvezhetik. A teljesítményjavasítások különösen hasznosak, amikor a pénztár globális keresési funkcióját (Keresés az összes üzletben) használja. Ennek az az oka, hogy a keresési eredményeket nem a Commerce központi felület adataiból, hanem az Azure Search indexből kell lekérni. 

### <a name="enable-the-cloud-powered-search-feature"></a>A felhőalapú keresési funkció engedélyezése

> [!NOTE]
> A Commerce központi felületére és a Commerce Scale Unit 10.0.18-as verziójára egyaránt szükség van. A pénztár frissítése nem kötelező.

Ha engedélyezni szeretné a Commerce központi felületén a felhőalapú keresés funkciót, kövesse az alábbi lépéseket.

1. Lépjen a **Rendszerfelügyelet \> Munkaterületek \> Funkciókezelés** részre.
1. Keresse meg és válassza ki az **(Előzetes verzió) felhőalapú vevőkeresés** funkciót, majd válassza az **Engedélyezés most** lehetőséget.
1. Kattintson a **Retail és Commerce > Központ beállítása > Kereskedelmi ütemező > Kereskedelmi ütemező inicializálása** lehetőségre, és válassza az **OK** gombot az új **1010_CustomerSearch** feladatnak az **Elosztási ütemezés** képernyőn való megjelenítéséhez.
1. Ugorjon a **Retail és Commerce > Retail és Commerce IT > Elosztási ütemezés** pontra.
1. Futtassa a **1010_CustomerSearch** feladatot. Ez a feladat közzéteszi a dátumot az Azure Search indexben. Amikor az index közzététele befejeződik, a feladat állapota **Alkalmazva** lesz.
1. Miután a **1010_CustomerSearch** feladat állapota **Alkalmazva**, futtassa az **1110 – globális konfiguráció** feladatot, hogy frissítse a **Funkciókezelés** újonnan engedélyezett funkciójának pénztárcsatornáit.
1. Ezt követően futtassa az **1010_CustomerSearch** feladatot, hogy a vevőfrissítéseket rendszeres időközönként a keresési indexbe küldje.

> [!NOTE]
> A kezdeti index közzétételéhez az **1010_CustomerSearch** több órát is igénybe vehet, mivel az összes vevőrekordot elküldi az Azure Search indexbe. A későbbi frissítések csak néhány percig tartanak. Abban az időszakban, amikor a felhőalapú keresési funkció engedélyezve van, de az index közzététele még nem fejeződött be, a pénztárból történő vevőkeresés alapértelmezés szerint a meglévő SQL-alapú keresést használja. Így garantálható, hogy az áruházi műveletek nem szakadnak meg.

### <a name="functional-differences-from-the-existing-search"></a>A meglévő kereséshez képesti funkcionális eltérések

Az alábbi lista bemutatja, hogy miben különbözik a felhőalapú vevőkeresési funkció a meglévő keresési funkciótól. 

- A Commerce központi felületén létrehozott és szerkesztett vevőket a rendszer az Azure Search indexbe küldi az **1010_CustomerSearch** feladat futtatásakor. Az index frissítéséhez legalább 15–20 perc szükséges. A pénztárfelhasználók a Commerce központi felületén bekövetkező frissítések után 15–20 perccel kereshetnek új vevőket (vagy a frissített információk alapján kereshetnek). Ha az üzleti folyamat megköveteli, hogy a Commerce központi felületén létrehozott vevők azonnal kereshetők legyenek a pénztárban, akkor előfordulhat, hogy ez nem a megfelelő szolgáltatás az Ön számára.
- A pénztárban létrehozott új vevőket a rendszer elküldi az Azure Search indexbe a Commerce Scale Unit alkalmazásból, és azonnal bármelyik üzletben kereshetőkké válnak. Ha viszont be van kapcsolva a Vevők aszinkron létrehozása funkció, a rendszer az új vevőrekordokat nem teszi közzé a Commerce Scale Unit alapján az Azure Search indexben, és nem kereshetők a pénztárból addig, amíg a vevőadatokat nem szinkronizálja a Commerce központi felületével és nem generál vevői adatokat az aszinkron vevőkre vonatkozóan. Az **1010_CustomerSearch** feladat ezután tudja elküldeni az Aszinkrfon vevőrekordokat az Azure Search indexbe. Átlagosan 30 percnek kell eltelnie ahhoz, hogy keresni lehessen az újonnan létrehozott Aszinkron vevők között a pénztárban. Ez a becslés feltételezi, hogy az **1010_CustomerSearch**, a **P-feladat** és a **Vevők és üzleti partnerek szinkronizálása aszinkron módból** feladatok futtatása 15 percenként történik.
- A felhőalapú keresés a másodlagos e-mail-címeket és a vevők telefonszámát is keresi, de jelenleg a vevőtalálatokban csak az elsődleges telefonszám és az elsődleges e-mail-cím látható. Első látásra úgy tűnik, hogy nem releváns keresési eredmények születtek, de ha a keresési eredmények között megkeresi a másodlagos e-mail-címet és a vevő telefonszámát, ellenőrizheti, hogy a keresett kulcsszó vevői egyezést eredményezett-e. A félreértések elkerülése érdekében azt tervezik, hogy javítják a keresési eredmények oldalt, hogy a felhasználók könnyen meg tudják érteni egy keresési eredmény létrejöttének okát.
- A szolgáltatásra nem vonatkozik az a követelmény, hogy a globális keresésben (Keresés az összes üzletben) legalább négy karaktert kell használni.

> [!NOTE]
> Az Azure Cognitive Search szolgáltatással használt vevőkeresési funkció előzetes verziója korlátozott régiókban érhető el. A vevőkeresési funkció a következő régiókban *nem* érhető el:
> - Brazília
> - India

[!INCLUDE[footer-include](../includes/footer-banner.md)]
