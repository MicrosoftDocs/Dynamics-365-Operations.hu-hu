---
title: Rugalmas raktárszintű dimenziófoglalási irányelv
description: Ez a témakör azt mutatja be, hogy a készletfoglalási irányelv, amely lehetővé teszi, hogy a kötegelt nyomon követésű termékeket értékesítő és a logisztikát a WMS-kompatibilis műveletekekként futtató vállalatok lefoglaljanak bizonyos kötegeket ügyfelek értékesítési rendeléseihez, még akkor is, ha a foglalási hierarchia a termékekhez kapcsolódóan nem engedélyezi a meghatározott kötegek foglalását.
author: perlynne
manager: tfehr
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-01-15
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: d75e6a8b48447a33156e03d50e990b8514bacda9
ms.sourcegitcommit: d540998ad6f9c894ca99498c045ae4b86b779806
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/08/2020
ms.locfileid: "3970703"
---
# <a name="flexible-warehouse-level-dimension-reservation-policy"></a>Rugalmas raktárszintű dimenziófoglalási irányelv

[!include [banner](../includes/banner.md)]

Amikor egy „kötegalatti\[hely\]” típusú készlet foglalási hierarchiája termékekhez van társítva, a kötegelt nyomon követéssel ellátott termékeket értékesítő és a logisztikai műveleteiket a Microsoft Dynamics 365 raktározási rendszerrel (WMS) kompatibilisként futtató vállalatok nem foglalhatják le az illető termékek konkrét kötegeit ügyfelek értékesítési rendeléseihez.

Ugyanígy nem foglalható le specifikus azonosítótábla az értékesítési rendelésen szereplő termékekhez, amikor ezek a termékek az alapértelmezett foglalási hierarchiához vannak társítva.

Ez a témakör bemutatja azt a készletfoglalási irányelvet, amely alapján a vállalatok meghatározott kötegeket vagy azonosítótáblákat foglalhatnak le, még akkor is, ha a termékek a „kötegalatti\[hely\]” foglalási hierarchiával vannak társítva.

## <a name="inventory-reservation-hierarchy"></a>Készletfoglalási hierarchia

Ez a szakasz összegzi a meglévő készletfoglalási hierarchiát.

A készletfoglalási hierarchia azt írja elő, hogy a tárolási dimenziókat illetően az igény szerinti rendelés a hely, a raktár és a készlet állapotának kötelező dimenzióit hordozza. A raktári logika felelős azért, hogy a kívánt mennyiségekhez helyet rendeljen, és lefoglalja azt. Más szóval az igény szerinti rendelés és a raktári műveletek közötti interakciókban várhatóan az igény szerinti rendelése jelzi, hogy honnan kell szállítani a rendelést (azaz a helyet és a raktárat). A raktár ezután saját logikájára alapozva megkeresi a szükséges mennyiséget a raktár területén.

Ha azonban az üzlet műveleti modelljét szeretné tükrözni, a nyomonkövetési dimenziók esetén (köteg-és sorozatszámok) nagyobb rugalmasságra van szükség. A készletfoglalási hierarchia olyan esetekhez használható, amelyekben teljesülnek az alábbi feltételek:

- A vállalat a raktári műveletei alapján kezeli a köteg-vagy sorozatszámmal ellátott mennyiségek kiválasztását, miután a mennyiségeket a rendszer megtalálta a raktározási tárolóhelyen. Ezt a modellt gyakran nevezzük *kötegalatti\[helynek\]* . Ezt általában akkor használják, ha a termék köteg- vagy sorozatszám-azonosítója nem fontos azoknak a vevőknek, akik a rendelést tették az értékesítő vállalatnál.
- Ha a köteg-vagy sorozatszámok a vevői rendelési specifikáció részei, és a program rögzíti azokat az igény szerinti rendelésen, akkor a raktári műveleteket, amelyek megkeresik a raktárban lévő mennyiségeket, az egyes igényelt számokkal korlátozni lehet, és azok nem módosíthatók. Ezt a modellt nevezzük *kötegfeletti\[helynek\]* .

Ezekben az esetekben a kihívás az, hogy csak egyetlen készletfoglalási hierarchiát lehet hozzárendelni az egyes kiadott termékekhez. Ezért ahhoz, hogy WMS kezelje a nyomon követett cikkeket, miután a hierarchia-hozzárendelés meghatározza, hogy mikor kell lefoglalni a köteg-vagy sorozatszámot (vagy az igény szerinti rendelés fogadásakor, vagy a raktári kitárolási munka során), ez az időzítés nem módosítható ad hoc módon.

## <a name="flexible-reservation-for-batch-tracked-items"></a>Rugalmas foglalás a kötegelten nyomon követett cikkeknél

### <a name="business-scenario"></a>Üzleti eset

