---
title: "A legyártott cikkek állandó költségeinek amortizálása"
description: "A legyártott cikk állandó költségei a művelet beállítási idejét és az állandó mennyiséggel vagy állandó selejtmennyiséggel megadott összetevőket tükrözik."
author: AndersGirke
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCalcDialog, BOMCalcTable, BOMCalcTrans
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 274503
ms.assetid: 535ab25d-a031-4e8c-84ec-478f2987a1ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: 1f3c837d601877142ac6708287a434f5afe088e6
ms.contentlocale: hu-hu
ms.lasthandoff: 01/17/2018

---

# <a name="amortize-constant-costs-for-a-manufactured-item"></a><span data-ttu-id="bd129-103">A legyártott cikkek állandó költségeinek amortizálása</span><span class="sxs-lookup"><span data-stu-id="bd129-103">Amortize constant costs for a manufactured item</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="bd129-104">A legyártott cikk állandó költségei a művelet beállítási idejét és az állandó mennyiséggel vagy állandó selejtmennyiséggel megadott összetevőket tükrözik.</span><span class="sxs-lookup"><span data-stu-id="bd129-104">A manufactured item’s constant costs reflect the operation setup times and the components that have a constant quantity or a constant scrap amount.</span></span> 

<span data-ttu-id="bd129-105">Ezeket az állandó költségeket a költségszámítási adagméret koncepciójának használatával kell amortizálni a legyártott cikk számított költségében.</span><span class="sxs-lookup"><span data-stu-id="bd129-105">The concept of a costing lot size is used to amortize these constant costs in the calculated cost of a manufactured item.</span></span> <span data-ttu-id="bd129-106">A koncepciónak több neve is van, ilyen például a könyvelési adagméret is.</span><span class="sxs-lookup"><span data-stu-id="bd129-106">This concept has several synonyms, one of which is accounting lot size.</span></span> <span data-ttu-id="bd129-107">Az állandó költségek amortizálási koncepciójának is többféle neve van, egyik ilyen az arányos állandó költség.</span><span class="sxs-lookup"><span data-stu-id="bd129-107">The concept of amortizing constant costs also has several synonyms, one of which is proportional constant costs.</span></span>

<span data-ttu-id="bd129-108">Az anyagjegyzék-számítások a legyártott cikk költségszámítási adagméretét használják.</span><span class="sxs-lookup"><span data-stu-id="bd129-108">The quantity of a costing lot size for a manufactured item is used in a bill of material (BOM) calculation.</span></span> <span data-ttu-id="bd129-109">A mennyiség attól függ, hogyan történik az anyagjegyzék-számítás indítása és végrehajtása, mint azt az alábbiak mutatják:</span><span class="sxs-lookup"><span data-stu-id="bd129-109">The quantity depends on how you initiate and perform the BOM calculation, as illustrated by the following:</span></span>

