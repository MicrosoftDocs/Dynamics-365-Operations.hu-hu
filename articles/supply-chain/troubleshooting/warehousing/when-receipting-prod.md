---
title: Egyetlen nyugta több munkafejlécéhez csak egy címke van nyomtatva
description: Egyetlen nyugta több munkafejlécéhez csak egy címke van nyomtatva.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSLicensePlateLabel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 8e11dc918eb3c9085018d15b43819522cc8bebe3
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026574"
---
# <a name="only-one-label-is-printed-for-multiple-work-headers-on-a-single-receipt"></a><span data-ttu-id="e4f19-103">Egyetlen nyugta több munkafejlécéhez csak egy címke van nyomtatva</span><span class="sxs-lookup"><span data-stu-id="e4f19-103">Only one label is printed for multiple work headers on a single receipt</span></span>

<span data-ttu-id="e4f19-104">Tudásbáziscikk száma: 4614667</span><span class="sxs-lookup"><span data-stu-id="e4f19-104">KB number: 4614667</span></span>

## <a name="symptoms"></a><span data-ttu-id="e4f19-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="e4f19-105">Symptoms</span></span>

<span data-ttu-id="e4f19-106">Több munkafejléc jön létre ugyanahhoz a cél azonosítótáblához egy raktári alkalmazás bevételi eseményeként.</span><span class="sxs-lookup"><span data-stu-id="e4f19-106">Multiple work headers are created for the same target license plate as part of a single warehouse app receiving event.</span></span> <span data-ttu-id="e4f19-107">Ugyanakkor a termék érkezésekor, csak egy táblacímke kerül nyomtatásra.</span><span class="sxs-lookup"><span data-stu-id="e4f19-107">However, only one license plate label is printed when the product is received.</span></span>

## <a name="resolution"></a><span data-ttu-id="e4f19-108">Felbontás</span><span class="sxs-lookup"><span data-stu-id="e4f19-108">Resolution</span></span>

<span data-ttu-id="e4f19-109">A rendszer úgy viselkedik, ahogy tervezték.</span><span class="sxs-lookup"><span data-stu-id="e4f19-109">The system is behaving as designed.</span></span>

<span data-ttu-id="e4f19-110">A jelenlegi kialakításban mindig egyetlen táblacímke jön létre, függetlenül a meglévő munkafejléc- és munkasorkombinációk számától.</span><span class="sxs-lookup"><span data-stu-id="e4f19-110">In the current design, a single license plate label is always generated, regardless of the number of work header and work line combinations that exist.</span></span> <span data-ttu-id="e4f19-111">A létrehozott címke csak egy kombináció adatait tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="e4f19-111">The generated label includes the information for only one combination.</span></span>

<span data-ttu-id="e4f19-112">A probléma megoldásához győződjön meg róla, hogy a munkafejléc létrehozása mindig csak egy célt azonosítótáblához van hozzárendelve.</span><span class="sxs-lookup"><span data-stu-id="e4f19-112">To work around this issue, make sure that work header creation is always mapped to just one target license plate.</span></span>
