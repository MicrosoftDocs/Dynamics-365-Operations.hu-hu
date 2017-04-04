---
title: "Alapértelmezett dimenziók és termékváltozatok sorrend beállításai"
description: "Az alapértelmezett rendelési beállítások határozzák meg azt a helyet és raktárt, ahol a cikkek beszerzése és tárolása történik, illetve azt a minimális, maximális, többszörös és szokásos mennyiséget, amely felhasználásra kerül a kereskedéshez vagy a készletgazdálkodáshoz, valamint az átfutási időket, a leállító jelzőket és a rendelési ígéret módszerét. Az alapértelmezett rendelési beállítások lesznek érvényesek a beszerzési rendelések, értékesítési rendelések, átmozgatási rendelések és készletnaplók létrehozásakor, valamint az alaptervezés elkészítésekor a tervezett rendelések létrehozásához. Az alapértelmezett rendelésbeállítások lehetnek cikkspecifikusak, helyspecifikusak, termékváltozat-specifikusak vagy termékdimenzió-specifikusak."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventItemOrderSetup
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 223084
ms.assetid: fbfbcd7b-dc75-44ab-bffc-8bad576804a4
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 60abaa69debd891b2fe2dd98184c0dab50b0bf9f
ms.lasthandoff: 03/29/2017


---

# <a name="default-order-settings-for-dimensions-and-product-variants"></a>Alapértelmezett dimenziók és termékváltozatok sorrend beállításai

Az alapértelmezett rendelési beállítások határozzák meg azt a helyet és raktárt, ahol a cikkek beszerzése és tárolása történik, illetve azt a minimális, maximális, többszörös és szokásos mennyiséget, amely felhasználásra kerül a kereskedéshez vagy a készletgazdálkodáshoz, valamint az átfutási időket, a leállító jelzőket és a rendelési ígéret módszerét. Az alapértelmezett rendelési beállítások lesznek érvényesek a beszerzési rendelések, értékesítési rendelések, átmozgatási rendelések és készletnaplók létrehozásakor, valamint az alaptervezés elkészítésekor a tervezett rendelések létrehozásához. Az alapértelmezett rendelésbeállítások lehetnek cikkspecifikusak, helyspecifikusak, termékváltozat-specifikusak vagy termékdimenzió-specifikusak.

Az alapértelmezett rendelésbeállításokat az **Alapértelmezett rendelésbeállítások** oldalon lehet beállítani. A lap megnyitásához nyissa meg **Termékinformációk kezelése**&gt;**termékek**&gt;**, amely a termékek**&gt; megjelent termék kiválasztása &gt;a a **terv** vagy *** készlet *** műveletpanel kezelése &gt;**rendelés beállítások**&gt;**alapértelmezett beállítások**.

## <a name="default-order-settings"></a>Alapértelmezett rendelésbeállítások
Háromféle alapértelmezett rendelésbeállítás van a beszerzésekhez, az értékesítésekhez és a készlethez. A beszerzések alapértelmezett rendelési beállításai használatosak a következők létrehozásakor:

-   Beszerzési rendelés sorai
-   Beszerzési szerződés sorai
-   Ajánlatkérés sorai
-   Beszerzési igénylési sorok
-   Bizományosi feltöltési sorok
-   Terv. besz. rendelések

Az értékesítés alapértelmezett rendelési beállításai használatosak a következők létrehozásakor:

-   Értékesítési rendelés sorai
-   Értékesítésiszerződés-sorok
-   Értékesítési ajánlat sorai
-   Visszáru-rendelési sorok és cikkhelyettesítő sorok
-   Igény-előrejelzés sorai

Az alapértelmezett értékesítési rendelési beállítások alkalmazandók a következők létrehozásakor is:

-   Projekt cikkszükségletei
-   Szervizrendelési cikkre vonatkozó követelmények

A készlet alapértelmezett rendelési beállításai használatosak a következők létrehozásakor:

-   Készletnaplók
-   Átmozgatási rendelések
-   Tervezett átmozgatási rendelések

Az alapértelmezett készletrendelési beállítások alkalmazandók a következők létrehozásakor is:

-   Karanténutasítások
-   Minőségi rendelések
-   Termelési rendelések
-   Anyagjegyzéksorok
-   Terv. term. rendelések

## <a name="full-definition-of-a-released-product"></a>Egy kiadott termék teljes meghatározása
A tranzakció létrehozásakor meg kell adnia kiadott termék teljes meghatározását a sor előtt Dynamics 365 műveletek megkísérli azonosítani az alapértelmezett beállítások. Megjelent termék teljes meghatározása azt jelenti, a cikkszám és minden aktív termék dimenziót, például a konfiguráció, méret, stílus és szín, megadva a tranzakcióban. Például, ha egy kiadott termékváltozathoz tartozó rendelési sort manuális hoz létre, meg kell adnia minden szükséges termékdimenziót, mielőtt a telephely, raktár, mennyiségek és átfutási idő megjelenik a rendeléssorban szereplő alapértelmezés szerint. 

