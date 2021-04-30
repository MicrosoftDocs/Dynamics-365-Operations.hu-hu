---
title: Szabadságkérelem munkafolyamat létrehozása
description: Hozzon létre egy szabadság- és távollétkérelem munkafolyamatot, a szabadságkérelmeket egységes kezeléséhez a Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
ms.date: 05/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: eb726f37d25e782a90938b7794be6dea2c30a7d5
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890723"
---
# <a name="create-a-leave-request-workflow"></a><span data-ttu-id="8cefc-103">Szabadságkérelem munkafolyamat létrehozása</span><span class="sxs-lookup"><span data-stu-id="8cefc-103">Create a leave request workflow</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="8cefc-104">Létrehozhat egy munkafolyamatot a Dynamics 365 Human Resources alkalmazásban a szabadságkérelmek egységes kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="8cefc-104">You can create a workflow in Dynamics 365 Human Resources to consistently manage your leave and absence requests.</span></span> <span data-ttu-id="8cefc-105">A **Szabadság és távollét** munkafolyamata lehetővé teszi:</span><span class="sxs-lookup"><span data-stu-id="8cefc-105">A **Leave and absence** workflow lets you:</span></span>

- <span data-ttu-id="8cefc-106">Feladatok definiálását</span><span class="sxs-lookup"><span data-stu-id="8cefc-106">Define tasks</span></span>
- <span data-ttu-id="8cefc-107">Annak meghatározását, hogy kinek kell végrehajtania a feladatokat</span><span class="sxs-lookup"><span data-stu-id="8cefc-107">Determine who must complete the tasks</span></span>
- <span data-ttu-id="8cefc-108">Annak megadását, hogy ki hagyhatja jóvá vagy utasíthatja el a kérelmeket</span><span class="sxs-lookup"><span data-stu-id="8cefc-108">Specify who can approve or reject requests</span></span>

## <a name="create-a-leave-and-absence-request-workflow"></a><span data-ttu-id="8cefc-109">Szabadság- és távolléti kérelem munkafolyamat létrehozása</span><span class="sxs-lookup"><span data-stu-id="8cefc-109">Create a Leave and absence request workflow</span></span>

1. <span data-ttu-id="8cefc-110">A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.</span><span class="sxs-lookup"><span data-stu-id="8cefc-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="8cefc-111">A **Beállítás** alatt válassza az **Emberi erőforrás munkafolyamatok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8cefc-111">Under **Setup**, select **Human resource workflows**.</span></span>

3. <span data-ttu-id="8cefc-112">Válassza az **Új** lehetőséget, majd válassza a **Szabadság- és távollétkérelem** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8cefc-112">Select **New**, and then select **Leave and absence request**.</span></span> 

4. <span data-ttu-id="8cefc-113">Amikor megjelenik a **Megnyitja ezt a fájlt?** üzenetmező, vákasza a **Megnyitás** lehetőséget, és jelentkezzen be a vállalati hitelesítő adataival.</span><span class="sxs-lookup"><span data-stu-id="8cefc-113">When the **Open this file?** message box appears, select **Open** and sign in with your company credentials.</span></span>

5. <span data-ttu-id="8cefc-114">A munkafolyamat-szerkesztővel hozzon létre egy munkafolyamatot a szabadságkérelmekhez.</span><span class="sxs-lookup"><span data-stu-id="8cefc-114">Use the workflow editor to create a workflow for your leave requests.</span></span> <span data-ttu-id="8cefc-115">További tájékoztatás a munkafolyamatok használatáról: [Munkafolyamatok létrehozása – áttekintés](../fin-ops-core/fin-ops/organization-administration/create-workflow.md?toc=%2fdynamics365%2fcommerce%2ftoc.json.)</span><span class="sxs-lookup"><span data-stu-id="8cefc-115">For more information about working with workflows, see [Create workflows overview](../fin-ops-core/fin-ops/organization-administration/create-workflow.md?toc=%2fdynamics365%2fcommerce%2ftoc.json.)</span></span>

## <a name="leave-and-absence-request-workflow-data-elements"></a><span data-ttu-id="8cefc-116">Szabadság- és távolléti kérelem munkafolyamatának adatelemei</span><span class="sxs-lookup"><span data-stu-id="8cefc-116">Leave and absence request workflow data elements</span></span>

<span data-ttu-id="8cefc-117">A következő adatelemek segítségével feltételes vagy automatikus jóváhagyásokat hozhat létre a munkafolyamatokban a szabadság- és a távolléti kérelmekhez:</span><span class="sxs-lookup"><span data-stu-id="8cefc-117">You can use the following data elements to create conditional or automatic approvals in workflows for leave and absence requests:</span></span>

