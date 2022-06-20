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
ms.openlocfilehash: cf39166dce860dbd796cb4749175628252ed96ea
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897574"
---
# <a name="differences-between-built-in-master-planning-and-planning-optimization"></a>A beépített alaptervezés és a tervezési optimalizálás közötti különbségek

[!include [banner](../../includes/banner.md)]

A Tervezésoptimalizálás eredményei eltérhetnek a beépített főtervező motor eredményeitől. A különbségeket a függőben lévő jellemzők okozhatják. Ez a cikk azokat **[a funkciókat sorolja fel, amelyek még nem támogatják a tervezési optimalizálást, és amelyek nem szerepelnek a Tervezési optimalizálás elemzésének lapján](planning-optimization-fit-analysis.md)**.

| Funkció | Jelenlegi viselkedés a tervezés optimalizálásában |
|---|---|
| Fogási súlyú termékek | A fogási súlyú termékek szokásos termékeknek minősülnek.|
| Bővíthető dimenziók | A bővíthető dimenziók üresek a tervezett megrendeléseken, még akkor is, ha a **Tárolási dimenziócsoportok** vagy a **Nyomon követési dimenziócsoportok** lapon be van jelölve a **Fedezeti terv dimenzió szerint** jelölőnégyzet. |
| Szűrt gyártási folyamatok | Részletekért lásd: [Termeléstervezés - Szűrők](production-planning.md#filters). |
| Előrejelzési terv | Az előrejelzés-tervezés nem támogatott. Javasoljuk a főterv használatát, ahol a főtervhez egy előrejelzési modell van hozzárendelve. |
| Számsorozatok a tervezett megrendelésekhez | A tervezett megrendelések számsorozatai nem támogatottak. A tervezett rendelési számok a szolgáltatási oldalon generálódnak. A tervezett rendelés száma általában 10 számjegyből áll, de a sorozat valójában 20 karakterből áll, és a tervezési futtatás számában szereplő 10 számjegyből, a tervezett rendelések számlálása pedig a további 10 számjegyből áll. |
| Tervmásolás, terv törlése és tervverzió tisztítás | <p>A navigációs ablaktáblában a következő elemek vannak letiltva a **Főtervezés \> Főtervezés \> Tervek karbantartása** alatt:</p><ul><li>Tervmásolat</li><li>Terv törlése</li><li>Tervezett verzió tisztítása</li></ul> |
| Visszárurendelések | A visszaküldött megrendeléseket nem vesszük figyelembe. |
| Ütemezéssel kapcsolatos funkciók | Részletekért lásd: [Ütemezés végtelen kapacitással](infinite-capacity-planning.md#limitations). |
| Biztonsági készlet teljesítése | A tervezési optimalizálás mindig a *Mai dátum + beszerzési* idő lehetőséget használja a **Cikkfedezet** lap **Minimális teljesítése** mezőjében. Ez segít elkerülni a nem kívánt tervezési rendeléseket, és más problémákat, ha a beszerzési idő nem szerepel a biztonsági készletben, akkor az aktuális alacsony raktárkészlethez létrehozott tervezett rendeléseket mindig az átfutási idő miatt késlelteti a program. |
| Biztonsági készlet-igénykövetés és nettó követelmények | A *Biztonsági készlet* követelménytípusa nem szerepel, és nem jelenik meg a **Nettó követelmények** lapon. A biztonsági készlet nem képvisel igényt, és nincs hozzá szükségletdátum társítva. Ehelyett megszorítást ad meg arra, hogy mennyi készletnek kell jelen lennie mindig. Az alaptervezés során azonban még mindig figyelembe veszi a rendszer a **Minimum** mező értékét a tervezett rendelések számítása során. Javasoljuk, hogy a **Nettó követelmények** lapon vizsgálja meg az **Összesített mennyiség** oszlopot, és ellenőrizze, hogy figyelembe lett-e véve ez az érték. |
| Közlekedési naptárak | A szállítási **módok** lapon a **szállítási naptár** oszlopban szereplő értéket figyelmen kívül hagyjuk. |
| Minimális/maximális fedezeti kód érték nélkül| A beépített tervezőmotor minimális/maximális fedezeti kód használata esetén, amelyben nincsenek beállítva minimális vagy maximális értékek, a tervezőmotor szükségletként kezeli a fedezeti kódot, és minden követelményhez létrehoz egy rendelést. A tervezési optimalizálás segítségével a rendszer naponta egy rendelést hoz létre, hogy az az adott napon teljes összeget fedezse.  |
| Nettó követelmények és manuálisan létrehozott tervezett rendelések | A beépített tervezőmotorral a cikkekhez manuálisan létrehozott ellátási rendelések automatikusan megjelennek az adott cikk nettó követelményei között. Amikor például beszerzési rendelést hoz létre egy értékesítési rendelésből, **a beszerzési rendelés előzetes műveletek nélkül megjelenik a Nettó követelmények** lapon. Ennek oka az, hogy a beépített tervezőmotor naplózza a `inventLogTTS`**tábla** készlettranzakcióit, és a dinamikus tervek nettókövetelmény-lapján megjeleníti a változásokat. A Tervezés optimalizálása beállításnál azonban a manuálisan létrehozott rendelések csak akkor jelennek meg a cikkek nettó követelményei között, ha a tervezési optimalizálás nem fut (a cikket tartalmazó tervvel), **\>** **vagy** amíg a Nettó követelmények lapon a Frissítési alaptervezés lehetőséget választja, amely a cikk alaptervezését fogja futtatni. A **Nettókövetelmények**[lapról](net-requirements.md) a Nettó követelmények lapon található további tájékoztatás, valamint a tervezési optimalizálási információk. |

## <a name="additional-resources"></a>További erőforrások

- [A Tervezési optimalizálás igazítási elemzése](planning-optimization-fit-analysis.md)
- [A Tervezési optimalizálás által nem használt paraméterek](not-used-parameters.md)
- [A Tervezési optimalizálás által nem használt dátum- és időparaméterek](date-time-used.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
