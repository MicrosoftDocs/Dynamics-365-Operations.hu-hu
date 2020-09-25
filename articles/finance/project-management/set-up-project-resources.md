---
title: Projekterőforrások beállítása
description: Ez a témakör a projekterőforrások beállításával vagy kérésével kapcsolatban tartalmaz tájékoztatást.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c882e23794e3937f85b3e73774b36deaf28ac3ed
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760568"
---
# <a name="set-up-project-resources"></a><span data-ttu-id="6e042-103">Projekterőforrások beállítása</span><span class="sxs-lookup"><span data-stu-id="6e042-103">Set up project resources</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6e042-104">Be kell állítania egy új naptárt és hozzá kell rendelnie egy alkalmazottat vagy egy dolgozót.</span><span class="sxs-lookup"><span data-stu-id="6e042-104">You must set up a calendar and associate it with an employee or a worker.</span></span> <span data-ttu-id="6e042-105">A naptár a projekthez fenntartott erőforrások munkaidejének és a projektek ütemezésére lesz használva.</span><span class="sxs-lookup"><span data-stu-id="6e042-105">The calendar is used to schedule the project and the working time of the resources that are reserved for the project.</span></span> <span data-ttu-id="6e042-106">A naptár beállítása alatt a projektvezető az erőforrás optimalizálásának részeként elvégezheti az erőforrás-kiegyenlítést.</span><span class="sxs-lookup"><span data-stu-id="6e042-106">During calendar setup, project managers can do resource leveling as part of resource optimization.</span></span> <span data-ttu-id="6e042-107">A naptár-ütemezés alapján korlátozások helyezhetők az erőforrásokra.</span><span class="sxs-lookup"><span data-stu-id="6e042-107">Based on the calendar schedule, restrictions can be put on resources.</span></span> <span data-ttu-id="6e042-108">Beállíthat egy naptárat a **Naptárak** oldalon.</span><span class="sxs-lookup"><span data-stu-id="6e042-108">You can set up a calendar on the **Calendars** page.</span></span>

<span data-ttu-id="6e042-109">Dolgozó projekt-erőforrásként való beállításakor választhat a vállalatnál dolgozó dolgozók közül, amelyhez beállítja az erőforrásokat.</span><span class="sxs-lookup"><span data-stu-id="6e042-109">When you set up a worker as a project resource, you can select from workers who work in the company that you're setting up resources for.</span></span> <span data-ttu-id="6e042-110">Másik megoldásként a szervezet más cégeinél dolgozó dolgozókat is választhat.</span><span class="sxs-lookup"><span data-stu-id="6e042-110">Alternatively, you can select workers from other companies in your organization.</span></span> <span data-ttu-id="6e042-111">Ezeket a dolgozókat vállalatközi erőforrásoknak nevezik.</span><span class="sxs-lookup"><span data-stu-id="6e042-111">These workers are known as intercompany resources.</span></span>

<span data-ttu-id="6e042-112">Az alábbi eljárások bemutatják, hogyan állítható be egy dolgozó projekterőforrásként a vállalaton belül, és hogyan állítható be egy vállalatközi projekterőforrás.</span><span class="sxs-lookup"><span data-stu-id="6e042-112">The following procedures explain how to set up a worker as a project resource in your company and how to set up an intercompany project resource.</span></span>

## <a name="set-up-a-worker-as-a-project-resource"></a><span data-ttu-id="6e042-113">Dolgozó beállítása, mint projekterőforrás</span><span class="sxs-lookup"><span data-stu-id="6e042-113">Set up a worker as a project resource</span></span>

1. <span data-ttu-id="6e042-114">A **Dolgozók** oldalon, a **Dolgozók** listában jelölje ki azt a dolgozót, akit projekterőforrásként szeretne hozzáadni, majd nyissa meg a dolgozó rekordot.</span><span class="sxs-lookup"><span data-stu-id="6e042-114">On the **Workers** page, in the **Workers** list, select the worker that you're adding as a project resource, and open the worker record.</span></span>
2. <span data-ttu-id="6e042-115">A Műveleti ablaktáblán válassza a **Projekt** &gt; **Beállítás** &gt; **Projektbeállítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6e042-115">On the Action Pane, select **Project** &gt; **Setup** &gt; **Project setup**.</span></span>
3. <span data-ttu-id="6e042-116">Válasszon ki egy naptárt, és zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6e042-116">Select a calendar, and then close the page.</span></span>

