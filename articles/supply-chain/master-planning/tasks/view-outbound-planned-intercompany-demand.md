---
title: Kimenő tervezett vállalatközi igény megtekintése
description: Ez az eljárás bemutatja, hogyan tekinthetők meg a vállalatközi szállítók által teljesítendő rendelések.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqOutboundIntercompanyDemand
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2e0e3a4613e5598e725c475c7dff7662bf4169a7
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "333714"
---
# <a name="view-outbound-planned-intercompany-demand"></a><span data-ttu-id="56b72-103">Kimenő tervezett vállalatközi igény megtekintése</span><span class="sxs-lookup"><span data-stu-id="56b72-103">View outbound planned intercompany demand</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="56b72-104">Ez az eljárás bemutatja, hogyan tekinthetők meg a vállalatközi szállítók által teljesítendő rendelések.</span><span class="sxs-lookup"><span data-stu-id="56b72-104">This procedure shows how to view all the planned orders that will be fulfilled by an intercompany vendor.</span></span> <span data-ttu-id="56b72-105">Ez az eljárás az DEMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="56b72-105">The demo data company used to create this procedure is DEMF.</span></span>

1. <span data-ttu-id="56b72-106">Kattintson az Alaptervezés parancsra.</span><span class="sxs-lookup"><span data-stu-id="56b72-106">Click Master planning.</span></span>
2. <span data-ttu-id="56b72-107">A Terv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="56b72-107">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="56b72-108">A Terv mezőben válassza a 10-es tervet.</span><span class="sxs-lookup"><span data-stu-id="56b72-108">In the Plan field, select plan 10.</span></span>  
3. <span data-ttu-id="56b72-109">Kattintson a Futtatás elemre.</span><span class="sxs-lookup"><span data-stu-id="56b72-109">Click Run.</span></span>
4. <span data-ttu-id="56b72-110">Adjon meg egy számot a Szálak száma mezőben.</span><span class="sxs-lookup"><span data-stu-id="56b72-110">In the Number of threads field, enter a number.</span></span>
    * <span data-ttu-id="56b72-111">Ez a fő tervezési célokra használandó párhuzamos szálak számát jelenti.</span><span class="sxs-lookup"><span data-stu-id="56b72-111">This represents the number of parallel threads to be used for master planning.</span></span>  
5. <span data-ttu-id="56b72-112">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="56b72-112">Click OK.</span></span>
    * <span data-ttu-id="56b72-113">Ez eltarthat egy ideig.</span><span class="sxs-lookup"><span data-stu-id="56b72-113">This may take a while.</span></span>  
6. <span data-ttu-id="56b72-114">Kattintson a Tervezett vállalatközi igény elemre.</span><span class="sxs-lookup"><span data-stu-id="56b72-114">Click Planned intercompany demand.</span></span>
7. <span data-ttu-id="56b72-115">Kattintson a Kimenő tervezett vállalatközi igény megjelenítése elemre.</span><span class="sxs-lookup"><span data-stu-id="56b72-115">Click Outbound planned intercompany demand.</span></span>
    * <span data-ttu-id="56b72-116">Ez a lap a belső ellátási láncba tartozó szállítók által kielégítendő, tervezett kereslet áttekintését biztosítja.</span><span class="sxs-lookup"><span data-stu-id="56b72-116">This page provides an overview of all the planned demand that will be fulfilled by an internal supply chain vendor.</span></span>  
8. <span data-ttu-id="56b72-117">Bontsa ki a Felfelé irányuló igény részletes adatai részt.</span><span class="sxs-lookup"><span data-stu-id="56b72-117">Expand the Upstream demand details section.</span></span>
    * <span data-ttu-id="56b72-118">Ebben a szakaszban a kereslet jövőbeli teljesítésének részleteit láthatja.</span><span class="sxs-lookup"><span data-stu-id="56b72-118">In this section, you can see the details about how the demand will be fulfilled.</span></span> <span data-ttu-id="56b72-119">Lehet, hogy meg kell várnia, amíg az alaptervezés a beszállítónál lefut, mielőtt további információkat láthatna itt.</span><span class="sxs-lookup"><span data-stu-id="56b72-119">You may need to wait for master planning to be run in the supply company before you can see additional information here.</span></span>  

