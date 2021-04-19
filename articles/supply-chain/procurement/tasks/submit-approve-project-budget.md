---
title: Projektköltségvetés elküldése és jóváhagyása
description: Ez az eljárás bemutatja, hogyan hozhatja létre és nyújthatja be a költségvetést a projekthez.
author: kamaybac
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProjProjectsListPage, ProjTable, ProjBudget, WorkflowSubmitDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Service industries
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6886bdba52b8f2c4e088f3b6896707e46f078f59
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811110"
---
# <a name="submit-and-approve-project-budget"></a><span data-ttu-id="5d0ab-103">Projektköltségvetés elküldése és jóváhagyása</span><span class="sxs-lookup"><span data-stu-id="5d0ab-103">Submit and approve project budget</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5d0ab-104">Ez az eljárás bemutatja, hogyan hozhatja létre és nyújthatja be a költségvetést a projekthez.</span><span class="sxs-lookup"><span data-stu-id="5d0ab-104">This procedure shows you how to create and submit the budget for a project.</span></span> 

<span data-ttu-id="5d0ab-105">Projektköltségvetés létrehozása esetén megadhatja a projekt becsült bevételét és költségeit, és ezután ezeket használhatja a projekt tényleges tranzakcióinak kezelésére.</span><span class="sxs-lookup"><span data-stu-id="5d0ab-105">When you create a project budget, you can enter estimated revenues and costs for a project, and then use those to control actual project transactions.</span></span> <span data-ttu-id="5d0ab-106">A projektköltségvetés során, az összes eredeti költségvetést és felülvizsgálatot be kell küldeni a projekt munkafolyamatba jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="5d0ab-106">In project budgeting, all original budgets and revisions must be sent to project workflow for approval.</span></span> <span data-ttu-id="5d0ab-107">A munkafolyamat a folyamatok feletti fokozott ellenőrzést és az előzmények rekordjainak létrehozását biztosítja.</span><span class="sxs-lookup"><span data-stu-id="5d0ab-107">Workflow gives you increased control over the process and creates a change history record.</span></span>

<span data-ttu-id="5d0ab-108">Ez a feladat a USSI adatkészlet segítségével lett létrehozva.</span><span class="sxs-lookup"><span data-stu-id="5d0ab-108">This task was created using the USSI data set.</span></span>

1. <span data-ttu-id="5d0ab-109">A **Navigációs ablaktáblán** lépjen a **Modulok > Projektvezetés és könyvelés > Projektek > Összes projekt** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5d0ab-109">In the **Navigation pane**, go to **Modules > Project management and accounting > Projects > All projects**.</span></span>
2. <span data-ttu-id="5d0ab-110">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="5d0ab-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="5d0ab-111">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="5d0ab-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="5d0ab-112">A **Művelet panelen** kattintson a **Tervezés** elemre.</span><span class="sxs-lookup"><span data-stu-id="5d0ab-112">On the **Action Pane**, click **Plan**.</span></span>
5. <span data-ttu-id="5d0ab-113">Kattintson a **Projektköltségvetés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5d0ab-113">Click **Project budget**.</span></span>
6. <span data-ttu-id="5d0ab-114">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5d0ab-114">In the **Description** field, type a value.</span></span>
7. <span data-ttu-id="5d0ab-115">Bontsa ki a **Költség** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="5d0ab-115">Expand the **Cost** fastTab.</span></span>
8. <span data-ttu-id="5d0ab-116">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="5d0ab-116">Click **New**.</span></span>
9. <span data-ttu-id="5d0ab-117">A **Tranzakció típusa** mezőben válasszon egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5d0ab-117">In the **Transaction type** field, select an option.</span></span>
10. <span data-ttu-id="5d0ab-118">A **Kategória** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5d0ab-118">In the **Category** field, enter or select a value.</span></span>
11. <span data-ttu-id="5d0ab-119">Az **Eredeti költségvetés** mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="5d0ab-119">In the **Original budget** field, enter a number.</span></span>
12. <span data-ttu-id="5d0ab-120">Bontsa ki a **Bevételek** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="5d0ab-120">Expand the **Revenues** fastTab.</span></span>
13. <span data-ttu-id="5d0ab-121">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="5d0ab-121">Click **New**.</span></span>
14. <span data-ttu-id="5d0ab-122">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="5d0ab-122">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="5d0ab-123">A **Tranzakció típusa** mezőben válasszon egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5d0ab-123">In the **Transaction type** field, select an option.</span></span>
16. <span data-ttu-id="5d0ab-124">A **Kategória** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5d0ab-124">In the **Category** field, enter or select a value.</span></span>
17. <span data-ttu-id="5d0ab-125">Az **Eredeti költségvetés** mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="5d0ab-125">In the **Original budget** field, enter a number.</span></span>
18. <span data-ttu-id="5d0ab-126">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="5d0ab-126">Click **Save**.</span></span>
19. <span data-ttu-id="5d0ab-127">Kattintson a **Munkafolyamat** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5d0ab-127">Click **Workflow**.</span></span>
20. <span data-ttu-id="5d0ab-128">Kattintson a **Küldés** elemre.</span><span class="sxs-lookup"><span data-stu-id="5d0ab-128">Click **Submit**.</span></span>
21. <span data-ttu-id="5d0ab-129">Írjon egy értéket a **Megjegyzés** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5d0ab-129">In the **Comment** field, type a value.</span></span>
22. <span data-ttu-id="5d0ab-130">Kattintson a **Küldés** elemre.</span><span class="sxs-lookup"><span data-stu-id="5d0ab-130">Click **Submit**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]