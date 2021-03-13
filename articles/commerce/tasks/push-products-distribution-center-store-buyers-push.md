---
title: " Termékek elosztása az elosztási központból az üzletbe a központi elosztás használatával"
description: Ez az eljárás bemutatja, hogy mely lépésekkel hozhat létre és dolgozhat fel egy Központi elosztást, amellyel termékeket oszthat el egyetlen helyről egy vagy több üzletbe.
author: rubencdelgado
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailBuyersPush, InventLocationIdLookup, InventItemIdLookupSimple, RetailReplenishmentTreeLookup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3720945823cf127f776a9ea6a6ad75a72ceec00c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5012341"
---
# <a name="push-products-from-distribution-center-to-store-using-buyers-push"></a><span data-ttu-id="2ff81-103"> Termékek elosztása az elosztási központból az üzletbe a központi elosztás használatával</span><span class="sxs-lookup"><span data-stu-id="2ff81-103">Push products from distribution center to store using buyer's push</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2ff81-104">Ez az eljárás bemutatja, hogy mely lépésekkel hozhat létre és dolgozhat fel egy Központi elosztást, amellyel termékeket oszthat el egyetlen helyről egy vagy több üzletbe.</span><span class="sxs-lookup"><span data-stu-id="2ff81-104">This procedure walks through the steps to create and process a Buyer´s push to distribute products from one location to one or many stores.</span></span> <span data-ttu-id="2ff81-105">A felhasználó több konfigurációt is definiálhat, majd kérheti a rendszer javaslatát a termékek elosztására, vagy manuálisan megadhatja, hogy a termékek elosztása hová és az egyes üzletekbe milyen mennyiségben történjen.</span><span class="sxs-lookup"><span data-stu-id="2ff81-105">The user can define multiple configurations and have the system suggest how to distribute the products, or manually enter where the products are distributed to and how much gets distributed to each store.</span></span> <span data-ttu-id="2ff81-106">Ez az eljárás nem tartalmazza a Központi elosztás lehetőségben használható adatok (például: feltöltési szabályok, szervezeti hierarchiák, üzletek súlya) beállítását.</span><span class="sxs-lookup"><span data-stu-id="2ff81-106">This procedure doesn't include setup of data that can be used in the Buyer´s push, such as replenishment rules, organizational hierarchies, and store weights.</span></span> <span data-ttu-id="2ff81-107">Ez az eljárás az USRT bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="2ff81-107">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="2ff81-108">Nyissa meg a következőt: Központi elosztás.</span><span class="sxs-lookup"><span data-stu-id="2ff81-108">Go to Buyer's push.</span></span>
2. <span data-ttu-id="2ff81-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2ff81-109">Click New.</span></span>
3. <span data-ttu-id="2ff81-110">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2ff81-110">In the Description field, type a value.</span></span>
4. <span data-ttu-id="2ff81-111">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2ff81-111">In the Site field, enter or select a value.</span></span>
5. <span data-ttu-id="2ff81-112">A Raktár mezőben adjon meg vagy válasszon ki egy raktárt, amelyben termékek aktuális készletei találhatók.</span><span class="sxs-lookup"><span data-stu-id="2ff81-112">In the Warehouse field, enter or select a warehouse that has products with on-hand quantities.</span></span>
6. <span data-ttu-id="2ff81-113">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="2ff81-113">Click Add.</span></span>
7. <span data-ttu-id="2ff81-114">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="2ff81-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="2ff81-115">A Cikkszám mezőben adjon meg, vagy válasszon ki egy terméket.</span><span class="sxs-lookup"><span data-stu-id="2ff81-115">In the Item number field, enter or select a product.</span></span>
9. <span data-ttu-id="2ff81-116">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="2ff81-116">Click Add.</span></span>
10. <span data-ttu-id="2ff81-117">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="2ff81-117">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="2ff81-118">A Cikkszám mezőben adjon meg, vagy válasszon ki egy termékváltozatot.</span><span class="sxs-lookup"><span data-stu-id="2ff81-118">In the Item number field, enter or select a variant product.</span></span>
    * <span data-ttu-id="2ff81-119">Termékváltozat megadásakor minden egyes változathoz létrejönnek sorok.</span><span class="sxs-lookup"><span data-stu-id="2ff81-119">When entering a variant product, lines will be created for each variant.</span></span>  
12. <span data-ttu-id="2ff81-120">Jelöljön meg egy sort a listán.</span><span class="sxs-lookup"><span data-stu-id="2ff81-120">In the list, mark a row.</span></span>
13. <span data-ttu-id="2ff81-121">A Központilag elosztott mennyiség mezőbe írja be, hogy a kiválasztott termékből mennyit kíván elosztani.</span><span class="sxs-lookup"><span data-stu-id="2ff81-121">In the Pushed quantity field, type how many of the selected product you want to distribute.</span></span>
14. <span data-ttu-id="2ff81-122">A További központilag elosztandó mennyiség mezőben adja meg azoknak a termékeknek a mennyiségét, amelyekből rendelkezésre áll elosztható mennyiség.</span><span class="sxs-lookup"><span data-stu-id="2ff81-122">In the Additional quantity to push field, enter the quantity of the products that have available quantity to distribute.</span></span>
15. <span data-ttu-id="2ff81-123">Az Elosztás mezőbe írja be: „Hely súly”.</span><span class="sxs-lookup"><span data-stu-id="2ff81-123">In the Distribution field, enter 'Location weight'.</span></span>
    * <span data-ttu-id="2ff81-124">Más elosztási szabályok használatához kiválaszthatja a többi típust is.</span><span class="sxs-lookup"><span data-stu-id="2ff81-124">You can select the other types to use other rules for the distribution.</span></span>  
16. <span data-ttu-id="2ff81-125">Válasszon ki egy értéket a Feltöltési hierarchia mezőben.</span><span class="sxs-lookup"><span data-stu-id="2ff81-125">In the Replenishment hierarchy field, select a value.</span></span>
17. <span data-ttu-id="2ff81-126">Válassza az Igen lehetőséget a Szortimentek figyelembevétele mezőben.</span><span class="sxs-lookup"><span data-stu-id="2ff81-126">Select Yes in the Respect assortments field.</span></span>
18. <span data-ttu-id="2ff81-127">Kattintson a Mennyiségek kiszámítása gombra, majd ellenőrizze a Raktár szakasz soraihoz adott mennyiségeket.</span><span class="sxs-lookup"><span data-stu-id="2ff81-127">Click Calculate quantities and review the quantities that are added to the rows in the Warehouse section.</span></span>
19. <span data-ttu-id="2ff81-128">Kattintson a Rendelés létrehozása gombra.</span><span class="sxs-lookup"><span data-stu-id="2ff81-128">Click Create order.</span></span>
20. <span data-ttu-id="2ff81-129">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="2ff81-129">Click Yes.</span></span>

