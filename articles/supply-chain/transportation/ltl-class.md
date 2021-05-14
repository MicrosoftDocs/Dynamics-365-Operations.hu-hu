---
title: Kevesebb mint a teherautóosztályok (LTL)
description: Ez a témakör bemutatja, hogy mik azok a kevesebb, mint a teherautórakomány (LTL) osztályok, és leírja, hogyan lehet ezeket beállítani a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.
author: Henrikan
ms.date: 04/05/2021
ms.topic: article
ms.search.form: WHSLTLClass
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-05
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 295006cac0a67cd577809a1b62566de043ea55fb
ms.sourcegitcommit: 636c1bf096a8666a551b67e898da1f48feb9a187
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/26/2021
ms.locfileid: "5941810"
---
# <a name="less-than-truckload-ltl-classes"></a><span data-ttu-id="28baf-103">Kevesebb mint a teherautóosztályok (LTL)</span><span class="sxs-lookup"><span data-stu-id="28baf-103">Less than truckload (LTL) classes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="28baf-104">A teherautórakománynál (LTL) kisebb osztály olyan fuvarszállítási osztály, amely a szállítható cikkek osztályozására használható.</span><span class="sxs-lookup"><span data-stu-id="28baf-104">A less than truckload (LTL) class is a freight shipping class that is used to classify items that can be shipped.</span></span> <span data-ttu-id="28baf-105">Általában minden termék- vagy árucikktípushoz NMFC (National Motor Freight Classification) kód tartozik, amely az LTL-szállítmányok meghatározott fuvarosztály-számának felel meg.</span><span class="sxs-lookup"><span data-stu-id="28baf-105">Generally, every type of product or commodity has a National Motor Freight Classification (NMFC) code that corresponds to a specific freight class number for LTL shipments.</span></span> <span data-ttu-id="28baf-106">Az LTL-fuvarozási osztályok cikkkategóriákat képviselnek, míg az NMFC-kódok a 18 fuvarosztály mindegyikében meghatározott árukhoz kapcsolódnak.</span><span class="sxs-lookup"><span data-stu-id="28baf-106">LTL freight classes represent categories of items, whereas NMFC codes are related to specific commodities in each of the 18 freight classes.</span></span>

<span data-ttu-id="28baf-107">A funkciók segítségével a rendszerrel az alábbi műveleteket végezeti el:</span><span class="sxs-lookup"><span data-stu-id="28baf-107">This feature lets you use your system to perform the following tasks:</span></span>

- <span data-ttu-id="28baf-108">A vállalatnál használt LTL-fuvarosztályok meghatározása.</span><span class="sxs-lookup"><span data-stu-id="28baf-108">Define the LTL freight classes that are used at your company.</span></span>
- <span data-ttu-id="28baf-109">Minden LTL-osztályt NMFC-kódhoz rendelése az **NMFC-kódok** oldalon.</span><span class="sxs-lookup"><span data-stu-id="28baf-109">Assign each LTL class to an NMFC code on the **NMFC Codes** page.</span></span> <span data-ttu-id="28baf-110">További információ az [NMFC (National Motor Freight Classification) kódok](nmfc-codes.md) részben található.</span><span class="sxs-lookup"><span data-stu-id="28baf-110">For more information, see [National Motor Freight Classification (NMFC) codes](nmfc-codes.md).</span></span>
- <span data-ttu-id="28baf-111">Rendeljen NMFC-kódot (és ennek megfelelően a termékhez társított LTL-kódot) minden termékhez a **Termékek** lapon.</span><span class="sxs-lookup"><span data-stu-id="28baf-111">Assign an NMFC code (and therefore its associated LTL code) to each product on the **Products** page.</span></span>
- <span data-ttu-id="28baf-112">Az NMFC-kódhoz rendelt termékek LTL-osztályának pontos felmérése.</span><span class="sxs-lookup"><span data-stu-id="28baf-112">Accurately assess the LTL class of each product that an NMFC code is assigned to.</span></span>
- <span data-ttu-id="28baf-113">Az egyes LTL-osztályok csomagolási követelményeinek meghatározása a nemzetközi LTL-szabványok ellenőrzésével.</span><span class="sxs-lookup"><span data-stu-id="28baf-113">Determine packing requirements for each LTL class by checking the international LTL standards.</span></span> <span data-ttu-id="28baf-114">Így biztosíthatja, hogy a termékek megfelelő védelemben és biztonságban lesznek szállítva.</span><span class="sxs-lookup"><span data-stu-id="28baf-114">In this way, you ensure that your products will be well protected and safely shipped.</span></span>
- <span data-ttu-id="28baf-115">Pontos szállítási becslések kérése az egyes termékek LTL-fuvarosztálya alapján.</span><span class="sxs-lookup"><span data-stu-id="28baf-115">Get accurate shipping estimates, based on the LTL freight class for each product.</span></span>

