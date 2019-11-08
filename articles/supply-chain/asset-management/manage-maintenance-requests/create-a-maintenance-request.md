---
title: Karbantartási kérések létrehozása
description: Ez a témakör azt mutatja be, hogyan lehet a karbantartási kérést létrehozni az Eszközkezelés modulban.
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
ms.openlocfilehash: 7fc9ec2f6a9a8a11d824e4b5c13d5aa173541454
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571921"
---
# <a name="create-maintenance-requests"></a><span data-ttu-id="cbccc-103">Karbantartási kérések létrehozása</span><span class="sxs-lookup"><span data-stu-id="cbccc-103">Create maintenance requests</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="cbccc-104">A karbantartási kérések akkor használhatók, ha a karbantartás dolgozók vagy a termelési dolgozók felfedezik, hogy a felszerelés javítása szükséges, de a javítási feladat nem hajtható végre azonnal.</span><span class="sxs-lookup"><span data-stu-id="cbccc-104">Maintenance requests can be used if maintenance workers or production workers discover that equipment requires repair, but the repair job can't be done right away.</span></span>

<span data-ttu-id="cbccc-105">**Példa:** Amíg a karbantartó dolgozó javítási munkát végez, rájön, hogy egy másik eszközt is szervizelni kell ugyanazon a helyszínen.</span><span class="sxs-lookup"><span data-stu-id="cbccc-105">**Example:** While a maintenance worker is making a repair, she discovers that another asset at the same location must be serviced.</span></span> <span data-ttu-id="cbccc-106">Azonban a karbantartási dolgozónak nincs ideje vagy a pótalkatrészek szükségesek a javítási feladat végrehajtásához.</span><span class="sxs-lookup"><span data-stu-id="cbccc-106">However, the maintenance worker doesn't have the time or the required spare parts to do the repair job.</span></span> <span data-ttu-id="cbccc-107">Ezért létrehoz egy karbantartási kérelmet a tárgyi eszközhöz, és beírja a probléma rövid leírását.</span><span class="sxs-lookup"><span data-stu-id="cbccc-107">Therefore, she creates a maintenance request on the asset and enters a short description of the issue.</span></span>

<span data-ttu-id="cbccc-108">Az **Aktív karbantartási kérések** részben a **Kapcsolódó információk** ablaktáblán az **Összes eszköz** vagy **Összes eszköz** oldal jobb oldalán (**Eszközök kezelése** \> **Közös** \> **Eszközök** \> **Összes eszköz** vagy **Aktív eszközök**) láthatók a kijelölt eszközhöz csatolt karbantartási kérések.</span><span class="sxs-lookup"><span data-stu-id="cbccc-108">The **Active maintenance requests** section of the **Related information** pane on the right side of the **All assets** or **Active assets** page (**Asset management** \> **Common** \> **Assets** \> **All assets** or **Active assets**) shows the active maintenance requests that are attached to the selected asset.</span></span>

