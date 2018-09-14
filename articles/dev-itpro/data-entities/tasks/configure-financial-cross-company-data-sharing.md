--- 
title: "Vállalatközi pénzügyi adatmegosztás konfigurálása"
description: "Ez az eljárás bemutatja, hogy hogyan lehet konfigurálni, engedélyezni, érvényesíteni, és feloldani az ütközéseket a vállalatok közötti adatmegosztás során."
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DataManagementWorkspace, DMFQuickImportExportRnr, DMFExecutionHistoryWorkspace, DMFExecutionHistorySummary, DMFExecutionHistoryEntities,  SysDataSharingConfiguration, SysDataSharingDiscrepencies
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 784a925fa06148cad780b494c88b9a7af1809c9d
ms.contentlocale: hu-hu
ms.lasthandoff: 09/14/2018

---
# <a name="configure-financial-cross-company-data-sharing"></a><span data-ttu-id="daf4d-103">Vállalatközi pénzügyi adatmegosztás konfigurálása</span><span class="sxs-lookup"><span data-stu-id="daf4d-103">Configure financial cross-company data sharing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="daf4d-104">Ez az eljárás bemutatja, hogy hogyan lehet konfigurálni, engedélyezni, érvényesíteni, és feloldani az ütközéseket a vállalatok közötti adatmegosztás során.</span><span class="sxs-lookup"><span data-stu-id="daf4d-104">This procedure shows how to configure, enable, validate, and resolve conflicts when sharing data between companies.</span></span> <span data-ttu-id="daf4d-105">Az USMF vállalatot és a pénzügyi adatmegosztási sablont használja.</span><span class="sxs-lookup"><span data-stu-id="daf4d-105">It uses the USMF company and the Financial data sharing template.</span></span>



<span data-ttu-id="daf4d-106">Ehhez a feladathoz 7.1-es vagy újabb verziós Dynamics AX platform szükséges.</span><span class="sxs-lookup"><span data-stu-id="daf4d-106">This task guide requires Dynamics AX platform 7.1 or later.</span></span>

1. <span data-ttu-id="daf4d-107">Ugrás a Rendszerfelügyelet > Munkaterület > Adatkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="daf4d-107">Go to System administration > Workspaces > Data management.</span></span>
2. <span data-ttu-id="daf4d-108">Kattintson az Importálás gombra.</span><span class="sxs-lookup"><span data-stu-id="daf4d-108">Click Import.</span></span>
3. <span data-ttu-id="daf4d-109">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="daf4d-109">In the Name field, type a value.</span></span>
4. <span data-ttu-id="daf4d-110">A Forrásadatok formátuma mezőben válassza ki a Csomag típusát.</span><span class="sxs-lookup"><span data-stu-id="daf4d-110">In the Source data format field, select the Package type.</span></span>
    * <span data-ttu-id="daf4d-111">Kattintson a Feltöltés hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="daf4d-111">Click Upload.</span></span> <span data-ttu-id="daf4d-112">Keresse meg a Pénzügyi adatmegosztási sablon csomagfájl helyét és válassza ki ezt a fájlt.</span><span class="sxs-lookup"><span data-stu-id="daf4d-112">Navigate to the location of the Financial data sharing template package file and select that file.</span></span>  
5. <span data-ttu-id="daf4d-113">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="daf4d-113">Click Save.</span></span>
6. <span data-ttu-id="daf4d-114">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="daf4d-114">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="daf4d-115">Válassza ki az újonnan létrehozott adatmegosztási házirendet.</span><span class="sxs-lookup"><span data-stu-id="daf4d-115">Select the data sharing policy that was just created.</span></span>  
7. <span data-ttu-id="daf4d-116">Kattintson az Importálás gombra.</span><span class="sxs-lookup"><span data-stu-id="daf4d-116">Click Import.</span></span>
8. <span data-ttu-id="daf4d-117">Kattintson a Bezárás gombra.</span><span class="sxs-lookup"><span data-stu-id="daf4d-117">Click Close.</span></span>
9. <span data-ttu-id="daf4d-118">Frissítse a lapot..</span><span class="sxs-lookup"><span data-stu-id="daf4d-118">Refresh the page.</span></span>
10. <span data-ttu-id="daf4d-119">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="daf4d-119">Close the page.</span></span>
11. <span data-ttu-id="daf4d-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="daf4d-120">Close the page.</span></span>
12. <span data-ttu-id="daf4d-121">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="daf4d-121">Close the page.</span></span>
13. <span data-ttu-id="daf4d-122">Ugorjon a Rendszerfelügyelet > Beállítás > Vállalatközi adatmegosztás konfigurálása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="daf4d-122">Go to System administration > Setup > Configure cross-company data sharing.</span></span>
14. <span data-ttu-id="daf4d-123">A listában keresse meg és jelölje ki a Fizetési napok lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="daf4d-123">In the list, find and select Payment days.</span></span>
15. <span data-ttu-id="daf4d-124">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="daf4d-124">Click Add.</span></span>
16. <span data-ttu-id="daf4d-125">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="daf4d-125">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="daf4d-126">A Vállalat mezőben írja be az „USSI” értéket.</span><span class="sxs-lookup"><span data-stu-id="daf4d-126">In the Company field, type 'USSI'.</span></span>
18. <span data-ttu-id="daf4d-127">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="daf4d-127">Click Add.</span></span>
19. <span data-ttu-id="daf4d-128">A Vállalat mezőben írja be az „USMF” értéket.</span><span class="sxs-lookup"><span data-stu-id="daf4d-128">In the Company field, type 'USMF'.</span></span>
20. <span data-ttu-id="daf4d-129">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="daf4d-129">Click Save.</span></span>
21. <span data-ttu-id="daf4d-130">Kattintson az Engedélyezés gombra.</span><span class="sxs-lookup"><span data-stu-id="daf4d-130">Click Enable.</span></span>
22. <span data-ttu-id="daf4d-131">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="daf4d-131">Click Yes.</span></span>
23. <span data-ttu-id="daf4d-132">Kattintson a Megosztási problémák keresése gombra.</span><span class="sxs-lookup"><span data-stu-id="daf4d-132">Click Find sharing issues.</span></span>
24. <span data-ttu-id="daf4d-133">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="daf4d-133">Click Yes.</span></span>
25. <span data-ttu-id="daf4d-134">Kattintson a Mezőérték frissítése gombra.</span><span class="sxs-lookup"><span data-stu-id="daf4d-134">Click Update field value.</span></span>
26. <span data-ttu-id="daf4d-135">Kattintson az Érték használata az 1-es vállalatból gombra.</span><span class="sxs-lookup"><span data-stu-id="daf4d-135">Click Use value from company 1.</span></span>
27. <span data-ttu-id="daf4d-136">Frissítse a lapot..</span><span class="sxs-lookup"><span data-stu-id="daf4d-136">Refresh the page.</span></span>
28. <span data-ttu-id="daf4d-137">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="daf4d-137">Close the page.</span></span>


