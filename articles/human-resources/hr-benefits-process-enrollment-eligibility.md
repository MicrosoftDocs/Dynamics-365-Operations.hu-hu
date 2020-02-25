---
title: Felvételi jogosultság feldolgozása
description: Ez a cikk bemutatja, hogyan kell futtatni a felvételi jogosultsági folyamatot.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.openlocfilehash: 0344c48460a7d1540481e09ba106526e119de72b
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009225"
---
# <a name="process-enrollment-eligibility"></a><span data-ttu-id="ca686-103">Felvételi jogosultság feldolgozása</span><span class="sxs-lookup"><span data-stu-id="ca686-103">Process enrollment eligibility</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="ca686-104">Ez a cikk bemutatja, hogyan kell futtatni a felvételi jogosultsági folyamatot.</span><span class="sxs-lookup"><span data-stu-id="ca686-104">This article explains how to run the enrollment eligibility process.</span></span>

1. <span data-ttu-id="ca686-105">A **Juttatások kezelése** munkaterületen, amely a **Feldolgozás** menüpontban található, válassza a **Felvételi jogosultság feldolgozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ca686-105">In the **Benefits management** workspace, under **Processing**, select **Enrollment eligibility processing**.</span></span>

2. <span data-ttu-id="ca686-106">A **Juttatásra vonatkozó felvételi jogosultságok futtatása** párbeszédpanelben adja meg a következő mezők értékeit:</span><span class="sxs-lookup"><span data-stu-id="ca686-106">In the **Run benefit enrollment eligibility process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="ca686-107">Mező</span><span class="sxs-lookup"><span data-stu-id="ca686-107">Field</span></span> | <span data-ttu-id="ca686-108">Leírás</span><span class="sxs-lookup"><span data-stu-id="ca686-108">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="ca686-109">Regisztrációs időszak</span><span class="sxs-lookup"><span data-stu-id="ca686-109">Enrollment period</span></span> | <span data-ttu-id="ca686-110">A beléptetési jogosultságok feldolgozására szolgáló beléptetési időszak.</span><span class="sxs-lookup"><span data-stu-id="ca686-110">The enrollment period to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="ca686-111">Jogi személy</span><span class="sxs-lookup"><span data-stu-id="ca686-111">Legal entity</span></span> | <span data-ttu-id="ca686-112">Az a jogi személy, amelyhez kapcsolódóan fel kell dolgozni a felvételi jogosultságot.</span><span class="sxs-lookup"><span data-stu-id="ca686-112">The legal entity to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="ca686-113">Dolgozó</span><span class="sxs-lookup"><span data-stu-id="ca686-113">Worker</span></span> | <span data-ttu-id="ca686-114">Az a dolgozó, akihez kapcsolódóan fel kell dolgozni a felvételi jogosultságot.</span><span class="sxs-lookup"><span data-stu-id="ca686-114">The worker to process enrollment eligibility for.</span></span> <span data-ttu-id="ca686-115">Ha ezt a mezőt üresen hagyja, a program minden dolgozónál feldolgozza a felvételi jogosultságot.</span><span class="sxs-lookup"><span data-stu-id="ca686-115">If you leave this field blank, enrollment eligibility will be processed for all workers.</span></span> |
   | <span data-ttu-id="ca686-116">Juttatási konstrukció</span><span class="sxs-lookup"><span data-stu-id="ca686-116">Benefit plan</span></span> | <span data-ttu-id="ca686-117">Az a juttatási terv, amelyhez kapcsolódóan fel kell dolgozni a felvételi jogosultságot.</span><span class="sxs-lookup"><span data-stu-id="ca686-117">The benefit plan to process enrollment eligibility for.</span></span>

3. <span data-ttu-id="ca686-118">Ha a háttérben szeretné futtatni a folyamatot, válassza a **Futtatás a háttérben** parancsot, majd hajtsa végre a következő műveleteket:</span><span class="sxs-lookup"><span data-stu-id="ca686-118">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="ca686-119">Információk megadása a folyamathoz.</span><span class="sxs-lookup"><span data-stu-id="ca686-119">Enter information for the process.</span></span>

   2. <span data-ttu-id="ca686-120">Ismétlődő feladat beállításához jelölje be az **Ismétlődés** jelölőnégyzetet, adja meg az ismétlődési adatokat, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="ca686-120">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="ca686-121">A munkafigyelmeztetések beállításához jelölje ki a **Figyelmeztetések** lehetőséget, válassza ki, hogy milyen figyelmeztetéseket akar kapni ezzel kapcsolatban, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="ca686-121">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="ca686-122">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ca686-122">Select **OK**.</span></span> <span data-ttu-id="ca686-123">A folyamat a megadott paraméterekkel fog futni.</span><span class="sxs-lookup"><span data-stu-id="ca686-123">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="ca686-124">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ca686-124">Select **OK**.</span></span>
