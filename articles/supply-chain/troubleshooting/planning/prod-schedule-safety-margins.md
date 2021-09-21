---
title: A termelésütemezés nem veszi figyelembe a biztonsági időtartalékokat.
description: A termelésütemezés nem veszi figyelembe a rögzített készlet cikkfedezetén beállított biztonsági időtartalékokat
author: ChristianRytt
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 738296b7570ded0a4ee806e4445204a68e6a08c8
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476531"
---
# <a name="production-scheduling-doesnt-consider-the-safety-margins"></a>A termelésütemezés nem veszi figyelembe a biztonsági időtartalékokat.

## <a name="symptoms"></a>Tünetek

Az alaptervezés figyelembe veszi a biztonsági időtartalékokat. A rendszer azonban figyelmen kívül hagyja a biztonsági időtartalékokat a tervezett termelési rendelések ütemezésekor.

## <a name="resolution"></a>Megoldás

Az időtartalékok csak az alaptervezés során lesznek figyelembe véve, a manuális ütemezés során nem. Az időtartalékok úgy vannak kialakítva, hogy a tervezési fázisban pufferként működjenek, hogy a tényleges folyamathoz bizonyos „időtartalékot” biztosítsanak.

A kívánt eredmény eléréséhez eltávolíthatja az időtartalékot. Az útvonalat ezután frissíteni kell, hogy tartalmazza a kívánt időt (például várakozási sorként). Az alaptervezésnek és a manuális ütemezésnek is ugyanazt az eredményt kell elérniük.
