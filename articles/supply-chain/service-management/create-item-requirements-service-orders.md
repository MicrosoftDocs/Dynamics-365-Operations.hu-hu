---
title: Cikkszükséglet létrehozása szervizrendelésekhez
description: A szolgáltatási rendelésekhez létrehozhat cikkszükségleteket, ha a szervizrendelésekhez konkrét cikkekre van szüksége.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 650d02d2160757d9629e4deb1e9217c85e9d01df
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831626"
---
# <a name="create-item-requirements-for-service-orders"></a><span data-ttu-id="dc368-103">Cikkszükséglet létrehozása szervizrendelésekhez</span><span class="sxs-lookup"><span data-stu-id="dc368-103">Create item requirements for service orders</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="dc368-104">Létrehozhat egy szervizrendelést a vevőknek nyújtott szolgáltatások kezelésére és nyomon követésére.</span><span class="sxs-lookup"><span data-stu-id="dc368-104">You can create a service order to track and manage services that you provide to your customers.</span></span> <span data-ttu-id="dc368-105">A szolgáltatási rendelésekhez létrehozhat cikkszükségleteket, ha a szervizrendelésekhez konkrét cikkekre van szüksége.</span><span class="sxs-lookup"><span data-stu-id="dc368-105">If you need to reserve specific items for a service order, you can create inventory item requirements for it.</span></span> <span data-ttu-id="dc368-106">Egy cikkszükséglet azonnali felhasználása történhet közvetlenül a készletből, vagy kezdeményezhető termelési megrendelés az adott cikkre.</span><span class="sxs-lookup"><span data-stu-id="dc368-106">An item requirement can be immediately consumed from inventory, or it can initiate a production order for the item.</span></span>

<span data-ttu-id="dc368-107">Ha cikktranzakció helyett cikkszükségletet használ, közvetlenül a cikk tényleges felhasználása előttre tervezheti a szállítást, beszerzési rendelést hozhat létre, a cikket szerepeltetheti a kereskedelmi megállapodási keretrendszerben, és a cikkszükségletet szerepeltetheti a gyártástervezésben.</span><span class="sxs-lookup"><span data-stu-id="dc368-107">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span>

<span data-ttu-id="dc368-108">Szervizrendelések cikkszükségleteinek feldolgozása projekten keresztül történik.</span><span class="sxs-lookup"><span data-stu-id="dc368-108">Item requirements for service orders are processed through a project.</span></span> <span data-ttu-id="dc368-109">Egy cikkszükséglet szervizrendelésben való létrehozásához szükséges, hogy a szervizrendelés egy kapcsolódó projekthez társuljon.</span><span class="sxs-lookup"><span data-stu-id="dc368-109">To create an item requirement on a service order, the service order must be assigned to a project.</span></span> <span data-ttu-id="dc368-110">Miután létrehozta a cikkszükségletet egy szervizrendeléshez, a cikkszükséglet megtekintheti a kiválasztott projekthez kapcsolódó **Projektek** képernyőn.</span><span class="sxs-lookup"><span data-stu-id="dc368-110">After you create an item requirement for a service order, you can view the item requirement in the **Projects** form for the selected project.</span></span>

## <a name="create-an-item-requirement-for-a-service-order"></a><span data-ttu-id="dc368-111">Cikkszükséglet létrehozása szervizrendeléshez</span><span class="sxs-lookup"><span data-stu-id="dc368-111">Create an item requirement for a service order</span></span>

1.  <span data-ttu-id="dc368-112">Kattintson a következőkre: **Szolgáltatáskezelés** \> **Közös** \> **Szervizrendelések** \> **Szervizrendelések**.</span><span class="sxs-lookup"><span data-stu-id="dc368-112">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="dc368-113">Válassza ki azt a szervizrendelést, amelyhez cikkszükségletet szeretne létrehozni.</span><span class="sxs-lookup"><span data-stu-id="dc368-113">Select the service order that you want to create an item requirement for.</span></span>

