---
title: "Újdonságok és változások a Dynamics AX 7.0 (2016. február) architektúrájában"
description: "Ez a leírás ismerteti az új vagy módosított a 7.0 alkalmazásverziójú Microsoft Dynamics AX szolgáltatásokat. Ez a 2016 februárjában megjelent verzió tartalmazza mind a platform, mind pedig a pályázat szolgáltatásait."
author: sericks007
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 91243
ms.assetid: 515bc6e7-a85d-4995-95c6-6cab6c8aa0f9
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 3ee5334c87b2b0acae2afa6882feca63e3b9cc8e
ms.openlocfilehash: cdd8acea22fb3298d1d0e7ccce0ca42c1427fe80
ms.contentlocale: hu-hu
ms.lasthandoff: 12/18/2018

---

# <a name="whats-new-or-changed-in-dynamics-ax-70-february-2016"></a>Újdonságok és változások a Dynamics AX 7.0 (2016. február) architektúrájában

[!include [banner](../includes/banner.md)]

Ez a leírás ismerteti az új vagy módosított a 7.0 alkalmazásverziójú Microsoft Dynamics AX szolgáltatásokat. Ez a 2016 februárjában megjelent verzió tartalmazza mind a platform, mind pedig a pályázat szolgáltatásait.

## <a name="cost-management"></a>Költségkezelés

<table>
<thead>
<tr>
<th>Mit lehet tenni?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Miért fontos ez?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Gyors áttekintés a készletegyenlegről, a folyamatban lévő munka (work in progress – WIP) készletegyenlegéről, és a kijelölt pénzügyi időszak készleteinek ki- és beáramlásairól.</td>
<td>Nem alkalmazható</td>
<td>A <strong>Költségadminisztráció</strong> munkaterület tartalmaz egy olyan szekciót, ahol látható a kijelölt pénzügyi időszakra vonatkozó készletkimutatás vagy WIP készletkimutatás. A készlet kimutatása egy adatkészlet-gyorsítótáron alapul, amely alapértelmezés szerint 24 óránként frissül. Az adatkészlet-gyorsítótár beállítható úgy, hogy a felhasználó kézzel frissítheti azt valós idejű jelentésért. Az <strong>Adatfrissítés-állapot kártya</strong> a <strong>Költségkezelés</strong> munkaterületen megmutatja a gyorsítótár utolsó frissítésének idejét.</td>
<td>A költségellenőrök számára fontos, hogy tudják, hogy a készletegyenleg vagy WIP készletegyenleg nő vagy csökken az idő folyamán. A műveleti események osztályozásával a kimutatásban a költségellenőr áttekintést kaphat a készletfolyamatról. Ha a készletet vagy WIP készlet értékelése elszámolóáron történik, a teljes regisztrált eltérés is látható.</td>
</tr>
<tr>
<td>Használja a<strong> Költségkezelés</strong> modult.</td>
<td>Nem alkalmazható</td>
<td>A költségkezelés szakterületként van bevezetve. A költséghez kapcsolódó konfiguráció és áttekintés többfelé volt megtalálható a Készletkezelésben, a Gyártásvezérlésben és a Kötelezettségekben.</td>
<td>Mivel minden, a költségkezeléssel kapcsolatos feladat egyetlen modulban összepontosul, így könnyebb a költségellenőröknek fenntartani a rendszert.</td>
</tr>
<tr>
<td>A készletkönyveléshez kapcsolódó feladási típusok és a termelés könyvelése frissítve lettek.</td>
<td>Az <strong>InventPosting</strong>, <strong>Erőforrás</strong>, <strong>ResourceGroup</strong>, és <strong>ProductionGroup</strong> képernyőkön lévő címkék nincsenek mindig összehangolva a ténylegesen használt <strong>LedgerPostingType</strong> címkékkel. A címkékben használt kifejezések megértése nem könnyű.</td>
<td>Az <strong>InventPosting</strong>, <strong>Erőforrás</strong>, <strong>ResourceGroup</strong>, és <strong>ProductionGroup</strong> képernyőkön lévő címkék nincsenek mindig összehangolva a ténylegesen használt <strong>LedgerPostingType</strong> címkékkel. Az összes címke is átnevezésre került, hogy a címkék megegyezzenek a működési eseményekkel. Vegye figyelembe, hogy a tényleges feladási logika még nem módosult.</td>
<td>Célszerűbb a rendszer komfigurálása, mert az új címkék azokhoz a működési eseményekhez kapcsolódnak, amelyek ezt a feladástípust használják.</td>
</tr>
<tr>
<td>A beszerzési ár, a költség és az eladási ár importálása/exportálása Microsoft Excel-ből vagy egy költségszámítási verzióból.</td>
<td>Nem lehet megfelelően importálni árakat vagy a költségeket a költségszámítási verzióba, mivel az adatmodell egy InventDim azonosítót kér.</td>
<td>Az adatentitások bevezetése lehetővé teszi egy importálási/exportálási funkció végrehajtását. Ez a funkció lehetővé teszi, hogy a felhasználók árakat vagy költségeket importáljanak/exportáljanak a költségszámítási verzióba.
<ul>
<li>A Beszerzési részlegtől kapott következő évi beszerzési árak teljes listájának importálása.</li>
<li>A költségek és a szokásos eladási árak leküldése a központból egy vagy több értékesítési vállalathoz egyetlen művelettel.</li>
</ul></td>
<td>Jelentős időt takaríthat meg a költségellenőrök számára a rendszer kezelésekor, különösen, ha azoknak a következő pénzügyi évre előre meghatározott költségek kezelését kell végezniük.</td>
</tr>
<tr>
<td>Gyors áttekintési lehetőséget nyújt a készlet-egyenlegről és költségobjektum átlagos egységenkénti költségéről.</td>
<td>A felhasználónak ki kell nyitnia az aktuális képernyőt, és ki kell választania azokat a készletdimenziókat, amelyek tükrözik a költség-objektumot. Ennek megfelelően a felhasználónak tudnia kell, mely készletdimenziók vannak megjelölve a pénzügyi készlethez az adott termékhez.</td>
<td>Új <strong>Költségobjektum</strong> lap csatlakozik. Alapértelmezés szerint ez a lap megmutatja az összes költségobjektumok, amelyek a termékhez kapcsolódnak. A lap megjeleníti az aktuális készletmennyiséget, az értékét és átlagos egységenkénti költséget költségobjektum szerint.</td>
<td>Eltávolít néhány összetettségét, és könnyebb lehet a költségellenőrnek lenni.</td>
</tr>
<tr>
<td>Használja az új <strong>Költségtételek</strong> lapot a készlet ellenőrzése során.</td>
<td>Bonyolult lehet készletellenőrzést végrehajtani a bejegyzett készlettranzakciókon és a kapcsolódó elszámolásokon, mivel ugyanezek a tranzakciók lehetnek ténylegesek vagy pénzügyiek.</td>
<td>A <strong>Költségtételek</strong> lap új lehetőséget kínál a készlettranzakciók megjelenítésére.
<ul>
<li>A tranzakciók időrendi sorrendben jelennek meg.</li>
<li>Csak a költségekhez hozzájáruló tranzakciók szerepelnek.</li>
<li>Nincs tényleges költség- vagy pénzügyi költség-fogalom.</li>
<li>Nincs tényleges mennyiség- vagy pénzügyi mennyiség-fogalom.</li>
<li>A költségek fokozatosan vannak hozzáadva.</li>
</ul></td>
<td>Jelentős időt takaríthat meg a költségellenőrök számára ha azoknak készletellenőrzést kell végrehajtaniuk a tranzakció szintjén.</td>
</tr>
<tr>
<td>Használja az új <strong>Termelési WIP-kimutatás</strong> párbeszédpanelt, hogy megjelenítse az egyes termékekre vonatkozó, halmozott költségekről szóló kimutatást.</td>
<td>Nem alkalmazható</td>
<td>A WIP-kimutatás egy adott termelési rendelés összesített WIP egyenlegét jeleníti meg megfelelő költségkategóriába csoportosítva. Egy diagram időrendi sorrendben megjeleníti, hogy a működési feladások hogyan befolyásolták a WIP-kimutatást.</td>
<td>Jelentős időt takaríthat meg a költségellenőrök számára, mikor egy adott termelési rendelés aktuális WIP-egyenlegét kell megismerniük, vagy azt kell megtudniuk, hogy mennyi anyag lett felhasználva a rendeléshez.</td>
</tr>
<tr>
<td>Használja a Költség összehasonlításának megtekintése funkciót, amely a termelési rendelésen lett bevezetve. A funkció megkönnyíti a termelési rendeléshez kapcsolódó költségek összevetését.</td>
<td>A felhasználó csak becsült költségeket és realizált költségeket tud összehasonlítani. Az összehasonlítás a legalsó szinten végezhető el.</td>
<td>A költség-összehasonlító funkcióval a költségellenőrök az alábbi adatokat hasonlítják össze:
<ul>
<li>Aktív költség vs. Becsült költség = Tervezési eltérés</li>
<li>Becsült költség vs. Realizált költség = Termelési eltérés</li>
<li>Tervezési eltérés + Termelési eltérés = Teljes eltérés</li>
</ul>
Ez a funkció a gyártott cikkhez rendelt költségszámítási módszerektől függetlenül működik. Alapértelmezés szerint a diagram költség-összehasonlítást költségcsoport-típusonként mutatja. A diagram segítségével a felhasználók részletesebb szintekre léphetnek.</td>
<td>Lehetővé teszi, hogy a költségellenőrök vagy a vezetőkkel elemezzék, honnan származnak a termelési különbözetek, és mi okozza őket.</td>
</tr>
</tbody>
</table>

## <a name="developer"></a>Fejlesztő

