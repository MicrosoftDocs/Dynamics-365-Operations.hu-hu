--- 
title: "Cikkek újbóli felosztására vonatkozó szabályok rövid kitárolásának beállítása"
description: "Ez az eljárás bemutatja, hogyan engedélyezze a raktári dolgozók számára az alternatív helyek gyorsan megtalálását, ha nincs elegendő készlet a helyen, ahová átirányították őket."
author: YuyuScheller
manager: AnnBe
ms.date: 10/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b67965b6c8641b5d91ab3c5b0a7a7fd28a07cba6
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-short-picking-item-reallocation"></a><span data-ttu-id="e782a-103">Cikkek újbóli felosztására vonatkozó szabályok rövid kitárolásának beállítása</span><span class="sxs-lookup"><span data-stu-id="e782a-103">Set up short picking item reallocation</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e782a-104">Ez az eljárás bemutatja, hogyan engedélyezze a raktári dolgozók számára az alternatív helyek gyorsan megtalálását, ha nincs elegendő készlet a helyen, ahová átirányították őket.</span><span class="sxs-lookup"><span data-stu-id="e782a-104">This procedure shows you how to enable warehouse workers to quickly find alternative locations if there isn’t sufficient inventory at the location they’ve been directed to.</span></span> <span data-ttu-id="e782a-105">Lehetőség van automatikus újbóli felosztási folyamat használatára, amely helyirányelvek segítségével teszi lehetővé áruk lekérését, ha elérhetők egy másik helyen.</span><span class="sxs-lookup"><span data-stu-id="e782a-105">It’s possible to use an automatic re-allocation process, which uses location directives to retrieve the goods if they’re available at another location.</span></span> <span data-ttu-id="e782a-106">Ha engedélyezve van a manuális újbóli felosztás, a mobileszközön megjelenik a helyek listája az elérhető mennyiségekkel, lehetővé téve a raktáros számára annak a kiválasztását, hogy melyik helyről szeretné használni a készletet.</span><span class="sxs-lookup"><span data-stu-id="e782a-106">Alternatively, when manual re-allocation is used, a list of the locations with the available quantity is shown on the mobile device, allowing the warehouse worker to choose which location to use inventory from.</span></span> <span data-ttu-id="e782a-107">Az USMF bemutatócég adataiban használhatja ezt az eljárást.</span><span class="sxs-lookup"><span data-stu-id="e782a-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="e782a-108">Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.</span><span class="sxs-lookup"><span data-stu-id="e782a-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="set-up-work-exceptions"></a><span data-ttu-id="e782a-109">Munkakivételek beállítása</span><span class="sxs-lookup"><span data-stu-id="e782a-109">Set up work exceptions</span></span>
1. <span data-ttu-id="e782a-110">Ugrás a Raktárkezelés > Beállítás > Munka > Munkakivételek elemre.</span><span class="sxs-lookup"><span data-stu-id="e782a-110">Go to Warehouse management > Setup > Work > Work exceptions.</span></span>
2. <span data-ttu-id="e782a-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e782a-111">Click New.</span></span>
    * <span data-ttu-id="e782a-112">Lehetőség van több munkakivétel meghatározására eltérő cikkfelosztási irányelvekkel, amelyek lehetővé teszik, hogy a raktáros válasszon egyet a feldolgozott szállítmány szükségletei szerint.</span><span class="sxs-lookup"><span data-stu-id="e782a-112">It’s possible to define several work exceptions with different item reallocation policies to enable the warehouse worker to choose one based on the needs of the shipment that they are processing.</span></span>  
3. <span data-ttu-id="e782a-113">Írjon be egy értéket a Munkakivételkód mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e782a-113">In the Work exception code field, type a value.</span></span>
    * <span data-ttu-id="e782a-114">Adjon olyan címet a munkakivételnek, amelyik arra utal, hogy mire használják.</span><span class="sxs-lookup"><span data-stu-id="e782a-114">Give the work exception a title to indicate what it’s used for.</span></span> <span data-ttu-id="e782a-115">Például: Rövid kitárolási kézikönyv.</span><span class="sxs-lookup"><span data-stu-id="e782a-115">For example, Short picking manual.</span></span>  
4. <span data-ttu-id="e782a-116">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="e782a-116">In the Description field, type a value.</span></span>
5. <span data-ttu-id="e782a-117">A Kivételtípus mezőben válassza ki a „Rövid kitárolás” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e782a-117">In the Exception type field, select 'Short pick'.</span></span>
6. <span data-ttu-id="e782a-118">Jelölje be a Készlethelyesbítés jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="e782a-118">Select the Adjust inventory check box.</span></span>
    * <span data-ttu-id="e782a-119">Ez a beállítás azt jelenti, hogy automatikusan megtörténik a készlet helyesbítése 0-ra a rövid kitárolás helyén.</span><span class="sxs-lookup"><span data-stu-id="e782a-119">This option means that inventory will automatically be adjusted to 0 at the short picked location.</span></span>  
7. <span data-ttu-id="e782a-120">Adjon meg vagy válasszon ki egy értéket az Alapértelmezett helyesbítéstípus-kód mezőben.</span><span class="sxs-lookup"><span data-stu-id="e782a-120">In the Default adjustment type code field, enter or select a value.</span></span>
    * <span data-ttu-id="e782a-121">Az USMF esetében például kiválasztható a következő: „Remove Res Adj Out”.</span><span class="sxs-lookup"><span data-stu-id="e782a-121">For example, in USMF you can select 'Remove Res Adj Out'.</span></span>  
8. <span data-ttu-id="e782a-122">A Cikk újbóli felosztása mezőben válassza ki a „Manuális” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e782a-122">In the Item reallocation field, select 'Manual'.</span></span>
    * <span data-ttu-id="e782a-123">Ha bejelöli a manuális, vagy az automatikus és manuális lehetőséget, a raktáros számára engedélyezni kell a manuális újbóli felosztást.</span><span class="sxs-lookup"><span data-stu-id="e782a-123">If you select Manual, or Automatic and Manual, the warehouse worker needs to be enabled to use manual reallocation.</span></span>  

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a><span data-ttu-id="e782a-124">A dolgozó beállítása a manuális cikk-újbólifelosztás használatára</span><span class="sxs-lookup"><span data-stu-id="e782a-124">Set up a worker to use manual item reallocation</span></span>
1. <span data-ttu-id="e782a-125">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e782a-125">Close the page.</span></span>
2. <span data-ttu-id="e782a-126">Ugrás a Raktárkezelés > Beállítás > Dolgozó elemre.</span><span class="sxs-lookup"><span data-stu-id="e782a-126">Go to Warehouse management > Setup > Worker.</span></span>
3. <span data-ttu-id="e782a-127">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e782a-127">Click Edit.</span></span>
4. <span data-ttu-id="e782a-128">A listában válassza a 24. dolgozó elemet.</span><span class="sxs-lookup"><span data-stu-id="e782a-128">In the list, select worker 24.</span></span>
5. <span data-ttu-id="e782a-129">Bontsa ki a Dolgozó szakaszt.</span><span class="sxs-lookup"><span data-stu-id="e782a-129">Expand the Work section.</span></span>
6. <span data-ttu-id="e782a-130">Válassza ki az Igen lehetőséget a Cikk újbóli manuális felosztásának engedélyezése mezőben.</span><span class="sxs-lookup"><span data-stu-id="e782a-130">Select Yes in the Allow manual item reallocation field.</span></span>

