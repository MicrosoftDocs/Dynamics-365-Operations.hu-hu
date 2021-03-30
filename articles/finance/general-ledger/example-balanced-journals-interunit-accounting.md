---
title: Kiegyensúlyozott naplók egységközi számlázáshoz
description: Ez a cikk ismerteti, hogyan történik a napló automatikus kiegyensúlyozása a főkönyvi oldalon található kiegyenlítő pénzügyi dimenzió kijelölésekor.
author: ShylaThompson
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8c5f73606708b8c32a7a8ebc364af6ba57c4c343
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5205523"
---
# <a name="balanced-journals-for-interunit-accounting"></a>Kiegyensúlyozott naplók egységközi számlázáshoz

[!include [banner](../includes/banner.md)]

Ez a cikk ismerteti, hogyan történik a napló automatikus kiegyensúlyozása a főkönyvi oldalon található kiegyenlítő pénzügyi dimenzió kijelölésekor. 

Ha a könyvelési bejegyzések a pénzügyi dimenzióértékek szintjén nem kiegyenlítettek, akkor automatikusan további könyvelési bejegyzéseket hoz létre a rendszer a napló kiegyensúlyozása érdekében. Ezek a számlatételek az **Egységközi - tartozás** és **Egységközi - jóváírás** feladási típusokat használják a **Számlák automatikus tranzakciókhoz** lapon a fő számla meghatározásához. Például az Üzleti egység, amely a második szegmens a főkönyvi számlában, a kiegyenlítő pénzügyi dimenzióként van kiválasztva, és a következő könyvelési tételek lesznek elkészítve.

|                      |           |
|----------------------|-----------|
| 6100 – MSP – OU\_256 | 100,00 TARTOZÁS |
| 6100 – NY – OU\_249  | 100,00 TARTOZÁS |
| 2100 – MSP – OU\_256 | 200.00 CR |

Ebben az esetben a következő egyenlegek vannak meghatározva:

-   Üzleti egység – MSP = 100.00 CR
-   Üzleti egység – NY = 100.00 DR

Ezért a következő könyvelési bejegyzések automatikusan létrejönnek a napló kiegyenlítésére a pénzügyi dimenzió értékeinek szintjén.

|                                   |           |
|-----------------------------------|-----------|
| (Egységközi - terhelés) – MSP – OU\_256 | 100,00 TARTOZÁS |
| (Egységközi - jóváírás) – NY – OU\_249 | 100.00 CR |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]