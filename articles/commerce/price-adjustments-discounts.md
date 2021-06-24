---
title: Ármódosítások és engedmények
description: Ez a cikk ármódosításokkal és engedményekkel kapcsolatban tartalmaz tájékoztatást a Dynamics 365 Commerce rendszerben.
author: scott-tucker
ms.date: 06/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailParameters, RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 44c03ae0a04d648e788a72d8f6dcc3671c5736c7
ms.sourcegitcommit: 7c9d6be464db058511df9cb6ba162d21dc0554e8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/11/2021
ms.locfileid: "6240942"
---
# <a name="price-adjustments-and-discounts"></a><span data-ttu-id="0d104-103">Ármódosítások és engedmények</span><span class="sxs-lookup"><span data-stu-id="0d104-103">Price adjustments and discounts</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0d104-104">Ez a cikk ármódosításokkal és engedményekkel kapcsolatban tartalmaz tájékoztatást a Dynamics 365 Commerce rendszerben.</span><span class="sxs-lookup"><span data-stu-id="0d104-104">This article provides information about price adjustments and discounts in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="0d104-105">A Commerce rendszerben módosíthatja a termékek árát, és engedményeket állíthat be egy sortételre vagy pénztári (POS) tranzakcióra, a hívásközpont értékesítési rendelésére, vagy akár egy online megrendelésre is.</span><span class="sxs-lookup"><span data-stu-id="0d104-105">In Commerce, you can make price adjustments to products, and can also set up discounts that are applied to a line item or a transaction at the point of sale (POS), in a call center sales order, or in an online order.</span></span> <span data-ttu-id="0d104-106">Az ármódosításokat és az engedményeket konkrét árcsoportokhoz is hozzákötheti.</span><span class="sxs-lookup"><span data-stu-id="0d104-106">Both price adjustments and discounts can be linked to price groups.</span></span> <span data-ttu-id="0d104-107">Ármódosítások és engedmények esetében is megadhat egyetlen kezdő és záró dátumot vagy egy ismétlődő időtartamot, egy engedménykódot, és néhány további attribútumot.</span><span class="sxs-lookup"><span data-stu-id="0d104-107">For both price adjustments and discounts, you can specify a single start date and end date or a reoccurring period, a discount code, and a few additional attributes.</span></span> 

<span data-ttu-id="0d104-108">Az ármódosítások és engedmények alkalmazhatók termékekre, változatokra vagy kategóriákra is.</span><span class="sxs-lookup"><span data-stu-id="0d104-108">Price adjustments and discounts can be applied to products, variants, or categories.</span></span> <span data-ttu-id="0d104-109">Ha egynél több engedmény vonatkozik egy termékre, a vevő megkaphatja az egyiket, vagy egy kombinált engedményt, az engedmény beállításaitól függően.</span><span class="sxs-lookup"><span data-stu-id="0d104-109">If more than one discount applies to a product, a customer might receive either one of the discounts or a combined discount, depending on the configuration of the discount.</span></span> <span data-ttu-id="0d104-110">A Commerce rendszer automatikusan alkalmazza az engedményt vagy az engedménykombinációt, és a vevő számára a legjobb árat adja.</span><span class="sxs-lookup"><span data-stu-id="0d104-110">Commerce automatically applies the discount or combination of discounts that gives the best price to the customer.</span></span> <span data-ttu-id="0d104-111">Ármódosítás vagy engedmény beállításakor mindenképpen győződjön meg arról, hogy az árcsoportok a megfelelő csatornákhoz, katalógusokhoz, fiókokhoz vagy hűségprogramokhoz vannak hozzárendelve, amelyekre szeretné, hogy vonatkozzon az engedmény.</span><span class="sxs-lookup"><span data-stu-id="0d104-111">When you set up a price adjustment or a discount, be sure to confirm that price groups are assigned to the correct channels, catalogs, affiliations, or loyalty programs that you want the discount to apply to.</span></span> <span data-ttu-id="0d104-112">Továbbá, ha szeretne automatikusan engedmény-azonosítót generálni, akkor a **Commerce paraméterek** oldalon az új engedmény vagy ármódosítás megadása előtt beállíthatja a számsorozatokat.</span><span class="sxs-lookup"><span data-stu-id="0d104-112">Additionally, if you want to automatically generate the discount ID, set up number sequences on the **Commerce parameters** page before you define a new price adjustment or discount.</span></span>

