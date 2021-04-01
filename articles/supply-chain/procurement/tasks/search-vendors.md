---
title: Szállítók keresése
description: Útmutató a szállítók meghatározott feltételek alapján történő kereséhez.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendSearchCriterion, VendSearchAddCategory, VendSearchAddReviewCriterionGroup, VendSearchResults, VendSearchAddReviewCriterion
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cf93307600aac6fa6e45524092ec4811742010e4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5244039"
---
# <a name="search-for-vendors"></a><span data-ttu-id="b8b95-103">Szállítók keresése</span><span class="sxs-lookup"><span data-stu-id="b8b95-103">Search for vendors</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b8b95-104">Útmutató a szállítók meghatározott feltételek alapján történő kereséhez.</span><span class="sxs-lookup"><span data-stu-id="b8b95-104">Learn how to search for vendors based on specific criteria.</span></span> <span data-ttu-id="b8b95-105">Ez a példa bemutatja, hogyan lehet olyan szállítókat keresni, amelyek egy adott beszerzési kategóriához jóváhagyottak, és az elsődleges címük egy adott országban van.</span><span class="sxs-lookup"><span data-stu-id="b8b95-105">This example shows you how to search for vendors that are approved for a particular procurement category and have their primary address in a specific country.</span></span> <span data-ttu-id="b8b95-106">Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja.</span><span class="sxs-lookup"><span data-stu-id="b8b95-106">You can run this procedure in demo data company USMF, or on your own data.</span></span> <span data-ttu-id="b8b95-107">Ezt a feladatot általában egy beszerzési szakember végzi el.</span><span class="sxs-lookup"><span data-stu-id="b8b95-107">This task would usually be carried out by a procurement professional.</span></span>

1. <span data-ttu-id="b8b95-108">Ugorjon a Beszerzés és forrás > Szállítók > Szállítók keresése elemre.</span><span class="sxs-lookup"><span data-stu-id="b8b95-108">Go to Procurement and sourcing > Vendors > Vendor search.</span></span>
2. <span data-ttu-id="b8b95-109">Kattintson a pluszjelre a Beszerzési kategória választó oldal megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="b8b95-109">Click on the Plus icon to open the Procurement category selection page.</span></span>  
3. <span data-ttu-id="b8b95-110">A fán válassza a „CORP PROCUREMENT CATEGORIES\OFFICE MACHINES” pontot.</span><span class="sxs-lookup"><span data-stu-id="b8b95-110">In the tree, select 'CORP PROCUREMENT CATEGORIES\OFFICE MACHINES'.</span></span>
    * <span data-ttu-id="b8b95-111">Ha a folyamatot feladat-útmutatóként használja, szükség lehet a Zárolás feloldása gombra, mielőtt a helyes csomópontot kiválaszthatja.</span><span class="sxs-lookup"><span data-stu-id="b8b95-111">If you're running this procedure as a task guide, you may have to click the Unlock button before you can select the correct node.</span></span> <span data-ttu-id="b8b95-112">Ha nem használ USMF-et, válassza a meglévő kategóriák egyikét.</span><span class="sxs-lookup"><span data-stu-id="b8b95-112">If you're not using USMF, select one of the categories that you have.</span></span>  
4. <span data-ttu-id="b8b95-113">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="b8b95-113">Click Add.</span></span>
    * <span data-ttu-id="b8b95-114">Itt egynél több kategóriát is kiválaszthat.</span><span class="sxs-lookup"><span data-stu-id="b8b95-114">It's possible to select more than one category here.</span></span> <span data-ttu-id="b8b95-115">Ha ezt teszi, a keresés megtalálja a kategóriák közül legalább egyhez engedélyezett szállítókat.</span><span class="sxs-lookup"><span data-stu-id="b8b95-115">If you do so, the search will find all the vendors that are approved for at least one of the categories.</span></span>  
5. <span data-ttu-id="b8b95-116">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b8b95-116">Click OK.</span></span>
6. <span data-ttu-id="b8b95-117">Írjon be egy értéket az Ország/régió mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b8b95-117">In the Country/region field, type a value.</span></span>
7. <span data-ttu-id="b8b95-118">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b8b95-118">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]