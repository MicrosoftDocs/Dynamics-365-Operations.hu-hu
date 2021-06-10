---
title: Felvételi jogosultság feldolgozása
description: Ez a cikk bemutatja, hogyan kell futtatni a felvételi jogosultsági folyamatot.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4dd63e755f0afdbce411b3001410d2e56036e432
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054260"
---
# <a name="process-enrollment-eligibility"></a><span data-ttu-id="376fe-103">Felvételi jogosultság feldolgozása</span><span class="sxs-lookup"><span data-stu-id="376fe-103">Process enrollment eligibility</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="376fe-104">Ez a cikk bemutatja, hogyan kell futtatni a felvételi jogosultsági folyamatot.</span><span class="sxs-lookup"><span data-stu-id="376fe-104">This article explains how to run the enrollment eligibility process.</span></span>

1. <span data-ttu-id="376fe-105">A **Juttatások kezelése** munkaterületen, amely a **Feldolgozás** menüpontban található, válassza a **Felvételi jogosultság feldolgozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="376fe-105">In the **Benefits management** workspace, under **Processing**, select **Enrollment eligibility processing**.</span></span>

2. <span data-ttu-id="376fe-106">A **Juttatásra vonatkozó felvételi jogosultságok futtatása** párbeszédpanelben adja meg a következő mezők értékeit:</span><span class="sxs-lookup"><span data-stu-id="376fe-106">In the **Run benefit enrollment eligibility process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="376fe-107">Mező</span><span class="sxs-lookup"><span data-stu-id="376fe-107">Field</span></span> | <span data-ttu-id="376fe-108">Leírás</span><span class="sxs-lookup"><span data-stu-id="376fe-108">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="376fe-109">**Regisztrációs időszak**</span><span class="sxs-lookup"><span data-stu-id="376fe-109">**Enrollment period**</span></span> | <span data-ttu-id="376fe-110">A beléptetési jogosultságok feldolgozására szolgáló beléptetési időszak.</span><span class="sxs-lookup"><span data-stu-id="376fe-110">The enrollment period to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="376fe-111">**Jogi személy**</span><span class="sxs-lookup"><span data-stu-id="376fe-111">**Legal entity**</span></span> | <span data-ttu-id="376fe-112">Az a jogi személy, amelyhez kapcsolódóan fel kell dolgozni a felvételi jogosultságot.</span><span class="sxs-lookup"><span data-stu-id="376fe-112">The legal entity to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="376fe-113">**Dolgozó**</span><span class="sxs-lookup"><span data-stu-id="376fe-113">**Worker**</span></span> | <span data-ttu-id="376fe-114">Az a dolgozó, akihez kapcsolódóan fel kell dolgozni a felvételi jogosultságot.</span><span class="sxs-lookup"><span data-stu-id="376fe-114">The worker to process enrollment eligibility for.</span></span> <span data-ttu-id="376fe-115">Ha ezt a mezőt üresen hagyja, a program minden dolgozónál feldolgozza a felvételi jogosultságot.</span><span class="sxs-lookup"><span data-stu-id="376fe-115">If you leave this field blank, enrollment eligibility will be processed for all workers.</span></span> |
   | <span data-ttu-id="376fe-116">**Juttatási terv**</span><span class="sxs-lookup"><span data-stu-id="376fe-116">**Benefit plan**</span></span> | <span data-ttu-id="376fe-117">Az a juttatási terv, amelyhez kapcsolódóan fel kell dolgozni a felvételi jogosultságot.</span><span class="sxs-lookup"><span data-stu-id="376fe-117">The benefit plan to process enrollment eligibility for.</span></span>

3. <span data-ttu-id="376fe-118">Ha a háttérben szeretné futtatni a folyamatot, válassza a **Futtatás a háttérben** parancsot, majd hajtsa végre a következő műveleteket:</span><span class="sxs-lookup"><span data-stu-id="376fe-118">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="376fe-119">Információk megadása a folyamathoz.</span><span class="sxs-lookup"><span data-stu-id="376fe-119">Enter information for the process.</span></span>

   2. <span data-ttu-id="376fe-120">Ismétlődő feladat beállításához jelölje be az **Ismétlődés** jelölőnégyzetet, adja meg az ismétlődési adatokat, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="376fe-120">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="376fe-121">A munkafigyelmeztetések beállításához jelölje ki a **Figyelmeztetések** lehetőséget, válassza ki, hogy milyen figyelmeztetéseket akar kapni ezzel kapcsolatban, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="376fe-121">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="376fe-122">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="376fe-122">Select **OK**.</span></span> <span data-ttu-id="376fe-123">A folyamat a megadott paraméterekkel fog futni.</span><span class="sxs-lookup"><span data-stu-id="376fe-123">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="376fe-124">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="376fe-124">Select **OK**.</span></span>

## <a name="view-process-results"></a><span data-ttu-id="376fe-125">Folyamateredmények megtekintése</span><span class="sxs-lookup"><span data-stu-id="376fe-125">View Process Results</span></span>

<span data-ttu-id="376fe-126">Ez a cikk bemutatja, hogyan lehet megtekinteni a jogosultsági folyamat eredményeit.</span><span class="sxs-lookup"><span data-stu-id="376fe-126">This article explains how to view eligibility process results.</span></span>

1.  <span data-ttu-id="376fe-127">A **Juttatások kezelése** munkaterületen, amely a **Feldolgozás** menüpontban található, válassza az **Eredmények feldolgozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="376fe-127">In the **Benefits management** workspace, under **Processing**, select **Process results**.</span></span>

