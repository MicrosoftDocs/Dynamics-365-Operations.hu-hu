---
title: Napló kiküldésének hibája egyensúlyhiány miatt
description: Ez a téma elmagyarázza, hogy miért fordulhat elő, hogy a terhelések és jóváírások nem egyenlők az utalványügyletekben, így a tranzakciókat nem lehet könyvelni. A téma a probléma javításának lépéseit is tartalmazza.
author: kweekley
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-8-03
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: fc413f8230849653aef8c2951f1749823edded6e
ms.sourcegitcommit: 25b3dd639e41d040c2714f56deadaa0906e4b493
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/06/2021
ms.locfileid: "7605429"
---
# <a name="journal-posting-failure-because-of-imbalance"></a>Napló kiküldésének hibája egyensúlyhiány miatt

[!include [banner](../includes/banner.md)]

Ez a téma elmagyarázza, hogy miért fordulhat elő, hogy a terhelések és jóváírások nem egyenlők az utalványügyletekben, így a tranzakciókat nem lehet könyvelni. A téma a probléma javításának lépéseit is tartalmazza.

## <a name="symptom"></a>Tünet

Bizonyos esetekben a naplót nem lehet könyvelni, és a következő üzenet jelenik meg: „Egy adott bizonylaton szereplő tranzakciók egy bizonyos időpontban nem állnak egyensúlyban (számviteli pénznem: 0,01 - jelentési pénznem: 0,06).” Miért nem lehet a naplót kifüggeszteni?

## <a name="resolution"></a>Megoldás

A főkönyvi könyvelés során minden bizonylatot a tranzakció pénznemében, a könyvelési pénznemben és a beszámoló pénznemében kell kiegyenlíteni, ha ezek a pénznemek a **főkönyv beállítása** lapon meg vannak határozva. (Az utalványok akkor kerülnek egyensúlyba, ha a terhelések összege megegyezik a jóváírások összegével.)

A naplósorok lap alján az összegek a számviteli pénznemben és a jelentési pénznemben jelennek meg. A devizatranzakciók esetében **nem** jelennek meg a tranzakció pénznemében. Ezenkívül a felhasználók által a szimuláció vagy a könyvelés során kapott hibaüzenet csak a számviteli pénznemben és a beszámoló pénznemében mutatják a különbségeket. Nem a tranzakciós pénznemben jeleníti meg őket, mivel egyetlen utalványhoz több tranzakciós pénznem is tartozhat, és a napló különböző tranzakciós pénznemekben lévő utalványokat is tartalmazhat. Emiatt fontos, hogy manuálisan ellenőrizze, hogy a tranzakció pénznemösszege minden olyan bizonylaton egyensúlyban van-e, amely csak egy tranzakciós pénznemet tartalmaz.

### <a name="transaction-currency"></a>Tranzakció pénzneme

A szimuláció és a könyvelés során a rendszer ellenőrzi, hogy minden utalvány, amely csak egy tranzakciós pénznemet tartalmaz a tranzakció pénznemében van-e kiegyenlítve. Minden egyes bevitt utalványhoz egy vagy több pénznemet lehet megadni a tranzakció pénznemeként. Például az általános naplóban rögzített bizonylatnak két tranzakciós pénzneme lehet, amikor egy eurót (EUR) használó bankszámláról egy kanadai dollárt (CAD) használó bankszámlára utalnak át készpénzt.

Ha egy utalványnak csak egy tranzakciós pénzneme van, a teljes terhelésnek meg kell egyeznie az adott utalvány teljes jóváírásával a az utalvány tranzakciós pénznemében. Az ügyfelek a következő esetekkel találkoztak, amikor a könyvelés helyesen sikertelen volt, mert a tranzakció pénznemének összegei nem voltak kiegyenlítve:

- A teljes terhelés és a teljes jóváírás **nem** volt kiegyensúlyozott a tranzakció pénznemében, de a számviteli pénznem és a jelentési pénznem esetében igen. Egy ügyfél azt feltételezte, hogy az utalványt továbbra is feladják. Ez a feltételezés azonban téves volt. **Az utalványon szereplő tranzakciós pénznemek összegének mindig egyensúlyban kell lennie, ha az utalvány minden sora azonos tranzakciós pénznemmel rendelkezik.**
- A bizonylatot adatentitással importálták az Adatkezelési keretrendszeren (DMF) keresztül, és a felhasználó azt gondolta, hogy a tranzakció pénznemösszege kiegyensúlyozott volt. az importált fájlban szereplő összegek egy része több mint két tizedesjegyet tartalmazott, és az összegek importálásakor több mint két tizedesjegy szerepelt. Ezért a terhelések nem egyeztek meg a jóváírásokkal, mert egy fillér töredékével tértek el. A napló nem tükrözte ezt a különbséget az utalvány soraiban, mivel a feltüntetett összegek csak két tizedesjegyet tartalmaznak.
- Az utalványt a DMF-en keresztül importálták egy adatentitással, és a felhasználó úgy gondolta, hogy a tranzakció pénznemének összegei kiegyenlítettek. Bár az **utalvány** kiegyensúlyozott volt, az utalvány egyes soraiban eltérő tranzakciós dátumok szerepeltek. Ha összeadta az összes terhelést és az összes jóváírást a tranzakció pénznemében **utalványonként és tranzakciós dátumonként**, akkor nem voltak kiegyensúlyozottak. Ez a követelmény akkor érvényesül, amikor az utalványt a rendszer általános naplóján keresztül rögzíti. Nem érvényesíthető azonban olyankor, amikor egy utalványt a DMF-űrlapon keresztül adatentitással importáltak.

