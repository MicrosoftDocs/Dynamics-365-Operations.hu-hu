---
title: Készletzárolás létrehozása és karbantartása
description: Ez az eljárás azt mutatja, hogyan előzheti meg a fizikai, aktuális készletek lefoglalását más kimenő forrásbizonylatokkal a készletzárolás segítségével.
author: perlynne
manager: tfehr
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e76c3d1f46e31dcd2171682a629dabe5bf5db418
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204148"
---
# <a name="create-and-maintain-an-inventory-blocking"></a><span data-ttu-id="4e7c3-103">Készletzárolás létrehozása és karbantartása</span><span class="sxs-lookup"><span data-stu-id="4e7c3-103">Create and maintain an inventory blocking</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4e7c3-104">Ez az eljárás azt mutatja, hogyan előzheti meg a fizikai, aktuális készletek lefoglalását más kimenő forrásbizonylatokkal a készletzárolás segítségével.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-104">This procedure shows how to prevent physical on-hand inventory from being reserved by other outbound source documents by using the inventory blocking.</span></span> <span data-ttu-id="4e7c3-105">Ezt az eljárást az USMF bemutató vállalatban is futtathatja a megjelenített példákat használva.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-105">You can run the procedure in demo data company USMF using the example values that are shown.</span></span> <span data-ttu-id="4e7c3-106">Az eljárás megkezdése előtt rendelkeznie kell egy fizikai, aktuális készletű cikkel.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-106">You need to have an item with physical on-hand inventory available before you start this procedure.</span></span>


## <a name="create-an-inventory-blocking"></a><span data-ttu-id="4e7c3-107">Készletzárolás létrehozása</span><span class="sxs-lookup"><span data-stu-id="4e7c3-107">Create an inventory blocking</span></span>
1. <span data-ttu-id="4e7c3-108">A **Navigációs ablaktáblán** lépjen a **Modulok > Készletgazdálkodás > Időszakos feladatok > Minőségkezelés > Készletzárolás** részre.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-108">In the **Navigation pane**, go to **Modules > Inventory management > Periodic tasks > Inventory blocking**.</span></span>
2. <span data-ttu-id="4e7c3-109">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-109">Click **New**.</span></span>
3. <span data-ttu-id="4e7c3-110">A **Cikkszám** mezőben kattintson a legördülő gombra a keresés megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-110">In the **Item number** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="4e7c3-111">A listából válassza ki a használni kívánt cikket.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-111">In the list, select the item you want to choose.</span></span> <span data-ttu-id="4e7c3-112">Válasszon ki egy blokkolni kívánt cikkszámot fizikai aktuális készlettel.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-112">Select an item number with physical on-hand inventory that you want to block.</span></span> <span data-ttu-id="4e7c3-113">Az USMF használata esetén választhatja a „M9201” cikket.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-113">If you're using USMF you can select item M9201.</span></span>  
5. <span data-ttu-id="4e7c3-114">Adjon meg egy számot a **Mennyiség** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-114">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="4e7c3-115">Az M9201 használata esetén kevesebb, mint 200-at kell választania.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-115">If you're using item M9201, you need to select less than 200.</span></span>
6. <span data-ttu-id="4e7c3-116">Bontsa ki a **Készletdimenziók** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-116">Expand the **Inventory dimensions** fastTab.</span></span>
7. <span data-ttu-id="4e7c3-117">A **Raktár** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-117">In the **Warehouse** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="4e7c3-118">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-118">In the list, find and select the desired record.</span></span> <span data-ttu-id="4e7c3-119">Az M9201 használata esetén kiválaszthatja az 51. raktárat.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-119">If you're using item M9201, you can select warehouse 51.</span></span>  
9. <span data-ttu-id="4e7c3-120">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-120">Click **Save**.</span></span>

## <a name="update-the-conditions-of-the-inventory-blocking"></a><span data-ttu-id="4e7c3-121">Készletzárolás feltételeinek frissítése</span><span class="sxs-lookup"><span data-stu-id="4e7c3-121">Update the conditions of the inventory blocking</span></span>
1. <span data-ttu-id="4e7c3-122">Írjon be egy számot az **Általános** gyorslap **Mennyiség** mezőjébe.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-122">In the **General** fastTab, in the **Quantity** field, enter a number.</span></span> <span data-ttu-id="4e7c3-123">Frissítse a készletmennyiség mezőt, hogy megfeleljen a blokkolni kívánt mennyiségnek.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-123">Update the inventory quantity field to reflect the quantity to block.</span></span>  
2. <span data-ttu-id="4e7c3-124">Adjon meg egy dátumot a **Várható dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-124">In the **Expected date** field, enter a date.</span></span> <span data-ttu-id="4e7c3-125">A várható dátum megadásával érdemes jelezni, hogy a blokkolt készlet a tervek szerint mikor foglalható újra.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-125">You might want to indicate when the blocked inventory is expected to become available for reservation by assigning an expected date.</span></span> <span data-ttu-id="4e7c3-126">Ha a Várt bevételezések lehetőség van kiválasztva a készletzároláshoz, mint ahogy az alapértelmezett esetben a blokkolás létrehozásakor történik, ez a dátum jelenik meg a várható tranzakción.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-126">If the Expected receipts option is selected for the inventory blocking, as it is by default when you manually create a blocking, this date will appear on the expected transaction.</span></span>  
3. <span data-ttu-id="4e7c3-127">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-127">Click **Save**.</span></span>

## <a name="remove-the-inventory-blocking"></a><span data-ttu-id="4e7c3-128">Készletzárolás megszüntetése</span><span class="sxs-lookup"><span data-stu-id="4e7c3-128">Remove the inventory blocking</span></span>
1. <span data-ttu-id="4e7c3-129">A **Művelet panelen** kattintson a **Törlés** elemre.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-129">On the **Action pane**, click **Delete**.</span></span>
2. <span data-ttu-id="4e7c3-130">Kattintson az **Igen** gombra.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-130">Click **Yes**.</span></span>
3. <span data-ttu-id="4e7c3-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-131">Close the page.</span></span>

