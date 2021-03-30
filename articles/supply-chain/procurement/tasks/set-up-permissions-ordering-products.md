---
title: Engedélyek létrehozása, amelyek birtokában mások nevében lehet termékeket rendelni
description: Ez a témakör bemutatja, hogyan adhat engedélyt dolgozóknak más dolgozók nevében beszerzési igénylésének elkészítésére.
author: RichardLuan
manager: tfehr
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqAuthorization, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 54d84e38a8816ec716414661d002cbe171623772
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5244015"
---
# <a name="set-up-permissions-for-ordering-products-on-behalf-of-someone-else"></a><span data-ttu-id="e25d0-103">Engedélyek létrehozása, amelyek birtokában mások nevében lehet termékeket rendelni</span><span class="sxs-lookup"><span data-stu-id="e25d0-103">Set up permissions for ordering products on behalf of someone else</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e25d0-104">Ez a témakör bemutatja, hogyan adhat engedélyt dolgozóknak más dolgozók nevében beszerzési igénylésének elkészítésére.</span><span class="sxs-lookup"><span data-stu-id="e25d0-104">This topic explains how to grant workers permission to prepare purchase requisitions on behalf of other workers.</span></span> <span data-ttu-id="e25d0-105">Más szóval a beszerzési igénylés „készítő” létrehozhat igénylést másik „kérelmező”-nek.</span><span class="sxs-lookup"><span data-stu-id="e25d0-105">In other words, a purchase requisition "preparer" can create a requisition for another "requester."</span></span> <span data-ttu-id="e25d0-106">AZ eljárás azt is megmutatja, hogyan adjon dolgozói engedélyeket cikkek és szolgáltatások megrendelésére különböző jogi személyek vagy üzemi egységek esetén.</span><span class="sxs-lookup"><span data-stu-id="e25d0-106">The procedure also shows how to grant a worker permission to order items and services in different legal entities or operating units.</span></span> <span data-ttu-id="e25d0-107">Általában a beszerzési vezető végzi el ezeket a feladatokat.</span><span class="sxs-lookup"><span data-stu-id="e25d0-107">Typically, these tasks are performed by a purchasing manager.</span></span> <span data-ttu-id="e25d0-108">Ezt a folyamatot az USMF bemutatócégnél vagy a saját adataiban is használhatja.</span><span class="sxs-lookup"><span data-stu-id="e25d0-108">You can use this procedure either on data for the USMF demo company or on your own data.</span></span>


## <a name="grant-permission-to-enter-purchase-requisitions-on-behalf-of-another-worker"></a><span data-ttu-id="e25d0-109">Adjon engedélyt, hogy bevihessen beszerzési igénylést egy másik dolgozó nevében.</span><span class="sxs-lookup"><span data-stu-id="e25d0-109">Grant permission to enter purchase requisitions on behalf of another worker</span></span>
1. <span data-ttu-id="e25d0-110">A navigációs ablaktáblán ugorjon a **Modulok > Beszerzés és forrás> Beállítás > Irányelvek > Beszerzési igénylési engedélyek** elemre.</span><span class="sxs-lookup"><span data-stu-id="e25d0-110">In the navigation pane, go to **Modules > Procurement and sourcing > Setup > Policies > Purchase requisition permissions**.</span></span> <span data-ttu-id="e25d0-111">Győződjön meg arról, hogy az **Aktuális nézet** mező értéke **Készítő által** értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="e25d0-111">Make sure that the **Current view** field is set to **By preparer**.</span></span> <span data-ttu-id="e25d0-112">A bal oldali ablakban található lista mutatja azokat a személyeket, akik kaphatnak engedélyt más felhasználók nevében igénylésének elkészítésére.</span><span class="sxs-lookup"><span data-stu-id="e25d0-112">The list in the left pane shows the people who can be granted permission to prepare requisitions on behalf of other people.</span></span>  
2. <span data-ttu-id="e25d0-113">Válassza ki azt a személyt, akinek az engedélyt adni akarja (a készítő).</span><span class="sxs-lookup"><span data-stu-id="e25d0-113">Select the person to grant permission to (the preparer).</span></span>
3. <span data-ttu-id="e25d0-114">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e25d0-114">Select **Add**.</span></span>
4. <span data-ttu-id="e25d0-115">Keresse meg és válassza ki a személyt, amelyet kérelmezőként kíván hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="e25d0-115">Find and select the person to add as a requester.</span></span>
    - <span data-ttu-id="e25d0-116">A kérelmező az a személy, aki a készítő nevében igényléseket hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="e25d0-116">The requester is the person that the preparer can create requisitions on behalf of.</span></span>  
    - <span data-ttu-id="e25d0-117">Az  **Engedélyezés** mezőben válassza a **Specifikus** lehetőséget, ha a készítőnek képesnek kell lennie a kijelölt dolgozó nevében beszerzési igénylést készítenie.</span><span class="sxs-lookup"><span data-stu-id="e25d0-117">In the **Authorization** field, select **Specific** if the preparer should be able to create purchase requisitions on behalf of the selected worker.</span></span> <span data-ttu-id="e25d0-118">Válassza a **Jelentés** lehetőséget, ha a készítő számára lehetséges kell legyen, hogy az összes olyan dolgozó nevében készíthessen beszerzési igénylést, akik az adott dolgozónak jelentenek.</span><span class="sxs-lookup"><span data-stu-id="e25d0-118">Select **Reporting** if the preparer should also be able to create purchase requisitions on behalf of all workers who report to that worker.</span></span>  