> [!NOTE]
> <span data-ttu-id="0d104-113">Az ármódosítások és az engedmények törölhetők is.</span><span class="sxs-lookup"><span data-stu-id="0d104-113">You can delete a price adjustment or a discount.</span></span> <span data-ttu-id="0d104-114">A statisztikai adatok azonban el fognak veszni.</span><span class="sxs-lookup"><span data-stu-id="0d104-114">However, statistical information will be lost.</span></span>

## <a name="types-of-discounts"></a><span data-ttu-id="0d104-115">Kedvezmények típusai</span><span class="sxs-lookup"><span data-stu-id="0d104-115">Types of discounts</span></span>

<span data-ttu-id="0d104-116">Számos típusú engedmény érhető el:</span><span class="sxs-lookup"><span data-stu-id="0d104-116">There are many types of discounts:</span></span>

- <span data-ttu-id="0d104-117">**Egyszerű engedmény** – egy adott százalék vagy összeg.</span><span class="sxs-lookup"><span data-stu-id="0d104-117">**Simple discount** – A single percentage or amount.</span></span>
- <span data-ttu-id="0d104-118">**Mennyiségi engedmény** – A két vagy több termék megvásárlásakor alkalmazott engedmény.</span><span class="sxs-lookup"><span data-stu-id="0d104-118">**Quantity discount** – A discount that is applied when two or more products are purchased.</span></span>
- <span data-ttu-id="0d104-119">**Kombinációs engedmény** – A kombinációs engedmény akkor biztosít engedményt, ha a termékek meghatározott kombinációját vásárolják meg.</span><span class="sxs-lookup"><span data-stu-id="0d104-119">**Mix and match discount** – A discount that is applied when a specific combination of products is purchased.</span></span>
- <span data-ttu-id="0d104-120">**Küszöbérték szerinti engedmény** – Olyan engedmény, amely esetében a tranzakció összege több mint egy meghatározott mennyiség.</span><span class="sxs-lookup"><span data-stu-id="0d104-120">**Threshold discount** – A discount that is applied when the transaction total is more than a specified amount.</span></span>
- <span data-ttu-id="0d104-121">**Fizetőeszköz-alapú engedmény** – Olyan engedmény, amely akkor kerül alkalmazásra, ha a tranzakció összege meghaladja a megadott összeget, és egy adott fizetési típus (például készpénz, hitel vagy betéti kártya) kerül a fizetéshez.</span><span class="sxs-lookup"><span data-stu-id="0d104-121">**Tender-based discount** – A discount that is applied when the transaction total is more than a specified amount and a specific payment type (for example, cash, credit, or debit card) is used for payment.</span></span>
- <span data-ttu-id="0d104-122">**Szállítási engedmény** – Olyan engedmény, amely akkor kerül alkalmazásra, ha a tranzakció összege meghaladja a megadott összeget, és a rendelésen egy adott szállítási mód (például kétnapos szállítás vagy egynapos szállítás) kerül alkalmazásra.</span><span class="sxs-lookup"><span data-stu-id="0d104-122">**Shipping discount** – A discount that is applied when the transaction total is more than a specified amount and a specific mode of delivery (for example, two day shipping or overnight shipping) is used on the order.</span></span>

