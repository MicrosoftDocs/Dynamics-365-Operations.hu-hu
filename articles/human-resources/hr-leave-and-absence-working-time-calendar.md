---
title: Munkaidőnaptár létrehozása
description: A Dynamics 365 Human Resources alkalmazásban munkaidőnaptárt, szabadnapokat és munkaidőket definiálhat.
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
ms.openlocfilehash: 641f66c75875cfba51af3753223a070d7cb7dc50
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009317"
---
# <a name="create-a-working-time-calendar"></a><span data-ttu-id="5e44f-103">Munkaidőnaptár létrehozása</span><span class="sxs-lookup"><span data-stu-id="5e44f-103">Create a working time calendar</span></span>

<span data-ttu-id="5e44f-104">A Dynamics 365 Human Resources alkalmazásban a munkaidőnaptár jeleníti meg azokat a napokat és órákat, amikor az alkalmazottak dolgoznak a szervezetben.</span><span class="sxs-lookup"><span data-stu-id="5e44f-104">A working time calendar in Dynamics 365 Human Resources shows the days and hours that employees work in your organization.</span></span> <span data-ttu-id="5e44f-105">Amikor egy alkalmazott szabadságra vonatkozó kérelmet küld, nem kell aggódnia a szabadnapok és a leállások miatt.</span><span class="sxs-lookup"><span data-stu-id="5e44f-105">When an employee submits a time-off request, they don't have to worry about holidays and closures.</span></span>

<span data-ttu-id="5e44f-106">A szabadságkérelmek egyszerűsítése érdekében konfigurálja a következő elemeket a szervezetnél:</span><span class="sxs-lookup"><span data-stu-id="5e44f-106">To streamline time-off requests, configure these items for your organization:</span></span>

- <span data-ttu-id="5e44f-107">Munkaidőnaptár</span><span class="sxs-lookup"><span data-stu-id="5e44f-107">Working time calendar</span></span>
- <span data-ttu-id="5e44f-108">Szabadnapok és leállások</span><span class="sxs-lookup"><span data-stu-id="5e44f-108">Holidays and closures</span></span>
- <span data-ttu-id="5e44f-109">Nem munkaidő</span><span class="sxs-lookup"><span data-stu-id="5e44f-109">Non-work time</span></span>

<span data-ttu-id="5e44f-110">Az utolsó két elemet a munkaidőnaptár beállítása közben is felveheti.</span><span class="sxs-lookup"><span data-stu-id="5e44f-110">You can add the last two items while you're setting up a working time calendar.</span></span> <span data-ttu-id="5e44f-111">Külön is konfigurálhatja vagy módosíthatja ezeket.</span><span class="sxs-lookup"><span data-stu-id="5e44f-111">You can also configure or update them separately.</span></span>

## <a name="set-up-a-working-time-calendar"></a><span data-ttu-id="5e44f-112">Munkaidőnaptár beállítása</span><span class="sxs-lookup"><span data-stu-id="5e44f-112">Set up a working time calendar</span></span>

<span data-ttu-id="5e44f-113">Állítson be legalább egy munkaidőnaptárt, amely megjeleníti a működési idejének napjait és óráit.</span><span class="sxs-lookup"><span data-stu-id="5e44f-113">Set up at least one working time calendar that shows your days and hours of operation.</span></span> <span data-ttu-id="5e44f-114">Ha több országban és régióban van jelen, akkor lehetséges, hogy minden területhez érdemes munkaidőnaptárt beállítania.</span><span class="sxs-lookup"><span data-stu-id="5e44f-114">If you have locations in multiple countries and regions, you might want to set up a working time calendar for each area.</span></span>

1. <span data-ttu-id="5e44f-115">A **Szervezet felügyelete** oldalon válassza a **Naptárak** elemet.</span><span class="sxs-lookup"><span data-stu-id="5e44f-115">On the **Organization administration** page, select **Calendars**.</span></span>

2. <span data-ttu-id="5e44f-116">Válassza az **Új** lehetőséget, és adja meg a naptár nevét és leírását.</span><span class="sxs-lookup"><span data-stu-id="5e44f-116">Select **New** and enter a name and description for your calendar.</span></span>

3. <span data-ttu-id="5e44f-117">A **Létrehozási beállítások** területen válassza ki a szervezet munkanapjait és munkaidőit.</span><span class="sxs-lookup"><span data-stu-id="5e44f-117">Under **Generation options**, select the work days for your organization and enter work times.</span></span> 
   - <span data-ttu-id="5e44f-118">Munkaszünet vagy leállás hozzáadásához válassza a **Hozzáadás** gombot a **Szabadnapok és leállások** elem mellett.</span><span class="sxs-lookup"><span data-stu-id="5e44f-118">To add a holiday or closure, select the **Add** button next to **Holidays and closures**.</span></span>
   - <span data-ttu-id="5e44f-119">Ha olyan időt szeretne hozzáadni, amely nem munkaidő, például ebédet vagy szünetet, akkor válassza a **Hozzáadás** gombot a **NEM MUNKAIDŐ** területen, és adja meg a nevet és az időtartományt.</span><span class="sxs-lookup"><span data-stu-id="5e44f-119">To add non-work time, like lunches or breaks, select **Add** under **NON-WORK TIME** and enter the name and time range.</span></span>

