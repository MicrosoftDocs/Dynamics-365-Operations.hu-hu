---
title: A beépített alaptervezés és a tervezési optimalizálás közötti különbségek
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
ms.openlocfilehash: a23256f3e092b32e1f1d09b708a8d0ca5f403785
ms.sourcegitcommit: 5d33a3398e7e1d3494bfc3cad342fffa7cfa5b76
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2022
ms.locfileid: "9680008"
---
# <a name="differences-between-built-in-master-planning-and-planning-optimization"></a>A beépített alaptervezés és a tervezési optimalizálás közötti különbségek

[!include [banner](../../includes/banner.md)]

A Tervezésoptimalizálás eredményei eltérhetnek a beépített főtervező motor eredményeitől. A különbségeket a függőben lévő jellemzők okozhatják. Ez a cikk azokat **[a funkciókat sorolja fel, amelyek még nem támogatják a tervezési optimalizálást, és amelyek nem szerepelnek a Tervezési optimalizálás elemzésének lapján](planning-optimization-fit-analysis.md)**.

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
| Minimális/maximális fedezeti kód érték nélkül| A beépített tervezőmotor minimális/maximális fedezeti kód használata esetén, amelyben nincsenek beállítva minimális vagy maximális értékek, a tervezőmotor szükségletként kezeli a fedezeti kódot, és minden követelményhez létrehoz egy rendelést. A tervezési optimalizálás segítségével a rendszer naponta egy rendelést hoz létre, hogy az az adott napon teljes összeget fedezse.  |
| Nettó követelmények és manuálisan létrehozott tervezett rendelések | A beépített tervezőmotorral a cikkekhez manuálisan létrehozott ellátási rendelések automatikusan megjelennek az adott cikk nettó követelményei között. Amikor például beszerzési rendelést hoz létre egy értékesítési rendelésből, **a beszerzési rendelés előzetes műveletek nélkül megjelenik a Nettó követelmények** lapon. Ennek oka az, hogy a beépített tervezőmotor naplózza a `inventLogTTS`**tábla** készlettranzakcióit, és a dinamikus tervek nettókövetelmény-lapján megjeleníti a változásokat. A Tervezés optimalizálása beállításnál azonban a manuálisan létrehozott rendelések csak akkor jelennek meg a cikkek nettó követelményei között, ha a tervezési optimalizálás nem fut (a cikket tartalmazó tervvel), **\>** **vagy** amíg a Nettó követelmények lapon a Frissítési alaptervezés lehetőséget választja, amely a cikk alaptervezését fogja futtatni. A **Nettókövetelmények**[lapról](net-requirements.md) a Nettó követelmények lapon található további tájékoztatás, valamint a tervezési optimalizálási információk. |
| Erőforrás-hozzárendelés | Korlátlan kapacitással való munka során a beépített alaptervezési motor minden tervezett rendelést ugyanannak az erőforrásnak ad hozzá ugyanannál az erőforráscsoportnál. A tervezési optimalizálás ezt úgy javítja, hogy véletlenszerűen választ ki erőforrásokat, így a különböző termelési rendelések különböző erőforrásokat használhatnak. Ha ugyanazt az erőforrást szeretné használni az összes tervezett rendeléshez, akkor meg kell adnia az útvonalon azt az erőforrást. |
| Kiterjesztett adattípusok (kiterjesztett adattípusok) | A tervezési optimalizálás nem támogatja a hatályos eduk (EDT) pontosságának változását. Ha például két tizedesjegyre növeli a termékmennyiség pontosságát (alapértelmezett) négy tizedesjegyre, akkor a tervezési optimalizálás csak két tizedesjegyet fog használni. |

## <a name="additional-resources"></a>További erőforrások

- [A Tervezési optimalizálás igazítási elemzése](planning-optimization-fit-analysis.md)
- [A Tervezési optimalizálás által nem használt paraméterek](not-used-parameters.md)
- [A Tervezési optimalizálás által nem használt dátum- és időparaméterek](date-time-used.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