| Mit lehet tenni? | Dynamics AX 2012 | Dynamics AX 7.0 | Miért fontos ez? |
|------------------|------------------|-----------------|------------------------|
| Olyan webalapú megoldások létrehozása a felhőben, amelyek elérhetők sok eszközön. | Nem érhető el. | A Dynamics AX jelenlegi verziója egy új webalapú ügyfélen és ügyfél-keretrendszer alapul. | Végfelhasználók számára következő generációs megoldásokkal szolgálhat. |
| A Microsoft Visual Studio használatával fejlesztheti a megoldásokat. | A Microsoft MorphX a fő fejlesztői környezet, de néhány változás a Visual Studio alkalmazásban következik be. | A Visual Studio az egyetlen fejlesztői környezet. | Megmaradtak az ismerős AX 2012 fogalmak, és azok problémamentesen igazodnak a Visual Studio keretéhez és paradigmáihoz. Lehetővé teszi a szokásos együttmáködést az egyéb .NET nyelvekkel és projektekkel. |
| Állítsa össze az egységes köztes nyelvet (Common Intermediate language, CIL) az összes funkcióhoz. | Az X ++ fordítása: p-kód. | A vadonatúj X ++ fordító minden funkcióhoz generál CIL-t. A CIL ugyanaz a közvetítő nyelv, amelyet más .NET-alapú nyelvek használnak. | A CIL gyorsabb, hatékonyan tud a felügyelt dinamikus csatolású könyvtárakban (DLL) lévő osztályokra hivatkozni, és .NET segédprogramok nagyszámú eszközalapján futtatható. |
| Üzletiintelligencia-jelentések és vizualizációk beágyazása a Microsoft Dynamics AX ügyfélbe. | Nem érhető el. | Könnyen elsajátítható és folyékony képi megjelenítés létrehozása. | Az Üzleti intelligencián alapuló döntéshozatali információkkal szolgál. |
| Integráció a Microsoft Office Outlook programmal | Nem érhető el. | Az új lehetőségek közé tartozik az Excel Data Connector alkalmazás, a **Munkafüzettervező** lap, az API exportálása és a Dokumentumkezelés. | Termelékenységmegoldásokat hozhat létre a végfelhasználói számára. |
| Az építés, a tesztelés és a telepítés automatizálása. | Részben elérhető | Telepítse a fejlesztői topológiát a Fejlesztő és az Építő virtuális gép használatával. Virtuális gép Építás automatikus beállítása a Visual Studio Online-ból (VSO) származó modulok felfedezésére, építésére és tesztek futtatására. A C\# és az X ++ modul fordítása és hivatkozások támogatottak. | A tesztelés és ellenőrzések költségének és munkájának csökkentésével növeli a fejlesztői termelékenységet. |
| A felülrétegzés és a kiterjesztés testreszabása. | Kiterjesztések nem érhetők el. | A Dynamics AX jelenlegi verziója rendelkezik egy új testreszabási modell-lel. | Testre szabhatja azoknak a modellelemeknek a forráskódját és metaadatait, melyeket a Microsoft vagy harmadik fél Microsoft-partnerek szállítanak le. |
| Új vezérlőelemek és felhasználói felület elemek építése az X++ és modern webes keretrendszer használatával. | Az egyéni vezérlők olyan külső keretrendszerekre támaszkodnak, mint például a Microsoft ActiveX és a Windows megjelenítési alaprendszer (WPF). | Célszerűbb vezérlőelemeket építeni az aktuális verzióba. Az X ++ keretrendszer alkalmazás működésére és az üzleti logikára használható, és a HTML/JavaScript-alapú ügyfél lehetővé teszi a modern képi megjelenítést. | A vezérlőket ki lehet úgy alakítani, hogy úgy nézzenek ki és viselkedjenek úgy, mint a Dynamics AX kulcsrakész (OOB) vezérlők. |
| Értékeljen és végezze a finomhangolást új eszközök használatával. | A PerfSDK, az Adatbővítő eszközkészlet, a Trace Parser webalkalmazás és a PerfTimer nem érhetők el. | A PerfSDK, az Adatbővítő eszközkészlet, a Trace Parser webalkalmazás és a PerfTimer új. | A szoftverfejlesztő készlet (SDK) segítségével tesztelheti és ellenőrizehti az összes kritikus üzleti folyamat teljesítményét egyfelhasználós, szükség esetén több felhasználó tesztfuttatásban. Az Adatbővítő eszközkészlettel megfelelően kibővítheti az összes teljesítménytesztet, amelyekben az alapadatokat és a tranzakciós adatokat megfelelő módon ki kell bontani. A Trace Parser segítségével ellenőrizheti az egyfelhasználós teljesítménytesztet vagy többfelhasználós futtatást. A PerfTimer segítségével ellenőrizheti, hogy van-e olyan lekérdezés, vagy bármilyen meghatározott metódushívás, amely teljesítménybeli problémát okoz. Ilyen módon nincs szükség követésre és nincs szükség rá, hogy mindent részletesen elemezzen. |
| Az OData használatával elérhetővé teszi a frissíthető megjelenítést. | Nem érhető el. | A Dynamics AX jelenlegi verziója bevezet egy nyilvános OData szolgáltatási végpontot, amely lehetővé teszi a Dynamics AX adataihoz való egységes hozzáférést sokféle ügyfél számára. | Az Ön megoldásai kapcsolatba léphetnek a RESTful szolgáltatásokkal, látható módon megoszthatnak adatokaz, és széles integrációt engedélyezhetnek a HTTP veremprotokol használatával. |
| használja ki a business connectort, hogy üzleti logika szerzője legyen és támogassa az integrációs eseteket. | A business connector a felügyelt kódból X ++ kód hívására érhető el. Javasoljuk, hogy csak akkor használja a business connectort, ha üzleti logika szerzője szeretne lenni a C\#-ben, integrációs forgatókönyveknél ne. | A business connector már nem támogatott. A szerzői követelményt az X++ felügyelt kódba való fordítása biztosítja. Ezért az interop egyszerűbb. Az integrációs esetek az OData használatával teljesülnek. | A business connector ettől az időponttól kezdve nem használhatja. |
| Válassza ki a méretet (vagyis tizedes jegyek számát) a valós adatbázismezőkön és a kiterjesztett adattípusokon (EDT). | A 16. méret az alapértelmezett méret és a fejlesztő által nem módosítható. | A kiterjesztett adattípusok és mezők olyan mérettulajdonsággal rendelkeznek, amelyet alkalmazni lehet az egyes mezőkhöz és az EDT-hez. Az alapértelmezett 6-ra és nem 16-ra van beállítva. | Az NCCI táblákkal (a memóriában lévő támogatás az SQL-ben) a teljesítmény nagyságrendekkel gyorsabb kisebb méret használata esetén. Módosítsa a méretet úgy, ahogyan az egyes mezők használata megkívánja. |

## <a name="financial-management"></a>Pénzgazdálkodás

<table>
<thead>
<tr>
<th>Mit lehet tenni?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Miért fontos ez?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Számlastruktúrák exportálás a Microsoft Excel programba.</td>
<td>Nem érhető el.</td>
<td>Most már kijelölhet egy számlastruktúrát és exportálhatja az Excel programba.</td>
<td>Számos vevő kérte számlastruktúrák exportálásának lehetőségét az Excel programba a könnyebb szűrés miatt.</td>
</tr>
<tr>
<td>Olyan főkönyvek és speciális szabálystruktúrák megjelenítése, amelyek egy számlastruktúrával vannak társítva egyetlen oldalon.</td>
<td> A felhasználónak több képernyőre kell navigálnia a használatban lévő főkönyv és számlastruktúra megtekintéséhez.</td>
<td>A számlastruktúra laphoz adatterületek vannak hozzá adva.</td>
<td>Könnyebb a fontos információkat elérni, ha a számlastruktúrák meg vannak határozva és szerkesztve.</td>
</tr>
<tr>
<td>Az egyetlen lapon lévő számlatükörrel társított főkönyvek megtekintése.</td>
<td>A felhasználó minden vállalathoz el kell navigálnia, és meg kell nyitnia a főkönyv képernyőt, hogy megtekinthesse a főkönyvhöz társított számlatükröt.</td>
<td>A <strong>Számlatükör</strong> lapjához adatterületek vannak hozzáadva.</td>
<td> Könnyebb a fontos információkat elérni, ha a számlatükrök meg vannak határozva és társítva vannak.</td>
</tr>
<tr>
<td>Zárólap-helyesbítések és a záró tranzakciók megtekintése külön oszlopokban a <strong>főkönyvi kivonat</strong> listaoldalán.</td>
<td>A felhasználó mindkét típusú tranzakciót egy oszlopban látja.</td>
<td>Egy további paraméter hozzá lett adva a <strong>főkönyvi kivonat</strong> listaoldalhoz.</td>
<td>Az adatok tömörebb elemzését teszi lehetővé, és néhány országban/régióban a hatósági jelentés is megköveteli.</td>
</tr>
<tr>
<td>Használja az új <strong>Globális általános napló</strong> oldalt.</td>
<td>Nem érhető el.</td>
<td>Az új <strong>Globális általános napló</strong> lapon általános naplókat táplálhat be. A laphoz tartozó jogosultságok hozzáadódnak a <strong>Könyvelő</strong> szerepkörhöz.</td>
<td>Lehetővé teszi a megosztott szolgáltatás könyvelőknek, hogy vállalatok közötti általános naplókat tápláljanak be anélkül, hogy el kellene navigálniuk az űrlapról vagy meg kellene változtatniuk a cégkontextust.</td>
</tr> 
<tr>
<td>Használja az új <strong>Könyvelési források böngészője </strong>oldalt.</td>
<td>A Dynamics AX 2012 R3 CU10-ből érhető el.</td>
<td>Új <strong>Könyvelési források böngészője</strong> oldal, és navigációs műveletek erre az oldalra a <strong>Főkönyvi kivonat</strong> listalapon és a <strong>Bizonylattranzakciók</strong> oldalon.</td>
<td>Lehetővé teszi a főkönyvi kivonat forrására vagy a főkönyv egyes könyvelési tételeire vonatkozó legrészletesebb információk megtekintését, vagy ad-hoc elemzését.</td>
</tr>
<tr>
<td>Adjon hozzá további feladási rétegeket.</td>
<td>További feladási rétegek hozzáadása fejlesztői élmény volt.</td>
<td>Jelenleg tíz feladási réteg érhető el.</td>
<td>A legtöbb ügyfél további feladási rétegeket ad hozzá.</td>
</tr>
<tr>
<td>Használja a Kapcsolódó bizonylat opciót.</td>
<td>Nem érhető el.</td>
<td>A Kapcsolódó bizonylat opcióval a felhasználók megtekinthetik az ellenoldali vállalati a bizonylatot vállalatközi tranzakciók könyvelése során. A kapcsolódó bizonylatok menüből elérhetőek a részletek, és az ellenoldali vállalati bizonylat is könnyen elérhető.</td>
<td>Vállalatközi tranzakciók feladásakor a felhasználók nem fértek hozzá és nem tudták nyomon követni az ellenoldali vállalatnál könyvelt bizonylatot.</td>
</tr>
<tr>
<td>Tömeges pénzügyi időszak zárás</td>
<td>Nem érhető el.</td>
<td>A felhasználók több cégre vonatkozóan egyszerre frissíthetik a modulhozzáférést és változtathatják meg a periódusállapotot.</td>
<td>Ezen szolgáltatás bevezetése előtt a felhasználóknak váltogatniuk kellett az általuk bejelentkezett vállalatok között, navigálniuk a főkönyv-naptár űrlapon és egyesével frissíteni a modulhozzáféréseket és a periódusállapotokat.</td>
</tr>
<tr>
<td>Az árfolyamok Oanda technológiával rendelkeznek.</td>
<td>Az importárfolyam-kalkulátor Oanda-ráták importálásra való konfigurálása fejlesztői élménynek bizonyult.</td>
<td>Ha a felhasználó rendelkezik Oanda-kulccsal, azt megadhatják az árfolyamkalkulátor konfigurálásakor.</td>
<td>A felhasználók az Oanda-ból előre meghatározott időközönként importált átváltási árfolyamok használatával élvezhetik a kulcsrakész (OOB) funkció előnyeit.</td>
</tr>
<tr>
<td>A méretek, jellemzők, dátumok és forgatókönyvek alapján (Management Reporter) a pénzügyi jelentések szűrhetők.</td>
<td> A felügyeleti jelentéskészítő jelentések minden szűrése a jelentés tervén keresztül történik. Például, ha egy megtekintési jogosultságokkal rendelkező felhasználó szeretne megtekinteni egy másik dátumú jelentést, akkor egy jelentéstervezőnek módosítást kell végrehajtania.</td>
<td>Jelentésbeállítások jelentek meg, így különböző szűrők alkalmazhatók, ha egy felhasználó megtekinti a jelentést. Ekkor új jelentés jön létre ezen szűrők alapján.</td>
<td>A pénzügyi jelentések fogyasztói különböző szűrőket alkalmazhatnak a dimenziókra, dátumokra, atribútumokra és esetekre, a jelentésterveinek frissítése nélkül.</td>
</tr>
<tr>
<td>A pénzügyi jelentések (Management reporter) megtekinthetők a Microsoft Dynamics AX kliensben.</td>
<td>A külön webes ügyfelet használt a Felügyeleti jelentéskészítő jelentések megtekintéséhez.</td>
<td>Minden pénzügyi jelentés elérhető a Dynamics AX ügyfélben. A felhasználó kiválaszt egy jelentést megtekintásre, és az ügyfélben megjelenik a jelentés.</td>
<td>Ekkor megtekintheti a pénzügyi jelentéseket anélkül, hogy másik ügyfélhez/alkalmazáshoz kellene hozzáférnie.</td>
</tr>
<tr>
<td>A pénzügyi jelentések (Management reporter) A Microsoft Dynamics AX kliensben ki is nyomtathatók.</td>
<td>Jelentés nyomtatásakor a böngésző nyomtatási beállításai kerülnek felhasználásra, és csak az kerül kinyomtatásra, amit a felhasználó a képernyőn lát.</td>
<td>A felhasználó kiválaszthatja a jelentés részletességi szintjét és oldalbeállításait a Dynamics AX kliens pénzügyi jelentés Nyomtatás opciójának használatával.</td>
<td>A jelentések kinyomtatásakor nem weblap kerül kinyomtatásra, hanem a nyomtatás aszerint történik, amit a felhasználó elvár.</td>
</tr><tr>
<td>Pénzügyi adatok elemzése a „Pénzügyi teljesítmény felügyelete” csomag használatával a PowerBI tartalomhoz.</td>
<td>Nem érhető el.</td>
<td>A PowerBI.com oldalon válassza az <strong>Adatok átvétele</strong> lehetőséget, majd válassza ki a <strong>Dynamics AX – Pénzügyi teljesítmény</strong> tartalomcsomagot. Adja meg a Dynamics AX végpont URL-címét, hogy megtekinthesse az adatainak az irányítópulton való megjelenését.</td>
<td>A vállalatok három-négy kattintással fontos pénzügyi adatokat tartalmazó PowerBI irányítópultot telepíthetnek. A szervezet személyre szabhatja a tartalmat.</td>
</tr>
<tr>
<td>Pénzügyi időszak lezárási folyamatainak nyomon követése.</td>
<td>Nem érhető el.</td>
<td>A Pénzügyi időszak lezárása konfigurációval zárósablonokat és ütemezéseket lehet létrehozni. Használja a <strong>Pénzügyi időszak lezárása</strong> munkaterületet, hogy nyomon kövesse a záró ütemezéseket több vállalat között.</td>
<td>A munkaterület kiiktatja a manuális rendszereket a záró tevékenységek meghatározásához, ütemezéséhez és kommunikálásához. Ezért csökkenti lezárásig hátralévő napok számát.</td>
</tr>
<tr>
<td>A költségvetés szerinti vs. tényleges egyenleg figyelése, és a főkönyvi előrejelzések létrehozása a <strong>Főkönyvi költségvetések és előrejelzések</strong> munkaterület és további lekérdezési képernyők használatával.</td>
<td>Nem érhető el.</td>
<td> A munkaterület elérhető a Dynamics AX irányítópulton keresztül. Számos új lekérdezési lapokra mutató hivatkozásokat tartalmaz: <strong>Tényleges vs. költségvetés szerinti egyenleg összesítése</strong>, <strong>Költségvetés-ellenőrzési statisztikai összesítő</strong>, <strong>Költségvetési tételjegyzék-bejegyzések</strong>, és <strong>Költségvetési tervek</strong>.</td>
<td>Az új lekérdezési lapok könnyen elérhetővá teszik a költségvetési adatokat. A munkaterület egy helyen kombinálja az összes költségvetés-karbantartási és -felügyeleti feladatot, és így könnyen használható a költségvetési vezetők vagy számviteli vezetők számára.</td>
</tr>
<tr>
<td>Költségvetési tervek és előrejelzések elrendezéseinek létrehozása.</td>
<td>A <strong>Költségvetési terv</strong> dokumentum sorok listájaként jelenik meg, amelyek rendelkeznek érvényességi dátummal és összeggel a pénzügyi dimenziók kombinációihoz. A felhasználónak Excel-sablont kell létrehoznia és használnia a költségvetési terv adatainak PivotTable táblázatban való megtekintéséhez.</td>
<td>Költségvetési tervekhez és az előrejelzésekhez korlátlan számú elrendezés érhető el. Az elrendezésben egyesítheti a kijelölt pénzügyi dimenziókat, a felhasználó által definiált oszlopokat és a többi sorattribútumot (például a megjegyzéseket, a projekteket és tárgyi eszközöket). A felhasználók menet közben válthatnak a költségvetési terv dokumentumelrendezést, és szerkeszthetik az adatokat a kiválaszott elrendezések használatával. A költségvetés-tervezési konfiguráció le van egyszerűsítve az esetmegszorítások kiküszöbölése által, valamint olyan elrendezések segítségével, amelyek meghatározzák, milyen adatokat lehet megtekinteni és szerkeszteni a költségvetési terv dokumentum egyes állomásain.</td>
<td>Ennek segítségével rugalmasan lehet létrehozni és szerkeszteni a költségvetési terveket, az Excel és a Dynamics AX ügyfél együttes használata mellett. Excel-munkafüzetsablonok a Költségvetési terv elrendezésének beállításának használatával lehet létrehozni.</td>
</tr>
<tr>
<td>Nyomtassa ki a <strong>Szállítói számlatranzakciók</strong> jelentést a <strong>Részletes esedékességi lista</strong> jelentésből származó adatok használatával, amely tartalmazza a lejárt határidejű napokat.</td>
<td>Két különböző jelentést kell kinyomtatnia: a <strong>Részletes esedékességi lista</strong> és a <strong>Szállítói számlatranzakciók</strong> jelentést.</td>
<td>A két jelentésen szereplő adatok összevonásával keletkezik a <strong>Szállítói számlatranzakciók</strong> jelentés. A <strong>Részletes esedékességi lista</strong> jelentés be lett szüntetve.</td>
<td>Emiatt nem szükséges két külön, de egymáshoz kapcsolódó jelentést kinyomtatni.</td>
</tr>
<tr>
<td>Hatósági jelentések készítése közvetlenül PDF formátumban.</td>
<td>Először hatósági jelentést kell készítenie egy formátumban, majd exportálnia kell PDF formátumba.</td>
<td>A PDF formátuma a hatósági jelentések alapértelmezett formátuma.</td>
<td>Egységes megjelenítést biztosít mind számítógép képernyőjén, mind a nyomtatott papír alapú példányon.</td>
</tr>
<tr>
<td>Áfa kiegyenlítési folyamat futtatása kötegelt feladatként.</td>
<td>Nem érhető el.</td>
<td>Az <strong>Áfakiegyenlítési időszak</strong> lapon megadhatja, hogy kell-e a kiegyenlítési folyamatot kötegelt módban futtatni.</td>
<td>Olyan időszakokban, amikor sok az adótranzakció, a kiegyenlítési folyamat sok időt vehet igénybe, és előnyösebb lehet, ha a folyamat futtatása kötegelt feladatként a háttérben zajlik.</td>
</tr>
</tbody>
</table>

