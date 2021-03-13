---
title: Teljesítmény optimalizálása automatikus tisztítási feladatokkal
description: Ez a cikk azt mutatja be, hogyan lehet megoldani a Microsoft Dynamics 365 Human Resources bizonyos teljesítménnyel kapcsolatos problémáit a kötegeltfeladat-előzmények adattisztításával.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 97f6e310d3a69c870fe8ef03bd7a10cc7ab652e5
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112819"
---
# <a name="optimize-performance-with-auto-cleanup-tasks"></a><span data-ttu-id="e3154-103">Teljesítmény optimalizálása automatikus tisztítási feladatokkal</span><span class="sxs-lookup"><span data-stu-id="e3154-103">Optimize performance with auto cleanup tasks</span></span>

<span data-ttu-id="e3154-104">**Kibocsátás**</span><span class="sxs-lookup"><span data-stu-id="e3154-104">**Issue**</span></span>

<span data-ttu-id="e3154-105">A Microsoft Dynamics 365 Human Resources teljesítményproblémái akkor tapasztalhatók, ha a kötelegelt feladatok előzményei túl nagy méretűre növekednek.</span><span class="sxs-lookup"><span data-stu-id="e3154-105">Microsoft Dynamics 365 Human Resources can experience performance issues if the batch job history grows too large.</span></span>

<span data-ttu-id="e3154-106">**Ok**</span><span class="sxs-lookup"><span data-stu-id="e3154-106">**Cause**</span></span>

<span data-ttu-id="e3154-107">A gyakran futó kötegelt feladatok nem fenntartható növekedést eredményezhetnek a kötegelt feladatok előzményeiben.</span><span class="sxs-lookup"><span data-stu-id="e3154-107">Batch jobs that run frequently can lead to unsustainable growth of the batch job history.</span></span> <span data-ttu-id="e3154-108">Ennek hatására a teljesítménnyel kapcsolatos problémák merülhetnek fel.</span><span class="sxs-lookup"><span data-stu-id="e3154-108">This can cause performance issues.</span></span> 

<span data-ttu-id="e3154-109">**Feloldás**</span><span class="sxs-lookup"><span data-stu-id="e3154-109">**Resolution**</span></span>

<span data-ttu-id="e3154-110">Ütemezzen automatikus feladatot a kötegelt feladat előzményeinek tisztítására.</span><span class="sxs-lookup"><span data-stu-id="e3154-110">Schedule an automatic task to clean up your batch job history.</span></span> <span data-ttu-id="e3154-111">Javasoljuk, hogy a feladatot hetente futtassák, de előfordulhat, hogy a környezettől függően gyakrabban vagy ritkábban kell futtatnia a tisztítást.</span><span class="sxs-lookup"><span data-stu-id="e3154-111">We recommend setting up the task to run weekly, but you might need to run the cleanup more or less frequently, depending on your environment.</span></span> <span data-ttu-id="e3154-112">A következő eljárás a javasolt beállításokat tartalmazza, de ezeket az igényeknek megfelelően módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="e3154-112">The following procedure contains our recommended settings, but you can change these according to your needs.</span></span>

1. <span data-ttu-id="e3154-113">A Human Resources alkalmazásban válassza a **Rendszerfelügyelet** elemet.</span><span class="sxs-lookup"><span data-stu-id="e3154-113">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="e3154-114">A **Keresés** sávon adja meg: **Kötegelt feladat előzményeinek tisztítása**.</span><span class="sxs-lookup"><span data-stu-id="e3154-114">In the **Search** bar, enter **Batch job history clean-up**.</span></span>

   ![Kötegelt feladat előzményeinek tisztítása – keresés](media/talent-batch-history-cleanup-search-bar.png)

3. <span data-ttu-id="e3154-116">Az **Előzmények időkorlátja (nap)** mezőben adja meg: **30**.</span><span class="sxs-lookup"><span data-stu-id="e3154-116">In **History limit (days)**, enter **30**.</span></span>

   ![Előzmények időkorlátjának 30 napra állítása](media/talent-batch-history-cleanup-history-limit.png)

4. <span data-ttu-id="e3154-118">Válassza a **Futtatás a háttérben** lehetőséget, majd az **Ismétlődés** elemet.</span><span class="sxs-lookup"><span data-stu-id="e3154-118">Select **Run in the background** and then select **Recurrence**.</span></span>

   ![Ismétlődés beállítása](media/talent-batch-history-cleanup-recurrence.png)

5. <span data-ttu-id="e3154-120">Az **Ismétlődés meghatározása** részben állítsa a **Kezdő dátum** és **Kezdő időpont** értékét úgy, hogy munkaidőn kívül vagy hétvégén legyen, majd válassza a **NINCS ZÁRÓ DÁTUM** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e3154-120">Under **Define recurrence**, set the **Start date** and **Start time** to occur during off-hours or the weekend, and then select **NO END DATE**.</span></span> 

   ![Az ismétlődés kezdő dátumának és időpontjának meghatározása](media/talent-batch-history-cleanup-define-recurrence.png)

6. <span data-ttu-id="e3154-122">Az **ISMÉTLŐDÉSI MINTA** részben válassza a **Napok** elemet és állítsa az **ISMÉTLÉS MEGHATÁROZOTT IDŐKÖZÖNKÉNT** lehetőséget **7** értékre.</span><span class="sxs-lookup"><span data-stu-id="e3154-122">Under **RECURRENCE PATTERN**, select **Days** and set **REPEAT AFTER SPECIFIED INTERVAL** to **7**.</span></span>

   ![Állítsa a tisztítást heti ismétlődésre](media/talent-batch-history-cleanup-recurrence-pattern.png)

7. <span data-ttu-id="e3154-124">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e3154-124">Select **OK**.</span></span>

8. <span data-ttu-id="e3154-125">Szükség szerint módosítsa a **Futtatás a háttérben** rész többi paraméterét, majd válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e3154-125">Change any other parameters under **Run in the background** as necessary, and then select **OK**.</span></span>

