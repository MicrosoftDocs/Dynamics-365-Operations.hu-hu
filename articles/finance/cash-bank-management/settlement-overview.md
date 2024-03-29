---
title: Kiegyenlítés – áttekintés
description: Ez a cikk a rendezési folyamat általános ismertetését tartalmazza. Leírja, hogy mely tranzakciótípusok kiegyenlítése lehetséges, és milyen ütemezés és folyamat tartozik a kiegyenlítésükhöz. Ez a kiegyenlítési folyamat eredményeit is leírja.
author: angelad116
ms.date: 07/30/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: kfend
ms.custom:
- "14551"
- intro-internal
ms.assetid: 0968fa71-5984-415b-8689-759a0136d5d1
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 343802b409363f2698f857f3fc0e2682b48fec92
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151222"
---
# <a name="settlement-overview"></a>Kiegyenlítés áttekintése

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


Ez a cikk a rendezési folyamat általános ismertetését tartalmazza. Leírja, hogy mely tranzakciótípusok kiegyenlítése lehetséges, és milyen ütemezés és folyamat tartozik a kiegyenlítésükhöz. Ez a kiegyenlítési folyamat eredményeit is leírja.

Kiegyenlítés során az egy bizonylaton található tranzakciók alkalmazásra kerülnek egy másik bizonylaton található tranzakciókhoz, hogy az egyes bizonylatok egyenlegét növeljék vagy csökkentsék. Például egy kifizetés alkalmazható egy számlához. Számos tranzakció-típus egyenlíthető ki különböző időkben és különböző módokon. A kiegyenlítési folyamat járhat továbbá új tranzakciók létrehozásával.

## <a name="what-transactions-can-be-settled"></a>Mely tranzakciók egyenlíthetőek ki

A kötelezettségeken vagy kinnlevőségeken belüli kiegyenlítések létrejöhetnek bármely tranzakció-típus között, amely hatással van a szállítói egyenlegre vagy vevői egyenlegre. Ilyen típusú tranzakciótípusok lehetnek számlák, kifizetések, jóváírások és díjak. Bármely tranzakció-típus kiegyenlíthető bármely egyéb tranzakció-típussal Például kiegyenlíthet egy kifizetést egy számlával, egy jóváírást egy számlával, egy számlát egy másik számlával vagy egy kifizetést egy másik kifizetéssel.

Kiegyenlíthet kifizetést egy tranzakcióval ugyanazon jogi személyben vagy más jogi személyben. A szervezetekben, amelyek központosított kifizetési modellt használnak a [központosított kifizetések](set-up-centralized-payments.md) elem segíthet a kifizetési folyamat hatékonyabbá tételében.

## <a name="when-to-settle-transactions"></a>Mikor történik a tranzakciók kiegyenlítése

A tranzakciók kiegyenlítése a fizetés bevitelekor történhet. Például, amikor létrehoz egy kifizetést egy szállítónak, akkor általában kiválasztja a kifizetendő számlákat. A számlák kijelölésével megjelöli őket kiegyenlítésre a kifizetés számára. Amikor egy kinnlevőség-kifizetés ügyintéző rögzít egy vevői kifizetés, akkor megjelölik a megfelelő számlákat kiegyenlítésre, az egyes vevői kifizetésekben szereplő adatok alapján. A **Tranzakciók kiegyenlítése** lapot használhatja a tranzakciók megjelöléséhez kiegyenlítéshez. Ezt a lapot megnyithatja bármely feladatlan számlából vagy kifizetésből. Amikor a tranzakció feladásra kerül, akkor a kiegyenlítés is feladásra kerül. 

A tranzakciók kiegyenlíthetőek továbbá a feladásuk után. Megadhat és feladhat egy vevői kifizetést anélkül, hogy kiegyenlítene vele bármilyen számlát. Előfordulhat azonban, hogy szeretne meggyőződni arról, hogy a kifizetés a megfelelő számlát egyenlíti ki, mielőtt feladná a kiegyenlítést. A **Tranzakciók kiegyenlítése** lap megnyitható az **Összes vevő** vagy **Összes szállító** lapról, vagy a **Tranzakciók** lapról bármely vevőhöz, vagy szállítóhoz.

Lefoglalhat továbbá feladott előlegeket egy számlához a megjelölve a kifizetést a beszerzési rendelés vagy értékesítési rendelés kiegyenlítéséhez. Ebben az esetben a kifizetés továbbra is nyílt egyenleggel fog rendelkezni, de nem lehet majd vele más számlát kiegyenlíteni. A kifizetés automatikusan a beszerzési rendelésből vagy értékesítési rendelésből létrejött számla kiegyenlítéséhez lesz felhasználva.

## <a name="how-to-settle-transactions"></a>Hogyan történik a tranzakciók kiegyenlítése

