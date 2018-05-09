--- 
title: "Fizetési felszólítások feldolgozása"
description: "Ez az eljárás a fizetési felszólítások létrehozását, nyomtatását és feladását mutatja be."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: cd53744abc4c43b8c7b97ee5cd057fff684c32e5
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="process-collection-letters"></a><span data-ttu-id="58126-103">Fizetési felszólítások feldolgozása</span><span class="sxs-lookup"><span data-stu-id="58126-103">Process collection letters</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="58126-104">Ez az eljárás a fizetési felszólítások létrehozását, nyomtatását és feladását mutatja be.</span><span class="sxs-lookup"><span data-stu-id="58126-104">This procedure shows how to create, print, and post collection letters.</span></span> <span data-ttu-id="58126-105">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="58126-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a><span data-ttu-id="58126-106">Állítson be egy fizetésifelszólítás-sorozatot a feladási profilon.</span><span class="sxs-lookup"><span data-stu-id="58126-106">Set up a collection letter sequence on the posting profile</span></span>
1. <span data-ttu-id="58126-107">Ugorjon a Követel és beszedések > Beállítás > Vevői feladási profilok pontra.</span><span class="sxs-lookup"><span data-stu-id="58126-107">Go to Credit and collections > Setup > Customer posting profiles.</span></span>
2. <span data-ttu-id="58126-108">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="58126-108">Click Edit.</span></span>
    * <span data-ttu-id="58126-109">Válasszon egy fizetésifelszólítás-sorozatot a legördülő listából.</span><span class="sxs-lookup"><span data-stu-id="58126-109">Select a collection letter sequence from the drop-down list.</span></span> <span data-ttu-id="58126-110">Ha nem szeretne fizetési felszólítást létrehozni a tranzakciókhoz ezzel a feladói profillal, hagyja a mezőt üresen.</span><span class="sxs-lookup"><span data-stu-id="58126-110">If you do not want generate collection letters for transactions using this posting profile, leave the field blank.</span></span>  
    * <span data-ttu-id="58126-111">A Tábla korlátozási lapján módosíthatja a fizetési felszólítások feldolgozásának módját.</span><span class="sxs-lookup"><span data-stu-id="58126-111">The table restriction tab allows you to change the way that collection letters are processed.</span></span> <span data-ttu-id="58126-112">Ha ez a mező Igen értékre van állítva, fizetési felszólítások kerülnek létrehozásra a feladási profilhoz.</span><span class="sxs-lookup"><span data-stu-id="58126-112">If this field is set to Yes, then collection letters will be created for this posting profile.</span></span>  
3. <span data-ttu-id="58126-113">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="58126-113">Close the page.</span></span>

## <a name="create-collection-letters"></a><span data-ttu-id="58126-114">Fizetési felszólítások létrehozása</span><span class="sxs-lookup"><span data-stu-id="58126-114">Create collection letters</span></span>
1. <span data-ttu-id="58126-115">Ugorjona a Követelések és beszedések > Fizetési felszólítás > Fizetési felszólítások létrehozása pontra.</span><span class="sxs-lookup"><span data-stu-id="58126-115">Go to Credit and collections > Collection letter > Create collection letters.</span></span>
    * <span data-ttu-id="58126-116">Ki kell választania azokat a tranzakciótípusokat, amelyekre fizetési felszólítást szeretne létrehozni.</span><span class="sxs-lookup"><span data-stu-id="58126-116">You must select the transaction types for which you will collect letters.</span></span> <span data-ttu-id="58126-117">Ez ilyen típusokhoz tartozó nyitott tranzakciók szerepelni fognak a számításban.</span><span class="sxs-lookup"><span data-stu-id="58126-117">All of the open transactions for these types will be included in the calculation.</span></span>  
2. <span data-ttu-id="58126-118">A Fizetési felszólítás mezőben válassza ki a kívánt beállítást.</span><span class="sxs-lookup"><span data-stu-id="58126-118">In the Collection letter field, select an option.</span></span>
3. <span data-ttu-id="58126-119">Adja meg a fizetési felszólítás dátumát.</span><span class="sxs-lookup"><span data-stu-id="58126-119">Enter the date of the collection letter.</span></span>
    * <span data-ttu-id="58126-120">Kétféle feladási profil lehetőség létezik: Számla – A vevő számlájához rendelt feladási profil minden egyes kamatlevélre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="58126-120">There are two posting profile options:   Account – Use the posting profile that is assigned to the customer account for each interest note.</span></span>   <span data-ttu-id="58126-121">Kiválasztott – a Feladási mezőben megadott feladási profil használata.</span><span class="sxs-lookup"><span data-stu-id="58126-121">Select – Use the posting profile that you select in the Posting profile field.</span></span>  
    * <span data-ttu-id="58126-122">Válasszon ki egy feladási profilt, ha módosította a „Feladási profil használata képernyő” lehetőséget „Kiválasztott” lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="58126-122">Select a posting profile if you changed "Use posting profile from" to "Select".</span></span>  
