---
title: Készségek konfigurálása
description: A dolgozó készségeit nyomon követheti a Dynamics 365 Human Resources rendszerben. Emellett megadhatja, hogy egy adott beosztáshoz milyen szakértelem szükséges.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 816822d1f3d365b4c5571c13e9f596e1c5d5e59c
ms.sourcegitcommit: 48528233e0f02dbd47e96e030254ef65f2bb899e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/20/2021
ms.locfileid: "6076559"
---
# <a name="configure-skills"></a><span data-ttu-id="1f908-104">Készségek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="1f908-104">Configure skills</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="1f908-105">A dolgozó készségeit nyomon követheti a Dynamics 365 Human Resources rendszerben.</span><span class="sxs-lookup"><span data-stu-id="1f908-105">You can track your worker's skills in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="1f908-106">Emellett megadhatja, hogy egy adott beosztáshoz milyen szakértelem szükséges.</span><span class="sxs-lookup"><span data-stu-id="1f908-106">You can also specify the skills that are required for a specific job.</span></span>

<span data-ttu-id="1f908-107">Nyomon követheti a szakértelmek például a következők:</span><span class="sxs-lookup"><span data-stu-id="1f908-107">Examples of skills you can track include:</span></span>

- <span data-ttu-id="1f908-108">Felügyelet – képesség mások munkájának felügyelésére.</span><span class="sxs-lookup"><span data-stu-id="1f908-108">Supervisory – Ability to supervise the work of others.</span></span>
- <span data-ttu-id="1f908-109">Vezetés – az alkalmazottak és a vállalati területek vezetésének képessége.</span><span class="sxs-lookup"><span data-stu-id="1f908-109">Leadership – Ability to lead employees and business domains.</span></span>
- <span data-ttu-id="1f908-110">Tervezés – képesség az előrelátásra, az elképzelések utasításokba öntésére, és az utasítások átlátására.</span><span class="sxs-lookup"><span data-stu-id="1f908-110">Planning – Ability to look ahead, to form vision statements, and to see them through.</span></span>
- <span data-ttu-id="1f908-111">HTML - HTML-kódolás ismerete.</span><span class="sxs-lookup"><span data-stu-id="1f908-111">HTML – Ability to write HTML code.</span></span>

<span data-ttu-id="1f908-112">Ha még nem állított be készségtípusokat és minősítési modelleket, a készségek létrehozása előtt hozzá kell adnia néhányat.</span><span class="sxs-lookup"><span data-stu-id="1f908-112">If you haven't already set up skill types and rating models, you'll need to add some before creating skills.</span></span>

<span data-ttu-id="1f908-113">A következő személyek adhatnak meg készséget a dolgozóknak:</span><span class="sxs-lookup"><span data-stu-id="1f908-113">The following people can enter skills for a worker:</span></span>

- <span data-ttu-id="1f908-114">A dolgozók megadhatnak maguknak készségeket az Alkalmazotti önkiszolgáló rendszerben.</span><span class="sxs-lookup"><span data-stu-id="1f908-114">Workers can enter skills for themselves in Employee self-service.</span></span> <span data-ttu-id="1f908-115">Ezeket a készségeket a vezetőnek jóvák kell hagynia.</span><span class="sxs-lookup"><span data-stu-id="1f908-115">These skills require manager approval.</span></span>
- <span data-ttu-id="1f908-116">A vezetők megadhatnak készségeket a munkavállalóikhoz.</span><span class="sxs-lookup"><span data-stu-id="1f908-116">Managers can enter skills for their workers.</span></span> <span data-ttu-id="1f908-117">Létrehozhat olyan munkafolyamatot, amely automatikusan jóváhagyja ezeket a készségeket.</span><span class="sxs-lookup"><span data-stu-id="1f908-117">You can create a workflow that auto-approves these skills.</span></span>

## <a name="create-a-skill-type"></a><span data-ttu-id="1f908-118">Készségtípusok létrehozása</span><span class="sxs-lookup"><span data-stu-id="1f908-118">Create a skill type</span></span>

<span data-ttu-id="1f908-119">A készségtípusok olyan kategóriák, amelyekbe az egyes készségek tartoznak (például Adminisztráció vagy Értékesítés).</span><span class="sxs-lookup"><span data-stu-id="1f908-119">Skill types are categories that individual skills fall under, such as Administration or Sales.</span></span>

