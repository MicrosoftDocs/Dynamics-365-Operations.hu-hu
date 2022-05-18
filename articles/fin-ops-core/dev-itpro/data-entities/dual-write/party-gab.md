---
title: Fél és globális címjegyzék
description: Ez a témakör a kettős írás Fél és globális címjegyzék-funkcióit ismerteti.
author: RamaKrishnamoorthy
ms.date: 04/25/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-02-22
ms.openlocfilehash: 1e2dcfa69308f6691e787a1ff1893f9080dcaef1
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/05/2022
ms.locfileid: "8717446"
---
# <a name="party-and-global-address-book"></a>Fél és globális címjegyzék

[!include [banner](../../includes/banner.md)]



*A* fél *és a globális címjegyzék* a pénzügyi és az üzemeltetési alkalmazások alapfogalmai. Egy fél lehet személy vagy szervezet. Hasznos egy fél tulajdonságainak –például név, nyelv, névjegyek és címek – globális tárolása és kezelése. Majd ha egy tulajdonság értéke egy helyen változik, az a változás minden olyan helyen tükröződik, ahol a fél érintett.

## <a name="party"></a>Fél

A fél az üzletben részt vevő személy vagy szervezet. Amikor a fél fogalmának használatával egy személy vagy szervezet egynél több szerepkört (például dolgozó, vevő, szállító vagy kapcsolattartó) is játszhat egy vállalkozásban. A szerepkör a kontextuson és a célon alapul. Néhány példa két fiktív vállalat, a Contoso és a Gyár szerepi szerepire:

+ **Dolgozó** – Egy alkalmazott. Ilyen például a Contoso alkalmazottja.
+ **Szállító** – Egy szállító szervezetre vagy egy olyan kizárólagos tulajdonosra vonatkozik, aki árukat vagy szolgáltatásokat nyújt egy vállalkozásnak. Ha például a Gyár kellékeket értékesít a Contoso számára, akkor a Gyár a Contoso szállítója.
+ **Névjegy** – Kapcsolattartó személy. Ha például a Contoso kellékeket vásárol a Gyártól, akkor a Contoso alkalmazottai kapcsolatba lépnek a Gyár kapcsolattartóval.
+ **Vevő** – Olyan személy vagy vállalat, aki vagy amely dolgokat vásárol egy vállalattól. Ha például a Contoso kellékeket vásárol a Gyártól, akkor a Contoso a Gyár vevői.

A fél modellt gyakran használják a szervezetek és az emberek közötti közepes és összetett kapcsolatok képviseletére, különösen akkor, ha egy párt egynél több szerepet játszik. Íme néhány gyakori példa:

+ A fél lehet vevő és szállító is. Például Észak-Amerika, a Gyár elektromos autókat értékesít a Contoso számára, és összeállítva vásárol a Contoso vállalattól. Európában a Gyár alkatrészeket értékesít a Contoso számára, de nem vásárol a Contoso vállalattól.
+ A fél lehet munkavállaló és vevő is. A Contoso egyik alkalmazottja például személyes használatra vásárol elektronikai termékeket a Contoso-tól.
+ Egy személy és egy szervezet között sok a sokhoz (N:N) kapcsolat is lehet. A Fabrikam például szervizszakértőket biztosít, és elhelyezési koordinátort alkalmaz. A helyettes koordinátor elosztja a Fabrikam több ügyféltől érkező munkakérelmeihez a szervizszakembereket. A Contoso a Gyár egyik vevői. Ha a Contoso szakértőt igényel, akkor kapcsolatba lép az elhelyezések koordinálóját, aki ezután megkönnyíti a kérést. Mivel a helyettes koordinátor kezeli az összes vevő kérését, egy N:N kapcsolatban vesz részt.

A következő ábrán a fél adatmodellje látható.

![Adatmodell a félhez.](media/party-gab-image1.png)

> [!TIP]
> Amikor új fiókrekordot próbál létrehozni, a **Fél** mezővel név szerint keresheti meg a rekordot. Így, ha a rekordot megtalálja, csak ki kell választania. A rendszer ezután automatikusan kitölti a fél összes adatát. Nem kell manuálisan beállítania az összes szükséges mezőt. Ez a viselkedés megtalálható a **Partner**, **Névjegy** és **Szállító** lapokon, amelyek gyárilag elérhetők.

