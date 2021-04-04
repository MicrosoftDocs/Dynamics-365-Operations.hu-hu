---
title: A szabadságok vásárlásával és eladásával kapcsolatos irányelvek kezelése
description: Engedélyezheti az alkalmazottaknak, hogy vásárolják és eladják a szabadságukat a Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
manager: tfehr
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeaveBuySellPolicy, LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ccc6bf2e8b070e92cc4dbb98d8ec35ce60723516
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5468083"
---
# <a name="manage-buy-and-sell-leave-policies"></a><span data-ttu-id="c6937-103">Szabadság vásárlásával és eladásával kapcsolatos irányelv kezelése</span><span class="sxs-lookup"><span data-stu-id="c6937-103">Manage buy and sell leave policies</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="c6937-104">Engedélyezheti az alkalmazottaknak, hogy szabadságot vegyenek és adjanak el egy szabadságvásárlási és eladási irányelv létrehozásával.</span><span class="sxs-lookup"><span data-stu-id="c6937-104">You can enable employees to buy and sell leave by creating a buy and sell leave policy.</span></span> <span data-ttu-id="c6937-105">Ezeket a szabályokat konfigurálhatja úgy, hogy munkafolyamatot használjon jóváhagyásra, beállítsa a maximális összegeket és mértékeket, valamint megadhatja a beszerzési és eladási árat.</span><span class="sxs-lookup"><span data-stu-id="c6937-105">You can configure these policies to use workflow for approvals, set maximum amounts and rates, and set rates for buying and selling.</span></span> 

## <a name="enable-employees-to-buy-and-sell-leave"></a><span data-ttu-id="c6937-106">Szabadság vásárlásának és eladásának engedélyezése az alkalmazottak számára</span><span class="sxs-lookup"><span data-stu-id="c6937-106">Enable employees to buy and sell leave</span></span>

1. <span data-ttu-id="c6937-107">A **Szabadság- és távollét** paraméterei oldalon válassza az **Igen** lehetőséget a **Szabadság eladásának engedélyezése az alkalmazottak számára** **Szabadság eladásának engedélyezése a munkavállalók számára** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c6937-107">On the **Leave and absence parameters** page, select **Yes** for **Allow employees to buy leave** and **Allow employees to sell leave**.</span></span>

## <a name="create-a-buy-and-sell-leave-policy"></a><span data-ttu-id="c6937-108">Szabadság vásárlási és eladási irányelv létrehozása</span><span class="sxs-lookup"><span data-stu-id="c6937-108">Create a buy and sell leave policy</span></span>

1. <span data-ttu-id="c6937-109">A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.</span><span class="sxs-lookup"><span data-stu-id="c6937-109">On the **Leave and absence** page, select the **Links** tab.</span></span> 

2. <span data-ttu-id="c6937-110">Válassza ki a **Szabadságok vásárlásával és eladásával kapcsolatos irányelv** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c6937-110">Select **Buy and sell leave policy**.</span></span>

3. <span data-ttu-id="c6937-111">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c6937-111">Select **New**.</span></span>

4. <span data-ttu-id="c6937-112">Adja meg a **Név** és **Leírás** elemet a **Szabadságok vásárlásával és eladásával kapcsolatos irányelv** alatti irányelvhez.</span><span class="sxs-lookup"><span data-stu-id="c6937-112">Enter a **Name** and **Description** for the policy under **Buy and sell leave policy**.</span></span> 

5. <span data-ttu-id="c6937-113">Válassza ki az **Irányelv típusa** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c6937-113">Select a **Policy type**.</span></span> 

   <span data-ttu-id="c6937-114">A rendelkezésre álló irányelvtípusok az **Összeg** és az **Órák hetente**.</span><span class="sxs-lookup"><span data-stu-id="c6937-114">The available policy types are **Amount** and **Hours per week**.</span></span> <span data-ttu-id="c6937-115">Válassza ki az **Összeg** elemet egy **Rögzített szám** megadásához az alkalmazottak által vásárolható és eladható maximális összeg megadásához.</span><span class="sxs-lookup"><span data-stu-id="c6937-115">Select **Amount** to enter a **Fixed amount** for the maximum amounts employees can buy and sell.</span></span> <span data-ttu-id="c6937-116">Ha az **Órák hetente** lehetőséget választja, az alkalmazott hozzárendelt munkanaptárban megadott munkaidőt használja a program a maximális összeg megállapítására.</span><span class="sxs-lookup"><span data-stu-id="c6937-116">If you select **Hours per week**, the working time defined in the employee's assigned working time calendar is used to determine the maximum amount of the policy.</span></span> 

6. <span data-ttu-id="c6937-117">Válassza ki a **Kezdő dátum** és **Záró dátum** lehetőséget az irányelv esetében.</span><span class="sxs-lookup"><span data-stu-id="c6937-117">Select a **Start date** and **End date** for the policy.</span></span> <span data-ttu-id="c6937-118">A vásárlásra vagy eladásra irányuló kérelem csak ebben az időkeretben érhető el elküldéshez.</span><span class="sxs-lookup"><span data-stu-id="c6937-118">Requests to buy or sell leave will only be available for submission during this time frame.</span></span> 