## <a name="foundation"></a>Alapítvány

<table>
<thead>
<tr>
<th>Mit lehet tenni?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Miért fontos ez?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Az ügyfélhez való hozzáférés bárhol, bármikor.</td>
<td>Az AX 2012 ügyfélprogram teljes űrlapkészletet tartalmaz, de csak azokon a számítógépeken futtatható, amelyeken Microsoft Windows fut, és telepítése szükséges hozzá. A Terminálkiszolgáló gyakran használatos az ügyfélprogrammal, hogy széles (WAN) hálózaton keresztüli hozzáférést tegyen lehetővé. Az Enterprise Portal webes ügyfél csökkentett űrlapkészletet tartalmaz.</td>
<td>A két AX 2012 ügyfelet egyetlen szabványos webes ügyfél váltotta ki, amely az ügyfélprogram teljes feladatkörét ellátja az Enterprise Portal-ügyfél hozzáférhetőségével együtt.</td>
<td>Megakadályozza, hogy a fejlesztési erőfeszítések a két UI platform között kettéosztódjanak. Szokásos webes felületek használatával nincs szükség Terminálkiszolgálóra.</td>
</tr>
<tr>
<td>Legyen eredményes az új Feladatrögzítő használatával.</td>
<td>Az AX 2012 Feladatrögzítő közvetlen hozzáférést kíván a Alkalmazásobjektum-kiszolgáló (AOS) számítógéphez, valamint magasabb szintű jogosultságokat, és nem tartalmaz szerkesztési beállításokat.</td>
<td>Az új Feladatrögzítő közvetlenül a webes ügyfélprogramból használható. A Feladatrögzítőhöz való hozzáférés nem igányel rendszergazdai jogosultságot. A rögzített lépések rögzítés közben tekinthetők meg élőben, új szerkesztési beállítások kerültek bevezetésre, és a Feladatrögzítő a már meglévő Üzleti folyamatmodellező (BPM) eseteken kívül további eseteket is támogat.</td>
<td>Az új Feladatrögzítő korszerű tapasztalatokat tartalmaz és erősíti az új lehetőségeket a Dynamics AX rendszerben. E funkciók közül némelyik már érhető el, és ezeket több követi majd a jövőben.</td>
</tr>
<tr>
<td>Segíti a felhasználókat a rájuk váró, munkaterületekkel való munka jobb megértésében.</td>
<td>A szerepkörfőoldal áttekintést ad a felhasználó munkakörére vonatkozó információkról a vállalatnál vagy a szervezetben.</td>
<td>A munkaterületek egy új koncepció a Dynamics AX-ben, aminek célja a szerepkörfőoldalak lecserélése, mint a feladatok és specifikus oldalakra történő navigáció elsődleges módja. Egy egyoldalas áttekintést nyújtanak az üzleti tevékenységről, és áttekinthetőbbé teszik az aktuális állapotot, a következő feladatokat, és a folyamat vagy felhasználó teljesítményét. A munkaterületek részletesebbek, mint az AX 2012 szerepkörfőoldalak, és a felhasználók hozzáférhetnek több munkaterülethez is hozzáférhetnek.</td>
<td>A munkaterületek célja, hogy növeljék a felhasználói hatékonyságot. A fejlesztőknek a termék által támogatott minden fontosabb „aktivitás” számára külön munkaterületet kell létrehozniuk. Az AX 2012-től örökölt szerepkörfőoldal a Dynamics AX mostani verziójában általában több munkaterülettel lesz helyettesítve.</td>
</tr>
<tr>
<td>Űrlapok válaszképessé tétele a megjelenítési terület vagy készülékméret függvényében.</td>
<td>Az AX 2012-ben az űrlapok tartalma mereven oszlopokban jelent meg, és az űrlap teljes magassága/szélessége nagyrészt az űrlapon található vezérlők függvényében került meghatározásra.</td>
<td>A legújabb Dynamics AX-ben tapasztalható web-re történő váltással az űrlapok méretei már a böngésző megjelenítési területe vagy a készülék mérete alapján kerülnek meghatározásra. A vezérlők és elrendezési paraméterek megváltoztatásra vagy hozzáadásra kerültek a megjelenítési terület méretére való jobb válaszképesség elérése érdekében.</td>
<td>Az űrlap tartalmának hatékonyabban kell tudnia válaszolni, a böngészőn vagy eszközön elérhető megjelenítési terület minél hatékonyabb kihasználása érdekében. A válaszképesség elérése változtatásokat követelhet meg az űrlapok modellezését illetően.</td>
</tr>
<tr>
<td>Minták használata jobb űrlapfejlesztési élmény elérése érdekében.</td>
<td>Az AX 2012-ben az űrlapsablonok képezték az űrlapfejlesztés kiindulópontját, az űrlap stílusától függően. Az Űrlapstílus Ellenőrző, egy opcionális bővítmény, információkkal szolgált arra vonatkozóan, hogy egy adott űrlap hogyan képezhető a hozzá tartozó mintából.</td>
<td>A Dynamics AX jelenlegi verziójában űrlapsémák kerültek bevezetésre. Az űrlapsémák az űrlapsablonok és a Űrlapstílus Ellenőrző kombinációja, így biztosítva szorosan integrált fejlesztői élményt. A sémák az űrlapok szintjén kerülnek definiálásra (mint az AX 2012-ben), illetve a csoport- és lapszinteken további alsémák érhetők el.</td>
<td>A sémákhoz igazodó űrlapoknak sok előnye van, mint például a konzisztensebb felhasználói felületek, egyszerűbb fejlesztés, könnyebb űrlap-feljavítás, valamint nagyobb önbizalom az űrlapelrendezés válaszképességében.</td>
</tr>
</tbody>
</table>

## <a name="help"></a>Súgó

<table>
<thead>
<tr>
<th>Mit lehet tenni?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Miért fontos ez?</th>
</tr>
</thead>
<tbody>
<tr>
<td>A <strong>Súgóra</strong> kattintva hozzáférhet Folyamatsúgóhoz (feladat-útmutatók) és az elméleti témakörökhöz-</td>
<td>Az AX 2012 Súgórendszer helyi webkiszolgálón tárolt HTML témaköröket mutat. Vevők és a partnerek létrehozhatják saját Súgójukat.</td>
<td>A Súgórendszer a Dynamics AX jelenlegi verziójában a Microsoft Dynamics Lifecycle Services (LCS) BPM-ben tárolt feladat-útmutatókat jelenít meg. A Súgórendszer a Microsoft dokumentációs webhelyéről származó témaköröket is megjelenít. További tájékoztatás: <a href="help-overview.md" data-raw-source="[Dynamics AX Help - Getting Started](help-overview.md)">Dynamics AX Súgó – Első lépések</a> és <a href="new-task-guides-available-february-2016.md" data-raw-source="[New task guides available (February 2016)](new-task-guides-available-february-2016.md)">Új feladat-útmutatók érhetők el (2016. február)</a>.</td>
<td>A feladat-útmutató irányított, interaktív tapasztalatot tartalmaz, amely végigvezeti a feladat vagy az üzleti folyamat lépésein. Letöltheti és testreszabhatja a Microsoft által kínált feladat-útmutatókat. A témakör segítségével gyorsabb és rugalmasabb a termékdokumentáció létrehozása, leszállítása, és frissítése. Ezért segítségével garantálható, hogy a legfrissebb technikai információkhoz jut hozzá.</td>
</tr>
</tbody>
</table>

## <a name="human-capital-management"></a>Emberierőforrás-menedzsment

