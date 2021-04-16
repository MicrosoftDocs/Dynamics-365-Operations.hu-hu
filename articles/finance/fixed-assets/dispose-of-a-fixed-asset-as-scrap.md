---
title: Tárgyi eszközök kivezetése selejtként
description: Ez a témakör azt mutatja be, hogyan lehet kiküszöbölni a tranzakciókat olyan tárgyi eszközök esetében, amelyek selejtként kerültek kivezetésre.
author: moaamer
ms.date: 08/14/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 413847d350ca6b2bdd6153a598ea5b3f34a33818
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826275"
---
# <a name="dispose-of-a-fixed-asset-as-scrap"></a><span data-ttu-id="ca8a4-103">Tárgyi eszközök kivezetése selejtként</span><span class="sxs-lookup"><span data-stu-id="ca8a4-103">Dispose of a fixed asset as scrap</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ca8a4-104">Ez a témakör azt mutatja be, hogyan lehet kiküszöbölni a tranzakciókat olyan tárgyi eszközök esetében, amelyek selejtként kerültek kivezetésre.</span><span class="sxs-lookup"><span data-stu-id="ca8a4-104">The topic describes the process of eliminating transactions for a fixed asset that was disposed of as scrap.</span></span> <span data-ttu-id="ca8a4-105">Az eltávolítható tranzakciótípusok között szerepelnek egy eszköz beszerzési és felhalmozott értékcsökkenési tranzakciói, valamint egyéb tárgyieszköz-tranzakciói.</span><span class="sxs-lookup"><span data-stu-id="ca8a4-105">The transaction types that can be eliminated include an asset's acquisition and accumulated depreciation transactions and other fixed asset transactions.</span></span> <span data-ttu-id="ca8a4-106">Ezeknek a tranzakcióknak a felszámolása érinti a mérlegszámlákat, például a beszerzések helyesbítését, az értékcsökkenés kiigazítását, az átértékelést, a felértékelési és a leírási számlákat.</span><span class="sxs-lookup"><span data-stu-id="ca8a4-106">Elimination of these transactions affects balance sheet accounts, such as acquisition adjustment, depreciation adjustment, revaluation, write-up, and write-down accounts.</span></span>

| <span data-ttu-id="ca8a4-107">Tranzakció</span><span class="sxs-lookup"><span data-stu-id="ca8a4-107">Transaction</span></span>                                         | <span data-ttu-id="ca8a4-108">Tartozás (Dr.)</span><span class="sxs-lookup"><span data-stu-id="ca8a4-108">Debit (Dr.)</span></span> | <span data-ttu-id="ca8a4-109">Jóváírás (Cr.)</span><span class="sxs-lookup"><span data-stu-id="ca8a4-109">Credit (Cr.)</span></span> |
|-----------------------------------------------------|-------------|--------------|
| <span data-ttu-id="ca8a4-110">Dr. Halmozott értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="ca8a4-110">Dr. Accumulated depreciation</span></span>                        | <span data-ttu-id="ca8a4-111">X</span><span class="sxs-lookup"><span data-stu-id="ca8a4-111">X</span></span>           |              |
| <span data-ttu-id="ca8a4-112">Cr. Tárgyi eszközök nyeresége/vesztesége</span><span class="sxs-lookup"><span data-stu-id="ca8a4-112">Cr. Fixed assets gain/loss</span></span>                          |             | <span data-ttu-id="ca8a4-113">X</span><span class="sxs-lookup"><span data-stu-id="ca8a4-113">X</span></span>            |
| <span data-ttu-id="ca8a4-114">Dr. Tárgyi eszközök nyeresége/vesztesége</span><span class="sxs-lookup"><span data-stu-id="ca8a4-114">Dr. Fixed assets gain/loss</span></span>                          | <span data-ttu-id="ca8a4-115">X</span><span class="sxs-lookup"><span data-stu-id="ca8a4-115">X</span></span>           |              |
| <span data-ttu-id="ca8a4-116">Cr. Tárgyieszköz-beszerzés számlája</span><span class="sxs-lookup"><span data-stu-id="ca8a4-116">Cr. Fixed asset acquisition account</span></span>                 |             | <span data-ttu-id="ca8a4-117">X</span><span class="sxs-lookup"><span data-stu-id="ca8a4-117">X</span></span>            |
| <span data-ttu-id="ca8a4-118">Dr. Tárgyi eszközök nyeresége/vesztesége (nettó könyv szerinti érték \[NKÉ\])</span><span class="sxs-lookup"><span data-stu-id="ca8a4-118">Dr. Fixed assets gain/loss (net book value \[NBV\])</span></span> | <span data-ttu-id="ca8a4-119">X</span><span class="sxs-lookup"><span data-stu-id="ca8a4-119">X</span></span>           |              |
| <span data-ttu-id="ca8a4-120">Cr. Tárgyi eszközök nyeresége/vesztesége (NKÉ)</span><span class="sxs-lookup"><span data-stu-id="ca8a4-120">Cr. Fixed assets gain/loss (NBV)</span></span>                    |             | <span data-ttu-id="ca8a4-121">X</span><span class="sxs-lookup"><span data-stu-id="ca8a4-121">X</span></span>            |

