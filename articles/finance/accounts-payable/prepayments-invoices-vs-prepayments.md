---
title: Előlegszámlák és előlegek
description: Ez a témakör az előlegfizetéshez (előlegfizetéshez) használt két módszert írja le, illetve ellentételét adja meg a szervezetek számára.
author: abruer
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, PurchTable
audience: Application User
ms.reviewer: twheeloc
ms.custom: 15871
ms.assetid: a0bb5220-73d4-48ae-84d0-46a171c224fa
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 62f828b93075c134778da280243c0875edf99300
ms.sourcegitcommit: 0d5c07ba91a9ceb2eeb11db032fd28037216789d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/25/2022
ms.locfileid: "9715829"
---
# <a name="prepayment-invoices-vs-prepayments"></a>Előlegszámlák és előlegek

[!include [banner](../includes/banner.md)]

Ez a témakör az előlegfizetéshez (előlegfizetéshez) használt két módszert írja le, illetve ellentételét adja meg a szervezetek számára. Az egyik módszer létrehoz egy előlegszámlát, amely társítva van egy beszerzési rendeléssel. A másik módszer előlegnapló-bizonylatokat hoz létre, naplóbejegyzések létrehozásával és azok előlegnapló-bizonylatnak jelölésével.

Előfordulhat, hogy egyes szervezetek előlegeket (előzetes kifizetéseket) adnak ki szállítóknak árukért vagy szolgáltatásokért azok átvétele, illetve teljesítése előtt. Szállítói előlegek kiadására kétféle módszer használható. A kockázat minimálisra csökkentése érdekében az előleg beszerzési rendelésben való definiálásával nyomon követheti az előlegeket. Ehhez a módszerhez létre kell hoznia egy beszerzési rendeléshez társított előlegszámlát. A módszert előlegszámlázásnak nevezzük. Azok a szervezetek, amelyek nem kívánják az előlegeket ilyen szorosan nyomon követni vagy nem kapnak a szállítójuktól előlegszámlát, az előlegszámlázás módszere helyett használhatnak előlegnapló-bizonylatokat. Előlegnapló-bizonylatokat naplóbejegyzések létrehozásával és azok előlegnapló-bizonylatként való megjelölésével hozhat létre. Ezzel a módszerrel nem követhető, hogy mely szállítói előleg mely beszerzési rendelés alapján kerül kifizetésre. Azonban egy beszerzési rendelés alapján kiegyenlítésre jelölhet egy feladott előleget.

## <a name="when-to-use-prepayment-invoicing-vs-prepayments"></a>Előlegszámlázás és előlegek – mikor használjuk?

| Előlegszámlázás                                                                | Előlegek                                                              |
|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------|
| Az előleg értéke meg van határozva a beszerzési rendelésen.                                    | Nincs meghatározva az előleg értéke a beszerzési rendelésen.                    |
| Fel kell adni egy előlegszámlát és egy végleges számlát.                       | Nem kell feladni előlegszámlát.                                    |
| Az előlegfizetési kötelezettség az előlegszámlát, nem pedig a kötelezettségek számláját terheli. | Az előlegfizetési kötelezettség a kötelezettségek számláját terheli.                  |
| A folyamat során a szállítói egyenleg nem tükrözi az előleg értékét.     | A folyamat során a szállítói egyenleg tükrözi az előleg értékét. |
| Az előlegszámlázás csak a Kötelezettségekben érhető el.                         | Az előlegek a Kötelezettségekben és a Kinnlevőségekben is elérhetők.    |

## <a name="overview-of-the-prepayment-process"></a>Az előlegfizetési folyamat áttekintése
Számos ország/terület könyvelési gyakorlata megköveteli, hogy a vevőktől beérkező vagy a szállítóknak kifizetett előlegek (előzetes kifizetések) ne a vevő vagy szállító általános összegző számlájára kerüljenek. Ehelyett az előlegeket speciális, az előlegek számára fenntartott főkönyvi számlákra kell feladni. Ha értékesítési rendelést vagy beszerzési rendelést hoz létre, akkor a program kiállít egy vevő részére szóló vagy szállítótól származó számlát. A számla fizetésekor az előleg főkönyvi számláján rögzített előleg- és áfaelőleg-bizonylatot a program sztornírozza, és a számlaösszegeket automatikusan az általános összegző számlákra adja fel. Előleg létrehozásához kövesse az alábbi lépéseket:

