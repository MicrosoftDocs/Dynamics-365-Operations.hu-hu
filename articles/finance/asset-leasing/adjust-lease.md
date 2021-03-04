---
title: Lízingek kiigazítása
description: A témakör azt mutatja be, hogyan lehet beállítani egy lízinget. Előfordulhat, hogy kiigazításra van szükség a lízingfeltételek módosításakor, a lízing meghosszabbításakor vagy más körülmény változásakor.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9d1c6e20e72fb2816c32e71e8921a94724ae5656
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/28/2020
ms.locfileid: "4444190"
---
# <a name="adjust-leases"></a>Lízingek kiigazítása

[!include [banner](../includes/banner.md)]

A témakör azt mutatja be, hogyan lehet beállítani egy lízinget. Előfordulhat, hogy kiigazításra van szükség a lízingfeltételek módosításakor, a lízing meghosszabbításakor vagy más körülmény változásakor. Az eszközök lízingelése megfelel a 842 (ASC 842) és a nemzetközi pénzügyi beszámolási szabvány 16. (IFRS 16) szerinti számviteli szabványoknak, amelyek a lízing módosítását írják elő. Az ASC 842-20-15-1 meghatározza a lízing módosítását olyan szerződések feltételeinek bármilyen változása esetén, amelyek a lízing hatókörét vagy ellenértékét eredményezik. Az IFRS 16 39. pontja szerint a lízingbevevőnek át kell értékelnie a lízingkötelezettséget, hogy az tükrözze a lízingdíjfizetések változását.

Az ASC 842 vagy IFRS 16 szabványoknak megfelelő szervezetek esetében a lízinget újra kell mérni, hogy a jövőbeli minimális lízingdíjfizetések jelenértéke (PVFMLP) változását tükrözzék. Ha a PVFMLP növekszik, akkor a létrehozott naplóbejegyzés tartozik a használatijog-eszközhöz (ROU), valamint az új PVFMLP és az előző PVFMLP közötti különbséghez a lízingkötelezettség jóváírása. Ha a PVFMLP csökken, akkor a naplóbejegyzés tartozik a lízingkötelezettséghez, és különbözet a ROU-eszközhöz tartozó jóváíráshoz.

Ha a korrekció a ROU-eszköznek a 0 (nulla) alá csökkenti az értékét, akkor a program jóváírja a maradékot a **Lízing feladási számlák** lapon megadott nyereségre a lízing módosítási számláján. Ezeknek a tranzakcióknak és egyéb helyesbítési bejegyzéseknek a rendszerszámlái, mint például az osztályozási változtatások, a kezdeti közvetlen költségek, a lízingösztönzők, az előlegek és a lízingmódosításokból eredő kiadások.

A lízingkorrekciós tranzakciókkal kapcsolatos konkrét útmutatást lásd az IFRS 16 és ASC 842 szabványban.

Egy lízing kiigazításához kövesse az alábbi lépéseket. A módosított adatok a létrehozási ütemezési folyamat futtatása után frissítik a lízingütemezéseket.

1. Lépjen az **Eszközlízing \> Lízingek \> Lízingösszesítő** felületre.
2. A **Lízingösszesítő** lapon válassza ki a helyesbíteni kívánt lízinget, majd válassza a **Lízing kiigazítása** lehetőséget.
3. A **Lízing kiigazítása** lapon adja meg a kiigazított lízing új adatait.

    Figyelje meg, hogy a **Lízing kiigazítása** lap hasonlít a **Lízing hozzáadása** lapra. Ezenkívül a lízing felvételekor megadott kezdő dátum határozza meg, hogy mikor induljon el az új lízing, a **Lízing kiigazítása** lap **Módosítás dátuma** mezője határozza meg, hogy mikor kezdődik a módosított lízing. Ez a dátum nem lehet későbbi a fizetési ütemezés soraiban megadott kezdő dátumnál.

    > [!NOTE]
    > A **ROU-szempontok** mezők a lízing kiigazítására vonatkozik. Ha nincs kezdeti közvetlen költség, bérleti ösztönzők, előlegek vagy lebontási költségek vannak társítva a módosított lízinghez, akkor ezeket a mezőket üresen kell hagyni. Az eredeti összegek nem vonatkoznak a frissített lízingre. A lízing módosításakor felmerülő további költségeket a **Lízing kiigazítása** lapon kell megadni.
    > 
    > Egy bérbeadó például egy 1.000 dollár ösztönzést nyújt a lízingkiegészítéshez való hozzájáruláshoz. Ebben az esetben a lízingkiterjesztéskor történő elszámoláskor az **1.000** értéket kell megadni a **Lízingösztönzők** mezőben. Ha nincsenek ösztönzők a lízingkorrekcióhoz, törölje a mezőbe korábban beírt értéket. Ugyanez a logika vonatkozik a többi ROU-megfontolásra is.

    A helyesbített lízing fizetési ütemezési sorait a potenciális vevők alapján kell létrehozni. A jövőbeli alapon létrehozott fizetési ütemezési sorok nem indíthatók el, mielőtt a lízingmódosítások érvénybe lépnek.

    A következő lépések csaknem megegyeznek a lízing első felismeréséhez szükséges lépésekkel.

