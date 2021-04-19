---
title: Készletzárolás létrehozása és karbantartása
description: Ez az eljárás azt mutatja, hogyan előzheti meg a fizikai, aktuális készletek lefoglalását más kimenő forrásbizonylatokkal a készletzárolás segítségével.
author: perlynne
ms.date: 08/08/2019
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
ms.openlocfilehash: 319ae6da1e0e504316b2d96001d582e835cef20c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834001"
---
# <a name="create-and-maintain-an-inventory-blocking"></a><span data-ttu-id="9efef-103">Készletzárolás létrehozása és karbantartása</span><span class="sxs-lookup"><span data-stu-id="9efef-103">Create and maintain an inventory blocking</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9efef-104">Ez az eljárás azt mutatja, hogyan előzheti meg a fizikai, aktuális készletek lefoglalását más kimenő forrásbizonylatokkal a készletzárolás segítségével.</span><span class="sxs-lookup"><span data-stu-id="9efef-104">This procedure shows how to prevent physical on-hand inventory from being reserved by other outbound source documents by using the inventory blocking.</span></span> <span data-ttu-id="9efef-105">Ezt az eljárást az USMF bemutató vállalatban is futtathatja a megjelenített példákat használva.</span><span class="sxs-lookup"><span data-stu-id="9efef-105">You can run the procedure in demo data company USMF using the example values that are shown.</span></span> <span data-ttu-id="9efef-106">Az eljárás megkezdése előtt rendelkeznie kell egy fizikai, aktuális készletű cikkel.</span><span class="sxs-lookup"><span data-stu-id="9efef-106">You need to have an item with physical on-hand inventory available before you start this procedure.</span></span>


## <a name="create-an-inventory-blocking"></a><span data-ttu-id="9efef-107">Készletzárolás létrehozása</span><span class="sxs-lookup"><span data-stu-id="9efef-107">Create an inventory blocking</span></span>
1. <span data-ttu-id="9efef-108">A **Navigációs ablaktáblán** lépjen a **Modulok > Készletgazdálkodás > Időszakos feladatok > Minőségkezelés > Készletzárolás** részre.</span><span class="sxs-lookup"><span data-stu-id="9efef-108">In the **Navigation pane**, go to **Modules > Inventory management > Periodic tasks > Inventory blocking**.</span></span>
2. <span data-ttu-id="9efef-109">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="9efef-109">Click **New**.</span></span>
3. <span data-ttu-id="9efef-110">A **Cikkszám** mezőben kattintson a legördülő gombra a keresés megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="9efef-110">In the **Item number** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="9efef-111">A listából válassza ki a használni kívánt cikket.</span><span class="sxs-lookup"><span data-stu-id="9efef-111">In the list, select the item you want to choose.</span></span> <span data-ttu-id="9efef-112">Válasszon ki egy blokkolni kívánt cikkszámot fizikai aktuális készlettel.</span><span class="sxs-lookup"><span data-stu-id="9efef-112">Select an item number with physical on-hand inventory that you want to block.</span></span> <span data-ttu-id="9efef-113">Az USMF használata esetén választhatja a „M9201” cikket.</span><span class="sxs-lookup"><span data-stu-id="9efef-113">If you're using USMF you can select item M9201.</span></span>  
5. <span data-ttu-id="9efef-114">Adjon meg egy számot a **Mennyiség** mezőben.</span><span class="sxs-lookup"><span data-stu-id="9efef-114">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="9efef-115">Az M9201 használata esetén kevesebb, mint 200-at kell választania.</span><span class="sxs-lookup"><span data-stu-id="9efef-115">If you're using item M9201, you need to select less than 200.</span></span>
6. <span data-ttu-id="9efef-116">Bontsa ki a **Készletdimenziók** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="9efef-116">Expand the **Inventory dimensions** fastTab.</span></span>
7. <span data-ttu-id="9efef-117">A **Raktár** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="9efef-117">In the **Warehouse** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="9efef-118">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="9efef-118">In the list, find and select the desired record.</span></span> <span data-ttu-id="9efef-119">Az M9201 használata esetén kiválaszthatja az 51. raktárat.</span><span class="sxs-lookup"><span data-stu-id="9efef-119">If you're using item M9201, you can select warehouse 51.</span></span>  
9. <span data-ttu-id="9efef-120">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="9efef-120">Click **Save**.</span></span>

## <a name="update-the-conditions-of-the-inventory-blocking"></a><span data-ttu-id="9efef-121">Készletzárolás feltételeinek frissítése</span><span class="sxs-lookup"><span data-stu-id="9efef-121">Update the conditions of the inventory blocking</span></span>
1. <span data-ttu-id="9efef-122">Írjon be egy számot az **Általános** gyorslap **Mennyiség** mezőjébe.</span><span class="sxs-lookup"><span data-stu-id="9efef-122">In the **General** fastTab, in the **Quantity** field, enter a number.</span></span> <span data-ttu-id="9efef-123">Frissítse a készletmennyiség mezőt, hogy megfeleljen a blokkolni kívánt mennyiségnek.</span><span class="sxs-lookup"><span data-stu-id="9efef-123">Update the inventory quantity field to reflect the quantity to block.</span></span>  
2. <span data-ttu-id="9efef-124">Adjon meg egy dátumot a **Várható dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="9efef-124">In the **Expected date** field, enter a date.</span></span> <span data-ttu-id="9efef-125">A várható dátum megadásával érdemes jelezni, hogy a blokkolt készlet a tervek szerint mikor foglalható újra.</span><span class="sxs-lookup"><span data-stu-id="9efef-125">You might want to indicate when the blocked inventory is expected to become available for reservation by assigning an expected date.</span></span> <span data-ttu-id="9efef-126">Ha a Várt bevételezések lehetőség van kiválasztva a készletzároláshoz, mint ahogy az alapértelmezett esetben a blokkolás létrehozásakor történik, ez a dátum jelenik meg a várható tranzakción.</span><span class="sxs-lookup"><span data-stu-id="9efef-126">If the Expected receipts option is selected for the inventory blocking, as it is by default when you manually create a blocking, this date will appear on the expected transaction.</span></span>  
3. <span data-ttu-id="9efef-127">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="9efef-127">Click **Save**.</span></span>

## <a name="remove-the-inventory-blocking"></a><span data-ttu-id="9efef-128">Készletzárolás megszüntetése</span><span class="sxs-lookup"><span data-stu-id="9efef-128">Remove the inventory blocking</span></span>
1. <span data-ttu-id="9efef-129">A **Műveleti panelen** kattintson a **Törlés** elemre.</span><span class="sxs-lookup"><span data-stu-id="9efef-129">On the **Action Pane**, click **Delete**.</span></span>
2. <span data-ttu-id="9efef-130">Kattintson az **Igen** gombra.</span><span class="sxs-lookup"><span data-stu-id="9efef-130">Click **Yes**.</span></span>
3. <span data-ttu-id="9efef-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9efef-131">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]