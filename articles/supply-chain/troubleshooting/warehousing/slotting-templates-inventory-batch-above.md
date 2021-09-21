---
title: Az aktuális készletet nem veszik figyelembe a kötegfeletti cikkeknél
description: Egyes időközökre bontási sablonok nem veszik figyelembe az aktuális készletet a köteg fölötti cikkeknél. A köteg- vagy sorozatszámot meg kell adni az igényrendelésen.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: df5642b32f5e053144230eab3dbcf633f526279a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476552"
---
# <a name="slotting-templates-dont-consider-on-hand-inventory-for-batch-above-items"></a>Az időközökre bontási sablonok nem veszik figyelembe az aktuális készletet a köteg fölötti cikkeknél

## <a name="symptoms"></a>Tünetek

Azok az időközökre bontási sablonok, amelyeknél az *Aktuálisan készleten lévők figyelembe vétele* időközfeltétel fennáll, nem veszik figyelembe az aktuális tényleges készletet a *köteg-felett* cikkeknél. Csak akkor veszik figyelembe, ha a kötegszám meg van adva az értékesítésirendelés-sorban.

*Köteg-alatt* cikkek használatakor azonban az aktuális tényleges készlet az elvárt.

További információ: [Raktári időközökre bontás](/dynamics365/supply-chain/warehousing/warehouse-slotting).

## <a name="resolution"></a>Megoldás

Az időközökre bontási sablon fejlécében meg lehet határozni a *Megrendelve*, *Lefoglalva* vagy a *Kiadva* igény szerinti stratégiához. A *Megrendelve* igény szerinti stratégia esetén ugyanazok a foglalásihierarchia-követelmények érvényesek, amelyek a foglalási vagy raktárba kiadási folyamatok esetén érvényesek. Ezért a *köteg-feletti* és *sorozat-alatti* foglalási hierarchiákkal rendelkező cikkeknél meg kell adni a köteg- vagy sorozatszámot az igény szerinti rendelésen (értékesítés vagy átmozgatás).

Másik lehetőségként a *Lefoglalva* igény szerinti stratégia arra használható, hogy kiválassza a köteg- vagy sorozatszámot, mielőtt létrejön a raktár időközökre bontási igénye.
