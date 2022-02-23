---
title: Kalkuláció hozzáadása termékkonfigurációs modellhez
description: Ez az eljárás bemutatja, hogyan lehet hozzáadni egy új számítást egy termékkonfigurációs modellhez.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e703c6d505f1e2e77f454732301de7a6c130c58a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429533"
---
# <a name="add-a-calculation-to-a-product-configuration-model"></a>Kalkuláció hozzáadása termékkonfigurációs modellhez

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan lehet hozzáadni egy új számítást egy termékkonfigurációs modellhez. Azt mutatja, hogyan lehet létrehozni egy logikai kifejezést az „if” operátorral, hogy a fehér hangszórók magassága 10 az egyéb felületekkel rendelkezőké pedig 15 legyen. Az eljárás a Felső kategóriás hangszóró összetevőt használja az USMF bemutatócégben.


## <a name="add-a-calculation"></a>Számítás hozzáadása

## <a name="create-calculation-expression"></a>Számításkifejezés létrehozása
1. Kattintson a Kifejezés szerkesztése lehetőségre.
2. A ConstraintBody mezőben írja be, hogy „If[CabinetFinish =="White", 10, 15]”.
3. Kattintson az Érvényesítés gombra.
4. Kattintson a Bezárás gombra.
5. Kattintson az OK gombra.

