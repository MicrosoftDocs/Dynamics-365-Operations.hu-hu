---
title: Szervizrendelési cikkre vonatkozó követelmények
description: A szolgáltatási rendelésekhez létrehozhat cikkszükségleteket, ha a szervizrendelésekhez konkrét cikkekre van szüksége.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjSalesItemReq
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3dc7c721af4b25e1586e546392518648110a3fb6
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562300"
---
# <a name="service-order-item-requirements"></a><span data-ttu-id="e3135-103">Szervizrendelési cikkre vonatkozó követelmények</span><span class="sxs-lookup"><span data-stu-id="e3135-103">Service order item requirements</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="e3135-104">Létrehozhat egy szervizrendelést a vevőknek nyújtott szolgáltatások kezelésére és nyomon követésére.</span><span class="sxs-lookup"><span data-stu-id="e3135-104">You can create a service order to track and manage services that you provide to your customers.</span></span> <span data-ttu-id="e3135-105">A szolgáltatási rendelésekhez létrehozhat cikkszükségleteket, ha a szervizrendelésekhez konkrét cikkekre van szüksége.</span><span class="sxs-lookup"><span data-stu-id="e3135-105">If you need to reserve specific items for a service order, you can create inventory item requirements for it.</span></span> <span data-ttu-id="e3135-106">Egy cikkszükséglet azonnali felhasználása történhet közvetlenül a készletből, vagy kezdeményezhető termelési megrendelés az adott cikkre.</span><span class="sxs-lookup"><span data-stu-id="e3135-106">An item requirement can be immediately consumed from inventory, or it can initiate a production order for the item.</span></span>

<span data-ttu-id="e3135-107">Ha cikktranzakció helyett cikkszükségletet használ, közvetlenül a cikk tényleges felhasználása előttre tervezheti a szállítást, beszerzési rendelést hozhat létre, a cikket szerepeltetheti a kereskedelmi megállapodási keretrendszerben, és a cikkszükségletet szerepeltetheti a gyártástervezésben.</span><span class="sxs-lookup"><span data-stu-id="e3135-107">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span>

<span data-ttu-id="e3135-108">Szervizrendelések cikkszükségleteinek feldolgozása projekten keresztül történik.</span><span class="sxs-lookup"><span data-stu-id="e3135-108">Item requirements for service orders are processed through a project.</span></span> <span data-ttu-id="e3135-109">Egy cikkszükséglet szervizrendelésben való létrehozásához a szervizrendelésnek projekthez kell kapcsolódnia.</span><span class="sxs-lookup"><span data-stu-id="e3135-109">To create an item requirement on a service order, the service order must be attached to a project.</span></span>

<span data-ttu-id="e3135-110">Amikor már létre van hozva cikkszükséglet egy szervizrendeléshez, az megtekinthető az adott szervizrendelés **Projekt** lapjáról, illetve az **Értékesítési rendelés** képernyőn keresztül.</span><span class="sxs-lookup"><span data-stu-id="e3135-110">As soon as an item requirement is created for a service order, it can be viewed from **Project** in the individual service order or through the **Sales order** form.</span></span>

## <a name="view-an-item-requirement-from-a-service-order"></a><span data-ttu-id="e3135-111">Szervizrendelés cikkszükségletének megtekintése</span><span class="sxs-lookup"><span data-stu-id="e3135-111">View an item requirement from a service order</span></span>

1.  <span data-ttu-id="e3135-112">Kattintson a következőkre: **Szolgáltatáskezelés** \> **Közös** \> **Szervizrendelések** \> **Szervizrendelések**.</span><span class="sxs-lookup"><span data-stu-id="e3135-112">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="e3135-113">Kattintson az **Elküldés**, és kattintson a **Cikkszükséglet** elemre a **Cikkszükségletek** képernyő megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e3135-113">Click **Dispatch**, and then click **Item requirement** to open the **Item requirements** form.</span></span>