1. <span data-ttu-id="1f908-120">Az **Alkalmazotti fejlesztés** munkaterületen válassza a **Hivatkozások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f908-120">In the **Employee development** workspace, select **Links**.</span></span>

2. <span data-ttu-id="1f908-121">A **Kompetencia beállítása** területen válassza ki a **Szakértelemtípusok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f908-121">Under **Competency setup**, select **Skill types**.</span></span>

3. <span data-ttu-id="1f908-122">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f908-122">Select **New**.</span></span>

4. <span data-ttu-id="1f908-123">Töltse ki a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="1f908-123">Complete the following fields:</span></span>

   - <span data-ttu-id="1f908-124">**Szakértelemtípus**: Adja meg a készségtípus nevét.</span><span class="sxs-lookup"><span data-stu-id="1f908-124">**Skill type**: Enter a name for the skill type.</span></span>
   - <span data-ttu-id="1f908-125">**Leírás**: Adja meg a készségtípus leírását.</span><span class="sxs-lookup"><span data-stu-id="1f908-125">**Description**: Enter a description for the skill type.</span></span>

5. <span data-ttu-id="1f908-126">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f908-126">Select **Save**.</span></span>

## <a name="create-a-rating-model"></a><span data-ttu-id="1f908-127">Minősítési modell létrehozása</span><span class="sxs-lookup"><span data-stu-id="1f908-127">Create a rating model</span></span>

<span data-ttu-id="1f908-128">A minősítési modellek segítenek meghatározni a személy valós szakértelmi szintjét, az elérendő szintet vagy az adott beosztáshoz szükséges szintet.</span><span class="sxs-lookup"><span data-stu-id="1f908-128">Rating models help evaluate a person's actual level of skill, the level they should work to achieve, or the level of skill required for a job.</span></span> <span data-ttu-id="1f908-129">Egy értékelési modell minden szintjéhez tényező társul.</span><span class="sxs-lookup"><span data-stu-id="1f908-129">Each level in a rating model is assigned a factor.</span></span>

1. <span data-ttu-id="1f908-130">Az **Alkalmazotti fejlesztés** munkaterületen válassza a **Hivatkozások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f908-130">In the **Employee development** workspace, select **Links**.</span></span>

2. <span data-ttu-id="1f908-131">A **Kompetencia beállítása** területen válassza a **Minősítési modellek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f908-131">Under **Competency setup**, select **Rating models**.</span></span>

3. <span data-ttu-id="1f908-132">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f908-132">Select **New**.</span></span>

4. <span data-ttu-id="1f908-133">Töltse ki a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="1f908-133">Complete the following fields:</span></span>

   - <span data-ttu-id="1f908-134">**Minősítés**: Adja meg a minősítési modell nevét, például **Készségek**.</span><span class="sxs-lookup"><span data-stu-id="1f908-134">**Rating**: Enter a name for the rating model, such as **Skills**.</span></span>
   - <span data-ttu-id="1f908-135">**Leírás**: Adja meg a minősítési modell leírását, például **Szakértelem értékelései**.</span><span class="sxs-lookup"><span data-stu-id="1f908-135">**Description**: Enter a description for the rating model, such as **Skill ratings**.</span></span>

