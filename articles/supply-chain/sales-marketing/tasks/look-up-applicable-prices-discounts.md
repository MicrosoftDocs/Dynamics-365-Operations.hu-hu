---
title: Alkalmazandó árak és engedmények keresése
description: Ez az eljárás bemutatja, hogyan lehet árat és/vagy az engedményt találni egy termékhez, amely jelenleg érvényes egy meghatározott vevőre, értékesítési rendelés létrehozása nélkül.
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ba95e651898da0e0fbd1221f61436ffac59db09e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "359865"
---
# <a name="look-up-applicable-prices-and-discounts"></a><span data-ttu-id="6e059-103">Alkalmazandó árak és engedmények keresése</span><span class="sxs-lookup"><span data-stu-id="6e059-103">Look up applicable prices and discounts</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6e059-104">Ez az eljárás bemutatja, hogyan lehet árat és/vagy az engedményt találni egy termékhez, amely jelenleg érvényes egy meghatározott vevőre, értékesítési rendelés létrehozása nélkül.</span><span class="sxs-lookup"><span data-stu-id="6e059-104">This procedure shows how to find the price and/or discount for a product which is currently valid for a specific customer, without creating a sales order.</span></span> <span data-ttu-id="6e059-105">Az eljárás végigvezet egy adott példán, és a szükséges értékek kiválasztásához követnie kell a példában az USMF bemutatóvállalat használatát.</span><span class="sxs-lookup"><span data-stu-id="6e059-105">The procedure walks through a specific example, and you need follow the example using the USMF demo company in order to select the necessary values.</span></span>


## <a name="find-the-applicable-price"></a><span data-ttu-id="6e059-106">A vonatkozó ár keresése</span><span class="sxs-lookup"><span data-stu-id="6e059-106">Find the applicable price</span></span>
1. <span data-ttu-id="6e059-107">Ugorjon az Értékesítés és marketing > Árak és engedmények > Árak keresése elemre.</span><span class="sxs-lookup"><span data-stu-id="6e059-107">Go to Sales and marketing > Prices and discounts > Find prices.</span></span>
2. <span data-ttu-id="6e059-108">A Vevői számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="6e059-108">In the Customer account field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="6e059-109">Az US-001 vevő megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="6e059-109">In the list, find and select customer US-001.</span></span>
4. <span data-ttu-id="6e059-110">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="6e059-110">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="6e059-111">A Cikkszám mezőbe írja be az „T0004” értéket.</span><span class="sxs-lookup"><span data-stu-id="6e059-111">In the Item number field, type 'T0004'.</span></span>
    * <span data-ttu-id="6e059-112">Alapértelmezés szerint a Mennyiség mező értéke 1.</span><span class="sxs-lookup"><span data-stu-id="6e059-112">By default, the Quantity field is set to 1.</span></span> <span data-ttu-id="6e059-113">Azonban ha ismeri a rendelés méretét, amelyet a vevő a szóban forgó termékre le kíván adni, akkor inkább adja meg ezt az értéket.</span><span class="sxs-lookup"><span data-stu-id="6e059-113">However, if you know the size of the order that the customer intends to place for the product in question, then enter this value instead.</span></span> <span data-ttu-id="6e059-114">Ez az információ akkor releváns, ha a vevővel való kereskedelmi megállapodások mennyiség szüneteket tartalmaznak, ha például a termék ára függ a minimális beszerzett mennyiségtől.</span><span class="sxs-lookup"><span data-stu-id="6e059-114">This information is relevant if the trade agreements with the customer have quantity breaks, that is, the product's price depends on the minimum quantity purchased.</span></span>  
6. <span data-ttu-id="6e059-115">A Dátum mezőben adjon meg egy dátumot, amikor a vevő várhatóan rendelést ad le.</span><span class="sxs-lookup"><span data-stu-id="6e059-115">In the Date field, enter a date for when the customer expects to place an order.</span></span> 
    * <span data-ttu-id="6e059-116">A dátum lehet az adott nap, vagy bármilyen jövőbeni dátum.</span><span class="sxs-lookup"><span data-stu-id="6e059-116">The date can be today's date or any date in the future.</span></span>  
    * <span data-ttu-id="6e059-117">A rendszer most visszaadja az árat, amely a kiválasztott termékre érvényes, ha a megadott mennyiséggel vásárolja meg a kiválasztott vevő a kiválasztott dátumon.</span><span class="sxs-lookup"><span data-stu-id="6e059-117">The system now returns the price that is valid for the selected product when bought by the selected customer on the selected date with a specified quantity.</span></span> <span data-ttu-id="6e059-118">Ebben a példában ha az US-001 vevő vásárol egy egységnyi T0004 terméket a mai napon, az egységenként 350 CAD-ba kerül.</span><span class="sxs-lookup"><span data-stu-id="6e059-118">In this example, if the customer US-001 bought 1 unit of product T0004 today, they would be charged 350 CAD a unit.</span></span> <span data-ttu-id="6e059-119">Ez az ár a vevővel között meglévő és aktív kereskedelmi megállapodásból származik.</span><span class="sxs-lookup"><span data-stu-id="6e059-119">This price comes from an existing and active trade agreement with the customer.</span></span>      <span data-ttu-id="6e059-120">Az oldalon az egyéb mezők további részleteket tartalmaznak a termék árakra és költségekre vonatkozóan (ha az alapterméknél van megadva), és a számított nyereségességet.</span><span class="sxs-lookup"><span data-stu-id="6e059-120">Other fields on the page provide more details about the product price and product cost (if set up on the product master), and calculated profitability.</span></span>  
    * <span data-ttu-id="6e059-121">Ha a Kapcsolódó termékváltozatok megjelenítése beállítás be van jelölve, az azt jelenti, hogy további kereskedelmi megállapodások léteznek a termékváltozatokra.</span><span class="sxs-lookup"><span data-stu-id="6e059-121">If the Show related product variants option is selected, it means that there are additional trade agreements for product's variants.</span></span>  
