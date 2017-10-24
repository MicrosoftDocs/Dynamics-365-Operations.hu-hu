---
title: "Értékcsökkenési módszerek és szabályok"
description: "Ez a cikk betekintést nyújt a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition által támogatott értékcsökkenési szabályokba és az értékcsökkenési metódusokba."
author: twheeloc
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile, AssetGroupBookSetup, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3441
ms.assetid: 1d8267b1-86a8-44bf-8814-f56b5d45a0ae
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d802933f29b3e08704480035925b2fbf6743e996
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="depreciation-methods-and-conventions"></a>Értékcsökkenési módszerek és szabályok

[!include[banner](../includes/banner.md)]


Ez a cikk betekintést nyújt a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition által támogatott értékcsökkenési szabályokba és az értékcsökkenési metódusokba.

Különféle értékcsökkenési módszerek és szabályok közül lehet választani. A módszerek célja, hogy a pénzügyi időszakok között felosszák a tárgyi eszköz értékcsökkenésként elszámolható értékét. A tárgyi eszköz értékcsökkenésként elszámolható részét úgy lehet kiszámítani, hogy a beszerzési árat csökkenti az esetleges maradványértékkel. 

Ha értékcsökkenési szabályokat használ, és módosítja egy eszköz értékcsökkenésének a futtatási dátumát, amellyel néhány értékcsökkenés kihagyását okozza, akkor a legutóbbi év értékcsökkenése kevesebb vagy több lehet a vártnál. Az értékcsökkenés kiigazítható az értékcsökkenés legutóbbi futtatási dátumának a módosításával befolyásolt értékcsökkenési időszakok számával.

Ha például három évig használja a féléves értékcsökkenési szabályt, akkor az értékcsökkenés normális esetben 3 1/2 évig tart. Ha a 3 1/2 év alatt módosítja a legutóbbi értékcsökkenés futtatási dátumát, akkor az értékcsökkenés utolsó éve már nem tartozik a érintett időszakok közé. Ha három hónappal áthelyezi a dátumot, akkor az utolsó évben kilenc hónapnyi értékcsökkenés lesz, pedig normális esetben csak hat hónapnyi értékcsökkenés lenne.

Az alábbi értékcsökkenési szabályok közül lehet választani.


-   Félév
-   Teljes hónap
-   Negyedév közepe
-   Hónap közepe (hó elseje)
-   Hónap közepe (hó 15-e)
-   Félév (évkezdet)
-   Félév (következő év)

A következő értékcsökkenési módok közül választhat.
-   Lineáris - élettartam
-   Degresszív
-   Manuális
-   Szorzó
-   Felhasználás
-   Lineáris - hátralevő élettartam
-   200% degresszív
-   175% degresszív
-   150% degresszív
-   125% degresszív

 



<a name="see-also"></a>Lásd még
--------

[Tárgyi eszközök értékcsökkenése](fixed-asset-depreciation.md)

[Lineáris – élettartam szerinti értékcsökkenés](Straight-line-service-life-depreciation.md)

[Degresszív értékcsökkenés](reduce-balance-depreciation.md)

[Kézi értékcsökkenés](manual-depreciation.md)

[Értékcsökkenési tényező](factor-depreciation.md)

[Felhasználás értékcsökkenése](consumption-depreciation.md)

[Lineáris - hátralevő élettartam értékcsökkenés](straight-line-life-remaining-depreciation.md)

[125 százalékos degresszív értékcsökkenés](125-percent-reducing-balance-depreciation.md)

[150 százalék degresszív értékcsökkenés](150-percent-reducing-balance-depreciation.md)

[175 százalék degresszív értékcsökkenés](175-percent-reducing-balance-depreciation.md)

[200 százalék degresszív értékcsökkenés](200-percent-reducing-balance-depreciation.md)




