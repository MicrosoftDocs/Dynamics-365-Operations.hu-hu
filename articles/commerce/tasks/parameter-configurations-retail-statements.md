---
title: A kiskereskedelmi kimutatásokat befolyásoló paraméterek konfigurálása
description: Ez a cikk a kimutatások létrehozásának és feladásának módját befolyásoló Commerce paraméterek konfigurációit mutatja be.
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
ms.openlocfilehash: 7892a216d836ebcc297a5b7eb87bc996dd9b91bf
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140835"
---
# <a name="configure-parameters-that-affect-retail-statements"></a>A kiskereskedelmi kimutatásokat befolyásoló paraméterek konfigurálása

[!include [banner](../includes/banner.md)]

Ez a cikk a kimutatások létrehozásának és feladásának módját befolyásoló Commerce paraméterek konfigurációit mutatja be. Ez az eljárás az USRT bemutatócéget használja.

1. A navigációs ablaktáblán lépjen a **Modulok > Retail és Commerce > Központ beállítás > Paraméterek > Commerce paraméterek** részhez.
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

