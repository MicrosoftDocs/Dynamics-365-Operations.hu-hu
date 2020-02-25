---
title: Szabadság- és távolléttípusok konfigurálása
description: Beállíthatja, hogy az alkalmazottak milyen típusú szabadságot vehetnek igénybe a Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1748ec2a888a50af9b9260720dfd439adc4686f9
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009318"
---
# <a name="configure-leave-and-absence-types"></a><span data-ttu-id="46a3e-103">Szabadság- és távolléttípusok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="46a3e-103">Configure leave and absence types</span></span>

<span data-ttu-id="46a3e-104">A Dynamics 365 Human Resources szabadságtípusai határozzák meg az alkalmazottak számára elérhető különböző típusú távolléteket.</span><span class="sxs-lookup"><span data-stu-id="46a3e-104">Leave types in Dynamics 365 Human Resources define the types of absences that employees can report.</span></span> <span data-ttu-id="46a3e-105">A szabadságtípusokat a szervezet igényeihez igazíthatja.</span><span class="sxs-lookup"><span data-stu-id="46a3e-105">You can tailor leave types according to the needs of your organization.</span></span> <span data-ttu-id="46a3e-106">Példák a szabadságtípusokra:</span><span class="sxs-lookup"><span data-stu-id="46a3e-106">Examples of leave types include:</span></span>

- <span data-ttu-id="46a3e-107">Fizetett szabadság (PTO)</span><span class="sxs-lookup"><span data-stu-id="46a3e-107">Paid time off (PTO)</span></span>
- <span data-ttu-id="46a3e-108">Fizetés nélküli szabadság</span><span class="sxs-lookup"><span data-stu-id="46a3e-108">Unpaid leave</span></span>
- <span data-ttu-id="46a3e-109">Fizetett szabadság</span><span class="sxs-lookup"><span data-stu-id="46a3e-109">Paid vacation</span></span>
- <span data-ttu-id="46a3e-110">Betegszabadság</span><span class="sxs-lookup"><span data-stu-id="46a3e-110">Sick leave</span></span>
- <span data-ttu-id="46a3e-111">Betegszabadság</span><span class="sxs-lookup"><span data-stu-id="46a3e-111">Medical leave</span></span>
- <span data-ttu-id="46a3e-112">Családi okokból történő</span><span class="sxs-lookup"><span data-stu-id="46a3e-112">Family leave</span></span>
- <span data-ttu-id="46a3e-113">Rövid távú fogyatékosság</span><span class="sxs-lookup"><span data-stu-id="46a3e-113">Short-term disability</span></span>
- <span data-ttu-id="46a3e-114">Haláleset miatti szabadság</span><span class="sxs-lookup"><span data-stu-id="46a3e-114">Bereavement leave</span></span>

## <a name="add-a-leave-type"></a><span data-ttu-id="46a3e-115">Szabadságtípus hozzáadása</span><span class="sxs-lookup"><span data-stu-id="46a3e-115">Add a leave type</span></span>

1. <span data-ttu-id="46a3e-116">A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.</span><span class="sxs-lookup"><span data-stu-id="46a3e-116">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="46a3e-117">A **Beállítás**területen válassza a **Szabadság- és távolléttípusok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46a3e-117">Under **Setup**, select **Leave and absence types**.</span></span>

3. <span data-ttu-id="46a3e-118">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46a3e-118">Select **New**.</span></span>

4. <span data-ttu-id="46a3e-119">Írjon be a szabadságtípus nevét a **Típus** mezőbe, válasszon egy munkafolyamatot a **Munkafolyamat-azonosító** listáról, és adja meg a leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="46a3e-119">Enter a name for the leave type under **Type**, select a workflow from **Workflow ID**, and enter a description under **Description**.</span></span>

5. <span data-ttu-id="46a3e-120">Az **Általános** lapon válassza ki a **Nincs**, az **Ütemezett** vagy a **Nem ütemezett** elemet a **Kategória** legördülő listáról.</span><span class="sxs-lookup"><span data-stu-id="46a3e-120">In **General**, select **None**, **Scheduled**, or **Unscheduled** from the **Category** dropdown.</span></span>

6. <span data-ttu-id="46a3e-121">Válasszon bevételkódot a **Bevételkód** legördülő listáról.</span><span class="sxs-lookup"><span data-stu-id="46a3e-121">Select an earning code from the **Earning code** dropdown.</span></span>

7. <span data-ttu-id="46a3e-122">**Az okkódot meg kell adni** beállításnál válassza ki, hogy szeretné-e előírni az okkód megadását.</span><span class="sxs-lookup"><span data-stu-id="46a3e-122">Under **Reason code required**, choose whether you want to require a reason code.</span></span> <span data-ttu-id="46a3e-123">Ha elő szeretné írni az okkódok használatát, akkor fel kell vennie ilyen kódokat.</span><span class="sxs-lookup"><span data-stu-id="46a3e-123">If you want to require reason codes, you might need to add them.</span></span> <span data-ttu-id="46a3e-124">Az **Okkódok** területen válassza a **Hozzáadás** elemet, válasszon egy okkódot, és jelölje be a mellette található **Engedélyezve** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="46a3e-124">Under **Reason codes**, select **Add**, select a reason code, and then select the **Enabled** checkbox next to it.</span></span>

