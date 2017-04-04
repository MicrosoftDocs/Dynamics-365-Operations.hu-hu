---
title: "Folytonos program beállítása egy hívásközpontnak"
description: "Ez a cikk bemutatja, hogyan állíthat be folytonos programot egy hívásközpontban."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16081
ms.assetid: 426a9be7-a931-4780-b372-e06f6083dd60
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: e32961f2a0e0e41715d98075cbc5777d256eb187
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-a-continuity-program-for-a-call-center"></a>Folytonos program beállítása egy hívásközpontnak

Ez a cikk bemutatja, hogyan állíthat be folytonos programot egy hívásközpontban.

A folytonos program (más néven ismétlődő rendelés) keretében a vevők egy előre definiált ütemezés alapján rendszeres szállítmányokat kapnak. Az egyes szállítmányok különböző termékeket is tartalmazhatnak, mint például „A hónap bestsellere” klubban, más esetekben pedig ugyanazt a terméket küldik. A folytonossági program beállításához a következő feladatokat kell elvégeznie.

1.  A folytonos paraméterek beállítása a **Hívásközponti paraméterek** oldalon.
2.  Hozzon létre egy folytonossági programot, amelyben megadja az olyan részleteket, mint például a fizetési ütemezés, a szállítmányok ütemezése, és hogy előzetes számlázást használ-e. Emellett meg kell adnia a folytonos programban használt termékek listáját is. Minden egyes terméket kap egy eseményt azonosító számot egymás után, 1-gyel kezdődően. Az esemény azonosítók küldött termékek sorrendjének meghatározásához.
    -   Ha a vevő minden szállítmányba egy másik terméket kap, akkor a termékeket az eseményazonosító alapján felállított sorrendben küldik ki, az aktuális eseménnyel kezdve.
    -   Ha a vevő minden szállítmányban ugyanazt a terméket kapja, akkor a list csak egy terméket tartalmaz, egyetlen eseményazonosítóval. Ugyanaz az esemény ismétlődik meg minden alkalommal. Megadhatja, hogy hányszor szeretné ismételni az egyes eseményeket.

3.  2. feladat a folyamatos programnak szülő termék létrehozása. Ha ezt a terméket ad hozzá egy értékesítési rendelés, a **folyamatos** lap megnyitásakor. Ezek után ezen az oldalon hozhatja létre a tényleges folytonos megrendelést. A szülőtermék nem határozza meg, hogy a vevő milyen termékeket kap az egyes szállításokban.

A folytonos program beállítása után (amelyről a fenti részben olvashat), készen áll rá, hogy folytonos megrendelést hozzon létre egy vevő részére. Egyes esetekben a következő, kiegészítő karbantartási feladatokra is szükség lehet

-   **Frissítse a folytonosság aktuális eseményidőszakát** – Állítson be olyan kötegelt feladatot, amely értesíti a rendszert az aktuális eseményidőszakról.
-   **Folytonos gyermekrendelések létrehozása** – Hozzon létre gyermekrendeléseket a folytonossági szülőrendelésből.
-   **Folytonos fizetések feldolgozása** – Dolgozza fel a folytonos értékesítési rendelésekhez kapcsolódó fizetések számláit és értesítéseit.
-   **Folytonossági sorok meghosszabbítása** (szükség esetén) – Hosszabbítsa meg a folytonos esemény ismétlődéseinek számát. A szállítások ismétlődése túllépheti a hívásközponti paramétereknél a **Folytonos ismétlődés küszöbértéke** mezőben megadott limitet.
-   **Folytonossági frissítés elvégzése** (szükség szerint) – Szinkronizálja a módosításokat a folytonos program és a szülő folytonos értékesítési rendelések között.
-   **Folytonossági szülősorok és rendelések lezárása** – Zárja le a folytonos megrendeléseket.