1.  Állítsa be az előlegek feladási profiljait.
2.  A Kinnlevőségek paraméterei és Kötelezettségek paraméterei képernyőkön, a **Főkönyv és áfa** lehetőségen belül, válassza ki az új feladási profilt a **Feladási profil előleget tartalmazó fizetési naplóhoz** paraméter használatával.
3.  Hozzon létre egy kifizetési naplót, majd hozza létre az új kifizetést.
4.  A kifizetést megjelölheti előlegként. Ha a kifizetés előlegként van megjelölve, az az 1. és 2. lépésben beállított feladási profilban definiált főkönyvi számlákba kerül feladásra. Továbbá ha a kifizetés előlegként van megjelölve, a program kiszámítja az adókötelezettségeket. Egyes kormányzatok megkövetelik az adók kifizetését előleg rögzítésekor, még akkor is, ha nincs számla.
5.  Adja fel az előleget.
6.  Választható lehetőség: Kiegyenlítheti az előleget a számla létrehozása előtti a beszerzési vagy értékesítési rendelés ellenében. Az értékesítési rendelés vagy beszerzési rendelés lapon, a Művelet panelen, használja a **Tranzakciók kiegyenlítése** lehetőséget.
7.  Miután a szállító kézbesítette a terméket vagy szolgáltatást, rögzítse a számlát. Ha a 6. lépésben kiegyenlítette a beszerzési vagy értékesítési rendeléshez tartozó előleget, az a létrehozott számla alapján automatikusan kiegyenlítődik. Ha a nem egyenlítette ki az előleget a beszerzési rendelés vagy értékesítési rendelés alapján, manuálisan kiegyenlítheti azt a számla alapján a vevő vagy szállító oldalán, a **Tranzakciók kiegyenlítése** lehetőséggel. Az előleg összege ezután törlődik a kötelezettségek/kinnlevőségek ideiglenes főkönyvi számlájáról. Ezenkívül az esetlegesen kiszámított adók is törlődnek, mivel a tényleges adók megtalálhatók a számlán.

## <a name="overview-of-the-prepayment-invoicing-process"></a>Az előlegszámlázási folyamat áttekintése
Az előlegszámlák gyakoriak az üzleti gyakorlatban. A szállítók azért állítanak ki előlegszámlákat, hogy a beszerzési rendelés teljesítése előtt letétet követeljenek a beszerzéshez. Előfordulhat például, hogy néhány szállító előlegre tart igényt egyedi árukért vagy szolgáltatásokért. Ha egy szállító előleget igénylő számlát állít ki, használhatja az előlegszámlázási funkciót. A beszerzési rendelésben definiálhatja az előleg értékét, rögzítheti és kifizetheti az előlegszámlát, majd alkalmazhatja az előlegszámlát a végleges számlára. Előleg létrehozásához kövesse az alábbi lépéseket:

1.  A beszerzési ügynök létrehozza, megerősíti, majd elküldi a beszerzési rendelést, amelyre vonatkozóan a szállító előleget igényelt. Az előleg értékét a megállapodás szerint a beszerzési rendelés definiálja.
2.  A szállító elküld egy előlegszámlát.
3.  A szállítókoordinátorhoz rögzíti az előlegszámlát a beszerzési rendelés alapján, majd az előlegszámla kifizetésre kerül.
4.  A szállító kifizetési kérelmet küld, amelyre szabványos szállítói számlaként hivatkozunk. Miután a szállító kézbesítette az árut vagy szolgáltatást és megtörtént a szabványos szállítói számlák átvétele, a szállítókoordinátor alkalmazza a szabványos számla alapján már kifizetett előlegösszeget.
5.  A szállítókoordinátor kifizeti és kiegyenlíti a szabványos számla fennmaradó összegét.

