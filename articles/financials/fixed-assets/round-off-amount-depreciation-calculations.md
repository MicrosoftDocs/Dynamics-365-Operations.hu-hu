---
title: "Az értékcsökkenési számítások kerekítési összegei."
description: "Ez a cikk az Értékcsökkenés kerekítése mezőt taglalja, amely a Könyv beállítása lapon található meg."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBookTable, AssetDepBookTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13931
ms.assetid: faf7db87-046f-41d1-9baf-0df66e373e97
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: ae5c24633a9ce4ce43e213581eb64c8548eecf5d
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="round-off-amount-for-depreciation-calculations"></a><span data-ttu-id="17004-103">Az értékcsökkenési számítások kerekítési összegei.</span><span class="sxs-lookup"><span data-stu-id="17004-103">Round-off amount for depreciation calculations</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="17004-104">Ez a cikk az Értékcsökkenés kerekítése mezőt taglalja, amely a Könyv beállítása lapon található meg.</span><span class="sxs-lookup"><span data-stu-id="17004-104">This article discusses the Round-off depreciation field that is found on the Book setup pages.</span></span>

<span data-ttu-id="17004-105">Az értékcsökkenések kerekítési összegei minden egyes könyvhöz beállíthatók.</span><span class="sxs-lookup"><span data-stu-id="17004-105">Round-off depreciation amounts are set for each book.</span></span> <span data-ttu-id="17004-106">Az értékcsökkenés-kerekítési összegek a tárgyi eszközök értékcsökkenési profiljában használhatóak, amely megmutatja a tárgyi eszköz értékének jövőbeni értékcsökkenését és az értékcsökkenési javaslatot.</span><span class="sxs-lookup"><span data-stu-id="17004-106">Round-off depreciation amounts are used in the fixed asset depreciation profile that shows the future depreciation and value of the fixed asset, and also in depreciation proposals.</span></span> <span data-ttu-id="17004-107">Adja meg a könyvben engedélyezett értékcsökkenés legalacsonyabb összegét.</span><span class="sxs-lookup"><span data-stu-id="17004-107">Enter the lowest depreciation amount that is allowed for the book.</span></span> 

<span data-ttu-id="17004-108">A beállított kerekítéstől függetlenül az utolsó értékcsökkenési időszak értékcsökkenési összege nem kerül kerekítésre.</span><span class="sxs-lookup"><span data-stu-id="17004-108">Regardless of the rounding that is set up, the depreciation amount in the last depreciation period isn't rounded.</span></span> <span data-ttu-id="17004-109">Az utolsó értékcsökkenési időszak végén a tárgyi eszköz értékének nulla kell legyen, vagy a selejtérték összege, ha használ selejtértéket.</span><span class="sxs-lookup"><span data-stu-id="17004-109">At the end of the last depreciation period, the value of the fixed asset must be 0 (zero) or the scrap value, if scrap value is used.</span></span>

### <a name="example"></a><span data-ttu-id="17004-110">Példa</span><span class="sxs-lookup"><span data-stu-id="17004-110">Example</span></span>

<span data-ttu-id="17004-111">A kerekítés nélkül számított értékcsökkenés 2444,44 egység.</span><span class="sxs-lookup"><span data-stu-id="17004-111">Depreciation without rounding is calculated as 2,444.44.</span></span> <span data-ttu-id="17004-112">Ahogy azt az alábbi tábla is mutatja, a javasolt összegek között különbség lehet, attól függően, milyen kerekítés van beállítva.</span><span class="sxs-lookup"><span data-stu-id="17004-112">As the following table shows, the amounts that are suggested vary, depending on how rounding is set up.</span></span>

| <span data-ttu-id="17004-113">Kerekítési mód</span><span class="sxs-lookup"><span data-stu-id="17004-113">Rounding method</span></span> | <span data-ttu-id="17004-114">Értékcsökkenés összege</span><span class="sxs-lookup"><span data-stu-id="17004-114">Depreciation amount</span></span> |
|-----------------|---------------------|
| <span data-ttu-id="17004-115">Kerekítés: 0,1</span><span class="sxs-lookup"><span data-stu-id="17004-115">Rounding 0.1</span></span>    | <span data-ttu-id="17004-116">2444,40</span><span class="sxs-lookup"><span data-stu-id="17004-116">2,444.40</span></span>            |
| <span data-ttu-id="17004-117">Kerekítés: 1,00</span><span class="sxs-lookup"><span data-stu-id="17004-117">Rounding 1.00</span></span>   | <span data-ttu-id="17004-118">2,444.00</span><span class="sxs-lookup"><span data-stu-id="17004-118">2,444.00</span></span>            |
| <span data-ttu-id="17004-119">Kerekítés: 10,00</span><span class="sxs-lookup"><span data-stu-id="17004-119">Rounding 10.00</span></span>  | <span data-ttu-id="17004-120">2,440.00</span><span class="sxs-lookup"><span data-stu-id="17004-120">2,440.00</span></span>            |
| <span data-ttu-id="17004-121">Kerekítés: 100,00</span><span class="sxs-lookup"><span data-stu-id="17004-121">Rounding 100.00</span></span> | <span data-ttu-id="17004-122">2,400.00</span><span class="sxs-lookup"><span data-stu-id="17004-122">2,400.00</span></span>            |





