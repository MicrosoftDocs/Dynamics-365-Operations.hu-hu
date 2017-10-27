---
title: "Mi új vagy mi változott a Dynamics 365 for Operations 1611. verziójában (2016. november)"
description: "Ez a témakör ismerteti az új vagy módosított 1611 verziójú Dynamics 365 for Operations szolgáltatásokat."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, UnifiedOperations
ms.custom: 221294
ms.assetid: 357931ed-f843-4bf5-bc85-0da3de0619ec
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 908f854e5ca50f4298110c08c87fefd9427b5cc9
ms.openlocfilehash: a0cf474aeff991f24fb7b879330065db2063cbe2
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="whats-new-or-changed-in-dynamics-365-for-operations-version-1611-november-2016"></a>Mi új vagy mi változott a Dynamics 365 for Operations 1611. verziójában (2016. november)

[!include[banner](../includes/banner.md)]


Ez a témakör ismerteti az új vagy módosított 1611 verziójú Dynamics 365 for Operations szolgáltatásokat.

<a name="cost-accounting"></a>Költségkönyvelés
---------------

<table>




<thead>
<tr class="header">
<th>Mit lehet tenni</th>
<th>Miért fontos ez</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Költségelem-dimenziók meghatározása és költségelem-dimenziótagok importálása.</td>
<td>A költségelemeket a költségkönyvelésben használjuk a költségek csoportosítására és a költségek folyamatának dokumentálására. Az elsődleges költségelemek importálása vagy a Microsoft Dynamics 365 for Operations adatcsatlakozó segítségével történik a fő számlák közvetlen lekéréséhez az Operationsből, vagy egy általános adatcsatlakozóval, amelynél a Microsoft Excel használatával történik a fő számlák beolvasása bármilyen más típusú forrásrendszerből. A fő számlák költségkönyvelésbe importálása után költségösszetevő-dimenziótagokként használják őket. A másodlagos költségelemeket a felhasználó definiálja, és a felosztásokban használatosak a költségek folyamatának dokumentálására.</td>
</tr>
<tr class="even">
<td>Végezze el a költségösszetevő-dimenziók leképezését.</td>
<td>Ha a fő számlák a jogi személyek között jogszabályi könyvelési követelmények miatt nem oszthatók meg, hozzárendelheti őket az importálásuk után a költségkönyvelésbe a szervezet holisztikus megjelenítéséhez.</td>
</tr>
<tr class="odd">
<td>Költségobjektum-dimenziók meghatározása és költségobjektum-dimenziótagok importálása.</td>
<td>A költségobjektumok bármilyen típusú objektumok, amelyekhez költségek vannak rendelve. A tipikus költségobjektumok közé tartoznak a termékek, projektek, erőforrások, részlegek, költséghelyek és földrajzi területek. Használhatja a Microsoft Dynamics 365 for Operations adatcsatlakozót a pénzügyi dimenziók és értékek lekéréséhez az Operationsből, vagy használhat egy általános adatcsatlakozót, amelynél a Microsoft Excel használatával történik a dimenziók és értékek beolvasása bármilyen más típusú forrásrendszerből. Például az objektumdimenzióként a költséghely pénzügyi dimenziót használja, minden importált költséghely dimenziótagja a költségobjektumnak.</td>
</tr>
<tr class="even">
<td>Statisztikai dimenziók meghatározása vagy importálása</td>
<td>A statisztikai dimenziótagok mérése nem pénzbeni egységekben történik: ilyenek a gépórák, az alkalmazottak száma és a négyzetméter. Kivonatokban használjuk őket vagy a felosztások és elosztások alapjaként.</td>
</tr>
<tr class="odd">
<td>Statisztikai mérték szolgáltatójának sablonjainak létrehozása.</td>
<td>A statisztikai mérték szolgáltatójának sablonja segítségével a Dynamics 365 for Operations adatok statisztikai mértékekké alakíthatók át. Ekkor a sablonhoz társítanak egy adott statisztikai dimenziótagot. A sablonok előzetesen szűrtek, így csak a pénzügyi dimenziókhoz társított táblázatokat jelenítik meg.</td>
</tr>
<tr class="even">
<td>Költségkönyvelési főkönyvek létrehozása.</td>
<td>A költségkönyvelési főkönyv egy független főkönyv, amely saját naptárat és pénznemet használ. Az összes költségtranzakció feldolgozásában fontos szerepet játszik. Például a költségkönyvelési főkönyv a költségeket saját költségösszetevői alapján osztályozza, és összesíti a költségeket a saját objektumdimenziói alapján. Tetszőleges számú költségkönyvelési főkönyv hozható létre a vezetői jelentéskészítéshez a különböző szempontok szerint.</td>
</tr>
<tr class="odd">
<td>Költség-ellenőrzőegységek létrehozása.</td>
<td>A költség-ellenőrzőegységekből áll össze a költségszerkezet, és ezek határozzák meg a költségek folyamatát a költségkönyvelési főkönyvben. Társítani kell őket a költségobjektum-dimenziókhoz, hogy a képviseljék a költségobjektum-dimenziókat a főkönyvben.</td>
</tr>
<tr class="even">
<td>Főkönyvi bejegyzések feldolgozása.</td>
<td>A tényleges teljesítmény mérésére adatokat kell rendelkeznie. Az adatok importálása a költségkönyvelési főkönyvben megadott összekötők használatával történik. A főkönyvi bejegyzések feldolgozásakor az adatok importálása fokozatosan történik.</td>
</tr>
<tr class="odd">
<td>Költségvetési bejegyzések feldolgozása.</td>
<td>Az előirányzott teljesítmény mérésére adatokat kell rendelkeznie. Az adatok importálása a költségkönyvelési főkönyvben megadott összekötők használatával történik. A költségvetési bejegyzések feldolgozásakor az adatok importálása fokozatosan történik.</td>
</tr>
<tr class="even">
<td>Költségműködési irányelv létrehozása és alkalmazása.</td>
<td>A költségműködési irányelvvel a költségek rögzített, változó vagy félig változó költségként osztályozhatók. Az irányelvek szabályalapúak és dátumra vonatkozóak. Alapértelmezés szerint minden költség nem besorolt megjelölésű mindaddig, amíg nem alkalmaz egy költségműködési irányelvet és ki nem számolja a szabály hatásait. A számítást követően a költségek besorolttá válnak.</td>
</tr>
<tr class="odd">
<td>Költségek követése.</td>
<td>A költségirányelvek hatásának megértéséhez a költségkönyvelés lehetővé teszi a költségek nyomon követését a forrásértékhez és az eredetüknél alkalmazott szabályokhoz. Ez a funkció teljes nyomon követhetőséget nyújt arról, hogy mikor merültek fel a költségek, milyen típusú költségek merültek fel, és milyen költségműködési szabályokat alkalmaztak.</td>
</tr>
<tr class="even">
<td>Dimenzióhierarchiák megadása.</td>
<td>Dimenzióhierarchiák kategorizálási vagy osztályozási célokra hozhatók létre. Meghatározható például egy kategorizálási hierarchia, amely egy költségösszetevő-dimenzión és a tagjain alapul. Alternatívaként meghatározható egy osztályozási hierarchia, amely egy költségobjektum-dimenzión és a tagjain alapul. A jelentési struktúrákat a következő esetekben használjuk:
<ul>
<li>Felosztásokat,költségszorzókat és költségösszesítési szabályokat ad meg.</li>
<li>A munkaterület használatával tekinti meg a kimutatásokat.</li>
<li>Hozzáférést határoz meg az összesített adatok megtekintéséhez.</li>
<li>Megtekinti az adatokat az Excel programban.</li>
</ul></td>
</tr>
<tr class="odd">
<td>A munkaterületen megtekinthető kimutatásokat hoz létre.</td>
<td>Tényleges és tervezett költségek, valamint az eltérések gyors áttekintésére használja a munkaterületet. Az adatok időszak vagy költségszint szerint szűrhetők. A munkaterületet a költségellenőrzésére felelős vezetők számára tervezték. A dimenzióhierarchiákra meghatározott hozzáférési szabályok szerint működik.</td>
</tr>
<tr class="even">
<td>Jelentések létrehozása az Excel programmal. <strong>Megjegyzés:</strong> A Microsoft Excel 2016 verziót kell futtatnia.</td>
<td>A költségkönyvelési adatok közvetlenül exportálhatók az Excelbe adatentitásokkal, és a Microsoft PivotTable használatával lehet jelentéseket létrehozni.</td>
</tr>
</tbody>
</table>

## <a name="expense-management"></a>Költséggazdálkodás
| Mit lehet tenni                                                            | Miért fontos ez                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|----------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Kilépett alkalmazott hitelkártyás tranzakcióinak ismételt hozzárendelése.                     | Előfordul, hogy amikor egy alkalmazott munkaviszonya megszűnt, az Active Directory tartományi szolgáltatások fiókját le van tiltva, amikor kötelezően elszámolandó aktív hitelkártya-tranzakciók importálása történik. Korábban nem lehetett költségbeviteli delegáltat hozzárendelni vagy hitelkártya-tranzakciót csatolni költségjelentéshez. Használható a **Hitelkártyás tranzakciók** oldal az ismételt hozzárendeléséhez az alkalmazottnak minden hitelkártya-tranzakció esetében, ahol a társított alkalmazott kilépett. A hitelkártyás tranzakció ismételt hozzárendelése után a tranzakció kiválasztható egy költségjelentéshez, és a költségjelentések normál visszaigénylési folyamatával fizethető ki a visszatérítés. |
| A költségekhez kapcsolódó hitelkártyaadatok módosítása függő és korábbi alkalmazottak esetében. | A költségkezelési hitelkártyaadatok módosíthatók a függő dolgozók és a korábbi dolgozók esetében. Korábban csak akkor lehetett módosítani a költség hitelkártyaadatait, ha a dolgozó aktív alkalmazott volt.                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Költségjelentés másolása.                                                    | Egy meglévő költséget már át lehet másolni ugyanabban a költségjelentésben egy új költség létrehozásakor. A meglévő költségjelentéseket és az összes kapcsolódó nem hitelkártya költséget át lehet másolni egy új költségjelentésbe. Még minden szükséges az elemekre bontás és a nyugták csatolása a meghatározott költségszabályok és kategóriák alapján. A hitelkártya-tranzakciók költségjelentéshez adhatók a nem egyeztetett költségek hozzáadásának kiválasztásával.                                                                                                                                                                                                                        |
| Költségek tömeges szerkesztése.                                                        | Előfordulhat, hogy néhány hitelkártyás tranzakció nem lett hozzárendelve egy költségkategóriához, vagy hibásan lett hozzárendelve az importáláskor. Az alkalmazottnak ebben az esetben manuálisan kell módosítania a kapcsolódó költségkategóriát. A nem egyeztetett költségek kezelésekor most már tömegesen szerkeszthető a kiválasztott költségek költségkategóriája. Ezenkívül egy adott költségjelentés kiválasztott kiadásainak kezelésekor lehetőség van a projekt és a további információk tömeges szerkesztésére.                                                                                                                                                                                    |
| A hitelkártyás tranzakciók árfolyamának módosítása.                     | A tényleges, a hitelkártya-tranzakcióhoz használt árfolyam, és a rendszerben beállított árfolyam különbözhet. Az alkalmazottak korábban egy, a Költséggazdálkodásba importált hitelkártya-tranzakció átváltási árfolyamát sem módosíthatták. Most már beállítható egy paraméter a **Költséggazdálkodási paraméterek** lapon, amely engedélyezi a hitelkártya-tranzakciók átváltási árfolyamának módosítását.                                                                                                                                                                                                                                            |
| Korrupcióellenes nyilatkozat beállítása a költségekhez.                            | A szervezetek néhány alkalmazottja üzleti kapcsolatba kerülhet állami hivatalnokokkal, és az üzleti kapcsolat részeként keletkező költségek egy részét korrupciógyanúsnak tekinthetik. A költséggazdálkodásban most már beállítható a korrupcióellenes nyilatkozat, amely megjelenik a kijelölt költségkategóriák, például az étkezés és az ajándékok esetében. Alkalmazottaknak ki kell választaniuk, hogy a korrupcióellenes nyilatkozattételhez beállított költségek megfelelnek a szervezet irányelveiben lefektetett feltételeknek.                                                                                                                                                                                     |
| Az adott költségkategóriákba történő manuális költségbevitel megakadályozása.          | A költségkategóriákra beállítható, hogy olyan hitelkártyás tranzakciót jelöljenek, amelyre nem módosítható a kategória.. Például késedelmes fizetés miatti hitelkártyadíj. Mostantól beállítható egy költségkategória, amelynél a költségeket csak importálással lehet létrehozni. Ez a funkció megakadályozza, hogy az alkalmazottak manuálisan hozzanak létre egy költséget a kategóriában. Ugyancsak nem teszi lehetővé a kategória módosítását az importált, és ezt a kategóriát használó tranzakciók esetében.                                                                                                                                                                                   |
| Nyugta csatolása több költséghez.                                     | A költséggazdálkodásba feltöltött nyugták több költséggel is kapcsolatosak lehetnek. Korábban a több költséghez köthető nyugtákat mindegyik költséghez külön fel kellett tölteni. A nyugta most már csatolható egy már feltöltött költséghez, és csatolható egy másik költséghez ugyanabban a költségjelentésben. Ezenkívül ha feltölt egy nyugtát a költségjelentés fejlécébe, választhat egy vagy több sort, amelyhez a nyugta csatolása történik.                                                                                                                                                                                        |
| Jövőbeli dátumú költségek létrehozása.                                              | Például költségjelentés másolásakor egy adott költség tranzakciódátuma jövőbeli dátum is lehet. A korábbi kiadásokban nem voltak engedélyezettek a jövőbeli dátumú költségek. Most már létrehozhatók és menthetők jövőbeli dátumú költségek. Azonban nem küldhetők el jövőbe dátumú költségek.                                                                                                                                                                                                                                                                                                                                                                                 |
| Költség utáni adó beállítása államhoz/tartományhoz.                              | Néhány országban/régióban az egyes államokban/tartományokban felmerült költségek eltérő áfakulcsok hatálya alá tartozhatnak. A költség utáni adó most már állam/tartomány szintjén, és nem csak az ország/terület szintjén állítható be. Ha az **Állam/tartomány** mezőt üresen hagyja az **Adókonfiguráció** lapon, az áfacsoport az adott ország/régió minden államára/tartományára vonatkozik.                                                                                                                                                                                                                                       |
| Költség-hitelkártyatípusok beállítása                                          | Korábban nem volt olyan lap, amelyen új hitelkártyatípusokat lehetett létrehozni a Költséggazdálkodás modulban történő használathoz (például Visa, MasterCard vagy AMEX). Most már létre lehet hozni hitelkártyatípusokat a Költséggazdálkodás modulban való használathoz. Az oldal a **Beállítás** területen található, a **Számítások és kódok** szakaszban.                                                                                                                                                                                                                                                                                                                                                 |
| Többszintű jóváhagyási munkafolyamat meghatározása a költségjelentésekhez.                 | A költségjelentések új munkafolyamata támogatja a többszintű jóváhagyási folyamatot. Az alkalmazottak megadják az ideiglenes jóváhagyókat és a végleges jóváhagyókat a költségjelentés létrehozásakor. A munkafolyamat először az ideiglenes jóváhagyóhoz irányítja a költségjelentést. A költségjelentést az ezen a szinten történő jóváhagyása után a munkafolyamat továbbítja végleges jóváhagyásra a végső jóváhagyóhoz.                                                                                                                                                                                                                                                                                          |
| Költségjelentéshez nem csatolt költségek létrehozása és karbantartása.    | A felhasználók most már létrehozhatnak és karbantarthatnak költségeket (például úgy, hogy csatolnak vagy tételesen részleteznek nyugtákat, vagy vendégeket rendelnek hozzá) költségjelentés előzetes létrehozása nélkül. Egy vagy több költség kijelölhető és egy új költségjelentéshez adható, hogy elküldhetők legyenek jóváhagyásra. A költségek karbantartásához új lap érhető el: **Költséggazdálkodás** &gt; **Költségeim** &gt; **Költségek**.                                                                                                                                                                                                                                                       |