## <a name="set-up-parameters-to-enable-the-prepayment-invoicing-process"></a>Paraméterek beállítása az előlegszámlázási folyamat engedélyezéséhez
Az előlegszámlát a **Készletkönyvelés** lap **Beszerzési rendelés** lapján kell definiálni (**Készletkezelés \> Beállítás \> Feladás \> Feladás**). Az előlegszámla az előlegszámla feladásakor frissül, általában terheléssel. Az előlegszámlán az egyenleg sztornírozva lesz, amikor az előlegszámlára alkalmazott szabványos számlát könyvelik. Ha az előlegszámlát nem egyenlíti ki egy kifizetésre, mielőtt az előlegszámlát a normál számlára alkalmazná, a könyvelt előlegszámláról származó könyvelési tételek sztornírozottak lesznek a normál számla könyvelésekor.

Az ellentételező összegző kötelezettségek számlája a **Szállító könyvelési** profiljában van definiálva. Az alapértelmezett könyvelési profil meghatározásához kattintson a **Kötelezettségek \> Beállítás \> Kötelezettségek paraméterei \> Főkönyv és áfa lap \> Profil feladása előrefizetett szállítói számlával**.

Az **Előlegfizetés alkalmazás házirendje** azt jelzi, hogy a rendszer automatikusan alkalmazza-e a kiegyenlített előlegszámlákat a manuálisan létrehozott végső számlára. Az adatbevitellel létrehozott számlák nem hivatkoznak az **Előleg alkalmazás házirendjére**. A kiegyenlített előlegszámlákat manuálisan kell alkalmazni az adatbevitel használatával létrehozott számlákra. A házirend meghatározásához válassza a **Kötelezettségek \> Beállítás \> Kötelezettségek paraméterei \> Főkönyv és áfa lap \> Előlegfizetés alkalmazási házirendje**. Ha az **Előlegfizetés alkalmazási házirend** mezője **Automatikus**, az előlegszámla automatikusan meg lesz jelölve kiegyenlítésre a végső számlával. Ha a mező **Értesítés** értékre van állítva, a végső számla létrehozásakor megjelenik egy vizuális jelzés, amely azt jelzi, hogy az előlegfizetési számla áll rendelkezésre alkalmazáshoz.

## <a name="create-a-purchase-order-that-contains-prepayment-invoice-information"></a>Előlegfizetési számla adatait tartalmazó beszerzési rendelés létrehozása
Amikor a szállító azt mondja, hogy a beszerzési rendelésen szereplő árukhoz és szolgáltatásokhoz előlegre van szükség, meg kell határoznia a kapcsolódó beszerzési rendeléshez tartozó előlegértéket. Ugrás a **Kötelezettségek \> Általános \> Beszerzési rendelések \> Összes beszerzési rendelés** elemre, és keresse meg a szállító beszerzési rendelését. A műveleti ablaktáblán válassza a **Beszerzés** lapot, és válassza ki az **Előlegfizetés** lehetőséget. Adja meg az előlegre vonatkozó információt, beleértve a leírást, az előleg értékét, hogy az előleg fix összeg vagy százalékos és az előleg kategória azonosítóját. 

Ne feledje, hogy a beszerzési rendelésen több előlegfizetés-definíció nem engedélyezett. Ha több előleget kell engedélyeznie egy beszerzési rendelésen, az előlegszámla helyett a kifizetési naplóval adja fel a kifizetéseket.

Az előleg eltávolítható a beszerzési rendelésből, kivéve, ha már kiegyenlített egy kifizetést a könyvelt előlegszámlával vagy a normál számlával szemben. Ha el szeretne távolítani egy előleginformációt a beszerzési rendelésből, válassza a **Kötelezettségek \> Általános \> Beszerzési rendelések \> Minden beszerzési rendelés** lehetőséget, és keresse meg a szállító beszerzési rendelését. A műveleti ablaktáblán válassza a **Beszerzés** lapot, és válassza ki az **Előleg eltávolítása** lehetőséget.

