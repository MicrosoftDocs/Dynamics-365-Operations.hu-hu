---
title: Kifejezésmegszorítás hozzáadása a termékkonfigurációs modellhez
description: Ez az eljárás bemutatja, hogyan lehet hozzáadni egy új megszorítási kifejezést egy termékkonfigurációs modellhez.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9cd5475e48cbcd8dcee6b228297f58e364ac503d
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920881"
---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a>Kifejezésmegszorítás hozzáadása a termékkonfigurációs modellhez

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan lehet hozzáadni egy új megszorítási kifejezést egy termékkonfigurációs modellhez. Azt mutatja, hogyan írható elő kötelezővé sarokvédelem alkalmazása a hangszórón, ha a felhasználó fém elülső rácsot választott. Az eljárás a Felső kategóriás hangszóró összetevőt használja az USMF bemutatócégben.

## <a name="create-an-expression-constraint"></a>Kifejezésmegszorítás szerkesztője

1. Lépjen a **Termékinformáció-kezelés \> Termékek \> Termékkonfigurációs modellek** elemre.
3. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Ez a példa a felső kategóriás hangszóró modellt használja.  
4. A listában válassza ki a kiválasztott sorból a hivatkozást.
5. Bontsa ki **Megszorítások** szakaszt.
6. Válassza a **Hozzáadás** lehetőséget.
7. Válassza a **Létrehozása** lehetőséget.
8. Írjon be egy értéket a **Név** mezőbe.

## <a name="enter-expression"></a>Kifejezés megadása

1. Válassza a **Kifejezés szerkesztése** lehetőséget.
    * Ha a feladatrögzítésben feloldja a felhasználói felületet ebben a fázisban, akkor az IntelliSense és a szimbólumlista segítségével felépítheti a megszorítási kifejezést.  
2. A **ConstraintBody** mezőben írja be „Implies [FrontGrill =="Metal", CornerProtection]”.
    * Ez a kifejezéslogika a következőt állítja: Ha az előlapi rács fém, akkor ki kell választani a sarokvédő lehetőséget.  
3. A **Validálás** kiválasztása.
    * Az érvényesítési funkció ellenőrzi a megszorítási kifejezést, és szintaktikai hibákat keres.  
4. Válassza **Bezárás** lehetőséget.
5. Válassza ki az **OK** lehetőséget.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]