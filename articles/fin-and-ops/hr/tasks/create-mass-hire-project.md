--- 
title: "Tömeges felvételi projekt létrehozása"
description: "Ez az eljárás végigvezeti a tömeges felvételi projekt beállítási folyamatán."
author: kherr75
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HRMMassHireProject,  HRMMassHireLineCreate, HcmJobLookup
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: f352435f8ad04f676aa786aae4669e3586a5715c
ms.contentlocale: hu-hu
ms.lasthandoff: 09/14/2018

---
# <a name="create-a-mass-hire-project"></a><span data-ttu-id="65ef3-103">Tömeges felvételi projekt létrehozása</span><span class="sxs-lookup"><span data-stu-id="65ef3-103">Create a mass hire project</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="65ef3-104">Ez az eljárás végigvezeti a tömeges felvételi projekt beállítási folyamatán.</span><span class="sxs-lookup"><span data-stu-id="65ef3-104">This procedure walks through the process of setting up a mass hire project.</span></span> <span data-ttu-id="65ef3-105">Egy toborzó a tömeges felvételi projekt segítségével könnyedén létrehozhat több beosztást, majd felvehet több dolgozót ezekre a beosztásokra.</span><span class="sxs-lookup"><span data-stu-id="65ef3-105">A recruiter can use mass hire projects to easily create multiple positions and hire a number of workers into those positions.</span></span> <span data-ttu-id="65ef3-106">Az eljárás megkezdéséhez ugorjon az Emberi erőforrások > Toborzás > Tömeges felvételi projektek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="65ef3-106">To begin this procedure, go to Human resources > Recruitment > Mass hire projects.</span></span> <span data-ttu-id="65ef3-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="65ef3-107">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="65ef3-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="65ef3-108">Click New.</span></span>
2. <span data-ttu-id="65ef3-109">A Tömeges felvételi projekt mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="65ef3-109">In the Mass hire project field, type a value.</span></span>
3. <span data-ttu-id="65ef3-110">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="65ef3-110">In the Description field, type a value.</span></span>
4. <span data-ttu-id="65ef3-111">A Projekt kezdete mezőben adjon meg dátumot.</span><span class="sxs-lookup"><span data-stu-id="65ef3-111">In the Project start field, enter a date.</span></span>
5. <span data-ttu-id="65ef3-112">A Projekt vége mezőben adjon meg dátumot.</span><span class="sxs-lookup"><span data-stu-id="65ef3-112">In the Project end field, enter a date.</span></span>
6. <span data-ttu-id="65ef3-113">Kattintson a Projekt megnyitása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="65ef3-113">Click Open project.</span></span>
7. <span data-ttu-id="65ef3-114">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="65ef3-114">Click Yes.</span></span>
8. <span data-ttu-id="65ef3-115">Kattintson a beosztások létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="65ef3-115">Click Create positions.</span></span>
9. <span data-ttu-id="65ef3-116">A Mennyiség mezőbe írja be a létrehozni kívánt beosztások számát</span><span class="sxs-lookup"><span data-stu-id="65ef3-116">In the Quantity field, enter the number of positions that you want to create</span></span>
    * <span data-ttu-id="65ef3-117">A kezdő dátum lesz az új dolgozók felvételi dátuma.</span><span class="sxs-lookup"><span data-stu-id="65ef3-117">The Start date will become the Hire date for the new workers.</span></span>  
    * <span data-ttu-id="65ef3-118">A záró dátum lesz az új dolgozók munkaviszony-megszüntetési dátuma.</span><span class="sxs-lookup"><span data-stu-id="65ef3-118">The End date will be the Termination date for the new workers.</span></span>  
    * <span data-ttu-id="65ef3-119">Határozza meg, hogy az új dolgozók alkalmazottak vagy alvállalkozók lesznek.</span><span class="sxs-lookup"><span data-stu-id="65ef3-119">Specify whether the new workers will be Employees or Contractors.</span></span>  
10. <span data-ttu-id="65ef3-120">A feladat mezőben kattintson a legördülő gombra, és válassza ki a feladatot, amelyhez beosztást kíván létrehozni.</span><span class="sxs-lookup"><span data-stu-id="65ef3-120">In the Job field, click the drop-down button to select the job to create the positions for.</span></span>
11. <span data-ttu-id="65ef3-121">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="65ef3-121">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="65ef3-122">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="65ef3-122">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="65ef3-123">Az alapértelmezett teljes munkaidős egyenérték a kiválasztott feladat alapján változik.</span><span class="sxs-lookup"><span data-stu-id="65ef3-123">The default full-time equivalent value will come from the selected job.</span></span> <span data-ttu-id="65ef3-124">Ez szükség szerint módosítható.</span><span class="sxs-lookup"><span data-stu-id="65ef3-124">You can change this if needed.</span></span>  
    * <span data-ttu-id="65ef3-125">Kiválaszthatja a részleget is az új beosztásokhoz.</span><span class="sxs-lookup"><span data-stu-id="65ef3-125">Optionally, select the Department for the new positions.</span></span>  
13. <span data-ttu-id="65ef3-126">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="65ef3-126">Click OK.</span></span>


