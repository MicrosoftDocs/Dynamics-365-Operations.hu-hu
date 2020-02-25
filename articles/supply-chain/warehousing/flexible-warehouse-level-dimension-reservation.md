---
title: Rugalmas raktárszintű dimenziófoglalási irányelv
description: Ez a témakör azt mutatja be, hogy a készletfoglalási irányelv, amely lehetővé teszi, hogy a kötegelt nyomon követésű termékeket értékesítő és a logisztikát a WMS-kompatibilis műveletekekként futtató vállalatok lefoglaljanak bizonyos kötegeket ügyfelek értékesítési rendeléseihez, még akkor is, ha a foglalási hierarchia a termékekhez kapcsolódóan nem engedélyezi a meghatározott kötegek foglalását.
author: omulvad
manager: AnnBe
ms.date: 02/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReservationHierarchy
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2020-01-15
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: c0baf96315dd9fe6bc1984d337fd1c50ae47016a
ms.sourcegitcommit: 4e62c22b53693c201baa646a8f047edb5a0a2747
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/07/2020
ms.locfileid: "3031043"
---
# <a name="flexible-warehouse-level-dimension-reservation-policy"></a>Rugalmas raktárszintű dimenziófoglalási irányelv

[!include [banner](../includes/banner.md)]

Amikor egy „kötegalatti\[hely\]” típusú készlet foglalási hierarchiája termékekhez van társítva, a kötegelt nyomon követéssel ellátott termékeket értékesítő és a logisztikai műveleteiket a Microsoft Dynamics 365 raktározási rendszerrel (WMS) kompatibilisként futtató vállalatok nem foglalhatják le az illető termékek konkrét kötegeit ügyfelek értékesítési rendeléseihez. Ez a témakör bemutatja azt a készletfoglalási irányelvet, amely alapján a vállalatok meghatározott kötegeket foglalhatnak le, még akkor is, ha a termékek a „kötegalatti\[hely\]” foglalási hierarchiával vannak társítva.

## <a name="inventory-reservation-hierarchy"></a>Készletfoglalási hierarchia

Ez a szakasz összegzi a meglévő készletfoglalási hierarchiát. A program a kötegelt nyomon követéssel és a sorozatszámmal kezelt cikkek kezelési módjára koncentrál.

A készletfoglalási hierarchia azt írja elő, hogy a tárolási dimenziókat illetően az igény szerinti rendelés a hely, a raktár és a készlet állapotának kötelező dimenzióit hordozza. A raktári logika felelős azért, hogy a kívánt mennyiségekhez helyet rendeljen, és lefoglalja azt. Más szóval az igény szerinti rendelés és a raktári műveletek közötti interakciókban várhatóan az igény szerinti rendelése jelzi, hogy honnan kell szállítani a rendelést (azaz a helyet és a raktárat). A raktár ezután saját logikájára alapozva megkeresi a szükséges mennyiséget a raktár területén.

Ha azonban az üzlet műveleti modelljét szeretné tükrözni, a nyomonkövetési dimenziók esetén (köteg-és sorozatszámok) nagyobb rugalmasságra van szükség. A készletfoglalási hierarchia olyan esetekhez használható, amelyekben teljesülnek az alábbi feltételek:

- A vállalat a raktári műveletei alapján kezeli a köteg-vagy sorozatszámmal ellátott mennyiségek kiválasztását, miután a mennyiségeket a rendszer megtalálta a raktározási tárolóhelyen. Ezt a modellt gyakran nevezzük *kötegalatti\[helynek\]*. Ezt általában akkor használják, ha a termék köteg- vagy sorozatszám-azonosítója nem fontos azoknak a vevőknek, akik a rendelést tették az értékesítő vállalatnál.
- Ha a köteg-vagy sorozatszámok a vevői rendelési specifikáció részei, és a program rögzíti azokat az igény szerinti rendelésen, akkor a raktári műveleteket, amelyek megkeresik a raktárban lévő mennyiségeket, az egyes igényelt számokkal korlátozni lehet, és azok nem módosíthatók. Ezt a modellt nevezzük *kötegfeletti\[helynek\]*.

Ezekben az esetekben a kihívás az, hogy csak egyetlen készletfoglalási hierarchiát lehet hozzárendelni az egyes kiadott termékekhez. Ezért ahhoz, hogy WMS kezelje a nyomon követett cikkeket, miután a hierarchia-hozzárendelés meghatározza, hogy mikor kell lefoglalni a köteg-vagy sorozatszámot (vagy az igény szerinti rendelés fogadásakor, vagy a raktári kitárolási munka során), ez az időzítés nem módosítható ad hoc módon.

## <a name="flexible-reservation-for-batch-tracked-items"></a>Rugalmas foglalás a kötegelten nyomon követett cikkeknél

### <a name="business-scenario"></a>Üzleti eset

Ebben a helyzetben a vállalat egy készletstratégiát alkalmaz, amelyben a késztermékeket a kötegszámokkal követi nyomon. Ez a vállalat is a WHS terhelést használja. Mivel ez a terhelés jól felszerelt logikával rendelkezik a raktári kitárolási és fuvarozási műveletek tervezéséhz és lefuttatásához kötegelésre engedélyezett elemek esetén, a kész cikkek többsége a „kötegalatti\[hely\]” készletfoglalási hierarchiához van társítva. Ennek a működési beállításnak az az előnye, hogy a döntéseket (amelyek valójában foglalási döntések) arról, hogy mely kötegeket kell kiválasztania, és hová kell tenni őket a raktárban, elhalasztják, amíg el nem kezdődnek a raktári kitárolási műveletek. Nem akkor jönnek létre, amikor az ügyfél rendel.

Bár a „kötegalatti\[hely\]” foglalási hierarchia jól szolgálja a vállalat üzleti céljait, a vállalatok ügyfeleinek többsége termékek újrarendelésekor ugyanazt a köteget kéri, amelyet már egyszer megvásárolt. A vállalatnak ezért rugalmasságra van szüksége a kötegelt foglalási szabályok kezelésében, hogy az ugyanazon tétel vevői igényének függvényében a következők történjenek:

- A kötegszám rögzíthető és lefoglalható, amikor a rendelést az értékesítési feldolgozó átveszi, és a raktári műveletek és/vagy más igények során nem módosítható. Ez a viselkedés segít annak biztosításában, hogy a megrendelt kötegszámot szállítsák az ügyfélnek.
- Ha a kötegszám nem fontos a vevő számára, akkor a raktári műveletek a kitárolási munka során meghatározhatják a kötegszámot az után, hogy az értékesítési rendelés regisztrálása és a foglalás megtörtént.

### <a name="allowing-reservation-of-a-specific-batch-on-the-sales-order"></a>Konkrét köteg foglalásának engedélyezése az értékesítési rendelésen

A „kötegalatti\[hely\]” foglalási hierarchiához társított cikkek kötegelt foglalási viselkedésében szükséges rugalmasság elérése érdekében a **Készletfoglalási hierarchiák lapon** a készletkezelőnek be kell jelölnie az **Foglalás engedélyezése igény szerinti foglalásra** jelölőnyégyzetet a **Köteg száma** szinten.

