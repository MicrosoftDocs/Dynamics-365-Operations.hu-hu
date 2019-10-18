---
title: Tárgyi eszközök tömeges módosítása
description: Ha könyveket használ, akkor egyszerre módosíthatja azoknak az eszközcsoportoknak az értékcsökkenési szabályát, amelyek ugyanahhoz a könyvhöz tartoznak.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3521
ms.assetid: 50207ffb-6b89-4fb9-92e9-928bc0729489
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 30b9aaaabcac09c9147c350422924a23f785c0ce
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178077"
---
# <a name="fixed-asset-mass-update"></a><span data-ttu-id="c5508-103">Tárgyi eszközök tömeges módosítása</span><span class="sxs-lookup"><span data-stu-id="c5508-103">Fixed asset mass update</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c5508-104">Ha könyveket használ, akkor egyszerre módosíthatja azoknak az eszközcsoportoknak az értékcsökkenési szabályát, amelyek ugyanahhoz a könyvhöz tartoznak.</span><span class="sxs-lookup"><span data-stu-id="c5508-104">If you use books, you can change the depreciation conventions for groups of assets that are part of the same book.</span></span>

<span data-ttu-id="c5508-105">Például ha az Egyesült Államokban tevékenykedik, és a tárgyi eszközök 40 százalékát az év utolsó negyedévében helyezte üzembe, akkor a negyedéven belüli értékcsökkenés szabályát kell alkalmaznia.</span><span class="sxs-lookup"><span data-stu-id="c5508-105">For example, if you are in the United States, and you put more than 40 percent of your assets in service during the fourth quarter of the year, you must use the mid-quarter depreciation convention.</span></span> <span data-ttu-id="c5508-106">A tömeges frissítés segítségével minden eszközt módosíthat, amelynek értékcsökkenését az új szabály szerint kell elszámolni.</span><span class="sxs-lookup"><span data-stu-id="c5508-106">You can use the process for a mass update to change all assets that require the new depreciation convention.</span></span> 

<span data-ttu-id="c5508-107">Ha frissíti a tárgyi eszközök értékcsökkenési szabályát, akkor ezzel törli ezen eszközök minden értékcsökkenési tranzakcióját.</span><span class="sxs-lookup"><span data-stu-id="c5508-107">When you update the depreciation convention for assets, you delete all depreciation transactions that exist for those assets.</span></span> <span data-ttu-id="c5508-108">Emellett ezen eszközökre vonatkozóan törli az összes értékcsökkenési helyesbítés tranzakcióit, és a rendkívüli értékcsökkenési tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="c5508-108">You also delete all transactions for depreciation adjustments, transactions for bonus depreciation, and transactions for extraordinary depreciation for those assets.</span></span> 

<span data-ttu-id="c5508-109">A már kivezetett eszközök értékcsökkenési szabályának frissítéséhez először törölni kell a meglévő kivezetési tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="c5508-109">To update the depreciation convention for assets that have already been disposed of, you must first delete the existing disposal transactions.</span></span> <span data-ttu-id="c5508-110">Emellett illetve a kivezetés következtében létrejött egyéb tranzakciókat is törölni kell.</span><span class="sxs-lookup"><span data-stu-id="c5508-110">You must also delete all transactions that were generated because of the disposal process.</span></span> 

<span data-ttu-id="c5508-111">Az eszközök értékcsökkenési szabályainak frissítése után elszámolhatja az egyes eszközök rendes és soronkívüli értékcsökkenését.</span><span class="sxs-lookup"><span data-stu-id="c5508-111">After you update the depreciation convention for assets, you can process depreciation and extraordinary depreciation for each asset.</span></span> <span data-ttu-id="c5508-112">Emellett szükség esetén elvégezheti a manuális korrekciókat is.</span><span class="sxs-lookup"><span data-stu-id="c5508-112">You can also make manual depreciation adjustments, if any adjustments are required.</span></span>





