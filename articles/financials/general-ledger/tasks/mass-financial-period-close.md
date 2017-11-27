--- 
title: "Pénzügyi időszakok tömeges lezárása"
description: "Ez az eljárás bemutatja, hogyan helyezhető várakoztatásba, illetve hogyan zárható le véglegesen egy időszak egy időben több jogi személyre vonatkoztatva."
author: aprilolson
manager: AnnBe
ms.date: 10/25/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ef3cad6538d9efbd1c1881f4b7d771382d9b1ba8
ms.openlocfilehash: 1954bfdf4807e91d275e3a1ba80f959bdf9464a8
ms.contentlocale: hu-hu
ms.lasthandoff: 10/26/2017

---
# <a name="mass-financial-period-close"></a>Pénzügyi időszakok tömeges lezárása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan helyezhető várakoztatásba, illetve hogyan zárható le véglegesen egy időszak egy időben több jogi személyre vonatkoztatva. Ezenkívül a feladat megmutatja, hogyan lehet bizonyos modulokra korlátozni a felhasználói csoportok könyvelését.

1. Lépjen a Főkönyv > Időszak lezárása > Főkönyvi naptárak elemre.
    * Vegye figyelembe, hogy a megjelenített jogi személyek listája a lapon kiválasztott pénzügyi naptár függvénye. Csak azok a jogi személyek jelennek meg, akik a kijelölt pénzügyi naptárat használják.  
2. Kattintson a Szerkesztés lehetőségre.
3. Válassza ki azt az időszakot, amelynek az állapotát módosítani szeretné.
4. Válassza ki a jogi személyeket, amelyeknek az állapotát frissíteni szeretné.
    * Gyorsan kijelölhet minden jogi személyt a rács bal felső oldalán látható pipa kiválasztásával.  
5. A kiválasztott modul könyvelés általi elérésének megadásához jelölje be a Modulelérés frissítése lehetőséget.
    * A modul állapota egyesével is frissíthető, ha egyenként szerkeszti a rácsban szereplő rekordokat. A gomb akkor hasznos, ha több jogi személy rekordjait kívánja gyorsan frissíteni.  
6. A Pályázat modul mezőben válassza ki a modult, amelynek frissíteni kívánja az állapotát. Kattintson a Kiválasztás lehetőségre.
7. A Hozzáférési szint elemnél válasszon az Összes és az Egyik sem lehetőség, illetve adott felhasználói csoport között. Kattintson a Kiválasztás lehetőségre.
    * Az Összes lehetőség jelezi, hogy az összes modulhoz szerkesztési joggal rendelkező felhasználó feladhat, ha az időszak nyitott. Az Egyik sem lehetőség azt jelezi, hogy a felhasználók nem adhatnak fel a modulba, ha az időszak nyitott. Egy adott felhasználócsoport lehetőség azt jelzi, hogy csak a csoportba tartozó felhasználók adhatnak fel a modulba, ha az időszak nyitott.  
8. Kattintson a Módosítás gombra.
9. Válasszon másik időszakot állapotfrissítésre.
10. Válassza ki a jogi személyeket, amelyek időszakállapotát frissíteni szeretné.
11. Válassza az Időszak állapotának frissítése lehetőséget, és az állapotot állítsa Várakoztatott, Nyitott vagy Véglegesen lezárt értékre.
    * Nyitott lehetőség jelzi, hogy az időszakba fel lehet adni, ha a felhasználó rendelkezik hozzáféréssel. A Várakoztatott azt jelenti, hogy az időszak nem adható fel, de az időszak újra megnyitható. A Véglegesen lezárt azt jelenti, hogy az időszak le van zárva, és többé nem lehet megnyitni. Kiigazítások nem adhatók fel. Nem ajánlott véglegesen lezártra állítani egy időszakot, amíg az összes kiigazítás és vizsgálat le nem zárult.  
12. Kattintson a Módosítás gombra.


