---
title: Karbantartási kérések
description: Ez a témakör áttekintést ad az Eszközkezelés modul karbantartási kéréseinek kezeléséről.
author: josaw1
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b19a92924d73847d9d2c09cd0ed111a9cbfdccbf
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571645"
---
# <a name="maintenance-requests"></a><span data-ttu-id="d4e55-103">Karbantartási kérések</span><span class="sxs-lookup"><span data-stu-id="d4e55-103">Maintenance requests</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="d4e55-104">A karbantartási kérések olyan jegyzetek vagy nyilatkozatok, amelyek létrehozásának célja egy vezető vagy tervező értesítése, hogy egy eszköznek karbantartási vagy javítási feladatra van szüksége, munkarendelés létrehozása nélkül.</span><span class="sxs-lookup"><span data-stu-id="d4e55-104">Maintenance requests are notes or declarations that are created to notify a manager or planner that an asset might require a maintenance or repair job, but without creating a work order.</span></span> <span data-ttu-id="d4e55-105">Ha a karbantartási kérelem tartalmát érvényesnek ítélik, akkor a karbantartási kérés alapján létre lehet hozni egy munkarendelést.</span><span class="sxs-lookup"><span data-stu-id="d4e55-105">If the contents of a maintenance request are considered valid, a work order can then be created based on the maintenance request.</span></span>

<span data-ttu-id="d4e55-106">Karbantartási kéréseket az Eszközkezelésben bármilyen eszközhöz létre lehet hozni.</span><span class="sxs-lookup"><span data-stu-id="d4e55-106">Maintenance requests can be created for any asset in Asset Management.</span></span> <span data-ttu-id="d4e55-107">Különböző típusú karbantartási kéréseket lehet létrehozni, attól függően, hogy hogyan használja a vállalat a karbantartási kéréseket.</span><span class="sxs-lookup"><span data-stu-id="d4e55-107">Various types of maintenance requests can be created, depending on how your company uses maintenance requests.</span></span> <span data-ttu-id="d4e55-108">Íme néhány példa:</span><span class="sxs-lookup"><span data-stu-id="d4e55-108">Here are some examples:</span></span>

- <span data-ttu-id="d4e55-109">Karbantartási kérések</span><span class="sxs-lookup"><span data-stu-id="d4e55-109">Maintenance requests</span></span>
- <span data-ttu-id="d4e55-110">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="d4e55-110">Notes</span></span>
- <span data-ttu-id="d4e55-111">Javítások vagy fejlesztések</span><span class="sxs-lookup"><span data-stu-id="d4e55-111">Corrections or enhancements</span></span>
- <span data-ttu-id="d4e55-112">Befektetések</span><span class="sxs-lookup"><span data-stu-id="d4e55-112">Investments</span></span>
- <span data-ttu-id="d4e55-113">Raktárjavítás (Ez a típus akkor használatos, amikor másik helyről kapnak eszközöket, amelyeken karbantartási vagy javítási feladatot kell végrehajtani, majd a feladat befejezése után visszaküldeni az eszközt.)</span><span class="sxs-lookup"><span data-stu-id="d4e55-113">Depot repair (This type is used when you receive assets from another location so that you can do a maintenance or repair job, and you then return the asset after the job is completed.)</span></span>

## <a name="view-maintenance-requests"></a><span data-ttu-id="d4e55-114">Karbantartási kérések megtekintése</span><span class="sxs-lookup"><span data-stu-id="d4e55-114">View maintenance requests</span></span>

<span data-ttu-id="d4e55-115">A karbantartási kérelmek megtekintéséhez válassza az **Eszközkezelés** \> **Általános** \> **Karbantartási kérések** \> **Összes karbantartási kérés**, **Aktív karbantartási kérések** vagy **Saját munkavégzési helyszínhez tartozó karbantartási kérések** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d4e55-115">To view maintenance requests, select **Asset management** \> **Common** \> **Maintenance requests** \> **All maintenance requests**, **Active maintenance requests**, or **My functional location maintenance requests**.</span></span> <span data-ttu-id="d4e55-116">Minden listaoldal megjelenít egy karbantartási kéréshez kapcsolódó adatok egy részét.</span><span class="sxs-lookup"><span data-stu-id="d4e55-116">Each list page shows some of the information that is related to a maintenance request.</span></span>

