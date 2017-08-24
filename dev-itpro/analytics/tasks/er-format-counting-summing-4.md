--- 
title: "Formátum futtatása számláláshoz és összegzéshez az elektronikus jelentéskészítéshez (ER)"
description: "Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat egy elektronikus jelentési (ER) formátumot számlálás és összegzés céljára a már létrehozott szöveges kimeneti adatok alapján."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 90a0dc0fc32a448d859fbb0933ea6f12ea16668f
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="run-the-format-to-do-counting-and-summing-for-electronic-reporting-er"></a>Formátum futtatása számláláshoz és összegzéshez az elektronikus jelentéskészítéshez (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat egy elektronikus jelentési (ER) formátumot számlálás és összegzés céljára a már létrehozott szöveges kimeneti adatok alapján. Ezeket a lépéseket a DEMF vállalatban hajthatja végre.

A lépések végrehajtásához először végre kell hajtania az „ER Számláláshoz és összegzéshez használt formátum konfigurálása (3. rész: Számlálások használata a kimenet elkészítéséhez)” eljárás lépéseit.

Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.


## <a name="test-this-configuration-for-generation-of-the-intrastat-reports"></a>A konfiguráció tesztelése az Intrastat-jelentések létrehozása céljából
1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
2. Kattintson a Jelentéskészítés konfigurációi lehetőségre.
3. A fastruktúrában bontsa ki az „Instrastat modell” elemet.
4. A fastruktúrában bontsa ki a következőt: „Intrastat modell\Intrastat (DE)”.
5. A fastruktúrában válassza ki a következőt: „Intrastat modell\Intrastat (DE) \Intrastat (DE) számolással és összegzéssel”.
6. Kattintson a Konfigurációk lehetőségre a Művelet Panelen.
7. Kattintson a Felhasználói paraméterek lehetőségre.
8. Válassza az Igen lehetőséget a Beállítások futtatása mezőben.
9. Kattintson az OK gombra.
10. Kattintson a Szerkesztés lehetőségre.
11. Válassza az Igen lehetőséget a Vázlat futtatása mezőben.
12. Kattintson a Mentés gombra.
13. Ugorjon az Adó > Beállítás > Külkereskedelmi > Külkereskedelmi paraméterek pontra.
14. Bontsa ki az elektronikus jelentéskészítés szakaszát.
15. Válassza az „Intrastat (DE) számolással és összegzéssel” konfigurációt.
16. Válassza az „Intrastat (DE) számolással és összegzéssel” konfigurációt.
17. Kattintson a Mentés gombra.
18. Zárja be a lapot.
19. Ugorjon az Adó > Nyilatkozatok > Külkereskedelem > Intrastat pontra.
20. Kattintson a Kimenet lehetőségre.
21. Kattintson a Jelentésre.
    * Az Intrastat jelentéslétrehozási folyamat futtatása.  
22. A Kezdő dátum mezőben állítsa „2000-01-01” értékűre a dátumot.
    * A jelentési időszak kezdő és záró dátumának beállítása, amelyek tartalmazzák a meglévő űrlaptranzakciókat.  
23. A Befejező dátum mezőben állítsa „2022-12-31” értékűre a dátumot.
    * A jelentési időszak kezdő és záró dátumának beállítása, amelyek tartalmazzák a meglévő űrlaptranzakciókat.  
24. Az Irány mezőben válassza az „Érkezések” lehetőséget.
25. Válassza az Igen lehetőséget a Fájl létrehozása mezőben.
26. Kattintson az OK gombra.
    * Tekintse át a létrehozott kimenetet, a végén az összesítő sorokkal.  
27. Kattintson az Új lehetőségre.
28. A listában jelölje meg a kiválasztott sort.
29. Az Irány mezőben válassza a „Feladások” lehetőséget.
30. Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.
31. Az Árucikk mezőben adjon meg vagy válasszon ki egy értéket.
32. A Tömeget állítsa a „10” értékre.
33. A Számlaösszeget állítsa a „10000” értékre.
34. A Statisztikai összeget állítsa a „10000” értékre.
35. Kattintson a Kimenet lehetőségre.
36. Kattintson a Jelentésre.
37. Az Irány mezőben válassza a „Feladások” lehetőséget.
38. Kattintson az OK gombra.
    * Tekintse át a létrehozott kimenetet, a végén az összesítő sorokkal. Fontos megjegyezni, hogy megváltozott az első futtatással összehasonlítva.  

## <a name="run-this-configuration-in-debug-mode-to-review-the-collected-counting--summing-data"></a>A konfiguráció futtatása hibakeresési módban az összegyűjtött számlálási és összegzési adatok felülvizsgálatához
1. Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.
2. A fastruktúrában bontsa ki az „Instrastat modell” elemet.
3. A fastruktúrában bontsa ki a következőt: „Intrastat modell\Intrastat (DE)”.
4. A fastruktúrában válassza ki a következőt: „Intrastat modell\Intrastat (DE) \Intrastat (DE) számolással és összegzéssel”.
5. Kattintson a Konfigurációk lehetőségre a Művelet Panelen.
6. Kattintson a Felhasználói paraméterek lehetőségre.
7. Válassza az Igen lehetőséget a Futtatás hibakeresési módban mezőben.
8. Kattintson az OK gombra.
9. Zárja be a lapot.
10. Ugorjon az Adó > Nyilatkozatok > Külkereskedelem > Intrastat pontra.
11. Kattintson a Kimenet lehetőségre.
12. Kattintson a Jelentésre.
13. Kattintson az OK gombra.
14. Zárja be a lapot.
15. Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.
16. A fastruktúrában bontsa ki az „Instrastat modell” elemet.
17. A fastruktúrában bontsa ki a következőt: „Intrastat modell\Intrastat (DE)”.
18. A fastruktúrában válassza ki a következőt: „Intrastat modell\Intrastat (DE) \Intrastat (DE) számolással és összegzéssel”.
19. Kattintson a Hibakeresési naplók lehetőségre.
    * Fontos megjegyezni, hogy hibakeresési naplóbejegyzés lett létrehozva a kijelölt konfiguráció végrehajtási folyamatához.  
20. Kattintson a Csatolás elemre.
21. Kattintson a Megnyitás gombra.
    * Tekintse át a létrehozott XML-fájlt, amely tartalmazza a kijelölt konfiguráció végrehajtása során gyűjtött számlálási és összegzési adatokat.  


