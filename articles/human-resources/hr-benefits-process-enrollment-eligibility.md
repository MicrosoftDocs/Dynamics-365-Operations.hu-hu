---
title: Felvételi jogosultság feldolgozása
description: Ez a cikk bemutatja, hogyan kell futtatni a felvételi jogosultsági folyamatot.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1d978982213e713e362798c49aa57e6dc8b7a862
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/06/2020
ms.locfileid: "3230016"
---
# <a name="process-enrollment-eligibility"></a><span data-ttu-id="0055c-103">Felvételi jogosultság feldolgozása</span><span class="sxs-lookup"><span data-stu-id="0055c-103">Process enrollment eligibility</span></span>

<span data-ttu-id="0055c-104">Ez a cikk bemutatja, hogyan kell futtatni a felvételi jogosultsági folyamatot.</span><span class="sxs-lookup"><span data-stu-id="0055c-104">This article explains how to run the enrollment eligibility process.</span></span>

1. <span data-ttu-id="0055c-105">A **Juttatások kezelése** munkaterületen, amely a **Feldolgozás** menüpontban található, válassza a **Felvételi jogosultság feldolgozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0055c-105">In the **Benefits management** workspace, under **Processing**, select **Enrollment eligibility processing**.</span></span>

2. <span data-ttu-id="0055c-106">A **Juttatásra vonatkozó felvételi jogosultságok futtatása** párbeszédpanelben adja meg a következő mezők értékeit:</span><span class="sxs-lookup"><span data-stu-id="0055c-106">In the **Run benefit enrollment eligibility process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="0055c-107">Mező</span><span class="sxs-lookup"><span data-stu-id="0055c-107">Field</span></span> | <span data-ttu-id="0055c-108">Leírás</span><span class="sxs-lookup"><span data-stu-id="0055c-108">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="0055c-109">**Regisztrációs időszak**</span><span class="sxs-lookup"><span data-stu-id="0055c-109">**Enrollment period**</span></span> | <span data-ttu-id="0055c-110">A beléptetési jogosultságok feldolgozására szolgáló beléptetési időszak.</span><span class="sxs-lookup"><span data-stu-id="0055c-110">The enrollment period to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="0055c-111">**Jogi személy**</span><span class="sxs-lookup"><span data-stu-id="0055c-111">**Legal entity**</span></span> | <span data-ttu-id="0055c-112">Az a jogi személy, amelyhez kapcsolódóan fel kell dolgozni a felvételi jogosultságot.</span><span class="sxs-lookup"><span data-stu-id="0055c-112">The legal entity to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="0055c-113">**Dolgozó**</span><span class="sxs-lookup"><span data-stu-id="0055c-113">**Worker**</span></span> | <span data-ttu-id="0055c-114">Az a dolgozó, akihez kapcsolódóan fel kell dolgozni a felvételi jogosultságot.</span><span class="sxs-lookup"><span data-stu-id="0055c-114">The worker to process enrollment eligibility for.</span></span> <span data-ttu-id="0055c-115">Ha ezt a mezőt üresen hagyja, a program minden dolgozónál feldolgozza a felvételi jogosultságot.</span><span class="sxs-lookup"><span data-stu-id="0055c-115">If you leave this field blank, enrollment eligibility will be processed for all workers.</span></span> |
   | <span data-ttu-id="0055c-116">**Juttatási terv**</span><span class="sxs-lookup"><span data-stu-id="0055c-116">**Benefit plan**</span></span> | <span data-ttu-id="0055c-117">Az a juttatási terv, amelyhez kapcsolódóan fel kell dolgozni a felvételi jogosultságot.</span><span class="sxs-lookup"><span data-stu-id="0055c-117">The benefit plan to process enrollment eligibility for.</span></span>

3. <span data-ttu-id="0055c-118">Ha a háttérben szeretné futtatni a folyamatot, válassza a **Futtatás a háttérben** parancsot, majd hajtsa végre a következő műveleteket:</span><span class="sxs-lookup"><span data-stu-id="0055c-118">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="0055c-119">Információk megadása a folyamathoz.</span><span class="sxs-lookup"><span data-stu-id="0055c-119">Enter information for the process.</span></span>

   2. <span data-ttu-id="0055c-120">Ismétlődő feladat beállításához jelölje be az **Ismétlődés** jelölőnégyzetet, adja meg az ismétlődési adatokat, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="0055c-120">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="0055c-121">A munkafigyelmeztetések beállításához jelölje ki a **Figyelmeztetések** lehetőséget, válassza ki, hogy milyen figyelmeztetéseket akar kapni ezzel kapcsolatban, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="0055c-121">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="0055c-122">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0055c-122">Select **OK**.</span></span> <span data-ttu-id="0055c-123">A folyamat a megadott paraméterekkel fog futni.</span><span class="sxs-lookup"><span data-stu-id="0055c-123">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="0055c-124">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0055c-124">Select **OK**.</span></span>

## <a name="view-process-results"></a><span data-ttu-id="0055c-125">Folyamateredmények megtekintése</span><span class="sxs-lookup"><span data-stu-id="0055c-125">View Process Results</span></span>

<span data-ttu-id="0055c-126">Ez a cikk bemutatja, hogyan lehet megtekinteni a jogosultsági folyamat eredményeit.</span><span class="sxs-lookup"><span data-stu-id="0055c-126">This article explains how to view eligibility process results.</span></span>

1.  <span data-ttu-id="0055c-127">A **Juttatások kezelése** munkaterületen, amely a **Feldolgozás** menüpontban található, válassza az **Eredmények feldolgozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0055c-127">In the **Benefits management** workspace, under **Processing**, select **Process results**.</span></span>

