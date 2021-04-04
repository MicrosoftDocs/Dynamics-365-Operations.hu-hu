---
title: Szervizrendelések létrehozása manuálisan
description: Szervizrendeléseket a szolgáltatási szerződésből vagy a **Szervizrendelések** képernyőn lehet manuálisan létrehozni.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 72b600bc59119a6304fa043240a34051435f8691
ms.sourcegitcommit: 34b8f6f5c6134b7b97a9fb41d0b2e63215c67062
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5470953"
---
# <a name="create-service-orders-manually"></a><span data-ttu-id="1d06a-103">Szervizrendelések létrehozása manuálisan</span><span class="sxs-lookup"><span data-stu-id="1d06a-103">Create service orders manually</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="1d06a-104">Szervizrendeléseket a szolgáltatási szerződésből vagy a **Szervizrendelések** képernyőn lehet manuálisan létrehozni.</span><span class="sxs-lookup"><span data-stu-id="1d06a-104">You can create service orders manually by using a service agreement or by using the **Service orders** form.</span></span> <span data-ttu-id="1d06a-105">Projektekből is létre lehet hozni szervizrendelést.</span><span class="sxs-lookup"><span data-stu-id="1d06a-105">You can also create a service order from a project.</span></span>

> [!TIP]
> <P><span data-ttu-id="1d06a-106">Automatizált folyamatok segítségével hozhat létre szervizrendeléseket.</span><span class="sxs-lookup"><span data-stu-id="1d06a-106">You can use automated processes to create service orders.</span></span> 

## <a name="create-a-service-order-manually-from-a-service-agreement"></a><span data-ttu-id="1d06a-107">Szervizrendelés manuális létrehozása egy szolgáltatási szerződésből</span><span class="sxs-lookup"><span data-stu-id="1d06a-107">Create a service order manually from a service agreement</span></span>

1.  <span data-ttu-id="1d06a-108">Válassza a **Szolgáltatáskezelés** \> **Közös** \> **Szolgáltatási szerződések** \> **Szolgáltatási szerződések** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1d06a-108">Select **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="1d06a-109">Válasszon ki egy szolgáltatási szerződést, vagy hozzon létre egy új szolgáltatási szerződést.</span><span class="sxs-lookup"><span data-stu-id="1d06a-109">Select a service agreement or create a new service agreement.</span></span>

3.  <span data-ttu-id="1d06a-110">Válassza a **Szállítás** lapot, és a **Létrehozás** csoportban válassza a **Tervezett szervizrendelések** lehetőséget a **Szervizrendelések létrehozása** képernyő megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="1d06a-110">Select the **Deliver** tab and in the **Create** group select **Planned service orders** to open the **Create service orders** form.</span></span>

## <a name="create-a-service-order-manually-in-the-service-orders-form"></a><span data-ttu-id="1d06a-111">Szervizrendelés manuális létrehozása a Szervizrendelések képernyőn</span><span class="sxs-lookup"><span data-stu-id="1d06a-111">Create a service order manually in the Service orders form</span></span>

1.  <span data-ttu-id="1d06a-112">Válassza: **Szolgáltatáskezelés** \> **Közös** \> **Szervizrendelések** \> **Szervizrendelések**.</span><span class="sxs-lookup"><span data-stu-id="1d06a-112">Select **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="1d06a-113">Válassza ki az **Új** lehetőséget egy új szolgáltatási utasítás létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="1d06a-113">Select **New** to create a new service order.</span></span>

3.  <span data-ttu-id="1d06a-114">Hozza létre a szervizrendelés szervizrendeléssorait.</span><span class="sxs-lookup"><span data-stu-id="1d06a-114">Create service order lines for the service order.</span></span>

> [!NOTE]
> <P><span data-ttu-id="1d06a-115">Ha a <STRONG>Szolgáltatáskezelés paraméterei</STRONG> képernyő <STRONG>Engedélyezés szolgáltatási szerződés nélkül</STRONG> jelölőnégyzete be van jelölve, akkor a szervizrendeléssorok tranzakcióit fel lehet adni anélkül, hogy szolgáltatási szerződéshez társítaná a szervizrendelést.</span><span class="sxs-lookup"><span data-stu-id="1d06a-115">If the <STRONG>Allow without service agreement</STRONG> check box in the <STRONG>Service management parameters</STRONG> form is selected, you can post the transactions from the service order lines without attaching the service order to a service agreement.</span></span> <span data-ttu-id="1d06a-116">Ha nincs bejelölve a jelölőnégyzet, akkor a kézzel létrehozott szervizrendelést társítani kell a projekthez a szervizrendeléssorok feladása előtt.</span><span class="sxs-lookup"><span data-stu-id="1d06a-116">If the check box is cleared, you must attach the manually created service order to a project before posting the service order lines.</span></span></P>

