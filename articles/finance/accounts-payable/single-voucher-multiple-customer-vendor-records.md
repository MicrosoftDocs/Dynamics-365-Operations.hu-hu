---
title: Egyetlen bizonylat több vevő- vagy szállítórekorddal
description: Ez a cikk áttekintést nyújt arról, hogy mi történik, ha egy bizonylatot több vevői vagy szállítói rekordot ad fel. Ennek a funkciónak Microsoft Dynamics a használata a 365 Pénzügy jövőbeli verzióiban megszűnik, ezért a kiegyenlítés feldolgozására gyakorolt könyvelési hatás miatt nem ajánljuk ezt a feladási módszert.
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 222534
ms.assetid: d4df11ce-4d36-4c66-8230-f5fc58e021bc
ms.openlocfilehash: 05f5173a6595814e66d0d114fad49c8107c9acf2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281265"
---
# <a name="single-voucher-with-multiple-customer-or-vendor-records"></a>Egyetlen bizonylat több vevő- vagy szállítórekorddal

[!include [banner](../includes/banner.md)]

Ez a cikk áttekintést nyújt arról, hogy mi történik, ha egy bizonylatot több vevői vagy szállítói rekordot ad fel. Ez a funkció a későbbi verziókban meg fog szűnni. Emiatt – az elszámolásfeldolgozás könyvelési hatása miatt – nem ajánlott ezzel a módszerrel végrehajtani a feladást. 

Egy bizonylat több vevő vagy szállító esetében történő használatára általánosan elterjedt példa az egyenlegátvitel az ügyfelek között vagy az egyenleg nettóérték-számítása a vevők és a szállítók között az adott szervezeten belül. 

Az egynél több vevőt vagy szállítót tartalmazó bizonylatok az alábbi módszerek valamelyikével vihetők be:

-   Olyan napló használata, amelynél a **Csak egy bizonylatszám** beállítás van megadva, ami azt jelenti, hogy a naplóhoz hozzáadott minden egyes sor ugyanazon a bizonylaton szerepel.
-   Többsoros bizonylat használata több vevővel vagy szállítóval, amelynél nincs főkönyvi ellenszámla.
-   Bizonylat bevitele, amelynél a számla és az ellenszámla szállító/szállító, vevő/vevő, szállító/vevő vagy vevő/szállító.

Ez a cikk azt mutatja be, hogyan történik a kiegyenlítés feldolgozása, amikor egy bizonylat több vevői vagy szállítói rekordot ad fel. Ez a cikk további megoldásokat is biztosít annak érdekében, hogy jobban megértsük, hogyan lehet elkerülni egy bizonylat több vevővel vagy szállítóval történő alkalmazását. Konkrét példákat is ismertetünk, amelyek két olyan gyakori kiegyenlítési helyzetet mutatnak be, amelyekre hatással van a több vevőt vagy szállítót tartalmazó bizonylatok használata:

-   Készpénzfizetési engedmény könyvelése
-   Átértékelés könyvelése

## <a name="how-does-settlement-impact-single-voucher-usage"></a>Hogyan befolyásolja a kiegyenlítés egy bizonylat felhasználását
Egy több vevő- vagy szállítórekordot tartalmazó bizonylat feladásakor egy könyvelési bizonylat jön létre, amely több kinnlevőségek vagy a kötelezettségek egyenleget tartalmaz. A kiegyenlítési folyamat során az eredeti könyvelési tételek a következőkre szolgálnak: könyvelési tételek létrehozása a készpénzfizetési engedményhez, a nem realizált nyereségekhez és veszteségekhez, a realizált nyereségekhez és veszteségekhez, valamint az eredeti dokumentum összegző számlája elhatárolásának kivezetése. Ha például a készpénzfizetési engedmény alkalmazására a szállítói kifizetés számla ellenében való kiegyenlítésekor kerül sor, a készpénzfizetési engedmény könyvelésének feladást kell végrehajtania a kötelezettségek főkönyvi számlára az eredeti számláról. Ha az eredeti számla feladása több szállítórekordot tartalmazó bizonylattal történt, az eredeti könyvelés összesített. Ebben az esetben, mivel nem lehet elérni egy bizonylaton minden szállítói tranzakció részletes könyvelési bejegyzését, nincs mód annak a meghatározása, hogy a felhasználó hogyan akarta végrehajtani a készpénzfizetési engedmény könyvelését.

