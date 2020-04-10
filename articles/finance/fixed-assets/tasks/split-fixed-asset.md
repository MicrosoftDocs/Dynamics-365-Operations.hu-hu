---
title: Tárgyi eszköz felosztása
description: Ez a témakör azt ismerteti, hogyan kell egy eszközkönyv egy részét egy másik eszközkönyvhöz rendeli.
author: saraschi2
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 85ccf187e77faf338ac29452d823c3652b806a21
ms.sourcegitcommit: c69926b4285cb2ec2d9ce1ad72d1cb852024dd5e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3138115"
---
# <a name="split-a-fixed-asset"></a><span data-ttu-id="076d3-103">Tárgyi eszköz felosztása</span><span class="sxs-lookup"><span data-stu-id="076d3-103">Split a fixed asset</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="076d3-104">Ez a témakör azt ismerteti, hogyan kell egy eszközkönyv egy részét egy másik eszközkönyvhöz rendeli.</span><span class="sxs-lookup"><span data-stu-id="076d3-104">This topic explains how to split a percentage of one asset book to a new asset book.</span></span> <span data-ttu-id="076d3-105">A Könyvelői szerepkört és a USMF bemutató adatokat használja.</span><span class="sxs-lookup"><span data-stu-id="076d3-105">It uses the Accountant role and USMF demo data.</span></span>


## <a name="create-a-new-fixed-asset"></a><span data-ttu-id="076d3-106">Új tárgyi eszköz létrehozása</span><span class="sxs-lookup"><span data-stu-id="076d3-106">Create a new fixed asset</span></span>
1. <span data-ttu-id="076d3-107">A navigációs ablaktáblán ugorjon a **Modulok > Tárgyi eszközök > Tárgyi eszközök > Tárgyi eszközök** elemre.</span><span class="sxs-lookup"><span data-stu-id="076d3-107">In the navigation pane, go to **Modules > Fixed assets > Fixed assets > Fixed assets**.</span></span>
2. <span data-ttu-id="076d3-108">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="076d3-108">Select **New**.</span></span>
3. <span data-ttu-id="076d3-109">A **Tárgyieszköz-csoport** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="076d3-109">In the **Fixed asset group** field, enter or select a value.</span></span> <span data-ttu-id="076d3-110">Jegyezze fel a tárgyi eszköz számát, a felosztás során későbbi felhasználás céljából.</span><span class="sxs-lookup"><span data-stu-id="076d3-110">Note the fixed asset number to use in the split process later.</span></span>  
4. <span data-ttu-id="076d3-111">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="076d3-111">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="076d3-112">Zárja be az űrlapot.</span><span class="sxs-lookup"><span data-stu-id="076d3-112">Close the form.</span></span>

## <a name="split-a-fixed-asset"></a><span data-ttu-id="076d3-113">Tárgyi eszköz felosztása</span><span class="sxs-lookup"><span data-stu-id="076d3-113">Split a fixed asset</span></span>
1. <span data-ttu-id="076d3-114">A listában keresse meg és válassza ki a felosztani kívánt tárgyi eszköz hivatkozását.</span><span class="sxs-lookup"><span data-stu-id="076d3-114">In the list, find and select the link of the fixed asset to split.</span></span>
2. <span data-ttu-id="076d3-115">Válassza ki a **Könyvek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="076d3-115">Select **Books**.</span></span> <span data-ttu-id="076d3-116">Válassza ki az új tárgyi eszközhöz hozzárendelni kívánt könyvet.</span><span class="sxs-lookup"><span data-stu-id="076d3-116">Select the book to split to the new asset.</span></span>  
3. <span data-ttu-id="076d3-117">Válassza a **Funkciók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="076d3-117">Select **Functions**.</span></span>
4. <span data-ttu-id="076d3-118">Válassza ki a **Tárgyi eszköz felosztása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="076d3-118">Select **Split fixed asset**.</span></span>
5. <span data-ttu-id="076d3-119">A **Záró tárgyi eszköz** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="076d3-119">In the **To fixed asset** field, enter or select a value.</span></span>
6. <span data-ttu-id="076d3-120">A **Könyvhöz** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="076d3-120">In the **To book** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="076d3-121">A **Tranzakció dátuma** mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="076d3-121">In the **Transaction date** field, enter a date.</span></span>
8. <span data-ttu-id="076d3-122">Adjon meg egy számot a  **Százalék** mezőben.</span><span class="sxs-lookup"><span data-stu-id="076d3-122">In the **Percent** field, enter a number.</span></span>
9. <span data-ttu-id="076d3-123">A **Napló neve** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="076d3-123">In the **Journal name** field, enter or select a value.</span></span>
10. <span data-ttu-id="076d3-124">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="076d3-124">Select **OK**.</span></span>

## <a name="post-the-journal-transaction"></a><span data-ttu-id="076d3-125">Naplótranzakciók feladása</span><span class="sxs-lookup"><span data-stu-id="076d3-125">Post the journal transaction</span></span>
1. <span data-ttu-id="076d3-126">A navigációs ablaktáblán nyissa meg a **Modulok > Tárgyi eszközök > Naplóbejegyzések > Tárgyi eszközök naplója** elemet.</span><span class="sxs-lookup"><span data-stu-id="076d3-126">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="076d3-127">A listában válassza ki a felosztással létrehozott naplót.</span><span class="sxs-lookup"><span data-stu-id="076d3-127">In the list, select the journal created with the split process.</span></span>
3. <span data-ttu-id="076d3-128">**Sorok** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="076d3-128">Select **Lines**.</span></span>

    - <span data-ttu-id="076d3-129">Erősítse meg a létrehozott naplósorokat.</span><span class="sxs-lookup"><span data-stu-id="076d3-129">Verify the journal lines created.</span></span>  
    - <span data-ttu-id="076d3-130">Egy beszerzés-helyesbítési tranzakció jön létre az eredeti tárgyi eszközhöz az értéknek a felosztás során generált százalékkal történő csökkentéséhez.</span><span class="sxs-lookup"><span data-stu-id="076d3-130">An Acquisition adjustment transaction is created for the original asset to decrease the value by the percentage specified during the split process.</span></span>  
    - <span data-ttu-id="076d3-131">Egy Beszerzési tranzakció jön létre az új eszközhöz ugyanazzal az összeggel.</span><span class="sxs-lookup"><span data-stu-id="076d3-131">An Acquisition transaction is created for the new asset for the same amount.</span></span>  

4. <span data-ttu-id="076d3-132">Válassza a **Feladás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="076d3-132">Select **Post**.</span></span>

