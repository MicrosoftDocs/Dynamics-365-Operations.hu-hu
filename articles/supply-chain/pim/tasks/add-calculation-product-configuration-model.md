---
title: Kalkuláció hozzáadása termékkonfigurációs modellhez
description: Ez az eljárás bemutatja, hogyan lehet hozzáadni egy új számítást egy termékkonfigurációs modellhez.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d201061ff47203f09f96dc08ff6fc8ac437a6f9e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570657"
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]