7. <span data-ttu-id="6e059-122">Jelölje be a Kapcsolódó termékváltozatok megjelenítése jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="6e059-122">Click the Show related product variants checkbox.</span></span>
    * <span data-ttu-id="6e059-123">Megjelenik a termékváltozatok listája, a dimenziókkal kapcsolatos információkkal együtt.</span><span class="sxs-lookup"><span data-stu-id="6e059-123">A list of the product variants is shown, with information about their dimensions.</span></span>  
8. <span data-ttu-id="6e059-124">A listában jelölje be a Fehér színt képviselő sort.</span><span class="sxs-lookup"><span data-stu-id="6e059-124">In the list, mark the line representing color White.</span></span>
    * <span data-ttu-id="6e059-125">Ne feledje, hogy a termék ára most eltér a korábban megjelenítettől, amikor nem dimenzió szerint volt megadva.</span><span class="sxs-lookup"><span data-stu-id="6e059-125">Notice, that the product price is now different from the one displayed previously when it was not specified per dimension.</span></span>  
9. <span data-ttu-id="6e059-126">Kattintson az Eladási árak megtekintése gombra.</span><span class="sxs-lookup"><span data-stu-id="6e059-126">Click View sales prices.</span></span>
    * <span data-ttu-id="6e059-127">Az Ár (eladási) oldal megjeleníti a termékre vonatkozó kereskedelmi megállapodásokat, a változatokkal együtt.</span><span class="sxs-lookup"><span data-stu-id="6e059-127">The Price (sales) page displays all the trade agreements applicable to the product, including its variants.</span></span>  
10. <span data-ttu-id="6e059-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6e059-128">Close the page.</span></span>

## <a name="find-the-applicable-discount"></a><span data-ttu-id="6e059-129">A vonatkozó engedmény keresése</span><span class="sxs-lookup"><span data-stu-id="6e059-129">Find the applicable discount</span></span>
    * <span data-ttu-id="6e059-130">Ellenőrizze, hogy a Vevői számla mező az US-001 vevőszámot tartalmazza-e.</span><span class="sxs-lookup"><span data-stu-id="6e059-130">Make sure the Customer account field contains customer number US-001</span></span>   
1. <span data-ttu-id="6e059-131">A Cikkszám mezőbe írja be az „T0012” értéket.</span><span class="sxs-lookup"><span data-stu-id="6e059-131">In the Item number field, type 'T0012'.</span></span>
    * <span data-ttu-id="6e059-132">Győződjön meg arról, hogy a Mennyiség mező értéke 1.</span><span class="sxs-lookup"><span data-stu-id="6e059-132">Make sure the Quantity field is set to 1.</span></span>  
    * <span data-ttu-id="6e059-133">A T0012 termékre vonatkozó következő árképzési adatok egy vagy több kereskedelmi megállapodásból származnak: az egységár 1000 CAD, és a sorengedmény százalékos értéke 5.</span><span class="sxs-lookup"><span data-stu-id="6e059-133">The following pricing details shown for product T0012 come from one or more trade agreements: The unit price is 1,000 CAD and the discount percentage is 5.</span></span>  
2. <span data-ttu-id="6e059-134">Állítsa a mennyiséget 20 értékre.</span><span class="sxs-lookup"><span data-stu-id="6e059-134">Set Quantity to '20'.</span></span>
    * <span data-ttu-id="6e059-135">A nagyobb rendelési mennyiség hatására a sorengedmény, amelyet a rendszer a vevőnek ajánl, 5-ről 7 százalékra változik.</span><span class="sxs-lookup"><span data-stu-id="6e059-135">The increased order quantity causes the line discount that will be offered to the customer to change from 5 to 7 percent.</span></span>  
    * <span data-ttu-id="6e059-136">A Nettó összeget az egységár, az engedmény és a teljes mennyiség alapján számítja ki.</span><span class="sxs-lookup"><span data-stu-id="6e059-136">The Net amount is calculated based on the unit price, discount and the total quantity.</span></span>  
3. <span data-ttu-id="6e059-137">Kattintson a Sorengedmény megtekintése gombra.</span><span class="sxs-lookup"><span data-stu-id="6e059-137">Click View line discount.</span></span>
    * <span data-ttu-id="6e059-138">A T0012 termékhez két sorkedvezmény-megállapodás tartozik, 5 százalék engedményt adva egy rendelési sor mennyiséghez 1-től 10-re, illetve 10 felett rendelési mennyiségre vonatkozóan 7 százalékos engedményt.</span><span class="sxs-lookup"><span data-stu-id="6e059-138">There are two line discount agreements for product T0012, specifying a 5 percent discount for an order line quantity from 1 to 10, and 7 percent discount for order quantities above 10.</span></span> <span data-ttu-id="6e059-139">Vegye figyelembe, hogy az engedmények egy termékcsoportra vonatkoznak, ebben a példában a 01 csoportkódra, amelynek a T0012 termék tagja.</span><span class="sxs-lookup"><span data-stu-id="6e059-139">Note that the discounts are applied to a group of products, in this example, Group code 01, of which product T0012 is a member.</span></span>  
4. <span data-ttu-id="6e059-140">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6e059-140">Close the page.</span></span>

