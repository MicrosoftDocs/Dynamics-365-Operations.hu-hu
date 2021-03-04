---
title: Alapértelmezett rendelési beállítások dimenziókhoz és termékváltozatokhoz
description: Az alapértelmezett rendelési beállítások határozzák meg azt a helyet és raktárt, ahol a cikkek beszerzése és tárolása történik, illetve azt a minimális, maximális, többszörös és szokásos mennyiséget, amely felhasználásra kerül a kereskedéshez vagy a készletgazdálkodáshoz, valamint az átfutási időket, a leállító jelzőket és a rendelési ígéret módszerét.
author: t-benebo
manager: tfehr
ms.date: 09/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventItemOrderSetup, InventItemIdLookupByDefaultOrderSetting, EcoResProductReleasedStoppedAllChartPart, UnitTestPartitions
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Retail
ms.custom: 223084
ms.assetid: fbfbcd7b-dc75-44ab-bffc-8bad576804a4
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: c3aa800c1a996a062bcb737afa23f00a9e52bb48
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429811"
---
# <a name="default-order-settings-for-dimensions-and-product-variants"></a>Dimenziókra és termékváltozatokra vonatkozó alapértelmezett rendelésbeállítások

[!include [banner](../includes/banner.md)]

A Dynamics 365 Supply Chain Management alapértelmezett rendelési beállításai határozzák meg azt a helyet és raktárt, ahol a cikkek beszerzése és tárolása történik, illetve azt a minimális, maximális, többszörös és szokásos mennyiséget, amely felhasználásra kerül a kereskedéshez vagy a készletgazdálkodáshoz, valamint az átfutási időket, a leállító jelzőket és a rendelési ígéret módszerét. Az alapértelmezett rendelési beállítások lesznek érvényesek a beszerzési rendelések, értékesítési rendelések, átmozgatási rendelések és készletnaplók létrehozásakor, valamint az alaptervezés elkészítésekor a tervezett rendelések létrehozásához. Az alapértelmezett rendelésbeállítások lehetnek cikkspecifikusak, helyspecifikusak, termékváltozat-specifikusak vagy termékdimenzió-specifikusak.

A termék alapértelmezett rendelési beállításainak megadásához kövesse az alábbi lépéseket.

1. Kattintson a **Termékinformációk kezelése** &gt; **Termékek** &gt; **Kiadott termékek** lehetőségre.
1. Válassza ki a releváns terméket a rácsban.
1. A műveleti panelen hajtsa végre a következő lépések valamelyikét, hogy megnyithassa a választott termék **Alapértelmezett rendelésbeállítások** adatlapját:

    - A **Tervezés** lapon a **Rendelés beállításai** csoportban válassza az **Alapértelmezett rendelési beállítások** lehetőséget.
    - A **Készlet kezelése** lapon a **Rendelés beállításai** csoportban válassza az **Alapértelmezett rendelési beállítások** lehetőséget.

1. Konfigurálja a beállításokat a témakörben leírt további módon.

## <a name="default-order-settings"></a>Alapértelmezett rendelésbeállítások

Háromféle alapértelmezett rendelésbeállítás van a beszerzésekhez, az értékesítésekhez és a készlethez. A beszerzések alapértelmezett rendelési beállításai használatosak a következők létrehozásakor:

- Beszerzési rendelés sorai
- Beszerzési szerződés sorai
- Ajánlatkérés sorai
- Beszerzési igénylési sorok
- Bizományosi feltöltési sorok (részben támogatott, lásd a megjegyzést)
- Terv. besz. rendelések

> [!NOTE]
> A bizományosi feltöltési rendeléssorokra az **Alapértelmezett rendelésbeállítások** lap **Beszerzési rendelés** gyorslapjából csak az **Alapértelmezett hely** mező, az **Alapértelmezett raktár** mező, és a **Leállítva** jelölőnégyzet vonatkozik.

Az értékesítés alapértelmezett rendelési beállításai használatosak a következők létrehozásakor:

- Értékesítési rendelés sorai
- Értékesítésiszerződés-sorok
- Értékesítési ajánlat sorai
- Visszáru-rendelési sorok és cikkhelyettesítő sorok
- Igény-előrejelzés sorai

Az alapértelmezett értékesítési rendelési beállítások alkalmazandók a következők létrehozásakor is:

- Projekt cikkszükségletei
- Szervizrendelési cikkre vonatkozó követelmények

A készlet alapértelmezett rendelési beállításai használatosak a következők létrehozásakor:

- Készletnaplók
- Átmozgatási rendelések
- Tervezett átmozgatási rendelések