Ebben a helyzetben a vállalat egy készletstratégiát alkalmaz, amelyben a késztermékeket a kötegszámokkal követi nyomon. Ez a vállalat is a WMS terhelést használja. Mivel ez a terhelés jól felszerelt logikával rendelkezik a raktári kitárolási és fuvarozási műveletek tervezéséhz és lefuttatásához kötegelésre engedélyezett elemek esetén, a kész cikkek többsége a „kötegalatti\[hely\]” készletfoglalási hierarchiához van társítva. Ennek a működési beállításnak az az előnye, hogy a döntéseket (amelyek valójában foglalási döntések) arról, hogy mely kötegeket kell kiválasztania, és hová kell tenni őket a raktárban, elhalasztják, amíg el nem kezdődnek a raktári kitárolási műveletek. Nem akkor jönnek létre, amikor az ügyfél rendel.

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
> A **Kötegszám** és az **Azonosítótábla** a hierarchia egyetlen olyan szintjei, amelyek nyitottat a rugalmas foglalási irányelv számára. Más szóval nem jelölheti be a **Foglalás engedélyezése igény szerinti rendelésnél** jelölőnégyzetet a **Hely** vagy **Sorozatszám** szinteken.
>
> Ha a foglalási hierarchiában szerepel a sorozatszám dimenzió (amelynek mindig a **Kötegszám** szint alatt kell lennie), és ha bekapcsolta a kötegszám-specifikus foglalást,, a rendszer továbbra is a sorozatszám szerinti foglalási és kitárolási műveleteket fogja kezelni a „sorszámalatti\[hely\]” foglalási irányelvre vonatkozó szabályok alapján.

A telepítés során bármikor engedélyezheti a kötegspecifikus foglalást egy létező „kötegalatti\[hely\]” foglalási hierarchiában a telepítésben. A módosítás nem fogja érinteni a módosítás előtt létrehozott foglalásokat és nyitott raktári munkákat. Azonban a **Foglalás engedélyezése az igény szerinti rendelésnél** jelölőnégyzetet nem lehet törölni, ha az adott foglalási hierarchiához társított egy vagy több cikk esetén a **Foglalt rendelt** , **Foglalt tényleges** vagy **Megrendelve** típusú problémák készlettranzakciói léteznek.

> [!NOTE]
> Ha egy elem meglévő foglalási hierarchiája nem teszi lehetővé a köteg megadását a rendelésen, akkor újra hozzárendelheti azt egy olyan foglalási hierarchiához, amely lehetővé teszi a köteg megadását, feltéve, hogy a hierarchia szintjének szerkezete mindkét hierarchiában ugyanaz. Az ismételt hozzárendeléshez használja a **Cikkek foglalási hierarchiájának módosítása** funkciót. Ez a módosítás akkor lehet fontos, ha el akarja kerülni a rugalmas kötegelt rendelést a kötegelt nyomonkövetésű cikkek egy csoportja esetén, azonban engedélyezni akarja azt a termékportfólió többi eleme számára.

Függetlenül attól, hogy bejelölte-e a **Foglalás engedélyezése igény szerinti rendelésnél** jelölőnégyzetet, ha a rendelési sorban nem szeretne lefoglalni egy konkrét kötegszámot, az alapértelmezett, „kötegalatti\[hely\]” foglalási hierarchia esetében érvényes raktárműveleti logika lép érvénybe.

### <a name="reserve-a-specific-batch-number-for-a-customer-order"></a>Konkrét kötegszám foglalása egy vevői rendeléshez

Ha egy kötegelt nyomonkövetésű elem „kötegalatti\[hely\]” típusú készle foglalási hierarchiája úgy van beállítva, hogy engedélyezze az értékesítési rendeléseken a konkrét kötegszám foglalását, akkor az értékesítési rendelések feldolgozói a vevői igényektől függően a következő módokon vehetik fel a vevői rendeléseket ugyanarra a tételre:

- **Rendelés részleteinek megadása a kötegszám megadása nélkül** – ezt a megközelítést akkor kell használni, ha a termékköteg megadása nem fontos a vevő számára. Az ilyen típusú rendelések kezelésével kapcsolatos összes meglévő folyamat változatlan marad. A felhasználók részéről nem szükséges további megfontolás.
- **Rendelés részleteinek megadása és egy konkrét kötegszám lefoglalása** – ezt a megközelítést akkor kell használni, ha a vevő egy konkrét köteget kér. A vevők általában akkor kérnek egy konkrét köteget, ha egy korábban vásárolt terméket rendelnek újra. Ezt a típusú kötegspecifikus foglalást nevezik *Rendelésben véglegesített foglalásnak* .

A következő szabályok érvényesek a mennyiségek feldolgozásakor, ha a köteg számát egy konkrét rendeléshez kötötték:

- Ha engedélyezni szeretné egy konkrét kötegszám foglalását a „kötegalatti\[hely\]” foglalási hierarchiában, a rendszernek a hely dimenzióig minden dimenziót le kell foglalnia. Ez a tartomány általában a rendszámtábla dimenziót tartalmazza.
- A hely irányelvei nem használatosak, amikor olyan értékesítési sorhoz hozza létre a kitárolási munkát, amely rendelésben véglegesített kötegfoglalást használ.
- A rendelésben véglegesített kötegfoglaláshoz tartozó munka raktári feldolgozása során sem a felhasználó, sem a rendszer nem módosíthatja a kötegszámot. (Ez a feldolgozás tartalmazza a kivételek kezelését.)

A következő példa bemutatja a végpontok közötti áramlást.

## <a name="example-scenario-batch-number-allocation"></a>Példaforgatókönyv: Köteg számának felosztása

Ebben a példában a bemutatóadatokat kell telepíteni, és az **USMF** demó-adatvállalatot kell használnia.

### <a name="set-up-an-inventory-reservation-hierarchy-to-allow-batch-specific-reservation"></a><a name="Example-batch-allocation"></a>Hozzon létre egy készletfoglalási hierarchiát, hogy lehetővé tegye a kötegspecifikus foglalást