![A készletfoglalási hierarchia rugalmassá tétele](media/Flexible-inventory-reservation-hierarchy.png)

Ha a hierarchiában kiválasztja a **Kötegszám** szintjét, akkor a program automatikusan kijelöli az illető szint fölötti és a **Hely** szintjén található összes dimenziót. (Alapértelmezetten szerint a **Hely** szint fölötti összes dimenzió előre be van jelölve.) Ez a viselkedés azt a logikát jelzi, amely szerint a kötegszám és a hely közötti tartományban található összes dimenziót a program automatikusan lefoglalja, miután a felhasználó lefoglalt egy meghatározott kötegszámot a rendelési sorban.

> [!NOTE]
> A **Foglalás engedélyezése igény szerinti rendelésnél** jelölőnégyzet csak a raktári hely dimenzió alatti foglalási hierarchia szintjére vonatkozik.
>
> A **Kötegszám** a hierarchia egyetlen olyan szintje, amely nyitott a rugalmas foglalási irányelv számára. Más szóval nem jelölheti be a **Foglalás engedélyezése igény szerinti rendelésnél** jelölőnégyzetet a **Hely**, **Rendszámtábla** vagy **Sorozatszám** szinteken.
>
> Ha a foglalási hierarchiában szerepel a sorozatszám dimenzió (amelynek mindig a **Kötegszám** szint alatt kell lennie), és ha bekapcsolta a kötegszám-specifikus foglalást,, a rendszer továbbra is a sorozatszám szerinti foglalási és kitárolási műveleteket fogja kezelni a „sorszámalatti\[hely\]” foglalási irányelvre vonatkozó szabályok alapján.

A telepítés során bármikor engedélyezheti a kötegspecifikus foglalást egy létező „kötegalatti\[hely\]” foglalási hierarchiában a telepítésben. A módosítás nem fogja érinteni a módosítás előtt létrehozott foglalásokat és nyitott raktári munkákat. Azonban a **Foglalás engedélyezése az igény szerinti rendelésnél** jelölőnégyzetet nem lehet törölni, ha az adott foglalási hierarchiához társított egy vagy több cikk esetén a **Foglalt rendelt**, **Foglalt tényleges** vagy **Megrendelve** típusú problémák készlettranzakciói léteznek.

> [!NOTE]
> Ha egy elem meglévő foglalási hierarchiája nem teszi lehetővé a köteg megadását a rendelésen, akkor újra hozzárendelheti azt egy olyan foglalási hierarchiához, amely lehetővé teszi a köteg megadását, feltéve, hogy a hierarchia szintjének szerkezete mindkét hierarchiában ugyanaz. Az ismételt hozzárendeléshez használja a **Cikkek foglalási hierarchiájának módosítása** funkciót. Ez a módosítás akkor lehet fontos, ha el akarja kerülni a rugalmas kötegelt rendelést a kötegelt nyomonkövetésű cikkek egy csoportja esetén, azonban engedélyezni akarja azt a termékportfólió többi eleme számára.

Függetlenül attól, hogy bejelölte-e a **Foglalás engedélyezése igény szerinti rendelésnél** jelölőnégyzetet, ha a rendelési sorban nem szeretne lefoglalni egy konkrét kötegszámot, az alapértelmezett, „kötegalatti\[hely\]” foglalási hierarchia esetében érvényes raktárműveleti logika lép érvénybe.

### <a name="reserve-a-specific-batch-number-for-a-customer-order"></a>Konkrét kötegszám foglalása egy vevői rendeléshez

Ha egy kötegelt nyomonkövetésű elem „kötegalatti\[hely\]” típusú készle foglalási hierarchiája úgy van beállítva, hogy engedélyezze az értékesítési rendeléseken a konkrét kötegszám foglalását, akkor az értékesítési rendelések feldolgozói a vevői igényektől függően a következő módokon vehetik fel a vevői rendeléseket ugyanarra a tételre:

- **Rendelés részleteinek megadása a kötegszám megadása nélkül** – ezt a megközelítést akkor kell használni, ha a termékköteg megadása nem fontos a vevő számára. Az ilyen típusú rendelések kezelésével kapcsolatos összes meglévő folyamat változatlan marad. A felhasználók részéről nem szükséges további megfontolás.
- **Rendelés részleteinek megadása és egy konkrét kötegszám lefoglalása** – ezt a megközelítést akkor kell használni, ha a vevő egy konkrét köteget kér. A vevők általában akkor kérnek egy konkrét köteget, ha egy korábban vásárolt terméket rendelnek újra. Ezt a típusú kötegspecifikus foglalást nevezik *Rendelésben véglegesített foglalásnak*.

A következő szabályok érvényesek a mennyiségek feldolgozásakor, ha a köteg számát egy konkrét rendeléshez kötötték:

- Ha engedélyezni szeretné egy konkrét kötegszám foglalását a „kötegalatti\[hely\]” foglalási hierarchiában, a rendszernek a hely dimenzióig minden dimenziót le kell foglalnia. Ez a tartomány általában a rendszámtábla dimenziót tartalmazza.
- A hely irányelvei nem használatosak, amikor olyan értékesítési sorhoz hozza létre a kitárolási munkát, amely rendelésben véglegesített kötegfoglalást használ.
- A rendelésben véglegesített kötegfoglaláshoz tartozó munka raktári feldolgozása során sem a felhasználó, sem a rendszer nem módosíthatja a kötegszámot. (Ez a feldolgozás tartalmazza a kivételek kezelését.)

A következő példa bemutatja a végpontok közötti áramlást.

## <a name="example-scenario"></a>Példaforgatókönyv

Ebben a példában a bemutatóadatokat kell telepíteni, és az **USMF** demó-adatvállalatot kell használnia.

### <a name="set-up-an-inventory-reservation-hierarchy-to-allow-batch-specific-reservation"></a>Hozzon létre egy készletfoglalási hierarchiát, hogy lehetővé tegye a kötegspecifikus foglalást

1. Nyissa meg a **Raktárkezelés** \> **Beállítás** \> **Készlet \> Foglalási hierarchia** lehetőséget.
2. Válassza az **Új** lehetőséget.
3. Adja meg a feladat egyedi nevét a **Név** mezőben (pl. **BatchFlex**).
4. A **Leírás** mezőben adjon meg egy leírást (például: **Rugalmas alatti kötteg**).
5. A **Kijelölve** mezőben válassza ki a **Sorozatszám** és a **Tulajdonos** lehetőségeket, majd a bal nyílgombra kattintva helyezze át őket a **Rendelkezésre áll** mezőbe.
6. Válassza ki az **OK** lehetőséget.
7. A **Kötegszám** dimenzió szintjének sorában jelölje be a **Foglalás engedélyezése igény szerinti rendelésnél** jelölőnégyzetet. A **Rendszámtábla** és a **Hely** szintje automatikusan be van jelölve, és a jelölőnégyzetek nem törölhetők.
8. Válassza a **Mentés** lehetőséget.

### <a name="create-a-new-released-product"></a>Új kiadott termék létrehozása

1. Adja meg a termék három alapadat-paraméterét az alábbi értékeket használva:

    - A **Tárolási dimenziócsoport** mezőben válassza a **Raktár** lehetőséget.
    - A **Nyomon követési dimenziócsoport** mezőben válassza a **Batch-Phy** lehetőséget.
    - A **Foglalási hierarchia** mezőben válassza ki a **BatchFlex** lehetőséget.