<span data-ttu-id="28baf-116">Ez a témakör azt mutatja be, hogyan lehet LTL-osztályokat hozzáadni a Microsoft Dynamics 365 Supply Chain Management alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="28baf-116">This topic describes how to create LTL classes in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="create-an-ltl-class"></a><span data-ttu-id="28baf-117">LTL-osztály létrehozása</span><span class="sxs-lookup"><span data-stu-id="28baf-117">Create an LTL class</span></span>

<span data-ttu-id="28baf-118">LTL-osztály létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="28baf-118">To create an LTL class, follow these steps.</span></span>

1. <span data-ttu-id="28baf-119">Tegye a következők egyikét:</span><span class="sxs-lookup"><span data-stu-id="28baf-119">Follow one of these steps:</span></span>

    - <span data-ttu-id="28baf-120">Menjen a **Raktárkezelés \> Beállítás \> Készlet \> LTL-osztályok** elemre.</span><span class="sxs-lookup"><span data-stu-id="28baf-120">Go to **Warehouse management \> Setup \> Inventory \> LTL classes**.</span></span>
    - <span data-ttu-id="28baf-121">Ugorjon a **Szállításkezelés \> Beállítás \> Szállítmányozási standardok \> LTL-osztályok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="28baf-121">Go to **Transportation management \> Setup \> Transportation standards \> LTL classes**.</span></span>

2. <span data-ttu-id="28baf-122">Jelölje be a műveleti ablakban az **Új** lehetőséget az LTL-osztály létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="28baf-122">On the Action Pane, select **New** to create an LTL class.</span></span> <span data-ttu-id="28baf-123">Majd, állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="28baf-123">Then set the following fields:</span></span>

    - <span data-ttu-id="28baf-124">**LTL-osztály** – Adja meg a vállalat belső LTL-osztályazonosítóját (azonosító) az árucikk típusához.</span><span class="sxs-lookup"><span data-stu-id="28baf-124">**LTL class** – Enter your company's internal LTL class identifier (ID) for the commodity type.</span></span> <span data-ttu-id="28baf-125">A legtöbb vállalat a nemzetközi szabványt használja.</span><span class="sxs-lookup"><span data-stu-id="28baf-125">Most companies use the international standard.</span></span> <span data-ttu-id="28baf-126">Ebben az esetben a mező értéke meg fog egyezni az **Osztály** mező értékével.</span><span class="sxs-lookup"><span data-stu-id="28baf-126">In that case, the value of this field will match the value of the **Class** field.</span></span> <span data-ttu-id="28baf-127">Ha azonban a vállalat saját szabványt használ, adjon meg egy kódot, amely megfelel ennek a szabványnak.</span><span class="sxs-lookup"><span data-stu-id="28baf-127">However, if your company uses its own standard, enter a code that conforms to that standard.</span></span>
    - <span data-ttu-id="28baf-128">**Név** – Adjon meg egy leíró nevet, amely segít Önnek és más felhasználóknak a megfelelő LTL-osztály kiválasztásában az egyes NMFC-kódokhoz.</span><span class="sxs-lookup"><span data-stu-id="28baf-128">**Name** – Enter a descriptive name that will help you and other users select the correct LTL class for each NMFC code.</span></span>
    - <span data-ttu-id="28baf-129">**Osztály** – Adja meg az árucikk-típus nemzetközi szabványos LTL-osztályazonosítóját.</span><span class="sxs-lookup"><span data-stu-id="28baf-129">**Class** – Enter the international standard LTL class ID for the commodity type.</span></span> <span data-ttu-id="28baf-130">Az itt beírott kódnak meg kell felelnie a hivatalos szabványnak.</span><span class="sxs-lookup"><span data-stu-id="28baf-130">The code that you enter here must conform to the official standard.</span></span>