A kettős írás nem támogatja a pénzügyi és műveletalkalmazások összes félszerepét. A fél szerepkörök teljes listáját a [Globális címjegyzék áttekintése](../../../fin-ops/organization-administration/overview-global-address-book.md) című témakörben találja.

### <a name="global-address-book"></a>Globális címjegyzék

A globális címjegyzék a vállalkozásban részt vevő szervezetek és személyek postai és elektronikus címeinek jegyzéke.

A globális címjegyzék annyi postai címet és elektronikus címet tárol és kezel, amennyit csak szükséges. Például a Fabrikamnak 50 helyen vannak benzinkutjai. Minden helynek más a postai címe, az e-mail-címe és a telefonszáma. Minden üzleti vásárlást a fő benzinkútnak számlázunk, de közvetlenül a vásárlást igényelő benzinkútra szállítjuk. A globális címjegyzék a fő benzinkutakat a Fabrikam számlázási címeként tárolja, és az egyes benzinkutakat szállítási címekként tárolja. A címek egyszer tárolhatók, és lekérdezhetők az ajánlatokhoz és megrendelésekhez, ha erre szükség van.

Az üzleti környezettől függően előfordulhat, hogy egy személy vagy szervezet több szerepkört is betölt, és minden szerepkörnél használható ugyanaz a postázási és elektronikus cím. Ebben az esetben az egyik szerepkör címváltozásának meg kell jelennie az összes többi szerepkörben. A globális címjegyzék tárolja és kezeli a címeket világszerte.

A következő ábra a globális címjegyzék adatmodelljét mutatja be.

![A globális címjegyzék adatmodellje.](media/party-gab-image2.png)

## <a name="contact"></a>Kapcsolat

Az ügyfélkapcsolati alkalmazásokban a kapcsolattartó egy személy. A **Kapcsolattartó** tábla azonban túlterhelt, hogy egy személyt, egy portálfelhasználót, egy céget és ügyfelet (B2C) vagy egy szállítót képviseljen. A reprezentáció implicit, és nem tudja megkülönböztetni a kapcsolódó tranzakciókat vizsgálat nélkül. A **Kapcsolattartó** tábla egy az egyhez (1:1) kapcsolattal rendelkezik a **Partner** táblával. A fél és a globális címjegyzék-modell részeként a kettős írás explicit tulajdonságokat vezet be a besoroláshoz, és lehetővé teszi az N:N kapcsolatokat egy kapcsolattartó személy és egy szervezet (**Partner** entitás vagy **Szállító** entitás) között.

A **Kapcsolattartó** soroknak két típusa van:

+ **Csíkozott kapcsolattartó** – A **Kapcsolattartó** sor, ahol a **Vállalat** mező kötelező értéket biztosít.
+ **Nem csíkozott kapcsolattartó** – A **Kapcsolattartó** sor, ahol a **Vállalat** mezője üres.

A **Kapcsolattartó** tábla az alábbi típusú sorokat tudja tárolni.

| Sor típusa | Leírás |
|----------|-------------|
| Olyan személy, aki vevő (például eladásra alkalmas kapcsolattartó vagy B2C vevő) | Olyan csíkozott kapcsolattartói rekord, ahol a **Vállalat** mező nem üres, és a **Vevő** mező beállítása **Igen**. |
| Olyan személy, aki szállító (például egyéni vállalkozóhoz hasonló szállító) | Olyan csíkozott kapcsolattartói rekord, ahol a **Vállalat** mező nem üres, és a **Szállító** mező beállítása **Igen**. |
| A személy lehet vevő és szállító is | Olyan csíkozott kapcsolattartói rekord, ahol a **Vállalat** mező nem üres, és a **Vevő** mező beállítása **Igen**, és a **Szállító** mező beállítása is **Igen**. Egy személy egyszerre lehet az egyik termék gyártója és egy másik termék fogyasztója. Ezt a kapcsolatot mind a pénzügy, mind az üzemeltetési alkalmazások, mind a kettősírásos alkalmazások támogatják. |
| Olyan személy, aki egy szervezet kapcsolattartója, de nem vevő vagy szállító | Olyan nem csíkozott kapcsolattartói rekord, ahol a **Vállalat** mező nem üres, és a **Vevő** mező beállítása **Nem**, és a **Szállító** mező beállítása is **Nem**. |