![Karbantartási kérések megtekintése](media/01-manage-maintenance-requests.png)

> [!NOTE]
> <span data-ttu-id="d4e55-118">A **Saját munkavégzési helyszínhez tartozó karbantartási kérések** listaoldal segítségével megtekintheti a karbantartási kérések listáját, amelyen vagy a dolgozóként Önhöz kapcsolódó munkavégzési helyszínek szerepelnek, vagy a munkavégzési helyszínekre telepített eszközök szerepelnek, amelyekhez dolgozóként kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="d4e55-118">Use the **My functional location maintenance requests** list page to view a list of maintenance requests that contain either functional locations that you're related to as a worker or assets that are installed on functional locations that you're related to as a worker.</span></span> <span data-ttu-id="d4e55-119">(A karbantartási dolgozók munkavégzési helyszíneinek beállítására vonatkozó további tudnivalókért tanulmányozza a [Karbantartási dolgozók és dolgozói csoportok](../setup-for-objects/workers-and-worker-groups.md) című témakört.)</span><span class="sxs-lookup"><span data-stu-id="d4e55-119">(For information about how to set up functional locations on maintenance workers, see [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).)</span></span>
> 
> <span data-ttu-id="d4e55-120">Bár a vevői számlaadatok elérhetők az Eszközszolgáltatás-menedzsment modulban (külső karbantartás), ez nem áll rendelkezésre az Eszközkezelésben (belső karbantartás).</span><span class="sxs-lookup"><span data-stu-id="d4e55-120">Although customer account information is available in Asset Service Management (external maintenance), it isn't available in Asset Management (internal maintenance).</span></span>

<span data-ttu-id="d4e55-121">Ha meg szeretné nyitni a rekord részletetes nézetét, az **Összes karbantartási kérés** listaoldalon a rácsnézetben válasszon egy hivatkozást a **Karbantartási kérés** oszlopban.</span><span class="sxs-lookup"><span data-stu-id="d4e55-121">To open the details view of a record, on the **All maintenance requests** list page, in the grid view, select a link in the **Maintenance request** column.</span></span>

![A karbantartási kérelem nézetrészletei.](media/02-manage-maintenance-requests.png)

<span data-ttu-id="d4e55-123">A műveleti ablak gombjai lapokon vannak rendezve.</span><span class="sxs-lookup"><span data-stu-id="d4e55-123">The buttons on the Action Pane are organized on tabs.</span></span> <span data-ttu-id="d4e55-124">A következő táblázat röviden leírja azokat a gombokat, amelyek az Eszközkezeléshez kötődnek.</span><span class="sxs-lookup"><span data-stu-id="d4e55-124">The following table briefly describes the buttons that are related to Asset Management.</span></span>

