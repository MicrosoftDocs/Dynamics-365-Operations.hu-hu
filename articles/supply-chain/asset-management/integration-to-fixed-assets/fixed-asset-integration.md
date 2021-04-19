---
title: Eszközkezelés integrálása tárgyi eszközökkel
description: Ez a témakör azt mutatja be, hogyan lehet integrálni az eszközkezelés és a tárgyi eszközök modulokat, hogy a tárgyi eszközöket a karbantartás alatt álló eszközökkel lehessen kapcsolni.
author: kamaybac
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: a45bf1f62cdcc8abed2ec157a223e7f3fddec7ce
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809854"
---
# <a name="integrate-asset-management-with-fixed-assets"></a><span data-ttu-id="1dcf6-103">Eszközkezelés integrálása tárgyi eszközökkel</span><span class="sxs-lookup"><span data-stu-id="1dcf6-103">Integrate asset management with fixed assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1dcf6-104">Az **Eszközkezelés** és a **tárgyi eszközök** modulok integrálásával a tárgyi eszközöket a karbantartás alatt álló eszközökkel lehet kapcsolni.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-104">By integrating the **Asset management** and **Fixed assets** modules, you can link fixed assets with maintenance assets.</span></span> <span data-ttu-id="1dcf6-105">A tárgyi eszközök felhasználói ezt követően létrehozhatnak egy új vagy meglévő tárgyi eszközből karbantartás alatt álló eszközt, és az eszközkezelési felhasználók egy meglévő tárgyi eszközhöz rendelhetik a karbantartás alatt álló eszközt.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-105">Fixed assets users can then create a maintenance asset from a new or existing fixed asset, and Asset management users can associate a maintenance asset with an existing fixed asset.</span></span> <span data-ttu-id="1dcf6-106">Ez a funkció megkönnyíti a tárgyi eszközök felhasználói számára, hogy megtekintsék a kapcsolódó karbantartás alatt álló eszköz munkarendeléseiből feladott költségeket.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-106">This feature also makes it easy for Fixed assets users to view the costs that were posted from work orders for related maintenance assets.</span></span>

> [!NOTE]
> <span data-ttu-id="1dcf6-107">Ebben a témakörben a *karbantartás alatt álló eszköz* az **Eszközkezelés** modul eszközeire utal, a *tárgyi eszközök* pedig a **Tárgyi eszközök** modul eszközeire.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-107">In this topic, *maintenance assets* refer to assets from the **Asset management** module, and *fixed assets* refer to assets from the **Fixed assets** module.</span></span>

## <a name="set-a-default-location-for-new-maintenance-assets-that-are-created-from-fixed-assets-optional"></a><span data-ttu-id="1dcf6-108">A tárgyi eszközökből létrehozott új karbantartás alatt álló eszközök alapértelmezett helyének beállítása (nem kötelező)</span><span class="sxs-lookup"><span data-stu-id="1dcf6-108">Set a default location for new maintenance assets that are created from fixed assets (optional)</span></span>

<span data-ttu-id="1dcf6-109">Ezzel a nem kötelező konfigurációval beállíthat alapértelmezett munkavégzési helyszínt a tárgyi eszközökből létrehozott új karbantartás alatt álló eszközökhöz.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-109">This optional configuration lets you set a default functional location for new maintenance assets that are created from fixed assets.</span></span> <span data-ttu-id="1dcf6-110">Ezt a konfigurációt általában csak egy alkalommal hajthatja végre, ha egyáltalán végrehajtja.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-110">You typically complete this configuration this just one time, if you complete it at all.</span></span>

<span data-ttu-id="1dcf6-111">A konfiguráció befejezéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-111">To complete the configuration, follow these steps.</span></span>

1. <span data-ttu-id="1dcf6-112">Lépjen az **Eszközkezelés \> Beállítás \> Eszközkezelési paraméterek** részre.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-112">Go to **Asset management \> Setup \> Asset management parameters**.</span></span>
1. <span data-ttu-id="1dcf6-113">A **Tárgyi eszközök** mezőben lévő **munkavégzési helyszín** lapon válassza ki az alapértelmezett helyét.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-113">On the **Fixed assets** tab, in the **Functional location** field, select the default location.</span></span>
1. <span data-ttu-id="1dcf6-114">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-114">On the Action Pane, select **Save**.</span></span>