## <a name="contact-for-party-table"></a>Fél kapcsolattartója tábla

A **Fél kapcsolattartója** tábla N:N kapcsolatokat tárol és kezel a **Partner** sorok és a **Kapcsolattartó** sorok között. Kiszűrheti a csíkozott **Kapcsolattartó** sorokat a nem csíkozott sorokból, és csak a nem csíkozott **Kapcsolattartó** sorokat társíthatja egy **Partner** vagy **Szállító** sorhoz.

Például Natasha Jones és Miguel Reyes állatorvosok, akik gondoskodnak a területük gazdaságáról. Natasha Seattle területen szolgál, míg Miguel Kent területen szolgál. Az ügyfélkapcsolati alkalmazásban a gazdaságok ügyfélként képviseltetik magukat, az állatorvosok pedig kapcsolattartókként jelennek meg. Natasha egyetlen **Kapcsolattartó** rekordja kapcsolódik az összes farmhoz, ahol Natasha dolgozik. Hasonlóan Miguel egyetlen **Kapcsolattartó** rekordja kapcsolódik az összes farmhoz, ahol Miguel dolgozik.

Ezeket a kapcsolatokat a Partner a **Fél kapcsolattartója** tábla tárolja. Ez az információ megtalálható a **Partner**, **Névjegy** és **Szállító** lapokon, amelyek gyárilag elérhetők:

+ A **Partner** lapon a **Társított kapcsolattartók** fülön társíthat egy vagy több kapcsolattartót a **Partner** sorához. Így rendelhet hozzá kapcsolattartókat egy szervezethez. Ezután a partnerhez kijelölhet egy elsődleges kapcsolattartót. Ha a **Gyors létrehozás** lapot használja, csak kapcsolattartót választhat ki. A viselkedés ugyanaz, ha a **Szállító** lapot használja, és a rekord típusa **Szervezet**.
+ A **Kapcsolattartó** lapon, amikor a sor egy vevő, egy szállító vagy mindkettő (egy csíkozott kapcsolattartó), akkor a **Társított kapcsolattartók** fülön társíthat hozzá egy vagy több kapcsolattartót. Így rendelhet hozzá kapcsolattartókat a B2C ügyfélhez vagy szállítóhoz. Ezután kijelölhet egy elsődleges kapcsolattartót. Ha a **Gyors létrehozás** lapot használja, csak kapcsolattartót választhat ki.
+ A **Kapcsolattartó** lapon, amikor a sor egy kapcsolattartó (egy nem csíkozott kapcsolattartó), akkor a **Társított szervezetek** fülön társíthat hozzá egy vagy több ügyfelet vagy szállítót. Így rendelhet hozzá egy ügyfelet vagy szállítót a mögöttes kapcsolattartóhoz. A vevő vagy szállító lehet szervezet, személy vagy mindkettő. Egyszerre csak egy értéket választhat a négy mezőből:

    + Ha a **Fél azonosítója** mezőben kiválaszt egy értéket, akkor az alapul szolgáló kapcsolattartó a kiválasztott fél összes szerepköréhez hozzá van rendelve.
    + Ha a **Társított kapcsolattartó** mezőben kiválaszt egy értéket, akkor a **Személy** típusú csíkozott kapcsolattartót választja.
    + Ha a **Társított partner** vagy a **Társított szállító** mezőben választ értéket, akkor egy szervezetet jelöl ki.

    ![Társított szervezetek fül a Kapcsolattartó lapon.](media/party-gab-image3.png)

    Az Ön választásától függetlenül a társítás a felek szintjén jön létre, és a fél összes szerepkörére vonatkozik, és a **Fél kapcsolattartója** entitásban tárolódik.

> [!NOTE]
> A **Fél kapcsolattartója** tábla megjelenítendő neve a Customer Engagement alkalmazásokban **Ügyfél/szállító kapcsolattartója**.

