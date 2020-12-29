---
title: Folyamatszerű gyártás – hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet javítani az folyamatszerű gyártás használata során felmerülő problémákat.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 63993fca2164301d31dbfa1474a4cf5eb16273e6
ms.sourcegitcommit: 8eefb4e14ae0ea27769ab2cecca747755560efa3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/13/2020
ms.locfileid: "4516795"
---
# <a name="troubleshoot-process-manufacturing"></a><span data-ttu-id="d2dd5-103">Folyamatszerű gyártás – hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="d2dd5-103">Troubleshoot process manufacturing</span></span>

<span data-ttu-id="d2dd5-104">Ez a témakör azt mutatja be, hogyan lehet javítani az folyamatszerű gyártás használata során felmerülő problémákat.</span><span class="sxs-lookup"><span data-stu-id="d2dd5-104">This topic describes how to fix issues that you might encounter while you work with process manufacturing.</span></span>

## <a name="when-i-use-the-job-card-device-to-report-a-partial-quantity-on-the-last-job-in-a-production-order-all-the-previous-jobs-on-that-order-that-have-a-status-of-in-progress-are-automatically-ended"></a><span data-ttu-id="d2dd5-105">Amikor a feladatkártya-eszközzel részleges mennyiséget jelentek a termelési rendelés utolsó feladatán, a rendelésben szereplő összes előző feladat, amelynek állapota Folyamatban van, automatikusan lezárul.</span><span class="sxs-lookup"><span data-stu-id="d2dd5-105">When I use the job card device to report a partial quantity on the last job in a production order, all the previous jobs on that order that have a status of In progress are automatically ended.</span></span>

<span data-ttu-id="d2dd5-106">Ez szándékosan van.</span><span class="sxs-lookup"><span data-stu-id="d2dd5-106">This behavior is by design.</span></span> <span data-ttu-id="d2dd5-107">A **Termelési rendelés alapértelmezései** lapon a **Készként jelentés** fülön van egy **Útvonal megjelölése befejezettként** lehetőség.</span><span class="sxs-lookup"><span data-stu-id="d2dd5-107">On the **Production order defaults** page, on the **Report as finished** tab, there is an option that is named **End-mark route**.</span></span> <span data-ttu-id="d2dd5-108">Ha ez a témakör *Igen* értékre van állítva, akkor egy útvonalkártya-naplót könyvel, amikor egy dolgozó a munkakártya-eszközt vagy a feladatkártya terminálját használja az utolsó művelet jelentéséhez.</span><span class="sxs-lookup"><span data-stu-id="d2dd5-108">If this topic is set to *Yes*, a route card journal is posted when a worker uses the job card device or job card terminal to report the last operation.</span></span> <span data-ttu-id="d2dd5-109">Ez a napló befejezettként jelöli meg az összes műveletet, és befejezi az összes termelési feladatot.</span><span class="sxs-lookup"><span data-stu-id="d2dd5-109">This journal marks all the operations as completed and ends all the production jobs.</span></span> <span data-ttu-id="d2dd5-110">Ha az **Útvonal megjelölése befejezettként** lehetőség *Igen* értékre van állítva, akkor a rendszer nem veszi figyelembe azt a feladatállapotot, amelyet a dolgozó az utolsó művelet jelentésekor választott.</span><span class="sxs-lookup"><span data-stu-id="d2dd5-110">When the **End-mark route** option is set to *Yes*, the system doesn't consider the job status that the worker selected when they reported the last operation.</span></span> <span data-ttu-id="d2dd5-111">A rendszer azt sem veszi figyelembe, hogy a dolgozó teljes vagy részleges mennyiséget jelent-e.</span><span class="sxs-lookup"><span data-stu-id="d2dd5-111">The system also doesn't consider whether the worker is reporting a full or partial quantity.</span></span>

## <a name="when-i-attempt-a-stock-closing-i-receive-the-following-warning-message-no-execution-of-backflush-costing-calculation-with-a-date-1-matching-period-end-has-been-registered"></a><span data-ttu-id="d2dd5-112">Amikor készletzárást kísérelek meg, a következő figyelmeztető üzenet jelenik meg: Az %1 egyeztetési időszak végén nem sikerült visszavezetéses költségelszámolás kiszámítását végrehajtani.”</span><span class="sxs-lookup"><span data-stu-id="d2dd5-112">When I attempt a stock closing, I receive the following warning message: "No execution of Backflush costing calculation with a date %1 matching period end has been registered."</span></span>

<span data-ttu-id="d2dd5-113">A 10.0.13-as verzió előtti kiadásokban, ha nem használja a lean termelési költségszámítási folyamatot, a következő hibás figyelmeztető üzenet jelenik meg a készletzárás során:</span><span class="sxs-lookup"><span data-stu-id="d2dd5-113">In releases before release 10.0.13, if you aren't using the lean production costing flow, you receive the following erroneous warning message during inventory closing:</span></span>

> <span data-ttu-id="d2dd5-114">Készletzárást készül végrehajtani %1.</span><span class="sxs-lookup"><span data-stu-id="d2dd5-114">You are about to execute an Inventory close with a date %1.</span></span> <span data-ttu-id="d2dd5-115">Az %1 egyeztetési időszak végén nem sikerült visszavezetéses költségelszámolás kiszámítását végrehajtani.</span><span class="sxs-lookup"><span data-stu-id="d2dd5-115">No execution of Backflush costing calculation with a date %1 matching period end has been registered.</span></span> <span data-ttu-id="d2dd5-116">Ne felejtse el végrehajtani az %1 egyeztetési időszak végén végrehajtani a visszavezetéses költségelszámolás kiszámítását.</span><span class="sxs-lookup"><span data-stu-id="d2dd5-116">Please remember to execute a Backflush costing calculation with a date of %1 matching period end.</span></span> <span data-ttu-id="d2dd5-117">A készletekre, az eladott áruk beszerzési értékére és az eltérésekre vonatkozó becslések nem lehetnek helyesek az alfőkönyv vagy a főkönyv modulban mindaddig, amíg nem történt meg a végrehajtás.</span><span class="sxs-lookup"><span data-stu-id="d2dd5-117">The valuation of inventories, cost of goods sold and variances might not be correct in Subledger or General ledger until this has been executed.</span></span>

<span data-ttu-id="d2dd5-118">A problémát a 10.0.13-as és újabb verzióiban javítottuk.</span><span class="sxs-lookup"><span data-stu-id="d2dd5-118">This issue has been fixed in release 10.0.13 and later.</span></span> <span data-ttu-id="d2dd5-119">További tájékoztatást a [KB 4582468](https://fix.lcs.dynamics.com/Issue/Details?kb=4582468&bugId=468844&dbType=3&qc=fcd64080446a27382cfde3e4c3bdcfb714279185932259cd11ceb0d500617296) témakörben talál.</span><span class="sxs-lookup"><span data-stu-id="d2dd5-119">For more information, see [KB 4582468](https://fix.lcs.dynamics.com/Issue/Details?kb=4582468&bugId=468844&dbType=3&qc=fcd64080446a27382cfde3e4c3bdcfb714279185932259cd11ceb0d500617296).</span></span>
