---
title: "Kiskereskedelmi termékek engedményeinek megakadályozása"
description: "Különböző okai lehetnek annak, hogy a kiskereskedők megakadályozzák bizonyos termékek engedménnyel való ellátását, akár promóció, akár a POS-ban történő eladás során."
author: jeffbl
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 85183
ms.assetid: e8c5a24f-7edd-4fd6-af80-5e0ac9f03127
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 70139c124486e3e6a01c1c08e71f140dcf1864c0
ms.openlocfilehash: e0d3a16da6a673f9ce6a025a7d4bde9ffb1a9e9b
ms.contentlocale: hu-hu
ms.lasthandoff: 10/24/2017

---

# <a name="prevent-discounts-for-retail-products"></a><span data-ttu-id="191e9-103">Kiskereskedelmi termékek engedményeinek megakadályozása</span><span class="sxs-lookup"><span data-stu-id="191e9-103">Prevent discounts for retail products</span></span>

[!include[banner](includes/banner.md)]

<span data-ttu-id="191e9-104">Különböző okai lehetnek annak, hogy a kiskereskedők megakadályozzák bizonyos termékek engedménnyel való ellátását, akár promóció, akár a POS-ban történő eladás során.</span><span class="sxs-lookup"><span data-stu-id="191e9-104">There are various reasons why retailers may want to prevent some products from being discounted, either from a promotion or during the sale at the POS.</span></span>

<span data-ttu-id="191e9-105">A következő opciók, amelyek a kiadott termékek **Kiskereskedelem** lapján találhatók, lehetővé teszik a termék konfigurálását az összes vagy a manuális kedvezmények megakadályozása érdekében.</span><span class="sxs-lookup"><span data-stu-id="191e9-105">The following options, which can be found on the **Retail** tab of released products, will allow the product to be configured to prevent all or manual discounts.</span></span> <span data-ttu-id="191e9-106">A beállítások kategóriaszinten is meghatározhatók a kiskereskedelmi kategóriák hierarchiájából.</span><span class="sxs-lookup"><span data-stu-id="191e9-106">The settings can also be specified at the category level from the retail category hierarchy.</span></span>

<span data-ttu-id="191e9-107">**Minden kedvezmény megakadályozása**: Válassza ezt a lehetőséget, hogy megakadályozza bármilyen típusú kedvezmény alkalmazását erre a termékre.</span><span class="sxs-lookup"><span data-stu-id="191e9-107">**Prevent all discounts**: Select this option to prevent all types of discounts from being applied to this product.</span></span> <span data-ttu-id="191e9-108">Ilyenek például a kombinációs engedmények, a mennyiségi engedmények és a küszöbérték szerinti engedmények, valamint a POS-felhasználó által az értékesítés során alkalmazott manuális sor- és tranzakciós engedmények.</span><span class="sxs-lookup"><span data-stu-id="191e9-108">This includes promotions such as mix and match, quantity and threshold discounts, as well as manual line and transaction discounts that are applied during a sale by a POS user.</span></span>

<span data-ttu-id="191e9-109">**Manuális engedmények megakadályozása**: Ezzel a beállítással csak a POS-felhasználó által az értékesítés során alkalmazott manuális vagy tranzakciós engedményeket akadályozza meg.</span><span class="sxs-lookup"><span data-stu-id="191e9-109">**Prevent manual discounts**: Select this option to only prevent the manual line or transaction discounts that are applied during a sale by a POS user.</span></span> <span data-ttu-id="191e9-110">Az ezzel a lehetőséggel rendelkező termékek továbbra is jogosultak az olyan promóciókra, mint például a kombinációs engedmények, a mennyiségi és a küszöbérték szerinti engedmények.</span><span class="sxs-lookup"><span data-stu-id="191e9-110">Products with this option selected are still eligible for promotions, such as mix and match and quantity and threshold discounts.</span></span>

<span data-ttu-id="191e9-111">**Megjegyzés:**: Ezek a beállítások nem korlátozzák az árfelülírás műveletet, mivel a beállítás az alapárat határozza meg, és nem minősül kedvezménynek.</span><span class="sxs-lookup"><span data-stu-id="191e9-111">**Note**: These settings do not restrict the price override operation, because that sets the base price and is not treated as a discount.</span></span>  

<span data-ttu-id="191e9-112">[![engedmények megakadályozása mező](./media/prevent discounts.png)](./media/prevent discounts.png)</span><span class="sxs-lookup"><span data-stu-id="191e9-112">[![prevent discounts field](./media/prevent discounts.png)](./media/prevent discounts.png)</span></span>

