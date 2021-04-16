---
title: Fél és globális címjegyzék
description: Ez a témakör a kettős írás Fél és globális címjegyzék-funkcióit ismerteti.
author: RamaKrishnamoorthy
ms.date: 02/22/2021
ms.topic: article
ms.service: dynamics-ax-applications
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-02-22
ms.openlocfilehash: e7bec58f8094a1448017822e7d8840368cc482b8
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750788"
---
# <a name="party-and-global-address-book"></a>Fél és globális címjegyzék

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

A Fél és globális címjegyzék fogalmak a Finance and Operations alkalmazásokban. Egy Fél lehet személy vagy szervezet. Hasznos egy **Fél** tulajdonságainak –például név, nyelv, névjegyek és címek – globális tárolása és kezelése. Ha egy tulajdonság értéke egy helyen változik, az minden olyan helyen tükröződik, ahol a **Fél** érintett.

## <a name="party"></a>Fél

A *Fél* az üzletben részt vevő személy vagy szervezet. A Fél fogalmának használatával egy személy vagy szervezet egynél több szerepkört (dolgozó, vevő, szállító vagy kapcsolattartó) is játszhat egy vállalkozásban. A szerepkör a kontextuson és a célon alapul. Íme néhány példa két fiktív vállalattól, a Contoso-ról és a Fabrikam-ról.

+ **Dolgozó**: Egy alkalmazott. Például a Contoso egyik alkalmazottja.
+ **Szállító**: Egy szállító szervezetre vagy egy olyan kizárólagos tulajdonosra vonatkozik, aki árukat vagy szolgáltatásokat nyújt egy vállalkozásnak. Ha például a Fabrikam kellékeket ad el a Contoso-nak, akkor a Fabrikam szerepköre beszállító.
+ **Névjegy** : Kapcsolattartó személy. Ha például Contoso kellékanyagokat vásárol a Fabrikamtól, a Contoso egyik alkalmazottja kapcsolatba lép a Fabrikam kapcsolattartójával.
+ **Vevő:** Az vevő olyan személy vagy vállalat, aki vagy amely dolgokat vásárol egy vállalattól. Ha például Contoso kellékeket vásárol a Fabrikamtól, akkor Contoso a Fabrikam vevője.

A Fél modellt gyakran használják a szervezetek és az emberek közötti közepes és összetett kapcsolatok képviseletére, különösen akkor, ha egy párt egynél több szerepet játszik. Íme néhány gyakori példa:

+ A fél lehet vevő és szállító is. Észak-Amerikában például a Fabrikam elektromos vezetékeket értékesít a Contoso-nak, és összeszerelt hangszórókat vásárol a Contoso-tól. Európában a Fabrikam alkatrészeket ad el a Contoso-nak, de a Contoso-tól semmit sem vásárol.
+ A fél lehet munkavállaló és vevő is. A Contoso egyik alkalmazottja például személyes használatra vásárol elektronikai termékeket a Contoso-tól.
+ Egy személy és egy szervezet között sok a sokhoz kapcsolat is lehet. A Fabrikam például szervizszakértőket biztosít, és elhelyezési koordinátort alkalmaz. A koordinátor elosztja a Fabrikam több ügyféltől érkező munkakérelmeihez a szervizszakembereket. A Contoso az egyik vevői partner. Amikor Contoso-nak szakemberre van szüksége, Contoso kapcsolatba lép a koordinátorral, aki elintézi a kérést. A koordinátor kezeli az összes ügyfél kéréseit, és sok a sokhoz kapcsolatot hoz létre.

A következő képen a Fél adatmodellje látható:

![Adatmodell félhez](media/party-gab-image1.png)

> [!Tip]
> Amikor új fiókrekordot próbál létrehozni, a „Fél” mezővel név szerint keresheti meg a rekordot. Abban az esetben, ha megtalálta a rekordot, csak ki kell választania a rekordot. A rendszer automatikusan kitölti a fél összes adatát. Nem kell manuálisan megadnia az összes szükséges mezőt. Ez a viselkedés megtalálható a Partner, Névjegy és Szállító űrlapokon, amelyek gyárilag elérhetők.

