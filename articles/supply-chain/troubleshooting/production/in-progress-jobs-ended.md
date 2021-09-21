---
title: A folyamatban lévő feladatok befejeződnek, amikor az utolsó feladatnál részmennyiséget jelent le
description: Amikor a feladatkártya-eszközzel részleges mennyiséget jelentek a termelési rendelés utolsó feladatán, a rendelésben szereplő összes előző feladat, amelynek állapota Folyamatban van, lezárul.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 11511d4ac7524facdd0d647e9bc38fe09c282be1
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476594"
---
# <a name="previous-in-progress-jobs-are-ended-when-reporting-partial-quantity-on-last-job"></a>Az előző folyamatban lévő feladatok befejeződnek, amikor az utolsó feladatnál részmennyiséget jelent le

## <a name="symptoms"></a>Tünetek

Amikor a feladatkártya-eszközzel részleges mennyiséget jelentenek le a termelési rendelés utolsó feladatán, a rendelésben szereplő összes előző feladat, amelynek állapota Folyamatban van, automatikusan lezárul.

## <a name="resolution"></a>Megoldás

Ez szándékosan van. A **Termelési rendelés alapértelmezései** lapon a **Készként jelentés** fülön van egy **Útvonal megjelölése befejezettként** lehetőség. Ha ez a témakör *Igen* értékre van állítva, akkor egy útvonalkártya-naplót könyvel, amikor egy dolgozó a munkakártya-eszközt vagy a feladatkártya terminálját használja az utolsó művelet jelentéséhez. Ez a napló befejezettként jelöli meg az összes műveletet, és befejezi az összes termelési feladatot. Ha az **Útvonal megjelölése befejezettként** lehetőség *Igen* értékre van állítva, akkor a rendszer nem veszi figyelembe azt a feladatállapotot, amelyet a dolgozó az utolsó művelet jelentésekor választott. A rendszer azt sem veszi figyelembe, hogy a dolgozó teljes vagy részleges mennyiséget jelent-e.
