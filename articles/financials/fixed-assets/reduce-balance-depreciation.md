---
title: Degresszív értékcsökkenés
description: Ez a cikk az értékcsökkenés egyenleg csökkentő módszeréről nyújt tájékoztatást.
author: ShylaThompson
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3281
ms.assetid: 1b86763d-d47c-4a6a-a9a6-d97a736750da
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2dd4a8726ca194de2e5d95128659f3b212eaace5
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840217"
---
# <a name="reduce-balance-depreciation"></a><span data-ttu-id="22311-103">Degresszív értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="22311-103">Reduce balance depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="22311-104">Ez a cikk az értékcsökkenés egyenleg csökkentő módszeréről nyújt tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="22311-104">This article gives an overview of the Reducing balance method of depreciation.</span></span>

<span data-ttu-id="22311-105">Amikor beállít egy tárgyieszköz-értékcsökkenési profilt és a Degresszív értéket választja a Mód mezőben az Értékcsökkenési profilok lapon, akkor az ehhez az értékcsökkenési profilhoz hozzárendelt tárgyi eszközök értékcsökkenése minden időszakban ugyanakkora százalékkal megy végbe.</span><span class="sxs-lookup"><span data-stu-id="22311-105">When you set up a fixed asset depreciation profile and select Reducing balance in the Method field in the Depreciation profiles page, the assets that have this depreciation profile assigned to them are depreciated by the same percentage in each depreciation period.</span></span>

<span data-ttu-id="22311-106">A degresszív értékcsökkenés beállítása esetén az Értékcsökkenési profilok képernyő Általános gyorslapján rendelkezésre álló beállításokat is meg kell adni.</span><span class="sxs-lookup"><span data-stu-id="22311-106">To set up reducing balance depreciation, you must also make selections in fields on the General FastTab of the Depreciation profiles page.</span></span> <span data-ttu-id="22311-107">Először válasszon egy évet az Értékcsökkenés éve mezőben.</span><span class="sxs-lookup"><span data-stu-id="22311-107">First, select a year in the Depreciation year field.</span></span> <span data-ttu-id="22311-108">A választástól függően az Időszak gyakorisága mezőben különböző lehetőségek közül lehet választani, ahogy az az alábbiakban egy külön szakaszban részletesen le van írva.</span><span class="sxs-lookup"><span data-stu-id="22311-108">Depending on the selection, different options appear in the Period frequency field, as explained in the following sections.</span></span> 

<span data-ttu-id="22311-109">A Százalék mezőben meg kell adni az értékcsökkenési profil értékét.</span><span class="sxs-lookup"><span data-stu-id="22311-109">You must also enter a value in the Percentage field for the depreciation profile.</span></span> <span data-ttu-id="22311-110">Ha a Teljes értékcsökkenés beállítást választja, akkor a program az utolsó értékcsökkenési időszakban a hátralevő értékcsökkenési alapot veszi, amely nagy összeg lehet.</span><span class="sxs-lookup"><span data-stu-id="22311-110">If you select the Full depreciation option, the remaining depreciation basis is taken in the last depreciation period and could be a large amount.</span></span> <span data-ttu-id="22311-111">Bizonyos országokban/régiókban nem alkalmaznak lineáris értékcsökkenést alternatív módszerként.</span><span class="sxs-lookup"><span data-stu-id="22311-111">Some countries/regions do not use a switchover to a straight line method.</span></span> <span data-ttu-id="22311-112">Alternatív értékcsökkenés olyankor lép fel, ha az alternatív értékcsökkenési módszer összege nagyobb, mint az elsődleges értékcsökkenési profil összege, akkor a rendszer az alternatív módszer összegét veszi értékcsökkenési összegnek.</span><span class="sxs-lookup"><span data-stu-id="22311-112">Switchover occurs when the alternative depreciation method amount is greater than or equal to the primary depreciation profile amount, and the depreciation amount taken is the alternative method amount.</span></span> 

