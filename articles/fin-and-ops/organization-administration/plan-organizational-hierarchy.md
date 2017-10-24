---
title: "Szervezeti hierarchia megtervezése"
description: "Szervezetek és szervezeti hierarchiák beállítása előtt, győződjön meg arról, hogy tisztában van vele, mi a vállalata modellezésének legjobb módja."
author: sericks007
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 17404
ms.assetid: babde0c6-bb5d-45ae-95ca-2af75a0ea292
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 45a00f03519679f07c95a669727ecd2fa1a91c41
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="plan-your-organizational-hierarchy"></a>Szervezeti hierarchia megtervezése

[!include[banner](../includes/banner.md)]


Szervezetek és szervezeti hierarchiák beállítása előtt a Microsoft Dynamics 365 for Finance and Operations programban, győződjön meg arról, hogy megtervezi, hogyan lehet modellezni vállalatát. A szervezeti modellnek jelentős hatása van a Microsoft Dynamics 365 for Finance and Operations és az üzleti folyamatok végrehajtására. 

Szervezeti hierarchiák a vállalkozását alkotó szervezetek közötti kapcsolatot jelölik. Ezért a legfontosabb szempont a szervezetek modellezésénél az üzlet szerkezete. Azt ajánljuk, hogy a funkcionális területek, mint például pénzügy és könyvelés, emberi erőforrások, tevékenységek, beszerzés, értékesítés és marketing funkcionális területek vezetőinek és felsővezetőinek visszajelzései alapján határozza meg a szervezeti szerkezeteket. 

Hierarchiák tervezése esetén fontos figyelembe venni a szervezeti hierarchia és a pénzügyi dimenziók közötti kapcsolatot. Több szervezeti hierarchiát is beállíthat a különböző üzleti nézetek ábrázolásához. Pénzügyi dimenziók segítségével, ezen nézetek alapján jelentések készíthetők. Dolgozzon a Microsoft Dynamics 365 for Finance and Operations partnerrel hierarchiák létrehozásához, amelyek a szervezeti és a kötelező jelentési szükségleteket is kezelik. 

> [!Note]
> Annak ellenére, hogy a pénzügyi dimenziók felhasználhatók jogi személyek képviseletére jogi személyek létrehozása nélkül a Microsoft Dynamics 365 for Finance and Operations alkalmazásban, a pénzügyi dimenziókat nem jogi személyek működési vagy üzleti igényeinek kielégítésére tervezték. A Microsoft Dynamics 365 for Finance and Operations rendszerben a Egységközi könyvelés funkció csak az egyes tranzakciók által létrehozott könyvelési tételek kezelését szolgálja. 

> [!Caution]
> A szervezetek modellezéséről nem szabad pusztán az e cikkben megadott információ alapján dönteni. Ez a dokumentáció útmutató. Dolgozhat az Dynamics 365 for Finance and Operations partnerrel a további útmutatásért. A Dynamics 365 for Finance and Operations partner tapasztalatot szerzett különböző ágazatokban és a vevő alapok között.

## <a name="decide-whether-to-model-internal-organizations-as-legal-entities-or-operating-units"></a>Döntse el, hogy a belső szervezeteket jogi személyekként vagy üzemi egységekként modellezi

Rendelkeznie kell legalább egy jogi személlyel, hogy képviselje a vállalatot a Dynamics 365 for Finance and Operations programban. A jogi személy törvényes szerződéseket köthet és pénzügyi kimutatásokat kell készítenie, amely beszámol teljesítményéről. 

A Dynamics 365 for Finance and Operations jogi személyek tranzakciós üzlethez vagy konszolidációhoz használhatók. Ez azt jelenti, hogy a jogi személy a Finance and Operations programban nem feltétlenül képvisel valódi entitást a vállalkozásban. Például egy vállalat, amely részt vesz a tranzakciókban leányvállalati jogi személyeket birtokolhat. Ebben az esetben a jogi személyt meg kell adni a tranzakciókhoz, és egy virtuális jogi személynek konszolidálnia kell a leányvállalati jogi személyek eredményeit és egyenlegét. 

