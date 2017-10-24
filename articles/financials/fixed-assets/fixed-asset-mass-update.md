---
title: "Tárgyi eszközök tömeges módosítása"
description: "Ha könyveket használ, akkor egyszerre módosíthatja azoknak az eszközcsoportoknak az értékcsökkenési szabályát, amelyek ugyanahhoz a könyvhöz tartoznak."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3521
ms.assetid: 50207ffb-6b89-4fb9-92e9-928bc0729489
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c04997ccc29182f0f403af0e4ad5f039dbd4ae60
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="fixed-asset-mass-update"></a><span data-ttu-id="576df-103">Tárgyi eszközök tömeges módosítása</span><span class="sxs-lookup"><span data-stu-id="576df-103">Fixed asset mass update</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="576df-104">Ha könyveket használ, akkor egyszerre módosíthatja azoknak az eszközcsoportoknak az értékcsökkenési szabályát, amelyek ugyanahhoz a könyvhöz tartoznak.</span><span class="sxs-lookup"><span data-stu-id="576df-104">If you use books, you can change the depreciation conventions for groups of assets that are part of the same book.</span></span>

<span data-ttu-id="576df-105">Például ha az Egyesült Államokban tevékenykedik, és a tárgyi eszközök 40 százalékát az év utolsó negyedévében helyezte üzembe, akkor a negyedéven belüli értékcsökkenés szabályát kell alkalmaznia.</span><span class="sxs-lookup"><span data-stu-id="576df-105">For example, if you are in the United States, and you put more than 40 percent of your assets in service during the fourth quarter of the year, you must use the mid-quarter depreciation convention.</span></span> <span data-ttu-id="576df-106">A tömeges frissítés segítségével minden eszközt módosíthat, amelynek értékcsökkenését az új szabály szerint kell elszámolni.</span><span class="sxs-lookup"><span data-stu-id="576df-106">You can use the process for a mass update to change all assets that require the new depreciation convention.</span></span> 

<span data-ttu-id="576df-107">Ha frissíti a tárgyi eszközök értékcsökkenési szabályát, akkor ezzel törli ezen eszközök minden értékcsökkenési tranzakcióját.</span><span class="sxs-lookup"><span data-stu-id="576df-107">When you update the depreciation convention for assets, you delete all depreciation transactions that exist for those assets.</span></span> <span data-ttu-id="576df-108">Emellett ezen eszközökre vonatkozóan törli az összes értékcsökkenési helyesbítés tranzakcióit, és a rendkívüli értékcsökkenési tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="576df-108">You also delete all transactions for depreciation adjustments, transactions for bonus depreciation, and transactions for extraordinary depreciation for those assets.</span></span> 

<span data-ttu-id="576df-109">A már kivezetett eszközök értékcsökkenési szabályának frissítéséhez először törölni kell a meglévő kivezetési tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="576df-109">To update the depreciation convention for assets that have already been disposed of, you must first delete the existing disposal transactions.</span></span> <span data-ttu-id="576df-110">Emellett illetve a kivezetés következtében létrejött egyéb tranzakciókat is törölni kell.</span><span class="sxs-lookup"><span data-stu-id="576df-110">You must also delete all transactions that were generated because of the disposal process.</span></span> 

<span data-ttu-id="576df-111">Az eszközök értékcsökkenési szabályainak frissítése után elszámolhatja az egyes eszközök rendes és soronkívüli értékcsökkenését.</span><span class="sxs-lookup"><span data-stu-id="576df-111">After you update the depreciation convention for assets, you can process depreciation and extraordinary depreciation for each asset.</span></span> <span data-ttu-id="576df-112">Emellett szükség esetén elvégezheti a manuális korrekciókat is.</span><span class="sxs-lookup"><span data-stu-id="576df-112">You can also make manual depreciation adjustments, if any adjustments are required.</span></span>





