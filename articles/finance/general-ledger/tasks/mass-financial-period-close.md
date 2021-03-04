---
title: Pénzügyi időszakok tömeges lezárása
description: Ez a cikk bemutatja, hogyan várakoztatható, illetve hogyan zárható le véglegesen egy időszak egyszerre, több jogi személyre vonatkoztatva.
author: aprilolson
manager: AnnBe
ms.date: 08/16/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerCalendar, LedgerPeriodModuleAccessControlUpdate, SysLookupPicklist, LedgerFiscalCalendarPeriodStatus
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a149b35c6964166207effc799a02cd4c59bbb843
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443905"
---
# <a name="mass-financial-period-close"></a>Pénzügyi időszakok tömeges lezárása

[!include [banner](../../includes/banner.md)]

Ez a cikk bemutatja, hogyan várakoztatható, illetve hogyan zárható le véglegesen egy időszak egyszerre, több jogi személyre vonatkoztatva. Ezenkívül a feladat megmutatja, hogyan lehet bizonyos modulokra korlátozni a felhasználói csoportok könyvelését.

1. A navigációs ablakban lépjen a **Modulok > Főkönyv > Időszak lezárása > Főkönyvi naptárak** részre. Vegye figyelembe, hogy a megjelenített jogi személyek listája a lapon kiválasztott pénzügyi naptár függvénye. Csak azok a jogi személyek jelennek meg, akik a kijelölt pénzügyi naptárat használják.
2. Válassza ki a **Szerkesztés** opciót.
3. Válassza ki azt az időszakot, amelynek az állapotát módosítani szeretné.
4. Válassza ki a jogi személyeket, amelyeknek az állapotát frissíteni szeretné. Gyorsan kijelölhet minden jogi személyt a rács bal felső oldalán látható pipa kiválasztásával.  
5. A kiválasztott modul könyvelés általi elérésének megadásához jelölje be a **Modulelérés frissítése** lehetőséget. A modul állapota egyesével is frissíthető, ha egyenként szerkeszti a rácsban szereplő rekordokat. A gomb akkor hasznos, ha több jogi személy rekordjait kívánja gyorsan frissíteni.  
6. A **Pályázat** modulban válassza ki azt a modult, amelynek frissíteni kívánja az állapotát. Kattintson a **Kiválasztás** lehetőségre.
7. A **Hozzáférési szintnél** válasszon az **Összes** és az **Egyik sem** lehetőség, illetve egy adott felhasználói csoport között. Kattintson a **Kiválasztás** lehetőségre. Az Összes lehetőség jelezi, hogy az összes modulhoz szerkesztési joggal rendelkező felhasználó feladhat, ha az időszak nyitott. Az Egyik sem lehetőség azt jelezi, hogy a felhasználók nem adhatnak fel a modulba, ha az időszak nyitott. Egy adott felhasználócsoport lehetőség azt jelzi, hogy csak a csoportba tartozó felhasználók adhatnak fel a modulba, ha az időszak nyitott.  
8. Válassza ki a **Frissítés** lehetőséget.
9. Válasszon másik időszakot állapotfrissítésre.
10. Válassza ki a jogi személyeket, amelyek időszakállapotát frissíteni szeretné.
11. Válassza az **Időszak állapotának frissítése** lehetőséget, és az állapotot állítsa **Várakoztatott**, **Nyitott** vagy **Véglegesen lezárt** értékre. A **Nyitott** lehetőség jelzi, hogy az időszakhoz lehetséges a feladás (ha a felhasználó rendelkezik hozzáféréssel). A **Várakoztatott** érték azt jelenti, hogy az időszak nem adható fel, de újra megnyitható. A **Véglegesen lezárt** azt jelenti, hogy az időszak le van zárva, és többé nem lehet megnyitni. Kiigazítások nem adhatók fel. Nem ajánlott **véglegesen lezártra** állítani egy időszakot, amíg az összes kiigazítás és vizsgálat le nem zárult.  
12. Válassza ki a **Frissítés** lehetőséget.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]