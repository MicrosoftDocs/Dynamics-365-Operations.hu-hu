---
title: Bevételelszámolás újbóli felosztása
description: Ez a témakör az újbóli felosztás lehetőségét ismerteti, amellyel a szervezetek újraszámíthatják a bevételi árakat, ha megváltoznak a szerződéses értékesítési feltételek. Más témakörökre mutató hivatkozásokat is talál itt, amelyek a bevételelszámolás különböző eseteit írják le.
author: kweekley
ms.date: 09/09/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7528202ed140dc2c0a7fc8c595178f155c3c1f75
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2022
ms.locfileid: "8726127"
---
# <a name="revenue-recognition-reallocation"></a>Bevételelszámolás újbóli felosztása

[!include [banner](../includes/banner.md)]

Az újbóli elszámolás lehetővé teszi a szervezeteknek, hogy újraszámítsák a bevételi árakat, ha megváltoznak a szerződéses értékesítési feltételek. A bevételelszámolás szempontjából az értékesítési rendelés dokumentumai is szerződésnek számítanak.

A szervezetnek önállóan kell eldöntenie, hogy szükséges-e az újbóli felosztás. Az értékesítési rendelés új sorral való kiegészítése és a vevő új értékesítési rendelésének létrehozása nem minden esetben számít szerződésmódosításnak. A következő esetekben azonban újbóli felosztásra lehet szükség:

- A vevő a rendelés teljes vagy részleges kiszámlázása után további cikkeket ad hozzá az értékesítési rendeléshez, vagy egyes cikkeket eltávolít az értékesítési rendelésből.
- Egy elfogadott szerződéshez több megerősített vagy számlázott állapotú értékesítési rendelést adnak hozzá.
- A vevő az eredeti értékesítési rendelés teljes vagy részleges kiszámlázása után visszaküld egy cikket vagy jóváírást kap egy cikk után.

Az újbóli felosztási folyamatra néhány fontos korlátozás vonatkozik:

- A folyamat csak egyszer futtatható. Ezért fontos, hogy csak az összes módosítás véglegesítését követően futtassa le a folyamatot.

    - Ez a korlátozás a 10.0.17-es és későbbi verziókból el lett távolítva.

- A folyamat nem futtatható a projekt típusú értékesítési rendeléseken.

    - Ez a korlátozás a 10.0.17-es és későbbi verziókból el lett távolítva.

- Több értékesítési rendelés esetén csak akkor futtatható, ha ezek ugyanahhoz a vevőfiókhoz tartoznak.
- Az újból felosztott értékesítési rendeléseknek ugyanazt a tranzakciós pénznemet kell használniuk.
- A folyamatot a futtatás után nem lehet sztornírozni, sem visszavonni.

    - Ez a korlátozás a 10.0.17-es és későbbi verziókból el lett távolítva.

- Az újraelosztás csak értékesítési rendelések vagy projekt értékesítési rendelések esetében lehetséges. Értékesítési rendelések és projekt értékesítési rendelések kombinációja esetén nem lehetséges.

    - Ez a korlátozás a 10.0.17-es és későbbi verziókból el lett távolítva.

## <a name="set-up-reallocation"></a>Az újbóli felosztás beállítása

Az újból felosztás folyamatát egy paraméter befolyásolja.

Mivel az újbóli felosztást a részben vagy teljesen kiszámlázott értékesítési rendeléseken lehet lefuttatni, a számla minden korábbi könyvelési tételét az új, újbóli felosztás szerinti bevételi árak alkalmazásával kell korrigálni. A korrekcióhoz sztornírozni kell az eredeti számlához tartozó könyvelési tételt, majd fel kell adni az újbóli felosztás szerinti bevételi árakon alapuló új könyvelési tételt.

