---
title: Teljesítmény optimalizálása a kötegelt feladatok munkaidő utáni ütemezésével
description: Ez a témakör azt mutatja be, hogyan lehet megoldani a Microsoft Dynamics 365 Human Resources bizonyos teljesítményproblémáit a hosszan futó kötegelt feladatok munkaidő utánra ütemezésével.
author: andreabichsel
manager: AnnBe
ms.date: 06/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 452a87cf5ba6c1ac73636584d75b2ec2ac555e02
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527765"
---
# <a name="optimize-performance-by-scheduling-batch-jobs-after-hours"></a><span data-ttu-id="3902a-103">Teljesítmény optimalizálása a kötegelt feladatok munkaidő utáni ütemezésével</span><span class="sxs-lookup"><span data-stu-id="3902a-103">Optimize performance by scheduling batch jobs after hours</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="issue"></a><span data-ttu-id="3902a-104">Kiadás</span><span class="sxs-lookup"><span data-stu-id="3902a-104">Issue</span></span>

<span data-ttu-id="3902a-105">A Microsoft Dynamics 365 Human Resources esetében teljesítménnyel kapcsolatos problémák jelentkezhetnek, ha a szokásos munkaidő alatt hosszú futási idejű feladatok futnak.</span><span class="sxs-lookup"><span data-stu-id="3902a-105">Microsoft Dynamics 365 Human Resources can experience performance issues if long-running batch jobs run during typical business hours.</span></span>

## <a name="resolution"></a><span data-ttu-id="3902a-106">Felbontás</span><span class="sxs-lookup"><span data-stu-id="3902a-106">Resolution</span></span>

<span data-ttu-id="3902a-107">A következő kötegelt feladatokat munkaidőn kívülre ütemezze.</span><span class="sxs-lookup"><span data-stu-id="3902a-107">Schedule the following batch jobs during off hours.</span></span> <span data-ttu-id="3902a-108">Ajánljuk a gyakran futó kötegelt feladatok gyakoriságának áttekintését is.</span><span class="sxs-lookup"><span data-stu-id="3902a-108">We also recommend reviewing the frequency of batch jobs that run frequently.</span></span> <span data-ttu-id="3902a-109">Ha lehetséges, csökkentse a kötegelt feladat ismétlődését.</span><span class="sxs-lookup"><span data-stu-id="3902a-109">If possible, reduce the recurrence of the batch job.</span></span> <span data-ttu-id="3902a-110">Sok esetben az alapértelmezett gyakoriság elegendő.</span><span class="sxs-lookup"><span data-stu-id="3902a-110">In many cases, the default frequency is sufficient.</span></span>

<span data-ttu-id="3902a-111">A következő kötegelt feladatoknak éjszaka vagy munkaidő után kell futniuk.</span><span class="sxs-lookup"><span data-stu-id="3902a-111">The following batch jobs should run at night or after hours.</span></span> <span data-ttu-id="3902a-112">Ellenőrizze az ismétlődő kötegelt feladatok időzónáját.</span><span class="sxs-lookup"><span data-stu-id="3902a-112">Be sure to check the time zone for these recurring batch jobs.</span></span> <span data-ttu-id="3902a-113">Előfordulhat, hogy egyes kötegelt feladatok a Pacific standard Time (PST) időzónát használják.</span><span class="sxs-lookup"><span data-stu-id="3902a-113">Some batch jobs might use Pacific Standard Time (PST).</span></span>

