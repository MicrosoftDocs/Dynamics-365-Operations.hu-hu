---
title: Tervezési optimalizálás hibaelhárítása
description: Ez a témakör azt mutatja be, hogyan lehet javítani a Tervezési optimalizálás használata során felmerülő problémákat.
author: ChristianRytt
ms.date: 05/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-5-7
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 2100235fadabe6af87849aab7d9ec55d85ea66fa
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812883"
---
# <a name="troubleshoot-planning-optimization"></a><span data-ttu-id="03fc1-103">Tervezési optimalizálás hibaelhárítása</span><span class="sxs-lookup"><span data-stu-id="03fc1-103">Troubleshoot Planning Optimization</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="03fc1-104">Ez a témakör azt mutatja be, hogyan lehet javítani a Tervezési optimalizálás használata során felmerülő gyakori problémákat.</span><span class="sxs-lookup"><span data-stu-id="03fc1-104">This topic describes how to fix common issues that you might encounter while working with Planning Optimization.</span></span>

## <a name="installation-of-the-planning-optimization-add-in-doesnt-complete"></a><span data-ttu-id="03fc1-105">A Tervezési optimalizálás beépülő modul telepítése nem fejeződött be</span><span class="sxs-lookup"><span data-stu-id="03fc1-105">Installation of the Planning Optimization add-in doesn't complete</span></span>

<span data-ttu-id="03fc1-106">A Tervezési optimalizálás egy Lifecycle Services (LCS) rendszerrel kompatibilis, 2. vagy magasabb (nem OneBox környezet) szintű, magas rendelkezésre állású környezetet igényel a Dynamics 365 Supply Chain Management 10.0.7-es vagy újabb verziójával.</span><span class="sxs-lookup"><span data-stu-id="03fc1-106">Planning Optimization requires a Lifecycle Services (LCS) enabled, high-availability environment, tier 2 or higher (not a OneBox environment), with Dynamics 365 Supply Chain Management version 10.0.7 or later.</span></span> <span data-ttu-id="03fc1-107">Ha OneBox környezetben próbálja meg telepíteni a bővítményt, a telepítés nem fog befejeződni.</span><span class="sxs-lookup"><span data-stu-id="03fc1-107">If you try to install the add-in on a OneBox environment, the installation won't complete.</span></span>

<span data-ttu-id="03fc1-108">**Javítás**: Szakítsa meg a telepítést, és használjon egy magas rendelkezésre állású, 2. vagy magasabb szintű (nem Onebox) környezetet.</span><span class="sxs-lookup"><span data-stu-id="03fc1-108">**Fix**: Cancel the installation and use a high-availability environment, tier 2 or higher (not a OneBox environment).</span></span>

## <a name="planning-of-batch-jobs-fails-when-planning-optimization-is-enabled"></a><span data-ttu-id="03fc1-109">A kötegelt feladatok tervezése meghiúsul, amikor a Tervezési optimalizálás engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="03fc1-109">Planning of batch jobs fails when Planning Optimization is enabled</span></span>

<span data-ttu-id="03fc1-110">A Tervezési optimalizálás engedélyezése esetén a beépített alaptervezési motor automatikusan le van tiltva.</span><span class="sxs-lookup"><span data-stu-id="03fc1-110">When you enable Planning Optimization, the built-in master planning engine is automatically disabled.</span></span> <span data-ttu-id="03fc1-111">A meglévő alaptervezett kötegelt feladatok, amelyeket a beépített Supply Chain Management tervezési morothoz hoztak létre, meghiúsulnak, ha elindulnak, miközben a Tervezési optimalizálás engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="03fc1-111">Master planning batch jobs that were created for the built-in Supply Chain Management planning engine will fail if they are triggered while Planning Optimization is enabled.</span></span> <span data-ttu-id="03fc1-112">Egy hibaüzenet jelenik meg, például *Ez a művelet olyan alaptervezést aktivált, amely nem támogatott, ha a Tervezési optimalizálás engedélyezve van*.</span><span class="sxs-lookup"><span data-stu-id="03fc1-112">You may receive an error message such as *This operation triggered master planning that isn't supported when Planning Optimization is enabled*.</span></span>

<span data-ttu-id="03fc1-113">**Javítás**: Szakítsa meg az összes olyan alaptervezési kötegelt feladatot, amelyek a beépített Supply Chain Management-tervezési motorhoz lett létrehozva.</span><span class="sxs-lookup"><span data-stu-id="03fc1-113">**Fix**: Cancel all master planning batch jobs that were created for the built-in Supply Chain Management planning engine.</span></span>