Az alapértelmezett készletrendelési beállítások alkalmazandók a következők létrehozásakor is:

- Karanténutasítások
- Minőségi rendelések
- Termelési rendelések
- Anyagjegyzéksorok
- Terv. term. rendelések

## <a name="full-definition-of-a-released-product"></a>Egy kiadott termék teljes meghatározása

Amikor tranzakciót hoz létre, pontosan meg kell adja a kiadott termék meghatározását a sorban, így a Supply Chain Management megpróbálhatja azonosítani az alapértelmezett rendelési beállításokat. A kiadott termék teljes meghatározásában a cikk száma és minden aktív termékdimenzió, mint például a konfigurálás, a méret, a stílus, a verzió és a szín mind meghatározásra kerülnek a tranzakcióban. Például, ha manuálisan hoz létre egy beszerzési rendelési sort egy kiadott termékvariánsra, meg kell adjon minden szükséges termékdimenziót, mielőtt az oldal a raktár, a mennyiségek és az átfutás megjelenik alapértelmezés szerint a rendelési soron. 

Az alapértelmezett rendelési beállítások paraméterei közül nem mindegyik kerül alkalmazásra, amikor rendelési vagy naplósorok jönnek létre. Az alapértelmezés szerint a mennyiségek és az átfutási idők csak szükség esetén jelennek meg. Például a naplósor megszámolásakor csak a telephely és raktár jelenik meg alapértelmezés szerint a sor létrehozásakor. Éppen ezért nincs alapértelmezett mennyiség, illetve nincsenek ellenőrzések a többszörösökön vagy a minimum értékeken a sor létrehozásakor vagy a napló feladásakor. 

A rendszer mindig megpróbál egy alapértelmezett telephelyet és raktárt találni, amikor egy rendeléshez vagy naplóhoz sor jön létre. Alapértelmezés szerint a telephely nem mindig látható a rendelési beállításokból. Például egy értékesítési rendelés vagy beszerzési rendelés létrehozásakor a rendelés fejlécében szereplő telephely automatikusan bekerül a rendelési sorokba. Anyagjegyzéksor létrehozásakor az anyagjegyzék fejlécében szereplő telephely használatos. A telephely meghatározása után ez felhasználásra kerül a helyspecifikus rendelésbeállítások megkeresésekor, amelyek ezután a raktár alapértelmezés szerint beállításai lehetnek. 

Az alapértelmezett rendelési típust, a beszerzést és a készlet-átfutási időket felül lehet írni a cikk fedezeti szabályaival a **Cikkfedezet** lapon. Annak ellenére, hogy az alapértelmezett rendelési beállítások nem teszik lehetővé a termelés és az átviteli átfutási idő megkülönböztetését, a cikkfedezeti szabályok ezt engedélyezik. A cikkfedezeti beállításokat azonban csak akkor használja az Alaptervezést (MRP), amikor tervezett termelési és tervezett átviteli rendeléseket hoznak létre, és nem kerülnek alkalmazásra, amikor manuálisan hoznak létre termelési és átviteli rendeléseket. 

## <a name="default-order-settings-rules"></a>Alapértelmezett rendelésbeállítások szabályai

Megadhatja az általános alapértelmezett rendelési beállításokat, és megadhat tetszőleges számú, olyan alapértelmezett rendelésbeállítási szabályt, amelyek csak bizonyos esetekben érvényesek, például a telephely vagy egy adott cikkdimenzió vagy termékdimenzió kombinációja esetében. Raktár-specifikus rendelésbeállításokat nem lehet meghatározni.

### <a name="rank-in-default-order-settings"></a>Rangsorolás az alapértelmezett rendelési beállításokban

Az alapértelmezett rendelésbeállítási szabályok rangsorolást is tartalmaznak. Minél magasabb a rangsorban elfoglalt helye, annál fontosabb a szabály, azaz nagyobb prioritása lesz, és az alacsonyabban rangsorolt szabályok előtt kerül használatra. Az általános alapértelmezett rendelésbeállítások 0. helyezéssel is rendelkeznek, és ezt nem lehet módosítani. Csak egy 0-ás helyezésű szabály lehet. A szabályok rangsorolása lehet az azonos, amennyiben a dimenziók másra vonatkoznak. Ez a helyspecifikus rendelésbeállítások modellezésénél hasznos. Új alapértelmezett rendelésbeállítási szabály létrehozása után a rendelési értékek, a leállító jelzők stb. értékei a 0-ás helyezésű szabályból öröklődnek, de ezeket felül lehet bírálni.

