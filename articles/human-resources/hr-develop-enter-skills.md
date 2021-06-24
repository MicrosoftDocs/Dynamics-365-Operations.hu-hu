---
title: Készségek megadása
description: A dolgozók és a vezetők megadhatják a szakértelemeket a Dynamics 365 Human Resources rendszerben.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 5a65f1884ea87bbf2519cc94e4c52a40ac1a91bd
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193977"
---
# <a name="enter-skills"></a><span data-ttu-id="4ce3e-103">Készségek megadása</span><span class="sxs-lookup"><span data-stu-id="4ce3e-103">Enter skills</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="4ce3e-104">A dolgozók, a pályázók vagy a kapcsolattartók a megcélzott vagy a már megszerzett készségeket is rögzíthetik a Dynamics 365 Human Resources rendszerben.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-104">You can enter target skills or actual skills for workers, applicants, or contacts in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="4ce3e-105">A megcélzott szakértelem olyan szakértelem, amelyet az adott személy el szeretne érni.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-105">A target skill is a skill that a person plans to achieve.</span></span> <span data-ttu-id="4ce3e-106">A tényleges szakértelem az, amivel már rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-106">An actual skill is a skill that a person currently has.</span></span>

## <a name="create-a-workflow-to-auto-approve-skills"></a><span data-ttu-id="4ce3e-107">Munkafolyamat létrehozása a készségek automatikus jóváhagyásához</span><span class="sxs-lookup"><span data-stu-id="4ce3e-107">Create a workflow to auto-approve skills</span></span>

<span data-ttu-id="4ce3e-108">A készségek jóváhagyás nélkül történő megadásához létre kell hoznia egy munkafolyamatot a készségek automatikus jóváhagyásához.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-108">To enter skills without requiring approval, you must create a workflow to auto-approve skills.</span></span>

> [!NOTE]
> <span data-ttu-id="4ce3e-109">A dolgozók által beírt készségek esetében mindig szükség van a vezető jóváhagyására.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-109">Skills entered by workers always require manager approval.</span></span> <span data-ttu-id="4ce3e-110">Ez a munkafolyamat csak a vezetők által a dolgozóik nevében megadott készségeket hagyja jóvá automatikusan.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-110">This workflow only auto-approves skills entered by managers on behalf of their workers.</span></span>

1. <span data-ttu-id="4ce3e-111">A **Személyzetkezelés** munkaterületen válassza a **Hivatkozások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-111">In the **Personnel management** workspace, select **Links**.</span></span>

2. <span data-ttu-id="4ce3e-112">A **Beállítás** részen válassza az **Emberi erőforrások munkafolyamatai** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-112">Under **Setup**, select **Human resources workflows**.</span></span>

3. <span data-ttu-id="4ce3e-113">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-113">Select **New**.</span></span>

4. <span data-ttu-id="4ce3e-114">A **Munkafolyamat létrehozása** panelen válassza ki a **Dolgozó szakértelmei** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-114">In the **Create workflow** pane, select **Worker skills**.</span></span>

   <span data-ttu-id="4ce3e-115">[![A Dolgozó szakértelmei munkafolyamat kiválasztása](media/hr-develop-skills-new-workflow.png)](media/hr-develop-skills-new-workflow.png)</span><span class="sxs-lookup"><span data-stu-id="4ce3e-115">[![Select Worker skills workflow](media/hr-develop-skills-new-workflow.png)](media/hr-develop-skills-new-workflow.png)</span></span>

5. <span data-ttu-id="4ce3e-116">A **Megnyitja ezt a fájlt?** párbeszédpanelen válassza a **Megnyitás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-116">In the **Open this file?** dialogue, select **Open**.</span></span> <span data-ttu-id="4ce3e-117">Amikor a rendszer kéri, adja meg a hitelesítő adatait.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-117">When prompted, enter your credentials.</span></span>

6. <span data-ttu-id="4ce3e-118">A munkafolyamat-szerkesztőben válassza ki a **Készségek jóváhagyása** munkafolyamat-elemet, és húzza a vászonra.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-118">In the workflow editor, select the **Approve skills** workflow element and drag it onto the canvas.</span></span>

   <span data-ttu-id="4ce3e-119">[![A Készségek jóváhagyása munkafolyamat-elem kiválasztása](media/hr-develop-skills-element.png)](media/hr-develop-skills-element.png)</span><span class="sxs-lookup"><span data-stu-id="4ce3e-119">[![Select Approve skills workflow element](media/hr-develop-skills-element.png)](media/hr-develop-skills-element.png)</span></span>