1. Nyissa meg a **Raktárkezelés** \> **Beállítás** \> **Készlet \> Foglalási hierarchia** lehetőséget.
2. Válassza az **Új** lehetőséget.
3. Adja meg a feladat egyedi nevét a **Név** mezőben (pl. **BatchFlex** ).
4. A **Leírás** mezőben adjon meg egy leírást (például: **Rugalmas alatti kötteg** ).
5. A **Kijelölve** mezőben válassza ki a **Sorozatszám** és a **Tulajdonos** lehetőségeket, majd a bal nyílgombra kattintva helyezze át őket a **Rendelkezésre áll** mezőbe.
6. Válassza ki az **OK** lehetőséget.
7. A **Kötegszám** dimenzió szintjének sorában jelölje be a **Foglalás engedélyezése igény szerinti rendelésnél** jelölőnégyzetet. A **Rendszámtábla** és a **Hely** szintje automatikusan be van jelölve, és a jelölőnégyzetek nem törölhetők.
8. Válassza a **Mentés** lehetőséget.

### <a name="create-a-new-released-product"></a>Új kiadott termék létrehozása

1. Adja meg a termék három alapadat-paraméterét az alábbi értékeket használva:

    - A **Tárolási dimenziócsoport** mezőben válassza a **Raktár** lehetőséget.
    - A **Nyomon követési dimenziócsoport** mezőben válassza a **Batch-Phy** lehetőséget.
    - A **Foglalási hierarchia** mezőben válassza ki a **BatchFlex** lehetőséget.

2. Hozzon létre két kötegszámot, például **B11** és **B22** .
3. Az alábbi értékek használatával adjon hozzá cikkmennyiségeket az aktuális készlethez.

    | Raktár | Köteg száma | Helyszín | Azonosítótábla | Mennyiség |
    |-----------|--------------|----------|---------------|----------|
    | 24        | B11          | BULK-001 | Egyik sem          | 10       |
    | 24        | B11          | FL-001   | LP11          | 10       |
    | 24        | B22          | FL-002   | LP22          | 10       |

### <a name="enter-sales-order-details"></a><a name="sales-order-details"></a>Értékesítési rendelés adatainak bevitele

1. Ugorjon az **Értékesítés és marketing** \> **Értékesítési rendelések** \> **Minden értékesítési** rendelés pontra.
2. Válassza az **Új** lehetőséget.
3. Az értékesítési rendelés fejlécében a **Vevői számla** mezőbe írja be az **US-003** értéket.
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

    - Egy olyan tranzakció, amelyben a **Referencia** mező értéke **Értékesítési rendelés** , és a **Kiadás** mező értéke **Foglalt tényleges** értékre van állítva, a **Hely** szint fölötti készletdimenziók sorának foglalását jelenti. A cikkek foglalási hierarchiája szerint ezek a dimenziók a telep, a raktár és a készletállapot.
    - Egy olyan tranzakció, amelyben a **Referencia** mező értéke **Rendelésben véglegesített foglalás** , és a **Kiadás** mező értéke **Foglalt tényleges** értékre van állítva, konkrét köteg és a fölötte levő összes készletdimenzió sorának foglalását jelenti. A cikkek foglalási hierarchiája szerint ezek a dimenziók a kötegszám és hely. Ebben a példában a hely **Bulk-001** .

9. Az értékesítési rendelés fejlécében válassza ki a **Raktár** \> **Műveletek** \> **Kiadás raktárba** lehetőséget. A rendelési sor mostantól hullámos, és létrejön a terhelés és a munka.

### <a name="review-and-process-warehouse-work-that-has-order-committed-batch-numbers"></a>A rendeléshez véglegesített kötegszámokkal rendelkezó raktári munka áttekintése és feldolgozása

