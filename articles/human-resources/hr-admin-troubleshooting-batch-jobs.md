---
title: Teljesítmény optimalizálása a kötegelt feladatok munkaidő utáni ütemezésével
description: Ez a témakör azt mutatja be, hogyan lehet megoldani a Microsoft Dynamics 365 Human Resources bizonyos teljesítményproblémáit a hosszan futó kötegelt feladatok munkaidő utánra ütemezésével.
author: andreabichsel
manager: tfehr
ms.date: 06/23/2020
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
ms.search.validFrom: 2020-06-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 0b13853598bbdec239bce98029e534991a53876b
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467217"
---
# <a name="optimize-performance-by-scheduling-batch-jobs-after-hours"></a><span data-ttu-id="cea24-103">Teljesítmény optimalizálása a kötegelt feladatok munkaidő utáni ütemezésével</span><span class="sxs-lookup"><span data-stu-id="cea24-103">Optimize performance by scheduling batch jobs after hours</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="issue"></a><span data-ttu-id="cea24-104">Kiadás</span><span class="sxs-lookup"><span data-stu-id="cea24-104">Issue</span></span>

<span data-ttu-id="cea24-105">A Microsoft Dynamics 365 Human Resources esetében teljesítménnyel kapcsolatos problémák jelentkezhetnek, ha a szokásos munkaidő alatt hosszú futási idejű feladatok futnak.</span><span class="sxs-lookup"><span data-stu-id="cea24-105">Microsoft Dynamics 365 Human Resources can experience performance issues if long-running batch jobs run during typical business hours.</span></span>

## <a name="resolution"></a><span data-ttu-id="cea24-106">Felbontás</span><span class="sxs-lookup"><span data-stu-id="cea24-106">Resolution</span></span>

<span data-ttu-id="cea24-107">A következő kötegelt feladatokat munkaidőn kívülre ütemezze.</span><span class="sxs-lookup"><span data-stu-id="cea24-107">Schedule the following batch jobs during off hours.</span></span> <span data-ttu-id="cea24-108">Ajánljuk a gyakran futó kötegelt feladatok gyakoriságának áttekintését is.</span><span class="sxs-lookup"><span data-stu-id="cea24-108">We also recommend reviewing the frequency of batch jobs that run frequently.</span></span> <span data-ttu-id="cea24-109">Ha lehetséges, csökkentse a kötegelt feladat ismétlődését.</span><span class="sxs-lookup"><span data-stu-id="cea24-109">If possible, reduce the recurrence of the batch job.</span></span> <span data-ttu-id="cea24-110">Sok esetben az alapértelmezett gyakoriság elegendő.</span><span class="sxs-lookup"><span data-stu-id="cea24-110">In many cases, the default frequency is sufficient.</span></span>

<span data-ttu-id="cea24-111">A következő kötegelt feladatoknak éjszaka vagy munkaidő után kell futniuk.</span><span class="sxs-lookup"><span data-stu-id="cea24-111">The following batch jobs should run at night or after hours.</span></span> <span data-ttu-id="cea24-112">Ellenőrizze az ismétlődő kötegelt feladatok időzónáját.</span><span class="sxs-lookup"><span data-stu-id="cea24-112">Be sure to check the time zone for these recurring batch jobs.</span></span> <span data-ttu-id="cea24-113">Előfordulhat, hogy egyes kötegelt feladatok a Pacific standard Time (PST) időzónát használják.</span><span class="sxs-lookup"><span data-stu-id="cea24-113">Some batch jobs might use Pacific Standard Time (PST).</span></span>