A vállalatban lévő belső szervezetek, mint például a területi irodák további jogi személyekként vagy a fő jogi személy üzemi egységeként ábrázolhatók. Az üzemi egységnek nem kell jogilag meghatározott szervezetnek lennie. Az üzemi egységek az üzletben lévő gazdasági erőforrások és üzemeltetési folyamatok szabályozására használatosak. Például a részlegek és a költséghelyek üzemi egységek. 

Néhány funkció a Dynamics 365 for Finance and Operations programban másképpen működik, attól függően, hogy a szervezet egy jogi személy vagy egy üzemi egység. Gondosan vizsgálja meg az alábbiakban leírt funkciót a döntés meghozatalakor. 


### <a name="master-data"></a>Alapadatok
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Ha a szervezet jogi személyként van modellezve      
Néhány alapadatot, mint például a vevőket, fizetési feltételeket, adóhatóságokat és helyspecifikus készletrendelést be kell állítani az egyes jogi személyekhez. Néhány alapadat, például a felhasználók, a termékek és a legtöbb humánerőforrás-adat az összes jogi személy között meg van osztva. 

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Ha a szervezet üzemi egységként van modellezve 
Az alapadatok meg vannak osztva az üzemi egységek között. 

### <a name="module-parameters"></a>Modulparaméterek
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Ha a szervezet jogi személyként van modellezve    
A modulonkénti paramétereket, például a Kinnlevőségek paramétereit, a Kötelezettségek paramétereit és a Készpénz- és bankkezelése paramétereit, jogi személyenként kell beállítani. Mivel a modulbeállítás a jogi személyekhez külön van, minden leányvállalat megfelelhet a helyi jogszabályi követelményeknek és üzleti eljárásoknak. Például a szakmai szolgáltatási jogi személynek és a gyártási jogi személynek különböző modulparaméterei lehetnek annak ellenére, hogy ugyanazon anyavállalatnak jelentenek. 

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Ha a szervezet üzemi egységként van modellezve 
A modulparaméterek az üzemi egységek között vannak megosztva. 

### <a name="data-security"></a>Adatbiztonság
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Ha a szervezet jogi személyként van modellezve    
A legtöbb adatot automatikusan védi a vállalat azonosítója. A vállalati azonosító a jogi személyhez társított adatok egyedi azonosítója. Egy vállalat csak egy jogi személyhez lehet társítva, egy jogi személy pedig csak egy vállalathoz lehet társítva. A felhasználók csak azon vállalatok adatait érhetik el, amelyekhez van hozzáférésük. Nem szükséges testreszabni a Dynamics 365 for Finance and Operations rendszert az adatvédelemhez a vállalat azonosítójának segítségével. 

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Ha a szervezet üzemi egységként van modellezve 
Az adatok üzemi egységenként védhetők a testreszabott adatbiztonsági szabályok létrehozásával. Az adatbiztonsági szabályok az adatokhoz való hozzáférés korlátozására szolgálnak. Tegyük fel például, hogy a felhasználó csak egy adott üzemi egységben hozhat létre beszerzési rendeléseket. Az adatbiztonsági szabályok létrehozhatók, hogy a felhasználót megakadályozzák abban, hogy más működési egységtől férjen hozzá beszerzési rendelési adatokhoz. A tranzakciók mennyisége és az adatbiztonsági szabályok száma befolyásolhatja a teljesítményt. Biztonsági házirendek tervezésekor gondoljon a teljesítményre. 

