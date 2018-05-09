--- 
title: "Vállalaton belüli árumozgás dokumentumainak beállítása"
description: "Ez az eljárás bemutatja, hogyan lehet átadási dokumentumokat létrehozni a vállalaton belüli árumozgáshoz."
author: v-oloski
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 4f37846f5cc881a37f6e803bb6183f6495100683
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="set-up-the-transfer-documents-for-goods-movement-inside-a-company"></a><span data-ttu-id="9b51f-103">Vállalaton belüli árumozgás dokumentumainak beállítása</span><span class="sxs-lookup"><span data-stu-id="9b51f-103">Set up the transfer documents for goods movement inside a company</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9b51f-104">Ez az eljárás bemutatja, hogyan lehet átadási dokumentumokat létrehozni a vállalaton belüli árumozgáshoz.</span><span class="sxs-lookup"><span data-stu-id="9b51f-104">This procedure shows how to create transfer documents for goods movement inside a company.</span></span> <span data-ttu-id="9b51f-105">Ez az eljárás csak litvániai elsődleges címmel rendelkező jogi személyek számára áll rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="9b51f-105">This procedure is only available for legal entities with a primary address in Lithuania.</span></span> <span data-ttu-id="9b51f-106">Az eljárást a DEMF bemutatócéget használva hozták létre, az elsődleges címéhez tartozó ország pedig Litvánia.</span><span class="sxs-lookup"><span data-stu-id="9b51f-106">The procedure was created using the demo data company DEMF with a primary address in Lithuania.</span></span> <span data-ttu-id="9b51f-107">Ahhoz, hogy befejezhesse ezt az eljárást, végre kell hajtania a következő eljárást: „Vállalaton belüli árumozgás dokumentumainak beállítása”.</span><span class="sxs-lookup"><span data-stu-id="9b51f-107">Before you can complete this procedure, you must complete the “Set up transfer documents for goods movement inside a company” procedure.</span></span> <span data-ttu-id="9b51f-108">Ez az eljárás készletkönyvelőknek szól.</span><span class="sxs-lookup"><span data-stu-id="9b51f-108">This procedure is intended for inventory accountants.</span></span> <span data-ttu-id="9b51f-109">Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.</span><span class="sxs-lookup"><span data-stu-id="9b51f-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-transfer-order"></a><span data-ttu-id="9b51f-110">Átmozgatási rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="9b51f-110">Create a transfer order</span></span>
1. <span data-ttu-id="9b51f-111">Ugrás a következőre: Készletnyilvántartás > Bejövő rendelések > Átmozgatási rendelés.</span><span class="sxs-lookup"><span data-stu-id="9b51f-111">Go to Inventory management > Inbound orders > Transfer order.</span></span>
2. <span data-ttu-id="9b51f-112">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9b51f-112">Click New.</span></span>
3. <span data-ttu-id="9b51f-113">A Forrásraktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9b51f-113">In the From warehouse field, enter or select a value.</span></span>
4. <span data-ttu-id="9b51f-114">A Célraktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9b51f-114">In the To warehouse field, enter or select a value.</span></span>
5. <span data-ttu-id="9b51f-115">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="9b51f-115">Click Add.</span></span>
6. <span data-ttu-id="9b51f-116">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="9b51f-116">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="9b51f-117">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9b51f-117">In the Item number field, enter or select a value.</span></span>