<span data-ttu-id="22311-113">Mivel az eszköz értékcsökkenése a százalékos számítás alapján soha nem lesz teljes, ezért csak a Teljes értékcsökkenés beállítás alkalmazásával lehet elérni, hogy az eszköz értékcsökkenése teljes legyen.</span><span class="sxs-lookup"><span data-stu-id="22311-113">Because an asset will never be fully depreciated based on a percentage calculation, you must select the Full depreciation option to fully depreciate an asset.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="22311-114">Az értékcsökkenési év kiválasztása</span><span class="sxs-lookup"><span data-stu-id="22311-114">Select a depreciation year</span></span>
<span data-ttu-id="22311-115">Kiválaszthatja a Naptár vagy Pénzügyi elemeket az Értékcsökkenési év mezőben az Értékcsökkenési profilok lapon.</span><span class="sxs-lookup"><span data-stu-id="22311-115">You can select either Calendar or Fiscal in the Depreciation year field in the Depreciation profiles page.</span></span> <span data-ttu-id="22311-116">A kiválasztás függvényében változnak az Időszak gyakorisága mezőben elérhető beállítások.</span><span class="sxs-lookup"><span data-stu-id="22311-116">The selection defines the options that are available in the Period frequency field.</span></span> <span data-ttu-id="22311-117">Az alapértelmezett beállítás a Naptár.</span><span class="sxs-lookup"><span data-stu-id="22311-117">The default option is Calendar.</span></span>

### <a name="calendar"></a><span data-ttu-id="22311-118">Naptár</span><span class="sxs-lookup"><span data-stu-id="22311-118">Calendar</span></span>

<span data-ttu-id="22311-119">A Naptár beállítás használata esetén a rendszer minden évben január elsején frissíti az értékcsökkenés alapját, amely jellemzően a nettó könyv szerinti érték csökkentve a maradványértékkel.</span><span class="sxs-lookup"><span data-stu-id="22311-119">The Calendar option updates the depreciation base, which is typically the net book value minus the scrap value, on January 1 of each year.</span></span> <span data-ttu-id="22311-120">A fejezet későbbi részében bemutatott degresszív értékcsökkenési példában az értékcsökkenés alapja a számítási oszlopban szereplő első szám.</span><span class="sxs-lookup"><span data-stu-id="22311-120">In the reducing balance depreciation example later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="22311-121">A Naptár lehetőség választása esetén a következő beállítások állnak rendelkezésre az Időszak gyakorisága mezőben, amelyek egész évben meghatározzák az értékcsökkenés feladási időpontját és összegét:</span><span class="sxs-lookup"><span data-stu-id="22311-121">If you select Calendar, the following options are available in the Period frequency field, which defines the depreciation accrual posting dates and amounts throughout the calendar year:</span></span>

-   <span data-ttu-id="22311-122">Évente: feladás december 31-én.</span><span class="sxs-lookup"><span data-stu-id="22311-122">Yearly posts on December 31.</span></span>
-   <span data-ttu-id="22311-123">Havonta: felad egy havi összeget minden naptári hó végén.</span><span class="sxs-lookup"><span data-stu-id="22311-123">Monthly posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="22311-124">Negyedévente: Felad egy negyedéves összeget minden naptári negyedév végén (március 31., június 30., szeptember 30. és december 31.).</span><span class="sxs-lookup"><span data-stu-id="22311-124">Quarterly posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="22311-125">Félévente: féléves összeget ad fel minden naptári félév végén (június 30. és december 31.).</span><span class="sxs-lookup"><span data-stu-id="22311-125">Half-Yearly posts a half-yearly amount at the end of each calendar half-year (June 30 and December 31).</span></span>
-   <span data-ttu-id="22311-126">A Naponta lehetőséget választva minden nap feladható egy tranzakció a napi értékcsökkenés módszerrel számolt értékcsökkenés összegével.</span><span class="sxs-lookup"><span data-stu-id="22311-126">Daily posts the depreciation amount for the daily depreciation method using one transaction for each day.</span></span>