## <a name="financial-management"></a>Pénzgazdálkodás
<table>




<thead>
<tr class="header">
<th>Mit lehet tenni</th>
<th>Miért fontos ez</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>A tárgyieszköz-értékelések nyomon követése egyetlen „könyv” koncepció segítségével.</td>
<td>Korábban kétféle értékelés volt használatban a tárgyieszköz-értékek nyomon követésére: értékmodellek és értékcsökkenési könyvek. Az aktuális verzióban a két koncepciót egyesítettük egyetlen értékelési koncepcióba, amelynek a neve könyv. A könyvek az értékmodellek és az értékcsökkenési könyvek összes funkcióját tartalmazzák. Például kikapcsolhatja a főkönyvbe történő feladást. A főkönyvbe feladó könyveket általában vállalati pénzügyi jelentési célokra használják. A főkönyvbe fel nem adó könyvek adóbevallási célokra használhatók.</td>
</tr>
<tr class="even">
<td>Főkönyvi év végi zárás végrehajtása több jogi személyhez.</td>
<td>Az év végi zárási folyamat felgyorsítására most már futtathatja az év végi zárást több jogi személynél, a megosztott év végi zárás lapról. Jogi személyek csoportjai határozhatók meg, olyan beállításokkal együtt, amelyeket egyik évről a következőre meg kell tartani. Egyéb használhatósági fejlesztések is történtek az év végi zárási folyamat esetében.</td>
</tr>
<tr class="odd">
<td>A főkönyvi devizaátértékelés fejlesztéseinek kihasználása.</td>
<td>A következő fejlesztések történtek a devizaátértékelés főkönyvi folyamatait érintően:
<ul>
<li>A fő számlához hozzá lett adva egy árfolyamtípus. Most már ez az árfolyamtípus használt az árfolyam meghatározásához az árfolyamátértékelés során. Ha nincs beállítva árfolyamtípus, a folyamat továbbra is a főkönyvben definiált árfolyamtípust használja.</li>
<li>Most már egyszerűbb fő számlákat és devizákat kiválasztani, amelyekre futtatni kell az átértékelési folyamatot.</li>
<li>Az átértékelési több jogi személynél futtatható.</li>
<li>A rendszer most már menti minden átértékelési folyamat előzményeit, ahogy a kinnlevőségek (AR) és a kötelezettségek (AP) átértékelési folyamatok előzményeit is.</li>
<li>A folyamat futtatásakor most már megtekintheti az átértékelés eredményének előnézetét. Az előnézet minden olyan jogi személy eredményeit megjeleníti, amelyre a folyamatot futtatták. Az előnézetből feladhatók a jogi személyek, vagy a jogi személyek valamely alkészlete. Az Excel programba exportálhatja az előnézet eredményeit.</li>
</ul></td>
</tr>
<tr class="even">
<td>További feladási rétegek tranzakcióinak megtekintése.</td>
<td>A <strong>Főkönyvi kivonat</strong> listaoldalon és a <strong>Dimenziókimutatás</strong> jelentésben most már kiválaszthatja a főkönyvbe felvett további feladási rétegeket. A további feladási rétegek kiválasztásakor a feladási rétegek kiigazításai bekerülnek az egyenlegekbe a listalapon vagy a jelentésben.</td>
</tr>
<tr class="odd">
<td>Útmutató dokumentáció csatolása a pénzügyi időszak lezárása sablonhoz.</td>
<td>Korábban a feladatok befejeződése után lehetett dokumentációt csatolni. Például csatolható volt egy generált jelentés. Most már útmutató dokumentumot is csatolhat a sablonhoz. Ezt az útmutató dokumentumot aztán átmásolja a rendszer a pénzügyi időszak ütemezésében szereplő minden egyes feladathoz, hogy a feladat tulajdonosa útmutatást tekinthessen meg arról, hogyan kell elvégezni a feladatot.</td>
</tr>
<tr class="even">
<td>Vállalatközi könyvelés beállításának megadása megosztott lapról.</td>
<td>A <strong>Vállalatközi könyvelés beállítási lapja</strong> most már meg van osztva, hogy a szervezet megadhassa azokat a jogiszemély-párokat, amelyek tranzakciókat bonyolíthatnak le egymással. Emellett most már meg lehet adni egy tranzakció a kiinduló jogi személynél, a cél jogi személynél viszont nem. Ha bármelyik jogi személy kezdeményezheti a vállalatközi tranzakciót, kölcsönös párt kell megadni. Emiatt a cél jogi személy is be van állítva kiinduló jogi személyként.</td>
</tr>
<tr class="odd">
<td>Indoklási dokumentumok benyújtása a költségvetési tervekhez.</td>
<td>Bármilyen kért költségvetési összeghez létre lehet hozni indoklási sablont kiegészítő dokumentációként. A felhasználók kitölthetik a sablon részletes adatait, és a sablont csatolhatják a költségvetési tervhez, hogy a jóváhagyási folyamat közben is használni lehessen.</td>
</tr>
<tr class="even">
<td>Speciális szabályok engedélyezése a költségvetési tételjegyzék-bejegyzésekhez.</td>
<td>Ha a főkönyvben speciális szabályok vannak beállítva, ezek a szabályok az új bejegyzésekhez és átvitelekhez is használhatók a költségvetési tételjegyzékben.</td>
</tr>
<tr class="odd">
<td>Az előlegszámlázási tevékenység továbbfejlesztett láthatósága előnyeinek kihasználása.</td>
<td>Új <strong>Nyitott előlegek</strong> listaoldal nyújtja az előlegszámlázási tevékenység állapotának pillanatképét. Az oldal a Kötelezettségek részleget látja el információval a fennmaradó előleg-értékekről, amelyeket számlázni kell, a számlázott értékekről, amelyeket ki kell fizetni, és a kifizetett számlaértékekről, amelyeket a normál számlákra kell alkalmazni. Emellett a számlázási ügyintézők számára az adatbevitel hatékonyabbá tételét segítik az előlegszámláknak a normális számlákra történő automatikus alkalmazását érintő továbbfejlesztések.</td>
</tr>
<tr class="even">
<td><strong>Szállítói együttműködési számlázás munkaterületének</strong> használata.</td>
<td>Az új <strong>Számlázás</strong> munkaterület a <strong>Szállítói együttműködési</strong> területen lehetővé teszi a külső szállítók számára a saját számlaadataik biztonságos elérését. A szállítók például láthatják, hogy kifizették-e a számlájukat, és saját számlát küldhetnek be. Ez a módosítás elősegíti a hatékonyabb és gyorsabb kommunikációt a külső szállítókkal. Emiatt a számlázási ügyintézők kevesebb zavart tapasztalnak.</td>
</tr>
<tr class="odd">
<td>Jogi személyek váltása a számla bevitelekor.</td>
<td>A fejlesztések lehetővé teszik a számlázási ügyintéző számára, akinek több jogi személyhez kell gyorsan számlákat bevinni, a jogi személy módosítását a számlázási oldalon. Ez a funkció időt takarít meg a számlázási ügyintéző számára, mivel nem kell kijelentkezniük az aktuális jogi személyből és bejelentkezni egy másik jogi személyhez. A <strong>Globális számlanapló</strong> és a <strong>Szállítói számlák</strong> lap egyaránt engedélyezi a felhasználóknak a jogi személy módosítását adatbevitel közben.</td>
</tr>
<tr class="even">
<td>Az USA adóhatósága (IRS) 1099-es kombinált szövetségi/állami benyújtási programja szerinti elektronikus fájlok támogatása</td>
<td>Ha az <strong>Egyesült Államok</strong> konfigurációs kulcs engedélyezve van, akkor az 1099-es elektronikus benyújtási folyamat további funkciót biztosít, amely megfelel-e az IRS előírásainak a kombinált szövetségi és állami bevallási programra nézve. Az IRS azért hozta létre a programot, hogy elektronikus úton továbbíthassa az információkat a részt vevő államoknak.</td>
</tr>
<tr class="odd">
<td>A kiegyenlítést érintő fejlesztések</td>
<td>A továbbfejlesztett funkciók megkönnyítik a pénzügyi ügyintézők munkáját, hatékonyabbá téve a kiegyenlítést, mivel az ügyintéző több nem feladott kifizetés kiegyenlítését engedélyezheti ugyanazon számla ellenében.</td>
</tr>
<tr class="even">
<td>Vállalatközi nézet</td>
<td>A központosított kifizetési ügyintéző most már több vállalatra kiterjedően tekintheti meg a lejárt számlákat. A <strong>Szállítói kifizetések</strong> és <strong>Vevői kifizetések</strong> munkaterületek mostantól jobb rálátást nyújtanak a lejárt határidejű számlákra és a kezelésüket is továbbfejlesztik, lehetővé téve a megtekintést és a szűrést a központosított kifizetés szervezeti hierarchiába tartozó vállalatokra nézve.</td>
</tr>
<tr class="odd">
<td>A <strong>Bankszámla kezelése</strong> munkaterület használata.</td>
<td>Az új <strong>Bankszámla kezelése</strong> munkaterület segít nyomon követni a bankszámlákat és egyenlegeket a jogi személyeknél. Azonnal rendelkezésre állnak az aktuális és a függő egyenlegek az összes számlához, és az egyenlegektől lefúrhat a tranzakciók részletes bizonylataiig. Emellett megtekintheti a korábbi egyenlegadatokat minden egyes bankszámlához, vagy a vállalaton belül minden bankszámlára összegzését, rövid és hosszú távon nézetben egyaránt. Jobb betekintést kaphat a bankszámla-egyeztetésbe, mivel minden egyes bankszámlához jelentés áll rendelkezésre a legutóbbi egyeztetésről, és a folyamatban lévő egyeztetésekről is van jelzés.</td>
</tr>
<tr class="even">
<td>Elektronikus banki kivonatok importálása az összes jogi személy esetében egy lépésben.</td>
<td>Most már importálhatja az elektronikus banki kivonatokat az összes jogi személy esetében egy lépésben. A bankikivonat-fájlok számos bankszámla és jogi személy kivonatait tartalmazhatják, a zip-fájlok pedig több bankikivonat-fájlt tartalmazhatnak. Az egyetlen importálási folyamat segítségével elindíthatja az összes jelentett bankszámla egyeztetését minden jogi személyhez. A funkcióval idő takarítható meg, mert nem kell váltani a vállalatok és több kimutatásimportálás között. Emellett automatikusan futtathatók egyeztetési szabályok az összes importált kimutatásra, mindegyik vállalatnál.</td>
</tr>
<tr class="odd">
<td>Értékelések nyomon követése</td>
<td>Egy tárgyi eszközhöz több értékelés tartozhat az eltérő könyvelési szabványok szerint, és opcionálisan feladhatja a kapcsolódó tranzakciókat a főkönyvbe. Korábban ezeknek az értékeléseknek a nyomon követése az értékmodellek vagy az értékcsökkenési könyvek segítségével történt. Most már nyomon követheti ezeket az értékeléseket, amelyek most a könyv nevet viselik, naplók, lekérdezések és jelentések közös készletének használatával. Az egyesített tapasztalat egyszerűbbé teszi a végrehajtást, és csökkenti az időszakos folyamatokhoz szükséges felületek számát.</td>
</tr>
<tr class="even">
<td>Használja ki a több vállalatot érintő értékcsökkenési futtatások továbbfejlesztéseinek előnyeit.</td>
<td>Mostantól egyetlen lapról indíthatja az eszközök értékcsökkenési futtatását minden jogi személyt lefedve. Emellett a naplók létrehozásuk után automatikusan adhatók fel. A naplók létrehozása és feladása beküldhető kötegelt feldolgozásra, úgy, hogy az értékcsökkenés a háttérben fusson. Ezek a fejlesztések csökkentik a hatékonysági problémákat, mivel nem kell minden vállalatnál külön elindítani az értékcsökkenési futtatást. A továbbfejlesztés emellett a tárgyi eszközök jobb központosított kezelését is lehetővé teszi.</td>
</tr>
</tbody>
</table>

