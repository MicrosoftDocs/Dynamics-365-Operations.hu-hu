---
title: Átalakítás elszámolóárra – áttekintés
description: Ezen cikk tájékoztatást nyújt arról, hogy hogyan lehet beállítani és futtatni az elszámolóár-átalakítást. Miután elvégezte az elszámolóárra való átalakítás előfeltételeit végre kell hajtania a felsorolt lépéseket.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.custom: 78212
ms.assetid: d601d9d5-1de3-4868-aff4-534dca01d624
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fdcb45918b404f8a47f27bcea7c02a8397c9336f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821441"
---
# <a name="standard-cost-conversion-overview"></a>Átalakítás elszámolóárra – áttekintés

[!include [banner](../includes/banner.md)]

Ezen cikk tájékoztatást nyújt arról, hogy hogyan lehet beállítani és futtatni az elszámolóár-átalakítást. Miután elvégezte az elszámolóárra való átalakítás előfeltételeit végre kell hajtania a felsorolt lépéseket. 

Használja az **Elszámolóár-átalakítások** oldalt a kiválasztott elemek kötegeire vonatkozó készletmodell a tényleges költségszámítási megközelítésből a szabványos költségszámítási megközelítéshez történő konvertálásához. Az átalakítási folyamat magába foglalja az előfeltételes készletzárást és számos lépést az átmeneti időszak során, amely meghatározza az átmenet kezdési dátumát és a tervezett átalakítási dátumot, majd ezt követően bezárja az átalakítás és a kapcsolódó készletadag.

-   Készletzárás az átmeneti időszak előtt − A készletzárás végrehajtása az átalakítás előfeltétele, mivel így a régi értékelési módszerrel kiegyenlíti a cikkek nyitott tranzakcióit. Az átmeneti időszak során megadhatja és feladhatja a visszadátumozott tranzakciókat, mint például a számlákat, így bezárhatja a megelőző időszakot. A készletzárás dátumának egy nappal az átmeneti időszak kezdési dátuma előttinek kell lennie annak érdekében, hogy világosan elváljon egymástól a régi és az új készletértékelési módszer.
-   Átalakítási lépések az átmeneti időszakban – Használja az **Elszámolóár-átalakítások** oldalt a felhasználói azonosítóját tartalmazó átalakítási rekord létrehozásához az új költségszámítási verzióra vonatkozóan. Az átalakítást igénylő cikkeket azonosítja, majd ezt követően megadja a cikk függő beruházási költségeit az új költségszámítási verzióban. A kijelölt cikkek ellenőrzését azon kiadások azonosítása érdekében hajtja végre, amelyek megakadályozhatják az átalakítást, kijavíthatják a kiadásokat, majd ezt követően egy másik ellenőrzést hajthatnak végre. Miután a cikkek sikeresen megfeleltek az ellenőrzésen, módosítsa az átalakítási rekord állapotát **Kész** lehetőségre. A tervezett átalakítási dátumon hajtsa végre az átalakítást, választhatóan egy készletzárással együtt. Egy cikk készletmozgásai a régi készletmodell szerint vannak feladva és értékelve az átmeneti időszak során. Ezután az átalakítás sikeres befejezése után a készletmozgások újra vannak értékelve az elszámolóárra.
-   Készletzárás az átalakítás előtt − A készletzárás része lehet a tervezett átalakítási dátum napján végrehajtott átalakításnak, vagy külön lépésként hajtható végre az átalakítást megelőzően.

Miután az átalakítási folyamat sikeresen befejeződött minden egyes cikkre vonatkozó készletmodell az elszámolóáron alapszik és a cikk elszámolóára engedélyezetté válik. Az ezt követő készlet-tranzakció kiértékelése a cikk elszámolóára alapján történik. Továbbá, a rendszer átalakítja a cikk tényleges készlet-tranzakcióját az átalakítási napon alapuló elszámolóárhoz a nyugtákra és a kiadásokra vonatkozóan. A rendszer átalakítja a cikk pénzügyi készletét is az elszámolóárra, és az értékben szereplő eltérést egy készletértékelésként adja fel. Az átalakítást követően minden tranzakció értékelése a cikkek elszámolóára alapján történik. Az átalakítás dátuma előtti dátumra nem dátumozhat vissza tranzakciókat, mivel az átalakítás előtt egy nappal készletzárást hajtott végre. Az átalakítás csak akkor hajtható végre, ha a készletzárást egy nappal korábban elvégezte. A készletzárást nem lehet érvényteleníteni.

