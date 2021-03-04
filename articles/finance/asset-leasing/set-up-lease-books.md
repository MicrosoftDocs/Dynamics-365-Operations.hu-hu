---
title: Lízingkönyvek beállítása
description: Ez a témakör a lízingkönyvekben található információkat ismerteti. A lízingkönyvek tartalmazzák azokat a könyvelési irányelveket, amelyek meghatározzák, hogyan számolja el a lízinget a rendszerben.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 28518341544327f1983e563b719b0f455b6e1c43
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/28/2020
ms.locfileid: "4444176"
---
# <a name="set-up-lease-books"></a>Lízingkönyvek beállítása

[!include [banner](../includes/banner.md)]

A lízingkönyvek tartalmazzák azokat a könyvelési irányelveket, amelyek meghatározzák, hogyan számolja el a lízinget a rendszerben. A készpénzalapú elszámolás mellett az eszközlízing a következő standardokat támogatja:

- Általánosan elfogadott könyvelési elvek az Egyesült Államokban (US GAAP)
- Könyvelési standardok kodifikációs témaköre 842 (ASC 842)
- ASC 840
- Nemzetközi pénzügyi jelentési standard 16 (IFRS 16)
- Nemzetközi könyvelési standard 17 (IAS 17)

Lízingkönyv létrehozásához kövesse az alábbi lépéseket.

1. Nyissa meg az **Eszközlízing \> Beállítás \> Lízingkönyvek** lehetőséget.
2. Könyv hozzáadásához válassza az **Új** lehetőséget.
3. Állítsa be a következő mezőket.

    | Név                                     | Leírás |
    |------------------------------------------|-------------|
    | Feladási réteg                            | Válassza ki a használni kívánt feladási réteget. Minden könyv, amely egy lízinghez van csatolva, egy adott feladási réteghez van beállítva. Minden feladási rétegnek különböző feladási céljai vannak. |
    | Lízingtípus                               | Válassza ki, hogy a lízinget automatikusan kell-e besorolni, vagy előre meg kell-e határozni pénzügyi vagy operatív lízingként. |
    | Könyvelési keretrendszer                     | Válassza ki a könyvhöz társított keretrendszert. |
    | Lízingfutamidő/hasznos élettartam beállítás          | A rendszer akkor minősíti a lízinget pénzügyi lízingnek, ha a lízingtípust **Automatikusra** állították, és ha az eszköz lízingfutamideje az eszköz hasznos élettartamán túl nagyobb vagy egyenlő az ebben a mezőben megadott százalékkal.  |
    | Jelenérték / Eszköz valós értékének beállítása   | Adjon meg egy egész számot a lízing típusát meghatározó küszöbérték meghatározásához. Ha a jövőbeli minimális lízingfizetések jelenértéke nagyobb, mint a könyv beállításából származó felhasználó által meghatározott érték, és ha a könyv lízingbesorolása automatikus, a rendszer a lízinget pénzügyi lízingként sorolja be. |
    | Rövid távú küszöbérték                     | Adja meg a rövid távú lízingek küszöbértékként használandó hónapok számát. Ha a lízing időtartama kisebb vagy egyenlő az itt megadott hónapok számával, a rendszer a lízinget rövid távú lízingként osztályozza, és a halasztott bérleti díjat kell alkalmazni. |
    | Alacsony értékű küszöb                      | Adja meg az alacsony értékű lízingek küszöbértékeként használandó összeget. Ha az eszköz valós értéke kisebb vagy egyenlő az itt megadott értékkel, a rendszer a lízinget alacsony értékű lízingként osztályozza, és a halasztott bérleti díjat kell alkalmazni. |
    | Fizetés szállítónak                            | Állítsa ezt a beállítást **Igen** értékre, ha lehetővé szeretné tenni a lízingkifizetések számlaként történő feladását az egyes lízingeken megadott szállítói számlára. A lízingkifizetés feladásakor a szállítói számla jóváírásra kerül. Ha ez a beállítás **Nem** értékű, akkor a **Lízing fizetési** feladási típushoz a **Lízing feladási paraméterek** lapon megadott számla kerül jóváírásra. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]