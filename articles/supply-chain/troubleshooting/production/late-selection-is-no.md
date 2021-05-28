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
# <a name="late-selection-isnt-respected-when-production-orders-are-reset-via-a-batch-job"></a><span data-ttu-id="cc5b6-103">A késedelmes kiválasztás nincs figyelembe véve, ha a termelési rendelések visszaállítása kötegelt feladat segítségével történik</span><span class="sxs-lookup"><span data-stu-id="cc5b6-103">Late selection isn't respected when production orders are reset via a batch job</span></span>

<span data-ttu-id="cc5b6-104">Tudásbáziscikk száma: 4614634</span><span class="sxs-lookup"><span data-stu-id="cc5b6-104">KB number: 4614634</span></span>

## <a name="symptoms"></a><span data-ttu-id="cc5b6-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="cc5b6-105">Symptoms</span></span>

<span data-ttu-id="cc5b6-106">Ha ismétlődő kötegelt feladattal állítja alaphelyzetbe a termelési rendelés állapotát, a késedelmes kiválasztásokat nem veszi figyelembe a program.</span><span class="sxs-lookup"><span data-stu-id="cc5b6-106">When you use a recurring batch job to reset the status of a production order, late selections aren't respected.</span></span>

## <a name="resolution"></a><span data-ttu-id="cc5b6-107">Felbontás</span><span class="sxs-lookup"><span data-stu-id="cc5b6-107">Resolution</span></span>

<span data-ttu-id="cc5b6-108">A jelenlegi terv nem támogatja a késedelmes kiválasztások használatát az *Állapot visszaállítása* folyamathoz.</span><span class="sxs-lookup"><span data-stu-id="cc5b6-108">The current design doesn't support the use of late selections for the *Reset status* process.</span></span>
