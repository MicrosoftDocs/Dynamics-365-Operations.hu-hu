---
title: Termelési rendelés kiadása
description: Ez az eljárás a termelési rendelések kiadását mutatja be.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmRelease, SrsReportViewerForm, ProdSetupRelease
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: beef850e7e58fb58db545c0be5990b52619070d3
ms.sourcegitcommit: 175f9394021322c685c5b37317c2f649c81a731a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "3826574"
---
# <a name="release-a-production-order"></a>Termelési rendelés kiadása

[!include [banner](../../includes/banner.md)]

Ez az eljárás a termelési rendelések kiadását mutatja be. Ez az eljárás az USMF bemutatócéget használja. Ez a negyedik eljárás abból a hétből, amely bemutatja a termelési rendelés életciklusát.

1. Ugrás a Gyártásvezérlés > Termelési rendelések > Minden termelési rendelésre.
    * A rácson belül válasszon ki egy Ütemezett állapotú termelési rendelést.  
2. A Művelet panelen kattintson a Termelési rendelés elemre.
3. Kattintson a Kiadás elemre.
    * Ezen a lapon tudja megerősíteni a termelési rendelések kiválasztott tartományának kiadását. Kattintson a Kijelölés gombra rendelések hozzáadásához.  
    * A Kiadási lépés azt a termelési rendelés, a termelési üzem részére történő kiadását jelzi annak érdekében, hogy az üzemi dolgozók jelentést tudjanak küldeni a termelési feladatok előrehaladásáról. A feladatok feldolgozása vonatkozó lényeges információkat tartalmazó termelési papírokat tud kiállítani. A rendszer nyersanyag kitárolással kapcsolatos raktári munkát generál a raktározási folyamatra előkészített cikkeket kapcsán.  
4. Kattintson az Általános fülre.
    * Válassza ki, hogy melyik termelési jelentések kerüljenek kinyomtatásra. A Feladatkártya-jelentés minden ütemezett feladat kapcsán kinyomtat egy oldalt, valamint előírja a termelési rendelés feladat szinten történő ütemezését. A jelentés az ütemezett kezdési és befejezési időponttal, az előállítandó mennyiséggel és a feladatot feldolgozó erőforrással kapcsolatos információkat tartalmazza. Az Útvonal-feladat jelentése ugyanezeket az információkat gyűjti össze egyazon oldalon, de nem nyomtat önálló oldalt minden egyes feladat kapcsán. Az Útvonalkártya-jelentés csak a műveletek jeleníti meg, a feladatokat azonban nem. Ez a jelentés tehát nem igényel feladatütemezést, hanem abban az esetben használható, ha a termelési rendelések ütemezése műveleti szinten történik.  
5. Jelölje be az Útvonalkártya nyomtatása jelölőnégyzetet.
6. Kattintson az OK gombra.
7. Zárja be a lapot.

