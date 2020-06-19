---
title: Tömeges felvételi projekt létrehozása
description: Ez az eljárás végigvezeti a tömeges felvételi projekt beállítási folyamatán.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMMassHireProject,  HRMMassHireLineCreate, HcmJobLookup, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8ddcfd531e7b5c76ac4b15cee54880f6868a73f1
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2020
ms.locfileid: "3428851"
---
# <a name="create-a-mass-hire-project"></a><span data-ttu-id="c5956-103">Tömeges felvételi projekt létrehozása</span><span class="sxs-lookup"><span data-stu-id="c5956-103">Create a mass hire project</span></span>



<span data-ttu-id="c5956-104">Ez az eljárás végigvezeti a tömeges felvételi projekt beállítási folyamatán.</span><span class="sxs-lookup"><span data-stu-id="c5956-104">This procedure walks through the process of setting up a mass hire project.</span></span> <span data-ttu-id="c5956-105">Egy toborzó a tömeges felvételi projekt segítségével könnyedén létrehozhat több beosztást, majd felvehet több dolgozót ezekre a beosztásokra.</span><span class="sxs-lookup"><span data-stu-id="c5956-105">A recruiter can use mass hire projects to easily create multiple positions and hire a number of workers into those positions.</span></span> <span data-ttu-id="c5956-106">Az eljárás megkezdéséhez ugorjon az Emberi erőforrások > Toborzás > Tömeges felvételi projektek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c5956-106">To begin this procedure, go to Human resources > Recruitment > Mass hire projects.</span></span> <span data-ttu-id="c5956-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="c5956-107">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="c5956-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c5956-108">Click New.</span></span>
2. <span data-ttu-id="c5956-109">A Tömeges felvételi projekt mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5956-109">In the Mass hire project field, type a value.</span></span>
3. <span data-ttu-id="c5956-110">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5956-110">In the Description field, type a value.</span></span>
4. <span data-ttu-id="c5956-111">A Projekt kezdete mezőben adjon meg dátumot.</span><span class="sxs-lookup"><span data-stu-id="c5956-111">In the Project start field, enter a date.</span></span>
5. <span data-ttu-id="c5956-112">A Projekt vége mezőben adjon meg dátumot.</span><span class="sxs-lookup"><span data-stu-id="c5956-112">In the Project end field, enter a date.</span></span>
6. <span data-ttu-id="c5956-113">Kattintson a Projekt megnyitása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c5956-113">Click Open project.</span></span>
7. <span data-ttu-id="c5956-114">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="c5956-114">Click Yes.</span></span>
8. <span data-ttu-id="c5956-115">Kattintson a beosztások létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c5956-115">Click Create positions.</span></span>
9. <span data-ttu-id="c5956-116">A Mennyiség mezőbe írja be a létrehozni kívánt beosztások számát</span><span class="sxs-lookup"><span data-stu-id="c5956-116">In the Quantity field, enter the number of positions that you want to create</span></span>
    * <span data-ttu-id="c5956-117">A kezdő dátum lesz az új dolgozók felvételi dátuma.</span><span class="sxs-lookup"><span data-stu-id="c5956-117">The Start date will become the Hire date for the new workers.</span></span>  
    * <span data-ttu-id="c5956-118">A záró dátum lesz az új dolgozók munkaviszony-megszüntetési dátuma.</span><span class="sxs-lookup"><span data-stu-id="c5956-118">The End date will be the Termination date for the new workers.</span></span>  
    * <span data-ttu-id="c5956-119">Határozza meg, hogy az új dolgozók alkalmazottak vagy alvállalkozók lesznek.</span><span class="sxs-lookup"><span data-stu-id="c5956-119">Specify whether the new workers will be Employees or Contractors.</span></span>  
10. <span data-ttu-id="c5956-120">A feladat mezőben kattintson a legördülő gombra, és válassza ki a feladatot, amelyhez beosztást kíván létrehozni.</span><span class="sxs-lookup"><span data-stu-id="c5956-120">In the Job field, click the drop-down button to select the job to create the positions for.</span></span>
11. <span data-ttu-id="c5956-121">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="c5956-121">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="c5956-122">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="c5956-122">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="c5956-123">Az alapértelmezett teljes munkaidős egyenérték a kiválasztott feladat alapján változik.</span><span class="sxs-lookup"><span data-stu-id="c5956-123">The default full-time equivalent value will come from the selected job.</span></span> <span data-ttu-id="c5956-124">Ez szükség szerint módosítható.</span><span class="sxs-lookup"><span data-stu-id="c5956-124">You can change this if needed.</span></span>  
    * <span data-ttu-id="c5956-125">Kiválaszthatja a részleget is az új beosztásokhoz.</span><span class="sxs-lookup"><span data-stu-id="c5956-125">Optionally, select the Department for the new positions.</span></span>  
13. <span data-ttu-id="c5956-126">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c5956-126">Click OK.</span></span>