2. Hozzon létre két kötegszámot, például **B11** és **B22**.
3. Az alábbi értékek használatával adjon hozzá cikkmennyiségeket az aktuális készlethez.

    | Raktár | Köteg száma | Helyszín | Azonosítótábla | Mennyiség |
    |-----------|--------------|----------|---------------|----------|
    | 24        | B11          | BULK-001 | Egyik sem          | 10       |
    | 24        | B11          | FL-001   | LP11          | 10       |
    | 24        | B22          | FL-002   | LP22          | 10       |

### <a name="enter-sales-order-details"></a>Értékesítési rendelés adatainak bevitele

1. Ugorjon az **Értékesítés és marketing** \> **Értékesítési rendelések** \> **Minden értékesítési** rendelés pontra.
2. Válassza az **Új** lehetőséget.
3. Az értékesítési rendelés fejlécében a **Vevői számla** mezőbe írja be az **US-003**értéket.
4. Adjon hozzá egy sort az új elemhez, és adja meg a **10** mennyiséget. Győződjön meg arról, hogy a **Raktár** mező értéke **24** legyen.
5. Válassza ki az **Értékesítési rendelés sorai** gyorslapot, válassza a **Készlet** elemet majd a **Karbantartás** csoportban válassza a **Köteg lefoglalása** elemet. A **Köteg lefoglalása** lapon látható a rendelési sor foglalásra használható kötegeinek listája. Ebben a példában a mennyiség **20** a **B11** kötegszámra, és **10** a **B22** kötegszámra. Figyelem, el, hogy a **Köteg lefoglalása** lap nem érhető el a sorból, ha a sorban szereplő tételt „kötegalatti\[hely\]” foglalási hierarchiához társították, hacsak nem úgy állították be, hogy engedélyezze a kötegspecifikus foglalást.

    > [!NOTE]
    > Ha egy értékesítési rendeléshez szeretne egy konkrét köteget foglalni, akkor a **Köteg lefoglalása** lapot kell használnia.
    >
    > Ha közvetlenül az értékesítési rendelés sorában adja meg a köteg számát, akkor a rendszer úgy viselkedik, mintha egy konkrét kötegértéket adott volna meg olyan cikkeknél, amelyek a „kötegalatti\[hely\]” foglalási irányelv szerint működnek. A sor mentésekor figyelmeztető üzenetet fog kapni. Ha megerősíti, hogy a kötegszám megadásának közvetlenül a rendelési sorban kell történnie, akkor a sort nem a szokásos raktárkezelési logika kezeli.
    >
    > Ha lefoglalja a mennyiséget a **Foglalás** oldalon, a program nem foglal le konkrét köteget, és a sor raktári műveleteinek végrehajtása a „kötegalatti\[hely\]” foglalási irányelv esetén alkalmazandó szabályokat fogja követni.

    Ez a lap általában ugyanúgy működik és ugyanúgy kell kezelni, mint az olyan cikkeknél, amelyek társított foglalási hierarchiája „kötegfölötti\[hely\]” típusú. Léteznek azonban a következő kivételek:

    - A **Forrássorhoz vállalt kötegszámok** gyorslapon láthatók az illető foglalási sorhoz lefoglalt kötegszámok. A rácsban lévő kötegértékek a rendelési sor teljes teljesítési ciklusa során láthatók, ideértve a raktár feldolgozási állapotát. Ezzel szemben az **Áttekintés** gyorslapon a szabályos rendelési sor foglalása (azaz a **Hely** szintje fölötti dimenziókra elvégzett foglalás) jelenik meg a rácsban addig a pontig, amikor a raktári munka létrejön. A munkaegység ezt követően átveszi a sor foglalását, és az már nem jelenik meg a lapon. A **Forrássorhoz vállalt kötegszámok** gyorslap biztosítja, hogy az értékesítési rendelés feldolgozója a köteg életciklusa során a számlázásig bármikor megtekintheti a vevői rendeléshez társított kötegszámokat.
    - Egy konkrét köteg lefoglalásán felül a felhasználó manuálisan is kiválaszthatja a köteg meghatározott helyét és a rendszámtáblát, nem kell hagynia, hogy a rendszer automatikusan kiválassza azokat. Ez a funkció a rendelésben véglegesített kötegfoglalás mechanizmus működésével kapcsolatos. Amint azt említettük, ha egy konkrét kötegszámot foglal egy cikk esetén a „kötegalatti\[hely\]” foglalási hierarchiában, a rendszernek a hely dimenzióig minden dimenziót le kell foglalnia. Ennélfogva a raktári munka ugyanazokat a tárolási dimenziókat fogja tartalmazni, amelyeket a rendelésekkel dolgozó felhasználók lefoglaltak, és nem biztos, hogy mindig a raktári kitárolási munkához kényelmes vagy éppen lehetséges tárolási helyet mutatja. Ha a rendelést feldolgozók ismerik a raktári megkötéseket, akkor megtörténhet, hogy manuálisan szeretnének bizonyos helyeket és rendszámtáblákat kiválasztani, amikor egy köteget foglalnak le. Ebben az esetben a felhasználónak a lap fejlécén található **Dimenziók megjelenítése** lehetőséget kell használnia, és a helyet és a rendszámtáblát fel kell vennie az **Áttekintés** gyorslap rácsára.

6. A **Köteg foglalása** lapon válassza ki a **B11** köteg sorát, majd válassza a **Sor foglalása** lehetőséget. Nincs kijelölt logika a helyek és a rendszámtáblák hozzárendelésére az automatikus foglalás során. A mennyiséget a **Foglalás** mezőbe manuálisan is beviheti. Figyelje meg, hogy a **Forrássorhoz vállalt kötegszámok** gyorslapon a **B11** köteg mellett a **Vállalt** szó látható.

    ![Meghatározott kötegszám vállalása egy értékesítési rendelés sorába a Köteg foglalása oldalon](media/Batch-reservation-form-with-order-committed-reservation.png)

    > [!NOTE]
    > Az értékesítési rendelés sorában szereplő mennyiség lefoglalása több köteg esetén is megtehető. Hasonlóképpen, ugyanannak a kötegnek a lefoglalása több hely és rendszámtábla esetén is megtehető (ha a rendszámtáblákat engedélyezték az illető helyekre).
    >
    > A konkrét köteg foglalási mennyisége is lehet részleges az illető minőségi rendelés sorában. Például a teljes, 100 egységnyi mennyiség lefoglalható úgy, hogy egy adott köteg 20 egységre legyen vállalva, míg 80 egységet a hely és a raktár szintjén kell lefoglalni bármely, rendelkezésre álló köteghez. Ebben az esetben a WMS két különálló munkasorral fogja kezelni a kitárolási műveleteket.

7. Kattintson a **Termékinformációk kezelése** \> **Termékek** \> **Kiadott termékek** lehetőségre. Válassza ki a kívánt elemet, majd válassza a **Készletkezelés** \> **Nézet** \> **Tranzakciók** elemet.

    ![Rendelésben véglegesített foglalás készlettranzakció-típusként](media/Inventory-transactions-for-order-committed-reservation.png)