## <a name="create-and-post-a-prepayment-invoice"></a>Előlegszámla létrehozása és feladása
A szállító előlegszámlájának rögzítéséhez ugorjon a **Szállítói számla** lapra az **Előlegszámla** lehetőség kiválasztáséval a **Beszerzési rendelések** lapon (**Kötelezettségek \> Általános \> Beszerzési rendelések \> Minden beszerzési rendelés \> Számla lap \> Előlegszámla**). Az előlegszámlához tartozó információ megadása, többek között a számla számának megadása. Előlegszámla mennyisége nem módosítható. Ha a szállító a beszerzési rendelésen meghatározott előlegérték részleges összegét számlázta ki, frissítheti az egységárat a részleges értéknek megfelelően.

Az előlegszámla feladásakor a szállítói egyenleg és az előlegszámla frissítve lesz. A beszerzési rendelésen szereplő előlegdefinícióhoz tartozó **Előleg alkalmazása** is frissítve lesz. Az alapértelmezett pénzügyidimenzió-bejegyzések a feladott előlegbizonylathoz a beszerzési rendelés fejlécinformációiból származnak.

Ha be **van** **kapcsolva a Pénzügyi dimenziók zárolása a szállítói előlegszámla szolgáltatás számlasorainál a Funkciókezelés** lapon, akkor az előlegfejlécben vagy -sorokban szereplő dimenziók nem frissíthetők. 

## <a name="post-and-settle-payments-for-the-prepayment-invoice"></a>Előlegszámla kifizetéseinek feladása és kiegyenlítése
Ezután az előlegszámla kifizetése a történik a **Fizetési napló** lapon. A fizetési naplók eléréséhez kattintson a **Kötelezettségek \> Naplók \> Kifizetések \> Kifizetési napló** elemre . A kifizetés kiegyenlítésének az előlegszámlára történő feladása után a beszerzési rendelés **Fennmaradó alkalmazott előleg** értéke frissül.

Az előlegszámlához tartozó standard számla feladása előtt sztornírhatja a kifizetés kiegyenlítését az előlegszámláról. Ugyanakkor, miután a standard számla alkalmazva lett az előlegszámlára, a kifizetés kiegyenlítése nem sztornírozható az előlegszámláról.

## <a name="post-the-standard-vendor-invoice-for-the-purchase-order-and-apply-the-prepayment-invoice-to-the-standard-invoice"></a>A beszerzési rendelés szabványos szállítói számlájának feladása és az előlegszámla alkalmazása a normál számlára
Rögzítse a szállítótól kapott standard számlát. Ennek a folyamatnak a részeként alkalmazhatja a kiegyenlített előlegszámlát a szállítói számlára, hogy a számla értéke csökkenjen a már kifizetett összeggel. Az előlegszámla alkalmazása a szállítói számlára biztosítja, hogy az előlegszámláról származó könyvelési tételek sztornírozva legyenek.

## <a name="application-of-the-prepayment-invoice-after-posting-the-standard-invoice"></a>Az előlegszámla alkalmazása a standard számla feladása után
Ha a szállítói számla feladásakor elfelejti alkalmazni az előleget a standard szállítói számlára, a kiegyenlített előleg a elérhető lesz alkalmazásra a szállító egyéb számláira a **Szállítók** oldalon (**Kintlévőségek \> Általános \> Szállítók \> Összes szállító \> Számla lap \> Alkalmazás**).

## <a name="reversal-of-the-prepayment-application-process"></a>Az előleg alkalmazási folyamatának sztornírozása
Ha egy előlegszámla alkalmazását egy normál számláról kell visszavonnia vagy sztorníroznia, válassza a **Szállítók** lap **Sztornírozás** műveletét (**Kötelezettségek \> Általános \> Szállítók \> Minden szállító \> Számla lap \> Sztornírozás**). Az előlegalkalmazás sztornírzása után alkalmazhatja az előleget egy másik normál számlára. 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
