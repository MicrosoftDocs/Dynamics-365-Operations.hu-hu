--- 
title: "Cikkek regisztrálása alapvető raktározásra engedélyezett cikkre, cikkérkeztetési napló használatával"
description: "Ez az eljárás megmutatja, hogyan regisztrálhat cikkeket a cikkérkeztetési napló segítségével, ha a készletkezelési modulban „alapvető raktározást” használ."
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: ab824bd99347cbd090e99435217f9ce8ae992b3d
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---
# <a name="register-items-for-a-basic-warehousing-enabled-item-using-an-item-arrival-journal"></a><span data-ttu-id="260e3-103">Cikkek regisztrálása alapvető raktározásra engedélyezett cikkre, cikkérkeztetési napló használatával</span><span class="sxs-lookup"><span data-stu-id="260e3-103">Register items for a basic warehousing enabled item using an item arrival journal</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="260e3-104">Ez az eljárás megmutatja, hogyan regisztrálhat cikkeket a cikkérkeztetési napló segítségével, ha a készletkezelési modulban „alapvető raktározást” használ.</span><span class="sxs-lookup"><span data-stu-id="260e3-104">This procedure shows you how to register items using the item arrival journal when you are using “basic warehousing” in the Inventory management module.</span></span> <span data-ttu-id="260e3-105">Ezt általában egy bevételezési adminisztrátor végzi.</span><span class="sxs-lookup"><span data-stu-id="260e3-105">This would usually be done by a receiving clerk.</span></span> <span data-ttu-id="260e3-106">Ezt az eljárást az USMF bemutató vállalatban is futtathatja a megjelenített példákat használva.</span><span class="sxs-lookup"><span data-stu-id="260e3-106">You can run this procedure in demo data company USMF with the example values that are shown.</span></span>  <span data-ttu-id="260e3-107">Ha nem az USMF-et használja, a útmutató elkezdése előtt jóváhagyott beszerzési rendelésre van szüksége nyitott beszerzésirendelés-sorral.</span><span class="sxs-lookup"><span data-stu-id="260e3-107">If you are not using USMF, you need to have a confirmed purchase order with an open purchase order line before you start this guide.</span></span> <span data-ttu-id="260e3-108">A sorban szereplő cikknek raktározottnak kell lennie, és nem használhat termékváltozatokat, és nem lehet nyomon követési dimenziója.</span><span class="sxs-lookup"><span data-stu-id="260e3-108">The item on the line must be stocked, and it must not use product variants, and must not have tracking dimensions.</span></span> <span data-ttu-id="260e3-109">A cikket egy olyan tárolásidimenzió-csoporthoz kell hozzárendelni, ahol a hely és a raktár aktív.</span><span class="sxs-lookup"><span data-stu-id="260e3-109">And the item needs to be associated with a storage dimension group, where site and warehouse are active.</span></span>


## <a name="create-item-arrival-journal-header"></a><span data-ttu-id="260e3-110">Cikkérkeztetési napló fejlécének létrehozása</span><span class="sxs-lookup"><span data-stu-id="260e3-110">Create item arrival journal header</span></span>
1. <span data-ttu-id="260e3-111">Lépjen a Készletgazdálkodás > Naplóbejegyzések > Cikkérkeztetés > Cikkérkeztetés menüpontra.</span><span class="sxs-lookup"><span data-stu-id="260e3-111">Go to Inventory management > Journal entries > Item arrival > Item arrival.</span></span>
2. <span data-ttu-id="260e3-112">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="260e3-112">Click New.</span></span>
3. <span data-ttu-id="260e3-113">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="260e3-113">In the Name field, type a value.</span></span>
    * <span data-ttu-id="260e3-114">Az USMF használata esetén beírhatja a „WHS” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="260e3-114">If you are using USMF, you can type WHS.</span></span> <span data-ttu-id="260e3-115">Ha más adatokat használ, a kiválasztott naplót az alábbiak szerint kell beállítania: a kitárolási hely ellenőrzése legyen a Nem beállításon, és a Karanténkezelés legyen a Nem beállításon.</span><span class="sxs-lookup"><span data-stu-id="260e3-115">If you’re using other data, the journal whose name you choose has to have the following properties: check picking location must be set to No, and Quarantine management must be set to No.</span></span>  
