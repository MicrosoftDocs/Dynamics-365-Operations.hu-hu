---
title: A beépített alaptervezés és a tervezési optimalizálás közötti különbségek
description: Ez a téma azokat a funkciókat sorolja fel, amelyeket a Tervezésoptimalizálás még nem támogat, és amelyek nem szerepelnek a Tervezésoptimalizálás illeszkedéselemzés oldalán.
author: ChristianRytt
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: e271ddd3331d7b5de78f00a02b60a0479879c172
ms.sourcegitcommit: f8b597b09157d934b62bd5fb9a4d05b8f82b5a0e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/26/2021
ms.locfileid: "7700005"
---
# <a name="differences-between-built-in-master-planning-and-planning-optimization"></a>A beépített alaptervezés és a tervezési optimalizálás közötti különbségek

[!include [banner](../../includes/banner.md)]

A Tervezésoptimalizálás eredményei eltérhetnek a beépített főtervező motor eredményeitől. A különbségeket a függőben lévő jellemzők okozhatják. Ez a téma azokat a funkciókat sorolja fel, amelyeket a Tervezésoptimalizálás még nem támogat, és amelyek nem szerepelnek a **[Tervezés Optimalizálás illeszkedéselemzés](planning-optimization-fit-analysis.md)** oldalon].

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

## <a name="additional-resources"></a>További erőforrások

- [A Tervezési optimalizálás igazítási elemzése](planning-optimization-fit-analysis.md)
- [A Tervezési optimalizálás által nem használt paraméterek](not-used-parameters.md)
- [A Tervezési optimalizálás által nem használt dátum- és időparaméterek](date-time-used.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