2.  <span data-ttu-id="376fe-128">A **Folyamateredmények** képernyőn a következő mezők vannak megadva:</span><span class="sxs-lookup"><span data-stu-id="376fe-128">In the **Process results** form, the following fields are specified:</span></span>

   | <span data-ttu-id="376fe-129">Mező</span><span class="sxs-lookup"><span data-stu-id="376fe-129">Field</span></span> | <span data-ttu-id="376fe-130">Leírás</span><span class="sxs-lookup"><span data-stu-id="376fe-130">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="376fe-131">**Folyamatazonosító**</span><span class="sxs-lookup"><span data-stu-id="376fe-131">**Process ID**</span></span> | <span data-ttu-id="376fe-132">A dolgozó, a jogi személy és a feldolgozás futtatása kombinációjának egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="376fe-132">The unique ID for the combination of Worker, Legal entity, and process run.</span></span> |
   | <span data-ttu-id="376fe-133">**Folyamat típusa**</span><span class="sxs-lookup"><span data-stu-id="376fe-133">**Process type**</span></span> | <span data-ttu-id="376fe-134">Ez azonosítja a futtatott folyamatot.</span><span class="sxs-lookup"><span data-stu-id="376fe-134">This identifies the process that was run.</span></span> <span data-ttu-id="376fe-135">Például: Regisztráció.</span><span class="sxs-lookup"><span data-stu-id="376fe-135">For example:  Enrollment.</span></span> |
   | <span data-ttu-id="376fe-136">**Időbélyeg**</span><span class="sxs-lookup"><span data-stu-id="376fe-136">**Time stamp**</span></span> | <span data-ttu-id="376fe-137">A jogosultsági folyamat futtatásának ideje.</span><span class="sxs-lookup"><span data-stu-id="376fe-137">The time that the eligibility process was run.</span></span> |
   | <span data-ttu-id="376fe-138">**Jogi személy**</span><span class="sxs-lookup"><span data-stu-id="376fe-138">**Legal entity**</span></span> | <span data-ttu-id="376fe-139">A regisztrációs folyamat során megadott jogi személy.</span><span class="sxs-lookup"><span data-stu-id="376fe-139">The legal entity specified during the enrollment process.</span></span> |
   | <span data-ttu-id="376fe-140">**Dolgozó**</span><span class="sxs-lookup"><span data-stu-id="376fe-140">**Worker**</span></span> | <span data-ttu-id="376fe-141">A feldolgozott dolgozó.</span><span class="sxs-lookup"><span data-stu-id="376fe-141">The worker who was processed.</span></span> |
   | <span data-ttu-id="376fe-142">\*\*Konstrukció</span><span class="sxs-lookup"><span data-stu-id="376fe-142">\*\*Plan</span></span> | <span data-ttu-id="376fe-143">Az a juttatási konstrukció amelyre a regisztrációt megkísérelték.</span><span class="sxs-lookup"><span data-stu-id="376fe-143">The Benefit plan that enrollment was attempted for.</span></span> |
   | <span data-ttu-id="376fe-144">**Jogosultsági szabály**</span><span class="sxs-lookup"><span data-stu-id="376fe-144">**Eligibility rule**</span></span> | <span data-ttu-id="376fe-145">A feldolgozott jogosultsági szabály.</span><span class="sxs-lookup"><span data-stu-id="376fe-145">The eligibility rule that was processed.</span></span> <span data-ttu-id="376fe-146">Ha hiba történt a jogosultság futtatása előtt, akkor ez a mező üresen marad.</span><span class="sxs-lookup"><span data-stu-id="376fe-146">If an error was encountered before eligibility was run, this will be blank.</span></span> <span data-ttu-id="376fe-147">Például: Ha nincs beállítva kompenzáció egy dolgozóhoz, akkor a jogosultsági folyamat nem fog lefutni, és a mező üresen marad.</span><span class="sxs-lookup"><span data-stu-id="376fe-147">For example: If compensation hasn't been defined for a worker, the eligibility process won't run, and this field will be left blank.</span></span> |
   | <span data-ttu-id="376fe-148">**Eredményállapot**</span><span class="sxs-lookup"><span data-stu-id="376fe-148">**Result status**</span></span> | <span data-ttu-id="376fe-149">Ez jogosult vagy nem jogosult lesz.</span><span class="sxs-lookup"><span data-stu-id="376fe-149">This will be Eligible or Ineligible.</span></span> <span data-ttu-id="376fe-150">Ha a dolgozó nem teljesítette a jogosultsági szabály feltételeit, akkor az eredmény állapota nem jogosult lesz, ha a dolgozó nem rendelkezik a szükséges adatokkal, például a fizetési gyakorisággal vagy a fix kompenzációval, vagy ha a juttatási konstrukcióban hiányzik egy olyan adat, amely megakadályozza a dolgozó regisztrációját.</span><span class="sxs-lookup"><span data-stu-id="376fe-150">The result status will be Ineligible if the worker didn’t meet the eligibility rule criteria, if the worker is missing required information such as a pay frequency or fixed compensation, or if there is information missing on the benefit plan that prevents workers from being enrolled.</span></span> |
   | <span data-ttu-id="376fe-151">**Eredményüzenet**</span><span class="sxs-lookup"><span data-stu-id="376fe-151">**Result message**</span></span> | <span data-ttu-id="376fe-152">Azt jelzi, hogy a dolgozó miért nem jogosult a juttatási konstrukcióra, vagy ha a jogosultsági szabály teljesült.</span><span class="sxs-lookup"><span data-stu-id="376fe-152">Indicates why a worker is ineligible for a benefit plan or if the eligibility rule passed.</span></span> |



[!INCLUDE[footer-include](../includes/footer-banner.md)]