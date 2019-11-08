---
title: Munkarendelések létrehozása
description: Ez a cikk azt mutatja be, hogyan lehet munkarendeléseket létrehozni az Eszközkezelés modulban.
author: josaw1
manager: AnnBe
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 6e910b2400106baf9f9dc06f6bc0d3daee8e4a43
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2019
ms.locfileid: "2570076"
---
# <a name="creating-work-orders"></a><span data-ttu-id="0d179-103">Munkarendelések létrehozása</span><span class="sxs-lookup"><span data-stu-id="0d179-103">Creating work orders</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="0d179-104">A megelőző karbantartási feladatok ütemezése után a következő lépés a feladatok munkarendeléseinek létrehozása.</span><span class="sxs-lookup"><span data-stu-id="0d179-104">When you have scheduled preventive maintenance jobs, next step is to create work orders for the jobs.</span></span> <span data-ttu-id="0d179-105">Ezt a karbantartási ütemezés képernyőn kell elvégezni:</span><span class="sxs-lookup"><span data-stu-id="0d179-105">This is done in one of the maintenance schedules.</span></span> <span data-ttu-id="0d179-106">A karbantartási ütemezésben szereplő ütemezett feladatok különböző hivatkozási típusokkal rendelkezhetnek:</span><span class="sxs-lookup"><span data-stu-id="0d179-106">The scheduled jobs in a maintenance schedule can have different reference types:</span></span>

| <span data-ttu-id="0d179-107">Hivatkozás típusa</span><span class="sxs-lookup"><span data-stu-id="0d179-107">Reference type</span></span> | <span data-ttu-id="0d179-108">Leírás</span><span class="sxs-lookup"><span data-stu-id="0d179-108">Description</span></span>                    |
|-----------------------|------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="0d179-109">Karbantartási tervek</span><span class="sxs-lookup"><span data-stu-id="0d179-109">Maintenance plans</span></span>     | <span data-ttu-id="0d179-110">Megelőző karbantartási feladatok az „idő” vagy a „számláló” típusú karbantartási konstrukciók alapján.</span><span class="sxs-lookup"><span data-stu-id="0d179-110">Preventive maintenance jobs based on maintenance plan types "Time" or "Counter".</span></span>                       |
| <span data-ttu-id="0d179-111">Karbantartási körök</span><span class="sxs-lookup"><span data-stu-id="0d179-111">Maintenance rounds</span></span>    | <span data-ttu-id="0d179-112">Olyan megelőző karbantartási feladatok, amelyek számos, hasonló típusú karbantartást igénylő eszközt tartalmaznak.</span><span class="sxs-lookup"><span data-stu-id="0d179-112">Preventive maintenance jobs containing several assets that require a similar type of maintenance.</span></span>           |
| <span data-ttu-id="0d179-113">Karbantartási kérés</span><span class="sxs-lookup"><span data-stu-id="0d179-113">Maintenance request</span></span>   | <span data-ttu-id="0d179-114">Egy eszköz karbantartására vagy javítására irányuló, manuálisan létrehozott kérelem, amely átalakítható munkarendelésbe.</span><span class="sxs-lookup"><span data-stu-id="0d179-114">Manually created request for maintenance or repair of an asset, which can be converted into a work order.</span></span> |


1. <span data-ttu-id="0d179-115">Kattintson az **Eszközkezelés** > **Közös** > **Összes karbantartási ütemezés** vagy **Nyitott karbantartási ütemezési sorok** vagy **Nyitott karbantartási ütemezési csoportok** elemre.</span><span class="sxs-lookup"><span data-stu-id="0d179-115">Click **Asset management** > **Common** > **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools**.</span></span>

2. <span data-ttu-id="0d179-116">Válassza ki azt azokat az ütemezett karbantartási munkákat, amelyhez munkarendelést szeretne létrehozni, majd kattintson a **Munkarendelés** elemre.</span><span class="sxs-lookup"><span data-stu-id="0d179-116">Select the scheduled maintenance jobs for which you want to create a work order and click **Work order**.</span></span> <span data-ttu-id="0d179-117">A **Munkarendelések létrehozása** párbeszédpanelen kiválasztott sorokhoz tartozó összes előrejelzési órák száma a **Karbantartási előrejelzési órák** mezőben látható.</span><span class="sxs-lookup"><span data-stu-id="0d179-117">In the **Create work orders** dialog, the total number of forecast hours for the selected lines is shown in the **Maintenance forecast hours** field.</span></span>

3. <span data-ttu-id="0d179-118">A **Paraméterek** szakaszban válassza ki, hogy hány munkarendelést kell létrehozni.</span><span class="sxs-lookup"><span data-stu-id="0d179-118">In the **Parameters** section, select how many work orders should be created.</span></span> <span data-ttu-id="0d179-119">Karbantartási ütemezés soronként létrehozhat egy munkarendelést, illetve számos munkarendelést az **Egy munkarendelés per** alapján.</span><span class="sxs-lookup"><span data-stu-id="0d179-119">You can create one work order per maintenance schedule line, or a number of work orders based on your selections in the **One work order per** section.</span></span>

4. <span data-ttu-id="0d179-120">Válassza ki azt a **Munkarendelés-típust**, amelyet a létrehozott összes munkarendelésnél használni fog.</span><span class="sxs-lookup"><span data-stu-id="0d179-120">Select a **Work order type** that will be used on all the work orders you create.</span></span> <span data-ttu-id="0d179-121">Az alábbi ábra a **Munkarendelések létrehozása** párbeszédpanel egy példáját mutatja be.</span><span class="sxs-lookup"><span data-stu-id="0d179-121">The illustration below shows an example of the **Create work orders** dialog.</span></span>

![1. ábra](media/18-preventive-maintenance.png)

5. <span data-ttu-id="0d179-123">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="0d179-123">Click **OK**.</span></span> <span data-ttu-id="0d179-124">Egy vagy több munkarendelést hoz létre a program.</span><span class="sxs-lookup"><span data-stu-id="0d179-124">One or more work orders are created.</span></span>

