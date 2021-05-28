---
title: A bizonylat nem jön létre
description: Ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítséget nyújtnak, arra az esetre, ha egy bizonylatnak kellene létrejönnie, de ez nem történik meg.
author: qire
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: ba23b597b1d7d283b99638fb7d5d91da00afb09c
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018757"
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