<table>
<thead>
<tr>
<th>Mit lehet tenni?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Miért fontos ez?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Szakértelmek és bizonyítványok kiutalása osztály résztvevőknek a tanfolyam befejezése után.</td>
<td>Ez kézi folyamat.</td>
<td>Tanfolyam befejezése után egy új beállítás érhető el a résztvevői rekordoknak az új szakértelmekkel és bizonyítványokkal való frissítéséhez.</td>
<td>Új és hatékony módot biztosít az alkalmazotti rekordok frissítéséhez.</td>
</tr>
<tr>
<td>Foglalkoztatás gyors ellenőrzése.</td>
<td>Ez kézi folyamat.</td>
<td>A HR részlege gyorsan ellenőrizheti a foglalkoztatást a munkaterület vagy az alkalmazotti oldal használatával.</td>
<td>A HR részlegének nem kell többé sok oldalhoz hozzáférnie, hogy ellenőrizze a beosztáshoz vagy kompenzációs adatokhoz tartozó kezdő dátumot, vezetőt és a hónapokat.</td>
</tr>
<tr>
<td>Hagjya, hogy az alkalmazottak betekintást megtekinthessék. frissítsék, vagy töröljék a rendszer adatait.</td>
<td>Korlátozott megjelenítéssel és frissítési lehetőséggel érhető el.</td>
<td>Ez a funkció engedélyezve van, és lehetővé teszi, hogy az alkalmazottak és alvállalkozók a személyes adatok széles skáláját megtekinthessék. Lehetőség van egy munkafolyamat használatára az adatok létrehozásakor, frissítésekor vagy törlésekor.</td>
<td>Lehetővé teszi, hogy az alkalmazottak maguk felügyeljék adataikat, ami lehet a cím vagy elérhetőség frissítése, egy munkára való jelentkezés, kérdőív kitöltése vagy a a képük frissítése. Ha egy munkafolyamat engedélyezve van, az adatokat felülvizsgálhatja a jóváhagyó vagy automatikusan jóvá lehet hagyni, az Ön üzleti folyamataitól függően.</td>
</tr>
<tr>
<td>Tegye lehetővé, hogy a vezetők megtekintsék vagy szerkesszék az alkalmazottak adatait.</td>
<td>Korlátozott megjelenítéssel és frissítési lehetőséggel érhető el.</td>
<td>A konfigurációs és biztonsági beállításoktól függően a vezetők megtekinthetik vagy szerkeszthetik az alkalmazottak adatait.</td>
<td>Lehetővé válik a vezetők számára, hogy fontos alkalmazott adatokat érjenek el, hogy ezek segítségével jobb döntéseket hozzanak a finanszírozással, a teljesítménnyel és az alkalmazottak fejlesztésével kapcsolatosan.</td>
</tr>
<tr>
<td>A kezelő az önkiszolgáló funkciók előnyei.</td>
<td>Nem érhető el.</td>
<td>A managerek mostantól kérelmeket adhatnak le új emberek (alkalmazottak és megbízottak) felvételére, átcsoportosítására, és elbocsátására. Továbbá a managerek mostantól új pozíció létrehozására, már meglévő pozíció meghosszabbítására, és pozícióváltoztatásra is leadhatnak kérelmeket.</td>
<td>Ezek a forgatókönyvek ezelőtt csak a HR számára voltak elérhetők. Ezen forgatókönyvek elérhetővé tételével a managerek számára könnyebb a szervezet irányítása. Bekapcsolhatók opcionális munkafolyamatok az értékelések és engedélyezések megfelelő szintjének biztosítása érdekében.</td>
</tr>
<tr>
<td>Kompenzációs feldolgozás eredményéhez való hozzáférés.</td>
<td>Az eredmények csak a feldolgozási időpontjában érhetők el.</td>
<td>A kompenzáció-feldolgozási eredmények mostantól a folyamat futtatása után bármikor elérhetők.</td>
<td>Biztosítja a folyamat és a folyamat eredményének kiváló könyvvizsgálatát. Továbbá átfogó áttekintést nyújt az adatokról, az alkalmazotti rekordokat frissítik.</td>
</tr>
<tr>
<td>A juttatások feldolgozásának eredményéhez való hozzáférés.</td>
<td>Az eredmények csak a feldolgozási időpontjában érhetők el.</td>
<td>A juttatások feldolgozási eredményei mostantól a folyamat futtatása után bármikor elérhetők.</td>
<td>Átfogó nézetet ad azokról az adatokról, amelyek a juttatás bejegyzésével és a költségváltozásokkal frissültek.</td>
</tr>
<tr>
<td>Az „Érvényességi dátum” idősor változásainak megjelenítése.</td>
<td>Nem érhető el.</td>
<td>Ez az összehasonlíó eszköz az alkalmazottak, beosztások és feladatok számára érhető el. Átfogó képet ad egy rekordnak az egyik verzióról egy másik verzióra való módosításairól.</td>
<td>Időt takarít meg az Ön számára, amikor az alkalmazottak, a beosztások és a feladatrekordok módosításait kívánja megtekinteni. Gyors összehasonlítást tesz lehetővé két rekirodverzió vagy az összes rekordverzió között, időbeli eloszlás szerint.</td>
</tr>
<tr>
<td>Alkalmazottak megjelenítése a vállalatonként.</td>
<td>Ez kézi folyamat, amely szűréssel hajtható végre.</td>
<td>Az alkalmazotti és alvállalkozói listákat automatikusan szűri a vállalat, ahova bejelentkezett.</td>
<td>Azoknak az alkalmazottaknak a szűrt nézetét adja, akik annál a vállalatnál állnak alkalmazásban, ahova bejelentkezett. Az összes alkalmazott és alvállalkozó szűretlen nézetéhez a dolgozók listája továbbra is elérhető. A Dynamics AX jelenlegi verziójában a rendszer nem változtatja meg a vállalatot, a listán kiválasztott alkalmazott alapján.</td>
</tr>
<tr>
<td>Tanfolyami résztvevők listájának frissítése.</td>
<td>Nem érhető el.</td>
<td>Tanfolyam résztvevői eltávolíthatók a résztvevők listájáról.</td>
<td>Egyszerűen frissítheti azoknak listáját, akik tévedésből regisztráltak egy tanfolyamra.</td>
</tr>
<tr>
<td>Kompenzációs események kezelése csoportban.</td>
<td>Nem érhető el.</td>
<td>Ez a funkció leegyszerűsíti az alkalmazottak kompenzációs módosításainak feldolgozását.</td>
<td>Egyszerű, korszerű folyamatot biztosít az alkalmazotti rekordok kompenzációs munkaterületen keresztüli frissítéséhez, valamint a kapcsolódó lapok frissítéséhez.</td>
</tr>
</tbody>
</table>

## <a name="inventory-management"></a>Készletgazdálkodás

Új funkciókat nem adtuk hozzá.

## <a name="localization"></a>Honosítás

<table>
<thead>
<tr>
<th>Mit lehet tenni?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Miért fontos ez?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Konfigurálja és létrehozza a különböző országok/régiók jogi követelményeinek megfelelő elektronikus dokumentumokat.</td>
<td>Az elektronikus dokumentumok X++-ban vagy XSL átalakítóban (XSLT) vannak kódolva. A formátumkorrekciókhoz fejlesztésre van szükség. Az adatokhoz és formázáshoz való hozzáférés nincs elkülönítve. A korrekciós formátum telepítése új Microsoft Dynamics AX gyorsjavítási csomagot igányel, amely felülírja a meglévő formátumot. Az egyes formátumok egyéni módosításait manuálisan kell bevinni egy új Microsoft Dynamics AX gyorsjavítási csomag forráskódjába.</td>
<td>Az elektronikus jelentés (ER) egy új eszköz, aminek segítségével olyan elektronikus jelentések konfigurálhatók vagy hozhatók létre, melyek a fejlesztő helyett az üzleti felhasználó számára készülnek. Az ER segítségével felállíthatók olyan dokumentumformátumok adatforrásaként szolgáló tartományspecifikus adatmodellek, melyek függetlenek a Microsoft Dynamics AX adatbázisától. Az üzleti felhasználó beállíthatja a formátumok, ezen tartomány-specifikus adatmodellek alapján (például kifizetésekhez, az Intrastat-jelentésekhez vagy adójelentésekhez). A felhasználó állítja be a formátumokat az Excelhez hasonló, egyszerű vizuális eszközök használatával. Az ER jelenleg a szöveg, XML, és Excel formátumú elektronikus dokumentumok generációját támogatja. Ezeket a dokumentumokat egyidejűleg lehet generálni, majd zip fájlokba csomagolni. Adatmodellek és formátumok támogatásának verziókövetése. Formátumverziónak lehet érvényességi időszaka. Minden egyes adatmodell vagy formátumverzió tárolása külön konfigurációban történik, és a partnerekhez és vevőkhöz az LCS keresztül jut el. A partnerek és a vevők testreszabhatják a Microsoft adatmodelleket és formátumokat, vagy létrehozhatják sajátjukat. Az ER elmenti a partner és a vevő konfigurációmódosításait, mint eltéréseket a Microsoft konfigurációihoz képest, ami leegyszerűsíti a Microsoft konfigurációk új verzióinak frissítését. Az LCS használatával a partnerek is megoszthatják adatmodelljeiket és formátumkonfigurációikat más partnerekkel és vevőkkel, akik a későbbiekben testreszabhatják és továbboszthatják azokat. Az eltérések testreszabását és az a könnyű frissítést a teljes testreszabási lánc támogatja.</td>
<td>Az ER egyszerűsíti az olyan elektronikus dokumentumok létrehozását, karbantartását és frissítését, melyek megfelelnek a különböző országok/régiók jogi követelményeinek. Az ER felgyorsítja és megkönnyíti az elektronikusdokumentum-formátumok létrehozásának és módosításának folyamatát. Ezeket a változtatásokat a fejlesztők helyett az üzleti felhasználók is megtehetik. Az ER felgyorsítja és megkönnyíti a partnerek és a vevők számára, hogy formátumaik testreszabásait azokra az új formátumverziókra frissítsék, amelyeket a Microsoft vagy más partnerek adtak ki. Az ER egy közös módot biztosít (az LCS-en keresztül) a Microsoft és a partnerek számára, az elektronikus dokumentum-konfigurációk más partnerek és vevők számára történő kiosztására.. Az ER továbbá megkönnyíti a partnerek és a vevők számára, hogy elektronikus dokumentumformátumaikat saját üzleti követelményeik szerint testreszabják, frissítsék vagy kiosszák.</td>
</tr>
<tr>
<td>(MEX) Mexikói általános forgalmi adó (áfa) hatósági jelentések készítése.</td>
<td>Létre kell hoznia az <strong>Értékesítések és beszerzések ÁFA-ja</strong> jelentést a nem realizált áfa funkció segítségével, hogy a felhasználók az állapot alapján megtalálják a realizált és nem realizált szakaszokhoz tartozó tranzakciókat.</td>
<td>Az <strong>Értékesítési és beszerzési ÁFA</strong> jelentéseket módosították, és most csak úgy veszik tekintetbe a feltételes adó funkciót, ha a nem realizált és a realizált értékesítési adókód meghatározásához megadott kiegyenlítési időszakokat használnak.</td>
<td>Szükséges az áfakódok konfigurációjának módosítása, hogy a felhasználók ezeket a jelentéseket megfelelő módon hozhassák létre. Feltételes áfafunkciót kötelező megadni, és a felhasználónak külön kiegyenlítési időszakokat, nem realizáltat és realizáltat kell konfigurálni, hogy a kapcsolódó szakaszterületeken a tranzakciókat azonosítani lehessen.</td>
</tr>
<tr>
<td>(JPN) Japán tárgyi eszköz gyorsított értékcsökkentés bevallási dokumentum kezelése.</td>
<td>Nem érhető el.</td>
<td>A fontos bevallási adatokat a jobb karbantartás érdekében központilag egyetlen dokumentumban tárolja a rendszer.</td>
<td>A dokumentumok megfeleléseés a kezelés egyszerűsége segít csökkenteni az ellenőrzések és felülvizsgálatok alkalmával felmerülő problémákat.</td>
</tr>
<tr>
<td>(JPN) Ellenőrizze a JBA karaktereket a bankszámlán.</td>
<td>Nem érhető el.</td>
<td>Ellenőrizheti, hogy a kana névmezők csak a JBA banki formátum által engedélyezett karaktereket tartalmazzák.</td>
<td>Ez csökkentheti a felhasználók kifizetési fájlánka létrehozása közben az érvénytelen karakterek miatt létrejövő zavarokat.</td>
</tr>
<tr>
<td>(JPN) Tényleges a japán tárgyi eszköz filléreltérés felzárkóztatása a pénzügyi év végén.</td>
<td>Nem érhető el.</td>
<td>A <strong>Tárgyi eszközök paraméterei</strong> lapon kiválaszthatja, hogy felzárkózik-e a pénzügyi időszak vagy a pénzügyi év végén.</td>
<td>Nagyobb rugalmasságot kínál a helyi gyakorlatok egyeztetésében.</td>
</tr>
<tr>
<td>(JPN) Japán vállalati adóbevallás csatolt táblázatok 16. sorozat létrehozása összesített értéken, a tárgyi eszköz fő típusa szerint.</td>
<td>Nem érhető el.</td>
<td>A tárgyi eszköz értékmodelljein kiválaszthatja, hogy összesít-e a fő típus szerint. Alapértelmezés szerint ez a funkció szolgál az újonnan létrehozott tárgyi eszközökhöz.</td>
<td>A több ezer tárgyi eszközzel rendelkező nagyvállalatoknál az összefoglaló jelentések jelentősen csökkentik a létrehozott jelentések méretét.</td>
</tr>
<tr>
<td>(JPN) Kezdje el kiutalni a Különleges értékecsökkenési tartalékot a következő pénzügyi évből a japán tárgyi eszközökhöz.</td>
<td>Nem érhető el.</td>
<td>A megfelelő rendkívüli értékcsökkenési profillal rendelkező tárgyi eszköz értékmodelljein kiválaszthatja, hogy a kiosztást a következő pénzügyi időszakból vagy a következő pénzügyi évből kezdi.</td>
<td>Nagyobb rugalmasságot kínál a helyi gyakorlatok egyeztetésében.</td>
</tr>
<tr>
<td>(JPN) Japán fogyasztásiadó-jelentés létrehozása, amely tartalmazza a módosított adókulcsokat.</td>
<td>A fogyasztásiadó-jelentés 5 százalékos adókulcshoz áll rendelkezésre.</td>
<td>A fogyasztásiadó-jelentés tartalmaz egy szakaszt a módosított adókulcshoz (például 8 százalék).</td>
<td>Az elrendezést a kormány nemrégiben jelentette be.</td>
</tr>
<tr>
<td>(EU) EU értékesítési lista kerekítési beállításainak konfigurálása.</td>
<td>Az egyes országoknak/régióknak jelentő EU értékesítési listák kerekítési beállításai X++ kódolásban vagy XSLTs (Rugalmas Nyelvi Stílussablon Változatok) kódolásban vannak megírva.</td>
<td>A kerekítési beállítások a Külföldi kereskedelmi paraméterekhez adódnak hozzá. Konfigurálhatja a kerekítés pontosságát, a kerekítés módszerét, a kimenet pontosságát és a kerekítés pontosságától kisebb mennyiségek viselkedését.</td>
<td>Ez egyesíti, és egyszerűbbé teszi az EU értékesítési lista jelentésének konfigurációját. A kerekítési beállítások kiigazítása többé nem igényel fejlesztői erőfeszítéseket.</td>
</tr>
<tr>
<td>(EU) Fordított költség-alkalmazhatósági szabályok beállítása.</td>
<td>A fordított költség-alkalmazhatósági szabályok belföldi fordított költségek esetére vannak kódolva. Az alkalmazhatósági tartomány cikkcsoportonként állítható be. EZ a funkció csak Nagy-Britanniában elérhető.</td>
<td>Konfigurálhatja a fordított költség-alkalmazhatósági szabályokat dokumentumonként (beszerzés/értékesítési rendelés, szállítói számla, ingyenes szöveges számla stb.) és fordított költségcsoportként, ami kombinálja az eszközöket, az eszközcsoportokat és a beszerzések/eladások kategóriákat. Az alkalmazhatósági szabályok hatással vannak a dátumra. Egyesével is kijelölheti az áfa-kódokat fordított költségre alkalmasnak az áfák csoportban. Az eladási számla jelentés beállítása úgy történik, hogy kimutassa az alkalmazott fordított költségek adatait. Ez a funkció rendelkezésre áll az összes európai országban/régióban.</td>
<td>Ez a változtatás egységesíti a fordított költség alkalmazási szabályok konfigurációit és támogatja a hazai fordított költség előírások elfogadását az Európai országok/régiók által.</td>
</tr>
<tr>
<td>(DE) Német könyvvizsgálati fájl készítése - GDPdUGoBD</td>
<td>A felhasználók a német ellenőrző szervek és a hatóságok által elfogadott formátumban exportálható pénzügyi adatokat tartalmazó definíciós táblákat hozhatnak létre.</td>
<td>A funkció elektronikus jelentési beállításként került megvalósításra. Ez a funkció Németország és Ausztria területén érhető el.</td>
<td>Ez a változtatás sokkal több lehetőséget biztosít a felhasználónak az adatformázás és a transzformáció terén, valamint biztosítja az összes elektronikus jelentéskonfigurációs élettartam-kezelési előnyt, például az egyszerű konfigurációs cserét, a verziókövetést, stb.</td>
</tr>
<tr>
<td>(FR) Egyenleglista csoportösszegző számla jelentéssel.</td>
<td>Az egyenleg lista a csoportösszegző számlák jelentésével SSRS jelentésként (LedgerAccountSum_FR) van beépítve.</td>
<td>A csoportösszegző számlák jelentéssel rendelkező egyenleg lista Kezelési Jelentő jelentésként került beépítésre és az LCS Eszköztár lokalizált pénzügyi jelentések mappájában található meg.</td>
<td>Ez lehetővé teszi a felhasználók számára az összes előny elérését és a teljes körű testreszabást a Kezelési Jelentő pénzügyi jelentéseinek használatakor.</td>
</tr>
<tr>
<td>(EZ) Fizetési tanács, Részvételi bizonylat és Kezelési jelentés a fizetésekhez.</td>
<td>Ezek a jelentések mind végrehajtottak és SSRS jelentések.</td>
<td>Ezeket a jelentéseket a Microsoft Excelben használt nyílt XML-sablonként hajtották végre.</td>
<td>Az elektronikus fizetési konfigurációk tartalmazzák a fizetési fájlformátum beállításokat és a sablonokat. Ez lehetővé teszi a felhasználók számára az összes előny elérését és a jelentések teljes körű testreszabását az Elektronikus jelentések használatakor.</td>
</tr>
<tr>
<td>(EU) Intrastat kerekítési beállításainak konfigurálása.</td>
<td>A különböző országokra/régiókra vonatkozó Intrastat jelentések kerekítési beállításai X++ vagy XSLTs (Rugalmas Nyelvi Stílussablon Változatok) kódolásban vannak megírva.</td>
<td>A kerekítési beállítások a külföldi kereskedelmi paraméterekhez adódnak hozzá. Konfigurálhatja a kerekítés pontosságát, a kerekítés módszerét, a kimenet pontosságát és a kerekítés pontosságától kisebb mennyiségek viselkedését.</td>
<td>Ez egyesíti, és egyszerűbbé teszi az Intrastat jelentések konfigurációját. A kerekítési beállítások kiigazítása többé nem igényel fejlesztői erőfeszítéseket.</td>
</tr>
<tr>
<td>(EU) Állítson be Intrastat árucikk kódokat a kategória hierarchiákban.</td>
<td>Az Intrastat árucikk kódok egy külön listaként szerepel. Ugyan létezik kategóriahierarchia az árucikk kódok típusaira, ezek az árucikk kódok beállíthatóak alapértelmezettként a Kiskereskedelmi HQent és értékesítési kategóriákban.</td>
<td>Az Intrastat árucikk kódok külön listája összevonásra kerül az Árucikk kód típusainak termékhierarchiájával.</td>
<td>Ez egyesíti a megközelítést az árucikk kódok kiadott termékekhez és értékesítési és beszerzési dokumentumok kategóriákhoz való hozzárendeléséhez.</td>
</tr>
<tr>
<td>(EU) Mennyiség jelentése kiegészítő egységekben az Intrastathoz az egység-átalakítás beállítás segítségével.</td>
<td>Az Intrastat árucikk kód rendelkezik egy szövegmezővel a kiegészítő egységek azonosítására,a<strong> Termék</strong> kártya pedig rendelkezik egy mezővel a kiegészítő egységek kilogrammban történő azonosítására.</td>
<td>A kiegészítő egységek az Intrastat árucikk-kódhoz az Egységek listából kerülnek kiválasztásra. A kiegészítő egységek mennyiségét egységkonvertálási beállítások segítségével számítják ki.</td>
<td>Ez egyesíti a megközelítést a tranzakció egységeiből történő újraszámításról a kiegészítő egységekre.</td>
</tr>
<tr>
<td>(EU) Rendelje hozzá az alapértelmezett szállítási módot a szállítási módhoz.</td>
<td>Nem érhető el.</td>
<td>A szállítás módjához hozzáadódik egy alapértelmezett szállítási mód mező.</td>
<td>Ez leegyszerűsíti az Intrastat jelentés előkészítését.</td>
</tr>
<tr>
<td>(EU) JJelölje meg a kiadott terméket, hogy az ne kerüljön bejelentésre az Intrastatban.</td>
<td>Nem érhető el.</td>
<td>A cikk Intrastat jelentésből történő kihagyása opció hozzá lett adva a kiadott termékhez.</td>
<td>Ez leegyszerűsíti az Intrastat jelentés előkészítését.</td>
</tr>
</tbody>
</table>

