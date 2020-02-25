---
title: Szabadság- és távollétparaméterek konfigurálása
description: Emberi erőforrások paramétereinek meghatározása a szabadsághoz és a távolléthez a Dynamics 365 Human Resources alkalmazásban.
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
ms.openlocfilehash: 2acb8502ebcab122a0a1ff21e9f5e23931026327
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009261"
---
# <a name="configure-leave-and-absence-parameters"></a><span data-ttu-id="3660d-103">Szabadság- és távollétparaméterek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="3660d-103">Configure leave and absence parameters</span></span>

<span data-ttu-id="3660d-104">Mielőtt beállítaná a szabadság- és a távollétterveket a Dynamics 365 Human Resources alkalmazásban, célszerű ellenőrizni az összes kapcsolódó emberierőforrás-paraméter beállítását, többek között a következőket:</span><span class="sxs-lookup"><span data-stu-id="3660d-104">Before you set up leave and absence plans in Dynamics 365 Human Resources, it's a good idea to verify the settings for all related human resources parameters, including:</span></span>

- <span data-ttu-id="3660d-105">A szabadságkérelmek számsorozata</span><span class="sxs-lookup"><span data-stu-id="3660d-105">Number sequence for leave requests</span></span>
- <span data-ttu-id="3660d-106">Családi okból történő és a betegszabadságról szóló amerikai törvény (FMLA) beállításai</span><span class="sxs-lookup"><span data-stu-id="3660d-106">Family Medical and Leave Act (FMLA) settings</span></span>
- <span data-ttu-id="3660d-107">Alkalmazotti önkiszolgáló rendszer beállításai a szabadság- és a távollétkérelmek esetében</span><span class="sxs-lookup"><span data-stu-id="3660d-107">Employee self service settings for leave and absence requests</span></span>
- <span data-ttu-id="3660d-108">Szabadság- és távollétparaméterek</span><span class="sxs-lookup"><span data-stu-id="3660d-108">Leave and absence parameters</span></span>

## <a name="view-and-change-human-resources-parameters"></a><span data-ttu-id="3660d-109">Emberierőforrás-paraméterek megtekintése és módosítása</span><span class="sxs-lookup"><span data-stu-id="3660d-109">View and change human resources parameters</span></span>

1. <span data-ttu-id="3660d-110">A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.</span><span class="sxs-lookup"><span data-stu-id="3660d-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="3660d-111">A **Beállítás** alatt válassza az **Emberierőforrás-paraméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3660d-111">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="3660d-112">A **Számsorozatok** lapon ellenőrizze, a **Számsorozat kódja** beálítást a **Szabadságkérelem azonosítója** esetében, és szükség szerint módosítsa.</span><span class="sxs-lookup"><span data-stu-id="3660d-112">On the **Number sequences** tab, verify the **Number sequence code** for **Leave request ID** and change as necessary.</span></span> <span data-ttu-id="3660d-113">Ez a beállítás határozza meg a szabadságkérelmekhez automatikusan hozzárendelt azonosítókhoz használt sorrendet.</span><span class="sxs-lookup"><span data-stu-id="3660d-113">This setting determines the sequence used for automatically assigning IDs to leave requests.</span></span>

4. <span data-ttu-id="3660d-114">Az **FMLA** lapon ellenőrizze az FMLA beállításait, és szükség esetén módosítsa azokat.</span><span class="sxs-lookup"><span data-stu-id="3660d-114">On the **FMLA** tab, verify the FMLA settings and change as necessary.</span></span>

5. <span data-ttu-id="3660d-115">Az **Alkalmazotti önkiszolgáló rendszer** lapon jelezze, hogy a vezetők az alkalmazottak nevében beírhatják-e a szabadság- és a távolléti kérelmeket .</span><span class="sxs-lookup"><span data-stu-id="3660d-115">On the **Employee self service** tab, indicate whether managers can enter leave and absence requests on behalf of their employees.</span></span>

6. <span data-ttu-id="3660d-116">A **Szabadság és távollét** lapon ellenőrizze a beállításokat, és szükség esetén módosítsa azokat.</span><span class="sxs-lookup"><span data-stu-id="3660d-116">On the **Leave and absence** tab, verify the settings and change as necessary.</span></span>

7. <span data-ttu-id="3660d-117">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3660d-117">Select **Save**.</span></span>

## <a name="configure-calendar-parameters"></a><span data-ttu-id="3660d-118">Naptárparaméterek karbantartása</span><span class="sxs-lookup"><span data-stu-id="3660d-118">Configure calendar parameters</span></span>

<span data-ttu-id="3660d-119">Ha engedélyezte a Szabadság és távollét naptár előnézeti funkcióját, további paramétereket kell konfigurálnia.</span><span class="sxs-lookup"><span data-stu-id="3660d-119">If you have enabled the Leave and absence calendar preview feature, you need to configure additional parameters.</span></span> 

[!include [banner](includes/preview-feature-leave-absence.md)]

> [!NOTE]
> <span data-ttu-id="3660d-120">A 2020. február 3-án esedékes előzetes kiadás esetében csak a **Függőben lévő szabadságkérelmek** engedélyezettek.</span><span class="sxs-lookup"><span data-stu-id="3660d-120">For the preview release on February 3, 2020, only **Pending leave requests** are enabled.</span></span>

1. <span data-ttu-id="3660d-121">A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.</span><span class="sxs-lookup"><span data-stu-id="3660d-121">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="3660d-122">A **Beállítás** alatt válassza az **Emberierőforrás-paraméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3660d-122">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="3660d-123">A **Naptár** lapon szükség szerint módosítsa a naptár beállításait.</span><span class="sxs-lookup"><span data-stu-id="3660d-123">On the **Calendar** tab, change calendar settings as necessary.</span></span>

4. <span data-ttu-id="3660d-124">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3660d-124">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="3660d-125">Lásd még</span><span class="sxs-lookup"><span data-stu-id="3660d-125">See also</span></span>

- [<span data-ttu-id="3660d-126">Szabadság és távollét áttekintése</span><span class="sxs-lookup"><span data-stu-id="3660d-126">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