Minden szervezetnek el kell döntenie, hogy a korrekció csak a főkönyvet frissítse vagy a kinnlevőségeket is. Ennek alapján ki kell választani a megfelelő beállításokat a **Számlajavítások feladása a Kinnlevőségekbe** lehetőségnél, amely a **Bevételelszámolás** lapon, a **Főkönyvi paraméterek** oldalon található (**Bevételelszámolás \> Beállítás \> Főkönyvi paraméterek**). A megfelelő beállítás az adott esettől függ. A lehetséges esetekkel kapcsolatos további információkért nyissa meg a témakör későbbi részében, az [Újbóli felosztáshoz kapcsolódó esetek](#scenarios-for-reallocation) című szakaszában található hivatkozásokat.

[![A Bevételelszámolás lap a Főkönyvi paraméterek oldalon.](./media/01_RevRecScenarios.png)](./media/01_RevRecScenarios.png)

Ha a **Számlajavítások feladása a Kinnlevőségekbe** lehetőségnél az **Igen** értéket választja, az újbóli felosztási folyamat a következő eredménnyel zárul:

- A kinnlevőségekben létrejön egy hiteldokumentum, amely sztornírozza a korrekciót igénylő számlát.

    - A hiteldokumentum az eredeti számla számát használja, amelyhez azonban hozzáfűzi a „-1” utótagot.
    - A rendszer automatikusan összeveti az eredeti számlát és a hiteldokumentumot. Ha az eredeti számlát már kiegyenlítették egy másik hiteldokumentummal vagy kifizetéssel, a rendszer automatikusan sztornírozza a kiegyenlítést.
    - A rendszer feladja a hiteldokumentumot a főkönyvbe, hogy sztornírozza az eredeti számlához feladott könyvelési tételt. A Készlet és az Eladott áruk beszerzési értéke (ELÁBÉ) tranzakciótételeket azonban a rendszer nem sztornírozza.

- Az újbóli felosztás utáni áron alapuló új számla létrejön a kinnlevőségekben.

    - Az új számla az eredeti számla számát használja, de hozzáfűzi a „-2” utótagot.
    - Az új számlát a rendszer automatikusan kiegyenlíti a korábban az eredeti számla alapján kiegyenlített hiteldokumentumok vagy kifizetések szerint.
    - A rendszer feladja az újbóli felosztás utáni bevételi ár összegével frissített új számlát a főkönyvbe. A rendszer nem adja fel újra a számlát a Készlet és az ELÁBÉ számlákba, mivel ezeket a tételeket az eredeti számla könyvelési tételei szerint kezelik.

Ha a **Számlajavítások feladása a Kinnlevőségekbe** lehetőségeknél a **Nem** értéket választják, az újbóli felosztási folyamat a következő eredménnyel zárul:

- A rendszer csak a főkönyvbe adja fel a sztornírozott könyvelési tételt. A rendszer az eredeti számla minden könyvelési tételét sztornírozza, kivéve a Készlet és az ELÁBÉ számlák tételeit.
- A rendszer csak a főkönyvbe adja fel az új könyvelési tételt, amely az új, újbóli elosztás szerinti bevételi árakon alapul. A rendszer nem adja fel újra a számlát a Készlet és az ELÁBÉ számlákba, mivel ezeket a tételeket az eredeti számla könyvelési tételei szerint kezelik.
- A **Vevői tranzakciók** oldalon szereplő számla nem módosul, továbbra is az eredeti könyvelési tételek láthatók rajta. Nem tartalmaz a sztornírozott vagy az új könyvelési tételekre mutató hivatkozást.

Ahogy említettük, beállíthatja, hogy a rendszer csak a főkönyvet, vagy a főkönyvet és a kinnlevőségeket is frissítse. Mindkét megközelítésnek vannak előnyei és hátrányai. Javasoljuk, hogy fontolja meg a szervezet igényeit, és ezek alapján határozza meg, hogy melyik lehetőséget választja. Ha mind a főkönyvet, mind a kinnlevőségeket frissíti, az új számlán a megfelelő könyvelési tételek fognak szerepelni, és a **Vevői tranzakciók** oldalon elérhető dokumentumban is megtekinthetik. Emellett a kiegyenlítési folyamat a frissített könyvelési tételeket fogja használni a készpénzfizetési engedmények és nyereségek/veszteségek feladásához. Azonban a hiteldokumentum és az új számla ilyenkor a vevői kivonatokon és a korosítási jelentésekben is megjelenik, a többi hiteldokumentumhoz és vevői számlához hasonlóan. E dokumentumok leírása jelezni fogja, hogy könyvelési korrekcióval hozták létre őket.

## <a name="run-the-reallocation-process"></a>Az újbóli felosztási folyamat futtatása

Az újbóli felosztási folyamat elindításához válassza **Az ár újrafelosztása új rendelési sorokba** lehetőséget minden olyan értékesítési rendelésnél, amelynél szeretne újbóli felosztást végezni. Másik lehetőség: lépjen a **Bevételelszámolás \> Időszakos feladatok \> Az ár újrafelosztása új rendelési sorokba** menüpontba, és adja meg a megfelelő szűrőket, például a vevői számlát.

[![Az ár újrafelosztása új rendelési sorokba oldal.](./media/02_RevRecScenarios.png)](./media/02_RevRecScenarios.png)

**Az ár újrafelosztása új rendelési sorokba** oldal felső rácsának neve **Értékesítés**. Itt láthatja a vevőhöz tartozó értékesítési rendeléseket. Válassza ki az újból felosztani kívánt értékesítési rendeléseket. Ha valamelyik értékesítési rendeléshez már tartozik újrafelosztási azonosító, ezt a rendelést egy másik felhasználó már megjelölte újbóli felosztásra. Ha egy vagy több értékesítési rendelésnél előzőleg ismételt elosztás történt, és egy másik újraelosztásban kell ezeknek szerepelniük, akkor először vissza kell vonni ezeknek az értékesítési rendeléseknek az ismételt elosztását. Csak ezután lehet őket bevonni egy új újrafelosztásban. A részletesebb információkért lásd az [Újrafelosztás visszavonása](#undo-a-reallocation) és [Többszöri újrafelosztás](#reallocate-multiple-times) szakaszokat később ebben a témában.

A lap alsó rácsának neve **Sorok**. Ha az **Értékesítés** rácsban kiválasztotta a kívánt értékesítési rendeléseket, a **Sorok** rácsban megjelennek a kapcsolódó értékesítésirendelés-sorok. Válassza ki az újból felosztani kívántértékesítésirendelés-sorokat. Ha csak egy értékesítési rendelést választott ki, az ahhoz tartozó sorokat újból fel kell osztani. Ez akkor fordulhat elő, ha az értékesítési rendelés egyik sorát korábban már kiszámlázták, majd új sort adtak hozzá a rendeléshez, vagy egy meglévő sort eltávolítottak vagy érvénytelenítettek. Az eltávolított sorok nem jelennek meg a rácsban. Ezért ezek nem választhatók ki. A rendszer azonban ezeket is figyelembe veszi az újbóli felosztási folyamat futtatásakor.

Ha végzett a szükséges értékesítésirendelés-sorok kijelölésével, az alábbiak szerint használhatja a Műveletpanelen található gombokat:

- **Újbóli felosztás frissítése** – Az új bevételi árak kiszámítása a kiválasztott értékesítésirendelés-sorok esetében. Ha egy sort eltávolítottak vagy töröltek, a rendszer csak a kiválasztott sorokon hajtja végre az újbóli felosztást. Az alábbi illusztráción az értékesítésirendelés-sorok állapota látható az újbóli felosztás frissítése előtt.

    [![Értékesítésirendelés-sorok az újbóli felosztás frissítése előtt.](./media/03_RevRecScenarios.png)](./media/03_RevRecScenarios.png)

    Az új bevételi árak az **Újból felosztott összeg** oszlopban láthatók a **Sorok** rácsban. Ekkor a rendszer már feldolgozta az újbóli felosztást, de még nem számította ki. Az alábbi illusztráción az újbóli felosztás frissítése utáni értékesítésirendelés-sorok láthatók.

    [![Értékesítésirendelés-sorok az újbóli felosztás frissítése után.](./media/04_RevRecScenarios.png)](./media/04_RevRecScenarios.png)

- **Feldolgozás** – Az újbóli felosztás szerinti bevételi árak feldolgozása vagy feladása. A gomb kiválasztása után az újbóli felosztást már nem lehet sztornírozni. Ha nem választotta ki az **Újbóli felosztás frissítése** lehetőséget, és így aktiválja a **Feldolgozás** funkciót, a rendszer automatikusan lefuttatja az újbóli felosztást.

    - Ha még egy értékesítésirendelés-sort sem számláztak ki, a rendszer minden olyan értékesítési rendelésnél frissíti a bevételi árakat, amelyet kijelöltek újbóli felosztásra.
    - Ha egy vagy több értékesítésirendelés-sort már kiszámláztak, a rendszer feladja a helyesbítő könyvelési tételeket, és kijavítja a már kiszámlázott értékesítésirendelés-sorokhoz létrehozott bevételütemezési adatokat.

- **Várható bizonylat** – A kiszámlázott értékesítésirendelés-sorokhoz létrehozott könyvelési tételek előnézetének megjelenítése. Itt csak akkor szerepel valami, ha már van kiszámlázott sor. Ha nem választotta ki az **Újbóli felosztás frissítése** lehetőséget a **Várható bizonylat** kiválasztása előtt, a rendszer automatikusan lefuttatja az újbóli felosztást.
- **Bevétel újbóli felosztása** – Megnyílik egy oldal, amelyen megtekintheti a kiválasztott sorokhoz tartozó bevételiár-felosztást. Az oldalon szereplő adatokat nem módosíthatja. Az újbóli felosztáshoz használt sorösszegek is láthatók az oldalon.

    [![Az újbóli felosztáshoz használt sorösszegek.](./media/05_RevRecScenarios.png)](./media/05_RevRecScenarios.png)

- **Adatok alaphelyzetbe állítása a kiválasztott vevőnél** – Ha az újbóli felosztási folyamatot elkezdték, de nem fejezték be, akkor ezzel a funkcióval törölheti az újbóli felosztási táblában szereplő adatokat a kiválasztott vevőnél. Például Ön több értékesítésirendelés-sort is kijelöl újbóli felosztásra, és megnyitva hagyja az oldalt, de nem választja ki a **Feldolgozás** lehetőséget, ezért a rendszer időtúllépés miatt kilép. Ebben az esetben az értékesítésirendelés-sorok megjelölve maradnak, de más felhasználó nem éri el őket, és nem tudja elvégezni az újbóli felosztást. Az is elképzelhető, hogy az oldal megnyitáskor üresen jelenik meg. Ebben a helyzetben az **Adatok alaphelyzetbe állítása a kiválasztott vevőnél** gombbal törölheti a fel nem dolgozott értékesítési rendeléseket, hogy egy másik felhasználó befejezhesse az újbóli felosztási folyamatot.

## <a name="undo-a-reallocation"></a>Újrafelosztás visszavonása

Egy újrafelosztás visszavonása egy másik újrafelosztás futtatásával vonható vissza. Ismét megtörténik az újrafelosztás, és a felhasználó más értékesítésirendelés-sorokat választ ki, hogy ezek szerepeljenek a második újrafelosztási folyamatban.

Ha egy újrafelosztás két vagy több külön értékesítési rendelésen történt meg, akkor az **Ár újrafelosztása új rendelési sorokkal** lehetőség kiválasztásával vonható vissza bármely értékesítési rendelésből, ami az újrafelosztásban szerepel. A **Bevétel-felismerés \> Időszakos feladatok \> Ár újrafelosztása új rendelési sorokkal** műveletekkel nem lehet visszavonni az újrafelosztást, mert az így megnyitott lap ezzel a módszerrel csak azokat az értékesítési rendeléseket jeleníti meg, amelyekhez nincs újrafelosztási azonosító. Az újrafelosztási azonosítót a dokumentum újrafelosztása után rendeli hozzá a rendszer.

Az **Ár újrafelosztása új rendelési sorokkal** lapon vegye ki a jelölést minden olyan értékesítési rendelésnél, amelyet ki kell zárni a szerződéses megállapodásból. Az újrafelosztás feldolgozásához használja a Műveleti ablak megfelelő gombjait, mint például az **Újrafelosztás frissítése** és **Feldolgozás**. Ha az aktív értékesítési rendelésen kívül minden értékesítési rendelésnél ki van véve a jelölés, akkor a rendszer a módosítás feldolgozásakor eltávolítja az újrafelosztási azonosítót.

Ha egy teljesen vagy részben számlázott értékesítési rendeléshez egy új sor hozzáadásával történt az újrafelosztás, akkor ez csak úgy vonható vissza, ha eltávolítja azt a sort az értékesítési rendelésből, majd ismét lefuttatja az újrafelosztást. Az értékesítésirendelés-sort el kell távolítani, mert egy értékesítési rendelés minden sora egyazon szerződés részének tekintendő. Az értékesítésirendelés-sorok jelölését nem lehet visszavonni, amíg az **Ár újrafelosztása új rendelési sorokkal** lapon van.

## <a name="reallocate-multiple-times"></a>Többszöri újrafelosztás

Ugyanannak az értékesítési rendelésnek a többszöri újrafelosztása akkor lehetséges, ha a szerződésen több módosítás történt. Minden újrafelosztás kiváltja egy újrafelosztási azonosító hozzárendelését az értékesítési rendeléshez vagy értékesítési rendelések csoportjához, hogy a módosításokat csoportosítsa. Ha többszöri újrafelosztás történik, minden további újrafelosztás ugyanazt az újrafelosztási azonosítót használja, mint az első újrafelosztás.

Például a 00045-ös értékesítési rendelés bevitel történik, ami több sorból áll. Az értékesítési rendelés teljes számlázása után egy új értékesítésirendelés-sor kerül a rendelésbe. Az újrafelosztást ezután az **Ár újrafelosztása új rendelési sorokkal** oldal megnyitásával futtatható, ami történhet a 00045-ös értékesítési rendelésből, vagy a **Bevétel-felismerés \> Időszakos feladatok \> Ár újrafelosztása új rendelési sorokkal** menüpontra lépve. A **Reall000001** újrafelosztási azonosítót a rendszer hozzárendeli az értékesítési rendeléshez.

Ugyanehhez a szerződéshez létrejön egy második értékesítési rendelés is, a 00052. Az újrafelosztás ismét lefuttatható az **Ár újrafelosztása új rendelési sorokkal** megnyitásával a 00045-ös értékesítési rendelésből, de 00052-es értékesítési rendelésből nem. Ha a 00052 értékesítési rendelésből nyitja meg az **Ár újrafelosztása új rendelési sorokkal** oldalt, a 00045-ös értékesítési rendelés nem jelenik meg, mivel hozzá van rendelve egy újrafelosztási azonosító. Az oldalon csak azok az értékesítési rendelések jelennek meg, amelyekhez nincs újrafelosztási azonosító.

A második újrafelosztást kétféleképpen lehet végrehajtani. Visszavonhatja a 00045 értékesítési rendelés újrafelosztását. Ebben az esetben a rendszer eltávolítja az újrafelosztási azonosítót, majd a 00045-ös vagy a 00052-es értékesítési rendelésből meg tudja csinálni az újrafelosztást. Másik lehetőségként megnyithatja a 00045-ös értékesítési rendelésből az **Ár újrafelosztása új rendelési sorokkal** oldalt, és hozzáadhatja a második értékesítési rendelést is. Az újrafelosztás feldolgozásakor a rendszer a **Reall000001** újrafelosztási azonosítót rendeli hozzá a 00045-ös értékesítési rendeléshez és a 00052-es értékesítési rendeléshez is.

## <a name="scenarios-for-reallocation"></a>Újbóli felosztáshoz kapcsolódó esetek

A következő témakörök a bevételelszámolás során felmerülő különböző helyzeteket mutatják be:

- [Bevételelszámolás újbóli felosztása – 1. eset](rev-rec-reallocation-scenario-1.md) – Két értékesítési rendelést visznek be, de ezek csak a megerősítésig jutnak el. Ugyanez a forgatókönyv hasonló eredményekkel jár, ha kettőnél több értékesítési rendelés van visszaigazolt állapotban.
- [Bevételelszámolás újbóli felosztása – 2. eset](rev-rec-reallocation-scenario-2.md) – Két értékesítési rendelést visznek be, majd a vevő az első értékesítési rendelés kiszámlázása után hozzáad egy további cikket a szerződéshez.
- [Bevételelszámolás újbóli felosztása – 3. eset](rev-rec-reallocation-scenario-3.md) –Új sort adnak egy meglévő, már kiszámlázott értékesítési rendeléshez.
- [Bevételelszámolás újbóli felosztása – 4. eset](rev-rec-reallocation-scenario-4.md) – Egy sort eltávolítanak egy meglévő, részben kiszámlázott értékesítési rendelésből.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
