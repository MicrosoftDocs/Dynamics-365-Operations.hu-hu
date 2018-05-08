--- 
title: "Hívásközponti rendelések létrehozása"
description: "Ez az eljárás bemutatja, hogy hogyan kereshet ki egy vevőt, hozhat létre egy új rendelést és kereshet rá egy termére, továbbá hogyan szedhet be kifizetést a vevőtől."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: b2e986df1e089ef2a394d0e9d9236d39f2726c77
ms.contentlocale: hu-hu
ms.lasthandoff: 02/07/2018

---
# <a name="create-call-center-orders"></a>Hívásközponti rendelések létrehozása

[!include [task guide banner](../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogy hogyan kereshet ki egy vevőt, hozhat létre egy új rendelést és kereshet rá egy termére, továbbá hogyan szedhet be kifizetést a vevőtől. Az eljárás az USRT bemutatócéget használja, és az Értékesítési adminisztrátor számára készült. Előfeltételek: Az eljárást elvégző felhasználók a Hívásközpont felhasználóiként vannak beállítva, valamint a Gyári Féléves Katalógus közzététele megtörtént, legalább egy Forráskóddal.

1. Nyissa meg a következőt: Kiskereskedelem és kereskedelem > Vevők > Ügyfélszolgálat.
2. A Keresés szövegben mezőbe írja be a feltételeket a vevő kikereséséhez.
    * Ebben a példaeljárásban írja be: „karen”, majd nyomja meg a TAB billentyűt.  
3. Kattintson a Keresés gombra.
    * Mivel a bemutató adatsor csak egy „Karen” nevű vevőt tartalmaz, az ő kiválasztása automatikusan megtörténik.  
4. Kattintson az Új értékesítési rendelés gombra.
5. Bontsa ki vagy csukja össze az Értékesítési rendelés fejléce szakaszt.
6. Válassza ki a katalógus forráskódját.
    * Amennyiben nincsenek aktív Forráskódok, bezárhatja a Forrás mezőt, és kihagyhatja ezt a lépést.  
7. Kattintson az Új sor hozzáadása lehetőségre.
8. A Cikkszám mezőbe írja be írja be a cikk-keresési kifejezést.
    * Ebben a mintaeljárásban írja be a következő cikkszám-részletet: „8111”, majd nyomja meg a TAB billentyűt. Ekkor megjelenik a cikk-kereső ablak.  
9. Válassza ki az értékesítési rendeléshez hozzáadandó terméket.
10. Adja meg az értékesítési mennyiséget.
11. Kattintson az Új > lehetőségre.
12. Kattintson a Befejezés gombra a vevői fizetés rögzítéséhez.
13. Kattintson a Hozzáadás gombra.
    * A Hivatkozás hozzáadása a Kifizetések lapon található. Bontsa ki a Kifizetések lapot, ha össze van csukva.  
14. Válassza ki a fizetési módot.
    * Ebben az eljárásban válassza ki a készpénzfizetési módszert.  
15. Zárja be a lapot.
16. Írja be az összeget.
    * Ennél az eljárásnál írjon be egy olyan összeget, amely megegyezik a rendelési egyenleggel. Ez az Értékesítési rendelés összesítése oldalon látható, az összeg mezőtől balra. Ez lehetővé teszi, hogy teljesen kifizetett állapotban befejezze a rendelést.  
17. Kattintson az OK gombra.
18. Kattintson a Küldés hivatkozásra.