## <a name="1-define-a-standard-cost-conversion-record-and-the-associated-costing-version"></a>1. Határozza meg az elszámolóárra történő átalakítás rekordját és az ahhoz tartozó költségszámítási verziót.
Használja az **Elszámolóár-átalakítások** oldalt az átalakítási rekord létrehozásához. Új átalakítási rekordot csak akkor lehet létrehozni, ha a meglévő átalakítási rekordokat már befejezték. A tervezett átmeneti időszak hosszát az átmenet kezdési dátuma és a tervezett átalakítási dátum határozza meg. A tervezett átmeneti időszak akár egyetlen nap is lehet. A tervezett átmeneti időszak segítségével győződjön meg arról, hogy az átalakítási folyamatnak elegendő ideje van az összes lépés végrehajtásához. A készletzárást végre kell hajtani az átmenet kezdési dátuma előtt egy nappal annak érdekében, hogy a biztosítani tudja, hogy a kiegyenlítések az átalakítási folyamat előtt egy nappal befejeződjenek. Annak érdekében, hogy meggyőződhessen arról, hogy az átmenet kezdési dátuma és a készletzárás dátuma megfelelően van kiválasztva, vagy módosíthatja az átmenet kezdési dátumát a meglévő készletzárást követő napra vagy végrehajthatja a készletzárást. Az átalakítási rekord rögzítésekor meg kell adnia annak az új költségszámítási verziónak a felhasználói azonosítóját, amely az átalakított cikkek elszámolóárát fogja tartalmazni. A költségszámítási verzió automatikusan létrejön a költségszámítási verzió mentésekor.

## <a name="2-review-and-change-the-new-costing-version-for-the-conversion-record"></a>2. Tekintse át és módosítsa az új költségszámítási verziót az átalakítási rekordra vonatkozóan.
Az újonnan létrehozott költségszámítási verzió hozzá van rendelve az átalakítási rekordhoz, mivel jelzi az **Átalakítás** költségszámítási típusa. A hozzárendelt költségszámítási verzió hasonlít a beruházási költségek költségszámítási verziójához és az átalakítási rekordhoz társított cikkek költségrekordjait tartalmazza. Az átalakítási rekordhoz hozzárendelt költségszámítási verziót a következőképpen kell beállítani, amelyet át kell tekintenie és módosítania kell szükség szerint a különböző füleken:

-   **Költségszámítási típus:** Ezt a mezőt **Elszámolóár** lehetőségre kell beállítani.
-   **Verzió:** A verzióazonosító a költségszámítási verzió azonosítójának átalakítási rekordjában megadott információkat jeleníti meg.
-   **Név:** Alapértelmezés szerint a név üres. Választhatóan adhatja meg a nevet.
-   **Zárolás:** Ezt a mezőt **Nem** lehetőségre kell beállítani. Egészen addig adhatja meg a költségrekordokat a költségszámítási verzióhoz, amíg nem módosítja az átalakítási rekord állapotát **Kész** értékre. A **Kész** állapot azt jelenti, hogy a kijelölt tételeket ellenőrizték, és a költségrekordok módosítása nem engedélyezett.
-   **Zárolás aktiválása:** Ezt a mezőt **Igen** lehetőségre kell beállítani. A hozzárendelt költségszámítási verzióban nem lehet manuálisan módosítani a függő költségrekordokat. Az aktiválás az átalakítás végrehajtásakor történik meg.
-   **Kezdő dátum:** A kezdő dátum azt a tervezett átalakítási dátumot jelöli, amelyet megadott az átalakítási rekordban.
-   **Oldal:** Hagyja üresen ezt a mezőt, hogy a költségrekordokat bármely webhely számára meg lehessen adni.
-   **Ár típusa mezőcsoport engedélyezése:** Állítsa ezt a mezőt **Igen** értékre, hogy csak az önköltségi ár rekordjait lehessen megadni.
-   **Tartalékelv:** Ezt a mezőt **Nincs** értékre kell beállítani. Módosítsa a tartalékelv állapotát **Aktív** értékre, ha olyan költségadatokra van szüksége, amelyeket más költségszámítási verziókban már aktiváltak. Például előfordulhat, hogy az összetevők, a költség kategóriák és a közvetett költségek költségadataira szükség van a gyártott cikkek költségeinek kiszámítása érdekében.
-   **Tartalék költségszámítási verzió:** Hagyja üresen a mezőt.

