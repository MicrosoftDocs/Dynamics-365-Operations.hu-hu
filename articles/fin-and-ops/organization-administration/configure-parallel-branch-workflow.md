---
title: "Párhuzamos ágának konfigurálása munkafolyamatban"
description: "A párhuzamos ág beállításához végezze el a következő eljárásokat a munkafolyamat-szerkesztőben."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 196043
ms.assetid: dfdae2b8-6a4f-4760-b339-b755c66f3f89
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: d0e45f4a6b1f6bcf94103dbcf4a8ca01457dc85d
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---

# <a name="configure-a-parallel-branch-in-a-workflow"></a><span data-ttu-id="ccbac-103">Párhuzamos ágának konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="ccbac-103">Configure a parallel branch in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ccbac-104">A párhuzamos ág beállításához végezze el a következő eljárásokat a munkafolyamat-szerkesztőben.</span><span class="sxs-lookup"><span data-stu-id="ccbac-104">To configure a parallel branch, complete the following procedures in the workflow editor.</span></span>

<span data-ttu-id="ccbac-105">A párhuzamos ág lényegében egy fölérendelt munkafolyamat részeként futó munkafolyamat.</span><span class="sxs-lookup"><span data-stu-id="ccbac-105">A parallel branch is essentially a workflow that runs in the context of a parent workflow.</span></span>

## <a name="name-a-branch"></a><span data-ttu-id="ccbac-106">Ág elnevezése</span><span class="sxs-lookup"><span data-stu-id="ccbac-106">Name a branch</span></span>
<span data-ttu-id="ccbac-107">A következő lépések segítségével nevezheti el a párhuzamos ágat.</span><span class="sxs-lookup"><span data-stu-id="ccbac-107">Follow these steps to enter a name for a parallel branch.</span></span>
1.  <span data-ttu-id="ccbac-108">Kattintson a jobb egérgombbal a párhuzamos ágra, majd kattintson a **Tulajdonságokra**.</span><span class="sxs-lookup"><span data-stu-id="ccbac-108">Right-click the parallel branch, and then click **Properties**.</span></span> <span data-ttu-id="ccbac-109">Megjelenik a **Tulajdonságok** űrlapja.</span><span class="sxs-lookup"><span data-stu-id="ccbac-109">The **Properties** form is displayed.</span></span>
2.  <span data-ttu-id="ccbac-110">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="ccbac-110">In the left pane, click **Basic Settings**.</span></span>
3.  <span data-ttu-id="ccbac-111">Adja meg a párhuzamos ág egyedi nevét a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="ccbac-111">In the **Name** field, enter a unique name for the parallel branch.</span></span>
4.  <span data-ttu-id="ccbac-112">Kattintson a **Bezárás** gombra.</span><span class="sxs-lookup"><span data-stu-id="ccbac-112">Click **Close**.</span></span>

## <a name="design-and-configure-the-elements-of-a-branch"></a><span data-ttu-id="ccbac-113">Tervezze meg és konfigurálja az ág elemeit</span><span class="sxs-lookup"><span data-stu-id="ccbac-113">Design and configure the elements of a branch</span></span>
<span data-ttu-id="ccbac-114">Végezze el a következő lépéseket a párhuzamos ág elemeinek megtervezéséhez és konfigurálásához.</span><span class="sxs-lookup"><span data-stu-id="ccbac-114">Follow these steps to design and configure the elements of a parallel branch.</span></span>
1.  <span data-ttu-id="ccbac-115">Kattintson duplán a párhuzamos ágra.</span><span class="sxs-lookup"><span data-stu-id="ccbac-115">Double-click the parallel branch.</span></span>
2.  <span data-ttu-id="ccbac-116">Húzzon munkafolyamat-elemeket a vászonra, majd állítsa be az elemeket, ugyanúgy, mint bármely más munkafolyamat létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="ccbac-116">Drag workflow elements onto the canvas, and then configure the elements, just as you would to create any other workflow.</span></span> <span data-ttu-id="ccbac-117">További tudnivalókkal kapcsolatban lásd: Munkafolyamat létrehozása.</span><span class="sxs-lookup"><span data-stu-id="ccbac-117">For more information, see Create a workflow.</span></span>



<a name="additional-resources"></a><span data-ttu-id="ccbac-118">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="ccbac-118">Additional resources</span></span>
--------

[<span data-ttu-id="ccbac-119">Munkafolyamat létrehozása</span><span class="sxs-lookup"><span data-stu-id="ccbac-119">Create a workflow</span></span>](create-workflow.md)




