---
title: Karbantartási kérések
description: Ez a témakör áttekintést ad az Eszközkezelés modul karbantartási kéréseinek kezeléséről.
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetRequestTable, EntAssetRequestWorkspace, EntAssetRequestActivePart, EntAssetRequestWorkOrderActive, EntAssetRequestType, EntAssetRequestTableCreateWO, EntAssetRequestTableLookup, EntAssetRequestTableActivePart, EntAssetMobileRequestDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3c72a16b8f3865129ad737c511e50eb34c9f2e91
ms.sourcegitcommit: 51cad1ce3ed44ebf7eb9bdf553ee2df4c1f03135
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/10/2021
ms.locfileid: "6015878"
---
# <a name="maintenance-requests"></a><span data-ttu-id="7108b-103">Karbantartási kérések</span><span class="sxs-lookup"><span data-stu-id="7108b-103">Maintenance requests</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7108b-104">A karbantartási kérések olyan jegyzetek vagy nyilatkozatok, amelyek létrehozásának célja egy vezető vagy tervező értesítése, hogy egy eszköznek karbantartási vagy javítási feladatra van szüksége, munkarendelés létrehozása nélkül.</span><span class="sxs-lookup"><span data-stu-id="7108b-104">Maintenance requests are notes or declarations that are created to notify a manager or planner that an asset might require a maintenance or repair job, but without creating a work order.</span></span> <span data-ttu-id="7108b-105">Ha a karbantartási kérelem tartalmát érvényesnek ítélik, akkor a karbantartási kérés alapján létre lehet hozni egy munkarendelést.</span><span class="sxs-lookup"><span data-stu-id="7108b-105">If the contents of a maintenance request are considered valid, a work order can then be created based on the maintenance request.</span></span>

<span data-ttu-id="7108b-106">Karbantartási kéréseket az Eszközkezelésben bármilyen eszközhöz létre lehet hozni.</span><span class="sxs-lookup"><span data-stu-id="7108b-106">Maintenance requests can be created for any asset in Asset Management.</span></span> <span data-ttu-id="7108b-107">Különböző típusú karbantartási kéréseket lehet létrehozni, attól függően, hogy hogyan használja a vállalat a karbantartási kéréseket.</span><span class="sxs-lookup"><span data-stu-id="7108b-107">Various types of maintenance requests can be created, depending on how your company uses maintenance requests.</span></span> <span data-ttu-id="7108b-108">Íme néhány példa:</span><span class="sxs-lookup"><span data-stu-id="7108b-108">Here are some examples:</span></span>

- <span data-ttu-id="7108b-109">Karbantartási kérések</span><span class="sxs-lookup"><span data-stu-id="7108b-109">Maintenance requests</span></span>
- <span data-ttu-id="7108b-110">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="7108b-110">Notes</span></span>
- <span data-ttu-id="7108b-111">Javítások vagy fejlesztések</span><span class="sxs-lookup"><span data-stu-id="7108b-111">Corrections or enhancements</span></span>
- <span data-ttu-id="7108b-112">Befektetések</span><span class="sxs-lookup"><span data-stu-id="7108b-112">Investments</span></span>
- <span data-ttu-id="7108b-113">Raktárjavítás (Ez a típus akkor használatos, amikor másik helyről kapnak eszközöket, amelyeken karbantartási vagy javítási feladatot kell végrehajtani, majd a feladat befejezése után visszaküldeni az eszközt.)</span><span class="sxs-lookup"><span data-stu-id="7108b-113">Depot repair (This type is used when you receive assets from another location so that you can do a maintenance or repair job, and you then return the asset after the job is completed.)</span></span>

## <a name="view-maintenance-requests"></a><span data-ttu-id="7108b-114">Karbantartási kérések megtekintése</span><span class="sxs-lookup"><span data-stu-id="7108b-114">View maintenance requests</span></span>

<span data-ttu-id="7108b-115">A karbantartási kérelmek megtekintéséhez válassza az **Eszközkezelés** \> **Általános** \> **Karbantartási kérések** \> **Összes karbantartási kérés**, **Aktív karbantartási kérések** vagy **Saját munkavégzési helyszínhez tartozó karbantartási kérések** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7108b-115">To view maintenance requests, select **Asset management** \> **Common** \> **Maintenance requests** \> **All maintenance requests**, **Active maintenance requests**, or **My functional location maintenance requests**.</span></span> <span data-ttu-id="7108b-116">Minden listaoldal megjelenít egy karbantartási kéréshez kapcsolódó adatok egy részét.</span><span class="sxs-lookup"><span data-stu-id="7108b-116">Each list page shows some of the information that is related to a maintenance request.</span></span>