## <a name="manufacturing"></a>Gyártás

| Mit lehet tenni? | Dynamics AX 2012 |
|------------------|------------------|
| Ellenőrizze a termelési rendelésekhez elérhető anyagot egy külön oldalon, amely a **Termelési szint kezelés** munkaterületről nyitható meg. | Nem érhető el. |
| Kezdjen bele és jelentse a termelési feladatok előrehaladását az új **Feladatkártya eszköze** oldal használatával. | A **Feladatregisztrálási** képernyő elsősorban nagy terminál képernyőkre van tervezve, és a felhasználói felületen általában az egérrel történő kattintással érhető el. |

## <a name="master-planning-and-forecasting"></a>Alaptervezés és előrejelzés

| Mit lehet tenni? | Dynamics AX 2012 | Dynamics AX 7.0 | Miért fontos ez? |
|------------------|------------------|-----------------|------------------------|
| Figyelmeztesse a felhasználót, ha egy értékesítési rendelés vagy termelési rendelés nem áll készen szállításra az ütemezett dátumkor. | Az Alaptervezés által létrehozott figyelmeztetések neve: *határidő-üzenetek*. A *Határidő* a két fél között létrejött szerződés egy eszköznek a mai napon megállapodott áráról (a *határidő ár*), annak ellenére, hogy a szállítás és fizetés egy jövőbeli időpontban (a *szállítási dátum*) történhet. | A *Határidős üzenetek* és a *határidős dátumok* át lettek nevezve, új nevük: *kiszámított késések* és *halasztott dátumok*. | Az AX 2012 rendszerben használt terminológia a nem volt pontos és a hibás fordításokhoz vezetett. |
| Nyerjen gyors betekintést az alaptervezés futtatásának állapotába, a sürgős tervezett rendelésekbe és a tervezett rendelésekbe, amelyek késedelmet okoznak. | Az információ rendelkezésre áll, de több képernyőn található. | Az **Alaptervezés** munkaterület egy pillantással áttekinthető adatokat kínál arról, hogy mikor fejeződött be a legutóbbi alaptervezés futtatása, fellépett-e hiba, mik a sürgős tervezett rendelések, és mely tervezett rendelések okoznak késést. | Nagy előnye száramzik a munkaterület nyújtotta áttekintésből. Az Alaptervezés útmutatásához és a termelés növeléséhez releváns adatokat gyűjtött a rendszer egybe. |
| Az igény-előrejelzések frissítésére használjon Excel formátumot. | Nem érhető el. | Kihasználhatja az Excellel való zökkenőmentes integráció előnyeit, amikor beírja az igény-előrejelzéseket, frissítéseket végez, vagy törli az igény-előrejelzéseket. | Segít növelni a hatékonyságot és termelékenységet. |
| Becsülje meg a jövőbeli keresletet és hozzon létre keresleti előrejelzéseket a múltbéli tranzakcióadatok alapján. | A Microsoft Dynamics AX 2012 R3-ban az előrejelzési modellt a Microsoft SQL Server elemzési szolgáltatást igény-előrejelzés létrehozásához használják. | Becsülje meg a jövőbeli keresletet a Microsoft Azure gép tanulás felhőszolgáltatás erejével és kiterjeszthetőségével. Használata könnyű, és kiterjeszti az előrejelzési modelleket a gépi tanulásban, hogy megfeleljen a vevői követelményeknek. A szolgáltatás kiválasztja a legjobban összeillő modelleket, és fő teljesítménymutatókat (KPI) kínál fel, amelyeket az előrejelzés pontosságának kiszámításához lehet felhasználni. | Hozzon létre pontosabb előrejelzéseket a gépi tanulási módszerek használatával. |
| Optimalizálja a rendelési dátumot és mennyiséget a kapcsolódó műveletek áttekintésére alapozva, az alaptervezés futtatásából. | Műveletek diagram áttekintése elérhető, de megjeleníti az összes kapcsolódó műveletet. Műveletek alkalmazásakor azok azonnal eltűnnek a nézetből. | A műveletek diagram jobb áttekintést nyújt. Ez magában foglalja azokat a beállításokat, amelyek csak az alkalmazott műveleteket és a kapcsolódó műveleteket hagyják megjeleníteni. Műveletek alkalmazásakor halványítva jelennek meg, de továbbra is láthatók. Emiatt az áttekintés megmarad. A műveletek diagramhoz további információk adódnak hozzá, hogy az adatok egy oldalon jelenjenek meg. | Kihasználhatja a termelés fokozódásának előnyeit, hiszen csak az aktuális műveletekre összpontosít. |

## <a name="procurement-and-sourcing"></a>Beszerzés és forrás

