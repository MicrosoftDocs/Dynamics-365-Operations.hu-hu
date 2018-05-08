---
title: "Csalási figyelmeztetések beállítása"
description: "Ez a témakör ismerteti a szabályok beállítását az ügyfélszolgálati munkatársak figyelmeztetésére az esetleg csaló információról a rendelések feldolgozása során. Meghatározhat specifikus kódokat, hogy automatikusan vagy manuálisan várakoztassa a gyanús rendeléseket."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: SalesPostingHistory, MCRHoldCodeTrans, SysOperationTemplateForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: f57cdb44d5ed3b078478cf47b74d1a79ba10323c
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-fraud-alerts"></a>Csalással kapcsolatos figyelmeztetések beállítása

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet kritériumokat és szabályokat létrehozni a potenciálisan csaló értékesítési megrendelések lefoglalására további ellenőrzés céljából. A csalás felülvizsgálatának funkciója meghatározza az információ érvényességét egy értékesítési megbízásban. Ha az értékesítési rendelésben szereplő információk a szervezet csalási kritériumai és szabályai alapján megkérdőjelezhetőnek tűnnek, akkor a megrendelést egy rendszergazda további felülvizsgálatra bocsátja.

> [!NOTE]
> Ez a funkció csak a Retail hívásközpont csatorna értékesítési rendeléseinek feldolgozására használható. 

Amikor a Call Center csatorna meg van adva, a **Rendeléskiegészítés engedélyezése** beállítása **Igen** kell, hogy legyen. Amikor a rendelés befejezése engedélyezett, a felhasználók megtekinthetik a rendelés összefoglalását, majd kattintsanak a **Küldés** lehetőségre a véglegesítéshez. A felhasználók számára is lehetőséget biztosítunk arra, hogy manuálisan helyezzék el az értékesítési rendelést a csalás felülvizsgálatára. A Call Center felhasználó által bevitt megrendelések feldolgozása folyamatban van a csalások ellenőrzési szabályainak és kritériumainak a benyújtási folyamat során.

Kétfajta csalási kritérium létezik, amelyekre a rendszer hivatkozni fog a csalás ellenőrzése érdekében:

-   A **statikus szabályok** egy meghatározott értéket használnak, például egy feketelistán szereplő telefonszámot vagy egy olyan e-mail címet, amelyet a múltbeli csalárd ügyletekhez használtak. A **Statikus csalási adatok** lapon a csalási információk manuálisan vagy adatbevitel útján is hozzáadhatók, a csaló információkhoz csatolt pontszámokkal. Ha a csalásellenőrzés be van kapcsolva, minden bevitt értékesítési rendelés összehasonlításra kerül a statikus adatokkal. Ha az adatok megtalálhatók az ügyfél számlázási vagy kézbesítési címében, vagy ha az adatok megtalálhatók az értékesítési vonal címzési címében, akkor az összes egyedi találat összegét összegezni fogják.  
-   A **dinamikus szabályok** az adott változók számára meghatározott változókból és feltételekből állnak. A dinamikus szabályokkal ellenőrizhetők a statikus szabályok által nem meghatározott egyéb kritériumok. Bonyolultabb "ÉS/VAGY" állítások használhatók több feltétel megfontolására annak megállapítására, hogy van-e pozitív egyezés a szabálykritériumokkal és a benyújtott vevői rendelettel. Például ha egy felhasználó csalásra szeretne tartani az ügyfelek összes olyan megrendelését, amely egy adott ügyfélcsoport értékéhez kötődik, és egy adott terméket rendelt el, az ügyfél hitelesítésének és a termékek validálásának feltételeit a **Szabályok** oldalon egy “ÉS” feltétellel. A megrendelés csak akkor lenne csalás, ha mindkét feltétel igaz, és ha a szabályhoz rendelt pontszám értéke a megrendelés teljes csalási pontszámát a Call Center-paraméterekben meghatározott minimális csalási pontszám fölé helyezi.

A hívásközpont-felhasználó manuálisan is elhelyezhet egy rendelést a csalási tartaléksorba. Ha a megrendelésbe bevonó felhasználó úgy véli, hogy a megrendelést elhelyező ügyfél gyanús lehet, és azt szeretné, hogy valaki másként ellenőrizze a megbízás érvényességét a feldolgozás előtt, akkor a megrendelést megadó felhasználó kiválaszthatja a **Csalás manuális várakoztatása** lehetőséget a **Várakoztatások** legördülő menüben az **Értékesítési rendelés összesítése** lapon (ez a **Kész** rendelésfunkció meghívása után jelenik meg). A felhasználót arra kérik, hogy írjon be egy megjegyzést annak érdekében, hogy részletesebben megmagyarázza, miért érzi úgy, hogy a megbízás csalárd, így a véleményezőnek több kontextusa is van.

Minden kézi csalással megtartott megrendelést vagy a csalások eredményeinek szisztematikus kiszámítása a **Rendelésvárakoztatások** lapon jelenik meg, ahol a megrendelést felül lehet vizsgálni, majd törölni lehet azt, vagy fel lehet szabadítani feldolgozásra.

> [!NOTE]
> Több szabály vagy túlságosan bonyolult szabályok használata rossz rendelési rendszert eredményezhet az értékesítési rendelések beadásakor. A csalás riasztási funkció nem lett optimalizálva, hogy nagy mennyiségű statikus csalási adatbevitelt és sok aktív szabályt kezeljen. Fontos megjegyezni, hogy minden szabályt a Call Center értékesítési rendelés bejegyzés funkciójában értékelnek. A szabályokat összevetjük az értékesítési rendelés fejlécével és az összes rendelési sorral. Minél több szabály létezik, és minél bonyolultabbak a szabályok, annál hosszabb lesz a folyamat. Ha sok sora van a rendelésében, és számos aktív szabályt és statikus adatbevitelt tartalmaz a rendelés, az összes adat ellenőrzésének és érvényesítésének szisztematikus folyamata és a csalás pontszámának számítása negatív hatással lehet a teljesítményre.  A funkciót használó szervezeteknek mindig meg kell győződniük és ellenőrizniük kell, hogy a rendelés beküldésének feldolgozási ideje elfogadható a szabályok vagy a statikus csalás kritériumainak a termelési környezetbe történő alkalmazása előtt.

