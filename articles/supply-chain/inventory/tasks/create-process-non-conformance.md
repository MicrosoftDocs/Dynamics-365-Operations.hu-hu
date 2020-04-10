---
title: Szabálytalanság létrehozása és feldolgozása
description: Ez a témekör ismerteti, hogy hogyan hajtsa végre a szabálytalanság kezelését, a meglévő minőségi rendelés alapján.
author: perlynne
manager: AnnBe
ms.date: 08/07/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1d012af1924e9eedee41f46de6c253d009cb52d2
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145709"
---
# <a name="create-and-process-a-conformance"></a><span data-ttu-id="2aa8b-103">Szabálytalanság létrehozása és feldolgozása</span><span class="sxs-lookup"><span data-stu-id="2aa8b-103">Create and process a conformance</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2aa8b-104">Ez a témekör ismerteti, hogy hogyan hajtsa végre a szabálytalanság kezelését, a meglévő minőségi rendelés alapján.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-104">This topic explains how to perform nonconformance management, based on an existing quality order.</span></span> <span data-ttu-id="2aa8b-105">Ezt a felvételt futtathatja az USMF bemutató vállalatban, és használhatja a javasolt értékeket.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-105">You can run this recording in the USMF demo company and can use the suggested values.</span></span> <span data-ttu-id="2aa8b-106">Ezt az eljárást általában a minőségi adminisztrátor végzi.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-106">Typically, this procedure is performed by a quality clerk.</span></span>  <span data-ttu-id="2aa8b-107">Előfeltételként hajtsa végre a következő utasításait: [Áruk minőségének vizsgálata](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).</span><span class="sxs-lookup"><span data-stu-id="2aa8b-107">As a prerequisite, complete the instructions in [Inspect the quality of goods](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).</span></span> <span data-ttu-id="2aa8b-108">A szabálytalanság jóváhagyásának feldolgozását a feladat rögzítését futtató felhasználónak rendelkeznie kell hozzárendelt „Név” értékkel a Felhasználók lapon.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-108">To process the approval of a nonconformance, the user who runs the task recording must have a "Name" value assigned on the Users page.</span></span> <span data-ttu-id="2aa8b-109">A dokumentummegjegyzések használatához a felhasználónak rendelkeznie kell a Dokumentumkezeléssel, amelyet a felhasználói beállításokban kell aktiválni.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-109">To use the document notes, the user must also have Document handling activated in the user options.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="2aa8b-110">Minőségi rendelés kiválasztása</span><span class="sxs-lookup"><span data-stu-id="2aa8b-110">Select a quality order</span></span>
1. <span data-ttu-id="2aa8b-111">A navigációs ablaktáblán lépjen a **Modulok > Készletgazdálkodás > Időszakos feladatok > Minőségkezelés > Minőségi rendelések** részre.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-111">In the navigation pane, go to **Modules > Inventory management > Periodic tasks > Quality management > Quality orders**.</span></span>
2. <span data-ttu-id="2aa8b-112">A listában válassza ki az itt létrejött minőségi rendelést: [Áruk minőségénak vizsgálata](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).</span><span class="sxs-lookup"><span data-stu-id="2aa8b-112">In the list, select the quality order that was created in [Inspect the quality of goods](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).</span></span>  

## <a name="create-a-nonconformance"></a><span data-ttu-id="2aa8b-113">Kattintson a Szabálytalanság létrehozása elemre.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-113">Create a nonconformance</span></span>
1. <span data-ttu-id="2aa8b-114">A műveleti ablaktáblán válassza a **Lekérdezések** elemet.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-114">In the action pane, select **Inquiries**.</span></span>
2. <span data-ttu-id="2aa8b-115">Válassza a **Szabálytalanságok** elemet.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-115">Select **Non conformances**.</span></span>
3. <span data-ttu-id="2aa8b-116">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-116">Select **New**.</span></span>
4. <span data-ttu-id="2aa8b-117">A **Probléma típusa** mező legördülő menüjében válassza ki az ellenőrzési folyamat során talált problémát.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-117">In the drop-down menu of the **Problem type** field, select the problem that was found during the inspection process.</span></span>  
5. <span data-ttu-id="2aa8b-118">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-118">Select **OK**.</span></span>

