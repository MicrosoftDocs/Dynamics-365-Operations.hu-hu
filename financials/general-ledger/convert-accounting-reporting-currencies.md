---
title: "Könyvelési vagy jelentési pénznem átváltása"
description: 
author: RobinARH
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 78223
ms.assetid: 31c56f9a-9c64-40a2-90e3-1969a760614b
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 728af2fff6317c17e47d48ea07dbeb57068fbf3f
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="convert-accounting-or-reporting-currencies"></a>Könyvelési vagy jelentési pénznem átváltása

[!include[banner](../includes/banner.md)]




Egy vállalat, amelynek módosítania kell a könyvelési pénznemét vagy a jelentési pénznemét, két lehetőség közül választhat. Az első lehetőség új vállalat létrehozása, és új kezdés. A rendelkezésre álló másik lehetőség a könyvelési, illetve a jelentési pénznem átváltási folyamatának futtatása. Ez az egy rendkívül hosszú ideig futó folyamat, amely minden tranzakciót módosít a rendszerben. A folyamat futtatása előtt némi beállítás is szükséges.

## <a name="preparing-the-legal-entity-for-currency-conversion"></a>Jogi személy felkészítése a pénznemváltásra.
A jogi személy pénznemének konvertálása előtt a vevői és szállítói számlák idegen pénznemű összegeinek átértékelését állítsa vissza, és az előző pénzügyi éveket zárja le. Ezenkívül végre kell hajtania az adatbázis előkészítését az átalakításra. Ezután végezze el a szükséges módosításokat a jogi személy számláján, amelyen pénznemkonverzió fog történni. A pénznemátváltás befejezése után néhány további eljárást kell végrehajtania. Egyeztetnie kell a kerekítési különbségeket a konvertált összegek esetében, újra kell számítani az üzleti statisztikát, naplózni kell a főkönyvi tranzakciókat, korlátozni a hozzáférést az átváltási eszközhöz, és átértékelni az idegen pénznemben megadott összegeket vevői és szállítói számlákhoz.

## <a name="setting-up-accounts-for-automatic-transactions"></a>Számlák beállítása automatikus tranzakciókhoz
A valutaátalakítási folyamat alatt a nyereségek, veszteségek vagy filléreltérések az **Automatikus tranzakciókhoz használt számlák** oldalon meghatározott számlákra kerülnek feladásra. A fő számlákat a következő típusú tranzakciókhoz kell hozzárendelni az átalakítási folyamat lefuttatása előtt:

-   Könyvelési pénznem árfolyamnyeresége
-   Könyvelési pénznem árfolyamvesztesége
-   Filléreltérés a könyvelési pénznemben
-   Fillérkülönbözet a jelentés pénznemében
-   Év végi eredmény

## <a name="posting-rounding-differences-and-sum-recalculations"></a>Összeg-újraszámítások és kerekítési különbségek feladása
Az alábbi rész bemutatja, hol fordulhatnak elő kerekítési különbségek:

-   Ha egyes termékek ára nullára konvertálódott, a program egy jelentést generál, amelyen a termékszám, a modul típusa, a konvertálás előtti ár és az egység szerepel.
-   Az áfa és a főkönyv közötti kerekítési különbségek a főkönyvi naplóba kerülnek feladásra.
-   A deviza-átértékelési összegek, valamint a vevői és szállítói tranzakciók összegei újraszámításra kerülnek.
-   Vevői és szállítói kiegyenlítési rekordjok jönnek létre az egyes vevői és szállítói tranzakciókból eredő kerekítési különbségek kezellésére.
-   A vevők és szállítók kerekítési különbségeinek a főkönyvi naplóba kerülnek feladásra.
-   A zárt készlettranzakciók kiegyenlített költségösszegeinek és költségigazítási összegei újraszámításra kerülnek.
-   A készletkezelésben fellépő kerekítési különbségek a főkönyvi naplóba kerülnek.
-   Az aktuális készlet újraszámításra kerül.
-   A főkönyvi napló végösszegei újraszámításra kerülnek.
-   A főkönyvi zárólapok újraszámításra kerülnek.
-   A főkönyvi egyenlegek újraszámításra kerülnek.
-   A főkönyvben fellépő kerekítési különbségek a főkönyvi naplóba kerülnek.
-   A főkönyvi nyitó tranzakciók újraszámításra kerülnek.
-   Kiszámításra kerül a főkönyvi egyenlegek végösszege.

Ha új főkönyvi könyvelési pénznemre konvertál, és hiba lép fel a végösszegek újraszámítása vagy a kerekítési különbségek feladása során, akkor zárja be a **Főkönyvi könyvelési pénznem átváltása** lapot. A rendszer újraszámolja a végösszegeket és feladja a kerekítési különbségeket.

## <a name="processing-the-currency-conversion"></a>Pénznemátváltás feldolgozása
A pénznemátváltási folyamat indítása előtt minden felhasználónak ki kell jelentkeznie a rendszerből. Meg kell adnia az új főkönyvet vagy a jelentési pénznemet és az árfolyamokat. Amikor rákattint az **OK** gombra, a folyamat lefut, és frissíti a rendszer minden tranzakcióját. A pénznemátváltás rendkívül hosszú folyamat. Amikor elkészült, megjelenik, hogy a könyvelés vagy a jelentési pénznem frissült a **Főkönyv** oldalon.

## <a name="completing-the-currency-conversion"></a>A pénznemátváltás befejezése
A pénznemváltást után minden egyeztetési jelentést újra kell generálni, hogy az összes átváltott érték biztosan helyesen jelenjen meg.

-   Ha a főkönyvi könyvelési pénznem kerekítési különbségeket okoz, ezek a különbségek nem lesznek feladva a bizonylat használatával, ahol a kerekítési különbség megjelent. Ehelyett a különbségek annak a bizonylatnak a használatával lesznek feladva, amely az átváltási feladásokhoz lett megadva. Az átváltás után minden jelentésen, amely bizonylat és dátum alapján készül, megjelennek a kerekítési különbségek is. Ez a viselkedés normális, figyelmen kívül hagyható jelenség.
-   Ha a vevői és a szállítói egyeztetési jelentéseknél különbség jelenik meg a végösszeg sorában, de az átváltás előtt nem volt különbség az összegek között, akkor ezt a különbséget fel kell adni. A használt számla a vevők és szállítók összesítő számlája. Az ellenszámla a főkönyvi számla az átváltási veszteséghez vagy az átváltási nyereséghez.

Ha az összes főkönyvi tranzakciónapló törölve lett, készíthet egy új naplót a főkönyvi tranzakciókról. Kattintson a **Főkönyv** &gt; **Időszakos** &gt; **Naplók** &gt; **Naplózás** lehetőségekre. A valutaösszegeket a pénznemátváltás után értékelheti át, ha átértékelésre van szükség. Idegen pénznemben megadott összegeket a **Szokásos** kiválasztásával a **Metódus** mezőben értékelhet át.




