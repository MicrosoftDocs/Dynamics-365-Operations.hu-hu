--- 
title: "Meghirdetési típusok és pontozási kritériumok létrehozása az ajánlatkérésekhez"
description: "Ez az útmutató bemutatja, hogyan hozhat létre meghirdetési típust, és hogyan társíthatja azt pontozási módszerrel."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 095855d552d228375635bdbaa9fca37c47a3b952
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="create-solicitation-types-and-scoring-criteria-for-rfqs"></a><span data-ttu-id="0e267-103">Meghirdetési típusok és pontozási kritériumok létrehozása az ajánlatkérésekhez</span><span class="sxs-lookup"><span data-stu-id="0e267-103">Create solicitation types and scoring criteria for RFQs</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0e267-104">Ez az útmutató bemutatja, hogyan hozhat létre meghirdetési típust, és hogyan társíthatja azt pontozási módszerrel.</span><span class="sxs-lookup"><span data-stu-id="0e267-104">This guide shows you how to create a solicitation type and associate this with a scoring method.</span></span> <span data-ttu-id="0e267-105">Tárgyalja a meghirdetési típus ajánlatkérésen való használatát is, amely meghatározza az alapértelmezett pontozási módszert.</span><span class="sxs-lookup"><span data-stu-id="0e267-105">It also shows how to use the solicitation type on a request for quotation (RFQ) which then sets the default scoring method.</span></span> <span data-ttu-id="0e267-106">Ezeket a feladatokat jellemzően egy beszerzési vezető végezné el.</span><span class="sxs-lookup"><span data-stu-id="0e267-106">These tasks would typically be carried out by a purchasing manager.</span></span> <span data-ttu-id="0e267-107">Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja.</span><span class="sxs-lookup"><span data-stu-id="0e267-107">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="0e267-108">A kezdéshez rendelkeznie kell egy elérhető pontozási módszerrel.</span><span class="sxs-lookup"><span data-stu-id="0e267-108">You need to have a scoring method available before you start.</span></span>


## <a name="create-a-solicitation-type"></a><span data-ttu-id="0e267-109">Ajánlatkérési típus létrehozása</span><span class="sxs-lookup"><span data-stu-id="0e267-109">Create a solicitation type</span></span>
1. <span data-ttu-id="0e267-110">Navigáljon a következő helyre: Beszerzés és forrás > Beállítás > Ajánlatkérés > Meghirdetés típusa.</span><span class="sxs-lookup"><span data-stu-id="0e267-110">Go to Procurement and sourcing > Setup > Request for quotation > Solicitation type.</span></span>
2. <span data-ttu-id="0e267-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e267-111">Click New.</span></span>
3. <span data-ttu-id="0e267-112">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0e267-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="0e267-113">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0e267-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="0e267-114">A Pontozási módszer mezőben válassza ki azt a pontozási módszert, amelyet az adott meghirdetési típusnál használni kíván.</span><span class="sxs-lookup"><span data-stu-id="0e267-114">In the Scoring method field, select the scoring method that you want to use for this solicitation type.</span></span>
6. <span data-ttu-id="0e267-115">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="0e267-115">Click Save.</span></span>
7. <span data-ttu-id="0e267-116">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="0e267-116">Close the page.</span></span>

## <a name="use-the-solicitation-type"></a><span data-ttu-id="0e267-117">A meghirdetési típus használata</span><span class="sxs-lookup"><span data-stu-id="0e267-117">Use the solicitation type</span></span>
1. <span data-ttu-id="0e267-118">Ugorjon a Beszerzés és forrás > Ajánlatkérések > Összes ajánlatkérés pontra.</span><span class="sxs-lookup"><span data-stu-id="0e267-118">Go to Procurement and sourcing > Requests for quotations > All requests for quotations.</span></span>
2. <span data-ttu-id="0e267-119">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e267-119">Click New.</span></span>
3. <span data-ttu-id="0e267-120">A Meghirdetés típusa mezőjében válassza ki az előzőleg létrehozott meghirdetési típust.</span><span class="sxs-lookup"><span data-stu-id="0e267-120">In the Solicitation type field, select the solicitation type that you have just created.</span></span> 
4. <span data-ttu-id="0e267-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="0e267-121">Click OK.</span></span>
5. <span data-ttu-id="0e267-122">Kattintson a Pontozási feltételek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e267-122">Click Scoring criteria.</span></span>
    * <span data-ttu-id="0e267-123">Abból a pontozási módszerből jelennek meg a pontozási feltétek, amelyet a meghirdetés típusához társított.</span><span class="sxs-lookup"><span data-stu-id="0e267-123">The scoring criteria that are shown are the ones from the scoring method that you associated with the solicitation type.</span></span> <span data-ttu-id="0e267-124">Ezen a lapon lehetősége van feltételek hozzáadására vagy törlésére.</span><span class="sxs-lookup"><span data-stu-id="0e267-124">You can choose to add or delete criteria on this page.</span></span> <span data-ttu-id="0e267-125">Új feltételeket más pontozási módszerből való másolással is hozzáadhat.</span><span class="sxs-lookup"><span data-stu-id="0e267-125">It's also possible to add new criteria by copying them from other scoring methods.</span></span>  
6. <span data-ttu-id="0e267-126">Kattintson a Feltételek másolása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e267-126">Click Copy criteria.</span></span>
7. <span data-ttu-id="0e267-127">A Pontozási módszer mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0e267-127">In the Scoring method field, enter or select a value.</span></span>
8. <span data-ttu-id="0e267-128">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="0e267-128">Click OK.</span></span>
9. <span data-ttu-id="0e267-129">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="0e267-129">Close the page.</span></span>


