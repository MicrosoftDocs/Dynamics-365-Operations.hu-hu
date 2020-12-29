---
title: Kiadott alaptermék alapbeállításának kitöltése
description: Ez az témakör bemutatja, hogyan kell elvégezni azt a minimális beállítást, amely szükséges ahhoz, hogy az alapterméket használni lehessen az Anyagjegyzék-verziókban.
author: ShylaThompson
manager: tfehr
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventTableInventoryDimensionGroups, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8ac4ceeb3e21ab089eb16565bb6e38c7eb44be80
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429529"
---
# <a name="complete-basic-setup-of-a-released-product-master"></a><span data-ttu-id="79db5-103">Kiadott alaptermék alapbeállításának kitöltése</span><span class="sxs-lookup"><span data-stu-id="79db5-103">Complete basic setup of a released product master</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="79db5-104">Ez az témakör bemutatja, hogyan kell elvégezni azt a minimális beállítást, amely szükséges ahhoz, hogy az alapterméket használni lehessen az Anyagjegyzék-verziókban.</span><span class="sxs-lookup"><span data-stu-id="79db5-104">This topic shows how to complete the minimum setup that is required before the product master can be used in BOM versions.</span></span>

<span data-ttu-id="79db5-105">Ez a harmadik eljárás a nyolcból, amely a dimenzión alapuló konfiguráció-kombinációk létrehozását ismerteti.</span><span class="sxs-lookup"><span data-stu-id="79db5-105">This is the third procedure out of eight which explains how to build combinations for dimension-based configuration.</span></span> <span data-ttu-id="79db5-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="79db5-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="79db5-107">Kattintson ide: **Navigációs ablaktábla > Modulok > Termékinformációk kezelése > Termékek > Kiadott termékek**.</span><span class="sxs-lookup"><span data-stu-id="79db5-107">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="79db5-108">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="79db5-108">In the list, find and select the desired record.</span></span> <span data-ttu-id="79db5-109">Válassza ki azt az alapterméket, amelyet a második eljárásban kiadott.</span><span class="sxs-lookup"><span data-stu-id="79db5-109">Select the product master that you have released in the second procedure.</span></span> <span data-ttu-id="79db5-110">Ezt az alapterméket a dimenzión alapuló konfigurációs technológiával hozta létre.</span><span class="sxs-lookup"><span data-stu-id="79db5-110">This product master is created with the dimension-based configuration technology.</span></span>  
3. <span data-ttu-id="79db5-111">A Művelet ablaktáblán válassza ki a **Termék** elemet.</span><span class="sxs-lookup"><span data-stu-id="79db5-111">On the Action Pane, select **Product**.</span></span>
4. <span data-ttu-id="79db5-112">A **Méretcsoportok** gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="79db5-112">Select **Dimension groups** to open the drop dialog.</span></span>
5. <span data-ttu-id="79db5-113">A **Tárolási dimenzió csoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="79db5-113">In the **Storage dimension group** field, select the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="79db5-114">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="79db5-114">In the list, find and select the desired record.</span></span> <span data-ttu-id="79db5-115">A tárolásidimenzió-csoport határozza meg, hogy mely tárolási dimenziókat használja a termék tranzakciójához.</span><span class="sxs-lookup"><span data-stu-id="79db5-115">The storage dimension group determines which storage dimensions are used for product transaction.</span></span> <span data-ttu-id="79db5-116">Jelölje be az eljáráshoz szükséges **helyet**.</span><span class="sxs-lookup"><span data-stu-id="79db5-116">Select **Site** for this procedure.</span></span>  
7. <span data-ttu-id="79db5-117">A **Nyomon követési dimenzió csoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="79db5-117">In the **Tracking dimension group** field, select the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="79db5-118">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="79db5-118">In the list, find and select the desired record.</span></span> <span data-ttu-id="79db5-119">A nyomonkövetésidimenzió-csoport határozza meg, hogy mely nyomon követési dimenziókat használja a termék tranzakciójához.</span><span class="sxs-lookup"><span data-stu-id="79db5-119">The tracking dimension group determines which tracking dimensions are used for product transaction.</span></span> <span data-ttu-id="79db5-120">Jelölje be az eljáráshoz a **Nincs** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="79db5-120">Select **None** for this procedure.</span></span>  
9. <span data-ttu-id="79db5-121">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="79db5-121">Click **OK**.</span></span>
10. <span data-ttu-id="79db5-122">Kattintson a **Szerkesztés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="79db5-122">Click **Edit**.</span></span>
11. <span data-ttu-id="79db5-123">A **Cikkmodellcsoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="79db5-123">In the **Item model group** field, select the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="79db5-124">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="79db5-124">In the list, find and select the desired record.</span></span> <span data-ttu-id="79db5-125">A Cikkmodellcsoportok olyan beállításokat tartalmaznak, amelyek meghatározzák, hogy a rendszer hogyan kezelje a cikkeket a cikkbevételezéseknél és -kiadásoknál.</span><span class="sxs-lookup"><span data-stu-id="79db5-125">Item model groups contain settings that determine how items are controlled and handled on item receipts and issues.</span></span> <span data-ttu-id="79db5-126">Meghatározzák továbbá a cikkfelhasználás számítását is.</span><span class="sxs-lookup"><span data-stu-id="79db5-126">They also determine how item consumption is calculated.</span></span> <span data-ttu-id="79db5-127">Jelölje be az eljáráshoz szükséges **FIFO**-t.</span><span class="sxs-lookup"><span data-stu-id="79db5-127">Select **FIFO** for this procedure.</span></span>  
13. <span data-ttu-id="79db5-128">Bontsa ki a **Költségkezelés** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="79db5-128">Expand the **Manage costs** section.</span></span>
14. <span data-ttu-id="79db5-129">A **Cikkcsoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="79db5-129">In the **Item group** field, select the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="79db5-130">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="79db5-130">In the list, find and select the desired record.</span></span> <span data-ttu-id="79db5-131">Ezen a képernyőn a cikkeket cikkjellemzők szerint csoportosítva kezelheti a készletet.</span><span class="sxs-lookup"><span data-stu-id="79db5-131">Item groups are used to manage inventory by dividing inventory items into groups.</span></span> <span data-ttu-id="79db5-132">Jelölje be az eljáráshoz a **CarAudio** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="79db5-132">Select **CarAudio** for this procedure.</span></span>  
16. <span data-ttu-id="79db5-133">A Műveleti ablaktáblán kattintson a **Tervezés** elemre.</span><span class="sxs-lookup"><span data-stu-id="79db5-133">On the Action Pane, select **Plan**.</span></span>
17. <span data-ttu-id="79db5-134">Válassza a **Termék alapértelmezett rendelésbeállításai** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="79db5-134">Select **Default order settings**.</span></span>
18. <span data-ttu-id="79db5-135">Az **Alapértelmezett rendelés típusa mezőben** válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="79db5-135">In the **Default order type field**, select an option.</span></span> <span data-ttu-id="79db5-136">Válassza ki a **Termelést**, ha az alaptermékhez tartozó alapértelmezett ellátási beállítás az előállítás.</span><span class="sxs-lookup"><span data-stu-id="79db5-136">Select **Production** to specify that the default supply option for this product master is to produce it.</span></span>  
19. <span data-ttu-id="79db5-137">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="79db5-137">Select **Save**.</span></span>
20. <span data-ttu-id="79db5-138">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="79db5-138">Close the page.</span></span>
21. <span data-ttu-id="79db5-139">Zárja be a **Kiadott termék részletei** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="79db5-139">Close the **Released product details** form.</span></span>

