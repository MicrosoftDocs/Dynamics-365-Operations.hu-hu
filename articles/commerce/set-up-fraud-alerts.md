---
title: Hívásközpontban jelentkező csalás-ellenőrzési figyelmeztetések beállítása és használata
description: Ez a témakör ismerteti a szabályok beállítását az ügyfélszolgálati munkatársak figyelmeztetésére az esetleg csaló információról a rendelések feldolgozása során. Meghatározhat specifikus kódokat, amelyek arra szolgálnak, hogy automatikusan vagy manuálisan várakoztassák a gyanús rendeléseket.
author: josaw1
ms.date: 05/14/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SalesPostingHistory, MCRHoldCodeTrans
audience: Application User
ms.reviewer: josaw
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: e692d43b8c2648a424ff3b4fdc9d0cf16d0e03702d6a237f71caaf49646c5ec3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6763668"
---
# <a name="set-up-and-work-with-call-center-fraud-alerts"></a>Hívásközpontban jelentkező csalás-ellenőrzési figyelmeztetések beállítása és használata

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet kritériumokat és szabályokat létrehozni a potenciálisan csaló értékesítési megrendelések várakoztatására további ellenőrzés céljából. A csalásellenőrzési funkció meghatározza az információ érvényességét egy értékesítési megbízásban. Ha az értékesítési rendelésben szereplő információk a szervezet csalási kritériumai és szabályai alapján megkérdőjelezhetőnek tűnnek, akkor a megrendelést várakoztatni lehet további ellenőrzés céljából. Ebben az esetben a rendelés nem adható ki a raktárba további feldolgozásra a várakoztatott törléséig.

> [!NOTE]
> Ez a funkció csak a Commerce hívásközpont csatorna értékesítési rendeléseinek feldolgozására használható.

## <a name="turning-on-the-fraud-check-feature"></a>A csalásellenőrző funkció bekapcsolása

A csalásellenőrzési funkció használatához a csatorna **Rendeléskiegészítés engedélyezése** opcióját **Igenre** kell állítania, amikor a hívásközpont [meghatározása:](/dynamics365/unified-operations/retail/set-up-order-processing-options). Amikor a rendelésteljesítés be van kapcsolva, a hívásközpont felhasználóinak ki kell választania a **Kész** lehetőséget az értékesítési rendelés lapján, minden létrehozott értékesítési rendeléshez. A Kész művelet eredményeképpen megnyílik az **Értékesítési rendelés összesítése** lap. Miután a felhasználók megadták a szükséges fizetési adatokat az **Értékesítési rendelés összesítése** lapon, kiválasztják a **Küldés** lehetőséget a rendelés véglegesítéséhez. A rendelés elküldésekor elindul a csalásellenőrzés funkció, és a rendszer esetleges szabályai automatikusan érvényesítésre kerülnek.

A hívásközpont felhasználói manuálisan is visszatarthatnak értékesítési rendeléseket csalásellenőrzésre, mielőtt kiválasztják a **Küldést**. Ahhoz, hogy manuálisan várakoztassanak egy értékesítési rendelést az **Értékesítési rendelés összesítése** oldalon, válassza a **Tartás**\>**Manuális csalási várakoztatás** lehetőséget. Felugrik egy ablak, hogy megjegyzés beírásával megindokolja, miért várakoztatja a rendelést. Ez a megjegyzés fog meg fog jelenni a [várakoztatott rendelések](/dynamics365/unified-operations/retail/work-with-order-holds) munkaterületen, hogy tájékoztassa azt a felhasználót, aki ellenőrzi a várakoztatott rendeléseket, és megállapítja, hogy a rendelés kiadható-e.

A **Rendelés teljesítésének engedélyezése** opció konfigurálásán túlmenően a csalásellenőrzési funkciót a hívásközpont paraméterei között is konfigurálnia kell. Lépjen ide: **Retail és Commerce**\>**Csatorna beállításai**\>**Hívásközponti beállítása**\>**Hívásközponti paraméterei**. A **Hívásközponti paraméterei** oldalon, a **Várakoztatás** lapon állítsa a **Csalásellenőrzés** opciót **Igenre**.

