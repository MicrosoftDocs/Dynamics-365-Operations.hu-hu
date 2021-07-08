---
title: Hiba történik a beépített alaptervezési motor futtatásakor
description: Az elavult beépített főtervező motor futtatásakor hibaüzenetet kap.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: Dialog_ReqCalcScheduleItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 9c950292a4f43319d21a7deafdfb341b7bef15d8
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294093"
---
# <a name="you-receive-an-error-when-running-the-built-in-master-planning-engine"></a><span data-ttu-id="98455-103">Hiba történik a beépített alaptervezési motor futtatásakor</span><span class="sxs-lookup"><span data-stu-id="98455-103">You receive an error when running the built-in master planning engine</span></span>

<span data-ttu-id="98455-104">Hibakód: ReqCalcScheduleItemTablePlanningOptimizationFitError</span><span class="sxs-lookup"><span data-stu-id="98455-104">Error code: ReqCalcScheduleItemTablePlanningOptimizationFitError</span></span>

## <a name="symptoms"></a><span data-ttu-id="98455-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="98455-105">Symptoms</span></span>

<span data-ttu-id="98455-106">Amikor az elavult beépített főtervező motor segítségével futtatja a főtervezést, a következő hibaüzenetet kapja:</span><span class="sxs-lookup"><span data-stu-id="98455-106">When you run master planning by using the deprecated built-in master planning engine, you receive the following error message:</span></span>

> <span data-ttu-id="98455-107">Ez a hibaüzenet akkor jelenik meg, ha a beépített alaptervezési motort a Tervezési optimalizálás által támogatott esetekhez használta.</span><span class="sxs-lookup"><span data-stu-id="98455-107">You receive this error message because the built-in master planning engine was used for scenarios supported by Planning Optimization.</span></span> <span data-ttu-id="98455-108">Most át kell telepítenie rendszerét a Tervezés optimalizálásra, mivel az aktuális beépített alaptervezés elavult.</span><span class="sxs-lookup"><span data-stu-id="98455-108">You should migrate to Planning Optimization now, as the current built-in master planning will be deprecated.</span></span> <span data-ttu-id="98455-109">Ne feledje, hogy ennek az alaptervezésnek a futtatása sikeresen befejeződött.</span><span class="sxs-lookup"><span data-stu-id="98455-109">Note that this master planning run did complete successfully.</span></span> <span data-ttu-id="98455-110">Abban az esetben, ha az áttelepítés erősen függ a függőben lévő szolgáltatásoktól, kérhető a beépített alaptervezési motor további használatának kivétele.</span><span class="sxs-lookup"><span data-stu-id="98455-110">In case your migration has strong dependencies on pending features, an exception to continued usage of the built-in master planning engine can be requested.</span></span> <span data-ttu-id="98455-111">Töltse ki a következő kérdőívet a kezdéshez, illetve a szükséges, kérelmezzen kivételt a Tervezési optimalizálásra való átállítás alól.</span><span class="sxs-lookup"><span data-stu-id="98455-111">Please complete the following questionnaire to get started and, if relevant, request an exception from migration to Planning Optimization.</span></span> [<span data-ttu-id="98455-112">Tervezési optimalizálási áttelepítés és kivételi kérdőív</span><span class="sxs-lookup"><span data-stu-id="98455-112">Planning Optimization migration and exception questionnaire</span></span>](https://go.microsoft.com/fwlink/?linkid=2144962)

## <a name="cause"></a><span data-ttu-id="98455-113">Ok</span><span class="sxs-lookup"><span data-stu-id="98455-113">Cause</span></span>

<span data-ttu-id="98455-114">Ha futtatja a tervezést, és nem használja a gyártásvezérlési funkciókat, fontolja meg a tervezési optimalizálási beállításra való áttelepítést.</span><span class="sxs-lookup"><span data-stu-id="98455-114">If you run planning and don't use production control features, you should consider migrating to Planning Optimization.</span></span> <span data-ttu-id="98455-115">A beépített alaptervezési motor elavult.</span><span class="sxs-lookup"><span data-stu-id="98455-115">The built-in master planning engine is being deprecated.</span></span> <span data-ttu-id="98455-116">Ezért ha továbbra is azt szeretné, hogy hibaüzenet fogadása nélkül használja, kivételt kell alkalmaznia a Microsofttól.</span><span class="sxs-lookup"><span data-stu-id="98455-116">Therefore, if you want to continue to use it without receiving the error message, you must apply for an exception from Microsoft.</span></span>

## <a name="resolution"></a><span data-ttu-id="98455-117">Megoldás</span><span class="sxs-lookup"><span data-stu-id="98455-117">Resolution</span></span>

<span data-ttu-id="98455-118">Ha további tájékoztatást ad arról, hogyan lehet áttérni a tervezési optimalizálásra, vagy hogyan lehet kivételeket alkalmazni, hogy továbbra is használni tudja az elavult beépített tervezőmotort, akkor tekintse át az [Áttelepítés tervezési optimalizálásra alaptervezéshez](/dynamics365/supply-chain/master-planning/new-master-planning-engine) részt.</span><span class="sxs-lookup"><span data-stu-id="98455-118">For more information about how to migrate to Planning Optimization, or how to apply for an exception so that you can continue to use the deprecated built-in planning engine instead, see [Migration to Planning Optimization for master planning](/dynamics365/supply-chain/master-planning/new-master-planning-engine).</span></span>
