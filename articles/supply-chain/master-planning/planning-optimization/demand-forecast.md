---
title: Alaptervezés az igény-előrejelzésekkel
description: Ez a témakör azt mutatja be, hogyan lehet szerepeltetni a Tervezési optimalizálással történő alaptervezés során az igény-előrejelzéseket.
author: ChristianRytt
manager: tfehr
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 8b47aee41494394a32ffc0ea0c42a512e5051532
ms.sourcegitcommit: b86576e1114e4125eba8c144d40c068025f670fc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/03/2020
ms.locfileid: "4666722"
---
# <a name="master-planning-with-demand-forecasts"></a>Alaptervezés az igény-előrejelzésekkel

[!include [banner](../../includes/banner.md)]

Az igény-előrejelzést a Tervezési optimalizálással együtt használhatja az alaptervezésben várható igény felméréséhez. Manuálisan létrehozhatja az igény-előrejelzést, importálhatja vagy generálhatja a Microsoft Dynamics 365 Supply Chain Management igény-előrejelzési funkciójának használatával. Az igény-előrejelzéssel kapcsolatos további tudnivalókat lásd: [Igény-előrejelzés áttekintése](../introduction-demand-forecasting.md).

> [!NOTE]
> A Tervezés optimalizálás során külön előrejelzési tervezés nem támogatott. Ezért az **Alaptervezés paraméterei** oldal **Aktuális előrejelzési terv** beállításának nincs hatása a Tervezés optimalizálás használata során.

## <a name="set-up-a-master-plan-to-include-a-demand-forecast"></a>Az igény-előrejelzést tartalmazó alapterv beállítása

Ha egy alaptervet úgy kíván konfigurálni, hogy az tartalmazza az igény-előrejelzést, hajtsa végre az alábbi lépéseket.

