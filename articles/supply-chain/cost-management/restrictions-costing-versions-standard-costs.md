---
title: Az elszámolóárakkal kapcsolatos költségszámítási verziókra vonatkozó korlátozások
description: Ez a témakör az elszámolóárakra vonatkozó költségszámítási verziókra érvényes korlátozásokat mutatja be.
author: AndersGirke
manager: tfehr
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2348d7721cd281bb2a1b5af007c98ce69377a412
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214435"
---
#  <a name="restrictions-on-costing-versions-for-standard-costs"></a>Az elszámolóárakkal kapcsolatos költségszámítási verziókra vonatkozó korlátozások

[!include [banner](../includes/banner.md)]

Ez a témakör az elszámolóárakra vonatkozó költségszámítási verziókra érvényes korlátozásokat mutatja be. 

A következő korlátozások segítenek biztosítani a szabványos költségszámítási elvek alkalmazását:

-  A cikkek költségében szerepelnie kell a költségeknek. A legyártott cikkhez tartozó költség az anyagjegyzékben és az útvonaladatokban szereplő amortizált állandó költséget képviseli. Emiatt a költségeknek szerepelnie kell az egységköltségben. A beszerzett cikkek költsége szintén szerepel a cikk egységköltségében.

-  A legyártott cikkek önköltségi árszámításának az elszámolóárakhoz tartozó költségszámítási verzióban szereplő költségrekordokon kell alapulnia. Költségadatok egyéb forrásait csak tervezett költségekhez tartozó költségszámítási verzióhoz lehet felhasználni, például beszerzett cikkekre vonatkozó, a beszerzési árakat meghatározó kereskedelmi megállapodások esetében. Az alternatív költségadatforrásokat az anyagjegyzék-számítási csoport határozza meg.

-  Az anyagjegyzék-számításokhoz egyszintű alábontást kell alkalmazni.

Az elszámolóárakhoz tartozó cikk-költség adatokat át lehet másolni az elszámolóárakat vagy tervezett költségeket tartalmazó másik költségszámítási verzióba. A tervezett költségekre vonatkozó cikk-költség adatokat azonban olyan költségszámítási verzióba nem lehet másolni, amely elszámolóárakat tartalmaz, mert a témakörben feljebb ismertetett megkötések nem érvényesek a tervezett költségekre.

<a name="related-topics"></a>Kapcsolódó témakörök
--------

[Költségszámítási verziók áttekintése](costing-versions.md)

[Az elszámolóárak frissítése nem gyártási környezetben](update-standard-costs-non-manufacturing-environment.md)

[Felkészülés a gyártott cikkek elszámolóárának karbantartására](update-standard-costs-manufacturing-environment.md)

