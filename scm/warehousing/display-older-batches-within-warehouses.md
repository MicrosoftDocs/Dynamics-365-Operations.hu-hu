---
title: "Raktáron belüli régebbi kötegek megjelenítésének konfigurálása mobileszközön"
description: "Ez a témakör leírja, hogy miként állítható be egy mobileszköz, hogy megjelenítse azoknak a helyeknek a listáját, ahol régebbi kötegek szerepelnek, mint egy munkasor jelenlegi helye."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 3e9386f6da7b8bdc1cbb817a78f72c225cbaa9bc
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---

# <a name="configure-display-older-batches-within-warehouse-on-a-mobile-device"></a><span data-ttu-id="286af-103">Raktáron belüli régebbi kötegek megjelenítésének konfigurálása mobileszközön</span><span class="sxs-lookup"><span data-stu-id="286af-103">Configure Display older batches within warehouse on a mobile device</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="286af-104">A **Raktáron belüli régebbi kötegek megjelenítése** konfiguráció lehetővé teszi azon helyek listájának megjelenítését, ahol olyan kötegek szerepelnek, amelyek régebbiek a munkasor jelenlegi helyénél.</span><span class="sxs-lookup"><span data-stu-id="286af-104">The **Display older batches within warehouse** configuration lets you display a list of locations with batches older than the current location of the work line.</span></span> <span data-ttu-id="286af-105">A megjelenített helyek listája tartalmazza a régebbi kötegekkel kapcsolatos információkat, az egyes tételek lejárati dátumával és fizikai készletével együtt.</span><span class="sxs-lookup"><span data-stu-id="286af-105">The list of locations that are displayed includes information about the older batches in the location with the expiration date and the physical inventory of each batch.</span></span> <span data-ttu-id="286af-106">Kiválaszthatja, hogy a kitárolás új helyről történjen, vagy folytathatja a kitárolást az aktuális helyről is.</span><span class="sxs-lookup"><span data-stu-id="286af-106">You can choose to pick from a new location or to continue picking from the current location.</span></span> 
- <span data-ttu-id="286af-107">Kitárolás új helyről – Ha új helyet választ ki a kitárolásra, akkor az aktuális munkasor frissül az új hely használatával, és a munka az új helyszínen a szokásos módon folytatódik.</span><span class="sxs-lookup"><span data-stu-id="286af-107">Pick from a new location - If you select a new location to pick from, the  current work line will be updated to use the new location and work will continue as usual with the new location.</span></span> <span data-ttu-id="286af-108">Ahhoz, hogy az új hely érvényes legyen, elegendő mennyiséggel kell rendelkeznie a teljes munkasorra kiterjedően.</span><span class="sxs-lookup"><span data-stu-id="286af-108">For the new location to be valid, it must have enough available quantity for the whole work line.</span></span> <span data-ttu-id="286af-109">Ha nem érhető el a szükséges mennyiség, akkor a munkasor nem frissül, és a lista jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="286af-109">If the required quantity is not available, the work line will not be updated, and the list will display.</span></span> 
- <span data-ttu-id="286af-110">Kitárolás folytatása a jelenlegi helyről – Ha folytatja az aktuális munkaterület használatát, akkor a munkasor mennyiségeit továbbra is az eredeti helyről tárolja ki a rendszer.</span><span class="sxs-lookup"><span data-stu-id="286af-110">Continue picking from the current location - If you continue with the current work line location, the quantities for the work line will continue to be picked from the original location.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="286af-111">Alkalmazási kör</span><span class="sxs-lookup"><span data-stu-id="286af-111">Where it applies</span></span>
<span data-ttu-id="286af-112">A Raktáron belüli régebbi kötegek megjelenítésének konfigurálása a mobileszköz menüelemeiben történik, és a kitárolási köteg alatti elemekre van hatással.</span><span class="sxs-lookup"><span data-stu-id="286af-112">Display older batches within warehouse is configured on mobile device menu items and affects the pick for batch below items.</span></span>

## <a name="set-up-display-older-batches-within-warehouse"></a><span data-ttu-id="286af-113">Raktáron belüli régebbi kötegek megjelenítésének beállítása</span><span class="sxs-lookup"><span data-stu-id="286af-113">Set up Display older batches within warehouse</span></span>
<span data-ttu-id="286af-114">A **Raktáron belüli régebbi kötegek megjelenítésének** konfigurálása akkor áll rendelkezésre mobileszközön menüelemek formájában, ha a **Legrégebbi köteg kitárolása** opció beállítása **Figyelmeztetés**.</span><span class="sxs-lookup"><span data-stu-id="286af-114">The **Display older batches within warehouse** configuration is available on mobile device menu items when the **Pick oldest batch** option is set to **Warn**.</span></span>

- <span data-ttu-id="286af-115">A **Raktárkezelés** > **Beállítás** > **Mobileszköz** > **Mobileszköz menüpontjai** lehetőségnél állítsa a **Meglévő munka használata** beállítást **Igen** értékre a menüpontra vonatkozóan, majd válassza ki a **Figyelmeztetés** beállítást a **Legrégebbi köteg kitárolása** mezőben.</span><span class="sxs-lookup"><span data-stu-id="286af-115">Under **Warehouse management** > **Setup** > **Mobile device** > **Mobile device menu items**, set **Use existing work** to **Yes** for the menu item, and select **Warn** in the **Pick oldest batch** field.</span></span> 


