--- 
title: "Kifejezésmegszorítás hozzáadása a termékkonfigurációs modellhez"
description: "Ez az eljárás bemutatja, hogyan lehet hozzáadni egy új megszorítási kifejezést egy termékkonfigurációs modellhez."
author: YuyuScheller
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: b8286eba5c799789ebba9a501a5a0b06ccdaabb1
ms.contentlocale: hu-hu
ms.lasthandoff: 07/28/2017

---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a>Kifejezésmegszorítás hozzáadása a termékkonfigurációs modellhez

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan lehet hozzáadni egy új megszorítási kifejezést egy termékkonfigurációs modellhez. Azt mutatja, hogyan írható elő kötelezővé sarokvédelem alkalmazása a hangszórón, ha a felhasználó fém elülső rácsot választott. Az eljárás a Felső kategóriás hangszóró összetevőt használja az USMF bemutatócégben.


## <a name="create-an-expression-constraint"></a>Kifejezésmegszorítás szerkesztője
1. Kattintson a Termékváltozat modelldefinícióra.
2. Kattintson a Termékkonfigurációs modellek lehetőségre.
3. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Ez a példa a felső kategóriás hangszóró modellt használja.  
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
5. Bontsa ki Megszorítások szakaszt.
6. Kattintson a Hozzáadás gombra.
7. Kattintson a Létrehozás lehetőségre.
8. Írjon be egy értéket a Név mezőbe.

## <a name="enter-expression"></a>Kifejezés megadása
1. Kattintson a Kifejezés szerkesztése lehetőségre.
    * Ha a feladatrögzítésben feloldja a felhasználói felületet ebben a fázisban, akkor az IntelliSense és a szimbólumlista segítségével felépítheti a megszorítási kifejezést.  
2. A ConstraintBody mezőben írja be „Implies [FrontGrill =="Metal", CornerProtection]”.
    * Ez a kifejezéslogika a következőt állítja: Ha az előlapi rács fém, akkor ki kell választani a sarokvédő lehetőséget.  
3. Kattintson az Érvényesítés gombra.
    * Az érvényesítési funkció ellenőrzi a megszorítási kifejezést, és szintaktikai hibákat keres.  
4. Kattintson a Bezárás gombra.
5. Kattintson az OK gombra.