- <span data-ttu-id="8cefc-118">**Összeg**</span><span class="sxs-lookup"><span data-stu-id="8cefc-118">**Amount**</span></span>
- <span data-ttu-id="8cefc-119">**Megjegyzés**</span><span class="sxs-lookup"><span data-stu-id="8cefc-119">**Comment**</span></span>
- <span data-ttu-id="8cefc-120">**Cég**</span><span class="sxs-lookup"><span data-stu-id="8cefc-120">**Company**</span></span>
- <span data-ttu-id="8cefc-121">**Létrehozta:**</span><span class="sxs-lookup"><span data-stu-id="8cefc-121">**Created by**</span></span>
- <span data-ttu-id="8cefc-122">**Létrehozás dátuma és időpontja**</span><span class="sxs-lookup"><span data-stu-id="8cefc-122">**Created date and time**</span></span>
- <span data-ttu-id="8cefc-123">**Befejezés**</span><span class="sxs-lookup"><span data-stu-id="8cefc-123">**End date**</span></span>
- <span data-ttu-id="8cefc-124">**Szabadság típusa**</span><span class="sxs-lookup"><span data-stu-id="8cefc-124">**Leave type**</span></span>
- <span data-ttu-id="8cefc-125">**Módosította:**</span><span class="sxs-lookup"><span data-stu-id="8cefc-125">**Modified by**</span></span>
- <span data-ttu-id="8cefc-126">**Módosítás dátuma és időpontja**</span><span class="sxs-lookup"><span data-stu-id="8cefc-126">**Modified date and time**</span></span>
- <span data-ttu-id="8cefc-127">**Okkód**</span><span class="sxs-lookup"><span data-stu-id="8cefc-127">**Reason code**</span></span>
- <span data-ttu-id="8cefc-128">**Kérelemazonosító**</span><span class="sxs-lookup"><span data-stu-id="8cefc-128">**Request ID**</span></span>
- <span data-ttu-id="8cefc-129">**Kezdés dátuma**</span><span class="sxs-lookup"><span data-stu-id="8cefc-129">**Start date**</span></span>
- <span data-ttu-id="8cefc-130">**Állapot**</span><span class="sxs-lookup"><span data-stu-id="8cefc-130">**Status**</span></span> 
- <span data-ttu-id="8cefc-131">**Küldés dátuma**</span><span class="sxs-lookup"><span data-stu-id="8cefc-131">**Submission date**</span></span>
- <span data-ttu-id="8cefc-132">**Beküldte:**</span><span class="sxs-lookup"><span data-stu-id="8cefc-132">**Submitted by**</span></span>
- <span data-ttu-id="8cefc-133">**Elküldve az Emberi erőforrások által**</span><span class="sxs-lookup"><span data-stu-id="8cefc-133">**Submitted by Human resources**</span></span>
- <span data-ttu-id="8cefc-134">**Beküldve a vezető által**</span><span class="sxs-lookup"><span data-stu-id="8cefc-134">**Submitted by Manager**</span></span>
- <span data-ttu-id="8cefc-135">**Beküldve a következő nevében**</span><span class="sxs-lookup"><span data-stu-id="8cefc-135">**Submitted on behalf**</span></span>
- <span data-ttu-id="8cefc-136">**Dolgozó**</span><span class="sxs-lookup"><span data-stu-id="8cefc-136">**Worker**</span></span>
- <span data-ttu-id="8cefc-137">**Dolgozó típusa**</span><span class="sxs-lookup"><span data-stu-id="8cefc-137">**Worker type**</span></span>

<span data-ttu-id="8cefc-138">Ezek a példák azt mutatják be, hogyan lehet különböző típusú munkafolyamat-feltételeket létrehozni a következő adatelemek segítségével:</span><span class="sxs-lookup"><span data-stu-id="8cefc-138">These examples show how you can create different types of workflow conditions by using these data elements:</span></span>

- <span data-ttu-id="8cefc-139">Az **Okkód** feltételes állításban történő használata a betegszabadság-kérelmek átirányításához a **Műtét** okkóddal a HR számára, míg az összes többi okkód átirányítása a vezetőhöz.</span><span class="sxs-lookup"><span data-stu-id="8cefc-139">Use **Reason code** in a conditional statement to route sick leave requests with the reason code **Surgery** to HR for approval, while routing all other reason codes to the manager.</span></span> <span data-ttu-id="8cefc-140">A feltételes állításokkal kapcsolatos további tudnivalókat lásd: [Feltételes döntések konfigurálása egy munkafolyamatban](../fin-ops-core/fin-ops/organization-administration/configure-conditional-decision-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="8cefc-140">For more information about conditional statements, see [Configure conditional decisions in a workflow](../fin-ops-core/fin-ops/organization-administration/configure-conditional-decision-workflow.md).</span></span> 

- <span data-ttu-id="8cefc-141">Az **Emberi erőforrások által elküldött** és a **Vezető által beküldött** elemek használata egy automatikus műveletben a szabadságkérelmek automatikus jóváhagyásához, amelyeket ezek a szerepkörök küldtek be a munkavállalók nevében.</span><span class="sxs-lookup"><span data-stu-id="8cefc-141">Use **Submitted by Human resources** and **Submitted by manager** in an automatic action to automatically approve leave requests that these roles submit on behalf of employees.</span></span> <span data-ttu-id="8cefc-142">Az automatikus műveletekkel kapcsolatos további tudnivalókat lásd: [Jóváhagyási folyamatok konfigurálása munkafolyamatokban](../fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="8cefc-142">For more information about automatic actions, see [Configure approval processes in a workflow](../fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow.md).</span></span>

- <span data-ttu-id="8cefc-143">A **Szabadságtípus** használata feltételes állításban vagy automatikus műveletben, annak meghatározásához, hogy a munkafolyamat hogyan irányítsa át az egyes szabadságtípusokat tartalmazó szabadságkérelmeket.</span><span class="sxs-lookup"><span data-stu-id="8cefc-143">Use **Leave type** in a conditional statement or automatic action to control how the workflow routes requests with certain leave types.</span></span>

## <a name="see-also"></a><span data-ttu-id="8cefc-144">Lásd még</span><span class="sxs-lookup"><span data-stu-id="8cefc-144">See also</span></span>

- [<span data-ttu-id="8cefc-145">Szabadság és távollét áttekintése</span><span class="sxs-lookup"><span data-stu-id="8cefc-145">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]