8. <span data-ttu-id="46a3e-125">A **Hozzáférés korlátozása a kijelölt szerepkörökre** beállításnál válassza ki, hogy szeretné-e korlátozni a hozzáférést.</span><span class="sxs-lookup"><span data-stu-id="46a3e-125">Under **Restrict access to selected roles**, choose whether you want to restrict access.</span></span> <span data-ttu-id="46a3e-126">Ezután a **Szabadságtípus biztonsági szerepkörei** beállításnál válassza ki a biztonsági szerepköröket.</span><span class="sxs-lookup"><span data-stu-id="46a3e-126">Then select the security roles under **Security roles for this leave type**.</span></span> <span data-ttu-id="46a3e-127">A biztonsági szerepkörök a jelen eljárás korábbi pontján, a **Munkafolyamat-azonosító** beállításnál kiválasztott munkafolyamatban határozhatók meg.</span><span class="sxs-lookup"><span data-stu-id="46a3e-127">The security roles are defined in the workflow you selected under **Workflow ID** earlier in this procedure.</span></span>

9. <span data-ttu-id="46a3e-128">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46a3e-128">Select **Save**.</span></span>

## <a name="configure-preview-features"></a><span data-ttu-id="46a3e-129">Előzetes funkciók konfigurálása</span><span class="sxs-lookup"><span data-stu-id="46a3e-129">Configure preview features</span></span>

<span data-ttu-id="46a3e-130">Ha engedélyezte a szabadság és a távollét előzetes funkcióit, akkor konfigurálnia kell azok beállításait.</span><span class="sxs-lookup"><span data-stu-id="46a3e-130">If you've enabled preview features for Leave and absence, you need to configure settings for them, too.</span></span>

[!include [banner](includes/preview-feature-leave-absence.md)]

1. <span data-ttu-id="46a3e-131">Adja meg a szabadságtípus kerekítési beállításait.</span><span class="sxs-lookup"><span data-stu-id="46a3e-131">Set rounding options for the leave type.</span></span> <span data-ttu-id="46a3e-132">Választási lehetőségek: **Nincs**, **Fel**, **Le** és **Legközelebbi**.</span><span class="sxs-lookup"><span data-stu-id="46a3e-132">Options include **None**, **Up**, **Down**, and **Nearest**.</span></span> <span data-ttu-id="46a3e-133">A szabadságtípus kerekítési pontosságát is megadhatja.</span><span class="sxs-lookup"><span data-stu-id="46a3e-133">You can also set rounding precision for the leave type.</span></span>

2. <span data-ttu-id="46a3e-134">Adja meg a szabadságtípus **Munkaszünet-korrekció** beállítását.</span><span class="sxs-lookup"><span data-stu-id="46a3e-134">Set **Holiday correction** for the leave type.</span></span> <span data-ttu-id="46a3e-135">Ha bejelöli ezt a lehetőséget, akkor a Human Resources szolgáltatás a munkanapra eső napok száma alapján határozza meg, hogyan kell elszámolni a szabadságtípus távolléti idejét.</span><span class="sxs-lookup"><span data-stu-id="46a3e-135">When you select this option, Human Resources uses the number of holidays that fall on a work day to determine how to accrue time off for the leave type.</span></span> <span data-ttu-id="46a3e-136">Ha például karácsony napja hétfőre esik, akkor a Human Resources szolgáltatás levon egy napot a szabadságtípusból a könyvelés feldolgozásakor.</span><span class="sxs-lookup"><span data-stu-id="46a3e-136">For example, if Christmas Day falls on a Monday, Human Resources will subtract one day from the leave type when processing accruals.</span></span>

   <span data-ttu-id="46a3e-137">A szabadnapokat a munkaidőnaptárban állíthatja be.</span><span class="sxs-lookup"><span data-stu-id="46a3e-137">You set holidays in the working time calendar.</span></span> <span data-ttu-id="46a3e-138">További információ: [Munkaidőnaptár létrehozása](hr-leave-and-absence-working-time-calendar.md)</span><span class="sxs-lookup"><span data-stu-id="46a3e-138">For more information, see [Create a working time calendar](hr-leave-and-absence-working-time-calendar.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="46a3e-139">Lásd még</span><span class="sxs-lookup"><span data-stu-id="46a3e-139">See also</span></span>

- [<span data-ttu-id="46a3e-140">Szabadság és távollét áttekintése</span><span class="sxs-lookup"><span data-stu-id="46a3e-140">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
- [<span data-ttu-id="46a3e-141">Szabadság- és távolléti terv létrehozása</span><span class="sxs-lookup"><span data-stu-id="46a3e-141">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)
- [<span data-ttu-id="46a3e-142">Munkaidőnaptár létrehozása</span><span class="sxs-lookup"><span data-stu-id="46a3e-142">Create a working time calendar</span></span>](hr-leave-and-absence-working-time-calendar.md)