---
title: Nem lehet készletfoglalást feloldani egy értékesítésirendelés-sorban
description: Ha nyitott munkát vet össze egy értékesítési sorral, és megpróbálja feloldani a készletfoglalást a sorban, hiba jelenik meg. A foglalás felszabadításához szükséges a munka befejezése vagy törlése.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 1a042065dc4cd637aff58e55cf16179b7022f6ca
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476561"
---
# <a name="cant-unreserve-inventory-on-a-sales-order-line"></a>Nem lehet készletfoglalást feloldani egy értékesítésirendelés-sorban

## <a name="symptoms"></a>Tünetek

Ha nyitott munkát vet össze egy értékesítésirendelés-sorral, és megpróbálja feloldani a készletfoglalást az adott sorban, a következő hiba jelenik meg:

> A foglalások nem távolíthatók el, mert létezik a foglalásokon alapuló munka.

## <a name="resolution"></a>Megoldás

Vizsgálja meg, hogy nyitott csomagolási csoportmunka létrezik-e, hogy a cikkeket egy csomagoló állomástól egy másik helyre (például *Baydoor*) vigye. A **Munkalétrehozási előzmények naplója** és **Munkarészletek** lapján található rekordok áttekintésével határozza meg, hogy mi a készlet tényleges foglalása, majd töltse ki vagy törölje a foglalást kiadó munkát.
