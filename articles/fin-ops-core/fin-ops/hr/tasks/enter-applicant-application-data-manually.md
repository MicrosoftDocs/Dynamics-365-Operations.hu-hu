---
title: Pályázók és a pályázatok adatainak manuális megadása
description: Ez az eljárás bemutatja, hogyan lehet manuálisan karbantartani a pályázóval és pályázatukkal kapcsolatos információkat.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmApplicant, LogisticsContactInfoGrid, HRMApplication,  DirPartyTable
audience: Application User
ms.reviewer: anbichse
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2ea39e86ace40cd8e3ad2733b7f7f7a873a963e7
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693040"
---
# <a name="enter-applicant-and-application-data-manually"></a><span data-ttu-id="932c2-103">Pályázók és a pályázatok adatainak manuális megadása</span><span class="sxs-lookup"><span data-stu-id="932c2-103">Enter applicant and application data manually</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="932c2-104">Ez az eljárás bemutatja, hogyan lehet manuálisan karbantartani a pályázóval és pályázatukkal kapcsolatos információkat.</span><span class="sxs-lookup"><span data-stu-id="932c2-104">This procedure shows how to manually maintain information about applicants and their application.</span></span>   <span data-ttu-id="932c2-105">Megadhat és karban tarthat személyes információkat, állásinterjú dátumokat és időpontokat, referenciákat, kompetenciákat és a pályázó kérvényeit.</span><span class="sxs-lookup"><span data-stu-id="932c2-105">You can enter and maintain personal information, interview dates and times, references, competencies, and accommodation requests for applicants.</span></span> <span data-ttu-id="932c2-106">Frissítheti a pályázó alkalmazási pályázatának állapotát, és leveleket vagy e-mail üzeneteket írhat, hogy kommunikáljon a pályázóval.</span><span class="sxs-lookup"><span data-stu-id="932c2-106">You can also update the status of applicants' applications for employment and create letters or email messages to communicate with applicants.</span></span> <span data-ttu-id="932c2-107">Ha létrehoz egy pályázói rekordot, egy személyes rekord jön létre a pályázószámára a globális címjegyzékben.</span><span class="sxs-lookup"><span data-stu-id="932c2-107">When you create an applicant record, a person record for that applicant is created in the global address book.</span></span>       <span data-ttu-id="932c2-108">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="932c2-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-new-applicant-record"></a><span data-ttu-id="932c2-109">Új pályázói rekord létrehozása</span><span class="sxs-lookup"><span data-stu-id="932c2-109">Create a new applicant record</span></span>
1. <span data-ttu-id="932c2-110">Ugorjon az Emberi erőforrások > Toborzás > Pályázók > Pályázók lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="932c2-110">Go to Human resources > Recruitment > Applicants > Applicants.</span></span>
2. <span data-ttu-id="932c2-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="932c2-111">Click New.</span></span>
3. <span data-ttu-id="932c2-112">Az Utónév mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="932c2-112">In the First name field, type a value.</span></span>
4. <span data-ttu-id="932c2-113">A Vezetéknéve mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="932c2-113">In the Last name field, type a value.</span></span>
    * <span data-ttu-id="932c2-114">További pályázói információkat is megadhat, ha ezek rendelkezésre állnak.</span><span class="sxs-lookup"><span data-stu-id="932c2-114">You can enter additional applicant information if it's available.</span></span> <span data-ttu-id="932c2-115">Például ezek közé tartozhat a pályázó legmagasabb iskolai végzettsége, jelenlegi beosztása vagy korábbi munkaadója.</span><span class="sxs-lookup"><span data-stu-id="932c2-115">For example, information can include the applicant's highest degree, current job title, or previous employer.</span></span>  
5. <span data-ttu-id="932c2-116">Bontsa ki a Kapcsolattartási adatok részt.</span><span class="sxs-lookup"><span data-stu-id="932c2-116">Toggle the expansion of the Contact information section.</span></span>
6. <span data-ttu-id="932c2-117">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="932c2-117">Click Add.</span></span>
7. <span data-ttu-id="932c2-118">A Leírás mezőbe írja be az „Kommunikáció e-mailen” szöveget.</span><span class="sxs-lookup"><span data-stu-id="932c2-118">In the Description field, type 'Communications email'.</span></span>
8. <span data-ttu-id="932c2-119">A Típus mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="932c2-119">In the Type field, select an option.</span></span>
9. <span data-ttu-id="932c2-120">Írjon be egy értéket a Kapcsolattartó száma/címe mezőbe.</span><span class="sxs-lookup"><span data-stu-id="932c2-120">In the Contact number/address field, type a value.</span></span>
    * <span data-ttu-id="932c2-121">Ezt az e-mail címet használja majd a rendszer a pályázóval folytatott kommunikációra.</span><span class="sxs-lookup"><span data-stu-id="932c2-121">This email address will be used to generate email communication with the applicant.</span></span>  
