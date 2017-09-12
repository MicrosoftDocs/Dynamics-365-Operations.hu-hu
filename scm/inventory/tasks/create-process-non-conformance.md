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
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: e5187c44aac881273900b2fc0ca91045a65cd838
ms.contentlocale: hu-hu
ms.lasthandoff: 09/12/2017

---
# <a name="create-and-process-a-conformance"></a><span data-ttu-id="0077e-103">Szabálytalanság létrehozása és feldolgozása</span><span class="sxs-lookup"><span data-stu-id="0077e-103">Create and process a conformance</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0077e-104">Ezekkel a lépésekkel végrehajthatja a szabálytalanság kezelését, a meglévő minőségi rendelés alapján.</span><span class="sxs-lookup"><span data-stu-id="0077e-104">Use this procedure to perform nonconformance management, based on an existing quality order.</span></span> <span data-ttu-id="0077e-105">Ezt a felvételt futtathatja az USMF bemutató vállalatban, és használhatja a javasolt értékeket.</span><span class="sxs-lookup"><span data-stu-id="0077e-105">You can run this recording in the USMF demo company and can use the suggested values.</span></span> <span data-ttu-id="0077e-106">Ezt az eljárást általában a minőségi adminisztrátor végzi.</span><span class="sxs-lookup"><span data-stu-id="0077e-106">Typically, this procedure is performed by a quality clerk.</span></span>  <span data-ttu-id="0077e-107">Előfeltételként futtassa az „Áruk minőségének vizsgálata” feladatrögzítést.</span><span class="sxs-lookup"><span data-stu-id="0077e-107">As a prerequisite, run the “Inspect the quality of goods” task recording.</span></span> <span data-ttu-id="0077e-108">A szabálytalanság jóváhagyásának feldolgozását a feladat rögzítését futtató felhasználónak rendelkeznie kell hozzárendelt „Név” értékkel a Felhasználók lapon.</span><span class="sxs-lookup"><span data-stu-id="0077e-108">To process the approval of a nonconformance, the user who runs the task recording must have a “Name” value assigned on the Users page.</span></span> <span data-ttu-id="0077e-109">A dokumentummegjegyzések használatához a felhasználónak rendelkeznie kell a Dokumentumkezeléssel, amelyet a felhasználói beállításokban kell aktiválni.</span><span class="sxs-lookup"><span data-stu-id="0077e-109">To use the document notes, the user must also have Document handling activated in the user options.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="0077e-110">Minőségi rendelés kiválasztása</span><span class="sxs-lookup"><span data-stu-id="0077e-110">Select a quality order</span></span>
1. <span data-ttu-id="0077e-111">Ugrás a Minőségi rendelések elemhez.</span><span class="sxs-lookup"><span data-stu-id="0077e-111">Go to Quality orders.</span></span>
2. <span data-ttu-id="0077e-112">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="0077e-112">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="0077e-113">Válassza ki a „Vizsgálja meg az áruk minőségét” tevékenységfelvétel alapján létrejött minőségi rendelést.</span><span class="sxs-lookup"><span data-stu-id="0077e-113">Select the quality order that was created from the "Inspect the quality of goods" task recording.</span></span>  

## <a name="create-a-nonconformance"></a><span data-ttu-id="0077e-114">Kattintson a Szabálytalanság létrehozása elemre.</span><span class="sxs-lookup"><span data-stu-id="0077e-114">Create a nonconformance</span></span>
1. <span data-ttu-id="0077e-115">Kattintson a Lekérdezések elemre.</span><span class="sxs-lookup"><span data-stu-id="0077e-115">Click Inquiries.</span></span>
2. <span data-ttu-id="0077e-116">Kattintson a Szabálytalanságok elemre.</span><span class="sxs-lookup"><span data-stu-id="0077e-116">Click Non conformances.</span></span>
3. <span data-ttu-id="0077e-117">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0077e-117">Click New.</span></span>
4. <span data-ttu-id="0077e-118">A Probléma típusa mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="0077e-118">In the Problem type field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="0077e-119">Válassza ki az ellenőrzési eljárás során található problémát.</span><span class="sxs-lookup"><span data-stu-id="0077e-119">Select the problem that was found during the inspection process.</span></span>  
5. <span data-ttu-id="0077e-120">A Probléma típusa mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="0077e-120">In the Problem type field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="0077e-121">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="0077e-121">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="0077e-122">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="0077e-122">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="0077e-123">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="0077e-123">Click OK.</span></span>