## <a name="human-capital-management"></a>Emberierőforrás-menedzselés
| Mit lehet tenni                                                                                | Miért fontos ez                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Teljesítménynapló létrehozása.                                                                  | Az értékelés befejezése előtt gyakran gyűjtjük be az adatokat azokról a tevékenységekről vagy eseményekről, amelyek hozzájárultak a sikerünkhöz alkalmazottként az értékelési időszak során. Az ilyen tevékenységek és események dokumentálásához bejegyzést hozhatunk létre a teljesítménynaplóban. A tevékenységeket és eseményeket emellett hozzákapcsolhatjuk egy célhoz vagy teljesítményértékeléshez, hogy további információkat nyújthassunk az értékelés vezetőjének.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Részletesebb célok létrehozása.                                                                    | Nagyobb befolyást kap a beállított célok tartalma felett. Méréseket hozhat létre a célokhoz, teljesítmény-naplóbejegyzéseket csatolhat a mérésekhez, és dokumentumokat csatolhat és tekinthet meg. A célokat tárolhatja sablonként, és felhasználhatja őket a gyors beállításhoz.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Részletesebb teljesítményértékelések létrehozása.                                                      | A teljesítményértékelések vagy korábban vitafórumok most már elég rugalmasak ahhoz, támogassák a folyamatos visszajelzést és a formálisabb értékeléseket. Aktív célokat vonhat be és megjegyzéseket írhat velük kapcsolatban, továbbá szakaszokat adhat hozzá a kompetenciái értékeléséhez. További szakaszok érhetők el, ahol méréseket, teljesítménynapló-bejegyzéseket, mellékleteket és az értékeléshez kapcsolódó láttamozásokat adhat hozzá és tekinthet meg.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| További beosztáshierarchiák társítása a munkafolyamatokkal.                                      | A munkafolyamatok beosztáshierarchiákkal társíthatók. Emellett módosíthatja a munkafolyamat-lépéseket a jóváhagyási folyamat optimalizálásához, megfeleljen az üzleti követelményeknek. Ez azt jelenti, hogy hatékony jóváhagyási struktúrát definiálhat, amely illeszkedik a szervezet által használt különböző jelentési kapcsolatokhoz.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Munkafolyamat-támogatás a személyes azonosítószámok (PIN) megadásához az alkalmazotti önkiszolgáló rendszerben. | Az emberi erőforrások munkafolyamat képességeit bővítettük, és most már támogatja a PIN-kódokat is. Az alkalmazottak hozzáadhatják és szerkeszthetik a PIN-kódjukat a hatékonyság növelésének érdekében. Azonban a HR-dolgozók felülvizsgálhatják az információ pontosságát és hiánytalanságát a hozzáadása előtt az alkalmazotti rekordhoz.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Célsablonok létrehozása és használata új célok hozzáadásához.                                          | Célsablonokat hozhat létre az olyan célokhoz, amelyeken a vállalat sok alkalmazottja osztozik. Az alkalmazottak hozzáadhatják a saját céljaikat egy sablon alapján, a vezetők célokat adhatnak hozzá a csapatuk számára egy sablon alapján, a HR-csapat tagjai pedig a vállalat alkalmazottai számára adhatnak hozzá célokat.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Célcsoportok létrehozása és használata új célok hozzáadásához.                                             | Célsablonok adhatók egy csoporthoz, és a csoport egy vagy több cél létrehozására használható egy alkalmazott, csoport, beosztás, részleg vagy a vállalat számára.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Az értékelési folyamat feletti nagyobb ellenőrzés.                                                     | A munkafolyamatot az értékelési folyamat nagyobb mértékű ellenőrzéshez használhatja. Értékelési sablonokat hozhat létre, amelyeket értékelések létrehozására használhat. Az értékelésekhez minősítések is hozzáadhatók.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Értékelési időszakok használata az értékelés időkeretének meghatározásához.                                    | Megadhatja a teljesítményértékelés időkeretét, és az értékelés kezdő és záró dátumát automatikusan kitölti a rendszer. Azonban szükség szerint módosíthatja ezeket az alapértelmezett dátumokat.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Öt új Power BI tartalmi csomag az Emberi erőforrásokhoz                                     | Az új tartalmi csomagok lehetővé teszik az emberierőforrás-szervezetek és az emberierőforrás-menedzserek számára a következők elemzését: Munkaerő-mutatók • Demográfiai lebontások életkor, nem és családi állapot alapján • A veszteségarányok összevetése az évek során, illetve azoknak az okoknak a megtekintése, amelyeket a munkavállalók megadtak a szervezet elhagyásának okaként • A nyitott pozíciók megtekintése, valamint a nyitott pozíciók összevetése a zárt pozíciókkal – Kompenzáció és juttatások • Órabért és fizetést kapó alkalmazottak összehasonlítása • A rendelkezésre álló juttatásoknál regisztrált alkalmazottak száma • Alkalmazottak megtekintése az alkalmazott-típus toborzás szerint • Jelentkezők elemzése a jelentkezők száma alapján, az alapján, hogy honnan jönnek, továbbá az alapján, hogy milyen pozícióknál jelentkeznek szervezeti képzésre • Tanfolyamokra való regisztrálás hely szerint • Tanfolyamokon való részvétel állapot szerint • A kurzusokra regisztrált alkalmazottak listája – Munkavállalói kompetenciák és fejlesztés • Lista az alkalmazottaknál nyilvántartott szakértelmekről. • Készségtípusok felosztása csapattagok szerint |

## <a name="localizations"></a>Honosítások
<table>