10. <span data-ttu-id="932c2-122">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="932c2-122">Click Add.</span></span>
11. <span data-ttu-id="932c2-123">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="932c2-123">In the Description field, type a value.</span></span>
12. <span data-ttu-id="932c2-124">Írjon be egy értéket a Kapcsolattartó száma/címe mezőbe.</span><span class="sxs-lookup"><span data-stu-id="932c2-124">In the Contact number/address field, type a value.</span></span>
    * <span data-ttu-id="932c2-125">A pályázó személyes információi.</span><span class="sxs-lookup"><span data-stu-id="932c2-125">Applicant personal information.</span></span>  
    * <span data-ttu-id="932c2-126">További személyes adatokat adhat meg a pályázóról, ha szükséges.</span><span class="sxs-lookup"><span data-stu-id="932c2-126">You can enter additional personal information for the applicant, if needed.</span></span> <span data-ttu-id="932c2-127">Például ezek közé tartozhat a születési dátum, az etnikai háttér, a nem vagy a családi állapot.</span><span class="sxs-lookup"><span data-stu-id="932c2-127">For example, this can include birth date, ethnic origin, gender, or marital status.</span></span>  
13. <span data-ttu-id="932c2-128">A Művelet panelen kattintson a Kompetenciák elemre.</span><span class="sxs-lookup"><span data-stu-id="932c2-128">On the Action Pane, click Competencies.</span></span>
    * <span data-ttu-id="932c2-129">Kitöltheti a pályázó kompetenciaprofilját, beleértve készségeit, szakmai tapasztalatát, oktatását, tesztjeit vagy bizonyítványait.</span><span class="sxs-lookup"><span data-stu-id="932c2-129">You can enter the applicant's competency profile, including their skills, professional experiences, education, tests, or certificates.</span></span>  
    * <span data-ttu-id="932c2-130">Ezekkel az információkkal összehasonlíthatók a pályázó képességei a cég adatbázisában a feladathoz rendelt képességekkel.</span><span class="sxs-lookup"><span data-stu-id="932c2-130">This information can be used to map the applicant's skills to the skills associated with the jobs defined in your company's data.</span></span>   

## <a name="create-an-application-for-the-applicant"></a><span data-ttu-id="932c2-131">Pályázat létrehozása a pályázónak</span><span class="sxs-lookup"><span data-stu-id="932c2-131">Create an application for the applicant</span></span>
1. <span data-ttu-id="932c2-132">Kattintson a Pályázatok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="932c2-132">Click Applications.</span></span>
2. <span data-ttu-id="932c2-133">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="932c2-133">Click New.</span></span>
3. <span data-ttu-id="932c2-134">A Toborzási projekt mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="932c2-134">In the Recruitment project field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="932c2-135">A toborzási projekt kiválasztásával a pályázót a projekt egyik üresedéséhez rendelik.</span><span class="sxs-lookup"><span data-stu-id="932c2-135">By selecting a recruitment project, the applicant will be associated with a specific opening included in that recruitment project.</span></span>  
4. <span data-ttu-id="932c2-136">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="932c2-136">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="932c2-137">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="932c2-137">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="932c2-138">Alapértelmezés szerint a feladat és a részleg a kiválasztott toborzási projekten alapul.</span><span class="sxs-lookup"><span data-stu-id="932c2-138">By default, the job and department are based on the selected recruitment project.</span></span>  
6. <span data-ttu-id="932c2-139">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="932c2-139">Click Save.</span></span>
    * <span data-ttu-id="932c2-140">Az alkalmazás elmentése után dokumentumokat adhat hozzá, beleértve a pályázó tapasztalatát, díjait és motivációs levelét.</span><span class="sxs-lookup"><span data-stu-id="932c2-140">After saving the application, you can attach documents to it, including the applicant's experience, awards, and cover letter.</span></span>  