## <a name="work-with-integrated-maintenance-assets-and-fixed-assets"></a><span data-ttu-id="1dcf6-115">Integrált karbantartás alatt álló eszközök és tárgyi eszközök használata</span><span class="sxs-lookup"><span data-stu-id="1dcf6-115">Work with integrated maintenance assets and fixed assets</span></span>

<span data-ttu-id="1dcf6-116">Ez a szakasz olyan eljárások gyűjteményét mutatja be, amelyek az integrált eszközkezelés és a tárgyi eszközök funkcióinak használatára különböző módszereket mutatnak be.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-116">This section provides a collection of procedures that show various ways that you can work with the integrated Asset management and Fixed assets features.</span></span>

### <a name="associate-an-existing-maintenance-asset-with-a-fixed-asset"></a><span data-ttu-id="1dcf6-117">Meglévő karbantartás alatt álló eszköz társítása tárgyi eszközhöz</span><span class="sxs-lookup"><span data-stu-id="1dcf6-117">Associate an existing maintenance asset with a fixed asset</span></span>

<span data-ttu-id="1dcf6-118">Meglévő karbantartás alatt álló eszköz társításához tárgyi eszközhöz kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-118">To associate an existing maintenance asset with a fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="1dcf6-119">Lépjen az **Eszközkezelés \> Eszközök \> Összes eszköz** (vagy **Aktív eszközök**) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-119">Go to **Asset management \> Assets \> All assets** (or **Active assets**).</span></span>
1. <span data-ttu-id="1dcf6-120">Válasszon egy eszközt.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-120">Select an asset.</span></span>
1. <span data-ttu-id="1dcf6-121">A **Tárgyi eszköz** gyorslapon a **Tárgyi eszköz száma** mezőben válasszon egy meglévő tárgyi eszközt.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-121">On the **Fixed asset** FastTab, in the **Fixed asset number** field, select an existing fixed asset.</span></span>
1. <span data-ttu-id="1dcf6-122">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-122">On the Action Pane, select **Save**.</span></span>

### <a name="view-the-fixed-asset-that-is-associated-with-a-selected-maintenance-asset"></a><span data-ttu-id="1dcf6-123">Tekintse meg a kiválasztott karbantartás alatt álló eszközhöz társított tárgyi eszközt</span><span class="sxs-lookup"><span data-stu-id="1dcf6-123">View the fixed asset that is associated with a selected maintenance asset</span></span>

<span data-ttu-id="1dcf6-124">A kiválasztott karbantartás alatt álló eszközhöz társított tárgyi eszköz megtekintéséhez kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-124">To view the fixed asset that is associated with a selected maintenance asset, follow these steps.</span></span>

1. <span data-ttu-id="1dcf6-125">Lépjen az **Eszközkezelés \> Eszközök \> Összes eszköz** (vagy **Aktív eszközök**) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-125">Go to **Asset management \> Assets \> All assets** (or **Active assets**).</span></span>
1. <span data-ttu-id="1dcf6-126">Válasszon egy eszközt.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-126">Select an asset.</span></span>
1. <span data-ttu-id="1dcf6-127">A **Tárgyi eszköz** gyorslapon a **Tárgyi eszköz száma** mezőben válassza a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-127">On the **Fixed asset** FastTab, in the **Fixed asset number** field, select the link.</span></span>

    <span data-ttu-id="1dcf6-128">A **Tárgyi eszköz** oldal megnyílik a kiválasztott eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-128">The **Fixed assets** page for the selected asset is opened.</span></span> <span data-ttu-id="1dcf6-129">(Ez a lap általában a **Tárgyi eszközök \> tárgyi eszközök \> tárgyi eszközök** helyen található.)</span><span class="sxs-lookup"><span data-stu-id="1dcf6-129">(Typically, this page is found at **Fixed assets \> Fixed assets \> Fixed assets**.)</span></span>

### <a name="view-the-maintenance-asset-that-is-associated-with-a-selected-fixed-asset"></a><span data-ttu-id="1dcf6-130">Tekintse meg a kiválasztott tárgyi eszközhöz társított karbantartás alatt álló eszközt</span><span class="sxs-lookup"><span data-stu-id="1dcf6-130">View the maintenance asset that is associated with a selected fixed asset</span></span>