![Karbantartási kérések megtekintése](media/01-manage-maintenance-requests.png)

> [!NOTE]
> <span data-ttu-id="7108b-118">A **Saját munkavégzési helyszínhez tartozó karbantartási kérések** listaoldal segítségével megtekintheti a karbantartási kérések listáját, amelyen vagy a dolgozóként Önhöz kapcsolódó munkavégzési helyszínek szerepelnek, vagy a munkavégzési helyszínekre telepített eszközök szerepelnek, amelyekhez dolgozóként kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="7108b-118">Use the **My functional location maintenance requests** list page to view a list of maintenance requests that contain either functional locations that you're related to as a worker or assets that are installed on functional locations that you're related to as a worker.</span></span> <span data-ttu-id="7108b-119">(A karbantartási dolgozók munkavégzési helyszíneinek beállítására vonatkozó további tudnivalókért tanulmányozza a [Karbantartási dolgozók és dolgozói csoportok](../setup-for-objects/workers-and-worker-groups.md) című témakört.)</span><span class="sxs-lookup"><span data-stu-id="7108b-119">(For information about how to set up functional locations on maintenance workers, see [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).)</span></span>
> 
> <span data-ttu-id="7108b-120">Bár a vevői számlaadatok elérhetők az Eszközszolgáltatás-menedzsment modulban (külső karbantartás), ez nem áll rendelkezésre az Eszközkezelésben (belső karbantartás).</span><span class="sxs-lookup"><span data-stu-id="7108b-120">Although customer account information is available in Asset Service Management (external maintenance), it isn't available in Asset Management (internal maintenance).</span></span>

<span data-ttu-id="7108b-121">Ha meg szeretné nyitni a rekord részletetes nézetét, az **Összes karbantartási kérés** listaoldalon a rácsnézetben válasszon egy hivatkozást a **Karbantartási kérés** oszlopban.</span><span class="sxs-lookup"><span data-stu-id="7108b-121">To open the details view of a record, on the **All maintenance requests** list page, in the grid view, select a link in the **Maintenance request** column.</span></span>

![A karbantartási kérelem nézetrészletei.](media/02-manage-maintenance-requests.png)

<span data-ttu-id="7108b-123">A műveleti ablak gombjai lapokon vannak rendezve.</span><span class="sxs-lookup"><span data-stu-id="7108b-123">The buttons on the Action Pane are organized on tabs.</span></span> <span data-ttu-id="7108b-124">A következő táblázat röviden leírja azokat a gombokat, amelyek az Eszközkezeléshez kötődnek.</span><span class="sxs-lookup"><span data-stu-id="7108b-124">The following table briefly describes the buttons that are related to Asset Management.</span></span>

