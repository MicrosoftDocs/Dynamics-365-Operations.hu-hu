---
title: A bizonylat nem jön létre
description: Ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítséget nyújtnak, arra az esetre, ha egy bizonylatnak kellene létrejönnie, de ez nem történik meg.
author: qire
manager: beya
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: eafc9110ec58be5083569188d59b67a62e86c85d
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947652"
---
# <a name="voucher-isnt-generated"></a>A bizonylat nem jön létre

[!include [banner](../includes/banner.md)]

Ha létre kellene jönnie egy bizonylatnak, de a **Bizonylattranzakciók** lapon egyetlen bizonylat sem látható, a probléma elhárításához kövesse az alábbi szakaszokban szereplő lépéseket.

[![Bizonylattranzakciók lap, amelyen nincsenek bizonylatok](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)

## <a name="check-the-tax-applicability"></a>Adó alkalmazhatóságának ellenőrzése

1. Menjen az **Adó** \> **Időszakos feladatok** \> **Analitikus napló bejegyzései még nincsenek átadva** helyre.
2. Ha van naplórekord, válassza ki, majd válassza ki az **Átvitel most** lehetőséget.

    [![Az Analitikus napló még nem átadott naplóbejegyzéseinek Átvitel gombja](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)

3. Nyissa meg ismét a **Bizonylattranzakciók** lapot, és tekintse meg, hogy a bizonylat létre lett-e hozva.

## <a name="determine-whether-customization-exists"></a>Annak meghatározása, hogy létezik-e testreszabás

Ha az előző szakaszban már befejezte a lépéseket, de nem találta meg a problémát, határozza meg, hogy van-e testreszabás. Ha nem létezik testreszabás, hozzon létre egy Microsoft szolgáltatáskérést további segítségért.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