<span data-ttu-id="1dcf6-131">A kiválasztott tárgyi eszközhöz társított karbantartás alatt álló eszköz megtekintéséhez kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-131">To view the maintenance asset that is associated with a selected fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="1dcf6-132">Lépjen a **Tárgyi eszközök \> Tárgyi eszközök \> Tárgyi eszközök** menüpontba.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-132">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="1dcf6-133">Válasszon egy eszközt.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-133">Select an asset.</span></span>
1. <span data-ttu-id="1dcf6-134">A Művelet ablaktábla **Eszközkezelés** lapjának **Nézet** csoportjában válassza a **karbantartás alatt álló eszköz** elemet.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-134">On the Action Pane, on the **Asset management** tab, in the **View** group, select **Maintenance asset**.</span></span>

    <span data-ttu-id="1dcf6-135">A kiválasztott tárgyi eszközhöz társított eszközhöz tartozó **karbantartás alatt álló eszköz** oldal megnyílik.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-135">The **Maintenance asset** page for the asset that is associated with the selected fixed asset is opened.</span></span> <span data-ttu-id="1dcf6-136">(Ez a lap általában a **Eszközkezelés \> Ezsközök \> Összes eszköz** helyen található.)</span><span class="sxs-lookup"><span data-stu-id="1dcf6-136">(Typically, this page is found at **Asset management \> Assets \> All assets**.)</span></span>

### <a name="view-maintenance-costs-that-are-associated-with-a-fixed-asset"></a><span data-ttu-id="1dcf6-137">Tárgyi eszközhöz társított karbantartási költségek megtekintése</span><span class="sxs-lookup"><span data-stu-id="1dcf6-137">View maintenance costs that are associated with a fixed asset</span></span>

<span data-ttu-id="1dcf6-138">Az eszközkezelési munkarendeléseket a karbantartás alatt álló eszközökhöz lehet feladni, és az egyes munkarendelések esetében általában költség szerepel.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-138">Asset management work orders can be posted for maintenance assets, and each of those work orders typically has a cost.</span></span> <span data-ttu-id="1dcf6-139">Ha egy tárgyi eszközhöz egy karbantartás alatt álló eszköz van társítva, akkor közvetlenül a tárgyi eszközről is megtekintheti a kapcsolódó költségeket.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-139">When a fixed asset is associated with a maintenance asset, you can go directly from the fixed asset to view the related costs.</span></span>

<span data-ttu-id="1dcf6-140">A tárgyi eszközhöz társított karbantartási költségek megtekintéséhez kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-140">To view the maintenance costs that are associated with a fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="1dcf6-141">Lépjen a **Tárgyi eszközök \> Tárgyi eszközök \> Tárgyi eszközök** menüpontba.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-141">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="1dcf6-142">Válasszon egy eszközt.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-142">Select an asset.</span></span>
1. <span data-ttu-id="1dcf6-143">A Művelet ablaktábla **Eszközkezelés** lapjának **Nézet** csoportjában válassza a **karbantartási költség** elemet.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-143">On the Action Pane, on the **Asset management** tab, in the **View** group, select **Maintenance cost**.</span></span>

    <span data-ttu-id="1dcf6-144">Megnyitja a **karbantartási költség** lapot, és megjeleníti a kapcsolódó költségeket.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-144">The **Maintenance cost** page is opened and shows the related costs.</span></span>

### <a name="create-a-new-maintenance-asset-for-an-existing-fixed-asset"></a><a name="new-maintenance-from-fixed"></a><span data-ttu-id="1dcf6-145">Új karbantartás alatt álló eszköz létrehozása meglévő tárgyi eszközhöz</span><span class="sxs-lookup"><span data-stu-id="1dcf6-145">Create a new maintenance asset for an existing fixed asset</span></span>

<span data-ttu-id="1dcf6-146">Új karbantartás alatt álló eszköz meglévő tárgyi eszközhöz való létrehozásához kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-146">To create a new maintenance asset for an existing fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="1dcf6-147">Lépjen a **Tárgyi eszközök \> Tárgyi eszközök \> Tárgyi eszközök** menüpontba.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-147">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="1dcf6-148">Válasszon egy eszközt.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-148">Select an asset.</span></span>
1. <span data-ttu-id="1dcf6-149">A Művelet ablaktábla **Eszközkezelés** lapjának **Új** csoportjában válassza a **karbantartás alatt álló eszköz létrehozása** elemet.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-149">On the Action Pane, on the **Asset management** tab, in the **New** group, select **Create maintenance asset**.</span></span> <span data-ttu-id="1dcf6-150">(Ha ez a beállítás nem érhető el, előfordulhat, hogy egy karbantartás alatt álló eszköz már hozzá van rendelve a kiválasztott tárgyi eszközhöz.)</span><span class="sxs-lookup"><span data-stu-id="1dcf6-150">(If this option is unavailable, a maintenance asset might already be associated with the selected fixed asset.)</span></span>
1. <span data-ttu-id="1dcf6-151">FEjezze be az eszköz létrehozását az [Eszköz létrehozása](../objects/create-an-object.md) részben leírtaknak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-151">Finish creating the asset as described in [Create an asset](../objects/create-an-object.md).</span></span>

