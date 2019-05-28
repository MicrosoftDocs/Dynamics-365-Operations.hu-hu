---
title: " Alapár- és kereskedelmi megállapodások"
description: Ez az eljárás bemutatja csatornaspecifikus eladási árra vonatkozó kereskedelmi megállapodások létrehozását.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PriceDiscGroup, RetailStoreTable, RetailChannelPriceGroup, EcoResProductDetailsExtended, PriceDiscAdmTable, PriceDiscAdm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4830ac553318cfbb3cb74395d1662e74dff75290
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1548531"
---
# <a name="base-price-and-trade-agreements"></a> Alapár- és kereskedelmi megállapodások

[!include[task guide banner](../includes/task-guide-banner.md)]

Ez az eljárás bemutatja csatornaspecifikus eladási árra vonatkozó kereskedelmi megállapodások létrehozását. Ez az eljárás az USRT bemutatócéget használja.

1. Nyissa meg a következőt: Kiskereskedelem és kereskedelem > Árképzés és engedmények > Árcsoportok > Minden árcsoport.
    * Az árcsoportok megadják, hogyan történjen a kereskedelmi megállapodások társítása az egyes csatornákhoz. Ha árcsoportokat használunk kereskedelmi megállapodások csatornához való társítására, lehetővé válik a csatornaspecifikus árazás.  
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket az Árcsoportok mezőbe.
4. Írjon be egy értéket a Név mezőbe.
5. Kattintson a Mentés gombra.
6. Zárja be a lapot.
7. Nyissa meg a következőt: Kiskereskedelem és kereskedelem > Csatornák > Kiskereskedelmi áruházak > Minden kiskereskedelmi üzlet.
8. Válassza ki a listából a következőt: „New York”.
9. A Művelet panelen kattintson az Üzlet elemre.
10. Kattintson az Árcsoportok lehetőségre.
11. Kattintson az Új lehetőségre.
12. Az Árcsoportok mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
13. Keresse meg és jelölje ki a kívánt rekordot a listán.
14. Kattintson a Mentés gombra.
15. Zárja be a lapot.
16. Zárja be a lapot.
17. Nyissa meg a következőt: Kiskereskedelem és kereskedelem > Termékek és kategóriák > Felszabadított termékek kategóriák szerint.
18. A listában kattintson a kijelölt sorban lévő hivatkozásra.
19. Kattintson a Szerkesztés lehetőségre.
20. Váltsa át az Eladás szakasz bővítését.
21. Adjon meg egy számot az Ár mezőben.
    * Ez az ár akkor használatos, ha nem található megfelelő kereskedelmi megállapodás.  
22. Kattintson a Mentés gombra.
23. A Művelet panelen kattintson az Értékesítés elemre.
24. Kattintson a Kereskedelmi megállapodások létrehozása lehetőségre.
25. Kattintson az Új elemre.
26. A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
27. A listában válassza ki a következőt: „Kiskereskedelem”.
    * A bemutató adatsorban a „Kiskereskedelem” naplónév a következő alapértelmezett objektumkapcsolattal rendelkezik: „Ár (eladási)”. Ez azt jelenti, hogy minden létrehozott új sor alapértelmezés szerint eladási árra vonatkozó kereskedelmi megállapodás lesz.  
28. Kattintson a Sorok pontra.
29. A Számlakód mezőben válassza ki a következőt: „Csoport”.
30. A Fiókválasztás mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
31. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Ez befejezi a Csatorna és a Kereskedelmi megállapodás közötti, Árcsoport által közvetített hivatkozást.  
32. Írjon be egy értéket a Cikk-kapcsolat mezőbe.
33. Az Összeg devizában mezőben adjon meg egy számot.
34. Jelölje be a Következő keresése jelölőnégyzetet, vagy törölje a jelölést.
    * Amennyiben a Következő keresése beállításnál az „Igen” van kiválasztva, az árképzési motor folytatja alacsonyabb eladási árra vonatkozó, megfelelő kereskedelmi megállapodások keresését. Amennyiben a Következő keresése beállításnál a „Nem” van kiválasztva, az árképzési motor befejezi a keresést és a meglévő kereskedelmi megállapodást használja.  
35. Kattintson a Feladás lehetőségre.
36. Kattintson az OK gombra.
37. Zárja be a lapot.
38. A Művelet panelen kattintson az Értékesítés elemre.
39. Kattintson az Eladási ár lehetőségre.

