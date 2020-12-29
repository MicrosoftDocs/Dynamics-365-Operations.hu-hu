---
title: Életesemények feldolgozása
description: A Microsoft Dynamics 365 Human Resources alkalmazotti életciklusa során minden alkalmazott találkozhat különböző életeseményekkel kapcsolatos változásokkal.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes, BenefitEligibilityProcessResultViewer
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ada986888a22afe83885985a694cd00ff94c9217
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418799"
---
# <a name="process-life-events"></a><span data-ttu-id="a2a8e-103">Életesemények feldolgozása</span><span class="sxs-lookup"><span data-stu-id="a2a8e-103">Process life events</span></span>

<span data-ttu-id="a2a8e-104">A Microsoft Dynamics 365 Human Resources alkalmazotti életciklusa során minden alkalmazott találkozhat különböző életeseményekkel kapcsolatos változásokkal.</span><span class="sxs-lookup"><span data-stu-id="a2a8e-104">During the employee lifecycle in Microsoft Dynamics 365 Human Resources, each employee may encounter various life event changes.</span></span> <span data-ttu-id="a2a8e-105">Például a házasság, a foglalkoztatás változása vagy a függő fél/kedvezményezett változása.</span><span class="sxs-lookup"><span data-stu-id="a2a8e-105">For example, marriage, change in employment, or dependent/beneficiary change.</span></span> <span data-ttu-id="a2a8e-106">Az életesemények használatához engedélyeznie kell az életeseményeket a juttatás paraméterei űrlapon, be kell állítania az életesemény típusát, és be kell állítania a terv típusára vonatkozó beállításokat.</span><span class="sxs-lookup"><span data-stu-id="a2a8e-106">To use life events, you must enable life events in the benefits parameters form, set up life event types, and set up life event options for plan types.</span></span>

<span data-ttu-id="a2a8e-107">Az életesemények feldolgozása előtt a felvételi időkereten belül már legalább egyszer futtatni kell a nyitott jelentkezést.</span><span class="sxs-lookup"><span data-stu-id="a2a8e-107">Before you can process life events, you must have already run open enrollment at least once during a hiring time frame.</span></span> <span data-ttu-id="a2a8e-108">Az Egyesült Államokban a nyitott jelentkezés általában évente egyszer történik.</span><span class="sxs-lookup"><span data-stu-id="a2a8e-108">In the United States, open enrollment is typically once per year.</span></span> <span data-ttu-id="a2a8e-109">Az Egyesült Államokon kívül nyitott jelentkezés a felvételkor történik.</span><span class="sxs-lookup"><span data-stu-id="a2a8e-109">Outside the United States, open enrollment may be run at the time of hire.</span></span> <span data-ttu-id="a2a8e-110">A dolgozónak nem kell kiválasztania juttatási tervet az életesemények feldolgozásához, viszont a nyitott jelentkezés feldolgozásakor szerepelniük kell.</span><span class="sxs-lookup"><span data-stu-id="a2a8e-110">A worker does not need to select a benefit plan in order for life events to be processed, but they need to have been included in open enrollment processing.</span></span> 

<span data-ttu-id="a2a8e-111">Az életesemény feldolgozását akkor érdemes használni, ha olyan alkalmazottai vannak, akiknél a jövőben történik életesemény.</span><span class="sxs-lookup"><span data-stu-id="a2a8e-111">Use life event processing when you have workers who have life events that take place on a future date.</span></span> <span data-ttu-id="a2a8e-112">Ez az esemény feldolgozza az összes olyan életeseményt, amelyeket nem dolgoztak fel (például a jövőbeli életeseményeket, illetve olyan életeseményeket, amelyek nem egyetlen dolgozóra jellemzőek – például egy új juttatás).</span><span class="sxs-lookup"><span data-stu-id="a2a8e-112">This event will process all life events that have not been processed (like future life events, or life events that have been added that are not specific to any one worker – one example is a new benefit).</span></span> <span data-ttu-id="a2a8e-113">A valós idejű életesemények el vannak rejtve.</span><span class="sxs-lookup"><span data-stu-id="a2a8e-113">Real-time life events are hidden.</span></span>

