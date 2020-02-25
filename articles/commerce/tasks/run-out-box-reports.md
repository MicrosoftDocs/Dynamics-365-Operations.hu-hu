---
title: Kulcsrakész jelentések generálása és futtatása
description: Használja ezt a feladatútmutatót kulcsrakész jelentések futtatásához a Központban a Commerce-ben található különböző munkaterületekről és Lekérdezésekből és Értékesítési jelentésekből.
author: ashishmsft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailCategoryAndProductWorkspace, RetailOrgHierarchyTreeLookup, SrsReportViewerForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5f9931a39e4ca2141ed5b43086226c7fcc7cbd7c
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022756"
---
# <a name="generate-and-run-out-of-box-reports"></a><span data-ttu-id="3b02c-103">Kulcsrakész jelentések generálása és futtatása</span><span class="sxs-lookup"><span data-stu-id="3b02c-103">Generate and run out of box reports</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="3b02c-104">Használja ezt a feladatútmutatót kulcsrakész jelentések futtatásához a Központban a Commerce-ben található különböző munkaterületekről és Lekérdezésekből és Értékesítési jelentésekből.</span><span class="sxs-lookup"><span data-stu-id="3b02c-104">Use this task guide to run out of box reports in Headquarters from different workspaces and Inquiries & Sales reports located in Commerce.</span></span>

<span data-ttu-id="3b02c-105">A bemutató adatsor típusa, melyet a vállalat használt az útmutató készítéséhez, az USRT.</span><span class="sxs-lookup"><span data-stu-id="3b02c-105">The demo data company used to create this recording is USRT.</span></span> <span data-ttu-id="3b02c-106">Ez a felvétel a Rendszeradminisztrátor szerepkör számára készült.</span><span class="sxs-lookup"><span data-stu-id="3b02c-106">This recording is intended for the System administrator role.</span></span>

## <a name="launch-reports-from-workspaces"></a><span data-ttu-id="3b02c-107">Indítsa el a jelentéseket a munkaterületekről</span><span class="sxs-lookup"><span data-stu-id="3b02c-107">Launch reports from workspaces</span></span>
1. <span data-ttu-id="3b02c-108">Ugorjon a Retail and Commerce > Termékek és kategóriák > Kategóriák és termékmenedzsment lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3b02c-108">Go to Retail and Commerce > Products and categories > Category and product management.</span></span>
2. <span data-ttu-id="3b02c-109">Kattintson a nyílra a Jelentések szakasz kibontásához vagy összecsukásához.</span><span class="sxs-lookup"><span data-stu-id="3b02c-109">Click the arrow to expand or collapse the Reports section.</span></span>
3. <span data-ttu-id="3b02c-110">Kattintson a Vezető termékek jelentései lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3b02c-110">Click Top products report.</span></span>
4. <span data-ttu-id="3b02c-111">Adjon meg egy dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="3b02c-111">In the From date field, enter a date.</span></span>
5. <span data-ttu-id="3b02c-112">Adja meg a dátumot a „Záró dátum” mezőben.</span><span class="sxs-lookup"><span data-stu-id="3b02c-112">In the To date field, enter a date.</span></span>
6. <span data-ttu-id="3b02c-113">A Csatorna mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="3b02c-113">In the Channel field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="3b02c-114">A fanézetben válassza ki a „Contoso Retail\Contoso Retail USA\Central\Houston” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3b02c-114">In the tree, select 'Contoso Retail\Contoso Retail USA\Central\Houston'.</span></span>
    * <span data-ttu-id="3b02c-115">Ez megmutatja az alapértelmezett szervezeti hierarchiát a Commerce jelentési célja esetében.</span><span class="sxs-lookup"><span data-stu-id="3b02c-115">This shows the default organization hierarchy for Commerce reporting purpose.</span></span>   <span data-ttu-id="3b02c-116">Ugorjon a Szervezet felügyelete > Szervezetek > Szervezeti hierarchia céljai lehetőségre és válassza ki a Commerce jelentést, majd a Hozzárendelt hierarchiák alatt ellenőrizze a hierarchia nevét, amelyhez be van jelölve az Alapértelmezett oszlop.</span><span class="sxs-lookup"><span data-stu-id="3b02c-116">Go to Organization administration > Organizations > Organization hierarchy purposes and choose Commerce reporting and under Assigned hierarchies, check the hierarchy name for which Default column is checked.</span></span> <span data-ttu-id="3b02c-117">A (feladatrögzítéshez használt) bemutatóadatok részeként észre fogja venni, hogy az Áruházak régiók szerint az alapértelmezett szervezeti hierarchia a jelentési célra.</span><span class="sxs-lookup"><span data-stu-id="3b02c-117">As part of demo data (used for this task recording) you would notice, Stores by Region, is the default organization hierarchy for the reporting purpose.</span></span>     