A **Várakoztatás** lapon meg kell adnia azokat a [várakoztatási kódokat is](/dynamics365/unified-operations/retail/work-with-order-holds), amelyek olyan rendelésekre vonatkoznak, amelyeket manuálisan vagy automatikusan várakoztatnak csalás ellenőrzésére. Állítsa be a várakoztatási kódokat a **Csalás manuális várakoztatási kódja** és a **Csalás várakoztatási kód** mezőben. Érdemes két egyedi várakoztatási kódot létrehozni, hogy a várakoztatási munkaterületen dolgozó felhasználók könnyen szűrhessék és megkülönböztethessék az automatikus várakoztatásokat a manuális várakoztatásoktól.

A csalásellenőrzési funkció hatékony működéséhez be kell állítania a **Minimális pontszám** mezőt is. A rendszerben meghatározott, mindegyik csalási feltételhez és a szabályhoz tartozik egy pontszám. Amikor egy értékesítési rendelést csalás szempontjából ellenőriznek, és az egy vagy több találatot eredményez, akkor a pontszámok összeadódnak, és kijön a teljes csalási pontszám. Ha a teljes csalási pontszám értéke meghaladja a **Minimális pontszám** mezőben megadott értéket, a rendelés el automatikusan várakoztatásra kerül. Tetszés szerint használhatja a pontszámhoz kapcsolódó többi mezőt is a **Várakoztatás** fülön, és meghatározhat pontszámot e-mail címhez, telefonszámhoz és postai irányítószámhoz. Ha nem ad meg pontszámot egyik ilyen statikus csalási feltételhez sem, amikor meghatározza ezeket a **Statikus csalási adatok** oldalon, a rendszer hozzájuk rendeli a pontszámokat azon alapértelmezett pontszámok segítségével, amelyeket Ön a **Várakoztatás** lapon, a **Hívásközponti paraméterek** oldalon megadott.

Végül a **Csalási megjegyzés típusa** mező bejelölésével megadhatja azt a dokumentumtípust, amelyet akkor kell használni, amikor a felhasználók megjegyzéseket írnak be, amikor egy rendelést manuálisan várakoztatnak csalás ellenőrzésére. Ennek a mezőnek az értéke leggyakrabban **Megjegyzés**.

## <a name="defining-fraud-criteria-and-rules"></a>Csalási feltételek és szabályok meghatározása

A rendszer kétfajta csalási kritériumot különböztet meg annak megállapításához, hogy egy rendelést várakoztasson-e csalás ellenőrzéséhez:

- **Statikus csalási adatok** meghatározott értékeket használ, például olyan telefonszámot, amely szerepel a zárolt számok listáján vagy olyan e-mail címet, amelyet megjelöltek, mert korábban azt csalási műveletekhez használták. A statikus csalási adatok beállításához lépjen ide: **Retail és Commerce**\>**Csatorna beállításai**\>**Hívásközpont beállítása**\>**Csalás**\>**Statikus csalási adatok**. A **Statikus csalási adatok** lapon manuálisan, illetve adatok importálásával adhat meg csalási feltételeket. A csalási információkhoz pontszámok vannak hozzárendelve. Ha a csalásellenőrzési funkció be van kapcsolva, minden bevitt értékesítési rendelés összehasonlításra kerül a statikus adatokkal. Ha az adatok megtalálhatók a vevő számlázási címében vagy a rendelési fejléchez kapcsolódó szállítási címben, vagy ha az adatok megtalálhatók abban a szállítási címben, amely az adott értékesítési rendelés bármelyik sorához kapcsolódik, akkor mindegyik egyedi találat összeadódik, és azt a rendszer összehasonlítja a **Minimális pontszám** értékével, és meghatározza, hogy a rendelést kell-e várakoztatni.

- A **Csalási szabályok** a felhasználó által definiált változókból állnak, és az ezekhez a változókhoz meghatározott feltételekből. Szabályok létrehozásához lépjen ide: **Retail és Commerce**\>**Csatorna beállítása**\>**Hívásközpont beállítása**\>**Csalás**\>**Szabályok**. A csalási szabályok segítségével a vállalat egy összetettebb szabályt állíthat be, amelyek tartalmazhatnak **ÉS** vagy **VAGY** lehetőségeket több feltétel kiértékeléséhez. Például egy felhasználó csalásellenőrzési várakoztatást akar kérni minden megrendelésre olyan vevők esetében, akik egy adott vevői csoporthoz tartoznak, és akik egy adott terméket rendeltek. Ebben az esetben a vevők és a termékek ellenőrzésére szolgáló feltételek meghatározása a **Szabályok** oldalon történik és az "ÉS" feltétel kerül alkalmazásra. A rendelés akkor kerül várakoztatott állapotba, ha mindkét feltétel teljesül, és ha a szabályhoz rendelt pontszám, valamint minden egyéb szabály alapján elért pontszám miatt a rendelés összesített csalási pontszáma meghaladja a **Minimális pontszám** értékét, amely a **Hívásközpont paraméterei** oldalon van meghatározva.