### <a name="create-a-new-fixed-asset-and-add-a-new-maintenance-asset-for-it"></a><span data-ttu-id="1dcf6-152">Új tárgyi eszköz létrehozása és hozzáadása új karbantartás alatt álló eszközhöz</span><span class="sxs-lookup"><span data-stu-id="1dcf6-152">Create a new fixed asset and add a new maintenance asset for it</span></span>

<span data-ttu-id="1dcf6-153">Új tárgyi eszköz létrehozásához és új karbantartás alatt álló eszköz hozzáadásához kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-153">To create a new fixed asset and add a new maintenance asset for it, follow these steps.</span></span>

1. <span data-ttu-id="1dcf6-154">Lépjen a **Tárgyi eszközök \> Tárgyi eszközök \> Tárgyi eszközök** menüpontba.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-154">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="1dcf6-155">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-155">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="1dcf6-156">Fejezze be a tárgyi eszköz létrehozását az [Tárgyi eszköz létrehozása](../../../finance/fixed-assets/tasks/create-fixed-asset.md) részben leírtaknak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-156">Finish creating the fixed asset as described in [Create a fixed asset](../../../finance/fixed-assets/tasks/create-fixed-asset.md).</span></span>
1. <span data-ttu-id="1dcf6-157">A Művelet ablaktábla **Eszközkezelés** lapjának **Új** csoportjában válassza a **karbantartás alatt álló eszköz létrehozása** elemet.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-157">On the Action Pane, on the **Asset management** tab, in the **New** group, select **Create maintenance asset**.</span></span>
1. <span data-ttu-id="1dcf6-158">FEjezze be az eszköz létrehozását az [Eszköz létrehozása](../objects/create-an-object.md) részben leírtaknak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-158">Finish creating the asset as described in [Create an asset](../objects/create-an-object.md).</span></span>

### <a name="remove-the-association-between-two-assets"></a><span data-ttu-id="1dcf6-159">Két eszköz közötti társítás eltávolítása</span><span class="sxs-lookup"><span data-stu-id="1dcf6-159">Remove the association between two assets</span></span>

<span data-ttu-id="1dcf6-160">Bizonyos esetekben előfordulhat, hogy egy karbantartás alatt álló eszköz társítását fel kell oldani egy tárgyi eszközről.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-160">In some cases, you might have to disassociate a maintenance asset from its fixed asset.</span></span> <span data-ttu-id="1dcf6-161">Ha például egy tárgyi eszközből [új karbantartás alatt álló eszközt](#new-maintenance-from-fixed) szeretne létrehozni, előbb el kell távolítania a meglévő társításokat.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-161">For example, if you want to [create a new maintenance asset](#new-maintenance-from-fixed) from a fixed asset, you must first remove any existing association.</span></span>

<span data-ttu-id="1dcf6-162">Karbantartás alatt álló eszköz és tárgyi eszköz közti meglévő társítás eltávolításához kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-162">To remove an existing association between a maintenance asset and a fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="1dcf6-163">Lépjen az **Eszközkezelés \> Eszközök \> Összes eszköz** (vagy **Aktív eszközök**) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-163">Go to **Asset management \> Assets \> All assets** (or **Active assets**).</span></span>
1. <span data-ttu-id="1dcf6-164">Keresse meg és nyissa meg a tárgyi eszközt.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-164">Find and open the fixed asset.</span></span>
1. <span data-ttu-id="1dcf6-165">A **tárgyi eszköz** gyorslapon törölje a jelet az érték a **munkavégzési helyszín** mezőből.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-165">On the **Fixed asset** FastTab, clear the value from the **Functional location** field.</span></span>
1. <span data-ttu-id="1dcf6-166">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1dcf6-166">On the Action Pane, select **Save**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]