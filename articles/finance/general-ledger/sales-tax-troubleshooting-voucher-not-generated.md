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
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: eb45b79fa710699cfa267e7c6359ba3ce761d62d
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8693227"
---
# <a name="voucher-isnt-generated"></a>A bizonylat nem jön létre

[!include [banner](../includes/banner.md)]

Ha létre kellene jönnie egy bizonylatnak, de a **Bizonylattranzakciók** lapon egyetlen bizonylat sem látható, a probléma elhárításához kövesse az alábbi szakaszokban szereplő lépéseket.

[![Bizonylattranzakciók lap, amelyen nincsenek bizonylatok.](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)

## <a name="check-the-tax-applicability"></a>Adó alkalmazhatóságának ellenőrzése

1. Menjen az **Adó** \> **Időszakos feladatok** \> **Analitikus napló bejegyzései még nincsenek átadva** helyre.
2. Ha van naplórekord, válassza ki, majd válassza ki az **Átvitel most** lehetőséget.

    [![Az Analitikus napló még nem átadott naplóbejegyzéseinek Átvitel gombja.](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)

3. Nyissa meg ismét a **Bizonylattranzakciók** lapot, és tekintse meg, hogy a bizonylat létre lett-e hozva.

## <a name="determine-whether-customization-exists"></a>Annak meghatározása, hogy létezik-e testreszabás

Ha az előző szakaszban már befejezte a lépéseket, de nem találta meg a problémát, határozza meg, hogy van-e testreszabás. Ha nem létezik testreszabás, hozzon létre egy Microsoft szolgáltatáskérést további segítségért.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
