---
title: A rakománysorok súlymezői nem egyeznek meg a rakomány súlymezőivel
description: A rakománysorok súlymezői nem egyeznek meg a rakomány súlymezőivel
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSShipmentDetails_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 639b82a9d46b74f179d6904d2c3b8e7dfb813b58
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924351"
---
# <a name="the-weight-fields-on-load-lines-dont-match-the-weight-fields-on-the-load"></a><span data-ttu-id="0e65b-103">A rakománysorok súlymezői nem egyeznek meg a rakomány súlymezőivel</span><span class="sxs-lookup"><span data-stu-id="0e65b-103">The weight fields on load lines don't match the weight fields on the load</span></span>

<span data-ttu-id="0e65b-104">Hibakódok: WHSLoadWeightOnLinesDoNotMatchLoadWarning</span><span class="sxs-lookup"><span data-stu-id="0e65b-104">Error codes: WHSLoadWeightOnLinesDoNotMatchLoadWarning</span></span>

## <a name="symptoms"></a><span data-ttu-id="0e65b-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="0e65b-105">Symptoms</span></span>

<span data-ttu-id="0e65b-106">A rendszer a következő hibaüzenetet jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="0e65b-106">The system shows the following error message:</span></span>

> <span data-ttu-id="0e65b-107">A rakománysorok súlymezői nem egyeznek meg a(z) %1 rakomány súlymezőivel.</span><span class="sxs-lookup"><span data-stu-id="0e65b-107">The weight fields on load lines do not match the weight fields on load %1.</span></span> <span data-ttu-id="0e65b-108">Futtassa a Raktári rakománysúly konzisztencia ellenőrzését a súlymezők újraszámítása érdekében.</span><span class="sxs-lookup"><span data-stu-id="0e65b-108">Run the Warehouse load weight consistency check to recalculate the weight fields.</span></span>

## <a name="cause"></a><span data-ttu-id="0e65b-109">Ok</span><span class="sxs-lookup"><span data-stu-id="0e65b-109">Cause</span></span>

<span data-ttu-id="0e65b-110">A **Nettó súly** és a **Tárasúly** mező *0* (nulla) értékre van állítva a rakománysoron.</span><span class="sxs-lookup"><span data-stu-id="0e65b-110">The **Net weight** and **Tara weight** fields are set to *0* (zero) on the load line.</span></span> <span data-ttu-id="0e65b-111">A súlymezők azonban nem *0*-ra vannak állítva a termék súlymérése során.</span><span class="sxs-lookup"><span data-stu-id="0e65b-111">However, the weight fields aren't set to *0* for the weight measurements on the product.</span></span> <span data-ttu-id="0e65b-112">Ha a rakománysoron nincsenek beállítva súlymezők, a rakománysor mennyiségének javításai helytelen tömegszámítást okozhatnak a rakományon.</span><span class="sxs-lookup"><span data-stu-id="0e65b-112">When weight fields aren't set on the load line, any corrections of the quantity on the load line might cause incorrect weight calculation on the load.</span></span> <span data-ttu-id="0e65b-113">Ez a hiba akkor fordulhat elő, ha a rakománysor létrehozása óta módosultak a termék súlyai.</span><span class="sxs-lookup"><span data-stu-id="0e65b-113">This issue might occur if the weights on the product have been changed since the load line was created.</span></span>

## <a name="resolution"></a><span data-ttu-id="0e65b-114">Felbontás</span><span class="sxs-lookup"><span data-stu-id="0e65b-114">Resolution</span></span>

<span data-ttu-id="0e65b-115">Rakománysor létrehozásakor a termék súlymezőit alapértelmezetten meg vannak adva.</span><span class="sxs-lookup"><span data-stu-id="0e65b-115">By default, when a load line is created, the weight fields from the product are entered on it.</span></span> <span data-ttu-id="0e65b-116">Ha a súly nulla, akkor a *Raktári rakománysúly konzisztencia ellenőrzése* funkcióval újraszámíthatja a súlyt.</span><span class="sxs-lookup"><span data-stu-id="0e65b-116">If the weight is zero, you can recalculate it by using the *Warehouse load weight consistency check* functionality.</span></span>

