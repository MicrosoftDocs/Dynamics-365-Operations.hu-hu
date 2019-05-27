---
title: Szervizrendelések létrehozása manuálisan
description: Szervizrendeléseket a szolgáltatási szerződésből vagy a **Szervizrendelések** képernyőn lehet manuálisan létrehozni.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9fbcdaa50a8f13247c13c1885cdb4ab7f5f39a47
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1552230"
---
# <a name="create-service-orders-manually"></a><span data-ttu-id="40323-103">Szervizrendelések létrehozása manuálisan</span><span class="sxs-lookup"><span data-stu-id="40323-103">Create service orders manually</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="40323-104">Szervizrendeléseket a szolgáltatási szerződésből vagy a **Szervizrendelések** képernyőn lehet manuálisan létrehozni.</span><span class="sxs-lookup"><span data-stu-id="40323-104">You can create service orders manually by using a service agreement or by using the **Service orders** form.</span></span> <span data-ttu-id="40323-105">Projektekből is létre lehet hozni szervizrendelést.</span><span class="sxs-lookup"><span data-stu-id="40323-105">You can also create a service order from a project.</span></span>

> [!TIP]
> <P><span data-ttu-id="40323-106">Automatizált folyamatok segítségével hozhat létre szervizrendeléseket.</span><span class="sxs-lookup"><span data-stu-id="40323-106">You can use automated processes to create service orders.</span></span> 

## <a name="create-a-service-order-manually-from-a-service-agreement"></a><span data-ttu-id="40323-107">Szervizrendelés manuális létrehozása egy szolgáltatási szerződésből</span><span class="sxs-lookup"><span data-stu-id="40323-107">Create a service order manually from a service agreement</span></span>

1.  <span data-ttu-id="40323-108">Kattintson a **Szolgáltatáskezelés** \> **Közös** \> **Szolgáltatási szerződések** \> **Szolgáltatási szerződések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="40323-108">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="40323-109">Válasszon ki egy szolgáltatási szerződést, vagy hozzon létre egy új szolgáltatási szerződést.</span><span class="sxs-lookup"><span data-stu-id="40323-109">Select a service agreement or create a new service agreement.</span></span>

3.  <span data-ttu-id="40323-110">Kattintson a **Szállítás** lapra, és a **Létrehozás** csoportban kattintson a **Tervezett szervizrendelések** lehetőségre a **Szervizrendelések létrehozása** képernyő megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="40323-110">Click the **Deliver** tab and in the **Create** group click **Planned service orders** to open the **Create service orders** form.</span></span>

## <a name="create-a-service-order-manually-in-the-service-orders-form"></a><span data-ttu-id="40323-111">Szervizrendelés manuális létrehozása a Szervizrendelések képernyőn</span><span class="sxs-lookup"><span data-stu-id="40323-111">Create a service order manually in the Service orders form</span></span>

1.  <span data-ttu-id="40323-112">Kattintson a következőkre: **Szolgáltatáskezelés** \> **Közös** \> **Szervizrendelések** \> **Szervizrendelések**.</span><span class="sxs-lookup"><span data-stu-id="40323-112">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="40323-113">Nyomja le a CTRL+N billentyűkombinációt új szervizrendelés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="40323-113">Press Ctrl+N to create a new service order.</span></span>

3.  <span data-ttu-id="40323-114">Hozza létre a szervizrendelés szervizrendeléssorait.</span><span class="sxs-lookup"><span data-stu-id="40323-114">Create service order lines for the service order.</span></span>

> [!NOTE]
> <P><span data-ttu-id="40323-115">Ha a <STRONG>Szolgáltatáskezelés paraméterei</STRONG> képernyő <STRONG>Engedélyezés szolgáltatási szerződés nélkül</STRONG> jelölőnégyzete be van jelölve, akkor a szervizrendeléssorok tranzakcióit fel lehet adni anélkül, hogy szolgáltatási szerződéshez társítaná a szervizrendelést.</span><span class="sxs-lookup"><span data-stu-id="40323-115">If the <STRONG>Allow without service agreement</STRONG> check box in the <STRONG>Service management parameters</STRONG> form is selected, you can post the transactions from the service order lines without attaching the service order to a service agreement.</span></span> <span data-ttu-id="40323-116">Ha nincs bejelölve a jelölőnégyzet, akkor a kézzel létrehozott szervizrendelést társítani kell a projekthez a szervizrendeléssorok feladása előtt.</span><span class="sxs-lookup"><span data-stu-id="40323-116">If the check box is cleared, you must attach the manually created service order to a project before posting the service order lines.</span></span></P>