4. <span data-ttu-id="5e44f-120">A **Napok** beállításnál válassza a **Létrehozás** lehetőséget, amivel létrehozza a napokat a naptárban.</span><span class="sxs-lookup"><span data-stu-id="5e44f-120">Under **Days**, select **Generate** to generate the days in your calendar.</span></span> <span data-ttu-id="5e44f-121">Adja meg a naptár dátumtartományát, majd válassza a **Napok létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5e44f-121">Enter the date range for your calendar and then select **Generate days**.</span></span>

5. <span data-ttu-id="5e44f-122">Munkaütemezések hozzáadásához a **Munkaütemezés** beállításnál válassza a **Hozzáadás** gombot, majd adja meg az egyes munkaütemezések idejét.</span><span class="sxs-lookup"><span data-stu-id="5e44f-122">To add work schedules, under **Work schedule**, select **Add** and then enter the times for each work schedule.</span></span>

## <a name="configure-holidays-and-closures"></a><span data-ttu-id="5e44f-123">Szabadnapok és leállások konfigurálása</span><span class="sxs-lookup"><span data-stu-id="5e44f-123">Configure holidays and closures</span></span>

<span data-ttu-id="5e44f-124">A munkaidőnaptárban külön is hozzáadhatja és módosíthatja a szabadnapokat és a leállásokat.</span><span class="sxs-lookup"><span data-stu-id="5e44f-124">You can add or change holidays and closures separately from a working time calendar.</span></span>

1. <span data-ttu-id="5e44f-125">A **Szervezet felügyelete** oldalon válassza a **Szabadnapok és leállások** elemet.</span><span class="sxs-lookup"><span data-stu-id="5e44f-125">On the **Organization administration** page, select **Holidays and closures**.</span></span>

2. <span data-ttu-id="5e44f-126">Válassza az **Új** lehetőséget, és adja meg a szabadnap vagy leállás nevét és dátumát.</span><span class="sxs-lookup"><span data-stu-id="5e44f-126">Select **New** and enter a name and date for the holiday or closure.</span></span>

## <a name="configure-non-work-time"></a><span data-ttu-id="5e44f-127">Nem munkaidő konfigurálása</span><span class="sxs-lookup"><span data-stu-id="5e44f-127">Configure non-work time</span></span>

<span data-ttu-id="5e44f-128">A munkaidőnaptárban külön is hozzáadhatja és módosíthatja a nem munkaidőnek számító időket.</span><span class="sxs-lookup"><span data-stu-id="5e44f-128">You can add or change non-work times separately from a working time calendar.</span></span>

1. <span data-ttu-id="5e44f-129">A **Szervezet felügyelete** oldalon válassza a **Nem munkaidő** elemet.</span><span class="sxs-lookup"><span data-stu-id="5e44f-129">On the **Organization administration** page, select **Non-work time**.</span></span>

2. <span data-ttu-id="5e44f-130">Válassza az **Új** lehetőséget, és adja meg a nem munkaidőnek számító idő nevét és időtartományát.</span><span class="sxs-lookup"><span data-stu-id="5e44f-130">Select **New** and enter a name and time range for the non-work time.</span></span>

## <a name="leave-and-absence-preview-feature"></a><span data-ttu-id="5e44f-131">Szabadság és távollét előzetes funkciója</span><span class="sxs-lookup"><span data-stu-id="5e44f-131">Leave and absence preview feature</span></span>

[!include [banner](includes/preview-feature-leave-absence.md)]

<span data-ttu-id="5e44f-132">Ha engedélyezte a szabadsággal és a távolléttel kapcsolatos munkaszünet-korrekciók előzetes funkcióját, akkor a Human Resources a szabadnapok és a leállások dátuma alapján határozza meg, hogy hány napot kell módosítani a naptárba bejegyzett alkalmazottaknál.</span><span class="sxs-lookup"><span data-stu-id="5e44f-132">If you've enabled the Leave and absence bank holiday corrections preview feature, Human Resources uses holidays and closure dates to determine the number of days to adjust for employees enrolled in the calendar.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e44f-133">Lásd még</span><span class="sxs-lookup"><span data-stu-id="5e44f-133">See also</span></span>

- [<span data-ttu-id="5e44f-134">Szabadság és távollét áttekintése</span><span class="sxs-lookup"><span data-stu-id="5e44f-134">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
- [<span data-ttu-id="5e44f-135">Szabadság- és távolléttípusok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="5e44f-135">Configure leave and absence types</span></span>](hr-leave-and-absence-types.md)