### <a name="one-voucher-with-multiple-vendors-and-the-impact-on-cash-discount-accounting"></a>Egy bizonylat több szállítóval, és ennek hatása a készpénzfizetési engedmény könyvelésére

A következő példában a főkönyvben több szállítói számla van rögzítve egy bizonylaton a **Főkönyvi napló** oldalon. Ezek a számlák több számladimenzión vannak elosztva.

| Bizonylat  | Számla típusa | Könyvelési számla  | Leírás | Tartozik | Követel |
|-------------|------------------|--------------|-----------------|-----------|------------|
| GNJL001     | Szállító           | 1001         | INV1            |           | 100,00     |
| GNJL001     | Szállító           | 1001         | INV2            |           | 200,00     |
| GNJL001     | Szállító           | 1001         | INV3            |           | 300,00     |
| GNJL001     | Főkönyv           | 606300-001-- | INV1            |   50,00   |            |
| GNJL001     | Főkönyv           | 606300-002-- | INV1            |   50,00   |            |
| GNJL001     | Főkönyv           | 606300-003-- | INV2            | 200,00    |            |
| GNJL001     | Főkönyv           | 606300-004-- | INV3            | 300,00    |            |

A feladást követően egy bizonylat jön létre.

| Bizonylat  | Könyvelési számla  | Feladás típusa | Összeg a tranzakció pénznemében. |
|-------------|--------------|------------------|------------------------------------|
| GNJL001     | 606300-001-- | Főkönyvi napló   | 50,00                              |
| GNJL001     | 606300-002-- | Főkönyvi napló   | 50,00                              |
| GNJL001     | 606300-003-- | Főkönyvi napló   | 200,00                             |
| GNJL001     | 606300-004-- | Főkönyvi napló   | 300,00                             |
| GNJL001     | 200110-001-  | Szállítói egyenleg   | -100,00                            |
| GNJL001     | 200110-001-  | Szállítói egyenleg   | -200,00                            |
| GNJL001     | 200110-001-  | Szállítói egyenleg   | -300.00                            |

Figyelje meg, hogy a bizonylat három bejegyzést tartalmaz a Szállítóegyenleg feladási típushoz az egyetlen bizonylaton. Nincs mód annak a jelzésére, hogy a 606300-001 50,00 tartozik értékének és a 606300-002 50,00 tartozik értékének a célja a 200110-001 szállítóiegyenleg-bejegyzés ellentételezése. Ennek az oka az, hogy a felhasználó több szállítórekordot vitt be egy bizonylaton.

A példa segítségével elemezhető az egy bizonylatos megoldás hatása a lefelé irányuló kiegyenlítéskönyvelésre. Tegyük fel, hogy a 197,00 összeget fizeti ki a 200,00 összegű számlára, 3,00 készpénzfizetési engedményt érvényesítve. Figyelje meg, hogy a készpénzfizetési engedmény számlaérték a számlabizonylat költségszámláiról az összes dimenzióra ki van osztva. Ennek az oka az, hogy egy bizonylatot használtak a fenti számla feladásához, és az egyetlen bizonylaton semmi sem mutatja, hogy a felhasználó hogyan szándékozta megvalósítani a költségfelosztások megfeleltetését a szállítói egyenlegnek.

| Bizonylat  | Könyvelési számla  | Feladás típusa     | Tartozik | Követel |
|-------------|--------------|----------------------|-----------|------------|
| APPAYM001   | 200110-001-  | Szállítói egyenleg       | 197.00    |            |
| APPAYM001   | 110110-001-  | Bank                 |           | 197.00     |
| 14000056    | 520200-001-- | Szállító készpénzfizetési engedménye |           | 0.25       |
| 14000056    | 520200-002-- | Szállító készpénzfizetési engedménye |           | 0.25       |
| 14000056    | 520200-003-- | Szállító készpénzfizetési engedménye |           | 1,00       |
| 14000056    | 520200-004-- | Szállító készpénzfizetési engedménye |           | 1.50       |
| 14000056    | 200110-001-  | Szállítói egyenleg       | 3,00      |            |