<span data-ttu-id="0d104-123">Az ármódosításokat és az engedményeket konkrét árcsoportokhoz is hozzárendelheti.</span><span class="sxs-lookup"><span data-stu-id="0d104-123">Both price adjustments and discounts can be associated with price groups.</span></span> <span data-ttu-id="0d104-124">Az árcsoportok ezután társíthatók csatornákhoz, katalógusokhoz, fiókokhoz és hűségprogramokhoz.</span><span class="sxs-lookup"><span data-stu-id="0d104-124">Price groups can then be associated with channels, catalogs, affiliations, and loyalty programs.</span></span>

> [!NOTE]
> <span data-ttu-id="0d104-125">A kombinációs engedménynek és a küszöbérték-engedménynek vannak „Kedvezményre nem jogosult termékek számolása” és „Kedvezményre nem jogosult termékek számolása a küszöbbel szemben” tulajdonságaik.</span><span class="sxs-lookup"><span data-stu-id="0d104-125">The mix and match discount and the threshold discount have properties named "Count non-discountable products" and "Count non-discountable products towards threshold", respectively.</span></span> <span data-ttu-id="0d104-126">Ha ezek a tulajdonságok engedélyezve vannak, akkor lehet olyan cikk esetében is lehetséges érvényesíteni a tranzakciót, amelyik nem jogosult az engedményre, de a nem jogosult cikk nem kap engedményt.</span><span class="sxs-lookup"><span data-stu-id="0d104-126">If these properties are enabled, an item that is not eligible for any discount can still help qualify a transaction for the discount, but the ineligible item will not get the discount.</span></span> 
> 
> <span data-ttu-id="0d104-127">Ha például két sorból – A és B – áll a kombinációs engedmény, ahol a vevőnek 10%-os kedvezményt kell kapnia mindkét cikkből, de az A cikknél be van jelölve az "Összes engedmény megakadályozása" konfiguráció, akkor ez általában megakadályozza, hogy az A cikk beleszámítson az engedménybe.</span><span class="sxs-lookup"><span data-stu-id="0d104-127">For example, if you create a mix and match discount with two lines, A and B, where a customer should get 10% off on both items, but item A has the configuration "Prevent all discounts" checked, then this would typically stop item A from being included in the discount.</span></span> <span data-ttu-id="0d104-128">Ha viszont engedélyezve van a „Kedvezményre nem jogosult termékek számolása” tulajdonság, az "A" cikk felhasználható a kombinációs engedményre való jogosultságra, de a 10% engedmény csak a B cikkre lesz érvényes. Hasonló logika vonatkozik a küszöbérték-engedményre is.</span><span class="sxs-lookup"><span data-stu-id="0d104-128">However, if the "Count non-discountable products" property is enabled, then item A can be used to qualify for the mix and match discount, but the 10% discount will only be applied to item B. Similar logic applies to the threshold discount.</span></span> 
>
> <span data-ttu-id="0d104-129">A "Kedvezményre nem jogosult termékek számolása a küszöbbel szemben" tulajdonság azonban további képességeket is képes alkalmazni a kombinációs engedmények "Kedvezményre nem jogosult termékek számolása" tulajdonsághoz képest.</span><span class="sxs-lookup"><span data-stu-id="0d104-129">However, the property "Count non-discountable products towards threshold" has an additional capability when compared to the "Count non-discountable products" property of the mix and match discounts.</span></span> <span data-ttu-id="0d104-130">Ha engedélyezve van a küszöbérték-engedmény, és van olyan cikk, amelynek van olyan engedménye, amely megakadályozza, hogy a cikk más engedményeket kapjon, akkor az adott cikkért fizetett ár megfelelő lesz a küszöbértéknek, de ez a cikk nem fog kapni további engedményt.</span><span class="sxs-lookup"><span data-stu-id="0d104-130">If the threshold discount is enabled, and if there is an item that has an existing discount which would prevent the item from any other discounts, then  the price paid for this item would qualify towards meeting the threshold, but this item will not get the additional discount.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
