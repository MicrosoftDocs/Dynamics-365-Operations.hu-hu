---
title: "Előlegszámlák és előlegek"
description: "Ez a cikk leírásokat és összehasonlításokat tartalmaz a két módszerről, amelyeket a szervezetek használhatnak az előzetes kifizetésekhez (előlegek). Az egyik módszerben Ön létrehoz egy előlegszámlát, amely társítva van a beszerzési rendeléssel. A másik módszerben Ön előlegnapló-bizonylatokat hoz létre, naplóbejegyzések létrehozásával és azok előlegnapló-bizonylatnak jelölésével."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, PurchTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15871
ms.assetid: a0bb5220-73d4-48ae-84d0-46a171c224fa
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 44d51807cd6bb64ae2c4bef58d8a445417ffa3a9
ms.openlocfilehash: 770a6fba8a27e9403235929b7e8cd547cc522486
ms.lasthandoff: 03/31/2017


---

# <a name="prepayment-invoices-vs-prepayments"></a>Előlegszámlák és előlegek

Ez a cikk leírásokat és összehasonlításokat tartalmaz a két módszerről, amelyeket a szervezetek használhatnak az előzetes kifizetésekhez (előlegek). Az egyik módszerben Ön létrehoz egy előlegszámlát, amely társítva van a beszerzési rendeléssel. A másik módszerben Ön előlegnapló-bizonylatokat hoz létre, naplóbejegyzések létrehozásával és azok előlegnapló-bizonylatnak jelölésével.

Előfordulhat, hogy egyes szervezetek előlegeket (előzetes kifizetéseket) adnak ki szállítóknak árukért vagy szolgáltatásokért azok átvétele, illetve teljesítése előtt. Szállítói előlegek kiadására kétféle módszer használható. A kockázat minimálisra csökkentése érdekében az előleg beszerzési rendelésben való definiálásával nyomon követheti az előlegeket. Ehhez a módszerhez létre kell hoznia egy beszerzési rendeléshez társított előlegszámlát. A módszert előlegszámlázásnak nevezzük. Azok a szervezetek, amelyek nem kívánják az előlegeket ilyen szorosan nyomon követni vagy nem kapnak a szállítójuktól előlegszámlát, az előlegszámlázás módszere helyett használhatnak előlegnapló-bizonylatokat. Előlegnapló-bizonylatokat naplóbejegyzések létrehozásával és azok előlegnapló-bizonylatként való megjelölésével hozhat létre. Ezzel a módszerrel nem követhető, hogy mely szállítói előleg mely beszerzési rendelés alapján kerül kifizetésre. Azonban egy beszerzési rendelés alapján kiegyenlítésre jelölhet egy feladott előleget.

## <a name="when-to-use-prepayment-invoicing-vs-prepayments"></a>Előlegszámlázás és előlegek – mikor használjuk?
| Előlegszámlázás                                                                | Előlegek                                                              |
|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------|
| Az előleg értéke meg van határozva a beszerzési rendelésen.                                    | Nincs meghatározva az előleg értéke a beszerzési rendelésen.                    |
| Kulcs: Fel kell adni egy előlegszámlát és egy végleges számlát.                       | Nem kell feladni előlegszámlát.                                    |
| Az előlegfizetési kötelezettség az előlegszámlát, nem pedig a kötelezettségek számláját terheli. | Az előlegfizetési kötelezettség a kötelezettségek számláját terheli.                  |
| A folyamat során a szállítói egyenleg nem tükrözi az előleg értékét.     | A folyamat során a szállítói egyenleg tükrözi az előleg értékét. |
| Az előlegszámlázás csak a Kötelezettségekben érhető el.                         | Az előlegek a Kötelezettségekben és a Kinnlevőségekben is elérhetők.    |