## <a name="example-set-up-ltl-classes"></a><span data-ttu-id="28baf-131">Példa: LTL-osztályok beállítása</span><span class="sxs-lookup"><span data-stu-id="28baf-131">Example: Set up LTL classes</span></span>

<span data-ttu-id="28baf-132">A következő példa bemutatja, hogyan lehet két különböző LTL-osztályokat beállítani, amelyek különböző típusú termékekkel használhatók.</span><span class="sxs-lookup"><span data-stu-id="28baf-132">The following example shows how to set up two different LTL classes that you can use with different types of products.</span></span>

1. <span data-ttu-id="28baf-133">Menjen a **Raktárkezelés \> Beállítás \> Készlet \> LTL-osztályok** elemre.</span><span class="sxs-lookup"><span data-stu-id="28baf-133">Go to **Warehouse management \> Setup \> Inventory \> LTL classes**.</span></span>
1. <span data-ttu-id="28baf-134">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="28baf-134">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="28baf-135">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="28baf-135">On the new line, set the following values:</span></span>

    - <span data-ttu-id="28baf-136">**LTL-osztály:** *92,5*</span><span class="sxs-lookup"><span data-stu-id="28baf-136">**LTL class:** *92.5*</span></span>
    - <span data-ttu-id="28baf-137">**Név:** *Számítógépek, monitorok, hűtők*</span><span class="sxs-lookup"><span data-stu-id="28baf-137">**Name:** *Computers, monitors, refrigerators*</span></span>
    - <span data-ttu-id="28baf-138">**Osztály:** *92,5*</span><span class="sxs-lookup"><span data-stu-id="28baf-138">**Class:** *92.5*</span></span>

1. <span data-ttu-id="28baf-139">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="28baf-139">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="28baf-140">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="28baf-140">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="28baf-141">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="28baf-141">On the new line, set the following values:</span></span>

    - <span data-ttu-id="28baf-142">**LTL-osztály:** *125*</span><span class="sxs-lookup"><span data-stu-id="28baf-142">**LTL class:** *125*</span></span>
    - <span data-ttu-id="28baf-143">**Név:** *Kis háztartási berendezések*</span><span class="sxs-lookup"><span data-stu-id="28baf-143">**Name:** *Small household appliances*</span></span>
    - <span data-ttu-id="28baf-144">**Osztály:** *125*</span><span class="sxs-lookup"><span data-stu-id="28baf-144">**Class:** *125*</span></span>

1. <span data-ttu-id="28baf-145">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="28baf-145">On the Action Pane, select **Save**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="28baf-146">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="28baf-146">Additional resources</span></span>

- [<span data-ttu-id="28baf-147">NMFC (National Motor Freight Classification) kódok</span><span class="sxs-lookup"><span data-stu-id="28baf-147">National Motor Freight Classification (NMFC) codes</span></span>](nmfc-codes.md)
- [<span data-ttu-id="28baf-148">Fuvarlevél létrehozása</span><span class="sxs-lookup"><span data-stu-id="28baf-148">Create a bill of lading</span></span>](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
