---
title: Eszközkezelés integrálása tárgyi eszközökkel
description: Ez a témakör azt mutatja be, hogyan lehet integrálni az eszközkezelés és a tárgyi eszközök modulokat, hogy a tárgyi eszközöket a karbantartás alatt álló eszközökkel lehessen kapcsolni.
author: kamaybac
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: adc14019c243b1992cdaa22ef7aa32cb44bfffd9
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253590"
---
# <a name="integrate-asset-management-with-fixed-assets"></a><span data-ttu-id="ab3cd-103">Eszközkezelés integrálása tárgyi eszközökkel</span><span class="sxs-lookup"><span data-stu-id="ab3cd-103">Integrate asset management with fixed assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ab3cd-104">Az **Eszközkezelés** és a **tárgyi eszközök** modulok integrálásával a tárgyi eszközöket a karbantartás alatt álló eszközökkel lehet kapcsolni.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-104">By integrating the **Asset management** and **Fixed assets** modules, you can link fixed assets with maintenance assets.</span></span> <span data-ttu-id="ab3cd-105">A tárgyi eszközök felhasználói ezt követően létrehozhatnak egy új vagy meglévő tárgyi eszközből karbantartás alatt álló eszközt, és az eszközkezelési felhasználók egy meglévő tárgyi eszközhöz rendelhetik a karbantartás alatt álló eszközt.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-105">Fixed assets users can then create a maintenance asset from a new or existing fixed asset, and Asset management users can associate a maintenance asset with an existing fixed asset.</span></span> <span data-ttu-id="ab3cd-106">Ez a funkció megkönnyíti a tárgyi eszközök felhasználói számára, hogy megtekintsék a kapcsolódó karbantartás alatt álló eszköz munkarendeléseiből feladott költségeket.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-106">This feature also makes it easy for Fixed assets users to view the costs that were posted from work orders for related maintenance assets.</span></span>

> [!NOTE]
> <span data-ttu-id="ab3cd-107">Ebben a témakörben a *karbantartás alatt álló eszköz* az **Eszközkezelés** modul eszközeire utal, a *tárgyi eszközök* pedig a **Tárgyi eszközök** modul eszközeire.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-107">In this topic, *maintenance assets* refer to assets from the **Asset management** module, and *fixed assets* refer to assets from the **Fixed assets** module.</span></span>

## <a name="set-a-default-location-for-new-maintenance-assets-that-are-created-from-fixed-assets-optional"></a><span data-ttu-id="ab3cd-108">A tárgyi eszközökből létrehozott új karbantartás alatt álló eszközök alapértelmezett helyének beállítása (nem kötelező)</span><span class="sxs-lookup"><span data-stu-id="ab3cd-108">Set a default location for new maintenance assets that are created from fixed assets (optional)</span></span>

<span data-ttu-id="ab3cd-109">Ezzel a nem kötelező konfigurációval beállíthat alapértelmezett munkavégzési helyszínt a tárgyi eszközökből létrehozott új karbantartás alatt álló eszközökhöz.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-109">This optional configuration lets you set a default functional location for new maintenance assets that are created from fixed assets.</span></span> <span data-ttu-id="ab3cd-110">Ezt a konfigurációt általában csak egy alkalommal hajthatja végre, ha egyáltalán végrehajtja.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-110">You typically complete this configuration this just one time, if you complete it at all.</span></span>

<span data-ttu-id="ab3cd-111">A konfiguráció befejezéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-111">To complete the configuration, follow these steps.</span></span>

1. <span data-ttu-id="ab3cd-112">Lépjen az **Eszközkezelés \> Beállítás \> Eszközkezelési paraméterek** részre.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-112">Go to **Asset management \> Setup \> Asset management parameters**.</span></span>
1. <span data-ttu-id="ab3cd-113">A **Tárgyi eszközök** mezőben lévő **munkavégzési helyszín** lapon válassza ki az alapértelmezett helyét.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-113">On the **Fixed assets** tab, in the **Functional location** field, select the default location.</span></span>
1. <span data-ttu-id="ab3cd-114">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-114">On the Action Pane, select **Save**.</span></span>

## <a name="work-with-integrated-maintenance-assets-and-fixed-assets"></a><span data-ttu-id="ab3cd-115">Integrált karbantartás alatt álló eszközök és tárgyi eszközök használata</span><span class="sxs-lookup"><span data-stu-id="ab3cd-115">Work with integrated maintenance assets and fixed assets</span></span>

