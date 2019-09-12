---
title: Szolgáltatási szint és leírás
description: Ez a témakör az Eszközkezelés modul szolgáltatási szintjeit és azok leírását ismerteti.
author: josaw1
manager: AnnBe
ms.date: 08/13/2019
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
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5e645c25208f55b1032bc7f7c181c72db7a2f265
ms.sourcegitcommit: 802dbf0a744d70f9e546632d419415b0993331ab
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/13/2019
ms.locfileid: "1874647"
---
# <a name="service-level-and-description"></a><span data-ttu-id="7c1e9-103">Szolgáltatási szint és leírás</span><span class="sxs-lookup"><span data-stu-id="7c1e9-103">Service level and description</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="7c1e9-104">Munkarendelések létrehozásakor megadhatja, hogy az adott munkarendelés milyen szolgáltatási szinteket és leírást tartalmazzon.</span><span class="sxs-lookup"><span data-stu-id="7c1e9-104">When you create a work order, you might want to define the service levels for it and add a general description to it.</span></span> <span data-ttu-id="7c1e9-105">Munkarendelési szolgáltatási szintet a **Munkarendelési szolgáltatási szintek** lapon és a **Munkarendelési szolgáltatási leírás** lapon hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="7c1e9-105">You can create work order service levels on the **Work order service levels** page and descriptions on the **Work order description** page.</span></span>

## <a name="create-a-service-level"></a><span data-ttu-id="7c1e9-106">Szolgáltatási szint létrehozása</span><span class="sxs-lookup"><span data-stu-id="7c1e9-106">Create a service level</span></span>

1. <span data-ttu-id="7c1e9-107">Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Munkarendelések** \> **Szolgáltatási szint** elemet.</span><span class="sxs-lookup"><span data-stu-id="7c1e9-107">Select **Asset management** \> **Setup** \> **Work orders** \> **Service level**.</span></span>
2. <span data-ttu-id="7c1e9-108">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7c1e9-108">Select **New**.</span></span>
3. <span data-ttu-id="7c1e9-109">A **Szolgáltatási szint** mezőben adja meg a szolgáltatási szintet (például egy számot).</span><span class="sxs-lookup"><span data-stu-id="7c1e9-109">In the **Service level** field, enter the service level (for example, a number).</span></span>
4. <span data-ttu-id="7c1e9-110">A **Név** mezőben adjon meg egy nevet.</span><span class="sxs-lookup"><span data-stu-id="7c1e9-110">In the **Name** field, enter a name.</span></span>

    <span data-ttu-id="7c1e9-111">A **Munkarendelések** gyorslapon meghatározhatja a várt kezdő és befejező dátumokat és időpontokat.</span><span class="sxs-lookup"><span data-stu-id="7c1e9-111">On the **Work orders** FastTab, you can define expected start and end dates and times.</span></span> <span data-ttu-id="7c1e9-112">A gyorslap mezői határozzák meg azt az időszakot, amikor a munkarendeléseket el kell indítani és be kell fejezni.</span><span class="sxs-lookup"><span data-stu-id="7c1e9-112">The fields on this FastTab define the period that work orders should be started and ended during.</span></span> <span data-ttu-id="7c1e9-113">Ezek a saját kezűleg létrehozott munkarendelések, valamint a karbantartási kérések alapján létrehozott munkarendelések esetében használhatók.</span><span class="sxs-lookup"><span data-stu-id="7c1e9-113">They are used for work orders that are manually created and work orders that are created based on maintenance requests.</span></span> 

