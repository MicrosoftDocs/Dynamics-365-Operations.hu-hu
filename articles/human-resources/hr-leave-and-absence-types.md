---
title: Szabadság- és távolléttípusok konfigurálása
description: Beállíthatja, hogy az alkalmazottak milyen típusú szabadságot vehetnek igénybe a Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
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
ms.openlocfilehash: df6e34fe6a23e6f0a8307a035752a35a15a3431c
ms.sourcegitcommit: 79f8aa2c0b166a423db9b8503da53e96e3fc43dc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2020
ms.locfileid: "3198050"
---
# <a name="configure-leave-and-absence-types"></a><span data-ttu-id="ae9f4-103">Szabadság- és távolléttípusok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ae9f4-103">Configure leave and absence types</span></span>

<span data-ttu-id="ae9f4-104">A Dynamics 365 Human Resources szabadságtípusai határozzák meg az alkalmazottak számára elérhető különböző típusú távolléteket.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-104">Leave types in Dynamics 365 Human Resources define the types of absences that employees can report.</span></span> <span data-ttu-id="ae9f4-105">A szabadságtípusokat a szervezet igényeihez igazíthatja.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-105">You can tailor leave types according to the needs of your organization.</span></span> <span data-ttu-id="ae9f4-106">Példák a szabadságtípusokra:</span><span class="sxs-lookup"><span data-stu-id="ae9f4-106">Examples of leave types include:</span></span>

- <span data-ttu-id="ae9f4-107">Fizetett szabadság (PTO)</span><span class="sxs-lookup"><span data-stu-id="ae9f4-107">Paid time off (PTO)</span></span>
- <span data-ttu-id="ae9f4-108">Fizetés nélküli szabadság</span><span class="sxs-lookup"><span data-stu-id="ae9f4-108">Unpaid leave</span></span>
- <span data-ttu-id="ae9f4-109">Fizetett szabadság</span><span class="sxs-lookup"><span data-stu-id="ae9f4-109">Paid vacation</span></span>
- <span data-ttu-id="ae9f4-110">Betegszabadság</span><span class="sxs-lookup"><span data-stu-id="ae9f4-110">Sick leave</span></span>
- <span data-ttu-id="ae9f4-111">Betegszabadság</span><span class="sxs-lookup"><span data-stu-id="ae9f4-111">Medical leave</span></span>
- <span data-ttu-id="ae9f4-112">Családi okokból történő</span><span class="sxs-lookup"><span data-stu-id="ae9f4-112">Family leave</span></span>
- <span data-ttu-id="ae9f4-113">Rövid távú fogyatékosság</span><span class="sxs-lookup"><span data-stu-id="ae9f4-113">Short-term disability</span></span>
- <span data-ttu-id="ae9f4-114">Haláleset miatti szabadság</span><span class="sxs-lookup"><span data-stu-id="ae9f4-114">Bereavement leave</span></span>

## <a name="add-a-leave-type"></a><span data-ttu-id="ae9f4-115">Szabadságtípus hozzáadása</span><span class="sxs-lookup"><span data-stu-id="ae9f4-115">Add a leave type</span></span>

1. <span data-ttu-id="ae9f4-116">A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-116">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="ae9f4-117">A **Beállítás**területen válassza a **Szabadság- és távolléttípusok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-117">Under **Setup**, select **Leave and absence types**.</span></span>

3. <span data-ttu-id="ae9f4-118">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-118">Select **New**.</span></span>

4. <span data-ttu-id="ae9f4-119">Írjon be a szabadságtípus nevét a **Típus** mezőbe, válasszon egy munkafolyamatot a **Munkafolyamat-azonosító** listáról, és adja meg a leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-119">Enter a name for the leave type under **Type**, select a workflow from **Workflow ID**, and enter a description under **Description**.</span></span>

5. <span data-ttu-id="ae9f4-120">Az **Általános** lapon válassza ki a **Nincs**, az **Ütemezett** vagy a **Nem ütemezett** elemet a **Kategória** legördülő listáról.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-120">In **General**, select **None**, **Scheduled**, or **Unscheduled** from the **Category** dropdown.</span></span>

6. <span data-ttu-id="ae9f4-121">Válasszon bevételkódot a **Bevételkód** legördülő listáról.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-121">Select an earning code from the **Earning code** dropdown.</span></span>

7. <span data-ttu-id="ae9f4-122">**Az okkódot meg kell adni** beállításnál válassza ki, hogy szeretné-e előírni az okkód megadását.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-122">Under **Reason code required**, choose whether you want to require a reason code.</span></span> <span data-ttu-id="ae9f4-123">Ha elő szeretné írni az okkódok használatát, akkor fel kell vennie ilyen kódokat.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-123">If you want to require reason codes, you might need to add them.</span></span> <span data-ttu-id="ae9f4-124">Az **Okkódok** területen válassza a **Hozzáadás** elemet, válasszon egy okkódot, és jelölje be a mellette található **Engedélyezve** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-124">Under **Reason codes**, select **Add**, select a reason code, and then select the **Enabled** checkbox next to it.</span></span>

