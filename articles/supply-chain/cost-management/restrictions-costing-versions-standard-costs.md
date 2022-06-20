---
title: Az elszámolóárakkal kapcsolatos költségszámítási verziókra vonatkozó korlátozások
description: Ez a témakör az elszámolóáras költségszámítási verziókra vonatkozó korlátozásokat ismerteti.
author: JennySong-SH
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8c5c00ae8952e2c80d97d039271a6f5c63e9a72f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8867985"
---
#  <a name="restrictions-on-costing-versions-for-standard-costs"></a>Az elszámolóárakkal kapcsolatos költségszámítási verziókra vonatkozó korlátozások

[!include [banner](../includes/banner.md)]

Ez a témakör az elszámolóáras költségszámítási verziókra vonatkozó korlátozásokat ismerteti. 

A következő korlátozások segítenek biztosítani a szabványos költségszámítási elvek alkalmazását:

-  A cikkek költségében szerepelnie kell a költségeknek. A legyártott cikkhez tartozó költség az anyagjegyzékben és az útvonaladatokban szereplő amortizált állandó költséget képviseli. Emiatt a költségeknek szerepelnie kell az egységköltségben. A beszerzett cikkek költsége szintén szerepel a cikk egységköltségében.

-  A legyártott cikkek önköltségi árszámításának az elszámolóárakhoz tartozó költségszámítási verzióban szereplő költségrekordokon kell alapulnia. Költségadatok egyéb forrásait csak tervezett költségekhez tartozó költségszámítási verzióhoz lehet felhasználni, például beszerzett cikkekre vonatkozó, a beszerzési árakat meghatározó kereskedelmi megállapodások esetében. Az alternatív költségadatforrásokat az anyagjegyzék-számítási csoport határozza meg.

-  Az anyagjegyzék-számításokhoz egyszintű alábontást kell alkalmazni.

Az elszámolóárakhoz tartozó cikk-költség adatokat át lehet másolni az elszámolóárakat vagy tervezett költségeket tartalmazó másik költségszámítási verzióba. A tervezett költségekhez kapcsolódó cikk-költség adatokat azonban nem lehet olyan költségszámítási verzióba másolni, amely elszámolóárakat tartalmaz, mert a cikk korábbi felsorolása nem vonatkozik a tervezett költségekre.

## <a name="related-articles"></a>Kapcsolódó cikkek

[Költségszámítási verziók áttekintése](costing-versions.md)

[Az elszámolóárak frissítése nem gyártási környezetben](update-standard-costs-non-manufacturing-environment.md)

[Felkészülés a gyártott cikkek elszámolóárának karbantartására](update-standard-costs-manufacturing-environment.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]