--- 
title: "Alkalmazottak felvétele változó kompenzációs konstrukcióba"
description: "A kompenzációkért és juttatásokért felelős vezető felvehet alkalmazottakat változó kompenzációs tervbe, hogy az alkalmazottak készpénzes és nem készpénzes jutalmát kiszámítsa."
author: kherr75
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: eb162e22276fc19cf11999380d551b29ba6a6d45
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="enroll-an-employee-in-a-variable-compensation-plan"></a><span data-ttu-id="2f37f-103">Alkalmazottak felvétele változó kompenzációs konstrukcióba</span><span class="sxs-lookup"><span data-stu-id="2f37f-103">Enroll an employee in a variable compensation plan</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2f37f-104">A kompenzációkért és juttatásokért felelős vezető felvehet alkalmazottakat változó kompenzációs tervbe, hogy az alkalmazottak készpénzes és nem készpénzes jutalmát kiszámítsa.</span><span class="sxs-lookup"><span data-stu-id="2f37f-104">The Compensation and Benefits manager can enrol employees in variable compensation plans to calculate cash and non-cash awards for employees.</span></span> <span data-ttu-id="2f37f-105">Ez az eljárás feltételezi, hogy a változó kompenzációs tervet úgy hozta létre, hogy a Belépés engedélyezése mező Igen értékre van állítva, és hogy létrehozott alkalmazhatósági szabályokat az adott változó kompenzációs tervhez.</span><span class="sxs-lookup"><span data-stu-id="2f37f-105">This procedure assumes that a variable compensation plan has been created with the Enable enrolment field set to Yes, and that eligibility rules have been created for that variable compensation plan.</span></span> <span data-ttu-id="2f37f-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="2f37f-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="2f37f-107">Az eljárás megkezdéséhez kattintson az Emberi Erőforrások > Dolgozók > Alkalmazottak > Kompenzáció > Változó konstrukciós felvétel lehetőségre</span><span class="sxs-lookup"><span data-stu-id="2f37f-107">To begin this procedure, go to Human resources > Workers > Employees > Compensation > Variable plan enrolment</span></span>

1. <span data-ttu-id="2f37f-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2f37f-108">Click New.</span></span>
2. <span data-ttu-id="2f37f-109">A Konstrukció mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="2f37f-109">In the Plan field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2f37f-110">A terv keresése úgy kerül szűrésre, hogy csak az alkalmazhatósági szabályok alapján megfelelő változó kompenzációs tervek jelenjenek meg az alkalmazotthoz.</span><span class="sxs-lookup"><span data-stu-id="2f37f-110">The plan lookup will be filtered to only show the variable compensation plans that the employee is eligible for based on the eligibility rules.</span></span>  
3. <span data-ttu-id="2f37f-111">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="2f37f-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="2f37f-112">Az Általános szakasz bővítésének átváltása.</span><span class="sxs-lookup"><span data-stu-id="2f37f-112">Toggle the expansion of the General section.</span></span>
5. <span data-ttu-id="2f37f-113">Adja meg a dátumot az Érvényesség dátuma mezőben.</span><span class="sxs-lookup"><span data-stu-id="2f37f-113">In the Effective date field, enter a date.</span></span>
6. <span data-ttu-id="2f37f-114">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="2f37f-114">Click Save.</span></span>
7. <span data-ttu-id="2f37f-115">A Felülír szakasz bővítésének átváltása.</span><span class="sxs-lookup"><span data-stu-id="2f37f-115">Toggle the expansion of the Overrides section.</span></span>
    * <span data-ttu-id="2f37f-116">A felvételi szabály dátumát is beállíthatja a felvételi dátum felülírásához, ha a kiválasztott változó tervben meghatározott felvételi szabály Százalék.</span><span class="sxs-lookup"><span data-stu-id="2f37f-116">Optionally, a hire rule date can be set to override the hire date for an employee when the hire rule specified for the selected variable plan is Percent.</span></span>  
    * <span data-ttu-id="2f37f-117">Ha a változó terv egy alapterv százaléka, a jutalom százaléka felülírható az alkalmazott számára.</span><span class="sxs-lookup"><span data-stu-id="2f37f-117">If the variable plan is a percent of basis plan, the award percentage can be overridden for the employee.</span></span> <span data-ttu-id="2f37f-118">Ha a változó kompenzációs terv egy egységek száma terv, az egységek száma felülírható az alkalmazottnál.</span><span class="sxs-lookup"><span data-stu-id="2f37f-118">If the variable compensation plan is a number of units plan, the number of units can be overridden for the employee.</span></span>  
    * <span data-ttu-id="2f37f-119">Ha az alkalmazottnak fix összeg jár a jutalomhoz, az összeget beállíthatja itt.</span><span class="sxs-lookup"><span data-stu-id="2f37f-119">If the employee should be given a flat amount for their award, the amount can be set here.</span></span>  
8. <span data-ttu-id="2f37f-120">A Szervezeti felülbírálások szakasz bővítésének átváltása.</span><span class="sxs-lookup"><span data-stu-id="2f37f-120">Toggle the expansion of the Organizational overrides section.</span></span>
    * <span data-ttu-id="2f37f-121">Ha az alkalmazott teljesítményét is figyelembe kell venni, a különböző részlegek teljesítménye vagy az alkalmazott beosztásától eltérő részleg esetén a részleg felülírható.</span><span class="sxs-lookup"><span data-stu-id="2f37f-121">If the employee's performance should take into consideration, the performance of different departments, or a department other than the one assigned on the employee's position, the department can be overridden.</span></span> <span data-ttu-id="2f37f-122">A Százalék oszlopban összesen 100-nak kell szerepelnie.</span><span class="sxs-lookup"><span data-stu-id="2f37f-122">The Percent column should total 100.</span></span>  

