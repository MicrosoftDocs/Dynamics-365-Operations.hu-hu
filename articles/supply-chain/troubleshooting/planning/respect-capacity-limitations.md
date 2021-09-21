---
title: Az alaptervezés többet ütemez, mint a rendelkezésre álló kapacitás
description: Úgy tűnik, hogy az alaptervezés nem veszi figyelembe a kapacitáskorlátozásokat, és a rendelkezésre álló kapacitásnál többet ütemez
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
ms.openlocfilehash: 48b3d179bb923ff6f6cc5b6be291408b3eb34d98
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476566"
---
# <a name="master-planning-is-scheduling-more-than-the-available-capacity"></a>Az alaptervezés többet ütemez, mint a rendelkezésre álló kapacitás

## <a name="symptoms"></a>Tünetek

Úgy tűnik, hogy az alaptervezés nem veszi figyelembe a kapacitáskorlátozásokat, és a rendelkezésre álló kapacitásnál többet ütemez.

Ha olyan műveletütemezést használ, ahol véges kapacitás van, és ahol az útvonal egy erőforráscsoport és az egyes erőforrások követelményeinek kombinációját meghatározza, akkor kis esély van a túlfoglalásra, mivel az algoritmus a kapacitásütközéseket figyelembe véve érvényesít. Ez a túlfoglalás akkor fordulhat elő, ha segédalkalmazásokkal futtatja az alaptervezést. Ez leginkább akkor fordul elő, ha sok olyan feladat van, amelyeknek viszonylag rövid a futásidejű.

## <a name="resolution"></a>Megoldás

Ha elengedhetetlen, hogy a műveletütemezéshez ne legyen túlfoglalás, az alaptervezés ütemezését egyszálassá teheti, ha bekapcsolja a **Műveletütemezéshez való pontos, véges kapacitás** beállítást az **Alaptervezési paraméterek** lapon. Ez a beállítás nem érhető el alapértelmezetten. A személyre szabási funkciók használatával manuálisan kell hozzáadnia az oldalhoz. Ha ezt a beállítást használja, az ütemezés lassabban fog futni a párhuzamos feldolgozás hiánya miatt.
