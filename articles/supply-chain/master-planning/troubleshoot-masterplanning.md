---
title: Alaptervezés – hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet javítani az alaptervezés használata során felmerülő problémákat.
author: SmithaNataraj
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 4dc3c5c8a1597fce4cc61461d16cd11ad80426eb8841871278772fcd7b8c86b1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6766631"
---
# <a name="troubleshoot-master-planning"></a>Alaptervezés – hibaelhárítás

Ez a témakör azt mutatja be, hogyan lehet javítani az alaptervezés használata során felmerülő problémákat.

## <a name="bill-of-materials-explosion-behaves-differently-for-firmed-production-orders-and-for-estimated-production-orders-for-manually-created-work"></a>Az anyagjegyzék alábontása eltérően viselkedik a megerősített termelési rendeléseknél és a manuálisan létrehozott munka becsült termelési rendeléseinél.

### <a name="issue-description"></a>Probléma leírása

Ha egy gyártási rendelés meg van erősítve, a cikkek nem lesznek alábontva, amikor alábontja az anyagjegyzéket (BOM). Azonban ha manuálisan hoz létre egy munkarendelést, majd megbecsüli a termelési rendelést, a cikkek alábontásra kerülnek.

### <a name="issue-resolution"></a>Probléma megoldása

A rendszer a várt módon működik. A termelési rendelés megerősítésekor bekövetkező alábontás a tervezett rendelésre mutat, de nem tűnik jelenik meg, hogy a tervezett rendelés ebben az esetben meg lennel erősítve. Ha azonban a termelési rendelés meg lett becsülve, az alábontás az engedélyezett termelési rendelésből aktiválódik, ahol nincs tervezett rendelés.

## <a name="the-delay-value-isnt-updated-when-i-reschedule-a-planned-order"></a>A Késleltetés érték nem frissül, amikor átütemezek egy tervezett rendelést.

A tervezett rendelések késésének frissítéséhez nyissa meg a tervezett rendelés **Átütemezés** párbeszédpaneljét. Győződjön meg arról , hogy az **Alábontás** gyorslapon az **Alábontás elvégzése átütemezés után** beállítás értéke *Igen* legyen.

## <a name="production-scheduling-doesnt-consider-the-safety-margins-that-are-set-on-the-item-coverage-for-pegged-supply"></a>A termelésütemezés nem veszi figyelembe a rögzített készlet cikkfedezetén beállított biztonsági időtartalékokat.

### <a name="issue-description"></a>Probléma leírása

Az alaptervezés figyelembe veszi a biztonsági időtartalékokat. A rendszer azonban figyelmen kívül hagyja a biztonsági időtartalékokat a tervezett termelési rendelések ütemezésekor.

### <a name="issue-resolution"></a>Probléma megoldása

Az időtartalékok csak az alaptervezés során lesznek figyelembe véve, a manuális ütemezés során nem. Az időtartalékok úgy vannak kialakítva, hogy a tervezési fázisban pufferként működjenek, hogy a tényleges folyamathoz bizonyos „időtartalékot” biztosítsanak.

A kívánt eredmény eléréséhez eltávolíthatja az időtartalékot. Az útvonalat ezután frissíteni kell, hogy tartalmazza a kívánt időt (például várakozási sorként). Az alaptervezésnek és a manuális ütemezésnek is ugyanazt az eredményt kell elérniük.

## <a name="planned-orders-are-generated-even-though-we-have-items-in-stock-and-production-orders-already-exist-for-them"></a>A tervezett rendelések akkor jönnek létre, ha a készleten lévő cikkek és termelési rendelések már léteznek.

Ezt a problémát úgy oldhatja meg, hogy növeli a **Fedezeti csoport** oldalon lévő **Pozitív napok** értékét. Ezen módosítás hatására a rendszer megállapítja, hogy az aktuális készlet használható-e a keresletre. Ezután nem jön létre új tervezett rendelés a készleten lévő cikkekhez.

## <a name="master-planning-doesnt-seem-to-respect-capacity-limitations-and-is-scheduling-more-than-the-available-capacity"></a>Úgy tűnik, hogy az alaptervezés nem veszi figyelembe a kapacitáskorlátozásokat, és a rendelkezésre álló kapacitásnál többet ütemez.

### <a name="issue-description"></a>Probléma leírása

Ha olyan műveletütemezést használ, ahol véges kapacitás van, és ahol az útvonal egy erőforráscsoport és az egyes erőforrások követelményeinek kombinációját meghatározza, akkor kis esély van a túlfoglalásra, mivel az algoritmus a kapacitásütközéseket figyelembe véve érvényesít. Ez a túlfoglalás akkor fordulhat elő, ha segédalkalmazásokkal futtatja az alaptervezést. Ez leginkább akkor fordul elő, ha sok olyan feladat van, amelyeknek viszonylag rövid a futásidejű.

### <a name="issue-resolution"></a>Probléma megoldása

Ha elengedhetetlen, hogy a műveletütemezéshez ne legyen túlfoglalás, az alaptervezés ütemezését egyszálassá teheti, ha bekapcsolja a **Műveletütemezéshez való pontos, véges kapacitás** beállítást az **Alaptervezési paraméterek** lapon. Ez a beállítás nem érhető el alapértelmezetten. A személyre szabási funkciók használatával manuálisan kell hozzáadnia az oldalhoz. Ha ezt a beállítást használja, az ütemezés lassabban fog futni a párhuzamos feldolgozás hiánya miatt.

## <a name="planned-orders-take-a-long-time-to-update"></a>A tervezett rendelések frissítése hosszú időt vesz igénybe.

### <a name="issue-description"></a>Probléma leírása

A szükséglet mennyiségének és/vagy szállítási dátumának tervezett rendelésen történő frissítésekor általában rendelésenként legalább 30 másodpercet vesz igénybe a frissítés mentése.

### <a name="issue-resolution"></a>Probléma megoldása

Ez egy ismert probléma a beépített fő tervezőmotorral. Ezt az okozza, hogy az anyagjegyzékstruktúrán keresztül a szerkesztések során automatikusan alá van bontva. Ezzel a problémával részletesebben a Tervezés optimalizálása című részben olvashat, ahol a tervező frissítheti és jóváhagyhatja a megfelelő rendeléseket, és szükség esetén tervezési futtatást indíthat el a mögöttes anyagjegyzékstruktúra tervezett rendeléseinek frissítéséhez.

A beépített fő tervezőmotorral a teljesítmény javításának egyik módja a következő:

1. Válassz az **Alaptervezés \> Beállítás \> Tervek \> Alaptervezések** lehetőséget.
1. Válasszon egy tervet.
1. Bontsa ki az **Időkorlátot napokban** gyorslapot.
1. Állítsa az **Alábontás** beállítást *Igen* értékre, és állítsa a beállítás alatti mezőt 0-ra (nulla).

> [!NOTE]
> Ez egyetlen napra korlátozza az alaptervben végrehajtott alábontások időszakát.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]