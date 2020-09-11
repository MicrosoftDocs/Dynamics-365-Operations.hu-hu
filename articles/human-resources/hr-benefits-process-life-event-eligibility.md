---
title: Életeseményekre vonatkozó jogosultságok feldolgozása
description: Ez a cikk bemutatja, hogyan futtathatja az életeseményre vonatkozó jogosultsági folyamatot.
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
ms.openlocfilehash: 17ecef1412eb0232fbb4782bd9d2d79f210c7e80
ms.sourcegitcommit: 9723b5ff40c84677316d71e185cf862556b32cf9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/31/2020
ms.locfileid: "3741387"
---
# <a name="process-life-event-eligibility"></a><span data-ttu-id="8faa8-103">Életeseményekre vonatkozó jogosultságok feldolgozása</span><span class="sxs-lookup"><span data-stu-id="8faa8-103">Process life event eligibility</span></span>

<span data-ttu-id="8faa8-104">Ez a cikk bemutatja, hogyan futtathatja az életeseményre vonatkozó jogosultsági folyamatot.</span><span class="sxs-lookup"><span data-stu-id="8faa8-104">This article shows you how to run the process for life event eligibility.</span></span>

1. <span data-ttu-id="8faa8-105">A **Juttatások kezelése** munkaterületen, amely a **Feldolgozás** menüpontban található, válassza az **Életeseményre vonatkozó jogosultságok feldolgozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8faa8-105">In the **Benefits management** workspace, under **Processing**, select **Life event eligibility processing**.</span></span>

2. <span data-ttu-id="8faa8-106">Az **Lleteseményre való jogosultságra vonatkozó folyamat futtatása** párbeszédpanelben adja meg a következő mezők értékeit:</span><span class="sxs-lookup"><span data-stu-id="8faa8-106">In the **Run life event eligibility process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="8faa8-107">Mező</span><span class="sxs-lookup"><span data-stu-id="8faa8-107">Field</span></span> | <span data-ttu-id="8faa8-108">Leírás</span><span class="sxs-lookup"><span data-stu-id="8faa8-108">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="8faa8-109">**Regisztrációs időszak**</span><span class="sxs-lookup"><span data-stu-id="8faa8-109">**Enrollment period**</span></span> | <span data-ttu-id="8faa8-110">Az életeseményre vonatkozó jogosultságok feldolgozására szolgáló beléptetési időszak.</span><span class="sxs-lookup"><span data-stu-id="8faa8-110">The enrollment period to process life event eligibility for.</span></span> |

3. <span data-ttu-id="8faa8-111">Ha a háttérben szeretné futtatni a folyamatot, válassza a **Futtatás a háttérben** parancsot, majd hajtsa végre a következő műveleteket:</span><span class="sxs-lookup"><span data-stu-id="8faa8-111">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="8faa8-112">Információk megadása a folyamathoz.</span><span class="sxs-lookup"><span data-stu-id="8faa8-112">Enter information for the process.</span></span>

   2. <span data-ttu-id="8faa8-113">Ismétlődő feladat beállításához jelölje be az **Ismétlődés** jelölőnégyzetet, adja meg az ismétlődési adatokat, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="8faa8-113">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="8faa8-114">A munkafigyelmeztetések beállításához jelölje ki a **Figyelmeztetések** lehetőséget, válassza ki, hogy milyen figyelmeztetéseket akar kapni ezzel kapcsolatban, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="8faa8-114">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="8faa8-115">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8faa8-115">Select **OK**.</span></span> <span data-ttu-id="8faa8-116">A folyamat a megadott paraméterekkel fog futni.</span><span class="sxs-lookup"><span data-stu-id="8faa8-116">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="8faa8-117">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8faa8-117">Select **OK**.</span></span>
