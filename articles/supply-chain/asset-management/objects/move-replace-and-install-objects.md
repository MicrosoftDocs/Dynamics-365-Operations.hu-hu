---
title: Eszközök áthelyezése, cseréje és telepítése
description: Ez a témakör bemutatja, hogyan lehet eszközöket áthelyezni, kicserélni és telepíteni az Eszközkezelés modulban.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectReplace, EntAssetObjectInstallLookup, EntAssetObjectMove, EntAssetObjectTableEditSubObjects
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c6d7a9c86029505602c562a3de4d2f52eace866f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808544"
---
# <a name="move-replace-and-install-assets"></a><span data-ttu-id="4df06-103">Eszközök áthelyezése, cseréje és telepítése</span><span class="sxs-lookup"><span data-stu-id="4df06-103">Move, replace, and install assets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="4df06-104">Ez a témakör bemutatja, hogyan lehet eszközöket áthelyezni, kicserélni és telepíteni az Eszközkezelés modulban.</span><span class="sxs-lookup"><span data-stu-id="4df06-104">This topic explains how to move, replace, and install assets in Asset Management.</span></span> <span data-ttu-id="4df06-105">Létrehozhat olyan egyedi eszközöket, amelyeknek nincs kapcsolata más eszközökkel, vagy létrehozhat egy olyan eszközstruktúrát, amely egy fölérendelt eszközt (legfelső szintű eszköz) és a kapcsolódó alárendelt eszközöket (aleszközök) tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="4df06-105">You can create individual assets that have no relations to other assets, or you can create an asset structure that includes a parent asset (top-level asset) and related child assets (sub-assets).</span></span> <span data-ttu-id="4df06-106">Az Eszközkezelésben három módszerrel mozgathatja az eszközt és módosíthatja a helyét:</span><span class="sxs-lookup"><span data-stu-id="4df06-106">In Asset Management, there are three approaches to moving and changing the location of an asset:</span></span>

- <span data-ttu-id="4df06-107">**Áthelyezés** – Az eszköz áthelyezése egy másik eszközszerkezetbe vagy ugyanazon eszközstruktúra más helyére.</span><span class="sxs-lookup"><span data-stu-id="4df06-107">**Move** – Move an asset either to another asset structure or to another location in the same asset structure.</span></span>
- <span data-ttu-id="4df06-108">**Csere** – Ideiglenesen eltávolít egy eszközt az eszközstruktúrából javítási vagy felújítási céllal, majd visszahelyezi a javított eszközt később az eszközstruktúrába.</span><span class="sxs-lookup"><span data-stu-id="4df06-108">**Replace** – Temporarily remove an asset from an asset structure so that it can be repaired or refurbished, and then add the refurbished asset back to the asset structure later.</span></span> <span data-ttu-id="4df06-109">Vagy véglegesen lecserélheti a használt eszközt egy új eszközre.</span><span class="sxs-lookup"><span data-stu-id="4df06-109">Alternatively, permanently replace a used asset with a new asset.</span></span>
- <span data-ttu-id="4df06-110">**Telepítés** – Egy fölérendelt eszközt és bármely kapcsolódó alárendelt eszközt telepít egy munkavégzési helyszínre.</span><span class="sxs-lookup"><span data-stu-id="4df06-110">**Install** – Install a parent asset and any related child assets on a functional location.</span></span>

> [!NOTE]
> <span data-ttu-id="4df06-111">A mozgatott, áthelyezett vagy telepített eszköz kapcsolódhat másik munkavégzési helyszínhez is.</span><span class="sxs-lookup"><span data-stu-id="4df06-111">The asset that you move, replace, or install might be related to another functional location.</span></span> <span data-ttu-id="4df06-112">Ebben az esetben előfordulhat, hogy az eszköz a munkavégzési helyszín pénzügyi dimenzióit használja.</span><span class="sxs-lookup"><span data-stu-id="4df06-112">In that case, the asset might use financial dimensions of the functional location.</span></span> <span data-ttu-id="4df06-113">A **Munkavégzési helyszíntípusok** lapon állíthatja be a pénzügyi dimenziók kezelését a munkavégzési helyszíneken.</span><span class="sxs-lookup"><span data-stu-id="4df06-113">On the **Functional location types** page, you set up the handling of financial dimensions on functional locations.</span></span>

