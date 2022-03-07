---
title: Raktári munka ellenőrzése munkasablonok és helyutasítások használatával
description: A témakör ismerteti a munkasablonok és helyutasítások segítségével meghatározhatja, hogy hol és hogyan lehet munkavégzés a raktárban.
author: perlynne
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocDirFailure, WHSLocDirHint, WHSLocDirTable, WHSLocDirTableUOM, WHSRFMenuItem, WHSWork, WHSWorkClass, WHSWorkPool, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72921
ms.assetid: 377ab8af-5b0c-4b5e-a387-06ac1e1820c0
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a7e955fba12e963a443c0304f0a8a0e395c46909dd34de12cd51fa9788491786
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6770144"
---
# <a name="control-warehouse-work-by-using-work-templates-and-location-directives"></a>Raktári munka ellenőrzése munkasablonok és helyutasítások használatával

[!include [banner](../includes/banner.md)]

A témakör ismerteti a munkasablonok és helyutasítások segítségével meghatározhatja, hogy hol és hogyan lehet munkavégzés a raktárban.

A Dynamics 365 Supply Chain Management programban beállított munkasablonok determinálják az utasításokat, amiket a raktári dolgozók a mobileszközeikre kapnak. Ezek határozzák meg a különböző raktári folyamatokat és feladatokat. A munkasablonok határozzák meg, hogy miként történik a munka minden egyes raktári folyamat esetében. A helyutasítás hozzárendelése a munkasablonhoz elősegíti, hogy a munka a raktárak meghatározott területein történjen.

## <a name="work-templates"></a>Munkasablonok

A **Munkasablonok** lapon megadhatja a műveleteket, amiket el kell végezni a raktárban. Általában a raktári műveletek két egymást követő műveletből állnak: egy raktári dolgozó felveszi az aktuális készletet az egyik helyen, majd lerakja a készletet egy másik helyen. 

A munkasablonok fejlécből és társított sorokból állnak. Minden munkasablon egy adott *Munkarendelés-típus* eleme. Számos munkarendelés-típushoz tartoznak forrásdokumentumok, mint például a beszerzési és értékesítési rendelések. Azonban más munkarendelési-típusok különböző raktári folyamatot képviselnek, például a ciklikus leltározás. A *Munkagyűjtő azonosító* segítségével a munkát csoportokba rendezheti. 

A munkafejléc-definíció beállításainak használatával lehet megállapítani, hogy mikor kell létrehozni az új munkákat. Például megadhatja a kitárolási sorok maximális számát, valamint a várható maximális kitárolási időt. Ezt követően ha az értékesítési rendeléshez szükséges munka meghaladja valamelyik értéket, a munka két részre lesz osztva.

A **Munkafejléc törése** gombbal meghatározhatja, hogy a rendszer mikor hozzon létre új munkafejléceket. Ha például munkafejlécet szeretne létrehozni minden egyes _rendelésszámhoz_, válassza a műveleti panelen a **Lekérdezés szerkesztése** lehetőséget, majd adja hozzá a **Rendelésszám** mezőt a lekérdezésszerkesző **Rendezés** lapjához. A **Rendezés** lapra hozzáadott mezők *csoportosítási mezőként* választhatók ki. A csoportosítási mezők beállításához válassza a műveleti panel **Munkafejléc törlései** elemet, majd minden egyes, csoportosítási mezőként használni kívánt mezőhöz jelölje be a **Csoportosítás adott mező szerint** oszlopban található jelölőnégyzetet.

A munkasorok a munka feldolgozásához szükséges fizikai tevékenységnek felelnek meg. Például egy kimenő raktári folyamathoz tartozhat egy sor, ami a cikkek raktáron belüli felvételéről szól, valamint egy másik sor, ami a cikkek átmeneti területre való szállításáról szól. Lehet egy további sor a cikkek előkészítő területről való felvételéről, valamint még egy sor, a rakodási folyamat részeként, a cikkek teherautóra helyezéséről. Beállíthat *Utasításkód* értéket a munkasablon sorban. Az utasításkód egy helyutasításhoz kapcsolódik, ezáltal segít biztosítani, hogy a raktári munka a megfelelő helyen legyen feldolgozva a raktárban.

Beállíthat egy lekérdezést, amivel szabályozza, hogy egy adott munkasablon mikor legyen használva. Például korlátozhatja, hogy egy adott sablon csak egy bizonyos raktárban legyen használható. Másik lehetőségként rendelkezhet több, a kimenő értékesítési rendelés feldolgozásához használatos sablonnal, az értékesítési forrástól függően. A rendszer a **Sorszám** mezőt használja, hogy meghatározza az elérhető munkasablonok sorrendjét. Ezért ha van egy adott lekérdezése egy adott munkasablonhoz, adjon neki alacsony sorozatszámot. Az a lekérdezés a többi, általánosabb lekérdezés előtt lesz kiértékelve.

