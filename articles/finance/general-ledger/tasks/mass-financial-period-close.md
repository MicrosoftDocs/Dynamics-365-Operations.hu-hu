---
title: Pénzügyi időszakok tömeges lezárása
description: Ez a cikk bemutatja, hogyan lehet egy adott időszakot vagy egynél több jogi személyt egyszerre véglegesen lezárni vagy véglegesen lezárni.
author: aprilolson
ms.date: 11/16/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerCalendar, LedgerPeriodModuleAccessControlUpdate, SysLookupPicklist, LedgerFiscalCalendarPeriodStatus
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8a85d512842b27f2d74507be16a8f2819f483e0d
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779810"
---
# <a name="mass-financial-period-close"></a>Pénzügyi időszakok tömeges lezárása

[!include [banner](../../includes/banner.md)]

Ez a cikk bemutatja, hogyan lehet egy adott időszakot vagy egynél több jogi személyt egyszerre véglegesen lezárni vagy véglegesen lezárni. Ezenkívül a feladat megmutatja, hogyan lehet bizonyos modulokra korlátozni a felhasználói csoportok könyvelését.

1. A navigációs ablakban menjen a Főkönyv **és a > időszak > főkönyvi naptárakba**. 

>[!NOTE]
> A jogi személyek megjelenített listája az oldalon kiválasztott pénzügyi naptártól függ. Csak azok a jogi személyek jelennek meg, akik a kijelölt pénzügyi naptárat használják.

2. Válassza ki a **Szerkesztés** opciót.
3. Válassza ki azt az időszakot, amelynek az állapotát módosítani szeretné.
4. Válassza ki a jogi személyeket, amelyeknek az állapotát frissíteni szeretné. Gyorsan kijelölhet minden jogi személyt a rács bal felső oldalán látható pipa kiválasztásával.  
5. A kiválasztott modul könyvelés általi elérésének megadásához jelölje be a **Modulelérés frissítése** lehetőséget. A modul állapota egyesével is frissíthető, ha egyenként szerkeszti a rácsban szereplő rekordokat. A gomb akkor hasznos, ha több jogi személy rekordjait kívánja gyorsan frissíteni.  
6. A **Pályázat** modulban válassza ki azt a modult, amelynek frissíteni kívánja az állapotát. Kattintson a **Kiválasztás** lehetőségre.
7. A **Hozzáférési szintnél** válasszon az **Összes** és az **Egyik sem** lehetőség, illetve egy adott felhasználói csoport között. Kattintson a **Kiválasztás** lehetőségre.  
- **Mind** – minden, a modulhoz szerkesztési hozzáféréssel rendelkezik felhasználó feladhat, ha az időszak meg van nyitva. 
- **Egyik** sem - a felhasználók nem tudnak a modulba küldőt, ha az időszak meg van nyitva. Egy adott felhasználócsoport lehetőség azt jelzi, hogy csak a csoportba tartozó felhasználók adhatnak fel a modulba, ha az időszak nyitott.  
8. Válassza a **Frissítés lehetőséget**, 
9. Válasszon másik időszakot állapotfrissítésre.
10. Válassza ki a jogi személyeket, amelyek időszakállapotát frissíteni szeretné.
11. Válassza az **Időszak állapotának frissítése** lehetőséget, és az állapotot állítsa **Várakoztatott**, **Nyitott** vagy **Véglegesen lezárt** értékre. A **Nyitott** lehetőség jelzi, hogy az időszakhoz lehetséges a feladás (ha a felhasználó rendelkezik hozzáféréssel). A **Várakoztatott** érték azt jelenti, hogy az időszak nem adható fel, de újra megnyitható. A **Véglegesen lezárt** azt jelenti, hogy az időszak le van zárva, és többé nem lehet megnyitni. Kiigazítások nem adhatók fel. Az összes korrekció **és** vizsgálat befejezéséig nem ajánlott Véglegesen lezárt időszak beállítása.  
12. Válassza ki a **Frissítés** lehetőséget.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