8. <span data-ttu-id="ae9f4-125">A **Hozzáférés korlátozása a kijelölt szerepkörökre** beállításnál válassza ki, hogy szeretné-e korlátozni a hozzáférést.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-125">Under **Restrict access to selected roles**, choose whether you want to restrict access.</span></span> <span data-ttu-id="ae9f4-126">Ezután a **Szabadságtípus biztonsági szerepkörei** beállításnál válassza ki a biztonsági szerepköröket.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-126">Then select the security roles under **Security roles for this leave type**.</span></span> <span data-ttu-id="ae9f4-127">A biztonsági szerepkörök a jelen eljárás korábbi pontján, a **Munkafolyamat-azonosító** beállításnál kiválasztott munkafolyamatban határozhatók meg.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-127">The security roles are defined in the workflow you selected under **Workflow ID** earlier in this procedure.</span></span>

9. <span data-ttu-id="ae9f4-128">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-128">Select **Save**.</span></span>

## <a name="configure-leave-type-rules"></a><span data-ttu-id="ae9f4-129">A szabadságtípus-szabályok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ae9f4-129">Configure leave type rules</span></span>

1. <span data-ttu-id="ae9f4-130">Adja meg a szabadságtípus kerekítési beállításait.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-130">Set rounding options for the leave type.</span></span> <span data-ttu-id="ae9f4-131">Választási lehetőségek: **Nincs**, **Fel**, **Le** és **Legközelebbi**.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-131">Options include **None**, **Up**, **Down**, and **Nearest**.</span></span> <span data-ttu-id="ae9f4-132">A szabadságtípus kerekítési pontosságát is megadhatja.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-132">You can also set rounding precision for the leave type.</span></span>

2. <span data-ttu-id="ae9f4-133">Adja meg a szabadságtípus **Munkaszünet-korrekció** beállítását.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-133">Set **Holiday correction** for the leave type.</span></span> <span data-ttu-id="ae9f4-134">Ha bejelöli ezt a lehetőséget, akkor a Human Resources szolgáltatás a munkanapra eső napok száma alapján határozza meg, hogyan kell elszámolni a szabadságtípus távolléti idejét.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-134">When you select this option, Human Resources uses the number of holidays that fall on a work day to determine how to accrue time off for the leave type.</span></span> <span data-ttu-id="ae9f4-135">Ha például karácsony napja hétfőre esik, akkor a Human Resources szolgáltatás levon egy napot a szabadságtípusból a könyvelés feldolgozásakor.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-135">For example, if Christmas Day falls on a Monday, Human Resources will subtract one day from the leave type when processing accruals.</span></span>

   <span data-ttu-id="ae9f4-136">A szabadnapokat a munkaidőnaptárban állíthatja be.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-136">You set holidays in the working time calendar.</span></span> <span data-ttu-id="ae9f4-137">További információ: [Munkaidőnaptár létrehozása](hr-leave-and-absence-working-time-calendar.md)</span><span class="sxs-lookup"><span data-stu-id="ae9f4-137">For more information, see [Create a working time calendar](hr-leave-and-absence-working-time-calendar.md)</span></span>
   
## <a name="configure-preview-features"></a><span data-ttu-id="ae9f4-138">Előzetes funkciók konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ae9f4-138">Configure preview features</span></span>

<span data-ttu-id="ae9f4-139">Ha engedélyezte a szabadság és a távollét előzetes funkcióit, akkor konfigurálnia kell azok beállításait.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-139">If you've enabled preview features for Leave and absence, you need to configure settings for them, too.</span></span>

[!include [banner](includes/preview-feature-leave-absence.md)]

1. <span data-ttu-id="ae9f4-140">Válassza ki a szabadságtípust, amelyhez az átviteli egyenlegek át lesznek irányítva.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-140">Choose the leave type for carry forward balances to be transferred to.</span></span> <span data-ttu-id="ae9f4-141">Az átvitelhez új szabadságtípust is létre lehet hozni.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-141">You can also create a new leave type for carry forward.</span></span> 

## <a name="see-also"></a><span data-ttu-id="ae9f4-142">Lásd még</span><span class="sxs-lookup"><span data-stu-id="ae9f4-142">See also</span></span>

- [<span data-ttu-id="ae9f4-143">Szabadság és távollét áttekintése</span><span class="sxs-lookup"><span data-stu-id="ae9f4-143">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
- [<span data-ttu-id="ae9f4-144">Szabadság- és távolléti terv létrehozása</span><span class="sxs-lookup"><span data-stu-id="ae9f4-144">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)
- [<span data-ttu-id="ae9f4-145">Munkaidőnaptár létrehozása</span><span class="sxs-lookup"><span data-stu-id="ae9f4-145">Create a working time calendar</span></span>](hr-leave-and-absence-working-time-calendar.md)
