---
title: "Kiegyensúlyozott naplók egységközi számlázáshoz"
description: "Ez a cikk ismerteti, hogyan történik a napló automatikus kiegyensúlyozása a főkönyvi oldalon található kiegyenlítő pénzügyi dimenzió kijelölésekor."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: f45d180dc8dcafb0579e76b890dd5d516df5b8c0
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="balanced-journals-for-interunit-accounting"></a>Kiegyensúlyozott naplók egységközi számlázáshoz

[!include[banner](../includes/banner.md)]


Ez a cikk ismerteti, hogyan történik a napló automatikus kiegyensúlyozása a főkönyvi oldalon található kiegyenlítő pénzügyi dimenzió kijelölésekor. 

Ha a könyvelési bejegyzések a pénzügyi dimenzióértékek szintjén nem kiegyenlítettek, akkor automatikusan további könyvelési bejegyzéseket hoz létre a rendszer a napló kiegyensúlyozása érdekében. Ezek a számlatételek az **Egységközi - tartozás** és**Egységközi - jóváírás** feladási típusokat használják a **Számlák automatikus tranzakciókhoz** lapon a fő számla meghatározásához. Például az Ág, amely a második szegmens a főkönyvi számlában, a kiegyenlítő pénzügyi dimenzióként van kiválasztva, és a következő könyvelési tételek lesznek elkészítve.

|                      |           |
|----------------------|-----------|
| 6100 – MSP – OU\_256 | 100,00 TARTOZÁS |
| 6100 – NY – OU\_249  | 100,00 TARTOZÁS |
| 2100 – MSP – OU\_256 | 200.00 CR |

Ebben az esetben a következő egyenlegek vannak meghatározva:

-   Ág MSP = 100,00 CR
-   Ágazati NY = 100,00 DR

Ezért a következő könyvelési bejegyzések automatikusan létrejönnek a napló kiegyenlítésére a pénzügyi dimenzió értékeinek szintjén.

|                                   |           |
|-----------------------------------|-----------|
| (Egységközi - terhelés) – MSP – OU\_256 | 100,00 TARTOZÁS |
| (Egységközi - jóváírás) – NY – OU\_249 | 100.00 CR |






