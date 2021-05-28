---
title: A késedelmes kiválasztás nincs figyelembe véve, ha a termelési rendelések visszaállítása kötegelt feladat segítségével történik
description: Ha ismétlődő kötegelt feladattal állítja alaphelyzetbe a termelési rendelés állapotát, a késedelmes kiválasztásokat nem veszi figyelembe a program.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: e53198f427f4060421a4f0078277682c43db1320
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026569"
---
# <a name="late-selection-isnt-respected-when-production-orders-are-reset-via-a-batch-job"></a>A késedelmes kiválasztás nincs figyelembe véve, ha a termelési rendelések visszaállítása kötegelt feladat segítségével történik

Tudásbáziscikk száma: 4614634

## <a name="symptoms"></a>Tünetek

Ha ismétlődő kötegelt feladattal állítja alaphelyzetbe a termelési rendelés állapotát, a késedelmes kiválasztásokat nem veszi figyelembe a program.

## <a name="resolution"></a>Felbontás

A jelenlegi terv nem támogatja a késedelmes kiválasztások használatát az *Állapot visszaállítása* folyamathoz.