Ha a felhasználó elégedetlen azzal, hogy a készpénzfizetési engedményt az eredeti számláról a költségfelosztások mindegyikéhez kiosztották, a számlák rögzítéséhez több bizonylatot kell használnia. Íme egy példa arra, hogyan lehet több bizonylatot bevinni a főkönyvbe egy bizonylat helyett, ahogy az a példa elején látható.

| Bizonylat  | Számla típusa | Könyvelési számla  | Leírás | Tartozik | Követel | Ellenszámla típusa | Ellenszámla |
|-------------|------------------|--------------|-----------------|-----------|------------|-----------------|--------------------|
| GNJL001     | Szállító           | 1001         | INV1            |           | 100,00     | Főkönyv          | &lt;üres&gt;      |
| GNJL001     | Főkönyv           | 606300-001-- | INV1            |   50,00   |            | Főkönyv          | &lt;üres&gt;:      |
| GNJL001     | Főkönyv           | 606300-002-- | INV1            |   50,00   |            | Főkönyv          | &lt;üres&gt;:      |
| GNJL002     | Szállító           | 1001         | INV2            |           | 200,00     | Főkönyv          | 606300-003--       |
| GNJL003     | Szállító           | 1001         | INV3            |           | 300,00     | Főkönyv          | 606300-004--       |

Az INV2 kifizetésekor a következő bejegyzés történik. Figyelje meg, hogy a készpénzfizetési engedmény pénzügyi dimenziói a társított kiadás pénzügyi dimenzióit követik.

| Bizonylat  | Könyvelési számla  | Feladás típusa     | Tartozik | Követel |
|-------------|--------------|----------------------|-----------|------------|
| APPAYM001   | 200110-001-  | Szállítói egyenleg       | 197.00    |            |
| APPAYM001   | 110110-001-  | Bank                 |           | 197.00     |
| 14000056    | 520200-003-- | Szállító készpénzfizetési engedménye |           | 3,00       |
| 14000056    | 200110-001-  | Szállítói egyenleg       | 3,00      |            |

### <a name="one-voucher-with-multiple-vendors-and-the-impact-on-realized-gainloss-accounting"></a>Egy bizonylat több szállítóval, és a hatás a realizált nyereség/veszteség könyvelésére

| Bizonylat  | Számla típusa | Könyvelési számla | Leírás | Tartozik | Követel | Számla típusa | Könyvelési számla  |
|-------------|------------------|-------------|-----------------|-----------|------------|------------------|--------------|
| GNJL001     | Szállító           | 1001        | INV1            |           | 100,00     | Főkönyv           | 606300-001-- |
| GNJL001     | Szállító           | 1001        | INV2            |           | 200,00     | Főkönyv           | 606300-002-- |

A következő példában a főkönyvben több szállítói számla van rögzítve egy bizonylaton a **Főkönyvi napló** oldalon. Ezek a számlák több számladimenzión vannak elosztva. A feladást követően egy bizonylat jön létre.

| Bizonylat  | Könyvelési számla  | Feladás típusa | Összeg a tranzakció pénznemében (EUR) | Összeg könyvelési pénznemben (USD) |
|-------------|--------------|------------------|------------------------------------------|-----------------------------------------|
| GNJL001     | 606300-001-- | Főkönyvi napló   | 100,00                                   | 114.00                                  |
| GNJL001     | 606300-002-- | Főkönyvi napló   | 200,00                                   | 228.00                                  |
| GNJL001     | 200110-001-  | Szállítói egyenleg   | -100,00                                  | -114.00                                 |
| GNJL001     | 200110-001-  | Szállítói egyenleg   | -200,00                                  | -228.00                                 |

Figyelje meg, hogy a bizonylat két bejegyzést tartalmaz a Szállítóegyenleg feladási típushoz az egyetlen bizonylaton. Nincs mód annak a jelzésére, hogy a 606300-001 50,00 tartozik értékének a célja a 200110-001 100,00 szállítóiegyenleg-bejegyzés ellentételezése. Ennek az oka az, hogy a felhasználó több szállítórekordot vitt be egy bizonylaton. 

