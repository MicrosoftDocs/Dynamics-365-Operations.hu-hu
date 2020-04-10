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
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8740846a6c6ba9e61c73ebce532d3bec525c2cc7
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148032"
---
# <a name="view-outbound-planned-intercompany-demand"></a><span data-ttu-id="a9ab5-103">Kimenő tervezett vállalatközi igény megtekintése</span><span class="sxs-lookup"><span data-stu-id="a9ab5-103">View outbound planned intercompany demand</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a9ab5-104">Ez az eljárás bemutatja, hogyan tekinthetők meg a vállalatközi szállítók által teljesítendő rendelések.</span><span class="sxs-lookup"><span data-stu-id="a9ab5-104">This procedure shows how to view all the planned orders that will be fulfilled by an intercompany vendor.</span></span> <span data-ttu-id="a9ab5-105">Ez az eljárás az DEMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="a9ab5-105">The demo data company used to create this procedure is DEMF.</span></span>

1. <span data-ttu-id="a9ab5-106">Kattintson az Alaptervezés parancsra.</span><span class="sxs-lookup"><span data-stu-id="a9ab5-106">Click Master planning.</span></span>
2. <span data-ttu-id="a9ab5-107">A Terv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="a9ab5-107">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="a9ab5-108">A Terv mezőben válassza a 10-es tervet.</span><span class="sxs-lookup"><span data-stu-id="a9ab5-108">In the Plan field, select plan 10.</span></span>  
3. <span data-ttu-id="a9ab5-109">Kattintson a Futtatás elemre.</span><span class="sxs-lookup"><span data-stu-id="a9ab5-109">Click Run.</span></span>
4. <span data-ttu-id="a9ab5-110">Adjon meg egy számot a Szálak száma mezőben.</span><span class="sxs-lookup"><span data-stu-id="a9ab5-110">In the Number of threads field, enter a number.</span></span>
    * <span data-ttu-id="a9ab5-111">Ez a fő tervezési célokra használandó párhuzamos szálak számát jelenti.</span><span class="sxs-lookup"><span data-stu-id="a9ab5-111">This represents the number of parallel threads to be used for master planning.</span></span>  
5. <span data-ttu-id="a9ab5-112">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="a9ab5-112">Click OK.</span></span>
    * <span data-ttu-id="a9ab5-113">Ez eltarthat egy ideig.</span><span class="sxs-lookup"><span data-stu-id="a9ab5-113">This may take a while.</span></span>  
6. <span data-ttu-id="a9ab5-114">Kattintson a Tervezett vállalatközi igény elemre.</span><span class="sxs-lookup"><span data-stu-id="a9ab5-114">Click Planned intercompany demand.</span></span>
7. <span data-ttu-id="a9ab5-115">Kattintson a Kimenő tervezett vállalatközi igény megjelenítése elemre.</span><span class="sxs-lookup"><span data-stu-id="a9ab5-115">Click Outbound planned intercompany demand.</span></span>
    * <span data-ttu-id="a9ab5-116">Ez a lap a belső ellátási láncba tartozó szállítók által kielégítendő, tervezett kereslet áttekintését biztosítja.</span><span class="sxs-lookup"><span data-stu-id="a9ab5-116">This page provides an overview of all the planned demand that will be fulfilled by an internal supply chain vendor.</span></span>  
8. <span data-ttu-id="a9ab5-117">Bontsa ki a Felfelé irányuló igény részletes adatai részt.</span><span class="sxs-lookup"><span data-stu-id="a9ab5-117">Expand the Upstream demand details section.</span></span>
    * <span data-ttu-id="a9ab5-118">Ebben a szakaszban a kereslet jövőbeli teljesítésének részleteit láthatja.</span><span class="sxs-lookup"><span data-stu-id="a9ab5-118">In this section, you can see the details about how the demand will be fulfilled.</span></span> <span data-ttu-id="a9ab5-119">Lehet, hogy meg kell várnia, amíg az alaptervezés a beszállítónál lefut, mielőtt további információkat láthatna itt.</span><span class="sxs-lookup"><span data-stu-id="a9ab5-119">You may need to wait for master planning to be run in the supply company before you can see additional information here.</span></span>  

