---
title: Készletzárolás létrehozása és karbantartása
description: Ez az eljárás azt mutatja, hogyan előzheti meg a fizikai, aktuális készletek lefoglalását más kimenő forrásbizonylatokkal a készletzárolás segítségével.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 845d517ad10245df3b208874df61e235c199c7fe
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1836401"
---
# <a name="create-and-maintain-an-inventory-blocking"></a><span data-ttu-id="f4411-103">Készletzárolás létrehozása és karbantartása</span><span class="sxs-lookup"><span data-stu-id="f4411-103">Create and maintain an inventory blocking</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f4411-104">Ez az eljárás azt mutatja, hogyan előzheti meg a fizikai, aktuális készletek lefoglalását más kimenő forrásbizonylatokkal a készletzárolás segítségével.</span><span class="sxs-lookup"><span data-stu-id="f4411-104">This procedure shows how to prevent physical on-hand inventory from being reserved by other outbound source documents by using the inventory blocking.</span></span> <span data-ttu-id="f4411-105">Ezt az eljárást az USMF bemutató vállalatban is futtathatja a megjelenített példákat használva.</span><span class="sxs-lookup"><span data-stu-id="f4411-105">You can run the procedure in demo data company USMF using the example values that are shown.</span></span> <span data-ttu-id="f4411-106">Az eljárás megkezdése előtt rendelkeznie kell egy fizikai, aktuális készletű cikkel.</span><span class="sxs-lookup"><span data-stu-id="f4411-106">You need to have an item with physical on-hand inventory available before you start this procedure.</span></span>


## <a name="create-an-inventory-blocking"></a><span data-ttu-id="f4411-107">Készletzárolás létrehozása</span><span class="sxs-lookup"><span data-stu-id="f4411-107">Create an inventory blocking</span></span>
1. <span data-ttu-id="f4411-108">Ugorjon a Készletkezelés > Időszakos feladatok > Készletzárolás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f4411-108">Go to Inventory management > Periodic tasks > Inventory blocking.</span></span>
2. <span data-ttu-id="f4411-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f4411-109">Click New.</span></span>
3. <span data-ttu-id="f4411-110">A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="f4411-110">In the Item number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="f4411-111">A listából válassza ki a használni kívánt cikket.</span><span class="sxs-lookup"><span data-stu-id="f4411-111">In the list, select the item you want to choose.</span></span> 
    * <span data-ttu-id="f4411-112">Válasszon ki egy blokkolni kívánt cikkszámot fizikai aktuális készlettel.</span><span class="sxs-lookup"><span data-stu-id="f4411-112">Select an item number with physical on-hand inventory that you want to block.</span></span> <span data-ttu-id="f4411-113">Az USMF használata esetén választhatja a „M9201” cikket.</span><span class="sxs-lookup"><span data-stu-id="f4411-113">If you’re using USMF you can select item M9201.</span></span>  
5. <span data-ttu-id="f4411-114">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="f4411-114">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="f4411-115">Az M9201 használata esetén kevesebb, mint 200-at kell választania.</span><span class="sxs-lookup"><span data-stu-id="f4411-115">If you’re using item M9201, you need to select less than 200.</span></span>  
6. <span data-ttu-id="f4411-116">Bontsa ki a Készletdimenziók szakaszt.</span><span class="sxs-lookup"><span data-stu-id="f4411-116">Toggle the expansion of the Inventory dimensions section.</span></span>
7. <span data-ttu-id="f4411-117">A Raktár mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="f4411-117">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="f4411-118">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="f4411-118">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="f4411-119">Az M9201 használata esetén kiválaszthatja az 51. raktárat.</span><span class="sxs-lookup"><span data-stu-id="f4411-119">If you’re using item M9201, you can select warehouse 51.</span></span>  
9. <span data-ttu-id="f4411-120">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="f4411-120">Click Save.</span></span>

## <a name="update-the-conditions-of-the-inventory-blocking"></a><span data-ttu-id="f4411-121">Készletzárolás feltételeinek frissítése</span><span class="sxs-lookup"><span data-stu-id="f4411-121">Update the conditions of the inventory blocking</span></span>
1. <span data-ttu-id="f4411-122">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="f4411-122">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="f4411-123">Frissítse a készletmennyiség mezőt, hogy megfeleljen a blokkolni kívánt mennyiségnek.</span><span class="sxs-lookup"><span data-stu-id="f4411-123">Update the inventory quantity field to reflect the quantity to block.</span></span>  
2. <span data-ttu-id="f4411-124">Adjon meg egy dátumot a Várható dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="f4411-124">In the Expected date field, enter a date.</span></span>
    * <span data-ttu-id="f4411-125">A várható dátum megadásával érdemes jelezni, hogy a blokkolt készlet a tervek szerint mikor foglalható újra.</span><span class="sxs-lookup"><span data-stu-id="f4411-125">You might want to indicate when the blocked inventory is expected to become available for reservation by assigning an expected date.</span></span> <span data-ttu-id="f4411-126">Ha a Várt bevételezések lehetőség van kiválasztva a készletzároláshoz, mint ahogy az alapértelmezett esetben a blokkolás létrehozásakor történik, ez a dátum jelenik meg a várható tranzakción.</span><span class="sxs-lookup"><span data-stu-id="f4411-126">If the Expected receipts option is selected for the inventory blocking, as it is by default when you manually create a blocking, this date will appear on the expected transaction.</span></span>  
3. <span data-ttu-id="f4411-127">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="f4411-127">Click Save.</span></span>

## <a name="remove-the-inventory-blocking"></a><span data-ttu-id="f4411-128">Készletzárolás megszüntetése</span><span class="sxs-lookup"><span data-stu-id="f4411-128">Remove the inventory blocking</span></span>
1. <span data-ttu-id="f4411-129">Kattintson a Törlés gombra.</span><span class="sxs-lookup"><span data-stu-id="f4411-129">Click Delete.</span></span>
2. <span data-ttu-id="f4411-130">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="f4411-130">Click Yes.</span></span>
3. <span data-ttu-id="f4411-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="f4411-131">Close the page.</span></span>

