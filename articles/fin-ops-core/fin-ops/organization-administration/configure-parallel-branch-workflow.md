---
title: Párhuzamos ágak konfigurálása munkafolyamatban
description: A párhuzamos ág beállításához végezze el a következő eljárásokat a munkafolyamat-szerkesztőben.
author: ChrisGarty
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 196043
ms.assetid: dfdae2b8-6a4f-4760-b339-b755c66f3f89
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 37c177e8c4c4e40bd81287430d9ee7598cf917d8
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566991"
---
# <a name="configure-parallel-branches-in-a-workflow"></a><span data-ttu-id="a7ee3-103">Párhuzamos ágak konfigurálása munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="a7ee3-103">Configure parallel branches in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a7ee3-104">A párhuzamos ág beállításához végezze el a következő eljárásokat a munkafolyamat-szerkesztőben.</span><span class="sxs-lookup"><span data-stu-id="a7ee3-104">To configure a parallel branch, complete the following procedures in the workflow editor.</span></span>

<span data-ttu-id="a7ee3-105">A párhuzamos ág lényegében egy fölérendelt munkafolyamat részeként futó munkafolyamat.</span><span class="sxs-lookup"><span data-stu-id="a7ee3-105">A parallel branch is essentially a workflow that runs in the context of a parent workflow.</span></span>

## <a name="name-a-branch"></a><span data-ttu-id="a7ee3-106">Ág elnevezése</span><span class="sxs-lookup"><span data-stu-id="a7ee3-106">Name a branch</span></span>

<span data-ttu-id="a7ee3-107">A következő lépések segítségével nevezheti el a párhuzamos ágat.</span><span class="sxs-lookup"><span data-stu-id="a7ee3-107">Follow these steps to enter a name for a parallel branch.</span></span>

1. <span data-ttu-id="a7ee3-108">Kattintson a jobb egérgombbal a párhuzamos ágra, majd kattintson a **Tulajdonságokra**.</span><span class="sxs-lookup"><span data-stu-id="a7ee3-108">Right-click the parallel branch, and then click **Properties**.</span></span> <span data-ttu-id="a7ee3-109">Megjelenik a **Tulajdonságok** űrlapja.</span><span class="sxs-lookup"><span data-stu-id="a7ee3-109">The **Properties** form is displayed.</span></span>
2. <span data-ttu-id="a7ee3-110">A bal oldali panelen kattintson az **Alapbeállítások** gombra.</span><span class="sxs-lookup"><span data-stu-id="a7ee3-110">In the left pane, click **Basic Settings**.</span></span>
3. <span data-ttu-id="a7ee3-111">Adja meg a párhuzamos ág egyedi nevét a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="a7ee3-111">In the **Name** field, enter a unique name for the parallel branch.</span></span>
4. <span data-ttu-id="a7ee3-112">Kattintson a **Bezárás** gombra.</span><span class="sxs-lookup"><span data-stu-id="a7ee3-112">Click **Close**.</span></span>

## <a name="design-and-configure-the-elements-of-a-branch"></a><span data-ttu-id="a7ee3-113">Tervezze meg és konfigurálja az ág elemeit</span><span class="sxs-lookup"><span data-stu-id="a7ee3-113">Design and configure the elements of a branch</span></span>

<span data-ttu-id="a7ee3-114">Végezze el a következő lépéseket a párhuzamos ág elemeinek megtervezéséhez és konfigurálásához.</span><span class="sxs-lookup"><span data-stu-id="a7ee3-114">Follow these steps to design and configure the elements of a parallel branch.</span></span>

1. <span data-ttu-id="a7ee3-115">Kattintson duplán a párhuzamos ágra.</span><span class="sxs-lookup"><span data-stu-id="a7ee3-115">Double-click the parallel branch.</span></span>
2. <span data-ttu-id="a7ee3-116">Húzzon munkafolyamat-elemeket a vászonra, majd állítsa be az elemeket, ugyanúgy, mint bármely más munkafolyamat létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="a7ee3-116">Drag workflow elements onto the canvas, and then configure the elements, just as you would to create any other workflow.</span></span> <span data-ttu-id="a7ee3-117">További információ: [Munkafolyamatok létrehozása – áttekintés](create-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="a7ee3-117">For more information, see [Create workflows overview](create-workflow.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a7ee3-118">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="a7ee3-118">Additional resources</span></span>

[<span data-ttu-id="a7ee3-119">Munkafolyamatok létrehozása – áttekintés</span><span class="sxs-lookup"><span data-stu-id="a7ee3-119">Create workflows overview</span></span>](create-workflow.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]