---
title: Előrejelzések, munkarendelések és projektek
description: Ez a témakör az előrejelzések és munkarendelések integrációját mutatja be az Eszközkezelés projektmenedzsment és könyvelés moduljában
author: josaw1
manager: AnnBe
ms.date: 08/16/2019
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
ms.openlocfilehash: 5e986d139ac9d0a7729bb9787f05332bcc09f59b
ms.sourcegitcommit: 109a6ef2d20758dc4a25c51b11e22dd2214a1cc4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/16/2019
ms.locfileid: "1886816"
---
# <a name="forecasts-work-orders-and-projects"></a>Előrejelzések, munkarendelések és projektek

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Az Eszközkezelés integrációja a **Projektmenedzsment és könyvelés** modulba a költségcsökkentés optimalizálása érdekében történik, így a felhasználók nyomon követhetik a karbantartási feladat típusú előrejelzések és a munkarendelések feladatainak költségét.

A karbantartási feladatoktípusok előrejelzéseinek nyomon követéséhez két beállítást kell végrehajtani:

1. Válasszon ki egy projektet az **Eszközkezelés** > **Beállítás** > **Eszközkezelési paraméterek** > **Eszközök** hivatkozás > **Projekt** gyorslap > **Karbantartási előrejelzés projekt** mezőben.

2. A **Karbantartás feladattípusalapértelmezései** alatt a karbantartási feladattípus alapértelmezés sora létrehozásakor, a program automatikusan létrehoz egy tevékenységszámot a sorhoz (**Eszközkezelés** > **Beállítás** > **Feladatok** > **Karbantartási feladattípusok alapértelmezései**).

A karbantartási feladattípus-előrejelzések két célt szolgálnak: Nyomon követheti a karbantartási feladattípus előrejelzések költségeit a **Projektmenedzsment és a könyvelés** modulban. Ezenkívül a program automatikusan átviszi az előrejelzéseket egy munkarendelési feladatprojektbe, amikor a munkarendelésen kiválaszt egy karbantartási feladattípust.

A munkarendelési feladatok költségeinek nyomon követéséhez előbb be kell állítania a munkarendelési projekteket. Olvassa el az [Munkarendelés projekt beállítása](../setup-for-work-orders/work-order-project-setup.md) szakaszt az eljárás leírásáért.

## <a name="work-order-job-projects"></a>Munkarendelési feladatprojekt

Amikor munkarendelésen hoz létre egy munkarendelés-feladatot, a munkarendelési projekt meghatározása a munkarendelések főprojektje beállításával történik az **Eszközkezelés** > **Beállítás** > **Munkarendelések** > **Projektbeállítások** helyen.

A Munkarendelés feladatprojektek a következő munkarendelésadatok együttes használatával jönnek létre:

- A munkarendelésen kiválasztott Munkarendeléstípus 
- A munkarendelési feladathoz tartozó eszközhöz kapcsolódó munkavégzési helyszín
- A munkarendelési feladathoz tartozó eszközhöz kapcsolódó eszköztípus  
- A munkarendelésen megadott várható kezdési és befejezési idő  

Előfordulhat, hogy a fentiekben említett információk nem mind találhatók meg a munkarendelésen. Ennek megfelelően a munkarendelés szülőprojektjének keresése a rendelkezésre álló adatok kombinációjának felhasználásával, illetve a projektazonosító adatainak megfelelő kiválasztásával történik

Példa: Az alábbi ábrán a „Teherautómotor” eszköztípus beállítása azt jelenti, hogy az adott eszköztípussal létrehozott összes munkarendelési feladat a „000186” projektazonosító alprojektje lesz.

![1. ábra](media/01-integration-to-pma.png)

A munkarendelésenszereplő projektazonosító és kapcsolódó tevékenységszám (**Eszközkezelés** > **Közös** > **Munkarendelések** > **Minden munkarendelés** > munkarendelés kiválasztása a listából > **Sor részletei** gyorslap > **Projektazonosító** mező és a **Tevékenység száma** mező) a munkarendelési feladathoz és a munkarendelésen kiválasztott eszközzel kapcsolatos feladat költségeinek nyomon követésére szolgál a **Projektmenedzsment és a könyvelési** modulban. 

Az alábbi ábra a munkarendelési projektek és a kapcsolódó projekttevékenységek grafikus áttekintését jeleníti meg.

![2. ábra](media/02-integration-to-pma.png)