4. <span data-ttu-id="58126-123">Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="58126-123">Expand the Records to include section.</span></span>
5. <span data-ttu-id="58126-124">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="58126-124">Click Filter.</span></span>
6. <span data-ttu-id="58126-125">A Feltételek mezőben, a Feltételek mezőben, adjon meg egy vevői azonosítót.</span><span class="sxs-lookup"><span data-stu-id="58126-125">In the Criteria field, In the Criteria field, enter a Customer ID.</span></span> <span data-ttu-id="58126-126">Adja meg például az „US-001”-et.</span><span class="sxs-lookup"><span data-stu-id="58126-126">For example, enter 'US-001'..</span></span>
7. <span data-ttu-id="58126-127">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="58126-127">Click OK.</span></span>
8. <span data-ttu-id="58126-128">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="58126-128">Click OK.</span></span>

## <a name="print-collection-letters"></a><span data-ttu-id="58126-129">Fizetési felszólítások nyomtatása</span><span class="sxs-lookup"><span data-stu-id="58126-129">Print collection letters</span></span>
1. <span data-ttu-id="58126-130">Ugorjon a Követelések és beszedések > Fizetési felszólítás > Fizetési felszólítások áttekintése és feldolgozása pontra.</span><span class="sxs-lookup"><span data-stu-id="58126-130">Go to Credit and collections > Collection letter > Review and process collection letters.</span></span>
2. <span data-ttu-id="58126-131">Az Állapot mezőben válassza ki a „Létrehozva” értéket.</span><span class="sxs-lookup"><span data-stu-id="58126-131">In the Status field, select 'Created'.</span></span>
3. <span data-ttu-id="58126-132">A Nyomtatott mezőben válassza a „Nem nyomtatva” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="58126-132">In the Printed field, select 'Not printed'.</span></span>
4. <span data-ttu-id="58126-133">Kattintson a Nyomtatás parancsra.</span><span class="sxs-lookup"><span data-stu-id="58126-133">Click Print.</span></span>
5. <span data-ttu-id="58126-134">Kattintson a Fizetésre felszólítás gombra.</span><span class="sxs-lookup"><span data-stu-id="58126-134">Click Collection letter note.</span></span>
6. <span data-ttu-id="58126-135">Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="58126-135">Expand the Records to include section.</span></span>
7. <span data-ttu-id="58126-136">Adja meg a feladások fordulónapjának dátumát.</span><span class="sxs-lookup"><span data-stu-id="58126-136">Enter the cutoff date for postings</span></span>
8. <span data-ttu-id="58126-137">Kattintson az OK gombra a fizetési felszólítás nyomtatásához.</span><span class="sxs-lookup"><span data-stu-id="58126-137">Click OK to print the collection letter.</span></span>

## <a name="post-the-collection-letter"></a><span data-ttu-id="58126-138">A fizetési felszólítás feladása</span><span class="sxs-lookup"><span data-stu-id="58126-138">Post the collection letter</span></span>
1. <span data-ttu-id="58126-139">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="58126-139">Click Post.</span></span>
2. <span data-ttu-id="58126-140">Adja meg a fizetési felszólítás feladási dátumát.</span><span class="sxs-lookup"><span data-stu-id="58126-140">Enter the posting date for the collection letter.</span></span>
3. <span data-ttu-id="58126-141">Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="58126-141">Expand the Records to include section.</span></span>
4. <span data-ttu-id="58126-142">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="58126-142">Click OK.</span></span>
5. <span data-ttu-id="58126-143">Az Állapot mezőben válassza ki a „Feladott” értéket.</span><span class="sxs-lookup"><span data-stu-id="58126-143">In the Status field, select 'Posted'.</span></span>
6. <span data-ttu-id="58126-144">Válasszon ki egy lehetőséget a Nyomtatott mezőben.</span><span class="sxs-lookup"><span data-stu-id="58126-144">In the Printed field, select an option.</span></span>