A tranzakciók kiegyenlíthetőek manuálisan, automatikusan, vagy a két módszer kombinálásával. Az kiegyenlítési mód kiválasztása az üzleti folyamataitól függ. A **Kötelezettségek paraméterei** és a **Kinnlevőségek paraméterei** lapokon konfigurálhatja a kiegyenlítési folyamatot úgy, hogy az megfeleljen azoknak az üzleti folyamatoknak.

Létrehozhat szállítói kifizetéseket és vevői közvetlen levonás kifizetéseket egy kifizetési ajánlat használatával. A fizetési javaslat a kifizetendő számlák kiválasztására szolgál. A kifizetési ajánlat manuálisan van elindítva, azonban azután a rendszer automatikusan megjelöli a kijelölt számlákat kiegyenlítésre, amikor a kifizetések létrejönnek.

Ha a kifizetéseket manuálisan hozza létre, akkor használhatja a **Tranzakciók kiegyenlítése** lapot, hogy kiválassza a kiegyenlítendő számlákat. Manuálisan kiválaszthatja a számlákat vagy használhatja a **Megjelölés prioritás szerint** opciót, hogy a számlákat automatikusan megjelölje kiegyenlítéshez. A **Megjelölés prioritás szerint** beállítás csak a kinnlevőségek számára érhető el. Ezt a beállítást a **Kinnlevőségek paraméterei** lap **Kiegyenlítési rangsorolása** lapján állíthatja be.

Ha egy kifizetési ügynök rögzít egy kifizetés, de nem egyenlíti ki a kifizetést mielőtt feladná, akkor a kifizetés kiegyenlíthető automatikusan. Bekapcsolhatja az automatikus kiegyenlítést a **Kinnlevőségi paraméterek** és **Kötelezettségi paraméterek** helyeken. Az automatikus kiegyenlítés csak ugyanabban a jogi személyben egyenlíti ki a tranzakciókat. Nem egyenlíti ki a tranzakciókat több jogi személy között.

Amikor az automatikus kiegyenlítést használja, akkor használhatja az előre meghatározott kiegyenlítési rangsort, vagy meghatározhatja a saját kiegyenlítési rangsorát a **Kinnlevőségi paraméterek** oldalon. Ez a funkció csak a kinnlevőségek számára érhető el.

## <a name="results-of-settlement"></a>A kifizetés eredménye

Ahogy a tranzakciók kifizetésre kerülnek az egyes tranzakciók hátralékos egyenlege növekszik vagy csökken a megfelelő mértékben. Általánosságban, ahol egy számla és kifizetés kerül kiegyenlítésre az egyes tranzakciók állapota és egyenlege a következő szabályoknak megfelelően frissül:

- Ha a kifizetés összege több mint a számla összege, akkor a számla egyenlege 0,00-ra csökken és a számla lezárul. A kifizetés nyitva marad és az egyenlege az a kifizetés összege és a számla összege közötti különbség lesz.
- Ha a kifizetés összege kevesebb mint a számla összege, akkor a kifizetés egyenlege 0,00-ra csökken és a kifizetés lezárul. A számla nyitva marad és az egyenlege az a számla összege és a kifizetés összege közötti különbség lesz.
- Ha a kifizetés összege egyenlő a számla egyenlegével, akkor a számla és a kifizetés is lezárul és mindkettő egyenlege 0,00-ra csökken.

Ha a [kifizetés összege kevesebb mint a számla összege](../accounts-payable/vendor-payments-partial-amount.md) egy készpénzfizetési engedmény, leírás vagy alulfizetés miatt, akkor a számla és a kifizetés még mindig lezárható, a kiegyenlítés beállításaitól függően a **Kötelezettség paraméterek** és a **Kinnlevőségi paraméterek** lapokon.

A kiegyenlítések létre is hozhatnak tranzakciókat. Például egy számla és kifizetés kiegyenlítése létrehozhat készpénzfizetés engedményt, realizált nyereséget vagy veszteséget, áfakorrekciókat, leírásokat vagy fillérkülönbözeteket.

## <a name="identifying-marked-transactions-during-settlement"></a>Megjelölt tranzakciók azonosítása a kiegyenlítés során

Ha megpróbál kiegyenlíteni egy tranzakciót, akkor észrevehet egy szimbólumot, amely azt jelzi, hogy a tranzakció egy másik helyen meg van jelölve. Ebben az esetben kiválaszthatja a tranzakciót a **Tranzakciók kiegyenlítése** lapon, majd választhatja a **Lekérdezés \> Kiegyenlítés a kiegyenlítés ablakból** lehetőséget. A lekérdezés nézete azokat a naplókat, értékesítési rendeléseket, számlákat, fizetési javaslatokat és vevői helyeket jeleníti meg, amelyek a tranzakció kiegyenlítését blokkolhatják. A probléma megoldásához a hivatkozás kiválasztásával a lekérdezésből közvetlenül a zárolt helyre ugorhat. Ezután frissítheti a dokumentumot a kiegyenlítéséhez szükséges módosításokkal. A **Megjelölt** jelölő segítségével azonosíthat más dokumentumokat is, amelyek ugyanazon a blokkolási helyen szerepelnek.