| <span data-ttu-id="cea24-114">Kötegelt feladat</span><span class="sxs-lookup"><span data-stu-id="cea24-114">Batch job</span></span> | <span data-ttu-id="cea24-115">Alapértelmezett előfordulás</span><span class="sxs-lookup"><span data-stu-id="cea24-115">Default occurrence</span></span> |
| --- | --- |
| <span data-ttu-id="cea24-116">Kötegelt feladatelőzmények tisztítása</span><span class="sxs-lookup"><span data-stu-id="cea24-116">Batch job history cleanup</span></span> | <span data-ttu-id="cea24-117">1 alkalommal havonta</span><span class="sxs-lookup"><span data-stu-id="cea24-117">1 time per month</span></span> |
| <span data-ttu-id="cea24-118">Az exportálás előkészítési adatainak kiürítése</span><span class="sxs-lookup"><span data-stu-id="cea24-118">Export staging cleanup</span></span> | <span data-ttu-id="cea24-119">1 alkalommal naponta</span><span class="sxs-lookup"><span data-stu-id="cea24-119">1 time per day</span></span> |
| <span data-ttu-id="cea24-120">Common Data Service kihagyott kérelem szinkronizálásának integrációja</span><span class="sxs-lookup"><span data-stu-id="cea24-120">Common Data Service integration missed request sync</span></span> | <span data-ttu-id="cea24-121">1 alkalommal naponta</span><span class="sxs-lookup"><span data-stu-id="cea24-121">1 time per day</span></span> |
| <span data-ttu-id="cea24-122">Adatbázis-tömörítési rendszerfeladat, amelynek a munkaidőn kívüli rendszeres futtatására van szükség.</span><span class="sxs-lookup"><span data-stu-id="cea24-122">Database compression system job that needs to run regularly during off hours</span></span> | <span data-ttu-id="cea24-123">1 alkalommal naponta</span><span class="sxs-lookup"><span data-stu-id="cea24-123">1 time per day</span></span> |
| <span data-ttu-id="cea24-124">Adatbázisindex-újraépítési rendszerfeladat, amelynek a munkaidőn kívüli rendszeres futtatására van szükség.</span><span class="sxs-lookup"><span data-stu-id="cea24-124">Database index rebuild system job that needs to run regularly during off hours</span></span> | <span data-ttu-id="cea24-125">1 alkalommal naponta</span><span class="sxs-lookup"><span data-stu-id="cea24-125">1 time per day</span></span> |

1. <span data-ttu-id="cea24-126">A Human Resources alkalmazásban válassza a **Rendszerfelügyelet** elemet.</span><span class="sxs-lookup"><span data-stu-id="cea24-126">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="cea24-127">A **Keresés** sávon keressen rá a fenti kötegelt feladatok egyikére.</span><span class="sxs-lookup"><span data-stu-id="cea24-127">In the **Search** bar, search for one of the above batch jobs.</span></span>

3. <span data-ttu-id="cea24-128">Válassza a **Futtatás a háttérben** lehetőséget, majd az **Ismétlődés** elemet.</span><span class="sxs-lookup"><span data-stu-id="cea24-128">Select **Run in the background**, and then select **Recurrence**.</span></span>

   ![Ismétlődés beállítása](media/talent-batch-history-cleanup-recurrence.png)

4. <span data-ttu-id="cea24-130">Az **Ismétlődés meghatározása** részben állítsa a **Kezdő dátum** és **Kezdő időpont** értékét úgy, hogy munkaidőn kívül vagy hétvégén legyen.</span><span class="sxs-lookup"><span data-stu-id="cea24-130">Under **Define recurrence**, set the **Start date** and **Start time** to occur during off hours or the weekend.</span></span> <span data-ttu-id="cea24-131">Válassza a **Nincs záró dátum** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cea24-131">Select **No end date**.</span></span> 

   ![Az ismétlődés kezdő dátumának és időpontjának meghatározása](media/talent-batch-history-cleanup-define-recurrence.png)

5. <span data-ttu-id="cea24-133">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cea24-133">Select **OK**.</span></span>

6. <span data-ttu-id="cea24-134">Szükség szerint módosítsa a **Futtatás a háttérben** rész többi paraméterét, majd válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cea24-134">If needed, change any other parameters under **Run in the background**, and then select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cea24-135">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="cea24-135">Additional resources</span></span>

[<span data-ttu-id="cea24-136">Teljesítmény optimalizálása automatikus tisztítási feladatokkal</span><span class="sxs-lookup"><span data-stu-id="cea24-136">Optimize performance with auto cleanup tasks</span></span>](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]