<thead>
<tr class="header">
<th>Mit lehet tenni</th>
<th>Miért fontos ez</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Honosítások 18 további ország esetében érhetők el:
<ul>
<li>Ausztria</li>
<li>Belgium</li>
<li>Brazília</li>
<li>Kína</li>
<li>Cseh Köztársaság</li>
<li>Észtország</li>
<li>Finnország</li>
<li>Magyarország</li>
<li>Olaszország</li>
<li>Lettország</li>
<li>Litvánia</li>
<li>Norvégia</li>
<li>Lengyelország</li>
<li>Szaúd-Arábia</li>
<li>Spanyolország</li>
<li>Svédország</li>
<li>Svájc</li>
<li>Thaiföld</li>
</ul>
A következő országok szintén igénylik a kiskereskedelmi honosítást. A kiskereskedelmi honosítás ezen országok esetében még nem fejeződött be, és csak H1 CY2017-re tervezett:
<ul>
<li>Brazília</li>
<li>Cseh Köztársaság</li>
<li>Észtország</li>
<li>Magyarország</li>
<li>Lettország</li>
<li>Litvánia</li>
<li>Malajzia</li>
<li>Lengyelország</li>
<li>Svédország</li>
</ul></td>
<td>A Dynamics 365 for Operations 18 további országban érhető el. A könnyebb és jobban konfigurálható honosítás megvalósításának részeként a szabályozói elektronikus jelentési funkciókat elektronikus jelentési (ER) konfigurációkká konvertáltuk, és néhány szabályozói Microsoft SQL Server Reporting Services (SSRS) jelentést Excel-sablonokat használó ER-konfigurációkká konvertáltuk. Ezeket a konvertált funkciókat részletesen ismertetjük később a táblázatban.</td>
</tr>
<tr class="even">
<td>Japán – Tárgyi eszközök csoportosítása a 26. űrlapból és hozzá fűzött táblákból való nyomtatásakor.</td>
<td>A 26. űrlapot minden város esetében be kell nyújtani, ahol a vállalat tevékenykedik. A munkaráfordítás csökkentése érdekében a 26. űrlap nyomtatásakor a tárgyi eszközök automatikusan csoportosíthatók és hely szerint vannak rendezve.</td>
</tr>
<tr class="odd">
<td>Japán – Az összegek megtekintése a profilban a gyorsított, valamint a további értékcsökkenés esetében.</td>
<td>A profil pontos becslést ad az összegekről a gyorsított, valamint további értékcsökkenés esetében.</td>
</tr>
<tr class="even">
<td>Japán – Adóelőleg progresszív kiszámítása.</td>
<td>A japán kormány megköveteli az adóelőleg progresszív számítását, a kifizetés összege alapján.</td>
</tr>
<tr class="odd">
<td>Japán – Postaiirányítószám-fájl importálása adott nagy vállalati épületek esetében.</td>
<td>A postaiirányítószám-fájl, amelyet a hatóság egyedi nagy vállalati épületekhez bocsájt ki, importálható a rendszerbe. A cím ezután az irányítószámokból származtatható.</td>
</tr>
<tr class="even">
<td>Japán – Tétlen időszak beállítása a tárgyi eszközökhöz.</td>
<td>Az üresjárati időszakok lehetővé teszik, hogy a felhasználó megadott időszak alatt felfüggessze a tárgyi eszközök értékcsökkenését. Ezt a funkciót a jogszabályi előírások teszik szükségessé.</td>
</tr>
<tr class="odd">
<td>Európa – Általános forgalmi adó (áfa) regisztrációs azonosító beállítása egy fél címéhez a nyilvántartásiazonosító-keretrendszer használatával.</td>
<td>Áfaregisztrációs-szám konfigurálható adott fél címéhez a nyilvántartásiazonosító-keretrendszer és az <strong>Adószám</strong> nevű új regisztrációs kategória használatával.</td>
</tr>
<tr class="even">
<td>Finnország – Vámhivatali vevőazonosító beállítása egy fél címéhez a nyilvántartásiazonosító-keretrendszer használatával.</td>
<td>Vámhivatali vevőazonosító konfigurálható adott fél címéhez a nyilvántartásiazonosító-keretrendszer és a <strong>Vámhivatali vevőazonosító</strong> nevű új regisztrációs kategória használatával.</td>
</tr>
<tr class="odd">
<td>Franciaország – Vevői számlák nyomtatása Franciaországra specifikus elrendezésben.</td>
<td>A vevői számla nyomtatása módosul a franciaországi követelmények teljesítéséhez.</td>
</tr>
<tr class="even">
<td>Franciaország – Dokumentumok időrendi számozásának kikényszerítése pénzügyi időszakonként.</td>
<td>A vevői számlák számozásával kapcsolatos franciaországi követelmények teljesítéséhez pénzügyi időszakonként számsorozatokat lehet beállítani a vevői számlákhoz.</td>
</tr>
<tr class="odd">
<td>Ausztriai honosítás – ER-konfigurációk</td>
<td><ul>
<li>Ausztriai XML-formátumú EU-s értékesítési lista</li>
<li>Intrastat formátum Ausztria esetében</li>
<li>ISO20022 átutalási fizetési formátum Ausztria esetében</li>
<li>ISO20022 beszedési megbízási fizetési formátum Ausztria esetében</li>
<li>Ausztriai EDIFACT-PAYMUL formátum</li>
<li>Ausztriai áfabevallás</li>
</ul></td>
</tr>
<tr class="even">
<td>Belgiumi honosítás – ER-konfigurációk</td>
<td><ul>
<li>BLWI-formátum Belgium esetében</li>
<li>Belgiumi XML-formátumú EU-s értékesítési lista</li>
<li>Tárgyieszköz-jelentés Belgium esetében</li>
<li>Intervat formátum Belgium esetében</li>
<li>Belgiumi Intrastat formátum</li>
<li>Számlaforgalmi jelentés Belgium esetében</li>
<li>Főkönyvi tranzakció exportformátum Belgium esetében</li>
<li>SWIFT szállítói fizetési formátum Belgium esetében</li>
<li>CODA banki kivonat importálási formátum Belgium esetében</li>
<li>ISO20022 átutalási fizetési formátum Belgium esetében</li>
<li>ISO20022 beszedési megbízási fizetési formátum Belgium esetében</li>
</ul></td>
</tr>
<tr class="odd">
<td>Brazil honosítás – ER-konfigurációk</td>
<td><ul>
<li>GIA SP Brazília esetében</li>
<li>GIA-ST Brazília esetében</li>
</ul></td>
</tr>
<tr class="even">
<td>Csehországi honosítás – ER-konfigurációk</td>
<td><ul>
<li>XML-formátumú EU-s értékesítési lista a Cseh Köztársaság esetében</li>
<li>Intrastat formátum a Cseh Köztársaság esetében</li>
<li>Áfabevallás a Cseh Köztársaság számára</li>
</ul></td>
</tr>
<tr class="odd">
<td>Kínai honosítás – ER-konfigurációk</td>
<td><ul>
<li>Vevői korosítási jelentési formátum Kína esetében</li>
<li>Vevői esedékes összeg elemzési jelentésformátum Kínai esetében</li>
<li>Kínai szállítói korosítási jelentés formátum</li>
<li>Szállítói esedékes összeg elemzési jelentésformátum Kínai esetében</li>
<li>Kinnlevőség-kifizetés korosítási elemzési formátum Kína esetében</li>
<li>Vevői egyenlegjelentési formátum Kína esetében</li>
<li>Főkönyvi egyenlegjelentési formátum Kína esetében</li>
<li>Szállítói egyenlegjelentési formátum Kína esetében</li>
<li>GBT-fájl Kína esetében</li>
<li>Formátum a Golden adóexportálási formátumhoz</li>
<li>Termelésfelhasználási eltérésjelentési formátum Kína számára</li>
</ul></td>
</tr>
<tr class="even">
<td>Észtországi honosítás – ER-konfigurációk</td>
<td><ul>
<li>Észtországi XML-formátumú EU-s értékesítési lista</li>
<li>Intrastat formátum Észtország esetében</li>
<li>Készletkimutatás-átsorolási kimutatás Észtország esetében</li>
<li>ISO20022 átutalási fizetési formátum Észtország esetében</li>
<li>Vevői szállítói egyenlegértesítési jelentés Észtország esetében</li>
<li>Észtországi áfabevallás</li>
</ul></td>
</tr>
<tr class="odd">
<td>Finnországi honosítás – ER-konfigurációk</td>
<td><ul>
<li>EU-s értékesítési lista TXT-formátumban Finnország esetében</li>
<li>Intrastat formátum Finnország esetében</li>
<li>ISO20022 átutalási fizetési formátum Finnország esetében</li>
</ul></td>
</tr>
<tr class="even">
<td>Magyarországi honosítás – ER-konfigurációk</td>
<td><ul>
<li>Magyarországi XML-formátumú EU-s értékesítési lista</li>
<li>Intrastat formátum Magyarország esetében</li>
<li>Egyszerűsített Intrastat formátum Magyarország esetében</li>
<li>Számlalista exportálási formátuma Magyarország esetében</li>
<li>Magyarországi áfabevallás</li>
<li>Magyarországi részletezett áfabevallás</li>
<li>Készletkimutatás Magyarország esetében</li>
<li>MultiCash fizetési formátum Magyarország esetében</li>
</ul></td>
</tr>
<tr class="odd">
<td>Olaszországi honosítás – ER-konfigurációk</td>
<td><ul>
<li>Intrastat formátum Olaszország esetében</li>
<li>Projektszámla-formátum Olaszország számára</li>
<li>Értékesítésiszámla-formátum Olaszország számára</li>
<li>ISO20022 átutalási fizetési formátum Olaszország esetében</li>
<li>ISO20022 beszedési megbízási fizetési formátum Olaszország esetében</li>
<li>RIBA gyűjtemény átutalási formátum Olaszország esetében</li>
<li>Belföldi adótranzakció-jelentés Olaszország esetében</li>
<li>Tiltólista-jelentés Olaszország esetében</li>
<li>Modello770 jelentés Olaszország esetében</li>
<li>Éves adóügyi kommunikációs jelentés Olaszország esetében</li>
</ul></td>
</tr>
<tr class="even">
<td>Lettországi honosítás – ER-konfigurációk</td>
<td><ul>
<li>Készpénzbefizetések használati jelentése Lettország esetében</li>
<li>Lettországi XML-formátumú EU-s értékesítési lista</li>
<li>Lettországi XML-formátumú EU-s értékesítési lista javítások</li>
<li>Intrastat (A) formátum Lettország esetében</li>
<li>Intrastat (B) formátum Lettország esetében</li>
<li>Leltárlistakészlet Lettország esetében</li>
<li>Leltárkimutatáskészlet Lettország esetében</li>
<li>Készletmozgás Lettország esetében</li>
<li>Belső szállítás szállítólevele Lettország esetében</li>
<li>Készletátsorolási bizonylat Lettország esetében</li>
<li>ISO20022 átutalási fizetési formátum Lettország esetében</li>
<li>Lettországi áfabevallás</li>
</ul></td>
</tr>
<tr class="odd">
<td>Litvániai honosítás – ER-konfigurációk</td>
<td><ul>
<li>Litvániai XML-formátumú EU-s értékesítési lista</li>
<li>Intrastat formátum Litvánia esetében</li>
<li>Készletkimutatás Litvánia esetében</li>
<li>ISO20022 átutalási fizetési formátum Litvánia esetében</li>
<li>Vevő és szállító közötti egyeztetési jelentés Litvánia esetében</li>
<li>Litvániai áfabevallás</li>
</ul></td>
</tr>
<tr class="even">
<td>Norvégiai honosítás – ER-konfigurációk</td>
<td><ul>
<li>Fizetési felszólítás formátuma Norvégia esetében</li>
<li>AutoGiro fizetési formátum Norvégia esetében</li>
<li>AvtaleGiro vevői kifizetési formátum Norvégia esetében</li>
<li>eFaktura vevői kifizetési formátum Norvégia esetében</li>
<li>ISO20022 átutalási fizetési formátum Norvégia esetében</li>
<li>NETS fizetési formátum Norvégia esetében</li>
</ul></td>
</tr>
<tr class="odd">
<td>Lengyelországi honosítás – ER-konfigurációk</td>
<td><ul>
<li>Intrastat formátum Lengyelország esetében</li>
<li>Raktári bizonylatok Lengyelország esetében</li>
<li>Készletátsorolási bizonylat Lengyelország esetében</li>
<li>MultiCash fizetési formátum Lengyelország esetében</li>
<li>MultiCash külföldi fizetési formátum Lengyelország esetében</li>
<li>Vevői szállítói egyenlegmegerősítési jelentés Lengyelország esetében</li>
</ul></td>
</tr>
<tr class="even">
<td>Szaúd-Arábiai honosítás – ER-konfigurációk</td>
<td>Bank LC vegyes költségfelosztási formátum Szaúd-Arábia esetében</td>
</tr>
<tr class="odd">
<td>Spanyolországi honosítás – ER-konfigurációk</td>
<td><ul>
<li>EU-s értékesítési lista TXT-formátumban Spanyolország esetében</li>
<li>Intrastat formátum Spanyolország esetében</li>
<li>Projektszámla-formátum Spanyolország számára</li>
<li>Értékesítésiszámla-formátum Spanyolország számára</li>
<li>ISO20022 átutalási fizetési formátum Spanyolország esetében</li>
<li>ISO20022 beszedési megbízási fizetési formátum Spanyolország esetében</li>
<li>Spanyol áfarögzítési könyv formátum</li>
<li>Spanyol áfarögzítési könyvek összegzése formátum</li>
<li>347-es nyilatkozat exportálása ASCII-formátumban Spanyolország esetében</li>
<li>A 347-es nyilatkozatról készült jelentés Spanyolország esetében</li>
</ul></td>
</tr>
<tr class="even">
<td>Svédországi honosítás – ER-konfigurációk</td>
<td><ul>
<li>Intrastat formátum Svédország esetében</li>
<li>Bankgirot Autogiro vevő fizetési formátum Svédország esetében</li>
<li>Bankgirot szállítói fizetési formátum Svédország számára</li>
<li>SWIFT szállítói fizetési formátum Svédország esetében</li>
<li>SIE-export formátum Svédország esetében</li>
<li>ISO20022 átutalási fizetési formátum Svédország esetében</li>
</ul></td>
</tr>
<tr class="odd">
<td>Svájci honosítás – ER-konfigurációk</td>
<td><ul>
<li>DebitDirect fizetési formátum Svájc esetében</li>
<li>LSV beszedési megbízás fizetési formátum Svájc esetében</li>
<li>ISO20022 átutalási fizetési formátum Svájc esetében</li>
<li>ISO20022 beszedési megbízás fizetési formátum Svájc esetében</li>
<li>ESR banki kivonatok importálási formátum Svájc esetében</li>
</ul></td>
</tr>
<tr class="even">
<td>Németország – szállítói kifizetések exportálása DTAZV formátumban</td>
<td>Németország a DTAZV-t külföldi formátumú specifikációval írja le, amely a németországi határokon átnyúló fizetésekre vonatkozó specifikációnak megfelelő külföldi fizetőeszközre vonatkozó utalás, vagyis egy külföldi bank vagy egy külföldi pénznemet használó belföldi bank számlájára vonatkozik. 
</td>
</tr>
</tbody>
</table>

### <a name="electronic-reporting"></a>Elektronikus jelentés

| Mit lehet tenni                                                                                                                                                                                                                                                                                     | Miért fontos ez                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ER-jelentések beállítása az adatok beszúrásához többféle formátumban a létrehozott elektronikus üzenetekbe a Dokumentumkezelés tárból.                                                                                                                                                              | Az ER-jelentések adatokat tudnak beszúrni a Dokumentumkezelés tárból létrehozott elektronikus üzenetekbe. Emiatt az üzleti dokumentumok mellékletei hozzáadhatók a dokumentumból létrehozott elektronikus üzenetkehez, a jogi követelményeknek megfelelően. Jelenleg ezeket a mellékleteket MIME-formátumban lehet hozzáadni a létrehozott XML-üzenethez. Másik lehetőségként a mellékletek Base64 formátumban adhatók hozzá a létrehozott bináris üzenethez.                                                                      |
| ER-jelentések beállítsa elektronikus dokumentumok előállításához Excel, Microsoft Word vagy PDF-formátumban.                                                                                                                                                                                                      | Egy konfiguráció teszi lehetővé az ER-jelentések számára elektronikus dokumentumok készítését három különböző formátumban: OpenXML munkalap (Excel), a Word és XML-űrlapok adatformátum (XFDF) (PDF). A felhasználók úgy választhatnak ki egy formátumot, hogy formátumsablont adnak egy ER-jelentéshez Excel, Word vagy PDF-dokumentum formájában.                                                                                                                                                                                                                                                                       |
| ER-jelentések konfigurálása adatok beszúrásához az OpenXML munkalapformátumban generált elektronikus dokumentumokon a lap fejlécébe és láblécébe, valamint az oldaltörések vezérlésére.                                                                                                                               | Az ER-jelentések képesek üzleti adatokat bevinni a lapok fejlécébe és láblécébe, valamint képesek az oldaltörések helyének szabályozására. Emiatt a jelentések támogatják a statikus felső és alsó szakaszokat a létrehozott elektronikus dokumentumok oldalain. Emellett támogatják a dokumentumok speciális oldalszámozását, hogy a dokumentumok megfeleljenek a jogi követelményeknek.                                                                                                                                                                                                             |
| Az ER-jelentések céljának beállítása úgy, hogy a kimenetet a rendszer e-mailként küldje el, illetve úgy, hogy az üzleti adatok és az ER-logika (kifejezések) segítségével futásidőben lehessen meghatározni a használandó e-mail-címet.                                                                                                    | Korábban az ER-cél konfigurálásakor a kimenet címzettjének e-mail-címét a tervezés során lehetett megadni. Most már kifejezés is konfigurálható az ER-formátumban. A kifejezés kiválasztható egy cél esetében az e-mail-cím forrásaként minden formátumkonfiguráció, illetve különállóan minden kimenetösszetevő (mappa vagy fájl) számára. Ennek megfelelően, amikor fut egy ER-jelentés, minden egyes fájl úgy jön létre, hogy eltérő címzetteknek legyen elküldhető, és az e-mail-címet az ER-logika és az üzleti adatok alapján lehet meghatározni. |
| Az ER-jelentések céljának konfigurálása úgy, hogy a kimenet küldése a Microsoft SharePoint-mappába történjen vagy új fájlként, vagy egy meglévő fájl új verziójaként, illetve úgy, hogy az üzleti adatok a Microsoft Power BI-keretrendszerben lehessenek használhatók adathalmazként vagy jelentésként.                 | Az ER-jelentések konfigurálása során most már könnyen (kódolás nélkül) készítheti elő a kért üzleti adatokat, hogy használni tudja őket a Power BI-keretrendszer. Az ER-jelentések futtatásakor a Power BI-keretrendszer ellátható a megfelelő, már rendelkezésre álló üzleti adatokkal és/vagy Excel-jelentésekkel. Ha a jelentés futását ismétlődő módú ütemezésre állítja, létrehozhatja az üzleti adatok ütemezett leküldését a Dynamics 365 for Operations rendszeréből a Power BI-keretrendszerbe, a Power BI-alapú jelentések frissítési ütemezésének támogatásához.                             |
| Az ER-jelentések beállítása úgy, hogy az elektronikus dokumentum már létrehozott részét használják adatforrásként a dokumentum többi részének létrehozásához.                                                                                                                                             | Beállíthatja a kimenetet szöveg formában létrehozó ER-jelentéseket arra, hogy számolják a dokumentum sorait. Ezt az információ a dokumentum más részeiben összegző részleteket tartalmazó sorok létrehozására lehet használni. Az összegző információk (összegek és számok) az adatok további átalakítása nélkül számíthatók ki és nyomtathatók a létrehozott elektronikus dokumentumokra. Emiatt ez a funkció továbbfejleszti a jelentésvégrehajtás teljesítményét, és segít egyszerűbbé tenni a konfigurált ER-formátum jövőbeli karbantartását.    |
| ER-jelentések konfigurálása úgy, hogy megadják a szöveges formátumban létrehozott elektronikus dokumentumok fájlkiterjesztését.                                                                                                                                                                                 | Beállítható, hogy az ER-jelentések szöveges formátumban hozzák létre a kimenetet, hogy aztán adott kiterjesztésű fájlként legyen menthető. Az alapértelmezett .txt kiterjesztésen kívül a formátummeghatározással összhangban beállíthatja az olyan bővítményeket, mint a .csv és a .prn.                                                                                                                                                                                                                                                                             |
| Az ER-modell adott verzióján alapuló új ER-jelentések létrehozása.                                                                                                                                                                                                                          | Korábban egy új ER-formátum létrehozásakor csak a kiválasztott ER-modell legújabb verziója volt használható a formátum adatforrás-helyeként. A kijelölt ER-modellnek most már bármelyik rendelkezésre álló verziója kiválasztható. Ez a funkció lehetővé teszi az ER-jelentések karbantartását az aktuális évre, és ezzel párhuzamosan az ER-modell új verziójának megtervezését a következő évre.                                                                                                                                                                                          |
| Adatforrások és formátumok/modellek keresése szöveg vagy kiválasztott műtermék alapján egy kattintással. Új alapra helyezési problémák megelőző jellegű megoldása, illetve konfigurációk közötti ütközések feloldása. ER-jelentések konfigurálása úgy, hogy több ellenőrzési üzenet jöjjön létre a jelentésvégrehajtás leállításáig észlelt hibákról. | Az ER-keretrendszeren végrehajtott számos, felhasználói élményt érintő fejlesztés segíti a felhasználókat a hatékonyabb és egyszerűbb ER-használatban.                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Az **ER** munkaterület megjelenítése a Power BI-jelentéseken.                                                                                                                                                                                                                                                      | A felhasználók beállíthatják az **ER-munkaterület** oldalt, hogy új menüelemek és élő csempék jelenjenek meg, amelyek a Power BI-alapú jelentéseket futtatják.                                                                                                                                                                                                                                                                                                                                                                                                                       |

