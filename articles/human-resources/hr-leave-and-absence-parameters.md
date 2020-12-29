---
title: Szabadság- és távollétparaméterek konfigurálása
description: Emberi erőforrások paramétereinek meghatározása a szabadsághoz és a távolléthez a Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
manager: tfehr
ms.date: 11/02/2020
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
ms.openlocfilehash: e1b2de94f9d9ac1ada16b6ef0e7628edbc9d683f
ms.sourcegitcommit: ffb5998e611b83c2e4f98323f39e3e8f6419c652
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/02/2020
ms.locfileid: "4418939"
---
# <a name="configure-leave-and-absence-parameters"></a><span data-ttu-id="276e4-103">Szabadság- és távollétparaméterek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="276e4-103">Configure leave and absence parameters</span></span>

<span data-ttu-id="276e4-104">Mielőtt beállítaná a szabadság- és a távollétterveket a Dynamics 365 Human Resources alkalmazásban, célszerű ellenőrizni az összes kapcsolódó emberierőforrás-paraméter beállítását, többek között a következőket:</span><span class="sxs-lookup"><span data-stu-id="276e4-104">Before you set up leave and absence plans in Dynamics 365 Human Resources, it's a good idea to verify the settings for all related human resources parameters, including:</span></span>

- <span data-ttu-id="276e4-105">A szabadságkérelmek számsorozata</span><span class="sxs-lookup"><span data-stu-id="276e4-105">Number sequence for leave requests</span></span>
- <span data-ttu-id="276e4-106">Családi okból történő és a betegszabadságról szóló amerikai törvény (FMLA) beállításai</span><span class="sxs-lookup"><span data-stu-id="276e4-106">Family Medical and Leave Act (FMLA) settings</span></span>
- <span data-ttu-id="276e4-107">Alkalmazotti önkiszolgáló rendszer beállításai a szabadság- és a távollétkérelmek esetében</span><span class="sxs-lookup"><span data-stu-id="276e4-107">Employee self service settings for leave and absence requests</span></span>
- <span data-ttu-id="276e4-108">Szabadság- és távollétparaméterek</span><span class="sxs-lookup"><span data-stu-id="276e4-108">Leave and absence parameters</span></span>

## <a name="view-and-change-human-resources-parameters"></a><span data-ttu-id="276e4-109">Emberierőforrás-paraméterek megtekintése és módosítása</span><span class="sxs-lookup"><span data-stu-id="276e4-109">View and change human resources parameters</span></span>

1. <span data-ttu-id="276e4-110">A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.</span><span class="sxs-lookup"><span data-stu-id="276e4-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="276e4-111">A **Beállítás** alatt válassza az **Emberierőforrás-paraméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="276e4-111">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="276e4-112">A **Számsorozatok** lapon ellenőrizze, a **Számsorozat kódja** beálítást a **Szabadságkérelem azonosítója** esetében, és szükség szerint módosítsa.</span><span class="sxs-lookup"><span data-stu-id="276e4-112">On the **Number sequences** tab, verify the **Number sequence code** for **Leave request ID** and change as necessary.</span></span> <span data-ttu-id="276e4-113">Ez a beállítás határozza meg a szabadságkérelmekhez automatikusan hozzárendelt azonosítókhoz használt sorrendet.</span><span class="sxs-lookup"><span data-stu-id="276e4-113">This setting determines the sequence used for automatically assigning IDs to leave requests.</span></span>

4. <span data-ttu-id="276e4-114">Az **FMLA** lapon ellenőrizze az FMLA beállításait, és szükség esetén módosítsa azokat.</span><span class="sxs-lookup"><span data-stu-id="276e4-114">On the **FMLA** tab, verify the FMLA settings and change as necessary.</span></span>