Egy támogatott forgatókönyv szerint egy utalványhoz egynél több tranzakciós pénznem is tartozhat. Ebben az esetben a rendszer **nem** ellenőrzi, hogy a terhelések megegyeznek-e a jóváírásokkal a tranzakció pénznemében, mivel a pénznemek nem egyeznek. Ehelyett a rendszer ellenőrzi, hogy a számviteli és jelentési pénznemek összegei egyensúlyban vannak-e.

### <a name="accounting-currency"></a>Könyvelési pénznem

Ha egy utalvány minden sora azonos tranzakciós pénznemmel rendelkezik, és ha a tranzakciós pénznemek összegei kiegyenlítettek, a rendszer ellenőrzi, hogy a könyvelési pénznemek összegei is kiegyenlítettek. Ha az utalványt külföldi pénznemben adják meg, az utalvány soraiban szereplő árfolyamot használják a tranzakció pénznemében megadott összegek számviteli pénznemre történő átszámításához. Először a bizonylat minden sorát átváltja és két tizedesjegyre kerekíti. Ezután a sorokat összeadjuk, hogy meghatározzuk a teljes terhelést és a teljes jóváírást. Mivel minden egyes sort lefordítanak, előfordulhat, hogy a teljes terhelés és a teljes jóváírás nem lesz egyensúlyban. Mindazonáltal, ha a különbözet abszolútértéke a **főkönyvi paraméterek** lapon meghatározott **Maximális filléres különbözet** értékén belül van, az utalvány könyvelésre kerül, és a különbözet automatikusan a Filléres különbözet számlára kerül könyvelésre.

Ha az utalvány egynél több tranzakciós pénznemet tartalmaz, az utalvány minden egyes sorát át kell számítani a számviteli pénznemre, majd két tizedesjegyre kerekíteni, majd a sorokat össze kell adni a teljes terhelés és a teljes jóváírás meghatározásához. Ahhoz, hogy kiegyensúlyozottnak számítsa a tartozik és a követel tételeket kik kell egyensúlyozni, vagy átváltva, vagy ha a könyvelési pénznem fillérre kerekített összege is bele van foglalva.

### <a name="reporting-currency"></a>Jelentési pénznem

Ha egy utalvány minden sora azonos tranzakciós pénznemmel rendelkezik, és ha a tranzakciós pénznemek összegei kiegyenlítettek, a rendszer ellenőrzi, hogy a jelentési pénznemek összegei kiegyenlítettek-e. Ha az utalványt külföldi pénznemben adják meg, az utalvány soraiban szereplő árfolyamot használják a tranzakció pénznemében megadott összegek beszámolási pénznemre történő átszámításához. Először a bizonylat minden sorát átváltja és két tizedesjegyre kerekíti. Ezután a sorokat összeadjuk, hogy meghatározzuk a teljes terhelést és a teljes jóváírást. Mivel minden egyes sort lefordítanak, előfordulhat, hogy a teljes terhelés és a teljes jóváírás nem lesz egyensúlyban. Mindazonáltal, ha a különbözet a **főkönyvi paraméterek** lapon meghatározott, a **jelentési pénznemben megadott maximális filléres kerekítésen** belül van, az utalvány könyvelésre kerül, és a különbözet automatikusan a Filléres különbözet számlára kerül könyvelésre.

Ha az utalvány egynél több tranzakciós pénznemet tartalmaz, az utalvány minden egyes sorát át kell számítani a jelentési pénznemre, majd két tizedesjegyre kerekíteni, majd a sorokat össze kell adni a teljes terhelés és a teljes jóváírás meghatározásához. Ahhoz, hogy kiegyensúlyozottnak számítsa a tartozik és a követel tételeket kik kell egyensúlyozni, vagy átváltva, vagy ha a jelentési pénznem fillérre kerekített összege is bele van foglalva.

### <a name="example-for-an-accounting-currency-imbalance"></a>Példa a könyvelési pénznem kiegyensúlyozatlanságára

> [!NOTE]
> A jelentési pénznem összege ugyanúgy van számítva a tranzakció pénznemösszegéből, mint a könyvelési pénznem összege.

Árfolyam: 1,5

| Sor | Bizonylat  | Könyvelési számla | Pénznem | Terhelés (tranzakció) | Jóváírás (tranzakció) | Terhelés (könyvelés) | Jóváírás (könyvelés) |
|---|---|---|---|---|---|---|---|
| 1 | 001 | 1101-01 | EUR | 3.33 | | 5,00 (4,995) | |
| 2 | 001 | 1101-02 | EUR | 3.33 | | 5,00 (4,995) | |
| 3 | 001 | 1101-03 | EUR | 3.34 | | 5.01 | |
| 4 | 001 | 4101- | EUR | | 10,00 | | 15.00 |
| **Teljes** | | | | **10.00** | **10.00** | **15.01** | **15.00** |

A könyvelési pénznem 0,01-gyel nincs egyensúlyban. Ha azonban a maximális fillérkerekítés a könyvelési pénznemben legalább 0,01, a különbözetet automatikusan feladja a program a Fillér különbözeti számlára, és a bizonylat feladása sikeresen megtörténik.