> [!NOTE]
> <span data-ttu-id="ca8a4-122">Javasoljuk, hogy szorosan működjön együtt a pénzügyi vezetőjével (CFO) vagy kontrollerével, hogy azonosítsa az egyes tranzakciótípusok helyes számláit az egyes tranzakciótípusokhoz, és azt is ellenőrizzék, hogy a selejtezési folyamat és az általa létrehozott tranzakciók megfelelően frissítik azokat a számlákat.</span><span class="sxs-lookup"><span data-stu-id="ca8a4-122">We recommend that you work closely with your company's chief financial officer (CFO) or controller to identify the correct accounts that should be used for each transaction type, and also to verify that the disposal process and the transactions that it generates update those accounts correctly.</span></span>

<span data-ttu-id="ca8a4-123">A tárgyi eszköz selejtezése előtt létre kell hoznia azokat a főkönyvi számlákat, amelyek a tárgyi eszköz beszerzési értékéhez, az aktuális évi értékcsökkenéshez, az előző évek értékcsökkenéséhez és az eszköz NKÉ-jéhez tartoznak.</span><span class="sxs-lookup"><span data-stu-id="ca8a4-123">Before you dispose of a fixed asset as scrap, you must create ledger accounts that are associated with the asset's acquisition value, depreciation for the current year, depreciation for previous years, and the asset's NBV.</span></span> <span data-ttu-id="ca8a4-124">A tárgyieszköz-tranzakciók típusai a **Tárgyi eszközök feladási profiljai** lapon láthatók.</span><span class="sxs-lookup"><span data-stu-id="ca8a4-124">The fixed asset transaction types are listed on the **Fixed assets posting profile** page.</span></span> <span data-ttu-id="ca8a4-125">Nyissa meg a **Tárgyi eszközök \> Beállítások \> Tárgyieszköz-feladási profilok** menüt, majd a **Selejtezés** gyorslapon válassza ki a **Selejt** lehetőséget a rács fölötti mezőben.</span><span class="sxs-lookup"><span data-stu-id="ca8a4-125">Go to **Fixed assets \> Setup \> Fixed asset posting profiles**, and then, on the **Disposal** FastTab, select **Scrap** in the field above the grid.</span></span> <span data-ttu-id="ca8a4-126">A következő ábra a tárgyieszköz-tranzakciótípusok listáját mutatja a **Tárgyieszköz-feladási profilok** oldalon.</span><span class="sxs-lookup"><span data-stu-id="ca8a4-126">The following illustration shows the list of fixed asset transaction types on the **Fixed asset posting profiles** page.</span></span>


