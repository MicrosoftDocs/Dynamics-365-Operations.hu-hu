---
title: Projekterőforrás-ütemezés teljesítménye
description: Ez a témakör azt mutatja be, hogyan javítható az erőforrás-ütemezés teljesítménye nagy számú projekt esetében.
author: Yowelle
manager: AnnBe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 10.0.14
ms.search.validFrom: 2020-09-01
ms.openlocfilehash: 988fc83230f08a6534caa7c37784757d73c1cc12
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760569"
---
# <a name="project-resource-scheduling-performance"></a><span data-ttu-id="7e8fb-103">Projekterőforrás-ütemezés teljesítménye</span><span class="sxs-lookup"><span data-stu-id="7e8fb-103">Project resource scheduling performance</span></span>

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]


<span data-ttu-id="7e8fb-104">Az erőforrás-ütemezéssel kapcsolatos teljesítmény-problémák akkor merülhetnek fel, ha a projektek száma több ezer.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-104">Performance issues related to resource scheduling can occur when the number of projects reaches into the thousands.</span></span> <span data-ttu-id="7e8fb-105">Az erőforrás-ütemezés hatékonyságának javítása érdekében elérhető egy szolgáltatás, amely lehetővé teszi a felhasználók számára, hogy csökkentsék az erőforrás-elérhetőségi képernyő indításához szükséges időt.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-105">To improve resource scheduling performance, a feature is available that allows users to reduce the time that it takes to launch the resource availability form.</span></span> <span data-ttu-id="7e8fb-106">Ez a művelet eltávolítja az erőforrás-kapacitások összesítő szinkronizálási folyamatát, és a **ResProjectResource** táblát használja az erőforrás-keresés felgyorsítására.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-106">Specifically, this removes the resource capacity roll-up synchronization process and uses the **ResProjectResource** table to speed up the resource lookup.</span></span> <span data-ttu-id="7e8fb-107">Ne felejtse el, hogy a **ResRollup** tábla már nem lesz használva.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-107">Note that the **ResRollup** table will no longer be used.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7e8fb-108">Ha függőség van az erőforrás-kapacitás összesítő szinkronizálási folyamatán vagy a **ResProjectResource** táblán, ne használja ezt a funkciót.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-108">If there is a dependency on either the resource capacity roll-up synchronization process or the **ResProjectResource** table, do not use this feature.</span></span>

## <a name="enable-resource-scheduling-performance-enhancement"></a><span data-ttu-id="7e8fb-109">Az erőforrás-ütemezés teljesítményjavításának engedélyezése</span><span class="sxs-lookup"><span data-stu-id="7e8fb-109">Enable resource scheduling performance enhancement</span></span>
<span data-ttu-id="7e8fb-110">Az erőforrás-ütemezés hatékonysága növelésének engedélyezéséhez hajtsa végre a következő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-110">To enable resource scheduling performance enhancement, complete the following steps.</span></span>

1. <span data-ttu-id="7e8fb-111">Nyissa meg a **Funkciókezelés** > **Összes** elemet, majd a szolgáltatások listájában keresse meg a **Az erőforrás-ütemezés teljesítményjavítása funkció engedélyezése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-111">Go to **Feature management** > **All**, and in the feature list, locate **Enable project resource scheduling performance enhancement feature**.</span></span>
2. <span data-ttu-id="7e8fb-112">Válassza az **Engedélyezés most** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-112">Select **Enable now**.</span></span>

> [!NOTE]
> <span data-ttu-id="7e8fb-113">Ha nem találja a funkciót a listán, válassza a **Frissítések keresése** lehetőséget a lista frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-113">If you can't find the feature in the list, select **Check for updates** to refresh the list.</span></span>

3. <span data-ttu-id="7e8fb-114">Frissítse a böngészőprogramot, majd nyissa meg a **Projektmenedzsment és a könyvelés** > **Időszakos** > **Projekterőforrások** > **Erőforrásnaptárak kapacitásának szinkronizálása az összes vállalat között** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-114">Refresh your browser, and then go to **Project management and accounting** > **Periodic** > **Project resources** > **Synchronize resource calendars capacity across all companies**.</span></span>
4. <span data-ttu-id="7e8fb-115">Az előző adatok eltávolításához állítsa a **Meglévő kapacitásrekordok eltávolítása** elemet **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-115">Set **Remove existing capacity records** to **Yes** to remove previous data.</span></span> <span data-ttu-id="7e8fb-116">Ha növekményes adatokat szeretne generálni, állítsa **Nem** értékre.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-116">If you want generate incremental data, set it to **No**.</span></span>
5. <span data-ttu-id="7e8fb-117">Az **időszak kódja** mezőben válassza ki azt az időszakot, amelyben az adatokat létrehozni kell.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-117">In the **Period code** field, select the period in which data should be generated.</span></span> <span data-ttu-id="7e8fb-118">Ha kiválaszt egy időszakot, akkor nem kell megadni a kezdő és a záró dátumot.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-118">If you select a period code, a start and end date do not need to be defined.</span></span>
6. <span data-ttu-id="7e8fb-119">Ha üresen hagyja az **Időszak kódja** mezőt, válassza ki a kezdési és befejezési dátumokat az adatok generálásához.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-119">If you leave the **Period code** field blank, select specific start and end dates to generate data.</span></span>
7. <span data-ttu-id="7e8fb-120">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-120">Select **OK**.</span></span>

 > [!NOTE]
 > <span data-ttu-id="7e8fb-121">Ennek hatására a program a környezete összes vállalata között megosztja az általános adatokat a **ResCalendarCapacity** táblába, így a kötegelt feladatot csak egy jogi személyben kell futtatni.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-121">This will distribute general data to the **ResCalendarCapacity** table across all companies in your environment, so the batch job only needs to be run in one legal entity.</span></span> <span data-ttu-id="7e8fb-122">Az ebben a kötegelt feladatban szereplő adatok szükségesek az erőforráskapacitás a társított naptáron keresztül történő számításához.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-122">The data in this batch job is needed to calculate resource capacity through the associated calendar.</span></span>