5. <span data-ttu-id="e25d0-119">Adjon meg egy dátumot az **Érvényesség** mezőben.</span><span class="sxs-lookup"><span data-stu-id="e25d0-119">In the **Effective** field, enter a date.</span></span>
6. <span data-ttu-id="e25d0-120">A **Lejárat ideje** mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="e25d0-120">In the **Expiration** field, enter a date.</span></span>

## <a name="view-preparers-who-have-permission-to-create-purchase-requisitions-for-a-selected-worker"></a><span data-ttu-id="e25d0-121">Tekintse át azokat a készítőket, akik engedéllyel rendelkeznek az kijelölt dolgozó nevében történő beszerzési igénylések létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="e25d0-121">View preparers who have permission to create purchase requisitions for a selected worker</span></span>
1. <span data-ttu-id="e25d0-122">Az **Aktuális nézet** mezőben, válassza a **Kérelmező által** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e25d0-122">In the **Current view** field, select **By requester**.</span></span> <span data-ttu-id="e25d0-123">Ezt a nézet mutatja azoknak a készítőknek a listáját, akik engedélyt kaptak beszerzési igények létrehozására egy adott dolgozó nevében.</span><span class="sxs-lookup"><span data-stu-id="e25d0-123">This view shows a list of preparers who have been granted permission to create purchase requisitions on behalf of a selected worker.</span></span>  
2. <span data-ttu-id="e25d0-124">Használja a Gyors Szűrést, hogy megtalálja azt a dolgozót, akit most adott hozzá kérelmezőként.</span><span class="sxs-lookup"><span data-stu-id="e25d0-124">Use the Quick Filter to find the worker that you just added as the requester.</span></span>
3. <span data-ttu-id="e25d0-125">Válassza ki a kérelmezőt.</span><span class="sxs-lookup"><span data-stu-id="e25d0-125">Select the requester.</span></span> <span data-ttu-id="e25d0-126">A Készítő lista azokat az embereket mutatja, akik engedéllyel rendelkeznek a bal oldali ablakban kiválasztott kérelmező nevében történő cikk rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="e25d0-126">The Preparer list shows the people who have permission to order items on behalf of the requester who is selected in the left pane.</span></span>  <span data-ttu-id="e25d0-127">További készítőknek itt is hozzáadhat.</span><span class="sxs-lookup"><span data-stu-id="e25d0-127">You can add additional preparers here.</span></span> <span data-ttu-id="e25d0-128">Ez a nézet lehetővé teszi a kérelmező engedély igénylés kiosztására, hogy igénylést hozhasson létre olyan jogi személyek és üzemi egységek nevében, amelyek nem az illető elsődleges jogi személye vagy üzemi egysége.</span><span class="sxs-lookup"><span data-stu-id="e25d0-128">This view also lets you grant the requester permission to create requisitions in legal entities and operating units that aren't that person's primary legal entity or operating unit.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]