<span data-ttu-id="22311-127">Ha például az Évente beállítást választja, az éves értékcsökkenés csak egyszer, minden év december 31-én kerül feladásra.</span><span class="sxs-lookup"><span data-stu-id="22311-127">For example, if you select Yearly, the yearly depreciation is posted only one time, on December 31 of each year.</span></span> <span data-ttu-id="22311-128">Ha a Havonta beállítást választja, a havi értékcsökkenés feladása havonta történik, az éves értékcsökkenési összeg egy-tizenkettedeként.</span><span class="sxs-lookup"><span data-stu-id="22311-128">If you select Monthly, the monthly depreciation is posted each month as 1/12 of the yearly depreciation amount.</span></span>

### <a name="fiscal"></a><span data-ttu-id="22311-129">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="22311-129">Fiscal</span></span>

<span data-ttu-id="22311-130">Ha a Pénzügyi beállítást választja az Értékcsökkenés éve mezőben, akkor a lineáris értékcsökkenési módszert alkalmazza a rendszer.</span><span class="sxs-lookup"><span data-stu-id="22311-130">If you select Fiscal in the Depreciation year field, the straight line depreciation method is used.</span></span> <span data-ttu-id="22311-131">Ezt a pénzügyi év alapján számítja ki a rendszer, amelyet a Pénzügyi naptárak lapon állíthat be a Főkönyv lapon kiválasztott pénzügyi naptárhoz.</span><span class="sxs-lookup"><span data-stu-id="22311-131">It is calculated based on the fiscal year, which is set up in the Fiscal calendars page for the fiscal calendar that is selected in the Ledger page.</span></span> <span data-ttu-id="22311-132">Egy július 1-től június 30-ig tartó pénzügyi év esetén az értékcsökkenés számítása július 1-jén kezdődik.</span><span class="sxs-lookup"><span data-stu-id="22311-132">For example, for fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="22311-133">Az üzleti év 12 hónapnál hosszabb vagy rövidebb is lehet.</span><span class="sxs-lookup"><span data-stu-id="22311-133">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="22311-134">Az értékcsökkenés minden egyes pénzügyi időszak végén módosul.</span><span class="sxs-lookup"><span data-stu-id="22311-134">The depreciation is adjusted for each fiscal period.</span></span> <span data-ttu-id="22311-135">A következő pénzügyi év hossza az új pénzügyi évnek a Pénzügyi naptárak lapon való létrehozásakor beállított pénzügyi időszakoktól függ.</span><span class="sxs-lookup"><span data-stu-id="22311-135">The length of the next fiscal year is based on the fiscal periods that you set up when you create a new fiscal year in the Fiscal calendars page.</span></span>


<span data-ttu-id="22311-136">Ha a Pénzügyi beállítást választja, az alábbi opciók lesznek elérhetőek az az Időszak gyakorisága mezőben:</span><span class="sxs-lookup"><span data-stu-id="22311-136">If you select Fiscal, the following options are available in the Period frequency field:</span></span>

-   <span data-ttu-id="22311-137">Évente: az üzleti évre vonatkozó értékcsökkenés teljes összege a pénzügyi év utolsó napján, egy összegként lesz feladva.</span><span class="sxs-lookup"><span data-stu-id="22311-137">Yearly posts the total amount of the depreciation calculated for the fiscal year as one amount on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="22311-138">A Pénzügyi időszak a pénzügyi évre számított értékcsökkenés teljes összegét feladja, amelyet a Főkönyv oldalon kiválasztott pénzügyi évhez tartozó pénzügyi időszakokra összegyűjtött a rendszer, vagy egy tárgyi eszköz könyvéhez kiválasztott pénzügyi naptárra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="22311-138">Fiscal period posts the total amount of the depreciation calculated for the fiscal year, which is accrued into the fiscal periods that are defined for the fiscal calendar that is selected in the Ledger page, or for the fiscal calendar that is selected for the book for a fixed asset.</span></span>