## <a name="create-a-service-order-from-a-project"></a><span data-ttu-id="40323-117">Szervizrendelés létrehozása egy projektből</span><span class="sxs-lookup"><span data-stu-id="40323-117">Create a service order from a project</span></span>

1.  <span data-ttu-id="40323-118">Kattintson a következőkre: **Projektvezetés és könyvelés** \> **Közös** \> **Projektek** \> **Minden projekt**.</span><span class="sxs-lookup"><span data-stu-id="40323-118">Click **Project management and accounting** \> **Common** \> **Projects** \> **All projects**.</span></span>

2.  <span data-ttu-id="40323-119">A **Projektek** képernyőn, a **Műveleti ablakban**, kattintson a **Kezelés** lapra \> kattintson **Szolgáltatás** \>**Szervizrendelések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="40323-119">In the **Projects** form, on the **Action pane**, click the **Manage** tab \> click **Service** \> **Service orders**.</span></span>

3.  <span data-ttu-id="40323-120">Az előbbi eljárás segítségével hozza létre manuálisan a szervizrendelést a **Szervizrendelések** képernyőn.</span><span class="sxs-lookup"><span data-stu-id="40323-120">Follow the previous procedure to create a service order manually in the **Service orders** form.</span></span> <span data-ttu-id="40323-121">A **Projekt azonosító** mezőben látható a projektreferencia.</span><span class="sxs-lookup"><span data-stu-id="40323-121">The **Project ID** field displays the project reference.</span></span>

> [!NOTE]
> <P><span data-ttu-id="40323-122">Ha a <STRONG>Szolgáltatáskezelés paraméterei</STRONG> képernyő <STRONG>Engedélyezés szolgáltatási szerződés nélkül</STRONG> jelölőnégyzete be van jelölve, akkor a szervizrendeléssorok tranzakcióit fel lehet adni anélkül, hogy szolgáltatási szerződéshez társítaná a szervizrendelést.</span><span class="sxs-lookup"><span data-stu-id="40323-122">If the <STRONG>Allow without service agreement</STRONG> check box in the <STRONG>Service management parameters</STRONG> form is selected, you can post the transactions from the service order lines without attaching the service order to a service agreement.</span></span> <span data-ttu-id="40323-123">Ha nincs bejelölve a jelölőnégyzet, akkor a kézzel létrehozott szervizrendelést társítani kell a projekthez a szervizrendeléssorok feladása előtt.</span><span class="sxs-lookup"><span data-stu-id="40323-123">If the check box is cleared, you must attach the manually created service order to a project before posting the service order lines.</span></span></P>

## <a name="create-a-service-order-from-the-sales-order-form"></a><span data-ttu-id="40323-124">Szervizrendelés létrehozása az értékesítési rendelés képernyőn</span><span class="sxs-lookup"><span data-stu-id="40323-124">Create a service order from the Sales order form</span></span>

<span data-ttu-id="40323-125">Szervizrendelést az **Értékesítési rendelések** képernyő használatával is létrehozhat; ehhez használja az **Új szervizrendelés létrehozása az értékesítési rendelés alapján** varázslót.</span><span class="sxs-lookup"><span data-stu-id="40323-125">You can create a service order from the **Sales orders** form by using the **Create a new service order based on the sales order** wizard.</span></span>

1.  <span data-ttu-id="40323-126">Kattintson ide: **Értékesítés és marketing** \> **Közös** \> **Értékesítési rendelések** \> **Minden értékesítési rendelés**.</span><span class="sxs-lookup"><span data-stu-id="40323-126">Click **Sales and marketing** \> **Common** \> **Sales orders** \> **All sales orders**.</span></span>

2.  <span data-ttu-id="40323-127">Nyissa meg a megfelelő értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="40323-127">Open the relevant sales order.</span></span>

3.  <span data-ttu-id="40323-128">Az **Értékesítési rendelés** fülön kattintson a **Szervizrendelés** lehetőségre ahhoz, hogy elindítsa az **Új szervizrendelés létrehozása az értékesítési rendelés alapján varázslót**.</span><span class="sxs-lookup"><span data-stu-id="40323-128">On the **Sales order** tab, click **Service order** to start the **Create a new service order based on the sales order** wizard.</span></span>

