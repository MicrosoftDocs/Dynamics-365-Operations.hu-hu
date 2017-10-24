--- 
title: "Új kereskedelmi szerződés létrehozása"
description: "Ez az eljárás bemutatja, hogyan hozhat létre egy kereskedelmi megállapodást, amelyben regisztrálhat egy új termékeladási árat, amelyben egy adott vevővel megállapodott."
author: omulvad
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1eb7a945243387f85ec5f38cc3b969d8d030ff25
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-new-trade-agreement"></a>Új kereskedelmi szerződés létrehozása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan hozhat létre egy kereskedelmi megállapodást, amelyben regisztrálhat egy új termékeladási árat, amelyben egy adott vevővel megállapodott. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja. Saját adatok használatakor az útmutató használatának megkezdése előtt győződjön meg róla, hogy a Kereskedelmi megállapodások napló neve létezik, ahol az Alapértelmezett viszony az "Ár (eladási)".


## <a name="create-and-post-a-new-trade-agreement-journal"></a>Hozzon létre és tegyen közzé egy új kereskedelmi megállapodási naplót
1. Ugorjon az Értékesítés és marketing >; Árak és engedmények > Kereskedelmi megállapodási naplók elemre.
2. Kattintson az Új lehetőségre.
3. A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. A kívánt rekord megkeresése és kijelölése a listán
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. Kattintson a Sorok pontra.
7. A Fiókkód mezőben válassza ki a Tábla lehetőséget.
    * Ebben a példában egy konkrét vevő árát frissíti, ami azt jelenti, hogy meg kell adnia egy Táblát. Ha a termék listaárát frissítené, az Összeset kellene kiválasztania, úgy, hogy az új ár legyen érvényes az összes vevőre. Ha különböző árakat különböztet meg az egyes vevői szegmensek között, akkor válassza a Csoportot. A Csoport kiválasztásához be kell állítania a Vevői árcsoportokat.  
8. A Fiókválasztás mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
9. Keresse meg és jelölje ki a kívánt rekordot a listán.
10. A Cikk-kód mezőben válassza ki a Tábla lehetőséget.
    * Ha "Ár (eladási)" típusú kereskedelmi megállapodást ír be, akkor csak a "Tábla" elemet válassza ki a Cikk-kód mezőben. Ennek oka az, hogy az ár abszolút érték, és nem lehet azonos egy termékcsoport összes termékére.  
11. A Cikk-viszony mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
12. A listában válassza ki a szerződésben szerepeltetni kívánt terméket.
    * Jegyezze meg, hogy mely termék van kijelölve.  
13. A listában kattintson a kijelölt sorban lévő hivatkozásra.
14. Adja meg a minimum mennyiséget a Kezdőérték mezőben.
    * Ha a vevőnek egy minimális mennyiséget kell rendelnie, mielőtt új ár igényelhetne, akkor meg kell adnia a mennyiséget itt.  
    * Adjon meg egy értéket a Címzett mezőben, hogy megadja a maximális mennyiséget, amely felett a megállapodási ár nem lesz érvényes. Ha több mennyiségi szünet alapján ajánl árakat és engedményeket, adja meg az egyes mennyiségi határértékeket egy minimális és maximális mennyiségként a Kezdő és a Befejező mezőkben.  
15. Az Összeg devizában mezőben adjon meg egy árat.
16. A Kezdő dátum mezőben adjon meg egy dátumot, amelytől kezdve érvényes lesz a szerződés.
17. Kattintson a Mentés gombra.
18. Kattintson az Érvényesítés gombra.
19. Kattintson a kijelölt sorok érvényesítése pontra.
20. Kattintson az OK gombra.
21. Kattintson a Feladás lehetőségre.
22. Kattintson az OK gombra.

## <a name="view-trade-agreements-for-a-product"></a>Termékkel kapcsolatos kereskedelmi megállapodások megtekintése
1. Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.
2. A listában keresse meg és válassza ki a terméket, amelynek éppen frissítette az árát.
3. A Művelet panelen kattintson az Értékesítés elemre.
4. Kattintson a Kereskedelmi megállapodások megtekintése pontra.
    * Tekintse át az imént létrehozott ármegállapodás részletes adatait.    
5. Zárja be a lapot.