1. <span data-ttu-id="0e65b-117">Nyissa meg a **Rendszeradminisztráció \> Ismétlődő feladatok \> Adatbázis \> Konzisztenciaellenőrzés** lehetőségét.</span><span class="sxs-lookup"><span data-stu-id="0e65b-117">Go to **System administration \> Periodic tasks \> Database \> Consistency check**.</span></span>
1. <span data-ttu-id="0e65b-118">A **Konzisztencia ellenőrzése** párbeszédpanelen állítsa a **Modul** mezőt *Raktárkezelés* beállításra.</span><span class="sxs-lookup"><span data-stu-id="0e65b-118">In the **Consistency check** dialog box, set the **Module** field to *Warehouse management*.</span></span>
1. <span data-ttu-id="0e65b-119">Állítsa be a **Ellenőrzés/javítás** mezőt *Hiba javítása* értékre.</span><span class="sxs-lookup"><span data-stu-id="0e65b-119">Set the **Check/Fix** field to *Fix error*.</span></span>
1. <span data-ttu-id="0e65b-120">A jelölőnégyzetek listájában jelölje be a **Raktári rakománysúly konzisztencia ellenőrzése** jelölőnégyzetet, és győződjön meg arról, hogy csak ennek a jelölőnégyzetnek a sora van kijelölve.</span><span class="sxs-lookup"><span data-stu-id="0e65b-120">In the checkbox list, select the **Warehouse load weight consistency check** checkbox, and make sure that only the row for this checkbox is highlighted.</span></span>
1. <span data-ttu-id="0e65b-121">A jelölőnégyzetek listájának tetején válassza a három pont gombot (**...**), majd válassza a **Párbeszéd** elemet a menüben.</span><span class="sxs-lookup"><span data-stu-id="0e65b-121">At the top of the checkbox list, select the ellipsis button (**...**), and then select **Dialog** on the menu.</span></span>
1. <span data-ttu-id="0e65b-122">A **Raktári rakománysúly konzisztencia ellenőrzése** jelölőnégyzetben a következő mezők beállításével adhatja meg, hogy a konzisztencia-ellenőrzésnél mely feltételeket kell ellenőrizni:</span><span class="sxs-lookup"><span data-stu-id="0e65b-122">In the **Warehouse load weight consistency check** dialog box, set the following fields to specify the criteria that the consistency check should run for:</span></span>

    - <span data-ttu-id="0e65b-123">**Rakományazonosító:** Rakományazonosító megadása.</span><span class="sxs-lookup"><span data-stu-id="0e65b-123">**Load ID:** Specify a load ID.</span></span> <span data-ttu-id="0e65b-124">Hagyja üresen, ha minden rakományazonosítót ellenőrizni kell.</span><span class="sxs-lookup"><span data-stu-id="0e65b-124">Leave this blank to check all load IDs.</span></span>
    - <span data-ttu-id="0e65b-125">**Cikkszám:** Cikkszám megadása.</span><span class="sxs-lookup"><span data-stu-id="0e65b-125">**Item number:** Specify an item number.</span></span> <span data-ttu-id="0e65b-126">Hagyja üresen, ha minden cikket ellenőrizni kell.</span><span class="sxs-lookup"><span data-stu-id="0e65b-126">Leave this blank to check all items.</span></span>
    - <span data-ttu-id="0e65b-127">**Rakományok súlyának újraszámítása mindig:** Állítsa Ezt a lehetőséget *Igen* beállításra.</span><span class="sxs-lookup"><span data-stu-id="0e65b-127">**Always recalculate weight on loads:** Set this option to *Yes*.</span></span>
    - <span data-ttu-id="0e65b-128">**A rakománysorok súlyának felülírásának engedélyezése:** Állítsa ezt a beállítást *Igen* beállításra.</span><span class="sxs-lookup"><span data-stu-id="0e65b-128">**Allow overwrite of weight on load lines:** Set this option to *Yes*.</span></span>

1. <span data-ttu-id="0e65b-129">Az **OK** gomb kiválasztásával zárja be a **Raktári rakománysúly konzisztencia ellenőrzése** párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="0e65b-129">Select **OK** to close the **Warehouse load weight consistency check** dialog box.</span></span>
1. <span data-ttu-id="0e65b-130">Válassza ki a három pont gombot, majd válassza a menü **Végrehajtás** parancsát.</span><span class="sxs-lookup"><span data-stu-id="0e65b-130">Select the ellipsis button, and then select **Execute** on the menu.</span></span>

<span data-ttu-id="0e65b-131">A rendszer a megadott feltételek alapján újraszámja a súlyt.</span><span class="sxs-lookup"><span data-stu-id="0e65b-131">The weight is recalculated based on the criteria that you specified.</span></span> <span data-ttu-id="0e65b-132">A konzisztencia-ellenőrzés eredményének megtekintéséhez válassza az **Üzenet részletei** hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="0e65b-132">Select the **Message details** link to view the result of the consistency check.</span></span>
