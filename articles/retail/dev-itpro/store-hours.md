---
title: Nyitvatartási idő létrehozása és frissítése
description: Ez a témakör azt mutatja be, hogyan lehet a Retail Headquarters alkalmazásban létrehozni és frissíteni a nyitvatartási időt.
author: josaw1
manager: AnnBe
ms.date: 7/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Retail 10.0.1 update
ms.openlocfilehash: 811d499a3eb8133e5ffd29bb4ae6a0c57708accd
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/24/2019
ms.locfileid: "2023442"
---
# <a name="create-and-update-store-hours"></a><span data-ttu-id="d57fd-103">Nyitvatartási idő létrehozása és frissítése</span><span class="sxs-lookup"><span data-stu-id="d57fd-103">Create and update store hours</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="overview"></a><span data-ttu-id="d57fd-104">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="d57fd-104">Overview</span></span>

<span data-ttu-id="d57fd-105">A kiskereskedők egyetlen helyről végezhetik a különböző földrajzi régiókban található üzletek nyitvatartási idejének létrehozását, karbantartását és kezelését.</span><span class="sxs-lookup"><span data-stu-id="d57fd-105">From a single place, retailers can create, maintain, and manage the store hours for different stores across geographic regions.</span></span> <span data-ttu-id="d57fd-106">A nyitvatartási idő ezután megjeleníthető a pénztári (POS) terminálokon.</span><span class="sxs-lookup"><span data-stu-id="d57fd-106">The store hours can then be shown on point of sale (POS) terminals.</span></span> <span data-ttu-id="d57fd-107">Így a pénztárosok megoszthatják a nyitvatartási időt a vevőkkel, és hatékonyabban segíthetnek azokat a vásárlóknak, akik más üzletek készlete iránt érdeklődnek.</span><span class="sxs-lookup"><span data-stu-id="d57fd-107">In this way, cashiers can share store hours with customers and better help shoppers who are interested in inventory in other stores.</span></span> <span data-ttu-id="d57fd-108">A nyitvatartási idő a nyugtákra is rányomtatható, az üzletbe később visszatérni kívánó vevők tájékoztatására.</span><span class="sxs-lookup"><span data-stu-id="d57fd-108">The store hours can also be printed on receipts, in case customers want to return to the store later.</span></span>

<span data-ttu-id="d57fd-109">A különböző csatornákhoz több nyitvatartási idő is konfigurálható.</span><span class="sxs-lookup"><span data-stu-id="d57fd-109">Multiple store hours can be configured across different channels.</span></span> <span data-ttu-id="d57fd-110">Ilyen csatornák a fizikai üzlethelyiségek, a telefonos ügyfélszolgálatok, a mobileszközök és az elektronikus kereskedelmi webhelyek.</span><span class="sxs-lookup"><span data-stu-id="d57fd-110">These channels include brick-and-mortar stores, call centers, mobile devices, and e-Commerce sites.</span></span>

<span data-ttu-id="d57fd-111">Ha egy vevőnek egy másik üzletben felvehető rendelése van, akkor a pénztáros kiválaszthatja azokat a dátumokat, amikor a rendelés felvehetővé válik abban az üzletben.</span><span class="sxs-lookup"><span data-stu-id="d57fd-111">If a customer has a pickup order for a different store, the cashier can select dates when the pickup will be available in that store.</span></span> <span data-ttu-id="d57fd-112">Az üzletkeresésben megjelennek a dátumok és a nyitvatartási idők.</span><span class="sxs-lookup"><span data-stu-id="d57fd-112">The store lookup will provide a reference to the dates and store times.</span></span> <span data-ttu-id="d57fd-113">A pénztáros kiválaszthat egy dátumot és helyet, valamint kinyomtathat egy átvételi bizonylatot is, amely tartalmazza az üzlet nyitvatartási idejét.</span><span class="sxs-lookup"><span data-stu-id="d57fd-113">The cashier can select a date and location, and can also print a pickup receipt that includes the store hours.</span></span>

<span data-ttu-id="d57fd-114">Ez a funkció a Microsoft Dynamics 365 Retail 8.1.2-es és későbbi verzióiban áll rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="d57fd-114">This functionality is available in Microsoft Dynamics 365 Retail versions 8.1.2 and later.</span></span>

