---
title: Kiegyensúlyozott naplók egységközi számlázáshoz
description: Ez a cikk ismerteti, hogyan történik a napló automatikus kiegyensúlyozása a főkönyvi oldalon található kiegyenlítő pénzügyi dimenzió kijelölésekor.
author: kweekley
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7f6ffccb2ee504f182250dbf6d316823efafddf5
ms.sourcegitcommit: 4f8465729d7ae0bf5150a2785a6140c984c7030e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/31/2021
ms.locfileid: "7726894"
---
# <a name="balanced-journals-for-interunit-accounting"></a>Kiegyensúlyozott naplók egységközi számlázáshoz

[!include [banner](../includes/banner.md)]

Ez a cikk ismerteti, hogyan történik a napló automatikus kiegyensúlyozása a főkönyvi oldalon található kiegyenlítő pénzügyi dimenzió kijelölésekor. 

Ha a könyvelési bejegyzések a pénzügyi dimenzióértékek szintjén nem kiegyenlítettek, akkor automatikusan további könyvelési bejegyzéseket hoz létre a rendszer a napló kiegyensúlyozása érdekében. Ezek a számlatételek az **Egységközi - tartozás** és **Egységközi - jóváírás** feladási típusokat használják a **Számlák automatikus tranzakciókhoz** lapon a fő számla meghatározásához. Például az Üzleti egység, amely a második szegmens a főkönyvi számlában, a kiegyenlítő pénzügyi dimenzióként van kiválasztva, és a következő könyvelési tételek lesznek elkészítve.

| &nbsp;               | &nbsp;    |
|----------------------|-----------|
| 6100 – MSP – OU\_256 | 100,00 TARTOZÁS |
| 6100 – NY – OU\_249  | 100,00 TARTOZÁS |
| 2100 – MSP – OU\_256 | 200.00 CR |

Ebben az esetben a következő egyenlegek vannak meghatározva:

-   Üzleti egység – MSP = 100.00 CR
-   Üzleti egység – NY = 100.00 DR

Ezért a következő könyvelési bejegyzések automatikusan létrejönnek a napló kiegyenlítésére a pénzügyi dimenzió értékeinek szintjén.

| &nbsp;                            | &nbsp;    |
|-----------------------------------|-----------|
| (Egységközi - terhelés) – MSP – OU\_256 | 100,00 TARTOZÁS |
| (Egységközi - jóváírás) – NY – OU\_249 | 100.00 CR |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