## <a name="example-of-reducing-balance-depreciation"></a><span data-ttu-id="22311-139">Példa degresszív értékcsökkenésre</span><span class="sxs-lookup"><span data-stu-id="22311-139">Example of reducing balance depreciation</span></span>

<span data-ttu-id="22311-140">Tegyük fel, hogy a tárgyi eszköz beszerzési ára 11 000, a maradványértéke 1 000 és az értékcsökkenés százalékos tényezője 30.</span><span class="sxs-lookup"><span data-stu-id="22311-140">Suppose that the fixed asset acquisition price is 11,000, the scrap value is 1,000, and the depreciation percentage factor is 30.</span></span> 

<span data-ttu-id="22311-141">A Degresszív módszerrel az értékcsökkenés alapjának (nettó könyv szerinti érték csökkentve a maradványértékkel) a 30 százalékát számítja ki a rendszer az előző értékcsökkenési időszak végén.</span><span class="sxs-lookup"><span data-stu-id="22311-141">Using the Reducing balance method, 30 percent of the depreciation base (net book value minus scrap value) is calculated at the end of the previous depreciation period.</span></span> <span data-ttu-id="22311-142">Az alábbi tábla bemutatja az első három év értékcsökkenését.</span><span class="sxs-lookup"><span data-stu-id="22311-142">Depreciation for the first three years is shown in the following table.</span></span>

| <span data-ttu-id="22311-143">Időszak</span><span class="sxs-lookup"><span data-stu-id="22311-143">Period</span></span> | <span data-ttu-id="22311-144">Az éves értékcsökkenési összeg számítása</span><span class="sxs-lookup"><span data-stu-id="22311-144">Calculation of yearly depreciation amount</span></span> | <span data-ttu-id="22311-145">Nettó könyv szerinti érték az év végén</span><span class="sxs-lookup"><span data-stu-id="22311-145">Net book value at the end of the year</span></span> |
|--------|-------------------------------------------|---------------------------------------|
| <span data-ttu-id="22311-146">1. év</span><span class="sxs-lookup"><span data-stu-id="22311-146">Year 1</span></span> | <span data-ttu-id="22311-147">(11 000-1000) \* 30% = 3000</span><span class="sxs-lookup"><span data-stu-id="22311-147">(11,000 - 1,000) \* 30% = 3,000</span></span>           | <span data-ttu-id="22311-148">(11 000 - 1000) - 3000 = 7000</span><span class="sxs-lookup"><span data-stu-id="22311-148">(11,000 - 1,000) - 3,000 = 7,000</span></span>      |
| <span data-ttu-id="22311-149">2. év</span><span class="sxs-lookup"><span data-stu-id="22311-149">Year 2</span></span> | <span data-ttu-id="22311-150">(7000-1000) \* 30% = 1800</span><span class="sxs-lookup"><span data-stu-id="22311-150">(7,000 - 1,000) \* 30% = 1,800</span></span>            | <span data-ttu-id="22311-151">(7000 -1800) = 5200</span><span class="sxs-lookup"><span data-stu-id="22311-151">(7,000 -1,800) = 5,200</span></span>                |
| <span data-ttu-id="22311-152">3. év</span><span class="sxs-lookup"><span data-stu-id="22311-152">Year 3</span></span> | <span data-ttu-id="22311-153">(5200-1000) \* 30% = 1260</span><span class="sxs-lookup"><span data-stu-id="22311-153">(5,200 - 1,000) \* 30% = 1,260</span></span>            | <span data-ttu-id="22311-154">(5200 - 1260) = 3940</span><span class="sxs-lookup"><span data-stu-id="22311-154">(5,200 - 1,260) = 3,940</span></span>               |


-