7. <span data-ttu-id="4ce3e-120">Kapcsolja össze a **Kezdés** és az **1. készségek jóváhagyása**, majd az **1. készségek jóváhagyása** és a **Befejezés** elemet.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-120">Connect the **Start** element to the **Approve skills 1** element, and then connect the **Approve skills 1** element to the **End** element.</span></span> <span data-ttu-id="4ce3e-121">Előfordulhat, hogy a **Záró** elem eléréséhez görgetni kell.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-121">You might need to scroll down to see the **End** element.</span></span> <span data-ttu-id="4ce3e-122">Az elemet közelebb húzhatja a többi elemhez.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-122">You can drag it closer to the other elements.</span></span>

   <span data-ttu-id="4ce3e-123">[![Munkafolyamat-elemek összekapcsolása](media/hr-develop-skills-connect-elements.png)](media/hr-develop-skills-connect-elements.png)</span><span class="sxs-lookup"><span data-stu-id="4ce3e-123">[![Connect workflow elements](media/hr-develop-skills-connect-elements.png)](media/hr-develop-skills-connect-elements.png)</span></span>

8. <span data-ttu-id="4ce3e-124">Kattintson duplán az **1. készségek jóváhagyása** munkafolyamat-elemre, majd kattintson a jobb gombbal az **1. lépés elemre**.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-124">Double-click the **Approve skills 1** workflow element, and then right-click the **Step 1** element.</span></span> <span data-ttu-id="4ce3e-125">Kattintson a jobb gombbal az **1. lépés** elemre, majd válassza a **Tulajdonságok** parancsot.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-125">Right-click the **Step 1** element, and then select **Properties**.</span></span>

9. <span data-ttu-id="4ce3e-126">A **Tulajdonságok** ablakban válassza a **Feltétel** lehetőséget a bal oldali navigációs sávon.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-126">In the **Properties** window, select **Condition** on the left-hand nav bar.</span></span>

10. <span data-ttu-id="4ce3e-127">Válassza a **Csak akkor fusson ez a lépés, ha teljesül a következő feltétel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-127">Select **Run this step only when the following condition is met**.</span></span>

11. <span data-ttu-id="4ce3e-128">Válassza ki a **Feltétel hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-128">Select **Add condition**.</span></span> <span data-ttu-id="4ce3e-129">Az **Ahol** elem után válassza a **Alkalmazotti készségek önkiszolgáló módon**, majd az **Alkalmazotti készségek önkiszolgáló módon.Személy** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-129">After **Where**, select **Employee self service skills**, and then select **Employee self service skills.Person**.</span></span> <span data-ttu-id="4ce3e-130">A **van** elem után válassza ki a **mezőt**, majd a **Felhasználó és szermély kapcsolata.Személy** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-130">After **is**, select **field**, and then select **User to person relationship.Person**.</span></span>

    <span data-ttu-id="4ce3e-131">[![Feltétel megadása](media/hr-develop-skills-condition.png)](media/hr-develop-skills-condition.png)</span><span class="sxs-lookup"><span data-stu-id="4ce3e-131">[![Specify condition](media/hr-develop-skills-condition.png)](media/hr-develop-skills-condition.png)</span></span>

12. <span data-ttu-id="4ce3e-132">Válassza a **Hozzárendelés** lehetőséget a bal oldali navigációs sávon.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-132">Select **Assignment** on the left-hand nav bar.</span></span>

13. <span data-ttu-id="4ce3e-133">A **Hozzárendelés típusa** lapon válassza a **Hierarchia** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-133">On the **Assignment type** tab, select **Hierarchy**.</span></span>

14. <span data-ttu-id="4ce3e-134">A **Hierarchia kiválasztása** lapon **Hierarchia típusa:** mezőjében válassza a **Vezetői hierarchia** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-134">On the **Hierarchy selection** tab, in the **Hierarchy type:** field, select **Managerial hierarchy**.</span></span>

    <span data-ttu-id="4ce3e-135">[![Vezetői hierarchia megadása](media/hr-develop-skills-hierarchy.png)](media/hr-develop-skills-hierarchy.png)</span><span class="sxs-lookup"><span data-stu-id="4ce3e-135">[![Specify managerial hierarchy](media/hr-develop-skills-hierarchy.png)](media/hr-develop-skills-hierarchy.png)</span></span>