## <a name="overview-of-the-prepayment-process"></a>Az előlegfizetési folyamat áttekintése
Számos ország/terület könyvelési gyakorlata megköveteli, hogy a vevőktől beérkező vagy a szállítóknak kifizetett előlegek (előzetes kifizetések) ne a vevő vagy szállító általános összegző számlájára kerüljenek. Ehelyett az előlegeket speciális, az előlegek számára fenntartott főkönyvi számlákra kell feladni. Ha értékesítési rendelést vagy beszerzési rendelést hoz létre, akkor a program kiállít egy vevő részére szóló vagy szállítótól származó számlát. A számla fizetésekor az előleg főkönyvi számláján rögzített előleg- és áfaelőleg-bizonylatot a program sztornírozza, és a számlaösszegeket automatikusan az általános összegző számlákra adja fel. Előleg létrehozásához kövesse az alábbi lépéseket:

1.  Állítsa be az előlegek feladási profiljait.
2.  A Kinnlevőségek paraméterei és Kötelezettségek paraméterei képernyőkön, a **Főkönyv és áfa** lehetőségen belül, válassza ki az új feladási profilt a **Feladási profil előleget tartalmazó fizetési naplóhoz** paraméter használatával.
3.  Hozzon létre egy kifizetési naplót, majd hozza létre az új kifizetést.
4.  A kifizetést megjelölheti előlegként. A kifizetés előlegként meg van jelölve, ha a fizetés feladása a feladási profil beállítása 1 és 2 lépésben meghatározott főkönyvi számlákra. Továbbá ha a kifizetés előlegként megjelölt, adók számítják ki. Egyes kormányzatok megkövetelik az adók kifizetését előleg rögzítésekor, még akkor is, ha nincs számla.
5.  Adja fel az előleget.
6.  Választható lehetőség: Is egyenlíti ki a beszerzési vagy értékesítési rendelés ellen az előleget a számla létrehozása előtt. Az értékesítési rendelés vagy beszerzési rendelés lapon a leggyakrabban használja **tranzakciók kiegyenlítése**.
7.  Miután a szállító kézbesítette a terméket vagy szolgáltatást, rögzítse a számlát. Ha a 6. lépésben kiegyenlítette a beszerzési vagy értékesítési rendeléshez tartozó előleget, az a létrehozott számla alapján automatikusan kiegyenlítődik. Ha a nem egyenlítette ki az előleget a beszerzési rendelés vagy értékesítési rendelés alapján, manuálisan kiegyenlítheti azt a számla alapján a vevő vagy szállító oldalán, a **Tranzakciók kiegyenlítése** lehetőséggel. Az előleg összege ezután törlődik a kötelezettségek/kinnlevőségek ideiglenes főkönyvi számlájáról. Ezenkívül az esetlegesen kiszámított adók is törlődnek, mivel a tényleges adók megtalálhatók a számlán.

## <a name="overview-of-the-prepayment-invoicing-process"></a>Az előlegszámlázási folyamat áttekintése
Az előlegszámlák gyakoriak az üzleti gyakorlatban. A szállítók azért állítanak ki előlegszámlákat, hogy a beszerzési rendelés teljesítése előtt letétet követeljenek a beszerzéshez. Előfordulhat például, hogy néhány szállító előlegre tart igényt egyedi árukért vagy szolgáltatásokért. Ha egy szállító előleget igénylő számlát állít ki, használhatja az előlegszámlázási funkciót. A beszerzési rendelésben definiálhatja az előleg értékét, rögzítheti és kifizetheti az előlegszámlát, majd alkalmazhatja az előlegszámlát a végleges számlára. Előleg létrehozásához kövesse az alábbi lépéseket:

1.  A beszerzési ügynök létrehozza, megerősíti, majd elküldi a beszerzési rendelést, amelyre vonatkozóan a szállító előleget igényelt. Az előleg értékét a megállapodás szerint a beszerzési rendelés definiálja.
2.  A szállító elküld egy előlegszámlát.
3.  A szállítókoordinátorhoz rögzíti az előlegszámlát a beszerzési rendelés alapján, majd az előlegszámla kifizetésre kerül.
4.  Miután a szállító kézbesítette az árut vagy szolgáltatást és megtörtént a kapcsolódó szállítói számlák átvétele, a szállítókoordinátor alkalmazza a számla alapján már kifizetett előlegösszeget.
5.  A szállítókoordinátor kifizeti és kiegyenlíti a számla fennmaradó összegét.



