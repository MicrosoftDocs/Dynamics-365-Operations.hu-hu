---
title: Mértékváltozások feldolgozása
description: A juttatási mérték változásainak feldolgozása a Microsoft Dynamics 365 Human Resources rendszerben, ha egy új vagy meglévő juttatási terv módosult a jogosultsági szabály beállításaiban.
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
ms.openlocfilehash: 9ebe5cfc2bdf7790770d27ece2dc67f7677db593
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009237"
---
# <a name="process-rate-changes"></a><span data-ttu-id="6408f-103">Mértékváltozások feldolgozása</span><span class="sxs-lookup"><span data-stu-id="6408f-103">Process rate changes</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="6408f-104">A juttatási mérték változásainak feldolgozása a Microsoft Dynamics 365 Human Resources rendszerben, ha egy új vagy meglévő juttatási terv módosult a jogosultsági szabály beállításaiban.</span><span class="sxs-lookup"><span data-stu-id="6408f-104">Process benefit rate changes in Microsoft Dynamics 365 Human Resources when a new or existing benefit plan has a change in eligibility rule settings.</span></span> <span data-ttu-id="6408f-105">Ha új jogosultsági szabályt létre, majd hozzárendeli a tervhez, akkor a rendszer újból lefuttatja az ellenőrzést arra vonatkozóan, hogy a dolgozó jogosult-e a tervre az új jogosultsági lehetőségek alapján.</span><span class="sxs-lookup"><span data-stu-id="6408f-105">If a new eligibility rule is created and assigned to the plan, this prompts the system to re-run worker eligibility to check if workers may now be eligible for the plan based on new eligibility options.</span></span> 

1. <span data-ttu-id="6408f-106">A **Juttatások kezelése** munkaterületen, amely a **Feldolgozás** menüpontban található, válassza a **Mértékváltozásra vonatkozó frissítés feldolgozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6408f-106">In the **Benefits management** workspace, under **Processing**, select **Rate change update processing**.</span></span>

2. <span data-ttu-id="6408f-107">A **Juttatásra vonatkozó mértékfrissítés futtatása** párbeszédpanelben adja meg a következő mezők értékeit:</span><span class="sxs-lookup"><span data-stu-id="6408f-107">In the **Run benefit rate update process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="6408f-108">Mező</span><span class="sxs-lookup"><span data-stu-id="6408f-108">Field</span></span> | <span data-ttu-id="6408f-109">Leírás</span><span class="sxs-lookup"><span data-stu-id="6408f-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="6408f-110">Regisztrációs időszak</span><span class="sxs-lookup"><span data-stu-id="6408f-110">Enrollment period</span></span> | <span data-ttu-id="6408f-111">Beléptetési időszak, amelyhez a mértékben történt változtatás feldolgozása szükséges.</span><span class="sxs-lookup"><span data-stu-id="6408f-111">The enrollment period to process rate changes for.</span></span> |

3. <span data-ttu-id="6408f-112">Ha a háttérben szeretné futtatni a folyamatot, válassza a **Futtatás a háttérben** parancsot, majd hajtsa végre a következő műveleteket:</span><span class="sxs-lookup"><span data-stu-id="6408f-112">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="6408f-113">Információk megadása a folyamathoz.</span><span class="sxs-lookup"><span data-stu-id="6408f-113">Enter information for the process.</span></span>

   2. <span data-ttu-id="6408f-114">Ismétlődő feladat beállításához jelölje be az **Ismétlődés** jelölőnégyzetet, adja meg az ismétlődési adatokat, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="6408f-114">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="6408f-115">A munkafigyelmeztetések beállításához jelölje ki a **Figyelmeztetések** lehetőséget, válassza ki, hogy milyen figyelmeztetéseket akar kapni ezzel kapcsolatban, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="6408f-115">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="6408f-116">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6408f-116">Select **OK**.</span></span> <span data-ttu-id="6408f-117">A folyamat a megadott paraméterekkel fog futni.</span><span class="sxs-lookup"><span data-stu-id="6408f-117">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="6408f-118">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6408f-118">Select **OK**.</span></span>