## <a name="approvereject-a-nonconformance"></a><span data-ttu-id="0077e-124">Szabálytalanság jóváhagyása/elutasítása</span><span class="sxs-lookup"><span data-stu-id="0077e-124">Approve/reject a nonconformance</span></span>
1. <span data-ttu-id="0077e-125">Kattintson a Funkciók elemre.</span><span class="sxs-lookup"><span data-stu-id="0077e-125">Click Functions.</span></span>
2. <span data-ttu-id="0077e-126">Kattintson A szabálytalanság jóváhagyása elemre.</span><span class="sxs-lookup"><span data-stu-id="0077e-126">Click Approve non conformance.</span></span>
    * <span data-ttu-id="0077e-127">Ebben a példában hagyja jóvá a szabálytalanságot.</span><span class="sxs-lookup"><span data-stu-id="0077e-127">For this example, approve the nonconformance.</span></span> <span data-ttu-id="0077e-128">A jóváhagyott szabálytalanságokat társíthatja a kapcsolódó műveletekhez az olyan munka rögzítése érdekében, amely a szabálytalanság kezelésének része, illetve a javítás kezelési feldolgozásának a része.</span><span class="sxs-lookup"><span data-stu-id="0077e-128">Approved nonconformances can be associated with related operations to record work that is done as part of the nonconformance handling and, as in this task recording, the processing of correction handling.</span></span>  
3. <span data-ttu-id="0077e-129">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="0077e-129">Click Yes.</span></span>

## <a name="create-a-correction-action"></a><span data-ttu-id="0077e-130">Javító művelet létrehozása</span><span class="sxs-lookup"><span data-stu-id="0077e-130">Create a correction action</span></span>
1. <span data-ttu-id="0077e-131">Kattintson a Korrekciók elemre.</span><span class="sxs-lookup"><span data-stu-id="0077e-131">Click Corrections.</span></span>
2. <span data-ttu-id="0077e-132">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0077e-132">Click New.</span></span>
3. <span data-ttu-id="0077e-133">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="0077e-133">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="0077e-134">A Személyes szám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="0077e-134">In the Personnel number field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="0077e-135">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="0077e-135">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="0077e-136">Kattintson a Kiválasztás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0077e-136">Click Select.</span></span>
7. <span data-ttu-id="0077e-137">Kattintson a Csatolás elemre.</span><span class="sxs-lookup"><span data-stu-id="0077e-137">Click Attach.</span></span>
    * <span data-ttu-id="0077e-138">Hozzon létre egy megjegyzést a javításhoz.</span><span class="sxs-lookup"><span data-stu-id="0077e-138">Create a note about the correction.</span></span> <span data-ttu-id="0077e-139">Ebben a példában a művelet a szállítóval való kapcsolatfelvétel a szabálytalansági eset megvitatása céljából.</span><span class="sxs-lookup"><span data-stu-id="0077e-139">For this example, the action is to contact the vendor to discuss the nonconformance case.</span></span>  
8. <span data-ttu-id="0077e-140">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0077e-140">Click New.</span></span>
9. <span data-ttu-id="0077e-141">Kattintson a Megjegyzés elemre.</span><span class="sxs-lookup"><span data-stu-id="0077e-141">Click Note.</span></span>
    * <span data-ttu-id="0077e-142">Ne feledje, hogy a jelentés beállításától függően a különféle dokumentumtípusokat kinyomtathatja a szabálytalanság kezeléséhez kapcsolódó jelentéseken.</span><span class="sxs-lookup"><span data-stu-id="0077e-142">Note that, depending on the report setup, different document types can be printed on the reports that are related to nonconformance management.</span></span>  
10. <span data-ttu-id="0077e-143">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0077e-143">In the Description field, type a value.</span></span>
11. <span data-ttu-id="0077e-144">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="0077e-144">Close the page.</span></span>

## <a name="maintain-a-correction"></a><span data-ttu-id="0077e-145">Korrekció kezelése</span><span class="sxs-lookup"><span data-stu-id="0077e-145">Maintain a correction</span></span>
1. <span data-ttu-id="0077e-146">Kattintson a Befejezés jelölése gombra.</span><span class="sxs-lookup"><span data-stu-id="0077e-146">Click Mark complete.</span></span>
2. <span data-ttu-id="0077e-147">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="0077e-147">Click OK.</span></span>
3. <span data-ttu-id="0077e-148">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="0077e-148">Close the page.</span></span>

## <a name="close-a-nonconformance"></a><span data-ttu-id="0077e-149">Szabálytalanság lezárása</span><span class="sxs-lookup"><span data-stu-id="0077e-149">Close a nonconformance</span></span>
1. <span data-ttu-id="0077e-150">Kattintson a Funkciók elemre.</span><span class="sxs-lookup"><span data-stu-id="0077e-150">Click Functions.</span></span>
2. <span data-ttu-id="0077e-151">Kattintson A szabálytalanság lezárása elemre.</span><span class="sxs-lookup"><span data-stu-id="0077e-151">Click Close non conformance.</span></span>
3. <span data-ttu-id="0077e-152">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="0077e-152">Click Yes.</span></span>
4. <span data-ttu-id="0077e-153">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="0077e-153">Close the page.</span></span>
5. <span data-ttu-id="0077e-154">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="0077e-154">Close the page.</span></span>

