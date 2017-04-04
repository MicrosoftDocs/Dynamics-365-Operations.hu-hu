---
title: "Ellenőrzési raktári munka munka sablonokat és hely irányelvek"
description: "A cikk ismerteti a munkasablonok és helyutasítások segítségével meghatározhatja, hogy hol és hogyan lehet munkavégzés a raktárban."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: WHSLocDirFailure, WHSLocDirHint, WHSLocDirTable, WHSLocDirTableUOM, WHSRFMenuItem, WHSWork, WHSWorkClass, WHSWorkPool, WHSWorkTemplateTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72921
ms.assetid: 377ab8af-5b0c-4b5e-a387-06ac1e1820c0
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 64bcea1f305d67c01967184596a58a48a002cf48
ms.lasthandoff: 03/31/2017


---

# <a name="control-warehouse-work-by-using-work-templates-and-location-directives"></a>Ellenőrzési raktári munka munka sablonokat és hely irányelvek

A cikk ismerteti a munkasablonok és helyutasítások segítségével meghatározhatja, hogy hol és hogyan lehet munkavégzés a raktárban.

A Microsoft Dynamics 365 for Operations programban beállított munkasablonok determinálják az utasításokat, amiket a raktári dolgozók a mobileszközeikre kapnak. Ezek határozzák meg a különböző raktári folyamatokat és feladatokat. A munkasablonok határozzák meg, hogy miként történik a munka minden egyes raktári folyamat esetében. A helyutasítás hozzárendelése a munkasablonhoz elősegíti, hogy a munka a raktárak meghatározott területein történjen.

## <a name="work-templates"></a>Munkasablonok
A **Munkasablonok** lapon megadhatja a műveleteket, amiket el kell végezni a raktárban. Általában a raktári műveletek két egymást követő műveletből állnak: egy raktári dolgozó felveszi az aktuális készletet az egyik helyen, majd lerakja a készletet egy másik helyen. 

A munkasablonok fejlécből és társított sorokból állnak. Minden munkasablon egy adott *Munkarendelés-típus*eleme. Számos munkarendelés-típushoz tartoznak forrásdokumentumok, mint például a beszerzési és értékesítési rendelések. Azonban más munkarendelési-típusok különböző raktári folyamatot képviselnek, például a ciklikus leltározás. A *Munkagyűjtő azonosító *segítségével a munkát csoportokba rendezheti. 

A munkafejléc-definíció beállításainak használatával lehet megállapítani, hogy mikor kell létrehozni az új munkákat. Például megadhatja a kitárolási sorok maximális számát, valamint a várható maximális kitárolási időt. Ezt követően ha az értékesítési rendeléshez szükséges munka meghaladja valamelyik értéket, a munka két részre lesz osztva. 

A munkasorok a munka feldolgozásához szükséges fizikai tevékenységnek felelnek meg. Például egy kimenő raktári folyamathoz tartozhat egy munkasor, ami a cikkek raktáron belüli felvételéről szól, valamint egy másik sor, ami a cikkek átmeneti területre való szállításáról szól. Lehet egy további sor a cikkek előkészítő területről való felvételéről, valamint még egy sor, a rakodási folyamat részeként, a cikkek teherautóra helyezéséről. Beállíthat *Utasításkód *értéket a munkasablon sorban. Az utasításkód egy helyutasításhoz kapcsolódik, ezáltal segít biztosítani, hogy a raktári munka a megfelelő helyen legyen feldolgozva a raktárban. 

Beállíthat egy lekérdezést, amivel szabályozza, hogy egy adott munkasablon mikor legyen használva. Például korlátozhatja, hogy egy adott sablon csak egy bizonyos raktárban legyen használható. Másik lehetőségként rendelkezhet több, a kimenő értékesítési rendelés feldolgozásához használatos sablonnal, az értékesítési forrástól függően. A rendszer a **sorszáma** mező, amely az elérhető sablonok bírálják sorrendjének meghatározásához. Ezért ha egy adott munka sablon nagyon specifikus lekérdezés, kell választani, hogy egy alacsony szám. Az a lekérdezés a többi, általánosabb lekérdezés előtt lesz kiértékelve. 

