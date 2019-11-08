---
title: Előrejelzések, munkarendelések és projektek
description: Ez a témakör az előrejelzések és munkarendelések integrációját mutatja be az Eszközkezelés projektmenedzsment és könyvelés moduljában
author: josaw1
manager: AnnBe
ms.date: 08/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e527a1ade9b050c0700ef42bbcac8da3f36160b9
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571783"
---
# <a name="forecasts-work-orders-and-projects"></a>Előrejelzések, munkarendelések és projektek

[!include [banner](../../includes/banner.md)]

 

Az Eszközkezelés integrációja a **Projektmenedzsment és könyvelés** modullal a költségcsökkentés optimalizálását segíti így a felhasználók nyomon követhetik a karbantartási feladat típusú előrejelzések és a munkarendelések feladatainak költségét.

A karbantartási feladatoktípusok előrejelzéseinek nyomon követéséhez két beállítás szükséges:

1. Válassza ki a kívánt projektet az **Eszközkezelés** > **Beállítások** > **Eszközkezelés paraméterei** alatt, majd a **Projekt** gyorslap **Eszközök** lapján > a **Karbantartási előrejelzési projekt** mezőben válasszon ki egy projektet.

2. A **Karbantartás feladattípusalapértelmezései** lapon a karbantartási feladattípus alapértelmezés sora létrehozásakor, a program automatikusan létrehoz egy tevékenységszámot a sorhoz (**Eszközkezelés** > **Beállítás** > **Feladatok** > **Karbantartási feladattípusok alapértelmezései**).

A karbantartási feladattípus előrejelzések két célt szolgálnak: 

- A karbantartási feladatoktípus előrejelzések költségei nyomon követhetők a **Projektmenedzsment és a könyvelés** modulban. 
- A program automatikusan átviszi az előrejelzéseket egy munkarendelési feladatprojektbe, amikor a munkarendelésen kiválaszt egy karbantartási feladattípust.

A munkarendelési feladatok költségeinek nyomon követéséhez előbb be kell állítania a munkarendelési projekteket. További információért lásd: [Munkarendelési projekt beállítása](../setup-for-work-orders/work-order-project-setup.md)

## <a name="work-order-job-projects"></a>Munkarendelési feladatprojekt

Amikor munkarendelésen hoz létre egy munkarendelés-feladatot, a munkarendelési projekt meghatározása a munkarendelések főprojektje beállításával történik a **Munkarendelési projekt beállítás** oldalon (**Eszközkezelés** > **Beállítás** > **Munkarendelések** > **Projektbeállítások**) helyen.

A Munkarendelés feladatprojektek a következő munkarendelésadatok együttes használatával jönnek létre:

- A munkarendelésen kiválasztott munkarendeléstípus 
- A munkarendelési feladathoz tartozó eszközhöz kapcsolódó munkavégzési helyszín
- A munkarendelési feladathoz tartozó eszközhöz kapcsolódó eszköztípus  
- A munkarendelésen megadott várható kezdési és befejezési idők  

Előfordulhat, hogy egy bizonyos információ nem található meg egy munkarendelésen. Ennek megfelelően a munkarendelés szülőprojektjének keresése a rendelkezésre álló adatok kombinációjának felhasználásával, illetve a projektazonosító adatainak megfelelő kiválasztásával történik

Például a következő ábrán a **Tehergépkocsi motor** eszköztípus be van állítva az összes munkarendelési feladaton, amely a **Tehergépkocsi motor** eszköztípussal van létrehozva a 000186-os projekt alprojektje lesz.

![1. ábra](media/01-integration-to-pma.png)

A munkarendelés feladaton szereplő projektazonosító és a kapcsolódó tevékenységszám célja munkarendelés-feladathoz kapcsolódó költségek és a kijelölt eszköz nyomon követése a **Projektmenedzsment és könyvelés** modulban. (A projekt azonosítójának és a tevékenységiszámnak megtekintéséhez válassza az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Minden munkarendelés** lehetőséget, majd jelölje ki a munkarendelést. A **Sor részletei** gyorslapon a **Projekt azonosítója** mező a projekt azonosítóját jeleníti meg, a **Tevékenység száma** mező pedig a tevékenység számát.) A költségkezeléssel kapcsolatos további tudnivalókat az Eszközkezelésben lásd a [Költség- és dátumellenőrzés](../controlling-and-reporting/cost-and-date-control.md) modulban.

Az alábbi ábrán a munkarendelési projektek és a kapcsolódó projekttevékenységek grafikus áttekintése látható.

![2. ábra](media/02-integration-to-pma.png)

Ha egy munkarendeléshez új munkarendelési feladatot hoz létre, akkor a program automatikusan létrehoz a feladathoz egy munkarendelési projektet. A program automatikusan átviszi a munkarendelési feladathoz kapcsolódó eszköz pénzügyi dimenzióit a munkarendelés-projektjébe.

