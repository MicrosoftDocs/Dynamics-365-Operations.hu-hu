---
title: Szabadság vásárlására és eladására irányuló kérelem munkafolyamatának létrehozása
description: Hozzon létre egy szabadság vásárlására és eladására irányuló kérelem munkafolyamatot, a szabadságkérelmeket egységes vételéhez és eladásához a Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
manager: tfehr
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 16260c66c2e92fb06664a8f20a5fc3ed4a964609
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5468131"
---
# <a name="create-a-buy-and-sell-leave-request-workflow"></a><span data-ttu-id="b2a08-103">Szabadság vásárlására és eladására irányuló kérelem munkafolyamatának létrehozása</span><span class="sxs-lookup"><span data-stu-id="b2a08-103">Create a buy and sell leave request workflow</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="b2a08-104">Létrehozhat egy munkafolyamatot a Dynamics 365 Human Resources alkalmazásban a szabadságkérelmek egységes vételéhez és eladásához.</span><span class="sxs-lookup"><span data-stu-id="b2a08-104">You can create a workflow in Dynamics 365 Human Resources to consistently manage your buy and sell leave requests.</span></span> <span data-ttu-id="b2a08-105">A **Szabadság vásárlása és eladása** munkafolyamat lehetővé teszi:</span><span class="sxs-lookup"><span data-stu-id="b2a08-105">A **Buy and sell leave** workflow lets you:</span></span>

- <span data-ttu-id="b2a08-106">Feladatok definiálását</span><span class="sxs-lookup"><span data-stu-id="b2a08-106">Define tasks</span></span>
- <span data-ttu-id="b2a08-107">Annak meghatározását, hogy kinek kell végrehajtania a feladatokat</span><span class="sxs-lookup"><span data-stu-id="b2a08-107">Determine who must complete the tasks</span></span>
- <span data-ttu-id="b2a08-108">Annak megadását, hogy ki hagyhatja jóvá vagy utasíthatja el a kérelmeket</span><span class="sxs-lookup"><span data-stu-id="b2a08-108">Specify who can approve or reject requests</span></span>

## <a name="create-a-buy-and-sell-leave-request-workflow"></a><span data-ttu-id="b2a08-109">Szabadság vásárlására és eladására irányuló kérelem munkafolyamatának létrehozása</span><span class="sxs-lookup"><span data-stu-id="b2a08-109">Create a buy and sell leave request workflow</span></span>

1. <span data-ttu-id="b2a08-110">A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.</span><span class="sxs-lookup"><span data-stu-id="b2a08-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="b2a08-111">A **Beállítás** alatt válassza az **Emberi erőforrás munkafolyamatok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b2a08-111">Under **Setup**, select **Human resource workflows**.</span></span>

3. <span data-ttu-id="b2a08-112">Válassza az **Új** lehetőséget, majd válassza a **Szabadságkérelem vásárlása és eladása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b2a08-112">Select **New**, and then select **Buy and sell leave request**.</span></span> 

4. <span data-ttu-id="b2a08-113">Amikor megjelenik a **Megnyitja ezt a fájlt?** üzenetmező, vákasza a **Megnyitás** lehetőséget, és jelentkezzen be a vállalati hitelesítő adataival.</span><span class="sxs-lookup"><span data-stu-id="b2a08-113">When the **Open this file?** message box appears, select **Open** and sign in with your company credentials.</span></span>

5. <span data-ttu-id="b2a08-114">A munkafolyamat-szerkesztővel hozzon létre egy munkafolyamatot a szabadságkérelmekhez.</span><span class="sxs-lookup"><span data-stu-id="b2a08-114">Use the workflow editor to create a workflow for your leave requests.</span></span> <span data-ttu-id="b2a08-115">További tájékoztatás a munkafolyamatok használatáról: [Munkafolyamatok létrehozása – áttekintés](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)</span><span class="sxs-lookup"><span data-stu-id="b2a08-115">For more information about working with workflows, see [Create workflows overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)</span></span>

## <a name="leave-and-absence-request-workflow-data-elements"></a><span data-ttu-id="b2a08-116">Szabadság- és távolléti kérelem munkafolyamatának adatelemei</span><span class="sxs-lookup"><span data-stu-id="b2a08-116">Leave and absence request workflow data elements</span></span>

<span data-ttu-id="b2a08-117">A következő adatelemek segítségével feltételes vagy automatikus jóváhagyásokat hozhat létre a munkafolyamatokban a szabadság vásárlásával és eladásával kapcsolatos kérelmekhez:</span><span class="sxs-lookup"><span data-stu-id="b2a08-117">You can use the following data elements to create conditional or automatic approvals in workflows for buy and sell leave requests:</span></span>

