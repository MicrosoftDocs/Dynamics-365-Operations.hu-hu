---
title: "Átfedő kedvezmények optimális kombinációjának meghatározása"
description: "Átfedő kedvezmények esetén meg kell határozni az egymást átfedő kedvezmények azon kombinációját, amely a legalacsonyabb tranzakciós végösszeget vagy a legnagyobb összes engedményt eredményezi. Ha az engedmény összege a vásárolt termékek ára szerint változik, például a kiskereskedelmben gyakori „1 vásárlása esetén 1 X százalék engedmény” esetén ez a folyamat kombinatorikai optimalizálási problémává válik."
author: kfend
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations, Retail
ms.custom: 89643
ms.assetid: 09843c9a-3e19-4e4a-a8ce-80650f2095f9
ms.search.region: global
ms.search.industry: Retail
ms.author: kfend
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: af31f0c4cb5304a213f883e3d076731f7cee468e
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="determine-the-optimal-combination-of-overlapping-discounts"></a>Átfedő kedvezmények optimális kombinációjának meghatározása

[!include[banner](includes/banner.md)]


Átfedő kedvezmények esetén meg kell határozni az egymást átfedő kedvezmények azon kombinációját, amely a legalacsonyabb tranzakciós végösszeget vagy a legnagyobb összes engedményt eredményezi. Ha az engedmény összege a vásárolt termékek ára szerint változik, például a kiskereskedelmben gyakori „1 vásárlása esetén 1 X százalék engedmény” esetén ez a folyamat kombinatorikai optimalizálási problémává válik.

Ez a cikk a Microsoft Dynamics AX 2012 R3 (KB 3105973-mal, kiadva 2015. november 2-án) vagy későbbi verzióira és a Microsoft Dynamics 365 for Retail kiadására vonatkozik. Az átfedő kedvezmények megfelelő kombinációjának időben történő meghatározásához bevezettünk egy, az átfedő kedvezmények alkalmazására szolgáló módszer. Ezen új módszernek a **marginálisérték-rangsorolás** nevet adtuk. A marginálisérték-rangsorolást használjuk, valahányszor az egymást átfedő kedvezmények lehetséges kombinációinak kiértékeléséhez szükséges idő átlépi azt a küszöbértéket, amely a **Kiskereskedelmi paraméterek** oldalán konfigurálható. A marginálisérték-rangsorolási módszerben minden átfedő engedménynél kiszámítunk egy értéket az engedmény a megosztott termékekre jutó értéke alapján. Az átfedő kedvezményeket ezután a legmagasabb relatív értéktől a legalacsonyabb relatív értékig alkalmazzuk. Az új módszer részleteit a „Marginális érték” részben találja a cikk későbbi részében. A marginálisérték-rangsorolást nem használjuk, egy termék engedményének összegét a tranzakció másik terméke nem befolyásolja. Például ezt a módszer nem használjuk két egyszerű engedmény esetén, sem egy egyszerű és egy termékalapú mennyiségi engedmény esetén.

## <a name="discount-examples"></a>Példák engedményre
Korlátlan számban hozhat létre kiskereskedelmi engedményeket közös csoportba sorolt termékekre vonatkozóan. Azonban mivel korlátozás nincsen, teljesítményproblémák merülhetnek fel, amikor megkísérli kiszámítani a különböző termékekre alkalmazott kedvezményeket. A következő példák részletesen mutatják be ezt a problémát. Az 1. példában két termékkel és két egymást átfedő kedvezménnyel indítunk. Ezt követően a 2. a példában megmutatjuk, hogyan alakul a probléma további termékek hozzáadásával.

### <a name="example-1-two-products-and-two-discounts"></a>1. példa: Két termék és két engedmény

Ebben a példában két termékre van szükség az egyes kedvezmények elnyerése érdekében, és a kedvezmények nem kombinálhatók. A példában szereplő engedmények **Legjobb ár** típusú engedmények. Mindkét termék mindkét engedményre jogosult. Az alábbiakban látható a két engedmény.
![Átfedő engedménykombináció 01](./media/overlapping-discount-combo-01.jpg)

Bármely két termékre e két engedmény közül a jobb a nagyobb termék árától függ. Ha mindkét termék ára azonos vagy közel azonos, az 1. engedmény a jobb. Ha az egyik termék ára jelentősen kisebb, mint a másik termék ára, a 2. engedmény a jobb. Íme a két engedmény egymással szembeni értékelésére szolgáló matematikai szabály: ![Átfedő engedménykombináció 02](./media/overlapping-discount-combo-02.jpg)