8. Tekintse át az értékesítési rendelés sorfoglalásához kapcsolódó készlettranzakciókat.

    - Egy olyan tranzakció, amelyben a **Referencia** mező értéke **Értékesítési rendelés**, és a **Kiadás** mező értéke **Foglalt tényleges** értékre van állítva, a **Hely** szint fölötti készletdimenziók sorának foglalását jelenti. A cikkek foglalási hierarchiája szerint ezek a dimenziók a telep, a raktár és a készletállapot.
    - Egy olyan tranzakció, amelyben a **Referencia** mező értéke **Rendelésben véglegesített foglalás**, és a **Kiadás** mező értéke **Foglalt tényleges** értékre van állítva, konkrét köteg és a fölötte levő összes készletdimenzió sorának foglalását jelenti. A cikkek foglalási hierarchiája szerint ezek a dimenziók a kötegszám és hely. Ebben a példában a hely **Bulk-001**.

9. Az értékesítési rendelés fejlécében válassza ki a **Raktár** \> **Műveletek** \> **Kiadás raktárba** lehetőséget. A rendelési sor mostantól hullámos, és létrejön a terhelés és a munka.

### <a name="review-and-process-warehouse-work-that-has-order-committed-batch-numbers"></a>A rendeléshez véglegesített kötegszámokkal rendelkezó raktári munka áttekintése és feldolgozása

1. Az **Értékesítési rendelés sorai** gyorslapon válassza ki a **Raktár** \> **Munka készletes adatai** lehetőséget.

    Az értékesítési rendelés soraihoz lefoglalt kötegelt mennyiségek kitárolási műveletét kezelő munka jellemzői:

    - A munka létrehozásához a rendszer munkasablonokat használ, de nem rendelkezik hellyel kapcsolatos irányelvekkel. A program a munkasablonokhoz meghatározott összes szabványos beállítást, például a kitárolási sorok maximális számát vagy egy konkrét mértékegységet alkalmazni fogja, hogy meghatározza, hogy mikor kell új munkát létrehozni. A kitárolási helyek azonosítására szolgáló hely irányelvvel kapcsolatos szabályokat azonban nem veszi figyelembe, mivel a rendelésben véglegesített foglalás már megadja az összes készlet dimenziót. Ezek a készletdimenziók tartalmazzák a raktárak tárolási szintjén levő dimenziókat. Ezért a munka a hellyel kapcsolatos irányelvek egyeztetése nélkül örökli ezeket a dimenziókat.
    - A kötegszám nem jelenik meg a kitárolási sorban (szemben a társított „kötegfölötti\[hely\]” foglalási hierarchiát tartalmazó cikkek esetében létrejövő munkasorokkal). Ehelyett a Kezdő kötegszám és az összes többi tárolási dimenzió látható a munkasorban a társított készlettranzakciók alapján hivatkozott munkakészlet-tranzakcióban.

        ![Raktári készlet tranzakciója olyan munkához, amely rendelésben véglegesített foglalásból származik](media/Work-inventory-transactions-for-order-committed-reservation.png)

    - Miután létrehozta a munkát, a program eltávolítja a cikk azon készlettranzakcióját, amely esetén a **Referencia** mező beállítása **Rendelésben véglegesített foglalás**. Az a készlettranzakció, amelyben a **Referencia** mező beállása **Munka**, most a tényleges foglalást tárolja az összes mennyiség raktárdimenziója esetén.

        A raktári műveletek a szokásos módon folytathatják a munka végrehajtásának kezelését. A mobileszközön érkező utasítások azonban arra utasítják a dolgozót, hogy jelöljön ki egy konkrét kötegszámot. Olyan raktárakban, ahol a helyek rendszámtábla alapján vezéreltek, miután a dolgozó elér egy olyan helyet, ahol ugyanazt a köteget több rendszámtáblán tárolják, kiválaszthatja bármelyik rendszámtáblát, amelyik még nincs lefoglalva (például egy másik rendelésben véglegesített foglalást vagy olyan munkát, amely az adott típusú foglalásból származik.)

        Ha kiderül, hogy a munkasorban megadott helyről történő kitárolás nem praktikus, a raktári kezelők a következő műveletek egyikét alkalmazhatják az adott köteg kitárolásának egy kényelmesebb helyre történő átirányítására:

        - Szabványos **Hely felülbírálása** művelet mobileszközről (feltéve, hogy az illető raktári munkás esetén a **Kitárolási hely felülbírálásának engedélyezése** beállítása engedélyezett)
        - A **Hely módosítása** művelet a **Munkalista részletei** oldalon. 

2. Fejezze be a kitárolást és a munka elhelyezését a mobileszközön.

    A **B11** kötegszámhoz tartozó menniységet (**10**) kitárolták az értékesítési rendelési sorra, és elhelyezték a **Baydoor** helyen. Ezen a ponton készen áll a teherautóra történő berakásra, és a vevő címére történő feladásra.

## <a name="exception-handling-of-warehouse-work-thas-has-order-committed-batch-numbers"></a>A rendeléshez véglegesített kötegszámokkal rendelkezó raktári munka kivételkezelése

A rendeléshez véglegesített kötegszámokkal kitárolási raktári munkájának a kivételkezelése és műveletei ugyanazok, mint a normális munkának. Általában a nyitott munka vagy munkasor érvényteleníthető, megszakítható, mert egy felhasználói hely megtelt, a kitárolása lehet rövid, és egy mozgás miatt módosítható. Hasonlóképpen a már elvégzett munka kitárolt mennyisége is csökkenthető, illetve a munka visszafordítható.

A program a következő kulcsfontosságú szabályt alkalmazza az összes ilyen kivételkezelési műveletre: a vevő számára lefoglalt kötegszám nem cserélhető ki egy másik kötegszámra, de a tárolási dimenziói (hely és rendszámtábla) módosíthatók akár egy a felhasználó általi manuális vagy a rendszer általi automatikus frissítéssel. Az automatikus frissítés a tárolási dimenziók ugyanazon véletlen hozzárendelése alapján történik, amelyeket egy konkrét köteg automatikus visszafordításakor alkalmaznak, ha nincsenek megadva tárolási dimenziók.

### <a name="example-scenario"></a>Példaforgatókönyv

Példa erre a helyzetre olyan eset, amikor a korábban elvégzett munka kitárolását a **Kitárolt mennyiség csökkentése** funkció használatával visszavonják. Ez a példa a témakör előző példájának folytatása.

1. Lépjen a **Raktárkezelés** \> **Rakományok** \> **Aktív rakományok** elemhez.
2. Válassza ki az értékesítési rendelés szállítmányával együtt létrehozott terhelést.
3. A **Terhelési rendelés sorai** gyorslapon válassza ki a **Kitárolt mennyiség csökkentése** lehetőséget.
4. A **Kitárolt mennyiség csökkentése** lapon az **Áthelyezés helyre** mezőben válassza az **FL-001** elemet.
5. Az **Áthelyezés azonosítótáblára** mezőben válassza az **LP33** lehetőséget.
6. A rácsban a **Visszatárolandó készletmennyiség** mezőbe írja be a **10** értéket.
7. Válassza ki az **OK** lehetőséget.

