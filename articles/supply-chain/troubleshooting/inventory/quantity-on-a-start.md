---
title: Az elindított karanténutasításban szereplő mennyiség nem frissül a rendelés felosztása esetén
description: Amikor karanténutasítást hoz létre, és megpróbálja felosztani, a rendelési mennyiség nem frissül a fennmaradó megosztott mennyiséggel.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: shawan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: a8af535257ce217629d5ba92e624623c3ea39345
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026588"
---
# <a name="quantity-on-a-started-quarantine-order-isnt-updated-when-the-order-is-split"></a><span data-ttu-id="275fc-103">Az elindított karanténutasításban szereplő mennyiség nem frissül a rendelés felosztása esetén</span><span class="sxs-lookup"><span data-stu-id="275fc-103">Quantity on a started quarantine order isn't updated when the order is split</span></span>

<span data-ttu-id="275fc-104">Tudásbáziscikk száma: 4613113</span><span class="sxs-lookup"><span data-stu-id="275fc-104">KB number: 4613113</span></span>

## <a name="symptoms"></a><span data-ttu-id="275fc-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="275fc-105">Symptoms</span></span>

<span data-ttu-id="275fc-106">Amikor karanténutasítást hoz létre, és megpróbálja felosztani, a rendelési mennyiség nem frissül a fennmaradó mennyiséggel a megosztás utám.</span><span class="sxs-lookup"><span data-stu-id="275fc-106">When you create a quarantine order and try to split it, the order quantity isn't updated to the remaining quantity after the split.</span></span>

## <a name="resolution"></a><span data-ttu-id="275fc-107">Felbontás</span><span class="sxs-lookup"><span data-stu-id="275fc-107">Resolution</span></span>

<span data-ttu-id="275fc-108">A rendszer nem módosítja az eredeti mennyiséget karanténutasításból, hogy nyomon követhető legyen az adott karanténutasításhoz létrehozott eredeti mennyiség.</span><span class="sxs-lookup"><span data-stu-id="275fc-108">The system doesn't change the original quantity from a quarantine order to ensure that you can track the original quantity that was created for that quarantine order.</span></span> <span data-ttu-id="275fc-109">A rendszer azonban nyomon követi a karanténutasításból felosztott mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="275fc-109">However, the system does track the quantity that is split from a quarantine order.</span></span> <span data-ttu-id="275fc-110">Ehhez a nyomon követéshez egy `QuantityThatHasSplitIntoOtherQuarantineOrders` nevű adatbázismezőt használ.</span><span class="sxs-lookup"><span data-stu-id="275fc-110">To do this tracking, it uses a database field that is named `QuantityThatHasSplitIntoOtherQuarantineOrders`.</span></span> <span data-ttu-id="275fc-111">Ez a mező azonban nem jelenik meg a felhasználói felületen (UI).</span><span class="sxs-lookup"><span data-stu-id="275fc-111">However, this field isn't visible in the user interface (UI).</span></span>
