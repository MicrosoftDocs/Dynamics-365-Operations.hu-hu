---
title: A tervezési optimalizálás és az elavult alaptervezési motor közötti különbségek
description: Ez a cikk felsorolja azokat a funkciókat, amelyek a tervezési optimalizálás még nem támogatottak, és amelyek nem szerepelnek a Tervezési optimalizálás elemzésének lapján.
author: t-benebo
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 6e1671a508b85a94ac9687af15e898d885ea94c1
ms.sourcegitcommit: 55e440e30490b2d36d86b22aa1263d5da97633aa
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/04/2022
ms.locfileid: "9745361"
---
# <a name="differences-between-planning-optimization-and-the-deprecated-master-planning-engine"></a>A tervezési optimalizálás és az elavult alaptervezési motor közötti különbségek

[!include [banner](../../includes/banner.md)]

A tervezési optimalizálás eredményei eltérhetnek az elavult alaptervezési motor eredményeitől. A különbségeket a függőben lévő jellemzők okozhatják. Ez a cikk azokat **[a funkciókat sorolja fel, amelyek még nem támogatják a tervezési optimalizálást, és amelyek nem szerepelnek a Tervezési optimalizálás elemzésének lapján](planning-optimization-fit-analysis.md)**.

| Funkció | Jelenlegi viselkedés a tervezés optimalizálásában |
|---|---|
| Fogási súlyú termékek | A fogási súlyú termékek szokásos termékeknek minősülnek.|
| Bővíthető dimenziók | A tervezésoptimalizálás nem támogatja a extenzhető dimenziókat. A tervezési optimalizálás használata esetén a tervezett rendeléseken akkor is üresek a extenzható dimenziók, **·** **·** **ha** a Tárolási dimenziócsoportok vagy a Nyomon követési dimenziócsoportok lapon be van jelölve a Dimenzió szerinti fedezeti terv jelölőnégyzet. |
| Szűrt gyártási folyamatok | Részletekért lásd: [Termeléstervezés - Szűrők](production-planning.md#filters). |
| Előrejelzési terv | Az előrejelzés-tervezés nem támogatott. Javasoljuk a főterv használatát, ahol a főtervhez egy előrejelzési modell van hozzárendelve. |
| Számsorozatok a tervezett megrendelésekhez | A tervezett megrendelések számsorozatai nem támogatottak. A tervezett rendelési számok a szolgáltatási oldalon generálódnak. A tervezett rendelés száma általában 10 számjegyből áll, de a sorozat valójában 20 karakterből áll, és a tervezési futtatás számában szereplő 10 számjegyből, a tervezett rendelések számlálása pedig a további 10 számjegyből áll. |
| Tervmásolás, terv törlése és tervverzió tisztítás | <p>A navigációs ablaktáblában a következő elemek vannak letiltva a **Főtervezés \> Főtervezés \> Tervek karbantartása** alatt:</p><ul><li>Tervmásolat</li><li>Terv törlése</li><li>Tervezett verzió tisztítása</li></ul> |
| Visszárurendelések | A visszaküldött megrendeléseket nem vesszük figyelembe. |
| Ütemezéssel kapcsolatos funkciók | Részletekért lásd: [Ütemezés végtelen kapacitással](infinite-capacity-planning.md#limitations). |
| Biztonsági készlet teljesítése | A tervezési optimalizálás mindig a *Mai dátum + beszerzési* idő lehetőséget használja a **Cikkfedezet** lap **Minimális teljesítése** mezőjében. Ez segít elkerülni a nem kívánt tervezési rendeléseket, és más problémákat, ha a beszerzési idő nem szerepel a biztonsági készletben, akkor az aktuális alacsony raktárkészlethez létrehozott tervezett rendeléseket mindig az átfutási idő miatt késlelteti a program. |
| Biztonsági készlet-igénykövetés és nettó követelmények | A *Biztonsági készlet* követelménytípusa nem szerepel, és nem jelenik meg a **Nettó követelmények** lapon. A biztonsági készlet nem képvisel igényt, és nincs hozzá szükségletdátum társítva. Ehelyett megszorítást ad meg arra, hogy mennyi készletnek kell jelen lennie mindig. Az alaptervezés során azonban még mindig figyelembe veszi a rendszer a **Minimum** mező értékét a tervezett rendelések számítása során. Javasoljuk, hogy a **Nettó követelmények** lapon vizsgálja meg az **Összesített mennyiség** oszlopot, és ellenőrizze, hogy figyelembe lett-e véve ez az érték. Mivel az pegging eltérő, különböző műveleteket javasolhat a program. |
| Közlekedési naptárak | A szállítási **módok** lapon a **szállítási naptár** oszlopban szereplő értéket figyelmen kívül hagyjuk. |
| Minimális/maximális fedezeti kód érték nélkül| Az elavult alaptervezési motornál minimális/maximális fedezeti kód használata esetén, amelyben nincsenek beállítva minimális vagy maximális értékek, a tervezőmotor szükségletként kezeli a fedezeti kódot, és minden követelményhez létrehoz egy rendelést. A tervezési optimalizálás segítségével a rendszer naponta egy rendelést hoz létre, hogy az az adott napon teljes összeget fedezse.  |
| Nettó követelmények és manuálisan létrehozott tervezett rendelések | Az elavult alaptervezési motorral a cikkekhez manuálisan létrehozott ellátási rendelések automatikusan megjelennek az adott cikk nettó követelményei között. Amikor például beszerzési rendelést hoz létre egy értékesítési rendelésből, **a beszerzési rendelés előzetes műveletek nélkül megjelenik a Nettó követelmények** lapon. Ennek az az oka, hogy az elavult alaptervezési motor `inventLogTTS`**naplózza** a táblában található készlettranzakciókat, és a dinamikus tervek nettókövetelmény-lapján megjeleníti a változásokat. A Tervezés optimalizálása beállításnál azonban a manuálisan létrehozott rendelések csak akkor jelennek meg a cikkek nettó követelményei között, ha a tervezési optimalizálás nem fut (a cikket tartalmazó tervvel), **\>** **vagy** amíg a Nettó követelmények lapon a Frissítési alaptervezés lehetőséget választja, amely a cikk alaptervezését fogja futtatni. A Nettó **követelmények**[lapról a Nettó követelmények és az igényekre vonatkozó információk tartalmaznak további tudnivalókat.](net-requirements.md) |
| Erőforrás-hozzárendelés | Korlátlan kapacitással való munka során az elavult alaptervezési motor minden tervezett rendelést ugyananhoz az erőforráshoz rendel ugyanannál az erőforráscsoportnál. A tervezési optimalizálás ezt úgy javítja, hogy véletlenszerűen választ ki erőforrásokat, így a különböző termelési rendelések különböző erőforrásokat használhatnak. Ha ugyanazt az erőforrást szeretné használni az összes tervezett rendeléshez, akkor meg kell adnia az útvonalon azt az erőforrást. |
| Kiterjesztett adattípusok (kiterjesztett adattípusok) | A tervezési optimalizálás nem támogatja a hatályos eduk (EDT) pontosságának változását. Ez azt jelenti, hogy ez a folyamat nem hivatalosan támogatott, és nem garantáltan működik. |
| Biztonsági készlet teljesítése | A tervezési optimalizálás mindig a mai **dátum +** *beszerzési idő minimumát használja*. Ezzel a műveletsekkel a rendszer a jövőben egyszerűbbé válik a tervezési beállításokban, és ez műveletre használható eredményt ad. Ha a beszerzési idő nem része a biztonsági készletnek, az alacsony aktuális készlethez létrehozott tervezett rendelések az átfutási idő miatt mindig késni fognak. Ez a viselkedés jelentős zajt és nemkívánatos tervezett rendeléseket eredményezhet. A legjobb gyakorlat az, ha a *mai dátum + beszerzési idő beállításra módosítja a beállítást*. Az alapadatok frissítése a figyelmeztetések elkerüléséhez. |
| Statikus dinamikus tervbe másolása | A tervezési optimalizálás nem másol statikus terveket a dinamikus tervekbe, **függetlenül az Alaptervezés paraméterei oldalon megadott beállítástól**. Általános szabály, hogy a tervezési optimalizálás által generált sebesség és teljes újragenerálás miatt ez a művelet kevésbé fontos. Ha két vagy több terv van használatban, akkor minden tervhez alaptervezést kell indítani. |

## <a name="additional-resources"></a>További erőforrások

- [A Tervezési optimalizálás igazítási elemzése](planning-optimization-fit-analysis.md)
- [A Tervezési optimalizálás által nem használt paraméterek](not-used-parameters.md)
- [A Tervezési optimalizálás által nem használt dátum- és időparaméterek](date-time-used.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
