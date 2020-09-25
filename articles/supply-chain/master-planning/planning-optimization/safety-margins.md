---
title: Biztonsági határok
description: Ez a témakör azt mutatja be, hogyan használhatók a biztonsági időtartalékok a Microsoft Dynamics 365 Supply Chain Management Tervezési optimalizálás bővítményében.
author: ChristianRytt
manager: tfehr
ms.date: 09/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-9-14
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 05ac817081689f27cdf55cb86a3235d7707a737b
ms.sourcegitcommit: 5bb36b74935ffe140367fd6ecf956b4857ad12e5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/14/2020
ms.locfileid: "3803421"
---
# <a name="safety-margins"></a>Biztonsági határok

[!include [banner](../../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan használhatók a biztonsági időtartalékok a Microsoft Dynamics 365 Supply Chain Management Tervezési optimalizálás bővítményében.

## <a name="safety-margins-overview"></a>Biztonsági időtartalékok – áttekintés

A biztonsági időtartalékok célja az, hogy lehetővé tegyenek egy olyan beállítást, amely a normál átfutási idő után némi pufferidőt biztosít. Ha például az anyagot ki kell csomagolni vagy meg kell vizsgálni, miután megérkezik a szállítótól, nem teheti azt, hogy egyszerűen hozzáad extra időt a beszerzés átfutási idejéhez, mivel ezzel további pufferidőt ad a beszállítóhoz. Ebben a példában a bevételezés időtartaléka használható annak biztosítására, hogy a szállító korábban szállítson. Ez a módszer a pufferidőt biztosít, hogy az árukat belül kezelni lehessen.

Háromféle biztonsági időtartalék van:

- **Újrarendelési időtartalék** – A beszerzési rendelés leadásának pufferideje
- **Bevételezési időtartalék** – A bejövő szállítás kezeléséhez tartozó pufferidő
- **Kiadási időtartalék** – A szállítmányok kezelésének pufferideje

A következő ábra bemutatja a biztonsági időtartalékok időbeli hatályát.

![Biztonsági határok](media/safety-margins-1.png)

Minden időtartalék napokban van meghatározva. Az alapértelmezett érték a *0* (nulla), ami azt jelzi, hogy nincs időtartalék alkalmazva. Ha több időtartalékot hoz létre, ezek mind hozzá lesznek adva a teljes időhöz az ellátási *rendelési dátum* és az igény *követelménydátuma* között. Például a beállításnak nincs átfutási ideje, és mindhárom időtartalék-típus egy napra van állítva. Ebben az esetben az ellátási rendelés dátuma és a szükségleti követelmény dátuma között három nap lesz, így ha a rendelési dátum július 1. a követelmény dátuma július 4.

### <a name="receipt-margin"></a>Bevételezési időtartalék

A bevételezési időtartalék a három biztonsági időtartalékból valószínűleg a leggyakrabban használt. A *szállítási dátumra* van alkalmazva a és a *szükséglet dátumától* visszaszámolva. Más szóval, a termékeket meg kell kapniuk a megadott számú bevételezési időtartalék napjaival a szükséglet előtt.

A következő ábrán ki van emelve e bevételezési időtartalék.

![Bevételezési időtartalék](media/safety-margins-2.png)

A bevételezési időtartalék általában pufferként használatos, hogy legyen elegendő idő a raktári regisztrációhoz vagy más időigényes folyamatokhoz, amelyek nincsenek rögzítve az általános átfutási időhöz a rendszerben. A beszerzések esetében az egyik előny az, hogy a beszerzési rendelés *szállítási dátuma* ennek megfelelően áthelyeződik. Ha az átfutási időt növeli a biztonsági időtartalék használata helyett, akkor a szállítónak továbbra is az utolsó pillanatban szükséges szállítania.

Figyelje meg, hogy a bevételezési időtartalék nem módosítja a kellék *szükségleti dátumát*. Ennélfogva a bevételezési időtartalék nem látható közvetlenül, amikor az igény és az ellátás követelménydátumai össze vannak hasonlítva (például a **Nettó igények** oldalon). Ha például a bevételezési időtartalék négy napos, és a beszerzési rendelés sora a hónap tizenötödik napjára van tervezve, akkor az mestertervezés a helyesbített bevételezést a hónap tizenkilencedik napjára számítja.

Ne felejtse el, hogy a rendszer nem alkalmazza a bevételezési időtartalékot, amikor az aktuális készletet használja a program. Minden aktuális készletet azonnal elérhetővé kell tennie a tényleges kézhezvételtől függetlenül.

### <a name="reorder-margin"></a>Újrarendelési időtartalék

> [!NOTE]
> **Hamarosan:** Ez a funkció még nem támogatott a Tervezési optimalizálásban. A támogatásig minden olyan értéket, amelyet az **Újrarendelési időtartalék hozzáadva a cikkátfutási időhöz** mezőben adnak meg *0* (nulla) értékként van kezelve.

A következő ábrán ki van emelve az újrarendelési időtartalék.

![Újrarendelési időtartalék](media/safety-margins-3.png)

Az újrarendelési időtartalék a program az alaptervezés során az összes tervezett rendeléshez tartozó átfutási idő elé adja hozzá. Ennek megfelelően további időt biztosít az ellátási rendelés leadására. Ez a tartalék általában pufferként használatos az ellátási rendelések létrehozása során szükséges jóváhagyási folyamatok és egyéb belső folyamatok céljából. Az újrarendelési időtartalék az *ellátási rendelés dátuma* és a *kezdő dátum* közé lesz elhelyezve.

### <a name="issue-margin"></a>Kiadási időtartalék

> [!NOTE]
> **Hamarosan:** Ez a funkció még nem támogatott a Tervezési optimalizálásban. A támogatásig minden olyan értéket, amelyet az **Követelmény dátumából levont kiadási időtartalék** mezőben adnak meg *0* (nulla) értékként van kezelve.

A következő ábrán ki van emelve az kiadási időtartalék.

![Kiadási időtartalék](media/safety-margins-4.png)

A kiadási időtartalék a mestertervezés során le lesz vonva az igény követelménydátumából. Segít abban, hogy ideje legyen a bejövő igény szerinti rendelésekre reagálni és leszállítani azokat. Ez az időtartalék általában pufferként használatos idő biztosításához szállításhoz és a kapcsolódó kimenő raktári folyamatokhoz.

Figyelje meg, hogy a kiadási időtartalék alkalmazása esetén a kapcsolódó beszállítás és igény szükségletek dátuma nem egyezik meg. Helyette a kibocsátási időtartalékkal eltérnek mivel a kiadási időtartalék hozzá van adva az ellátás *követelménydátuma* és az igény *követelménydátum* közé.

## <a name="set-up-safety-margins"></a>Biztonsági időtartalékok beállítása

### <a name="turn-on-safety-margins-in-feature-management"></a>A biztonsági időtartalékok bekapcsolása a Funkciókezelés modulban

Mielőtt használhatná ezt a funkciót a Tervezési optimalizálásában, be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a [Funkciókezelés](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview) munkaterületet a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A funkció a következő módon jelenik meg:

- **Modul:** _Alaptervezés modul_
- **Funkció neve:** _Időtartalékok tervezési optimalizáláshoz_

### <a name="define-safety-margins"></a>Biztonsági időtartalékok definiálása

A biztonsági időtartalékok rugalmas beállítással rendelkeznek. Ezek mind *fedezeticsoport*, mind az *alaptervezés* szintjén beállíthatók. Fontos, hogy megértse, hogy a különbözeteket a program egymáshoz adja. Például egy 2 napos bevételezési időtartalék a fedezetcsoportban, illetve három nap az alaptervezésben öt napos bevételezési időtartalékot eredményez.

Az alaptervben történő biztonsági tartalék beállításának lehetősége akkor lehet hasznos, ha egy adott tervhez hosszabb átfutási időt vagy bizonytalanságot szeretne szimulálni, úgy, hogy nem befolyásolja a napi tervezést.

#### <a name="coverage-group-safety-margins"></a>Fedezetcsoportok biztonsági tartalékai

Ha a biztonsági tartalékot egy fedezeti csoportra szeretné alkalmazni, hajtsa végre az alábbi lépéseket.

1. Manjen az **Alaptervezés \> Beállítás \> Fedezetcsoportok** menübe.
1. A lista ablaktáblán válassza ki a kívánt fedezeti csoportot.
1. Az **Egyéb** gyorslapon a **Biztonsági időtartalék napban** szakaszban a következő mezőkkel állíthatja be a szükséges biztonsági időtartalékokat (napokban):

    - Követelmény dátumához hozzáadott bevételezési időtartalék
    - Követelmény dátumából levont kiadási időtartalék
    - Újrarendelési időtartalék hozzáadva a cikkátfutási időhöz

#### <a name="master-plan-safety-margins"></a>Alaptervek biztonsági időtartalékai

Ha a biztonsági tartalékot egy alaptervre szeretné alkalmazni, hajtsa végre az alábbi lépéseket.

1. Válassz az **Alaptervezés \> Beállítás \> Tervek \> Alaptervezések** lehetőséget.
1. A lista ablaktáblán válassza ki a kívánt alaptervet.
1. A **Biztonsági időtartalék napban** gyorslapon a következő mezőkkel állíthatja be a szükséges biztonsági időtartalékokat (napokban):

    - Követelmény dátumához hozzáadott bevételezési időtartalék
    - Követelmény dátumából levont kiadási időtartalék
    - Újrarendelési időtartalék hozzáadva a cikkátfutási időhöz

### <a name="define-whether-calculations-are-based-on-calendar-days-or-work-days"></a>Annak megadása, hogy a számítások naptári napokon vagy munkanapokon alapuljanak-e

Az összes biztonsági időtartalékot beállíthatja úgy, hogy a naptári napok vagy munkanapok alapján legyen számítva.

1. Ugorjon az **Alaptervezés \> Beállítás \> Alaptervezés paraméterei** pontra.
1. Az **Általános** lap **Biztonsági időtartalék napban** szakaszában állítsa a **Munkanapok** beállítását *Igen* értékre, hogy a munkanapok alapján számítsa ki a tartalékot. A *Nem* értékre állítása esetén naptári napok alapján számítja ki a különbözetet.

Például egy naptár hétfőtől péntekig van nyitva, szombaton pedig vasárnapig zárva. Ha egy nap bevételezési időtartalék van, akkor egy hétfőn a követelmény előző hét pénteki szállítási dátumot hoz létre, mivel a szombat és a vasárnap nem munkanap.

A munkanapok meghatározásához használt naptár a beállítástól és az ellátási típustól függ. A fedezeti csoport, a raktár és a szállító naptárai vezérelhetik.

> [!NOTE]
> Ha a *raktár* nem része a fedezeti dimenziónak (más szóval a tervezés csak a *helyszínen* alapul ), akkor a program nem használja a raktári naptárat.

A rendszer olyan beállítást is tud kezelni, ahol egy vagy több naptár van beállítva. A következő alszakaszokban a lehetséges kombinációk leírása található, amelyek az eredmények szabályzására használhatók.

#### <a name="calendar-that-is-used-for-the-duration"></a>Az időtartamhoz használt naptár

A definiált naptárak a tényleges teljes átfutási időt naptári napokban vezérlik, az ellátási rendelés dátumától a szükségleti követelmény dátumáig. A következő naptár-prioritás használatos:

- **Beszerzési átfutási ideje** – Csak a fedezeti csoport naptárát veszi figyelembe a rendszer.
- **Bevételezési időtartalék** – A fedezeti csoport naptárát használja a rendszer, ha az meg van határozva. Más esetben a raktár naptárát használja.
- **Kiadási időtartalék** – A fedezeti csoport naptárát használja a rendszer, ha az meg van határozva. Más esetben a raktár naptárát használja.
- **Rendelési időtartalék** – Csak a fedezeti csoport naptárát veszi figyelembe a rendszer.

#### <a name="calendar-that-is-used-for-the-final-date"></a>A végső dátumhoz használt naptár

A következő szabályok érvényesek annak meghatározására, hogy a tervezési motor egy adott dátumtípusra vonatkozóan használhatja-e a megadott dátumot:

- **Beszerzési kézhezvételi dátuma** – a program a szállítói naptárat használja, ha az meg van határozva. Máskülönben a fedezeti csoport naptárát használja a rendszer, ha az meg van határozva. Ha egyik naptár sincs definiálva, akkor a program a raktári naptárat használja.
- **Átmozgatás bevételezési dátuma** – A fedezeti csoport naptárát használja a rendszer, ha az meg van határozva. Más esetben a raktár naptárát használja.
- **Termelés bevételezési dátuma** – A fedezeti csoport naptárát használja a rendszer, ha az meg van határozva. Más esetben a raktár naptárát használja.
- **Igény kiadásának nyitónapja** – A raktár naptárát használja a rendszer, ha az meg van határozva. Máskülönben a fedezeti csoport naptárát használja a rendszer.
- **Rendelés nyitónapja** – A fedezeti csoport naptárának és a szállítói naptárnak a kombinációja (metszéspontja) használatos. A dátum használatához mindkét naptárnak nyitva kell lennie. Ha csak az egyik naptár van definiálva, akkor a program csak azt a naptárat használja.

#### <a name="calendar-setup-overview-matrix"></a>Naptár-beállítás áttekintése – mátrix

A következő ábra bemutatja azt a mátrixot, amely összegzi a biztonsági időtartalékok kiszámításakor alkalmazott naptárakat. A következő rövidítések és színek azt jelzik, hogy hol vannak meghatározva az egyes naptár-típusok:

- **Fedezeti csoport (CG):** Zöld
- **Raktár (WH):** sárga
- **Szállító (V):** kék

![Naptár-beállítás áttekintése – mátrix](media/safety-margins-calendar-matrix.png)

## <a name="calculating-delays"></a>Késések számítása

A biztonsági időtartalékok mindhárom típusa számításba van véve, amikor a rendszer meghatározza, hogy a rendelés késik-e.

Például egy cikkek átfutási ideje egy nap és a bevételezési időtartalék három nap. Ehhez a tételhez egy értékesítési rendelés ma szükséges. Ebben az esetben a késés kiszámítása: *átfutási idő* + *bevételezési időtartalék* = négy nap. Ha tehát a mai dátum augusztus 14, akkor a négy nap késés augusztus 18-ára helyezi a szállítást. A következő ábrán ez a példa látható.

![Késésszámítási példa](media/safety-margins-delays.png)

## <a name="additional-resources"></a>További erőforrások

[Tervezési optimalizálás kezdő lépései](get-started.md)

[Tervezési optimalizálás igazítási elemzése](planning-optimization-fit-analysis.md)
