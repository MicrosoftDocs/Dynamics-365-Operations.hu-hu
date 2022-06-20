---
title: Értékcsökkenési javaslat létrehozása
description: Ez a cikk bemutatja az értékcsökkenési kötegjavaslatok működikát, és bemutatja, hogyan lehet javasolni a tárgyi eszközök értékcsökkenését.
author: abruer
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a1f39a1412c6f96fe0a8261602a88a6a3c3cd6b8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858496"
---
# <a name="create-a-depreciation-proposal"></a>Értékcsökkenési javaslat létrehozása

[!include [banner](../../includes/banner.md)]

Ez a cikk bemutatja az értékcsökkenési kötegjavaslatok működikát, és bemutatja, hogyan lehet javasolni a tárgyi eszközök értékcsökkenését. Ez a feladat a USMF bemutató vállalatot, illetve a könyvelői szerepkört használja.


## <a name="create-a-depreciation-proposal"></a>Értékcsökkenési javaslat létrehozása
1. A navigációs ablakban menjen **a Tárgyi eszközök > az Értékcsökkenési javaslat létrehozása > lapra**.
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
