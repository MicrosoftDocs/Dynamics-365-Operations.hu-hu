---
title: Sortétel munkafolyamatok konfigurálása
description: Ez a témakör bemutatja a sortétel-munkafolyamat-elem beállításának menetét.
author: ChrisGarty
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195833
ms.assetid: 3237347e-71d5-4569-bc9a-0d0fc9410b78
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f35676799a625656b6885cbc33d30870cee85e12
ms.sourcegitcommit: e55efd2f62bf60f678108c09ad4701a76b20cc68
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/17/2020
ms.locfileid: "3698195"
---
# <a name="configure-line-item-workflows"></a><span data-ttu-id="546da-103">Sortétel munkafolyamatok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="546da-103">Configure line-item workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="546da-104">Ez a témakör bemutatja a sortétel-munkafolyamat-elem beállításának menetét.</span><span class="sxs-lookup"><span data-stu-id="546da-104">This topic explains how to configure a line-item workflow element.</span></span>

<span data-ttu-id="546da-105">A sortétel munkafolyamatának a munkafolyamat-szerkesztőben történő beállításához kattintson a jobb gombbal az elemre, és kattintson **Tulajdonságok** lap megnyitásához a **Tulajdonságok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="546da-105">To configure a line-item workflow element, in the workflow editor, right-click the element, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="546da-106">Ezután a következő eljárások segítségével beállíthatja a sortétel munkafolyamat-elem különféle tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="546da-106">Then use the following procedures to configure the properties of the line-item workflow element.</span></span>

## <a name="name-the-line-item-workflow-element"></a><span data-ttu-id="546da-107">A sortétel-munkafolyamat-elem elnevezése</span><span class="sxs-lookup"><span data-stu-id="546da-107">Name the line-item workflow element</span></span>

<span data-ttu-id="546da-108">A következő lépések segítségével elnevezheti a sortétel munkafolyamat-elemet.</span><span class="sxs-lookup"><span data-stu-id="546da-108">Follow these steps to enter a name for the line-item workflow element.</span></span>

1. <span data-ttu-id="546da-109">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="546da-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="546da-110">A **Név** mezőbe írja be a sortétel munkafolyamat-elem egyedi nevét.</span><span class="sxs-lookup"><span data-stu-id="546da-110">In the **Name** field, enter a unique name for the line-item workflow element.</span></span>

## <a name="specify-whether-the-same-workflow-is-used-to-process-all-line-items"></a><span data-ttu-id="546da-111">Adja meg, hogy ugyanazon munkafolyamat segítségével dolgozza-e fel az összes sortételt</span><span class="sxs-lookup"><span data-stu-id="546da-111">Specify whether the same workflow is used to process all line items</span></span>

<span data-ttu-id="546da-112">A következőképpen határozhatja meg, hogy ugyanazon munkafolyamat segítségével akarja-e feldolgozni a dokumentum összes sortételét.</span><span class="sxs-lookup"><span data-stu-id="546da-112">Follow these steps to specify whether the same workflow is used to process all the line items on a document.</span></span>

1. <span data-ttu-id="546da-113">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="546da-113">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="546da-114">Ha ugyanazon munkafolyamattal akarja feldolgozni a dokumentum összes sortételét, kattintson az **Egyetlen munkafolyamat indítása az összes sortételhez** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="546da-114">If the same workflow should process all the line items on a document, click **Invoke a single workflow for all line-items**.</span></span> <span data-ttu-id="546da-115">Ezután válassza ki a sortételek feldolgozásához használni kívánt munkafolyamatot.</span><span class="sxs-lookup"><span data-stu-id="546da-115">Then select the workflow to use to process the line items.</span></span>
3. <span data-ttu-id="546da-116">Ha egy bizonyos feltételkészletnek megfelelő sortételeket egy bizonyos munkafolyamattal akarja feldolgozni, kattintson a **Külön munkafolyamat indítása minden egyes sortételhez** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="546da-116">If a specific workflow should process line items that meet a specific set of conditions, click **Invoke a workflow for each line-item**.</span></span> <span data-ttu-id="546da-117">Ezután hajtsa végre a következő lépéseket a feltételkészlet meghatározásához:</span><span class="sxs-lookup"><span data-stu-id="546da-117">Then follow these steps to define the set of conditions:</span></span>

    1. <span data-ttu-id="546da-118">Kattintson a **Hozzáadás** gombra.</span><span class="sxs-lookup"><span data-stu-id="546da-118">Click **Add**.</span></span>
    2. <span data-ttu-id="546da-119">Válassza ki a táblán levő feltételt.</span><span class="sxs-lookup"><span data-stu-id="546da-119">Select the condition in the table.</span></span>
    3. <span data-ttu-id="546da-120">A **Feltétel neve** lapon írja be a meghatározni kívánt feltételkészlet nevét.</span><span class="sxs-lookup"><span data-stu-id="546da-120">On the **Condition name** tab, enter a name for the set of conditions that you're defining.</span></span>
    4. <span data-ttu-id="546da-121">Kattintson a **Feltétel hozzáadása** lehetőségre a feltétel beírásához.</span><span class="sxs-lookup"><span data-stu-id="546da-121">Click **Add condition** to enter a condition.</span></span>
    5. <span data-ttu-id="546da-122">Adja meg a további szükséges feltételeket.</span><span class="sxs-lookup"><span data-stu-id="546da-122">Enter any additional conditions that are required.</span></span>
    6. <span data-ttu-id="546da-123">Ha ellenőrizni szeretné a megadott feltételkészlet beállításának helyességét, kattintson a **Teszt** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="546da-123">To verify that the set of conditions that you entered is configured correctly, click **Test**.</span></span> <span data-ttu-id="546da-124">A **Munkafolyamati feltétel tesztelése** lapon, a **Feltétel érvényesítése** területen válasszon ki egy rekordot, majd kattintson a **Teszt** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="546da-124">On the **Test workflow condition** page, in the **Validate condition** area, select a record, and then click **Test**.</span></span> <span data-ttu-id="546da-125">A rendszer értékeli a bejegyzést, annak érdekében, hogy meghatározza, hogy a meghatározott feltételeknek megfeleljen-e.</span><span class="sxs-lookup"><span data-stu-id="546da-125">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span> <span data-ttu-id="546da-126">Kattintson az **OK** vagy a **Mégse** lehetőségre a **Tulajdonságok** lapra történő visszalépéshez.</span><span class="sxs-lookup"><span data-stu-id="546da-126">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

    <span data-ttu-id="546da-127">A **Munkafolyamat** lapon válassza ki azon sortételek feldolgozásához használni kívánt munkafolyamatot, amelyek megfelelnek a meghatározott feltételkészletnek.</span><span class="sxs-lookup"><span data-stu-id="546da-127">On the **Workflow** tab, select the workflow select the workflow to use to process line items that meet the set of conditions that you defined.</span></span>
