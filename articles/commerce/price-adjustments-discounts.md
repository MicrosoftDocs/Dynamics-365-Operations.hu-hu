---
title: Ármódosítások és engedmények
description: Ez a cikk ármódosításokkal és engedményekkel kapcsolatban tartalmaz tájékoztatást a Dynamics 365 Commerce rendszerben.
author: scott-tucker
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters, RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: dfaacfa7681258e3b2273083017c0c398d566651
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022828"
---
# <a name="price-adjustments-and-discounts"></a><span data-ttu-id="242f6-103">Ármódosítások és engedmények</span><span class="sxs-lookup"><span data-stu-id="242f6-103">Price adjustments and discounts</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="242f6-104">Ez a cikk ármódosításokkal és engedményekkel kapcsolatban tartalmaz tájékoztatást a Dynamics 365 Commerce rendszerben.</span><span class="sxs-lookup"><span data-stu-id="242f6-104">This article provides information about price adjustments and discounts in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="242f6-105">A Commerce rendszerben módosíthatja a termékek árát, és engedményeket állíthat be egy sortételre vagy pénztári (POS) tranzakcióra, a hívásközpont értékesítési rendelésére, vagy akár egy online megrendelésre is.</span><span class="sxs-lookup"><span data-stu-id="242f6-105">In Commerce, you can make price adjustments to products, and can also set up discounts that are applied to a line item or a transaction at the point of sale (POS), in a call center sales order, or in an online order.</span></span> <span data-ttu-id="242f6-106">Az ármódosításokat és az engedményeket konkrét árcsoportokhoz is hozzákötheti.</span><span class="sxs-lookup"><span data-stu-id="242f6-106">Both price adjustments and discounts can be linked to price groups.</span></span> <span data-ttu-id="242f6-107">Ármódosítások és engedmények esetében is megadhat egyetlen kezdő és záró dátumot vagy egy ismétlődő időtartamot, egy engedménykódot, és néhány további attribútumot.</span><span class="sxs-lookup"><span data-stu-id="242f6-107">For both price adjustments and discounts, you can specify a single start date and end date or a reoccurring period, a discount code, and a few additional attributes.</span></span> 

<span data-ttu-id="242f6-108">Az ármódosítások és engedmények alkalmazhatók termékekre, változatokra vagy kategóriákra is.</span><span class="sxs-lookup"><span data-stu-id="242f6-108">Price adjustments and discounts can be applied to products, variants, or categories.</span></span> <span data-ttu-id="242f6-109">Ha egynél több engedmény vonatkozik egy termékre, a vevő megkaphatja az egyiket, vagy egy kombinált engedményt, az engedmény beállításaitól függően.</span><span class="sxs-lookup"><span data-stu-id="242f6-109">If more than one discount applies to a product, a customer might receive either one of the discounts or a combined discount, depending on the configuration of the discount.</span></span> <span data-ttu-id="242f6-110">A Commerce rendszer automatikusan alkalmazza az engedményt vagy az engedménykombinációt, és a vevő számára a legjobb árat adja.</span><span class="sxs-lookup"><span data-stu-id="242f6-110">Commerce automatically applies the discount or combination of discounts that gives the best price to the customer.</span></span> <span data-ttu-id="242f6-111">Ármódosítás vagy engedmény beállításakor mindenképpen győződjön meg arról, hogy az árcsoportok a megfelelő csatornákhoz, katalógusokhoz, fiókokhoz vagy hűségprogramokhoz vannak hozzárendelve, amelyekre szeretné, hogy vonatkozzon az engedmény.</span><span class="sxs-lookup"><span data-stu-id="242f6-111">When you set up a price adjustment or a discount, be sure to confirm that price groups are assigned to the correct channels, catalogs, affiliations, or loyalty programs that you want the discount to apply to.</span></span> <span data-ttu-id="242f6-112">Továbbá, ha szeretne automatikusan engedmény-azonosítót generálni, akkor a **Commerce paraméterek** oldalon az új engedmény vagy ármódosítás megadása előtt beállíthatja a számsorozatokat.</span><span class="sxs-lookup"><span data-stu-id="242f6-112">Additionally, if you want to automatically generate the discount ID, set up number sequences on the **Commerce parameters** page before you define a new price adjustment or discount.</span></span>

> [!NOTE]
> <span data-ttu-id="242f6-113">Az ármódosítások és az engedmények törölhetők is.</span><span class="sxs-lookup"><span data-stu-id="242f6-113">You can delete a price adjustment or a discount.</span></span> <span data-ttu-id="242f6-114">A statisztikai adatok azonban el fognak veszni.</span><span class="sxs-lookup"><span data-stu-id="242f6-114">However, statistical information will be lost.</span></span>

## <a name="types-of-discounts"></a><span data-ttu-id="242f6-115">Kedvezmények típusai</span><span class="sxs-lookup"><span data-stu-id="242f6-115">Types of discounts</span></span>

<span data-ttu-id="242f6-116">Négyféle engedmény érhető el:</span><span class="sxs-lookup"><span data-stu-id="242f6-116">There are four types of discounts:</span></span>

- <span data-ttu-id="242f6-117">**Egyszerű engedmény** – egy adott százalék vagy összeg.</span><span class="sxs-lookup"><span data-stu-id="242f6-117">**Simple discount** – A single percentage or amount.</span></span>
- <span data-ttu-id="242f6-118">**Mennyiségi engedmény** – A két vagy több termék megvásárlásakor alkalmazott engedmény.</span><span class="sxs-lookup"><span data-stu-id="242f6-118">**Quantity discount** – A discount that is applied when two or more products are purchased.</span></span>
- <span data-ttu-id="242f6-119">**Kombinációs engedmény** – A kombinációs engedmény akkor biztosít engedményt, ha a termékek meghatározott kombinációját vásárolják meg.</span><span class="sxs-lookup"><span data-stu-id="242f6-119">**Mix and match discount** – A discount that is applied when a specific combination of products is purchased.</span></span>
- <span data-ttu-id="242f6-120">**Küszöbérték szerinti engedmény** – Olyan engedmény, amely esetében a tranzakció összege több mint egy meghatározott mennyiség.</span><span class="sxs-lookup"><span data-stu-id="242f6-120">**Threshold discount** – A discount that is applied when the transaction total is more than a specified amount.</span></span>

<span data-ttu-id="242f6-121">Az ármódosításokat és az engedményeket konkrét árcsoportokhoz is hozzárendelheti.</span><span class="sxs-lookup"><span data-stu-id="242f6-121">Both price adjustments and discounts can be associated with price groups.</span></span> <span data-ttu-id="242f6-122">Az árcsoportok ezután társíthatók csatornákhoz, katalógusokhoz, fiókokhoz és hűségprogramokhoz.</span><span class="sxs-lookup"><span data-stu-id="242f6-122">Price groups can then be associated with channels, catalogs, affiliations, and loyalty programs.</span></span>