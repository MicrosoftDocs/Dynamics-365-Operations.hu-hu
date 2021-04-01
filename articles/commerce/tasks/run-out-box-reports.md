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
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d3dd941eb4e682e61c8b3d10ef0ccd14239f090c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232713"
---
# <a name="generate-and-run-out-of-box-reports"></a><span data-ttu-id="64553-103">Kulcsrakész jelentések generálása és futtatása</span><span class="sxs-lookup"><span data-stu-id="64553-103">Generate and run out of box reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="64553-104">Használja ezt a feladatútmutatót kulcsrakész jelentések futtatásához a Központban a Commerce-ben található különböző munkaterületekről és Lekérdezésekből és Értékesítési jelentésekből.</span><span class="sxs-lookup"><span data-stu-id="64553-104">Use this task guide to run out of box reports in Headquarters from different workspaces and Inquiries & Sales reports located in Commerce.</span></span>

<span data-ttu-id="64553-105">A bemutató adatsor típusa, melyet a vállalat használt az útmutató készítéséhez, az USRT.</span><span class="sxs-lookup"><span data-stu-id="64553-105">The demo data company used to create this recording is USRT.</span></span> <span data-ttu-id="64553-106">Ez a felvétel a Rendszeradminisztrátor szerepkör számára készült.</span><span class="sxs-lookup"><span data-stu-id="64553-106">This recording is intended for the System administrator role.</span></span>

## <a name="launch-reports-from-workspaces"></a><span data-ttu-id="64553-107">Indítsa el a jelentéseket a munkaterületekről</span><span class="sxs-lookup"><span data-stu-id="64553-107">Launch reports from workspaces</span></span>
1. <span data-ttu-id="64553-108">Ugorjon a Retail és Commerce > Termékek és kategóriák > Kategóriák és termékmenedzsment lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="64553-108">Go to Retail and Commerce > Products and categories > Category and product management.</span></span>
2. <span data-ttu-id="64553-109">Kattintson a nyílra a Jelentések szakasz kibontásához vagy összecsukásához.</span><span class="sxs-lookup"><span data-stu-id="64553-109">Click the arrow to expand or collapse the Reports section.</span></span>
3. <span data-ttu-id="64553-110">Kattintson a Vezető termékek jelentései lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="64553-110">Click Top products report.</span></span>
4. <span data-ttu-id="64553-111">Adjon meg egy dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="64553-111">In the From date field, enter a date.</span></span>
5. <span data-ttu-id="64553-112">Adja meg a dátumot a „Záró dátum” mezőben.</span><span class="sxs-lookup"><span data-stu-id="64553-112">In the To date field, enter a date.</span></span>
6. <span data-ttu-id="64553-113">A Csatorna mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="64553-113">In the Channel field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="64553-114">A fanézetben válassza ki a „Contoso Retail\Contoso Retail USA\Central\Houston” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="64553-114">In the tree, select 'Contoso Retail\Contoso Retail USA\Central\Houston'.</span></span>
    * <span data-ttu-id="64553-115">Ez megmutatja az alapértelmezett szervezeti hierarchiát a Commerce jelentési célja esetében.</span><span class="sxs-lookup"><span data-stu-id="64553-115">This shows the default organization hierarchy for Commerce reporting purpose.</span></span>   <span data-ttu-id="64553-116">Ugorjon a Szervezet felügyelete > Szervezetek > Szervezeti hierarchia céljai lehetőségre és válassza ki a Commerce jelentést, majd a Hozzárendelt hierarchiák alatt ellenőrizze a hierarchia nevét, amelyhez be van jelölve az Alapértelmezett oszlop.</span><span class="sxs-lookup"><span data-stu-id="64553-116">Go to Organization administration > Organizations > Organization hierarchy purposes and choose Commerce reporting and under Assigned hierarchies, check the hierarchy name for which Default column is checked.</span></span> <span data-ttu-id="64553-117">A (feladatrögzítéshez használt) bemutatóadatok részeként észre fogja venni, hogy az Áruházak régiók szerint az alapértelmezett szervezeti hierarchia a jelentési célra.</span><span class="sxs-lookup"><span data-stu-id="64553-117">As part of demo data (used for this task recording) you would notice, Stores by Region, is the default organization hierarchy for the reporting purpose.</span></span>     
