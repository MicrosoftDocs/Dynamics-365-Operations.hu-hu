---
title: Vállalatközi pénzügyi adatmegosztás konfigurálása
description: Ez az eljárás bemutatja, hogy hogyan lehet konfigurálni, engedélyezni, érvényesíteni, és feloldani az ütközéseket a vállalatok közötti adatmegosztás során.
author: aprilolson
manager: AnnBe
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DataManagementWorkspace, DMFQuickImportExportRnr, DMFExecutionHistoryWorkspace, DMFExecutionHistorySummary, DMFExecutionHistoryEntities,  SysDataSharingConfiguration, SysDataSharingDiscrepencies
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 167f43224591462a4db42d041487ff8f66b02cd9
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561074"
---
# <a name="configure-financial-cross-company-data-sharing"></a><span data-ttu-id="eb3ae-103">Vállalatközi pénzügyi adatmegosztás konfigurálása</span><span class="sxs-lookup"><span data-stu-id="eb3ae-103">Configure financial cross-company data sharing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="eb3ae-104">Ez az eljárás bemutatja, hogy hogyan lehet konfigurálni, engedélyezni, érvényesíteni, és feloldani az ütközéseket a vállalatok közötti adatmegosztás során.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-104">This procedure shows how to configure, enable, validate, and resolve conflicts when sharing data between companies.</span></span> <span data-ttu-id="eb3ae-105">Az USMF vállalatot és a pénzügyi adatmegosztási sablont használja.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-105">It uses the USMF company and the Financial data sharing template.</span></span>

<span data-ttu-id="eb3ae-106">Ehhez a feladathoz 7.1-es vagy újabb verziós Dynamics AX platform szükséges.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-106">This task guide requires Dynamics AX platform 7.1 or later.</span></span>

1. <span data-ttu-id="eb3ae-107">Ugorjon a **Navigációs lap > Modulok > Rendszerfelügyelet > Munkaterületek > Adatkezelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-107">Go to **Navigation pane > Modules > System administration > Workspaces > Data management**.</span></span>
2. <span data-ttu-id="eb3ae-108">Kattintson az **Importálás** gombra.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-108">Click **Import**.</span></span>
3. <span data-ttu-id="eb3ae-109">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-109">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="eb3ae-110">A **Forrásadatok formátuma** mezőben válassza ki a „Csomag” típusát</span><span class="sxs-lookup"><span data-stu-id="eb3ae-110">In the **Source data format** field, select the 'Package' type.</span></span> <span data-ttu-id="eb3ae-111">Kattintson a **Feltöltés** hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-111">Click **Upload**.</span></span> <span data-ttu-id="eb3ae-112">Keresse meg a Pénzügyi adatmegosztási sablon csomagfájl helyét és válassza ki ezt a fájlt.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-112">Navigate to the location of the Financial data sharing template package file and select that file.</span></span>
5. <span data-ttu-id="eb3ae-113">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-113">Click **Save**.</span></span>
6. <span data-ttu-id="eb3ae-114">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-114">In the list, mark the selected row.</span></span> <span data-ttu-id="eb3ae-115">Válassza ki az újonnan létrehozott adatmegosztási házirendet.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-115">Select the data sharing policy that was just created.</span></span>  
7. <span data-ttu-id="eb3ae-116">Kattintson az **Importálás** gombra.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-116">Click **Import**.</span></span>
8. <span data-ttu-id="eb3ae-117">Kattintson a **Bezárás** gombra.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-117">Click **Close**.</span></span>
9. <span data-ttu-id="eb3ae-118">Frissítse a lapot..</span><span class="sxs-lookup"><span data-stu-id="eb3ae-118">Refresh the page.</span></span>
10. <span data-ttu-id="eb3ae-119">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-119">Close the page.</span></span>
11. <span data-ttu-id="eb3ae-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-120">Close the page.</span></span>
12. <span data-ttu-id="eb3ae-121">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-121">Close the page.</span></span>
13. <span data-ttu-id="eb3ae-122">Ugorjon a **Navigációs panel > Modulok > Rendszerfelügyelet > Beállítás > Vállalatközi adatmegosztás konfigurálása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-122">Go to **Navigation pane > Modules > System administration > Setup > Configure cross-company data sharing**.</span></span>
14. <span data-ttu-id="eb3ae-123">A listában keresse meg és jelölje ki a **Fizetési napok** lehetőséget</span><span class="sxs-lookup"><span data-stu-id="eb3ae-123">In the list, find and select **Payment days**.</span></span>
15. <span data-ttu-id="eb3ae-124">Kattintson a **Hozzáadás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-124">Click **Add**.</span></span>
16. <span data-ttu-id="eb3ae-125">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-125">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="eb3ae-126">A **Vállalat** mezőben írja be az „USSI” értéket.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-126">In the **Company** field, type 'USSI'.</span></span>
18. <span data-ttu-id="eb3ae-127">Kattintson a **Hozzáadás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-127">Click **Add**.</span></span>
19. <span data-ttu-id="eb3ae-128">A **Vállalat** mezőben írja be az „USMF” értéket.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-128">In the **Company** field, type 'USMF'.</span></span>
20. <span data-ttu-id="eb3ae-129">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-129">Click **Save**.</span></span>
21. <span data-ttu-id="eb3ae-130">Kattintson az **Engedélyezés** gombra.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-130">Click **Enable**.</span></span>
22. <span data-ttu-id="eb3ae-131">Kattintson az **Igen** gombra.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-131">Click **Yes**.</span></span>
23. <span data-ttu-id="eb3ae-132">Kattintson a **Megosztási problémák keresése** gombra.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-132">Click **Find sharing issues**.</span></span>
24. <span data-ttu-id="eb3ae-133">Kattintson az **Igen** gombra.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-133">Click **Yes**.</span></span>
25. <span data-ttu-id="eb3ae-134">Kattintson a **Mezőérték frissítése** gombra.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-134">Click **Update field value**.</span></span>
26. <span data-ttu-id="eb3ae-135">Kattintson az **Érték használata az 1-es** vállalatból gombra.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-135">Click **Use value from company 1**.</span></span>
27. <span data-ttu-id="eb3ae-136">Frissítse a lapot..</span><span class="sxs-lookup"><span data-stu-id="eb3ae-136">Refresh the page.</span></span>
28. <span data-ttu-id="eb3ae-137">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="eb3ae-137">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]