## <a name="configure-store-hours"></a><span data-ttu-id="d57fd-115">Nyitvatartási idő konfigurálása</span><span class="sxs-lookup"><span data-stu-id="d57fd-115">Configure store hours</span></span>

<span data-ttu-id="d57fd-116">A nyitvatartási idő konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="d57fd-116">Follow these steps to configure store hours.</span></span>

1. <span data-ttu-id="d57fd-117">Lépjen a **Kiskereskedelem** \> **Csatorna beállítása** \> **Nyitvatartás** elemre.</span><span class="sxs-lookup"><span data-stu-id="d57fd-117">Go to **Retail** \> **Channel Setup** \> **Store hours**.</span></span>
2. <span data-ttu-id="d57fd-118">Válassza az **Új** lehetőséget új nyitvatartásiidő-sablon létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="d57fd-118">Select **New** to create a new store hours template.</span></span> <span data-ttu-id="d57fd-119">Meglévő sablon használatához válassza ki a sablont a bal oldali ablaktáblán.</span><span class="sxs-lookup"><span data-stu-id="d57fd-119">To use an existing template, select the template in the left pane.</span></span>
3. <span data-ttu-id="d57fd-120">A **Tartomány hozzáadása** párbeszédpanelen adja meg a dátumtartományt, a nyitvatartási időt, valamint az esetleges ünnepnapokat.</span><span class="sxs-lookup"><span data-stu-id="d57fd-120">In the **Add range** dialog box, define the date range, the store hours, and any holidays that are required.</span></span>

    - <span data-ttu-id="d57fd-121">Ha a nyitvatartási idő nem változik, válassza a **Nem ér véget** lehetőséget a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="d57fd-121">If store hours don't change, select **Never ends** in the **End date** field.</span></span>
    - <span data-ttu-id="d57fd-122">Ha a nyitvatartási idő egy adott hónapra, hétre vagy napra vonatkozik, állítsa be a megfelelő dátumokat a **Kezdő dátum** és a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="d57fd-122">If the store hours are for a specific month, week, or day, set the appropriate dates in the **Start Date** and **End date** fields.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d57fd-123">Több sablont is létrehozhat, egymást átfedő kezdő és a záró dátumokkal.</span><span class="sxs-lookup"><span data-stu-id="d57fd-123">You can create multiple templates that have overlapping start and end dates.</span></span> <span data-ttu-id="d57fd-124">Így például megadhatja a különböző időzónákban található üzletek nyitvatartási idejét.</span><span class="sxs-lookup"><span data-stu-id="d57fd-124">Therefore, you can, for example, define store hours for stores in different time zones.</span></span>

    <span data-ttu-id="d57fd-125">![Tartomány hozzáadása párbeszédpanel](../dev-itpro/media/Storehours1.png "Tartomány hozzáadása párbeszédpanel")</span><span class="sxs-lookup"><span data-stu-id="d57fd-125">![Add range dialog box](../dev-itpro/media/Storehours1.png "Add range dialog box")</span></span>

4. <span data-ttu-id="d57fd-126">A nyitvatartási idő sablonját társítsa azokkal az üzletekkel, ahol használatban lesz.</span><span class="sxs-lookup"><span data-stu-id="d57fd-126">Associate the store hours template with the stores where it will be used.</span></span> <span data-ttu-id="d57fd-127">A **Szervezeti csomópontok kiválasztása** párbeszédpanelen válassza ki azokat az üzleteket, régiókat és szervezeteket, amelyekkel a sablont társítani szeretné.</span><span class="sxs-lookup"><span data-stu-id="d57fd-127">In the **Choose organization nodes** dialog box, select the stores, regions, and organizations that the template should be associated with.</span></span>

    - <span data-ttu-id="d57fd-128">Minden üzlethez csak egy nyitvatartásiidő-sablon tartozhat.</span><span class="sxs-lookup"><span data-stu-id="d57fd-128">Only one store hours template can be associated with each store.</span></span>
    - <span data-ttu-id="d57fd-129">A nyílgombokkal válassza ki az üzleteket, régiókat vagy szervezeteket.</span><span class="sxs-lookup"><span data-stu-id="d57fd-129">Use the arrow buttons to select stores, regions, or organizations.</span></span> <span data-ttu-id="d57fd-130">A naptár az üzletek vagy üzletcsoportok számára lesz hozzáférhető, és a pénztárnál is megjelenik referenciaként.</span><span class="sxs-lookup"><span data-stu-id="d57fd-130">The calendar will be available to the stores or store groups, and it will be visible at the POS for reference.</span></span>

    <span data-ttu-id="d57fd-131">![Szervezeti csomópontok kiválasztása párbeszédpanel](../dev-itpro/media/Storehours2.png "Szervezeti csomópontok kiválasztása párbeszédpanel")</span><span class="sxs-lookup"><span data-stu-id="d57fd-131">![Choose organization nodes dialog box](../dev-itpro/media/Storehours2.png "Choose organization nodes dialog box")</span></span>

