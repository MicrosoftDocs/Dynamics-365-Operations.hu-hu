---
title: Tömeges felvételi projekt létrehozása
description: Ez az eljárás végigvezeti a tömeges felvételi projekt beállítási folyamatán.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMMassHireProject,  HRMMassHireLineCreate, HcmJobLookup, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d6d553c5762dcb456bd7178858c09129bc154349
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467049"
---
# <a name="create-a-mass-hire-project"></a><span data-ttu-id="b9e7e-103">Tömeges felvételi projekt létrehozása</span><span class="sxs-lookup"><span data-stu-id="b9e7e-103">Create a mass hire project</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



<span data-ttu-id="b9e7e-104">Ez az eljárás végigvezeti a tömeges felvételi projekt beállítási folyamatán.</span><span class="sxs-lookup"><span data-stu-id="b9e7e-104">This procedure walks through the process of setting up a mass hire project.</span></span> <span data-ttu-id="b9e7e-105">Egy toborzó a tömeges felvételi projekt segítségével könnyedén létrehozhat több beosztást, majd felvehet több dolgozót ezekre a beosztásokra.</span><span class="sxs-lookup"><span data-stu-id="b9e7e-105">A recruiter can use mass hire projects to easily create multiple positions and hire a number of workers into those positions.</span></span> <span data-ttu-id="b9e7e-106">Az eljárás megkezdéséhez ugorjon az Emberi erőforrások > Toborzás > Tömeges felvételi projektek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b9e7e-106">To begin this procedure, go to Human resources > Recruitment > Mass hire projects.</span></span> <span data-ttu-id="b9e7e-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="b9e7e-107">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="b9e7e-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b9e7e-108">Click New.</span></span>
2. <span data-ttu-id="b9e7e-109">A Tömeges felvételi projekt mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b9e7e-109">In the Mass hire project field, type a value.</span></span>
3. <span data-ttu-id="b9e7e-110">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b9e7e-110">In the Description field, type a value.</span></span>
4. <span data-ttu-id="b9e7e-111">A Projekt kezdete mezőben adjon meg dátumot.</span><span class="sxs-lookup"><span data-stu-id="b9e7e-111">In the Project start field, enter a date.</span></span>
5. <span data-ttu-id="b9e7e-112">A Projekt vége mezőben adjon meg dátumot.</span><span class="sxs-lookup"><span data-stu-id="b9e7e-112">In the Project end field, enter a date.</span></span>
6. <span data-ttu-id="b9e7e-113">Kattintson a Projekt megnyitása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b9e7e-113">Click Open project.</span></span>
7. <span data-ttu-id="b9e7e-114">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="b9e7e-114">Click Yes.</span></span>
8. <span data-ttu-id="b9e7e-115">Kattintson a beosztások létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b9e7e-115">Click Create positions.</span></span>
9. <span data-ttu-id="b9e7e-116">A Mennyiség mezőbe írja be a létrehozni kívánt beosztások számát</span><span class="sxs-lookup"><span data-stu-id="b9e7e-116">In the Quantity field, enter the number of positions that you want to create</span></span>
    * <span data-ttu-id="b9e7e-117">A kezdő dátum lesz az új dolgozók felvételi dátuma.</span><span class="sxs-lookup"><span data-stu-id="b9e7e-117">The Start date will become the Hire date for the new workers.</span></span>  
    * <span data-ttu-id="b9e7e-118">A záró dátum lesz az új dolgozók munkaviszony-megszüntetési dátuma.</span><span class="sxs-lookup"><span data-stu-id="b9e7e-118">The End date will be the Termination date for the new workers.</span></span>  
    * <span data-ttu-id="b9e7e-119">Határozza meg, hogy az új dolgozók alkalmazottak vagy alvállalkozók lesznek.</span><span class="sxs-lookup"><span data-stu-id="b9e7e-119">Specify whether the new workers will be Employees or Contractors.</span></span>  
10. <span data-ttu-id="b9e7e-120">A feladat mezőben kattintson a legördülő gombra, és válassza ki a feladatot, amelyhez beosztást kíván létrehozni.</span><span class="sxs-lookup"><span data-stu-id="b9e7e-120">In the Job field, click the drop-down button to select the job to create the positions for.</span></span>
11. <span data-ttu-id="b9e7e-121">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="b9e7e-121">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="b9e7e-122">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="b9e7e-122">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="b9e7e-123">Az alapértelmezett teljes munkaidős egyenérték a kiválasztott feladat alapján változik.</span><span class="sxs-lookup"><span data-stu-id="b9e7e-123">The default full-time equivalent value will come from the selected job.</span></span> <span data-ttu-id="b9e7e-124">Ez szükség szerint módosítható.</span><span class="sxs-lookup"><span data-stu-id="b9e7e-124">You can change this if needed.</span></span>  
    * <span data-ttu-id="b9e7e-125">Kiválaszthatja a részleget is az új beosztásokhoz.</span><span class="sxs-lookup"><span data-stu-id="b9e7e-125">Optionally, select the Department for the new positions.</span></span>  
13. <span data-ttu-id="b9e7e-126">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b9e7e-126">Click OK.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]