A példa segítségével elemezhető az egy bizonylatos megoldás hatása a lefelé irányuló kiegyenlítéskönyvelésre. Tegyük fel, hogy a könyvelés pénzneme USD, és a fenti tranzakciók feladása EUR tranzakciós pénznemben történt. Tegyük fel, hogy teljes egészében kifizeti a 200,00 eurós számlát, de veszteséget realizál, mivel eltérés van a számla feladásai időpontjának és a kifizetés időpontjának árfolyama között. Figyelje meg, hogy a realizált veszteség számlaérték a számlabizonylat költségszámláiról az összes dimenzióra ki van osztva. Ebben az esetben a 001 és a 002 dimenzió egyaránt fel van osztva, bár a felhasználó azt gondolhatja, hogy csak a 002 tartozik a kiegyenlítés alatt levő számla költségszámlájához. Ennek az oka az, hogy egy bizonylatot használtak a fenti számla feladásához, és így semmi sem mutatja, hogy a felhasználó hogyan szándékozta megvalósítani a költségfelosztások megfeleltetését a szállítói egyenlegnek.

| Bizonylat  | Könyvelési számla | Feladás típusa   | Összeg a tranzakció pénznemében (EUR) | Összeg könyvelési pénznemben (USD) |
|-------------|-------------|--------------------|------------------------------------------|-----------------------------------------|
| APPAYM001   | 200110-001- | Szállítói egyenleg     | 200,00                                   | 230.00                                  |
| APPAYM001   | 110110-001- | Bank               | -200,00                                  | -230.00                                 |
| 14000056    | 801300-001- | Árfolyamveszteség | 0,00                                     | 0.67                                    |
| 14000056    | 801300-002- | Árfolyamveszteség | 0,00                                     | 1.33                                    |
| 14000056    | 200110-001- | Szállítói egyenleg     |                                          | -2.00                                   |

Ha a felhasználó elégedetlen azzal, hogy az árfolyamveszteséget az eredeti számláról a költségfelosztások mindegyikéhez kiosztották, a számlák rögzítéséhez több bizonylatot kell használnia. Íme egy példa arra, hogyan lehet több bizonylatot bevinni a főkönyvbe egy bizonylat helyett, ahogy az a példa elején látható.

| Bizonylat  | Számla típusa | Könyvelési számla | Leírás | Tartozik | Követel | Ellenszámla típusa | Ellenszámla |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| GNJL002     | Szállító           | 1001        | INV1            |           | 100,00     | Főkönyv          | 606300-001--       |
| GNJL003     | Szállító           | 1001        | INV2            |           | 200,00     | Főkönyv          | 606300-002--       |

Az INV2 kifizetésekor a következő bejegyzés történik. Figyelje meg, hogy az árfolyamveszteség pénzügyi dimenziói a társított kiadás pénzügyi dimenzióit követik.

| Bizonylat  | Könyvelési számla | Feladás típusa   | Összeg a tranzakció pénznemében (EUR) | Összeg könyvelési pénznemben (USD) |
|-------------|-------------|--------------------|------------------------------------------|-----------------------------------------|
| APPAYM001   | 200110-001- | Szállítói egyenleg     | 200,00                                   | 230.00                                  |
| APPAYM001   | 110110-001- | Bank               | -200,00                                  | -230.00                                 |
| 14000056    | 801300-002- | Árfolyamveszteség | 0,00                                     | 2.00                                    |
| 14000056    | 200110-001- | Szállítói egyenleg     |                                          | -2.00                                   |

## <a name="one-voucher-for-balance-transfers-and-netting-scenarios"></a>Egyetlen bizonylat az egyenlegátvitelekhez és a nettóérték-számítási forgatókönyvekhez
Ez egy bizonylat több vevő vagy szállító esetében történő használatára általánosan elterjedt forgatókönyvek közé tartozik a következő kettő: egyenlegátvitel egy vevőtől/szállítótól egy másik vevőhöz/szállítóhoz, illetve nettóérték-számítás az ugyanabban a szervezetben található vevők és a szállítók között. A következő két példa ezeknek a forgatókönyveknek az előnyben részesített beviteli módszerét mutatja be az egy bizonylaton történő bevitel alternatívájaként. 

Az *egyenlegátvitel* több vevőt tartalmazó egyetlen bizonylat, amelyet azért visznek be, hogy egyenlegátvitelt hajtsanak végre egyik vevőtől egy másiknak (vagy egyik szállítótól a másiknak). Ez a forgatókönyv akkor fordul elő, ha a számla kifizetésének felelősségét átviszik egy másik félnek, például a leányvállalat az anyavállalatnak adja át a felelősséget. 