<span data-ttu-id="ab3cd-116">Ez a szakasz olyan eljárások gyűjteményét mutatja be, amelyek az integrált eszközkezelés és a tárgyi eszközök funkcióinak használatára különböző módszereket mutatnak be.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-116">This section provides a collection of procedures that show various ways that you can work with the integrated Asset management and Fixed assets features.</span></span>

### <a name="associate-an-existing-maintenance-asset-with-a-fixed-asset"></a><span data-ttu-id="ab3cd-117">Meglévő karbantartás alatt álló eszköz társítása tárgyi eszközhöz</span><span class="sxs-lookup"><span data-stu-id="ab3cd-117">Associate an existing maintenance asset with a fixed asset</span></span>

<span data-ttu-id="ab3cd-118">Meglévő karbantartás alatt álló eszköz társításához tárgyi eszközhöz kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-118">To associate an existing maintenance asset with a fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="ab3cd-119">Lépjen az **Eszközkezelés \> Eszközök \> Összes eszköz** (vagy **Aktív eszközök**) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-119">Go to **Asset management \> Assets \> All assets** (or **Active assets**).</span></span>
1. <span data-ttu-id="ab3cd-120">Válasszon egy eszközt.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-120">Select an asset.</span></span>
1. <span data-ttu-id="ab3cd-121">A **Tárgyi eszköz** gyorslapon a **Tárgyi eszköz száma** mezőben válasszon egy meglévő tárgyi eszközt.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-121">On the **Fixed asset** FastTab, in the **Fixed asset number** field, select an existing fixed asset.</span></span>
1. <span data-ttu-id="ab3cd-122">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-122">On the Action Pane, select **Save**.</span></span>

### <a name="view-the-fixed-asset-that-is-associated-with-a-selected-maintenance-asset"></a><span data-ttu-id="ab3cd-123">Tekintse meg a kiválasztott karbantartás alatt álló eszközhöz társított tárgyi eszközt</span><span class="sxs-lookup"><span data-stu-id="ab3cd-123">View the fixed asset that is associated with a selected maintenance asset</span></span>

<span data-ttu-id="ab3cd-124">A kiválasztott karbantartás alatt álló eszközhöz társított tárgyi eszköz megtekintéséhez kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-124">To view the fixed asset that is associated with a selected maintenance asset, follow these steps.</span></span>

1. <span data-ttu-id="ab3cd-125">Lépjen az **Eszközkezelés \> Eszközök \> Összes eszköz** (vagy **Aktív eszközök**) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-125">Go to **Asset management \> Assets \> All assets** (or **Active assets**).</span></span>
1. <span data-ttu-id="ab3cd-126">Válasszon egy eszközt.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-126">Select an asset.</span></span>
1. <span data-ttu-id="ab3cd-127">A **Tárgyi eszköz** gyorslapon a **Tárgyi eszköz száma** mezőben válassza a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-127">On the **Fixed asset** FastTab, in the **Fixed asset number** field, select the link.</span></span>

    <span data-ttu-id="ab3cd-128">A **Tárgyi eszköz** oldal megnyílik a kiválasztott eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-128">The **Fixed assets** page for the selected asset is opened.</span></span> <span data-ttu-id="ab3cd-129">(Ez a lap általában a **Tárgyi eszközök \> tárgyi eszközök \> tárgyi eszközök** helyen található.)</span><span class="sxs-lookup"><span data-stu-id="ab3cd-129">(Typically, this page is found at **Fixed assets \> Fixed assets \> Fixed assets**.)</span></span>

### <a name="view-the-maintenance-asset-that-is-associated-with-a-selected-fixed-asset"></a><span data-ttu-id="ab3cd-130">Tekintse meg a kiválasztott tárgyi eszközhöz társított karbantartás alatt álló eszközt</span><span class="sxs-lookup"><span data-stu-id="ab3cd-130">View the maintenance asset that is associated with a selected fixed asset</span></span>