3.  <span data-ttu-id="dc368-114">A **Műveleti ablaktábla** **Elküldés lapján** kattintson a **Cikkszükséglet** elemre.</span><span class="sxs-lookup"><span data-stu-id="dc368-114">On the **Action Pane**, on the **Dispatch** tab, click **Item requirement**.</span></span>

4.  <span data-ttu-id="dc368-115">A **Cikkszükséglet** képernyőn írja be a kívánt cikkre vonatkozó megfelelő adatokat.</span><span class="sxs-lookup"><span data-stu-id="dc368-115">In the **Item requirements** form, enter information for the required item.</span></span> <span data-ttu-id="dc368-116">További információk az adott mezőkről: [Cikkszükséglet (képernyő)](https://technet.microsoft.com/library/aa552021\(v=ax.60\))..</span><span class="sxs-lookup"><span data-stu-id="dc368-116">For more information about the specific fields, see [Item requirements (form)](https://technet.microsoft.com/library/aa552021\(v=ax.60\)).</span></span>

## <a name="create-an-item-requirement-for-a-service-agreement"></a><span data-ttu-id="dc368-117">Cikkszükséglet létrehozása szolgáltatási szerződéshez</span><span class="sxs-lookup"><span data-stu-id="dc368-117">Create an item requirement for a service agreement</span></span>

1.  <span data-ttu-id="dc368-118">Kattintson a **Szolgáltatáskezelés** \> **Közös** \> **Szolgáltatási szerződések** \> **Szolgáltatási szerződések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dc368-118">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="dc368-119">Nyissa meg azt a szolgáltatási szerződést, amelyhez cikkszükségletet szeretne létrehozni.</span><span class="sxs-lookup"><span data-stu-id="dc368-119">Open the service agreement for which you want to create an item requirement.</span></span>

3.  <span data-ttu-id="dc368-120">A **Sorok** gyorslapon kattintson a **Hozzáadás** lehetőségre egy új sor létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="dc368-120">On the **Lines** FastTab, click **Add** to create a new line.</span></span>

4.  <span data-ttu-id="dc368-121">Válassza ki a **Cikk** elemet a **Tranzakció típusa** mezőben.</span><span class="sxs-lookup"><span data-stu-id="dc368-121">In the **Transaction type** field, select **Item**.</span></span>

5.  <span data-ttu-id="dc368-122">A **Cikk beállítása** mezőben válassza ki a **Cikkszükséglet** elemet.</span><span class="sxs-lookup"><span data-stu-id="dc368-122">In the **Item setup** field, select **Item requirement**.</span></span>

6.  <span data-ttu-id="dc368-123">A **Cikkszám** mezőben válassza ki a szolgáltatási szerződéshez szükséges cikket.</span><span class="sxs-lookup"><span data-stu-id="dc368-123">In the **Item number** field, select the item that is required for the service agreement.</span></span>

7.  <span data-ttu-id="dc368-124">A **Sor adatai** gyorslapon, a **Termékdimenziók** lapon a **Hely** mezőben válassza ki a cikkhez tartozó a készlethelyet.</span><span class="sxs-lookup"><span data-stu-id="dc368-124">On the **Line details** FastTab, on the **Product dimensions** tab, in the **Site** field, select the inventory site for the item.</span></span>

8.  <span data-ttu-id="dc368-125">A szolgáltatásiszerződés-sorból szervizrendelés létrehozásához a **Sorok** gyorslapon kattintson a **Szervizrendelések létrehozása** elemre, majd a **Szervizrendelések létrehozása** képernyőn adja meg a lényeges adatokat.</span><span class="sxs-lookup"><span data-stu-id="dc368-125">To create a service order from the agreement line, on the **Lines** FastTab, click **Create service orders**, and then enter the relevant information in the **Create service orders** form.</span></span> 


## <a name="see-also"></a><span data-ttu-id="dc368-126">Lásd még</span><span class="sxs-lookup"><span data-stu-id="dc368-126">See also</span></span>

<span data-ttu-id="dc368-127">[Szervizrendelések automatikus létrehozása](create-service-orders-automatically.md).</span><span class="sxs-lookup"><span data-stu-id="dc368-127">[Create service orders automatically](create-service-orders-automatically.md).</span></span>

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]