Az alapértelmezett rendelési beállítások paraméterei közül nem mindegyik kerül alkalmazásra, amikor rendelési vagy naplósorok jönnek létre. Szükség esetén alapértelmezés szerint csak megjelenik a mennyiségek és az átfutási idők. Például egy naplósorban leltári csak a hely és a raktár jelenik meg alapértelmezés szerint a sor létrehozásakor. Nyilvánvalóan nem alapértelmezett mennyiség vagy több ellenőrzésére és minimumokat végzik a sor létrehozásakor vagy a napló feladása. 

A rendszer mindig megpróbál egy alapértelmezett telephelyet és raktárt találni, amikor egy rendeléshez vagy naplóhoz sor jön létre. Alapértelmezés szerint a telephely nem mindig látható a rendelési beállításokból. Például egy értékesítési rendelés vagy beszerzési rendelés létrehozásakor a rendelés fejlécében szereplő telephely automatikusan bekerül a rendelési sorokba. Egy AJ-sor létrehozása esetén a webhely a DBJ-fejléc szolgál. A webhely határozza meg, miután használandó bármely webhelyen található Speciális beállítások, majd használhatja az alapértelmezett raktár. 

Az alapértelmezett rendelési típus, a beszerzés és a készlet átfutási idejét is bírálható felül a cikk fedezeti szabályok szerint a a **Cikkfedezet** oldalon. Bár az alapértelmezett beállítások nem teszik lehetővé számára a termelés és az átviteli átfutási idő közötti különbség a cikkfedezet-szabályok lehetővé. A cikkfedezeti beállításokat azonban csak akkor használja az anyagszükséglet-tervezés, amikor tervezett termelési és tervezett átviteli rendeléseket hoznak létre, és nem kerülnek alkalmazásra, amikor manuálisan hoznak létre termelési és átviteli rendeléseket. 

## <a name="default-order-settings-rules"></a>Alapértelmezett rendelésbeállítások szabályai
Megadhatja az általános alapértelmezett rendelési beállításokat, és megadhat tetszőleges számú, olyan alapértelmezett rendelésbeállítási szabályt, amelyek csak bizonyos esetekben érvényesek, például a telephely vagy egy adott cikkdimenzió vagy termékdimenzió kombinációja esetében. Raktár-specifikus rendelésbeállításokat nem lehet meghatározni.

### <a name="rank-in-default-order-settings"></a>Rangsorolás az alapértelmezett rendelési beállításokban

Az alapértelmezett rendelésbeállítási szabályok rangsorolást is tartalmaznak. Minél magasabb a rangsorban elfoglalt helye, annál fontosabb a szabály, azaz nagyobb prioritása lesz, és az alacsonyabban rangsorolt szabályok előtt kerül használatra. Az általános alapértelmezett rendelésbeállítások 0. helyezéssel is rendelkeznek, és ezt nem lehet módosítani. Csak egy 0-ás helyezésű szabály lehet. A szabályok rangsorolása lehet az azonos, amennyiben a dimenziók másra vonatkoznak. Ez a helyspecifikus rendelésbeállítások modellezésénél hasznos. Új alapértelmezett rendelésbeállítási szabály létrehozása után a rendelési értékek, a leállító jelzők stb. értékei a 0-ás helyezésű szabályból öröklődnek, de ezeket felül lehet bírálni.

### <a name="default-order-settings-for-released-products"></a>Alapértelmezett rendelésbeállítások kiadott termékekhez

Egyedi kiadott termékek esetében általános rendelési beállításokat vagy helyspecifikus rendelésbeállításokat határozhat meg. Az általános rendelésbeállításokhoz mindig 0-ás helyezés tartozik. Ha új értékesítési, beszerzési és készletre vonatkozó rendelésbeállítások állít be együtt, egyszerre, ajánlott, hogy a **Részletes nézetet** használja az **Alapértelmezett rendelésbeállítások **oldalon. Váltás a részletes nézetre, Ugrás a **beállítások** műveletpanel &gt;**beállítások lap**&gt;**nézet váltása**&gt;**Részletek nézet**.

### <a name="site-specific-order-settings"></a>Helyspecifikus rendelésbeállítások

