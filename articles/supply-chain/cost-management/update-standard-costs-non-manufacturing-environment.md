---
title: "Elszámoló árak frissítése nem-termelő jellegű környezetben"
description: "Ez a cikk az elszámoló-árak nem-gyártási környezetben történő frissítésének útmutatását tartalmazza."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 79723
ms.assetid: 7ba0c408-2450-4042-9542-6fdf83c12e6c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 0386ca1e5e7bf6e578ba2abf1b2c9eefe4dd2a02
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="update-standard-costs-in-a-non-manufacturing-environment"></a>Elszámoló árak frissítése nem-termelő jellegű környezetben

[!include [banner](../includes/banner.md)]

Ez a cikk az elszámoló-árak nem-gyártási környezetben történő frissítésének útmutatását tartalmazza.

Az alábbi irányelvek feltételezik, hogy a kétverziós megközelítés segítségével frissíti az elszámoló árat. Ebben a megközelítésben az egyik költségszámítási verzió az eredetileg a befagyasztott időszakra meghatározott elszámolási árakat tartalmazza, míg a másik költségszámítási verzió a járulékos frissítéseket tartalmazza. Minden módosítás a második költségverzióban rögzített költségrekordként kerül bevitelre, végül pedig engedélyezésre. Alternatív megoldás a kezdetben meghatározott elszámolási árakat használó egyverziós megközelítés alkalmazása. A kétverziós megközelítés egy második költségszámítási verzió meghatározását igényli. Az ennek a költségszámítási verziónak a meghatározására vonatkozó irányelvek a következők:

-   Rendeljen hozzá egy **Elszámoló árat** a költségszámítási típushoz.
-   Rendeljen hozzá egy egyértelmű azonosítót a költségverzióhoz, amely utal a költségverzió tartalmára. Például: **2016-FRISSÍTÉSEK**.
-   Győződjön meg róla, hogy a tartalomban szerepelnek költségrekordok.
-   Engedélyezze a költségrekordok bevitelét minden webhely esetében. Ha megad egy webhelyet, akkor a költségrekordok csak arra a webhelyre rögzíthetők.
-   Tartalékelvként adja meg a **Nincs** beállítást. A tartalékelv csak a legyártott cikkek költségkalkulációira vonatkozik.

Az új cikkekre vonatkozó elszámoló árak javításához, korrekciójához vagy frissítéséhez kövesse az alábbi lépéseket:

1.  Használja a **Költségszámítási verzió** **beállítás** lapját a költségadatok második költségszámítási verziójába történő beírásának engedélyezéséhez. Lehetőség szerint, akadályozza meg a függő költségek aktiválását, hogy az aktiválás a függő költségek teljes körű és pontos meghatározása után történjen csak meg. Szintén igény szerint adhat meg dátumot a **Dátumtól** mezőben. Általánosan az az alapelv, hogy a járulékos frissítések tervezett aktiválási időpontjának dátumát kell megadni. Másik lehetőségként a költségszámítási verzió **Dátumtól** mezőjét üresen lehet hagyni és elég az egyes költségrekordok esetében kitölteni a **Dátumtól** mezőt.
2.  Használja a **Cikkár** lapot a frissítések második költségszámítási verzióba foglalt cikk-költségrekordként történő beviteléhez.
3.  Használja a **Cikk árak** jelentést a második költségszámítási verzióba foglalt cikk-költségrekordok teljességének és pontosságának a megerősítéséhez.
4.  Használja a **Költségszámítási verzió fenntartása** lapot, hogy módosítsa a zárolás jelzőt, ezzel lehetővé téve a második költségszámítási verzióba foglalt függőben lévő költségrekordok aktiválását.
5.  Használja a **Költségszámítási verzió fenntartása** lapról megnyitható **Árak aktiválása** oldalt, hogy aktiválja az összes a második költségszámítási verzióba foglalt függőben lévő költségrekordot. Az egyes cikkekhez tartozó függőköltség-rekordokat is aktiválhatja a **Cikk ár** oldalon szereplő **Függő-ár aktiválása** gombbal .
6.  A további adat-fenntartás megelőzése érdekében, használja a **Költségszámítási verzió beállítása** lapot, hogy módosítsa a második költségszámítási verzióba foglalt zárolás jelzőket. Az irányelvek zárolása megakadályozza az új függő költségek bevitelét és a függő költségek aktiválását.





