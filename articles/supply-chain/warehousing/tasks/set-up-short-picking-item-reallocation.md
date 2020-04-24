---
title: Cikkek újbóli felosztására vonatkozó szabályok rövid kitárolásának beállítása
description: Ez az eljárás bemutatja, hogyan engedélyezze a raktári dolgozók számára az alternatív helyek gyorsan megtalálását, ha nincs elegendő készlet a helyen, ahová átirányították őket.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e860a54c2306f8140947b77cdcb538160a84e06f
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216805"
---
# <a name="set-up-short-picking-item-reallocation"></a><span data-ttu-id="daf83-103">Rövid kitárolásra jelölt cikkek újbóli felosztásának beállítása</span><span class="sxs-lookup"><span data-stu-id="daf83-103">Set up short picking item reallocation</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="daf83-104">Ez az eljárás bemutatja, hogyan engedélyezze a raktári dolgozók számára az alternatív helyek gyorsan megtalálását, ha nincs elegendő készlet a helyen, ahová átirányították őket.</span><span class="sxs-lookup"><span data-stu-id="daf83-104">This procedure shows you how to enable warehouse workers to quickly find alternative locations if there isn't sufficient inventory at the location they've been directed to.</span></span> <span data-ttu-id="daf83-105">Lehetőség van automatikus újbóli felosztási folyamat használatára, amely helyirányelvek segítségével teszi lehetővé áruk lekérését, ha elérhetők egy másik helyen.</span><span class="sxs-lookup"><span data-stu-id="daf83-105">It's possible to use an automatic re-allocation process, which uses location directives to retrieve the goods if they're available at another location.</span></span> <span data-ttu-id="daf83-106">Ha engedélyezve van a manuális újbóli felosztás, a mobileszközön megjelenik a helyek listája az elérhető mennyiségekkel, lehetővé téve a raktáros számára annak a kiválasztását, hogy melyik helyről szeretné használni a készletet.</span><span class="sxs-lookup"><span data-stu-id="daf83-106">Alternatively, when manual re-allocation is used, a list of the locations with the available quantity is shown on the mobile device, allowing the warehouse worker to choose which location to use inventory from.</span></span> <span data-ttu-id="daf83-107">Az USMF bemutatócég adataiban használhatja ezt az eljárást.</span><span class="sxs-lookup"><span data-stu-id="daf83-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="daf83-108">Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.</span><span class="sxs-lookup"><span data-stu-id="daf83-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="set-up-work-exceptions"></a><span data-ttu-id="daf83-109">Munkakivételek beállítása</span><span class="sxs-lookup"><span data-stu-id="daf83-109">Set up work exceptions</span></span>
1. <span data-ttu-id="daf83-110">A **Navigációs ablaktáblán** ugorjon a **Raktárkezelés > Beállítás > Munka > Munkakivételek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="daf83-110">In the **Navigation pane**, go to **Warehouse management > Setup > Work > Work exceptions**.</span></span>
2. <span data-ttu-id="daf83-111">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="daf83-111">Click **New**.</span></span> <span data-ttu-id="daf83-112">Lehetőség van több munkakivétel meghatározására eltérő cikkfelosztási irányelvekkel, amelyek lehetővé teszik, hogy a raktáros válasszon egyet a feldolgozott szállítmány szükségletei szerint.</span><span class="sxs-lookup"><span data-stu-id="daf83-112">It's possible to define several work exceptions with different item reallocation policies to enable the warehouse worker to choose one based on the needs of the shipment that they are processing.</span></span>  
3. <span data-ttu-id="daf83-113">Adjon meg egy értéket a **Munkakivételkód** mezőben.</span><span class="sxs-lookup"><span data-stu-id="daf83-113">In the **Work exception code** field, type a value.</span></span> <span data-ttu-id="daf83-114">Adjon olyan címet a munkakivételnek, amelyik arra utal, hogy mire használják.</span><span class="sxs-lookup"><span data-stu-id="daf83-114">Give the work exception a title to indicate what it's used for.</span></span> <span data-ttu-id="daf83-115">Például: Rövid kitárolási kézikönyv.</span><span class="sxs-lookup"><span data-stu-id="daf83-115">For example, Short picking manual.</span></span>  
4. <span data-ttu-id="daf83-116">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="daf83-116">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="daf83-117">A **Kivétel** típusú mezőben válassza ki a „Rövid kitárolás” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="daf83-117">In the **Exception** type field, select 'Short pick'.</span></span>
6. <span data-ttu-id="daf83-118">Jelölje be a **Készlethelyesbítés** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="daf83-118">Select the **Adjust inventory** check box.</span></span> <span data-ttu-id="daf83-119">Ez a beállítás azt jelenti, hogy automatikusan megtörténik a készlet helyesbítése 0-ra a rövid kitárolás helyén.</span><span class="sxs-lookup"><span data-stu-id="daf83-119">This option means that inventory will automatically be adjusted to 0 at the short picked location.</span></span>  
7. <span data-ttu-id="daf83-120">Adjon meg vagy válasszon ki egy értéket az **Alapértelmezett helyesbítéstípus-kód** mezőben.</span><span class="sxs-lookup"><span data-stu-id="daf83-120">In the **Default adjustment type code** field, enter or select a value.</span></span> <span data-ttu-id="daf83-121">Az USMF esetében például kiválasztható a következő: „Remove Res Adj Out”.</span><span class="sxs-lookup"><span data-stu-id="daf83-121">For example, in USMF you can select 'Remove Res Adj Out'.</span></span>  
8. <span data-ttu-id="daf83-122">A **Cikk újbóli felosztása** mezőben válassza ki a „Manuális” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="daf83-122">In the **Item reallocation** field, select 'Manual'.</span></span> <span data-ttu-id="daf83-123">Ha bejelöli a manuális, vagy az automatikus és manuális lehetőséget, a raktáros számára engedélyezni kell a manuális újbóli felosztást.</span><span class="sxs-lookup"><span data-stu-id="daf83-123">If you select Manual, or Automatic and Manual, the warehouse worker needs to be enabled to use manual reallocation.</span></span>  

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a><span data-ttu-id="daf83-124">A dolgozó beállítása a manuális cikk-újbólifelosztás használatára</span><span class="sxs-lookup"><span data-stu-id="daf83-124">Set up a worker to use manual item reallocation</span></span>
1. <span data-ttu-id="daf83-125">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="daf83-125">Close the page.</span></span>
2. <span data-ttu-id="daf83-126">A **Navigációs ablaktáblán** ugorjon a **Raktárkezelés > Beállítás > Dolgozó >** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="daf83-126">In the **Navigation pane**, go to **Warehouse management > Setup > Worker**.</span></span>
3. <span data-ttu-id="daf83-127">Kattintson a **Szerkesztés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="daf83-127">Click **Edit**.</span></span>
4. <span data-ttu-id="daf83-128">A listában válassza a 24. dolgozó elemet.</span><span class="sxs-lookup"><span data-stu-id="daf83-128">In the list, select worker 24.</span></span>
5. <span data-ttu-id="daf83-129">Bontsa ki a **Munka** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="daf83-129">Expand the **Work** fastTab.</span></span>
6. <span data-ttu-id="daf83-130">Válassza ki az „Igen” lehetőséget a **Cikk újbóli manuális felosztásának engedélyezése** mezőben.</span><span class="sxs-lookup"><span data-stu-id="daf83-130">Select 'Yes' in the **Allow manual item reallocation** field.</span></span>