## <a name="move-asset"></a><span data-ttu-id="4df06-114">Eszköz áthelyezése</span><span class="sxs-lookup"><span data-stu-id="4df06-114">Move asset</span></span>

<span data-ttu-id="4df06-115">Az **Eszköz áthelyezése** funkcióval egy másik eszközszerkezetbe vagy ugyanazon eszközstruktúra más helyére helyezheti át az eszközt.</span><span class="sxs-lookup"><span data-stu-id="4df06-115">Use the **Move asset** function to move an asset either to another asset structure or to another location in the same asset structure.</span></span> <span data-ttu-id="4df06-116">Az eszközt ki is veheti egy eszközszerkezetből úgy, hogy önálló eszközként álljon, amelynek nincsenek szerkezeti kapcsolatai.</span><span class="sxs-lookup"><span data-stu-id="4df06-116">You can also move an asset out of an asset structure so that it becomes a standalone asset that has no structure relations.</span></span>

> [!NOTE]
> <span data-ttu-id="4df06-117">Ne használja ezt a funkciót, ha az eszközöket javítja, vagy csak ideiglenesen lecseréli.</span><span class="sxs-lookup"><span data-stu-id="4df06-117">Don't use this function if assets are being repaired or temporarily replaced.</span></span> <span data-ttu-id="4df06-118">Ehelyett használja a témakör későbbi részében ismertetett **Eszköz cseréje** funkciót.</span><span class="sxs-lookup"><span data-stu-id="4df06-118">Instead, use the **Replace asset** functionality that is described later in this topic.</span></span>

1. <span data-ttu-id="4df06-119">Válassza ki az **Eszközkezelés** \> **Általános** \> **Eszközök** \> **Összes eszköz** vagy **Aktív eszközök** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4df06-119">Select **Asset management** \> **Common** \> **Assets** \> **All assets** or **Active assets**.</span></span>
2. <span data-ttu-id="4df06-120">A listából válassza ki az áthelyezni kívánt eszközt.</span><span class="sxs-lookup"><span data-stu-id="4df06-120">In the list, select the asset to move.</span></span> <span data-ttu-id="4df06-121">Ha az eszköz rendelkezik alárendelt eszközökkel, akkor ezeket az eszközöket is áthelyezi.</span><span class="sxs-lookup"><span data-stu-id="4df06-121">If the asset has child assets, you also move those assets.</span></span>
3. <span data-ttu-id="4df06-122">Válassza az **Eszköz áthelyezése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4df06-122">Select **Move asset**.</span></span>
4. <span data-ttu-id="4df06-123">Ha úgy szeretné áthelyezni az eszközt, hogy az eszközstruktúra részévé váljon, válassza ki az új fölérendelt eszközt a **Fölérendelt eszköz** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4df06-123">To move the asset so that it becomes part of an asset structure, select the new parent asset in the **Parent asset** field.</span></span> <span data-ttu-id="4df06-124">Ha alárendelt eszközt helyez át, vagy különálló, szerkeszeti kapcsolatokkal nem rendelkező eszközzé szeretné alakítani, hagyja üresen a **fölérendelt eszköz** mezőt.</span><span class="sxs-lookup"><span data-stu-id="4df06-124">If you're moving a child asset, and you want to make it a standalone asset that has no structure relations, leave the **Parent asset** field blank.</span></span>
5. <span data-ttu-id="4df06-125">Alapértelmezett módon a **Hatályos** mező értéke az aktuális dátum és időpont lesz.</span><span class="sxs-lookup"><span data-stu-id="4df06-125">By default, the **Effective** field is set to the current date and time.</span></span> <span data-ttu-id="4df06-126">Választhat azonban másik dátumot és időpontot is, amikortól az eszköz áthelyezése hatályos.</span><span class="sxs-lookup"><span data-stu-id="4df06-126">However, you can select a different date and time that the asset move is valid from.</span></span>
6. <span data-ttu-id="4df06-127">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4df06-127">Select **OK**.</span></span>

## <a name="replace-asset"></a><span data-ttu-id="4df06-128">Eszköz cseréje</span><span class="sxs-lookup"><span data-stu-id="4df06-128">Replace asset</span></span>