| <span data-ttu-id="7108b-125">Gomb neve</span><span class="sxs-lookup"><span data-stu-id="7108b-125">Button name</span></span>                      | <span data-ttu-id="7108b-126">Leírás</span><span class="sxs-lookup"><span data-stu-id="7108b-126">Description</span></span> |
|----------------------------------|-------------|
| <span data-ttu-id="7108b-127">Szerkesztés</span><span class="sxs-lookup"><span data-stu-id="7108b-127">Edit</span></span>                             | <span data-ttu-id="7108b-128">A kijelölt karbantartási kérés szerkesztése.</span><span class="sxs-lookup"><span data-stu-id="7108b-128">Edit the selected maintenance request.</span></span> |
| <span data-ttu-id="7108b-129">Új</span><span class="sxs-lookup"><span data-stu-id="7108b-129">New</span></span>                              | <span data-ttu-id="7108b-130">Hozzon létre új karbantartási kérést.</span><span class="sxs-lookup"><span data-stu-id="7108b-130">Create a new maintenance request.</span></span> |
| <span data-ttu-id="7108b-131">Eltávolítás</span><span class="sxs-lookup"><span data-stu-id="7108b-131">Delete</span></span>                           | <span data-ttu-id="7108b-132">Törölje a kiválasztott karbantartási kérést.</span><span class="sxs-lookup"><span data-stu-id="7108b-132">Delete the selected maintenance request.</span></span> |
| <span data-ttu-id="7108b-133">Munkarendelés-gyűjtő</span><span class="sxs-lookup"><span data-stu-id="7108b-133">Work order pool</span></span>                  | <span data-ttu-id="7108b-134">A kijelölt karbantartási kérést csatlakoztathatja egy munkarendelési gyűjtőhöz.</span><span class="sxs-lookup"><span data-stu-id="7108b-134">Connect the selected maintenance request to a work order pool.</span></span> |
| <span data-ttu-id="7108b-135">Munkarendelés</span><span class="sxs-lookup"><span data-stu-id="7108b-135">Work order</span></span>                       | <span data-ttu-id="7108b-136">A kijelölt karbantartási kérés alapján hozzon létre egy munkarendelést.</span><span class="sxs-lookup"><span data-stu-id="7108b-136">Create a work order, based on the selected maintenance request.</span></span> |
| <span data-ttu-id="7108b-137">Eszközhiba</span><span class="sxs-lookup"><span data-stu-id="7108b-137">Asset fault</span></span>                      | <span data-ttu-id="7108b-138">Kattintson az **Eszközhibák** elemre, ahol rögzítheti a hibákat a kiválasztott karbantartási kérésen.</span><span class="sxs-lookup"><span data-stu-id="7108b-138">Click **Asset faults**, where you can create a fault registration on the selected maintenance request.</span></span> |
| <span data-ttu-id="7108b-139">Munkarendelések</span><span class="sxs-lookup"><span data-stu-id="7108b-139">Work orders</span></span>                      | <span data-ttu-id="7108b-140">Az összes munkarendelés listáját megjelenítheti, amelyek a kijelölt karbantartási kéréshez kapcsolódnak.</span><span class="sxs-lookup"><span data-stu-id="7108b-140">Show a list of all work orders that are connected to the selected maintenance request.</span></span> |
| <span data-ttu-id="7108b-141">Karbantartási kérés állapotának frissítése</span><span class="sxs-lookup"><span data-stu-id="7108b-141">Update maintenance request state</span></span> | <span data-ttu-id="7108b-142">Frissítheti a karbantartási kérés állapotát.</span><span class="sxs-lookup"><span data-stu-id="7108b-142">Update the maintenance request state.</span></span> |
| <span data-ttu-id="7108b-143">Életciklus-állapot naplója</span><span class="sxs-lookup"><span data-stu-id="7108b-143">Lifecycle state log</span></span>              | <span data-ttu-id="7108b-144">Megtekinthet egy naplót, amely a kiválasztott karbantartási kérés életciklus-állapotait mutatja.</span><span class="sxs-lookup"><span data-stu-id="7108b-144">View a log that shows the lifecycle states of the selected maintenance request.</span></span> |
| <span data-ttu-id="7108b-145">Karbantartási kérés részletei</span><span class="sxs-lookup"><span data-stu-id="7108b-145">Maintenance request details</span></span>      | <span data-ttu-id="7108b-146">Kinyomtathat egy jelentést, amely a kijelölt karbantartási kérés részleteit mutatja.</span><span class="sxs-lookup"><span data-stu-id="7108b-146">Print a report that shows details of the selected maintenance request.</span></span> |
| <span data-ttu-id="7108b-147">Kölcsönzött eszköz küldése</span><span class="sxs-lookup"><span data-stu-id="7108b-147">Send loan asset</span></span>                  | <span data-ttu-id="7108b-148">Válasszon ki egy kölcsönzött eszközt, amelyet ideiglenes helyettesítőként használhatnak egy eszköz helyett, amelyet a kijelölt karbantartási kérésen kiválasztottak.</span><span class="sxs-lookup"><span data-stu-id="7108b-148">Select a loan asset that should be a temporary replacement for the asset that is selected on the selected maintenance request.</span></span> |
| <span data-ttu-id="7108b-149">Kölcsönzött eszköz visszaküldése</span><span class="sxs-lookup"><span data-stu-id="7108b-149">Return loan asset</span></span>                | <span data-ttu-id="7108b-150">A kölcsönzött eszközt visszaküldöttként rögzítheti.</span><span class="sxs-lookup"><span data-stu-id="7108b-150">Register the loan asset as returned.</span></span> |



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]