Ha olyan **Kapcsolattartó** sort nyit meg, amelyben mind a **Vevő**, mind a **Szállító** mezője **Nem** értékre van állítva, akkor megjelenik a **Kapcsolódó szervezetek** fül. Ezzel a füllel egy vagy több vevői vagy szállítói szervezetet társíthat a kapcsolattartóhoz.

Ha olyan **Kapcsolattartó** sort nyit meg, amelyben vagy a **Vevő** vagy a **Szállító** mező **Igen** értékre van állítva, akkor megjelenik a **Kapcsolódó kapcsolattartók** fül. Ezen a lapon egy vagy több kapcsolattartót társíthat.

## <a name="postal-addresses"></a>Postai címek

A **Partner**, **Kapcsolattartó** és **Szállító** lapokon egy új **Címek** fül került bevezetésre. Ez a fül több postai címet is támogat a rács használatával, lásd az alábbi ábrát.

![A postai címek rácsa.](media/party-gab-image4.png)

A rács a következő oszlopokat tartalmazza:

+ **Postacím szerepek** – A postacím célja.
+ **Elsődleges** – Ez az érték jelzi, hogy a cím elsődleges-e vagy sem.
+ **Cím száma** – A cím sorrendje.

A rács fölötti **Új cím** gombbal annyi postai címet hozhat létre, amennyit csak szeretne.

A **Cím 1** és **Cím 2** mezők az **Összegzés** lapon a **Partner** lapon megfelelnek a **Szállítási** és **Számlázási** címeknek.

![A postai címek összegző lapja.](media/party-gab-image5.png)

A **Cím 1**, **Cím 2** és **Cím 3** mezők az **Összegzés** lapon a **Kapcsolattartó** lapon megfelelnek a **Céges**, **Szállítási** és **Számlázási** címeknek.

## <a name="electronic-addresses"></a>Elektronikus címek

A **Partner**, **Kapcsolattartó** és **Szállító** lapokon egy új **Elektronikus címek** fül került bevezetésre. Ez a fül több elektronikus címet is támogat a rács használatával, lásd az alábbi ábrát.

![Az elektronikus címek rácsa.](media/party-gab-image6.png)

A rács a következő oszlopokat tartalmazza:

+ **Típus** – Az elektronikus cím típusa.
+ **Elsődleges** Ez az érték jelzi, hogy a cím elsődleges-e vagy sem.
+ **Cél** – Az elektronikus cím célja.

A rács fölötti **Új elektronikus cím** gombbal annyi címet hozhat létre, amennyit csak szeretne.

Az érdeklődő képesítési folyamata során meg lehet adni egy üzleti telefonszám és egy mobiltelefonszám is. Az üzleti telefonszám az **elsődleges telefonszám (ha Is Yes**=Nem). **A mobiltelefonszám a másodlagos telefonszámnak számít, ha Igen**.

> [!TIP]
> A postai és elektronikus címek kezeléséhez használja a **Címek** és az **Elektronikus címek** lapokat a **Fiók** és a **Kapcsolat** űrlapokon. Így garantálható, hogy a címadatok szinkronizálva lesznek a pénzügyekkel és a műveletekkel kapcsolatos alkalmazásokkal.

## <a name="setup"></a>Beállítás

1. Nyissa meg az ügyfélkapcsolati alkalmazáskörnyezetét.

2. Telepítse az összes előfeltétel-megoldást a [Részletes kétírásos alkalmazáscsomagban leírtak szerint](separated-solutions.md).