1. Az **Értékesítési rendelés sorai** gyorslapon válassza ki a **Raktár** \> **Munka készletes adatai** lehetőséget.

    Az értékesítési rendelés soraihoz lefoglalt kötegelt mennyiségek kitárolási műveletét kezelő munka jellemzői:

    - A munka létrehozásához a rendszer munkasablonokat használ, de nem rendelkezik hellyel kapcsolatos irányelvekkel. A program a munkasablonokhoz meghatározott összes szabványos beállítást, például a kitárolási sorok maximális számát vagy egy konkrét mértékegységet alkalmazni fogja, hogy meghatározza, hogy mikor kell új munkát létrehozni. A kitárolási helyek azonosítására szolgáló hely irányelvvel kapcsolatos szabályokat azonban nem veszi figyelembe, mivel a rendelésben véglegesített foglalás már megadja az összes készlet dimenziót. Ezek a készletdimenziók tartalmazzák a raktárak tárolási szintjén levő dimenziókat. Ezért a munka a hellyel kapcsolatos irányelvek egyeztetése nélkül örökli ezeket a dimenziókat.
    - A kötegszám nem jelenik meg a kitárolási sorban (szemben a társított „kötegfölötti\[hely\]” foglalási hierarchiát tartalmazó cikkek esetében létrejövő munkasorokkal). Ehelyett a Kezdő kötegszám és az összes többi tárolási dimenzió látható a munkasorban a társított készlettranzakciók alapján hivatkozott munkakészlet-tranzakcióban.

        ![Raktári készlet tranzakciója olyan munkához, amely rendelésben véglegesített foglalásból származik](media/Work-inventory-transactions-for-order-committed-reservation.png)

    - Miután létrehozta a munkát, a program eltávolítja a cikk azon készlettranzakcióját, amely esetén a **Referencia** mező beállítása **Rendelésben véglegesített foglalás** . Az a készlettranzakció, amelyben a **Referencia** mező beállása **Munka** , most a tényleges foglalást tárolja az összes mennyiség raktárdimenziója esetén.

        A raktári műveletek a szokásos módon folytathatják a munka végrehajtásának kezelését. A mobileszközön érkező utasítások azonban arra utasítják a dolgozót, hogy jelöljön ki egy konkrét kötegszámot. Olyan raktárakban, ahol a helyek rendszámtábla alapján vezéreltek, miután a dolgozó elér egy olyan helyet, ahol ugyanazt a köteget több rendszámtáblán tárolják, kiválaszthatja bármelyik rendszámtáblát, amelyik még nincs lefoglalva (például egy másik rendelésben véglegesített foglalást vagy olyan munkát, amely az adott típusú foglalásból származik.)

        Ha kiderül, hogy a munkasorban megadott helyről történő kitárolás nem praktikus, a raktári kezelők a következő műveletek egyikét alkalmazhatják az adott köteg kitárolásának egy kényelmesebb helyre történő átirányítására:

        - Szabványos **Hely felülbírálása** művelet mobileszközről (feltéve, hogy az illető raktári munkás esetén a **Kitárolási hely felülbírálásának engedélyezése** beállítása engedélyezett)
        - A **Hely módosítása** művelet a **Munkalista részletei** oldalon. 

2. Fejezze be a kitárolást és a munka elhelyezését a mobileszközön.

    A **B11** kötegszámhoz tartozó menniységet ( **10** ) kitárolták az értékesítési rendelési sorra, és elhelyezték a **Baydoor** helyen. Ezen a ponton készen áll a teherautóra történő berakásra, és a vevő címére történő feladásra.

## <a name="flexible-license-plate-reservation"></a>Rugalmas azonosítótábla-foglalás

### <a name="business-scenario"></a>Üzleti eset

Ebben a forgatókönyvben a vállalat raktárkezelést és munkafeldolgozást alkalmaz, illetve a munka létrehozása előtt, a Supply Chain Managementen kívül kezeli a rakománytervezést az egyes raklapok/tárolók szintjén. Ezeket a tárolókat a készletdimenziók modulban az azonosítótáblák jelölik. Ezért ehhez a megközelítéshez a kitárolási munka megkezdése előtt be kell jelölni a megadott azonosítótábla-kiosztást az értékesítési rendeléssorokhoz. A vállalat rugalmasan kívánja kezelni a azonosítótábla-foglalási szabályokat, így a következő viselkedések fordulhatnak elő:

- Az azonosítótábla rögzíthető és lefoglalható, amikor a rendelést az értékesítési feldolgozó átveszi, és más igények során nem alkalmazható. Ez a viselkedés segít annak biztosításában, hogy a tervezett azonosítótáblát szállítsák az ügyfélnek.
- Ha az azonosítótábla még nincs hozzárendelve értékesítési rendeléssorhoz, akkor a raktári személyzet a kitárolási munka során, az értékesítési rendelés regisztrálása és a foglalás befejeződése után kiválaszthatja az azonosítótáblát.

### <a name="turn-on-flexible-license-plate-reservation"></a>Kapcsolja be a rugalmas azonosítótábla-foglalást

A rugalmas azonosítótábla-foglalás használata előtt két funkciót be kall kapcsolni a rendszerében. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat ezen funkciók állapotának ellenőrzéséhez, és szükség esetén a bekapcsolásához. A funkciókat a következő sorrendben kell bekapcsolni:

1. **Funkció neve:** *Rugalmas raktárszintű dimenziófoglalás*
1. **Funkció neve:** *Rugalmas rendeléshez véglegesített azonosítótábla-foglalás*

### <a name="reserve-a-specific-license-plate-on-the-sales-order"></a>Specifikus azonosítótábla foglalása az értékesítési rendelésen

Ha engedélyezni szeretné az azonosítótábla foglalását egy rendelésen, akkor ki kell választania a **Foglalás engedélyezése az igény szerinti rendelésnél** jelölőnégyzetet az **Azonosítótábla** szinten a megfelelő cikkel társított hierarchiához tartozó **Készletfoglalási hierarchiák** oldalon.

![Készletfoglalási hierarchiák oldala a rugalmas azonosítótábla foglalási hierarchiához](media/Flexible-LP-reservation-hierarchy.png)

A rendeléshez tartozó azonosítótábla-foglalást a telepítés bármely pontján engedélyezheti. A módosítás nem fogja érinteni a módosítás előtt létrehozott foglalásokat vagy nyitott raktári munkákat. Azonban a **Foglalás engedélyezése az igény szerinti rendelésnél** jelölőnégyzetet nem tudja törölni, ha az adott foglalási hierarchiához társított egy vagy több cikk esetén a *Rendelésben* , *Foglalt tényleges* vagy *Megrendelve* állapotú nyitott, kimenő készlettranzakció-problémák léteznek.

