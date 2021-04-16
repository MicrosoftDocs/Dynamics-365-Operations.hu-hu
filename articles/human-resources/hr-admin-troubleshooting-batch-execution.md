---
title: Beragadt kötegelt feladatok alaphelyzetbe állítása
description: Ez a témakör bemutatja, hogyan oldhatja meg a beragadt kötegelt feladatokkal kapcsolatos problémákat.
author: andreabichsel
ms.date: 03/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: 01ef0bf8ccc486614eec42d3fb6f0b2941fc47c0
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794949"
---
# <a name="reset-stuck-batch-jobs"></a><span data-ttu-id="3f274-103">Beragadt kötegelt feladatok alaphelyzetbe állítása</span><span class="sxs-lookup"><span data-stu-id="3f274-103">Reset stuck batch jobs</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="issue"></a><span data-ttu-id="3f274-104">Kiadás</span><span class="sxs-lookup"><span data-stu-id="3f274-104">Issue</span></span>

<span data-ttu-id="3f274-105">A Microsoft Dynamics 365 Human Resources esetében olyan kötegelt feladatokkal kapcsolatos problémákat tapasztalhat, amelyek **Végrehajtás** vagy **Megszakítás** állapotban vannak, és nem fejeződnek be.</span><span class="sxs-lookup"><span data-stu-id="3f274-105">Microsoft Dynamics 365 Human Resources can experience issues with batch jobs that are stuck in either an **Executing** or **Canceling** state and don't complete.</span></span>

## <a name="resolution"></a><span data-ttu-id="3f274-106">Felbontás</span><span class="sxs-lookup"><span data-stu-id="3f274-106">Resolution</span></span>

<span data-ttu-id="3f274-107">Ha egy kötegelt feldolgozás **Végrehajtás** vagy **Megszakítás** állapotban van, a feladat törlésének kényszerítésével alaphelyzetbe állíthatja az állapotot.</span><span class="sxs-lookup"><span data-stu-id="3f274-107">When a batch job is stuck in an **Executing** or **Canceling** state, you can reset the status by forcing the cancellation of the job.</span></span> <span data-ttu-id="3f274-108">A megszakítás után visszaállíthatja a kötegelt feldolgozást **Várakozás** állapotra.</span><span class="sxs-lookup"><span data-stu-id="3f274-108">After you cancel it, you can reset the batch job by setting it to a **Waiting** status.</span></span> <span data-ttu-id="3f274-109">Ezután a következő ütemezett kötegfuttatásban újra fel lehet venni a végrehajtáshoz.</span><span class="sxs-lookup"><span data-stu-id="3f274-109">It will then be picked up again for execution in the next scheduled batch run.</span></span>

1. <span data-ttu-id="3f274-110">A **Rendszerfelügyelet** munkaterületen jelölje ki a **Hivatkozások** lapot, és válassza a **Kötegelt feladatok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3f274-110">In the **System administration** workspace, select the **Links** page, and select **Batch jobs**.</span></span>

2. <span data-ttu-id="3f274-111">A **Kötegelt feladat** listaoldalon jelölje ki az alaphelyzetbe állításhoz szükséges feladatokat.</span><span class="sxs-lookup"><span data-stu-id="3f274-111">On the **Batch job** list page, select the job that needs to be reset.</span></span>

3. <span data-ttu-id="3f274-112">A művelet menüszalagján válassza a **Megszakítás kényszerítése** lehetőséget, és erősítse meg a műveletet.</span><span class="sxs-lookup"><span data-stu-id="3f274-112">On the action ribbon, select **Force cancel**, and confirm the action.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3f274-113">A **Megszakítás kényszeítése** művelet csak akkor érhető el, ha a kijelölt kötegelt feldolgozás **Végrehajtás** vagy **Megszakítás** állapotú, és a feladathoz nem fut kötegelt végrehajtási vagy törlési folyamat.</span><span class="sxs-lookup"><span data-stu-id="3f274-113">The **Force cancel** action is only available when the selected batch job has a status of either **Executing** or **Canceling**, and no batch execution or cancellation processes are running for the job.</span></span>

4. <span data-ttu-id="3f274-114">A művelet menüszalagján válassza az **Állapot módosítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3f274-114">On the action ribbon, select **Change status**.</span></span>

5. <span data-ttu-id="3f274-115">Az **Új állapot kiválasztása** lapon válassza a **Várakozás** lehetőséget, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="3f274-115">On the **Select new status** page, select **Waiting**, and then select **OK**.</span></span>

   ![Új kötegelt feldolgozási állapot kiválasztása](./media/hr-admin-reset-batch-job-status.png)

## <a name="see-also"></a><span data-ttu-id="3f274-117">Lásd még</span><span class="sxs-lookup"><span data-stu-id="3f274-117">See also</span></span>

[<span data-ttu-id="3f274-118">Teljesítmény optimalizálása a kötegelt feladatok munkaidő utáni ütemezésével</span><span class="sxs-lookup"><span data-stu-id="3f274-118">Optimize performance by scheduling batch jobs after hours</span></span>](hr-admin-troubleshooting-batch-jobs.md)<br>
[<span data-ttu-id="3f274-119">Teljesítmény optimalizálása automatikus tisztítási feladatokkal</span><span class="sxs-lookup"><span data-stu-id="3f274-119">Optimize performance with auto cleanup tasks</span></span>](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