15. <span data-ttu-id="4ce3e-136">Válassza a **Bezárás**, majd a vászon útkövető modulján a **Munkafolyamat** elemet, végül a **Mentés és bezárás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-136">Select **Close**, select **Workflow** in the canvas breadcrumb, and then select **Save and close**.</span></span>

<span data-ttu-id="4ce3e-137">További tájékoztatás a munkafolyamatok létrehozásáról: [A munkafolyamat-rendszer áttekintése](../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md?toc=/dynamics365/human-resources/toc.json).</span><span class="sxs-lookup"><span data-stu-id="4ce3e-137">For more information about creating workflows, see [Workflow system overview](../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md?toc=/dynamics365/human-resources/toc.json).</span></span>

## <a name="enter-skills-for-a-worker"></a><span data-ttu-id="4ce3e-138">Dolgozó készségeinek megadása</span><span class="sxs-lookup"><span data-stu-id="4ce3e-138">Enter skills for a worker</span></span>

1. <span data-ttu-id="4ce3e-139">Jelöljön ki egy dolgozót.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-139">Select a worker.</span></span>

2. <span data-ttu-id="4ce3e-140">A **Dolgozó** oldal műveletsávján válassza ki a **Személy**, majd a **Készségek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-140">In the action bar of the **Worker** page, select **Person**, and then select **Skills**.</span></span>

3. <span data-ttu-id="4ce3e-141">A **Készségek** oldalon minden készségnél töltse ki a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="4ce3e-141">On the **Skills** page, complete the following fields for each skill:</span></span>

   - <span data-ttu-id="4ce3e-142">**Készség**: Válasszon ki egy készséget.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-142">**Skill**: Select a skill.</span></span>
   - <span data-ttu-id="4ce3e-143">**Szinttípus**: Válassza a **Tényleges** lehetőséget az olyan szakértelemekhez, amelyekkel a dolgozó már rendelkezik, és válassza a **Cél** lehetőséget az olyan szakértelmekhez, amelyeket a dolgozó próbál megszerezni.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-143">**Level type**: Select **Actual** for a skill the worker already has, or select **Target** for a skill the worker is working toward.</span></span>
   - <span data-ttu-id="4ce3e-144">**Szint**: A dolgozó szakértelmének megfelelő szint kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-144">**Level**: Select a level for the worker's skill.</span></span>
   - <span data-ttu-id="4ce3e-145">**Szint dátuma**: A naptárban válasszon ki dátumot.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-145">**Level date**: Select a date in the calendar tool.</span></span>
   - <span data-ttu-id="4ce3e-146">**Vizsgáló**: Ha lehetséges, válasszon ki egy vizsgáztatót a listáról.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-146">**Examiner**: If appropriate, select an examiner from the list.</span></span> <span data-ttu-id="4ce3e-147">A keresés szűrhető.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-147">You can filter your search.</span></span>
   - <span data-ttu-id="4ce3e-148">**Tapasztalat (év)**: Adja meg, hány éves tapasztalata van az illetőnek.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-148">**Years of experience**: Enter years of experience.</span></span>
   - <span data-ttu-id="4ce3e-149">**Ellenőrizve**: Ha a készséget ellenőrizték van, jelölje be a jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-149">**Verified**: If the skill is verified, check the box.</span></span>
   - <span data-ttu-id="4ce3e-150">**Ellenőrizte**: Adja meg az ellenőrző nevét.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-150">**Verified by**: Enter the name of the verifier.</span></span>

4. <span data-ttu-id="4ce3e-151">Ha megadta a szakértelmek részleteit, válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4ce3e-151">When you're done entering skills, select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="4ce3e-152">Lásd még</span><span class="sxs-lookup"><span data-stu-id="4ce3e-152">See also</span></span>

[<span data-ttu-id="4ce3e-153">Készségek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="4ce3e-153">Configure skills</span></span>](hr-develop-skills.md)<br>
[<span data-ttu-id="4ce3e-154">Készségek hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="4ce3e-154">Map skills</span></span>](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]