3.  <span data-ttu-id="e3135-114">Kattintson a **Projekt** lapra és ellenőrizze a **Szervizrendelés** mezőt a cikkszükséglethez tartozó szervizrendelések megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="e3135-114">Click the **Project** tab, and check the **Service order** field to see the service orders of the item requirement.</span></span>

## <a name="delete-service-orders-with-item-requirements"></a><span data-ttu-id="e3135-115">Cikkszükségletekkel rendelkező szervizrendelések törlése</span><span class="sxs-lookup"><span data-stu-id="e3135-115">Delete service orders with item requirements</span></span>

<span data-ttu-id="e3135-116">Ha egy szervizrendelésen cikkszükséglet van létrehozva, a szervizrendelést nem tudja törölni.</span><span class="sxs-lookup"><span data-stu-id="e3135-116">If an item requirement is created on a service order, you cannot delete the service order.</span></span> <span data-ttu-id="e3135-117">Törölnie kell a cikkszükségletet mielőtt a szervizrendelést törölni tudja.</span><span class="sxs-lookup"><span data-stu-id="e3135-117">You must delete the item requirement before you can delete the service order.</span></span>

1.  <span data-ttu-id="e3135-118">Kattintson a következőkre: **Szolgáltatáskezelés** \> **Közös** \> **Szervizrendelések** \> **Szervizrendelések**.</span><span class="sxs-lookup"><span data-stu-id="e3135-118">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="e3135-119">Kattintson az **Elküldés**, és kattintson a **Cikkszükséglet** elemre a **Cikkszükségletek** képernyő megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e3135-119">Click **Dispatch**, and then click **Item requirement** to open the **Item requirements** form.</span></span> <span data-ttu-id="e3135-120">A képernyő a szervizrendelésen létrehozott cikkszükségleteket tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="e3135-120">This form lists the item requirements that are created on the service order.</span></span>

3.  <span data-ttu-id="e3135-121">Válassza ki a törölni kívánt cikkszükségletet, majd kattintson a **Törlés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e3135-121">Select the item requirement to delete, and then click **Delete**.</span></span>

<span data-ttu-id="e3135-122">– vagy –</span><span class="sxs-lookup"><span data-stu-id="e3135-122">–or–</span></span>

1.  <span data-ttu-id="e3135-123">Kattintson a következőkre: **Projektvezetés és könyvelés** \> **Közös** \> **Projektek** \> **Minden projekt**.</span><span class="sxs-lookup"><span data-stu-id="e3135-123">Click **Project management and accounting** \> **Common** \> **Projects** \> **All projects**.</span></span>

2.  <span data-ttu-id="e3135-124">Nyissa meg az azt a szervizrendelést tartalmazó projektet, amelyen a cikkszükséglet létrehozása történik.</span><span class="sxs-lookup"><span data-stu-id="e3135-124">Open the project that has the service order in which an item requirement is created.</span></span>

3.  <span data-ttu-id="e3135-125">A **Projektek** képernyőn a jobb oldali ablakban kattintson a **Cikkszükségletek** elemre.</span><span class="sxs-lookup"><span data-stu-id="e3135-125">In the **Projects** form, in the right pane, click **Item requirements**.</span></span> <span data-ttu-id="e3135-126">Megnyílik a **Cikkszükségletek** képernyő, és tartalmazza a kijelölt projekthez társított cikkszükségletek listáját.</span><span class="sxs-lookup"><span data-stu-id="e3135-126">The **Item requirements** form lists the item requirements that are associated with the selected project.</span></span>

4.  <span data-ttu-id="e3135-127">Válassza ki a törölni kívánt cikkszükségletet, majd kattintson a **Törlés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e3135-127">Select the item requirement to delete, and then click **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3135-128">Lásd még</span><span class="sxs-lookup"><span data-stu-id="e3135-128">See also</span></span>

<span data-ttu-id="e3135-129">[Cikkszükséglet (képernyő)](https://technet.microsoft.com/en-us/library/aa552021\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="e3135-129">[Item requirements (form)](https://technet.microsoft.com/en-us/library/aa552021\(v=ax.60\))</span></span>

