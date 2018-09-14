--- 
title: "Kiadott alaptermék alapbeállításának kitöltése"
description: "Ez az eljárás bemutatja, hogyan kell elvégezni azt a minimális beállítást, amely szükséges ahhoz, hogy az alapterméket használni lehessen az Anyagjegyzék-verziókban."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, InventTableInventoryDimensionGroups, InventItemOrderSetup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 0d3a91977c38c0ce0f9fe114bec943c7cb32a5d4
ms.contentlocale: hu-hu
ms.lasthandoff: 09/14/2018

---
# <a name="complete-basic-setup-of-a-released-product-master"></a><span data-ttu-id="c08af-103">Kiadott alaptermék alapbeállításának kitöltése</span><span class="sxs-lookup"><span data-stu-id="c08af-103">Complete basic setup of a released product master</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c08af-104">Ez az eljárás bemutatja, hogyan kell elvégezni azt a minimális beállítást, amely szükséges ahhoz, hogy az alapterméket használni lehessen az Anyagjegyzék-verziókban.</span><span class="sxs-lookup"><span data-stu-id="c08af-104">This procedure shows how to complete the minimum setup that is required before the product master can be used in BOM versions.</span></span>

<span data-ttu-id="c08af-105">Ez a harmadik eljárás a nyolcból, amely a dimenzión alapuló konfiguráció-kombinációk létrehozását ismerteti.</span><span class="sxs-lookup"><span data-stu-id="c08af-105">This is the third procedure out of eight which explains how to build combinations for dimension-based configuration.</span></span> <span data-ttu-id="c08af-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="c08af-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="c08af-107">Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c08af-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="c08af-108">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="c08af-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="c08af-109">Válassza ki azt az alapterméket, amelyet a második eljárásban kiadott.</span><span class="sxs-lookup"><span data-stu-id="c08af-109">Select the product master that you have released in the second procedure.</span></span> <span data-ttu-id="c08af-110">Ezt az alapterméket a dimenzión alapuló konfigurációs technológiával hozta létre.</span><span class="sxs-lookup"><span data-stu-id="c08af-110">This product master is created with the dimension-based configuration technology.</span></span>  
3. <span data-ttu-id="c08af-111">A Művelet panelen kattintson a Termék elemre.</span><span class="sxs-lookup"><span data-stu-id="c08af-111">On the Action Pane, click Product.</span></span>
4. <span data-ttu-id="c08af-112">A Méretcsoportok gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="c08af-112">Click Dimension groups to open the drop dialog.</span></span>
5. <span data-ttu-id="c08af-113">A Tárolási dimenzió csoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="c08af-113">In the Storage dimension group field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="c08af-114">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="c08af-114">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="c08af-115">A tárolásidimenzió-csoport határozza meg, hogy mely tárolási dimenziókat használja a termék tranzakciójához.</span><span class="sxs-lookup"><span data-stu-id="c08af-115">The storage dimension group determines which storage dimensions are used for product transaction.</span></span> <span data-ttu-id="c08af-116">Jelölje be az eljáráshoz szükséges helyet.</span><span class="sxs-lookup"><span data-stu-id="c08af-116">Select Site for this procedure.</span></span>  
7. <span data-ttu-id="c08af-117">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="c08af-117">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="c08af-118">A Nyomon követési dimenzió csoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="c08af-118">In the Tracking dimension group field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="c08af-119">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="c08af-119">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="c08af-120">A nyomonkövetésidimenzió-csoport határozza meg, hogy mely nyomon követési dimenziókat használja a termék tranzakciójához.</span><span class="sxs-lookup"><span data-stu-id="c08af-120">The tracking dimension group determines which tracking dimensions are used for product transaction.</span></span> <span data-ttu-id="c08af-121">Jelölje be az eljáráshoz a Nincs lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c08af-121">Select None for this procedure.</span></span>  
10. <span data-ttu-id="c08af-122">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="c08af-122">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="c08af-123">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c08af-123">Click OK.</span></span>
12. <span data-ttu-id="c08af-124">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="c08af-124">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="c08af-125">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c08af-125">Click Edit.</span></span>
    * <span data-ttu-id="c08af-126">A feladat beállítása érdekében nyissa meg a Kiadott termék részletei képernyőt.</span><span class="sxs-lookup"><span data-stu-id="c08af-126">Open the Released product details form to continue the setup task.</span></span>  
14. <span data-ttu-id="c08af-127">A Cikkmodellcsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="c08af-127">In the Item model group field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="c08af-128">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="c08af-128">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="c08af-129">A Cikkmodellcsoportok olyan beállításokat tartalmaznak, amelyek meghatározzák, hogy a rendszer hogyan kezelje a cikkeket a cikkbevételezéseknél és -kiadásoknál.</span><span class="sxs-lookup"><span data-stu-id="c08af-129">Item model groups contain settings that determine how items are controlled and handled on item receipts and issues.</span></span> <span data-ttu-id="c08af-130">Meghatározzák továbbá a cikkfelhasználás számítását is.</span><span class="sxs-lookup"><span data-stu-id="c08af-130">They also determine how item consumption is calculated.</span></span> <span data-ttu-id="c08af-131">Jelölje be az eljáráshoz szükséges FIFO-t.</span><span class="sxs-lookup"><span data-stu-id="c08af-131">Select   FIFO for this procedure.</span></span>  
16. <span data-ttu-id="c08af-132">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="c08af-132">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="c08af-133">Bontsa ki vagy zárja be a Költségek kezelése szakaszt.</span><span class="sxs-lookup"><span data-stu-id="c08af-133">Expand or collapse the Manage costs section.</span></span>
18. <span data-ttu-id="c08af-134">A Cikkcsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="c08af-134">In the Item group field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="c08af-135">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="c08af-135">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="c08af-136">Ezen a képernyőn a cikkeket cikkjellemzők szerint csoportosítva kezelheti a készletet.</span><span class="sxs-lookup"><span data-stu-id="c08af-136">Item groups are used to manage inventory by dividing inventory items into groups.</span></span> <span data-ttu-id="c08af-137">Jelölje be az eljáráshoz a CarAudio lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c08af-137">Select   CarAudio for this procedure.</span></span>  
20. <span data-ttu-id="c08af-138">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="c08af-138">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="c08af-139">A Művelet panelen kattintson a Terv elemre.</span><span class="sxs-lookup"><span data-stu-id="c08af-139">On the Action Pane, click Plan.</span></span>
22. <span data-ttu-id="c08af-140">Kattintson az Alapértelmezett rendelésbeállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="c08af-140">Click Default order settings.</span></span>
23. <span data-ttu-id="c08af-141">Az Alapértelmezett rendelés típusa mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c08af-141">In the Default order type field, select an option.</span></span>
    * <span data-ttu-id="c08af-142">Válassza ki a Termelést, ha az alaptermékhez tartozó alapértelmezett ellátási beállítás az előállítás.</span><span class="sxs-lookup"><span data-stu-id="c08af-142">Select Production to specify that the default supply option for this product master is to produce it.</span></span>  
24. <span data-ttu-id="c08af-143">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c08af-143">Close the page.</span></span>
25. <span data-ttu-id="c08af-144">Zárja be a Kiadott termék részletei képernyőt.</span><span class="sxs-lookup"><span data-stu-id="c08af-144">Close the Released product details form.</span></span>


