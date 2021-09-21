---
title: A rakomány felszabadításakor a kitárolási munka azonnali létrehozása
description: Ha a munkát azonnal létre kell hozni a rakomány kiadásakor, ennek megfelelően kell konfigurálnia a hullámsablont. Ez a lap végigvezeti a lépéseken.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: fdeb0b27f4d2c1a2cc9f8e0c4ba537cdce604bd2
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476570"
---
# <a name="picking-work-isnt-generated-immediately-when-outbound-load-is-released"></a>A kitárolási munka nem jön létre azonnal, amikor a kimenő rakomány ki van adva

## <a name="symptoms"></a>Tünetek

Kimenő rakományt értékesítési vagy átátviteli rendeléssel lehet létrehozni, és a rakományt a raktárba kell kiadni. Azonban észreveszi, hogy kitárolási munka még nem jött létre.

## <a name="resolution"></a>Megoldás

Ha a munkát azonnal létre kell hozni a rakomány kiadásakor, ennek megfelelően kell konfigurálnia a hullámsablont. A hullámsablonon állítsa a következő beállításokat *Igen* értékre:

- Hullámlétrehozás automatizálása
- Hullám feldolgozása a raktárba történő kiadáskor
- Hullámkiadás automatizálása