A Finance and Operations alkalmazások nem minden fél szerepkörét támogatja a kettős írás. A fél szerepkörök teljes listáját a [Globális címjegyzék áttekintése](../../../fin-ops/organization-administration/overview-global-address-book.md) című témakörben találja.

### <a name="global-address-book"></a>Globális címjegyzék

A globális címjegyzék a vállalkozásban részt vevő szervezetek és személyek postai és elektronikus címeinek jegyzéke.

A globális címjegyzék annyi postai címet és elektronikus címet tárol és kezel, amennyit csak szükséges. Tegyük fel például, hogy a Fabrikamnak 50 helyen vannak benzinkutjai. Minden helynek más a postai címe, az e-mail címe és a telefonszáma. Minden üzleti vásárlást a fő benzinkútnak számlázunk, de a vásárlásokat közvetlenül a vásárlást igényelő benzinkútra szállítjuk. A globális címjegyzék a fő benzink állomást számlázási címként, az egyes benzinkutak pedig a Fabrikam szállítási címeként tárolja. A címek egyszer tárolhatók, és szükség szerint lekérdezhetők az ajánlatokhoz és megrendelésekhez.

Egy személy vagy szervezet az üzleti környezet alapján egynél több szerepkört is játszhat. Ha így van, akkor a postacímük és az elektronikus címük ugyanaz lehet. Ebben az esetben az egyik szerepkör címváltozásának meg kell jelennie a másik szerepkörben, és fordítva. A globális címjegyzék tárolja és kezeli a címeket világszerte.

![A globális címjegyzék adatmodellje](media/party-gab-image2.png)

## <a name="contacts"></a>Kapcsolattartók

Az ügyfélkapcsolati alkalmazásokban a *Kapcsolattartó* egy személy. A **Kapcsolattartó** tábla azonban túlterhelt, hogy egy személyt, egy portálfelhasználót, egy B2C vevőt vagy egy szállítót képviseljen. A reprezentáció implicit, és nem tudja megkülönböztetni a kapcsolódó tranzakciók vizsgálata nélkül. A **Kapcsolattartó** tábla 1:1 kapcsolattal rendelkezik a **Partner** táblával. A Fél és a globális címjegyzék-modell részeként a kettős írás explicit tulajdonságokat vezet be a besoroláshoz, és a kettős írás lehetővé teszi az N:N kapcsolatokat egy **Kapcsolattartó** személy és egy szervezet (Partner entitás vagy Szállító entitás) között.

A **Kapcsolattartó** soroknak két típusa van:

+ Csíkozott kapcsolattartó – Kötelező értéket biztosító kapcsolattartó sor a **Vállalat** mezőben.
+ Nem csíkozott kapcsolattartó – A kapcsolattartó sor üres **Vállalat** mezővel.

A **Kapcsolattartó** tábla az alábbi típusú sorokat tudja tárolni:

Sor típusa | Leírás
---|---
Olyan személy, aki vevő, például eladásra alkalmas kapcsolattartó vagy B2C vevő. | Olyan csíkozott kapcsolattartói rekord, ahol a **Vállalat** mező nem üres, és a **Vevő** mező beállítása **Igen**.
Olyan személy, aki szállító, például egyéni vállalkozóhoz hasonló szállító. | Olyan csíkozott kapcsolattartói rekord, ahol a **Vállalat** mező nem üres, és a **Szállító** mező beállítása **Igen**.
A személy lehet vevő és szállító is. | Olyan csíkozott kapcsolattartói rekord, ahol a **Vállalat** mező nem üres, és a **Vevő** mező beállítása **Igen**, és a **Szállító** mező beállítása is **Igen**. Egy személy egyszerre lehet az egyik termék gyártója és egy másik termék fogyasztója. Mind Finance and Operations alkalmazások, mind a kettős írás támogatja ezt a kapcsolatot.
Olyan személy, aki egy szervezet kapcsolattartója, de nem vevő vagy szállító. | Olyan nem csíkozott kapcsolattartói rekord, ahol a **Vállalat** mező nem üres, és a **Vevő** mező beállítása **Nem**, és a **Szállító** mező beállítása is **Nem**.

