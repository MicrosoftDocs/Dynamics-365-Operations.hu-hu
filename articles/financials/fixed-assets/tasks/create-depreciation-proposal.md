---
title: Értékcsökkenési javaslat létrehozása
description: Ez az eljárás bemutatja, hogy hogyan működnek az értékcsökkenési kötegjavaslatok, illetve elmagyarázza, hogy hogyan hozhat létre tárgyi eszközök értékcsökkenésére irányuló javaslatot.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d11554ee5f26ef5a85e799194d2f75757a31c254
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "361291"
---
# <a name="create-depreciation-proposal"></a>Értékcsökkenési javaslat létrehozása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogy hogyan működnek az értékcsökkenési kötegjavaslatok, illetve elmagyarázza, hogy hogyan hozhat létre tárgyi eszközök értékcsökkenésére irányuló javaslatot. Ez a feladat a USMF bemutató vállalatot, illetve a könyvelői szerepkört használja.


## <a name="create-depreciation-proposal"></a>Értékcsökkenési javaslat létrehozása
1. Ugorjon a Tárgyi eszközök > Naplóbejegyzések > Értékcsökkenési javaslat létrehozása pontra.
2. A Napló neve mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. Adja meg a dátumot a „Záró dátum” mezőben.
    * A z Értékcsökkenés összegzése opció kiválasztásával egyetlen naplósorba összegezheti a havi értékcsökkenéseket.  
    * Például ha a záródátum értéke 2015. március 31., a program a következő leírást generálja: „Értékcsökkenés 2015. január 31-e óta”. A javasolt naplósorok Dátummezője ekkor 2015. március 31-re áll át.  
    * A Szűrő opció segítségével eszköz, eszközcsoport vagy egyéb feltétel szerint szűrheti az értékcsökkenési javaslatokat.  
    * A Beszerzési vagy értékcsökkenési javaslatok tárgyi eszközökhöz adatlap használata esetén tud kötegenkénti értékcsökkenésre vonatkozó javaslatot adni meg. Ezt a módszert ajánljuk olyan nagyobb javaslatoknál, amelyek komolyabb mértékben használják a rendszer erőforrásait. Ha a köteg lehetőséget választja, akkor a rendszert közben más feladatokhoz is használhatja. Ha ezzel a módszerrel hoz létre értékcsökkenési javaslatot, akkor az értékcsökkenés a tárgyieszköz-értékmodellekre jön létre.  
5. Kattintson a Napló létrehozása lehetőségre.

## <a name="review-depreciation-entries"></a>Tekintse át az értékcsökkenés bejegyzéseket
1. Ugorjon a Tárgyi eszközök > Naplóbejegyzések > Tárgyi eszközök naplója pontra.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. Kattintson a Sorok pontra.
4. Kattintson a Feladás lehetőségre.