Helyspecifikus rendelésbeállítások létrehozásához kattintson az **Új** lehetőségre. A **Részletek nézet**, töltse ki a webhelyet a **vonatkozó beállítások**&gt;**hely** mező. A **Rács nézetben**, töltse ki a helyet a **Hely** oszlopban. Az új szabály automatikusan kap egy új helyezést, amely magasabb, mint nulla. Tetszőleges számú helyspecifikus szabályt hozhat létre, és az összes helyspecifikus szabályhoz hozzárendelheti ugyanazt a helyezést, amivel azt jelzi, hogy azok ugyanolyan fontosak. 

Ha a **Részletes nézetben** van, akkor nem lehet áttekinteni a cikkhez létrehozott szabályokat. Váltson a **Lista megjelenítése/elrejtése** gombbal az áttekintő adatok megjelenítéséhez. Bármilyen típusú egy rendelési sor létrejön, ha a megadott webhely nem rendelkezik, Dynamics 365 műveletek keres egy szabály nincs megadva hely. Ez segíthet a sorban lévő alapértelmezett hely határozza meg. Ezt a helyet használja ezután a rendszer, hogy egy olyan helyspecifikus szabályt találjon, ahol az alapértelmezett raktárt esetleg beállították. Ez a raktár vonatkozik a rendelési sorra.

### <a name="specific-order-settings-for-product-dimension"></a>Specifikus rendelésbeállítások termékdimenzióhoz

Bármely aktív termékdimenzióhoz vagy aktív cikkdimenziók kombinációjához lehet rendelésbeállítási szabályokat meghatározni. Ha a termékdimenzió egyik mezője üresen marad, akkor az adott szabály a termékdimenzió összes értékére vonatkozik. 

Tételezzük fel a következő termékpéldát:

|                                                     |                                         |
|-----------------------------------------------------|-----------------------------------------|
| **Product name**                                    | Fotoelektromos érzékelő                    |
| **Item number**                                     | XW56                                    |
| **Konfiguráció** (a fény típusának modellezéséhez használatos) | C1 látható piros fény, C2 infravörös fény |
| **Stílus** (mérnöki felülvizsgálat modellezéséhez használatos)  | R1, R2, R3                              |

Ebben a példában azt feltételezzük, hogy a terméket beszerzik és nem gyártják. Azt is feltételezzük, hogy a C1 konfigurációt gyakrabban használják, ezért rövidebb az átfutási ideje. 

Hozza létre a következő alapértelmezett rendelésbeállítást a jelen eset modellezéséhez.

| Helyezés | Telephely | Konfiguráció | Stílus | Beszerzés - Alapértelmezett beállítások felülbírálása | Beszerzés átfutási ideje | Beszerzés - Leállítva | Értékesítés - Alapértelmezett beállítások felülbírálása | Értékesítés - leállítva |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 10   |      | C1            |       | Igen                                  | 2                  |                    |                                   |                 |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

Amikor a beszerzési rendeléssor vagy a tervezett beszerzési rendelés létrejön az XW56, C1 konfigurációjához, a verziótól vagy a telephelytől függetlenül, a sor el van helyezve, és az átfutási idő feltételezett értéke 2. Tegyük fel, hogy az R3 verzión kívül mindegyik verzió leállt.

A következő alapértelmezett rendelésbeállítási szabályokat lehet létrehozni.

| Helyezés | Telephely | Konfiguráció | Stílus | Beszerzés - Alapértelmezett beállítások felülbírálása | Beszerzés átfutási ideje | Beszerzés - Leállítva | Értékesítés - Alapértelmezett beállítások felülbírálása | Értékesítés - leállítva |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 20   |      |               | R2    | Igen                                  |                    | Igen                | Igen                               | Igen             |
| 20   |      |               | R1    | Igen                                  |                    | Igen                | Igen                               | Igen             |
| 10   |      | C1            |       | Igen                                  | 2                  |                    |                                   |                 |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

A régi verziók leállításának két szabálya azonos helyezéssel rendelkezik, ami azt jelenti, azok ugyanolyan fontosak. Mindkettő helyezése magasabb, mint a C1 konfigurációra vonatkozó szabályé, ez azt jelenti, hogy elsőbbséget élveznek a C1 konfigurációs szabállyal szemben. 

Ez a példa ismerteti a rangsorolását szükségességét. Ha egy beszerzési rendelést hoznak létre a C1 konfigurációhoz és az R2 verzióhoz, a rangsorolását hiányában az R2-re és a C1-re meghatározott két szabály nem lenne egyértelmű. A félreérthetőség megoldására a Dynamics 365 for Operations keresést végez a szabályok között, csökkenő sorrendben, és az első vonatkozó szabályt alkalmazza. A jelen példában, amikor beszerzési rendeléssort hoznak létre a C1 konfigurációhoz és az R2 verzióhoz, a felhasználó figyelmeztetést kap, hogy a cikk várakoztatva van, és ennek oka a verzió értéke. Ha a konfigurációra vonatkozó szabály helyezése magasabb lenne, mint a verzióra vonatkozó szabályé, akkor a C1 konfiguráció és az R2 verzió beszerzési rendeléssor létrehozása sikerült volna, és a felhasználó nem kapott volna "cikk várakoztatva" üzenetet. 

