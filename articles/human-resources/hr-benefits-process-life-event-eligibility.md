---
title: Életeseményekre vonatkozó jogosultságok feldolgozása
description: Ez a cikk bemutatja, hogyan futtathatja az életeseményre vonatkozó jogosultsági folyamatot.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 7eadf3480ccd703a059e80858ab44efc5b27d8d2
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803849"
---
# <a name="process-life-event-eligibility"></a><span data-ttu-id="dbd93-103">Életeseményekre vonatkozó jogosultságok feldolgozása</span><span class="sxs-lookup"><span data-stu-id="dbd93-103">Process life event eligibility</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="dbd93-104">Ez a cikk bemutatja, hogyan futtathatja az életeseményre vonatkozó jogosultsági folyamatot.</span><span class="sxs-lookup"><span data-stu-id="dbd93-104">This article shows you how to run the process for life event eligibility.</span></span>

1. <span data-ttu-id="dbd93-105">A **Juttatások kezelése** munkaterületen, amely a **Feldolgozás** menüpontban található, válassza az **Életeseményre vonatkozó jogosultságok feldolgozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dbd93-105">In the **Benefits management** workspace, under **Processing**, select **Life event eligibility processing**.</span></span>

2. <span data-ttu-id="dbd93-106">Az **Lleteseményre való jogosultságra vonatkozó folyamat futtatása** párbeszédpanelben adja meg a következő mezők értékeit:</span><span class="sxs-lookup"><span data-stu-id="dbd93-106">In the **Run life event eligibility process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="dbd93-107">Mező</span><span class="sxs-lookup"><span data-stu-id="dbd93-107">Field</span></span> | <span data-ttu-id="dbd93-108">Leírás</span><span class="sxs-lookup"><span data-stu-id="dbd93-108">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="dbd93-109">**Regisztrációs időszak**</span><span class="sxs-lookup"><span data-stu-id="dbd93-109">**Enrollment period**</span></span> | <span data-ttu-id="dbd93-110">Az életeseményre vonatkozó jogosultságok feldolgozására szolgáló beléptetési időszak.</span><span class="sxs-lookup"><span data-stu-id="dbd93-110">The enrollment period to process life event eligibility for.</span></span> |

3. <span data-ttu-id="dbd93-111">Ha a háttérben szeretné futtatni a folyamatot, válassza a **Futtatás a háttérben** parancsot, majd hajtsa végre a következő műveleteket:</span><span class="sxs-lookup"><span data-stu-id="dbd93-111">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="dbd93-112">Információk megadása a folyamathoz.</span><span class="sxs-lookup"><span data-stu-id="dbd93-112">Enter information for the process.</span></span>

   2. <span data-ttu-id="dbd93-113">Ismétlődő feladat beállításához jelölje be az **Ismétlődés** jelölőnégyzetet, adja meg az ismétlődési adatokat, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="dbd93-113">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="dbd93-114">A munkafigyelmeztetések beállításához jelölje ki a **Figyelmeztetések** lehetőséget, válassza ki, hogy milyen figyelmeztetéseket akar kapni ezzel kapcsolatban, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="dbd93-114">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="dbd93-115">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dbd93-115">Select **OK**.</span></span> <span data-ttu-id="dbd93-116">A folyamat a megadott paraméterekkel fog futni.</span><span class="sxs-lookup"><span data-stu-id="dbd93-116">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="dbd93-117">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dbd93-117">Select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]