## <a name="create-a-service-order-from-a-project"></a><span data-ttu-id="1d06a-117">Szervizrendelés létrehozása egy projektből</span><span class="sxs-lookup"><span data-stu-id="1d06a-117">Create a service order from a project</span></span>

1.  <span data-ttu-id="1d06a-118">Lépjen a következőkre: **Projektvezetés és könyvelés** \> **Közös** \> **Projektek** \> **Minden projekt**.</span><span class="sxs-lookup"><span data-stu-id="1d06a-118">Go to **Project management and accounting** \> **Common** \> **Projects** \> **All projects**.</span></span>

2.  <span data-ttu-id="1d06a-119">A **Projektek** képernyőn, a **Műveleti panelen**, válassza a **Kezelés** lapot \> kattintson **Szolgáltatás** \> **Szervizrendelések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1d06a-119">In the **Projects** form, on the **Action Pane**, select the **Manage** tab \> select **Service** \> **Service orders**.</span></span>

3.  <span data-ttu-id="1d06a-120">Az előbbi eljárás segítségével hozza létre manuálisan a szervizrendelést a **Szervizrendelések** képernyőn.</span><span class="sxs-lookup"><span data-stu-id="1d06a-120">Follow the previous procedure to create a service order manually in the **Service orders** form.</span></span> <span data-ttu-id="1d06a-121">A **Projekt azonosító** mezőben látható a projektreferencia.</span><span class="sxs-lookup"><span data-stu-id="1d06a-121">The **Project ID** field displays the project reference.</span></span>

> [!NOTE]
> <P><span data-ttu-id="1d06a-122">Ha a <STRONG>Szolgáltatáskezelés paraméterei</STRONG> képernyő <STRONG>Engedélyezés szolgáltatási szerződés nélkül</STRONG> jelölőnégyzete be van jelölve, akkor a szervizrendeléssorok tranzakcióit fel lehet adni anélkül, hogy szolgáltatási szerződéshez társítaná a szervizrendelést.</span><span class="sxs-lookup"><span data-stu-id="1d06a-122">If the <STRONG>Allow without service agreement</STRONG> check box in the <STRONG>Service management parameters</STRONG> form is selected, you can post the transactions from the service order lines without attaching the service order to a service agreement.</span></span> <span data-ttu-id="1d06a-123">Ha nincs bejelölve a jelölőnégyzet, akkor a kézzel létrehozott szervizrendelést társítani kell a projekthez a szervizrendeléssorok feladása előtt.</span><span class="sxs-lookup"><span data-stu-id="1d06a-123">If the check box is cleared, you must attach the manually created service order to a project before posting the service order lines.</span></span></P>

## <a name="create-a-service-order-from-the-sales-order-form"></a><span data-ttu-id="1d06a-124">Szervizrendelés létrehozása az értékesítési rendelés képernyőn</span><span class="sxs-lookup"><span data-stu-id="1d06a-124">Create a service order from the Sales order form</span></span>

<span data-ttu-id="1d06a-125">Szervizrendelést az **Értékesítési rendelések** képernyő használatával is létrehozhat; ehhez használja az **Új szervizrendelés létrehozása az értékesítési rendelés alapján** varázslót.</span><span class="sxs-lookup"><span data-stu-id="1d06a-125">You can create a service order from the **Sales orders** form by using the **Create a new service order based on the sales order** wizard.</span></span>

1.  <span data-ttu-id="1d06a-126">Lépjen ide: **Értékesítés és marketing** \> **Közös** \> **Értékesítési rendelések** \> **Összes értékesítési rendelés**.</span><span class="sxs-lookup"><span data-stu-id="1d06a-126">Go to **Sales and marketing** \> **Common** \> **Sales orders** \> **All sales orders**.</span></span>

2.  <span data-ttu-id="1d06a-127">Nyissa meg a megfelelő értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="1d06a-127">Open the relevant sales order.</span></span>