5. <span data-ttu-id="1f908-136">A **Szintek** szakaszban válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f908-136">In the **Levels** section, select **New**.</span></span> <span data-ttu-id="1f908-137">Minden egyes hozzáadni kívánt szintnél töltse ki a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="1f908-137">For each level you want to add, complete the following fields:</span></span>

   - <span data-ttu-id="1f908-138">**Szint**: Adja meg a szint nevét.</span><span class="sxs-lookup"><span data-stu-id="1f908-138">**Level**: Enter a name for the level.</span></span>
   - <span data-ttu-id="1f908-139">**Leírás**: Adja meg a szint leírását.</span><span class="sxs-lookup"><span data-stu-id="1f908-139">**Description**: Enter a description for the level.</span></span>
   - <span data-ttu-id="1f908-140">**Szorzó**: Adjon meg egy szorzóértéket 0 és 9 között.</span><span class="sxs-lookup"><span data-stu-id="1f908-140">**Factor**: Enter a factor value from 0-9.</span></span> <span data-ttu-id="1f908-141">A szorzók segítenek normalizálni a készségek különböző minősítési modelleket használó pontszámát.</span><span class="sxs-lookup"><span data-stu-id="1f908-141">Factors help normalize the scores of skills that use different rating models.</span></span> <span data-ttu-id="1f908-142">Minden szinthez egyedi szorzót kell megadni.</span><span class="sxs-lookup"><span data-stu-id="1f908-142">Each level must have a unique factor.</span></span> <span data-ttu-id="1f908-143">A magasabb értékű szorzóval rendelkező szintek nagyobb súlyt képviselnek a minősítés modellben.</span><span class="sxs-lookup"><span data-stu-id="1f908-143">Levels with higher factor values carry more weight in a rating model.</span></span>

   <span data-ttu-id="1f908-144">Szükség szerint adjon hozzá további szinteket.</span><span class="sxs-lookup"><span data-stu-id="1f908-144">Continue adding levels as necessary.</span></span> <span data-ttu-id="1f908-145">Egy minősítési modellhez legfeljebb 10 minősítési szintet adhat meg.</span><span class="sxs-lookup"><span data-stu-id="1f908-145">You can enter up to 10 levels for each rating model.</span></span>

6. <span data-ttu-id="1f908-146">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f908-146">Select **Save**.</span></span>

## <a name="create-a-skill"></a><span data-ttu-id="1f908-147">Készségek létrehozása</span><span class="sxs-lookup"><span data-stu-id="1f908-147">Create a skill</span></span>

<span data-ttu-id="1f908-148">Egy készség hozzárendelése, szakértelem-feltérképezési keresés vagy szakértelemprofil létrehozása előtt meg kell adnia a szakértelemre vonatkozó adatokat a **Szakértelmek** képernyőn.</span><span class="sxs-lookup"><span data-stu-id="1f908-148">Before you can assign a skill, or create a skill-mapping search or skill profile, you must enter information about the skills on the **Skills** page.</span></span> <span data-ttu-id="1f908-149">Minden egyes szakértelmhez kiválaszthatja a típust és a minősítési modellt.</span><span class="sxs-lookup"><span data-stu-id="1f908-149">For each skill, you can select a skill type and a rating model.</span></span>

1. <span data-ttu-id="1f908-150">Az **Alkalmazotti fejlesztés** munkaterületen válassza a **Hivatkozások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f908-150">In the **Employee development** workspace, select **Links**.</span></span>

2. <span data-ttu-id="1f908-151">A **Kompetencia beállítása** területen válassza ki a **Szakértelmek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f908-151">Under **Competency setup**, select **Skills**.</span></span>

3. <span data-ttu-id="1f908-152">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f908-152">Select **New**.</span></span>

4. <span data-ttu-id="1f908-153">Töltse ki a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="1f908-153">Complete the following fields:</span></span>

   - <span data-ttu-id="1f908-154">**Készség**: Adja meg a készség nevét.</span><span class="sxs-lookup"><span data-stu-id="1f908-154">**Skill**: Enter a name for the skill.</span></span>
   - <span data-ttu-id="1f908-155">**Leírás**: Adja meg a készség leírását.</span><span class="sxs-lookup"><span data-stu-id="1f908-155">**Description**: Enter a description for the skill.</span></span>
   - <span data-ttu-id="1f908-156">**Minősítés**: A készséghez használandó minősítési modell kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="1f908-156">**Rating**: Select the rating model you want to use for this skill.</span></span>
   - <span data-ttu-id="1f908-157">**Szakértelemtípus**: Válasszon a szakértelemtípusok listájából.</span><span class="sxs-lookup"><span data-stu-id="1f908-157">**Skill type**: Select from the list of skill types.</span></span>

5. <span data-ttu-id="1f908-158">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f908-158">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f908-159">Lásd még</span><span class="sxs-lookup"><span data-stu-id="1f908-159">See also</span></span>

[<span data-ttu-id="1f908-160">Készségek megadása</span><span class="sxs-lookup"><span data-stu-id="1f908-160">Enter skills</span></span>](hr-develop-enter-skills.md)<br>
[<span data-ttu-id="1f908-161">Készségek hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="1f908-161">Map skills</span></span>](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]