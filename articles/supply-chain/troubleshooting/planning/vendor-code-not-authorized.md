---
title: A szállítókód nem engedélyezett adott termékhez és dátumhoz
description: Ha egy tervezett rendelést meg szeretne határozni, vagy ha sort ad hozzá egy beszerzési rendeléshez, akkor olyan hibaüzenet jelenik meg, amely szerint a szállítókód nincs engedélyezve egy termékhez és dátumhoz.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPO_ReqTransPoMarkFirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e6b1189e4fedfdb029f4b4503f0635133df9d87e
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294095"
---
# <a name="vendor-code-isnt-authorized-for-a-specific-product-and-date"></a><span data-ttu-id="23d38-103">A szállítókód nem engedélyezett adott termékhez és dátumhoz</span><span class="sxs-lookup"><span data-stu-id="23d38-103">Vendor code isn't authorized for a specific product and date</span></span>

<span data-ttu-id="23d38-104">Hibakód: SYP4881415</span><span class="sxs-lookup"><span data-stu-id="23d38-104">Error code: SYP4881415</span></span>

## <a name="symptoms"></a><span data-ttu-id="23d38-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="23d38-105">Symptoms</span></span>

<span data-ttu-id="23d38-106">Amikor tervezett rendelést próbál megerősíteni, illetve sort próbál hozzáadni egy beszerzési rendeléshez, a következő hibaüzenetet kapja:</span><span class="sxs-lookup"><span data-stu-id="23d38-106">When you try to firm a planned order or add a line to a purchase order, you receive the following error message:</span></span>

> <span data-ttu-id="23d38-107">A(z) %1 szállítói kód nincs engedélyezve %2 esetében a következőn: %3.</span><span class="sxs-lookup"><span data-stu-id="23d38-107">Vendor code %1 is not authorized for %2 on %3.</span></span>

## <a name="cause"></a><span data-ttu-id="23d38-108">Ok</span><span class="sxs-lookup"><span data-stu-id="23d38-108">Cause</span></span>

<span data-ttu-id="23d38-109">A hiba oka, hogy az **Engedélyezett szállítók ellenőrzési módszere** mező értéke az adott terméknél *Csak figyelmeztetés* vagy *Nem megengedett*, és a szállító számára jelenleg nem engedélyezett az adott termék biztosítása.</span><span class="sxs-lookup"><span data-stu-id="23d38-109">The error occurs because the **Approved vendor check method** field is set to *Warning only* or *Not allowed* for the specified product, and the vendor isn't currently authorized to supply that product.</span></span>

## <a name="resolution"></a><span data-ttu-id="23d38-110">Megoldás</span><span class="sxs-lookup"><span data-stu-id="23d38-110">Resolution</span></span>

<span data-ttu-id="23d38-111">A probléma megoldásához vagy tiltsa le a vonatkozó termék szállítói ellenőrzését, vagy hagyja jóvá a szállítót.</span><span class="sxs-lookup"><span data-stu-id="23d38-111">To fix this issue, either disable the vendor check for the relevant product or approve the vendor.</span></span>

<span data-ttu-id="23d38-112">A következő lépésekkel tilthatja le a szállítói ellenőrzést egy adott terméknél.</span><span class="sxs-lookup"><span data-stu-id="23d38-112">To disable the vendor check for a product, follow these steps.</span></span>

1. <span data-ttu-id="23d38-113">Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="23d38-113">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="23d38-114">Nyissa mega releváns terméket.</span><span class="sxs-lookup"><span data-stu-id="23d38-114">Open the relevant product.</span></span>
1. <span data-ttu-id="23d38-115">A **Vásárlás** gyorslapon módosítsa úgy az **Engedélyezett szállítók ellenőrzési módszere** mező értékét, hogy ne *Csak figyelmeztetés* vagy *Nem megengedett* legyen.</span><span class="sxs-lookup"><span data-stu-id="23d38-115">On the **Purchase** FastTab, set the **Approved vendor check method** field to a value other than *Warning only* or *Not allowed*.</span></span>

<span data-ttu-id="23d38-116">A következő lépésekkel hagyhat jóvá egy szállítót egy adott terméknél.</span><span class="sxs-lookup"><span data-stu-id="23d38-116">To approve a vendor for a product, follow these steps.</span></span>

1. <span data-ttu-id="23d38-117">Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="23d38-117">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="23d38-118">Nyissa meg a releváns cikket.</span><span class="sxs-lookup"><span data-stu-id="23d38-118">Open the relevant item.</span></span>
1. <span data-ttu-id="23d38-119">A Művelet panel **Vásárlás** lapján lévő **Engedélyezett szállító** csoportban válassza a **Beállítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="23d38-119">On the Action Pane, on the **Purchase** tab, in the **Approved vendor** group, select **Setup**.</span></span>
1. <span data-ttu-id="23d38-120">Az **Engedélyezett szállító** listaoldalon adjon hozzá egy sort a rácshoz, majd állítsa be hozzá a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="23d38-120">On the **Approved vendor** list page, add a row to the grid, and set the following values for it:</span></span>

    - <span data-ttu-id="23d38-121">**Szállító** – az aktuális termékhez jóváhagyni kívánt szállító kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="23d38-121">**Vendor** – Select the vendor to approve for the current product.</span></span>
    - <span data-ttu-id="23d38-122">**Hatályba lépési dátum** – az első olyan dátum kiválasztása, ahelyhez jóváhagyja a szállítót.</span><span class="sxs-lookup"><span data-stu-id="23d38-122">**Effective date** – Select the first date that the vendor is approved for.</span></span>
    - <span data-ttu-id="23d38-123">**Lejárati dátum** – az utolsó olyan dátum kiválasztása, ahelyhez jóváhagyja a szállítót.</span><span class="sxs-lookup"><span data-stu-id="23d38-123">**Expiration date** – Select the last date that the vendor is approved for.</span></span>

<span data-ttu-id="23d38-124">További információk: [A meghatározott termékek szállítójának jóváhagyása](/dynamics365/supply-chain/procurement/tasks/approve-vendors-specific-products.md).</span><span class="sxs-lookup"><span data-stu-id="23d38-124">For more information, see [Approve vendors for specific products](/dynamics365/supply-chain/procurement/tasks/approve-vendors-specific-products.md).</span></span>
