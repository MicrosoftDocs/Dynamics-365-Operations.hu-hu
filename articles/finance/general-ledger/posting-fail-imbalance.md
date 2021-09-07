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
ms.openlocfilehash: a59724ff698b6ad0e84b0642240da5f8953ab3d1
ms.sourcegitcommit: 9642494da87c0d237f9fcbe15df14315d9e88fa2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/15/2021
ms.locfileid: "7385723"
---
# <a name="journal-posting-failure-because-of-imbalance"></a>Napló kiküldésének hibája egyensúlyhiány miatt

[!include [banner](../includes/banner.md)]

Ez a téma elmagyarázza, hogy miért fordulhat elő, hogy a terhelések és jóváírások nem egyenlők az utalványügyletekben, így a tranzakciókat nem lehet könyvelni. A téma a probléma javításának lépéseit is tartalmazza.

## <a name="symptom"></a>Tünet

Bizonyos esetekben a naplót nem lehet könyvelni, és a következő üzenet jelenik meg: „Egy adott bizonylaton szereplő tranzakciók egy bizonyos időpontban nem állnak egyensúlyban (számviteli pénznem: 0,01 - jelentési pénznem: 0,06).” Miért nem lehet a naplót kifüggeszteni?

## <a name="resolution"></a>Megoldás

A főkönyvi könyvelés során minden bizonylatot a tranzakció pénznemében, a könyvelési pénznemben és a beszámoló pénznemében kell kiegyenlíteni, ha ezek a pénznemek a **főkönyv beállítása** lapon meg vannak határozva. (Az utalványok akkor kerülnek egyensúlyba, ha a terhelések összege megegyezik a jóváírások összegével.)

A naplósorok lap alján az összegek a számviteli pénznemben és a jelentési pénznemben jelennek meg. A devizatranzakciók esetében **nem** jelennek meg a tranzakció pénznemében. Ezenkívül a felhasználók által a szimuláció vagy a könyvelés során kapott hibaüzenet csak a számviteli pénznemben és a beszámoló pénznemében mutatják a különbségeket. Nem a tranzakciós pénznemben jeleníti meg őket, mivel egyetlen utalványhoz több tranzakciós pénznem is tartozhat, és a napló különböző tranzakciós pénznemekben lévő utalványokat is tartalmazhat. Ezért fontos, hogy ellenőrizze, hogy a tranzakciós pénznemek összegei minden utalvány esetében kiegyensúlyozottak-e.

### <a name="transaction-currency"></a>Tranzakció pénzneme

A szimuláció és a könyvelés során a rendszer ellenőrzi, hogy minden utalvány a tranzakció pénznemében van-e kiegyenlítve. Minden egyes bevitt utalványhoz egy vagy több pénznemet lehet megadni a tranzakció pénznemeként. Például az általános naplóban rögzített bizonylatnak két tranzakciós pénzneme lehet, amikor egy eurót (EUR) használó bankszámláról egy kanadai dollárt (CAD) használó bankszámlára utalnak át készpénzt.

Ha egy utalványnak csak egy tranzakciós pénzneme van, a teljes terhelésnek meg kell egyeznie az adott utalvány teljes jóváírásával. Az ügyfelek a következő esetekkel találkoztak, amikor a könyvelés helyesen sikertelen volt, mert a tranzakció pénznemének összegei nem voltak kiegyenlítve:

- A teljes terhelés és a teljes jóváírás **nem** volt kiegyensúlyozott a tranzakció pénznemében, de a számviteli pénznem és a jelentési pénznem esetében igen. Egy ügyfél azt feltételezte, hogy az utalványt továbbra is feladják. Ez a feltételezés azonban téves volt. **Az utalványon szereplő tranzakciós pénznemek összegének mindig egyensúlyban kell lennie, ha az utalvány minden sora azonos pénznemmel rendelkezik.**
- Az utalványt a Microsoft Excel oldalon keresztül importálták, és a felhasználó úgy gondolta, hogy a tranzakció pénznemének összegei kiegyenlítettek. Az Excel-munkafüzetben az importált összegek **numerikus** értékként voltak beállítva, nem pedig **pénznemként**. Ebben a forgatókönyvben a munkafüzetben szereplő numerikus összegek több mint két tizedesjegyet tartalmaztak, és az összegek importálásakor több mint két tizedesjegy szerepelt. Ezért a terhelések nem egyeztek meg a jóváírásokkal, mert egy fillér töredékével tértek el. A napló nem tükrözte ezt a különbséget az utalvány soraiban, mivel a feltüntetett összegek csak két tizedesjegyet tartalmaznak.
- Az utalványt az Excel segítségével importálták, és a felhasználó úgy gondolta, hogy a tranzakciós pénznemek összegei kiegyensúlyozottak. Bár az utalvány kiegyensúlyozott volt, az utalvány egyes soraiban eltérő tranzakciós dátumok szerepeltek. Ha összeadta az összes terhelést és az összes jóváírást utalványonként és tranzakciós dátumonként, akkor nem voltak kiegyensúlyozottak. A rendszer mostantól megakadályozza ezt a forgatókönyvet. Egy utalványnak csak egy tranzakciós dátuma lehet. Ez a követelmény akkor érvényesül, amikor az utalványt a rendszer általános naplóján keresztül rögzíti. Eredetileg azonban nem volt érvényesítve, amikor egy utalványt az Excel segítségével importáltak.

