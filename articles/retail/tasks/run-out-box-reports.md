--- 
title: "Kulcsrakész jelentések generálása és futtatása"
description: "Használja ezt a feladatútmutató kulcsrakész jelentések futtatásához a központban a különböző munkaterületekről és Lekérdezésekből Értékesítési jelentések a Kiskereskedelem és Kereskedelem alatt."
author: ashishmsft
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: e688527bd9ae3346fd2eede956ea673e340f59b8
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="generate-and-run-out-of-box-reports"></a><span data-ttu-id="6bc65-103">Kulcsrakész jelentések generálása és futtatása</span><span class="sxs-lookup"><span data-stu-id="6bc65-103">Generate and run out-of-box reports</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="6bc65-104">Használja ezt a feladatútmutató kulcsrakész jelentések futtatásához a központban a különböző munkaterületekről és Lekérdezésekből Értékesítési jelentések a Kiskereskedelem és Kereskedelem alatt.</span><span class="sxs-lookup"><span data-stu-id="6bc65-104">Use this task guide to run out of box reports in headquarters from different workspaces and Inquiries & Sales reports located under Retail & Commerce.</span></span>



<span data-ttu-id="6bc65-105">A bemutató adatsor típusa, melyet a vállalat használt az útmutató készítéséhez, az USRT.</span><span class="sxs-lookup"><span data-stu-id="6bc65-105">The demo data company used to create this recording is USRT.</span></span> <span data-ttu-id="6bc65-106">Ez a felvétel a Rendszeradminisztrátor szerepkör számára készült.</span><span class="sxs-lookup"><span data-stu-id="6bc65-106">This recording is intended for the System administrator role.</span></span>


## <a name="launch-reports-from-workspaces"></a><span data-ttu-id="6bc65-107">Indítsa el a jelentéseket a munkaterületekről</span><span class="sxs-lookup"><span data-stu-id="6bc65-107">Launch reports from workspaces</span></span>
1. <span data-ttu-id="6bc65-108">Ugorjon a Kiskereskedelem és kereskedelem > Termékek és kategóriák > Kategóriák és termékmenedzsment lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6bc65-108">Go to Retail and commerce > Products and categories > Category and product management.</span></span>
2. <span data-ttu-id="6bc65-109">Kattintson a nyílra a Jelentések szakasz kibontásához vagy összecsukásához.</span><span class="sxs-lookup"><span data-stu-id="6bc65-109">Click the arrow to expand or collapse the Reports section.</span></span>
3. <span data-ttu-id="6bc65-110">Kattintson a Vezető termékek jelentései lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6bc65-110">Click Top products report.</span></span>
4. <span data-ttu-id="6bc65-111">Adjon meg egy
Adjon meg egy dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="6bc65-111">In the From date field, enter a date.</span></span>
5. <span data-ttu-id="6bc65-112">Adja meg a dátumot a „Záró dátum” mezőben.</span><span class="sxs-lookup"><span data-stu-id="6bc65-112">In the To date field, enter a date.</span></span>
6. <span data-ttu-id="6bc65-113">A Csatorna mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="6bc65-113">In the Channel field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="6bc65-114">A fanézetben válassza ki a „Contoso Retail\Contoso Retail USA\Central\Houston” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6bc65-114">In the tree, select 'Contoso Retail\Contoso Retail USA\Central\Houston'.</span></span>
    * <span data-ttu-id="6bc65-115">Ez megmutatja az alapértelmezett kiskereskedelmi szervezeti hierarchiát Kiskereskedelmi jelentési célból.</span><span class="sxs-lookup"><span data-stu-id="6bc65-115">This shows the default retail organization hierarchy for Retail reporting purpose.</span></span>   <span data-ttu-id="6bc65-116">Ugorjon a Szervezet felügyelete >Szervezetek > Szervezeti hierarchia céljai lehetőségre és válassza ki a kiskereskedelmi jelentést, majd a Hozzárendelt hierarchiák alatt ellenőrizze a hierarchia nevét, amelyhez be van jelölve az Alapértelmezett oszlop.</span><span class="sxs-lookup"><span data-stu-id="6bc65-116">Go to Organization administration >Organizations >Organization hierarchy purposes and choose Retail reporting and under Assigned hierarchies, check the hierarchy name for which Default column is checked.</span></span>      <span data-ttu-id="6bc65-117">A (feladatrögzítéshez használt) bemutatóadatok részeként észre fogja venni, hogy a Kiskereskedelmi áruházak régiók szerint az alapértelmezett szervezeti hierarchia a Kiskereskedelmi jelentési célra.</span><span class="sxs-lookup"><span data-stu-id="6bc65-117">As part of demo data (used for this task recording) you would notice, Retail Stores by Region, is the default organization hierarchy for the Retail reporting purpose.</span></span>     
