---
title: A kiskereskedelmi kimutatásokat befolyásoló kiskereskedelmi paraméterek konfigurálása
description: Ez a cikk a Kiskereskedelmi kimutatások létrehozásának és feladásának módját befolyásoló Kiskereskedelmi paraméterek konfigurációit mutatja be.
author: josaw1
manager: AnnBe
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b9a0386a4d61395903e82d988244dd131c1febaf
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867271"
---
# <a name="configure-retail-parameters-that-affect-retail-statements"></a>A kiskereskedelmi kimutatásokat befolyásoló kiskereskedelmi paraméterek konfigurálása

[!include[task guide banner](../includes/task-guide-banner.md)]

Ez a cikk a Kiskereskedelmi kimutatások létrehozásának és feladásának módját befolyásoló Kiskereskedelmi paraméterek konfigurációit mutatja be. Ez az eljárás az USRT bemutatócéget használja.

1. A navigációs ablaktáblán lépjen a **Modulok > Kiskereskedelem és kereskedelem > Központ beállítás > Paraméterek > Kiskereskedelmi paraméterek** részhez.
2. Lépjen a **Feladás** lapra.
    - Ha kifejezetten az időszaki engedmények összegét szeretné feladni, akkor válassza az **Igen** lehetőséget.  
    - Válassza a **Normál** lehetőséget az alapértelmezett számlák használatához, vagy az **Időszakos** lehetőséget, ha Ön szeretné megadni az egyes időszakos engedményekhez használandó számlákat.  
      - Válassza az **Összegzés** lehetőséget, ha szeretné, hogy a rendszer minden lehetséges alkalommal összesítse a készlet sorait.  
      - Válassza az **Igen** lehetőséget, ha szeretné, hogy a rendszer automatikusan rendezze a számlákat és a kifizetéseket a Kimutatásfeladási folyamat során.  
      - Válassza az **Igen** lehetőséget, ha összesíteni szeretné a széfes befizetéses tranzakciókat.  
      - Válassza az **Igen** lehetőséget, ha összesíteni szeretné a banki fizetőeszközökkel végrehajtott tranzakciókat.  
      - Válassza az **Igen** lehetőséget, ha a kimutatásfeladáshoz be szeretné kapcsolni az összesítést.  
      - Válassza az **Igen** lehetőséget, ha szeretne párhuzamos megrendeléseket létrehozni és feldolgozni a kimutatás feladása során.  
      - Adja meg a kötegelt feladatonként feldolgozandó megrendelések maximális számát.  
3. Válassza a **Mentés** lehetőséget.