Vegye figyelembe a következő, alapértelmezett rendelésbeállítási szabályokat.

| Helyezés | Telephely | Konfiguráció | Stílus | Alapértelmezett hely | Alapértelmezett raktár | Beszerzés - Alapértelmezett tárolási dimenzió felülbírálása | Beszerzési raktár |
|------|------|---------------|-------|--------------|-------------------|------------------------------------------------|--------------------|
| 20   | 2    |               |       |              |                   | Igen                                            | 22                 |
| 10   |      | C1            |  R2   |  2           |  21               |                                                |                    |
| 0    |      |               |       | 1            | 11                |                                                |                    |

A rendszer kétszer bejárja a szabálykészletet annak érdekében, hogy meghatározza a helyet és a raktárt. Konfiguráció C1, R2, stílus a beszerzési rendelési sor létrehozásakor a webhely határozza meg a szabály rang 10. A rendszer megkeresi egy szabály 2 helyen a raktár meghatározásához. Megtalálja a 20. szabályt, és mivel ennek magasabb a rangsorolása, a beszerzési rendeléssoron szereplő raktár 22 lesz, és nem 21. 

Általános útmutatásként: a specifikus szabályok és az olyan dimenziókra vonatkozó szabályok, amelyek fontosabbak más dimenzióknál, magasabb helyezést kapnak, míg az általánosabb szabályok rangsorolása alacsonyabb. 

A 0-ás helyezésű szabály biztonsági hálóként szolgál. Ha nem található más szabály, a 0-ás szabály alapértelmezett rendelési beállításai kerülnek felhasználásra. 

Mivel a helyezési szám ennyire fontos, az **Alapértelmezett rendelésbeállítások **műveletpanelén található egy olyan funkció, amellyel felfelé vagy lefelé lehet mozgatni és át lehet számozni a szabályokat úgy, hogy a köztük lévő lépésköz mindig 10. 

Egy kiadott termékhez létrehozott szabályok száma nagy lehet. Ahhoz, hogy jobban meg lehessen érteni, hogy egy-egy szabály miket ír felül, és miért van rá szükség, a **Rács nézet** használatát javasoljuk az ** Alapértelmezett rendelésbeállítások** oldalon. Engedélyezheti a rács nézetben nyissa meg a **beállítások** műveletpanel &gt;**beállítások lap**&gt;**nézet váltása**&gt;**táblázatos nézet**. A rácson megjelenő oszlopok száma nagy lehet, különösen az értékesítésre és a készletre vonatkozó lapok esetében. A rács látható oszlopok számának korlátozásához csoportok oszlopok rejtett vagy jelenik meg a gomb segítségével a **alapértelmezett beállítások**&gt;**Oszlop megjelenítés** menü.

### <a name="specific-order-settings-for-released-product-variant"></a>Specifikus rendelésbeállítások kiadott termékváltozatokhoz

Ha az alapértelmezett rendelési beállításokra vonatkozó szabály túl nehézkes, lehetőség van arra is, hogy egyszerűen meghatározzák az alapértelmezett rendelési beállításokat minden termékváltozathoz. A következő példák megmutatják, hogy ez hogy néz ki a fentiekben ismertetett terméknél és eseteknél.

| Helyezés | Telephely | Konfiguráció | Stílus | Beszerzés - Alapértelmezett beállítások felülbírálása | Beszerzés átfutási ideje | Beszerzés - Leállítva | Értékesítés - Alapértelmezett beállítások felülbírálása | Értékesítés - leállítva |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 10   |      | C2            | R3    | Igen                                  | 5                  |                    |                                   |                 |
| 10   |      | C2            | R2    | Igen                                  | 5                  | Igen                | Igen                               | Igen             |
| 10   |      | C2            | R1    | Igen                                  | 5                  | Igen                | Igen                               | Igen             |
| 10   |      | C1            | R3    | Igen                                  | 2                  |                    |                                   |                 |
| 10   |      | C1            | R2    | Igen                                  | 2                  | Igen                | Igen                               | Igen             |
| 10   |      | C1            | R1    | Igen                                  | 2                  | Igen                | Igen                               | Igen             |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

A rangsorban elfoglalt hely ebben az esetben nem nagyon számít, így el is lehet rejteni. Ez a megoldás potenciálisan karbantartási eseményt vált ki. Ugyanakkor érdemes fontolóra venni ennek a beállításnak a használatát, ha Termékéletciklus-kezelés (PLM) rendszerekkel való integrációt tervez.