Egy munkafolyamat leállításához, vagy felfüggesztéséhez használhatja a **Munka leállítása** beállítást a munkasorból. Ebben az esetben a munkát végző dolgozónak nem kell végrehajtania a következő munkát a sorban. A következő lépéshez, az egyik dolgozónak ki kell választania a munkát újra. Elkülönítheti a feladatokat munkán belül, különböző *Munkaosztály-azonosító *használatával a munkasablon soraiban.

## <a name="location-directives"></a>Helyutasítások
A helyutasítások olyan szabályok, amik segítik a kitárolási és betárolási helyek meghatározását, készletmozgatás esetében. Például egy értékesítési rendelés tranzakciójába a helyutasítás azt határozza meg, ahol a cikkek kitárolása történik, valamint ahol a cikkeket betárolják. A helyutasítások fejlécből és társított sorokból állnak, valamint a **Helyutasítások** oldalon hozhatja létre őket. 

A fejlécben minden egyes helyutasításhoz társul egy *Munkarendelés típus *, amely megadja, hogy melyik készlet-tranzakció típushoz lesz használva az utasítás, mint például értékesítési rendelések, feltöltések vagy nyersanyag kitárolások. A *Munkatípus *meghatározza, hogy a helyutasítás kitároláshoz vagy betároláshoz lesz használva, vagy egyéb raktári folyamathoz, például leltárhoz vagy a készlet állapotának változtatásához. Ki kell töltenie a *Hely *és a *Raktár*mezőket. Az *Utasításkód *, amit a fejlécen ad meg, a helyutasítás egy vagy több munkasablonhoz rendelésére is használható. 

A munkasablonoknál beállíthat egy lekérdezést, ami meghatározza, hogy mikor legyen használva egy bizonyos helyutasítás. Például megadhatja, hogy ha elektronikus kereskedelem az értékesítési rendelés eredete, a készlet a raktár egy bizonyos területéről legyen felvéve. A rendszer a **Sorszám** mezőt használja, hogy meghatározza az elérhető helyutasítások sorrendjét. 

A helyutasítási sorok további korlátozásokat szabnak meg a helykeresés szabályaival kapcsolatban. Megadhat egy minimális és egy maximális mennyiséget, amire az utasítás vonatkozik, valamint megadhatja, hogy az utasítás csak egy adott készletegységre vonatkozzon. Például ha a mértékegység a raklap a raklapon található cikkeket adott helyre lehet vinni. Megadhatja azt is, hogy a mennyiség el lehet-e osztva több hely között. A helyutasítási műveletek fejléchez hasonlóan minden helyutasítás sorművelete rendelkezik egy sorszámmal, amely meghatározza a sorok értékelési sorrendjét. 

A helyutasítások rendelkeznek egy további részletességi szinttel, ez a: *helyutasítási műveletek*. Több helyutasítási műveletet is megadhat minden sornak. Még egyszer a sorszámot bírálják a műveletek sorrendjének meghatározásához használatos. Ezen a szinten állíthat be a lekérdezés definiálásához, hogyan lehet megtalálni a legjobb hely a raktárban. Emellett használható előre definiált **Stratégia **beállítás, az optimális hely megtalálásához.

### <a name="example-of-the-use-of-location-directives"></a>Példa a helyutasítás használatához

Ehhez a példához egy olyan beszerzési rendelési folyamatot veszünk alapul, ahol a helyutasításnak szabad területet kell találnia egy raktáron belül, azoknak a készletcikkeknek, amiket most regisztráltak a bevételezési területen. Először szabad kapacitást kell találnunk a raktár területén, az aktuális készlet konszolidálásával. Ha a konszolidáció nem lehetséges, üres helyet kell találnunk. 

Ebben az esetben két helyutasítási műveletek kell megadni. A sorozat első művelete a **Konszolidálás** stratégiája, a másodiknak az **Üres hely bejövő munka nélkül** stratégiáját használjuk. Hacsak nem adunk meg műveletet a túlcsordulás kezelésére, két végkifejlet lehetséges akkor, ha nincs több kapacitása a raktárnak: a munka létrehozható, habár nem lesz hely meghatározva, vagy a munka-létrehozási folyamat sikertelenül zárul. Az eredményt a **Helyutasítási hibák** lap beállításai határozzák meg, ahol eldöntheti, hogy beállítja-e a **Munka leállítása, ha a helyutasítások sikertelenek** lehetőséget minden Munkarendelés-típushoz.


