---
title: Az elszámolóárakkal kapcsolatos költségszámítási verziókra vonatkozó korlátozások
description: Ez a témakör az elszámolóárakra vonatkozó költségszámítási verziókra érvényes korlátozásokat mutatja be.
author: AndersGirke
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
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9d828e2413a20c4e61d162a31d3c2ed2b18718b
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187674"
---
#  <a name="restrictions-on-costing-versions-for-standard-costs"></a>Az elszámolóárakkal kapcsolatos költségszámítási verziókra vonatkozó korlátozások

[!include [banner](../includes/banner.md)]

Ez a témakör az elszámolóárakra vonatkozó költségszámítási verziókra érvényes korlátozásokat mutatja be. 

A következő korlátozások segítenek biztosítani a szabványos költségszámítási elvek alkalmazását:

-  A cikkek költségében szerepelnie kell a költségeknek. A legyártott cikkhez tartozó költség az anyagjegyzékben és az útvonaladatokban szereplő amortizált állandó költséget képviseli. Emiatt a költségeknek szerepelnie kell az egységköltségben. A beszerzett cikkek költsége szintén szerepel a cikk egységköltségében.

-  A legyártott cikkek önköltségi árszámításának az elszámolóárakhoz tartozó költségszámítási verzióban szereplő költségrekordokon kell alapulnia. Költségadatok egyéb forrásait csak tervezett költségekhez tartozó költségszámítási verzióhoz lehet felhasználni, például beszerzett cikkekre vonatkozó, a beszerzési árakat meghatározó kereskedelmi megállapodások esetében. Az alternatív költségadatforrásokat az anyagjegyzék-számítási csoport határozza meg.

-  Az anyagjegyzék-számításokhoz egyszintű alábontást kell alkalmazni.

Az elszámolóárakhoz tartozó cikk-költség adatokat át lehet másolni az elszámolóárakat vagy tervezett költségeket tartalmazó másik költségszámítási verzióba. A tervezett költségekre vonatkozó cikk-költség adatokat azonban olyan költségszámítási verzióba nem lehet másolni, amely elszámolóárakat tartalmaz, mert a témakörben feljebb ismertetett megkötések nem érvényesek a tervezett költségekre.

## <a name="related-topics"></a>Kapcsolódó témakörök

[Költségszámítási verziók áttekintése](costing-versions.md)

[Az elszámolóárak frissítése nem gyártási környezetben](update-standard-costs-non-manufacturing-environment.md)

[Felkészülés a gyártott cikkek elszámolóárának karbantartására](update-standard-costs-manufacturing-environment.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]