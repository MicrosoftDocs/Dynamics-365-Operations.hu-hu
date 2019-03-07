---
title: Sortétel munkafolyamatok konfigurálása
description: Ez a témakör bemutatja a sortétel-munkafolyamat-elem beállításának menetét.
author: sericks007
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
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 66e79389bba4566176330914ace462110cd0aa22
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "336106"
---
# <a name="configure-line-item-workflows"></a><span data-ttu-id="f9b47-103">Sortétel munkafolyamatok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="f9b47-103">Configure line-item workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f9b47-104">Ez a témakör bemutatja a sortétel-munkafolyamat-elem beállításának menetét.</span><span class="sxs-lookup"><span data-stu-id="f9b47-104">This topic explains how to configure a line-item workflow element.</span></span>

<span data-ttu-id="f9b47-105">A sortétel munkafolyamatának a munkafolyamat-szerkesztőben történő beállításához kattintson a jobb gombbal az elemre, és kattintson **Tulajdonságok** lap megnyitásához a **Tulajdonságok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f9b47-105">To configure a line-item workflow element, in the workflow editor, right-click the element, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="f9b47-106">Ezután a következő eljárások segítségével beállíthatja a sortétel munkafolyamat-elem különféle tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="f9b47-106">Then use the following procedures to configure the properties of the line-item workflow element.</span></span>

## <a name="name-the-line-item-workflow-element"></a><span data-ttu-id="f9b47-107">A sortétel-munkafolyamat-elem elnevezése</span><span class="sxs-lookup"><span data-stu-id="f9b47-107">Name the line-item workflow element</span></span>

<span data-ttu-id="f9b47-108">A következő lépések segítségével elnevezheti a sortétel munkafolyamat-elemet.</span><span class="sxs-lookup"><span data-stu-id="f9b47-108">Follow these steps to enter a name for the line-item workflow element.</span></span>

1. <span data-ttu-id="f9b47-109">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="f9b47-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="f9b47-110">A **Név** mezőbe írja be a sortétel munkafolyamat-elem egyedi nevét.</span><span class="sxs-lookup"><span data-stu-id="f9b47-110">In the **Name** field, enter a unique name for the line-item workflow element.</span></span>

## <a name="specify-whether-the-same-workflow-is-used-to-process-all-line-items"></a><span data-ttu-id="f9b47-111">Adja meg, hogy ugyanazon munkafolyamat segítségével dolgozza-e fel az összes sortételt</span><span class="sxs-lookup"><span data-stu-id="f9b47-111">Specify whether the same workflow is used to process all line items</span></span>

<span data-ttu-id="f9b47-112">A következőképpen határozhatja meg, hogy ugyanazon munkafolyamat segítségével akarja-e feldolgozni a dokumentum összes sortételét.</span><span class="sxs-lookup"><span data-stu-id="f9b47-112">Follow these steps to specify whether the same workflow is used to process all the line items on a document.</span></span>

1. <span data-ttu-id="f9b47-113">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="f9b47-113">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="f9b47-114">Ha ugyanazon munkafolyamattal akarja feldolgozni a dokumentum összes sortételét, kattintson az **Egyetlen munkafolyamat indítása az összes sortételhez** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f9b47-114">If the same workflow should process all the line items on a document, click **Invoke a single workflow for all line-items**.</span></span> <span data-ttu-id="f9b47-115">Ezután válassza ki a sortételek feldolgozásához használni kívánt munkafolyamatot.</span><span class="sxs-lookup"><span data-stu-id="f9b47-115">Then select the workflow to use to process the line items.</span></span>
3. <span data-ttu-id="f9b47-116">Ha egy bizonyos feltételkészletnek megfelelő sortételeket egy bizonyos munkafolyamattal akarja feldolgozni, kattintson a **Külön munkafolyamat indítása minden egyes sortételhez** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f9b47-116">If a specific workflow should process line items that meet a specific set of conditions, click **Invoke a workflow for each line-item**.</span></span> <span data-ttu-id="f9b47-117">Ezután hajtsa végre a következő lépéseket a feltételkészlet meghatározásához:</span><span class="sxs-lookup"><span data-stu-id="f9b47-117">Then follow these steps to define the set of conditions:</span></span>

    1. <span data-ttu-id="f9b47-118">Kattintson a **Hozzáadás** gombra.</span><span class="sxs-lookup"><span data-stu-id="f9b47-118">Click **Add**.</span></span>
    2. <span data-ttu-id="f9b47-119">Válassza ki a táblán levő feltételt.</span><span class="sxs-lookup"><span data-stu-id="f9b47-119">Select the condition in the table.</span></span>
    3. <span data-ttu-id="f9b47-120">A **Feltétel neve** lapon írja be a meghatározni kívánt feltételkészlet nevét.</span><span class="sxs-lookup"><span data-stu-id="f9b47-120">On the **Condition name** tab, enter a name for the set of conditions that you're defining.</span></span>
    4. <span data-ttu-id="f9b47-121">Kattintson a **Feltétel hozzáadása** lehetőségre a feltétel beírásához.</span><span class="sxs-lookup"><span data-stu-id="f9b47-121">Click **Add condition** to enter a condition.</span></span>
    5. <span data-ttu-id="f9b47-122">Adja meg a további szükséges feltételeket.</span><span class="sxs-lookup"><span data-stu-id="f9b47-122">Enter any additional conditions that are required.</span></span>
    6. <span data-ttu-id="f9b47-123">Ha ellenőrizni szeretné a megadott feltételkészlet beállításának helyességét, kattintson a **Teszt** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f9b47-123">To verify that the set of conditions that you entered is configured correctly, click **Test**.</span></span> <span data-ttu-id="f9b47-124">A **Munkafolyamati feltétel tesztelése** lapon, a **Feltétel érvényesítése** területen válasszon ki egy rekordot, majd kattintson a **Teszt** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f9b47-124">On the **Test workflow condition** page, in the **Validate condition** area, select a record, and then click **Test**.</span></span> <span data-ttu-id="f9b47-125">A rendszer értékeli a bejegyzést, annak érdekében, hogy meghatározza, hogy a meghatározott feltételeknek megfeleljen-e.</span><span class="sxs-lookup"><span data-stu-id="f9b47-125">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span> <span data-ttu-id="f9b47-126">Kattintson az **OK** vagy a **Mégse** lehetőségre a **Tulajdonságok** lapra történő visszalépéshez.</span><span class="sxs-lookup"><span data-stu-id="f9b47-126">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

    <span data-ttu-id="f9b47-127">A **Munkafolyamat** lapon válassza ki azon sortételek feldolgozásához használni kívánt munkafolyamatot, amelyek megfelelnek a meghatározott feltételkészletnek.</span><span class="sxs-lookup"><span data-stu-id="f9b47-127">On the **Workflow** tab, select the workflow select the workflow to use to process line items that meet the set of conditions that you defined.</span></span>
