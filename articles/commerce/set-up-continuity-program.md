---
title: Folytonossági programok beállítása hívásközpontok számára
description: Ez a cikk bemutatja, hogyan állíthat be folytonos programot egy hívásközpontban.
author: josaw1
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 16081
ms.assetid: 426a9be7-a931-4780-b372-e06f6083dd60
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 39c3e6d740bff2af27a2fba2ac4c406c01b43a87218fdc1dcfe094c147cd3de3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716150"
---
# <a name="set-up-continuity-programs-for-call-centers"></a>Folytonossági programok beállítása hívásközpontok számára

[!include [banner](includes/banner.md)]

Ez a cikk bemutatja, hogyan állíthat be folytonos programot egy hívásközpontban.

A folytonos program (más néven ismétlődő rendelés) keretében a vevők egy előre definiált ütemezés alapján rendszeres szállítmányokat kapnak. Az egyes szállítmányok különböző termékeket is tartalmazhatnak, mint például „A hónap bestsellere” klubban, más esetekben pedig ugyanazt a terméket küldik. A folytonossági program beállításához a következő feladatokat kell elvégeznie.

1. A folytonos paraméterek beállítása a **Hívásközponti paraméterek** oldalon.
2. Hozzon létre egy folytonossági programot, amelyben megadja az olyan részleteket, mint például a fizetési ütemezés, a szállítmányok ütemezése, és hogy előzetes számlázást használ-e. Emellett meg kell adnia a folytonos programban használt termékek listáját is. Minden termék eseményazonosító számot kap, amely az egyesnél kezdődően rendelésenként nő. Az eseményazonosító a termékek eljuttatásának sorrendjét határozza meg.

    - Ha a vevő minden szállítmányba egy másik terméket kap, akkor a termékeket az eseményazonosító alapján felállított sorrendben küldik ki, az aktuális eseménnyel kezdve.
    - Ha a vevő minden szállítmányban ugyanazt a terméket kapja, akkor a list csak egy terméket tartalmaz, egyetlen eseményazonosítóval. Ugyanaz az esemény ismétlődik meg minden alkalommal. Megadhatja, hogy hányszor szeretné ismételni az egyes eseményeket.

3. Hozzon létre egy szülő terméket, amely a 2. feladatban létrehozott folytonossági programot jelöli ki. Ha ezt a terméket hozzáadja egy értékesítési rendeléshez, megnyílik a **Folytonosság** oldal. Ezek után ezen az oldalon hozhatja létre a tényleges folytonos megrendelést. A szülőtermék nem határozza meg, hogy a vevő milyen termékeket kap az egyes szállításokban.

A folytonos program beállítása után (amelyről a fenti részben olvashat), készen áll rá, hogy folytonos megrendelést hozzon létre egy vevő részére. Egyes esetekben a következő, kiegészítő karbantartási feladatokra is szükség lehet

- **Frissítse a folytonosság aktuális eseményidőszakát** – Állítson be olyan kötegelt feladatot, amely értesíti a rendszert az aktuális eseményidőszakról.
- **Folytonos gyermekrendelések létrehozása** – Hozzon létre gyermekrendeléseket a folytonossági szülőrendelésből.
- **Folytonos fizetések feldolgozása** – Dolgozza fel a folytonos értékesítési rendelésekhez kapcsolódó fizetések számláit és értesítéseit.
- **Folytonossági sorok meghosszabbítása** (szükség esetén) – Hosszabbítsa meg a folytonos esemény ismétlődéseinek számát. A szállítások ismétlődése túllépheti a hívásközponti paramétereknél a **Folytonos ismétlődés küszöbértéke** mezőben megadott limitet.
- **Folytonossági frissítés elvégzése** (szükség szerint) – Szinkronizálja a módosításokat a folytonos program és a szülő folytonos értékesítési rendelések között.
- **Folytonossági szülősorok és rendelések lezárása** – Zárja le a folytonos megrendeléseket.


[!INCLUDE[footer-include](../includes/footer-banner.md)]