7. <span data-ttu-id="c6937-119">Válassza ki a házirend **Munkafolyamat-azonosítóját**.</span><span class="sxs-lookup"><span data-stu-id="c6937-119">Select a **Workflow ID** for the policy.</span></span> <span data-ttu-id="c6937-120">A vásárlási és eladási kérelmek ezt a munkafolyamatot használják áttekintés és jóváhagyás céljából.</span><span class="sxs-lookup"><span data-stu-id="c6937-120">Any buy and sell requests will use this workflow for review and approval.</span></span> 

8. <span data-ttu-id="c6937-121">A **Vásárlási irányelv** alatt válassza a válassza ki a **Teljes munkaidő egyenérték** (FTE) lehetőséget a maximális összegnek az alkalmazott beosztásához megadott FTE alapján történő meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="c6937-121">Under **Buy policy**, select **Full time equivalency** (FTE) to prorate the maximum amount based on the FTE defined on the employee's position.</span></span> <span data-ttu-id="c6937-122">Ha az irányelv típusa **Összeg**, adja meg a **Maximális rögzített összeg** értékét.</span><span class="sxs-lookup"><span data-stu-id="c6937-122">If the policy type is **Amount**, enter a **Maximum fixed amount**.</span></span> 

9. <span data-ttu-id="c6937-123">Válassza a **Hozzáadás** lehetőséget azon alkalmazottak típusának megadásához, akik szabadságot vásárolhatnak.</span><span class="sxs-lookup"><span data-stu-id="c6937-123">Select **Add** to add the leave types for employees to buy leave.</span></span> <span data-ttu-id="c6937-124">Az irányelvhez több szabadságtípust is hozzáadhat.</span><span class="sxs-lookup"><span data-stu-id="c6937-124">You can add multiple leave types to the policy.</span></span> 

10. <span data-ttu-id="c6937-125">Adja meg a szabadságtípus **Munkaviszony hossza hónapokban** elemét annak engedélyezéséhez, hogy a munkaviszony hossza hónapokban határozza meg a maximális összeget, amennyit egy alkalmazott vásárolhat.</span><span class="sxs-lookup"><span data-stu-id="c6937-125">Enter the **Months of service** for the leave type to enable different months of service to determine the maximum amount an employee can buy.</span></span> 

11. <span data-ttu-id="c6937-126">Adja meg a szabadságtípushoz a **Maximális összeg** elemet.</span><span class="sxs-lookup"><span data-stu-id="c6937-126">Enter the **Maximum amount** for the leave type.</span></span> 

12. <span data-ttu-id="c6937-127">Adja meg az **Arány** elemet, amely megadja a megvásárolható szabadság mértékét.</span><span class="sxs-lookup"><span data-stu-id="c6937-127">Enter the **Rate** at which the employee will buy the leave.</span></span> 

13. <span data-ttu-id="c6937-128">Tetszés szerint adja meg a szabadságvásárláshoz használt **Bevételkódot**.</span><span class="sxs-lookup"><span data-stu-id="c6937-128">Optionally enter the **Earning code** to be used for buying leave.</span></span> 

14. <span data-ttu-id="c6937-129">Opcionálisan azt is beállíthatja, hogy az FTE használatával határozza meg a szabadságtípus maximális összegét.</span><span class="sxs-lookup"><span data-stu-id="c6937-129">Optionally set whether to use FTE to determine the maximum amount for the leave type.</span></span> 

15. <span data-ttu-id="c6937-130">Értékesítési irányelv létrehozásához kövesse a 8–14. lépéseket az **Eladási irányelv** részben.</span><span class="sxs-lookup"><span data-stu-id="c6937-130">To create a sell policy, follow steps 8 through 14 under **Sell policy**.</span></span> 

## <a name="add-the-buy-and-sell-leave-policy-to-a-leave-and-absence-plan"></a><span data-ttu-id="c6937-131">A szabadság vásárlásával és eladásával kapcsolatos irányelv hozzáadása egy szabadsági és távolléti tervhez</span><span class="sxs-lookup"><span data-stu-id="c6937-131">Add the buy and sell leave policy to a leave and absence plan</span></span>

1. <span data-ttu-id="c6937-132">A **Szabadság és távollét** oldalon válasszon ki egy szabadság és távollét tervet.</span><span class="sxs-lookup"><span data-stu-id="c6937-132">On the **Leave and absence** page, select a leave and absence plan.</span></span>

2. <span data-ttu-id="c6937-133">A **Szabályok** alatt válassza ki a **Szabadságok vásárlásával és eladásával kapcsolatos irányelv** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c6937-133">Under **Rules**, select **Buy and sell leave policy**.</span></span>

## <a name="see-also"></a><span data-ttu-id="c6937-134">Lásd még</span><span class="sxs-lookup"><span data-stu-id="c6937-134">See also</span></span>

[<span data-ttu-id="c6937-135">Szabadság és távollét áttekintése</span><span class="sxs-lookup"><span data-stu-id="c6937-135">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="c6937-136">Szabadság- és távolléttípusok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c6937-136">Configure leave and absence types</span></span>](hr-leave-and-absence-types.md)</br>
[<span data-ttu-id="c6937-137">Szabadság- és távolléti tervek elhatárolása</span><span class="sxs-lookup"><span data-stu-id="c6937-137">Accrue leave and absence plans</span></span>](hr-leave-and-absence-accrue.md)</br>
[<span data-ttu-id="c6937-138">Szabadság vásárlása és eladása</span><span class="sxs-lookup"><span data-stu-id="c6937-138">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]