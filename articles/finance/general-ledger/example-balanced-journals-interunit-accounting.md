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
ms.search.scope: Core, Operations
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e84d96b5467b38e07a9ed31f142c27b638289284
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443865"
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