5. <span data-ttu-id="7c1e9-114">A **Kezdő nap** mezőben adja meg azt az időszakot (napok számát), ameddig a munkarendelésnek meg kell kezdődnie.</span><span class="sxs-lookup"><span data-stu-id="7c1e9-114">In the **Start day** field, enter a number of days to define the period that the work order should start during.</span></span> <span data-ttu-id="7c1e9-115">A napok számát a munkarendelés létrehozásától kezdődően számolja ki a rendszer.</span><span class="sxs-lookup"><span data-stu-id="7c1e9-115">The number of days is calculated from the creation date of the work order.</span></span> <span data-ttu-id="7c1e9-116">Ha például a munkarendelést a létrehozáskor kell elindítani, adja meg a **0**értéket.</span><span class="sxs-lookup"><span data-stu-id="7c1e9-116">For example, if the work order should start when it's created, enter **0**.</span></span> <span data-ttu-id="7c1e9-117">Ha a munkarendelést a létrehozása után egy héten belül el kell indítani, akkor a **7-et** írja be.</span><span class="sxs-lookup"><span data-stu-id="7c1e9-117">If the work order should start within one week after it's created, enter **7**.</span></span>
6. <span data-ttu-id="7c1e9-118">Ha a munkarendelés kezdő időpontját is meg szeretné adni a kezdő dátumon kívül, állítsa a **Kezdő dátum beállítása** lehetőséget **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="7c1e9-118">To set a start time for the work order, in addition to a start date, set the **Set start time** option to **Yes**.</span></span> <span data-ttu-id="7c1e9-119">Ezután írja be a kezdő időpontot a **Kezdő időpont** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="7c1e9-119">Then enter the start time in the **Start time** field.</span></span> <span data-ttu-id="7c1e9-120">Ha a beállítást **Nem**értékre állítja, akkor a program az aktuális időpontot használja.</span><span class="sxs-lookup"><span data-stu-id="7c1e9-120">If you set the option to **No**, the current time of day is used.</span></span>
7. <span data-ttu-id="7c1e9-121">A **Záró nap** mezőben adja meg azt az időszakot (napok számát), ameddig a munkarendelésnek be kell fejeződnie.</span><span class="sxs-lookup"><span data-stu-id="7c1e9-121">In the **End day** field, enter a number of days to define the period that the work order should end during.</span></span> <span data-ttu-id="7c1e9-122">A napok számát a munkarendelés kezdő dátumától kezdődően számolja ki a rendszer.</span><span class="sxs-lookup"><span data-stu-id="7c1e9-122">The number of days is calculated from the start date of the work order.</span></span> <span data-ttu-id="7c1e9-123">Ha például a munkarendelésnek a kezdő dátumtól számítva egy héten belül be kell fejeződnie, akkor a **7-et** írja be.</span><span class="sxs-lookup"><span data-stu-id="7c1e9-123">For example, if the work order should end within one week of its start date, enter **7**.</span></span>
8. <span data-ttu-id="7c1e9-124">Ha a munkarendelés záró időpontját is meg szeretné adni a záró dátumon kívül, állítsa a **Záró dátum beállítása** lehetőséget **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="7c1e9-124">To set an end time for the work order, in addition to an end date, set the **Set end time** option to **Yes**.</span></span> <span data-ttu-id="7c1e9-125">Ezután írja be a záró időpontot a **Záró időpont** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="7c1e9-125">Then enter the end time in the **End time** field.</span></span> <span data-ttu-id="7c1e9-126">Ha a beállítást **Nem**értékre állítja, akkor a program az aktuális időpontot használja.</span><span class="sxs-lookup"><span data-stu-id="7c1e9-126">If you set the option to **No**, the current time of day is used.</span></span>
9. <span data-ttu-id="7c1e9-127">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7c1e9-127">Select **Save**.</span></span>

![1. ábra](media/19-setup-for-work-orders.png)

## <a name="create-a-description"></a><span data-ttu-id="7c1e9-129">Leírás létrehozása</span><span class="sxs-lookup"><span data-stu-id="7c1e9-129">Create a description</span></span>

1. <span data-ttu-id="7c1e9-130">Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Munkarendelések** \> **Leírások** elemet.</span><span class="sxs-lookup"><span data-stu-id="7c1e9-130">Select **Asset management** \> **Setup** \> **Work orders** \> **Descriptions**.</span></span>
2. <span data-ttu-id="7c1e9-131">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7c1e9-131">Select **New**.</span></span>
3. <span data-ttu-id="7c1e9-132">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="7c1e9-132">In the **Description** field, enter the description.</span></span>
4. <span data-ttu-id="7c1e9-133">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7c1e9-133">Select **Save**.</span></span>