8. <span data-ttu-id="64553-118">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="64553-118">Click OK.</span></span>
9. <span data-ttu-id="64553-119">Válasszon ki egy lehetősége a Nézet mezőben.</span><span class="sxs-lookup"><span data-stu-id="64553-119">In the View field, select an option.</span></span>
10. <span data-ttu-id="64553-120">Válasszon ki egy lehetőséget a Szerint mezőben.</span><span class="sxs-lookup"><span data-stu-id="64553-120">In the By field, select an option.</span></span>
11. <span data-ttu-id="64553-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="64553-121">Click OK.</span></span>

## <a name="launch-reports-from-the-inquiries-and-sales-reports"></a><span data-ttu-id="64553-122">Jelentések indítása a lekérdezésekből és az értékesítési jelentésekből</span><span class="sxs-lookup"><span data-stu-id="64553-122">Launch reports from the inquiries and sales reports</span></span>
1. <span data-ttu-id="64553-123">Ugorjon a Retail és Commerce > Lekérdezések és jelentések > Értékesítési jelentések > Értékesítési kategóriajelentés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="64553-123">Go to Retail and Commerce > Inquiries and reports > Sales reports > Category sales report.</span></span>
2. <span data-ttu-id="64553-124">Adjon meg egy dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="64553-124">In the From date field, enter a date.</span></span>
3. <span data-ttu-id="64553-125">Adja meg a dátumot a „Záró dátum” mezőben.</span><span class="sxs-lookup"><span data-stu-id="64553-125">In the To date field, enter a date.</span></span>
4. <span data-ttu-id="64553-126">A Csatorna mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="64553-126">In the Channel field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="64553-127">A fanézetben válassza ki a „Contoso Retail\Contoso Retail USA\West\Seattle” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="64553-127">In the tree, select 'Contoso Retail\Contoso Retail USA\West\Seattle'.</span></span>
    * <span data-ttu-id="64553-128">Ez megmutatja az alapértelmezett szervezeti hierarchiát a Commerce jelentési célja esetében.</span><span class="sxs-lookup"><span data-stu-id="64553-128">This shows the default organization hierarchy for Commerce reporting purpose.</span></span> <span data-ttu-id="64553-129">Ugorjon a Szervezet felügyelete > Szervezetek > Szervezeti hierarchia céljai lehetőségre és válassza ki a Commerce jelentést, majd a Hozzárendelt hierarchiák alatt ellenőrizze a hierarchia nevét, amelyhez be van jelölve az Alapértelmezett oszlop.</span><span class="sxs-lookup"><span data-stu-id="64553-129">Go to Organization administration > Organizations > Organization hierarchy purposes and choose Commerce reporting and under Assigned hierarchies, check the hierarchy name for which Default column is checked.</span></span> <span data-ttu-id="64553-130">A (feladatrögzítéshez használt) bemutatóadatok részeként észre fogja venni, hogy az Áruházak régiók szerint az alapértelmezett szervezeti hierarchia a jelentési célra.</span><span class="sxs-lookup"><span data-stu-id="64553-130">As part of demo data (used for this task recording) you would notice, Stores by Region, is the default organization hierarchy for the reporting purpose.</span></span>     
6. <span data-ttu-id="64553-131">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="64553-131">Click OK.</span></span>
7. <span data-ttu-id="64553-132">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="64553-132">Click OK.</span></span>

## <a name="export-an-hq-reports"></a><span data-ttu-id="64553-133">Központi jelentések exportálása</span><span class="sxs-lookup"><span data-stu-id="64553-133">Export an HQ reports</span></span>
1. <span data-ttu-id="64553-134">Ugorjon a Retail és Commerce > Lekérdezések és jelentések > Értékesítési jelentések > Szervezeti kategóriajelentés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="64553-134">Go to Retail and Commerce > Inquiries and reports > Sales reports > Organization sales report.</span></span>
2. <span data-ttu-id="64553-135">Adjon meg egy dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="64553-135">In the From date field, enter a date.</span></span>
3. <span data-ttu-id="64553-136">Adja meg a dátumot a „Záró dátum” mezőben.</span><span class="sxs-lookup"><span data-stu-id="64553-136">In the To date field, enter a date.</span></span>
4. <span data-ttu-id="64553-137">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="64553-137">Click OK.</span></span>
5. <span data-ttu-id="64553-138">Kattintson az Exportálás elemre.</span><span class="sxs-lookup"><span data-stu-id="64553-138">Click Export.</span></span>
6. <span data-ttu-id="64553-139">Kattintson a PDF elemre.</span><span class="sxs-lookup"><span data-stu-id="64553-139">Click PDF.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]