## <a name="approvereject-a-nonconformance"></a><span data-ttu-id="2aa8b-119">Szabálytalanság jóváhagyása/elutasítása</span><span class="sxs-lookup"><span data-stu-id="2aa8b-119">Approve/reject a nonconformance</span></span>
1. <span data-ttu-id="2aa8b-120">Válassza a **Funkciók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-120">Select **Functions**.</span></span>
2. <span data-ttu-id="2aa8b-121">Válassza a **Szabálytalanság jóváhagyása** elemet.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-121">Select **Approve non conformance**.</span></span> <span data-ttu-id="2aa8b-122">Ebben a példában hagyja jóvá a szabálytalanságot.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-122">For this example, approve the nonconformance.</span></span> <span data-ttu-id="2aa8b-123">A jóváhagyott szabálytalanságokat társíthatja a kapcsolódó műveletekhez az olyan munka rögzítése érdekében, amely a szabálytalanság kezelésének része, illetve a javítás kezelési feldolgozásának a része, ahogy ebben a témakörben.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-123">Approved nonconformances can be associated with related operations to record work that is done as part of the nonconformance handling and, as in this topic, the processing of correction handling.</span></span>  
3. <span data-ttu-id="2aa8b-124">Válassza ki az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-124">Select **Yes**.</span></span>

## <a name="create-a-correction-action"></a><span data-ttu-id="2aa8b-125">Javító művelet létrehozása</span><span class="sxs-lookup"><span data-stu-id="2aa8b-125">Create a correction action</span></span>
1. <span data-ttu-id="2aa8b-126">Válassza a **Helyesbítések** elemet.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-126">Select **Corrections**.</span></span>
2. <span data-ttu-id="2aa8b-127">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-127">Select **New**.</span></span>
3. <span data-ttu-id="2aa8b-128">Az új sor **Személyzeti szám** mezőjében válassza ki a kívánt rekordot a legördülő menüből.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-128">In the **Personnel number** field of the new row, select the desired record from the drop down menu.</span></span>
4. <span data-ttu-id="2aa8b-129">Kattintson a **Kiválasztás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-129">Click **Select**.</span></span>
5. <span data-ttu-id="2aa8b-130">Válassza a **Csatolás** elemet.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-130">Select **Attach**.</span></span> <span data-ttu-id="2aa8b-131">Hozzon létre egy megjegyzést a javításhoz.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-131">Create a note about the correction.</span></span> <span data-ttu-id="2aa8b-132">Ebben a példában a művelet a szállítóval való kapcsolatfelvétel a szabálytalansági eset megvitatása céljából.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-132">For this example, the action is to contact the vendor to discuss the nonconformance case.</span></span>  
6. <span data-ttu-id="2aa8b-133">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-133">Select **New**.</span></span>
7. <span data-ttu-id="2aa8b-134">Válassza a **Megjegyzés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-134">Select **Note**.</span></span> <span data-ttu-id="2aa8b-135">A jelentés beállításától függően a különféle dokumentumtípusokat kinyomtathatja a szabálytalanság kezeléséhez kapcsolódó jelentéseken.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-135">Depending on the report setup, different document types can be printed on the reports that are related to nonconformance management.</span></span>  
8. <span data-ttu-id="2aa8b-136">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-136">In the **Description** field, type a value.</span></span>
9. <span data-ttu-id="2aa8b-137">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-137">Close the page.</span></span>

## <a name="maintain-a-correction"></a><span data-ttu-id="2aa8b-138">Korrekció kezelése</span><span class="sxs-lookup"><span data-stu-id="2aa8b-138">Maintain a correction</span></span>
1. <span data-ttu-id="2aa8b-139">Válassza a **Megjelölés készként** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-139">Select **Mark complete**.</span></span>
2. <span data-ttu-id="2aa8b-140">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-140">Select **OK**.</span></span>
3. <span data-ttu-id="2aa8b-141">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-141">Close the page.</span></span>

## <a name="close-a-nonconformance"></a><span data-ttu-id="2aa8b-142">Szabálytalanság lezárása</span><span class="sxs-lookup"><span data-stu-id="2aa8b-142">Close a nonconformance</span></span>
1. <span data-ttu-id="2aa8b-143">Válassza a **Funkciók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-143">Select **Functions**.</span></span>
2. <span data-ttu-id="2aa8b-144">Válassza a **Szabálytalanság lezárása** elemet.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-144">Select **Close non conformance**.</span></span>
3. <span data-ttu-id="2aa8b-145">Válassza ki az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-145">Select **Yes**.</span></span>
4. <span data-ttu-id="2aa8b-146">Zárja be a lapokat.</span><span class="sxs-lookup"><span data-stu-id="2aa8b-146">Close the pages.</span></span>