4. <span data-ttu-id="260e3-116">Írjon be egy értéket a szállítólevél mezőbe.</span><span class="sxs-lookup"><span data-stu-id="260e3-116">In the Packing slip field, type a value.</span></span>
    * <span data-ttu-id="260e3-117">Ez a szállítólevél azonosítója a vevő által kiállított szállítólevélről.</span><span class="sxs-lookup"><span data-stu-id="260e3-117">This is the packing slip ID from the packing slip issued by the vendor.</span></span> <span data-ttu-id="260e3-118">Adjon meg egy egyedi számot.</span><span class="sxs-lookup"><span data-stu-id="260e3-118">Add a unique number.</span></span>  
5. <span data-ttu-id="260e3-119">A Szám mezőben válassza ki a beszerzési rendelést.</span><span class="sxs-lookup"><span data-stu-id="260e3-119">In the Number field, In the Number field, select the purchase order..</span></span>
6. <span data-ttu-id="260e3-120">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="260e3-120">Click OK.</span></span>

## <a name="add-lines-to-item-arrival-journal"></a><span data-ttu-id="260e3-121">Sorok hozzáadása a cikkérkeztetési naplóhoz</span><span class="sxs-lookup"><span data-stu-id="260e3-121">Add lines to item arrival journal</span></span>
1. <span data-ttu-id="260e3-122">Kattintson a Funkciók elemre.</span><span class="sxs-lookup"><span data-stu-id="260e3-122">Click Functions.</span></span>
2. <span data-ttu-id="260e3-123">Kattintson a Sorok létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="260e3-123">Click Create lines.</span></span>
    * <span data-ttu-id="260e3-124">A sorokat létrehozhatja automatikusan, vagy megadhatja azokat a naplóba manuálisan.</span><span class="sxs-lookup"><span data-stu-id="260e3-124">The lines can be entered manually into this journal or created automatically.</span></span> <span data-ttu-id="260e3-125">Ez az automatikus létrehozást mutatja be.</span><span class="sxs-lookup"><span data-stu-id="260e3-125">This will show you how to create this automatically.</span></span>  
3. <span data-ttu-id="260e3-126">Jelölje be vagy törölje a jelölést a Mennyiség kezdeti beállítása jelölőnégyzetből.</span><span class="sxs-lookup"><span data-stu-id="260e3-126">Check or uncheck the Initialize quantity checkbox.</span></span>
    * <span data-ttu-id="260e3-127">Ez inicializálja a naplósorok mennyiségét a beszerzési rendelés sorából nem regisztrált mennyiséggel.</span><span class="sxs-lookup"><span data-stu-id="260e3-127">This will initialize the quantity on the journal lines with the quantity not registered from the purchase order line.</span></span>  
4. <span data-ttu-id="260e3-128">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="260e3-128">Click OK.</span></span>

## <a name="post-the-journal"></a><span data-ttu-id="260e3-129">Napló feladása</span><span class="sxs-lookup"><span data-stu-id="260e3-129">Post the journal</span></span>
1. <span data-ttu-id="260e3-130">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="260e3-130">Click Post.</span></span>
2. <span data-ttu-id="260e3-131">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="260e3-131">Click OK.</span></span>

## <a name="generate-the-product-receipt"></a><span data-ttu-id="260e3-132">Termékbevételezés létrehozása</span><span class="sxs-lookup"><span data-stu-id="260e3-132">Generate the product receipt</span></span>
1. <span data-ttu-id="260e3-133">Kattintson a Funkciók elemre.</span><span class="sxs-lookup"><span data-stu-id="260e3-133">Click Functions.</span></span>
2. <span data-ttu-id="260e3-134">Kattintson a Termékbevételezés elemre.</span><span class="sxs-lookup"><span data-stu-id="260e3-134">Click Product receipt.</span></span>
3. <span data-ttu-id="260e3-135">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="260e3-135">Click OK.</span></span>


