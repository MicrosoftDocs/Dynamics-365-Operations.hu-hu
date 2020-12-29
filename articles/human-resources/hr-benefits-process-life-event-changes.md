---
title: Életesemények módosításainak feldolgozása
description: Egy életeseményben végrehajtott módosítás feldolgozása a Microsoft Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: 39d1e94347809a1756fc4f66e5edc345c70eaf39
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418800"
---
# <a name="process-life-event-changes"></a><span data-ttu-id="43d32-103">Életesemények módosításainak feldolgozása</span><span class="sxs-lookup"><span data-stu-id="43d32-103">Process life event changes</span></span>

<span data-ttu-id="43d32-104">Két életeseményben végrehajtott módosítás feldolgozása a Microsoft Dynamics 365 Human Resources rendszerben:</span><span class="sxs-lookup"><span data-stu-id="43d32-104">Process life event changes in Microsoft Dynamics 365 Human Resources for two life event changes:</span></span>

- <span data-ttu-id="43d32-105">Születésnapra vonatkozó változtatások</span><span class="sxs-lookup"><span data-stu-id="43d32-105">Birthday changes</span></span>
- <span data-ttu-id="43d32-106">A jogosultsági szabály felülírja a lejárati változtatásokat</span><span class="sxs-lookup"><span data-stu-id="43d32-106">Eligibility rule override expiration changes</span></span> 

1. <span data-ttu-id="43d32-107">A **Juttatások kezelése** munkaterületen, amely a **Feldolgozás** menüpontban található, válassza az **Életesemény módosításának feldolgozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="43d32-107">In the **Benefits management** workspace, under **Processing**, select **Life event change processing**.</span></span>

2. <span data-ttu-id="43d32-108">Az **Életeseményben történt módosításra vonatkozó folyamat futtatása** párbeszédpanelben adja meg a következő mezők értékeit:</span><span class="sxs-lookup"><span data-stu-id="43d32-108">In the **Run life event change process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="43d32-109">Mező</span><span class="sxs-lookup"><span data-stu-id="43d32-109">Field</span></span> | <span data-ttu-id="43d32-110">Leírás</span><span class="sxs-lookup"><span data-stu-id="43d32-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="43d32-111">Regisztrációs időszak</span><span class="sxs-lookup"><span data-stu-id="43d32-111">Enrollment period</span></span> | <span data-ttu-id="43d32-112">Az életesemények módosításainak feldolgozására szolgáló beléptetési időszak.</span><span class="sxs-lookup"><span data-stu-id="43d32-112">The enrollment period to process life event changes for.</span></span> |
   | <span data-ttu-id="43d32-113">Jogi személy</span><span class="sxs-lookup"><span data-stu-id="43d32-113">Legal entity</span></span> | <span data-ttu-id="43d32-114">Az a jogi személy, amelyre vonatkozóan fel kell dolgozni az életeseményben történt módosításokat.</span><span class="sxs-lookup"><span data-stu-id="43d32-114">The legal entity to process life event changes for.</span></span> |

3. <span data-ttu-id="43d32-115">Ha a háttérben szeretné futtatni a folyamatot, válassza a **Futtatás a háttérben** parancsot, majd hajtsa végre a következő műveleteket:</span><span class="sxs-lookup"><span data-stu-id="43d32-115">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="43d32-116">Információk megadása a folyamathoz.</span><span class="sxs-lookup"><span data-stu-id="43d32-116">Enter information for the process.</span></span>

   2. <span data-ttu-id="43d32-117">Ismétlődő feladat beállításához jelölje be az **Ismétlődés** jelölőnégyzetet, adja meg az ismétlődési adatokat, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="43d32-117">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="43d32-118">A munkafigyelmeztetések beállításához jelölje ki a **Figyelmeztetések** lehetőséget, válassza ki, hogy milyen figyelmeztetéseket akar kapni ezzel kapcsolatban, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="43d32-118">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="43d32-119">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="43d32-119">Select **OK**.</span></span> <span data-ttu-id="43d32-120">A folyamat a megadott paraméterekkel fog futni.</span><span class="sxs-lookup"><span data-stu-id="43d32-120">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="43d32-121">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="43d32-121">Select **OK**.</span></span>