**Megjegyzés:** Ha az 1. termék ára megegyezik a 2. termék árának kétharmadval, a két engedmény egyenlő. Ebben a példában az 1. engedménynél a tényleges engedmény százaléka változik a néhány százalék (amikor a két termék ára messze esik egymástól) és a legfeljebb 25% között (amikor a két termék ára azonos). A tényleges engedmény százaléka a 2. engedmény esetén fix. Mindig 20 százalék. Mivel az 1. engedmény tényleges százaléka olyan tartományba esik, amely több vagy kevesebb is lehet, mint a 2. engedmény, az, hogy melyik a legjobb kedvezmény, a két diszkontálandó termék árától függ. Ebben a példában a számítás gyorsan befejeződött, mert csak két engedményt alkalmaztunk mindössze két termékre. Csak két lehetséges kombináció létezik: az 1. engedmény egy alkalmazása vagy a 2. engedmény egy alkalmazása. Nincsenek kiszámítandó permutációk. Minden engedmény értéke kiszámításra kerül mindkét termék használatával, és a rendszer a legjobb kedvezményt használja.

### <a name="example-2-four-products-and-two-discounts"></a>2. példa: Négy termék és két engedmény

Ezután négy terméket fogunk használni és ugyanazon két engedményt. Mind a négy termék mindkét engedményre jogosult. Itt tizenkét lehetséges kombináció létezik. Végezetül két engedményt alkalmazunk a tranzakcióra három kombináció valamelyikében: az 1. engedmény két alkalmazása, a 2. engedmény két alkalmazása vagy az 1. engedmény két alkalmazása és a 2. engedmény egy alkalmazása. A lehetséges kombinációk bemutatására négy más-más árú termékből álló két termékcsomagra vetünk közelebbi pillantást:

-   Mind a négy termék ára ugyanaz, 15,00 USD. Ebben az esetben a legjobb engedménykombináció az 1. engedmény két alkalmazása. Két termék teljes áron kerül eladásra, kettő pedig 50 százalékon. A tranzakció diszkontált összértéke 45 USD (15 + 15 + 7,50 + 7,50), amely 15 USD (25 százalék) kedvezményt jelent a teljes, nem diszkontált 60 USD-s összegből. A 2. kedvezmény csak 12 USD (20 százalék).
-   Két termék egyenként 20 USD, egy termék 15 USD, egy termék pedig 5 USD. Ebben az esetben a legjobb engedménykombináció a 2. engedmény egy alkalmazása és az 1. engedmény egy alkalmazása. A következő táblázatok az engedményeket mutatják be.

A táblák olvasásához vegyen egy terméket egy sorból és egy terméket egy oszlopból. Például az 1. engedmény táblájában két 20 USD-s terméket kombinálva 10 USD kedvezményt kapunk. A 2. engedmény táblájában a 15 USD-s és az 5 USD-s terméket kombinálva 4 USD kedvezményt kapunk.
![Átfedő engedménykombináció 03](./media/overlapping-discount-combo-03.jpg)

Először megkeressük a legnagyobb engedményt, amely valamelyik engedmény használatával két termékre csak elérhető. A két tábla a két termék összes kombinációjához mutatja az engedmény összegét. A táblák árnyékolt részekkel képviselik azokat az eseteket, amikor egy termék önmagával lenne párosítva, ami nem lehetséges, illetve a fordított párosításokat, amelyeknél ugyanazt az engedményösszeget kapjuk, tehát ezek figyelmen kívül hagyhatók. A táblákat megnézve látható, hogy az 1. engedmény a két 20 USD-s tételre a legnagyobb kedvezmény, aminél egyik engedményt a négy termék bármelyikére alkalmazva sem kapunk nagyobbat. (Ezt az engedményt az első tábla zölddel emeli ki.) Így csak a 15 USD-s és az 5 USD-s termék marad. Ha ismét megnézzük a két táblát, láthatja, hogy e két termékre vonatkozóan az 1. engedmény 2,50 USD kedvezményt ad, a 2. engedmény pedig 4 USD kedvezményt. Ezért a 2. engedményt választjuk. A teljes engedmény 14 USD. E gondolatmenet egyszerűbb megjelenítéséhez az alábbiakban két további táblát talál, amelyek minden lehetséges kéttermékes kombinációra megmutatják a tényleges engedmény százalékát mind az 1. engedménynél, mind a 2. engedménynél. Csak a kombinációk listájának fele látható, mivel e két engedménynél nem számít a sorrend, amelyben a két terméket beleszámítjuk az engedménybe. A legmagasabb tényleges engedmény (25 százalék) ki van emelve zölddel, a legalacsonyabb tényleges engedmény (10 százalék) pedig pirossal. 

