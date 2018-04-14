---
title: "Szabálytalanság létrehozása és feldolgozása"
description: "Ezekkel a lépésekkel végrehajthatja a szabálytalanság kezelését, a meglévő minőségi rendelés alapján."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: adecf9b2ea29abaee378f1c02c64551c3aeede6d
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---
# <a name="create-and-process-a-conformance"></a><span data-ttu-id="8f177-103">Szabálytalanság létrehozása és feldolgozása</span><span class="sxs-lookup"><span data-stu-id="8f177-103">Create and process a conformance</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8f177-104">Ezekkel a lépésekkel végrehajthatja a szabálytalanság kezelését, a meglévő minőségi rendelés alapján.</span><span class="sxs-lookup"><span data-stu-id="8f177-104">Use this procedure to perform nonconformance management, based on an existing quality order.</span></span> <span data-ttu-id="8f177-105">Ezt a felvételt futtathatja az USMF bemutató vállalatban, és használhatja a javasolt értékeket.</span><span class="sxs-lookup"><span data-stu-id="8f177-105">You can run this recording in the USMF demo company and can use the suggested values.</span></span> <span data-ttu-id="8f177-106">Ezt az eljárást általában a minőségi adminisztrátor végzi.</span><span class="sxs-lookup"><span data-stu-id="8f177-106">Typically, this procedure is performed by a quality clerk.</span></span>  <span data-ttu-id="8f177-107">Előfeltételként futtassa az „Áruk minőségének vizsgálata” feladatrögzítést.</span><span class="sxs-lookup"><span data-stu-id="8f177-107">As a prerequisite, run the “Inspect the quality of goods” task recording.</span></span> <span data-ttu-id="8f177-108">A szabálytalanság jóváhagyásának feldolgozását a feladat rögzítését futtató felhasználónak rendelkeznie kell hozzárendelt „Név” értékkel a Felhasználók lapon.</span><span class="sxs-lookup"><span data-stu-id="8f177-108">To process the approval of a nonconformance, the user who runs the task recording must have a “Name” value assigned on the Users page.</span></span> <span data-ttu-id="8f177-109">A dokumentummegjegyzések használatához a felhasználónak rendelkeznie kell a Dokumentumkezeléssel, amelyet a felhasználói beállításokban kell aktiválni.</span><span class="sxs-lookup"><span data-stu-id="8f177-109">To use the document notes, the user must also have Document handling activated in the user options.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="8f177-110">Minőségi rendelés kiválasztása</span><span class="sxs-lookup"><span data-stu-id="8f177-110">Select a quality order</span></span>
1. <span data-ttu-id="8f177-111">Ugrás a Minőségi rendelések elemhez.</span><span class="sxs-lookup"><span data-stu-id="8f177-111">Go to Quality orders.</span></span>
2. <span data-ttu-id="8f177-112">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="8f177-112">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="8f177-113">Válassza ki a „Vizsgálja meg az áruk minőségét” tevékenységfelvétel alapján létrejött minőségi rendelést.</span><span class="sxs-lookup"><span data-stu-id="8f177-113">Select the quality order that was created from the "Inspect the quality of goods" task recording.</span></span>  

## <a name="create-a-nonconformance"></a><span data-ttu-id="8f177-114">Kattintson a Szabálytalanság létrehozása elemre.</span><span class="sxs-lookup"><span data-stu-id="8f177-114">Create a nonconformance</span></span>
1. <span data-ttu-id="8f177-115">Kattintson a Lekérdezések elemre.</span><span class="sxs-lookup"><span data-stu-id="8f177-115">Click Inquiries.</span></span>
2. <span data-ttu-id="8f177-116">Kattintson a Szabálytalanságok elemre.</span><span class="sxs-lookup"><span data-stu-id="8f177-116">Click Non conformances.</span></span>
3. <span data-ttu-id="8f177-117">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8f177-117">Click New.</span></span>
4. <span data-ttu-id="8f177-118">A Probléma típusa mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="8f177-118">In the Problem type field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="8f177-119">Válassza ki az ellenőrzési eljárás során található problémát.</span><span class="sxs-lookup"><span data-stu-id="8f177-119">Select the problem that was found during the inspection process.</span></span>  
5. <span data-ttu-id="8f177-120">A Probléma típusa mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="8f177-120">In the Problem type field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="8f177-121">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="8f177-121">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="8f177-122">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="8f177-122">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="8f177-123">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="8f177-123">Click OK.</span></span>