A hozzárendelt költségszámítási verzióban lévő cikk-költség adatokat csak az **Átalakítások elszámolóárra** képernyőn keresztül lehet karbantartani. Nem használhatja a **Költségszámítási verzió beállítása** lapot vagy a **Költségszámítási verzió karbantartása** lapot a költségszámítási verzióra vonatkozó költségek kiszámítására az átalakítás során. Ezen lapokat azonban csak akkor használhatja a hozzárendelt költségszámítási verzió tartására, miután befejezte az átalakítási verziót.

## <a name="3-identify-the-items-to-convert-to-standard-cost"></a>3. Határozza meg, hogy cikket alakítja át elszámoló áras cikké.
Használja az **Elszámolóár-átalakítások** lapot azon cikkek azonosítására, amelyeket elszámolóáras cikkekké kell konvertálni. A **Cikkek hozzáadása az elszámolóárra való átalakítás** oldal segítségével több cikket is megadhat. Az egyetlen átalakítási rekordnak minden gyártott cikket tartalmaznia kell ahhoz, hogy a költségek számítása megfelelő legyen.

## <a name="4-enter-or-calculate-the-pending-standard-cost-for-each-item-that-is-being-converted"></a>4. Adja meg vagy számítsa ki a függő elszámolóárat minden egyes átalakítandó cikkre.
A **Cikk ára** képernyőn adja meg a függő elszámolóárat a beszerzett cikkek és átvitt cikkek hozzárendelt költségszámítási verziójában. A költségrekordok telephelyfüggőek, tehát a cikkek függő költségeit minden telephelyre külön meg kell adni. A **Cikk ára** képernyőn számítsa ki a gyártott cikkek függő elszámolóárát. A gyártott cikkek függő költségeit minden termékgyártási webhelyre vonatkozóan kell kiszámítani, kivéve ha a webhely egy átmeneti telephelyként működik. Ebben az esetben a függő költségeket manuálisan kell beírni. Egyes cikkek rendelkezhetnek szín, méret vagy konfigurációs termékdimenziókkal. Az **Elszámolóár-átalakítások** lapon a **Változatonkénti önköltségi ár használata** jelölőnégyzet a cikkdimenziók összes kombinációjára vonatkozó elszámolóárát megjeleníti. Ha a jelölőnégyzet nincs bejelölve, akkor csak egy függő költséget kell megadni a cikkhez.

## <a name="5-check-and-resolve-any-issues-for-the-items-that-are-being-converted"></a>5. Ellenőrizze, hogy vannak-e hibák az átalakítandó cikkekben, és javítsa ki azokat.
Az **Elszámolóár-Átalakítás elszámolóárra-ellenőrzések** jelentés segítségével azonosíthatja az átalakítandó cikkre vonatkozó kiadásokat. Ha egy cikk problémamentes, akkor az átalakítási rekordban látható állapotot **Ellenőrizve** értékre kell állítani. Ha cikkben észlelhető probléma, akkor ki kell javítani azokat, majd újra kell futtatni a jelentést egészen addig, amíg a cikk állapota **Ellenőrizve** értékű nem lesz. Ha egy cikk problémái nem oldhatók meg elfogadható időn belül, akkor lehetőség van arra, hogy törölje a cikket az átalakítási rekordból, és a cikket egy későbbi időpontban alakítsa át.

## <a name="6-change-the-status-of-the-conversion-record-to-ready"></a>6. Módosítsa az átalakítási rekord állapotát Kész értékre.
Ha az átalakítási rekord állapotát **Kész** értékre állította, a rendszer elvégzi a végső ellenőrzést az Átalakítás elszámolóárra funkció futtatását megelőzően. Az állapota csak akkor vált **Kész** értékre, ha teljesülnek a következő feltételek:

-   Az átalakítási rekordon belül minden cikk állapota **Ellenőrizve** értékű.
-   Az átmenet kezdési dátumát megelőzően egy nappal végrehajtották a készletzárást. Annak érdekében, hogy meggyőződhessen arról, hogy az átmenet kezdési dátuma és a készletzárás dátuma megfelelően van kiválasztva, vagy módosíthatja az átmenet kezdési dátumát a meglévő készletzárást követő napra vagy végrehajthatja a készletzárást.

## <a name="7-back-up-the-database-before-conversion"></a>7. Készítsen biztonsági másolatot az adatbázisról az átalakítás előtt
A biztonsági mentés lehetővé teszi az adatbázis helyreállítását, ha hiba merül fel az átalakítási folyamat során.

