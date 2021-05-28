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
# <a name="voucher-isnt-generated"></a><span data-ttu-id="e7d9d-103">A bizonylat nem jön létre</span><span class="sxs-lookup"><span data-stu-id="e7d9d-103">Voucher isn't generated</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e7d9d-104">Ha létre kellene jönnie egy bizonylatnak, de a **Bizonylattranzakciók** lapon egyetlen bizonylat sem látható, a probléma elhárításához kövesse az alábbi szakaszokban szereplő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="e7d9d-104">If a voucher should be generated, but the **Voucher transactions** page doesn't show any vouchers, follow the steps in the following sections as required to troubleshoot this issue.</span></span>

<span data-ttu-id="e7d9d-105">[![Bizonylattranzakciók lap, amelyen nincsenek bizonylatok](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="e7d9d-105">[![Voucher transactions page that has no vouchers](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)</span></span>

## <a name="check-the-tax-applicability"></a><span data-ttu-id="e7d9d-106">Adó alkalmazhatóságának ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="e7d9d-106">Check the tax applicability</span></span>

1. <span data-ttu-id="e7d9d-107">Menjen az **Adó** \> **Időszakos feladatok** \> **Analitikus napló bejegyzései még nincsenek átadva** helyre.</span><span class="sxs-lookup"><span data-stu-id="e7d9d-107">Go to **Tax** \> **Periodic tasks** \> **Subledger journal entries not yet transferred**.</span></span>
2. <span data-ttu-id="e7d9d-108">Ha van naplórekord, válassza ki, majd válassza ki az **Átvitel most** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e7d9d-108">If there is a journal record, select it, and then select **Transfer now**.</span></span>

    <span data-ttu-id="e7d9d-109">[![Az Analitikus napló még nem átadott naplóbejegyzéseinek Átvitel gombja](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="e7d9d-109">[![Transfer now button on the Subledger journal entries not yet transferred page](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)</span></span>

3. <span data-ttu-id="e7d9d-110">Nyissa meg ismét a **Bizonylattranzakciók** lapot, és tekintse meg, hogy a bizonylat létre lett-e hozva.</span><span class="sxs-lookup"><span data-stu-id="e7d9d-110">Open the **Voucher transactions** page again to see whether the voucher was generated.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="e7d9d-111">Annak meghatározása, hogy létezik-e testreszabás</span><span class="sxs-lookup"><span data-stu-id="e7d9d-111">Determine whether customization exists</span></span>

<span data-ttu-id="e7d9d-112">Ha az előző szakaszban már befejezte a lépéseket, de nem találta meg a problémát, határozza meg, hogy van-e testreszabás.</span><span class="sxs-lookup"><span data-stu-id="e7d9d-112">If you've completed the steps in the previous section but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="e7d9d-113">Ha nem létezik testreszabás, hozzon létre egy Microsoft szolgáltatáskérést további segítségért.</span><span class="sxs-lookup"><span data-stu-id="e7d9d-113">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
