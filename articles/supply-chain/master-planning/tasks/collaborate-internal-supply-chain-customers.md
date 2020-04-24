---
title: Együttműködés a belső ellátási lánc vevőivel
description: Ez az eljárás bemutatja, hogyan tekinthetők meg a vállalatközi szállítók által teljesítendő rendelések.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqOutboundIntercompanyDemand
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fb807a904afaba09d0dc364c06f964c135d3cfb1
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208662"
---
# <a name="collaborate-with-internal-supply-chain-customers"></a><span data-ttu-id="c0f1a-103">Együttműködés a belső ellátási lánc vevőivel</span><span class="sxs-lookup"><span data-stu-id="c0f1a-103">Collaborate with internal supply chain customers</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c0f1a-104">Ez az eljárás bemutatja, hogyan tekinthetők meg a vállalatközi szállítók által teljesítendő rendelések.</span><span class="sxs-lookup"><span data-stu-id="c0f1a-104">This procedure shows how to view all the planned orders that will be fulfilled by an intercompany vendor.</span></span> <span data-ttu-id="c0f1a-105">Ez az eljárás az DEMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="c0f1a-105">The demo data company used to create this procedure is DEMF.</span></span>

1. <span data-ttu-id="c0f1a-106">Kattintson az Alaptervezés parancsra.</span><span class="sxs-lookup"><span data-stu-id="c0f1a-106">Click Master planning.</span></span>
2. <span data-ttu-id="c0f1a-107">A Terv mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c0f1a-107">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="c0f1a-108">A Terv mezőben válassza a 10-es tervet.</span><span class="sxs-lookup"><span data-stu-id="c0f1a-108">In the Plan field, select plan 10.</span></span>  
3. <span data-ttu-id="c0f1a-109">Kattintson a Futtatás elemre.</span><span class="sxs-lookup"><span data-stu-id="c0f1a-109">Click Run.</span></span>
4. <span data-ttu-id="c0f1a-110">Adjon meg egy számot a Szálak száma mezőben.</span><span class="sxs-lookup"><span data-stu-id="c0f1a-110">In the Number of threads field, enter a number.</span></span>
    * <span data-ttu-id="c0f1a-111">Ez a fő tervezési célokra használandó párhuzamos szálak számát jelenti.</span><span class="sxs-lookup"><span data-stu-id="c0f1a-111">This represents the number of parallel threads to be used for master planning.</span></span>  
5. <span data-ttu-id="c0f1a-112">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c0f1a-112">Click OK.</span></span>
    * <span data-ttu-id="c0f1a-113">Ez eltarthat egy ideig.</span><span class="sxs-lookup"><span data-stu-id="c0f1a-113">This may take a while.</span></span>  
6. <span data-ttu-id="c0f1a-114">Kattintson a Tervezett vállalatközi igény elemre.</span><span class="sxs-lookup"><span data-stu-id="c0f1a-114">Click Planned intercompany demand.</span></span>
7. <span data-ttu-id="c0f1a-115">Kattintson a Kimenő tervezett vállalatközi igény megjelenítése elemre.</span><span class="sxs-lookup"><span data-stu-id="c0f1a-115">Click Outbound planned intercompany demand.</span></span>
    * <span data-ttu-id="c0f1a-116">Ez a lap a belső ellátási láncba tartozó szállítók által kielégítendő, tervezett kereslet áttekintését biztosítja.</span><span class="sxs-lookup"><span data-stu-id="c0f1a-116">This page provides an overview of all the planned demand that will be fulfilled by an internal supply chain vendor.</span></span>  
8. <span data-ttu-id="c0f1a-117">Bontsa ki a Felfelé irányuló igény részletes adatai részt.</span><span class="sxs-lookup"><span data-stu-id="c0f1a-117">Expand the Upstream demand details section.</span></span>
    * <span data-ttu-id="c0f1a-118">Ebben a szakaszban a kereslet jövőbeli teljesítésének részleteit láthatja.</span><span class="sxs-lookup"><span data-stu-id="c0f1a-118">In this section, you can see the details about how the demand will be fulfilled.</span></span> <span data-ttu-id="c0f1a-119">Lehet, hogy meg kell várnia, amíg az alaptervezés a beszállítónál lefut, mielőtt további információkat láthatna itt.</span><span class="sxs-lookup"><span data-stu-id="c0f1a-119">You may need to wait for master planning to be run in the supply company before you can see additional information here.</span></span>  