### <a name="ledgers"></a>Főkönyvek
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Ha a szervezet jogi személyként van modellezve    
Minden jogi személyhez szükséges főkönyv, amely a fiókokat, a könyvelési pénznemet, a jelentési pénznemet és a pénzügyi naptárat táblázatos formában jeleníti meg. Mérleg csak jogi személyhez hozható létre. Fő számlák, dimenziók, számlastruktúrák, számlák és a főkönyviszámla szabály diagramok egynél több jogi személy által használhatók.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Ha a szervezet üzemi egységként van modellezve 
Üzemi egységnek nem lehetnek saját főkönyvi adatai. Ha a belső szervezeteknek nincs szüksége egyedi főkönyvekre, üzemi egységekként modellezheti őket. Főkönyvi adatokat a fölérendelt jogi személyhez állítanak be a hierarchiában. Kimutatások is létrehozhatók az üzemi egységekhez a jogi személyen vagy a szülő jogi személyen belül. 

### <a name="fiscal-calendars"></a>Pénzügyi naptárak 
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Ha a szervezet jogi személyként van modellezve    
Minden jogi személyhez tartozik saját pénzügyi naptár. Ha a belső szervezetek a különböző pénzügyi évek és pénzügyi naptárakat használnak, a szervezeteket jogi személyekként kell modellezni. 

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Ha a szervezet üzemi egységként van modellezve 
Az üzemi egységeknek meg kell osztani egy pénzügyi naptárat. Ha a belső szervezetek ugyanazokat a pénzügyi éveket és pénzügyi naptárakat használhatják, a szervezeteket működési egységekként modellezheti. 

### <a name="consolidation"></a>Konszolidáció
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Ha a szervezet jogi személyként van modellezve    
A regionális irodák pénzügyi eredményeit konszolidálni kell egy egységes, összesített vállalatba, annak érdekében, hogy pénzügyi kimutatásokat készítsünk. 

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Ha a szervezet üzemi egységként van modellezve 
A konszolidáció nem kötelező, mert az adatok már meg vannak osztva az üzemi egységek között. 

### <a name="centralized-payments"></a>Központosított kifizetések
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Ha a szervezet jogi személyként van modellezve 
A központosított kifizetéseket be kell állítani, hogy az alárendelt jogi személyek számlái kifizethetők a fölérendelt jogi személynek vagy a fölérendelt jogi személytől. 

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Ha a szervezet üzemi egységként van modellezve 
A központosított kifizetések nem szükségesek, mert minden számla rögzítve van a jogi személyben.

### <a name="intercompany-transactions"></a>Vállalatközi tranzakciók
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Ha a szervezet jogi személyként van modellezve 
A vállalatközi értékesítési rendelések, beszerzési rendelések, kifizetések és bevételek egymással alkalmazhatók. Naplóbizonylatok használata nem kötelező. A vállalatközi tranzakciókat megtekintheti a részfőkönyvi szinten (Kinnlevőségek, kötelezettségek). Az alábbi példák bemutatják, hogyan kezelhetők a vállalatközi tranzakciók. 

##### <a name="example-1-headquarters-provides-services-to-regional-offices-and-must-charge-the-costs-of-those-services-to-the-regional-offices"></a>1. példa: A központ szolgáltatásokat nyújt a regionális irodáknak és a szolgáltatások költségeinek díját a regionális irodáknak számolja fel.
Ha a regionális irodát jogi személyként modellezi, akkor a következő lehetőségei vannak: 
- A központ naplóbejegyzést hoz létre, hogy a keresztköltségeket ráterhelje a regionális irodára a kiadásért. A tranzakciók nem korosíthatók.
- A központ beszerzési rendelést küld a szolgáltatásokért a területi irodába. Az értékesítési rendelés automatikusan létrejön a jogi személyben a regionális hivatalhoz a vállalatközi részleges főkönyvi tranzakciókkal. 

