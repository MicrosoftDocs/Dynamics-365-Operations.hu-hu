---
title: Tervezési optimalizálás hibaelhárítása
description: Ez a témakör azt mutatja be, hogyan lehet javítani a Tervezési optimalizálás használata során felmerülő problémákat.
author: ChristianRytt
manager: tfehr
ms.date: 05/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-5-7
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: c3dd0bf262f65aac2359c05ff954bdfbd294353f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429298"
---
# <a name="troubleshoot-planning-optimization"></a><span data-ttu-id="45b58-103">Tervezési optimalizálás hibaelhárítása</span><span class="sxs-lookup"><span data-stu-id="45b58-103">Troubleshoot Planning Optimization</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="45b58-104">Ez a témakör azt mutatja be, hogyan lehet javítani a Tervezési optimalizálás használata során felmerülő gyakori problémákat.</span><span class="sxs-lookup"><span data-stu-id="45b58-104">This topic describes how to fix common issues that you might encounter while working with Planning Optimization.</span></span>

## <a name="installation-of-the-planning-optimization-add-in-doesnt-complete"></a><span data-ttu-id="45b58-105">A Tervezési optimalizálás beépülő modul telepítése nem fejeződött be</span><span class="sxs-lookup"><span data-stu-id="45b58-105">Installation of the Planning Optimization add-in doesn't complete</span></span>

<span data-ttu-id="45b58-106">A Tervezési optimalizálás egy Lifecycle Services (LCS) rendszerrel kompatibilis, 2. vagy magasabb (nem OneBox környezet) szintű, magas rendelkezésre állású környezetet igényel a Dynamics 365 Supply Chain Management 10.0.7-es vagy újabb verziójával.</span><span class="sxs-lookup"><span data-stu-id="45b58-106">Planning Optimization requires a Lifecycle Services (LCS) enabled, high-availability environment, tier 2 or higher (not a OneBox environment), with Dynamics 365 Supply Chain Management version 10.0.7 or later.</span></span> <span data-ttu-id="45b58-107">Ha OneBox környezetben próbálja meg telepíteni a bővítményt, a telepítés nem fog befejeződni.</span><span class="sxs-lookup"><span data-stu-id="45b58-107">If you try to install the add-in on a OneBox environment, the installation won't complete.</span></span>

<span data-ttu-id="45b58-108">**Javítás**: Szakítsa meg a telepítést, és használjon egy magas rendelkezésre állású, 2. vagy magasabb szintű (nem Onebox) környezetet.</span><span class="sxs-lookup"><span data-stu-id="45b58-108">**Fix**: Cancel the installation and use a high-availability environment, tier 2 or higher (not a OneBox environment).</span></span>

## <a name="planning-of-batch-jobs-fails-when-planning-optimization-is-enabled"></a><span data-ttu-id="45b58-109">A kötegelt feladatok tervezése meghiúsul, amikor a Tervezési optimalizálás engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="45b58-109">Planning of batch jobs fails when Planning Optimization is enabled</span></span>

<span data-ttu-id="45b58-110">A Tervezési optimalizálás engedélyezése esetén a beépített alaptervezési motor automatikusan le van tiltva.</span><span class="sxs-lookup"><span data-stu-id="45b58-110">When you enable Planning Optimization, the built-in master planning engine is automatically disabled.</span></span> <span data-ttu-id="45b58-111">A meglévő alaptervezett kötegelt feladatok, amelyeket a beépített Supply Chain Management tervezési morothoz hoztak létre, meghiúsulnak, ha elindulnak, miközben a Tervezési optimalizálás engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="45b58-111">Master planning batch jobs that were created for the built-in Supply Chain Management planning engine will fail if they are triggered while Planning Optimization is enabled.</span></span> <span data-ttu-id="45b58-112">Egy hibaüzenet jelenik meg, például *Ez a művelet olyan alaptervezést aktivált, amely nem támogatott, ha a Tervezési optimalizálás engedélyezve van*.</span><span class="sxs-lookup"><span data-stu-id="45b58-112">You may receive an error message such as *This operation triggered master planning that isn't supported when Planning Optimization is enabled*.</span></span>

<span data-ttu-id="45b58-113">**Javítás**: Szakítsa meg az összes olyan alaptervezési kötegelt feladatot, amelyek a beépített Supply Chain Management-tervezési motorhoz lett létrehozva.</span><span class="sxs-lookup"><span data-stu-id="45b58-113">**Fix**: Cancel all master planning batch jobs that were created for the built-in Supply Chain Management planning engine.</span></span>

## <a name="planning-optimization-results-are-different-from-earlier-results"></a><span data-ttu-id="45b58-114">A Tervezési optimalizálás eredményei eltérnek a korábbi eredményektől</span><span class="sxs-lookup"><span data-stu-id="45b58-114">Planning Optimization results are different from earlier results</span></span>

