---
title: A szabadságok vásárlásával és eladásával kapcsolatos irányelvek kezelése
description: Engedélyezheti az alkalmazottaknak, hogy vásárolják és eladják a szabadságukat a Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
manager: AnnBe
ms.date: 06/01/2020
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
ms.openlocfilehash: 859445f2b6e980b5960e512e69129f6a8fc6df2b
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2020
ms.locfileid: "3429013"
---
# <a name="manage-buy-and-sell-leave-policies"></a><span data-ttu-id="6dff9-103">A szabadságok vásárlásával és eladásával kapcsolatos irányelvek kezelése</span><span class="sxs-lookup"><span data-stu-id="6dff9-103">Manage buy and sell leave policies</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="6dff9-104">Engedélyezheti az alkalmazottaknak, hogy szabadságot vegyenek egy szabadságvásárlási irányelv létrehozásával.</span><span class="sxs-lookup"><span data-stu-id="6dff9-104">You can enable employees to buy leave by creating a buy leave policy.</span></span>  

## <a name="enable-employees-to-buy-and-sell-leave"></a><span data-ttu-id="6dff9-105">Szabadság vásárlásának és eladásának engedélyezése az alkalmazottak számára</span><span class="sxs-lookup"><span data-stu-id="6dff9-105">Enable employees to buy and sell leave</span></span>

1. <span data-ttu-id="6dff9-106">A **Szabadság- és távollétparaméterek** oldalon válassza az **Igen** lehetőséget a **Szabadság vásárlásának engedélyezése az alkalmazottak számára** esetében.</span><span class="sxs-lookup"><span data-stu-id="6dff9-106">On the **Leave and absence parameters** page, select **Yes** for **Allow employees to buy leave**.</span></span> 

## <a name="create-a-buy-leave-policy"></a><span data-ttu-id="6dff9-107">Szabadságvásárlási irányelv létrehozása</span><span class="sxs-lookup"><span data-stu-id="6dff9-107">Create a buy leave policy</span></span>

1. <span data-ttu-id="6dff9-108">A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.</span><span class="sxs-lookup"><span data-stu-id="6dff9-108">On the **Leave and absence** page, select the **Links** tab.</span></span> 

2. <span data-ttu-id="6dff9-109">Válassza ki a **Szabadságok vásárlásával és eladásával kapcsolatos irányelv** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6dff9-109">Select **Buy and sell leave policy**.</span></span>

3. <span data-ttu-id="6dff9-110">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6dff9-110">Select **New**.</span></span>

4. <span data-ttu-id="6dff9-111">Adja meg a **Név** és **Leírás** elemet a **Szabadságok vásárlásával és eladásával kapcsolatos irányelv** alatti irányelvhez.</span><span class="sxs-lookup"><span data-stu-id="6dff9-111">Enter a **Name** and **Description** for the policy under **Buy and sell leave policy**.</span></span> 

5. <span data-ttu-id="6dff9-112">Válassza ki az **Irányelv típusa** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6dff9-112">Select a **Policy type**.</span></span> 

   <span data-ttu-id="6dff9-113">A rendelkezésre álló irányelvtípusok az **Összeg** és az **Órák hetente**.</span><span class="sxs-lookup"><span data-stu-id="6dff9-113">The available policy types are **Amount** and **Hours per week**.</span></span> <span data-ttu-id="6dff9-114">Válassza ki az **Összeg** elemet egy **Rögzített szám** megadásához az alkalmazottak által vásárolható és eladható maximális összeg megadásához.</span><span class="sxs-lookup"><span data-stu-id="6dff9-114">Select **Amount** to enter a **Fixed amount** for the maximum amounts employees can buy and sell.</span></span> <span data-ttu-id="6dff9-115">Ha az **Órák hetente** lehetőséget választja, az alkalmazott hozzárendelt munkanaptárban megadott munkaidőt használja a program a maximális összeg megállapítására.</span><span class="sxs-lookup"><span data-stu-id="6dff9-115">If you select **Hours per week**, the working time defined in the employee's assigned working time calendar is used to determine the maximum amount of the policy.</span></span> 

6. <span data-ttu-id="6dff9-116">Válassza ki a **Kezdő dátum** és **Záró dátum** lehetőséget az irányelv esetében.</span><span class="sxs-lookup"><span data-stu-id="6dff9-116">Select a **Start date** and **End date** for the policy.</span></span> <span data-ttu-id="6dff9-117">A vásárlásra vagy eladásra irányuló kérelem csak ebben az időkeretben érhető el elküldéshez.</span><span class="sxs-lookup"><span data-stu-id="6dff9-117">Requests to buy or sell leave will only be available for submission during this time frame.</span></span> 

