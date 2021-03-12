---
title: Kifejezésmegszorítás hozzáadása a termékkonfigurációs modellhez
description: Ez az eljárás bemutatja, hogyan lehet hozzáadni egy új megszorítási kifejezést egy termékkonfigurációs modellhez.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 411e20bd8631b70df981c5785f502693d5ba3705
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4987129"
---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a>Kifejezésmegszorítás hozzáadása a termékkonfigurációs modellhez

[!include [banner](../../includes/banner.md)]

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

