--- 
title: "Kalkuláció hozzáadása termékkonfigurációs modellhez"
description: "Ez az eljárás bemutatja, hogyan lehet hozzáadni egy új számítást egy termékkonfigurációs modellhez."
author: ShylaThompson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2db8fb922b085a7f118822ef4fd974ac338f4d99
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="add-a-calculation-to-a-product-configuration-model"></a>Kalkuláció hozzáadása termékkonfigurációs modellhez

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan lehet hozzáadni egy új számítást egy termékkonfigurációs modellhez. Azt mutatja, hogyan lehet létrehozni egy logikai kifejezést az „if” operátorral, hogy a fehér hangszórók magassága 10 az egyéb felületekkel rendelkezőké pedig 15 legyen. Az eljárás a Felső kategóriás hangszóró összetevőt használja az USMF bemutatócégben.


## <a name="add-a-calculation"></a>Számítás hozzáadása

## <a name="create-calculation-expression"></a>Számításkifejezés létrehozása
1. Kattintson a Kifejezés szerkesztése lehetőségre.
2. A ConstraintBody mezőben írja be, hogy „If[CabinetFinish =="White", 10, 15]”.
3. Kattintson az Érvényesítés gombra.
4. Kattintson a Bezárás gombra.
5. Kattintson az OK gombra.