<span data-ttu-id="6e042-117">Meghatározhat alapértelmezett projekteket az erőforráshoz, mint előzetes hozzárendelés típus.</span><span class="sxs-lookup"><span data-stu-id="6e042-117">You can also specify default projects for a resource as a type of pre-assignment.</span></span> <span data-ttu-id="6e042-118">Az előzetes hozzárendelések akkor használhatóak, ha az erőforrás-kezelő vagy a projektkezelő előre tudja, hogy az erőforrás milyen projekteken fog dolgozni.</span><span class="sxs-lookup"><span data-stu-id="6e042-118">Pre-assignments can be used when the resource manager or project manager knows which projects the resource will be working on in advance.</span></span> <span data-ttu-id="6e042-119">Az előzetes hozzárendelések alapulhatnak a projekttámogató vagy a vevő kérelmein.</span><span class="sxs-lookup"><span data-stu-id="6e042-119">Pre-assignments can also be based on the request of a project sponsor or customer.</span></span> <span data-ttu-id="6e042-120">A projekt előzetes hozzárendeléséhez a **Projektek hozzárendelése** oldalon a **Projektek** lapon a **Fennmaradó projektet** listáján jelölje ki a megfelelő projektet.</span><span class="sxs-lookup"><span data-stu-id="6e042-120">To pre-assign a project, on the **Assign projects** page, on the **Projects** tab, in the **Remaining projects** list, select the appropriate project.</span></span>

## <a name="set-up-an-intercompany-resource"></a><span data-ttu-id="6e042-121">Egy vállalatközi erőforrás beállítása</span><span class="sxs-lookup"><span data-stu-id="6e042-121">Set up an intercompany resource</span></span>

<span data-ttu-id="6e042-122">A munkavállaló vállalatközi erőforrásként való beállításakor el kell végezni a beállítást a kölcsönbe adó és a kölcsönbe vevő vállalatnál.</span><span class="sxs-lookup"><span data-stu-id="6e042-122">When you set up a worker as an intercompany resource, you must complete the setup in both the lending company and the borrowing company.</span></span>

### <a name="in-the-lending-company"></a><span data-ttu-id="6e042-123">A kölcsönbe adó vállalatnál</span><span class="sxs-lookup"><span data-stu-id="6e042-123">In the lending company</span></span>

1. <span data-ttu-id="6e042-124">A Finance rendszerben ellenőrizze, hogy a kölcsönbe adó vállalat ki legyen jelölve, majd végezze el az előző szakaszban leírt eljárást: „Dolgozó beállítása projekterőforrásként”.</span><span class="sxs-lookup"><span data-stu-id="6e042-124">In Finance, verify that the lending company is selected, and then complete the procedure in the previous section, "Set up a worker as a project resource."</span></span>
2. <span data-ttu-id="6e042-125">A **Vállalatközi könyvelés** oldalon válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6e042-125">On the **Intercompany accounting** page, select **New**.</span></span>
3. <span data-ttu-id="6e042-126">A **Jogi személy azonosítója** mezőben válassza ki a kölcsönbe adó vállalatot.</span><span class="sxs-lookup"><span data-stu-id="6e042-126">In the **Legal entity ID** field, select the lending company.</span></span> <span data-ttu-id="6e042-127">Töltse ki a többi megfelelő mezőt, és válassza a **Mentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="6e042-127">Fill in the remaining fields as appropriate, and then select **Save**.</span></span>
4. <span data-ttu-id="6e042-128">A **Transzferár** oldalon válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6e042-128">On the **Transfer price** page, select **New**.</span></span>
5. <span data-ttu-id="6e042-129">A **Kölcsönbe vevő jogi személy** mezőben válassza ki a megfelelő vállalatot.</span><span class="sxs-lookup"><span data-stu-id="6e042-129">In the **Borrowing legal entity** field, select the appropriate company.</span></span>
6. <span data-ttu-id="6e042-130">Ha a kölcsönbe vevő vállalat számára csak az e szakasz elején létrehozott erőforrást szeretné kölcsönbe adni, az **Erőforrás** mezőben válassza ki a létrehozott erőforrás nevét.</span><span class="sxs-lookup"><span data-stu-id="6e042-130">To lend the borrowing company only the resource that you created at the beginning of this section, in the **Resource** field, select the name of the resource that you created.</span></span> <span data-ttu-id="6e042-131">Ha a kölcsönbe adó vállalat összes erőforrását elérhetővé szeretné tenni a kölcsönbe vevő vállalat számára, hagyja üresen az **Erőforrás** mezőt.</span><span class="sxs-lookup"><span data-stu-id="6e042-131">To make all resources in the lending company available to the borrowing company, leave the **Resource** field blank.</span></span>
7. <span data-ttu-id="6e042-132">A **Projektvezetési és könyvelési paraméterek** oldalon a **Vállalatközi** lapon állítsa a **Vállalatközi erőforrás-ütemezés és időnyilvántartások engedélyezése** mező értékét az **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="6e042-132">On the **Project management and accounting parameters** page, on the **Intercompany** tab, set the **Enable intercompany resource scheduling and timesheets** option to **Yes**.</span></span>