## <a name="enter-transportation-details-for-the-transfer-order"></a><span data-ttu-id="9b51f-118">Szállítás részleteinek bevitele az átmozgatási rendeléshez</span><span class="sxs-lookup"><span data-stu-id="9b51f-118">Enter transportation details for the transfer order</span></span>
1. <span data-ttu-id="9b51f-119">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="9b51f-119">Click Save.</span></span>
2. <span data-ttu-id="9b51f-120">A Művelet panelen kattintson a Szállítás elemre.</span><span class="sxs-lookup"><span data-stu-id="9b51f-120">On the Action Pane, click Ship.</span></span>
3. <span data-ttu-id="9b51f-121">Kattintson a Szállítás részletei lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9b51f-121">Click Transportation details.</span></span>
4. <span data-ttu-id="9b51f-122">Válassza az Igen lehetőséget a Szállítás részletes adatainak nyomtatása mezőben.</span><span class="sxs-lookup"><span data-stu-id="9b51f-122">Select Yes in the Print transportation details field.</span></span>
5. <span data-ttu-id="9b51f-123">Az Áruk kiadva általa mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9b51f-123">In the Goods issued by field, enter or select a value.</span></span>
6. <span data-ttu-id="9b51f-124">A Csomag mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9b51f-124">In the Package field, type a value.</span></span>
7. <span data-ttu-id="9b51f-125">A Rakomány kockázatszintje mezőben adjon meg egy értékét.</span><span class="sxs-lookup"><span data-stu-id="9b51f-125">In the Risk level of the load field, type a value.</span></span>
8. <span data-ttu-id="9b51f-126">A Szállítmányozó mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9b51f-126">In the Carrier field, enter or select a value.</span></span>
9. <span data-ttu-id="9b51f-127">A Modell mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9b51f-127">In the Model field, enter or select a value.</span></span>
10. <span data-ttu-id="9b51f-128">Írjon be egy értéket a Regisztrációs szám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9b51f-128">In the Registration number field, type a value.</span></span>
11. <span data-ttu-id="9b51f-129">Írjon be egy értéket az Utánfutó regisztrációs száma mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9b51f-129">In the Trailer registration number field, type a value.</span></span>
12. <span data-ttu-id="9b51f-130">A Sofőr mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9b51f-130">In the Driver field, enter or select a value.</span></span>
13. <span data-ttu-id="9b51f-131">Írjon be egy értéket a Járművezető neve mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9b51f-131">In the Driver name field, type a value.</span></span>
14. <span data-ttu-id="9b51f-132">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="9b51f-132">Click Save.</span></span>
15. <span data-ttu-id="9b51f-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9b51f-133">Close the page.</span></span>

## <a name="view-the-packing-slip-for-the-unposted-transfer-order"></a><span data-ttu-id="9b51f-134">Szállítólevél megtekintése a könyveletlen átmozgatási rendeléshez</span><span class="sxs-lookup"><span data-stu-id="9b51f-134">View the packing slip for the unposted transfer order</span></span>
1. <span data-ttu-id="9b51f-135">Kattintson a Szállítólevél lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9b51f-135">Click Packing slip.</span></span>
2. <span data-ttu-id="9b51f-136">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9b51f-136">Click OK.</span></span>
3. <span data-ttu-id="9b51f-137">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9b51f-137">Close the page.</span></span>

## <a name="view-the-packing-slip-for-the-posted-transfer-order"></a><span data-ttu-id="9b51f-138">Szállítólevél megtekintése a könyvelt átmozgatási rendeléshez</span><span class="sxs-lookup"><span data-stu-id="9b51f-138">View the packing slip for the posted transfer order</span></span>
1. <span data-ttu-id="9b51f-139">Kattintson az Átmozgatási rendelés lehetőségre a Művelet Panelen.</span><span class="sxs-lookup"><span data-stu-id="9b51f-139">On the Action Pane, click Transfer order.</span></span>
2. <span data-ttu-id="9b51f-140">A Művelet panelen kattintson a Szállítás elemre.</span><span class="sxs-lookup"><span data-stu-id="9b51f-140">On the Action Pane, click Ship.</span></span>
3. <span data-ttu-id="9b51f-141">Kattintson az Átmozgatási rendelések szállítása elemre.</span><span class="sxs-lookup"><span data-stu-id="9b51f-141">Click Ship transfer order.</span></span>
4. <span data-ttu-id="9b51f-142">Kattintson az Általános fülre.</span><span class="sxs-lookup"><span data-stu-id="9b51f-142">Click the General tab.</span></span>
5. <span data-ttu-id="9b51f-143">A Frissítés mezőben válasszon egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9b51f-143">In the Update field, select an option.</span></span>
6. <span data-ttu-id="9b51f-144">Kattintson az Áttekintés fülre.</span><span class="sxs-lookup"><span data-stu-id="9b51f-144">Click the Overview tab.</span></span>
7. <span data-ttu-id="9b51f-145">Írjon be egy értéket a szállítólevél mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9b51f-145">In the Packing slip field, type a value.</span></span>
8. <span data-ttu-id="9b51f-146">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9b51f-146">Click OK.</span></span>
9. <span data-ttu-id="9b51f-147">A Művelet panelen kattintson a Szállítás elemre.</span><span class="sxs-lookup"><span data-stu-id="9b51f-147">On the Action Pane, click Ship.</span></span>
10. <span data-ttu-id="9b51f-148">Kattintson a Szállítólevél lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9b51f-148">Click Packing slip.</span></span>
11. <span data-ttu-id="9b51f-149">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9b51f-149">Click OK.</span></span>


