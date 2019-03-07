---
title: Tárgyi eszköz áthelyezése leltárba
description: Ez a cikk azt a Magyarországra vonatkozó országspecifikus funkciót írja le, amely lehetővé teszi a tárgyi eszközök készletbe való átvitelét a nettó könyv szerinti értéken. A tárgyi eszköz állapota „Selejtezett” lesz, a nettó könyv szerinti érték pedig 0 (nulla). Ezenkívül a készletben lévő termék mennyisége 1-re van állítva, és az önköltségi ár a tárgyi eszköz nettó könyv szerinti értékére van beállítva.
author: Anasyash
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalAsset
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 274423
ms.search.region: Hungary
ms.author: anasyash
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 77d2f8ada2810fdf1b36b2573e4df01df22a35eb
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "370881"
---
# <a name="move-a-fixed-asset-to-inventory"></a><span data-ttu-id="06cc1-105">Tárgyi eszköz áthelyezése leltárba</span><span class="sxs-lookup"><span data-stu-id="06cc1-105">Move a fixed asset to inventory</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="06cc1-106">Ez a cikk azt a Magyarországra vonatkozó országspecifikus funkciót írja le, amely lehetővé teszi a tárgyi eszközök készletbe való átvitelét a nettó könyv szerinti értéken.</span><span class="sxs-lookup"><span data-stu-id="06cc1-106">This article describes country-specific functionality for Hungary that lets you transfer fixed assets to inventory at the net book value.</span></span> <span data-ttu-id="06cc1-107">A tárgyi eszköz állapota „Selejtezett” lesz, a nettó könyv szerinti érték pedig 0 (nulla).</span><span class="sxs-lookup"><span data-stu-id="06cc1-107">The status of the fixed asset is set to Scrapped, and the net book value is set to 0 (zero).</span></span><span data-ttu-id="06cc1-108"> Ezenkívül a készletben lévő termék mennyisége 1-re van állítva, és az önköltségi ár a tárgyi eszköz nettó könyv szerinti értékére van beállítva.</span><span class="sxs-lookup"><span data-stu-id="06cc1-108"> Additionally, the quantity of a product in inventory is set to 1, and the cost price is set to the net book value of the fixed asset.</span></span>

<span data-ttu-id="06cc1-109">Tárgyi eszközöket helyezhet át a készletbe a nettó könyv szerinti értéken.</span><span class="sxs-lookup"><span data-stu-id="06cc1-109">You can transfer fixed assets to inventory at the net book value.</span></span> <span data-ttu-id="06cc1-110">Az átvitel nyomán a tárgyi eszköz állapota **Selejtezett** lesz, a nettó könyv szerinti érték pedig **0** (nulla).</span><span class="sxs-lookup"><span data-stu-id="06cc1-110">As result of this transfer, the status of the fixed asset is set to **Scrapped**, and the net book value is set to **0** (zero).</span></span> <span data-ttu-id="06cc1-111">Ezenkívül a készletben lévő termék mennyisége **1**-re van állítva, és az önköltségi ár a tárgyi eszköz nettó könyv szerinti értékére van beállítva.</span><span class="sxs-lookup"><span data-stu-id="06cc1-111">Additionally, the quantity of a product in inventory is set to **1**, and the cost price is set to the net book value of the fixed asset.</span></span> <span data-ttu-id="06cc1-112">Használja a szokásos Készlet a tárgyi eszközökhöz naplót arra, hogy átvigye a tárgyi eszközöket a készletbe.</span><span class="sxs-lookup"><span data-stu-id="06cc1-112">Use the standard Inventory to fixed assets journal to transfer fixed assets to inventory.</span></span> 

<span data-ttu-id="06cc1-113">Tárgyi eszköz készletbe való áthelyezéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="06cc1-113">To transfer a fixed asset to inventory, follow these steps.</span></span>

1.  <span data-ttu-id="06cc1-114">Ellenőrizze, hogy a tárgyi eszköz értékcsökkenése fel van-e adva legkésőbb az átvitel napján.</span><span class="sxs-lookup"><span data-stu-id="06cc1-114">Validate that the depreciation for the fixed asset is posted up to the transfer date.</span></span>
2.  <span data-ttu-id="06cc1-115">Hozzon létre egy új készletet a tárgyi eszközök naplójához.</span><span class="sxs-lookup"><span data-stu-id="06cc1-115">Create a new Inventory to fixed assets journal.</span></span>
3.  <span data-ttu-id="06cc1-116">A naplóvonalakon válassza ki az átadandó eszközt és a fogadott terméket.</span><span class="sxs-lookup"><span data-stu-id="06cc1-116">On the journal lines, select the asset to transfer and the product to receive.</span></span>
4.  <span data-ttu-id="06cc1-117">Adjon meg egy negatív mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="06cc1-117">Enter a negative quantity.</span></span>
5.  <span data-ttu-id="06cc1-118">Ellenőrizze, hogy az **Önköltségi ár** mezőben szerepel a **Nettó könyv szerinti** érték.</span><span class="sxs-lookup"><span data-stu-id="06cc1-118">Validate that the **Cost price** field has the **Net book** value.</span></span>
6.  <span data-ttu-id="06cc1-119">Napló feladása.</span><span class="sxs-lookup"><span data-stu-id="06cc1-119">Post the journal.</span></span>
7.  <span data-ttu-id="06cc1-120">Ellenőrizze, hogy a tárgyi eszköz és a készletügyletek helyesen lettek-e létrehozva.</span><span class="sxs-lookup"><span data-stu-id="06cc1-120">Validate that the fixed asset and inventory transactions were created correctly.</span></span>