<span data-ttu-id="a2a8e-114">Ha például ma február elseje van, és február 14-én Joe Smith dolgozónak időpontja van a jogi személyiségével kapcsolatos módosításra, a február 15-én futtatott eseményfeldolgozás során a rendszer feldolgoz minden, február 15-ig történt eseményt.</span><span class="sxs-lookup"><span data-stu-id="a2a8e-114">For example, if today is February 1, and on February 14 worker Joe Smith is scheduled to change legal entities, if you run life event processing for February 15, the system processes all events up until February 15.</span></span> 

1. <span data-ttu-id="a2a8e-115">A **Juttatások kezelése** munkaterületen, amely a **Feldolgozás** menüpontban található, válassza az **Életesemény feldolgozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2a8e-115">In the **Benefits management** workspace, under **Processing**, select **Life event processing**.</span></span>

2. <span data-ttu-id="a2a8e-116">Az **Életeseményre vonatkozó folyamat futtatása** párbeszédpanelben adja meg a következő mezők értékeit:</span><span class="sxs-lookup"><span data-stu-id="a2a8e-116">In the **Run life event process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="a2a8e-117">Mező</span><span class="sxs-lookup"><span data-stu-id="a2a8e-117">Field</span></span> | <span data-ttu-id="a2a8e-118">Leírás</span><span class="sxs-lookup"><span data-stu-id="a2a8e-118">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="a2a8e-119">**Regisztrációs időszak**</span><span class="sxs-lookup"><span data-stu-id="a2a8e-119">**Enrollment period**</span></span> | <span data-ttu-id="a2a8e-120">Az életesemények feldolgozására szolgáló beléptetési időszak.</span><span class="sxs-lookup"><span data-stu-id="a2a8e-120">The enrollment period to process life events for.</span></span> |
   | <span data-ttu-id="a2a8e-121">**Jogi személy**</span><span class="sxs-lookup"><span data-stu-id="a2a8e-121">**Legal entity**</span></span> | <span data-ttu-id="a2a8e-122">Jogi személy, amelynek életeseményre vonatkozó feldolgozásra van szüksége.</span><span class="sxs-lookup"><span data-stu-id="a2a8e-122">The legal entity to process life events for.</span></span> |
   | <span data-ttu-id="a2a8e-123">**Életesemény dátuma**</span><span class="sxs-lookup"><span data-stu-id="a2a8e-123">**Life event date**</span></span> | <span data-ttu-id="a2a8e-124">A rendszer feldolgozza az összes mai napig esedékes eseményt a belépési időszakban.</span><span class="sxs-lookup"><span data-stu-id="a2a8e-124">The system processes all events during the enrollment period that occur up until this date.</span></span> |
   | <span data-ttu-id="a2a8e-125">**Dolgozó**</span><span class="sxs-lookup"><span data-stu-id="a2a8e-125">**Worker**</span></span> | <span data-ttu-id="a2a8e-126">Az a dolgozó, akivel kapcsolatban fel kell dolgozni az életeseményt.</span><span class="sxs-lookup"><span data-stu-id="a2a8e-126">The worker to process life events for.</span></span> <span data-ttu-id="a2a8e-127">Ha ezt a mezőt üresen hagyja, a program minden dolgozónál feldolgozza az életeseményeket.</span><span class="sxs-lookup"><span data-stu-id="a2a8e-127">If you leave this field blank, life events will be processed for all workers.</span></span> |

3. <span data-ttu-id="a2a8e-128">Ha a háttérben szeretné futtatni a folyamatot, válassza a **Futtatás a háttérben** parancsot, majd hajtsa végre a következő műveleteket:</span><span class="sxs-lookup"><span data-stu-id="a2a8e-128">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="a2a8e-129">Információk megadása a folyamathoz.</span><span class="sxs-lookup"><span data-stu-id="a2a8e-129">Enter information for the process.</span></span>

   2. <span data-ttu-id="a2a8e-130">Ismétlődő feladat beállításához jelölje be az **Ismétlődés** jelölőnégyzetet, adja meg az ismétlődési adatokat, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="a2a8e-130">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="a2a8e-131">A munkafigyelmeztetések beállításához jelölje ki a **Figyelmeztetések** lehetőséget, válassza ki, hogy milyen figyelmeztetéseket akar kapni ezzel kapcsolatban, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="a2a8e-131">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="a2a8e-132">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2a8e-132">Select **OK**.</span></span> <span data-ttu-id="a2a8e-133">A folyamat a megadott paraméterekkel fog futni.</span><span class="sxs-lookup"><span data-stu-id="a2a8e-133">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="a2a8e-134">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2a8e-134">Select **OK**.</span></span>
