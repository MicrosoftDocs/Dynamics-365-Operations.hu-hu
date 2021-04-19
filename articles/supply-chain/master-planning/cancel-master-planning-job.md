---
title: Alaptervezési feladat visszavonása
description: Ez a témakör azt mutatja be, hogyan lehet érvényteleníteni egy olyan aktív tervezési feladatot, amely a beépített tervezési funkciót használja.
author: ChristianRytt
ms.date: 05/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace, ReqProcessList
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-12-16
ms.dyn365.ops.version: ''
ms.openlocfilehash: 513aee3b9475506e28db4bffe90df58567b6b281
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816604"
---
# <a name="cancel-a-master-planning-job"></a><span data-ttu-id="6ae97-103">Alaptervezési feladat visszavonása</span><span class="sxs-lookup"><span data-stu-id="6ae97-103">Cancel a master planning job</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6ae97-104">A Microsoft Dynamics 365 Supply Chain Management alkalmazásban több lehetőség van az alaptervezés feladat visszavonására.</span><span class="sxs-lookup"><span data-stu-id="6ae97-104">In Microsoft Dynamics 365 Supply Chain Management, there are multiple options for canceling a master planning job.</span></span> <span data-ttu-id="6ae97-105">Előfordulhat például, hogy vissza szeretne vonni egy alaptervezési feladatot, ha azt tévedésből indította el, vagy a vártnál tovább tart, és meg szeretné szakítani.</span><span class="sxs-lookup"><span data-stu-id="6ae97-105">For example, you may want to cancel a master planning job if it was started by mistake or is running longer than expected and you want to end it.</span></span> <span data-ttu-id="6ae97-106">A tervezési feladatok megszakításához a legjobb módszer a **Befejezetlen tervezési folyamatok** lap.</span><span class="sxs-lookup"><span data-stu-id="6ae97-106">The best way to cancel a planning job is from  the **Unfinished planning processes** page.</span></span> <span data-ttu-id="6ae97-107">A **Kötegelt feladatok** és a **Kötegelt feladatok – speciális** lapok alternatív lehetőségei csak akkor használhatók, ha az alaptervezési feladat a **Befejezetlen tervezési folyamatok** lapról néhány percen belül nem fejeződött be.</span><span class="sxs-lookup"><span data-stu-id="6ae97-107">Alternative options from the **Batch jobs** and **Batch jobs enhanced** pages should only be used if canceling the master planning job from the **Unfinished planning processes** page did not complete within a few minutes.</span></span>

## <a name="preferred-cancel-option"></a><span data-ttu-id="6ae97-108">Előnyben részesített visszavonási beállítás</span><span class="sxs-lookup"><span data-stu-id="6ae97-108">Preferred cancel option</span></span>
### <a name="cancel-master-planning-job-from-unfinished-planning-processes-page"></a><span data-ttu-id="6ae97-109">Alaptervezési feladat visszavonása a **Befejezetlen tervezési folyamatok** lapról</span><span class="sxs-lookup"><span data-stu-id="6ae97-109">Cancel master planning job from **Unfinished planning processes** page</span></span>
1. <span data-ttu-id="6ae97-110">Lépjen az **Alaptervezés > Lekérdezések és jelentések > Alaptervezés > Befejezetlen tervezési folyamatok** elemre.</span><span class="sxs-lookup"><span data-stu-id="6ae97-110">Go to **Master planning > Inquiries and reports > Master planning > Unfinished planning processes**.</span></span>
2. <span data-ttu-id="6ae97-111">Válassza ki a visszavonni kívánt tervezési folyamathoz tartozó sort.</span><span class="sxs-lookup"><span data-stu-id="6ae97-111">Select the line with the planning process that you want to cancel.</span></span>
3. <span data-ttu-id="6ae97-112">Kattintson a **Mégse** gombra.</span><span class="sxs-lookup"><span data-stu-id="6ae97-112">Click **Cancel**.</span></span>

