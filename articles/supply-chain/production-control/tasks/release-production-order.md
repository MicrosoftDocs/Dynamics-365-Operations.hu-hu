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
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 82a8316014d28f1c31343a2e54038fc93623cd70
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966256"
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]