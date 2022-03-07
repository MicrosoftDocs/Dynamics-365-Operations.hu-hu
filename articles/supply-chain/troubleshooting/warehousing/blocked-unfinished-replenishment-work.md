---
title: A kitárolási munka lezáratlan feltöltési munka miatt zárolva van
description: A kitárolási munka a függő feltöltési munka miatt zárolva lehet. Fejezze be a feltöltési munkát, majd dolgozza fel a kitárolási munkát.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 53b50d1e3e2d7bb64e78514affe80076ddcb9052
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476598"
---
# <a name="picking-work-cant-be-unblocked-because-of-unfinished-replenishment-work"></a>A kitárolási munka a be nem fejezett feltöltési munka miatt nem oldható fel

## <a name="symptoms"></a>Tünetek

Hullám igényfeltöltésének használata esetén a kitárolási munka blokkolható a függő feltöltési munka miatt. Ha a rendszer a feltöltési munkát és a kitárolási munkát egyaránt létrehozza, a kitárolási helyet fel kell tölteni a forrásrendelés igényének kielégítésére. A kitárolási munka azonban addig megakadályozza a kitárolást, amíg be nem fejeződik a feltöltési munka, és a következő hibaüzenet jelenik meg:

> A(z) %1 munka zárolása nem szüntethető meg, mert befejezetlen feltöltési munka kapcsolódik hozzá.

## <a name="resolution"></a>Megoldás

Ez a viselkedés szándékos, mert a kitárolási hely nem rendelkezik elegendő készlettel, ha a feltöltési munka be van fejezve. Fejezze be a feltöltési munkát, majd dolgozza fel a kitárolási munkát.
