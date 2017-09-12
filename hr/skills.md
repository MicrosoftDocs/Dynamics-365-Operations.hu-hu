---
title: "A munkaerő szakértelmének üzleti igényű igazítása"
description: "Nyomon követheti azokat a szakértelmeket, amelyekkel dolgozók, pályázók vagy kapcsolattartók jelentkeznek vagy jelentkezniük kellene. Emellett megadhatja, hogy egy adott beosztáshoz milyen szakértelem szükséges."
author: kherr75
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 2b76064049daccdcdff04c9f2fdde9a8b9c9e8e0
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---

# <a name="align-workforce-skills-with-business-needs"></a><span data-ttu-id="3b9c4-104">A munkaerő szakértelmének üzleti igényű igazítása</span><span class="sxs-lookup"><span data-stu-id="3b9c4-104">Align workforce skills with business needs</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="3b9c4-105">Nyomon követheti azokat a szakértelmeket, amelyekkel dolgozók, pályázók vagy kapcsolattartók jelentkeznek vagy jelentkezniük kellene.</span><span class="sxs-lookup"><span data-stu-id="3b9c4-105">You can track the skills that workers, applicants, or contact persons have, or should have, to fulfill their roles effectively.</span></span> <span data-ttu-id="3b9c4-106">Emellett megadhatja, hogy egy adott beosztáshoz milyen szakértelem szükséges.</span><span class="sxs-lookup"><span data-stu-id="3b9c4-106">You can also specify the skills that are required for a specific job.</span></span>

<span data-ttu-id="3b9c4-107">Nyomon követheti a szakértelmek például a következők:</span><span class="sxs-lookup"><span data-stu-id="3b9c4-107">Examples of skills you can track include the following:</span></span>
-   <span data-ttu-id="3b9c4-108">Felügyelet – képesség mások munkájának felügyelésére.</span><span class="sxs-lookup"><span data-stu-id="3b9c4-108">Supervisory – Ability to supervise the work of others.</span></span>
-   <span data-ttu-id="3b9c4-109">Vezetés – az alkalmazottak és a vállalati területek vezetésének képessége.</span><span class="sxs-lookup"><span data-stu-id="3b9c4-109">Leadership – Ability to lead employees and business domains.</span></span>
-   <span data-ttu-id="3b9c4-110">Tervezés – képesség az előrelátásra, az elképzelések formába öntésére, és azok átlátására.</span><span class="sxs-lookup"><span data-stu-id="3b9c4-110">Planning – Ability to look ahead, to form visions, and to see them through.</span></span>
-   <span data-ttu-id="3b9c4-111">HTML - HTML-kódolás ismerete.</span><span class="sxs-lookup"><span data-stu-id="3b9c4-111">HTML – Ability to write HTML code.</span></span>

<span data-ttu-id="3b9c4-112">A szakértelem adott személyhez vagy beosztáshoz való hozzárendelése, szakértelem-feltérképezési keresés futtatása és szakértelemprofil létrehozása előtt meg kell adnia a szakértelemre vonatkozó adatokat a **Szakértelmek** képernyőn.</span><span class="sxs-lookup"><span data-stu-id="3b9c4-112">Before you can assign a skill to a person or a job, create a skill-mapping search, or create a skill profile, you must enter information about the skills on the **Skills** page.</span></span> <span data-ttu-id="3b9c4-113">Minden egyes szakértelmhez kiválaszthatja a típust és a minősítési modellt.</span><span class="sxs-lookup"><span data-stu-id="3b9c4-113">For each skill, you can select a skill type and a rating model.</span></span>

## <a name="rating-models"></a><span data-ttu-id="3b9c4-114">Minősítési modellek</span><span class="sxs-lookup"><span data-stu-id="3b9c4-114">Rating models</span></span>
<span data-ttu-id="3b9c4-115">A minősítési modellek segítenek meghatározni a személy valós szakértelmi szintjét, az elérendő szintet, vagy egy adott beosztáshoz szükséges szintet.</span><span class="sxs-lookup"><span data-stu-id="3b9c4-115">Rating models help evaluate a person's actual level of skill, the level they should work to achieve, or the level of skill that is required for a job.</span></span> <span data-ttu-id="3b9c4-116">Legfeljebb 10 minősítési szintet adhat meg.</span><span class="sxs-lookup"><span data-stu-id="3b9c4-116">You can enter up to 10 levels for a rating model.</span></span>  <span data-ttu-id="3b9c4-117">Egy értékelési modell minden szintjéhez tényező társul.</span><span class="sxs-lookup"><span data-stu-id="3b9c4-117">Each level in a rating model is assigned a factor.</span></span>  <span data-ttu-id="3b9c4-118">A tényező értékét a különböző minősítési modelleket használó készségek pontszámainak normalizálására használják.</span><span class="sxs-lookup"><span data-stu-id="3b9c4-118">The factor value will be used to normalize the scores of skills that use different rating models.</span></span>  <span data-ttu-id="3b9c4-119">A tényezőnek egy 0 és 9 közötti számnak kell lennie, és minden szinthez egyedi tényezőnek kell tartoznia.</span><span class="sxs-lookup"><span data-stu-id="3b9c4-119">The factor must be a number between 0-9 and each level must have a unique factor.</span></span>  <span data-ttu-id="3b9c4-120">A magasabb értékű szorzóval rendelkező szintek nagyobb súlyt képviselnek a minősítés modellben.</span><span class="sxs-lookup"><span data-stu-id="3b9c4-120">Levels with higher factor values carry more weight in a rating model.</span></span>