## <a name="contact-for-party"></a>Fél kapcsolattartója

A **Fél kapcsolattartója** N:N kapcsolatokat tárol és kezel a **Partner** sorok és a **Kapcsolattartó** sorok között. Kiszűrheti a csíkozott **Kapcsolattartó** sorokat a nem csíkozott sorokból, és csak a nem csíkozott **Kapcsolattartó** sorokat társíthatja egy **Partner** vagy **Szállító** sorhoz.

Például Natasha Jones és Miguel Reyes állatorvosok, akik gondoskodnak a területük gazdaságáról. Natasha Seattle területen szolgál, míg Miguel Kent területen szolgál. Az ügyfélkapcsolati alkalmazásban a gazdaságok ügyfélként képviseltetik magukat, az állatorvosok pedig kapcsolattartók. Natasha egyetlen **Kapcsolattartó** rekordja kapcsolódik az összes farmhoz, ahol Natasha dolgozik. Hasonlóan Miguel egyetlen **Kapcsolattartó** rekordja kapcsolódik az összes farmhoz, ahol Miguel dolgozik.

Ezeket a kapcsolatokat a Partner a **Fél kapcsolattartója** tábla tárolja. Az információkat a gyári űrlapokon találja:

+ Amikor a **Partner** űrlapon van, van egy **Társított kapcsolattartók** nevű lap. Ezen a lapon egy vagy több kapcsolattartót társíthat a **Partner** sorhoz. Ezen az űrlapon egy kapcsolattartót rendel egy szervezethez. Miután hozzárendelt kapcsolattartókat, kiválaszthatja az egyiket az adott partner elsődleges kapcsolattartójaként. A **Gyors létrehozás** űrlapon csak kapcsolattartót választhat. A viselkedés ugyanaz, ha a **Szállító** képernyőt használja, és a rekord típusa **Szervezet**.
+ Amikor a **Kapcsolattartó** képernyőn van, és a sor vevő vagy szállító, vagy mindkettő (egy csíkozott ügyfél), van egy **Társított kapcsolattartók** nevű lap. Ezen a lapon egy vagy több kapcsolattartót társíthat. Ezen az űrlapon egy kapcsolattartót rendel a B2C ügyfélhez vagy szállítóhoz. Miután hozzárendelt kapcsolattartókat, kiválaszthatja az egyiket elsődleges kapcsolattartóként. A **Gyors létrehozás** űrlapon csak kapcsolattartót választhat.
+ Amikor a **Kapcsolattartó** űrlapon van, és a sor egy kapcsolattartó (egy nem csíkozott ügyfél), van egy **Társított szervezetek** nevű lap. Ezen a lapon egy vagy több ügyfelet vagy szállítót társíthat. Ezen az űrlapon egy ügyfelet vagy szállítót rendel a mögöttes kapcsolattartóhoz. A vevő vagy szállító lehet szervezet, személy vagy mindkettő. Egy adott időpontban csak egy értéket választhat a négy mezőből.

    ![Társított szervezetek lap](media/party-gab-image3.png)

    + Ha a **Fél azonosítója** lehetőséget választja, akkor az alapul szolgáló kapcsolattartó a kiválasztott fél összes szerepköréhez hozzá van rendelve.
    + Ha a **Társított kapcsolattartó** lehetőséget választja, akkor a személytípusú csíkozott kapcsolattartót választja.
    + Ha a **Társított partner** vagy a **Szállító** lehetőséget választja, akkor egy szervezetet választ.

    Az Ön választásától függetlenül a társítás a felek szintjén jön létre, és a fél összes szerepkörére vonatkozik, és a „Fél kapcsolattartója” entitásban tárolódik.

> [!Note]
> A **Fél kapcsolattartója** tábla megjelenítendő neve az ügyfélkapcsolati alkalmazásban **Ügyfél/szállító kapcsolattartója**.