A következő példa egy olyan értékesítést tételez fel, amelynél a vevő készpénzkedvezményre jogosult abban az esetben, ha 10 napon belül fizet. A példában szereplő vevő egy biztosítótársaságot használ, amely a számla kifizetésének felelőse lesz. A biztosítótársaság második vevőként van beállítva a rendszerben. Az eredeti vevő egyenlegét átviszik a biztosítótársasághoz, aki kifizeti a számlát, a kedvezményes időszakban történő kifizetés 2%-os készpénzfizetési engedményét érvényesítve. 

Illusztrálásként tegyük fel, hogy a következő értékesítés az ACME vevőnek történik. Az alábbi könyvelési tételek felelnek meg az értékesítésnek.

| Főkönyvi számla | Feladás típusa | Tartozik | Követel |
|--------------------|------------------|-----------|------------|
| 401100-002-023-    | Bevétel          |           | 100        |
| 130100-002-        | Vevői egyenleg | 100       |            |

Ezután a felhasználó átviszi az ACME-től esedékes egyenleget a biztosítótársasághoz, egy bizonylaton a kinnlevőségek kifizetési naplóban. A biztosítótársaság Biztosítás vevőként van beállítva.

| Bizonylat  | Számla típusa | Könyvelési számla | Leírás | Tartozik | Követel | Ellenszámla típusa | Ellenszámla |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| ARPAYM001   | Vevő         | ACME        | Átvitel        |           | 100,00     | Vevő        | Biztosítás          |

Figyelje meg, hogy fenti bejegyzést egy bizonylat tartalmazza. Ez a bizonylat két vevőrekordot tartalmaz. A következő bizonylat a fenti főkönyvi bejegyzés feladásakor jön létre.

| Bizonylat  | Könyvelési számla | Feladás típusa | Összeg a tranzakció pénznemében. |
|-------------|-------------|------------------|------------------------------------|
| ARPAYM001   | 130100-002- | Vevői egyenleg | 100,00                             |
| ARPAYM001   | 130100-002- | Vevői egyenleg | -100,00                            |

Ezután tegyük fel, hogy kifizetés érkezik 98,00 értékben a Biztosítás vevőtől, és úgy döntünk, hogy a kiegyenlítést az egyenlegátvitel által létrehozott számlával végezzük el. Ez a következő bizonylat feladását eredményezi. Létező elvárás lehet, hogy a kiegyenlítés az eredeti számláról használja a pénzügyi dimenziókat, de ez nem lehetséges, mert a Biztosítás vevőtől nem létezik számladokumentum. Figyelje meg, hogy alapértelmezés szerint a készpénzfizetési engedmény felosztási dimenzióinak származási helye az átvitellel létrehozott vevői tranzakció, és nem az eredeti számla bevételi számlája. Az alapértelmezett érték annak az eredménye, hogy az egyenlegek átvitele egyetlen bizonylat segítségével történik.

| Bizonylat  | Könyvelési számla | Feladás típusa | Tartozik | Követel |
|-------------|-------------|------------------|-----------|------------|
| ARPAYM002   | 110110-002- | Bank             | 98.00     |            |
| ARPAYM002   | 130100-002- | Vevői egyenleg |           | 98.00      |

A készpénzfizetési engedményhez kapcsolódó bizonylaton a pénzügyi dimenzió alapértelmezetten az átadásból létrehozott vevői tranzakcióból származik, mert az átadásnak egynél több vevője van.

| Bizonylat  | Könyvelési számla | Feladás típusa       | Tartozik | Követel |
|-------------|-------------|------------------------|-----------|------------|
| ARP-00001   | 403300-002- | Vevő készpénzfizetési engedménye | 2.00      |            |
| ARP-00001   | 130100-002- | Vevői egyenleg       |           | 2.00       |

Ha a felhasználó elégedetlen a készpénzfizetési engedmény pénzügyi dimenzióinak alapértelmezésével, egy bizonylat helyett több bizonylatot kell használni az egyenlegátvitel rögzítése érdekében. Ezt a forgatókönyvet úgy kell kivitelezni, hogy létrehozunk egy jóváírást a vevő számára, AMELYBŐL áthelyezzük az egyenleget, és létrehozunk egy megbízást vagy számlát annak a vevőnek, AKINEK az egyenleg átvisszük. A következő példa bemutatja, hogyan lehet több bizonylatot bevinni a kinnlevőségek kifizetések naplójába az egyenleg átviteléhez egy bizonylat helyett, ahogy az a példa elején látható.

