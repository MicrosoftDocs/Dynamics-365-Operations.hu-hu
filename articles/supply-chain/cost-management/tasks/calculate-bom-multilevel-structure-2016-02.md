---
title: Anyagjegyzék-számítás elvégzése több szintű struktúra használatával (2016. február)
description: Ez az eljárás bemutatja, hogyan lehet kiszámítani egy késztermék költségét többszintű alábontással, amelynek az alapja a költségszámítási táblázat.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventItemPrice, BOMCalcDialog, BOMCalcTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fcc1248d64145c10f1c67bfac49c053e99dc1598
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "323364"
---
# <a name="calculate-a-bom-by-using-a-multilevel-structure-february-2016"></a>Anyagjegyzék-számítás elvégzése több szintű struktúra használatával (2016. február)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan lehet kiszámítani egy késztermék költségét többszintű alábontással, amelynek az alapja a költségszámítási táblázat. Ez az anyagjegyzék-számítási sorozat hetedik feladata. A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.

1. Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Termék BOM_1 kiválasztása.  
3. A Művelet panelen kattintson a Költségkezelés elemre.
4. Kattintson a Cikk ára elemre.
5. Kattintson a Cikk-költség kiszámítása lehetőségre.
    * Előfordulhat, hogy a három pont (...) elemre kell kattintania a lehetőség megtekintéséhez a főmenüben.  
6. A Költségszámítási verzió mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza a 20-as költségszámítási verziót, mivel ez egy tervezett költségtípus, és az alábontási mód többszintű.   A többszintű alábontási módot a tervezett költségekhez és szimulációkhoz használjuk. Az elszámolóárhoz nem használt.  
7. Kattintson az OK gombra.
8. Kattintson a Számítás részleteinek megjelenítése elemre.
    * Előfordulhat, hogy a három pont (...) elemre kell kattintania a lehetőség megtekintéséhez a főmenüben.  Ebben az esetben figyelje meg, hogy BOM_2 kiszámításánál figyelembe vesszük a nyersanyagot, a feldolgozást és a járulékos költséget összesen 29,40 értékben ahelyett a 10-es elszámolóár helyett, amelyet a sorozat első feladat-útmutatójában aktiváltunk.  
9. Kattintson a Költségszámítási táblázat fülre.
    * A Költségszámítás lapfülre lépve a költségcsoportonkénti összegek különböznek az előző feladat-útmutatóban elvégzett számítástól.  
10. A Szint mezőben válassza a következőt: „Többszörös”.
    * Többszörös kiválasztáskor a költségek besorolásának alapja a BOM_2, ahol a 10 forrása az M1 költségcsoport (ITEM_C), a 15,60 pedig a gyártásából származik, ahol a költségcsoport az L2. A közvetett költségek is eltérőek lehetnek.  
11. Zárja be a lapot.
12. Zárja be a lapot.