4.  <span data-ttu-id="40323-129">Kattintson a **Tovább \>** gombra, majd végezze el a következő lépéseket a **Válassza ki a szerződést a szervizrendeléshez** lapon:</span><span class="sxs-lookup"><span data-stu-id="40323-129">Click **Next \>**, and then complete the following steps on the **Select agreement for service order** page:</span></span>
    
      - <span data-ttu-id="40323-130">A **Szolgáltatási szerződés** mezőben válassza ki azt a szolgáltatási szerződést, amelyhez az új szervizrendelést társítani kívánja.</span><span class="sxs-lookup"><span data-stu-id="40323-130">Use the **Service agreement** field to select the service agreement with which the new service order should be associated.</span></span>
    
      - <span data-ttu-id="40323-131">Nem kötelező: A **Projektazonosító** mező segítségével egy projekthez társíthatja a szervizrendelést.</span><span class="sxs-lookup"><span data-stu-id="40323-131">Optional: Use the **Project ID** field to associate this service order with a particular project.</span></span>

5.  <span data-ttu-id="40323-132">Kattintson a **Tovább \>** gombra, majd végezze el a következő lépéseket a **Szervizrendelés létrehozása** lapon:</span><span class="sxs-lookup"><span data-stu-id="40323-132">Click **Next \>**, and then complete the following steps on the **Create service order** page:</span></span>
    
      - <span data-ttu-id="40323-133">Adja meg a szervizhívás indításának dátumát és időpontját a **Preferált szolgáltatási idő** mezőben.</span><span class="sxs-lookup"><span data-stu-id="40323-133">Enter a date and time for the service call to begin in the **Preferred service time** field.</span></span>
    
      - <span data-ttu-id="40323-134">Nem kötelező. módosítsa a **Leírás** mezőben szereplő szöveget.</span><span class="sxs-lookup"><span data-stu-id="40323-134">Optional: Modify the text in the **Description** field.</span></span> <span data-ttu-id="40323-135">Alapértelmezés szerint ez a mező tartalmazza az előző lapon kiválasztott szolgáltatási szerződés leírását.</span><span class="sxs-lookup"><span data-stu-id="40323-135">By default, this field contains the description of the service agreement that you selected on the previous page.</span></span>
    
      - <span data-ttu-id="40323-136">A **Felelős** mezőben válassza ki annak az alkalmazottnak az azonosítóját, aki felelős a szerződésért, illetve ha ismert, akkor adja meg annak a technikusnak az azonosítóját, akit az ügyfél előnyben részesít szervizhíváskor.</span><span class="sxs-lookup"><span data-stu-id="40323-136">In the **Responsible** field, select the ID of the employee who is responsible for the agreement, and if you know what it is, enter the ID of the customer's preferred technician for the service call.</span></span>
    
      - <span data-ttu-id="40323-137">A **Kapcsolattartó azonosítója** mezőben válassza ki azt a személyt a vevő vállalatánál, akivel kapcsolatba kell lépni a szervizrendeléssel kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="40323-137">In the **Contact ID** field, select the person in the customer's company who should be contacted regarding this service order.</span></span>

6.  <span data-ttu-id="40323-138">Kattintson a **Új\>** gombra, majd a **Befejezés** gombra.</span><span class="sxs-lookup"><span data-stu-id="40323-138">Click **Next \>**, and then click **Finish**.</span></span>


## <a name="see-also"></a><span data-ttu-id="40323-139">Lásd még</span><span class="sxs-lookup"><span data-stu-id="40323-139">See also</span></span>

[<span data-ttu-id="40323-140">Szervizrendelések</span><span class="sxs-lookup"><span data-stu-id="40323-140">Service orders</span></span>](service-orders.md)

[<span data-ttu-id="40323-141">Szervizrendelések automatikus létrehozása</span><span class="sxs-lookup"><span data-stu-id="40323-141">Create service orders automatically</span></span>](create-service-orders-automatically.md)

<span data-ttu-id="40323-142">[Szervizrendelések létrehozása (osztályképernyő)](https://technet.microsoft.com/en-us/library/aa553901\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="40323-142">[Create service orders (class form)](https://technet.microsoft.com/en-us/library/aa553901\(v=ax.60\))</span></span> 