### <a name="default-order-settings-for-released-products"></a>Alapértelmezett rendelésbeállítások kiadott termékekhez

Egyedi kiadott termékek esetében általános rendelési beállításokat vagy helyspecifikus rendelésbeállításokat határozhat meg. Az általános rendelésbeállításokhoz mindig 0-ás helyezés tartozik. Ha új értékesítési, beszerzési és készletre vonatkozó rendelésbeállítások állít be egyszerre, ajánlott, hogy a **Részletes nézetet** használja az **Alapértelmezett rendelésbeállítások** oldalon. Ahhoz, hogy a részletes nézetre váltson, kövesse ezt az elérési útvonalat: **Beállítások** &gt; **Lap beállításai** &gt; **Nézet megváltoztatása** &gt; **Részletes nézet**.

### <a name="site-specific-order-settings"></a>Helyspecifikus rendelésbeállítások

Helyspecifikus rendelésbeállítások létrehozásához válassza ki az **Új** lehetőséget. A **Részletek nézet** menüpontban, adja meg a helyet a **Hely** mezőben, a **Vonatkozó beállítások** részben. A **Rácsnézet**-ben , adja meg a helyet a **Hely** oszlopban. Az új szabály automatikusan kap egy új helyezést, amely magasabb, mint 0 (nulla). Annyi helyspecifikus szabályt hozhat létre, amennyire csak szüksége van. Hogy jelezze, hogy egyformán fontosak, hozzájuk rendelheti ugyanazon helyezési számot az összes helyspecifikus szabályhoz.

Ha a **Részletes nézetben** van, akkor nem lehet áttekinteni a cikkhez létrehozott szabályokat. Használja a **Lista megjelenítése/elrejtése** gombot az áttekintő adatok megjelenítéséhez. Amikor létrehoznak egy bármilyen típusú rendeléssort, és nincs megadva hely, a Supply Chain Management keres egy olyan szabályt, amelyhez nincs megadva telephely. Ez segít meghatározni a rendeléssorban szereplő alapértelmezett helyet. Ezt a helyet használja ezután a rendszer, hogy egy olyan helyspecifikus szabályt találjon, ahol az alapértelmezett raktárt esetleg beállították. Ez a raktár vonatkozik a rendelési sorra.

### <a name="specific-order-settings-for-product-dimension"></a>Specifikus rendelésbeállítások termékdimenzióhoz

Bármely aktív termékdimenzióhoz vagy aktív cikkdimenziók kombinációjához lehet rendelésbeállítási szabályokat meghatározni. Ha a termékdimenzió egyik mezője üres, akkor az adott szabály a termékdimenzió összes értékére vonatkozik. 

Tételezzük fel a következő termékpéldát:

|                                                     |                                         |
|-----------------------------------------------------|-----------------------------------------|
| **Termék neve**                                    | Fotoelektromos érzékelő                    |
| **Cikkszám**                                     | XW56                                    |
| **Konfiguráció** (a fény típusának modellezéséhez használatos) | C1 látható piros fény, C2 infravörös fény |
| **Verzió** | V1, V2, V3                              |

Ebben a példában azt feltételezzük, hogy a terméket beszerzik és nem gyártják. Azt is feltételezzük, hogy a C1 konfigurációt gyakrabban használják, ezért rövidebb az átfutási ideje. 

Hozza létre a következő alapértelmezett rendelésbeállítást a jelen eset modellezéséhez.

| Helyezés | Hely | Konfiguráció | Verzió | Beszerzés - Alapértelmezett beállítások felülbírálása | Beszerzés átfutási ideje | Beszerzés - Leállítva | Értékesítés - Alapértelmezett beállítások felülbírálása | Értékesítés - leállítva |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 10   |      | C1            |       | Igen                                  | 2                  |                    |                                   |                 |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

Amikor egy beszerzési rendelési sor vagy egy tervezett beszerzési rendelés kerül létrehozásra az XW56 cikkre, a C1-es konfigurációval, tekintet nélkül a verzióra, vagy a helyre, ahová a sor elhelyezésre kerül, az átfutási idő 2-ként lesz megadva. Tegyük fel, hogy az V3 verzión kívül mindegyik verzió leállt.

A következő alapértelmezett rendelésbeállítási szabályokat lehet létrehozni.

