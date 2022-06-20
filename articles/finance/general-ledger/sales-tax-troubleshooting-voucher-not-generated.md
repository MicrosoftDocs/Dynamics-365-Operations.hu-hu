---
title: A bizonylat nem jön létre
description: Ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítséget nyújtnak a bizonylatok generálása során, de nem.
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
ms.openlocfilehash: 1200fe50bf9be4c6d1ca809ad9a86da2ff3e0ced
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8909011"
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