## <a name="specify-job-skills"></a><span data-ttu-id="3b9c4-121">Beosztáshoz szükséges szakértelmek meghatározása</span><span class="sxs-lookup"><span data-stu-id="3b9c4-121">Specify job skills</span></span>
<span data-ttu-id="3b9c4-122">Ha információkat ad meg egy munkakörről, megadhatja azokat a készségeket, amelyekre a személynek szüksége van a munkakörhöz szükséges munka elvégzéséhez.</span><span class="sxs-lookup"><span data-stu-id="3b9c4-122">When you enter information about a job, you can specify the skills that a person should have to perform the work required for the job.</span></span>  <span data-ttu-id="3b9c4-123">Emellett megadhatja a kívánt szintet minden egyes készség számára, továbbá a készség fontosságának szintjét is.</span><span class="sxs-lookup"><span data-stu-id="3b9c4-123">In addition you can specify the desired level for each skill as well the level of importance of the skill.</span></span> <span data-ttu-id="3b9c4-124">Különböző beosztásoknál ugyanaz a szakértelem eltérő fontosságú lehet.</span><span class="sxs-lookup"><span data-stu-id="3b9c4-124">Different jobs can require different levels of importance for the same skill.</span></span>

## <a name="enter-skills-for-workers-applicants-or-contacts"></a><span data-ttu-id="3b9c4-125">A dolgozók, pályázók és kapcsolattartók szakértelmeinek megadása</span><span class="sxs-lookup"><span data-stu-id="3b9c4-125">Enter skills for workers, applicants, or contacts</span></span>
<span data-ttu-id="3b9c4-126">A dolgozók, pályázók vagy kapcsolattartók megcélzott vagy már megszerzett szakértelmeit is rögzítheti.</span><span class="sxs-lookup"><span data-stu-id="3b9c4-126">You can enter target skills or actual skills for workers, applicants, or contacts.</span></span> <span data-ttu-id="3b9c4-127">A megcélzott szakértelem olyan szakértelem, amelyet az adott személy el szeretne érni.</span><span class="sxs-lookup"><span data-stu-id="3b9c4-127">A target skill is a skill that a person plans to achieve.</span></span> <span data-ttu-id="3b9c4-128">A tényleges szakértelem az, amivel már rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="3b9c4-128">An actual skill is a skill that a person currently has.</span></span>

## <a name="skill-mapping-and-skill-mapping-profiles"></a><span data-ttu-id="3b9c4-129"> A szakértelem-feltérképezés és a szakértelem-feltérképezési profilok beállítása</span><span class="sxs-lookup"><span data-stu-id="3b9c4-129">Skill mapping and Skill mapping profiles</span></span>
<span data-ttu-id="3b9c4-130">Létrehozhat egy készségleképező keresést olyan dolgozó, jelentkező vagy kapcsolattartó kereséséhez, aki megfelelő képesítéssel rendelkezik egy adott feladattípus végrehajtásához.</span><span class="sxs-lookup"><span data-stu-id="3b9c4-130">You can create a skill-mapping search to find a worker, applicant, or contact person who is qualified to perform a specific type of task.</span></span> <span data-ttu-id="3b9c4-131">A készségleképező keresések készségek, képzés, tanúsítványok, megbízható pozíciók és projekttapasztalatok között keresnek, és olyan találatokat adnak vissza, amelyek megfelelnek a megadott feltételeknek.</span><span class="sxs-lookup"><span data-stu-id="3b9c4-131">Skill-mapping searches look across skills, education, certificates, positions of trust and project experience and return a results that match the criteria entered.</span></span>  <span data-ttu-id="3b9c4-132">Például hasznos lehet tudni, hogy szervezete mely dolgozói keresték meg a CPA-jukat.</span><span class="sxs-lookup"><span data-stu-id="3b9c4-132">For example, it might be useful to know which workers in your organization earned their CPA.</span></span>

