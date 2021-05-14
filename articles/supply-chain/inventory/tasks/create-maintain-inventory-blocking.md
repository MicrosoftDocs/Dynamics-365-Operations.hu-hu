---
title: Készletzárolás létrehozása és karbantartása
description: Ez az témakör azt mutatja be, hogyan használhat készletzárolást, amellyel megelőzheti a fizikai, aktuális készletek lefoglalását más kimenő forrásbizonylatokkal.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e9aa38ca52da577fff258bb330922ad7f4044330
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956158"
---
# <a name="create-and-maintain-an-inventory-blocking"></a><span data-ttu-id="1bf19-103">Készletzárolás létrehozása és karbantartása</span><span class="sxs-lookup"><span data-stu-id="1bf19-103">Create and maintain an inventory blocking</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1bf19-104">Ez az témakör azt mutatja be, hogyan használhat készletzárolást, amellyel megelőzheti a fizikai, aktuális készletek lefoglalását más kimenő forrásbizonylatokkal.</span><span class="sxs-lookup"><span data-stu-id="1bf19-104">This topic describes how to use an inventory blocking to prevent physical on-hand inventory from being reserved by other outbound source documents.</span></span> <span data-ttu-id="1bf19-105">A témakörben szereplő eljárások megkezdése előtt rendelkeznie kell egy olyan cikkel, amelyhez fizikai, aktuális készlet elérhető.</span><span class="sxs-lookup"><span data-stu-id="1bf19-105">Before you start the procedures in this topic, you must have an item that physical on-hand inventory is available for.</span></span>

## <a name="block-inventory"></a><span data-ttu-id="1bf19-106">Készletzárolás</span><span class="sxs-lookup"><span data-stu-id="1bf19-106">Block inventory</span></span>

<span data-ttu-id="1bf19-107">A következő lépésekkel lehet készletzárolási rekordot létrehozni a készlet zárolása érdekében.</span><span class="sxs-lookup"><span data-stu-id="1bf19-107">To create an inventory blocking record so that inventory is blocked, follow these steps.</span></span>

1. <span data-ttu-id="1bf19-108">Ugorjon a **Készletkezelés \> Időszakos feladatok \> Készletzárolás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1bf19-108">Go to **Inventory management \> Periodic tasks \> Inventory blocking**.</span></span>
1. <span data-ttu-id="1bf19-109">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="1bf19-109">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="1bf19-110">Az új zárolási rekord fejlécében állítsa a **Cikkszám** mezőt a blokkolni kívánt cikkre, és adjon meg egy leírást.</span><span class="sxs-lookup"><span data-stu-id="1bf19-110">On the header of the new blocking record, set the **Item number** field to the item that you want to block, and enter a description.</span></span>
1. <span data-ttu-id="1bf19-111">Az **Általános** gyorslapon a **Mennyiség** mezőben adja meg a zárolni kívánt cikkek számát.</span><span class="sxs-lookup"><span data-stu-id="1bf19-111">On the **General** FastTab, in the **Quantity** field, enter the number of items to block.</span></span>
1. <span data-ttu-id="1bf19-112">A **Készletdimenziók** gyorslapon adja meg azt a telephelyet és raktárt, ahol a blokkolni kívánt cikkek jelenleg találhatók.</span><span class="sxs-lookup"><span data-stu-id="1bf19-112">On the **Inventory dimensions** FastTab, specify the site and warehouse where the items that you want to block are currently located.</span></span>
1. <span data-ttu-id="1bf19-113">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1bf19-113">On the Action Pane, select **Save**.</span></span>

## <a name="update-the-conditions-of-the-inventory-blocking"></a><span data-ttu-id="1bf19-114">Készletzárolás feltételeinek frissítése</span><span class="sxs-lookup"><span data-stu-id="1bf19-114">Update the conditions of the inventory blocking</span></span>

<span data-ttu-id="1bf19-115">A következő lépésekkel frissítheti a készletzárolási rekordokat.</span><span class="sxs-lookup"><span data-stu-id="1bf19-115">To update an inventory blocking record, follow these steps.</span></span>

1. <span data-ttu-id="1bf19-116">Ugorjon a **Készletkezelés \> Időszakos feladatok \> Készletzárolás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1bf19-116">Go to **Inventory management \> Periodic tasks \> Inventory blocking**.</span></span>
1. <span data-ttu-id="1bf19-117">A lista ablaktáblán válassza ki a releváns zárolási rekordot.</span><span class="sxs-lookup"><span data-stu-id="1bf19-117">In the list pane, select the relevant blocking record.</span></span>
1. <span data-ttu-id="1bf19-118">Szerkessze a rekordot szükség szerint.</span><span class="sxs-lookup"><span data-stu-id="1bf19-118">Edit the record as required.</span></span> <span data-ttu-id="1bf19-119">Például a **Várható dátum** mező értékének módosításával érdemes jelezni, hogy a zárolt készlet a tervek szerint mikor foglalható újra.</span><span class="sxs-lookup"><span data-stu-id="1bf19-119">For example, you might change the value of the **Expected date** field to indicate when the blocked inventory is expected to become available for reservation.</span></span> <span data-ttu-id="1bf19-120">Ha a **Várt bevételezések** beállítás van kiválasztva, a dátum megjelenik a várható tranzakcióban.</span><span class="sxs-lookup"><span data-stu-id="1bf19-120">If the **Expected receipts** option is selected, the date will appear on the expected transaction.</span></span> <span data-ttu-id="1bf19-121">(A **Várt bevételezések** beállítását alapértelmezés szerint a zárolási rekord manuális létrehozása esetén választja ki a program.)</span><span class="sxs-lookup"><span data-stu-id="1bf19-121">(The **Expected receipts** option is selected by default when you manually create a blocking record.)</span></span>
1. <span data-ttu-id="1bf19-122">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1bf19-122">On the Action Pane, select **Save**.</span></span>

## <a name="unblock-inventory"></a><span data-ttu-id="1bf19-123">Készletzárolás feloldása</span><span class="sxs-lookup"><span data-stu-id="1bf19-123">Unblock inventory</span></span>

<span data-ttu-id="1bf19-124">A következő lépésekkel lehet készletzárolási rekordot eltávolítani a készlet zárolásának feloldása érdekében.</span><span class="sxs-lookup"><span data-stu-id="1bf19-124">To remove an inventory blocking record so that inventory is unblocked, follow these steps.</span></span>

1. <span data-ttu-id="1bf19-125">Ugorjon a **Készletkezelés \> Időszakos feladatok \> Készletzárolás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1bf19-125">Go to **Inventory management \> Periodic tasks \> Inventory blocking**.</span></span>
1. <span data-ttu-id="1bf19-126">A lista ablaktáblán válassza ki a releváns zárolási rekordot.</span><span class="sxs-lookup"><span data-stu-id="1bf19-126">In the list pane, select the relevant blocking record.</span></span>
1. <span data-ttu-id="1bf19-127">A Műveletpanelen válassza ezután a **Törlés** elemet.</span><span class="sxs-lookup"><span data-stu-id="1bf19-127">On the Action Pane, select **Delete**.</span></span>
1. <span data-ttu-id="1bf19-128">A rendszer felszólítja, hogy erősítse meg a műveletet.</span><span class="sxs-lookup"><span data-stu-id="1bf19-128">You're prompted to confirm the operation.</span></span> <span data-ttu-id="1bf19-129">A folytatáshoz kattintson az **Igen** gombra.</span><span class="sxs-lookup"><span data-stu-id="1bf19-129">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="1bf19-130">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1bf19-130">Close the page.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
