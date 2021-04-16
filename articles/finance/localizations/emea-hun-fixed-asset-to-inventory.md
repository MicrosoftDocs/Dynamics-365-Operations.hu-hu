---
title: Tárgyi eszköz áthelyezése leltárba
description: Ez a cikk azt a Magyarországra vonatkozó országspecifikus funkciót írja le, amely lehetővé teszi a tárgyi eszközök készletbe való átvitelét a nettó könyv szerinti értéken. A tárgyi eszköz állapota „Selejtezett” lesz, a nettó könyv szerinti érték pedig 0 (nulla). Ezenkívül a készletben lévő termék mennyisége 1-re van állítva, és az önköltségi ár a tárgyi eszköz nettó könyv szerinti értékére van beállítva.
author: Anasyash
ms.date: 04/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalAsset
audience: Application User
ms.reviewer: kfend
ms.custom: 274423
ms.search.region: Hungary
ms.author: anasyash
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: bdd7b81a2563b86cda5fa04025d958e8b23062ba
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815017"
---
# <a name="move-a-fixed-asset-to-inventory"></a><span data-ttu-id="66039-105">Tárgyi eszköz áthelyezése leltárba</span><span class="sxs-lookup"><span data-stu-id="66039-105">Move a fixed asset to inventory</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="66039-106">Ez a cikk azt a Magyarországra vonatkozó országspecifikus funkciót írja le, amely lehetővé teszi a tárgyi eszközök készletbe való átvitelét a nettó könyv szerinti értéken.</span><span class="sxs-lookup"><span data-stu-id="66039-106">This article describes country-specific functionality for Hungary that lets you transfer fixed assets to inventory at the net book value.</span></span> <span data-ttu-id="66039-107">A tárgyi eszköz állapota „Selejtezett” lesz, a nettó könyv szerinti érték pedig 0 (nulla).</span><span class="sxs-lookup"><span data-stu-id="66039-107">The status of the fixed asset is set to Scrapped, and the net book value is set to 0 (zero).</span></span> <span data-ttu-id="66039-108">Ezenkívül a készletben lévő termék mennyisége 1-re van állítva, és az önköltségi ár a tárgyi eszköz nettó könyv szerinti értékére van beállítva.</span><span class="sxs-lookup"><span data-stu-id="66039-108">Additionally, the quantity of a product in inventory is set to 1, and the cost price is set to the net book value of the fixed asset.</span></span>

<span data-ttu-id="66039-109">Tárgyi eszközöket helyezhet át a készletbe a nettó könyv szerinti értéken.</span><span class="sxs-lookup"><span data-stu-id="66039-109">You can transfer fixed assets to inventory at the net book value.</span></span> <span data-ttu-id="66039-110">Az átvitel nyomán a tárgyi eszköz állapota **Selejtezett** lesz, a nettó könyv szerinti érték pedig **0** (nulla).</span><span class="sxs-lookup"><span data-stu-id="66039-110">As result of this transfer, the status of the fixed asset is set to **Scrapped**, and the net book value is set to **0** (zero).</span></span> <span data-ttu-id="66039-111">Ezenkívül a készletben lévő termék mennyisége **1**-re van állítva, és az önköltségi ár a tárgyi eszköz nettó könyv szerinti értékére van beállítva.</span><span class="sxs-lookup"><span data-stu-id="66039-111">Additionally, the quantity of a product in inventory is set to **1**, and the cost price is set to the net book value of the fixed asset.</span></span> <span data-ttu-id="66039-112">Használja a szokásos Készlet a tárgyi eszközökhöz naplót arra, hogy átvigye a tárgyi eszközöket a készletbe.</span><span class="sxs-lookup"><span data-stu-id="66039-112">Use the standard Inventory to fixed assets journal to transfer fixed assets to inventory.</span></span> 

<span data-ttu-id="66039-113">Tárgyi eszköz készletbe való áthelyezéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="66039-113">To transfer a fixed asset to inventory, follow these steps.</span></span>

1.  <span data-ttu-id="66039-114">Ellenőrizze, hogy a tárgyi eszköz értékcsökkenése fel van-e adva legkésőbb az átvitel napján.</span><span class="sxs-lookup"><span data-stu-id="66039-114">Validate that the depreciation for the fixed asset is posted up to the transfer date.</span></span>
2.  <span data-ttu-id="66039-115">Hozzon létre egy új készletet a tárgyi eszközök naplójához.</span><span class="sxs-lookup"><span data-stu-id="66039-115">Create a new Inventory to fixed assets journal.</span></span>
3.  <span data-ttu-id="66039-116">A naplóvonalakon válassza ki az átadandó eszközt és a fogadott terméket.</span><span class="sxs-lookup"><span data-stu-id="66039-116">On the journal lines, select the asset to transfer and the product to receive.</span></span>
4.  <span data-ttu-id="66039-117">Adjon meg egy negatív mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="66039-117">Enter a negative quantity.</span></span>
5.  <span data-ttu-id="66039-118">Ellenőrizze, hogy az **Önköltségi ár** mezőben szerepel a **Nettó könyv szerinti** érték.</span><span class="sxs-lookup"><span data-stu-id="66039-118">Validate that the **Cost price** field has the **Net book** value.</span></span>
6.  <span data-ttu-id="66039-119">Napló feladása.</span><span class="sxs-lookup"><span data-stu-id="66039-119">Post the journal.</span></span>
7.  <span data-ttu-id="66039-120">Ellenőrizze, hogy a tárgyi eszköz és a készletügyletek helyesen lettek-e létrehozva.</span><span class="sxs-lookup"><span data-stu-id="66039-120">Validate that the fixed asset and inventory transactions were created correctly.</span></span>




[!INCLUDE[footer-include](../../includes/footer-banner.md)]