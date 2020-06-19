---
title: Szabadság- és távollétparaméterek konfigurálása
description: Emberi erőforrások paramétereinek meghatározása a szabadsághoz és a távolléthez a Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5e4d3b3e4b373631bed5e2d7e3c3a4e14f0c5c98
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2020
ms.locfileid: "3428944"
---
# <a name="configure-leave-and-absence-parameters"></a><span data-ttu-id="01a93-103">Szabadság- és távollétparaméterek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="01a93-103">Configure leave and absence parameters</span></span>

<span data-ttu-id="01a93-104">Mielőtt beállítaná a szabadság- és a távollétterveket a Dynamics 365 Human Resources alkalmazásban, célszerű ellenőrizni az összes kapcsolódó emberierőforrás-paraméter beállítását, többek között a következőket:</span><span class="sxs-lookup"><span data-stu-id="01a93-104">Before you set up leave and absence plans in Dynamics 365 Human Resources, it's a good idea to verify the settings for all related human resources parameters, including:</span></span>

- <span data-ttu-id="01a93-105">A szabadságkérelmek számsorozata</span><span class="sxs-lookup"><span data-stu-id="01a93-105">Number sequence for leave requests</span></span>
- <span data-ttu-id="01a93-106">Családi okból történő és a betegszabadságról szóló amerikai törvény (FMLA) beállításai</span><span class="sxs-lookup"><span data-stu-id="01a93-106">Family Medical and Leave Act (FMLA) settings</span></span>
- <span data-ttu-id="01a93-107">Alkalmazotti önkiszolgáló rendszer beállításai a szabadság- és a távollétkérelmek esetében</span><span class="sxs-lookup"><span data-stu-id="01a93-107">Employee self service settings for leave and absence requests</span></span>
- <span data-ttu-id="01a93-108">Szabadság- és távollétparaméterek</span><span class="sxs-lookup"><span data-stu-id="01a93-108">Leave and absence parameters</span></span>

## <a name="view-and-change-human-resources-parameters"></a><span data-ttu-id="01a93-109">Emberierőforrás-paraméterek megtekintése és módosítása</span><span class="sxs-lookup"><span data-stu-id="01a93-109">View and change human resources parameters</span></span>

1. <span data-ttu-id="01a93-110">A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.</span><span class="sxs-lookup"><span data-stu-id="01a93-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="01a93-111">A **Beállítás** alatt válassza az **Emberierőforrás-paraméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01a93-111">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="01a93-112">A **Számsorozatok** lapon ellenőrizze, a **Számsorozat kódja** beálítást a **Szabadságkérelem azonosítója** esetében, és szükség szerint módosítsa.</span><span class="sxs-lookup"><span data-stu-id="01a93-112">On the **Number sequences** tab, verify the **Number sequence code** for **Leave request ID** and change as necessary.</span></span> <span data-ttu-id="01a93-113">Ez a beállítás határozza meg a szabadságkérelmekhez automatikusan hozzárendelt azonosítókhoz használt sorrendet.</span><span class="sxs-lookup"><span data-stu-id="01a93-113">This setting determines the sequence used for automatically assigning IDs to leave requests.</span></span>

4. <span data-ttu-id="01a93-114">Az **FMLA** lapon ellenőrizze az FMLA beállításait, és szükség esetén módosítsa azokat.</span><span class="sxs-lookup"><span data-stu-id="01a93-114">On the **FMLA** tab, verify the FMLA settings and change as necessary.</span></span>

5. <span data-ttu-id="01a93-115">Az **Alkalmazotti önkiszolgáló rendszer** lapon jelezze, hogy a vezetők az alkalmazottak nevében beírhatják-e a szabadság- és a távolléti kérelmeket .</span><span class="sxs-lookup"><span data-stu-id="01a93-115">On the **Employee self service** tab, indicate whether managers can enter leave and absence requests on behalf of their employees.</span></span>

6. <span data-ttu-id="01a93-116">A **Szabadság és távollét** lapon ellenőrizze a beállításokat, és szükség esetén módosítsa azokat.</span><span class="sxs-lookup"><span data-stu-id="01a93-116">On the **Leave and absence** tab, verify the settings and change as necessary.</span></span>