##### <a name="example-2-headquarters-procures-and-pays-for-service-that-is-delivered-to-a-regional-office"></a>2. példa: A központ vásárol, és fizet a területi irodába kiszállított szolgáltatásért.
Ha a regionális irodát jogi személyként modellezi, akkor a következő lehetőségei vannak: 
- A számlázás és fizetés a központ jogszabályi követelményeinek megfelelően történik. A központ naplóbejegyzést hozhat létre, hogy a keresztköltségeket ráterhelje a regionális irodára a kiadásért. A tranzakciók nem korosíthatók. 
- A számlázás és fizetés a központ jogszabályi követelményeinek megfelelően történik. A központ létrehozhat egy vállalatközi részleges főkönyvi tranzakciót.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Ha a szervezet üzemi egységként van modellezve 
Az üzemi egységek között a vállalatközi tranzakciók csak a naplóbizonylatokon keresztül támogatottak. Az üzemi egység nem adhat ki vagy kaphat beszerzési rendelést, értékesítési rendelést vagy számlát egy másik üzemi egységtől ugyanabban a jogi személyben. A vállalatközi tranzakciókat nem lehet megtekinteni a részfőkönyv szintjén (Kinnlevőségek, kötelezettségek). Az alábbi példák bemutatják, hogyan kezelhetők a vállalatközi tranzakciók. 

##### <a name="example-1-headquarters-provides-services-to-regional-offices-and-must-charge-the-costs-of-those-services-to-the-regional-offices"></a>1. példa: A központ szolgáltatásokat nyújt a regionális irodáknak és a szolgáltatások költségeinek díját a regionális irodáknak számolja fel.
Ha a regionális hivatalt üzemi egységként modellezi, a központ egy költségtranzakció rögzít, és azt a területi irodához kódolja. 

##### <a name="example-2-headquarters-procures-and-pays-for-service-that-is-delivered-to-a-regional-office"></a>2. példa: A központ vásárol, és fizet a területi irodába kiszállított szolgáltatásért.
Ha a regionális hivatalt üzemi egységként modellezi, akkor a számlázás és a fizetési a központ jogszabályok követelményeinek megfelelően történik. A számla kódolt lehet a regionális irodához. Az eredménykimutatásban a regionális irodához használja a kiegyenlítő pénzügyi dimenziót a költségek jelentéséhez.

### <a name="local-tax-requirements"></a>Helyi adókövetelmények
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Ha a szervezet jogi személyként van modellezve
Jogi személy az adott országban/területen érvényes adóhatóság adótörvényeinek hatálya alá tartozik, ahol a jogi személy regisztrálva van. Például egy jogi személyre, amely regisztrálva van Dániában a dán adó törvények és jogszabályok tartoznak. A Dynamics 365 for Finance and Operations rendszerben egy jogi személy csak egy országhoz/régióhoz tartozhat. A jogi személyhez elsődleges címként beállított ország/régió határozza meg az adott jogi személy számára hozzáférhető ország/régióspecifikus funkciókat. Például ha a jogi személy elsődleges címe Dániában van, dán adótörvényekhez és jogszabályokhoz kapcsolódó funkciók válnak elérhetővé. Ennek megfelelően, ha a szervezetek különböző országokban/régiókban vannak és különböző helyi adóbeállításokat igényelnek, be kell állítania a szervezeteket önálló jogi személyekként.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Ha a szervezet üzemi egységként van modellezve 
Az üzemi egységek a fölérendelt jogi személy ország kontextusát használja. Az ugyanabban a jogi személyben lévő üzemi egységeknek nem lehetnek különböző ország-/ területspecifikus követelményei. Ha a szervezetek ugyanabban az országban/régióban találhatók és az azonos adózási beállításokat használják, akkor beállíthatja azokat üzemi egységeknek.


