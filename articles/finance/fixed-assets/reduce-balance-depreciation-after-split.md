---
title: Degresszív értékcsökkenés felosztás után
description: Ez a témakör azt a módszert ismerteti, amelyet a Tárgyi eszközök eszköz felosztása utáni értékcsökkenés kiszámítására használnak az egyenleg csökkentése módszerrel.
author: moaamer
manager: Ann Beebe
ms.date: 11/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-11-17
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: f276f49e5b1bc2814dc851f1ad4204a151d86c43
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222383"
---
# <a name="reduce-balance-depreciation-after-a-split"></a><span data-ttu-id="2ba6e-103">Degresszív értékcsökkenés felosztás után</span><span class="sxs-lookup"><span data-stu-id="2ba6e-103">Reduce balance depreciation after a split</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2ba6e-104">Ez a témakör azt a módszert ismerteti, amelyet a Tárgyi eszközök egy másik eszköz felosztása utáni értékcsökkenés kiszámítására használnak az egyenleg csökkentése módszerrel.</span><span class="sxs-lookup"><span data-stu-id="2ba6e-104">This topic describes the method that is used in Fixed assets to calculate depreciation after an asset is split to another asset by using the reduce balance method.</span></span> <span data-ttu-id="2ba6e-105">Az eszközkönyvben konfigurált értékcsökkenési év a pénzügyi év.</span><span class="sxs-lookup"><span data-stu-id="2ba6e-105">The depreciation year that is configured in the asset book is the fiscal year.</span></span> <span data-ttu-id="2ba6e-106">További információ: [Degresszív értékcsökkenés](reduce-balance-depreciation.md) és [Tárgyi eszköz felosztása](tasks/split-fixed-asset.md).</span><span class="sxs-lookup"><span data-stu-id="2ba6e-106">For more information, see [Reduce balance depreciation](reduce-balance-depreciation.md) and [Split a fixed asset](tasks/split-fixed-asset.md).</span></span>

<span data-ttu-id="2ba6e-107">Ha egy tárgyi eszközt olyan pénzügyi időszakban oszt fel, amely későbbi, mint az eszköz beszerzésének időszaka, a degresszív értékcsökkenés az eszköz előző évi nettó könyv szerinti értékét (NBV) veszi figyelembe.</span><span class="sxs-lookup"><span data-stu-id="2ba6e-107">If you split a fixed asset during a fiscal period that is later than the period when the asset was acquired, the reduced balance depreciation will account for the asset's net book value (NBV) for the previous year.</span></span> <span data-ttu-id="2ba6e-108">Figyelembe veszi az eszközt felosztó tranzakcióból származó beszerzési és értékcsökkenés-kiigazítási tranzakciókat is.</span><span class="sxs-lookup"><span data-stu-id="2ba6e-108">It will also account for the acquisition and depreciation adjustment transactions that were generated from the transaction that split the asset.</span></span> <span data-ttu-id="2ba6e-109">Ez a viselkedés azt feltételezi, hogy az eszközt egy pénzügyi évben szerezték be, és egy későbbi pénzügyi évben osztották fel.</span><span class="sxs-lookup"><span data-stu-id="2ba6e-109">This behavior assumes that the asset was acquired in one fiscal year and split in a later fiscal year.</span></span> <span data-ttu-id="2ba6e-110">Az az összeg, amelyet a felosztás után az eredeti eszközre le kell csökkenteni, az eszköz felosztása előtti NBV-t, valamint a felosztásra feladott beszerzési és értékcsökkenési kiigazítási tranzakciót tükrözi.</span><span class="sxs-lookup"><span data-stu-id="2ba6e-110">The amount that must be depreciated for the original asset after the split reflects the asset's NBV before the asset was split, and the acquisition and depreciation adjustment transaction that was posted for the split.</span></span>

<span data-ttu-id="2ba6e-111">Például a következő feltételek vannak érvényben:</span><span class="sxs-lookup"><span data-stu-id="2ba6e-111">For example, the following conditions are in effect:</span></span>

- <span data-ttu-id="2ba6e-112">A pénzügyi időszak június 30-tól július 1-ig tart.</span><span class="sxs-lookup"><span data-stu-id="2ba6e-112">The fiscal period is from June 30 to July 1.</span></span>
- <span data-ttu-id="2ba6e-113">A csökkentési egyenleg százaléka 18 százalék, és egy eszközt 2019 júniusában 10.000 dollár beszerzési áron szereznek be.</span><span class="sxs-lookup"><span data-stu-id="2ba6e-113">The reducing balance percentage is 18 percent, and an asset is acquired in June 2019 at an acquisition price of $10,000.</span></span>
- <span data-ttu-id="2ba6e-114">Az első pénzügyi év értékcsökkenése 18.000 dollár, a havi értékcsökkenés 150 dollár, majd az eszköz értékcsökkenése 2019 novemberéig 738,75 dollár.</span><span class="sxs-lookup"><span data-stu-id="2ba6e-114">The depreciation of the first fiscal year equals $18,000, the monthly depreciation equals $150, and the asset is then depreciated until November 2019, in the amount of $738.75.</span></span>
- <span data-ttu-id="2ba6e-115">2019 novemberében az eszköz 80 százaléka feloszlik egy másik tárgyi eszközre.</span><span class="sxs-lookup"><span data-stu-id="2ba6e-115">In November 2019, 80 percent of the asset is split to another fixed asset.</span></span>

<span data-ttu-id="2ba6e-116">[![Degresszív értékcsökkenés felosztás után](./media/reduce-balance-depreciation-after-split.png)](./media/reduce-balance-depreciation-after-split.png)</span><span class="sxs-lookup"><span data-stu-id="2ba6e-116">[![Reduce balance depreciation after a split](./media/reduce-balance-depreciation-after-split.png)](./media/reduce-balance-depreciation-after-split.png)</span></span>

<span data-ttu-id="2ba6e-117">Az eredeti eszköz értékcsökkenésének összege 1.822,25 dollár.</span><span class="sxs-lookup"><span data-stu-id="2ba6e-117">The amount to depreciate for the original asset is $1,822.25.</span></span> <span data-ttu-id="2ba6e-118">Ez az összeg megegyezik az NBV-vel a felosztásos tranzakció feladása előtt (9111,25 dollár), valamint a felosztásos tranzakció feladása során keletkező beszerzési helyesbítés (-8000 dollár), valamint a felosztásos tranzakció során keletkező értékcsökkenési helyesbítés (711 dollár).</span><span class="sxs-lookup"><span data-stu-id="2ba6e-118">This amount equals the NBV before the split transaction is posted ($9,111.25), plus the acquisition adjustment that is generated during posting of the split transaction (-$8,000), plus the depreciation adjustment that is generated during the split transaction ($711).</span></span> <span data-ttu-id="2ba6e-119">Ezért a második év értékcsökkenése (1.822,25 × 18 százalék) ÷ 12 = 27,33 dollár.</span><span class="sxs-lookup"><span data-stu-id="2ba6e-119">Therefore, the depreciation for the second year is (1,822.25 × 18 percent) ÷ 12 = $27.33.</span></span>

<span data-ttu-id="2ba6e-120">Az új tárgyi eszköz értékcsökkenésének összege az első évben (8 000 × 18 százalék) ÷ 12 = 120 dollár.</span><span class="sxs-lookup"><span data-stu-id="2ba6e-120">The amount to depreciate for the new fixed asset in the first year is (8,000 × 18 percent) ÷ 12 = $120.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]