## <a name="payroll"></a>Bérlista
<table>




<thead>
<tr class="header">
<th>Mit lehet tenni</th>
<th>Miért fontos ez</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Fizetési rekordok konfigurálása és a bérszámfejtés feldolgozása olyan funkcionalitással, amely egyenrangú a Microsoft Dynamics AX 2012 R3 <strong>Bérlista</strong> moduljáéval.</td>
<td>Most már beállítható és feldolgozható az USA-beli bérszámfejtés az AX 2012 R3 funkciókészletével megegyező szolgáltatásokkal.
<ul>
<li>Konfigurálhatók fizetési ciklusok és fizetési időszakok, munkaciklusok és munkaidőszakok, kereseti kódok és kereseti kódok csoportjai, ütemezések, távolléti típusok juttatásfelhalmozási tervek.</li>
<li>Beállítható az adók és juttatások kötelező levonása, illetve a pozíciók és dolgozók bérlistaadatainak rögzítése jelentési és elemzési célokra.</li>
<li>Emellett beállíthatók és kezelhetők a letiltásokkal és adókkal, valamint a kapcsolódó adminisztratív díjakkal kapcsolatos levonások.</li>
</ul></td>
</tr>
<tr class="even">
<td>Fizetési időszak folyamat figyelése és feldolgozásához az új <strong>Bérszámfejtés</strong> munkaterületet használatával.</td>
<td>Mostantól egyszerűen figyelhető a bérlista feldolgozása. A bérszámfejtők azonnal láthatják a figyelmet igénylő kereseti és kifizetési kimutatásokat, és így a fizetésfuttatás teljes és gyors lesz. A <strong>Bérszámfejtés</strong> munkaterület segítségével a felhasználók figyelhetik a folyamatokat, illetve teljes körű folyamatokat futtathatnak egyetlen munkaterületről.</td>
</tr>
<tr class="odd">
<td>Fizetési ellenőrző fájl előállítása bérszámfejtési célra</td>
<td>Új bővítmény áll rendelkezésre a készpénz- és bankkezelés ellenőrzött fizetés funkciójához a bérszámfejtéshez. A fő folyamathoz külön menüelemeket adtunk a bérszámfejtésre specifikus, elkülönített konfiguráció lehetővé tételére. A funkcionalitás azonos a mag ellenőrzött fizetési funkcióval, amely a 7.0.1-es (2016. május) Microsoft Dynamics AX alkalmazásverzióban jelent meg. A bővítmény miatt a bérlistaadatok teljesen elkülönülnek a többit a fizetési ellenőrző tranzakciótól. Az elkülönítés segítségével garantálható, hogy csak a bérlista-felhasználók érhetik el és láthatják a bérlistához kapcsolódó adatokat.</td>
</tr>
<tr class="even">
<td>Keresetkimutatás sorainak importálása külső forrásból az új keresetkimutatási sorok adatentitás használatával.</td>
<td>Egy új fontos adatentitás lehetővé teszi az integrációt a külső idő- és keresetszámítási rendszerekkel. Az adatentitás importálja a keresetkimutatás sorait, és végrehajtja ugyanazokat az alapértelmezett logikákat, amelyet a felhasználó közvetlenül a kereseti kimutatáson vitt be. Az importálás után a sorokat a rendszer automatikusan a megfelelő kereseti kimutatás dokumentumhoz társítja. Ha nem létezik megfelelő kereseti kimutatás dokumentum, a dokumentum automatikusan létrejön.</td>
</tr>
</tbody>
</table>

## <a name="planning-and-scheduling"></a>Tervezés és ütemezés
| Mit lehet tenni                                                                                                                                                                                                      | Miért fontos ez                                                                                                                                                                                                                                                                                                                                                                                                                 |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Alapértelmezett rendelésbeállítások az értékesítésekhez és beszerzésekhez, az alaptermék bármilyen aktív termékdimenziója alapján. Emiatt alapértelmezett rendelési beállításokat lehet megadni a raktározási egységhez (SKU) vagy egy részleges raktározási egységhez. | Alapértelmezett rendelésbeállítási szabályokat lehet meghatározni, amelyek termékdimenziókra vagy cikkdimenziók kombinációjára vonatkoznak. **Példa** Egy Polo póló nevű terméket értékesít. A termék két színben érhető el: kék és zöld. Emellett két méretben kapható: kicsi és közepes. A Szín és a Méret a Polo póló esetében aktív termékdimenzió. Zárolható minden zöld Polo póló beszerzése, függetlenül attól, mi a méretük. |

## <a name="product-master-data"></a>Alaptermékadatok
<table>




<thead>
<tr class="header">
<th>Mit lehet tenni</th>
<th>Miért fontos ez</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Az összes alapértelmezett rendelési beállítás és helyspecifikus rendelésbeállítás egyetlen oldalról adható meg.</td>
<td>Ez a funkció jobb áttekintést tartalmaz a cikkbeállításokról.</td>
</tr>
<tr class="even">
<td>Elnevezési rendszer létrehozása a termékváltozatszámokhoz.</td>
<td>A termékváltozat-számokba olyan elemeket lehet felvenni, mint a termékdimenziók, attribútumok és karakterek. Egy értékesítési rendelés vagy beszerzési rendelés létrehozásakor gyorsan megtalálhatja az adott termékváltozatokat.</td>
</tr>
<tr class="odd">
<td>Termékek és termékváltozatok keresése értékesítési és a beszerzési esetekben.</td>
<td>Értékesítési sor vagy beszerzési sor létrehozásakor termékdimenziók és bármilyen termékszám segítségével kereshet termékeket, kivéve a globális kereskedelmi cikkszámokat (GTIN) és a vonalkódokat. Ez egy teljes szöveges keresés, amely lecseréli a meglévő „Kezdete” keresést, amely az értékesítési és beszerzési keresőlistában használt. A szolgáltatás lehetővé teszi hasonló tulajdonságokkal rendelkező termékek csoportjának keresését, vagy egy egyedi jellemzőkkel rendelkező termék keresését. A funkció engedélyezéséhez jelölje be a <strong>Kikeresés engedélyezése termékek kereséséhez</strong> paramétert a <strong>Paraméterek keresése</strong> oldalon.</td>
</tr>
<tr class="even">
<td>Adja meg közvetlenül a termékváltozatot az értékesítési vagy beszerzési tranzakciók létrehozásakor. Másik lehetőségként az érvényes dimenziókombinációk listájáról is választhat.</td>
<td>Ez a funkció a termelékenységet növeli. <strong>Példa</strong> Egy Polo póló nevű terméket értékesít. A termék két színben érhető el: kék és zöld. Emellett két méretben kapható: kicsi és közepes. A Szín és a Méret a Polo póló esetében aktív termékdimenzió. Amikor bevisz egy értékesítési sort Polo pólóhoz, amelynek a színe zöld és kis méretű, nem kell adatokat megadnia a <strong>Cikkszám</strong>, <strong>Szín</strong> és <strong>Méret</strong> mezőkben. A sort az alábbi lépések valamelyikével hozhatja létre:
<ul>
<li>A <strong>Cikkszám</strong> mezőbe írja be a termékváltozat számát, illetve a szín vagy a méret értékét. A kikeresésben keresse meg az értékesíteni kívánt konkrét változatot, és hozza létre az értékesítési sort.</li>
<li>A <strong>Cikkszám</strong> mezőbe írja be a cikkszámot. Ugorjon a termékdimenzió mezőre. A <strong>Termékdimenzió</strong> kikeresési képernyőn megjelennek a Polo pólóra vonatkozó kiadott dimenziókombinációk. Egy lépésben válaszhatja ki az értékesíteni kívánt termékváltozatot.</li>
</ul></td>
</tr>
<tr class="odd">
<td>A termékszámok tranzakciós lapokon való megjelenítésének beállítása.</td>
<td>A tranzakciós lapokon, például az értékesítési és beszerzési rendeléseken, csak a <strong>Cikkszám</strong> és <strong>Terméknév</strong> mezők láthatók. A <strong>Termékszám</strong> mező megtekintéséhez válassza ki a <strong>Termékszámok megjelenítése a képernyőkön</strong> paramétert a <strong>Termékinformáció-kezelési paraméterek</strong> alatt.</td>
</tr>
</tbody>
</table>

## <a name="project-management-and-accounting"></a>Projektvezetés és könyvelés
| Mit lehet tenni                                                                                                           | Miért fontos ez                                                                                                                                                                                                                                                                                                             |
|---------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Kései kiválasztás használata számlajavaslatok kötegelt feladásakor.                                                            | A projektkönyvelők beállíthatnak egy kötegelt feladatot, amely automatikusan begyűjti a számlajavaslatokat feladásra, ha a javaslatok teljesítik a kötegelt feladatokhoz megadott feltételeket. Ez a funkció továbbfejleszti az automatikus számlafeladást, mert a kötegelt feldolgozást folyamatosan lehet futtatni, és automatikusan felveszi a javaslatokat a feladáshoz. |
| Analitika létrehozása a Power BI asztalon.                                                                                     | A Power BI asztalon könnyen hozható létre üzletiintelligencia-tartalom a projekthez kötődő és erőforrásokra vonatkozó adatokhoz.                                                                                                                                                                                                       |
| Beszerzési rendelés előlegek használata, és a megfelelő beágyazásuk a projektbecslési folyamatba.                               | A projektek beszerzési rendeléseinek esetében az előlegeket fel kell dolgozni, mielőtt bizonyos kifizetések feloldhatók lennének a szállítók számára. Ezek az előlegszámlák most már megjelennek a projektbecslés/elismerés folyamatában a **Rögzített ár** típusú projekteknél.                                                                                           |
| Hozzáférés a költség- és bevételbecslésekhez, valamint a cikk-követelményekhez, illetve a kezelésük lehetősége, közvetlenül a munkalebontási struktúra (WBS) munkafeladatból. | Egy adott WBS-feladat költségbecsléseit, bevételbecsléseit és cikkszükségleteit a feladat részletei párbeszédpanelen kezelheti a WBS tervezési nézetben.                                                                                                                                                                 |
| Finanszírozási forrás választása a díjnaplók esetében.                                                                                    | Ha egy projekt szerződése több finanszírozási forrást tartalmaz, kiválaszthat egy adott finanszírozási forrást a díjak feladásakor. Ha nem jelöl meg egy adott finanszírozási forrást, a díjak felosztása a szerződésben megadott finanszírozási szabályok használatával történik.                                                                   |
| Projektkimutatások Excelben történő megnyitása.                                                                                         | A főkönyvi és költségvetési frissítések új adatentitásai lehetővé teszik a projektkimutatási adatok Excel programban történő megnyitását és analitika létrehozását az Excel-funkciók segítségével.                                                                                                                                                                           |
| Csak egy konfigurációs kulcs használata a projektvezetési és könyvelési (PMA) funkció engedélyezéséhez.                       | A projekthez kapcsolódó konfigurációs kulcsokat egy projektkonfigurációs kulcs váltotta ki, amely bekapcsolja a PMA-funkciót.                                                                                                                                                                                                       |

