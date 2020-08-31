---
title: Párhuzamos tevékenységek beállítása munkafolyamatban
description: A párhuzamos tevékenység beállításához végezze el a következő eljárásokat a munkafolyamat-szerkesztőben.
author: ChrisGarty
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 998ee559a092c4acd34a6df05e893bdbf4289099
ms.sourcegitcommit: e55efd2f62bf60f678108c09ad4701a76b20cc68
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/17/2020
ms.locfileid: "3698315"
---
# <a name="configure-parallel-activities-in-a-workflow"></a><span data-ttu-id="79329-103">Párhuzamos tevékenységek beállítása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="79329-103">Configure parallel activities in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="79329-104">A párhuzamos tevékenység beállításához végezze el a következő eljárásokat a munkafolyamat-szerkesztőben.</span><span class="sxs-lookup"><span data-stu-id="79329-104">To configure a parallel activity, complete the following procedures in the workflow editor.</span></span>

<span data-ttu-id="79329-105">A párhuzamos tevékenység egy időben futó munkafolyamatágakból áll.</span><span class="sxs-lookup"><span data-stu-id="79329-105">A parallel activity consists of workflow branches that run at the same time.</span></span>

## <a name="name-a-parallel-activity"></a><span data-ttu-id="79329-106">Párhuzamos tevékenység elnevezése</span><span class="sxs-lookup"><span data-stu-id="79329-106">Name a parallel activity</span></span>

<span data-ttu-id="79329-107">A következő lépések segítségével elnevezheti a párhuzamos tevékenységet.</span><span class="sxs-lookup"><span data-stu-id="79329-107">Follow these steps to enter a name for a parallel activity.</span></span>

1. <span data-ttu-id="79329-108">Kattintson a jobb gombbal a párhuzamos tevékenységre, majd kattintson a **Tulajdonságok** lehetőségre a **Tulajdonságok** űrlap megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="79329-108">Right-click the parallel activity, and then click **Properties** to open the **Properties** form.</span></span>
2. <span data-ttu-id="79329-109">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="79329-109">In the left pane, click **Basic Settings**.</span></span>
3. <span data-ttu-id="79329-110">Adja meg a párhuzamos tevékenység egyedi nevét a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="79329-110">In the **Name** field, enter a unique name for the parallel activity.</span></span>
4. <span data-ttu-id="79329-111">Kattintson a **Bezárás** gombra.</span><span class="sxs-lookup"><span data-stu-id="79329-111">Click **Close**.</span></span>

## <a name="configure-the-branches-of-a-parallel-activity"></a><span data-ttu-id="79329-112">A párhuzamos tevékenység ágainak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="79329-112">Configure the branches of a parallel activity</span></span>

<span data-ttu-id="79329-113">Végezze el a következő lépéseket a párhuzamos tevékenység ágainak hozzáadása és konfigurálása érdekében.</span><span class="sxs-lookup"><span data-stu-id="79329-113">Follow these steps to add and configure the branches of this parallel activity.</span></span>

1. <span data-ttu-id="79329-114">Kattintson duplán a párhuzamos tevékenységre a párhuzamos tevékenység ágainak megjelenítése érdekében.</span><span class="sxs-lookup"><span data-stu-id="79329-114">Double-click the parallel activity to display the branches of the parallel activity.</span></span>
2. <span data-ttu-id="79329-115">Ág hozzáadásához húzza az **Ág** elemet a **Munkafolyamat-elemek** területről a vászon egyik beillesztési pontjára.</span><span class="sxs-lookup"><span data-stu-id="79329-115">To add a branch, drag the **Branch** element from the **Workflow elements** area to an insertion point on the canvas.</span></span> <span data-ttu-id="79329-116">Az alábbi ábrán egy beillesztési pont látható.</span><span class="sxs-lookup"><span data-stu-id="79329-116">The following figure shows an insertion point.</span></span>

    ![Beillesztési pont](./media/workflow_insertionpoint.gif)

    > [!NOTE]
    > <span data-ttu-id="79329-118">Az ágának sorrendje nem számít, mivel a párhuzamos tevékenység ágai egyszerre futnak.</span><span class="sxs-lookup"><span data-stu-id="79329-118">The order of the branches is not important because all the branches of a parallel activity run at the same time.</span></span>

3. <span data-ttu-id="79329-119">Az egyes ágak konfigurálása: [Párhuzamos ágak konfigurálása munkafolyamatban](configure-parallel-branch-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="79329-119">To configure each branch, see [Configure parallel branches in a workflow](configure-parallel-branch-workflow.md).</span></span>