- <span data-ttu-id="b2a08-118">**Összeg**</span><span class="sxs-lookup"><span data-stu-id="b2a08-118">**Amount**</span></span>
- <span data-ttu-id="b2a08-119">**Szabadság vásárlásával és eladásával kapcsolatos irányelv**</span><span class="sxs-lookup"><span data-stu-id="b2a08-119">**Buy and sell leave policy**</span></span>
- <span data-ttu-id="b2a08-120">**Cég**</span><span class="sxs-lookup"><span data-stu-id="b2a08-120">**Company**</span></span>
- <span data-ttu-id="b2a08-121">**Létrehozta**</span><span class="sxs-lookup"><span data-stu-id="b2a08-121">**Created by**</span></span>
- <span data-ttu-id="b2a08-122">**Létrehozás dátuma és időpontja**</span><span class="sxs-lookup"><span data-stu-id="b2a08-122">**Created date and time**</span></span>
- <span data-ttu-id="b2a08-123">**Befejezés**</span><span class="sxs-lookup"><span data-stu-id="b2a08-123">**End date**</span></span>
- <span data-ttu-id="b2a08-124">**Szabadság típusa**</span><span class="sxs-lookup"><span data-stu-id="b2a08-124">**Leave type**</span></span>
- <span data-ttu-id="b2a08-125">**Módosította:**</span><span class="sxs-lookup"><span data-stu-id="b2a08-125">**Modified by**</span></span>
- <span data-ttu-id="b2a08-126">**Módosítás dátuma és időpontja**</span><span class="sxs-lookup"><span data-stu-id="b2a08-126">**Modified date and time**</span></span>
- <span data-ttu-id="b2a08-127">**Kérelemazonosító**</span><span class="sxs-lookup"><span data-stu-id="b2a08-127">**Request ID**</span></span>
- <span data-ttu-id="b2a08-128">**Kezdés dátuma**</span><span class="sxs-lookup"><span data-stu-id="b2a08-128">**Start date**</span></span>
- <span data-ttu-id="b2a08-129">**Állapot**</span><span class="sxs-lookup"><span data-stu-id="b2a08-129">**Status**</span></span> 
- <span data-ttu-id="b2a08-130">**Küldés dátuma**</span><span class="sxs-lookup"><span data-stu-id="b2a08-130">**Submission date**</span></span>
- <span data-ttu-id="b2a08-131">**Beküldte:**</span><span class="sxs-lookup"><span data-stu-id="b2a08-131">**Submitted by**</span></span>
- <span data-ttu-id="b2a08-132">**Elküldve az Emberi erőforrások által**</span><span class="sxs-lookup"><span data-stu-id="b2a08-132">**Submitted by Human resources**</span></span>
- <span data-ttu-id="b2a08-133">**Beküldve a vezető által**</span><span class="sxs-lookup"><span data-stu-id="b2a08-133">**Submitted by Manager**</span></span>
- <span data-ttu-id="b2a08-134">**Beküldve a következő nevében**</span><span class="sxs-lookup"><span data-stu-id="b2a08-134">**Submitted on behalf**</span></span>
- <span data-ttu-id="b2a08-135">**Dolgozó**</span><span class="sxs-lookup"><span data-stu-id="b2a08-135">**Worker**</span></span>

## <a name="workflow-examples"></a><span data-ttu-id="b2a08-136">Munkafolyamat-példák</span><span class="sxs-lookup"><span data-stu-id="b2a08-136">Workflow examples</span></span>

<span data-ttu-id="b2a08-137">Ezek a példák azt mutatják be, hogyan lehet különböző típusú munkafolyamat-feltételeket létrehozni a következő adatelemek segítségével:</span><span class="sxs-lookup"><span data-stu-id="b2a08-137">These examples show how you can create different types of workflow conditions by using these data elements:</span></span>

- <span data-ttu-id="b2a08-138">Az **Emberi erőforrások által elküldött** és a **Vezető által beküldött** elemek használata egy automatikus műveletben a szabadságkérelmek eladásának és vételének automatikus jóváhagyásához, amelyeket ezek a szerepkörök küldtek be a munkavállalók nevében.</span><span class="sxs-lookup"><span data-stu-id="b2a08-138">Use **Submitted by Human resources** and **Submitted by manager** in an automatic action to automatically approve buy and sell leave requests that these roles submit on behalf of employees.</span></span> <span data-ttu-id="b2a08-139">Az automatikus műveletekkel kapcsolatos további tudnivalókat lásd: [Jóváhagyási folyamatok konfigurálása munkafolyamatokban](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).</span><span class="sxs-lookup"><span data-stu-id="b2a08-139">For more information about automatic actions, see [Configure approval processes in a workflow](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).</span></span>

- <span data-ttu-id="b2a08-140">A **Szabadságtípus** használata feltételes állításban vagy automatikus műveletben, annak meghatározásához, hogy a munkafolyamat hogyan irányítsa át az egyes szabadságtípusokat tartalmazó szabadságkérelmeket.</span><span class="sxs-lookup"><span data-stu-id="b2a08-140">Use **Leave type** in a conditional statement or automatic action to control how the workflow routes requests with certain leave types.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2a08-141">Lásd még</span><span class="sxs-lookup"><span data-stu-id="b2a08-141">See also</span></span>

[<span data-ttu-id="b2a08-142">Szabadság és távollét áttekintése</span><span class="sxs-lookup"><span data-stu-id="b2a08-142">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)<br>
[<span data-ttu-id="b2a08-143">Szabadság vásárlásával és eladásával kapcsolatos irányelv kezelése</span><span class="sxs-lookup"><span data-stu-id="b2a08-143">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]