<span data-ttu-id="ca8a4-127">[![Eszköz selejtezése selejtként, 1. ábra](./media/Fixed_asset_Disposal_scrap_scenario_1.png)](./media/Fixed_asset_Disposal_scrap_scenario_1.png)</span><span class="sxs-lookup"><span data-stu-id="ca8a4-127">[![Disposing of an asset as scap, Fig. 1](./media/Fixed_asset_Disposal_scrap_scenario_1.png)](./media/Fixed_asset_Disposal_scrap_scenario_1.png)</span></span>

<span data-ttu-id="ca8a4-128">A következő példában a tárgyi eszköz a 2018. január 1-én került beszerzésre, és azt 2019 március 31-én selejtezték le.</span><span class="sxs-lookup"><span data-stu-id="ca8a4-128">For the following example, a fixed asset was acquired on January 1, 2018, and it will be scrapped on March 31, 2019.</span></span>

- <span data-ttu-id="ca8a4-129">**Beszerzési ár:** 24 000,00 amerikai dollár (USD)</span><span class="sxs-lookup"><span data-stu-id="ca8a4-129">**Acquisition price:** 24,000.00 US dollars (USD)</span></span>
- <span data-ttu-id="ca8a4-130">**Hasznos élettartam:** Két év</span><span class="sxs-lookup"><span data-stu-id="ca8a4-130">**Service life:** Two years</span></span>
- <span data-ttu-id="ca8a4-131">**Avultatási mód:** Lineáris, élettartam szerinti értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="ca8a4-131">**Depreciation method:** Straight line service life</span></span>
- <span data-ttu-id="ca8a4-132">**Értékcsökkenés összege:** 1000,00 USD havonta</span><span class="sxs-lookup"><span data-stu-id="ca8a4-132">**Depreciation amount:** 1,000.00 USD per month</span></span>

<span data-ttu-id="ca8a4-133">A tárgyi eszköz NKÉ-je következő képlet segítségével számítható ki:</span><span class="sxs-lookup"><span data-stu-id="ca8a4-133">The NBV of a fixed asset is calculated by using the following formula:</span></span>

<span data-ttu-id="ca8a4-134">Nettó könyv szerinti érték = Beszerzési ár – értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="ca8a4-134">Net book value = Acquisition price – Depreciation</span></span>

<span data-ttu-id="ca8a4-135">Ebben a példában a tárgyi eszköz beszerzése és avultatása 15 hónapig, 2018 januárjától 2019 márciusáig tartott.</span><span class="sxs-lookup"><span data-stu-id="ca8a4-135">In this example, the fixed asset was acquired and was depreciated for 15 months, from January 2018 through March 2019.</span></span> <span data-ttu-id="ca8a4-136">Ennek megfelelően az eszköz NKÉ-je 9000,00 USD (24 000,00 USD – 15 000,00 USD).</span><span class="sxs-lookup"><span data-stu-id="ca8a4-136">Therefore, the asset's NBV is 9,000.00 USD (24,000.00 USD – 15,000.00 USD).</span></span>

<span data-ttu-id="ca8a4-137">[![Tárgyi eszköz avultatása példa](./media/Fixed_asset_Disposal_scrap_scenario_2.png)](./media/Fixed_asset_Disposal_scrap_scenario_2.png)</span><span class="sxs-lookup"><span data-stu-id="ca8a4-137">[![Fixed asset depreciation example](./media/Fixed_asset_Disposal_scrap_scenario_2.png)](./media/Fixed_asset_Disposal_scrap_scenario_2.png)</span></span>