1. Válassz az **Alaptervezés \> Beállítás \> Tervek \> Alaptervezések** lehetőséget.
1. Válasszon ki egy meglévő tervet, vagy hozzon létre egy új tervet.
1. Az **Általános** gyorslapon állítsa be a következő mezőket:

    - **Előrejelzési modell** – Válassza ki az alkalmazni kívánt előrejelzési modellt. Ezt a modellt akkor kell figyelembe venni, amikor az aktuális alaptervhez létrejön egy ellátási javaslat.
    - **Igény-előrejelzéssel együtt** – Állítsa ezt a beállítást *Igen* értékre az igény-előrejelzés aktuális alaptervben való szerepeltetéséhez. Ha *Nem* értékre állítja be, az igény-előrejelzési tranzakciók nem fognak szerepelni az alaptervben.
    - **Előrejelzési követelmények csökkentéséhez használt módszer** – Válassza ki az előrejelzési követelmények csökkentéséhez használandó módszert. További tudnivalókért lásd a [Előrejelzés csökkentési kulcsok](#reduction-keys) című részt, a témakör későbbi részében.

1. Az **Időkorlát napokban** gyorslapon a következő mezőkkel adhatja meg azt az időszakot, amelyen az igény-előrejelzés szerepel:

    - **Előrejelzési terv** – Ezt a beállítást *Igen* értékre állítva felülbírálhatja az egyes fedezeti csoportoktól származó előrejelzési terv időkorlátját. A *Nem* értékre állítása esetén az aktuális alaptervhez tartozó egyes fedezeti csoportok értékeit kell használni.
    - **Előrejelzési időszak** – Ha az **Előrejelzési terv** beállítás *Igen* értékre van állítva, adja meg, hogy hány napig (a mai dátumtól) kell alkalmazni az igény-előrejelzést.

    > [!IMPORTANT]
    > A Tervezés optimalizálás az **Előrejelzési terv** beállítást még nem támogatja.

## <a name="set-up-a-coverage-group-to-include-a-demand-forecast"></a>Az igény-előrejelzést tartalmazó fedezeti csoport beállítása

Ha egy fedezeti csoportot úgy kíván konfigurálni, hogy az tartalmazza az igény-előrejelzést, hajtsa végre az alábbi lépéseket.

1. Manjen az **Alaptervezés \> Beállítás \> Tervek \> Fedezeti csoportok** menübe.
1. Válasszon ki egy meglévő fedezeti csoportot, vagy hozzon létre egy új csoportot.
1. Az **Egyéb** gyorslapon állítsa be a következő mezőket:

    - **Előrejelzési terv időkorlátja** – Adja meg a napok számát (a mai dátumtól számítva), amelyre az igény-előrejelzést alkalmazni kell. Ez az érték felülbírálható az alaptervben szereplő **Előrejelzési terv** beállítással, az előző szakaszban leírtak szerint.
    - **Csökkentési kulcs** – Válassza ki az alkalmazni kívánt csökkentési kulcsot. A további tudnivalókat lásd: [Előrejelzési és csökkentési kulcs létrehozása és beállítása](#create-reduction-key), majd a [Csökkentési kulcs használata](#use-reduction-key) szakaszokban a témakör későbbi részében.
    - **Előrejelzés csökkentésének mennyisége** – Azon alaptervek esetében, amelyeknél az **Előrejelzési követelmények csökkentéséhez használt módszer** a *Tranzakciók – Csökkentési kulcs* vagy a *Tranzakciók – Dinamikus időszak* beállítására van állítva, adja meg, hogy mely tranzakciók csökkentsék az előrejelzést. Válasszon a következő értékek közül:

        - **Minden tranzakció** – Minden tranzakciónak csökkentenie kell az előrejelzést.
        - **Rendelések** – Csak az értékesítési rendelések csökkenthetik az előrejelzést.

        > [!NOTE]
        > Ha az *Összes tranzakció* lehetőséget választja, akkor azok a tranzakciók, amelyeknél az igény és az ellátás egyaránt szerepel ugyanazon készletdimenziók között, semlegesnek számít, és az előrejelzési csökkentés során figyelmen kívül maradnak. Ha például a tervezési dimenzió csak a telephelyre van beállítva, nem a raktárra, akkor az átmozgatási rendelést az 1. hely 11. raktára és az 1. hely 13. raktára között figyelmen kívül hagyja a rendszer, és nem fogja csökkenteni a hátralévő igény-előrejelzést.

    - **Vállalatközi rendelések szerepeltetése** – Ezt a lehetőséget akkor kell *Igen* értékkel megadni, ha a vállalatközi rendeléseket figyelembe kell venni az előrejelzés csökkentéséhez. Ellenkező esetben a beállítás *Nem* értékre van állítva.
    - **Vevői előrejelzés belefoglalása az igény-előrejelzésbe** – Annak megadása, hogy a vevői előrejelzés szerepeljen-e az általános előrejelzésben. Ez a beállítás határozza meg, hogy a tényleges igény hogyan csökkenti az előrejelzett igényt. A beállítás segítségével biztosítható, hogy az alaptervezés lefedi az adott vevők által beszerzett cikkek kínálatát.

        - Ezt a beállítást *Igen* értékre állítva a vevői előrejelzéseket a teljes előrejelzésbe is belefoglalhatja. Ebben az esetben a tényleges vevői igény csökkenti mind a vevői előrejelzést, mind a teljes előrejelzést. Az alaptervezés létrehozza a teljes előrejelzett mennyiséget lefedő tervezett rendeléseket.
        - Ezt a beállítást állítsa *Nem* értékre, ha nem szeretné a vevői előrejelzéseket a teljes előrejelzésbe is belefoglalni. Ebben az esetben a tényleges vevői igény csak a vevői előrejelzést csökkenti. Az alaptervezés létrehozza a teljes előrejelzett mennyiséget, és az egyes előrejelzett vevői mennyiségeket lefedő tervezett rendeléseket.

## <a name="forecast-reduction-keys"></a><a name="reduction-keys"></a>Előrejelzés csökkentési kulcsok

Ez a szakasz az előrejelzési követelmények csökkentése érdekében használt különböző módszerekkel kapcsolatosan tartalmaz információkat. Az egyes módszerek eredményire példákat tartalmaz. Azt is bemutatja, hogyan lehet létrehozni, beállítani és használni az előrejelzési csökkentési kulcsot. Bizonyos módszerek csökkentési kulcsot használnak az előrejelzési követelmények csökkentéséhez.

### <a name="methods-that-are-used-to-reduce-forecast-requirements"></a>Előrejelzési követelmények csökkentésére használható módszerek

Ha előrejelzés vesz fel egy alaptervbe, kiválaszthatja az előrejelzési követelmények csökkentésének módját, ha tényleges igény is szerepel a tervben. Ne feledje, hogy az alaptervezés kizárja a múltbeli előrejelzési követelményeket, ami azt jelenti, hogy az összes előrejelzési követelmény a mai dátum előtt szerepel ki lesz zárva.

Alapterv beépítéséhez az alaptervbe, és az előrejelzési követelmények csökkentése érdekében használt módszer kiválasztásához válassza az **Alaptervezés \> Beállítás \> Tervek \> Alaptervek** lehetőséget. Az **Előrejelzési modell** mezőben válasszon egy előrejelzési modellt. A **Előrejelzési követelmények csökkentésére szolgáló metodológia** mezőben válasszon egy metodológiát. Ehhez a következő lehetőségek állnak rendelkezésre:

- None
- Százalék – csökkentési kulcs
- Tranzakciók – csökkentési kulcs (még nem támogatott a Tervezési optimalizálásban)
- Tranzakciók – dinamikus időszak

A következő részekben további információkat találhat minden egyes lehetőségről.

#### <a name="none"></a>Egyik sem

Ha a **Nincs** lehetőséget választja: az alapütemezés során az előrejelzési követelmények nem csökkennek. Ebben az esetben az alaptervezés tervezett rendeléseket hoz létre az előre jelzett kereslet kiszolgálásához (előrejelzési követelmények). A tervezett rendelések megtartják a javasolt mennyiséget, függetlenül a más típusú igényektől. Például, értékesítési rendelések leadása esetén az alaptervezés további tervezett rendeléseket hoz létre az értékesítési rendelések kiszolgálásához. Az előrejelzési követelmények mennyisége nem csökken.

#### <a name="percent--reduction-key"></a>Százalék – csökkentési kulcs

Ha a **Százalék – csökkentési kulcs** lehetőséget választja, az előrejelzési követelmények csökkentése a százalékok és az időszakok alapján történik, amelyeket a csökkentési kulcs definiál. Ebben az esetben az alaptervezés tervezett rendeléseket hoz létre, ahol a mennyiség számítása előre jelzett mennyiség x csökkentési kulcs módszerrel történik az egyes időszakokban. Más típusú igények esetén az alaptervezés tervezett rendelések is létrehoz az igény teljesítéséhez.

##### <a name="example-percent--reduction-key"></a>Példa: Százalék – csökkentési kulcs

Csökkentési kulcs az előrejelzési követelmények csökkentése a százalékok és az időszakok alapján történik, amelyeket a csökkentési kulcs definiál.

Az ebben a példában a következő igény-előrejelzést tartalmazza az alapterv.

| Hónap    | Igény-előrejelzés |
|----------|-----------------|
| Január  | 1000           |
| Február | 1000           |
| Március    | 1000           |
| Április    | 1000           |

A **Csökkentési kulcsok** lapon beállítja a következő sorokat.

| Visszajáró | Egység  | Százalék |
|--------|-------|---------|
| 1      | Hónap | 100     |
| 2      | Hónap | 75      |
| 3      | Hónap | 50      |
| 4      | Hónap | 25      |

Hivatkozás a csökkentési kulcsot hozzárendeli a cikk fedezeti csoporthoz. Majd az **Alaptervek** oldalon, az **Előrejelzési követelmények csökkentésére szolgáló metodológia** mezőben kiválasztja a **Százalék - csökkentési kulcs** lehetőséget.

Ebben az eseteben, ha előrejelzési ütemezést január 1-jén futtatja, az igény-előrejelzés követelményeinek felhasználása a százalékokat, amelyek a beállítása a **Csökkentési kulcsok** oldalon. Az alábbi mennyiségi követelések kerülnek az alaptervbe.

| Hónap                | Tervezett rendelési mennyiség. | Számítás    |
|----------------------|------------------------|----------------|
| Január              | 0                      | = 0% × 1000   |
| Február             | 250                    | = 25% × 1000  |
| Március                | 500                    | = 50% × 1000  |
| Április                | 750                    | = 75% × 1000  |
| május – december | 1000                  | = 100% × 1000 |

#### <a name="transactions--reduction-key"></a>Tranzakciók – csökkentési kulcs

Ha a **Tranzakciók – csökkentési kulcs** lehetőséget választja, az előrejelzési követelmények azon tranzakciók mértékével csökkennek, amelyek a csökkentési kulcs által definiált időszakokra vonatkoznak.

##### <a name="example-transactions--reduction-key"></a>Példa: Tranzakciók – csökkentési kulcs

Csökkentési kulcs az előrejelzési követelmények csökkentése a százalékok és az időszakok alapján történik, amelyeket a csökkentési kulcs definiál.

Ebben a példában az **Alaptervek** oldalon, az **Előrejelzési követelmények csökkentésére szolgáló metodológia** mezőben kiválasztja a **Százalék - csökkentési kulcs** lehetőséget.

A következő értékesítési rendelések léteznek január 1-én.

| Hónap    | Rendelt darabszám |
|----------|--------------------------|
| Január  | 956                      |
| Február | 1,176                    |
| Március    | 451                      |
| Április    | 119                      |

Ugyanazt a havi 1000 darabos értékesítési előrejelzést alkalmazva, mint az előző példában az alábbi mennyiségi követelések kerülnek az alaptervbe.

| Hónap                | Szükséges darabszám |
|----------------------|---------------------------|
| Január              | 44                        |
| Február             | 0                         |
| Március                | 549                       |
| Április                | 881                       |
| május – december | 1000                     |

#### <a name="transactions--dynamic-period"></a>Tranzakciók – dinamikus időszak

Ha a **tranzakciók - dinamikus időszak** lehetőséget választja, az előrejelzési követelmények csökkentve lesznek a tényleges rendelési tranzakciókkal, amelyek a dinamikus időszak során következnek be. A dinamikus időszak fedezi az aktuális előrejelzési dátumokat és akkor ér véget a következő előrejelzés kezdetén. Ebben az esetben az alaptervezés tervezett rendeléseket hoz létre az előre jelzett kereslet kiszolgálásához (előrejelzési követelmények). Azonban, amikor tényleges rendelési tranzakciókat ad le, az előrejelzési követelmények csökkentve lesznek. A tényleges tranzakciók az előrejelzési követelmények egy részét felhasználják.

Ez a beállítás használata esetén a következő történik:

- Csökkentési kulcsok nem szükségesek vagy használatosak. 
- Ha az előrejelzés teljes mértékben lecsökken, az előrejelzési követelmények az aktuális előrejelzéshez 0-ra (nulla) váltanak.
- Nincs jövőbeli előrejelzés esetén beírt utolsó előrejelzésből az előrejelzési követelmények csökkentése.
- Időkorlátok az előrejelzés-csökkentés-számításban szerepel.
- Időkorlátok az előrejelzés-csökkentés-számításban szerepel.
- Tényleges rendelési tranzakciók túllépik az előre jelzett követelményeit, ha a fennmaradó tranzakciók nem továbbítja a következő előrejelzési időszak.

##### <a name="example-1-transactions--dynamic-period"></a>1. példa: Tranzakciók – dinamikus időszak

Itt egy egyszerű példa, amely tartalmazza, hogyan működik a **Tranzakciók - dinamikus időszak** metódus.

Az ebben a példában a következő igény-előrejelzést tartalmazza az alapterv.

| Dátum       | Igény-előrejelzés |
|------------|-----------------|
| Január 1.  | 1000           |
| február 1. | 1000             |

A következő értékesítési rendeléseket is létrehozza.

| Dátum        | Eladási árhoz kapcsolódó mennyiség |
|-------------|----------------------|
| Január 15.  | 200                  |
| február 15. | 400                  |

Ebben az esetben a következő tervezett rendelések jönnek létre.

| Igény-előrejelzés kockája | Mennyiség | Magyarázat                           |
|--------------------- |----------|---------------------------------------|
| Január 1.            | 800      | Előrejelzési követelmények (= 1000 – 200) |
| Január 15.           | 200      | Értékesítési rendelések követelményei             |
| február 1.           | 600      | Előrejelzési követelmények (= 1000 – 400) |
| február 15.          | 400      | Értékesítési rendelések követelményei             |

##### <a name="example-2-transactions--dynamic-period"></a>2. példa: Tranzakciók – dinamikus időszak

A legtöbb esetben rendszerek vannak beállítva, hogy a tranzakciók csökkenti az igény-előrejelzés egyedi előrejelzési időszakokon belül: hét, hónap, és így tovább. A csökkentési kulcs határozza meg ezeket az időszakokat. Ugyanakkor két között eltelt idő igény-előrejelzési sort is *Jelenti* egy időszakot.

Ebben a példában létrehoz egy igény-előrejelzés a következő dátumokat és mennyiségeket.

| Dátum       | Igény-előrejelzés |
|------------|-----------------|
| Január 1.  | 1000           |
| Január 5.  | 500             |
| Január 12. | 1000           |

Figyelje meg, hogy ez előrejelzésben, nincs egyértelmű időszak az előrejelzési dátumok között. Az első és második dátum között egy négy napos időtartam van, és a második és harmadik dátum között egy hét napos időtartam van. Ezek az időszakok dinamikus időszakok.

A következő értékesítési rendelési sorokat is létrehozza.

| Dátum                             | Eladási árhoz kapcsolódó mennyiség |
|----------------------------------|----------------------|
| December 15-re vonatkozóan az előző év | 500                  |
| Január 3.                        | 100                  |
| Január 10.                       | 200                  |

Ebben az esetben az előrejelzés a következő módon csökken:

- Mivel az első értékesítési rendelés egyik időszakhoz sem tartozik, így azt nem csökkenti egyik előrejelzést sem.
- Mivel a második értékesítési rendelés január 1. és január 5. között van csökkenteni január 1-hez tartozó előrejelzést 100-zal.
- Mivel a harmadik értékesítési rendelés január 5. és január 12. között van csökkenteni január 5-höz tartozó előrejelzést 200-zal.

Tehát a következő tervezett rendelések jönnek létre.

| Igény-előrejelzés kockája             | Mennyiség | Magyarázat                                                         |
|----------------------------------|----------|---------------------------------------------------------------------|
| December 15-re vonatkozóan az előző év | 500      | Értékesítési rendelés követelményei                                            |
| Január 1.                        | 900      | Előrejelzési követelmények időszaka január 1 és január 5 között (= 1 000-100) |
| Január 3.                        | 100      | Értékesítési rendelés követelményei                                            |
| Január 5.                        | 300      | Előrejelzési követelmények időszaka január 5 és január 10 között (= 500 – 200)  |
| Január 12.                       | 1000    | Előrejelzési követelmények időszaka január 12 és január vége között                      |

### <a name="create-and-set-up-a-forecast-reduction-key"></a><a name="create-reduction-key"></a>Előrejelzési csökkentési kulcs létrehozása és beállítása

Az előrejelzési csökkentési kulcs a **Tranzakciók - csökkentési kulcs** és **Százalék-csökkentési kulcs** metodológiákban van használva az előrejelzési követelmények csökkentéséhez. Kövesse az alábbi lépéseket csökkentési kulcs létrehozásához és beállításához.

1. Manjen az **Alaptervezés \> Beállítás \> Fedezet \> Csökkentési kulcsok** menübe.
2. Válassza az **Új** lehetőséget, vagy nyomja le a **Ctrl + N** billentyűkombinációt csökkentési kulcs létrehozásához.
3. A **csökkentési kulcs** mezőben írjon be az előre jelzett csökkentési kulcs egyedi azonosítóját. Majd a **Név** mezőben adjon meg egy nevet. 
4. Adja meg az időszakokat és a csökkentési kulcs százalékát az egyes időszakokhoz:

    - Az **Érvényesség dátuma** mező jelzi az időszakok létrehozása megkezdésének dátumát. Ha az **Érvényesség dátuma** mezőt értéke **Igen**, az időszakok érvényesség dátumán kezdődnek. Ha az érték **Nem**, az időszakok azon a napon kezdődnek, amikor az alaptervezést futtatják.
    - Határozza meg az előrejelzés-csökkentés bekövetkezésének időszakait.
    - Egy adott időszakhoz adja meg a százalékokat, amelyekkel az előrejelzési követelmények csökkenteni kell. A követelmények csökkentése érdekében pozitív értékeket, a követelmények növelése érdekében negatív értékek adjon meg.

### <a name="use-a-reduction-key"></a><a name="use-reduction-key"></a>Csökkentési kulcs használata

Előre jelzett csökkentési kulcsot a cikk fedezeti csoportjához kell hozzárendelni. Kövesse az alábbi lépéseket a csökkentési kulcs hozzárendeléséhez egy cikk fedezeti csoportjához.

1. Manjen az **Alaptervezés \> Beállítás \> Fedezet \> Fedezeti csoportok** menübe.
2. Az **Egyéb** gyorslapon, a **Csökkentési kulcs** mezőben, válassza ki a csökkentési kulcsot, amelyet a fedezeti csoporthoz rendel. A csökkentési kulcs ezután a cikkfedezeti csoporthoz tartozó összes cikkre vonatkozik.
3. A csökkentési kulcs használatához előrejelzés-csökkentés számításához az alapütemezésben meg kell adnia ezt a beállítást az előrejelzési terv és az alapütemezés beállításánál. Lépjen az alábbiak közül valamelyik helyre:

    - Alaptervezés \> Beállítás \> Tervek \> Előrejelzési tervek
    - Alaptervezés \> Beállítás \> Tervek \> Alapütemezések

4. Az **Előrejelzési tervek** vagy **Alaptervek** oldalon az **Általános** gyorslapon, az **Előrejelzési követelmények csökkentésére szolgáló metodológia** mezőben válassza a **Százalék - csökkentési kulcs** vagy **Tranzakciók - csökkentési kulcs** lehetőséget.

### <a name="reduce-a-forecast-by-transactions"></a>Előrejelzés csökkentése tranzakciókkal

Ha bejelöli a **Tranzakciók - csökkentési kulcs** vagy **Tranzakciók - dinamikus időszak** az előrejelzési követelmények csökkentésének módszereként, megadhatja a tranzakciók az előrejelzés csökkentéséhez. A **Fedezeti csoportok** oldalon, az **Egyéb** gyorslapon, akkor az **Előrejelzés csökkentése ennyivel:** mezőben válassza ki az **Összes tranzakció**, ha az összes tranzakció csökkentse az előrejelzést, vagy a **Rendelések** lehetőséget, ha csak az értékesítési rendelések csökkentsék az előrejelzést.