## <a name="additional-cancel-options"></a><span data-ttu-id="6ae97-113">További visszavonási lehetőségek</span><span class="sxs-lookup"><span data-stu-id="6ae97-113">Additional cancel options</span></span>
<span data-ttu-id="6ae97-114">Ezek csak akkor használhatók, ha az alaptervezési feladat megszakítása a **Befejezetlen tervezési folyamatok** lapról nem fejeződött be pár percen belül.</span><span class="sxs-lookup"><span data-stu-id="6ae97-114">These should only be used if canceling the master planning job from the **Unfinished planning processes** page did not complete within a few minutes.</span></span>

### <a name="delete-master-planning-job-from-the-batch-jobs-page"></a><span data-ttu-id="6ae97-115">Az alaptervezési feladat törlése a **Kötegelt feladatok** oldalról</span><span class="sxs-lookup"><span data-stu-id="6ae97-115">Delete master planning job from the **Batch jobs** page</span></span>
1. <span data-ttu-id="6ae97-116">Ugorjon a **Rendszerfelügyelet > Lekérdezések > Kötegelt feladatok** pontra.</span><span class="sxs-lookup"><span data-stu-id="6ae97-116">Go to **System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="6ae97-117">Válassza ki a törölni kívánt tervezési feladathoz tartozó sort.</span><span class="sxs-lookup"><span data-stu-id="6ae97-117">Select the line with the planning job that you want to delete.</span></span>
3. <span data-ttu-id="6ae97-118">Kattintson a **Törlés** gombra.</span><span class="sxs-lookup"><span data-stu-id="6ae97-118">Click **Delete**.</span></span>

### <a name="abort-master-planning-job-task-from-the-batch-jobs-enhanced-page"></a><span data-ttu-id="6ae97-119">Az alaptervezési feladat megszakítása a **Kötegelt feladatok – speciális** oldalról</span><span class="sxs-lookup"><span data-stu-id="6ae97-119">Abort master planning job task from the **Batch jobs enhanced** page</span></span>
1. <span data-ttu-id="6ae97-120">Ugorjon a **Rendszerfelügyelet > Lekérdezések > Kötegelt feladatok** pontra.</span><span class="sxs-lookup"><span data-stu-id="6ae97-120">Go to **System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="6ae97-121">Ha a feladatazonosító nem jelenik meg a listában, kattintson a **Váltás a speciális nézetre** lehetőségre, különben folytassa a következő lépéssel.</span><span class="sxs-lookup"><span data-stu-id="6ae97-121">If the job ID is not shown in the list, click **Switch to enhanced form**, otherwise proceed with the next step.</span></span>
3. <span data-ttu-id="6ae97-122">Nyissa meg a kötegelt feladatot.</span><span class="sxs-lookup"><span data-stu-id="6ae97-122">Open the batch job.</span></span> <span data-ttu-id="6ae97-123">Kattintson a befejezendő feladatokkal rendelkező kötegelt feladat **Feladatazonosító** elemére.</span><span class="sxs-lookup"><span data-stu-id="6ae97-123">Click the **Job ID** for the batch job with tasks that you want to end.</span></span>
4. <span data-ttu-id="6ae97-124">A **Kötegelt feladatok** területen válassza ki a befejezendő feladatokat.</span><span class="sxs-lookup"><span data-stu-id="6ae97-124">In **Batch tasks**, select the tasks to end.</span></span>
5. <span data-ttu-id="6ae97-125">Kattintson az **Állapot módosítása**, majd a **Visszavonás** elemre, majd az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="6ae97-125">Click **Change status**, choose **Canceling** and click **OK**.</span></span>
6. <span data-ttu-id="6ae97-126">A **Kötegelt feladatok** gyorslapon kattintson a **Megszakítás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="6ae97-126">On the **Batch tasks** FastTab, click **Abort**.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]