| Helyezés | Hely | Konfiguráció | Verzió | Beszerzés - Alapértelmezett beállítások felülbírálása | Beszerzés átfutási ideje | Beszerzés - Leállítva | Értékesítés - Alapértelmezett beállítások felülbírálása | Értékesítés - leállítva |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 20   |      |               | V2    | Igen                                  |                    | Igen                | Igen                               | Igen             |
| 20   |      |               | V1    | Igen                                  |                    | Igen                | Igen                               | Igen             |
| 10   |      | C1            |       | Igen                                  | 2                  |                    |                                   |                 |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

A két szabály a régi verziók leállítására ugyanolyan rangsorolással rendelkeznek. Ettől még egyformán fontosak. Mivel hogy mindkét szabálynak magasabb rangsorolása van a C1 konfigurációban, elsőbbséget élveznek a C1 konfiguráció szabályával szemben. 

Ez a példa ismerteti a rangsorolását szükségességét. Ha a besorolás nincs használva, amikor egy beszerzési rendelés kerül létrehozásra a C1 konfigurációban vagy a V2 verzióban, a két szabály, ami a V2-ben és C1-ben van megadva, ütközni fognak. A félreérthetőség megoldására a Supply Chain Management keresést végez a szabályok között, csökkenő sorrendben, és az első vonatkozó szabályt alkalmazza. A jelen példában, mikor egy beszerzési rendelési sor kerül hozzáadásra a C1 konfigurációban és a V2 verzióban, a felhasználó figyelmeztető üzenetet kap arról, hogy a cikk várakoztatott állapotú, és arról, hogy ezt a várakoztatást a verzió értéke okozta. Ha a konfiguráció szabálya magasabb rangsorolási értékkel bír, mint a verzióhoz tartozó szabály, a beszerzési rendelési sor sikeresen létrehozásra kerül a C1 konfigurációban és a V2 verzióban, és a felhasználó nem kap üzenetet "várakoztatott állapotú cikkről". 

Vegye figyelembe a következő, alapértelmezett rendelésbeállítási szabályokat.

| Helyezés | Hely | Konfiguráció | Verzió | Alapértelmezett hely | Alapértelmezett raktár | Beszerzés - Alapértelmezett tárolási dimenzió felülbírálása | Beszerzési raktár |
|------|------|---------------|-------|--------------|-------------------|------------------------------------------------|--------------------|
| 20   | 2    |               |       |              |                   | Igen                                            | 22                 |
| 10   |      | C1            |  V2   |  2           |  21               |                                                |                    |
| 0    |      |               |       | 1            | 11                |                                                |                    |

A rendszer kétszer bejárja a szabálykészletet, hogy meghatározza a helyet és a raktárt. Amikor egy beszerzési rendelési sort hoznak létre a C1 konfigurációban és az V2 verzióban, a hely meghatározása a 10. rangsorolású szabály alapján történik. A rendszer ezután szabályokat keres egy 2-es számú helyhez, amely meghatároz egy raktárt. A 20-as szabály megtalálásra került, és ezért nagyobb rangsorolási számot kap, a raktár a beszerzési rendelési soron 22-es lesz, nem 21-es.

Általános útmutatásként: a specifikus szabályok és az olyan dimenziókra vonatkozó szabályok, amelyek fontosabbak más dimenzióknál, magasabb helyezést kapnak, míg az általánosabb szabályok rangsorolása alacsonyabb. 

A 0-ás helyezésű szabály biztonsági hálóként szolgál. Ha nem található más szabály, a 0-ás szabály alapértelmezett rendelési beállításai kerülnek felhasználásra. 

Mivel a helyezési szám fontos, az **Alapértelmezett rendelésbeállítások** műveletpanelén található egy olyan funkció, amellyel felfelé vagy lefelé lehet mozgatni és át lehet számozni a szabályokat úgy, hogy a köztük lévő lépésköz mindig 10. 

Egy kiadott termékhez létrehozott szabályok száma nagy lehet. Ahhoz, hogy jobban megértse, hogy egy-egy szabály miket ír felül, és miért van rá szükség, a **Rács nézet** használatát javasoljuk az **Alapértelmezett rendelésbeállítások** oldalon. A Rács nézet engedélyezéséhez kövesse ezt az elérési útvonalat: **Lehetőségek** &gt; **Oldalbeállítások** &gt; **Nézet megváltoztatása** &gt; **Rácsnézet**. A rácson megjelenő oszlopok száma nagy lehet, különösen az értékesítésre és a készletre vonatkozó lapok esetében. A rácsban látható oszlopok számának korlátozásához az oszlopok csoportjait el lehet rejteni vagy láthatóvá lehet tenni az **Alapértelmezett rendelésbeállítások** &gt; **Oszlop megjelenítése** menüben lévő gombok segítségével.