### <a name="in-the-borrowing-company"></a><span data-ttu-id="6e042-133">A kölcsönbe vevő vállalatnál</span><span class="sxs-lookup"><span data-stu-id="6e042-133">In the borrowing company</span></span>

- <span data-ttu-id="6e042-134">Az **Erőforrások listája** oldalon a keresési szűrőbe írja be a nevét a kölcsönbe adó vállalathoz létrehozott erőforrásnak annak az ellenőrzéséhez, hogy az erőforrás szerepel a kölcsönbe vevő vállalat erőforráslistájában.</span><span class="sxs-lookup"><span data-stu-id="6e042-134">On the **Resources list** page, in the search filter, enter the name of the resource that you created for the lending company, to verify that the name is included in the resource list for the borrowing company.</span></span>

## <a name="request-project-resources"></a><span data-ttu-id="6e042-135">Projekterőforrás kérése</span><span class="sxs-lookup"><span data-stu-id="6e042-135">Request project resources</span></span>
<span data-ttu-id="6e042-136">A projekterőforrás-ütemezési szolgáltatás csak a személyzettel ellátott erőforrások vagy előjegyzések elosztását engedi az erőforrás-kezelőknek.</span><span class="sxs-lookup"><span data-stu-id="6e042-136">The functionality for project resource scheduling only lets resource managers distribute staffed resources on engagements or projects.</span></span> <span data-ttu-id="6e042-137">A funkció engedélyezéséhez végezze el a következő feladatokat, vagy győződjön meg arról, hogy befejeződtek:</span><span class="sxs-lookup"><span data-stu-id="6e042-137">To enable this functionality, complete the following tasks, or verify that they have been completed:</span></span>

- <span data-ttu-id="6e042-138">Számsorozatok beállítása.</span><span class="sxs-lookup"><span data-stu-id="6e042-138">Set up number sequences.</span></span>
- <span data-ttu-id="6e042-139">Munkafolyamatok beállítása a projektvezetéshez és a könyveléshez.</span><span class="sxs-lookup"><span data-stu-id="6e042-139">Set up project management and accounting workflows.</span></span>
- <span data-ttu-id="6e042-140">Engedélyezze az erőforrás-kérelem munkafolyamatokat.</span><span class="sxs-lookup"><span data-stu-id="6e042-140">Enable resource request workflows.</span></span>

<span data-ttu-id="6e042-141">Miután az előző feladatok befejeződtek, elvégezheti az alábbi feladatokat, szükség szerint:</span><span class="sxs-lookup"><span data-stu-id="6e042-141">After the preceding tasks have been completed, you can complete the following tasks as you require:</span></span>

- <span data-ttu-id="6e042-142">Erőforrás-igénylés létrehozása ideiglenesen lefoglalt személyzettel ellátott erőforráshoz.</span><span class="sxs-lookup"><span data-stu-id="6e042-142">Create a resource request from a soft-booked staffed resource.</span></span>
- <span data-ttu-id="6e042-143">Erőforrás-kérelmek figyelése.</span><span class="sxs-lookup"><span data-stu-id="6e042-143">Monitor resource requests.</span></span>
- <span data-ttu-id="6e042-144">Erőforrás-kérelmek teljesítése.</span><span class="sxs-lookup"><span data-stu-id="6e042-144">Fulfill resource requests.</span></span>
- <span data-ttu-id="6e042-145">Személyzettel ellátott erőforrás kérése WBS-től.</span><span class="sxs-lookup"><span data-stu-id="6e042-145">Request a staffed resource from a WBS.</span></span>
- <span data-ttu-id="6e042-146">Erőforrások foglalása egy projekthez személyzettel ellátott erőforrások iránti kérelem nélkül.</span><span class="sxs-lookup"><span data-stu-id="6e042-146">Book resources to a project without having a request for a staffed resource.</span></span>