3.  <span data-ttu-id="1d06a-128">Az **Értékesítési rendelés** fülön kattintson a **Szervizrendelés** lehetőségre ahhoz, hogy elindítsa az **Új szervizrendelés létrehozása az értékesítési rendelés alapján varázslót**.</span><span class="sxs-lookup"><span data-stu-id="1d06a-128">On the **Sales order** tab, select **Service order** to start the **Create a new service order based on the sales order** wizard.</span></span>

4.  <span data-ttu-id="1d06a-129">Válassza a **Tovább \>** gombot, majd végezze el a következő lépéseket a **Válassza ki a szerződést a szervizrendeléshez** lapon:</span><span class="sxs-lookup"><span data-stu-id="1d06a-129">Select **Next \>**, and then complete the following steps on the **Select agreement for service order** page:</span></span>
    
      - <span data-ttu-id="1d06a-130">A **Szolgáltatási szerződés** mezőben válassza ki azt a szolgáltatási szerződést, amelyhez az új szervizrendelést társítani kívánja.</span><span class="sxs-lookup"><span data-stu-id="1d06a-130">Use the **Service agreement** field to select the service agreement with which the new service order should be associated.</span></span>
    
      - <span data-ttu-id="1d06a-131">Nem kötelező: A **Projektazonosító** mező segítségével egy projekthez társíthatja a szervizrendelést.</span><span class="sxs-lookup"><span data-stu-id="1d06a-131">Optional: Use the **Project ID** field to associate this service order with a particular project.</span></span>

5.  <span data-ttu-id="1d06a-132">Válassza a **Tovább \>** gombot, majd végezze el a következő lépéseket a **Szervizrendelés létrehozása** lapon:</span><span class="sxs-lookup"><span data-stu-id="1d06a-132">Select **Next \>**, and then complete the following steps on the **Create service order** page:</span></span>
    
      - <span data-ttu-id="1d06a-133">Adja meg a szervizhívás indításának dátumát és időpontját a **Preferált szolgáltatási idő** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1d06a-133">Enter a date and time for the service call to begin in the **Preferred service time** field.</span></span>
    
      - <span data-ttu-id="1d06a-134">Nem kötelező. módosítsa a **Leírás** mezőben szereplő szöveget.</span><span class="sxs-lookup"><span data-stu-id="1d06a-134">Optional: Modify the text in the **Description** field.</span></span> <span data-ttu-id="1d06a-135">Alapértelmezés szerint ez a mező tartalmazza az előző lapon kiválasztott szolgáltatási szerződés leírását.</span><span class="sxs-lookup"><span data-stu-id="1d06a-135">By default, this field contains the description of the service agreement that you selected on the previous page.</span></span>
    
      - <span data-ttu-id="1d06a-136">A **Felelős** mezőben válassza ki annak az alkalmazottnak az azonosítóját, aki felelős a szerződésért, illetve ha ismert, akkor adja meg annak a technikusnak az azonosítóját, akit az ügyfél előnyben részesít szervizhíváskor.</span><span class="sxs-lookup"><span data-stu-id="1d06a-136">In the **Responsible** field, select the ID of the employee who is responsible for the agreement, and if you know what it is, enter the ID of the customer's preferred technician for the service call.</span></span>
    
      - <span data-ttu-id="1d06a-137">A **Kapcsolattartó azonosítója** mezőben válassza ki azt a személyt a vevő vállalatánál, akivel kapcsolatba kell lépni a szervizrendeléssel kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="1d06a-137">In the **Contact ID** field, select the person in the customer's company who should be contacted regarding this service order.</span></span>

6.  <span data-ttu-id="1d06a-138">Válassza a **Következő\>** elemet, majd a **Befejezés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1d06a-138">Select **Next \>**, and then select **Finish**.</span></span>


## <a name="see-also"></a><span data-ttu-id="1d06a-139">Lásd még</span><span class="sxs-lookup"><span data-stu-id="1d06a-139">See also</span></span>

[<span data-ttu-id="1d06a-140">Szervizrendelések</span><span class="sxs-lookup"><span data-stu-id="1d06a-140">Service orders</span></span>](service-orders.md)

[<span data-ttu-id="1d06a-141">Szervizrendelések automatikus létrehozása</span><span class="sxs-lookup"><span data-stu-id="1d06a-141">Create service orders automatically</span></span>](create-service-orders-automatically.md)

<span data-ttu-id="1d06a-142">[Szervizrendelések létrehozása (osztályképernyő)](https://technet.microsoft.com/library/aa553901\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="1d06a-142">[Create service orders (class form)](https://technet.microsoft.com/library/aa553901\(v=ax.60\))</span></span> 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]