-   <span data-ttu-id="bd129-110">Alapértelmezett számítási mennyiség cikk anyagjegyzék-számításában – A cikk alapértelmezett rendelési mennyisége készletre a költségszámítási adag méretének alapértelmezéseként viselkedik, de az alapértelmezett érték lehet nagyobb mennyiség is, hogy a cikk rendelési mennyiségének többszörösét tükrözze.</span><span class="sxs-lookup"><span data-stu-id="bd129-110">Default calculation quantity in an item’s BOM calculation − The item’s standard order quantity for inventory acts as the costing lot size, but the default value might be a greater quantity to reflect the item’s order quantity multiple.</span></span> <span data-ttu-id="bd129-111">A cikk alapértelmezett rendelési mennyisége és többszöröse meghatározható az alapértelmezett rendelési beállításoknál vagy a helyspecifikus rendelési beállításokban is.</span><span class="sxs-lookup"><span data-stu-id="bd129-111">The item’s standard order quantity and multiple can be defined within its default order settings or site-specific order settings.</span></span>
-   <span data-ttu-id="bd129-112">Cikk anyagjegyzék-számításában megadott számítási mennyiség – A megadott mennyiség a cikk költségszámítási adagméreteként viselkedik.</span><span class="sxs-lookup"><span data-stu-id="bd129-112">Specified calculation quantity in an item’s BOM calculation − The specified calculation quantity acts as the costing lot size for the item.</span></span> <span data-ttu-id="bd129-113">A számítási mennyiség kezdetben a cikk alapértelmezett rendelési mennyiségét használja, de az alapértelmezett érték manuálisan felülbírálható.</span><span class="sxs-lookup"><span data-stu-id="bd129-113">The calculation quantity initially uses the item’s standard order quantity, but the default value can be manually overridden.</span></span> <span data-ttu-id="bd129-114">A megadott számítási mennyiség a költségszámítási adagméretet jelenti az adott cikkre vonatkozóan, illetve az anyagjegyzéksor típusú gyártású gyártott összetevőkre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="bd129-114">The specified calculation quantity represents the costing lot size for the specified item, and for manufactured components that have a BOM line type of production.</span></span> <span data-ttu-id="bd129-115">Ennek oka az a feltételezés, hogy az összetevő előállítása a pontos mennyiségben történik.</span><span class="sxs-lookup"><span data-stu-id="bd129-115">This is because it is assumed that the component will be produced to the exact quantity.</span></span> <span data-ttu-id="bd129-116">A költségszámítási adagméret az egyéb legyártott összetevőkre vonatkozóan anyagjegyzéksor típus esetén az alapértelmezett rendelési mennyiségnek felel meg.</span><span class="sxs-lookup"><span data-stu-id="bd129-116">The costing lot size for other manufactured components that have a BOM line type of item will reflect their standard order quantity.</span></span>
-   <span data-ttu-id="bd129-117">Adott rendelésre gyártási mennyiség cikk anyagjegyzék-számításában – a megadott számítási mennyiség viselkedik költségszámítási adagméretként a cikk és gyártott összetevői szempontjából, amikor az anyagjegyzék-számítások rendelésre gyártási alábontási módot alkalmaznak.</span><span class="sxs-lookup"><span data-stu-id="bd129-117">Specified make-to-order calculation quantity in an item’s BOM calculation − The specified calculation quantity acts as the costing lot size for the item and its manufactured components when BOM calculations use a make-to-order explosion mode.</span></span> <span data-ttu-id="bd129-118">A feltételezés az, hogy az összetevők előállítása ugyanúgy a pontos mennyiségben történik, mint a termelési típusú anyagjegyzéksorok esetében.</span><span class="sxs-lookup"><span data-stu-id="bd129-118">It is assumed that the manufactured components will be produced to the exact quantity, just like a manufactured component that has a BOM line type of production.</span></span>
-   <span data-ttu-id="bd129-119">Megadott számítási mennyiség rendelésspecifikus anyagjegyzék-számításban – rendelésspecifikus anyagjegyzék-számítást beszerzési rendelés, értékesítési ajánlat vagy szervizrendelés sorára vonatkozóan lehet végezni.</span><span class="sxs-lookup"><span data-stu-id="bd129-119">Specified calculation quantity in an order-specific BOM calculation − An order-specific BOM calculation can be performed for a line item on a sales order, sales quotation, or service order.</span></span> <span data-ttu-id="bd129-120">A megadott számítási mennyiség a kiindulási sor mennyiségét veszi fel, de az alapértelmezett mennyiség felülbírálható.</span><span class="sxs-lookup"><span data-stu-id="bd129-120">The specified calculation quantity uses the quantity on the originating line item, but the default quantity can be overridden.</span></span> <span data-ttu-id="bd129-121">Be lehet állítani, hogy a rendelésspecifikus anyagjegyzék-számítás rendelésre készítési vagy többszintű alábontási módot használjon.</span><span class="sxs-lookup"><span data-stu-id="bd129-121">You can select whether the order-specific BOM calculation uses a make-to-order or multilevel explosion mode.</span></span>

<span data-ttu-id="bd129-122">A legyártott cikk amortizált állandó költségeinek számított mennyiségét nevezik költségnek.</span><span class="sxs-lookup"><span data-stu-id="bd129-122">The calculated amount of a manufactured item’s amortized constant costs is termed charges.</span></span>