> [!NOTE]
> Több szabály vagy túlságosan bonyolult szabályok használata hatással lehet a rendszer teljesítményére, amikor benyújtják az értékesítési rendeléseket. A csalásellenőrési funkció nem lett optimalizálva, hogy nagy mennyiségű statikus csalási adatbevitelt és sok aktív szabályt kezeljen. Ne feledje, hogy minden szabály értékelésére sor kerül, amikor a hívásközpont felhasználói kiválasztják a **Küldés** lehetőséget értékesítési rendelésbevitel során. A szabályokat összevetjük az értékesítési rendelés fejlécével és az összes rendelési sorral. Minél több szabály létezik, és minél bonyolultabbak a szabályok, annál hosszabb időt vesz igénybe a feldolgozási folyamat. Ha sok sor van a rendelésében, és sok aktív szabályt és statikus adatbevitelt tartalmaz a rendelés, az összes adat ellenőrzésének és érvényesítésének automatikus folyamata és a csalás pontszámának számítása negatív hatással lehet a teljesítményre. A jelen funkciót használó szervezeteknek mindig meg kell győződniük és ellenőrizniük kell, hogy a rendelés beküldésének feldolgozási ideje elfogadható a szabályok vagy a statikus csalás kritériumainak a termelési környezetbe történő alkalmazása előtt.

## <a name="identifying-orders-that-are-on-hold-for-fraud-review"></a>Csalásellenőrzés miatt várakoztatott rendelések azonosítása

Amikor a hívásközpont felhasználói elküldenek egy értékesítési rendelést, és ha a rendelés megfelel a csalási feltételeknek vagy szabályoknak, és ha a pontszám meghaladja a minimális értéket, a felhasználók figyelmeztetést kapnak, amely szerint a rendelés várakoztatott állapotba került. A felhasználók bezárhatják ezt az üzenetet, mert ez csak tájékoztatási célt szolgál. A felhasználók úgy is dönthetnek, hogy ezt az információt továbbítják a vevőnek. Az üzletnek meg kell határoznia, hogy a felhasználók milyen protokoll szerint járjanak el ebben a helyzetben.

A rendelést menti a rendszer, de megjelöli a következőként: **Feldolgozni tilos**. Ennek a jelölésnek a segítségével garantálható, hogy a rendelést nem lehet kiadni a raktárba. A felhasználók bármely értékesítési rendelés esetében megtekinthetik a **Feldolgozni tilos** jelölés beállítását a **Részletes állapot** lapon. Ezt az oldalt a **Minden értékesítési rendelés** és az **Ügyfélszolgálat** lapon lehet megnyitni. A rendszer frissíti a megrendeléshez tartozó **Részletes állapot** mező értékét is a következőre: **Csalás miatt várakoztatva**.

A csalásellenőrzés miatt várakoztatott rendelések megtekintéséhez és kezeléséhez lépjen ide: **Retail és Commerce**\>**Vevők**\>**Várakoztatott rendelések**. A **Várakoztatott rendelések** oldalon jelöljön ki egy bejegyzést a listában, és kattintson a **Várakoztatott rendelés** lehetőségre, hogy olyan részletesebb nézetet lásson, amely tartalmazza a várakoztatás okát. A **Csalás részletei** gyorslapon meg lehet tekinteni azokat a szisztematikus csalási feltételeket, amelyek előfordultak a rendelés esetében, valamint itt találhatók az alkalmazott pontszámok is. Ha a rendelést manuálisan várakoztatják, megtekintheti annak a felhasználónak a megjegyzéseit, aki várakoztatott állapotba tette a rendelést; ehhez nézze meg a **Csalási megjegyzések** szakaszt a **Megjegyzések** gyorslapon.

További tájékoztatás a rendelések várakoztatásával kapcsolatban itt találhatók: [ Rendelések várakoztatása: ](/dynamics365/unified-operations/retail/work-with-order-holds).


[!INCLUDE[footer-include](../includes/footer-banner.md)]