8. <span data-ttu-id="3b02c-118">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3b02c-118">Click OK.</span></span>
9. <span data-ttu-id="3b02c-119">Válasszon ki egy lehetősége a Nézet mezőben.</span><span class="sxs-lookup"><span data-stu-id="3b02c-119">In the View field, select an option.</span></span>
10. <span data-ttu-id="3b02c-120">Válasszon ki egy lehetőséget a Szerint mezőben.</span><span class="sxs-lookup"><span data-stu-id="3b02c-120">In the By field, select an option.</span></span>
11. <span data-ttu-id="3b02c-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3b02c-121">Click OK.</span></span>

## <a name="launch-reports-from-the-inquiries-and-sales-reports"></a><span data-ttu-id="3b02c-122">Jelentések indítása a lekérdezésekből és az értékesítési jelentésekből</span><span class="sxs-lookup"><span data-stu-id="3b02c-122">Launch reports from the inquiries and sales reports</span></span>
1. <span data-ttu-id="3b02c-123">Ugorjon a Retail és Commerce > Lekérdezések és jelentések > Értékesítési jelentések > Értékesítési kategóriajelentés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3b02c-123">Go to Retail and Commerce > Inquiries and reports > Sales reports > Category sales report.</span></span>
2. <span data-ttu-id="3b02c-124">Adjon meg egy dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="3b02c-124">In the From date field, enter a date.</span></span>
3. <span data-ttu-id="3b02c-125">Adja meg a dátumot a „Záró dátum” mezőben.</span><span class="sxs-lookup"><span data-stu-id="3b02c-125">In the To date field, enter a date.</span></span>
4. <span data-ttu-id="3b02c-126">A Csatorna mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="3b02c-126">In the Channel field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="3b02c-127">A fanézetben válassza ki a „Contoso Retail\Contoso Retail USA\West\Seattle” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3b02c-127">In the tree, select 'Contoso Retail\Contoso Retail USA\West\Seattle'.</span></span>
    * <span data-ttu-id="3b02c-128">Ez megmutatja az alapértelmezett szervezeti hierarchiát a Commerce jelentési célja esetében.</span><span class="sxs-lookup"><span data-stu-id="3b02c-128">This shows the default organization hierarchy for Commerce reporting purpose.</span></span> <span data-ttu-id="3b02c-129">Ugorjon a Szervezet felügyelete > Szervezetek > Szervezeti hierarchia céljai lehetőségre és válassza ki a Commerce jelentést, majd a Hozzárendelt hierarchiák alatt ellenőrizze a hierarchia nevét, amelyhez be van jelölve az Alapértelmezett oszlop.</span><span class="sxs-lookup"><span data-stu-id="3b02c-129">Go to Organization administration > Organizations > Organization hierarchy purposes and choose Commerce reporting and under Assigned hierarchies, check the hierarchy name for which Default column is checked.</span></span> <span data-ttu-id="3b02c-130">A (feladatrögzítéshez használt) bemutatóadatok részeként észre fogja venni, hogy az Áruházak régiók szerint az alapértelmezett szervezeti hierarchia a jelentési célra.</span><span class="sxs-lookup"><span data-stu-id="3b02c-130">As part of demo data (used for this task recording) you would notice, Stores by Region, is the default organization hierarchy for the reporting purpose.</span></span>     
6. <span data-ttu-id="3b02c-131">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3b02c-131">Click OK.</span></span>
7. <span data-ttu-id="3b02c-132">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3b02c-132">Click OK.</span></span>

## <a name="export-an-hq-reports"></a><span data-ttu-id="3b02c-133">Központi jelentések exportálása</span><span class="sxs-lookup"><span data-stu-id="3b02c-133">Export an HQ reports</span></span>
1. <span data-ttu-id="3b02c-134">Ugorjon a Retail és Commerce > Lekérdezések és jelentések > Értékesítési jelentések > Szervezeti kategóriajelentés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3b02c-134">Go to Retail and Commerce > Inquiries and reports > Sales reports > Organization sales report.</span></span>
2. <span data-ttu-id="3b02c-135">Adjon meg egy dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="3b02c-135">In the From date field, enter a date.</span></span>
3. <span data-ttu-id="3b02c-136">Adja meg a dátumot a „Záró dátum” mezőben.</span><span class="sxs-lookup"><span data-stu-id="3b02c-136">In the To date field, enter a date.</span></span>
4. <span data-ttu-id="3b02c-137">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3b02c-137">Click OK.</span></span>
5. <span data-ttu-id="3b02c-138">Kattintson az Exportálás elemre.</span><span class="sxs-lookup"><span data-stu-id="3b02c-138">Click Export.</span></span>
6. <span data-ttu-id="3b02c-139">Kattintson a PDF elemre.</span><span class="sxs-lookup"><span data-stu-id="3b02c-139">Click PDF.</span></span>