### <a name="statutory-reporting-for-a-countryregion"></a>Kötelező jelentés országhoz/régióhoz 
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Ha a szervezet jogi személyként van modellezve
Az olyan országok és régiók, amelyeket a Dynamics 365 for Finance and Operations program támogat, a legtöbb kötelező jelentés létrehozható. További információért arról, hogy milyen jelentések érhetők el minden egyes országhoz/régióhoz lásd, [Microsoft Dynamics honosítási portál](https://mbs.microsoft.com/customersource/global/ax/support/support-news/GFMLocalizationPortalMC) a Dynamics 365 for Finance and Operations rendszerhez. (Kötelező megadni a vevői forrás bejelentkezést.) 

> [!Note]
> A Finance and Operationsben a főkönyvi feladási réteg segítségével a korrekciós bejegyzések elvégezhetők olyan fölérendelt vállalatba, amely egy másik könyvelési standardot használ mint az alárendelt vállalat. Ha például egy vállalatra vonatkozóan, amely az Egyesült Királyságban (Egyesült Királyság GAAP) általánosan elfogadott könyvelési gyakorlatokat használ helyesbítő tételeket végezhet a feladási rétegben. Ezek a bejegyzések konszolidálhatók a fölérendelt vállalatba, amely az Egyesült Államokban általánosan elfogadott könyvelési elveket (GAAP) használja. A korrekciós bejegyzések nem befolyásolják a UK GAAP jelentést.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Ha a szervezet üzemi egységként van modellezve 
Kötelező jelentéseket létre kell hozni egy másik alkalmazás segítségével. Győződjön meg arról, hogy az adatok rögzítése megtörténik a Dynamics 365 for Finance and Operations rendszerben az üzemi egységek követelményeinek támogatására, ahol azok különböznek a központ követelményeitől. 

### <a name="currency"></a>Pénznem
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Ha a szervezet jogi személyként van modellezve
Ha a belső szervezeteknek különböző funkcionális pénznemeket kell használnia, a szervezeteket jogi személyekként kell modelleznie. Működési pénznemek jogi személyenként vannak beállítva. Azonban tranzakciókat több pénznemben is megadhat. 

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Ha a szervezet üzemi egységként van modellezve 
Ha a szervezetek egyetlen működési pénznemet használhatnak, a szervezetek üzemi egységekként is modellezhetők. Az üzemi egységeknek meg kell osztaniuk a működési valutát. Azonban több pénznemben is megadhat tranzakciókat és készíthet jelentéseket. 


### <a name="year-end-closing"></a>Év végi zárás
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Ha a szervezet jogi személyként van modellezve
Ha a törvények és a könyvelési szabályok eltérnek az országok/területek között, ahol a szervezetek találhatók, szükség lehet a különböző év végi eljárásokra szervezetenként. Ez azt jelenti, hogy a szervezeteket jogi személyekként kell modelleznie. Minden jogi személyhez tartozik év végi eljárás. 

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Ha a szervezet üzemi egységként van modellezve 
Ha a törvények és a könyvelési szabályok ugyanazok az országokban/területeken, ahol a szervezetek találhatók, szükség lehet egységes év végi eljárásokra. Ez azt jelenti, hogy a szervezeteket működési egységekként modellezheti. Az összes üzemi egységnek ugyanazt az év végi zárási eljárást kell használnia. 
   
### <a name="number-sequences"></a>Számsorozatok
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Ha a szervezet jogi személyként van modellezve
A hivatkozásokhoz számsorozatok állíthatók be jogi személyenként. Egyes számsorozatok megoszthatók. 

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Ha a szervezet üzemi egységként van modellezve 
Néhány hivatkozáshoz számsorozatok működési egységenként állíthatók be. Egyes számsorozatok megoszthatók.

### <a name="products"></a>Termékek 
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Ha a szervezet jogi személyként van modellezve
Termékdefiníciók meg vannak osztva, és ki kell adni őket az egyes jogi személyeknek mielőtt szerepelnek a tranzakciókban. Minden jogi személyhez tartoznak saját tranzakciós dokumentumokban szereplő kiadott termékek. Ha a belső szervezeteknek különböző termékeket kell használniuk, a szervezeteket jogi személyekként kell modellezni. 

> [!Note]
> Annak ellenére, hogy a termékdefiníciók meg vannak osztva valamennyi jogi személynél, ahol a termék már ki van adva, minden egyes készlethelyen a cikkhez különböző értékesítési, beszerzési és tárolási paramétereket adhat meg. 

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Ha a szervezet üzemi egységként van modellezve 
Az összes üzemi egység ugyanazokat a termékeket osztja meg. Ha a belső szervezetek ugyanazokat a termékeket oszthatják meg, a szervezeteket működési egységekként modellezheti. 

### <a name="inquiry-and-reporting"></a>Lekérdezések és jelentések  
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Ha a szervezet jogi személyként van modellezve
Manuálisan kell módosítania a vállalatokat a tranzakciók megadásához és a lekérdezések végrehajtásához több jogi személyben. Adatbiztonsági határokat miatt, a konszolidált lekérdezés és a jelentés időigényes és erőforrás-igényes lehet. 

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Ha a szervezet üzemi egységként van modellezve 
Nem kell módosítania a vállalatokat több üzemi egységből származó adatok eléréséhez. A konszolidált lekérdezés és jelentés és a regionális lekérdezés könnyebb és gyorsabb.

## <a name="best-practices-for-modeling-organizations-and-hierarchies"></a>Legjobb gyakorlati tanácsok szervezetek és hierarchiák modellezéséhez
Vegye figyelembe a következő legjobb gyakorlati tanácsokat a szervezeti hierarchia végrehajtásánál:
-   Hozzon létre részleget, hogy modellezni tudja a jogi személy és az üzleti egység közötti metszetet. Ezután felvetíthet adatot egy részlegből a jogi személynek kötelező jelentéshez és részlegből üzleti egységhez belső jelentéshez. A részlegek profitközpontokként szolgálhatnak. Ha részlegeket használ, nem kell jogi személyeket és üzleti egységeket használnia dimenziókként a számlastruktúrában. Használhat csak részlegeket is dimenzióként. Azonban, költséghelyeket és részlegeket is használnia kell dimenzióként a számlastruktúrában, ha a költséghelyek csak költséggyűjtőkként vannak használva és a részlegeket bevétel elismeréshez használják.
-   Modellezze a több hierarchiát a működési egységekhez, ha bonyolult követelményei vannak a nyereség és a haszon jelentésére.
-   Egy jogi személyben ne modellezzen több hierarchiát ugyanahhoz a hierarchiacélhoz.
-   Ne hozzon létre hierarchiát minden célhoz. Általában használhat egy hierarchiát több célra. Például működési egységek hierarchiáját hozzá lehet rendelni minden irányelvre vonatkozó célhoz.
-   Egyensúlyi hierarchiák létrehozása. Hierarchiában az alap csomóponttól azonos távolságra lévő csomópontok egy szintként vannak meghatározva. Kiegyensúlyozott hierarchiában üzemi egységek csak egyféle típusa fordulhat elő minden szinten, és az alap csomóponttól lévő távolság minden egyes szinten összhangban van. Ha közbenső szintek vannak a részleg és a jogi személy vagy üzleti egység között, a helyőrző szervezeteknek szükséges lehet a kiegyensúlyozott hierarchia létrehozása.
-   Ne modellezze az üzemi egységek külön hierarchiáját, ha a szerkezet a jogi személyekhez egyben a működési struktúra is. A jogi személyek és üzemi egységek vegyes hierarchiája mindkét célra szolgálhat.
-   A fő átstruktúrálási tervek modellezése előtt használja a hierarchia érvényességi dátumát a hatáselemzés és az érvényességi teszt végrehajtásához.
-   A vázlat mód segítségével módosíthatja a hierarchiát az új verzió közzététele előtt termékkörnyezetben.
-   Korlátozhatja az emberek számát, akiknek engedélye van szervezetek hozzáadásához vagy eltávolításához a hierarchiából a termékkörnyezetben. A kevesebb csökkenti annak lehetőségét, hogy költséges hibák fordulnak elő és helyesbítéseket kell elvégezni.

