---
title: Készletcímke számlálása
description: Ez a témakör tájékoztatást ad a címkeszámlálásról, ami akkor használatos, amikor egy raktár tényleges tartalmát hasonlítja össze az aktuális készlettel.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCountTag
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Retail
ms.custom: 11594
ms.assetid: 03772d0e-5c37-454c-ab85-82bc8b60a76d
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: efb555cdfbcf3fd0c10ec0e2abcdbe7f4a90d82d
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3212687"
---
# <a name="inventory-tag-counting"></a><span data-ttu-id="3a6fb-103">Készletcímke számlálása</span><span class="sxs-lookup"><span data-stu-id="3a6fb-103">Inventory tag counting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3a6fb-104">Ez a témakör tájékoztatást ad a címkeszámlálásról, ami akkor használatos, amikor egy raktár tényleges tartalmát hasonlítja össze az aktuális készlettel.</span><span class="sxs-lookup"><span data-stu-id="3a6fb-104">This topic provides information about tag counting, which you use to compare the actual contents of a warehouse with the on-hand inventory.</span></span>

<span data-ttu-id="3a6fb-105">A **Címkeleltár** lapon sorok létrehozásával minden készletcikkre szám formájú - például 1 és 500 közötti - címke kerül.</span><span class="sxs-lookup"><span data-stu-id="3a6fb-105">By creating lines on the **Tag counting** page, you place a tag number on each inventory item, such as a number from 1 to 500.</span></span> <span data-ttu-id="3a6fb-106">A leltár során adja meg a cikkszámot és a mennyiséget a megfelelő címkén.</span><span class="sxs-lookup"><span data-stu-id="3a6fb-106">During the count, you enter the item number and the quantity on a corresponding tag.</span></span> <span data-ttu-id="3a6fb-107">A címke majd használható az alapja a címke számbavételi napló bevitt adatokat.</span><span class="sxs-lookup"><span data-stu-id="3a6fb-107">This tag can then be used as the basis for input in the tag counting journal.</span></span> <span data-ttu-id="3a6fb-108">A címkeleltárnapló feladásakor a címkeleltárnapló-sorok alapján új leltárnapló jön létre a **Számlálás** oldalon.</span><span class="sxs-lookup"><span data-stu-id="3a6fb-108">After you post the tag counting journal, a new counting journal is created on the **Counting** page.</span></span> <span data-ttu-id="3a6fb-109">A címkeleltárnapló feladásakor a címkeleltárnapló-sorok alapján új leltárnapló jön létre.</span><span class="sxs-lookup"><span data-stu-id="3a6fb-109">The new journal is based on the tag counting journal lines that you created.</span></span> <span data-ttu-id="3a6fb-110">Címke száma egy adott készletdimenzió elemek, jelölje be a dimenzió a a **Megjelenítendő dimenzió** látható a címke számbavételi napló létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="3a6fb-110">To tag-count items by a specific inventory dimension, select the dimension on the **Display dimension** page that is displayed when you create the tag counting journal.</span></span> <span data-ttu-id="3a6fb-111">Ha például egy adott raktárban található cikkek száma, jelölje be a **Raktár** négyzet jelölését.</span><span class="sxs-lookup"><span data-stu-id="3a6fb-111">For example, to count items in a specific warehouse, select the **Warehouse** check box.</span></span> <span data-ttu-id="3a6fb-112">Ha a **Cikkek zárolása leltár közben** csúszka a **Készlet- és raktárkezelési paraméterek** négyzet be van jelölve, a cikkek ténylegesen nem frissíthető leltározás közben.</span><span class="sxs-lookup"><span data-stu-id="3a6fb-112">If the **Lock items during count** slider on the **Inventory and warehouse management parameters** page is selected, items can't be physically updated during counting.</span></span> <span data-ttu-id="3a6fb-113">Azonban címkeleltárnaplókban szereplő cikkek a leltár során nincs zárolva.</span><span class="sxs-lookup"><span data-stu-id="3a6fb-113">However, items in tag counting journals aren't locked during counting.</span></span> <span data-ttu-id="3a6fb-114">Nem jönnek létre készlettranzakciók, amíg a címkenaplósorokat át nem vitték egy leltárnaplóba a feladás során.</span><span class="sxs-lookup"><span data-stu-id="3a6fb-114">Inventory transactions aren't created until the tag counting lines are posted and transferred to a counting journal.</span></span> <span data-ttu-id="3a6fb-115">Ha a címkék bevitele véletlenszerűen történik, és szeretné azonosítani a hiányzó címkéket, akkor a sorok rendezéséhez kattintson a **Címke** mezőre.</span><span class="sxs-lookup"><span data-stu-id="3a6fb-115">If tags are entered randomly, and you want to identify missing tags, click the **Tag** column header to sort the lines by tag.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3a6fb-116">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="3a6fb-116">Additional resources</span></span>

[<span data-ttu-id="3a6fb-117">Ciklikus leltározás</span><span class="sxs-lookup"><span data-stu-id="3a6fb-117">Cycle counting</span></span>](../warehousing/cycle-counting.md)