<span data-ttu-id="3b9c4-133">A készségleképező profilokkal olyan jelenlegi alkalmazottakra vagy jelöltekre kereshet, akiknek olyan végzettségei vannak, amelyek közvetlenül megfelelnek az üzleti szükségleteknek.</span><span class="sxs-lookup"><span data-stu-id="3b9c4-133">Skill-mapping profiles allow you to find current employees or candidates with qualifications that directly correspond to business needs.</span></span>  <span data-ttu-id="3b9c4-134">Létrehozhat például egy készségleképezési profilt a szervezeténél meglévő nyitott pozícióhoz.</span><span class="sxs-lookup"><span data-stu-id="3b9c4-134">For example, you could create a skill-mapping profile for an open position in your organization.</span></span> <span data-ttu-id="3b9c4-135">Egy adott beosztáshoz profilok létrehozása és másolása a szakértelem, a végzettség és a tanúsítványt az adott feladat a profilt, gyorsan kereshet dolgozók, pályázó és kapcsolattartó személyek megfelelő egy vagy több mellőzhető a profilban megadott feltételeknek megfelelő és a pályázók, akiknek szakismeretei leginkább megfelelnek a projekthez szükséges szakértelmek listájának megtekintése.</span><span class="sxs-lookup"><span data-stu-id="3b9c4-135">By creating a profile for a particular job and copying the skills, education and certificates from that job to the profile, you can quickly search workers, applicants and contact persons who match one or more of the criteria entered on the profile and view a list of the candidates whose skills most closely match the skills required for the job.</span></span>

><span data-ttu-id="3b9c4-136">**Megjegyzés** Csak a kereséshez kiválasztott dolgozók, pályázók és kapcsolattartó személyek jelennek meg a szakértelem-feltérképezés eredménylistájában és kerülnek bele szakértelemprofilba.</span><span class="sxs-lookup"><span data-stu-id="3b9c4-136">**Note** Only workers, applicants, and contact persons who are selected to be included in skill mapping searches can be displayed in a skill-mapping results list, or included in a skill profile.</span></span> <span data-ttu-id="3b9c4-137">A dolgozó, pályázó vagy kapcsolattartó személy a szakértelem-feltérképezés kereséseinek szerepeltetéséhez beállítása a **felvétel a szakértelem-feltérképezés** kiválasztási Igen, a következő lapokon:</span><span class="sxs-lookup"><span data-stu-id="3b9c4-137">To include a worker, applicant, or contact person in skill mapping searches, set the **Include in skill mapping** selection to Yes in the following pages:</span></span>

> + <span data-ttu-id="3b9c4-138">Dolgozó</span><span class="sxs-lookup"><span data-stu-id="3b9c4-138">Worker</span></span>
> + <span data-ttu-id="3b9c4-139">Alkalmazott</span><span class="sxs-lookup"><span data-stu-id="3b9c4-139">Employee</span></span>
> + <span data-ttu-id="3b9c4-140">Pályázó</span><span class="sxs-lookup"><span data-stu-id="3b9c4-140">Applicant</span></span>
> + <span data-ttu-id="3b9c4-141">Kapcsolattartók</span><span class="sxs-lookup"><span data-stu-id="3b9c4-141">Contacts</span></span>

## <a name="skill-gap-analysis-and-skill-profile-analysis"></a><span data-ttu-id="3b9c4-142">Szakértelemhiány-elemzések és szakértelemprofil-elemzések</span><span class="sxs-lookup"><span data-stu-id="3b9c4-142">Skill gap analysis and skill profile analysis</span></span>
<span data-ttu-id="3b9c4-143">Szakértelemprofil-elemzés létrehozásával egy dolgozó, pályázó vagy kapcsolattartó adott dátumon érvényes kompetenciáinak listáját tekintheti meg.</span><span class="sxs-lookup"><span data-stu-id="3b9c4-143">You can create a skill profile analysis to view a list of the competencies of a worker, applicant, or contact person as of a specific date.</span></span> <span data-ttu-id="3b9c4-144">Szakértelemhiány-elemzéssel egy személy szakértelmeit összehasonlíthatja egy adott feladathoz szükséges szakértelmi szintekkel</span><span class="sxs-lookup"><span data-stu-id="3b9c4-144">You can create a skill gap analysis to compare a person’s skills and the skills that are required for a specific job.</span></span>  



<a name="see-also"></a><span data-ttu-id="3b9c4-145">Lásd még</span><span class="sxs-lookup"><span data-stu-id="3b9c4-145">See also</span></span>
--------

[<span data-ttu-id="3b9c4-146">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="3b9c4-146">Human resources</span></span>](index.md)