<span data-ttu-id="ca8a4-138">A kivezetési napló létrehozásához nyissa meg a **Tárgyi eszközök \> Naplóbejegyzések \> Tárgyi eszközök naplója** lehetőséget, majd a műveleti ablaktáblán válassza a **Sorok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ca8a4-138">To create a disposal journal, go to **Fixed assets \> Journal entries \> Fixed assets journal**, and then, on the Action Pane, select **Lines**.</span></span> <span data-ttu-id="ca8a4-139">Válassza a **Kivezetés – selejt** lehetőséget, majd válassza ki a tárgyi eszköz azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="ca8a4-139">Select **Disposal – scrap**, and then select a fixed asset ID.</span></span> <span data-ttu-id="ca8a4-140">Az eszköz teljes mértékű kivezetéséhez ne írjon be értéket **Terhelés** vagy a **Jóváírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ca8a4-140">To fully dispose of the asset, don't enter a value in either the **Debit** field or the **Credit** field.</span></span>

<span data-ttu-id="ca8a4-141">[![Tárgyi eszközök naplója](./media/Fixed_asset_Disposal_scrap_scenario_3.png)](./media/Fixed_asset_Disposal_scrap_scenario_3.png)</span><span class="sxs-lookup"><span data-stu-id="ca8a4-141">[![Fixed assets journal](./media/Fixed_asset_Disposal_scrap_scenario_3.png)](./media/Fixed_asset_Disposal_scrap_scenario_3.png)</span></span>

<span data-ttu-id="ca8a4-142">A tárgyi eszközök kivezetési tranzakciója a következő módon módosítja a tárgyi eszköz könyvének mezőértékeit:</span><span class="sxs-lookup"><span data-stu-id="ca8a4-142">The fixed asset disposal scrap transaction changes the field values for the fixed asset book in the following ways:</span></span>

- <span data-ttu-id="ca8a4-143">Az **Egyenleg** szakaszban az **Állapot** mező a **selejtezettre** módosul.</span><span class="sxs-lookup"><span data-stu-id="ca8a4-143">In the **Balance** section, the **Status** field is updated to **Scrapped**.</span></span>
- <span data-ttu-id="ca8a4-144">A **Kiadás** szakaszban a **Kivezetés dátuma** mező az eszköz selejtezésének dátumát adja meg.</span><span class="sxs-lookup"><span data-stu-id="ca8a4-144">In the **Issue** section, the **Disposal date** field is set to the date when the asset was scrapped.</span></span>

<span data-ttu-id="ca8a4-145">[![Tárgyieszköz-napló részletei](./media/Fixed_asset_Disposal_scrap_scenario_4.png)](./media/Fixed_asset_Disposal_scrap_scenario_4.png)</span><span class="sxs-lookup"><span data-stu-id="ca8a4-145">[![Fixed assets journal detail](./media/Fixed_asset_Disposal_scrap_scenario_4.png)](./media/Fixed_asset_Disposal_scrap_scenario_4.png)</span></span>

<span data-ttu-id="ca8a4-146">A következő ábra a tárgyi eszköz egyenlegét jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="ca8a4-146">The following illustration shows the fixed asset balance.</span></span>

<span data-ttu-id="ca8a4-147">[![Tárgyieszköz egyenleg](./media/Fixed_asset_Disposal_scrap_scenario_5.png)](./media/Fixed_asset_Disposal_scrap_scenario_5.png)</span><span class="sxs-lookup"><span data-stu-id="ca8a4-147">[![Fixed asset balance](./media/Fixed_asset_Disposal_scrap_scenario_5.png)](./media/Fixed_asset_Disposal_scrap_scenario_5.png)</span></span>

<span data-ttu-id="ca8a4-148">A következő ábrán egy feladott bizonylat látható.</span><span class="sxs-lookup"><span data-stu-id="ca8a4-148">The following illustration shows the voucher that is posted.</span></span>

<span data-ttu-id="ca8a4-149">[![Nettó könyv szerinti érték](./media/Fixed_asset_Disposal_scrap_scenario_6.png)](./media/Fixed_asset_Disposal_scrap_scenario_6.png)</span><span class="sxs-lookup"><span data-stu-id="ca8a4-149">[![Net book value](./media/Fixed_asset_Disposal_scrap_scenario_6.png)](./media/Fixed_asset_Disposal_scrap_scenario_6.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]