> [!NOTE]
> Ha meg szeretné akadályozni, hogy a rendszer automatikusan felülírja a munkasablon *sorozatszámait* a sablon törlése után, kapcsolja be a *Munkasablon-sorozatszámok megőrzése törléskor* funkciót a [Szolgáltatáskezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) részben.

Egy munkafolyamat leállításához, vagy felfüggesztéséhez használhatja a **Munka leállítása** beállítást a munkasorból. Ebben az esetben a munkát végző dolgozónak nem kell végrehajtania a következő munkát a sorban. A következő lépéshez, az egyik dolgozónak ki kell választania a munkát újra. Elkülönítheti a feladatokat munkán belül, különböző *Munkaosztály-azonosító* használatával a munkasablon soraiban.

## <a name="location-directives"></a>Helyutasítások

A helyutasítások olyan szabályok, amik segítik a kitárolási és betárolási helyek meghatározását, készletmozgatás esetében. Például egy értékesítési rendelés tranzakciójába a helyutasítás azt határozza meg, ahol a cikkek kitárolása történik, valamint ahol a cikkeket betárolják. A helyutasítások fejlécből és társított sorokból állnak, valamint a **Helyutasítások** oldalon hozhatja létre őket.

A fejlécben minden egyes helyutasításhoz társul egy *Munkarendelés típus*, amely megadja, hogy melyik készlet-tranzakció típushoz lesz használva az utasítás, mint például értékesítési rendelések, feltöltések vagy nyersanyag kitárolások. A *Munkatípus* meghatározza, hogy a helyutasítás kitároláshoz vagy betároláshoz lesz használva, vagy egyéb raktári folyamathoz, például leltárhoz vagy a készlet állapotának változtatásához. Ki kell töltenie a *Hely* és a *Raktár* mezőket. Az *Utasításkód*, amit a fejlécen ad meg, a helyutasítás egy vagy több munkasablonhoz rendelésére is használható. 

A munkasablonoknál beállíthat egy lekérdezést, ami meghatározza, hogy mikor legyen használva egy bizonyos helyutasítás. Például megadhatja, hogy ha elektronikus kereskedelem az értékesítési rendelés eredete, a készlet a raktár egy bizonyos területéről legyen felvéve. A rendszer a **Sorszám** mezőt használja, hogy meghatározza az elérhető helyutasítások sorrendjét.

A helyutasítási sorok további korlátozásokat szabnak meg a helykeresés szabályaival kapcsolatban. Megadhat egy minimális és egy maximális mennyiséget, amire az utasítás vonatkozik, valamint megadhatja, hogy az utasítás csak egy adott készletegységre vonatkozzon. Például ha a mértékegység a raklap a raklapon található cikkeket adott helyre lehet vinni. Megadhatja azt is, hogy a mennyiség el lehet-e osztva több hely között. A helyutasítási műveletek fejléchez hasonlóan minden helyutasítás sorművelete rendelkezik egy sorszámmal, amely meghatározza a sorok értékelési sorrendjét.

A helyutasítások rendelkeznek egy további részletességi szinttel, ez a: *helyutasítási műveletek*. Több helyutasítási műveletet is megadhat minden sornak. Még egyszer, a sorozatszám meghatározza a műveletek értékelésének sorrendjét. Ezen a szinten megadhat egy lekérdezést, hogy megadja, hogyan legyen megtalálva a legjobb hely a raktárban. Emellett használható előre definiált **Stratégia** beállítás, az optimális hely megtalálásához.

A helyutasítások létrehozásával és konfigurálásával kapcsolatos további tudnivalókért lásd: [Helyutasítás létrehozása](create-location-directive.md).

### <a name="how-location-directives-work"></a>Helyutasítások használata

A helyutasítások határozzák meg, hogy a cikkek kitárolása *hol* történjen, és *hova* tegyék őket. A rendszer kiértékeli a helyutasítást az egyes munkasorok alapján, majd kiválasztja a helyet a munkasor részletei alapján. A rendszer először megkeresi az összes olyan helyutasítást, amely megfelel egy adott munkasornak (például a megfelelő raktárhoz tartoznak, és megfelelnek a lekérdezésnek). Ezután egymás után értékeli az általa talált utasításokat.

> [!NOTE]
> Vannak olyan különleges esetek, amikor a kitárolási hely vagy a betárolási hely előre be van jelölve. A _vásárlás regisztrálása_ során például az első kitárolás mindig a regisztráció helyéről történik. Egy másik példa a *készletmozgatás sablon szerint*, ahol a raktári dolgozó kiválasztja a kitárolási helyet, és csak a betárolási helyeket keresi meg a rendszer a helyutasítások alapján.

## <a name="additional-resources"></a>További erőforrások

- Videó: [Raktárkezelési konfiguráció teljes részletességgel](https://community.dynamics.com/365/b/techtalks/posts/warehouse-management-configuration-deep-dive-october-14-2020)
- Súgótémakör: [Munka helyutasításokkal](create-location-directive.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]