3. [Kettős írású fél és globális címjegyzék megoldások](https://aka.ms/dual-write-gab) telepítése.

4. Nyissa meg a Finance and Operations alkalmazást. Nyissa meg az Adatkezelés modult, és válassza a Kettős írás lapot. Megnyílik a kettős írás adminisztrációja lap.

5. A 2. és a 3. lépésben telepített mindkét megoldást alkalmazza a [Megoldás alkalmazása](link-your-environment.md) funkcióval.

6. Állítsa le a következő leképezéseket, mert már nem szükségesek. Ehelyett futtassa a `Contacts V2 (msdyn_contactforparties)` leképezést.

    + CDS Kapcsolattartók V2 és Kapcsolattartók (vevői kapcsolattartókra vonatkozik)
    + CDS Kapcsolattartók V2 és Kapcsolattartók (szállítói kapcsolattartókra vonatkozik)

7. A felek funkcióira vonatkozó következő entitásleképezések frissülnek, ezért a legújabb verziót kell alkalmazni ezekre a leképezésekre.

    Megfeleltetés | Frissítés erre a verzióra | Változások
    ---|---|---
    `CDS Parties (msdyn_parties)`| 1.0.0.2 | Ez egy új leképezés, amely ezen kiadás részeként lett hozzáadva.
    `Contacts V2 (msdyn_contactforparties)`| 1.0.0.6 | Ez egy új leképezés, amely ezen kiadás részeként lett hozzáadva.
    `Customers V3 (accounts)` | 1.0.0.5 |Eltávolítottuk a `PartyNumber` és más, félhez kapcsolódó mezőket, például a nevet, a személyes adatokat, a postai címmezőket, és az elektronikus kapcsolattartó címét.
    `Customer V3 (contacts)` | 1.0.0.5 | Eltávolítottuk a `PartyNumber` és más, félhez kapcsolódó mezőket, például a nevet, a személyes adatokat, a postai címmezőket, és az elektronikus kapcsolattartó címét.
    `Vendors V2 (msdyn_vendors)` | 1.0.0.6 | Eltávolítottuk a `PartyNumber` és más, félhez kapcsolódó mezőket, például a nevet, a személyes adatokat, a postai címmezőket, és az elektronikus kapcsolattartó címét.
    `CDS Sales quotation headers (quotes)` | 1.0.0.7 | Kicseréltük a kapcsolattartót a `ContactforParty` hivatkozásra.
    `Sales invoice headers V2 (invoices)` | 1.0.0.4 | Kicseréltük a kapcsolattartót a `ContactforParty` hivatkozásra.
    `CDS Sales order headers (salesorders)` | 1.0.0.5 | Kicseréltük a kapcsolattartót a `ContactforParty` hivatkozásra.
    `CDS Party postal address locations (msdyn_partypostaladdresses)` | 1.0.0.1  | Ez egy új leképezés, amely ezen kiadás részeként lett hozzáadva.
    `CDS postal address history V2 (msdyn_postaladdresses)` | 1.0.0.2 | Ez egy új leképezés, amely ezen kiadás részeként lett hozzáadva.
    `CDS postal address locations (msdyn_postaladdresscollections)` | 1.0.0.0 | Ez egy új leképezés, amely ezen kiadás részeként lett hozzáadva.
    `Party Contacts V3 (msdyn_partyelectronicaddresses)` | 1.0.0.0 | Ez egy új leképezés, amely ezen kiadás részeként lett hozzáadva.
    `Complimentary Closings (msdyn_compliemntaryclosings)` | 1.0.0.0 | Ez egy új leképezés, amely ezen kiadás részeként lett hozzáadva.
    `Decision making roles (msdyn_decisionmakingroles)` | 1.0.0.0 | Ez egy új leképezés, amely ezen kiadás részeként lett hozzáadva.
    `Loyalty levels (msdyn_loyaltylevels)` | 1.0.0.0 | Ez egy új leképezés, amely ezen kiadás részeként lett hozzáadva.
    `Contact person titles (msdyn_salescontactpersontitles)` | 1.0.0.0 | Ez egy új leképezés, amely ezen kiadás részeként lett hozzáadva.
    `Personal character types (msdyn_personalcharactertypes)` | 1.0.0.0 | Ez egy új leképezés, amely ezen kiadás részeként lett hozzáadva.
    `Salutations (msdyn_salutations)` | 1.0.0.0 | Ez egy új leképezés, amely ezen kiadás részeként lett hozzáadva.
    `Employment job functions (msdyn_employmentjobfunctions)` | 1.0.0.0 | Ez egy új leképezés, amely ezen kiadás részeként lett hozzáadva.
    `CDS Address roles (msdyn_addressroles)` | 1.0.0.0 | Ez egy új leképezés, amely ezen kiadás részeként lett hozzáadva.

8. A fenti leképezések futtatása előtt manuálisan kell frissítenie az integrációs kulcsokat a következő lépéseknek megfelelően. Majd válassza a **Mentés** lehetőséget.

    | Megfeleltetés | Kulcsok |
    |-----|------|
    | Könyvelési számla |  accountnumber [Számlaszám]<br>msdyn_company.cdm_companycode [Vállalat (Vállalatkód)] |
    | Kapcsolat | msdyn_contactpersonid [Számlaszám/Kontaktszemély azonosítója]<br>msdyn_company.cdm_companycode [Vállalat (Vállalatkód)] |
    | Vevő/szállító kapcsolattartója | msdyn_contactforpartynumber [Fél kapcsolattartójának száma]<br>msdyn_associatedcompanyid.cdm_companycode [Társított vállalat (Vállalatkód)] |
    | Szállító | msdyn_vendoraccountnumber [Szállító számlaszáma]<br>msdyn_company.cdm_companycode [Vállalat (Vállalatkód)]|

9. A Dataverse-ben az ismétlődések észlelési szabályaiban szereplő karakterkorlátok száma 450-ről 700 karakterre nő. Ezzel a korláttal egy vagy több kulcsot adhat hozzá az ismétlődések észlelési szabályaihoz. Bontsa ki a **Partnerek** tábla ismétlődések észlelési szabályát a következő mezők beállításával.

    | Mező | Érték |
    |-------|-------|
    | Név | Azonos fióknévvel rendelkező partnerek. |
    | Leírás | A Számlanév attribútumban azonos értéket tartalmazó fiókrekordok észlelése. |
    | Alap rekordtípus | Könyvelési számla |
    | Egyező rekordtípus | Könyvelési számla |
    | Számla neve (mező) | Pontos egyezés |
    | Vállalat (mező) | Pontos egyezés |
    | Kapcsolattípus (mező) | Pontos egyezés |
    | Félazonosító (mező) | Pontos egyezés |
    | Kiválasztás (mező) | (üres) |

    ![Ismétlődő szabály a Számlákhoz.](media/duplicate-rule-1.PNG)

10. Bontsa ki a **Kapcsolattartók** tábla ismétlődések észlelési szabályát a következő mezők beállításával.

    | Mező | Érték |
    |-------|-------|
    | Név | Azonos keresztnév és vezetéknévvel szereplő kapcsolattartók. |
    | Leírás | A Keresztnév és Vezetéknév mezőkben megegyező értékekkel rendelkező kapcsolattartókat észleli. |
    | Alap rekordtípus | Kapcsolat |
    | Egyező rekordtípus | Kapcsolat |
    | Keresztnév (mező) | Pontos egyezés |
    | Vezetéknév (mező) | Pontos egyezés |
    | Vállalat (mező) | Pontos egyezés |
    | Félazonosító (mező) | Pontos egyezés |
    | Kiválasztás (mező) | (üres) |

    ![Ismétlődő szabály a Kapcsolattartókhoz.](media/duplicate-rule-2.PNG)

11. Ha Ön kettős írású felhasználó, hajtsa végre a [Frissítés a fél és globális címjegyzék modelljére](upgrade-party-gab.md) megadott utasításokat, és frissítse az adatait. **Ne lépjen tovább a 12. lépésre a lépés befejezése nélkül.** Ha Ön egy új kettős írású felhasználó, folytassa a 12. lépéssel.

12. Ha ön kettős írású felhasználó, a 11. lépést kell végrehajtania, és a következő sorrendben futtathatja a leképezések futtatását. Ha Ön egy új kétírásos vevő, közvetlenül folytathatja. Ha megjelenik egy hibaüzenet, amely a "Projektellenőrzés sikertelen" üzenetet jelenik meg. Hiányzik a célmezőből,nyissa meg a leképezés, és válassza **a** Táblák frissítése lehetőséget, majd futtassa a leképezés.

    Pénzügy és műveletek alkalmazás | Customer Engagement alkalmazás  
    ----------------------------|------------------------
    [CDS-felek](mapping-reference.md#220) | msdyn_parties
    [CDS postai címének helyei](mapping-reference.md#234) | msdyn_postaladdresscollections
    [CDS-fél postai címének előzményei V2](mapping-reference.md#235) | msdyn_postaladdresses
    [CDS-fél postai címének helyei](mapping-reference.md#233) | msdyn_partypostaladdresses
    [Ügyfél-kapcsolattartók V3](mapping-reference.md#236) | msdyn_partyelectronicaddresses
    [Vevők V3](mapping-reference.md#101) | számlák
    [Vevők V3](mapping-reference.md#116) | kapcsolattartók
    [Szállítók V2](mapping-reference.md#202) | msdyn_vendors
    [Kapcsolattartó megszólításai](mapping-reference.md#223) | msdyn_salescontactpersontitles
    [Udvarias levélzárások](mapping-reference.md#222) | msdyn_complimentaryclosings
    [Üdvözlések](mapping-reference.md#228) | msdyn_salutations
    [Döntéshozatali szerepkörök](mapping-reference.md#224) | msdyn_decisionmakingroles
    [Foglalkoztatási beosztásfunkciók](mapping-reference.md#225) | msdyn_employmentjobfunctions
    [Hűségszintek](mapping-reference.md#226) | msdyn_loyaltylevels
    [Személyes karaktertípusok](mapping-reference.md#227) | msdyn_personalcharactertypes
    [Kapcsolattartók V2](mapping-reference.md#221) | msdyn_contactforparties
    [CDS értékesítésiajánlat-fejléc](mapping-reference.md#215) | ajánlatok
    [CDS értékesítésirendelés-fejlécek](mapping-reference.md#217) | salesorders
    [Értékesítésiszámla-fejlécek V2](mapping-reference.md#118) | számlák
    [CDS-címszerepkre](mapping-reference.md#301) | msdyn_addressroles

> [!NOTE]
> A `CDS Contacts V2 (contacts)` leképezés az 1. lépésben leállított térkép. Amikor más leképezéseket próbál futtatni, előfordulhat, hogy ez a 2 leképezés a függők listájában fog megjelenni. Ne futtassa ezeket a leképezéseket.
>
> Ha telepítve van a fél és a globális címjegyzék megoldás, le kell tiltani a következő nevűt `Microsoft.Dynamics.SCMExtended.Plugins.Plugins.LeadPrimaryContactPostCreate: QualifyLead of lead`: . Ha törli a fél és globális címjegyzék megoldást, akkor újra engedélyeznie kell a beépülő modult.
>
> A `msdyn_*partynumber` mezőt (egyetlen sor szövegmezője) nem szabad előre használni a **Partner**, **Kapcsolattartó** és **Szállító** táblában. A címkenév az egyértelműség kedvéért az **(Elavult)** előtagot fogja viselni. Ehelyett használja az **msdyn_partyid** mezőt. A mező a **msdyn_party** tábla keresője.
>
> Tábla neve | Régi mező | Új mező
> --------|-------|--------
> Könyvelési számla | `msdyn_partynumber` | `msdyn_partyid`
> Kapcsolat | `msdyn_partynumber` | `msdyn_partyid`
> msdyn_vendor | `msdyn_vendorpartynumber` | `msdyn_partyid`

## <a name="templates"></a>Sablonok

Ahogy az alábbi táblázatban látható, az táblaleképezések gyűjteménye együttműködik a fél és globális címjegyzék interakciók során.

| Pénzügy és műveletek alkalmazás | Customer Engagement alkalmazás | Leírás |
|----------------------------|-------------------------|-------------|
| [Kapcsolattartó megszólításai](mapping-reference.md#223) | msdyn\_salescontactpersontitles |
| [Vevők V3](mapping-reference.md#101) | számlák |
| [Vevők V3](mapping-reference.md#116) | kapcsolattartók |
| [CDS-felek](mapping-reference.md#220) | msdyn\_parties |
| [CDS-fél postai címének helyei](mapping-reference.md#233) | msdyn\_partypostaladdresses |
| [CDS-fél postai címének előzményei V2](mapping-reference.md#235) | msdyn\_postaladdresses |
| [CDS postai címének helyei](mapping-reference.md#234) | msdyn\_postaladdresscollections |
| [CDS értékesítésiajánlat-fejléc](mapping-reference.md#215) | ajánlatok |
| [CDS értékesítésirendelés-fejlécek](mapping-reference.md#217) | salesorders |
| [Udvarias levélzárások](mapping-reference.md#222) | msdyn\_complimentaryclosings |
| [Kapcsolattartók V2](mapping-reference.md#221) | msdyn\_contactforparties |
| [Döntéshozatali szerepkörök](mapping-reference.md#224) | msdyn\_decisionmakingroles |
| [Foglalkoztatási beosztásfunkciók](mapping-reference.md#225) | msdyn\_employmentjobfunctions |
| [Hűségszintek](mapping-reference.md#226) | msdyn\_loyaltylevels |
| [Ügyfél-kapcsolattartók V3](mapping-reference.md#236) | msdyn\_partyelectronicaddresses |
| [Személyes karaktertípusok](mapping-reference.md#227) | msdyn\_personalcharactertypes |
| [Értékesítésiszámla-fejlécek V2](mapping-reference.md#118) | számlák |
| [Üdvözlések](mapping-reference.md#228) | msdyn\_salutations |
| [Szállítók V2](mapping-reference.md#202) | msdyn\_vendors |
| [CDS-címszerepkre](mapping-reference.md#301) |msdynaddressroles\_|

További tájékoztatás: [Kettős írású leképezési hivatkozás](mapping-reference.md).

## <a name="address-roles-as-a-multi-select-drop-down-list"></a>Címszerepek több kijelölésű legördülő listaként
Egy postai cím vagy e-mail cím több célra is használható. Például a postai cím számlázási címként és szállítási címként is szolgál. Ilyen esetben a felhasználók **a** **legördülő** listában a Számlázás és a Szállítás listában is választhatnak, amint azt az alábbi ábra mutatja. 

![Cél/szerepkör legördülő lista](media/purpose.png)

## <a name="known-issues-and-limitations"></a>Ismert problémák és korlátozások

+ A pénzügyi és műveleti alkalmazásokban előfordulhat, hogy a címvel együtt vevőt hoz létre és ment, előfordulhat, hogy a cím nem szinkronizálható a Cím **táblával**. Ez a kettős írású platform sorrendbe állítási hibája miatt van. Ez a megoldás megoldás: először hozza létre a vevőt, és mentse el. Ezután adja meg a címet.
+ A pénzügyi és műveleti alkalmazásokban, amikor egy vevőrekordhoz elsődleges cím tartozik, és az adott vevőhöz új kapcsolattartót hoz létre, akkor a kapcsolattartó-rekord a társított vevőrekordból örökli az elsődleges címet. Ez a szállító kapcsolattartója esetén is megtörténik. Dataverse jelenleg nem támogatja ezt a viselkedést. Ha engedélyezve van a kettős írás, a rendszer a címével szinkronizálja a Dataverse pénzügyek és műveletek alkalmazásában elsődleges címmel örökölt vevői kapcsolattartókat.
+ A Pénzügy és műveletek alkalmazásokban kapcsolattartó-rekordot hozhat létre a **Kapcsolattartó hozzáadása képernyőn**. Amikor a **Kapcsolattartó megtekintése** képernyőről megpróbál új kapcsolattartót létrehozni, a művelet sikertelen lesz. Ez egy ismert probléma.

    ![Ismert probléma a Kapcsolattartó hozzáadásával kapcsolatban.](media/party-gab-contact-issue.png)

+ A **Kezdeti szinkronizálás** nem támogatja az **Elérhető űrlap** és **Elérhető** lehetőségeket a **ContactForParty** időmezőkön, mivel a DIXF egész szám helyett karakterlánccá alakítja az értéket. Az átalakítás a `Cannot convert the literal '<say 08:00:00>' to the expected type edm.int32` hibát váltja ki.
+ Előredátumozott postai címet nem lehet kettős írású pénzügyi és műveleti alkalmazással megadni, mert Dataverse ez nem támogatja a dátumhatályt. Ha egy pénzügyi és műveleti alkalmazás segítségével ad meg egy jövőbeli postai címet, Dataverse akkor az teljesen szinkronizál, és a cím azonnal látható a felhasználói felületen. A rekord minden frissítése hibát eredményez, mivel az jövőbeli dátumú, nem pedig aktuális a pénzügy és a műveletek alkalmazásban.
