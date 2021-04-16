---
title: Jelentkezők kiválasztására szolgáló eszközök azonosítása és rendszerbe állítása
description: Nehéz megfelelően képzett személyeket találni bizonyos pozíciók betöltésére, különösen, ha az a pozíció különleges képességeket igényel.
author: andreabichsel
ms.date: 11/20/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkillMapping, HcmJobLookup, HcmSkillMappingLine, HcmPersonCertificate, CCHTMLPrintPreview
audience: Application User
ms.reviewer: anbichse
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a9e0b300692d817024455c669c226a81e601366e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751910"
---
# <a name="identify-and-deploy-candidate-selection-tools"></a><span data-ttu-id="3fc6b-103">Jelentkezők kiválasztására szolgáló eszközök azonosítása és rendszerbe állítása</span><span class="sxs-lookup"><span data-stu-id="3fc6b-103">Identify and deploy candidate selection tools</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3fc6b-104">Nehéz megfelelően képzett személyeket találni bizonyos pozíciók betöltésére, különösen, ha az a pozíció különleges képességeket igényel.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-104">Finding a qualified pool of candidates to fill vacancies can be difficult, especially when a position requires a unique set of skills.</span></span>  <span data-ttu-id="3fc6b-105">Azonban lehet, hogy a megfelelő képzettségű pályázók már az ön szervezeténél dolgoznak.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-105">However, candidates with the skills you need might already be employed in your organization.</span></span> <span data-ttu-id="3fc6b-106">Rákereshet egy adott szakértelemre a meglévő alkalmazottak és az új pályázók között.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-106">You can search for a specific skill set among existing employees, or new applicants.</span></span> <span data-ttu-id="3fc6b-107">Ez lehetővé teszi, hogy a toborzó gyorsan megszűrhesse és összegyűjthesse a pályázókat, akik most vagy a múltban pályáztak egy nyitott pozícióra, vagy hogy a meglévő alkalmazottak közül találjon valakit.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-107">This allows a recruiter to quickly gather and screen applicants who have applied for open position now or in the past, or to find potential candidates from their existing pool of employees.</span></span> <span data-ttu-id="3fc6b-108">A feladatrögzítés segítségével megtudhatja, hogy a Szakértelem feltérképezése funkció hogyan segíti önt a megfelelő személy megtalálásában egy nyitott pozícióra.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-108">Use this task recording to learn how the skill mapping functionality can help you find the right person for an open position.</span></span> <span data-ttu-id="3fc6b-109">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-109">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="3fc6b-110">Ugrás az Emberi erőforrások > Szakértelem > Szakértelem elemzése > Szakértelem-feltérképezési profilok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-110">Go to Human resources > Competencies > Skill analysis > Skill mapping profiles.</span></span>
2. <span data-ttu-id="3fc6b-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-111">Click New.</span></span>
3. <span data-ttu-id="3fc6b-112">A szakértelem-feltérképezéshez adjon meg egy nevet a Szakértelem feltérképezése mezőben.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-112">In the Skill mapping field, enter a name for your skill mapping.</span></span>  <span data-ttu-id="3fc6b-113">Például: könyvelő.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-113">Example: Accountant.</span></span>
4. <span data-ttu-id="3fc6b-114">A Leírás mezőbe írja be a szakértelem-feltérképezés leírását.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-114">In the Description field, enter a description of the skill mapping..</span></span>
5. <span data-ttu-id="3fc6b-115">Adja meg a dátumot a Dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-115">In the Date field, enter a date.</span></span>
6. <span data-ttu-id="3fc6b-116">Kattintson a Profil beolvasására.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-116">Click Retrieve profile.</span></span>
    * <span data-ttu-id="3fc6b-117">A profil beolvasása segítségével a Diploma, Szakértelem, Végzettség adatokban a kijelölt Személy, Feladat vagy Tanfolyam közül kérhet elemet a keresés alapjára vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-117">Use Retrieve profile to pull in the Certificate, Skill, and Education data from a selected Person, Job or Course as the basis for your search.</span></span>   <span data-ttu-id="3fc6b-118">Ezután hozzáadhat vagy távolítsa el a feltételeket, ha a feltétel nem kötelező, és rangsorolja a feltételek fontosságát.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-118">You can then add or remove criteria, state if the criteria is optional and rank the importance of the criteria.</span></span>  