![Átfedő engedménykombináció 04](./media/overlapping-discount-combo-04.jpg)

**Megjegyzés:** amikor az árak változnak, és két vagy több engedmény verseng egymással, csak úgy lehet garantálni a kedvezmények optimális kombinációjának biztosítását, hogy mindkét engedményt kiértékeljük és összehasonlítjuk.

## <a name="total-possible-combinations"></a>Összes lehetséges kombináció
Ez a szakasz az előzőekben látott példát folytatja. További termékeket és egy másik engedményt adunk hozzá, és megnézzük, hány kombinációt kell kiszámítani és összevetni. Az alábbi táblázat mutatja a lehetséges engedménykombinációk számát, ahogy a termékmennyiség növekszik. A tábla azt mutatja, mi történik, ha két egymást átfedő kedvezmény van jelen, miként az előző példában, illetve ha egymást átfedő kedvezmény van jelen. A lehetséges engedménykombinációk száma, amit értékelni kell, gyorsan meghaladja azt a mértéket, amit akár egy a gyors számítógép is képes elég gyorsan kiszámítani és összehasonlíthatani ahhoz, hogy az kiskereskedelmi tranzakcióknál elfogadható legyen.

![Átfedő engedménykombináció 05](./media/overlapping-discount-combo-05.jpg)

Amikor még nagyobb mennyiségeket vagy több egymást átfedő engedményt alkalmazunk, a lehetséges engedménykombinációk száma hamarosan eléri a milliós nagyságrendet, és a kiértékelésükhöz és a legjobb kiválasztásához szükséges idő hamarosan észrevehetővé válik. A kiskereskedelmi ármotorban optimalizálást végeztünk a kiértékelendő kombinációk teljes számának csökkentésére. Azonban mivel az átfedő kedvezmények és a tranzakcióban részt vevő mennyiségek száma nem korlátozott, mindig sok kombinációt kell kiértékelni, valahányszor egymást átfedő kedvezményekkel számolunk. A marginálisérték-rangsorolás erre a problémára kínál megoldást.

## <a name="marginal-value-method"></a>Marginálisérték-módszer
Az exponenciálisan növekvő számú, kiértékelendő kombináció problémájának megoldása érdekében létezik egy optimalizálás, amely minden termékcsoportnál, amelyre két vagy több engedmény alkalmazható, az értéket minden engedménynél megosztott termékenként számítja ki. Ezt az értéket a megosztott termékek kedvezménye **marginális értékének** hívjuk. A marginális érték a kedvezmény értékének azon termékenkénti átlagos növekedése, amelyet akkor kapunk, ha a megosztott termékeket minden engedménybe belefoglaljuk. A marginális értéket úgy számítjuk ki, hogy vesszük az összengedmény összegét (DTotal), kivonjuk belőle a megosztott termékek nélküli engedmény összegét (DMinus\\ Megosztott), és ez a különbséget elosztjuk a megosztott termékek (ProductsShared) számával. 
![Átfedő engedménykombináció 06](./media/overlapping-discount-combo-06.jpg)

Miután a megosztott termékcsoport minden egyes kedvezményének marginális értékét kiszámítottuk, az összes kedvezményt sorrendben alkalmazzuk a megosztott termékekre a legmagasabb marginális értéktől a legalacsonyabbig. Ennél a módszernél nem hasonlítjuk össze az összes fennmaradó engedménylehetőséget, valahányszor alkalmaztuk egy kedvezmény egy példányát. Ehelyett az egymást átfedő kedvezményeket egyszer összehasonlítjuk, majd pedig sorrendben alkalmazzuk. További összehasonlításokra nem kerül sor. A küszöbérték, amelynél a rendszer a marginálisérték-módszerre vált, a **Kiskereskedelmi paraméterek** oldal **Engedmény** lapján állítható be. Az összengedmény kiszámítására felhasznált elfogadható idő hossza kiskereskedelmi iparáganként változik. Az idő általában viszont a tized ezredmásodpercek és az egy másodperc közti tartományba esik.