## <a name="planning-optimization-results-are-different-from-earlier-results"></a><span data-ttu-id="03fc1-114">A Tervezési optimalizálás eredményei eltérnek a korábbi eredményektől</span><span class="sxs-lookup"><span data-stu-id="03fc1-114">Planning Optimization results are different from earlier results</span></span>

<span data-ttu-id="03fc1-115">A Tervezés optimalizálás néhány területen eltér a beépített alaptervezési konstrukciótól.</span><span class="sxs-lookup"><span data-stu-id="03fc1-115">Planning Optimization differs from the built-in master planning design in some areas.</span></span> <span data-ttu-id="03fc1-116">Ez a függő szolgáltatások miatt is történhet.</span><span class="sxs-lookup"><span data-stu-id="03fc1-116">This can also be caused by pending features.</span></span>

<span data-ttu-id="03fc1-117">**Javítás**: Futtassa a Tervezési optimalizálás illeszkedési elemzését, majd elemezze az eredményeket a vonatkozó dokumentációval összevetve, hogy megértsék a hatásait.</span><span class="sxs-lookup"><span data-stu-id="03fc1-117">**Fix**: Run Planning Optimization fit analysis and then analyze the results while referring to the related documentation to understand the impact.</span></span> <span data-ttu-id="03fc1-118">További tájékoztatás: [Tervezésoptimalizálás illeszkedési elemzése](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="03fc1-118">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

## <a name="cant-enable-planning-optimization"></a><span data-ttu-id="03fc1-119">A Tervezési optimalizálás nem engedélyezhető?</span><span class="sxs-lookup"><span data-stu-id="03fc1-119">Can't enable Planning Optimization</span></span>

<span data-ttu-id="03fc1-120">A **Kapcsolat állapota** állapotnak **Csatlakoztatva** értékűnek kell lennie ahhoz, hogy a **Tervezési optimalizálás használata** beállításnak az **Igen** értéket adja meg.</span><span class="sxs-lookup"><span data-stu-id="03fc1-120">The **Connection status** must be **Connected** before you can set **Use Planning Optimization** to **Yes**.</span></span> <span data-ttu-id="03fc1-121">További tájékoztatás: [Első lépések a Tervezésoptimalizálással](get-started.md).</span><span class="sxs-lookup"><span data-stu-id="03fc1-121">For more information, see [Get started with Planning Optimization](get-started.md).</span></span>

<span data-ttu-id="03fc1-122">**Javítás**: Győződjön meg arról, hogy a Tervezési optimalizálás beépülő modul telepítése sikeresen befejeződött.</span><span class="sxs-lookup"><span data-stu-id="03fc1-122">**Fix**: Make sure that the Planning Optimization add-in was installed successfully.</span></span>

## <a name="error-message-is-shown-during-ctp"></a><span data-ttu-id="03fc1-123">Hibaüzenet jelenik meg a CTP során</span><span class="sxs-lookup"><span data-stu-id="03fc1-123">Error message is shown during CTP</span></span>

<span data-ttu-id="03fc1-124">Ha megpróbálja futtatni az ígérhető (CTP) elemet egy értékesítési rendelésből, amikor a Tervezési optimalizálás engedélyezve van, akkor a következő hibaüzenet jelenik meg: *A művelet olyan alaptervezést aktivált, amely nem támogatott, ha a Tervezés optimalizálása engedélyezve van*.</span><span class="sxs-lookup"><span data-stu-id="03fc1-124">If you try to run capable to promise (CTP) from a sales order when Planning Optimization is enabled, you will receive the following error message: *This operation triggered master planning that isn't supported when the Planning Optimization is enabled*.</span></span>

<span data-ttu-id="03fc1-125">Ez a termelési rendelések támogatásának részeként tervezett függő funkcióhoz kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="03fc1-125">This is related to a pending feature that is planned as part of the support for production orders.</span></span>

<span data-ttu-id="03fc1-126">**Javítás:** Kerülje a CTP-számításokat, amikor a Tervezési optimalizálás engedélyezve van, amíg elérhetővé nem válik a CTP-támogatás.</span><span class="sxs-lookup"><span data-stu-id="03fc1-126">**Fix:** Avoid CTP calculations when Planning Optimization is enabled until CTP support is available.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="03fc1-127">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="03fc1-127">Additional resources</span></span>

[<span data-ttu-id="03fc1-128">Tervezési optimalizálás kezdő lépései</span><span class="sxs-lookup"><span data-stu-id="03fc1-128">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="03fc1-129">Tervezési optimalizálás igazítási elemzése</span><span class="sxs-lookup"><span data-stu-id="03fc1-129">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]