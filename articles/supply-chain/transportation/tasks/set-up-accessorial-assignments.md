--- 
title: "Kiegészítő szolgáltatási megbízások beállítása"
description: "Ez az eljárás bemutatja, hogyan állíthat be kiegészítő szolgáltatást."
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 31787aa180639b934b837b98dc170070d33fd56f
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-accessorial-assignments"></a><span data-ttu-id="405d1-103">Kiegészítő szolgáltatási megbízások beállítása</span><span class="sxs-lookup"><span data-stu-id="405d1-103">Set up accessorial assignments</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="405d1-104">Ez az eljárás bemutatja, hogyan állíthat be kiegészítő szolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="405d1-104">This procedure shows how to set up an accessorial assignment.</span></span> <span data-ttu-id="405d1-105">Ezt általában egy szállítási koordinátor végzi.</span><span class="sxs-lookup"><span data-stu-id="405d1-105">This is typically done by a transportation coordinator.</span></span> <span data-ttu-id="405d1-106">Az útmutató használata előtt futassa le a „Központi kiegészítő szolgáltatások díjainak és kiegészítő alaptermékek beállítása” útmutatót.</span><span class="sxs-lookup"><span data-stu-id="405d1-106">Before you use this guide you need to run the "Set up hub accessorial charges and accessorial masters" guide.</span></span>


## <a name="set-up-accessorial-assignment"></a><span data-ttu-id="405d1-107">Kiegészítő szolgáltatás beállítása</span><span class="sxs-lookup"><span data-stu-id="405d1-107">Set up Accessorial assignment</span></span>
1. <span data-ttu-id="405d1-108">Ugorjon a Szállításkezelés > Beállítás > Minősítés > Kiegészítő szolgáltatások lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="405d1-108">Go to Transportation management > Setup > Rating > Accessorial assignments.</span></span>
2. <span data-ttu-id="405d1-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="405d1-109">Click New.</span></span>
3. <span data-ttu-id="405d1-110">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="405d1-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="405d1-111">Bontsa ki a Részletek részt.</span><span class="sxs-lookup"><span data-stu-id="405d1-111">Toggle the expansion of the Details section.</span></span>
5. <span data-ttu-id="405d1-112">A Központ mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="405d1-112">In the Hub field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="405d1-113">A listában válassza ki a Központot, amely számára létrehozta a kiegészítő alaptermékeket a „Központi kiegészítő szolgáltatások díjainak és kiegészítő alaptermékek beállítása” útmutató futtatásakor.</span><span class="sxs-lookup"><span data-stu-id="405d1-113">In the list, select the Hub that you created an accessorial master for when you ran the "Set up hub accessorial charges and accessorial masters" guide.</span></span> 
7. <span data-ttu-id="405d1-114">A Központi kiegészítő szolgáltatás azonosítója mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="405d1-114">In the Hub accessorial ID field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="405d1-115">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="405d1-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="405d1-116">Bontsa ki a Feltételek részt.</span><span class="sxs-lookup"><span data-stu-id="405d1-116">Toggle the expansion of the Criteria section.</span></span>
    * <span data-ttu-id="405d1-117">A Kritériumok részben kiválaszthatja a pontos kritériumot a költség alkalmazására az itt felkínált különböző lehetőségek alapján.</span><span class="sxs-lookup"><span data-stu-id="405d1-117">In the Criteria section you can choose the exact criteria for when the charge should apply, based on the different values offered here.</span></span>  
10. <span data-ttu-id="405d1-118">Állítsa a Mindig alkalmazza lehetőséget Igenre.</span><span class="sxs-lookup"><span data-stu-id="405d1-118">Set the Always apply option to Yes.</span></span>
11. <span data-ttu-id="405d1-119">Válasszon ki egy lehetőséget a Kiegészítő szolgáltatás társítási szintje mezőben.</span><span class="sxs-lookup"><span data-stu-id="405d1-119">In the Accessorial assignment level field, select an option.</span></span>
12. <span data-ttu-id="405d1-120">Bontsa ki a Számítás részt.</span><span class="sxs-lookup"><span data-stu-id="405d1-120">Toggle the expansion of the Calculation section.</span></span>
13. <span data-ttu-id="405d1-121">A Kiegészítő szolgáltatás díja mezőben válassza ki a „Fix” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="405d1-121">In the Accessorial fee type field, select 'Flat'.</span></span>
    * <span data-ttu-id="405d1-122">A Kiegészítő díj típusa határozza meg, hogy hogyan kell kiszámítani a tényleges költséget.</span><span class="sxs-lookup"><span data-stu-id="405d1-122">The Accessorial fee type determines how to calculate the actual charge.</span></span> <span data-ttu-id="405d1-123">Ebben a példában fix költségről van szó.</span><span class="sxs-lookup"><span data-stu-id="405d1-123">In this example it's a flat charge.</span></span>  
14. <span data-ttu-id="405d1-124">A Kiegészítő szolgáltatás díja mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="405d1-124">In the Accessorial fee field, enter a number.</span></span>
15. <span data-ttu-id="405d1-125">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="405d1-125">Click Save.</span></span>