## <a name="8-perform-the-conversion-when-the-conversion-record-has-a-ready-status"></a>8. Hajtsa végre az átalakítást, ha az átalakítási rekord állapota Kész értékű.
Az átalakítási folyamat megköveteli, hogy a tervezett átalakítási dátum előtt egy nappal végrehajtsák a készletzárást. Ezen követelmény segítségével gondoskodhat arról, hogy az átalakítási időszakban ne adhassanak meg visszadátumozott tranzakciókat. Ha még nem hajtotta végre a készletzárást, akkor a rendszer rákérdez, hogy az átalakítási folyamat részeként végre kívánja-e végrehajtani a készletzárást. Az átalakítási folyamat egyszerre egy cikket kezel. A termékszerkezetben szereplő legalacsonyabb cikkel kezdődik a cikkek alsó szintű kódja alapján. Amikor egy cikket sikeresen átalakított, akkor az átalakítási rekordban az állapota **Felismert** értékűre változik. Ha az átalakítási folyamat megszakad, akkor a még nem átalakított cikkek állapota **Ellenőrizve** értékű marad. Az átalakítási folyamat sikeres végrehajtása a következő hatásokkal jár:

-   Az átalakítási rekord állapota **Kész** értékről, **Befejeződött** értékűre változik, és minden kijelölt elem állapota **Bejelölt** értékről **Felismert** értékre módosul.
-   Az átalakított cikkek készletmodellcsoportja módosul, és ezután egy elszámolóáras készletmodell új csoportját jelöli.
-   Az átalakított cikkek elszámolóára engedélyezetté válik a hozzárendelt költségszámítási verzióban.
-   A költségszámítási verzió költségszámítási típusa **Konverzió** értékről **Elszámolóár** értékre módosul, és a költségszámítási verzió ezt követően ugyanúgy viselkedik, mint az elszámoló árak többi verziója.

## <a name="9-validate-and-reconcile-the-inventory-values-for-the-converted-items"></a>9. Érvényesítse és egyeztesse az átalakított cikkekre vonatkozó készletértékeket.
A **Különbözetelemzési kimutatás** jelentés segítségével elemezheti az átértékelési eltérést és az **Készletérték** jelentés lehetővé teszi a készletérték megjelenítését egy adott dátumon.

-   Elemezze az újraértékeléssel járó eltéréseket. A **Különbözetelemzési kimutatás** jelentés segítségével megtekintheti az átalakított cikkek készletértékelési eltéréseit. Az **Elszámolóáras tranzakciók** oldalt is használhajta a készlettel rendelkező átalakított cikkek készlet újraértékelési tranzakcióinak megtekintéséhez.
-   Vizsgálja meg a készletértékeket az átmenet kezdési dátuma előtt. A **Készletérték** jelentés segítségével megtekintheti az átalakított cikkek készletértékeit. A jelentés záró dátumához az átmeneti időszak kezdési dátumát megelőző nap dátumát használja.
-   Vizsgálja meg a készletértéket az átalakítás kezdési dátuma előtt. A **Készletérték** jelentés segítségével megtekintheti az átalakított cikkek készletértékeit. A jelentés záró dátumaként az átalakítási időszakkezdési dátumát megelőző nap dátumát használja.
-   Vizsgálja meg a készletértékeket az átalakítás napján. A **Készletérték** jelentés segítségével megtekintheti az átalakítás napján érvényes készletértékeket. A jelentés kezdő és záró dátumának egyaránt az átalakítás dátumának kell lennie. A jelentés kiválasztási feltételeinek az átalakított cikkeket kell eredményül adnia.
-   Vizsgálja meg a visszadátumozott készletmozgásokat. A **Készletérték** jelentés segítségével megtekintheti az átalakítás után megadott visszadátumozott készletmozgásokat. A „Jelentés kezdő és záró dátumának meg kell fellelnie az átmenet kezdési dátumának és az átalakítást megelőző nap dátumának. A jelentés kiválasztási feltételeinek az átalakított cikkeket kell eredményül adnia. A jelentés megjeleníti azokat a készletmozgásokat, amelyeket az elszámolóárnál hoztak létre az átmeneti időszak során.


<a name="additional-resources"></a>További erőforrások
--------

[Az elszámolóárra való átalakítás előfeltételei](prerequisites-standard-cost-conversion.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]