7. <span data-ttu-id="01a93-117">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01a93-117">Select **Save**.</span></span>

## <a name="view-and-change-leave-and-absence-parameters"></a><span data-ttu-id="01a93-118">Szabadság és távollét paramétereinek megtekintése és módosítása</span><span class="sxs-lookup"><span data-stu-id="01a93-118">View and change leave and absence parameters</span></span>

1. <span data-ttu-id="01a93-119">A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.</span><span class="sxs-lookup"><span data-stu-id="01a93-119">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="01a93-120">A **Beállítás**területen válassza a **Szabadság- és távollétparaméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01a93-120">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="01a93-121">Az **Általános** lapon állítsa be a következő paramétereket:</span><span class="sxs-lookup"><span data-stu-id="01a93-121">On the **General** tab, set the following parameters:</span></span>
 
    - <span data-ttu-id="01a93-122">A **Szabadság és távollét mértékegysége** elemet állítsa órára vagy napra.</span><span class="sxs-lookup"><span data-stu-id="01a93-122">Set **Unit for leave and absence** to either hours or days.</span></span> <span data-ttu-id="01a93-123">Ha a nap lehetőséget választja , akkor a **Félnapos meghatározás** engedélyezése beállítással lehetővé teheti az alkalmazottak számára, hogy a nap első vagy második felét válasszák ki távollét-kérelmeikben.</span><span class="sxs-lookup"><span data-stu-id="01a93-123">If days, you can select **Enable half day definition** to allow employees to choose either first or second half of day in their time-off requests.</span></span> 

    - <span data-ttu-id="01a93-124">Válassza a **Szolgálti hónapok az érvényeség dátumáig** kiválasztásával beállíthatja, hogy az elhatárolási mérték a szolgálati hónapok alapján befolyásolja a szabadságterveket.</span><span class="sxs-lookup"><span data-stu-id="01a93-124">Select **Months of service effective date** to set when the accrual rates take effect for leave plans using months of service.</span></span>

    - <span data-ttu-id="01a93-125">Válassza az **Egyenleg számítása** lehetőséget, ha az egyenlegeket a mai napig vagy az elhatárolási időszakig szeretné megjeleníteni.</span><span class="sxs-lookup"><span data-stu-id="01a93-125">Select **Balance calculation** to display balances display as of today or as of the accrual period.</span></span> <span data-ttu-id="01a93-126">Ha az **Egyenleg a mai napig** lehetőséget választja, akkor az egyenleg az összes elhatárolást, kiigazítást és kérelmet megjeleníti a mai napig.</span><span class="sxs-lookup"><span data-stu-id="01a93-126">If you select **Balance as of today**, the balance displays the total of all accruals, adjustments, and requests as of today.</span></span> <span data-ttu-id="01a93-127">Ha az **Egyenleg az elhatárolási időszakig** lehetőséget választja, akkor az egyenleg az elszámolási időszak gyakorisága által meghatározott elhatárolási időszak összes elhatárolását, helyesbítését és kérését jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="01a93-127">If you select **Balance as of accrual period**, the balance displays the total of all accruals, adjustments, and requests as of the accrual period defined by the frequency in the leave plan.</span></span> 

## <a name="configure-calendar-parameters"></a><span data-ttu-id="01a93-128">Naptárparaméterek karbantartása</span><span class="sxs-lookup"><span data-stu-id="01a93-128">Configure calendar parameters</span></span>

1. <span data-ttu-id="01a93-129">A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.</span><span class="sxs-lookup"><span data-stu-id="01a93-129">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="01a93-130">A **Beállítás**területen válassza a **Szabadság- és távollétparaméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01a93-130">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="01a93-131">A **Naptár** lapon szükség szerint módosítsa a naptár beállításait.</span><span class="sxs-lookup"><span data-stu-id="01a93-131">On the **Calendar** tab, change calendar settings as necessary.</span></span>

4. <span data-ttu-id="01a93-132">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01a93-132">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="01a93-133">Lásd még</span><span class="sxs-lookup"><span data-stu-id="01a93-133">See also</span></span>

- [<span data-ttu-id="01a93-134">Szabadság és távollét áttekintése</span><span class="sxs-lookup"><span data-stu-id="01a93-134">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
