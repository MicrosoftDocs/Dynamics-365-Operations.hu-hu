---
title: Alkalmazottak felvétele fix kompenzációs konstrukcióba
description: A kompenzációkért és juttatásokért felelős vezető kijelölhet alkalmazottakat fix kompenzációs tervre az alapfizetésük kezelése érdekében.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompFixedEmpl, HRMCompFixedEmplActionDialog, HcmPositionLookup, HRMCompRefPointLookup
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ee0ba197ee47d2a2da2372b12291e5625ddc9ba1
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/19/2019
ms.locfileid: "859943"
---
# <a name="enroll-an-employee-in-a-fixed-compensation-plan"></a><span data-ttu-id="ff1d5-103">Alkalmazottak felvétele fix kompenzációs konstrukcióba</span><span class="sxs-lookup"><span data-stu-id="ff1d5-103">Enroll an employee in a fixed compensation plan</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ff1d5-104">A kompenzációkért és juttatásokért felelős vezető kijelölhet alkalmazottakat fix kompenzációs tervre az alapfizetésük kezelése érdekében.</span><span class="sxs-lookup"><span data-stu-id="ff1d5-104">The compensation and benefits manager can assign employees to fixed compensation plans to manage their base pay.</span></span> <span data-ttu-id="ff1d5-105">Ez az eljárás feltételezi, hogy a fix terv létrehozása és aktiválás megtörtént, és hogy beállított alkalmazhatósági szabályokat a tervhez.</span><span class="sxs-lookup"><span data-stu-id="ff1d5-105">This procedure assumes that a fixed plan has been created and is active, and that eligibility rules have been set for the plan.</span></span> <span data-ttu-id="ff1d5-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="ff1d5-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="ff1d5-107">Az eljárás megkezdéséhez kattintson a HR > Dolgozók > Alkalmazottak > Kompenzáció > Fix terv lehetőségre</span><span class="sxs-lookup"><span data-stu-id="ff1d5-107">To begin the procedure, go to Human resources > Workers > Employees > Compensation > Fixed plan</span></span>

1. <span data-ttu-id="ff1d5-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ff1d5-108">Click New.</span></span>
2. <span data-ttu-id="ff1d5-109">A Művelet mezőben válasszon ki egy fix kompenzációs műveletet vagy írja be a felvétel/újrafelvétel lehetőséget az alkalmazott kompenzációmódosításának leírásához.</span><span class="sxs-lookup"><span data-stu-id="ff1d5-109">In the Action field, select a Fixed compensation action of type Hire/Rehire to describe the change in the employee's compensation.</span></span>
3. <span data-ttu-id="ff1d5-110">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="ff1d5-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="ff1d5-111">A Beosztás mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="ff1d5-111">In the Position field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="ff1d5-112">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="ff1d5-112">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ff1d5-113">A megjelenített szint a Pozícióban lévő feladat Kompenzációs szintéből származik.</span><span class="sxs-lookup"><span data-stu-id="ff1d5-113">The level that's displayed is from the Compensation Level of the Job on the Position.</span></span> <span data-ttu-id="ff1d5-114">Az alkalmazotthoz csak akkor lehet kompenzációt rendelni, ha beállította a szintet a feladathoz.</span><span class="sxs-lookup"><span data-stu-id="ff1d5-114">The level must be set on the Job before compensation can be assigned to the employee.</span></span>  
6. <span data-ttu-id="ff1d5-115">A Terv mezőben válassza ki a fix kompenzációs tervet az alkalmazotthoz.</span><span class="sxs-lookup"><span data-stu-id="ff1d5-115">In the Plan field, select the fixed compensation plan for the employee.</span></span> <span data-ttu-id="ff1d5-116">A Terv keresése szűrve van, hogy csak az alkalmazhatósági szabályok alapján megfelelő tervek jelenjenek meg az alkalmazotthoz.</span><span class="sxs-lookup"><span data-stu-id="ff1d5-116">The Plan lookup is filtered to show only the plans that the employee is eligible for based on the Eligibility rules.</span></span>
7. <span data-ttu-id="ff1d5-117">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="ff1d5-117">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="ff1d5-118">A kompenzáció érvényesség dátuma és a lejárati dátum alapértelmezés szerint a dolgozó beosztásának kezdeti és záró dátumától függ.</span><span class="sxs-lookup"><span data-stu-id="ff1d5-118">The Effective and Expiration dates for the compensation default from the start and end dates for the worker's position assignment.</span></span> <span data-ttu-id="ff1d5-119">Ezek a dátumok szükség szerint módosíthatók.</span><span class="sxs-lookup"><span data-stu-id="ff1d5-119">You can adjust these dates as needed.</span></span>  
    * <span data-ttu-id="ff1d5-120">Ha a fix kompenzációs terv lépés típusú terv, válassza ki az alkalmazott fizetési díját tartalmazó megfelelő lépést.</span><span class="sxs-lookup"><span data-stu-id="ff1d5-120">If the Fixed compensation plan is a step plan, select the step containing the correct pay rate for the employee.</span></span> <span data-ttu-id="ff1d5-121">Ha a fix kompenzációs terv fokozatos vagy széles sávú konstrukciójú terv, írja be az alkalmazott fizetési díját.</span><span class="sxs-lookup"><span data-stu-id="ff1d5-121">If the fixed compensation plan is a grade or a band plan, enter the pay rate for the employee.</span></span> <span data-ttu-id="ff1d5-122">A fizetési díj a terv tűrési beállításai, valamint a feladat kompenzációs szintjének minimum és maximum referenciapontjai szerint kerül ellenőrzésre.</span><span class="sxs-lookup"><span data-stu-id="ff1d5-122">The pay rate will be validated against the tolerance settings for the plan, and the minimum and maximum reference points for the job's compensation level.</span></span>  
8. <span data-ttu-id="ff1d5-123">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="ff1d5-123">Click OK.</span></span>

