---
title: A hullám nem jogosult tisztításra
description: A hullám nem jogosult tisztításra
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWaveTable_WHSWaveProcessingDataCleanup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3e5142cf40a6c0d308e8e952bbe17e85b498826d
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924327"
---
# <a name="wave-isnt-eligible-for-cleanup"></a><span data-ttu-id="f5222-103">A hullám nem jogosult tisztításra</span><span class="sxs-lookup"><span data-stu-id="f5222-103">Wave isn't eligible for cleanup</span></span>

<span data-ttu-id="f5222-104">Hibakód: WaveNotEligibleForCleanup</span><span class="sxs-lookup"><span data-stu-id="f5222-104">Error code: WaveNotEligibleForCleanup</span></span>

## <a name="symptoms"></a><span data-ttu-id="f5222-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="f5222-105">Symptoms</span></span>

<span data-ttu-id="f5222-106">A rendszer a következő hibaüzenetet jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="f5222-106">The system shows the following error message:</span></span>

> <span data-ttu-id="f5222-107">A(z) %1 hullám nem törölhető.</span><span class="sxs-lookup"><span data-stu-id="f5222-107">Wave %1 is not eligible for cleanup.</span></span>

<span data-ttu-id="f5222-108">A hullámadatok nem tisztíthatóak.</span><span class="sxs-lookup"><span data-stu-id="f5222-108">The wave data can't be cleaned up.</span></span>  

## <a name="cause"></a><span data-ttu-id="f5222-109">Ok</span><span class="sxs-lookup"><span data-stu-id="f5222-109">Cause</span></span>

<span data-ttu-id="f5222-110">A hullám feldolgozása jelenleg folyamatban van, az alábbi feltételek egyikének megfelelően:</span><span class="sxs-lookup"><span data-stu-id="f5222-110">The wave is currently being processed, as indicated by one of the following conditions:</span></span>

- <span data-ttu-id="f5222-111">Állítsa a **Hullám állapota** mező értékét erre: *Végrehajtás*.</span><span class="sxs-lookup"><span data-stu-id="f5222-111">The **Wave status** field is set to *Executing*.</span></span>
- <span data-ttu-id="f5222-112">Ha a műveletpanel **Hullám lapján** a **Hullám** csoportban a **Kötegelt feladat** lehetőséget választja, az **Állapot** mező nincs beállítva *Befejezve*, *Hiba* vagy *Megszakítva* értékre.</span><span class="sxs-lookup"><span data-stu-id="f5222-112">When you select **Batch job** in the **Wave** group on the **Wave** tab of the Action Pane, the **Status** field isn't set to *Ended*, *Error*, or *Canceled*.</span></span> <span data-ttu-id="f5222-113">Emiatt jelenleg egy kötegelt feladat fut.</span><span class="sxs-lookup"><span data-stu-id="f5222-113">Therefore, a batch job is currently running.</span></span>

## <a name="resolution"></a><span data-ttu-id="f5222-114">Felbontás</span><span class="sxs-lookup"><span data-stu-id="f5222-114">Resolution</span></span>

<span data-ttu-id="f5222-115">A műveletpanel **Hullám** lapján, a **Hullám** csoportban válassza a **Kötegelt feladatot**, majd hajtsa végre a következő lépések valamelyikét:</span><span class="sxs-lookup"><span data-stu-id="f5222-115">On the Action Pane, on the **Wave** tab, in the **Wave** group, select **Batch job**, and then follow one of these steps:</span></span>

- <span data-ttu-id="f5222-116">Ha az **Állapot** mező *Végrehajtás* értékre van állítva: A Műveleti panelen a **Kötegelt feladat** lap **Kötegelt feladat** csoportjában válassza a **Feladatok megtekintése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f5222-116">If the **Status** field is set to *Executing*: On the Action Pane, on the **Batch job** tab, in the **Batch job** group, select **View tasks**.</span></span> <span data-ttu-id="f5222-117">A **Kötegelt feladatok** lap frissítésével figyelemmel követheti a folyamat állapotát.</span><span class="sxs-lookup"><span data-stu-id="f5222-117">You can follow the progress by refreshing the **Batch tasks** page.</span></span>
- <span data-ttu-id="f5222-118">Ha az **Állapot** mező nem *Végrehajtás* értékre van állítva: A Műveleti panelen a **Kötegelt feladat** lap **Funkciók** csoportjában válassza az **Állapot módosítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f5222-118">If the **Status** field isn't set to *Executing*: On the Action Pane, on the **Batch job** tab, in the **Functions** group, select **Change status**.</span></span> <span data-ttu-id="f5222-119">Az **Új állapot kiválasztása** mezőben válassza az *Várakozás* lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f5222-119">In the **Select new status** field, select *Waiting*.</span></span> <span data-ttu-id="f5222-120">Majd kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f5222-120">Then select **OK**.</span></span>