Ha egy munkarendeléshez új munkarendelési feladatot hoz létre, akkor a program automatikusan létrehoz a feladathoz egy munkarendelési projektet. A program automatikusan átviszi a munkarendelési feladathoz kapcsolódó eszköz pénzügyi dimenzióit a munkarendelés-projektjébe. A munkarendelési feladathoz létrehozott projekttevékenységek a karbantartási feladattípussal, a karbantartás feladattípus változattal és a szakmával kapcsolatos információkat tartalmaz. Ezeket az adatok akkor lehetnek hasznosak, ha például egy beszerzési rendelést egy munkarendelésből hoz létre (lásd [Beszerzés](../work-orders/procurement.md)), vagy ha az időnyilvántartáshoz a **Projektmenedzsment és a könyvelés** modult használja.  

Ha az eszköz egy munkavégzési helyszínre lett telepítve, és az eszköz később egy másik munkavégzési helyszínre kerül, akkor az újmunkavégzési helyszínhez kapcsolódó pénzügyi dimenziók automatikusan frissülnek az eszközön. Ezt követően, amikor munkarendelési feladatot hoz létre a tárgyi eszközhöz, a munkarendelési feladat munkarendelési projektje automatikusan beolvassa az eszközhöz kapcsolódó pénzügyi dimenziókat. Ez azt jelenti, hogy a munkavégzési helyszíneket használva mindig nyomon lehet követni azokat a munkavégzési helyszíneket, amelyeken egy eszköz egy adott időpontban telepítve van. A pénzügyi dimenziók automatikus frissítése biztosítja a projektköltségek teljes nyomon követhetőségét ellenőrzési és jelentéskészítési célból.  


## <a name="work-order-projects-work-order-lifecycle-states-project-stages-and-project-types"></a>Munkarendelési projektek, munkarendelés életciklusállapotok, projektfázisok és a projekttípusok

A munkarendelések életciklusának helyes használatának biztosítása, valamint a munkarendelésekhez kapcsolódó projektfázisok munkarendeléseken helyes használata érdekében, vegye figyelembe, hogy milyen függőségek vannak a **Projektmenedzsment és a könyvelési** modulban:

- A **Projektmenedzsment és könyvelés** modulban a projektek fázisa a projekttípusokhoz van beállítva a **Projektvezetési és könyvelési paraméterek** helyen.  
- A **Projektvezetési és könyvelési paramétereknél** ne felejtse el kiválasztani a megfelelő projektfázis jelölőnégyzeteket a használni kívánt összes projekttípushoz. Az alábbi ábrán öt fázis **Létrehozva** - **Becsült** - **Ütemezett** - **Folyamatban** - **Befejezve** az „Idő” és „Belső” projekttípusokhoz. Ezek az öt fázis mind a belső karbantartási, mind a szerviz karbantartási feladatokhoz kapcsolódik.  
- Az **Eszközkezelés** modulban a projekttervek a **Munkarendelés projekt beállítása** űrlap> **Projektcsoport** hivatkozásával vannak meghatározva.  
- A Munkarendelések létrehozása során a **Munkarendelés projektbeállítását** projektcsoportok beállítását használja a rendszer. Ha egy munkarendelés jön létre akkor a program automatikusan létrehoz a munkarendeléshez egy munkarendelési projektet.  
- A Munkarendelés életciklus-állapotoknak tartalmazniuk kell egy kapcsolódó projektfázist.  
- A Munkarendelés életciklus-állapotához kapcsolódó projektfázist aktív fázisként kell definiálni a munkarendelési projektben meghatározott projektcsoporthoz. A munkarendelési projekt automatikusan létrejön egy munkarendelésen.  
- Amikor létrehoz egy munkarendelést a munkarendelési projektek automatikus elosztása a **Munkarendelés projektbeállításán** alapul (**Eszközkezelés** > **Beállítás** > **Munkarendelések** > **Projektbeállítások**).  

A munkarendelés projektcsoportok, a kapcsolódó projekttípus, projektfázisok és munkarendelés életciklusok között társítások az alábbi ábrákon láthatók.  

![3. ábra](media/03-integration-to-pma.png)

![4. ábra](media/04-integration-to-pma.png)

![5. ábra](media/05-integration-to-pma.png)

Lásd [Munkarendelés projektbeállítás](../setup-for-work-orders/work-order-project-setup.md) a munkarendelés projektek beállításával kapcsolatosan, valamint a [Munkarendelés életciklus-állapotok](../setup-for-work-orders/work-order-lifecycle-states.md) részt a munkarendelés életciklus-állapotok létrehozásával kapcsolatosan.

Az alábbi ábra az **Eszközkezelés** modulban létrehozott különböző projektek grafikus áttekintését jeleníti meg, amely lehetővé teszi a **Projektmenedzsment és a könyvelés** modul integrálását, valamint azokat a munkafolyamatokat, amelyekhez a projektek kapcsolódnak.

![6. ábra](media/06-integration-to-pma.png)