| Bizonylat  | Számla típusa | Könyvelési számla | Leírás | Tartozik | Követel | Ellenszámla típusa | Ellenszámla |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| ARPAYM001   | Vevő         | ACME        |                 |           | 100,00     | Főkönyv          | 401100-002-023-    |
| ARPAYM002   | Vevő         | Biztosítás   |                 | 100,00    |            | Főkönyv          | 401100-002-023-    |

Ez azt jelenti, hogy amikor a Biztosítás vevő kifizet 98,00 összeget az ARPAYM02 bizonylattal, a rendszer az ARPAYM002 bizonylat főkönyviszámla-bejegyzésének helyes pénzügyi dimenziót fogja használni.

| Bizonylat  | Könyvelési számla | Feladás típusa | Tartozik | Követel |
|-------------|-------------|------------------|-----------|------------|
| ARPAYM003   | 110110-002- | Bank             | 98.00     |            |
| ARPAYM003   | 130100-002  | Vevői egyenleg |           | 98.00      |

A készpénzfizetési engedményhez kapcsolódó bizonylaton a rendszer az ARPAYM002 bizonylatán megjelenő ellentételező bevételi számláról származó pénzügyi dimenziókat fogja használni.

| Bizonylat  | Könyvelési számla     | Feladás típusa       | Tartozik | Követel |
|-------------|-----------------|------------------------|-----------|------------|
| ARP-00001   | 403300-002-023- | Vevő készpénzfizetési engedménye | 2.00      |            |
| ARP-00001   | 130100-002-     | Vevői egyenleg       |           | 2.00       |

## <a name="one-voucher-with-a-netting-for-multiple-customers-and-vendors"></a>Egy bizonylat több vevő és szállító számára szóló nettóérték-számítással
A nettóérték-számítás akkor lehet hasznos, amikor egy szervezet ugyanazzal a vállalattal kereskedve vásárol és ad el. A szállítói számlák kifizetése és a vevői számlákhoz tartozó fizetésre várakozás helyett a szállítói és vevői számlák nettóérték-számítását végzik el. A nettóérték-számítási tranzakciót a fennmaradó egyenlegre nézve egyenlítik ki. 

Illusztrációként tegyük fel, hogy az 1001 jelzetű szállító és az USA-008 jelzetű vevő ugyanaz a jogi személy, így a vállalat el akarja végezni a kötelezettségek és kinnlevőségek egyenlegének nettóérték-számítását a maradványösszeg kifizetése/fogadása előtt. Tegyük fel, hogy a vevőrekord fizetendő értéke 75,00 EUR, és a szállítói rekord tartozása 100,00 EUR, ami azt jelenti, hogy előnyben részesítjük a nettóérték-számítás elvégzését, és csak 25,00 EUR kifizetését szeretnénk megtenni a szállító számára. Tegyük fel továbbá, hogy az alapértelmezett pénznem az USD. Ebben az esetben egy nettóérték-számítási tranzakciót viszünk be egyetlen bizonylaton a kötelezettségek fizetési naplóba.

| Bizonylat  | Számla típusa | Könyvelési számla | Leírás | Tartozik | Követel | Ellenszámla típusa | Ellenszámla |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| APPAYM001   | Szállító           | 1001        | Nettóérték-számítás         |  75,00    |            | Vevő        | US-008             |

A tranzakció jövőbeli kiegyenlítésével kapcsolatos nemkívánatos problémák elkerülése érdekében a naplóba több bizonylatot kell bevinni a nettóérték-számítási tranzakció rögzítésére. Figyelje meg, hogy a vevői és szállítói egyenlegek ellentételezése egyetlen elszámolószámlával történik egyetlen, több vevői és szállítói egyenleget tartalmazó bizonylat használatának az elkerülése érdekében.

| Bizonylat  | Számla típusa | Könyvelési számla | Leírás | Tartozik | Követel | Ellenszámla típusa | Ellenszámla |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| 001         | Vevő         | US-008      |                 |           |  75,00     | Főkönyv          | 999999---          |
| 002         | Szállító           | 1001        |                 |  75,00    |            | Főkönyv          | 999999---          |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