<span data-ttu-id="45b58-115">A Tervezés optimalizálás néhány területen eltér a beépített alaptervezési konstrukciótól.</span><span class="sxs-lookup"><span data-stu-id="45b58-115">Planning Optimization differs from the built-in master planning design in some areas.</span></span> <span data-ttu-id="45b58-116">Ez a függő szolgáltatások miatt is történhet.</span><span class="sxs-lookup"><span data-stu-id="45b58-116">This can also be caused by pending features.</span></span>

<span data-ttu-id="45b58-117">**Javítás**: Futtassa a Tervezési optimalizálás illeszkedési elemzését, majd elemezze az eredményeket a vonatkozó dokumentációval összevetve, hogy megértsék a hatásait.</span><span class="sxs-lookup"><span data-stu-id="45b58-117">**Fix**: Run Planning Optimization fit analysis and then analyze the results while referring to the related documentation to understand the impact.</span></span> <span data-ttu-id="45b58-118">További tájékoztatás: [Tervezésoptimalizálás illeszkedési elemzése](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="45b58-118">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

## <a name="master-planning-doesnt-respect-the-coverage-time-fence"></a><span data-ttu-id="45b58-119">Az alaptervezés nem veszi figyelembe a fedezeti időkorlátot</span><span class="sxs-lookup"><span data-stu-id="45b58-119">Master planning doesn't respect the coverage time fence</span></span>

<span data-ttu-id="45b58-120">Ezt a Tervezés optimalizálás egy függőben lévő funkciója okozza.</span><span class="sxs-lookup"><span data-stu-id="45b58-120">This is caused by a pending feature for Planning Optimization.</span></span>

<span data-ttu-id="45b58-121">**Javítás**: Mindaddig, amíg a függő funkció nem érhető el, szűrje vagy törölje a tervezett rendeléseket a fedezeti időkorláton kívüli ellátási javaslatok eltávolításához.</span><span class="sxs-lookup"><span data-stu-id="45b58-121">**Fix**: Until the pending feature is available, filter or delete planned orders to remove supply suggestions outside of the coverage time fence.</span></span>

## <a name="cant-enable-planning-optimization"></a><span data-ttu-id="45b58-122">A Tervezési optimalizálás nem engedélyezhető?</span><span class="sxs-lookup"><span data-stu-id="45b58-122">Can't enable Planning Optimization</span></span>

<span data-ttu-id="45b58-123">A **Kapcsolat állapota** állapotnak **Csatlakoztatva** értékűnek kell lennie ahhoz, hogy a **Tervezési optimalizálás használata** beállításnak az **Igen** értéket adja meg.</span><span class="sxs-lookup"><span data-stu-id="45b58-123">The **Connection status** must be **Connected** before you can set **Use Planning Optimization** to **Yes**.</span></span> <span data-ttu-id="45b58-124">További tájékoztatás: [Első lépések a Tervezésoptimalizálással](get-started.md).</span><span class="sxs-lookup"><span data-stu-id="45b58-124">For more information, see [Get started with Planning Optimization](get-started.md).</span></span>

<span data-ttu-id="45b58-125">**Javítás**: Győződjön meg arról, hogy a Tervezési optimalizálás beépülő modul telepítése sikeresen befejeződött.</span><span class="sxs-lookup"><span data-stu-id="45b58-125">**Fix**: Make sure that the Planning Optimization add-in was installed successfully.</span></span>

## <a name="error-message-is-shown-during-ctp"></a><span data-ttu-id="45b58-126">Hibaüzenet jelenik meg a CTP során</span><span class="sxs-lookup"><span data-stu-id="45b58-126">Error message is shown during CTP</span></span>

<span data-ttu-id="45b58-127">Ha megpróbálja futtatni az ígérhető (CTP) elemet egy értékesítési rendelésből, amikor a Tervezési optimalizálás engedélyezve van, akkor a következő hibaüzenet jelenik meg: *A művelet olyan alaptervezést aktivált, amely nem támogatott, ha a Tervezés optimalizálása engedélyezve van*.</span><span class="sxs-lookup"><span data-stu-id="45b58-127">If you try to run capable to promise (CTP) from a sales order when Planning Optimization is enabled, you will receive the following error message: *This operation triggered master planning that isn't supported when the Planning Optimization is enabled*.</span></span>

<span data-ttu-id="45b58-128">Ez a termelési rendelések támogatásának részeként tervezett függő funkcióhoz kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="45b58-128">This is related to a pending feature that is planned as part of the support for production orders.</span></span>

<span data-ttu-id="45b58-129">**Javítás:** Kerülje a CTP-számításokat, amikor a Tervezési optimalizálás engedélyezve van, amíg elérhetővé nem válik a CTP-támogatás.</span><span class="sxs-lookup"><span data-stu-id="45b58-129">**Fix:** Avoid CTP calculations when Planning Optimization is enabled until CTP support is available.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="45b58-130">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="45b58-130">Additional resources</span></span>

[<span data-ttu-id="45b58-131">Tervezési optimalizálás kezdő lépései</span><span class="sxs-lookup"><span data-stu-id="45b58-131">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="45b58-132">Tervezési optimalizálás igazítási elemzése</span><span class="sxs-lookup"><span data-stu-id="45b58-132">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)