8. <span data-ttu-id="6bc65-118">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="6bc65-118">Click OK.</span></span>
9. <span data-ttu-id="6bc65-119">Válasszon ki egy lehetősége a Nézet mezőben.</span><span class="sxs-lookup"><span data-stu-id="6bc65-119">In the View field, select an option.</span></span>
10. <span data-ttu-id="6bc65-120">Válasszon ki egy lehetőséget a Szerint mezőben.</span><span class="sxs-lookup"><span data-stu-id="6bc65-120">In the By field, select an option.</span></span>
11. <span data-ttu-id="6bc65-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="6bc65-121">Click OK.</span></span>

## <a name="launch-reports-from-the-inquiries-and-sales-reports-located-under-retail--commerce-app-link"></a><span data-ttu-id="6bc65-122">Indítsa el a jelentéseket a lekérdezésekből, illetve a Retail & Commerce alkalmazás alatt található értékesítési jelentéseket.</span><span class="sxs-lookup"><span data-stu-id="6bc65-122">Launch reports from the inquiries and sales reports located under Retail & Commerce app link.</span></span>
1. <span data-ttu-id="6bc65-123">Ugorjon a Kiskereskedelmi és kereskedelem > Lekérdezések és jelentések > Értékesítési jelentések > Értékesítési kategória-jelentés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6bc65-123">Go to Retail and commerce > Inquiries and reports > Sales reports > Category sales report.</span></span>
2. <span data-ttu-id="6bc65-124">Adjon meg egy
Adjon meg egy dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="6bc65-124">In the From date field, enter a date.</span></span>
3. <span data-ttu-id="6bc65-125">Adja meg a dátumot a „Záró dátum” mezőben.</span><span class="sxs-lookup"><span data-stu-id="6bc65-125">In the To date field, enter a date.</span></span>
4. <span data-ttu-id="6bc65-126">A Csatorna mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="6bc65-126">In the Channel field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="6bc65-127">A fanézetben válassza ki a „Contoso Retail\Contoso Retail USA\West\Seattle” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6bc65-127">In the tree, select 'Contoso Retail\Contoso Retail USA\West\Seattle'.</span></span>
    * <span data-ttu-id="6bc65-128">Ez megmutatja az alapértelmezett kiskereskedelmi szervezeti hierarchiát Kiskereskedelmi jelentési célból.</span><span class="sxs-lookup"><span data-stu-id="6bc65-128">This shows the default retail organization hierarchy for Retail reporting purpose.</span></span>   <span data-ttu-id="6bc65-129">Ugorjon a Szervezet felügyelete >Szervezetek > Szervezeti hierarchia céljai lehetőségre és válassza ki a kiskereskedelmi jelentést, majd a Hozzárendelt hierarchiák alatt ellenőrizze a hierarchia nevét, amelyhez be van jelölve az Alapértelmezett oszlop.</span><span class="sxs-lookup"><span data-stu-id="6bc65-129">Go to Organization administration >Organizations >Organization hierarchy purposes and choose Retail reporting and under Assigned hierarchies, check the hierarchy name for which Default column is checked.</span></span>      <span data-ttu-id="6bc65-130">A (feladatrögzítéshez használt) bemutatóadatok részeként észre fogja venni, hogy a Kiskereskedelmi áruházak régiók szerint az alapértelmezett szervezeti hierarchia a Kiskereskedelmi jelentési célra.</span><span class="sxs-lookup"><span data-stu-id="6bc65-130">As part of demo data (used for this task recording) you would notice, Retail Stores by Region, is the default organization hierarchy for the Retail reporting purpose.</span></span>     
6. <span data-ttu-id="6bc65-131">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="6bc65-131">Click OK.</span></span>
7. <span data-ttu-id="6bc65-132">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="6bc65-132">Click OK.</span></span>

## <a name="export-an-hq-reports"></a><span data-ttu-id="6bc65-133">Központi jelentések exportálása</span><span class="sxs-lookup"><span data-stu-id="6bc65-133">Export an HQ reports</span></span>
1. <span data-ttu-id="6bc65-134">Ugorjon a Kiskereskedelmi és kereskedelem > Lekérdezések és jelentések > Értékesítési jelentések > Szervezeti kategória-jelentés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6bc65-134">Go to Retail and commerce > Inquiries and reports > Sales reports > Organization sales report.</span></span>
2. <span data-ttu-id="6bc65-135">Adjon meg egy
Adjon meg egy dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="6bc65-135">In the From date field, enter a date.</span></span>
3. <span data-ttu-id="6bc65-136">Adja meg a dátumot a „Záró dátum” mezőben.</span><span class="sxs-lookup"><span data-stu-id="6bc65-136">In the To date field, enter a date.</span></span>
4. <span data-ttu-id="6bc65-137">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="6bc65-137">Click OK.</span></span>
5. <span data-ttu-id="6bc65-138">Kattintson az Exportálás elemre.</span><span class="sxs-lookup"><span data-stu-id="6bc65-138">Click Export.</span></span>
6. <span data-ttu-id="6bc65-139">Kattintson a PDF elemre.</span><span class="sxs-lookup"><span data-stu-id="6bc65-139">Click PDF.</span></span>

