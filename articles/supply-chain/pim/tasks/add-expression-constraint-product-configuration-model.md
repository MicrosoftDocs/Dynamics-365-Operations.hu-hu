---
title: Kifejezésmegszorítás hozzáadása a termékkonfigurációs modellhez
description: Ez az eljárás bemutatja, hogyan lehet hozzáadni egy új megszorítási kifejezést egy termékkonfigurációs modellhez.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f67d912b3349d4b5dd861b97533a7722a2b02fa4
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845137"
---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a>Kifejezésmegszorítás hozzáadása a termékkonfigurációs modellhez

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