5. <span data-ttu-id="276e4-115">Az **Alkalmazotti önkiszolgáló rendszer** lapon jelezze, hogy a vezetők az alkalmazottak nevében beírhatják-e a szabadság- és a távolléti kérelmeket .</span><span class="sxs-lookup"><span data-stu-id="276e4-115">On the **Employee self service** tab, indicate whether managers can enter leave and absence requests on behalf of their employees.</span></span>

7. <span data-ttu-id="276e4-116">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="276e4-116">Select **Save**.</span></span>

>[!IMPORTANT]
><span data-ttu-id="276e4-117">A szabadság és a távollét megtekintése a vállalatok között jelenleg előzetes verzióban érhető el.</span><span class="sxs-lookup"><span data-stu-id="276e4-117">Viewing leave and absence across companies is currently in preview.</span></span> <span data-ttu-id="276e4-118">Engedélyeznie kell azt a **Tesztkörnyezetben** a szabadság és távollét lehetőségének megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="276e4-118">You'll need to enable it in your **Sandbox** environment to display the option for leave and absence.</span></span> <span data-ttu-id="276e4-119">Az előzetes funkciók engedélyezésével kapcsolatos további részletekért tekintse meg a [Kezelési funkciók](hr-admin-manage-features.md) cikket.</span><span class="sxs-lookup"><span data-stu-id="276e4-119">For more information about enabling preview features, see [Manage features](hr-admin-manage-features.md).</span></span>

## <a name="view-and-change-human-resources-shared-parameters"></a><span data-ttu-id="276e4-120">A Human Resources megosztott paraméterek megtekintése és módosítása</span><span class="sxs-lookup"><span data-stu-id="276e4-120">View and change Human resources shared parameters</span></span>

1. <span data-ttu-id="276e4-121">A **Személyzetkezelés** oldalon válassza a **Hivatkozások** lapot.</span><span class="sxs-lookup"><span data-stu-id="276e4-121">On the **Personnel management** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="276e4-122">A **Beállítás** alatt válassza a **Humán erőforrás megosztott paraméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="276e4-122">Under **Setup**, select **Human resources shared parameters**.</span></span>

3. <span data-ttu-id="276e4-123">Az **Előzetes hozzáférés** lapon válassza az **Igen** lehetőséget a **Vállalatközi szabadságnézet engedélyezése** elemnél, hogy a szabadság megtekinthető legyen a vállalatok között.</span><span class="sxs-lookup"><span data-stu-id="276e4-123">On the **Advance access** tab, select **Yes** for **Enable cross company leave view** to allow leave to be viewed across company.</span></span>

4. <span data-ttu-id="276e4-124">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="276e4-124">Select **Save**.</span></span>

## <a name="view-and-change-leave-and-absence-parameters"></a><span data-ttu-id="276e4-125">Szabadság és távollét paramétereinek megtekintése és módosítása</span><span class="sxs-lookup"><span data-stu-id="276e4-125">View and change leave and absence parameters</span></span>