### <a name="specific-order-settings-for-released-product-variant"></a>Specifikus rendelésbeállítások kiadott termékváltozatokhoz

Ha az alapértelmezett rendelési beállításokra vonatkozó szabály túl nehézkes, lehetőség van arra is, hogy meghatározzák az alapértelmezett rendelési beállításokat minden termékváltozathoz. A következő példa megmutatja, hogy ez hogy néz ki a fentiekben ismertetett terméknél és eseteknél.

| Helyezés | Hely | Konfiguráció | Verzió | Beszerzés - Alapértelmezett beállítások felülbírálása | Beszerzés átfutási ideje | Beszerzés - Leállítva | Értékesítés - Alapértelmezett beállítások felülbírálása | Értékesítés - leállítva |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 10   |      | C2            | V3    | Igen                                  | 5                  |                    |                                   |                 |
| 10   |      | C2            | V2    | Igen                                  | 5                  | Igen                | Igen                               | Igen             |
| 10   |      | C2            | V1    | Igen                                  | 5                  | Igen                | Igen                               | Igen             |
| 10   |      | C1            | V3    | Igen                                  | 2                  |                    |                                   |                 |
| 10   |      | C1            | V2    | Igen                                  | 2                  | Igen                | Igen                               | Igen             |
| 10   |      | C1            | V1    | Igen                                  | 2                  | Igen                | Igen                               | Igen             |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

A rangsorban elfoglalt hely ebben az esetben nem nagyon számít, így el is lehet rejteni. Ez a megoldás potenciálisan karbantartási eseményt vált ki. Ugyanakkor érdemes fontolóra venni ennek a beállításnak a használatát, ha Termékéletciklus-kezelés (PLM) rendszerekkel való integrációt tervez.

## <a name="use-strict-or-standard-validation-of-default-order-quantities"></a>Az alapértelmezett rendelési mennyiségek szigorú vagy normál jóváhagyásának használata

Megadhatja, hogy milyen szigorú legyen a rendszer a termékkel kapcsolatos **Alapértelmezett rendelési beállításokban** megadott mennyiségek jóváhagyásakor. Az új szigorú beállítás használata esetén a **Szokásos rendelési mennyiségnek** mindig a megadott beszerzési rendelések, készlet és értékesítési rendelések **Többszörösének** kell lennie. Ha szigorú ellenőrzést alkalmaz, nem fogja tudni menteni azokat az alapértelmezett rendelési beállításokat, amelyek nem felelnek meg ennek a követelménynek (és egy hibaüzenet jelenik meg az üzenetsávban). 

A szigorú ellenőrzés az **Alapértelmezett rendelési beállítások** lapjának **Beszerzési rendelés**, **Készlet** és **Értékesítési rendelés** gyorslapján megadott **Szokásos rendelési mennyiség** értékeire vonatkozik. Minden gyorslap saját **Több** beállítással rendelkezik, amely az adott gyorslaphoz megadott **Szokásos rendelési mennyiség** érték érvényesítésére szolgál.

### <a name="enable-the-strict-validation-option"></a>A szigorú ellenőrzési beállítás engedélyezése

A szigorú ellenőrzési lehetőség használata előtt engedélyeznie kell a saját rendszerében. A rendszergazdák használhatják a [Funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) oldalt a funkció állapotának ellenőrzéséhez, és szükség esetén engedélyezéséhez. Itt a funkció a következőként szerepel:

- **Modul** - *Termékinformáció-kezelés*
- **Funkciónév** - *Szigorú ellenőrzés az alapértelmezett rendelési mennyiségeknél*

### <a name="set-the-validation-option"></a>Az ellenőrzési lehetőség beállítása

Az ellenőrzési lehetőség beállításához:

1. Lépjen a **Termékinformáció kezelése \> Beállítás \> Termékinformáció kezelés paraméterei** elemre.
1. Az **Általános** lapon állítsa az **Alapértelmezett rendelési mennyiségek ellenőrzése** lehetőséget a következő értékek valamelyikére:
    - **Szigorú** – Akkor válassza ezt a lehetőséget, ha azt szeretné, hogy az összes **Szokásos rendelési mennyiség** értékei a **Több** többszörösei legyenek minden egyes Gyorslapon (**Beszerzési rendelés**, **Készlet** és **Értékesítési rendelés**).
    - **Szokásos** – Akkor válassza ezt a lehetőséget, ha a szokásos ellenőrzést szeretné használni (amely ugyanúgy működik, mint amikor ez a funkció nincs engedélyezve).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]