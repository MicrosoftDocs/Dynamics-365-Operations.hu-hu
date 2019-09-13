---
title: Értékcsökkenési javaslat létrehozása
description: Ez a témakör leírja, hogyan működnek az értékcsökkenési kötegjavaslatok, és bemutatja, hogyan hozhat létre tárgyi eszközök értékcsökkenésére irányuló javaslatot.
author: abruer
manager: AnnBe
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 90c24e9d89c055ea95ca5f25cd85ef4042476a90
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867607"
---
# <a name="create-a-depreciation-proposal"></a>Értékcsökkenési javaslat létrehozása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez a témakör leírja, hogyan működnek az értékcsökkenési kötegjavaslatok, és bemutatja, hogyan hozhat létre tárgyi eszközök értékcsökkenésére irányuló javaslatot. Ez a feladat a USMF bemutató vállalatot, illetve a könyvelői szerepkört használja.


## <a name="create-a-depreciation-proposal"></a>Értékcsökkenési javaslat létrehozása
1. A navigációs ablaktáblán nyissa meg a **Modulok > Tárgyi eszközök > Naplóbejegyzések > Értékcsökkenési javaslat létrehozása** elemet.
2. A **Napló neve** mezőben válasszon ki egy opciót a legördülő menüben.
3. Adjon meg egy dátumot a **Záró dátum** mezőben.

    - Az **Értékcsökkenés összegzése** opció kiválasztásával egyetlen naplósorba összegezheti a havi értékcsökkenéseket.  
    - Például ha a záródátum értéke 2015. március 31., a program a következő leírást generálja: „Értékcsökkenés 2015. január 31-e óta”. A javasolt naplósorok **Dátum** mezője ekkor 2015. március 31-re áll át.  
    - A **Szűrő** opció segítségével eszköz, eszközcsoport vagy egyéb feltétel szerint szűrheti az értékcsökkenési javaslatokat.  
    - A **Beszerzési vagy értékcsökkenési javaslatok tárgyi eszközökhöz** adatlap használata esetén tud kötegenkénti értékcsökkenésre vonatkozó javaslatot adni meg. Ezt a módszert ajánljuk olyan nagyobb javaslatoknál, amelyek komolyabb mértékben használják a rendszer erőforrásait. Ha a köteg lehetőséget választja, akkor a rendszert közben más feladatokhoz is használhatja. Ha ezzel a módszerrel hoz létre értékcsökkenési javaslatot, akkor az értékcsökkenés a tárgyieszköz-értékmodellekre jön létre.  

4. Válassza a **Napló létrehozása** elemet.

## <a name="review-depreciation-entries"></a>Tekintse át az értékcsökkenés bejegyzéseket
1. A navigációs ablaktáblán nyissa meg a **Modulok > Tárgyi eszközök > Naplóbejegyzések > Tárgyi eszközök naplója** elemet.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. **Sorok** kiválasztása.
4. Válassza a **Feladás** parancsot.