A visszatárolási művelet eredményei:

- A korábban lezárt munka állapotát a rendszer **Visszavonva** értékre állítja.
- Új, **Készletmozgás** típusú munka jön létre a **B11** kötegszám esetén visszatárolt mennyiséghez (**10**). Ez a munka a **Baydoor** helyről az **FL-001** helyen található **LP33** rendszámtáblához való mozgást jelzi. Az rendszer átállítja az állapotot erre: **Lezárva**.
- A rendszer újra lefoglalja az eredetileg megrendelt kötegszámot, és hozzárendeli a helyet és a rendszámtábla azonosítóit. (Ez a folyamat egyenértékű a rendeléssor **Sor foglalása** funkciójának futtatásával egy adott kötegszám esetén). Ennek eredményekétten a **B11** köteg a **Köteg lefoglalása** oldal **Forrássorhoz vállalt kötegszámok** gyorslapján vállaltként jelenik meg, és a **Foglalás** mező a **B11** kötegszám esetén a **10** mennyiséget tartalmazza. Ezenkívül a **Hely** mező értéke **FL-001**, és a **Rendszámtábla** mező értéke **LP11**. (Hozzáadhatja ezeket a mezőket a rácshoz, ha nem láthatók.)

Az alábbi táblázatokban egy áttekintés látható, amely bemutatja, hogy a rendszer hogyan kezeli a konkrét raktári műveletekhez rendelt rendelésben véglegesített kötegfoglalásokat. A táblázatok tartalmának értelmezéséhez tételezzük fel, hogy minden egyes raktári művelet egy már létező raktári munka kontextusában fut, amely egy rendelésben véglegesített kötegfoglalásból származi, vagy hogy az egyes raktározási műveletek végrehajtása hatással van az adott típusú munkára.

> [!NOTE]
> Ezekben a táblázatokban a Kötegelt mennyiség elérhető oszlop jelzi, hogy az aktuális rendelésben véglegesített foglalások számára már lefoglalt, vagy az ugyanolyan típusú foglalásokból származó raktári munka által már lefoglalt mennyiség mellett rendelkezésre áll-e a kötegelt mennyiség.

#### <a name="override-the-pick-location-on-the-open-work"></a>Kitárolási hely felülbírálása nyitott munkában

<table>
<thead>
<tr>
<th>Fő beállítási paraméterek</th>
<th>Kötegelt mennyiség elérhető</th>
<th>Kulcsfontosságú felhasználói lépések</th>
<th>Raktári munka</th>
<th>Rendelésben véglegesített kötegfoglalás</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>A <strong>Kitárolási hely felülbírálásának engedélyezése</strong> beállítás az illető munkás esetén engedélyezve van.</td>
<td>Igen</td>
<td>
<ol>
<li>Válassza ki a <strong>Hely felülbírálása</strong> menüpontot a Warehouse Mobile App (WMA) alkalmazásban a kitárolási munka megkezdésekor.</li>
<li>Válassza a <strong>Javaslás</strong> lehetőséget.</li>
<li>Erősítse meg, hogy a kötegelt mennyiség elérhetősége alapján új helyet javasolt.</li>
</ol>
</td>
<td>Az aktuális munkában a következő műveletek történnek:
<ul>
<li>A kitárolási hely sora módosul az új hely értékére. (Ha a hely rendszámtábla által vezérelt, akkor a rendszer véletlenszerűen hozzárendel egy rendszámtáblát a munkakészlet-tranzakcióhoz, és a dolgozó kiválaszthatja bármelyik rendszámot, amelyik rendelkezik a rendelkezésre álló mennyiséggel.)</li>
<li>Ha a mennyiség egynél több rendszámtábla esetében is elérhető az új helyen, a rendszer az eredeti kitárolási sort szétosztja több sorra, hogy minden rendszámtáblának megfeleltesse a mennyiséget.</li>
</ul>
</td>
<td>Nem alkalmazható</td>
</tr>
<tr>
<td>Nem</td>
<td>
<ol>
<li>Válassza ki a <strong>Hely felülbírálása</strong> menüpontot a WMA alkalmazásban a kitárolási munka megkezdésekor.</li>
<li>Adja meg a helyet manuálisan.</li>
</ol>
</td>
<td>A <strong>Hely felülbírálása</strong> művelet végrehajtása nem lehetséges. Nem sikerült, és a program hibát jelez.</td>
<td>Nem alkalmazható</td>
</tr>
</tbody>
</table>

#### <a name="full-button--split-a-work-line-because-of-overflow-on-the-user-location"></a>Teljes gomb – munkasor megosztása a felhasználó helyén történő túlcsordulás miatt

<table>
<thead>
<tr>
<th>Fő beállítási paraméterek</th>
<th>Kötegelt mennyiség elérhető</th>
<th>Kulcsfontosságú felhasználói lépések</th>
<th>Raktári munka</th>
<th>Rendelésben véglegesített kötegfoglalás</th>
</tr>
</thead>
<tbody>
<tr>
<td>A <strong>Munka felosztásának engedélyezése</strong> beállítás engedélyezve van a mobileszköz menüjében.</td>
<td>Nem alkalmazható</td>
<td>
<ol>
<li>Válassza ki a <strong>Teljes</strong> menüpontot a WMA alkalmazásban a kitárolási munka feldolgozásakor.</li>
<li>A <strong>Mennyiség kitárolása</strong> mezőbe írja be a szükséges kitárolás egy részleges mennyiségét, hogy jelezze a teljes mennyiséget.</li>
</ol>
</td>
<td>
<ul>
<li>Az aktuális munkában a mennyiséget a rendszer frissíti arra a fennmaradó mennyiségre, amelyet ki kell tárolni.</li>
<li>A kitárolt mennyiséghez új munka jön létre és zárul le.</li>
</ul></td>
<td>Nem alkalmazható</td>
</tr>
</tbody>
</table>

#### <a name="reduce-the-picked-quantity-of-completed-work-from-a-load"></a>A teljesített munka kitárolt mennyiségének csökkentése (rakományból)

<table>
<thead>
<tr>
<th>Fő beállítási paraméterek</th>
<th>Kötegelt mennyiség elérhető</th>
<th>Kulcsfontosságú felhasználói lépések</th>
<th>Raktári munka</th>
<th>Rendelésben véglegesített kötegfoglalás</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>Nem alkalmazható</td>
<td>Igen</td>
<td>
<ol>
<li>A rakomány sorából nyissa meg a <strong>Kitárolt mennyiség csökkentése</strong> oldalt.</li>
<li>Adja meg a teljes visszatárolandó mennyiséget.</li>
<li>Válassza ki az „áthelyezési” helyet/rendszámtáblát.</li>
</ol>
</td>
<td>
<ul> 
<li>A rendszer érvényteleníti a rakomány sorához társított munkát.</li>
<li>A készletmozgáshoz új munka jön létre és zárul le.</li>
</ul>
</td>
<td>A mennyiséget a rendszer ismét lefoglalja ugyanarra a kötegre. A rendszer véletlenszerűen hozzárendel egy helyet és egy rendszámtáblát (ha a hely rendszám alapján vezérelt) ott, ahol a mennyiség rendelkezésre áll.</td>
</tr>
<tr>
<td>Nem</td>
<td>Lásd az előző sort.</td>
<td>Lásd az előző sort.</td>
<td>A program újra lefoglalja a mennyiséget ugyanarra a kötegre, és ugyanarra a helyre és rendszámtáblára (ha a hely rendszám alapján vezérelt), amelyet a kitároláskor bevittek.</td>
</tr>
</tbody>
</table>