8. <span data-ttu-id="7e8fb-123">Nyissa meg a **Projektvezetés és könyvelés** > **Időszakos** > **Projekterőforrások** > **Projekterőforrások kitöltése az összes vállalat között** menüt, és válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-123">Go to **Project management and accounting** > **Periodic** > **Project resources** > **Populate project resources across all companies** and then select **OK**.</span></span> <span data-ttu-id="7e8fb-124">Ez a **ResProjectResource**, **ResCalendarDateTimeRange** és **ResEffectiveDateTimeRange** táblák általános adatainak adatfrissítési parancsfájlja.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-124">This is the data upgrade script for general data in the **ResProjectResource**, **ResCalendarDateTimeRange**, and **ResEffectiveDateTimeRange** tables.</span></span> <span data-ttu-id="7e8fb-125">A **PSAPRojSchedRole.RootActivity** mező értékeit is frissíti a program.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-125">Values for the **PSAPRojSchedRole.RootActivity** field are also updated.</span></span> <span data-ttu-id="7e8fb-126">Ha ez nem fut, akkor figyelmeztetés jelenik meg, amikor megpróbálja végrehajtani az erőforrás-ütemezési műveleteket.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-126">If this is not run, you will receive a warning when you try to execute resource scheduling operations.</span></span>
 
## <a name="turn-off-resource-scheduling-performance-enhancement"></a><span data-ttu-id="7e8fb-127">Az erőforrás-ütemezés teljesítményjavításának kikapcsolása</span><span class="sxs-lookup"><span data-stu-id="7e8fb-127">Turn off resource scheduling performance enhancement</span></span>

1. <span data-ttu-id="7e8fb-128">Nyissa meg a **Funkciókezelés** > **Összes** elemet, majd keresse meg a **Az erőforrás-ütemezés teljesítményjavítása funkció engedélyezése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-128">Go to **Feature management** > **All**  and search for **Enable project resource scheduling performance enhancement feature**.</span></span>
2. <span data-ttu-id="7e8fb-129">Válassza ki a funkciót, majd válassza a **Letiltás** gombot.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-129">Select the feature, and then select the **Disable** button.</span></span>
3. <span data-ttu-id="7e8fb-130">Frissítse a böngészőt.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-130">Refresh your browser.</span></span>
4. <span data-ttu-id="7e8fb-131">Válassza a **Projektvezetés és könyvelés** > **Időszakos** > **Kapacitásszinkronizálás** > **Erőforrás kapacitás-összesítéseinek szinkronizálása** lehetőségeket.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-131">Go to **Project management and accounting** > **Periodic** > **Capacity synchronization** > **Synchronize resource capacity roll-ups**.</span></span>
5. <span data-ttu-id="7e8fb-132">A **Kapacitás összesítő szinkronizálása** lapon állítsa be a **Meglévő kapacitás-rekordok eltávolítása** elemet **Igen** értékre a korábbi adatok eltávolításához.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-132">On the **Capacity roll-up synchronization** page, set **Remove existing capacity records** to **Yes** to remove previous data.</span></span> <span data-ttu-id="7e8fb-133">Ha növekményes adatokat szeretne generálni, állítsa **Nem** értékre.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-133">If you want to generate incremental data, set it to **No**.</span></span>
6. <span data-ttu-id="7e8fb-134">Az **időszak kódja** mezőben válassza ki azt az időszakot, amelyben az adatokat létrehozni kell.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-134">In the **Period code** field, select the period in which data should be generated.</span></span> <span data-ttu-id="7e8fb-135">Ha kiválaszt egy időszakot, akkor nem kell megadni a kezdő és a záró dátumot.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-135">If you select a period code, a start and end date do not need to be defined.</span></span>
7. <span data-ttu-id="7e8fb-136">Ha üresen hagyja az **Időszak kódja** mezőt, válassza ki a kezdési és befejezési dátumokat az adatok generálásához.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-136">If you leave the **Period code** field blank, select specific start and end dates to generate data.</span></span>
8. <span data-ttu-id="7e8fb-137">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-137">Select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="7e8fb-138">Ennek hatására a program a környezete összes vállalata között megosztja az általános adatokat a **ResRollup** táblába, így a kötegelt feladatot csak egy jogi személyben kell futtatni.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-138">This will distribute general data to the **ResRollup** table across all companies in your environment, so the batch job only needs to be run in one legal entity.</span></span> <span data-ttu-id="7e8fb-139">Ez a kötegelt feladat minden **Erőforrás elérhetősége** nézet esetében szükséges.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-139">This batch job is needed for all **Resource Availability** views.</span></span> <span data-ttu-id="7e8fb-140">Ha ezt a kötegelt feladatot nem futtatja, akkor a program a **ResRollup** adatait a menet közben hozza létre, amely időt vehet igénybe.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-140">If this batch job is not run, the **ResRollup** data will be generated on the fly, which can take time.</span></span>
