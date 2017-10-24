--- 
title: "Tárgyi eszköz felosztása"
description: "Ez a feladat-útmutató az egyik eszközkönyv egy részét egy másik eszközkönyvhöz rendeli."
author: saraschi2
manager: AnnBe
ms.date: 10/19/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b4c1b39bcae1fa3830f3a217d1ad89e84cd72134
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="split-a-fixed-asset"></a><span data-ttu-id="15cc7-103">Tárgyi eszköz felosztása</span><span class="sxs-lookup"><span data-stu-id="15cc7-103">Split a fixed asset</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="15cc7-104">Ez a feladat-útmutató az egyik eszközkönyv egy részét egy másik eszközkönyvhöz rendeli.</span><span class="sxs-lookup"><span data-stu-id="15cc7-104">This task guide will split a percentage of one asset book to a new asset book.</span></span>  <span data-ttu-id="15cc7-105">A Könyvelői szerepkört és a USMF bemutató adatokat használja.</span><span class="sxs-lookup"><span data-stu-id="15cc7-105">It uses the Accountant role and USMF demo data.</span></span>


## <a name="create-a-new-fixed-asset"></a><span data-ttu-id="15cc7-106">Új tárgyi eszköz létrehozása</span><span class="sxs-lookup"><span data-stu-id="15cc7-106">Create a new fixed asset</span></span>
1. <span data-ttu-id="15cc7-107">Nyissa meg a következőt: Tárgyi eszközök > Tárgyi eszközök > Tárgyi eszközök.</span><span class="sxs-lookup"><span data-stu-id="15cc7-107">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="15cc7-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="15cc7-108">Click New.</span></span>
3. <span data-ttu-id="15cc7-109">A Tárgyieszköz-csoport mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="15cc7-109">In the Fixed asset group field, enter or select a value.</span></span>
4. <span data-ttu-id="15cc7-110">Jegyezze fel a tárgyi eszköz számát, a felosztás során későbbi felhasználás céljából.</span><span class="sxs-lookup"><span data-stu-id="15cc7-110">Note the fixed asset number to use in the split process later.</span></span>
5. <span data-ttu-id="15cc7-111">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="15cc7-111">In the Name field, type a value.</span></span>
6. <span data-ttu-id="15cc7-112">Zárja be az űrlapot.</span><span class="sxs-lookup"><span data-stu-id="15cc7-112">Close the form.</span></span>

## <a name="split-a-fixed-asset"></a><span data-ttu-id="15cc7-113">Tárgyi eszköz felosztása</span><span class="sxs-lookup"><span data-stu-id="15cc7-113">Split a fixed asset</span></span>
1. <span data-ttu-id="15cc7-114">A listában keresse meg és válassza ki a felosztani kívánt tárgyi eszközt.</span><span class="sxs-lookup"><span data-stu-id="15cc7-114">In the list, find and select the fixed asset to split.</span></span>
2. <span data-ttu-id="15cc7-115">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="15cc7-115">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="15cc7-116">Kattintson a Könyvek elemre.</span><span class="sxs-lookup"><span data-stu-id="15cc7-116">Click Books.</span></span>
    * <span data-ttu-id="15cc7-117">Válassza ki az új tárgyi eszközhöz hozzárendelni kívánt könyvet.</span><span class="sxs-lookup"><span data-stu-id="15cc7-117">Select the book to split to the new asset.</span></span>  
4. <span data-ttu-id="15cc7-118">Kattintson a Funkciók elemre.</span><span class="sxs-lookup"><span data-stu-id="15cc7-118">Click Functions.</span></span>
5. <span data-ttu-id="15cc7-119">Kattintson a Tárgyi eszköz értékének felosztása gombra.</span><span class="sxs-lookup"><span data-stu-id="15cc7-119">Click Split fixed asset.</span></span>
6. <span data-ttu-id="15cc7-120">A Cél tárgyi eszköz mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="15cc7-120">In the To fixed asset field, enter or select a value.</span></span>
7. <span data-ttu-id="15cc7-121">A Könyvbe mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="15cc7-121">In the To book field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="15cc7-122">A Tranzakció dátuma mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="15cc7-122">In the Transaction date field, enter a date.</span></span>
9. <span data-ttu-id="15cc7-123">A Százalék mezőbe írjon be egy számot.</span><span class="sxs-lookup"><span data-stu-id="15cc7-123">In the Percent field, enter a number.</span></span>
10. <span data-ttu-id="15cc7-124">A Napló neve mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="15cc7-124">In the Journal name field, enter or select a value.</span></span>
11. <span data-ttu-id="15cc7-125">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="15cc7-125">Click OK.</span></span>

## <a name="post-the-journal-transaction"></a><span data-ttu-id="15cc7-126">Naplótranzakciók feladása</span><span class="sxs-lookup"><span data-stu-id="15cc7-126">Post the journal transaction</span></span>
1. <span data-ttu-id="15cc7-127">Ugorjon a Tárgyi eszközök > Naplóbejegyzések > Tárgyi eszközök naplója pontra.</span><span class="sxs-lookup"><span data-stu-id="15cc7-127">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>
2. <span data-ttu-id="15cc7-128">A listában válassza ki a felosztással létrehozott naplót.</span><span class="sxs-lookup"><span data-stu-id="15cc7-128">In the list, select the journal created with the split process.</span></span>
3. <span data-ttu-id="15cc7-129">Kattintson a Sorok pontra.</span><span class="sxs-lookup"><span data-stu-id="15cc7-129">Click Lines.</span></span>
    * <span data-ttu-id="15cc7-130">Erősítse meg a létrehozott naplósorokat.</span><span class="sxs-lookup"><span data-stu-id="15cc7-130">Verify the journal lines created.</span></span>  <span data-ttu-id="15cc7-131">Egy beszerzés-helyesbítési tranzakció jön létre az eredeti tárgyi eszközhöz az értéknek a felosztás során generált százalékkal történő csökkentéséhez.</span><span class="sxs-lookup"><span data-stu-id="15cc7-131">An Acquisition adjustment transaction is created for the original asset to decrease the value by the percentage specified during the split process.</span></span>  <span data-ttu-id="15cc7-132">Egy Beszerzési tranzakció jön létre az új eszközhöz ugyanazzal az összeggel.</span><span class="sxs-lookup"><span data-stu-id="15cc7-132">An Acquisition transaction is created for the new asset for the same amount.</span></span>  
4. <span data-ttu-id="15cc7-133">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="15cc7-133">Click Post.</span></span>