#### <a name="move-an-item-within-a-warehouse"></a>Cikkek áthelyezése raktáron belül

> [!NOTE]
> Ez a raktári művelet csak a **Munka-létrehozási folyamat** típusú mozgásra vonatkozik, a sablon szerinti mozgásra nem.

<table>
<thead>
<tr>
<th>Fő beállítási paraméterek</th>
<th>Kötegelt mennyiség elérhető</th>
<th>Kulcsfontosságú felhasználói lépések</th>
<th>Raktári munka</th>
<th>Rendelésben véglegesített kötegfoglalás</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>A <strong>Készlet mozgatásának engedélyezése társított munkával</strong> lehetőség a dolgozó esetén engedélyezve van.</td>
<td>Igen</td>
<td>
<ol>
<li>Kezdje meg a mozgatást a WMA alkalmazáson.</li>
<li>Adja meg Innen és Ide helyeket.</li>
</ol></td>
<td>
<ul>
<li>Az áthelyezés által érintett összes létező munkánál a kitárolási hely módosul az új Ide helyre.</li>
<li>A készletmozgáshoz új munka jön létre és zárul le.</li>
</ul>
</td>
<td>A program az adott helyről származó mennyiségmozgatás által érintett összes meglévő foglalást ismételten lefoglalja ugyanarra a kötegre. A rendszer véletlenszerűen hozzárendel egy helyet és egy rendszámtáblát (ha a hely rendszám alapján vezérelt) ott, ahol a mennyiség rendelkezésre áll.</td>
</tr>
<tr>
<td>Nem</td>
<td>Lásd az előző sort.</td>
<td>Lásd az előző sort.</td>
<td>A program az adott helyről származó mennyiségmozgatás által érintett összes meglévő foglalást ismételten lefoglalja ugyanarra a kötegre, és az új Ide helyre és rendszámtáblára (ha a hely rendszám által vezérelt).</td>
</tr>
</tbody>
</table>

#### <a name="reverse-the-picked-quantity-of-completed-work-from-a-load-or-a-wave"></a>A teljesített munka kitárolt mennyiségének sztornírozása (rakományból vagy hullámból)

<table>
<thead>
<tr>
<th>Fő beállítási paraméterek</th>
<th>Kötegelt mennyiség elérhető</th>
<th>Kulcsfontosságú felhasználói lépések</th>
<th>Raktári munka</th>
<th>Rendelésben véglegesített kötegfoglalás</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='6'>Nem alkalmazható</td>
<td>Igen</td>
<td>
<ol>
<li>Nyissa meg a <strong>Munka sztornírozása</strong> oldalt.</li>
<li>A kérelem oldalán válassza ki <strong>A cikkek az aktuális helyen maradnak</strong> beállítást.</li>
</ol>
</td>
<td>A rendszer érvényteleníti a rakományhoz társított összes munkát.</td>
<td>A mennyiséget a rendszer ismét lefoglalja ugyanarra a kötegre. A rendszer véletlenszerűen hozzárendel egy helyet és egy rendszámtáblát (ha a hely rendszám alapján vezérelt) ott, ahol a mennyiség rendelkezésre áll.</td>
</tr>
<tr>
<td>Nem</td>
<td>Lásd az előző sort.</td>
<td>Lásd az előző sort.</td>
<td>A program újra lefoglalja a mennyiséget ugyanarra a kötegre, illetve azon helyre és rendszámtáblára esetében, ahol a mennyiség a sztornírozás után megmaradt.</td>
</tr>
<tr>
<td>Igen</td>
<td>
<ol>
<li>Nyissa meg a <strong>Munka sztornírozása</strong> oldalt.</li>
<li>A kérelem oldalán válassza ki a <strong>Cikkek hozzárendelése ehhez a helyhez</strong> beállítást.</li>
</ol>
</td>
<td>
<ul>
<li>Az aktuális munkát a rendszer érvényteleníti.</li>
<li>A készletmozgáshoz új munka jön létre és zárul le.</li>
</ul>
</td>
<td>A mennyiséget a rendszer ismét lefoglalja ugyanarra a kötegre. A rendszer véletlenszerűen hozzárendel egy helyet és egy rendszámtáblát (ha a hely rendszám alapján vezérelt) ott, ahol a mennyiség rendelkezésre áll.</td>
</tr>
<tr>
<td>Nem</td>
<td>Lásd az előző sort.</td>
<td>Lásd az előző sort.</td>
<td>A program újra lefoglalja a mennyiséget ugyanarra a kötegre, illetve azon helyre és rendszámtáblára esetében, ahova a mennyiséget a sztornírozás után hozzárendelték.</td>
</tr>
<tr>
<td>Igen/Nem</td>
<td>
<ol>
<li>Nyissa meg a <strong>Munka sztornírozása</strong> oldalt.</li>
<li>A kérelem oldalán válassza ki a <strong>Cikkek áthelyezése erre a helyre</strong> beállítást.</li>
</ol>
</td>
<td>A sztornírozás nem támogatott.</td>
<td>Nem alkalmazható</td>
</tr>
<tr>
<td>Igen/Nem</td>
<td>
<ol>
<li>Nyissa meg a <strong>Munka sztornírozása</strong> oldalt.</li>
<li>A kérelem oldalán válassza ki a <strong>Cikkek mozgatása helyutasítások alapján</strong> beállítást.</li>
</ol>
</td>
<td>A sztornírozás nem támogatott. </td>
<td>Nem alkalmazható</td>
</tr>
</tbody>
</table>

#### <a name="short-pick-a-quantity--register-the-quantity-as-physically-not-found-at-the-locationlicense-plate-while-you-perform-picking-work"></a>Egy mennyiség rövid kitárolása – a kitárolási munka végrehajtása közben a mennyiség fizikailag nem fellelhetőként történő regisztrálása a helynél/rendszámnál

