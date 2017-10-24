--- 
title: "Késztermék létrehozása (csak 2016. február)"
description: "Ez a feladat egy késztermék létrehozására szolgál."
author: YuyuScheller
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 5485c949e932572542ba22e052007e9625e20314
ms.openlocfilehash: a14b56b508e5d46bb2898828bd30fdf6c3c14023
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-finished-product-february-2016-only"></a><span data-ttu-id="38f9e-103">Késztermék létrehozása (csak 2016. február)</span><span class="sxs-lookup"><span data-stu-id="38f9e-103">Create a finished product (February 2016 only)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="38f9e-104">Ez a feladat egy késztermék létrehozására szolgál.</span><span class="sxs-lookup"><span data-stu-id="38f9e-104">This task focuses on creating a finished product.</span></span> <span data-ttu-id="38f9e-105">Ez az anyagjegyzék-számítási sorozat első feladata.</span><span class="sxs-lookup"><span data-stu-id="38f9e-105">It is the first task in the BOM calculation series.</span></span> <span data-ttu-id="38f9e-106">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="38f9e-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="38f9e-107">Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="38f9e-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="38f9e-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="38f9e-108">Click New.</span></span>
3. <span data-ttu-id="38f9e-109">Írjon be egy értéket a Termékszám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="38f9e-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="38f9e-110">A bemutató céljára írja be a következőt: BOM_1.</span><span class="sxs-lookup"><span data-stu-id="38f9e-110">For the demonstration, type BOM_1.</span></span>  
4. <span data-ttu-id="38f9e-111">Az Elem modellcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="38f9e-111">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="38f9e-112">Válassza az STD lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="38f9e-112">Select STD.</span></span> <span data-ttu-id="38f9e-113">Az STD az elszámolóár rövidítése, és a költségszámításokkal dolgozva ez a leggyakrabban használt modell.</span><span class="sxs-lookup"><span data-stu-id="38f9e-113">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="38f9e-114">Az Elemcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="38f9e-114">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="38f9e-115">Válassza például a következőt: Audió.</span><span class="sxs-lookup"><span data-stu-id="38f9e-115">For example, select Audio.</span></span> <span data-ttu-id="38f9e-116">Nincs hatással a költségszámításokra.</span><span class="sxs-lookup"><span data-stu-id="38f9e-116">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="38f9e-117">A Tárolási dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="38f9e-117">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="38f9e-118">SiteWH kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="38f9e-118">Select SiteWH.</span></span> <span data-ttu-id="38f9e-119">A bemutatóhoz csak a helyet és a raktárat használjuk.</span><span class="sxs-lookup"><span data-stu-id="38f9e-119">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="38f9e-120">A Nyomon követési dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="38f9e-120">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="38f9e-121">A nyomon követési dimenziókat nem használjuk ennél a példánál, válassza a Nincs lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="38f9e-121">Tracking dimensions will not be used for this example, select None.</span></span>  
8. <span data-ttu-id="38f9e-122">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="38f9e-122">Click OK.</span></span>
9. <span data-ttu-id="38f9e-123">A Művelet panelen kattintson a Készletkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="38f9e-123">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="38f9e-124">Kattintson az Alapértelmezett rendelésbeállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="38f9e-124">Click Default order settings.</span></span>
11. <span data-ttu-id="38f9e-125">Az Alapértelmezett rendelés típusa mezőben válassza ki a „Termelés” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="38f9e-125">In the Default order type field, select 'Production'.</span></span>
    * <span data-ttu-id="38f9e-126">Mivel ez egy késztermék, amely gyártásba kerül, válassza a Termelés lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="38f9e-126">Because this is a finished product that will be produced, select Production.</span></span>  
12. <span data-ttu-id="38f9e-127">A Beszerzési hely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="38f9e-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="38f9e-128">A bemutatóhoz válassza az 1. helyet.</span><span class="sxs-lookup"><span data-stu-id="38f9e-128">For the demonstration, select Site 1.</span></span>  
13. <span data-ttu-id="38f9e-129">A Készlethely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="38f9e-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="38f9e-130">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="38f9e-130">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="38f9e-131">Az Értékesítési hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="38f9e-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="38f9e-132">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="38f9e-132">For this example, select Site 1.</span></span>  
15. <span data-ttu-id="38f9e-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="38f9e-133">Close the page.</span></span>