| Mit lehet tenni? | Dynamics AX 2012 | Dynamics AX 7.0 | Miért fontos ez? |
|------------------|------------------|-----------------|------------------------|
| Használja a **Beszerzési rendelés előkészítése** munkaterületet, hogy gyors betekintést nyerjen az előkészítés alatt álló beszerzési rendelések állapotába. | Nem támogatott | A **Beszerzési rendelés előkészítése** munkaterület áttekintést nyújt a rendelésekről kezdve onnan, hogy vázlatként létrehozzák őket és nyomon követi azokat a munkafolyamat-jóváhagyási állapoton keresztül egészen a visszaigazolásig. | A beszerzési részlegnek nem kell már több oldal adatait átböngészni, hanem az áttekintésből tájékozódhat, amelyet a munkaterületen biztosít. |
| Használja a **Beszerzési rendelés bevételezése és követése** munkaterületet, hogy gyors betekintést nyerjen a bevételezésre váró beszerzési rendelésekbe, így segítve azok lekövetését. | Nem támogatott | A **Beszerzési rendelés bevételezése és követése** munkaterület azokról a visszaigazolt beszerzési megrendelésekről nyújt áttekintést, amelyek bevételezésre vagy szállításra várnak. A munkaterület a lejárt bevételezésű vagy bevételezésre várók listáját tartalmazza, hogy segítsen a proaktív proaktív ellenőrzéssel és a szállító általi követéssel. A munkaterület továbbá olyan beszerzési megrendeléseket is listáz, amelyeknek a beérkezési regisztrációja megtörtént a a raktárban, így segít biztosítani, hogy a bevételezést feladták. Azok a Beszerzésirendelés-visszaküldések is elérhetők az ellenőrzés számára, amelyek még nem kerültek kiszállításra. | A beszerzési részlege hasznosíthatja a munkaterület nyújtotta áttekintést. A követés útmutatásához és a termelés növeléséhez releváns adatokat gyűjtött a rendszer egybe. |
| Küldjön beszerzési rendeléseket visszaigazolásra a szállítói portálra , melyet a Dynamics AX kliens működtet. Hagyja, hoyg a szállító jóváhagyja vagy elutasítsa. | Nem támogatott | A szállítói portál felület lehetővé teszi, hogy a szállítók megkapják a beszerzési rendeléseket jóváhagyásra vagy elutasításra. Lehetővé teszi továbbá a szállító számára, hogy áttekintést nyerjen egy számlára érkezett összes jóváhagyott beszerzési rendelésről. A beszerző küldhet olyan beszerzési rendelést, melyben visszaigazolást kér a szállítótól. A szállítónak regisztrált AAD (Microsoft Azure Active Directory – Azure AD) felhasználónak kell lennie a Dynamics AX rendszerben, rendelkeznie kell kapcsolattartóval, és kell hogy legyen kijelölt biztonsági szerepköre. | A beszerzési részleg előnyére szolgál, hogy csökken a papírmunka és a beszerzési rendelésekre érkező válaszok manuális nyomon követése, mivel mindez közvetlenül a rendszerben történik. Ha egy valós tartalommal bíró forrás van, kevesebb a félreértés a vevő és a szállító között. |

## <a name="projects"></a>Projektek

| Mit lehet tenni? | Dynamics AX 2012 | Dynamics AX 7.0 | Miért fontos ez? |
|------------------|------------------|-----------------|------------------------|
| Foglaljon le dolgozókat a projektekhez forrásként. | Az erőforrásokhoz hasonlóan, a dolgozókat is közvetlenül foglalják le a projektekhez az erőforrások mellé. | A Munkaközpont táblázatot, amelyben a gyártás és a termelés erőforrásait tárolják, mostantól arra is használhatja, hogy dolgozókat foglal le a projekthez erőforrásként. | Projektek foglalásakor ha csak erőforrásokat kell foglalnia. |

## <a name="retail-sales-marketing-and-customer-service"></a>Kiskereskedelmi értékesítés, marketing és ügyfélszolgálat

### <a name="retail-hq"></a>Kiskereskedelmi munkaállomás

A Microsoft Azure rendszer kiskereskedelmi munkaállomása a webes kliensen keresztül a kereskedelmi műveletek minden részébe teljes betekintést és központosított kezelést nyújt.

<table>
<thead>
<tr>
<th>Mit lehet tenni?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Miért fontos ez?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Árusítási műveletek végrehajtása.</td>
<td>A felhasználóknak több képernyőhoöz kell hozzáférniük ezeknek az adatoknak a kezeléséhez:
<ul>
<li>Kategóriák kezelése</li>
<li>Termékkezelés</li>
<li>Csatornatermék-attribútumok</li>
<li>Szortimentek</li>
<li>Katalóguskezelés</li>
<li>Csomagok</li>
<li>Árak és engedmények</li>
</ul></td>
<td>A <strong>Kategória- és termékkezelés</strong> munkaterület a következő funkciókat teszi lehetővé:
<ul>
<li>Választék kezelése.</li>
<li>Választék életciklus nyomon követése.</li>
<li>Kiadott termékek kezelése.</li>
</ul>
Az <strong>Árak és engedmények kezelése munkaterület</strong> a következő funkciókat teszi lehetővé:
<ul>
<li>Az Árak és engedmények kezelése egy adott csatorna és kategória esetében.</li>
<li>Kategória-árszabály kezelése.</li>
<li>Az Ár- és engedményprioritások azok, amelyek révén Ön prioritásokat rendel az árcsoportokhoz és az engedményekhez, így szabályozhatja a rendelést, amelyben alkalmazzák őket.</li>
<li>Fiók- és a katalógusengedmény kezelése.</li>
</ul>
A <strong>Katalóguskezelés</strong> munkaterület a következő funkciókat teszi lehetővé:
<ul>
<li>Aktív katalógusok összefoglalása.</li>
<li>A katalógus életciklus nyomon követése egyetlen helyen.</li>
</ul></td>
<td><ul>
<li>A munkaterületek fokozzák a dolgozók hatékonyságát és termelékenységét azáltal, hogy ők kezelhetik központilag az árusítási szerepkörükhöz tartozó feladataikat és műveleteiket.</li>
<li>Az ár- és engedményprioritások szolgáltatás által a vevők jobban felügyelhetik, hogy hogyan használják az árakat és engedményeket. A funkció továbbá új eseteket engedélyez, ahol a magasabb üzlet árak felülírják az egységárakat.</li>
</ul></td>
</tr>
<tr>
<td>Kiskereskedelmi csatorna telepítések és műveletek kezelése</td>
<td>A felhasználónak több képernyőn kell elvégeznie a következő feladatokat:
<ul>
<li>Új csatornák és kapcsolódó entitások létrehozása és konfigurálása.</li>
<li>Napi üzlet tevékenységek kezelése.</li>
<li>Kiskereskedelmi tranzakciók feldolgozása a Microsoft Dynamics AX-ben, és a kiskereskedelmi kimutatások készítése, és a Microsoft Dynamics AX-készlet és a pénzügyi adatok frissítése.</li>
</ul>
</td>
<td>A <strong>Csatornatelepítés</strong> munkaterület a következő feladatok elvégzését teszi lehetővé:
<ul>
<li>Új csatornák és kapcsolódó entitások létrehozása.</li>
<li>A kiskereskedelmi áruház konfigurálása előrehaladásának nyomon követése.</li>
<li>A feladat befejezéséhez szükséges lépések megtétele vagy a feladat végrehajtásához szükséges adatok megadása.</li>
<li>Eszközök állapotának követése, és a Retail Modern POS (MPOS) programtelepítő közevtlen ellenőrzése és letöltése az üzletekben.</li>
<li>Az összes kapcsolódó lap elérése.</li>
</ul>A 
<strong>Kiskereskedelmi üzlet kezelése</strong> munkaterület a következő feladatok elvégzését teszi lehetővé:
<ul>
<li>Dolgozók és a dolgozók pénztári (POS) engedélyeinek kezelése</li>
<li>Egy adott áruház vagy üzletcsoportok műszak állapotának nyomon követése.</li>
<li>Az MPOS programtelepítés közvetlen ellenőrzése és letöltése az üzletekben.</li>
<li>Jelentések nyomtatása és a kapcsolódó lapok elérése.</li>
</ul>A 
<strong>Kiskereskedelmi üzlet pénzügyi adatai</strong> munkaterület a következő feladatok elvégzését teszi lehetővé:
<ul>
<li>Egy adott csatornához tartozó kimutatások létrehozása, kiszámítása és feladása.</li>
<li>Kötegelt feladat ütemezése a készlet frissítéséhez, és a kimutatások kiszámításához és feladásához.</li>
<li>Nyitott kimutatások nyomon követése.</li>
<li>Egy adott áruház vagy üzletcsoportok műszak állapotának nyomon követése.</li>
<li>Jelentések gyors nyomtatása és az összes kapcsolódó lap elérése.</li>
</ul></td>
<td>A munkaterületek fokozzák a dolgozók hatékonyságát és termelékenységét azáltal, hogy ők kezelhetik központilag a csatornatelepítéshez, üzletirányításhoz és pénzügyi adatokhoz tartozó legtöbb feladatukat és műveletüket.</td>
</tr>
<tr>
<td>Kiskereskedelmi IT műveletek kezelése.</td>
<td>A felhasználónak több képernyőt kell elérnie.</td>
<td>A <strong>Kiskereskedelmi informatikai</strong> munkaterület lehetővé teszi, hogy az adott csatornánhoz tartozó Commerce Data Exchange-lekérdezések egyetlen helyen történjenek, így a következő feladatokat végezheti:
<ul>
<li>Munkamenetek letöltése.</li>
<li>Munkamenetek feltöltése.</li>
<li>Sikertelen munkamenetek nyomon követése, azok újrakezdeményezése és futtatása.</li>
<li>Közelgő feladatok megtekintése vagy futtatása.</li>
</ul></td>
<td>A munkaterületek fokozzák a dolgozók hatékonyságát és termelékenységét azáltal, hogy ők kezelhetik központilag a kiskereskedelmi informatikai műveletekhez tartozó feladataikat és műveleteiket.</td>
</tr>
<tr>
<td>Adatok importálása/exportálása adatentitások használatával.</td>
<td>Az AX 2012 támogatja a kész Microsoft Dynamics Retail Management System (RMS) áttelepítését az Adatimportálási és -exportálási keretrendszeren keresztül.</td>
<td>A kiskereskedelmi adatentitások ki lettek bontva, hogy minden a kiskereskedelemhez kapcsolódó fő- és hivatkozási adatot támogassanak. Továbbá a Dynamics AX megoldás egészére kiterjed az adatentitások támogatása.</td>
<td>Az adatentitások lehetővé teszik a vevők számára a metaadat-központú adatimportálást és adatexportálást. Továbbá az adatentitások segítségével a vevők integrálhatják a Dynamics AX-t külső programok segítségével is.</td>
</tr>
<tr>
<td>Hajtson végre intelligens elemzést a BI jelentések segítségével a Dynamics Microsoft AX-ből és a POS-ügyfélből.</td>
<td>Több mint 25 háttérirodai és öt csatornaoldal-jelentés elérhető.</td>
<td>Több mint 30 háttérirodai és 10 csatornaoldal-jelentés elérhető.</td>
<td>Ezek a jelentések több BI-t tesznek lehetővé a vevők számára a trendek előrejelzésére, elképzelések felfedésére és a folyamatos csúcsteljesítményen való működésre.</td>
</tr>
<tr>
<td>Elemezze a kiskereskedelmi csatorna értékesítési adatait a „Kiskereskedelmi csatorna teljesítményének felügyelete” Power BI tartalom segítségével.</td>
<td>Nem érhető el.</td>
<td>A PowerBI.com oldalon jelölje be az <strong>Adatok átvétele</strong> lehetőséget, majd válassza ki a <strong>Dynamics AX – Kiskereskedelmi csatorna teljesítménye</strong> tartalomcsomagot. Adja meg a Dynamics AX végpont URL-címét, hogy megtekinthesse az adatainak az irányítópulton való megjelenését.</td>
<td>A vállalatok három-négy kattintással fontos pénzügyi adatokat tartalmazó PowerBI irányítópultot telepíthetnek. A szervezet személyre szabhatja a tartalmat. Ezenkívül a felhasználók belehelyezhetik Power BI irányítópult-lapokat személyre szabott munkaterületükbe a Dynamics AX rendszerben, hogy segítségükkel egyetlen pillantással áttekinthessék az elemzési adatokat.</td>
</tr>
<tr>
<td>Vevői engedélyek konfigurálása.</td>
<td>Nem érhető el.</td>
<td>A vevők választhatnak, hogy rendelkezésére álljanak-e POS-máveletek a fogyasztók számára. A Kiskereskedelmi kiszolgáló alkalmazásprogramozási felület hívásokhoz (API) engedélyeket használ.</td>
<td>Ez lehetővé teszi a vevőszintű engedélyek beállítását.</td>
</tr>
<tr>
<td>Kezeli és érvényesíti az entitáskonfigurációkat.</td>
<td>Nem érhető el.</td>
<td>A konfigurációkezelő és -érvényesítő szolgáltatás a következő funkciókat teszi lehetővé:
<ul>
<li>Tömeges konfigurációs adatok feltöltése</li>
<li>Üzleti egység ellenőrzése</li>
</ul></td>
<td>Ez lehetővé teszi a konfiguráció feltöltését, és a különböző konfigurációs elemek elrendezése teljességének és állapotának ellenőrzését.</td>
</tr>
</tbody>
</table>

### <a name="retail-hardware-station"></a>Retail hardverállomás

| Mit lehet tenni? | Dynamics AX 2012 | Dynamics AX 7.0 | Miért fontos ez? |
|------------------|------------------|-----------------|------------------------|
| Engedélyezi a POS-készülékek számára az olyan perifériás eszközökhöz való csatlakozást, mint például nyomtatók, pénztárfiókok vagy fizetési eszközök. | A MPOS hardverprofil a használt eszközök megadására szolgál. | Egy hozzáadott hardverprofil több különböző hardvert támogat egy állomástól a következőig. Egy új Hardveres állomás profil egyedi terminálazonosítót támogat minden egyes Hardverállomáshoz elektronikus átutalás (EFT) tranzakciók feldolgozásakor. Az EFT-támogatás bele lett olvasztva egy hardveres állomásba, hogy csökkenjen az MPOS részvétele az EFT kifizetésfeldolgozásban. | Nagyobb rugalmasságot kölcsönöz a végrehajtásokhoz. Továbbá fokozza a biztonságot és csökkenti a hitelkártyaadatok kitettségét. |