<table>
<thead>
<tr>
<th>Fő beállítási paraméterek</th>
<th>Kötegelt mennyiség elérhető</th>
<th>Kulcsfontosságú felhasználói lépések</th>
<th>Raktári munka</th>
<th>Rendelésben véglegesített kötegfoglalás</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>A <strong>Rövid kitárolás</strong> típusra munkakivétel ven beállítva, amelynek értelmében <strong>Cikk újbóli felosztása</strong> = <strong>Egyik sem</strong>, <strong>Készlethelyesbítés</strong> = <strong>Igen</strong>, és <strong>Foglalások eltávolítása</strong> = <strong>Nem</strong>.</td>
<td>Igen</td>
<td>
<ol>
<li>Válassza ki a <strong>Rövid kitárolás</strong> menüpontot a WMA alkalmazásban a kitárolási munka futtatásakor.</li>
<li>Írja be a <strong>0</strong> (nulla) értéket a <strong>Kitárolási mennyiség</strong> mezőbe.</li>
<li>Az <strong>Ok</strong> mezőbe írja be a következőt: <strong>Nincs újrafelosztás</strong>.</li>
</ol>
</td>
<td>
<ul>
<li>A rendszer lezárja az aktuális munkát, a kitárolt mennyiség 0 (nulla).</li>
<li>A program létrehoz egy <strong>Számlálás</strong> típusú és <strong>Eladva</strong> kibocsátási típusú, készlettranzakciót, amely a módosítást reprezentálja.</li>
</ul>
</td>
<td>A mennyiséget a rendszer ismét lefoglalja ugyanarra a kötegre. A rendszer véletlenszerűen hozzárendel egy helyet és egy rendszámtáblát (ha a hely rendszám alapján vezérelt) ott, ahol a mennyiség rendelkezésre áll.</td>
</tr>
<tr>
<td>Nem</td>
<td>Lásd az előző sort.</td>
<td>
<ul>
<li>A rövid kitárolási művelet nem sikerült, és a program hibát jelez.</li>
<li>Az aktuális munka nyitva marad.</li>
</ul>
</td>
<td>Nem alkalmazható</td>
</tr>
<tr>
<td rowspan='2'>A <strong>Rövid kitárolás</strong> típusra munkakivétel ven beállítva, amelynek értelmében <strong>Cikk újbóli felosztása</strong> = <strong>Egyik sem</strong>, <strong>Készlethelyesbítés</strong> = <strong>Igen</strong>, és <strong>Foglalások eltávolítása</strong> = <strong>Igen</strong>.</td>
<td>Igen</td>
<td>
<ol>
<li>Válassza ki a <strong>Rövid kitárolás</strong> menüpontot a WMA alkalmazásban a kitárolási munka futtatásakor.</li>
<li>Írja be a <strong>0</strong> (nulla) értéket a <strong>Kitárolási mennyiség</strong> mezőbe.</li>
<li>Az <strong>Ok</strong> mezőbe írja be a következőt: <strong>Nincs újrafelosztás</strong>.</li>
</ol>
</td>
<td>
<ul>
<li>A rendszer lezárja az aktuális munkát, a kitárolt mennyiség 0 (nulla).</li>
<li>A program létrehoz egy <strong>Számlálás</strong> típusú és <strong>Eladva</strong> kibocsátási típusú, készlettranzakciót, amely a módosítást reprezentálja.</li>
</ul>
</td>
<td>A program a röviden kitárolt helyről származó mennyiségmódosítás által érintett összes meglévő foglalást ismételten lefoglalja ugyanarra a kötegre. A rendszer véletlenszerűen hozzárendel egy helyet és egy rendszámtáblát (ha a hely rendszám alapján vezérelt) ott, ahol a mennyiség rendelkezésre áll.</td>
</tr>
<tr>
<td>Nem</td>
<td>Lásd az előző sort.</td>
<td>Lásd az előző sort.</td>
<td>A program a röviden kitárolt helyről származó mennyiségmódosítás által érintett összes meglévő foglalást eltávolítja.</td>
</tr>
<tr>
<td>A <strong>Rövid kitárolás</strong> típusra munkakivétel ven beállítva, amelynek értelmében <strong>Cikk újbóli felosztása</strong> = <strong>Manuális</strong>, <strong>Készlethelyesbítés</strong> = <strong>Igen</strong>, és <strong>Foglalások eltávolítása</strong> = <strong>Nem/Igen</strong>. Ezenkívül a <strong>Cikk újbóli manuális felosztásának engedélyezése</strong> beállítás a dolgozó esetén engedélyezve van.</td>
<td>Igen</td>
<td>
<ol>
<li>Válassza ki a <strong>Rövid kitárolás</strong> menüpontot a WMA alkalmazásban a kitárolási munka futtatásakor.</li>
<li>Írja be a <strong>0</strong> (nulla) értéket a <strong>Rövid kitárolási mennyiség</strong> mezőbe.</li>
<li>Az <strong>Ok</strong> mezőben válassza ki a <strong>Rövid kitárolást manuális újrafelosztással</strong> lehetőséget.</li>
<li>Válassza ki a helyet vagy a rendszámtábla a listából.</li>
</ol>
</td>
<td>
<ul>
<li>Az aktuális munkában a következő műveletek történnek:
<ul>
<li>A rendszer lezárja a kitárolási sort, a kitárolt mennyiség 0 (nulla).</li>
<li>A rendszer érvényteleníti a betárolási sort.</li>
<li>Új kitárolási sor jön létre. Ez a felhasználó által kiválasztott helyet/rendszámtáblát használja.</li>
<li>Új betárolási sor jön létre.</li>
</ul>
</li>
<li>A program létrehoz egy <strong>Számlálás</strong> típusú és <strong>Eladva</strong> kibocsátási típusú, készlettranzakciót, amely a módosítást reprezentálja.</li>
</ul>
</td>
<td>Nem alkalmazható</td>
</tr>
<tr>
<td>A <strong>Rövid kitárolás</strong> típusra munkakivétel ven beállítva, amelynek értelmében <strong>Cikk újbóli felosztása</strong> = <strong>Manuális</strong>, <strong>Készlethelyesbítés</strong> = <strong>Igen</strong>, és <strong>Foglalások eltávolítása</strong> = <strong>Nem</strong>. Ezenkívül a <strong>Cikk újbóli manuális felosztásának engedélyezése</strong> beállítás a dolgozó esetén engedélyezve van.</td>
<td>Nem</td>
<td>
<ol>
<li>Válassza ki a <strong>Rövid kitárolás</strong> menüpontot a WMA alkalmazásban a kitárolási munka futtatásakor.</li>
<li>Írja be a <strong>0</strong> (nulla) értéket a <strong>Rövid kitárolási mennyiség</strong> mezőbe.</li>
<li>Az <strong>Ok</strong> mezőben válassza ki a <strong>Rövid kitárolást manuális újrafelosztással</strong> lehetőséget.</li>
</ol>
</td>
<td>A rövid kitárolási művelet nem sikerült, és a program hibát jelez.</td>
<td>Nem alkalmazható</td>
</tr>
<tr>
<td>A <strong>Rövid kitárolás</strong> típusra munkakivétel ven beállítva, amelynek értelmében <strong>Cikk újbóli felosztása</strong> = <strong>Manuális</strong>, <strong>Készlethelyesbítés</strong> = <strong>Igen</strong>, és <strong>Foglalások eltávolítása</strong> = <strong>Igen</strong>. Ezenkívül a <strong>Cikk újbóli manuális felosztásának engedélyezése</strong> beállítás a dolgozó esetén engedélyezve van.</td>
<td>Nem</td>
<td>
<ol>
<li>Válassza ki a <strong>Rövid kitárolás</strong> menüpontot a WMA alkalmazásban a kitárolási munka futtatásakor.</li>
<li>Írja be a <strong>0</strong> (nulla) értéket a <strong>Rövid kitárolási mennyiség</strong> mezőbe.</li>
<li>Az <strong>Ok</strong> mezőben válassza ki a <strong>Rövid kitárolást manuális újrafelosztással</strong> lehetőséget.</li>
<li>Válassza ki a helyet vagy a rendszámtábla a listából.</li>
</ol>
</td>
<td>
<ul>
<li>Az aktuális munkában a következő műveletek történnek:
<ul>
<li>A rendszer lezárja a kitárolási sort, a kitárolt mennyiség 0 (nulla).</li>
<li>A rendszer érvényteleníti a betárolási sort.</li>
</ul>
</li>
<li>A program létrehoz egy <strong>Számlálás</strong> típusú és <strong>Eladva</strong> kibocsátási típusú, készlettranzakciót, amely a módosítást reprezentálja.</li>
</ul>
</td>
<td>A program a röviden kitárolt helyről/rendszámtáblából származó mennyiségmódosítás által érintett összes meglévő foglalást eltávolítja.</td>
</tr>
<tr>
<td>A <strong>Rövid kitárolás</strong> típusra munkakivétel ven beállítva, amelynek értelmében <strong>Cikk újbóli felosztása</strong> = <strong>Autonatikus</strong>, <strong>Készlethelyesbítés</strong> = <strong>Igen/Nem</strong>, és <strong>Foglalások eltávolítása</strong> = <strong>Igen/Nem</strong>.</td>
<td>Nem alkalmazható</td>
<td>
<ol>
<li>Válassza ki a <strong>Rövid kitárolás</strong> menüpontot a WMA alkalmazásban a kitárolási munka futtatásakor.</li>
<li>Írja be a <strong>0</strong> (nulla) értéket a <strong>Rövid kitárolási mennyiség</strong> mezőbe.</li>
<li>Az <strong>Ok</strong> mezőben válassza ki a <strong>Rövid kitárolást automatikus újrafelosztással</strong> lehetőséget.</li>
</ol>
</td>
<td>Az automatikus újrafelosztással kapcsolatos rövid kitárolás nem támogatott.</td>
<td>Az automatikus újrafelosztással kapcsolatos rövid kitárolás nem támogatott.</td>
</tr>
</tbody>
</table>

