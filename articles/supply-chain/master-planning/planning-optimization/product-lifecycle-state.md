---
title: Bizonyos termékéletciklus-állapotokkal rendelkező termékek kizárása
description: Ez a témakör azt mutatja be, hogyan lehet kizárni a termékeket az életciklus-állapotuk alapján a Tervezési optimalizálás funkció használatakor.
author: ChristianRytt
manager: tfehr
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-11-13
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: a1e0c734db763ffa69e2d6540a07d5fa04c22ea1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227818"
---
# <a name="exclude-products-that-have-specific-product-lifecycle-states"></a><span data-ttu-id="1c15b-103">Bizonyos termékéletciklus-állapotokkal rendelkező termékek kizárása</span><span class="sxs-lookup"><span data-stu-id="1c15b-103">Exclude products that have specific product lifecycle states</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1c15b-104">A kiadott termékek és a kiadott verziók tartalmazzák a **Termékéletciklus-állapot** mezőt.</span><span class="sxs-lookup"><span data-stu-id="1c15b-104">Released products and released product versions include a **Product lifecycle state** field.</span></span> <span data-ttu-id="1c15b-105">Ez a mező lehetővé teszi többek között az alaptervezés során figyelembe veendő termékek szabályozását.</span><span class="sxs-lookup"><span data-stu-id="1c15b-105">This field lets you control, among other things, which products are included during master planning.</span></span> <span data-ttu-id="1c15b-106">Az életciklus-állapotokat a **Termékinformáció-kezelés \> Beállítása \> Termékéletciklus-állapot** részre lépve lehet hozzáadni, eltávolítani és szerkeszteni.</span><span class="sxs-lookup"><span data-stu-id="1c15b-106">You can add, remove, and edit lifecycle states as required by going to **Product information management \> Setup \> Product lifecycle state**.</span></span> <span data-ttu-id="1c15b-107">Állítsa az **Aktív a tervezéshez** beállítást minden egyes termékéletciklus-állapot esetében *Igen* értékre, ha az alaptervezés során figyelembe kell venni az ilyen állapotú termékeket.</span><span class="sxs-lookup"><span data-stu-id="1c15b-107">For each product lifecycle state, set the **Is active for planning** option to *Yes* if products that have that state should be included during master planning.</span></span> <span data-ttu-id="1c15b-108">Ha a beállítás értéke *Nem*, akkor a program kizárja a társított termékeket és változatokat az alaptervezésből és minden számításból az anyagjegyzék szintjén.</span><span class="sxs-lookup"><span data-stu-id="1c15b-108">When the option is set to *No*, the associated products and variants will be excluded from all master planning and all calculations at the bill of materials (BOM) level.</span></span>

<span data-ttu-id="1c15b-109">Azokat a kiadott termékek és változatok, amelyeknél a **Termékéletciklus-állapot** mező üresen marad, úgy kell tekinteni, mintha olyan termékéletciklus-állapottal rendelkeznének, ahol az **Aktív a tervezéshez** beállítás a *Igen* értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="1c15b-109">Released products and variants where the **Product lifecycle state** field is left blank are treated as though they have a product lifecycle state where the **Is active for planning** option is set to *Yes*.</span></span> <span data-ttu-id="1c15b-110">Más szóval ezek az alaptervezés során szerepelni fognak.</span><span class="sxs-lookup"><span data-stu-id="1c15b-110">In other words, they will be included during master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="1c15b-111">A szükségtelen ellátási javaslatok elkerüléséhez kifejezetten ajánljuk, hogy az összes elavult kiadású terméket és változatot olyan termékéletciklus-állapottal társítsa, ahol az **Aktív a tervezéshez** beállítás esetében a *Nem* érték van beállítva.</span><span class="sxs-lookup"><span data-stu-id="1c15b-111">To help avoid unnecessary supply suggestions, we strongly recommend that you associate all obsolete released products and variants with a product lifecycle state where the **Is active for planning** option is set to *No*.</span></span> <span data-ttu-id="1c15b-112">Ez a megközelítés különösen akkor fontos, ha olyan termékkonfiguráció-változatokkal dolgozik, amelyek nem használhatók fel újra, mert ez segít elkerülni a hulladékot.</span><span class="sxs-lookup"><span data-stu-id="1c15b-112">This approach is especially important when you work with product configuration variants that aren't reusable, because it will help prevent waste.</span></span>

## <a name="related-resources"></a><span data-ttu-id="1c15b-113">Kapcsolódó erőforrások</span><span class="sxs-lookup"><span data-stu-id="1c15b-113">Related resources</span></span>

<span data-ttu-id="1c15b-114">A termékéletciklus-állapotokkal kapcsolatos további tudnivalókat lásd: [Termékéletciklus-állapotok áttekintése](../../pim/product-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="1c15b-114">For more information about product lifecycle states, see [Product lifecycle state overview](../../pim/product-lifecycle.md).</span></span>

<span data-ttu-id="1c15b-115">Részletes információkért arról, hogyan lehet a termékéletciklus-állapotokat termékek kizárására használni az alaptervezésből és az anyagjegyzékszint-számításból, lásd: [Termékéletciklus-állapot létrehozása termékek kizárására az alaptervezésből](../../pim/tasks/exclude-products-master-planning.md).</span><span class="sxs-lookup"><span data-stu-id="1c15b-115">For detailed information that includes steps for using product lifecycle states to exclude products from master planning and BOM-level calculations, see [Create a product lifecycle state to exclude products from Master planning](../../pim/tasks/exclude-products-master-planning.md).</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]