### <a name="retail-server-and-data-management"></a>Kiskereskedelmi kiszolgáló és adatkezelés

A Kiskereskedelmi kiszolgáló és adatkezelés lehetővé teszi a vevők és vállalatok számára, hogy omni csatorna vásárlási tapasztalatot hozzon létre on-line, üzletbe ni vagy hívásközponti csatornákon keresztül.

<table>
<thead>
<tr>
<th>Mit lehet tenni?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Miért fontos ez?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Csatalkozás egy kiskereskedelmi futtatókörnyezet (CRT) adatbázishoz, amely CRT-szolgáltatásokkal üzleti adatokat tárol a csatornához.</td>
<td>Az OData V3 támogatott.</td>
<td>Az OData V4 támogatott.</td>
<td>Segít a vevőnek, hogy naprakész legyen a OData szabályok segítségével. Továbbá az üzletbeli, mobil- és online csatornákon keresztüli értékesítés integrálásával egy robusztus omni csatorna tapasztalatot hoz létre.</td>
</tr>
<tr>
<td>Kiskereskedelmi szolgáltatások, mint üzemeltethető szolgáltatások támogatása.</td>
<td>Az elektronikus kereskedelem API nem támogatott a Kiskereskedelmi kiszolgálón keresztül.</td>
<td>Az elektronikus kereskedelem API nem elérhető a Kiskereskedelmi kiszolgálón keresztül az online esetek támogatására.</td>
<td>Tárolt és skálázható elektronikus kereskedelmi szolgáltatásokat nyújt, amelyek harmadik fél online áruházak esetében használhatók.</td>
</tr>
<tr>
<td>A Microsoft Dynamics AX háttériroda és a csatornák közötti adatáthelyezés a Commerce Data Exchange használatával.</td>
<td>A Commerce Data Exchange olyan rendszer, amely átviszi az adatokat a Microsoft Dynamics AX és a kiskereskedelmi csatornák között, például online áruházak és a fizikai üzletek között. További tudnivalókért lásd: <a href="https://technet.microsoft.com/library/dn741440.aspx">Kereskedelmi Adatcsere [AX 2012]</a>.</td>
<td>Funkcionális paritás van a Microsoft Dynamics AX 2012 CU8-cal. Azonban vegye figyelembe a következőket:
<ul>
<li>A Commerce Data Exchange-t újra kialakították a felhő számára.</li>
<li>Az Async szolgáltatás közvetlen adatbázis-elérést használ a csatorna-adatbázishoz.</li>
<li>A Commerce Data Exchange: a valós idejű szolgáltatás a Microsoft Dynamics AX egyéni szolgáltatásként üzemel.</li>
<li>Az MPOS az offline adatbázisok és a Kiskereskedelmi kiszolgáló közötti szinkronizálást kezeli.</li>
</ul></td>
<td>A Commerce Data Exchange-t újra kialakították a felhőplatform számára. Továbbra is az adatátvitelt kezeli a Microsoft Dynamics AX és a kiskereskedelmi csatornák között, például online áruházak és a fizikai üzletek között.</td>
</tr>
<tr>
<td>Támogatja az automatikus felismerést és konfigurálást, a félig integrált csatornák közötti fizetések feldolgozásátaz SDK kifizetés segítségével.</td>
<td>Az AX 2012 a következő funkciókat nyújtja:
<ul>
<li>Az összes csatorna támogatása: pénztár, elektronikus kereskedelem és hívásközpont.</li>
<li>Támogatja a jelenlévő és a nem jelenlévő kártyát.</li>
<li>Oldal a kifizetés elfogadására.</li>
<li>Az LS5300 és az MX925, mint Kiskereskedelmi SDK-ban lévő mintakódok perifériás támogatása.</li>
</ul></td>
<td>A Dynamics AX jelenlegi verziója támogatja az összes meglévő Microsoft Dynamics AX-et a Kiskereskedelmi 2012 hitel-/betéti kártya funkciókhoz és négy új fejlesztéséhez.</td>
<td>Lehetővé teszi a vevő számára hitel-/betéti kártya tranzakciók lefolytatását a kifizetésekhez.</td>
</tr>
<tr>
<td>Eszközök aktiválása egy Microsoft-fiók (Microsoft Azure Active Directory (ADD)) segítségével.</td>
<td>Nem érhető el.</td>
<td>A következő funkciók érhetők el:
<ul>
<li>Fokozott biztonság az Azure AD-alapú aktiválás segítségével a felhőhöz.</li>
<li>Fokozott biztonság a tokenkezelésben.</li>
<li>Fokozott megbízhatóság, hibaelhárítás és hibaüzenetküldés az aktiválás során</li>
<li>Egyszerűsített, az aktiváláshoz tartozó informatikai felügyeleti feladatok.</li>
<li>Újra megvizsgált fenyegetettségi modell és javított biztonsági kérdések.</li>
</ul></td>
<td>Ez a következő előnyökkel jár:
<ul>
<li>A biztonsági rendszer az Azure AD-n és az eszköztokenen/-azonosítón (RS hívások, amelyek tokent használnak, felhasználó-specifikus alkalmazástárolás) keresztül ki van terjesztve.</li>
<li>Leállítja az MPOS (fizikai eszköz) nem negedélyezett távoli használatát.</li>
<li>Nyomon követi az MPOS eszközöket PCI megfelelés céljából.</li>
<li>Leképezi az üzleti entitással (nyilvántartás) a fizikai eszközöket az eszköz token használatával.</li>
<li>Beállításokat inicializál az MPOS problémamentes működéséhez (számsorozatok és hardverprofilok) az MPOS első lépéseként.</li>
<li>Eszközadatokat jelent a központból.</li>
</ul></td>
</tr>
<tr>
<td>Gazdag médiatartalmat kezel a Médiatáron keresztüli engedélyezéshez és kiszolgáláshoz.</td>
<td>Nem érhető el.</td>
<td><ul>
<li>Támogatja a képek feltöltését, a megtekintésüket, a kezelésüket és a törlésüket a Médiatárból, mind a külső kiszolgálótól, mind a Kiskereskedelmi kiszolgálótól származó képek esetében.</li>
<li>Támogatja a képfeltöltést és megtekintést az entitások lapjairól (<strong>Termékek</strong>, <strong>Katalógusok</strong> stb.) a Médiatárból történő képhivatkozással vagy az asztalon lévő kép feltöltésével.</li>
<li>Képek optimalizálása gyorsnézeti képhez, egyéni mérethez és eredeti mérethez.</li>
<li>Entitások tömeges hivatkozása sablon és háttérfeladatok alapján tömeges társításhoz.</li>
<li>A Microsoft Excel-integráció felülírja az elnevezési konvenciók és előre meghatározott elérési utak attribútumcsoport-korlátozását.</li>
<li>Támogatja az offline képeket és a biztonságos képeket a személyes azonosításra alkalmas adatok tartalma esetében, mint például a kiskereskedelem által szolgáltatott alkalmazotti és vevői képek.</li>
</ul></td>
<td><ul>
<li>Foglalkozik a rendszeren kívülről jövő képek gyenge pontjaival, ilyen módon elkerülhető az előre és hátra ugrálás, és helyette egy helyen kezelheti a képeket.</li>
<li>Hatékony tartalomkezelést nyújt a Médiatáron keresztül a felöltött és a rendszeren kívülről érkező képekhez, továbbá szűrést alkalmaz, hogy könnyebben megtalálja a keresett képet.</li>
<li>Segítségével könnyen létrehozhat tömeges társításokat a rendszeren kívülről jövő képek és az olyan entitások között, mint például termékek és katalógusok.</li>
<li>Támogatja a kiskereskedelem által szolgáltatott képtárolást és az Excel integrációját a könnyű frissítések érdekében.</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="rich-clientele-experience"></a>Gazdag kiszolgálási tapasztalat

A Kiskereskedelem gazdag mobilélményt kínál bárhol, bármikor és bármilyen eszközön. Ez a funkció fokozott vásárlási élményt tesz lehetővé minden csatornán.

<table>
<thead>
<tr>
<th>Mit lehet tenni?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Miért fontos ez?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Termékek kutatása, böngészése, keresése vagy beolvasása, termék hozzáadása a kosárhoz, fizetés elfogadása, és kijelentkezés, mindez könnyen használható, érintőképernyős és gazdag felhasználói élményt nyújt az MPOS-en.</td>
<td>Az AX 2012 a következő funkciókra használható:
<ul>
<li>Értékesítés, visszáruzás és érvénytelenítés elvégzése.</li>
<li>Vevői rendelések létrehozása, módosítása és felvétele.</li>
<li>Műszak- és fiókműveletek végzése.</li>
<li>Rendelések kitárolása és bevételezése és leltár elvégzése.</li>
<li>Üzletbeli jelentések megtekintése.</li>
</ul></td>
<td>Az AX 2012 MPOS-szel funkcionális paritás áll rendelkezésre. Ez a következő funkciókból áll:
<ul>
<li>Vevőkeresés üzleteken/csatornákon keresztül.</li>
<li>A vevői rendelések létrehozása a valós idejű szolgáltatások elérése nélkül.</li>
<li>Továbbfejlesztett eszközaktiválási munkafolyamatok, állapot- és hibaüzenetek.</li>
<li>Bővítési javítások, feladás előtti eseményindítók és tevékenység támogatása a testreszabás javítása érdekében.</li>
</ul></td>
<td>Értékesítési munkatársak értékesítési tranzakciókat és vevői rendelések dolgozhatnak fel, és napi műveleteket hajthatnak és készletkezelsét létre mobileszközök használatával bárhol az üzletben.</td>
</tr>
<tr>
<td>Indítsa el a POS-t webalkalmazásként a POS felhőn keresztül.</td>
<td>Nem érhető el.</td>
<td>Az MPOS-szel funkcionális paritás áll rendelkezésre. Ez a következő funkciókból áll:
<ul>
<li>Eszközaktiválás az ADD segítségével</li>
<li>Igényekre reagáló elrendezésdizájn</li>
<li>Támogatás az Internet Explorer,az Edge és a Chrome böngészőkhöz.</li>
</ul></td>
<td>POS webalkalmazást biztosít, amelynek a funkciói kompatibilisek az MPOS-szel, és amelyet több platformon és böngészőn lehet használni telepítési költségek nélkül.</td>
</tr>
<tr>
<td>Integrálható a tartalomkezelő rendszerekkel, hogy omni-csatornás elektronikus kereskedelmi webhelyet lehessen létrehozni.</td>
<td>A Microsoft SharePoint és a harmadik fél kirakatokok támogatottak.</td>
<td>Rendelkezésére áll egy elektronikus kereskedelmi platform is, amely támogatja a harmadik-fél kirakatokat. A platform a következő funkciókat foglalja magában:
<ul>
<li>Gazdag felhasználói API.</li>
<li>Engedélyezési integráció minden nyitott azonosítót biztosító külső szolgáltató számára.</li>
<li>Kifizetés-integráció.</li>
</ul></td>
<td>A vevők innentől fogva rugalmasan használhatják a tartalomkezelő rendszert tetszés szerint.</td>
</tr>
<tr>
<td>Vevők megcélzása postai rendelési katalógusokon keresztül, műveletek racionalizálása gyors rendelésbevitel, támogatott értékesítés és teljesítés segítségével, a Hívásközpont használatával.</td>
<td><ul>
<li>Hívásközponti csatorna</li>
<li>Postán érkező katalógusok rendeléshez</li>
<li>Gyors rendelésbevitel és támogatott értékesítés</li>
<li>Fokozott rendelésteljesítés</li>
<li>Ügyfélszolgálat</li>
<li>Integrált árképzés és promóciók/kedvezmények</li>
</ul></td>
<td>Az AX 2012 Hívásközpont megoldáshoz funkcióparitás áll rendelkezésre, árfelülbírálás kivételével.</td>
<td>A Hívásközpontok olyan kiskereskedelmi csatornatípusok, amelyek lehetővé teszik, hogy a dolgozók rendeléseket vegyenek fel a vevőktől telefonon keresztül, és értékesítési rendelést hozzanak létre.</td>
</tr>
</tbody>
</table>

### <a name="commerce-essentials"></a>Kereskedelmi alapok

A kiskereskedelemre és keresekedelemre fókuszált konfigurációs beállítás segítségével leegyszerűsítheti a kiskereskedelem-specifikus telepítéseket.