2.  <span data-ttu-id="0055c-128">A **Folyamateredmények** képernyőn a következő mezők vannak megadva:</span><span class="sxs-lookup"><span data-stu-id="0055c-128">In the **Process results** form, the following fields are specified:</span></span>

   | <span data-ttu-id="0055c-129">Mező</span><span class="sxs-lookup"><span data-stu-id="0055c-129">Field</span></span> | <span data-ttu-id="0055c-130">Leírás</span><span class="sxs-lookup"><span data-stu-id="0055c-130">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="0055c-131">**Folyamatazonosító**</span><span class="sxs-lookup"><span data-stu-id="0055c-131">**Process ID**</span></span> | <span data-ttu-id="0055c-132">A dolgozó, a jogi személy és a feldolgozás futtatása kombinációjának egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="0055c-132">The unique ID for the combination of Worker, Legal entity, and process run.</span></span> |
   | <span data-ttu-id="0055c-133">**Folyamat típusa**</span><span class="sxs-lookup"><span data-stu-id="0055c-133">**Process type**</span></span> | <span data-ttu-id="0055c-134">Ez azonosítja a futtatott folyamatot.</span><span class="sxs-lookup"><span data-stu-id="0055c-134">This identifies the process that was run.</span></span> <span data-ttu-id="0055c-135">Például: Regisztráció.</span><span class="sxs-lookup"><span data-stu-id="0055c-135">For example:  Enrollment.</span></span> |
   | <span data-ttu-id="0055c-136">**Időbélyeg**</span><span class="sxs-lookup"><span data-stu-id="0055c-136">**Time stamp**</span></span> | <span data-ttu-id="0055c-137">A jogosultsági folyamat futtatásának ideje.</span><span class="sxs-lookup"><span data-stu-id="0055c-137">The time that the eligibility process was run.</span></span> |
   | <span data-ttu-id="0055c-138">**Jogi személy**</span><span class="sxs-lookup"><span data-stu-id="0055c-138">**Legal entity**</span></span> | <span data-ttu-id="0055c-139">A regisztrációs folyamat során megadott jogi személy.</span><span class="sxs-lookup"><span data-stu-id="0055c-139">The legal entity specified during the enrollment process.</span></span> |
   | <span data-ttu-id="0055c-140">**Dolgozó**</span><span class="sxs-lookup"><span data-stu-id="0055c-140">**Worker**</span></span> | <span data-ttu-id="0055c-141">A feldolgozott dolgozó.</span><span class="sxs-lookup"><span data-stu-id="0055c-141">The worker who was processed.</span></span> |
   | <span data-ttu-id="0055c-142">\*\*Konstrukció</span><span class="sxs-lookup"><span data-stu-id="0055c-142">\*\*Plan</span></span> | <span data-ttu-id="0055c-143">Az a juttatási konstrukció amelyre a regisztrációt megkísérelték.</span><span class="sxs-lookup"><span data-stu-id="0055c-143">The Benefit plan that enrollment was attempted for.</span></span> |
   | <span data-ttu-id="0055c-144">**Jogosultsági szabály**</span><span class="sxs-lookup"><span data-stu-id="0055c-144">**Eligibility rule**</span></span> | <span data-ttu-id="0055c-145">A feldolgozott jogosultsági szabály.</span><span class="sxs-lookup"><span data-stu-id="0055c-145">The eligibility rule that was processed.</span></span> <span data-ttu-id="0055c-146">Ha hiba történt a jogosultság futtatása előtt, akkor ez a mező üresen marad.</span><span class="sxs-lookup"><span data-stu-id="0055c-146">If an error was encountered before eligibility was run, this will be blank.</span></span> <span data-ttu-id="0055c-147">Például: Ha nincs beállítva kompenzáció egy dolgozóhoz, akkor a jogosultsági folyamat nem fog lefutni, és a mező üresen marad.</span><span class="sxs-lookup"><span data-stu-id="0055c-147">For example: If compensation hasn't been defined for a worker, the eligibility process won't run, and this field will be left blank.</span></span> |
   | <span data-ttu-id="0055c-148">**Eredményállapot**</span><span class="sxs-lookup"><span data-stu-id="0055c-148">**Result status**</span></span> | <span data-ttu-id="0055c-149">Ez jogosult vagy nem jogosult lesz.</span><span class="sxs-lookup"><span data-stu-id="0055c-149">This will be Eligible or Ineligible.</span></span> <span data-ttu-id="0055c-150">Ha a dolgozó nem teljesítette a jogosultsági szabály feltételeit, akkor az eredmény állapota nem jogosult lesz, ha a dolgozó nem rendelkezik a szükséges adatokkal, például a fizetési gyakorisággal vagy a fix kompenzációval, vagy ha a juttatási konstrukcióban hiányzik egy olyan adat, amely megakadályozza a dolgozó regisztrációját.</span><span class="sxs-lookup"><span data-stu-id="0055c-150">The result status will be Ineligible if the worker didn’t meet the eligibility rule criteria, if the worker is missing required information such as a pay frequency or fixed compensation, or if there is information missing on the benefit plan that prevents workers from being enrolled.</span></span> |
   | <span data-ttu-id="0055c-151">**Eredményüzenet**</span><span class="sxs-lookup"><span data-stu-id="0055c-151">**Result message**</span></span> | <span data-ttu-id="0055c-152">Azt jelzi, hogy a dolgozó miért nem jogosult a juttatási konstrukcióra, vagy ha a jogosultsági szabály teljesült.</span><span class="sxs-lookup"><span data-stu-id="0055c-152">Indicates why a worker is ineligible for a benefit plan or if the eligibility rule passed.</span></span> |