## <a name="retail-and-commerce"></a>Kiskereskedelem és kereskedelem
### <a name="advanced-warehouse-management-in-a-retail-store"></a>Speciális raktárkezelés egy kiskereskedelmi üzletben

A kiskereskedők használatba vehetik a speciális raktárkezelési (WHS) megoldást az üzleteikben, és végrehajthatják a szükséges frissítéseket a jelenlegi pénztár (POS) funkciókon a megoldás támogatása érdekében. A kézi megoldás folyamatai elvileg ugyanúgy működnek az üzletekben, mint bármelyik másik raktárban. Az összes aktuális kiskereskedelmi árukészlettel kapcsolatos folyamat, illetve az összes készlettranzakciókat létrehozó vagy frissítő POS-folyamat frissült úgy, hogy a meghatározott követelményeket használják a WHS-t alkalmazó raktárak esetében.

| Mit lehet tenni                                                                       | Miért fontos ez                                                                                                                                                                                                                          |
|---------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| POS használat a rendelkezésre álló készlet megkereséséhez a WHS-t alkalmazó raktárakban.                     | Készlet keresésekor a folyamat működése ugyanaz lesz, mint korábban. A keresésnek a rendelkezésre álló mennyiségeket kell megjelenítenie a raktár szintjén, és nem szabad figyelembe vennie a hely, készletállapot és azonosítótábla dimenziókat. |
| POS használata az átmozgatási rendelésekhez tartozó termékbevételezések feldolgozásához a WHS-t alkalmazó raktárak esetében. | A WHS-t alkalmazó raktárak és cikkek esetében POS átmozgatási rendelések bevételezése történhet. A felhasználónak ki kell tudni választani a bevételezés helyét, be kell tudnia vinni az azonosítótábla-azonosítókat a bevételezési sorok automatikus feltöltéséhez.    |
| POS használata a beszerzési rendelésekhez tartozó termékbevételezések feldolgozásához a WHS-t alkalmazó raktárak esetében. | A WHS-t alkalmazó raktárak és cikkek esetében POS beszerzési rendelések érkezhetnek. A felhasználónak ki kell tudni választani a bevételezés helyét, be kell tudnia vinni az azonosítótábla-azonosítókat a bevételezési sorok automatikus feltöltéséhez.    |
| POS használata egy WHS-t alkalmazó raktárból érkező termékszállítmány feldolgozásához.               | A WHS-t alkalmazó raktárak és cikkek esetében átmozgatásokat regisztrálhat a POS-ból. A felhasználónak ki kell tudnia választani a szállítás kezdő helyeit, a készletállapotnak automatikusan létre kell jönnie, az azonosítótáblákat figyelmen kívül kell hagyni.         |

### <a name="enable-seamless-omni-channel-commerce"></a>Zökkenőmentes többcsatornás kereskedelem lehetővé tétele

A zökkenőmentes többcsatornás kereskedelem a hagyományos fizikai üzleteket, online üzleteket, hívásközpontokat és mobilkereskedelmi megoldásokat lefedő kezelésre és a rendelésfeldolgozásra vonatkozik. Ebben a verzióban a következő beruházások történtek ezen a területen:

-   E‑commerce kirakatok közzétételének javításai
-   Új, a fogyasztó által használt mobilalkalmazás, amely lehetővé teszi a termék felkutatását, a fiókkezelést és az online vásárlást

| Mit lehet tenni                                                                                                                                                                                                                                                                   | Miért fontos ez                                                                                                                                                            |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Fogyasztó: Az ügyfél által használt alkalmazás jelenlegi verziója a következő funkciókat nyújtja – termékkeresés, kategória tallózása, hozzáadás a bevásárlókocsihoz és fizetés vendégként. A kiskereskedők személyre szabhatják az alkalmazást a vállalat márkaarculati elemeivel, és benyújthatják közzétételre az Android és iOS alkalmazásáruházakba. | Kiskereskedők is könnyedén létrehozhatnak egy ügyfél által használt alkalmazását, amellyel az ügyfelek böngészhetnek, termékeket kereshetnek és termékek szállíttathatnak ki a mobileszközük használatával.                      |
| Vevői kívánságlista az e-kereskedelmi online kirakatok esetében                                                                                                                                                                                                                             | A kívánságlista vezérlő segítségével a független szoftverfejlesztők (ISV) lehetővé tehetik a felhasználók számára több lista létrehozását és kezelését az online üzletükben, továbbá a listák megtekintését/használatát a POS-ben. |
| Aszinkron vevőlétrehozás az elektronikus kereskedelmi online kirakatokon keresztül                                                                                                                                                                                                                  | Az ISV most már akkor is létrehozhatnak vevői számlákat, amikor a Commerce Data Exchange: Real-time Service nem érhető el.                                                                        |
| Csatornatermékek közzététele kiskereskedelmi kiszolgálóról harmadik fél kirakatokba.                                                                                                                                                                                                           | A kiskereskedelmi kiszolgáló most már támogatja a szolgáltatások közti hitelesítést. Az ISV kihasználhatják a csatornatermékek közzétételének előnyeit kiskereskedelmi kiszolgálóról harmadik fél kirakatokba.               |

### <a name="extensibility"></a>Bővíthetőség

-   A kereskedelmi futásidejű projektek most már el vannak szigetelve a Retail SDK-tól.
-   Könnyebb telepítés és karbantartás az összetevőkre bontott Microsoft összetevőcsomagokkal és ISV csomagokkal a POS, kiskereskedelmi kiszolgáló, adatbázisok, fizetés és hardver állomásokhoz.

| Mit lehet tenni                                                                                                                 | Miért fontos ez                                                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CRT/kiskereskedelmi kiszolgáló: a kiskereskedők vagy az ISV-k bővíthetik a CRT-t a kiterjesztés horgok használatával. A beágyazott kód módosításai már nem támogatottak. | A folyamatos integráció és folyamatos üzembe helyezés lehetővé tételéhez a beágyazott kód módosításait teljesen kerülni kell. Ez a gyorsjavítások egyszerű alkalmazásának támogatásához is szükséges, mivel így nincs szükség a kódegyesítésre és üzembe helyezésre a CRT-összetevők esetében. |

### <a name="personalized-product-recommendations"></a>Személyre szabott termékajánlások

| Mit lehet tenni                                                                                                                                                                                                                                                                        | Miért fontos ez                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Személyre szabott termékajánlások megtekintése több érintkezési pontnál a pénztáraknál annak meghatározásához, hogy mi iránt érdeklődhet egy ügyfél a vásárlási előzményei, a kívánságlistáján lévő cikkek, valamint azon cikkek alapján, amelyeket más ügyfelek vásároltak az interneten vagy a fizikai üzletekben | A nagy katalógusokkal rendelkező kiskereskedők esetén a személyre szabott ajánlások segítenek az ügyfélnek a termék felfedezésében, és lehetővé teszik az üzlettársításoknál az intelligens ügyféltárolást. A vevő érdeklődésének és vásárlási szokásainak megfelelően célzott termékek bemutatásával a termékajánlások segíthetik a kiskereskedőket az értéknövelő, értékesítésben, és növelhetik a vevők megtartását. A Microsoft Dynamics 365 for Retail rendszerben a termékajánlásokat a kognitív szolgáltatás és a Microsoft Azure gépi tanulás szolgálja ki. |

### <a name="pos-task-recorder"></a>Pénztári feladatrögzítő

| Mit lehet tenni                                                                                                                                                                                                  | Miért fontos ez                                                                                                                                                                                    |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| A kiskereskedők a POS feladatrögzítő használatával oktatóanyagokat és üzletifolyamat-modellező diagramokat készíthetnek, illetve súgótartalmat állíthatnak elő a hatékonyság fokozása, valamint az alkalmazások jobb elemzése és tervezése érdekében. | A folyamatos integráció és folyamatos üzembe helyezés lehetővé tételéhez a beágyazott módosításokat teljesen kerülni kell. Ez a gyorsjavítások egyszerű alkalmazásának támogatásához is szükséges, mivel így nincs szükség a kódegyesítésre és üzembe helyezésre a CRT-összetevők esetében. |
| Vvalós idejű segítség a POS-ban                                                                                                                                                                                           | A pénztáros/kezelő valós idejű segítséget kérhet POS-tól az üzleti folyamattal kapcsolatban, környezetváltás nélkül.                                                                                                           |

### <a name="store-system-providing-a-seamless-on-premises-store-experience"></a>Üzleti rendszer: zökkenőmentes helyszíni üzleti élmény biztosítása

Az üzleti rendszer üzembe helyezési választási lehetőség a kiskereskedők számára, amely üzletműveletek bizonyos készletét teszi zökkenőmentesebbé, függetlenül attól, hogy egy helyi üzletről, egy Microsoft nyilvános felhőről vagy a vevő saját felhőjéről van szó. Ennél a verziónál a hatókör csak in-store üzleten belüli. A lassú és megbízhatatlan hálózati kapcsolattal rendelkező környezetek jobb támogatása érdekében lehetővé kell tennünk a kiskereskedők számára a csatorna-adatbázis és a kiskereskedelmi kiszolgáló üzembe helyezését az üzletben. Ebben az esetben még akkor is tovább futtathatják a fő üzleti forgatókönyveket, ha nincs kapcsolat a központtal (HQ). A különböző adatpontok alapján, amelyek magukban foglalták a mérnöki csoportos megbeszéléséket, a vevői felmérések eredményeit és a versenytársak elemzését, a következő megoldáshatókört azonosítottuk a célügyfeleink számára ideálisként:

-   Önkiszolgáló csomag áll rendelkezésre az üzleti rendszerhez.
-   Az alapértelmezett telepítését egy egydobozos telepítés, de az egyénre szabott telepítés is megengedett.
-   Egyszerű telepítés/saját karbantartási engedélyezése.
-   A kiskereskedelmi kiszolgáló és az üzlet adatbázisa az üzletben van, az Async Client szolgáltatással együtt.
-   Az üzlet kiskereskedelmi kiszolgálója közvetlenül kommunikál az Application Object Server (AOS) kiszolgálóval az üzleti rendszer központjában.
-   Támogatja a párhuzamos terminál eseteket, ahol nincs központi kapcsolat.
-   A Retail Modern POS és a Cloud POS mindig az üzletben levő kiskereskedelmi kiszolgálóval kommunikál.
-   Retail Modern POS és Cloud POS támogatása, ha nincs kapcsolat a központtal.
-   Retail Modern POS-specifikus offline adatbázis (minden egyes Retail Modern POS-példányra elszigetelt) támogatása, ha nincs kapcsolat a központtal.
-   A hitelesítés alapja a szolgáltatások közvetlen kommunikációja csak az üzleti rendszer esetében.
-   A valós idejű szolgáltatáshívások nem támogatottak, ha a nincs internetkapcsolat.
-   A Retail Modern POS és a csatornaadatbázis közvetlen adatbáziskapcsolata nem támogatott.
-   Telemetria/megfigyelés engedélyezése.

| Mit lehet tenni                                                                                                                                       | Miért fontos ez                                                                                   |
|-------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| A kiskereskedő letölti az üzleti rendszer önkiszolgáló telepítőjét a Dynamics AX központ csatornaadatbázis lapjáról, és letölti a konfigurációs fájlt.   | Kiskereskedő zökkenőmentesen töltheti le az önkiszolgáló csomagot.                                          |
| A kiskereskedő az önkiszolgáló telepítő használatával telepíti az üzleti rendszert.                                                                                 | A kiskereskedő az önkiszolgáló csomag használatával telepítheti az üzleti rendszert.                                |
| Az üzleti rendszert az informatikai konfigurálja a Dynamics 365 for Operations használatával (csatorna-adatbázis, csatornaprofil, üzlet, telepítendő csomag).             | Az informatikai vezet egyszerűen és hatékonyan konfigurálhatja az üzleti rendszert.                                       |
| A kiskereskedő a Retail Modern POS-t a helyi üzletben üzemelteti, és ha van kapcsolat, valós idejű műveleteket végezhet, például ajándékutalványok kiadása. | A kiskereskedő valós idejű műveleteket végezhet az üzleti rendszerből, ha van kapcsolat.                |
| A kiskereskedő szinkronizálhatja az adatokat a helyi üzleti rendszerből a központtal, amikor van kapcsolat.                                                      | A kiskereskedő szinkronizálhat az üzleti rendszerből, illetve az üzleti rendszerbe, ha van kapcsolat.                              |
| A kiskereskedő biztonságos kommunikációt folytathat a helyi üzleti rendszer és a központ között.                                                                 | A kiskereskedő biztonságosan kommunikálhat az üzleti rendszerből, ha van kapcsolat.                     |
| Az informatikai vezető és a Microsoft Operations figyelemmel követheti a helyszíni üzleti rendszert és jelentéseket készíthet (diagnosztika és jelentési módosítások).                   | Az informatikai vezető és a Microsoft Operations biztonságosan figyelheti az üzleti rendszert, és hatékony hibaelhárítást végezhet. |

