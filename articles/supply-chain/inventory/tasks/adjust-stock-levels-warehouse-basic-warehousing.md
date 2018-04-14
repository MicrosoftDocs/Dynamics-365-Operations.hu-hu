---
title: "Készletszintek kiigazítása a raktárban (alap raktározáskészlet-nyilvántartás)"
description: "Ez az eljárás végigvezeti a folyamaton, amellyel létrehozható és feladható egy készlethelyesbítési napló a raktárban található termékek készletszintjének helyesbítéséhez."
author: MarkusFogelberg
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
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 84ed2bfa708664674af781c575cfab35640e7079
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---
# <a name="adjust-stock-levels-in-the-warehouse-basic-warehousing"></a><span data-ttu-id="d311c-103">Készletszintek kiigazítása a raktárban (alap raktározáskészlet-nyilvántartás)</span><span class="sxs-lookup"><span data-stu-id="d311c-103">Adjust stock levels in the warehouse (basic warehousing)</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d311c-104">Ez az eljárás végigvezeti a folyamaton, amellyel létrehozható és feladható egy készlethelyesbítési napló a raktárban található termékek készletszintjének helyesbítéséhez.</span><span class="sxs-lookup"><span data-stu-id="d311c-104">This procedure walks you through the process of creating and posting an inventory adjustment journal in order to adjust stock levels of products in the warehouse.</span></span> <span data-ttu-id="d311c-105">Ennek megkezdése előtt először be kell állítani egy készletnaplónevet a készlethelyesbítéshez.</span><span class="sxs-lookup"><span data-stu-id="d311c-105">You need to have an inventory journal name set up for inventory adjustments before you start this.</span></span> <span data-ttu-id="d311c-106">Ezt a folyamatot az USMF bemutatócégen vagy saját adata használatával is elvégezheti.</span><span class="sxs-lookup"><span data-stu-id="d311c-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="d311c-107">Ezeket a feladatokat általában egy raktári alkalmazott végzi el.</span><span class="sxs-lookup"><span data-stu-id="d311c-107">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-adjustment-journal"></a><span data-ttu-id="d311c-108">Készlethelyesbítési napló létrehozása</span><span class="sxs-lookup"><span data-stu-id="d311c-108">Create an inventory adjustment journal</span></span>
1. <span data-ttu-id="d311c-109">Ugrás a Készletgazdálkodás > Naplóbejegyzések > Cikkek > Készlethelyesbítés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d311c-109">Go to Inventory management > Journal entries > Items > Inventory adjustment.</span></span>
2. <span data-ttu-id="d311c-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d311c-110">Click New.</span></span>
3. <span data-ttu-id="d311c-111">A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d311c-111">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="d311c-112">A listában kattintson a készlethelyesbítési naplónévre, amelyet használni kíván.</span><span class="sxs-lookup"><span data-stu-id="d311c-112">In the list, click on the inventory adjustment journal name you want to use.</span></span>
    * <span data-ttu-id="d311c-113">Ki lesz töltve néhány más mező a kiválasztott készlethelyesbítés naplónév beállításai alapján.</span><span class="sxs-lookup"><span data-stu-id="d311c-113">Some other fields will be populated based on the setup of the inventory adjustment journal name you select.</span></span>  
5. <span data-ttu-id="d311c-114">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="d311c-114">Click OK.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="d311c-115">Naplósorok létrehozása</span><span class="sxs-lookup"><span data-stu-id="d311c-115">Create journal lines</span></span>
1. <span data-ttu-id="d311c-116">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d311c-116">Click New.</span></span>
2. <span data-ttu-id="d311c-117">A listában jelölje ki a Cikkszám mezőt.</span><span class="sxs-lookup"><span data-stu-id="d311c-117">In the list, mark the item number field.</span></span>
3. <span data-ttu-id="d311c-118">Válasszon egy cikket a Cikkszám mezőben.</span><span class="sxs-lookup"><span data-stu-id="d311c-118">In the Item number field, Select an item.</span></span> <span data-ttu-id="d311c-119">Az USMF bemutatócég használata esetén írja be a „D0001” kódot.</span><span class="sxs-lookup"><span data-stu-id="d311c-119">If you are using demo data company USMF, type 'D0001'.</span></span>
4. <span data-ttu-id="d311c-120">A Hely mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d311c-120">In the Site field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="d311c-121">A listában válasszon ki egy telephelyet.</span><span class="sxs-lookup"><span data-stu-id="d311c-121">In the list, select a site.</span></span>
6. <span data-ttu-id="d311c-122">A Raktár mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d311c-122">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="d311c-123">A listában válasszon ki egy raktárat.</span><span class="sxs-lookup"><span data-stu-id="d311c-123">In the list, select a warehouse.</span></span>
    * <span data-ttu-id="d311c-124">Ha egy olyan cikket választott ki, amelynek kötelező dimenziója a Hely, itt kell megadnia a helyet.</span><span class="sxs-lookup"><span data-stu-id="d311c-124">If you have selected an item with Location as a mandatory dimension, you would have to specify the location here.</span></span>  
8. <span data-ttu-id="d311c-125">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="d311c-125">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="d311c-126">Az önköltségi ár mező meghatározza az egységenkénti költséget a készletbevételek számára.</span><span class="sxs-lookup"><span data-stu-id="d311c-126">The cost price field specifies the cost per unit for inventory receipts.</span></span> <span data-ttu-id="d311c-127">Ha nincs megadva a költség a cikkszámhoz, vagy ha manuálisan szeretné módosítani a költséget, azt itt teheti meg.</span><span class="sxs-lookup"><span data-stu-id="d311c-127">If the cost is not specified for the item number or if you wanted to change it manually, you would do this here.</span></span>  

## <a name="validate-and-post-the-inventory-adjustment-journal"></a><span data-ttu-id="d311c-128">Készlethelyesbítési napló érvényesítése és feladása</span><span class="sxs-lookup"><span data-stu-id="d311c-128">Validate and post the inventory adjustment journal</span></span>
1. <span data-ttu-id="d311c-129">Kattintson az Érvényesítés gombra.</span><span class="sxs-lookup"><span data-stu-id="d311c-129">Click Validate.</span></span>
2. <span data-ttu-id="d311c-130">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="d311c-130">Click OK.</span></span>
3. <span data-ttu-id="d311c-131">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d311c-131">Click Post.</span></span>
    * <span data-ttu-id="d311c-132">Az ilyen típusú napló feladásakor a rendszer egy készletbevételezést vagy készletkiadást ad fel, módosítja a készletszintet és a készletértéket, és főkönyvi tranzakciókat generál.</span><span class="sxs-lookup"><span data-stu-id="d311c-132">When you post this kind of journal, an inventory receipt or issue is posted, the inventory level and value are changed, and ledger transactions are generated.</span></span>  
4. <span data-ttu-id="d311c-133">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="d311c-133">Click OK.</span></span>
5. <span data-ttu-id="d311c-134">Zárja be az űrlapot.</span><span class="sxs-lookup"><span data-stu-id="d311c-134">Close the form.</span></span>
6. <span data-ttu-id="d311c-135">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d311c-135">Close the page.</span></span>

