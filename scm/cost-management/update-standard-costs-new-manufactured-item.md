---
title: "Újonnan gyártott cikkek elszámoló árának frissítése"
description: "Ez a leírás az újonnan gyártott cikkek alapköltségeinek frissítéséhez nyújt útmutatást."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 79693
ms.assetid: ba64b70f-3f4c-4373-9a7d-8fd07c45a8cf
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: d8f1b5614811faad3fda15809e4e606c93e6b786
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="update-standard-costs-for-a-new-manufactured-item"></a>Újonnan gyártott cikkek elszámoló árának frissítése

[!include[banner](../includes/banner.md)]


Ez a leírás az újonnan gyártott cikkek alapköltségeinek frissítéséhez nyújt útmutatást. 

Az alábbi irányelvek feltételezik, hogy a kétverziós megközelítés segítségével frissíti az elszámoló költséget. Ebben a megközelítésben az egyik költségszámítási verzió az eredetileg a befagyasztott időszakra meghatározott elszámolási árakat tartalmazza, míg a másik költségszámítási verzió az újonnan gyártott cikkekhez tartozó járulékos frissítéseket tartalmazza. A járulékos frissítéseket költségrekordként lehet megadni a második költségszámítási verzióban, majd ezután válnak elérhetővé. A kétverziós megközelítés egy második költségszámítási verzió meghatározását igényli. Az ennek a költségszámítási verziónak a meghatározására vonatkozó irányelvek a következők:

-   Rendeljen hozzá egy **Alapköltség** típusú költségszámítást.
-   Rendeljen hozzá egy egyértelmű azonosítót a költségverzióhoz, amely utal a költségverzió tartalmára. Például: **2016-FRISSÍTÉSEK**.
-   Az **Ártípusok engedélyezése** mezőcsoportban, győződjön meg róla, hogy az **Önköltségi ár** értéke **Igen**.
-   Engedélyezze a költség feljegyzések bevitelét minden webhely számára úgy, hogy üresen hagyja a **Webhely**mezőt. Ha megad egy webhelyet, akkor a költségrekordok csak arra a webhelyre rögzíthetők.
-   Használja az **Aktív** tartalékelvet.

Ha a befagyasztott időszak során új gyártott cikkeket kíván hozzáadni, tegye a következőket:

1.  Használja a **Költségszámítási verzió beállítása** lapot a költségrekordok második, járulékos frissítéseket tartalmazó költségszámítási verziójába történő beírásának engedélyezéséhez. Előzze meg a függő költségek aktiválását ott, ahol csak a függő költségek teljes és pontos meghatározásakor van engedélyezve az aktiválás. A költségverzióban egy üres kezdő dátumot adjon meg szabályként, majd adja meg az egyes költségrekordok rögzítésének dátumát kezdő dátumként. A kezdő dátumnak meg kell előznie az új cikkek beszerzési vagy gyártási dátumát.
2.  Használja a **Cikk ár** oldalt, hogy rögzítse az új beszerzett cikkek költségrekordjait. Minden költségrekordnál adja meg a költségszámítási verziót, amely tartalmazza a járulékos frissítéseket, és adjon meg olyan kezdő dátumot, amely megelőzi az új cikkek várható gyártásának a dátumát.
3.  Számítsa ki az új gyártott cikkek költségét a **Kiszámítás** lap segítségével. Nyissa meg a **Kiszámítás** lapot a **költségszámítási verzió fenntartása** oldalról, majd válassza ki azt a költségszámítási verziót, amely a járulékos frissítéseket tartalmazza. Használja a kiválasztási feltételeket, hogy meghatározza az újonnan gyártott cikkeket és azok bármely gyártási összetevőjét. Többszintű termékszerkezet esetén szükség lehet az újonnan gyártott cikkeket összetevőként tartalmazó főcikk azonosítására is. Adjon meg egy kezdő dátumot az anyagjegyzék-számításhoz, amely megfelel annak az időpontnak, amikor az új cikkeket gyártani kezdik. A kezdő dátumnak a cikk anyagjegyzék-verziójának és útvonalverziójának tényleges dátumai közé kell esnie. **Megjegyzés:** A hiányzó költségrekord jelezheti az újonnan gyártott cikket. Az Anyagjegyzék-számítások korlátozhatók a hiányos költségekkel rendelkező cikkekre.
4.  Erősítse meg az újonnan gyártott cikkek számított árainak a pontosságát és teljesítettségét. A **Teljesített** lap használatával lehet az egyes cikk-költség rekordokhoz tartozó számított költségeket, valamint az információs napló esetleges figyelmeztető üzeneteit ellenőrizni. Másik lehetőségként a **Számítás** oldal használatával lehet a számított költségek listáját ellenőrizni.
5.  Használja a **Költségszámítási verzió beállítása** lapot, hogy módosítsa a zárolás jelzőt, ezzel lehetővé téve a második költségszámítási verzióba foglalt függőben lévő költségrekordok aktiválását.
6.  Használja a **Költségszámítási verzió fenntartása** lapról megnyitható **Árak aktiválása** oldalt, hogy engedélyezze az összes a második költségszámítási verzióba foglalt függőben lévő költségrekordot. Elérhetővé teheti az egyes cikkekhez tartozó függőköltség-rekordokat is a **Cikk ár** oldalon szereplő **Aktiválás** gombbal.
7.  A további adat-fenntartás megelőzése érdekében, használja a **Költségszámítási verzió beállítása** lapot, hogy módosítsa a második költségszámítási verzióba foglalt zárolás jelzőket. Az irányelvek zárolása megakadályozza az új függő költségek bevitelét és a függő költségek aktiválását.