Amikor megnyit egy **Kapcsolattartó** sort, ahol a **Vevő** értéke **Nem** a **Szállító** értéke **Nem**, a **Társított szervezetek** lap jelenik meg. Ezen a lapon egy vagy több vevő- vagy szállító szervezetet társíthat a kapcsolattartóhoz.

Amikor megnyit egy **Kapcsolattartó** sort, ahol a **Vevő** értéke **Igen** a **Szállító** értéke **Igen**, a **Társított kapcsolattartók** lap jelenik meg. Ezen a lapon egy vagy több kapcsolattartót társíthat.

## <a name="postal-address"></a>Postai cím

A **Partner**, **Kapcsolattartó** és **Szállító** űrlapokon egy **Címek** nevű új lap került bevezetésre. A **Címek** N címet támogat egy rács használatával, a képen látható módon:

![A postai címek rácsa](media/party-gab-image4.png)

+ A **Postacím szerepek** oszlop a cím célját sorolja fel.
+ Az **Elsődleges** oszlop felsorolja az elsődleges címet.
+ A **Cím száma** oszlop listázza a cím sorrendjét.
+ A **+ Új cím** gomb segítségével új címet hozhat létre. Tetszőleges számú címet lehet létrehozni.

A **Cím 1** és **Cím 2** mezők az **Összegzés** lapon a **Partner** űrlapon megfelelnek a **Szállítási** és **Számlázási** címeknek.

![A postai cím összegző lapja](media/party-gab-image5.png)

A **Cím 1**, **Cím 2** és **Cím 3** mezők az **Összegzés** lapon a **Kapcsolattartó** űrlapon megfelelnek a **Céges**, **Szállítási** és **Számlázási** címeknek.

## <a name="electronic-address"></a>E-mail cím

A **Partner**, **Kapcsolattartó** és **Szállító** űrlapokon egy új **Elektronikus címek** nevű új lap került bevezetésre. A **Címek** N címet támogat egy rács használatával, a képen látható módon:

![Az elektronikus címek rácsa](media/party-gab-image6.png)

+ A **Típus** oszlop felsorolja a cím típusát.
+ Az **Elsődleges** oszlop felsorolja az elsődleges címet.
+ A **Cél** oszlop az elektronikus cím célját sorolja fel.
+ A **+ Új elektronikus cím** gomb segítségével új címet hozhat létre. Tetszőleges számú címet lehet létrehozni.

Az elektronikus címek csak ezen a rácson érhetők el. A későbbi verziókban minden elektronikus és postai cím mező törlődik a többi lapról, például az **Összegzés** és **Részletek** lapról.

## <a name="setup-instructions"></a>Telepítési útmutató

Ha Ön már kettős írású ügyfél, a következő beállítási lépések szükségesek. Ellenkező esetben ezt a szakaszt kihagyhatja.

1. Állítsa le a következő leképezéseket, mert már nem szükségesek. Ehelyett futtassa a Kapcsolattartók V2 (msdyn_contactforparties) leképezést.

    + CDS Kapcsolattartók V2 és Kapcsolattartók (vevői kapcsolattartókra vonatkozik)
    + CDS Kapcsolattartók V2 és Kapcsolattartók (szállítói kapcsolattartókra vonatkozik)

2. A felek funkcióira vonatkozó következő entitásleképezések frissülnek, ezért a legújabb verziót kell alkalmazni ezekre a leképezésekre.