<span data-ttu-id="4df06-129">Az **Eszköz cseréje** funkció használata az elhasználódott eszköz javítási, felújítási vagy tartós lecserélésére használható egy új eszköz által.</span><span class="sxs-lookup"><span data-stu-id="4df06-129">Use the **Replace asset** function in connection with repairs, refurbishment, or permanent replacement of a worn-out asset by a new asset.</span></span> <span data-ttu-id="4df06-130">Ennek a funkciónak a segítségével helyettesítheti az alárendelt eszközöket egy eszközstruktúrában.</span><span class="sxs-lookup"><span data-stu-id="4df06-130">This function is used to replace child assets in an asset structure.</span></span> <span data-ttu-id="4df06-131">A fölérendelt eszközöknél (az olyan eszközöknél, amelyek aktuálisan nem rendelkeznek fölérendelt eszközzel), a cserét a munkavégzési helyszínen hajtják végre.</span><span class="sxs-lookup"><span data-stu-id="4df06-131">For parent assets (that is, assets that don't currently have a parent asset), this replacement is done on a functional location.</span></span> <span data-ttu-id="4df06-132">A fölérendelt eszközök munkavégzési helyszínen való cseréjével kapcsolatos további információkért tekintse meg az [Eszközök telepítése munkavégzési helyszíneken](../functional-locations/install-objects-on-functional-locations.md) című részt.</span><span class="sxs-lookup"><span data-stu-id="4df06-132">For more information about how to replace parent assets on a functional location, see [Install assets on functional locations](../functional-locations/install-objects-on-functional-locations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4df06-133">Ha a termeléi osztályhoz javítóműhely is kapcsolódik, akkor létrehozhat olyan munkavégzési helyszíneket, mint **Javítás**, **Selejt** és **Tárolás**, amellyel az eszközök javítása és cseréje kezelhető.</span><span class="sxs-lookup"><span data-stu-id="4df06-133">If a repair shop is related to your production department, you can create functional locations such as **Repair**, **Scrap**, and **Storage** to handle the repair and replacement of assets.</span></span>

1. <span data-ttu-id="4df06-134">Válassza ki az **Eszközkezelés** \> **Általános** \> **Eszközök** \> **Összes eszköz** vagy **Aktív eszközök** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4df06-134">Select **Asset management** \> **Common** \> **Assets** \> **All assets** or **Active assets**.</span></span>
2. <span data-ttu-id="4df06-135">Válassza ki a listából a lecserélni kívánt alárendelt eszközt.</span><span class="sxs-lookup"><span data-stu-id="4df06-135">In the list, select the child asset to replace.</span></span> <span data-ttu-id="4df06-136">Ha az eszköz rendelkezik alárendelt eszközökkel, akkor ezeket az eszközöket is lecseréli.</span><span class="sxs-lookup"><span data-stu-id="4df06-136">If the asset has child assets, you also replace those assets.</span></span>
3. <span data-ttu-id="4df06-137">Válassza az **Eszköz cseréje** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4df06-137">Select **Replace asset**.</span></span>

    <span data-ttu-id="4df06-138">A **Struktúraváltozás** mezőben látható a kiválasztott eszköz és a kapcsolódó alárendelt eszközök eszközszerkezetben történt legutóbbi mozgatásának dátuma és időpontja.</span><span class="sxs-lookup"><span data-stu-id="4df06-138">The **Structure change** field shows the last date and time that the selected asset and related child assets were moved in the asset structure.</span></span>

4. <span data-ttu-id="4df06-139">A **Kiválasztott eszköz** szakasz **Cél munkavégzési helyszín** mezőjében válassza ki azt a munkavégzési helyszínt, ahova mozgatni szeretné az eszközt.</span><span class="sxs-lookup"><span data-stu-id="4df06-139">In the **Selected asset** section, in the **Target functional location** field, select the functional location to move the asset to.</span></span> <span data-ttu-id="4df06-140">Válassza például a **Javítás** vagy a **Selejt** helyet.</span><span class="sxs-lookup"><span data-stu-id="4df06-140">For example, select the **Repair** or **Scrap** location.</span></span>

    <span data-ttu-id="4df06-141">A **fölérendelt eszköz** szakasz **Hatályos** mezője azt az utolsó dátumot és időpontot mutatja, amikor a fölérendelt eszköz és a kapcsolódó alárendelt eszközök telepítése vagy áthelyezése az aktuális munkavégzési helyszínen megtörtént.</span><span class="sxs-lookup"><span data-stu-id="4df06-141">In the **Parent asset** section, the **Effective** field shows the last date and time that the parent asset and related child assets were installed or moved on the current functional location.</span></span>

5. <span data-ttu-id="4df06-142">Az **Új eszköz** szakasz **Eszköz** mezőjében válassza ki azt az eszközt, amelyet a kijelölt eszköz ideiglenes vagy végleges helyettesítési eszközeként kíván beszúrni.</span><span class="sxs-lookup"><span data-stu-id="4df06-142">In the **New asset** section, in the **Asset** field, select the asset to insert as a temporary or permanent replacement for the selected asset.</span></span> <span data-ttu-id="4df06-143">Előfordulhat, hogy az eszköz jelenleg egy másik munkavégzési helyszínen található, például a **Tárolás** helyen.</span><span class="sxs-lookup"><span data-stu-id="4df06-143">This asset might currently be located on another functional location, such as **Storage**.</span></span>
7. <span data-ttu-id="4df06-144">A **Hatályosság kezdete** szakaszban a **Hatályos** mező értéke alapértelmezett módon az aktuális dátum és időpont lesz.</span><span class="sxs-lookup"><span data-stu-id="4df06-144">In the **Effective from** section, the **Effective** field is set to the current date and time by default.</span></span> <span data-ttu-id="4df06-145">Választhat azonban másik dátumot és időpontot is, amikortól az eszköz cseréje hatályos.</span><span class="sxs-lookup"><span data-stu-id="4df06-145">However, you can select a different date and time that the asset replacement is valid from.</span></span>
8. <span data-ttu-id="4df06-146">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4df06-146">Select **OK**.</span></span>

## <a name="install-asset"></a><span data-ttu-id="4df06-147">Eszköz telepítése</span><span class="sxs-lookup"><span data-stu-id="4df06-147">Install asset</span></span>

<span data-ttu-id="4df06-148">Az **Eszköz telepítése** funkcióval egy eszközstruktúrát telepíthet egy munkavégzési helyszínre.</span><span class="sxs-lookup"><span data-stu-id="4df06-148">Use the **Install asset** function to install an asset structure on a functional location.</span></span>

> [!NOTE]
> <span data-ttu-id="4df06-149">Mindig jelöljön ki egy fölérendelt eszközt.</span><span class="sxs-lookup"><span data-stu-id="4df06-149">Always select a parent asset.</span></span> <span data-ttu-id="4df06-150">A fölérendelt eszköz és a kapcsolódó alárendelt eszközök a kijelölt munkavégzési helyszínre kerülnek.</span><span class="sxs-lookup"><span data-stu-id="4df06-150">The parent asset and related child assets will be moved to the selected functional location.</span></span>

1. <span data-ttu-id="4df06-151">Válassza ki az **Eszközkezelés** \> **Általános** \> **Eszközök** \> **Összes eszköz** vagy **Aktív eszközök** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4df06-151">Select **Asset management** \> **Common** \> **Assets** \> **All assets** or **Active assets**.</span></span>
2. <span data-ttu-id="4df06-152">A listában jelölje ki a fölérendelt eszközt, amelyet másik munkavégzési helyszínen szeretne telepíteni.</span><span class="sxs-lookup"><span data-stu-id="4df06-152">In the list, select the parent asset to install on another functional location.</span></span>
3. <span data-ttu-id="4df06-153">Válassza az **Eszköz telepítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4df06-153">Select **Install asset**.</span></span>

    <span data-ttu-id="4df06-154">Az **Attribútumok** szakasz mutatja a fölérendelt eszköznél beállított eszközattribútumokat.</span><span class="sxs-lookup"><span data-stu-id="4df06-154">The **Attributes** section shows the asset attributes that are set up on the parent asset.</span></span>

4. <span data-ttu-id="4df06-155">A **Munkavégzési helyszín** mezőben válassza ki az új helyet.</span><span class="sxs-lookup"><span data-stu-id="4df06-155">In the **Functional location** field, select the new location.</span></span>
5. <span data-ttu-id="4df06-156">Alapértelmezett módon a **Hatályos** mező értéke az aktuális dátum és időpont lesz.</span><span class="sxs-lookup"><span data-stu-id="4df06-156">By default, the **Effective** field is set to the current date and time.</span></span> <span data-ttu-id="4df06-157">Választhat azonban másik dátumot és időpontot is, amikortól az eszközstruktúra telepítése hatályos.</span><span class="sxs-lookup"><span data-stu-id="4df06-157">However, you can select a different date and time that the installation on the asset structure is valid from.</span></span>
6. <span data-ttu-id="4df06-158">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4df06-158">Select **OK**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]