4. A helyesbített kifizetési ütemezés létrehozásához válassza az **Ütemezések létrehozása** elemet. Egy üzenet jelenik meg, amely jelzi, hogy a lízinghez létrejön a kifizetési ütemezés.

    > [!IMPORTANT]
    > Az **Ütemezések létrehozása** előtt győződjön meg arról, hogy a módosítás dátuma és a kifizetési ütemezés sorai pontosak. Győződjön meg arról is, hogy minden kezdeti közvetlen költség, lízingösztönzők, előlegek vagy bontási költségek csak a kiigazításból eredő költségeknek felelnek meg.

5. Az újonnan létrehozott kifizetési ütemezés megtekintéséhez válassza ki a **Könyvek** lehetőséget, majd nyissa meg a **Fizetési ütemezés** lapot.
6. A **Fizetési ütemezés** lapon a kifizetési ütemezés jóváhagyása előtt szerkesztheti a helyesbített kifizetési összegeket. Az ütemezés jóváhagyásához jelölje be az **Ütemezés jóváhagyása** jelölőnégyzetet.

    A fizetési ütemezés megerősítésekor létrejön az új eszköz értékcsökkenése, és az új lízingkötelezettség ütemezései.

7. Ha meg szeretné tekinteni az új bemenetekből létrejövő új lízingkötelezettség amortizációs ütemezését, zárja be a **Fizetési ütemezés** lapot, majd nyissa meg a **Kötelezettség amortizációs ütemezése** lapot.
8. Az újonnan létrejövő eszközértékcsökkenési ütemezés megtekintéséhez nyissa meg az **Eszköz értékcsökkenési ütemezése** lapot a **Könyv részletei** oldalon.
9. A módosítási napló bejegyzésének létrehozásához válassza a **Funkció \> Lízingkorrekció** lehetőséget. Egy üzenet jelenik meg, amely jelzi, hogy a kiigazítási naplóbejegyzés létrejött. 
10. A naplóbejegyzés megtekintéséhez válassza ki a **Naplók \> Eszköz lízingcsoport** lehetőséget.
11. A naplóbejegyzés feladásához válassza ki a sort, majd válassza a **Feladás** parancsot.

## <a name="view-lease-versions"></a>Lízingverziók megtekintése

Ha a lízing módosult, megtekintheti a különböző verzióit. Megtekintheti a múltbeli ütemezéseket és a múltbeli lízing adatait is.

1. Válassza ki a másolni kívánt lízinget a **Lízingösszesítő** oldalon, majd a művelet ablaktáblán válassza a **Lízingverzió előzménye** parancsot.

    Ha a kijelölt lízing be van állítva, akkor a **Lízing verzióelőzmény** lap a különböző verziókat jeleníti meg. Az eredeti lízing **1**, és az azt követő verzió pedig növekvő numerikus sorrendben van.

    A kiválasztott lízingverzió esetében megtekinthetők a pénzügyi dimenziók, a szerződés részletei, a hely és a fizetési ütemezés sorai.

2. Ha meg szeretné tekinteni a múltbeli ütemezéseket, nyissa meg a **Lízingösszesítő** oldalon a módosított lízinget, válassza ki a kívánt könyvet, majd a művelet ablaktáblán válassza ki a **Könyv verziójának előzményeit**.
3. A **Könyvverzió** oldalon válassza ki a kívánt verziót, és a megtekinteni kívánt ütemezést.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]