#### <a name="change-the-inventory-status"></a>A készletállapot módosítása

> [!NOTE]
> Ez a raktári művelet több belépési pontról is elvégezhető. Az itt látható példa a **Készletállapot-változás** műveletet használja az **Aktuális készlet hely szerint** oldalon.

<table>
<thead>
<tr>
<th>Fő beállítási paraméterek</th>
<th>Kötegelt mennyiség elérhető</th>
<th>Kulcsfontosságú felhasználói lépések</th>
<th>Raktári munka</th>
<th>Rendelésben véglegesített kötegfoglalás</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>A <strong>Raktár</strong> lapon a <strong>Raktár</strong> rekordban a <strong>Foglalások és jelölések eltávolítása</strong> mező értéke <strong>Foglalások</strong> vagy <strong>Jelölések és foglalások</strong>.</td>
<td>Igen</td>
<td>
<ol>
<li>Válasszon ki egy konkrét helyet.</li>
<li>Válasszon ki egy sort, amely rendelkezik egy adott cikkel, hellyel és rendszámtáblábal (ha a hely rendszám alapján vezérelt).</li>
<li>Válassza a <strong>Készletállapot-változás</strong> lehetőséget.</li>
<li>Állítsa a <strong>Készlet állapota</strong> mező értékét erre: <strong>Zárolás</strong>.</li>
</ol>
</td>
<td>A készlet állapotának módosításai nem engedélyezettek a munkára fenntartott mennyiségek esetében.</td>
<td>
<ul>
<li>A mennyiséget a rendszer ismét lefoglalja ugyanarra a kötegre. A rendszer véletlenszerűen hozzárendel egy helyet és egy rendszámtáblát (ha a hely rendszám alapján vezérelt) ott, ahol a mennyiség rendelkezésre áll.</li>
<li>Létrejön a készlet állapota dimenziójának módosítását jelképező két <strong>Készletállapot-változás</strong> típusú készlettranzakció.</li>
<li>Létrejön egy <strong>Készletzárolás</strong> típusú és egy <strong>Lefoglalt tényleges</strong> kiadási típusú készlettranzakció, amelyek a zárolt mennyiség lefoglalását hivatottak jelképezni.</li>
</ul>
</td>
</tr>
<tr>
<td>Nem</td>
<td>Lásd az előző sort.</td>
<td>A készlet állapotának módosításai nem engedélyezettek a munkára fenntartott mennyiségek esetében.</td>
<td>
<ul>
<li>A foglalást a program eltávolítja.</li>
<li>Létrejön a készlet állapota dimenziójának módosítását jelképező két <strong>Készletállapot-változás</strong> típusú készlettranzakció.</li>
<li>Létrejön egy <strong>Készletzárolás</strong> típusú és egy <strong>Lefoglalt tényleges</strong> kiadási típusú készlettranzakció, amelyek a zárolt mennyiség lefoglalását hivatottak jelképezni.</li>
</ul>
</td>
</tr>
<tr>
<td rowspan='2'>A <strong>Raktár</strong> lapon a <strong>Raktár</strong> rekordban a <strong>Foglalások és jelölések eltávolítása</strong> mező értéke <strong>Nincs</strong>.</td>
<td>Igen</td>
<td>
<ol>
<li>Válasszon ki egy konkrét helyet.</li>
<li>Válasszon ki egy sort, amely rendelkezik egy adott cikkel, hellyel és rendszámtáblábal (ha a hely rendszám alapján vezérelt).</li>
<li>Válassza a <strong>Készletállapot-változás</strong> lehetőséget.</li>
<li>Állítsa a <strong>Készlet állapota</strong> mező értékét erre: <strong>Zárolás</strong>.</li>
</ol>
</td>
<td>A készlet állapotának módosításai nem engedélyezettek a munkára fenntartott mennyiségek esetében.</td>
<td>A mennyiséget a rendszer ismét lefoglalja ugyanarra a kötegre. A rendszer véletlenszerűen hozzárendel egy helyet és egy rendszámtáblát (ha a hely rendszám alapján vezérelt) ott, ahol a mennyiség rendelkezésre áll.</td>
</tr>
<tr>
<td>Nem</td>
<td>Lásd az előző sort.</td>
<td>A készlet állapotának módosításai nem engedélyezettek a munkára fenntartott mennyiségek esetében.</td>
<td>A készlet állapotának változtatásai nem engedélyezettek.</td>
</tr>
</tbody>
</table>

## <a name="limitations"></a>Korlátozások

- A rugalmas raktárszintű dimenziófoglalási funkció nem támogatja a következő szolgáltatásokat:

    - Tényleges súly kezelése
    - Tényleges negatív készlet
    - Foglalás megrendelt ellátással szemben
    - Átmozgatási rendelések és nyersanyag kitárolása

- A tároló utasítási egység szerinti csomagolásra vonatkozó összevonási szabályának emgvannak a korlátai. A rendelésben véglegesített foglalások esetében azt javasoljuk, hogy ne használjon olyan tárolóépítési sablonokat, amelyek **Csomagolás utasításegység szerint** mezőjét engedélyezték. A jelenlegi rendszer a raktári munka létrehozásakor nem használ helyutasításokat. Ennek megfelelően a rendszer csak az egységszekvencia-csoport (a készletegységben) legkisebb egységét alkalmazza a tárolóra bontási hullámlépés során.
