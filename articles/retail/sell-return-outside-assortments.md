---
title: "Szortimenten kívüli termékek eladása és visszavétele"
description: "A Dynamics 365 for Retail segítségével szortimenteken kívüli termékeket értékesíthet és küldhet vissza."
author: pdp1207
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: 
ms.custom: 
ms.search.region: Global
ms.search.industry: retail
ms.author: prabhup
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7fa5b240bc9c9f96ae5483be316eff62df915570
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="sell-and-return-products-outside-of-an-assortment"></a><span data-ttu-id="1977e-103">Szortimenten kívüli termékek eladása és visszavétele</span><span class="sxs-lookup"><span data-stu-id="1977e-103">Sell and return products outside of an assortment</span></span>
<span data-ttu-id="1977e-104">Minden kiskereskedőben közös, hogy termékeket értékesítenek az ügyfeleknek, vagy visszárut fogadnak el a vevőktől, még akkor is, ha az adott termék nem található meg az üzletben (vagyis a termékek nem tartoznak az üzlet szortimentjébe).</span><span class="sxs-lookup"><span data-stu-id="1977e-104">A common scenario for any retailer is to sell products to their customers or accept returns from their customers even if they don’t carry the specific products in their store (in other words, the products are not assorted to the store).</span></span>
<span data-ttu-id="1977e-105">Íme néhány tipikus forgatókönyv:</span><span class="sxs-lookup"><span data-stu-id="1977e-105">Here are some typical scenarios:</span></span>

+ <span data-ttu-id="1977e-106">Egy kiskereskedő nem tartja minden termékét egy adott üzletben.</span><span class="sxs-lookup"><span data-stu-id="1977e-106">A retailer doesn’t carry all its products in a specific store.</span></span> <span data-ttu-id="1977e-107">A fennmaradó termékeket a raktárban tárolják.</span><span class="sxs-lookup"><span data-stu-id="1977e-107">The remaining products are stored in the warehouse.</span></span> <span data-ttu-id="1977e-108">Az üzlet alkalmazottja segítséget nyújthat az ügyfélnek a raktárban lévő termékek keresése vagy tallózása révén, hozzáadhatja azokat a kosárhoz, és elvégezheti a fizetést egy kiszállítási mód kiválasztásával, például a raktárból egy adott címre történő elküldésével, vagy a terméknek a vevő által az aktuális üzletből vagy egy másik üzletből történő felvételével.</span><span class="sxs-lookup"><span data-stu-id="1977e-108">The store associate can assist the customer by searching or browsing for the products in the warehouse, add them to the cart, and complete the checkout by selecting a delivery method, such as shipping to an address from the warehouse or letting the customer pick up the product from the current store or from another store.</span></span>
+ <span data-ttu-id="1977e-109">A kiskereskedő üzletében nincsenek ott a kontkrét termékek, vagy nincsenek készleten abban az üzletben, ahol a vevő járt, de a termékek elérhetők más üzletekben.</span><span class="sxs-lookup"><span data-stu-id="1977e-109">A retailer doesn’t carry specific products in the store or doesn’t have them in stock at the store the customer visited, but the products are available in other stores.</span></span> <span data-ttu-id="1977e-110">Az üzlet alkalmazottja segítséget nyújthat az ügyfélnek a raktárban lévő termékek keresése vagy tallózása révén, hozzáadhatja azokat a kosárhoz, és elvégezheti a fizetést egy kiszállítási mód kiválasztásával.</span><span class="sxs-lookup"><span data-stu-id="1977e-110">The store associate can assist the customer by searching or browsing the products in the other store, add them to the cart, and complete the checkout by selecting a delivery method.</span></span>
+ <span data-ttu-id="1977e-111">A kiskereskedő számos üzlettel rendelkezik egy bizonyos város vagy irányítószám körzetében, és nem akarja az ügyfeleket arra kényszeríteni, hogy ugyanabba az üzletbe vigyék vissza a termékeket, amelyikben vásárolták őket.</span><span class="sxs-lookup"><span data-stu-id="1977e-111">A retailer has many stores in and around a specific city or zip code and doesn’t want to force the customers to return products to the same store they were purchased in.</span></span> <span data-ttu-id="1977e-112">Ehelyett a vevők bármelyik üzletbe visszavihetik a termékeket.</span><span class="sxs-lookup"><span data-stu-id="1977e-112">Instead, customers can return products to any store.</span></span>


<span data-ttu-id="1977e-113">A Dynamics 365 for Retail használatával ezek az általános forgatókönyvek elérhetők a kiskereskedők számára.</span><span class="sxs-lookup"><span data-stu-id="1977e-113">Those common scenarios are available for retailers using Dynamics 365 for Retail.</span></span> <span data-ttu-id="1977e-114">A Retail alkalmazással a következőket teheti:</span><span class="sxs-lookup"><span data-stu-id="1977e-114">With Retail, you can:</span></span>
+ <span data-ttu-id="1977e-115">Más üzletekben lévő termékek keresése vagy tallózása.</span><span class="sxs-lookup"><span data-stu-id="1977e-115">Search or browse products at other stores.</span></span>
+ <span data-ttu-id="1977e-116">Az összes kiadott termék keresése vagy tallózása.</span><span class="sxs-lookup"><span data-stu-id="1977e-116">Search or browse all released products.</span></span>
+ <span data-ttu-id="1977e-117">Cash-and-carry típusú tranzakciók vagy vevői rendelések létrehozása.</span><span class="sxs-lookup"><span data-stu-id="1977e-117">Create cash-and-carry transactions or customer orders.</span></span>
+ <span data-ttu-id="1977e-118">Vevői rendelések szállítási lehetőségeinek kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="1977e-118">Select delivery options for customer orders.</span></span>
+ <span data-ttu-id="1977e-119">Termékek átvétele az aktuális üzletben vagy egy másik üzletben.</span><span class="sxs-lookup"><span data-stu-id="1977e-119">Pick up products at the current store or another store.</span></span>
+ <span data-ttu-id="1977e-120">Rendelés érvénytelenítése az aktuális üzletben vagy egy másik üzletben.</span><span class="sxs-lookup"><span data-stu-id="1977e-120">Cancel an order at the current store or another store.</span></span>
+ <span data-ttu-id="1977e-121">Visszárurendelés nyugtával vagy anélkül a jelenlegi vagy egy másik üzletben.</span><span class="sxs-lookup"><span data-stu-id="1977e-121">Return an order with or without the receipt at the current store or another store.</span></span>