7. <span data-ttu-id="3fc6b-119">Kattintson a Munkára.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-119">Click Job.</span></span>
8. <span data-ttu-id="3fc6b-120">A Munka mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-120">In the Job field, enter or select a value.</span></span>
9. <span data-ttu-id="3fc6b-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-121">Click OK.</span></span>
10. <span data-ttu-id="3fc6b-122">Bontsa ki Tartomány gyorslapot, és adjon meg további információkat, például részleg.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-122">Expand the Range FastTab, and add any additional information, such as department.</span></span>
11. <span data-ttu-id="3fc6b-123">Bontsa ki a Tanúsítványok gyorslapot a diplomák megjelenítéséhez és szerkesztéséhez.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-123">Expand the Certificates FastTab to view or edit the certificates.</span></span>
12. <span data-ttu-id="3fc6b-124">Bontsa ki a Szakértelmek gyorslapot a Szakértelmek megjelenítéséhez és szerkesztéséhez.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-124">Expand the Skills FastTab to view or edit the skills.</span></span>
13. <span data-ttu-id="3fc6b-125">Bontsa ki a Képzettség gyorslapot a képzettségi kritériumok megjelenítéséhez és szerkesztéséhez.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-125">Expand the Education FastTab to view or edit the education criteria.</span></span>
14. <span data-ttu-id="3fc6b-126">Kattintson a végrehajtásra.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-126">Click Execute.</span></span>
15. <span data-ttu-id="3fc6b-127">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-127">Click OK.</span></span>
16. <span data-ttu-id="3fc6b-128">Kattintson az Eredményre.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-128">Click Result.</span></span>
17. <span data-ttu-id="3fc6b-129">Kattintson az Eredményre.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-129">Click Result.</span></span>
18. <span data-ttu-id="3fc6b-130">Kattintson az Önéletrajzra.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-130">Click Resume.</span></span>
19. <span data-ttu-id="3fc6b-131">Kattintson a Bizonyítványokra.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-131">Click Certificates.</span></span>
    * <span data-ttu-id="3fc6b-132">Minden megjelenő személy esetében külön megtekintheti a végzettséggel, szakértelemmel és szakmai tapasztalattal kapcsolatos részletes információkat.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-132">You can drill further into each person listed and see details regarding their education, skills, and professional experience.</span></span>  
20. <span data-ttu-id="3fc6b-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-133">Close the page.</span></span>
21. <span data-ttu-id="3fc6b-134">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-134">Close the page.</span></span>
22. <span data-ttu-id="3fc6b-135">Válassza ki újra az eredményt.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-135">Select result again.</span></span>
23. <span data-ttu-id="3fc6b-136">Kattintson a Jelentésre.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-136">Click Report.</span></span>
    * <span data-ttu-id="3fc6b-137">A jelentés a legjobb találatokat felül mutatja.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-137">The report will list the best matches at the top of the report.</span></span>  <span data-ttu-id="3fc6b-138">Megtekintheti, hogy van-e hiányelem felsorolva.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-138">You can see that a gap element is listed.</span></span>  <span data-ttu-id="3fc6b-139">Ez az elem az eltérést jelzi a szakértelem feltérképezésén felsorolt szint és a személy szakértelmének szintje között.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-139">This is the difference between the level that was listed on the skill mapping, and the level of the skill that is assigned to the person.</span></span>  
24. <span data-ttu-id="3fc6b-140">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-140">Close the page.</span></span>
25. <span data-ttu-id="3fc6b-141">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="3fc6b-141">Click Save.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]