Megfeleltetés | Frissítés erre a verzióra | Változások
---|---|---
Vevők V3 .(partnerek) | 1.0.0.5 |Eltávolítottuk a PartyNumber mezőt és más, félhez kapcsolódó mezőket, például a nevet, a személyes adatokat, a postai címmezőket, az elektronikus kapcsolattartó címmezőit stb.
Ügyfél V3 (kapcsolattartók) | 1.0.0.5 | Eltávolítottuk a PartyNumber mezőt és más, félhez kapcsolódó mezőket, például a nevet, a személyes adatokat, a postai címmezőket, az elektronikus kapcsolattartó címmezőit stb.
Szállítók V2 (msdyn_vendors) | 1.0.0.6 | Eltávolítottuk a PartyNumber mezőt és más, félhez kapcsolódó mezőket, például a nevet, a személyes adatokat, a postai címmezőket, az elektronikus kapcsolattartó címmezőit stb.
CDS értékesítési ajánlat fejléce (quotes) | 1.0.0.6 | Kicseréltük a kapcsolattartö személyt a ContactforParty hivatkozásra.
Értékesítésiszámla-fejlécek V2 (számlák) | 1.0.0.4 | Kicseréltük a kapcsolattartö személyt a ContactforParty hivatkozásra.
CDS értékesítési rendelések fejlécei (salesorders) | 1.0.0.5 | Kicseréltük a kapcsolattartö személyt a ContactforParty hivatkozásra.
Kapcsolattartók V2 (msdyn_contactforparties) | 1.0.0.2 | Ez egy új leképezés. Ha a fél megoldásának már van egy korábbi verziója, ügyeljen arra, hogy a már említett legújabb verzióra frissítse ezt a leképezést.
CDS fél postai címének helyei (msdyn_partypostaladdresses) | 1.0.0.1  | Ez egy új leképezés, amely az előző fél előzetes verziójú kiadás részeként lett hozzáadva.
CDS postai címelőzmények V2 (msdyn_postaladdresses) | | Ez egy új leképezés, amely az előző fél előzetes verziójú kiadás részeként lett hozzáadva.
CDS fél postai címének helyei (msdyn_postaladdresscollections) | | Ez egy új leképezés, amely az előző fél előzetes verziójú kiadás részeként lett hozzáadva.
Fél kapcsolattartói V3 (msdyn_partyelectronicaddresses) | | Ez egy új leképezés, amely ezen kiadás részeként lett hozzáadva.

## <a name="templates"></a>Sablonok

Ahogy az alábbi táblázatban látható, az táblaleképezések gyűjteménye együttműködik a fél és globális címjegyzék interakciók során.

Finance and Operations alkalmazás | Customer Engagement alkalmazás     | Leírás
----------------------------|-----------------------------|------------
[Kapcsolattartó megszólításai](mapping-reference.md#223) | msdyn_salescontactpersontitles |
[Vevők V3](mapping-reference.md#101) | számlák |
[Vevők V3](mapping-reference.md#116) | kapcsolattartók |
[CDS-felek](mapping-reference.md#220) | msdyn_parties |
[CDS-fél postai címének helyei](mapping-reference.md#233) | msdyn_partypostaladdresses |
[CDS-fél postai címének előzményei V2](mapping-reference.md#235) | msdyn_postaladdresses |
[CDS postai címének helyei](mapping-reference.md#234) | msdyn_postaladdresscollections |
[CDS értékesítésiajánlat-fejléc](mapping-reference.md#215) | ajánlatok |
[CDS értékesítésirendelés-fejlécek](mapping-reference.md#217) | salesorders |
[Udvarias levélzárások](mapping-reference.md#222) | msdyn_complimentaryclosings |
[Kapcsolattartók V2](mapping-reference.md#221) | msdyn_contactforparties |
[Döntéshozatali szerepkörök](mapping-reference.md#224) | msdyn_decisionmakingroles |
[Foglalkoztatási beosztásfunkciók](mapping-reference.md#225) | msdyn_employmentjobfunctions |
[Hűségszintek](mapping-reference.md#226) | msdyn_loyaltylevels |
[Ügyfél-kapcsolattartók V3](mapping-reference.md#236) | msdyn_partyelectronicaddresses |
[Személyes karaktertípusok](mapping-reference.md#227) | msdyn_personalcharactertypes |
[Értékesítésiszámla-fejlécek V2](mapping-reference.md#118) | számlák |
[Üdvözlések](mapping-reference.md#228) | msdyn_salutations |
[Szállítók V2](mapping-reference.md#202) | msdyn_vendors |

További tájékoztatás: [Kettős írású leképezési hivatkozás](mapping-reference.md).
