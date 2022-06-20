---
title: Lízingkönyvek beállítása
description: Ez a témakör a bérleti könyvekben karbantartott információkat ismerteti. A lízingkönyvek tartalmazzák azokat a könyvelési irányelveket, amelyek meghatározzák, hogyan számolja el a lízinget a rendszerben.
author: moaamer
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseBookMaster
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ee8cb3c827d590a5eb91121fe4510fbc56c13d9a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903218"
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
    | Lízingmegállapodás                       | Válassza ki a lízingszerződés kezdő dátumát:<ul><li><b>Nincs</b> – a lízing kezdő dátuma legyen a kezdő dátum.</li><li><b>Teljes hónap</b> – a kezdési dátum annak a hónapnak az első napja, amelybe a lízing kezdő dátuma esik.</li></ul><p>Ha a <b>Nincs</b> lehetőséget választja, akkor felmerül a kockázat, hogy a kötelezettségamortizációs és az eszköz értékcsökkenési ütemezései a hónap közepén végzik az elhatárolást és a költségek feladását, nem pedig a hónap végén. A <b>Teljes hónap</b> kiválasztásával biztosíthatja, hogy a rendszer a hónap első napján elszámolja a lízinget, és az egész hónapra vonatkozó költséget a hónap utolsó napján határolja el és adja fel.</p><p><strong>Megjegyzés:</strong> A lízingelési konvenciókkal kapcsolatos funkciót be kell kapcsolni a Funkciókezelés segítségével. A <b>Funkciókezelés</b> munkaterületen keresse meg és válassza ki az <b>Eszközkezelési lízingelési konvenciók</b> funkciót, majd válassza ki az <b>Engedélyezés most</b> lehetőséget.</p> |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