Egy támogatott forgatókönyv szerint egy utalványhoz egynél több tranzakciós pénznem is tartozhat. Ebben az esetben a rendszer **nem** ellenőrzi, hogy a terhelések megegyeznek-e a jóváírásokkal a tranzakció pénznemében, mivel a pénznemek nem egyeznek. Ehelyett a rendszer ellenőrzi, hogy a számviteli pénznemek összegei egyensúlyban vannak-e.

### <a name="accounting-currency"></a>Könyvelési pénznem

Ha egy utalvány minden sora azonos tranzakciós pénznemmel rendelkezik, és ha a tranzakciós pénznemek összegei kiegyenlítettek, a rendszer ellenőrzi, hogy a könyvelési pénznemek összegei is kiegyenlítettek. Ha az utalványt külföldi pénznemben adják meg, az utalvány soraiban szereplő árfolyamot használják a tranzakció pénznemében megadott összegek számviteli pénznemre történő átszámításához. Először az utalvány minden egyes sorát lefordítjuk. Ezután a sorokat összeadjuk, hogy meghatározzuk a teljes terhelést és a teljes jóváírást. Mivel minden egyes sort lefordítanak, előfordulhat, hogy a teljes terhelés és a teljes jóváírás nem lesz egyensúlyban. Mindazonáltal, ha a különbözet a **főkönyvi paraméterek** lapon meghatározott **Maximális filléres különbözet** értékén belül van, az utalvány könyvelésre kerül, és a különbözet automatikusan a Filléres különbözet számlára kerül könyvelésre.

Ha az utalvány egynél több tranzakciós pénznemet tartalmaz, az utalvány minden egyes sorát át kell számítani a számviteli pénznemre, majd a sorokat össze kell adni a teljes terhelés és a teljes jóváírás meghatározásához. Ahhoz, hogy kiegyensúlyozottnak lehessen tekinteni, a terheléseknek és a jóváírásoknak egyensúlyban kell lenniük, és nem lehet filléres kerekítési különbség.

### <a name="reporting-currency"></a>Jelentési pénznem

Ha egy utalvány minden sora azonos tranzakciós pénznemmel rendelkezik, és ha a tranzakciós pénznemek összegei kiegyenlítettek, a rendszer ellenőrzi, hogy a jelentési pénznemek összegei kiegyenlítettek-e. Ha az utalványt külföldi pénznemben adják meg, az utalvány soraiban szereplő árfolyamot használják a tranzakció pénznemében megadott összegek beszámolási pénznemre történő átszámításához. Először az utalvány minden egyes sorát lefordítjuk. Ezután a sorokat összeadjuk, hogy meghatározzuk a teljes terhelést és a teljes jóváírást. Mivel minden egyes sort lefordítanak, előfordulhat, hogy a teljes terhelés és a teljes jóváírás nem lesz egyensúlyban. Mindazonáltal, ha a különbözet a **főkönyvi paraméterek** lapon meghatározott, a **jelentési pénznemben megadott maximális filléres kerekítésen** belül van, az utalvány könyvelésre kerül, és a különbözet automatikusan a Filléres különbözet számlára kerül könyvelésre.

Ha az utalvány egynél több tranzakciós pénznemet tartalmaz, az utalvány minden egyes sorát át kell számítani a jelentési pénznemre, majd a sorokat össze kell adni a teljes terhelés és a teljes jóváírás meghatározásához. Ahhoz, hogy kiegyensúlyozottnak lehessen tekinteni, a terheléseknek és a jóváírásoknak egyensúlyban kell lenniük, és nem lehet filléres kerekítési különbség.
