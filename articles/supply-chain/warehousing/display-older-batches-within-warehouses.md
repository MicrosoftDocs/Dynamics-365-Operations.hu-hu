---
title: Raktáron belüli régebbi kötegek megjelenítésének konfigurálása mobileszközön
description: Ez a témakör leírja, hogy miként állítható be egy mobileszköz, hogy megjelenítse azoknak a helyeknek a listáját, ahol régebbi kötegek szerepelnek, mint egy munkasor jelenlegi helye.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5156b17b9eddc2c3127b6d91fd8cd7d519d240e8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838298"
---
# <a name="configure-display-older-batches-within-warehouse-on-a-mobile-device"></a><span data-ttu-id="a98ef-103">Raktáron belüli régebbi kötegek megjelenítésének konfigurálása mobileszközön</span><span class="sxs-lookup"><span data-stu-id="a98ef-103">Configure Display older batches within warehouse on a mobile device</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a98ef-104">A **Raktáron belüli régebbi kötegek megjelenítése** konfiguráció lehetővé teszi azon helyek listájának megjelenítését, ahol olyan kötegek szerepelnek, amelyek régebbiek a munkasor jelenlegi helyénél.</span><span class="sxs-lookup"><span data-stu-id="a98ef-104">The **Display older batches within warehouse** configuration lets you display a list of locations with batches older than the current location of the work line.</span></span> <span data-ttu-id="a98ef-105">A megjelenített helyek listája tartalmazza a régebbi kötegekkel kapcsolatos információkat, az egyes tételek lejárati dátumával és fizikai készletével együtt.</span><span class="sxs-lookup"><span data-stu-id="a98ef-105">The list of locations that are displayed includes information about the older batches in the location with the expiration date and the physical inventory of each batch.</span></span> <span data-ttu-id="a98ef-106">Kiválaszthatja, hogy a kitárolás új helyről történjen, vagy folytathatja a kitárolást az aktuális helyről is.</span><span class="sxs-lookup"><span data-stu-id="a98ef-106">You can choose to pick from a new location or to continue picking from the current location.</span></span> 
- <span data-ttu-id="a98ef-107">Kitárolás új helyről – Ha új helyet választ ki a kitárolásra, akkor az aktuális munkasor frissül az új hely használatával, és a munka az új helyszínen a szokásos módon folytatódik.</span><span class="sxs-lookup"><span data-stu-id="a98ef-107">Pick from a new location - If you select a new location to pick from, the  current work line will be updated to use the new location and work will continue as usual with the new location.</span></span> <span data-ttu-id="a98ef-108">Ahhoz, hogy az új hely érvényes legyen, elegendő mennyiséggel kell rendelkeznie a teljes munkasorra kiterjedően.</span><span class="sxs-lookup"><span data-stu-id="a98ef-108">For the new location to be valid, it must have enough available quantity for the whole work line.</span></span> <span data-ttu-id="a98ef-109">Ha nem érhető el a szükséges mennyiség, akkor a munkasor nem frissül, és a lista jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="a98ef-109">If the required quantity is not available, the work line will not be updated, and the list will display.</span></span> 
- <span data-ttu-id="a98ef-110">Kitárolás folytatása a jelenlegi helyről – Ha folytatja az aktuális munkaterület használatát, akkor a munkasor mennyiségeit továbbra is az eredeti helyről tárolja ki a rendszer.</span><span class="sxs-lookup"><span data-stu-id="a98ef-110">Continue picking from the current location - If you continue with the current work line location, the quantities for the work line will continue to be picked from the original location.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="a98ef-111">Alkalmazási kör</span><span class="sxs-lookup"><span data-stu-id="a98ef-111">Where it applies</span></span>
<span data-ttu-id="a98ef-112">A Raktáron belüli régebbi kötegek megjelenítésének konfigurálása a mobileszköz menüelemeiben történik, és a kitárolási köteg alatti elemekre van hatással.</span><span class="sxs-lookup"><span data-stu-id="a98ef-112">Display older batches within warehouse is configured on mobile device menu items and affects the pick for batch below items.</span></span>

## <a name="set-up-display-older-batches-within-warehouse"></a><span data-ttu-id="a98ef-113">Raktáron belüli régebbi kötegek megjelenítésének beállítása</span><span class="sxs-lookup"><span data-stu-id="a98ef-113">Set up Display older batches within warehouse</span></span>
<span data-ttu-id="a98ef-114">A **Raktáron belüli régebbi kötegek megjelenítésének** konfigurálása akkor áll rendelkezésre mobileszközön menüelemek formájában, ha a **Legrégebbi köteg kitárolása** opció beállítása **Figyelmeztetés**.</span><span class="sxs-lookup"><span data-stu-id="a98ef-114">The **Display older batches within warehouse** configuration is available on mobile device menu items when the **Pick oldest batch** option is set to **Warn**.</span></span>

- <span data-ttu-id="a98ef-115">A **Raktárkezelés** > **Beállítás** > **Mobileszköz** > **Mobileszköz menüpontjai** lehetőségnél állítsa a **Meglévő munka használata** beállítást **Igen** értékre a menüpontra vonatkozóan, majd válassza ki a **Figyelmeztetés** beállítást a **Legrégebbi köteg kitárolása** mezőben.</span><span class="sxs-lookup"><span data-stu-id="a98ef-115">Under **Warehouse management** > **Setup** > **Mobile device** > **Mobile device menu items**, set **Use existing work** to **Yes** for the menu item, and select **Warn** in the **Pick oldest batch** field.</span></span> 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]