| Mit lehet tenni? | Dynamics AX 2012 | Dynamics AX 7.0 | Miért fontos ez? |
|------------------|------------------|-----------------|------------------------|
| Haználja a Kereskedelmi alapok irányítópultot. | Elérhető egy területlap menüelemekhez kapcsolódó hivatkozásokkal. | A Kereskedelmi alapok irányítópult hivatkozások ad meg gyakori feladatokhoz, beleértve a munkaterületekhez, a Power BI webes vezérlőhöz, a Kedvencekhez, a legutóbbi oldalakhoz és az aktuális munkaelemekhez kapcsolódó hivatkozásokat. | A továbbfejlesztett irányítópult feljogosítja a dolgozókat, hatékonyabbá teszi őket, és a rugalmas kiindulópontként szolgál kiskereskedelem-specifikus tevékenységekhez. |
| Adatentitások használata a számlamódosítások eléréséhez. | A számlamódosításokat a fájlrendszerben található mappába exportálja a program. | A számlamódosítások az adatentitásokon keresztül érhetők el. | Ez a funkció nagyobb rugalmasságot biztosít az adatok elkülönült rendszerek közötti áthelyezésekor. Ez a funkció fokozható az OData alkalmazásokkal is. |
| A POS felhő és az MPOS használata. | Csak az Enterprise POS (EPOS) támogatott , amely már rögtön az installálás után használható. | Az MPOS és a POS felhő helyettesíti az EPOS ügyfelet. Az elektronikus kereskedelem csatorna is alapértelmezés szerint hozzá lett adva a Kereskedelmi alapokhoz. | Ez a funkció az installálást követő állapotában nagyobb csatornatámogatást tesz lehetővé gyorsan telepíthető pénztári ügyfelekkel. |
| A két-réteg felépítés megvalósítása és karbantartása. | Az Adatimportálási és-exportálási keretrendszer lehetővé teszi az adatoknak az AX 2012 és külső a rendszerek közötti áthelyezését. | A program adatentitásokat hoz létre a kétrétegű architektúra támogatásának növelésére. | Az adatentitások és az OData-alkalmazások egy absztrakciós réteget biztosítanak, hogy könnyebben lehessen a kétszintű eseteket megvalósítani és karbantartni. |
| Egyszerűsíti a képernyőket. | Egyéni kódl szükséges a felhasználói felület egyszerűsítéséhez. | A képernyő- és a menübővítmények szabványos felhasználóifelület-egyszerűsítést nyújtanak. | Ez a funkció gyorsabb és egyszerűbb képernyő-finomhangolást tesz lehetővé a kiskereskedői igényektől függően. |

### <a name="pos-task-recorder"></a>POS feladatrögzítő

<table>
<thead>
<tr>
<th>Mit lehet tenni?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Miért fontos ez?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Feladat-útmutatókat és dokumentumokat hoz létre és oszt meg a Modern POS-hez.</td>
<td>Nem érhető el.</td>
<td>Az MPOS Feladatrögzítő a következő funkciókat támogatja:
<ul>
<li>Feladatrögzítések létrehozása az MPOS-ben végrehajtott különféle feladatokhoz.</li>
<li>Hozzon létre lépéseket és képernyőképek tartalmazó dokumentumot és társítása az üzleti folyamatmodellben lévő csomóponttal.</li>
</ul></td>
<td>A partnerek és a független szoftverszállítók (ISV) testreszabhatják az MPOS-t és támogató dokumentumokat biztosíthatnak felhasználóik képzéséhez.</td>
</tr>
</tbody>
</table>

### <a name="extensibility"></a>Bővíthetőség

<table>
<thead>
<tr>
<th>Mit lehet tenni?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Miért fontos ez?</th>
</tr>
</thead>
<tbody>
<tr>
<td>A Központban, a Hívásközpontban, az Elektronikus kereskedelemben és a Pénztárban bővíthető és egyszerűen telepíthető Kiskereskedelem összetevőket támogat.</td>
<td>A íkiskereskedelem SDK segítségével az összetevők kiterjeszthetők. Nincs csomagolóanyag- és a telepítésilehetőség-támogatás.</td>
<td>A kódelkülönítés és szervizelhetőség jobb támogatása érdekében a program fejlesztette a bővítési horgokat a különböző összetevőkhöz. Íme néhány elérhető funkciók:
<ul>
<li>Munkafolyamat, tevékenység és művelet.</li>
<li>Eseményindító előttiek és utániak, amelyekkel könnyen meghosszabbítható egy munkafolyamat.</li>
<li>Művelet- és alkalmazás-eseményindítók.</li>
</ul>
Ezenkívül rendelkezésre áll egy olyan keretrendszer, amely lehetővé teszi, hogy ezeket az összetevőket létrehozza és csomagolja az MSBuild használatával, majd problémamentesen telepítse a testreszabást az LCS-en (Microsoft Dynamics Lifecycle Services) keresztül.</td>
<td>A kiskereskedőknek nagyon speciális követelményeik vannak, műveleti szektoroktól és földrajzi régióktól függően. Egy könnyen bővíthető platform biztosítása által lehetővé tesszük a szektorokban és piacokon történő használatot. Mivel a Kiskereskedelem nagyon elosztott architektúrával is rendelkezik, a problémamentes telepítés nagyban javítja a termelékenységet.</td>
</tr>
</tbody>
</table>

### <a name="lifecycle-management"></a>Életciklus kezelése

Az LCS (Életciklus Szolgáltatások–Lifecycle Services) olyan szolgáltatáscsomagot tartalmaz, amelynek segítségével az ügyfelek és partnerek kezelhetik a rendszer életciklusát a regisztrációtól a napi műveletekig.

<table>
<thead>
<tr>
<th>Mit lehet tenni?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Miért fontos ez?</th>
</tr>
</thead>
<tbody>
<tr>
<td>A program felhőtelepítési szolgáltatásokon keresztüli kezelése.</td>
<td>Nem érhető el.</td>
<td>A következő topológiák telepíthetők a felhőre:
<ul>
<li>Kiskereskedelmi 1 dobozos próbatopológia.</li>
<li>Kiskereskedelmi többdobozos magas rendelkezésre állású topológia.</li>
<li>Fejlesztői topológia Kiskereskedelmi SDK-val.</li>
</ul>
Van egy továbbfejlesztett „kevés támogatást igénylő” ügyfélösszetevő-telepítés az önkiszolgáló rendszer telepítésén keresztül:
<ul>
<li>Kiskereskedelmi Modern Pénztár.</li>
<li>Kiskereskedelmi Hardver Állomás.</li>
<li>A testreszabott csomagok feltöltésének és terjesztésének támogatása az önkiszolgáló-telepítésen keresztül.</li>
</ul></td>
<td>A felhőtelepítési szolgáltatások a következő előnyökkel járnak:
<ul>
<li>Jelentősen csökkentett telepítési munka és Kiskereskedelmi központ összetettsége.</li>
<li>Anyanyelvi telepítés a Microsoft Azure nyilvános felhőhöz.</li>
<li>Az üzleten belüli összetevők fejlesztett önkiszolgáló-telepítése a konfiguráció egyszerűbbé tétele érdekében</li>
</ul></td>
</tr>
<tr>
<td>A rendszer állapotának figyelése, hibák és problémák diagnosztizálása.</td>
<td>Ehhez a funkcióhoz a következő szükséges: <a href="http://www.microsoft.com/download/details.aspx?id=42636">System Center 2012 felügyeleti csomag a Microsoft Dynamics AX 2012 R3 CU8 Kiskereskedelemhez</a>.</td>
<td>A kiskereskedelmi összetevők felügyelete és diagnosztizálás már elérhető az <strong>Üzemeltetési elképzelések</strong> irányítópulton keresztül az LCS-ben.</td>
<td>Az <strong>Üzemeltetési elképzelések</strong> irányítópult egy felhőalapú ellenőrzési portál, amely felülírja a System Center üzemeltetési vezető (SCOM) infrastruktúra telepítését.</td>
</tr>
<tr>
<td>Kiskereskedelmi Hardverállomást és eszközöket hoz létre, konfigurál, letölt és telepít az önkiszolgáló használatával.</td>
<td>A telepítéscsomagoló és az Enterprise Portal használatával a felhasználó végrehajthatja minden olyan összetevő automatikus telepítését és a konfigurálását, amely egy adott számítógépen szükséges, megadott topológiától függően.</td>
<td>Mivel csak két telepítőcsomag van, egy az MPOS ügyfél és egy másik a Kiskereskedelmi hardverállomás összetevőjéhez, az önkiszolgáló csökkentette az ügyfélösszetevők telepítéséhez szükséges munkát egyes szintekhez.</td>
<td>Az önkiszolgáló célja, hogy minimálisra csökkentse a követelményeket és megkönnyítse a felhasználó számára a telepítést.</td>
</tr>
</tbody>
</table>

## <a name="sales"></a>Értékesítés

<table>
<thead>
<tr>
<th>Mit lehet tenni?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Miért fontos ez?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Szállítási alternatívák gyors áttekintése rendelések ígéretekor.</td>
<td>Termékelérhetőség-korlátozáskor, és amikor a vevő által kért szállítási dátum a rendelésen szereplő egy vagy több termék esetében nem teljesíthető, a rendelésígéret-feladat kihívást jelent. Ahhoz, hogy olyan megoldást találjunk, mely kompenzálja a rendelkezésre állási és szállítási idővel kapcsolatos problémákat, úgy, hogy a vevő által kért dátum teljesíthető legyen, vagy hogy a vevőnek olyan szállítási megoldást ajánlhassunk fel, amelyet elfogad és amelyben megbízhat, a rendelésfeldolgozónak több képernyőt kell megnyitnia, amelyek mindegyikén a szükséges információknak csak egy része jelenik meg. Pontosabban egy képernyő mutatja az aktuális mennyiséget a telephelyeken, egy másik képernyő mutatja az aktuális mennyiséget a vállalatközi beállításban, egy harmadik képernyő segítségével a felhasználó kiszámíthatja a legkorábbi elérhető dátumot egy telephelyhez/változathoz egyszerre, valamint egy negyedik képernyő mutatja ellátási rendeléseket. Emiatt a felhasználók nem érzik úgy, hogy figyelembe vették az összes vonatkozó opciót, az azonnali, de optimálisnál rosszabb megoldás kiválasztása helyett. A felhasználók nem érzik magukat hatékonynak sem, mert számos zavaró tényező lép fel a rendelés ígéret folyamatában, több lap megnyitása és bezárása, és az információk és lehetőségek kombinálása közben.</td>
<td>A kiszállítási idő kiszámításának meglévő algoritmusai alapján a <strong>Szállítási alternatívák </strong>oldal új felhasználói élményt kínál a rendelési ígérethez:
<ul>
<li>A több űrlapról származó vonatkozó információkat összegzi.</li>
<li>„Kész” alternatív szállítási csomagokat kínál, mint például a telephely/raktár/változat/szállítás kombinációjának módját, a leggyorsabb szállítási (legkorábbi elérhető dátum) feltételein alapulva, amelyek közül a felhasználó választhat.</li>
<li>Lehetővé teszi, hogy a felhasználó kiválassza a beállításokat szimulációs felületről, és áthelyezze őket az értékesítésirendelés-sorba.</li>
</ul></td>
<td>Azoknak a vállalatoknak, amelyek magas színvonalú ügyfélszolgálatot kívánnak biztosítani, miközben a készletoptimalizálási stratégiájuk felé is elkötelezettek, képesnek kell lenniük megbízható és versenyképes rendelésígéreteket tenni. Végső soron vevőik saját üzletei megkövetelik, hogy a termékek időben rendelkezésre álljanak. A <strong>Szállítási alternatívák</strong> feladatlapja a rendelésígéret feladatát gyorsabbá, egyszerűbbé és rendszerszerűbbé teszi azáltal, hogy a legjobb alternatív rendelésszállítási dátumokat egy interaktív helyen azonosítja és javasolja.</td>
</tr>
</tbody>
</table>

## <a name="service-management"></a>Szolgáltatáskezelés

Új funkciókat nem adtuk hozzá.

## <a name="transportation-management"></a>Szállításkezelés

Új funkciókat nem adtuk hozzá.

## <a name="travel-and-expense"></a>Utazás és költség

Új funkciókat nem adtuk hozzá.

## <a name="warehouse-management"></a>Raktárkezelés

| Mit lehet tenni? | Dynamics AX 2012 | Dynamics AX 7.0 | Miért fontos ez? |
|------------------|------------------|-----------------|------------------------|
| Raktári mobileszköz-portál letöltése, telepítése és konfigurálása. | A őportált letöltheti, telepítheti és konfigurálhatja a Microsoft Dynamics AX telepítési folyamata során normál beállításokon keresztül. Önálló, helyszíni telepítésre és konfigurációra tervezték. | A különálló telepítőt a menüelemen keresztül, a Raktári kezelésben töltheti le. Önálló, helyszíni telepítésre és konfigurációra tervezték. | Amikor a mobileszköz-funkciót beállítja, telepítenie és konfigurálnia kell a Raktári Mobileszköz-portált helyileg, és csatlakoznia kell a Dynamics AX programhoz a felhőben. |

## <a name="additional-resources"></a>További erőforrások

[Új vagy módosult elemek](whats-new-changed.md)

[Új feladat-útmutatók érhetők el (2016. február)](new-task-guides-available-february-2016.md)

