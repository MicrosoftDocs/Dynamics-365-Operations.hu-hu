--- 
title: "Eladási ár kiválasztási feltételeinek létrehozása"
description: "Ez az eljárás bemutatja, hogyan hozhat létre eladási ár kiválasztási feltételeket az attribútumalapú eladásiár-modellekhez."
author: YuyuScheller
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 59f6a4131f6a27c0089a1259e3f849f91a47bc87
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-sales-price-selection-criteria"></a>Eladási ár kiválasztási feltételeinek létrehozása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan hozhat létre eladási ár kiválasztási feltételeket az attribútumalapú eladásiár-modellekhez. Az eljáráshoz előfeltétel, hogy legyen legalább egy elérhető eladásiár-modell. Ebben a példában a hangszóró megoldás eladásiár-modelljének ármodelljét használjuk a USMF bemutatócég esetében. Ezt az eljárást általában a termékmenedzser használja.


## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a>Új feltétel hozzáadása a meglévő eladásiár-modellhez
1. Kattintson a Termékváltozat modelldefinícióra.
2. Kattintson a Termékkonfigurációs modellek lehetőségre.
3. A listában jelölje ki a hangszóró megoldás termékmodelljének a sorát, de ne kattintson a modell nevének hivatkozására.
4. A Művelet panelen kattintson a Modell elemre.
5. Kattintson az Ármodellfeltételek lehetőségre.
6. Kattintson az Új lehetőségre.
7. A Név mezőbe írja be a „10. vásárlócsoport” szöveget.
    * Az ármodellfeltétel nevének a használata segít azonosítani az alapul szolgáló kiválasztási feltételeket.  
8. Az Ármodell mezőben adjon meg vagy válasszon ki egy értéket.
9. A Rendeléstípus mezőben válassza ki az Értékesítési rendelés elemet.
    * A rendelés típusa határozza meg, hogy az adatbázis mely mezői állnak rendelkezésre a kiválasztási lekérdezéshez.  
10. Adja meg a dátumot az Érvényesség kezdete mezőben.
11. Az Érvényesség vége mezőben adjon meg egy dátumot.
12. Kattintson a Mentés gombra.

## <a name="create-the-query-for-the-selection-criteria"></a>A lekérdezés létrehozása a kiválasztási feltételekhez
1. Kattintson a Szerkesztés lehetőségre.
2. Válasszon ki vevőket a Tábla mezőben. 
3. A Mező mezőben válassza ki a Vevőcsoportot.
    * Ebben a példában egy bizonyos vevőcsoportot fogunk használni kiválasztási feltételnek.  
4. A Feltétel mezőben válassza ki a 10. vevőcsoportot. 
5. Kattintson az OK gombra.


