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
ms.openlocfilehash: d8cae6d2fa7c469f50fa92141a6cb5a0af1df4b0
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022767"
---
# <a name="configure-parameters-that-affect-retail-statements"></a>A kiskereskedelmi kimutatásokat befolyásoló paraméterek konfigurálása

[!include[task guide banner](../includes/task-guide-banner.md)]

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