### <a name="universal-windows-platform-app-for-retail-modern-pos"></a>Univerzális Windows Platform alkalmazás a Retail Modern POS-hez

A Retail Modern POS jelenleg csak Windows 8.1 alkalmazásként elérhető el asztali számítógépekhez és táblagépekhez, és Cloud POS formájában az asztali vagy táblagépes böngészőkhöz. Ebben a verzióban a Retail Modern POS-t univerzális Windows Platform (UWP) alkalmazássá konvertáljuk. Ez a módosítás lehetővé teszi a Retail Modern POS futtatását bármely Windows 10 eszközön (asztali, tábla vagy telefon), sőt, a nézetek közti váltást is a Continuum-kompatibilis eszközök esetében.

| Mit lehet tenni                                                   | Miért fontos ez                                                                                     |
|-------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|
| Fontos POS-funkciók engedélyezése a kis helyigény eszközök esetében. | A Retail POS funkcionalitás elérhető a telefonok és más kis helyigény, Windows 10 rendszert futtató eszközök esetében. |

## <a name="supply-chain-management"></a>Ellátásilánc-kezelés
### <a name="consignment-inventory"></a>Bizományosi készlet

| Mit lehet tenni                                                                                                                                                                | Miért fontos ez                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Szállítóként nyersanyagokat tárolhat a vevő raktárában. Vevőként elhalaszthatja a tényleges beszerzést, amíg a nyersanyagok szükségessé nem válnak a termeléshez. | A nyersanyagok készleten tartása súlyos költséggel járhat. A szállítmánykészlet használatával a szállító nyersanyagokat tárolhat a vevő raktárában. A vevő így elhalaszthatja a tényleges beszerzést, amíg a nyersanyagok szükségessé nem válnak a termeléshez. A nyersanyagok megrendelése és fogadása szállítmányfeltöltési rendeléssel történik. A feltöltési rendelés rögzíti a tényleges tranzakciókat, de nem befolyásolja a főkönyvet. Vevő által birtokolt készletcikkek és a szállító által birtokolt készletcikkek megkülönböztetésére a tulajdonos készletdimenzió használható. A készlet tulajdonosváltását egy naplófolyamat kezeli, amely kezeli a nyersanyagok tulajdonjogának átvitelét a szállító által birtokolt készletből a vevő által birtokolt készletbe. A folyamat kiváltja egy beszerzési rendelés és a termékbevételezés létrehozását. **Megjegyzés:** Ez a funkció a termelési nyersanyagok bejövő bizományosi szállítmányaira korlátozódik. Nincs integrálva raktárkezelés (WHS) és a szállításkezelés (TMS) funkciókkal. |
| Szállítóként információ lekérése a bizományosi készletről, amelynek az átvitele megtörténik a vevőhöz.                                                                      | A számla kiállításához a vevő számára a szállítónak szüksége van bizományosi készletből megvásárolt nyersanyagok adataira, valamint a vásárlás dátumára. A szállító is figyelemmel követheti a vevő telephelyén rendelkezésre álló készletet a szállítói együttműködés felhasználói felületén.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| A szállító tulajdonában lévő készlet átvitele átmozgatási napló segítségével.                                                                                                                       | A szállító által birtokolt készlet fizikai helyének nyomon követésére a helynek rögzíthetőnek kell lennie a rendszerben. Az átmozgatási naplót segítségével rögzítheti a készlet tényleges mozgatását, többek között az átmozgatást az egyik helyről a raktárban egy másik helyre a raktárban.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| A szállító tulajdonában lévő készlet igazítása számlálási napló segítségével.                                                                                                                     | Fontos, hogy a rendszerbeli aktuális készlet mindig szinkronban legyen a tényleges készlettel. A szállító által birtokolt készlet folyamatosan igazítható a számlálási eljárásokkal, például a mennyiség módosítása és a számlálási napló folyamatokkal.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| További tudnivalók a Dynamics 365 for Operations bizományosi támogatásáról                                                                                                         | A bizományosi folyamatok támogatásával kapcsolatos további tudnivalókat lásd: [Szállítmány](../../supply-chain/inventory/consignment.md), [Szállítmány beállítása](../../supply-chain/inventory/set-up-consignment.md), [Bizományosi feltöltési rendelés létrehozása (Feladat-útmutató)](../../supply-chain/inventory/tasks/create-consignment-replenishment-order.md) és [Bizományosi készlet tulajdonosának módosítása gyártási igény alapján (Feladat-útmutató)](../../supply-chain/inventory/tasks/change-ownership-consignment.md).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |

### <a name="vendor-collaboration-previously-known-as-the-vendor-portal"></a>Szállítói együttműködési (korábbi nevén a szállítói portál)

| Mit lehet tenni                                                                      | Miért fontos ez                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|--------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Engedély a szállítók számára a válaszolásra a beszerzési rendelés egyes soraira és módosítások javasolására.           | Bizonyos esetekben szállítók szeretnének elfogadni egyes beszerzésirendelés-sorokat, másokat viszont elutasítani. A szállítók most már egyenként kezelhetik a beszerzésirendelés-sorokat. Minden sor elutasítható, elfogadhat, vagy elfogadható módosításokkal. A szállítók például módosíthatják a szállítási dátumot, feloszthatják a szállítást és a mennyiséget, vagy alternatív cikket javasolhatnak.                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Kapcsolattartó adatainak kezelésének engedélyezése a szállítók számára.                                 | A szállítók tarthatják karban a vállalathoz tartozó kapcsolattartó személy adatait. Az adatok között szerepelnek a nevek, az e-mail címek és a telefonszámok. A funkcióhoz való hozzáférést megvalósítása dedikált biztonsági szerepkörön keresztül történik.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| A beszerzési rendelésekkel kapcsolatos dokumentumok megosztása a szállítókkal.                    | Amikor meg kell osztania egy dokumentum egy szállítóval, például egy követelményekkel kapcsolatos dokumentumot, kényelmes megoldás a dokumentumot behivatkozni a megfelelő beszerzési rendeléshez. A szállító így jegyzeteket és mellékleteket oszthat meg az ügyféllel úgy, hogy a dokumentumot behivatkozza a beszerzési rendelésre adott válaszához. A dokumentumkezelés az alapul szolgáló kiegészítő keretrendszer, és csak a „külsőként” besorolt jegyzetek és mellékletek oszthatók meg a szállítókkal.                                                                                                                                                                                                                                                                                                                              |
| Új szállítói felhasználók létrehozása.                                                          | Ha a szállító a szállítói együttműködési felület használja, egyszerűen igényelhet új felhasználói fiókokat, amikor új kapcsolattartóknak kell hozzáférniük a szállítói együttműködéshez. A beszerzési szakemberek kérhetnek felhasználói fiókot a szállítói szervezet kapcsolattartói számára. Az a szállítói kapcsolattartó személy, aki már együttműködési felhasználó, szintén küldhet ilyen típusú kérelmet. A kérelem végül létrehoz egy új felhasználót Dynamics 365 for Operations megoldásban, amelyhez szállítóspecifikus biztonsági szerepkörök tartoznak. Emellett kérelmet indít el a Microsoft Azure B2B portálon, hogy a felhasználó megkapja az új Azure Active Directory (Azure AD) felhasználói fiókot. A szállítók emellett kérhetik adott szállítói felhasználói fiókok inaktívvá tételét, vagy a biztonsági szerepkörök módosítását. |
| További tudnivalók a Dynamics 365 for Operations szállítói együttműködési támogatásáról. | A szállítói együttműködéssel kapcsolatos további tudnivalókat lásd: [A külső szállítókkal történő szállítói együttműködés](../../supply-chain/procurement/vendor-collaboration-work-external-vendors.md), [Szállítói együttműködés a vevőkkel](../../supply-chain/procurement/vendor-collaboration-work-customers-dynamics-365-operations.md), [Szállítói együttműködés felhasználóinak kezelése](../../supply-chain/procurement/manage-vendor-collaboration-users.md), [Szállítói együttműködés beállítása és karbantartása](../../supply-chain/procurement/set-up-maintain-vendor-collaboration.md) és [Szállítói együttműködési számlázás munkaterület](../../financials/accounts-payable/vendor-portal-invoicing-workspace.md).                                                         |

### <a name="intercompany-order-processing"></a>Vállalatközi rendelésfeldolgozás

<table>




<thead>
<tr class="header">
<th>Mit lehet tenni</th>
<th>Miért fontos ez</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Határozza meg, közvetlenül az értékesítésirendelés-sorokban, hogy honnan kell beszerezni az igényt, és hogyan kell beszerezni. <strong>Példa</strong> Hozzon létre egy értékesítésirendelés-sort, és adja meg a közvetlen kiszállítást szállítási típusként. Az elsődleges szállító forráspontként az értékesítésirendelés-sorhoz lesz adva.</td>
<td>A rendelésfelvétel folyamatát jelentős mértékben továbbfejlesztettük. Meghatározhatja, közvetlenül az értékesítésirendelés-sorokban, hogy honnan kell beszerezni az igényt, és hogyan kell beszerezni. Most már nem kell megvárnia, hogy az összes sor hozzá legyen adva az értékesítési rendeléshez. Az értékesítésirendelés-sorok új beállításainak segítségével a szállító megadásakor adhatja meg a szállítási típust. Amikor az értékesítésirendelés-sorokhoz társít egy szállítót, rendelési láncok jönnek létre a szállítótól történő rendeléshez.
<ul>
<li>A szállító lehet vállalatközi szállító, amely belső beszerzési rendelést vagy értékesítésirendelést használ, vagy külső szállító, amely külső beszerzési rendelést használ.</li>
<li>A szállítás típusa lehet <strong>Közvetlen szállítás</strong> vagy <strong>Készlet</strong>. A <strong>Készlet</strong> szállítási típusa jelzi, hogy a szállítónak a helyi készletbe kell beszállítania, mielőtt a vevőnek szállítana.</li>
</ul></td>
</tr>
<tr class="even">
<td>Rendelési ígéret közvetlen létrehozása az értékesítésirendelés-sorokból. <strong>Példa</strong> Hozzon létre egy értékesítésirendelés-sort, amelynek a forrása egy vállalatközi szállító. Lépjen ki a sorból. A szállítási dátumokat a forrás vállalat rendelkezésre állása alapján számítják ki.</td>
<td>Az új beszerzési információkat használó értékesítési rendelési sorok létrehozásakor a szállítási dátumok számítása a <strong>Szállítási dátum</strong> vezérlőelem alapján történik. Ha például egy vállalatközi szállító van bejelölve, megtörténik a forrás vállalat rendelkezésre állásának számítása. Ezzel a módszerrel a rendelési láncokat a rendszer automatikusan hozza létre az értékesítésirendelés-sorokkal együtt. A funkció segítségével garantálható, hogy a forrás vállalatnál láthatók legyenek a szállítási dátumok, hogy az ígérethez rendelkezésre álló (ATP) profilok a várható igényeket közvetlenül az értékesítési rendelések létrehozásakor tudják kezelni.</td>
</tr>
<tr class="odd">
<td>Termék elérhetőségének ellenőrzése minden forráshelyen, és a legjobb forráslehetőség kiválasztása.</td>
<td>A <strong>Szállítási alternatívák</strong> lap megváltozott, és most értékes információkat jelenít meg minden jóváhagyott belső és külső szállítóról. Az adatok közé tartoznak a szállítói beszerzési forráslehetőségei. Szállítási mód kiválasztásakor a rendszer kiszámítja a lehetséges szállítási dátumot. Válassza ki zökkenőmentesen a vevőhöz tartozó legjobb megoldást, és ezt a beállítást alkalmazza minden értékesítésirendelés-sorhoz.</td>
</tr>
</tbody>
</table>

### <a name="warehouse-enhancements-for-high-volume-distribution-centers"></a>Nagy mennyiségű elosztóközpontok raktárbővítményei

