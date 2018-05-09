---
title: "A feldolgozási kanbanfeladat előkészítése, amikor az anyagok elérhetők a munkacellához"
description: "Ez a feladat a feldolgozási kanbanfeladat előkészítésével foglalkozik, amikor minden anyag elérhetők a munkacellához."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 6f1f858a8be6ecd8be968a8d71bab4c025b84ebf
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="prepare-a-process-kanban-job-when-materials-are-available-for-the-work-cell"></a><span data-ttu-id="b546d-103">A feldolgozási kanbanfeladat előkészítése, amikor az anyagok elérhetők a munkacellához</span><span class="sxs-lookup"><span data-stu-id="b546d-103">Prepare a process kanban job when materials are available for the work cell</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b546d-104">Ez a feladat a feldolgozási kanbanfeladat előkészítésével foglalkozik, amikor minden anyag elérhetők a munkacellához.</span><span class="sxs-lookup"><span data-stu-id="b546d-104">This task focuses on preparing a process kanban job when all materials are available for the work cell.</span></span> <span data-ttu-id="b546d-105">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="b546d-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="b546d-106">Ezt a feladatot a gépkezelő használja.</span><span class="sxs-lookup"><span data-stu-id="b546d-106">This task is intended for the machine operator.</span></span>

1. <span data-ttu-id="b546d-107">Ugorjon a feldolgozási feladatok kanbantáblájára.</span><span class="sxs-lookup"><span data-stu-id="b546d-107">Go to Kanban board for process jobs.</span></span>
2. <span data-ttu-id="b546d-108">A Munkacella mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="b546d-108">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="b546d-109">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="b546d-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="b546d-110">Válassza ki az 1250 munkacellát, és kattintson az OK lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b546d-110">Select work cell 1250 and click OK.</span></span>  
4. <span data-ttu-id="b546d-111">Jelölje ki az 4. sort a listában.</span><span class="sxs-lookup"><span data-stu-id="b546d-111">In the list, select row 4.</span></span>
    * <span data-ttu-id="b546d-112">A tiszta bemutatócégnél a 000329 kanban a 4. sorban az első feladat, amelyet nem végeztek el.</span><span class="sxs-lookup"><span data-stu-id="b546d-112">In the clean demo company, Kanban 000329 in row 4 is the first job that is not completed yet.</span></span>  
5. <span data-ttu-id="b546d-113">Bontsa ki a Kitárolási lista részt.</span><span class="sxs-lookup"><span data-stu-id="b546d-113">Toggle the expansion of the Picking list section.</span></span>
    * <span data-ttu-id="b546d-114">Ellenőrizze, hogy az ellátási állapot elérhető-e minden cikkhez a kitárolási listában.</span><span class="sxs-lookup"><span data-stu-id="b546d-114">Verify that the supply status is available for all items in the picking list.</span></span>  
    * <span data-ttu-id="b546d-115">Ha több feladat is ki van választva, a kitárolási lista a kiválasztott feladathoz szükséges minden cikk összegét mutatja.</span><span class="sxs-lookup"><span data-stu-id="b546d-115">If multiple jobs are selected, the picking list will show the sum of all items needed for the selected jobs.</span></span>  
6. <span data-ttu-id="b546d-116">Kattintson az Előkészítés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b546d-116">Click Prepare.</span></span>
    * <span data-ttu-id="b546d-117">Az előkészítési folyamat most befejeződött.</span><span class="sxs-lookup"><span data-stu-id="b546d-117">The preparation process is now completed.</span></span> <span data-ttu-id="b546d-118">A kiválasztott jelölőnégyzet a kitárolási lista minden sorában azt mutatja, hogy az ellátási állapot kitárolt.</span><span class="sxs-lookup"><span data-stu-id="b546d-118">The selected check box for all rows in the picking list indicates that the supply status is picked.</span></span>  