1. <span data-ttu-id="cbccc-109">Válassza az **Eszközkezelés** \> **Közös** \> **Karbantartási kérések** \> **Összes karbantartási kérés** vagy **Aktív karbantartási kérések** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cbccc-109">Select **Asset management** \> **Common** \> **Maintenance requests** \> **All maintenance requests** or **Active maintenance requests**.</span></span>
2. <span data-ttu-id="cbccc-110">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cbccc-110">Select **New**.</span></span>
3. <span data-ttu-id="cbccc-111">A **Kérelem létrehozása** párbeszédpanel **Karbantartási kérés típusa** mezőjében válassza ki a karbantartási kérés típusát.</span><span class="sxs-lookup"><span data-stu-id="cbccc-111">In the **Create request** dialog box, in the **Maintenance request type** field, select the type of maintenance request.</span></span> <span data-ttu-id="cbccc-112">Egy alapértelmezett típus javasolva van.</span><span class="sxs-lookup"><span data-stu-id="cbccc-112">A default type is suggested.</span></span>
4. <span data-ttu-id="cbccc-113">A **Leírás** mezőben adjon meg egy nevet vagy egy címet, amely röviden leírja a karbantartási kérést.</span><span class="sxs-lookup"><span data-stu-id="cbccc-113">In the **Description** field, enter a name or title that briefly describes the maintenance request.</span></span>
5. <span data-ttu-id="cbccc-114">A **Munkavégzési helyszín** és az **Eszköz** mezőben válasszon ki egy munkavégzési helyszínt vagy egy eszközt, vagy egy munkavégzési helyszín és egy eszköz kombinációját, ahogy szükséges.</span><span class="sxs-lookup"><span data-stu-id="cbccc-114">In the **Functional location** and **Asset** fields, select a functional location or an asset, or a combination of a functional location and an asset, as you require.</span></span> <span data-ttu-id="cbccc-115">A karbantartási kérést egy eszköz kiválasztása nélkül is létre lehet hozni, és az eszköz később is hozzáadható a karbantartási kéréshez.</span><span class="sxs-lookup"><span data-stu-id="cbccc-115">You can create a maintenance request without selecting an asset, and the asset can be added to the maintenance request later.</span></span> <span data-ttu-id="cbccc-116">Ha a karbantartási dolgozó, aki bejelentkezett egy eszközhöz kapcsolódó erőforráshoz kapcsolódik, akkor az **Eszköz** mező automatikusan be lesz állítva.</span><span class="sxs-lookup"><span data-stu-id="cbccc-116">If the maintenance worker who is signed in is related to a resource that is related to an asset, the **Asset** field is automatically set.</span></span>

    <span data-ttu-id="cbccc-117">Ha már van hozzárendelve egy karbantartási kérés a kiválasztott eszközhöz, akkor egy üzenetsáv jelenik meg a **Kérés létrehozása** párbeszédpanel tetején, amely tájékoztatja a meglévő karbantartási kérés azonosítójáról.</span><span class="sxs-lookup"><span data-stu-id="cbccc-117">If a maintenance request is already attached to the selected asset, a message bar appears at the top of the **Create request** dialog box to notify you about the ID of the existing maintenance request.</span></span> <span data-ttu-id="cbccc-118">Egy üzenetsáv azt is jelzi, ha az eszközhöz garancia tartozik.</span><span class="sxs-lookup"><span data-stu-id="cbccc-118">A message bar also notifies you if the asset is covered by a warranty agreement.</span></span>

6. <span data-ttu-id="cbccc-119">A **Szolgáltatási szint** mezőben válassza ki azt a szolgáltatási szintet, amely a kérés sürgősségét jelzi.</span><span class="sxs-lookup"><span data-stu-id="cbccc-119">In the **Service level** field, select a service level that indicates the urgency of the request.</span></span>
7. <span data-ttu-id="cbccc-120">Ha az 5. lépésben kiválasztott egy eszközt, akkor a **Hiba tünete**, **Hibás terület**és **Hiba típusa** mezőket használhatja a hiba regisztrálásának létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="cbccc-120">If you selected an asset in step 5, you can use the **Fault symptom**, **Fault area**, and **Fault type** fields to create a fault registration.</span></span>
8. <span data-ttu-id="cbccc-121">Ha a karbantartási kérés karbantartás miatti üzemkimaradást okozott, adja meg az üzemkimaradás kezdő dátumát és időpontját.</span><span class="sxs-lookup"><span data-stu-id="cbccc-121">If the maintenance request has caused maintenance downtime, enter the start date and time of the downtime.</span></span>

    <span data-ttu-id="cbccc-122">A program automatikusan az Ön nevére állítja az **Elindította** mezőt.</span><span class="sxs-lookup"><span data-stu-id="cbccc-122">The **Started by** field is automatically set to your name.</span></span>

10. <span data-ttu-id="cbccc-123">A **Tényleges kezdés** mező értéke automatikusan az aktuális dátum és időpont lesz.</span><span class="sxs-lookup"><span data-stu-id="cbccc-123">The **Actual start** field is automatically set to the current date and time.</span></span> <span data-ttu-id="cbccc-124">A mező értéke azonban igény szerint módosítható.</span><span class="sxs-lookup"><span data-stu-id="cbccc-124">However, you can change the value as you require.</span></span>
11. <span data-ttu-id="cbccc-125">A **Megjegyzések** mezőbe írja be a szükséges további megjegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="cbccc-125">In the **Notes** field, enter any additional notes that are required.</span></span>
12. <span data-ttu-id="cbccc-126">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cbccc-126">Select **OK**.</span></span>

![Karbantartási kérés létrehozása](media/03-manage-maintenance-requests.png)

## <a name="subsequent-processing-of-maintenance-requests"></a><span data-ttu-id="cbccc-128">Karbantartási kérések utólagos feldolgozása</span><span class="sxs-lookup"><span data-stu-id="cbccc-128">Subsequent processing of maintenance requests</span></span>