5. <span data-ttu-id="d57fd-132">Az **Elosztási ütemezés** oldalon futtassa a **1070** és **1090** feladatokat, hogy a nyitvatartási időt elérhetővé tegye a pénztárnál.</span><span class="sxs-lookup"><span data-stu-id="d57fd-132">On the **Distribution schedule** page, run the **1070** and **1090** jobs to make the store hours available to the POS.</span></span>

## <a name="add-store-hours-to-printed-receipts"></a><span data-ttu-id="d57fd-133">Nyitvatartási idő hozzáadása a nyomtatott nyugtákhoz</span><span class="sxs-lookup"><span data-stu-id="d57fd-133">Add store hours to printed receipts</span></span>

<span data-ttu-id="d57fd-134">A nyitvatartási idő kinyomtatott pénztári nyugtákon való feltüntetéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="d57fd-134">Follow these steps to add store hours to the printed POS receipts.</span></span>

1. <span data-ttu-id="d57fd-135">Nyissa meg a nyugtatervezőt.</span><span class="sxs-lookup"><span data-stu-id="d57fd-135">Open the receipt designer.</span></span>
2. <span data-ttu-id="d57fd-136">Válassza ki a **Lábléc** elemet a bal alsó sarokban.</span><span class="sxs-lookup"><span data-stu-id="d57fd-136">Select **Footer** in the lower-left corner.</span></span>
3. <span data-ttu-id="d57fd-137">Húzza át a **Nyitvatartás** elemet a bal oldali ablaktáblából a nyugta sablonjának alján található láblécbe.</span><span class="sxs-lookup"><span data-stu-id="d57fd-137">Drag the **Store hours** element from the left pane to the footer at the bottom of the receipt template.</span></span>
4. <span data-ttu-id="d57fd-138">A **Nyitvatartás** elem alapértelmezett feliratát igény szerint szerkesztheti.</span><span class="sxs-lookup"><span data-stu-id="d57fd-138">You can edit the default label on the **Store hours** element as you require.</span></span>
5. <span data-ttu-id="d57fd-139">Mentse a nyugtát, és zárja be a nyugtatervezőt.</span><span class="sxs-lookup"><span data-stu-id="d57fd-139">Save the receipt, and close the receipt designer.</span></span>
6. <span data-ttu-id="d57fd-140">Az **Elosztási ütemezés** lapon futtassa a **1070** és a **1090** feladatot.</span><span class="sxs-lookup"><span data-stu-id="d57fd-140">On the **Distribution schedule** page, run the **1070** and **1090** jobs.</span></span>
7. <span data-ttu-id="d57fd-141">Bejelentkezés a pénztárba.</span><span class="sxs-lookup"><span data-stu-id="d57fd-141">Sign in to the POS.</span></span>
8. <span data-ttu-id="d57fd-142">Hajtson végre egy értékesítést, és válassza a nyugta nyomtatását.</span><span class="sxs-lookup"><span data-stu-id="d57fd-142">Complete a sale, and select to print a receipt.</span></span>

<span data-ttu-id="d57fd-143">A pénztári nyugtákon ettől kezdve megjelenik a nyitvatartási idő.</span><span class="sxs-lookup"><span data-stu-id="d57fd-143">POS receipts now include the store hours.</span></span> <span data-ttu-id="d57fd-144">Ha a sablonban egy vagy több ünnepnap is meg van adva, akkor azok is megjelennek a nyugtán.</span><span class="sxs-lookup"><span data-stu-id="d57fd-144">If any holidays were included in the template, they are shown on the receipt.</span></span>

<span data-ttu-id="d57fd-145">![Példa nyugtára](../dev-itpro/media/Storehours3.png "Példa nyugtára")</span><span class="sxs-lookup"><span data-stu-id="d57fd-145">![Receipt example](../dev-itpro/media/Storehours3.png "Receipt example")</span></span>
