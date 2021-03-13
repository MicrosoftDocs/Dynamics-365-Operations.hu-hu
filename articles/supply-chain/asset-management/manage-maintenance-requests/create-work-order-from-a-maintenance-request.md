---
title: Munkarendelések létrehozása karbantartási kérésekből
description: Ez a témakör azt mutatja be, hogyan lehet munkarendelést létrehozni karbantartási kérésből az Eszközkezelés modulban.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 23039306bb827beb861eaacc3177f4917fabc8bf
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/16/2021
ms.locfileid: "5018096"
---
# <a name="create-work-orders-from-maintenance-requests"></a><span data-ttu-id="495a1-103">Munkarendelések létrehozása karbantartási kérésekből</span><span class="sxs-lookup"><span data-stu-id="495a1-103">Create work orders from maintenance requests</span></span>

[!include [banner](../../includes/banner.md)]

 


<span data-ttu-id="495a1-104">Miután létrehozta a karbantartási kéréseket, egyszerűen átalakíthatja azokat a munkarendelésekké.</span><span class="sxs-lookup"><span data-stu-id="495a1-104">After you've created maintenance requests, you can easily convert them to work orders.</span></span> <span data-ttu-id="495a1-105">Ez a témakör a karbantartási kérésekkel végzett munkával kapcsolatos leggyorsabb módszert írja le, egyszerre több karbantartási kérelmet frissít, majd egyszerre több karbantartási kérelemhez készít munkarendelést.</span><span class="sxs-lookup"><span data-stu-id="495a1-105">This topic describes the quickest way to work with maintenance requests, update several maintenance requests at the same time, and then create a work order for several maintenance requests at the same time.</span></span> <span data-ttu-id="495a1-106">Az **Aktív karbantartási kérések** vagy **Saját munkavégzési helyszínhez tartozó karbantartási kérések** oldalon egyszerre egy karbantartási kéréssel is dolgozhat, és egy karbantartási kérést is átalakíthat munkarendeléssé.</span><span class="sxs-lookup"><span data-stu-id="495a1-106">On the **Active maintenance requests** or **My functional location maintenance requests** page, you can also work with one maintenance request at a time and convert one maintenance request to a work order.</span></span>

> [!NOTE]
> <span data-ttu-id="495a1-107">Minden karbantartási kérés csak egy munkarendeléshez kapcsolható.</span><span class="sxs-lookup"><span data-stu-id="495a1-107">Every maintenance request can be related to only one work order.</span></span> <span data-ttu-id="495a1-108">Azonban több karbantartási kérés is szerepelhet egy munkarendelésben, még akkor is, ha a karbantartási kérések különböző eszközökkel rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="495a1-108">However, multiple maintenance requests can be included in one work order, even if the maintenance requests have different assets.</span></span>

1. <span data-ttu-id="495a1-109">Válassza az **Eszközkezelés** \> **Közös** \> **Karbantartási kérések** \> **Összes karbantartási kérés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="495a1-109">Select **Asset management** \> **Common** \> **maintenance requests** \> **All maintenance requests**.</span></span>
2. <span data-ttu-id="495a1-110">Ahhoz, hogy a karbantartási kérésekből munkarendeléseket hozhasson létre, ki kell választania legalább egy karbantartási feladattípust a karbantartási kérésekhez, valamint egy karbantartási feladattípust- változatot és szakmát ha ez az információ releváns.</span><span class="sxs-lookup"><span data-stu-id="495a1-110">Before you can create a work order from maintenance requests, you must select, at a minimum, a maintenance job type for the maintenance requests, and also a maintenance job type variant and trade, if this information is relevant.</span></span> <span data-ttu-id="495a1-111">A rácsnézetben egyszerűen frissítheti a karbantartási kérések adatait.</span><span class="sxs-lookup"><span data-stu-id="495a1-111">In the grid view, you can easily update information for a maintenance request.</span></span>
3. <span data-ttu-id="495a1-112">Ha készen áll a munkarendelés létrehozására, válassza ki azokat a karbantartási kéréseket, amelyeket bele szeretne foglalni abba.</span><span class="sxs-lookup"><span data-stu-id="495a1-112">When you're ready to create a work order, select the maintenance requests to include in it.</span></span>

    - <span data-ttu-id="495a1-113">Ha több karbantartási kérést választ egy munkarendeléssé konvertáláshoz, akkor a munkarendelés létrehozása előtt az **Eszköz** és a **Karbantartási feladat típusa** mezőt is be kell állítania.</span><span class="sxs-lookup"><span data-stu-id="495a1-113">If you select several maintenance requests to convert to a work order, both the **Asset** field and the **Maintenance job type** field must be set before you create the work order.</span></span>
    - <span data-ttu-id="495a1-114">Ha egy munkarendelésre való átalakításhoz kiválaszt egy karbantartási kérést, csak az **Eszköz** mezőt kell megadni a munkarendelés létrehozása előtt.</span><span class="sxs-lookup"><span data-stu-id="495a1-114">If you select one maintenance request to convert to a work order, only the **Asset** field must be set before you create the work order.</span></span> <span data-ttu-id="495a1-115">A munkarendelés létrehozásakor azonban a **Munkarendelés létrehozása** párbeszédpanelen kiválaszthatja a karbantartási feladat típusát (és a kapcsolódó karbantartási feladattípus változatát és szakmáját, ha ez az információ releváns).</span><span class="sxs-lookup"><span data-stu-id="495a1-115">However, when you create the work order, you can select a maintenance job type (and a related maintenance job type variant and trade, if this information is relevant) in the **Create work order** dialog box.</span></span>

4. <span data-ttu-id="495a1-116">**Munkarendelés** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="495a1-116">Select **Work order**.</span></span>
5. <span data-ttu-id="495a1-117">A **A Munkarendelés létrehozása** párbeszédpanelen állítsa be a mezőket, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="495a1-117">In the **Create work order** dialog box, set the fields, and then select **OK**.</span></span>

    <span data-ttu-id="495a1-118">Egy üzenetsáv figyelmeztetést adhat arról, hogy új munkarendelést hoztak létre.</span><span class="sxs-lookup"><span data-stu-id="495a1-118">A message bar might notify you that a new work order has been created.</span></span>

    <span data-ttu-id="495a1-119">Ezenkívül amikor karbantartási kérésen alapuló munkarendelést hoz létre, ha a karbantartási kéréssel kapcsolatos eszköz szerepel egy garanciális megállapodásban, egy üzenetsáv értesíti a garanciamegállapodásról.</span><span class="sxs-lookup"><span data-stu-id="495a1-119">Additionally, when you create a work order that is based on a maintenance request, if the asset that is related to the maintenance request is included in a warranty agreement, a message bar notifies you about the warranty agreement.</span></span>

6. <span data-ttu-id="495a1-120">Válassza az **Eszközkezelés** \> **Közös** \> **Munkarendelések** \> **Összes munkarendelés** lehetőséget, és nyissa meg az új munkarendelést.</span><span class="sxs-lookup"><span data-stu-id="495a1-120">Select **Asset management** \> **Common** \> **Work orders** \> **All work orders**, and open the new work order.</span></span>

    ![Új munkarendelés nyitása](media/05-manage-maintenance-requests.png)

