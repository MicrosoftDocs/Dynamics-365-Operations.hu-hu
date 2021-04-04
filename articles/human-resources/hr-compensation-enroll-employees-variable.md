---
title: Alkalmazottak felvétele változó kompenzációs konstrukcióba
description: A kompenzációkért és juttatásokért felelős vezető felvehet alkalmazottakat változó kompenzációs tervbe, hogy az alkalmazottak készpénzes és nem készpénzes jutalmát kiszámítsa.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompVarEnrollEmpl, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f10164b4002d3cb83a2332e913adcb25506ffdd2
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5468227"
---
# <a name="enroll-an-employee-in-a-variable-compensation-plan"></a><span data-ttu-id="f3843-103">Alkalmazottak felvétele változó kompenzációs konstrukcióba</span><span class="sxs-lookup"><span data-stu-id="f3843-103">Enroll an employee in a variable compensation plan</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="f3843-104">A kompenzációkért és juttatásokért felelős vezető felvehet alkalmazottakat változó kompenzációs tervbe, hogy az alkalmazottak készpénzes és nem készpénzes jutalmát kiszámítsa.</span><span class="sxs-lookup"><span data-stu-id="f3843-104">The Compensation and Benefits manager can enroll employees in variable compensation plans to calculate cash and non-cash awards for employees.</span></span> <span data-ttu-id="f3843-105">Ez az eljárás feltételezi, hogy a változó kompenzációs tervet úgy hozta létre, hogy a Belépés engedélyezése mező Igen értékre van állítva, és hogy létrehozott alkalmazhatósági szabályokat az adott változó kompenzációs tervhez.</span><span class="sxs-lookup"><span data-stu-id="f3843-105">This procedure assumes that a variable compensation plan has been created with the Enable enrolment field set to Yes, and that eligibility rules have been created for that variable compensation plan.</span></span> <span data-ttu-id="f3843-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="f3843-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="f3843-107">Az eljárás megkezdéséhez kattintson az Emberi Erőforrások > Dolgozók > Alkalmazottak > Kompenzáció > Változó konstrukciós felvétel lehetőségre</span><span class="sxs-lookup"><span data-stu-id="f3843-107">To begin this procedure, go to Human resources > Workers > Employees > Compensation > Variable plan enrolment</span></span>

1. <span data-ttu-id="f3843-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f3843-108">Click New.</span></span>
2. <span data-ttu-id="f3843-109">A Konstrukció mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="f3843-109">In the Plan field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="f3843-110">A terv keresése úgy kerül szűrésre, hogy csak az alkalmazhatósági szabályok alapján megfelelő változó kompenzációs tervek jelenjenek meg az alkalmazotthoz.</span><span class="sxs-lookup"><span data-stu-id="f3843-110">The plan lookup will be filtered to only show the variable compensation plans that the employee is eligible for based on the eligibility rules.</span></span>  
3. <span data-ttu-id="f3843-111">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="f3843-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="f3843-112">Az Általános szakasz bővítésének átváltása.</span><span class="sxs-lookup"><span data-stu-id="f3843-112">Toggle the expansion of the General section.</span></span>
5. <span data-ttu-id="f3843-113">Adja meg a dátumot az Érvényesség dátuma mezőben.</span><span class="sxs-lookup"><span data-stu-id="f3843-113">In the Effective date field, enter a date.</span></span>
6. <span data-ttu-id="f3843-114">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="f3843-114">Click Save.</span></span>
7. <span data-ttu-id="f3843-115">A Felülír szakasz bővítésének átváltása.</span><span class="sxs-lookup"><span data-stu-id="f3843-115">Toggle the expansion of the Overrides section.</span></span>
    * <span data-ttu-id="f3843-116">A felvételi szabály dátumát is beállíthatja a felvételi dátum felülírásához, ha a kiválasztott változó tervben meghatározott felvételi szabály Százalék.</span><span class="sxs-lookup"><span data-stu-id="f3843-116">Optionally, a hire rule date can be set to override the hire date for an employee when the hire rule specified for the selected variable plan is Percent.</span></span>  
    * <span data-ttu-id="f3843-117">Ha a változó terv egy alapterv százaléka, a jutalom százaléka felülírható az alkalmazott számára.</span><span class="sxs-lookup"><span data-stu-id="f3843-117">If the variable plan is a percent of basis plan, the award percentage can be overridden for the employee.</span></span> <span data-ttu-id="f3843-118">Ha a változó kompenzációs terv egy egységek száma terv, az egységek száma felülírható az alkalmazottnál.</span><span class="sxs-lookup"><span data-stu-id="f3843-118">If the variable compensation plan is a number of units plan, the number of units can be overridden for the employee.</span></span>  
    * <span data-ttu-id="f3843-119">Ha az alkalmazottnak fix összeg jár a jutalomhoz, az összeget beállíthatja itt.</span><span class="sxs-lookup"><span data-stu-id="f3843-119">If the employee should be given a flat amount for their award, the amount can be set here.</span></span>  
8. <span data-ttu-id="f3843-120">A Szervezeti felülbírálások szakasz bővítésének átváltása.</span><span class="sxs-lookup"><span data-stu-id="f3843-120">Toggle the expansion of the Organizational overrides section.</span></span>
    * <span data-ttu-id="f3843-121">Ha az alkalmazott teljesítményét is figyelembe kell venni, a különböző részlegek teljesítménye vagy az alkalmazott beosztásától eltérő részleg esetén a részleg felülírható.</span><span class="sxs-lookup"><span data-stu-id="f3843-121">If the employee's performance should take into consideration, the performance of different departments, or a department other than the one assigned on the employee's position, the department can be overridden.</span></span> <span data-ttu-id="f3843-122">A Százalék oszlopban összesen 100-nak kell szerepelnie.</span><span class="sxs-lookup"><span data-stu-id="f3843-122">The Percent column should total 100.</span></span>  



[!INCLUDE[footer-include](../includes/footer-banner.md)]