## <a name="resolve-issues-with-transactions-that-cant-be-settled"></a>A nem rendezhető tranzakciókkal kapcsolatos problémák megoldása

Előfordul, hogy azért nem tudja rendezni a tranzakciókat, mert egy másik tevékenység éppen feldolgozza a dokumentumot. Ha megpróbálja kiegyenlíteni a tranzakciókat, hiba lép fel, mert ezeket a tranzakciókat használják. A probléma megoldásához a **Megjelölt tranzakciók részletei** lap segítségével megkeresheti az elszámolásra megjelölt tranzakciókat, és azonosíthatja az azokat elérő egyéb folyamatokat.

A tranzakciókat akkor jelölik ki elszámolásra, amikor a szállítói számlák kifizetése folyamatban van, vagy amikor az ügyfelek kifizetik a nyitott számláikat. Előfordulhat, hogy ezek a számlák már elszámolásra megjelöltek. Ezért a felhasználók nem választhatják ki őket fizetésre. A számlákat jelölheti egy másik ügyfélfizetési napló, értékesítési megbízás, szállítói fizetési napló vagy beszerzési megbízás a jelenlegi vagy egy másik jogi személynél.

Ha egy tranzakciót az ügyfélfizetés rögzítésekor blokkolnak elszámolásra, nyissa meg az **Ügyfél megjelölt tranzakció adatai** oldalt **(Követelések \> Időszakos feladatok \> Ügyfél megjelölt tranzakció adatai**). Annak gyors azonosításához, hogy hol van blokkolva egy tranzakció, a következő kiválasztási paraméterek bármelyikét beállíthatja: **Ügyfélszámla**, **Utalvány**, **Dátum** vagy **Számla**. Ha nem állít be semmilyen kiválasztási paramétert, a rendszer az aktuális vagy egy másik kiválasztott vállalat összes zárolt dokumentumát megjeleníti. Miután azonosította az elszámolásra zárolt tranzakciót, kijelölheti azt, majd válassza a **Kijelölt tranzakciók jelölésének feloldása** lehetőséget. A kiválasztott tranzakciót ezután a rendszer eltávolítja minden olyan naplóból, amely tartalmazza azt. A dokumentum azonban nem kerül eltávolításra a másik helyről. A naplóból csak a jelölési információk kerülnek eltávolításra.

Ha a szállítói kifizetés rögzítésekor egy tranzakciót blokkolnak elszámolásra, nyissa meg a **Szállítóval megjelölt tranzakció adatai** oldalt **(Fizetendő számlák \> Időszakos feladatok \> Szállítóval megjelölt tranzakció adatai**). Annak gyors azonosításához, hogy hol van egy tranzakció blokkolva, beállíthatja a következő kiválasztási paraméterek bármelyikét: **szállítói számla**, **bizonylat**, **dátum** vagy **számla**. Ha nem állít be semmilyen kiválasztási paramétert, a rendszer az aktuális vagy egy másik kiválasztott vállalat összes zárolt dokumentumát megjeleníti. Miután a tranzakciót azonosította, kijelölheti azt, majd a **Kijelölt tranzakciók kijelölésének megszüntetése** opciót választhatja a blokkolási probléma megoldásához. A kiválasztott tranzakciót ezután a rendszer eltávolítja minden más naplóból, ahol az ki van jelölve. A dokumentum azonban nem kerül eltávolításra a másik helyről. A naplóból csak a jelölési információk kerülnek eltávolításra.

Az összes zárolt dokumentum azonosításához nyissa meg a **Minden megjelölt tranzakció részletei** oldalt **(Követelések \> Időszakos feladatok \> Minden megjelölt tranzakció részletei** vagy **Fizetendő számlák \> Időszakos feladatok \> Minden megjelölt tranzakció részletei**). Annak gyors azonosításához, hogy hol van egy tranzakció blokkolva, beállíthatja a következő kiválasztási paraméterek bármelyikét: **Ügyfélszámla**, **Szállítói számla**, **Bizonylat**, **Dátum** vagy **Számla**. Ha nem állít be semmilyen kiválasztási paramétert, a rendszer az aktuális vagy egy másik kiválasztott vállalat összes zárolt dokumentumát megjeleníti. Miután a tranzakciót azonosította, kijelölheti azt, majd a **Kijelölt tranzakciók kijelölésének megszüntetése** opciót választhatja a blokkolási probléma megoldásához. A kiválasztott tranzakciót ezután a rendszer eltávolítja minden más naplóból, ahol az ki van jelölve. A dokumentum azonban nem kerül eltávolításra a másik helyről. A naplóból csak a jelölési információk kerülnek eltávolításra.

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a **Funkciókezelés** munkaterületet a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A funkció a következő módon jelenik meg:

- **Modul:** Készpénz- és bankkezelés
- **Jellemző neve:** Megjelölt tranzakció részletező űrlap

## <a name="additional-resources"></a>További erőforrások

- [Hátralék kiegyenlítése](settle-remainder.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