## <a name="approvereject-a-nonconformance"></a><span data-ttu-id="8f177-124">Szabálytalanság jóváhagyása/elutasítása</span><span class="sxs-lookup"><span data-stu-id="8f177-124">Approve/reject a nonconformance</span></span>
1. <span data-ttu-id="8f177-125">Kattintson a Funkciók elemre.</span><span class="sxs-lookup"><span data-stu-id="8f177-125">Click Functions.</span></span>
2. <span data-ttu-id="8f177-126">Kattintson A szabálytalanság jóváhagyása elemre.</span><span class="sxs-lookup"><span data-stu-id="8f177-126">Click Approve non conformance.</span></span>
    * <span data-ttu-id="8f177-127">Ebben a példában hagyja jóvá a szabálytalanságot.</span><span class="sxs-lookup"><span data-stu-id="8f177-127">For this example, approve the nonconformance.</span></span> <span data-ttu-id="8f177-128">A jóváhagyott szabálytalanságokat társíthatja a kapcsolódó műveletekhez az olyan munka rögzítése érdekében, amely a szabálytalanság kezelésének része, illetve a javítás kezelési feldolgozásának a része.</span><span class="sxs-lookup"><span data-stu-id="8f177-128">Approved nonconformances can be associated with related operations to record work that is done as part of the nonconformance handling and, as in this task recording, the processing of correction handling.</span></span>  
3. <span data-ttu-id="8f177-129">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="8f177-129">Click Yes.</span></span>

## <a name="create-a-correction-action"></a><span data-ttu-id="8f177-130">Javító művelet létrehozása</span><span class="sxs-lookup"><span data-stu-id="8f177-130">Create a correction action</span></span>
1. <span data-ttu-id="8f177-131">Kattintson a Korrekciók elemre.</span><span class="sxs-lookup"><span data-stu-id="8f177-131">Click Corrections.</span></span>
2. <span data-ttu-id="8f177-132">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8f177-132">Click New.</span></span>
3. <span data-ttu-id="8f177-133">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="8f177-133">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="8f177-134">A Személyes szám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="8f177-134">In the Personnel number field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="8f177-135">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="8f177-135">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="8f177-136">Kattintson a Kiválasztás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8f177-136">Click Select.</span></span>
7. <span data-ttu-id="8f177-137">Kattintson a Csatolás elemre.</span><span class="sxs-lookup"><span data-stu-id="8f177-137">Click Attach.</span></span>
    * <span data-ttu-id="8f177-138">Hozzon létre egy megjegyzést a javításhoz.</span><span class="sxs-lookup"><span data-stu-id="8f177-138">Create a note about the correction.</span></span> <span data-ttu-id="8f177-139">Ebben a példában a művelet a szállítóval való kapcsolatfelvétel a szabálytalansági eset megvitatása céljából.</span><span class="sxs-lookup"><span data-stu-id="8f177-139">For this example, the action is to contact the vendor to discuss the nonconformance case.</span></span>  
8. <span data-ttu-id="8f177-140">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8f177-140">Click New.</span></span>
9. <span data-ttu-id="8f177-141">Kattintson a Megjegyzés elemre.</span><span class="sxs-lookup"><span data-stu-id="8f177-141">Click Note.</span></span>
    * <span data-ttu-id="8f177-142">Ne feledje, hogy a jelentés beállításától függően a különféle dokumentumtípusokat kinyomtathatja a szabálytalanság kezeléséhez kapcsolódó jelentéseken.</span><span class="sxs-lookup"><span data-stu-id="8f177-142">Note that, depending on the report setup, different document types can be printed on the reports that are related to nonconformance management.</span></span>  
10. <span data-ttu-id="8f177-143">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8f177-143">In the Description field, type a value.</span></span>
11. <span data-ttu-id="8f177-144">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8f177-144">Close the page.</span></span>

## <a name="maintain-a-correction"></a><span data-ttu-id="8f177-145">Korrekció kezelése</span><span class="sxs-lookup"><span data-stu-id="8f177-145">Maintain a correction</span></span>
1. <span data-ttu-id="8f177-146">Kattintson a Befejezés jelölése gombra.</span><span class="sxs-lookup"><span data-stu-id="8f177-146">Click Mark complete.</span></span>
2. <span data-ttu-id="8f177-147">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="8f177-147">Click OK.</span></span>
3. <span data-ttu-id="8f177-148">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8f177-148">Close the page.</span></span>

## <a name="close-a-nonconformance"></a><span data-ttu-id="8f177-149">Szabálytalanság lezárása</span><span class="sxs-lookup"><span data-stu-id="8f177-149">Close a nonconformance</span></span>
1. <span data-ttu-id="8f177-150">Kattintson a Funkciók elemre.</span><span class="sxs-lookup"><span data-stu-id="8f177-150">Click Functions.</span></span>
2. <span data-ttu-id="8f177-151">Kattintson A szabálytalanság lezárása elemre.</span><span class="sxs-lookup"><span data-stu-id="8f177-151">Click Close non conformance.</span></span>
3. <span data-ttu-id="8f177-152">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="8f177-152">Click Yes.</span></span>
4. <span data-ttu-id="8f177-153">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8f177-153">Close the page.</span></span>
5. <span data-ttu-id="8f177-154">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8f177-154">Close the page.</span></span>