| Mit lehet tenni                                                              | Miért fontos ez                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Munka létrehozása az áruk csomagolási állomáson való csomagolása után.               | Ez a funkció akkor hasznos, ha vannak további folyamatok a kézi csomagolási munka után (például raklapra csomagolás, minőségvizsgálat, szállítmányok konszolidálása vagy berakodási tárolókat érintő változások). Az új **Becsomagolt tároló kitárolása** munkatípus külön munkasorok használatával teszi lehetővé az ilyen feladatok modellezését. Most már modellezhetők a csomagoló helyek munka generálásához csomagolás után. Ez a munka a csomagolt készlet mozgásának szervezésére használható.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Tárolók csoportosítása a csomagoló helyen.                                     | Ez a funkció lehetővé teszi több csomag egy tárolóba vagy azonosítótábla alá csoportosítását a csomagoló helyen. Egy e-kereskedelmi/nagykereskedelmi kezelő például egyetlen tárolóba csoportosíthat 100 egyenként csomagolt csomagot (például raklapot vagy ládát). Ez a tároló ezután áthelyezhető, előkészíthető vagy betölthető egyetlen munkautasítással, amelyet a dolgozó úgy hoz létre, hogy beszkennel egyetlen vonalkódot (azonosítótáblát) a csoportosított tárolóhoz. Ez a funkció több kisebb csomagolt tároló áthelyezési munkatranzakcióinak számát minimalizálja. További információért lásd: [Menüelem létrehozása mobileszközhöz azonosítótábla-konszolidáláshoz (Feladat-útmutató)](../../supply-chain/warehousing/tasks/create-mobile-device-license-plate-consolidation.md)                                                                                                                                                                                                                                                                                                                                                                                            |
| Csomagolt tárolók kiadási házirendjének létrehozása.                               | A tárolókiadás által kiváltott munka létrehozható automatikusan vagy manuálisan. Automatikus kiváltás esetén a munka a tároló lezárásakor jön létre a helyutasítás és a munkasablon-keretrendszer használatával. Manuális kiadás esetén a csomagoló eldöntheti, hogy a munka egyetlen tárolóhoz vagy tárolók csoportjához jöjjön létre. Ez a funkció csökkenti annak a kockázatát, hogy a lezárt tárolókat kitárolják és elvigyék, mielőtt még készen állnának az elszállításra a csomagolási állomáshelyről. Emellett lehetővé teszi a nem a rendszer által irányított csoportosított kiadást.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Rövid kitárolás újbóli felosztása                                                   | Új lehetőségként támogatottá váltak a rövid kitárolási folyamatok az olyan munkatársak támogatásához, akik nem tudják kitárolni az árukat, és teljesíteni akarják a rendelést, amikor a kért cikk rendelkezésre áll egy másik helyen. Egy automatikus újbóli felosztási folyamat használatára van lehetőség, amely ugyanazokat a helyirányelveket használja az áruk lekéréséhez, ha elérhetők egy másik helyen. Másik megoldásként kézi újbóli felosztás használatakor a mobileszköz megjeleníti a helyek listáját a rendelkezésre álló mennyiséggel együtt. A raktári dolgozó ekkor kiválaszthatja, melyik helyről szeretné használni a készletet. Ez a két módszer külön-külön vagy kombinálva is beállítható egyetlen parancsként a raktári dolgozó menüben. Manuális újbóli felosztás használata esetén a raktári dolgozó a rövid kitárolású cikkmennyiséget több helyről is kitárolhatják. További információért lásd: [Cikkek újbóli felosztására vonatkozó szabályok rövid kitárolásának beállítása (Feladat-útmutató)](../../supply-chain/warehousing/tasks/set-up-short-picking-item-reallocation.md).                                                                                                                                                                                          |
| Társított munkával rendelkező készlet mozgatásának engedélyezése                             | A társított munkával rendelkező készlet most már mozgatható. Ez a funkció akkor lehet hasznos, ha a dolgozó például érkeztetési területet szeretne felszabadítani, és a regisztrált, betárolásra váró raklapokat egy másik érkeztetési területre szeretné átmozgatni. A terület felszabadul és kész további áruk fogadására, az áthelyezett készletet pedig új betárolási adatokkal frissítik. A funkció használatával a kitárolási helyeken is lehet területet felszabadítani, a társított munkával rendelkező készlet mozgatásával és feltöltési hely létrehozásával. Rakományok áthelyezésére is használható egyik előkészítő helyről a másikra, a létrehozott betöltési munka elvesztése nélkül. Ezzel a módszerrel a szolgáltatás segít optimalizálni az érkező teherautók berakodásához szükséges időt. Áthelyezhető olyan készlet, amelyik már le van foglalva az értékesítési rendelésekhez, átmozgatásirendelés-problémák, átmozgatásirendelés-bevételezéséhez és beszerzési rendelések. Az áthelyezés nem lehetséges, ha felosztaná a sorokat. Ha például egy munkasor 100 darab cikkből áll, akkor nem lehet áthelyezni a cikkből csak 30 darabot egy másik helyre. |
| Társított munkával rendelkező azonosítótáblák egyesítése.                    | A kimenő társított munkával rendelkező azonosítótáblák egyesíthetők. Ha például egy kitárolást több munkára szedtek szét, hasznos lehet engedélyezni az azonosítótáblák egyesítését, miután megérkeztek az előkészítő helyre. Az azonosítótáblák csak akkor konszolidálhatók, ha ugyanazon a helyen vannak, azonos terhelés tagjai, és azonosak a szállítmányinformációik.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Feltöltéssel társított kitárolási munka befagyasztása sor szinten. | Most már lehetőség van a munka befagyasztása sor szinten fejléc szint helyett, hogy a dolgozók teljesíthessék azokat a kitárolási sorokat, amelyeket nem fagyasztott be az igényfeltöltés. Ezen a módon egy nagykereskedő, amelynek nagy értékesítési rendelései vannak, vagy egy kiskereskedő, amelynek nagy értékesítési rendelései vagy feltöltési átmozgatási rendelései vannak, engedélyezheti a kitárolási munka megkezdését minden olyan soron, amely nem esik a feltöltési munka hatálya alá. A kitárolási és a feltöltési munka így párhuzamosan fejezhető be. Ez a funkció beállítható, vagyis kiválaszthatja, hogy a fejléc szintjén vagy a sor szintjén szeretné alkalmazni a befagyasztást. Mindkét módszer is alkalmazható, és külön munkasablon hozható létre mindegyikhez. A fejléc/sor konfiguráció beállítása a munkasablonokon történik, azonban meg lehet változtatni közvetlenül a generált munkánál.                                                                                                                                                                                                                                                                                                                                                                      |
| Munka megszakítása a mobileszköz használatával.                                      | A mobileszköz használatával most már megszakítható a munka, igényfeltöltéssel vagy nélküle. Korábban ehhez a funkciógazdag ügyfélalkalmazást kellett használni. A funkció engedélyezéséhez hozzon létre egy mobileszköz-menüelemet, amelynek a beállítsa a módnál **Közvetett**, a tevékenység kódja pedig **Munka megszakítása**.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

### <a name="warehouse-operation-enhancements"></a>Raktári műveletek bővítményei

| Mit lehet tenni                    | Miért fontos ez                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Különböző tárolótípusok modellezése.   | Különböző tárolótípusokat használhat a raktárban a tárolás optimalizálására vagy más okból. Az új tárolótípus entitás a tárolótípusok fizikai jellemzőit tartalmazza. Most már társíthatók az azonosítótáblák adott tárolótípusokkal, és használhatók a hely rakodási korlátai. A funkció segítségével például megadhatja, hány raklap (vagy más tárolótípus) van engedélyezve egy meghatározott helyen. A tárolótípusok az egységszekvencia-csoportokhoz is hozzá lettek adva, hogy alapértelmezett tárolótípusokat lehessen hozzáadni a bevételezési folyamathoz. A tárolótípusok a bejövő és kimenő helyutasításokkal használható. Az aktuális készlet nézetben is használhatók, ami segít megállapítani, hogy hány tárolótípus van a jelenleg tárolt készletben. További információért lásd a [Tárolótípussal társított azonosítótáblák használata a raktárkezelési folyamatok támogatásához](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/06/20/use-of-license-plates-associated-with-a-container-type-to-drive-warehouse-management-processes/) blogbejegyzést. Annak ellenére, hogy a blogbejegyzés a Microsoft Dynamics AX 2012 egyik frissítését ismerteti, ugyanazt a támogatást adtuk most hozzá a Dynamics 365 for Operations megoldáshoz.                                                                                                                                                                                                                                                                                                                         |
| Szállítmányok sztornírozása.                 | A raktárban kezelni kell tudni a késői változtatásokat. Például egyes áruk sérültek lehetnek, így nem szállíthatók. Azt is megtörténhet, hogy egy vevő késői kérelmeket küld, vagy megszakít vagy módosít egy megrendelést. A Dynamics 365 for Operations most már lehetővé teszi a szállítmányok sztornírozását. Emiatt érvényteleníthető a szállítólevél, hogy később frissíthető legyen a helyes mennyiségekkel. Ehhez hasonlóan a bejövő folyamatban érvényteleníthetők a termékbevételezések, és így frissített változat hozható létre.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Vegyes cikkeket tartalmazó raklapok használata. | Most már lehetőség van „vegyes” raklapok fogadására és regisztrálására. A vegyes raklapok különböző cikkeket tartalmaznak, amelyeket egy raklapra csomagoltak, egy vagy több beszerzési rendeléshez vagy sorhoz. Minden regisztráció összesíthető egy cél azonosítótáblára. A folyamat a raktári mobileszközzel engedélyezhető. Ha például a vegyes cikkeket tartalmazó raklap megérkezik a raktárba, a bevételezési adminisztrátor azonosítja raklapon levő cikkeket és mennyiségüket, mielőtt a raklapot átmozgatnák a kijelölt betárolási helyekre. A betárolási helyeket a munkasablonok és a helyutasítások azonosítják. Ha a betárolási helyek több olyan cikket érintenek, amelyeknek rögzített helye van, a funkció annyi betárolási munkasort hoz létre, amennyi különböző cikk van a vegyes raklapon. A funkció gyorsabbá és rugalmasabbá teszi a beérkező vegyes raklapok regisztrálását és betárolását. További tájékoztatásért lásd a [Vegyes forrásdokumentum-sorokkal rendelkező raklap beérkezése és regisztrálása egy azonosítótábla segítségével](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/13/receive-and-register-a-pallet-with-mixed-source-document-lines-using-1-license-plate-purchase-order-matching/) blogbejegyzést, valamint az információkat a vegyes raklapok támogatásáról a [közelmúltbeli összesítő frissítés bejelentésében](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/06/30/whats-new-in-cu11-for-wms-and-tms/). Annak ellenére, hogy a blogbejegyzés az AX 2012 egyik frissítését ismerteti, ugyanazt a támogatást adtuk most hozzá a Dynamics 365 for Operations megoldáshoz. |

### <a name="minor-feature-enhancements-in-supply-chain-management"></a>Kisebb finomítások az ellátásilánc-kezelésben

<table>




<thead>
<tr class="header">
<th>Mit lehet tenni</th>
<th>Miért fontos ez</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Adatok importálása és exportálása új entitások segítségével.</td>
<td>Az adatokat a következő adatentitások segítségével importálhatja és exportálhatja:
<ul>
<li>Fuvarszámla</li>
<li>Aktuális összesítés raktár és a készlet állapota szerint</li>
<li>Készletköltségek</li>
<li>Árajánlat</li>
</ul></td>
</tr>
<tr class="even">
<td>Továbbfejlesztett Gantt-vezérlő interaktív ütemezési helyzetek fejlesztésére.</td>
<td>A továbbfejlesztett Gantt-vezérlő segítségével új interaktív ütemezési helyzetek fejleszthetők ki, és továbbfejlesztett API-kat lehet szállítani, amelyekkel testre szabható a tevékenységek megjelenése. Az alábbiakban az új API-k közül sorolunk fel néhányat:
<ul>
<li>Függőleges fogd és vidd tevékenységek</li>
<li>Hozzáadási/eltávolítási tevékenységek</li>
<li>Foglalt időszakok előnézetének megtekintése az összegző sorban</li>
<li>Tevékenységhatárok színének és stílusának módosítása</li>
<li>A szöveg színének, stílusának és hátterének módosítása a rácsban</li>
</ul></td>
</tr>
<tr class="odd">
<td>Anyag- és erőforrás-tervezés jobb kezelése.</td>
<td>Néhány továbbfejlesztést tettünk az anyag- és erőforrás-tervezés területén:
<ul>
<li>A rendszer most már kezeli a kiadási időtartalékot, amikor egy cikk készleten van.</li>
<li>Felülírja a szállítási dátumot, amikor megerősíti a tervezett rendeléseket.</li>
<li>Biztonsági készlettel szemben a rendelések teljesítésének előnyben részesítése.</li>
<li>A rendelések múltbeli időpontra ütemezésének megakadályozása.</li>
</ul></td>
</tr>
<tr class="even">
<td>Jelentés a tényleges termelési felhasználásról, valamint a készlet állapotának megtekintése.</td>
<td>Megtekinthető a termelés tényleges felhasználása. Emellett az új <strong>Készletállapot megjelenítése</strong> jelölőnégyzet, amely hozzá lett adva az <strong>Áthelyezés</strong> elemhez a <strong>Munka létrehozása</strong> menüelemen, lehetővé teszi a készlet állapotának megtekintését.</td>
</tr>
<tr class="odd">
<td>Térfogattömeg számítása, ha a szállítmányozó díjai a tömegtérfogaton alapulnak.</td>
<td>Tömegtérfogat-alapú új TMS-díjkalkulátorral bővült a rendszer, hogy lehetőség legyen a tömegtérfogat számítására.</td>
</tr>
</tbody>
</table>



<a name="see-also"></a>Lásd még
--------

[Mi az, ami új vagy módosított](whats-new-changed.md)




