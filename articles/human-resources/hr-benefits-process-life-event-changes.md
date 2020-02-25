---
title: Életesemények módosításainak feldolgozása
description: Egy életeseményben végrehajtott módosítás feldolgozása a Microsoft Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: f9bce9394a361bbecfcc0531c5d7ebe9302c8f11
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009291"
---
# <a name="process-life-event-changes"></a><span data-ttu-id="6a730-103">Életesemények módosításainak feldolgozása</span><span class="sxs-lookup"><span data-stu-id="6a730-103">Process life event changes</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="6a730-104">Két életeseményben végrehajtott módosítás feldolgozása a Microsoft Dynamics 365 Human Resources rendszerben:</span><span class="sxs-lookup"><span data-stu-id="6a730-104">Process life event changes in Microsoft Dynamics 365 Human Resources for two life event changes:</span></span>

- <span data-ttu-id="6a730-105">Születésnapra vonatkozó változtatások</span><span class="sxs-lookup"><span data-stu-id="6a730-105">Birthday changes</span></span>
- <span data-ttu-id="6a730-106">A jogosultsági szabály felülírja a lejárati változtatásokat</span><span class="sxs-lookup"><span data-stu-id="6a730-106">Eligibility rule override expiration changes</span></span> 

1. <span data-ttu-id="6a730-107">A **Juttatások kezelése** munkaterületen, amely a **Feldolgozás** menüpontban található, válassza az **Életesemény módosításának feldolgozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6a730-107">In the **Benefits management** workspace, under **Processing**, select **Life event change processing**.</span></span>

2. <span data-ttu-id="6a730-108">Az **Életeseményben történt módosításra vonatkozó folyamat futtatása** párbeszédpanelben adja meg a következő mezők értékeit:</span><span class="sxs-lookup"><span data-stu-id="6a730-108">In the **Run life event change process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="6a730-109">Mező</span><span class="sxs-lookup"><span data-stu-id="6a730-109">Field</span></span> | <span data-ttu-id="6a730-110">Leírás</span><span class="sxs-lookup"><span data-stu-id="6a730-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="6a730-111">Regisztrációs időszak</span><span class="sxs-lookup"><span data-stu-id="6a730-111">Enrollment period</span></span> | <span data-ttu-id="6a730-112">Az életesemények módosításainak feldolgozására szolgáló beléptetési időszak.</span><span class="sxs-lookup"><span data-stu-id="6a730-112">The enrollment period to process life event changes for.</span></span> |
   | <span data-ttu-id="6a730-113">Jogi személy</span><span class="sxs-lookup"><span data-stu-id="6a730-113">Legal entity</span></span> | <span data-ttu-id="6a730-114">Az a jogi személy, amelyre vonatkozóan fel kell dolgozni az életeseményben történt módosításokat.</span><span class="sxs-lookup"><span data-stu-id="6a730-114">The legal entity to process life event changes for.</span></span> |

3. <span data-ttu-id="6a730-115">Ha a háttérben szeretné futtatni a folyamatot, válassza a **Futtatás a háttérben** parancsot, majd hajtsa végre a következő műveleteket:</span><span class="sxs-lookup"><span data-stu-id="6a730-115">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="6a730-116">Információk megadása a folyamathoz.</span><span class="sxs-lookup"><span data-stu-id="6a730-116">Enter information for the process.</span></span>

   2. <span data-ttu-id="6a730-117">Ismétlődő feladat beállításához jelölje be az **Ismétlődés** jelölőnégyzetet, adja meg az ismétlődési adatokat, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="6a730-117">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="6a730-118">A munkafigyelmeztetések beállításához jelölje ki a **Figyelmeztetések** lehetőséget, válassza ki, hogy milyen figyelmeztetéseket akar kapni ezzel kapcsolatban, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="6a730-118">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="6a730-119">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6a730-119">Select **OK**.</span></span> <span data-ttu-id="6a730-120">A folyamat a megadott paraméterekkel fog futni.</span><span class="sxs-lookup"><span data-stu-id="6a730-120">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="6a730-121">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6a730-121">Select **OK**.</span></span>
