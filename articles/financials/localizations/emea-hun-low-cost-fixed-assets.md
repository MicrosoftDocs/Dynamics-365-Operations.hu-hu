---
title: Kis értékű tárgyi eszközök
description: Ez a témakör a Magyarországon használt kis értékű tárgyi eszközökhöz tartalmaz információt.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 10/31/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 264684
ms.search.region: Hungary
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 85ca328013fdf276d770cdc12355eb37652d056d
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571204"
---
# <a name="low-cost-fixed-assets"></a><span data-ttu-id="625d5-103">Kis értékű tárgyi eszközök</span><span class="sxs-lookup"><span data-stu-id="625d5-103">Low-cost fixed assets</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="625d5-104">Ez a témakör a Magyarországon használt kis értékű tárgyi eszközökhöz tartalmaz információt.</span><span class="sxs-lookup"><span data-stu-id="625d5-104">This topic provides information about low-cost fixed assets for Hungary.</span></span>

<span data-ttu-id="625d5-105">A kis értékű tárgyi eszköz olyan eszköz, amelynek a beszerzési költsége nem halad meg egy előre meghatározott összeget.</span><span class="sxs-lookup"><span data-stu-id="625d5-105">A low-cost asset is an asset for which the acquisition cost doesn't exceed a predefined amount.</span></span> <span data-ttu-id="625d5-106">A magyar adójog meghatározza a kis értékű tárgyi eszközök összeghatárát (küszöbértékét).</span><span class="sxs-lookup"><span data-stu-id="625d5-106">Hungarian tax law defines the limit (threshold) for low-cost assets.</span></span> <span data-ttu-id="625d5-107">Ezek az eszközök teljes mértékben leírhatók a beszerzéssel egy időben.</span><span class="sxs-lookup"><span data-stu-id="625d5-107">These assets can be fully depreciated at the same time that they are acquired.</span></span>

## <a name="set-up-the-low-cost-asset-threshold"></a><span data-ttu-id="625d5-108">A kis értékű tárgyi eszköz küszöbértékének beállítása</span><span class="sxs-lookup"><span data-stu-id="625d5-108">Set up the low-cost asset threshold</span></span>

<span data-ttu-id="625d5-109">A kis értékű tárgyi eszköz küszöbértékének beállításához kattintson a **Tárgyi eszközök** &gt; **Beállítás** &gt; **Tárgyi eszközök paraméterei** elemre.</span><span class="sxs-lookup"><span data-stu-id="625d5-109">To set up the limit for low-cost assets, click **Fixed assets** &gt; **Setup** &gt; **Fixed assets parameters**.</span></span> <span data-ttu-id="625d5-110">Ezután a **Kis értékű tárgyi eszköz küszöbértéke** mezőjébe írja be a kis értékű tárgyi eszközök értékhatárát.</span><span class="sxs-lookup"><span data-stu-id="625d5-110">Then, in the **Low-cost asset threshold** field, enter the value limit for low-cost assets.</span></span>

## <a name="set-up-books-for-low-cost-fixed-assets"></a><span data-ttu-id="625d5-111">Könyvek beállítása a kis értékű tárgyi eszközökhöz</span><span class="sxs-lookup"><span data-stu-id="625d5-111">Set up books for low-cost fixed assets</span></span>

<span data-ttu-id="625d5-112">Amikor beszerzési tranzakciót hoz létre egy olyan eszközhöz, amely a kis értékű tárgyi eszközök könyvét használja, az értékcsökkenés automatikusan létrejön.</span><span class="sxs-lookup"><span data-stu-id="625d5-112">When you create an acquisition transaction for an asset that uses the book for low-cost assets, depreciation is generated automatically.</span></span>

1.  <span data-ttu-id="625d5-113">Kattintson a **Tárgyi eszközök** &gt; **Beállítás** &gt; **Könyvek** elemre.</span><span class="sxs-lookup"><span data-stu-id="625d5-113">Click **Fixed assets** &gt; **Setup** &gt; **Books**.</span></span>
2.  <span data-ttu-id="625d5-114">Válassza ki a kis értékű tárgyi eszközökhöz használandó könyvet, majd jelölje be a **Kis értékű tárgyi eszköz** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="625d5-114">Select the book for low-cost assets, and select the **Low-cost asset** check box.</span></span>

<span data-ttu-id="625d5-115">**Megjegyzés:** a kis értékű értékcsökkenéshez csak a „Kézi” vagy „Lineáris - élettartam” értékcsökkenési profilokat/globális módszereket használó értékmodellek, illetve a Magyarország-specifikus „Lineáris (Hu)” módszer áll rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="625d5-115">**Note:** Only value models that use the "Manual" or "Straight line service life" depreciation profiles/global methods, or the Hungary-specific "Straight line (Hu)" method, are available for low-cost depreciation.</span></span>

## <a name="generate-acquisition-and-depreciation-transactions-for-low-cost-fixed-assets"></a><span data-ttu-id="625d5-116">Beszerzési és értékcsökkenési tranzakciók létrehozása kis értékű tárgyi eszközökhöz</span><span class="sxs-lookup"><span data-stu-id="625d5-116">Generate acquisition and depreciation transactions for low-cost fixed assets</span></span>

<span data-ttu-id="625d5-117">Eszköz megszerzésekor egy beszerzési tranzakciót hoz létre a beszerzést megelőző tranzakcióból.</span><span class="sxs-lookup"><span data-stu-id="625d5-117">When you acquire an asset, you create an acquisition transaction from the pre-acquisition transaction.</span></span> <span data-ttu-id="625d5-118">Amikor feladja a kis értékű tárgyi eszköz beszerzési tranzakcióját, az értékcsökkenési tranzakció automatikusan létrejön.</span><span class="sxs-lookup"><span data-stu-id="625d5-118">When you post the acquisition transaction for a low-cost asset, the depreciation transaction is generated automatically.</span></span>