<span data-ttu-id="ab3cd-131">A kiválasztott tárgyi eszközhöz társított karbantartás alatt álló eszköz megtekintéséhez kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-131">To view the maintenance asset that is associated with a selected fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="ab3cd-132">Lépjen a **Tárgyi eszközök \> Tárgyi eszközök \> Tárgyi eszközök** menüpontba.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-132">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="ab3cd-133">Válasszon egy eszközt.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-133">Select an asset.</span></span>
1. <span data-ttu-id="ab3cd-134">A Művelet ablaktábla **Eszközkezelés** lapjának **Nézet** csoportjában válassza a **karbantartás alatt álló eszköz** elemet.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-134">On the Action Pane, on the **Asset management** tab, in the **View** group, select **Maintenance asset**.</span></span>

    <span data-ttu-id="ab3cd-135">A kiválasztott tárgyi eszközhöz társított eszközhöz tartozó **karbantartás alatt álló eszköz** oldal megnyílik.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-135">The **Maintenance asset** page for the asset that is associated with the selected fixed asset is opened.</span></span> <span data-ttu-id="ab3cd-136">(Ez a lap általában a **Eszközkezelés \> Ezsközök \> Összes eszköz** helyen található.)</span><span class="sxs-lookup"><span data-stu-id="ab3cd-136">(Typically, this page is found at **Asset management \> Assets \> All assets**.)</span></span>

### <a name="view-maintenance-costs-that-are-associated-with-a-fixed-asset"></a><span data-ttu-id="ab3cd-137">Tárgyi eszközhöz társított karbantartási költségek megtekintése</span><span class="sxs-lookup"><span data-stu-id="ab3cd-137">View maintenance costs that are associated with a fixed asset</span></span>

<span data-ttu-id="ab3cd-138">Az eszközkezelési munkarendeléseket a karbantartás alatt álló eszközökhöz lehet feladni, és az egyes munkarendelések esetében általában költség szerepel.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-138">Asset management work orders can be posted for maintenance assets, and each of those work orders typically has a cost.</span></span> <span data-ttu-id="ab3cd-139">Ha egy tárgyi eszközhöz egy karbantartás alatt álló eszköz van társítva, akkor közvetlenül a tárgyi eszközről is megtekintheti a kapcsolódó költségeket.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-139">When a fixed asset is associated with a maintenance asset, you can go directly from the fixed asset to view the related costs.</span></span>

<span data-ttu-id="ab3cd-140">A tárgyi eszközhöz társított karbantartási költségek megtekintéséhez kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-140">To view the maintenance costs that are associated with a fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="ab3cd-141">Lépjen a **Tárgyi eszközök \> Tárgyi eszközök \> Tárgyi eszközök** menüpontba.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-141">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="ab3cd-142">Válasszon egy eszközt.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-142">Select an asset.</span></span>
1. <span data-ttu-id="ab3cd-143">A Művelet ablaktábla **Eszközkezelés** lapjának **Nézet** csoportjában válassza a **karbantartási költség** elemet.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-143">On the Action Pane, on the **Asset management** tab, in the **View** group, select **Maintenance cost**.</span></span>

    <span data-ttu-id="ab3cd-144">Megnyitja a **karbantartási költség** lapot, és megjeleníti a kapcsolódó költségeket.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-144">The **Maintenance cost** page is opened and shows the related costs.</span></span>

### <a name="create-a-new-maintenance-asset-for-an-existing-fixed-asset"></a><a name="new-maintenance-from-fixed"></a><span data-ttu-id="ab3cd-145">Új karbantartás alatt álló eszköz létrehozása meglévő tárgyi eszközhöz</span><span class="sxs-lookup"><span data-stu-id="ab3cd-145">Create a new maintenance asset for an existing fixed asset</span></span>

<span data-ttu-id="ab3cd-146">Új karbantartás alatt álló eszköz meglévő tárgyi eszközhöz való létrehozásához kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-146">To create a new maintenance asset for an existing fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="ab3cd-147">Lépjen a **Tárgyi eszközök \> Tárgyi eszközök \> Tárgyi eszközök** menüpontba.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-147">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="ab3cd-148">Válasszon egy eszközt.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-148">Select an asset.</span></span>
1. <span data-ttu-id="ab3cd-149">A Művelet ablaktábla **Eszközkezelés** lapjának **Új** csoportjában válassza a **karbantartás alatt álló eszköz létrehozása** elemet.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-149">On the Action Pane, on the **Asset management** tab, in the **New** group, select **Create maintenance asset**.</span></span> <span data-ttu-id="ab3cd-150">(Ha ez a beállítás nem érhető el, előfordulhat, hogy egy karbantartás alatt álló eszköz már hozzá van rendelve a kiválasztott tárgyi eszközhöz.)</span><span class="sxs-lookup"><span data-stu-id="ab3cd-150">(If this option is unavailable, a maintenance asset might already be associated with the selected fixed asset.)</span></span>
1. <span data-ttu-id="ab3cd-151">FEjezze be az eszköz létrehozását az [Eszköz létrehozása](../objects/create-an-object.md) részben leírtaknak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-151">Finish creating the asset as described in [Create an asset](../objects/create-an-object.md).</span></span>