Még ha az **Azonosítótábla** szintjén be is van jelölve a **Foglalás engedélyezése igény szerinti rendelésnél** jelölőnégyzet, akkor is lehetséges, hogy a rendeléshez *nem* foglalja le az adott azonosítótáblát. Ebben az esetben a foglalási hierarchiára az alapértelmezett raktári műveletek logika vonatkozik.

Ha egy specifikus azonosítótábla-foglalásra van szüksége, egy [Open Data Protocol (OData)](../../fin-ops-core/dev-itpro/data-entities/odata.md) folyamatot kell használnia. Az alkalmazásban ezt a foglalást közvetlenül egy értékesítési rendelésből is megteheti az **Excel programban történő megnyitás** parancs **Azonosítótáblánkénti rendelésben véglegesített foglalások** lehetőségével. Az Excel-bővítményben megnyitott entitásadatokban meg kell adnia a következő foglaláshoz kapcsolódó adatokat, majd ki kell választania a **Közzététel** lehetőséget az adatokat Supply Chain Managementbe történő visszaküldéséhez:

- Hivatkozás (Csak az *Értékesítési rendelés* értéke támogatott.)
- Rendelésszám (Az érték az adagból származtatható.)
- Adagazonosító
- Azonosítótábla
- Mennyiség

Ha egy kötegelt nyomkövetésű cikkhez külön azonosítótábla-foglalásra van szüksége, használja a **Köteg lefoglalása** oldalt az [Értékesítési rendelés adatainak bevitele](#sales-order-details) szakaszban leírtaknak megfelelően.

Amikor a rendeléshez véglegesített azonosítótábla-foglalást használó értékesítési rendeléssort a raktári műveletek dolgozzák fel, a rendszer nem használja a helyutasításokat.

Ha egy raktári munkacikk olyan sorokból áll, amelyek egy teljes raklapnak felelnek meg, és rendelkeznek azonosítótáblával – véglegesített mennyiségekkel, akkor a kitárolási folyamatot egy olyan mobileszköz menüelemével optimalizálhatja, amin a **Kezelés azonosítótábla szerint** értéke *Igen* . A raktári dolgozó ezután a tárolási munka befejezéséhez beolvashatja az azonosítótáblát, és nem kell egyenként beolvasnia a cikkeket.

![A mobileszköz menüeleme, amelyen a Kezelés azonosítótábla szerint lehetőség Igen értékre van állítva](media/Handle-by-LP-menu-item.png)

Mivel a **Kezelés azonosítótábla szerint** funkció nem támogatja a több raklapot magába foglaló munkát, jobb, ha külön munkaelemet használ a különböző azonosítótáblákhoz. Ennek a módszernek a használatához adja hozzá a **Munkasablon** oldalhoz munkafejlécként a **Rendeléshez véglegesített azonosítótábla azonosítója** mezőt.

> [!NOTE]
> A rendeléssel kapcsolatos munka-létrehozási folyamathoz a program egy „rendeléssel kapcsolatos készletdimenzió” értéket rendel a kitárolási munkasorokhoz, és nem lehet közvetlenül megtekinteni a azonosítótábla értékét. A *Felhasználó által irányított* folyamat támogatott a mobileszköz-menüpont beállításakor.

## <a name="example-scenario-set-up-and-process-an-order-committed-license-plate-reservation"></a>Példaforgatókönyv: állítson be és dolgozzon fel egy rendeléshez véglegesített azonosítótábla-foglalást

Ez a forgatókönyv bemutatja, hogyan állítson be és dolgozzon fel egy rendeléshez véglegesített azonosítótábla-foglalást.

### <a name="make-demo-data-available"></a>A bemutató adatok elérhetővé tétele

Ez a forgatókönyv olyan értékekre és rekordokra hivatkozik, amelyek szerepelnek a Supply Chain Management szolgáltatáshoz biztosított standard bemutatóadatokban. Ha a munkát az itt megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan környezetben kell dolgoznia, amelynél a szokásos demóadatok telepítve vannak. Emellett a kezdés előtt állítson be egy jogi személyt az **USMF** lehetőséghez.

### <a name="create-an-inventory-reservation-hierarchy-that-allows-for-license-plate-reservation"></a>Hozzon létre egy olyan készletfoglalási hierarchiát, amely lehetővé teszi az azonosítótábla foglalást

1. Nyissa meg a **Raktárkezelés \> Beállítás \> Készlet \> Foglalási hierarchia lehetőséget** .
1. Válassza az **Új** lehetőséget.
1. Adjon meg egy értéket a **Név** mezőben (pl. *FlexibleLP* ).
1. A **Leírás** mezőben adjon meg egy értéket (például: *Rugalmas LP foglalás* ).
1. A **Kiválasztott** listában válassza ki a **Kötegszám** , **Sorozatszám** , és **Tulajdonos** értéket.
1. Válassza az **Eltávolítás** gomb ![vissza nyíl](media/backward-button.png) lehetőségét a kiválasztott rekordok **Elérhető** listára történő átmozgatásához.
1. Válassza ki az **OK** lehetőséget.
1. Az **Azonosítótábla** dimenzió szintjének sorában jelölje be a **Foglalás engedélyezése igény szerinti rendelésnél** jelölőnégyzetet. A **Hely** szintje automatikusan be van jelölve, és a jelölőnégyzet nem törölhető.
1. Válassza a **Mentés** lehetőséget.

### <a name="create-two-released-products"></a>Két kiadott termék létrehozása

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az **Új kiadás** párbeszédpanelen adja meg a következő értékeket:

    - **Termékszám:** *Cikk1*
    - **Cikkszám:** *Cikk1*
    - **Cikkmodellcsoport:** *FIFO*
    - **Cikkcsoport:** *Audio*
    - **Tárolásidimenzió-csoport:** *Áru*
    - **Nyomonkövetésidimenzió-csoport:** *Nincs*
    - **Foglalási hierarchia:** *RugalmasLP*

1. Válassza az **OK** gombot a termék létrehozásához és a párbeszédpanel bezárásához.
1. Az új termék megnyílik. A **Raktár** gyorslapon állítsa az **Egységszekvenciacsoport-azonosító** mezőt *ea* értékre.
1. Az előző lépések megismétlésével létrehozhat egy második terméket, amelynek ugyanaz a beállítása, de a **Termékszám** és a **Termékazonosító** mezőket a *Cikk2* értékre kell állítani.
1. A Műveleti panelen, a **Készletkezelés lapon** a **Megtekintés** csoportban válassza ki az **Aktuális készlet** lehetőséget. Ezután válassza ki a **Mennyiség kiigazítása** lehetőséget.
1. Állítsa be az új cikkek aktuális készletét a következő táblában meghatározott módon.

    | Tétel  | Raktár | Hely | Azonosítótábla | Mennyiség |
    |-------|-----------|----------|---------------|----------|
    | Cikk1 | 24        | FL-010   | LP01          | 10       |
    | Cikk1 | 24        | FL-011   | LP02          | 10       |
    | Cikk2 | 24        | FL-010   | LP01          | 5        |
    | Cikk2 | 24        | FL-011   | LP02          | 5        |

    > [!NOTE]
    > Létre kell hoznia a két azonosítótáblát, és olyan helyeket kell – például *FL-010* és *FL-011* – használnia, amelyek engedélyezik a vegyes cikkek használatát.

### <a name="create-a-sales-order-and-reserve-a-specific-license-plate"></a>Hozzon létre értékesítési rendelést, és foglaljon le egy specifikus azonosítótáblát

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. Válassza az **Új** lehetőséget.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - **Vevőkód** *US-001*
    - **Raktár:** *24*

1. Válassza az **OK** gombot az **Értékesítési rendelés létrehozása** párbeszédpanel bezárásához, és nyissa meg az új beszerzési rendelést.
1. Az **Értékesítésirendelés-sorok** gyorslapon adjon hozzá egy sort, amely a következő beállításokat tartalmazza:

    - **Cikkszám:** *Cikk1*
    - **Mennyiség:** *10*

1. Adjon hozzá egy második értékesítési rendeléssort, amelynek beállításai a következők:

    - **Cikkszám:** *Cikk2*
    - **Mennyiség:** *5*

1. Válassza a **Mentés** lehetőséget.
1. A **Sor részletei** gyorslapon,, a **Beállítás** lapon jegyezze fel az egyes sorok **Adagazonosító** értékét. Ezekre az értékekre szükség lesz a specifikus azonosítótábla foglalásakor.

    > [!NOTE]
    > Ha egy specifikus azonosítótábla foglalására van szükség, akkor az **Azonosítótáblánkénti rendelésben véglegesített foglalások** adatentitást kell használnia. Egy kötegelt nyomkövetésű cikkhez specifikus azonosítótábla-foglaláshoz használhatja a **Köteg lefoglalása** oldalt az [Értékesítési rendelés adatainak bevitele](#sales-order-details) szakaszban leírtaknak megfelelően.
    >
    > Ha közvetlenül az értékesítési rendeléssorban adja meg a azonosítótáblát, és megerősíti azt a rendszerben, akkor a raktárkezelés feldolgozását nem használják a sorhoz.

1. Válassza a **Megnyitás Microsoft Office-ban** , majd az **Azonosítótáblánkénti rendelésben véglegesített foglalások** lehetőséget, és töltse le a fájlt.
1. Nyissa meg az Excel programban a letöltött fájlt, és válassza a **Szerkesztés engedélyezése** lehetőséget az Excel-bővítmény futtatásának engedélyezéséhez.
1. Ha az Excel beépülő modult első alkalommal futtatja, válassza az **Ez a bővítmény megbízható** lehetőséget.
1. Ha a rendszer bejelentkezést kér, válassza a **Bejelentkezés** lehetőséget, majd a Supply Chain Management bejelentkezéshez használt hitelesítő adatok használatával jelentkezzen be.
1. Ha egy cikk foglalását egy adott azonosítótáblához szeretné lefoglalni, az Excel-bővítményben válassza az **Új** lehetőséget a foglalási sor hozzáadásához, majd állítsa be a következő értékeket:

    - **Adagazonosító:** Adja meg a *Cikk1* értékesítési rendelési sorában talált **Adagazonosító** értéket.
    - **Azonosítótábla:** *LP02*
    - **Készletmennyiség lefoglalása:** *10*

1. Válassza ki az **Új** lehetőséget egy további foglalási sor hozzáadásához, és állítsa be a következő értékeket:

    - **Adagazonosító:** Adja meg a *Cikk2* értékesítési rendelési sorában talált **Adagazonosító** értéket.
    - **Azonosítótábla:** *LP02*
    - **Készletmennyiség lefoglalása:** *5*

1. Az Excel-bővítményben válassza a **Közzététel** lehetőséget, ha vissza szeretné küldeni az adatokat a Supply Chain Management szolgáltatásba.

    > [!NOTE]
    > A foglalási sor csak akkor jelenik meg a rendszerben, ha a közzététel hibátlanul befejeződött.

1. Menjen vissza a Supply Chain Management szolgáltatásba. 
1. A cikk foglalásának megtekintéséhez kattintson az **Értékesítési rendeléssorok** gyorslapon a **Készlet** menüre, majd válassza a **Megtartás \> Foglalás** pontra. Figyelje meg, hogy a *Cikk1* értékesítési rendeléssorához a *10* -es készlet van lefoglalva, a *Cikk2* értékesítési rendeléssorához pedig az *5* -ös készlet van lefoglalva.
1. Az értékesítési rendeléssor foglalásához kapcsolódó készlettranzakciók áttekintéséhez kattintson az **Értékesítési rendeléssorok** gyorslap **Készlet** menüre, és válassza a **Megtekintés \> Tranzakciók** pontot. Figyelje meg, hogy két olyan tranzakció van, amely a foglaláshoz kapcsolódik: az egyikben a **Hizatkozás** mező *Értékesítési rendelés* lehetőségre van állítva, a másiknál pedig a **Hivatkozás** mező *Rendelésben véglegesített foglalás* lehetőségre van állítva.

    > [!NOTE]
    > Egy olyan tranzakció, amelyben a **Hivatkozás** mező értéke *Értékesítési rendelés* értékre van állítva, a **Hely** szint fölötti készletdimenziók sorának foglalását jelenti (webhely, raktás és készletállapot). Az olyan tranzakció, amelyben a **Hivatkozás** mező a *Rendelésben véglegesített foglalás* értékre van állítva, a megadott azonosítótábla és hely rendelési sor foglalását jelenti.

1. Az értékesítési rendelés kiadásához a műveleti ablaktáblán a **Raktár** lapon a **Műveletek** csoportban válassza a **Kiadás raktárhoz** lehetőséget.

### <a name="review-and-process-warehouse-work-with-order-committed-license-plates-assigned"></a>A raktári munka áttekintése és feldolgozása a hozzárendelt, rendelésben véglegesített azonosítótáblával

1. Az **Értékesítési rendelés sorai** gyorslap **Raktár** menüjében válassza a **Munka részletes adatai** lehetőséget.

    Amikor egy adott köteg foglalása befejeződik, a rendszer nem használja a helyutasításokat, amikor létrehozza az azonosítótábla-foglalást használó értékesítési rendeléshez tartozó munkát. Mivel a rendelésben véglegesített foglalás meghatározza az összes készletdimenziót, többek között a helyet is, így nem kell használni a helyutasításokat, mivel ezek a készletdimenziók csak a munkában szerepelnek. Ezek a **Munkakészlet-tranzakciók** lap **Készletdimenziókból** szakaszában jelennek meg.

    > [!NOTE]
    > Miután létrehozta a munkát, a program eltávolítja a cikk azon készlettranzakcióját, amely esetén a **Referencia** mező beállítása *Rendelésben véglegesített foglalás* . Az a készlettranzakció, amelyben a **Referencia** mező beállása *Munka* , most a tényleges foglalást tárolja az összes mennyiség raktárdimenziójához.

1. A mobileszközön végezze el a munka ki- és betárolást egy olyan menüelem használatával, ahol ki van pipálva a **Kezelés azonosítótábla szerint** jelölőnégyzet.

    > [!NOTE]
    > A **Kezelés azonosítótábla szerint** funkció segít a teljes azonosítótábla feldolgozásában. Ha az azonosítótábla egy részét mindenképpen fel kell dolgoznia, akkor ez a funkció nem használható.
    >
    > Azt javasoljuk, hogy minden azonosítótáblához külön hozzon létre egy munkát. Ennek érdekében használja a **Munkasablon** lap **Munkafejléc-szünetek** funkcióját.

    Az *LP02* azonosítótáblát ezennel már kitárolták az értékesítési rendeléssorokban, és betárolták a *Baydoor* helyre. Ezen a ponton készen áll a berakásra, és a vevőnek történő feladásra.

## <a name="exception-handling-of-warehouse-work-that-has-order-committed-batch-numbers"></a>A rendeléshez véglegesített kötegszámokkal rendelkezó raktári munka kivételkezelése

A rendeléshez véglegesített kötegszámokkal kitárolási raktári munkájának a kivételkezelése és műveletei ugyanazok, mint a normális munkának. Általában a nyitott munka vagy munkasor érvényteleníthető, megszakítható, mert egy felhasználói hely megtelt, a kitárolása lehet rövid, és egy mozgás miatt módosítható. Hasonlóképpen a már elvégzett munka kitárolt mennyisége is csökkenthető, illetve a munka visszafordítható.

A program a következő kulcsfontosságú szabályt alkalmazza az összes ilyen kivételkezelési műveletre: a vevő számára lefoglalt kötegszám nem cserélhető ki egy másik kötegszámra, de a tárolási dimenziói (hely és rendszámtábla) módosíthatók akár egy a felhasználó általi manuális vagy a rendszer általi automatikus frissítéssel. Az automatikus frissítés a tárolási dimenziók ugyanazon véletlen hozzárendelése alapján történik, amelyeket egy konkrét köteg automatikus visszafordításakor alkalmaznak, ha nincsenek megadva tárolási dimenziók.

### <a name="example-scenario"></a>Példaforgatókönyv

Példa erre a helyzetre olyan eset, amikor a korábban elvégzett munka kitárolását a **Kitárolt mennyiség csökkentése** funkció használatával visszavonják. Ez a példa feltételezi, hogy már befejezte a [Példaforgatókönyv: Köteg számának felosztása](#Example-batch-allocation) részben leírt lépéseket. Ettől a példától folytatódik.

1. Lépjen a **Raktárkezelés** \> **Rakományok** \> **Aktív rakományok** elemhez.
2. Válassza ki az értékesítési rendelés szállítmányával együtt létrehozott terhelést.
3. A **Terhelési rendelés sorai** gyorslapon válassza ki a **Kitárolt mennyiség csökkentése** lehetőséget.
4. A **Kitárolt mennyiség csökkentése** lapon az **Áthelyezés helyre** mezőben válassza az **FL-001** elemet.
5. Az **Áthelyezés azonosítótáblára** mezőben válassza az **LP33** lehetőséget.
6. A rácsban a **Visszatárolandó készletmennyiség** mezőbe írja be a **10** értéket.
7. Válassza ki az **OK** lehetőséget.

A visszatárolási művelet eredményei:

- A korábban lezárt munka állapotát a rendszer **Visszavonva** értékre állítja.
- Új, **Készletmozgás** típusú munka jön létre a **B11** kötegszám esetén visszatárolt mennyiséghez ( **10** ). Ez a munka a **Baydoor** helyről az **FL-001** helyen található **LP33** rendszámtáblához való mozgást jelzi. Az rendszer átállítja az állapotot erre: **Lezárva** .
- A rendszer újra lefoglalja az eredetileg megrendelt kötegszámot, és hozzárendeli a helyet és a rendszámtábla azonosítóit. (Ez a folyamat egyenértékű a rendeléssor **Sor foglalása** funkciójának futtatásával egy adott kötegszám esetén). Ennek eredményekétten a **B11** köteg a **Köteg lefoglalása** oldal **Forrássorhoz vállalt kötegszámok** gyorslapján vállaltként jelenik meg, és a **Foglalás** mező a **B11** kötegszám esetén a **10** mennyiséget tartalmazza. Ezenkívül a **Hely** mező értéke **FL-001** , és a **Rendszámtábla** mező értéke **LP11** . (Hozzáadhatja ezeket a mezőket a rácshoz, ha nem láthatók.)

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
<li>Válassza ki a <strong>Hely felülbírálása</strong> menüpontot a raktárkezelő alkalmazásban a kitárolási munka megkezdésekor.</li>
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
<td>Nincs</td>
<td>
<ol>
<li>Válassza ki a <strong>Hely felülbírálása</strong> menüpontot a raktárkezelő alkalmazásban a kitárolási munka megkezdésekor.</li>
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
<li>Válassza ki a <strong>Teljes</strong> menüpontot a raktárkezelő alkalmazásban a kitárolási munka feldolgozásakor.</li>
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
<li>Kezdje meg a mozgatást a raktárkezelő alkalmazáson.</li>
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
<li>Válassza ki a <strong>Rövid kitárolás</strong> menüpontot a raktárkezelő alkalmazásban a kitárolási munka futtatásakor.</li>
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
<li>Válassza ki a <strong>Rövid kitárolás</strong> menüpontot a raktárkezelő alkalmazásban a kitárolási munka futtatásakor.</li>
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
<li>Válassza ki a <strong>Rövid kitárolás</strong> menüpontot a raktárkezelő alkalmazásban a kitárolási munka futtatásakor.</li>
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
<td>Nincs</td>
<td>
<ol>
<li>Válassza ki a <strong>Rövid kitárolás</strong> menüpontot a raktárkezelő alkalmazásban a kitárolási munka futtatásakor.</li>
<li>Írja be a <strong>0</strong> (nulla) értéket a <strong>Rövid kitárolási mennyiség</strong> mezőbe.</li>
<li>Az <strong>Ok</strong> mezőben válassza ki a <strong>Rövid kitárolást manuális újrafelosztással</strong> lehetőséget.</li>
</ol>
</td>
<td>A rövid kitárolási művelet nem sikerült, és a program hibát jelez.</td>
<td>Nem alkalmazható</td>
</tr>
<tr>
<td>A <strong>Rövid kitárolás</strong> típusra munkakivétel ven beállítva, amelynek értelmében <strong>Cikk újbóli felosztása</strong> = <strong>Manuális</strong>, <strong>Készlethelyesbítés</strong> = <strong>Igen</strong>, és <strong>Foglalások eltávolítása</strong> = <strong>Igen</strong>. Ezenkívül a <strong>Cikk újbóli manuális felosztásának engedélyezése</strong> beállítás a dolgozó esetén engedélyezve van.</td>
<td>Nincs</td>
<td>
<ol>
<li>Válassza ki a <strong>Rövid kitárolás</strong> menüpontot a raktárkezelő alkalmazásban a kitárolási munka futtatásakor.</li>
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
<li>Válassza ki a <strong>Rövid kitárolás</strong> menüpontot a raktárkezelő alkalmazásban a kitárolási munka futtatásakor.</li>
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
