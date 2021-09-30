---
title: Az egység- és egységmennyiség nem működnek megfelelően a készletnaplóban.
description: Az egység- és egységmennyiség nem működnek megfelelően a készletnaplóban.
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 39f462ae325aa1104a25a8290daed70388e624ec
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476533"
---
# <a name="the-unit-and-unit-quantity-arent-working-correctly-in-the-inventory-journal"></a>Az egység- és egységmennyiség nem működnek megfelelően a készletnaplóban.

## <a name="symptoms"></a>Tünetek

Ha készletnapló egységekkel és mennyiségekkel dolgozik, a következő problémák valamelyike vagy mindkettő előfordulhat:

- Ha a kiadott termékhez be van állítva az átváltás egysége, akkor nem látja a készletnaplóban az egységeket és az egységmennyiségeket, és nem lehet benne módosítani az egységet.
- A készletnaplóban a **Mennyiség** és az **Egység** mezők láthatók, az **Egység mennyisége** mező azonban nem. Ha módosítja az egységet, adjon meg egy mennyiséget, majd adja fel a naplót – a naplóban továbbra is látható az adott mennyiség eredeti mértékegysége.

## <a name="resolution"></a>Megoldás

Ezen hiba javításához kövesse az alábbi lépéseket.

1. A **Szolgáltatáskezelés** munkaterületen győződjön meg arról, hogy be van kapcsolva a *Mértékegység és az egységmennyiség használata a készletnaplókban* funkció. Ez a funkció hozzáadja az **Egység** és az **Egységmennyiség** mezőket a naplóhoz.
1. A funkció bekapcsolás után használja a következő módon a **Mennyiség**, **Egységmennyiség** és **Egység** mezőket:

    - **Mennyiség** – Határozza meg a mennyiséget a kiadott termékre meghatározott alapértelmezett egység használatával. Ugyanakkor maga az alapértelmezett egység nem jelenik meg itt. Ha az alapértelmezett egység és az **Egység** mezőben kiválasztott egység között átváltás van beállítva, akkor a **Mennyiség** mező automatikusan frissül az **Egységmennyiség** és az **Egység** mezőben megadott beállításoknak megfelelően.
    - **Egységmennyiség** – Adja meg a mennyiséget az **Egység** mezőben kiválasztott egység használatával.
    - **Egység** – Válassza ki az **Egységmennyiség** mezőben szereplő értékre alkalmazandó egységet.