### <a name="create-a-new-fixed-asset-and-add-a-new-maintenance-asset-for-it"></a><span data-ttu-id="ab3cd-152">Új tárgyi eszköz létrehozása és hozzáadása új karbantartás alatt álló eszközhöz</span><span class="sxs-lookup"><span data-stu-id="ab3cd-152">Create a new fixed asset and add a new maintenance asset for it</span></span>

<span data-ttu-id="ab3cd-153">Új tárgyi eszköz létrehozásához és új karbantartás alatt álló eszköz hozzáadásához kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-153">To create a new fixed asset and add a new maintenance asset for it, follow these steps.</span></span>

1. <span data-ttu-id="ab3cd-154">Lépjen a **Tárgyi eszközök \> Tárgyi eszközök \> Tárgyi eszközök** menüpontba.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-154">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="ab3cd-155">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-155">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="ab3cd-156">Fejezze be a tárgyi eszköz létrehozását az [Tárgyi eszköz létrehozása](../../../finance/fixed-assets/tasks/create-fixed-asset.md) részben leírtaknak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-156">Finish creating the fixed asset as described in [Create a fixed asset](../../../finance/fixed-assets/tasks/create-fixed-asset.md).</span></span>
1. <span data-ttu-id="ab3cd-157">A Művelet ablaktábla **Eszközkezelés** lapjának **Új** csoportjában válassza a **karbantartás alatt álló eszköz létrehozása** elemet.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-157">On the Action Pane, on the **Asset management** tab, in the **New** group, select **Create maintenance asset**.</span></span>
1. <span data-ttu-id="ab3cd-158">FEjezze be az eszköz létrehozását az [Eszköz létrehozása](../objects/create-an-object.md) részben leírtaknak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-158">Finish creating the asset as described in [Create an asset](../objects/create-an-object.md).</span></span>

### <a name="remove-the-association-between-two-assets"></a><span data-ttu-id="ab3cd-159">Két eszköz közötti társítás eltávolítása</span><span class="sxs-lookup"><span data-stu-id="ab3cd-159">Remove the association between two assets</span></span>

<span data-ttu-id="ab3cd-160">Bizonyos esetekben előfordulhat, hogy egy karbantartás alatt álló eszköz társítását fel kell oldani egy tárgyi eszközről.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-160">In some cases, you might have to disassociate a maintenance asset from its fixed asset.</span></span> <span data-ttu-id="ab3cd-161">Ha például egy tárgyi eszközből [új karbantartás alatt álló eszközt](#new-maintenance-from-fixed) szeretne létrehozni, előbb el kell távolítania a meglévő társításokat.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-161">For example, if you want to [create a new maintenance asset](#new-maintenance-from-fixed) from a fixed asset, you must first remove any existing association.</span></span>

<span data-ttu-id="ab3cd-162">Karbantartás alatt álló eszköz és tárgyi eszköz közti meglévő társítás eltávolításához kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-162">To remove an existing association between a maintenance asset and a fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="ab3cd-163">Lépjen az **Eszközkezelés \> Eszközök \> Összes eszköz** (vagy **Aktív eszközök**) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-163">Go to **Asset management \> Assets \> All assets** (or **Active assets**).</span></span>
1. <span data-ttu-id="ab3cd-164">Keresse meg és nyissa meg a tárgyi eszközt.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-164">Find and open the fixed asset.</span></span>
1. <span data-ttu-id="ab3cd-165">A **tárgyi eszköz** gyorslapon törölje a jelet az érték a **munkavégzési helyszín** mezőből.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-165">On the **Fixed asset** FastTab, clear the value from the **Functional location** field.</span></span>
1. <span data-ttu-id="ab3cd-166">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab3cd-166">On the Action Pane, select **Save**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]