7. <span data-ttu-id="6dff9-118">A **Vásárlási irányelv** alatt válassza a válassza ki a **Teljes munkaidő egyenérték** (FTE) lehetőséget a maximális összegnek az alkalmazott beosztásához megadott FTE alapján történő meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="6dff9-118">Under **Buy policy**, select **Full time equivalency** (FTE) to prorate the maximum amount based on the FTE defined on the employee's position.</span></span> <span data-ttu-id="6dff9-119">Ha az irányelv típusa **Összeg**, adja meg a **Maximális rögzített összeg** értékét.</span><span class="sxs-lookup"><span data-stu-id="6dff9-119">If the policy type is **Amount**, enter a **Maximum fixed amount**.</span></span> 

8. <span data-ttu-id="6dff9-120">Válassza a **Hozzáadás** lehetőséget azon alkalmazottak típusának megadásához, akik szabadságot vásárolhatnak.</span><span class="sxs-lookup"><span data-stu-id="6dff9-120">Select **Add** to add the leave types for employees to buy leave.</span></span> <span data-ttu-id="6dff9-121">Az irányelvhez több szabadságtípust is hozzáadhat.</span><span class="sxs-lookup"><span data-stu-id="6dff9-121">You can add multiple leave types to the policy.</span></span> 

9. <span data-ttu-id="6dff9-122">Adja meg a szabadságtípus **Munkaviszony hossza hónapokban** elemét annak engedélyezéséhez, hogy a munkaviszony hossza hónapokban határozza meg a maximális összeget, amennyit egy alkalmazott vásárolhat.</span><span class="sxs-lookup"><span data-stu-id="6dff9-122">Enter the **Months of service** for the leave type to enable different months of service to determine the maximum amount an employee can buy.</span></span> 

10. <span data-ttu-id="6dff9-123">Adja meg a szabadságtípushoz a **Maximális összeg** elemet.</span><span class="sxs-lookup"><span data-stu-id="6dff9-123">Enter the **Maximum amount** for the leave type.</span></span> 

11. <span data-ttu-id="6dff9-124">Adja meg az **Arány** elemet, amely megadja a megvásárolható szabadság mértékét.</span><span class="sxs-lookup"><span data-stu-id="6dff9-124">Enter the **Rate** at which the employee will buy the leave.</span></span> 

12. <span data-ttu-id="6dff9-125">Tetszés szerint adja meg a szabadságvásárláshoz használt **Bevételkódot**.</span><span class="sxs-lookup"><span data-stu-id="6dff9-125">Optionally enter the **Earning code** to be used for buying leave.</span></span> 

13. <span data-ttu-id="6dff9-126">Opcionálisan azt is beállíthatja, hogy az FTE használatával határozza meg a szabadságtípus maximális összegét.</span><span class="sxs-lookup"><span data-stu-id="6dff9-126">Optionally set whether to use FTE to determine the maximum amount for the leave type.</span></span> 

## <a name="add-the-buy-and-sell-leave-policy-to-a-leave-and-absence-plan"></a><span data-ttu-id="6dff9-127">A szabadság vásárlásával és eladásával kapcsolatos irányelv hozzáadása egy szabadsági és távolléti tervhez</span><span class="sxs-lookup"><span data-stu-id="6dff9-127">Add the buy and sell leave policy to a leave and absence plan</span></span>

1. <span data-ttu-id="6dff9-128">A **Szabadság és távollét** oldalon válasszon ki egy szabadság és távollét tervet.</span><span class="sxs-lookup"><span data-stu-id="6dff9-128">On the **Leave and absence** page, select a leave and absence plan.</span></span>

2. <span data-ttu-id="6dff9-129">A **Szabályok** alatt válassza ki a **Szabadságok vásárlásával és eladásával kapcsolatos irányelv** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6dff9-129">Under **Rules**, select **Buy and sell leave policy**.</span></span>

## <a name="see-also"></a><span data-ttu-id="6dff9-130">Lásd még</span><span class="sxs-lookup"><span data-stu-id="6dff9-130">See also</span></span>

[<span data-ttu-id="6dff9-131">Szabadság és távollét áttekintése</span><span class="sxs-lookup"><span data-stu-id="6dff9-131">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="6dff9-132">Szabadság- és távolléttípusok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="6dff9-132">Configure leave and absence types</span></span>](hr-leave-and-absence-types.md)</br>
[<span data-ttu-id="6dff9-133">Szabadság- és távolléti tervek elhatárolása</span><span class="sxs-lookup"><span data-stu-id="6dff9-133">Accrue leave and absence plans</span></span>](hr-leave-and-absence-accrue.md)</br>
[<span data-ttu-id="6dff9-134">Szabadság vásárlása és eladása</span><span class="sxs-lookup"><span data-stu-id="6dff9-134">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