<span data-ttu-id="cbccc-129">Miután létrehozta a karbantartási kérést, de még a munkarendeléssé történő átalakítás előtt, számos adatot frissíteni kell hozzá.</span><span class="sxs-lookup"><span data-stu-id="cbccc-129">After a maintenance request is created, but before it's converted to a work order, various information should be updated on it.</span></span> <span data-ttu-id="cbccc-130">Általában egy tervező vagy más adminisztratív alkalmazott hajtja végre ezt a feladatot.</span><span class="sxs-lookup"><span data-stu-id="cbccc-130">Typically, a planner or another administrative employee completes this task.</span></span>

- <span data-ttu-id="cbccc-131">Az **Összes karbantartási kérés** vagy **Aktív karbantartási kérések** lapon válassza ki a munkához használandó kérelmet, majd válassza a **Szerkesztés** parancsot .</span><span class="sxs-lookup"><span data-stu-id="cbccc-131">On the **All maintenance requests** or **Active maintenance requests** page, select the request to work with, and then select **Edit**.</span></span>

<span data-ttu-id="cbccc-132">A részleteket nézetben különböző információkat lehet frissíteni.</span><span class="sxs-lookup"><span data-stu-id="cbccc-132">In the details view, you can update various information.</span></span> <span data-ttu-id="cbccc-133">Íme néhány példa:</span><span class="sxs-lookup"><span data-stu-id="cbccc-133">Here are some examples:</span></span>

- <span data-ttu-id="cbccc-134">Az eszköz kiválasztása és ellenőrzése.</span><span class="sxs-lookup"><span data-stu-id="cbccc-134">Select and verify the asset.</span></span> <span data-ttu-id="cbccc-135">Ha később egy másik eszközt kell kiválasztania, akkor az **Eszköz ellenőrizve** beállítást állítsa **Nem** értékre.</span><span class="sxs-lookup"><span data-stu-id="cbccc-135">If you must select a different asset later, you can set the **Asset verified** option to **No**.</span></span>
- <span data-ttu-id="cbccc-136">Válassszon egy felelős karbantartásidolgozó-csoportot és/vagy egy felelős karbantartási dolgozót.</span><span class="sxs-lookup"><span data-stu-id="cbccc-136">Select a responsible maintenance worker group and/or a responsible maintenance worker.</span></span> <span data-ttu-id="cbccc-137">A szükséges beállításokkal kapcsolatos további tudnivalókat lásd a [Felelős karbantartási dolgozók](../setup-for-maintenance-requests/responsible-workers.md) című részt.</span><span class="sxs-lookup"><span data-stu-id="cbccc-137">For more information about the required setup, see [Responsible maintenance workers](../setup-for-maintenance-requests/responsible-workers.md).</span></span>
- <span data-ttu-id="cbccc-138">Válassza ki a karbantartási feladat típusát, és ha ez az információ releváns, akkor egy kapcsolódó karbantartási feladat változatát és a szakmát.</span><span class="sxs-lookup"><span data-stu-id="cbccc-138">Select a maintenance job type and, if this information is relevant, a related maintenance job variant and a job trade.</span></span>
- <span data-ttu-id="cbccc-139">A **Földrajzi szélesség** és **Földrajzi hosszúság** mezőkben adja meg a földrajzi koordinátákat.</span><span class="sxs-lookup"><span data-stu-id="cbccc-139">In the **Latitude** and **Longitude** fields, enter geographic coordinates.</span></span> <span data-ttu-id="cbccc-140">A karbantartási kéréshez hozzáadott koordinátákat a program automatikusan átviszi a kapcsolódó munkarendelésbe.</span><span class="sxs-lookup"><span data-stu-id="cbccc-140">Any coordinates that are added to a maintenance request are automatically transferred to a related work order.</span></span> 

![Karbantartási kérések frissítése](media/04-manage-maintenance-requests.png)

> [!NOTE]
> <span data-ttu-id="cbccc-142">Ha a karbantartási kérés létrehozásakor kiválaszt egy eszközt, akkor egy hiba adható hozzá a tárgyi eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="cbccc-142">If you select an asset when you create a maintenance request, you can add one fault to the asset.</span></span> <span data-ttu-id="cbccc-143">A karbantartási kérés létrehozása után, igény esetén több hibát is megadhat.</span><span class="sxs-lookup"><span data-stu-id="cbccc-143">After the maintenance request has been created, you can add more faults, as you require.</span></span> <span data-ttu-id="cbccc-144">Hibák hozzáadásához válassza ki az **Eszköz hibája** lehetőséget az **Összes karbantartási kérés** oldalon.</span><span class="sxs-lookup"><span data-stu-id="cbccc-144">To add faults, select **Asset fault** on the **All maintenance requests** page.</span></span>