1. <span data-ttu-id="276e4-126">A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.</span><span class="sxs-lookup"><span data-stu-id="276e4-126">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="276e4-127">A **Beállítás** területen válassza a **Szabadság- és távollétparaméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="276e4-127">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="276e4-128">Az **Általános** lapon állítsa be a következő paramétereket:</span><span class="sxs-lookup"><span data-stu-id="276e4-128">On the **General** tab, set the following parameters:</span></span>
 
    - <span data-ttu-id="276e4-129">A **Szabadság és távollét mértékegysége** elemet állítsa órára vagy napra.</span><span class="sxs-lookup"><span data-stu-id="276e4-129">Set **Unit for leave and absence** to either hours or days.</span></span> <span data-ttu-id="276e4-130">Ha a nap lehetőséget választja , akkor a **Félnapos meghatározás** engedélyezése beállítással lehetővé teheti az alkalmazottak számára, hogy a nap első vagy második felét válasszák ki távollét-kérelmeikben.</span><span class="sxs-lookup"><span data-stu-id="276e4-130">If days, you can select **Enable half day definition** to allow employees to choose either first or second half of day in their time-off requests.</span></span> 

    - <span data-ttu-id="276e4-131">Válassza a **Szolgálti hónapok az érvényeség dátumáig** kiválasztásával beállíthatja, hogy az elhatárolási mérték a szolgálati hónapok alapján befolyásolja a szabadságterveket.</span><span class="sxs-lookup"><span data-stu-id="276e4-131">Select **Months of service effective date** to set when the accrual rates take effect for leave plans using months of service.</span></span>

    - <span data-ttu-id="276e4-132">Válassza az **Egyenleg számítása** lehetőséget, ha az egyenlegeket a mai napig vagy az elhatárolási időszakig szeretné megjeleníteni.</span><span class="sxs-lookup"><span data-stu-id="276e4-132">Select **Balance calculation** to display balances as of today or as of the accrual period.</span></span> <span data-ttu-id="276e4-133">Ha az **Egyenleg a mai napig** lehetőséget választja, akkor az egyenleg az összes elhatárolást, kiigazítást és kérelmet megjeleníti a mai napig.</span><span class="sxs-lookup"><span data-stu-id="276e4-133">If you select **Balance as of today**, the balance displays the total of all accruals, adjustments, and requests as of today.</span></span> <span data-ttu-id="276e4-134">Ha az **Egyenleg az elhatárolási időszakig** lehetőséget választja, akkor az egyenleg az elszámolási időszak gyakorisága által meghatározott elhatárolási időszak összes elhatárolását, helyesbítését és kérését jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="276e4-134">If you select **Balance as of accrual period**, the balance displays the total of all accruals, adjustments, and requests as of the accrual period defined by the frequency in the leave plan.</span></span> 

    - <span data-ttu-id="276e4-135">Az átvitt lejárati kötegelt feladat kezdési időpontjának beállítása.</span><span class="sxs-lookup"><span data-stu-id="276e4-135">Set the start time for the carry forward expiration batch job.</span></span>  
    
    - <span data-ttu-id="276e4-136">Válassza az **Igen** lehetőséget a **Szabadság vásárlásnak engedélyezése az alkalmazottaknak** és **Szabadság eladásánek engedélyezése az alkalmazottaknak** lehetőségekhez.</span><span class="sxs-lookup"><span data-stu-id="276e4-136">Select **Yes** for **Allow employees to buy leave** and **Allow employees to sell leave**.</span></span> <span data-ttu-id="276e4-137">Ha ezekhez a lehetőségekhez az **Igen** értéket választja, akkor létrehozhat szabadságvásárlási és -eladási irányelveket, és lehetővé teszi az alkalmazottak számára, hogy vásároljanak és eladjanak a szabadságot.</span><span class="sxs-lookup"><span data-stu-id="276e4-137">If you select **Yes** for these options, you can create buy and sell leave policies and enable employees to submit buy and sell leave requests.</span></span>

## <a name="configure-calendar-parameters"></a><span data-ttu-id="276e4-138">Naptárparaméterek karbantartása</span><span class="sxs-lookup"><span data-stu-id="276e4-138">Configure calendar parameters</span></span>

1. <span data-ttu-id="276e4-139">A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.</span><span class="sxs-lookup"><span data-stu-id="276e4-139">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="276e4-140">A **Beállítás** területen válassza a **Szabadság- és távollétparaméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="276e4-140">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="276e4-141">A **Naptár** lapon szükség szerint módosítsa a naptár beállításait.</span><span class="sxs-lookup"><span data-stu-id="276e4-141">On the **Calendar** tab, change calendar settings as necessary.</span></span>

4. <span data-ttu-id="276e4-142">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="276e4-142">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="276e4-143">Lásd még</span><span class="sxs-lookup"><span data-stu-id="276e4-143">See also</span></span>

- [<span data-ttu-id="276e4-144">Szabadság és távollét áttekintése</span><span class="sxs-lookup"><span data-stu-id="276e4-144">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