A munkarendelési feladathoz létrehozott projekttevékenységhez kapcsolódó információk vannak csatolva. Ez az információ a karbantartási feladat típusát, a karbantartási feladattípus változatát és a szakmát tartalmazza. Ez akkor lehet hasznos, ha például egy beszerzési rendelést egy munkarendelésből hoz létre (lásd [Beszerzés](../work-orders/procurement.md)), vagy ha az időnyilvántartáshoz a **Projektmenedzsment és a könyvelés** modult használja.

Ha az eszköz egy munkavégzési helyszínre lett telepítve, de az eszköz később egy másik munkavégzési helyszínre kerül, akkor az új munkavégzési helyszínhez kapcsolódó pénzügyi dimenziók automatikusan frissülnek az eszközön. Majd amikor munkarendelési feladatot hoz létre a tárgyi eszközhöz, a munkarendelési feladat munkarendelési projektje automatikusan beolvassa az eszközhöz kapcsolódó pénzügyi dimenziókat. Tehát a munkavégzési helyszíneket használva mindig nyomon lehet követni azokat a munkavégzési helyszíneket, amelyeken egy eszköz egy adott időpontban telepítve van. A pénzügyi dimenziók automatikus frissítése segít garantálni a projektköltségek teljes nyomon követhetőségét ellenőrzési és jelentéskészítési célból.

## <a name="work-order-projects-work-order-lifecycle-states-project-stages-and-project-types"></a>Munkarendelési projektek, munkarendelés életciklusállapotok, projektfázisok és a projekttípusok

A munkarendelések életciklusának helyes használatának biztosítása elősegítés, valamint a munkarendelésekhez kapcsolódó projektfázisok munkarendeléseken helyes használata érdekében, vegye figyelembe, hogy milyen függőségek vannak a **Projektmenedzsment és a könyvelési** modulban:

- A **Projektmenedzsment és könyvelés** modulban a projektek fázisa a projekttípusokhoz van beállítva a **Projektvezetési és könyvelési paraméterek** oldalon.  
- A **Projektvezetési és könyvelési paramétereknél** oldalon használja megfelelő projektfázis jelölőnégyzeteket a használni kívánt összes projektfázishoz. Az alábbi ábrán öt fázis (**Létrehozva**, **Becsült**, **Ütemezett**, **Folyamatban** és **Befejezve**) az **Idő és anyag** és **Belső** projekttípusokhoz. Ezek az öt fázis mind a belső karbantartási feladatokhoz, mind a szerviz karbantartási feladatokhoz kapcsolódik.
- Az **Eszközkezelés** modulban a projekttípusok a **Munkarendelés projekt beállítása** oldal > **Projektcsoport** lapján beállított projektcsoportok (**Eszközkezelés** > **Beállítások** > **Munkarendelések** > **Projekt beállítása**).  
- A Munkarendelések létrehozása során a **Munkarendelés projekt beállítása** oldal projektcsoportok beállítását használja a rendszer. Ha egy munkarendelés jön létre akkor a program automatikusan létrehoz a munkarendeléshez egy munkarendelési projektet.  
- Minden munkarendelés életciklus-állapotnak tartalmaznia kell egy kapcsolódó projektfázist.  
- A Munkarendelés életciklus-állapotához kapcsolódó projektfázist aktív fázisaként kell definiálni a munkarendelési projektben meghatározott projektcsoporthoz. A munkarendelési projekt automatikusan létrejön egy munkarendelésen.
- Amikor létrehoz egy munkarendelést a munkarendelési projektek automatikus elosztása a **Munkarendelés projekt beállítása** oldalon alapul  

A munkarendelés projektcsoportok, a kapcsolódó projekttípus, projektfázisok és munkarendelés életciklusok között társítások az alábbi ábrákon láthatók.

![3. ábra](media/03-integration-to-pma.png)

![4. ábra](media/04-integration-to-pma.png)

![5. ábra](media/05-integration-to-pma.png)

A munkarendelés-projektek beállításáról a [Munkarendelés-projektek beállításai](../setup-for-work-orders/work-order-project-setup.md) című cikkben talál további információt. A munkarendelés életciklus-állapotok és projektfázisok létrehozásával kapcsolatos további információért lásd: [Munkarendelés életciklus-állapotai](../setup-for-work-orders/work-order-lifecycle-states.md).

A következő ábra az **Eszközkezelés** modulban létrehozott különböző projektek grafikus áttekintését mutatja be, amely lehetővé teszi a **Projektmenedzsment és a könyvelési** modul integrációját. Bemutatja azokat a munkafolyamatokat is, amelyekhez a projektek kapcsolódnak.

![6. ábra](media/06-integration-to-pma.png)