| <span data-ttu-id="3902a-114">Kötegelt feladat</span><span class="sxs-lookup"><span data-stu-id="3902a-114">Batch job</span></span> | <span data-ttu-id="3902a-115">Alapértelmezett előfordulás</span><span class="sxs-lookup"><span data-stu-id="3902a-115">Default occurrence</span></span> |
| --- | --- |
| <span data-ttu-id="3902a-116">Kötegelt feladatelőzmények tisztítása</span><span class="sxs-lookup"><span data-stu-id="3902a-116">Batch job history cleanup</span></span> | <span data-ttu-id="3902a-117">1 alkalommal havonta</span><span class="sxs-lookup"><span data-stu-id="3902a-117">1 time per month</span></span> |
| <span data-ttu-id="3902a-118">Az exportálás előkészítési adatainak kiürítése</span><span class="sxs-lookup"><span data-stu-id="3902a-118">Export staging cleanup</span></span> | <span data-ttu-id="3902a-119">1 alkalommal naponta</span><span class="sxs-lookup"><span data-stu-id="3902a-119">1 time per day</span></span> |
| <span data-ttu-id="3902a-120">Common Data Service kihagyott kérelem szinkronizálásának integrációja</span><span class="sxs-lookup"><span data-stu-id="3902a-120">Common Data Service integration missed request sync</span></span> | <span data-ttu-id="3902a-121">1 alkalommal naponta</span><span class="sxs-lookup"><span data-stu-id="3902a-121">1 time per day</span></span> |
| <span data-ttu-id="3902a-122">Adatbázis-tömörítési rendszerfeladat, amelynek a munkaidőn kívüli rendszeres futtatására van szükség.</span><span class="sxs-lookup"><span data-stu-id="3902a-122">Database compression system job that needs to run regularly during off hours</span></span> | <span data-ttu-id="3902a-123">1 alkalommal naponta</span><span class="sxs-lookup"><span data-stu-id="3902a-123">1 time per day</span></span> |
| <span data-ttu-id="3902a-124">Adatbázisindex-újraépítési rendszerfeladat, amelynek a munkaidőn kívüli rendszeres futtatására van szükség.</span><span class="sxs-lookup"><span data-stu-id="3902a-124">Database index rebuild system job that needs to run regularly during off hours</span></span> | <span data-ttu-id="3902a-125">1 alkalommal naponta</span><span class="sxs-lookup"><span data-stu-id="3902a-125">1 time per day</span></span> |

1. <span data-ttu-id="3902a-126">A Human Resources alkalmazásban válassza a **Rendszerfelügyelet** elemet.</span><span class="sxs-lookup"><span data-stu-id="3902a-126">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="3902a-127">A **Keresés** sávon keressen rá a fenti kötegelt feladatok egyikére.</span><span class="sxs-lookup"><span data-stu-id="3902a-127">In the **Search** bar, search for one of the above batch jobs.</span></span>

3. <span data-ttu-id="3902a-128">Válassza a **Futtatás a háttérben** lehetőséget, majd az **Ismétlődés** elemet.</span><span class="sxs-lookup"><span data-stu-id="3902a-128">Select **Run in the background**, and then select **Recurrence**.</span></span>

   ![Ismétlődés beállítása](media/talent-batch-history-cleanup-recurrence.png)

4. <span data-ttu-id="3902a-130">Az **Ismétlődés meghatározása** részben állítsa a **Kezdő dátum** és **Kezdő időpont** értékét úgy, hogy munkaidőn kívül vagy hétvégén legyen.</span><span class="sxs-lookup"><span data-stu-id="3902a-130">Under **Define recurrence**, set the **Start date** and **Start time** to occur during off hours or the weekend.</span></span> <span data-ttu-id="3902a-131">Válassza a **Nincs záró dátum** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3902a-131">Select **No end date**.</span></span> 

   ![Az ismétlődés kezdő dátumának és időpontjának meghatározása](media/talent-batch-history-cleanup-define-recurrence.png)

5. <span data-ttu-id="3902a-133">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3902a-133">Select **OK**.</span></span>

6. <span data-ttu-id="3902a-134">Szükség szerint módosítsa a **Futtatás a háttérben** rész többi paraméterét, majd válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3902a-134">If needed, change any other parameters under **Run in the background**, and then select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3902a-135">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="3902a-135">Additional resources</span></span>

[<span data-ttu-id="3902a-136">Teljesítmény optimalizálása automatikus tisztítási feladatokkal</span><span class="sxs-lookup"><span data-stu-id="3902a-136">Optimize performance with auto cleanup tasks</span></span>](hr-admin-troubleshooting-batch-history.md)
