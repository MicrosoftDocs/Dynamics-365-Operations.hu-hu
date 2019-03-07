---
title: Tárgyi eszköz felosztása
description: Ez a feladat-útmutató az egyik eszközkönyv egy részét egy másik eszközkönyvhöz rendeli.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6be9de64265a4d7b5c91af3ee8acfce80c78e0f1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "333369"
---
# <a name="split-a-fixed-asset"></a><span data-ttu-id="c79a4-103">Tárgyi eszköz felosztása</span><span class="sxs-lookup"><span data-stu-id="c79a4-103">Split a fixed asset</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c79a4-104">Ez a feladat-útmutató az egyik eszközkönyv egy részét egy másik eszközkönyvhöz rendeli.</span><span class="sxs-lookup"><span data-stu-id="c79a4-104">This task guide will split a percentage of one asset book to a new asset book.</span></span>  <span data-ttu-id="c79a4-105">A Könyvelői szerepkört és a USMF bemutató adatokat használja.</span><span class="sxs-lookup"><span data-stu-id="c79a4-105">It uses the Accountant role and USMF demo data.</span></span>


## <a name="create-a-new-fixed-asset"></a><span data-ttu-id="c79a4-106">Új tárgyi eszköz létrehozása</span><span class="sxs-lookup"><span data-stu-id="c79a4-106">Create a new fixed asset</span></span>
1. <span data-ttu-id="c79a4-107">Nyissa meg a következőt: Tárgyi eszközök > Tárgyi eszközök > Tárgyi eszközök.</span><span class="sxs-lookup"><span data-stu-id="c79a4-107">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="c79a4-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c79a4-108">Click New.</span></span>
3. <span data-ttu-id="c79a4-109">A Tárgyieszköz-csoport mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c79a4-109">In the Fixed asset group field, enter or select a value.</span></span>
4. <span data-ttu-id="c79a4-110">Jegyezze fel a tárgyi eszköz számát, a felosztás során későbbi felhasználás céljából.</span><span class="sxs-lookup"><span data-stu-id="c79a4-110">Note the fixed asset number to use in the split process later.</span></span>
5. <span data-ttu-id="c79a4-111">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c79a4-111">In the Name field, type a value.</span></span>
6. <span data-ttu-id="c79a4-112">Zárja be az űrlapot.</span><span class="sxs-lookup"><span data-stu-id="c79a4-112">Close the form.</span></span>

## <a name="split-a-fixed-asset"></a><span data-ttu-id="c79a4-113">Tárgyi eszköz felosztása</span><span class="sxs-lookup"><span data-stu-id="c79a4-113">Split a fixed asset</span></span>
1. <span data-ttu-id="c79a4-114">A listában keresse meg és válassza ki a felosztani kívánt tárgyi eszközt.</span><span class="sxs-lookup"><span data-stu-id="c79a4-114">In the list, find and select the fixed asset to split.</span></span>
2. <span data-ttu-id="c79a4-115">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="c79a4-115">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="c79a4-116">Kattintson a Könyvek elemre.</span><span class="sxs-lookup"><span data-stu-id="c79a4-116">Click Books.</span></span>
    * <span data-ttu-id="c79a4-117">Válassza ki az új tárgyi eszközhöz hozzárendelni kívánt könyvet.</span><span class="sxs-lookup"><span data-stu-id="c79a4-117">Select the book to split to the new asset.</span></span>  
4. <span data-ttu-id="c79a4-118">Kattintson a Funkciók elemre.</span><span class="sxs-lookup"><span data-stu-id="c79a4-118">Click Functions.</span></span>
5. <span data-ttu-id="c79a4-119">Kattintson a Tárgyi eszköz értékének felosztása gombra.</span><span class="sxs-lookup"><span data-stu-id="c79a4-119">Click Split fixed asset.</span></span>
6. <span data-ttu-id="c79a4-120">A Cél tárgyi eszköz mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c79a4-120">In the To fixed asset field, enter or select a value.</span></span>
7. <span data-ttu-id="c79a4-121">A Könyvbe mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="c79a4-121">In the To book field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="c79a4-122">A Tranzakció dátuma mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="c79a4-122">In the Transaction date field, enter a date.</span></span>
9. <span data-ttu-id="c79a4-123">A Százalék mezőbe írjon be egy számot.</span><span class="sxs-lookup"><span data-stu-id="c79a4-123">In the Percent field, enter a number.</span></span>
10. <span data-ttu-id="c79a4-124">A Napló neve mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c79a4-124">In the Journal name field, enter or select a value.</span></span>
11. <span data-ttu-id="c79a4-125">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c79a4-125">Click OK.</span></span>

## <a name="post-the-journal-transaction"></a><span data-ttu-id="c79a4-126">Naplótranzakciók feladása</span><span class="sxs-lookup"><span data-stu-id="c79a4-126">Post the journal transaction</span></span>
1. <span data-ttu-id="c79a4-127">Ugorjon a Tárgyi eszközök > Naplóbejegyzések > Tárgyi eszközök naplója pontra.</span><span class="sxs-lookup"><span data-stu-id="c79a4-127">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>
2. <span data-ttu-id="c79a4-128">A listában válassza ki a felosztással létrehozott naplót.</span><span class="sxs-lookup"><span data-stu-id="c79a4-128">In the list, select the journal created with the split process.</span></span>
3. <span data-ttu-id="c79a4-129">Kattintson a Sorok pontra.</span><span class="sxs-lookup"><span data-stu-id="c79a4-129">Click Lines.</span></span>
    * <span data-ttu-id="c79a4-130">Erősítse meg a létrehozott naplósorokat.</span><span class="sxs-lookup"><span data-stu-id="c79a4-130">Verify the journal lines created.</span></span>  <span data-ttu-id="c79a4-131">Egy beszerzés-helyesbítési tranzakció jön létre az eredeti tárgyi eszközhöz az értéknek a felosztás során generált százalékkal történő csökkentéséhez.</span><span class="sxs-lookup"><span data-stu-id="c79a4-131">An Acquisition adjustment transaction is created for the original asset to decrease the value by the percentage specified during the split process.</span></span>  <span data-ttu-id="c79a4-132">Egy Beszerzési tranzakció jön létre az új eszközhöz ugyanazzal az összeggel.</span><span class="sxs-lookup"><span data-stu-id="c79a4-132">An Acquisition transaction is created for the new asset for the same amount.</span></span>  
4. <span data-ttu-id="c79a4-133">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c79a4-133">Click Post.</span></span>