| <span data-ttu-id="d4e55-125">Gomb neve</span><span class="sxs-lookup"><span data-stu-id="d4e55-125">Button name</span></span>                      | <span data-ttu-id="d4e55-126">Leírás</span><span class="sxs-lookup"><span data-stu-id="d4e55-126">Description</span></span> |
|----------------------------------|-------------|
| <span data-ttu-id="d4e55-127">Szerkesztés</span><span class="sxs-lookup"><span data-stu-id="d4e55-127">Edit</span></span>                             | <span data-ttu-id="d4e55-128">A kijelölt karbantartási kérés szerkesztése.</span><span class="sxs-lookup"><span data-stu-id="d4e55-128">Edit the selected maintenance request.</span></span> |
| <span data-ttu-id="d4e55-129">Új</span><span class="sxs-lookup"><span data-stu-id="d4e55-129">New</span></span>                              | <span data-ttu-id="d4e55-130">Hozzon létre új karbantartási kérést.</span><span class="sxs-lookup"><span data-stu-id="d4e55-130">Create a new maintenance request.</span></span> |
| <span data-ttu-id="d4e55-131">Eltávolítás</span><span class="sxs-lookup"><span data-stu-id="d4e55-131">Delete</span></span>                           | <span data-ttu-id="d4e55-132">Törölje a kiválasztott karbantartási kérést.</span><span class="sxs-lookup"><span data-stu-id="d4e55-132">Delete the selected maintenance request.</span></span> |
| <span data-ttu-id="d4e55-133">Munkarendelés-gyűjtő</span><span class="sxs-lookup"><span data-stu-id="d4e55-133">Work order pool</span></span>                  | <span data-ttu-id="d4e55-134">A kijelölt karbantartási kérést csatlakoztathatja egy munkarendelési gyűjtőhöz.</span><span class="sxs-lookup"><span data-stu-id="d4e55-134">Connect the selected maintenance request to a work order pool.</span></span> |
| <span data-ttu-id="d4e55-135">Munkarendelés</span><span class="sxs-lookup"><span data-stu-id="d4e55-135">Work order</span></span>                       | <span data-ttu-id="d4e55-136">A kijelölt karbantartási kérés alapján hozzon létre egy munkarendelést.</span><span class="sxs-lookup"><span data-stu-id="d4e55-136">Create a work order, based on the selected maintenance request.</span></span> |
| <span data-ttu-id="d4e55-137">Eszközhiba</span><span class="sxs-lookup"><span data-stu-id="d4e55-137">Asset fault</span></span>                      | <span data-ttu-id="d4e55-138">Kattintson az **Eszközhibák** elemre, ahol rögzítheti a hibákat a kiválasztott karbantartási kérésen.</span><span class="sxs-lookup"><span data-stu-id="d4e55-138">Click **Asset faults**, where you can create a fault registration on the selected maintenance request.</span></span> |
| <span data-ttu-id="d4e55-139">Munkarendelések</span><span class="sxs-lookup"><span data-stu-id="d4e55-139">Work orders</span></span>                      | <span data-ttu-id="d4e55-140">Az összes munkarendelés listáját megjelenítheti, amelyek a kijelölt karbantartási kéréshez kapcsolódnak.</span><span class="sxs-lookup"><span data-stu-id="d4e55-140">Show a list of all work orders that are connected to the selected maintenance request.</span></span> |
| <span data-ttu-id="d4e55-141">Karbantartási kérés állapotának frissítése</span><span class="sxs-lookup"><span data-stu-id="d4e55-141">Update maintenance request state</span></span> | <span data-ttu-id="d4e55-142">Frissítheti a karbantartási kérés állapotát.</span><span class="sxs-lookup"><span data-stu-id="d4e55-142">Update the maintenance request state.</span></span> |
| <span data-ttu-id="d4e55-143">Életciklus-állapot naplója</span><span class="sxs-lookup"><span data-stu-id="d4e55-143">Lifecycle state log</span></span>              | <span data-ttu-id="d4e55-144">Megtekinthet egy naplót, amely a kiválasztott karbantartási kérés életciklus-állapotait mutatja.</span><span class="sxs-lookup"><span data-stu-id="d4e55-144">View a log that shows the lifecycle states of the selected maintenance request.</span></span> |
| <span data-ttu-id="d4e55-145">Karbantartási kérés részletei</span><span class="sxs-lookup"><span data-stu-id="d4e55-145">Maintenance request details</span></span>      | <span data-ttu-id="d4e55-146">Kinyomtathat egy jelentést, amely a kijelölt karbantartási kérés részleteit mutatja.</span><span class="sxs-lookup"><span data-stu-id="d4e55-146">Print a report that shows details of the selected maintenance request.</span></span> |
| <span data-ttu-id="d4e55-147">Kölcsönzött eszköz küldése</span><span class="sxs-lookup"><span data-stu-id="d4e55-147">Send loan asset</span></span>                  | <span data-ttu-id="d4e55-148">Válasszon ki egy kölcsönzött eszközt, amelyet ideiglenes helyettesítőként használhatnak egy eszköz helyett, amelyet a kijelölt karbantartási kérésen kiválasztottak.</span><span class="sxs-lookup"><span data-stu-id="d4e55-148">Select a loan asset that should be a temporary replacement for the asset that is selected on the selected maintenance request.</span></span> |
| <span data-ttu-id="d4e55-149">Kölcsönzött eszköz visszaküldése</span><span class="sxs-lookup"><span data-stu-id="d4e55-149">Return loan asset</span></span>                | <span data-ttu-id="d4e55-150">A kölcsönzött eszközt visszaküldöttként rögzítheti.</span><span class="sxs-lookup"><span data-stu-id="d4e55-150">Register the loan asset as returned.</span></span> |

