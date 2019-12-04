---
title: Dimenzión alapuló termékkonfiguráció áttekintése
description: A dimenzión alapuló termékkonfiguráció egy egyszerű megoldás több termékváltozat létrehozására egy alaptermékből és annak anyagjegyzékéből.
author: cvocph
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConfigRule, BOMTable, ConfigChooseFromRoute, ConfigGroup, ConfigHierarchy, EcoResDimensionBasedConfiguration
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19821
ms.assetid: 4db9890b-306b-4be7-ba98-3be2094d561f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ad8c2c82f9104a350d37534e4d70372da82f40a7
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/18/2019
ms.locfileid: "2815042"
---
# <a name="dimension-based-product-configuration-overview"></a><span data-ttu-id="b7275-103">Dimenzión alapuló termékkonfiguráció áttekintése</span><span class="sxs-lookup"><span data-stu-id="b7275-103">Dimension-based product configuration overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b7275-104">A dimenzión alapuló termékkonfiguráció egy egyszerű megoldás több termékváltozat létrehozására egy alaptermékből és annak anyagjegyzékéből.</span><span class="sxs-lookup"><span data-stu-id="b7275-104">Dimension-based product configuration represents a simple solution for creating many product variants from a single product master and its bill of materials.</span></span>

<span data-ttu-id="b7275-105">A dimenzión alapuló termékkonfiguráció egyike a három beépített termék konfigurációs technológiának.</span><span class="sxs-lookup"><span data-stu-id="b7275-105">Dimension-based product configuration is one of the three built-in product configuration technologies.</span></span> <span data-ttu-id="b7275-106">A két másik technológia az előre definiált változatok és a megszorításon alapuló konfiguráció.</span><span class="sxs-lookup"><span data-stu-id="b7275-106">The two other technologies are predefined variants and constraint-based configuration.</span></span> <span data-ttu-id="b7275-107">Minden három technológia alapterméket használ kiindulási pontként, és a felhasználó termékváltozatokat hozhat létre egy alaptermékhez.</span><span class="sxs-lookup"><span data-stu-id="b7275-107">All three technologies use a product master as the starting point and allow the user to create many product variants for one product master.</span></span>

## <a name="key-concepts"></a><span data-ttu-id="b7275-108">Alapfogalmak</span><span class="sxs-lookup"><span data-stu-id="b7275-108">Key concepts</span></span>
<span data-ttu-id="b7275-109">A dimenzión alapuló termékkonfiguráció a következő alapfogalmakon alapszik:</span><span class="sxs-lookup"><span data-stu-id="b7275-109">Dimension-based product configuration is based on the following key concepts:</span></span>

-   <span data-ttu-id="b7275-110">Alaptermékek</span><span class="sxs-lookup"><span data-stu-id="b7275-110">Product masters</span></span>
-   <span data-ttu-id="b7275-111">Termékdimenzió konfigurációja</span><span class="sxs-lookup"><span data-stu-id="b7275-111">Configuration product dimension</span></span>
-   <span data-ttu-id="b7275-112">Konfigurációs csoportok</span><span class="sxs-lookup"><span data-stu-id="b7275-112">Configuration groups</span></span>
-   <span data-ttu-id="b7275-113">Anyagjegyzék (BOM)</span><span class="sxs-lookup"><span data-stu-id="b7275-113">Bill of materials (BOM)</span></span>
-   <span data-ttu-id="b7275-114">Konfigurációs útvonal</span><span class="sxs-lookup"><span data-stu-id="b7275-114">Configuration route</span></span>
-   <span data-ttu-id="b7275-115">Konfigurációs szabályok</span><span class="sxs-lookup"><span data-stu-id="b7275-115">Configuration rules</span></span>

### <a name="product-masters"></a><span data-ttu-id="b7275-116">Alaptermékek</span><span class="sxs-lookup"><span data-stu-id="b7275-116">Product masters</span></span>

<span data-ttu-id="b7275-117">Egy alaptermék lesz a kiindulópont minden termék konfigurációs folyamathoz.</span><span class="sxs-lookup"><span data-stu-id="b7275-117">A product master is the starting point for any product configuration process.</span></span> <span data-ttu-id="b7275-118">A termék dimenzión alapuló konfigurációjához szükség van egy alaptermékre ezzel az adott konfigurálási technológiával és termékdimenzió csoporttal, amely tartalmazza a konfigurációs termékdimenziót.</span><span class="sxs-lookup"><span data-stu-id="b7275-118">For the dimension-based product configuration, you need a product master with this particular configuration technology and a product dimension group that includes the configuration product dimension.</span></span>

### <a name="configuration-product-dimension"></a><span data-ttu-id="b7275-119">Termékdimenzió konfigurációja</span><span class="sxs-lookup"><span data-stu-id="b7275-119">Configuration product dimension</span></span>

<span data-ttu-id="b7275-120">A konfigurációs termékdimenzió egy alaptermék termékváltozatainak azonosítására használható, a dimenzión alapuló konfiguráció technológiával.</span><span class="sxs-lookup"><span data-stu-id="b7275-120">The configuration product dimension is used to identify the product variants for a product master with the dimension-based configuration technology.</span></span> <span data-ttu-id="b7275-121">A konfigurációs dimenzió értékét a felhasználó adja meg, és az egyedi termékváltozatok azonosításában segít.</span><span class="sxs-lookup"><span data-stu-id="b7275-121">The configuration dimension value is entered by the user and should help to identify the individual product variants.</span></span>

### <a name="configuration-groups"></a><span data-ttu-id="b7275-122">Konfigurációs csoportok</span><span class="sxs-lookup"><span data-stu-id="b7275-122">Configuration groups</span></span>

<span data-ttu-id="b7275-123">A konfigurációs csoportok egy központi tárházban meghatározottak, és minden dimenzión alapuló termékkonfigurációs modellhez használható.</span><span class="sxs-lookup"><span data-stu-id="b7275-123">Configuration groups are defined in a central repository and can be used for all dimension-based product configuration models.</span></span> <span data-ttu-id="b7275-124">A konfigrációs csoportok különböző anyagjegyzék sorokhoz vannak társítva, és együtt sorcsoportokat alkotnak, amelyek kölcsönösen kizárólagosak.</span><span class="sxs-lookup"><span data-stu-id="b7275-124">Configuration groups are associated to the individual BOM lines and hold together a group of lines that are mutually exclusive.</span></span> <span data-ttu-id="b7275-125">Ez azt jelenti, hogy a csoportnak csak egy sora lehet kiválasztva egy termékváltozathoz.</span><span class="sxs-lookup"><span data-stu-id="b7275-125">This means that only one line in a group can be selected for a single product variant.</span></span>

### <a name="bill-of-materials-bom"></a><span data-ttu-id="b7275-126">Anyagjegyzék (BOM)</span><span class="sxs-lookup"><span data-stu-id="b7275-126">Bill of materials (BOM)</span></span>

<span data-ttu-id="b7275-127">Az anyagjegyzék a dimenzión alapuló termékkonfiguráció felépítési egységét képviseli.</span><span class="sxs-lookup"><span data-stu-id="b7275-127">The BOM represent the building blocks for a dimension-based product configuration.</span></span> <span data-ttu-id="b7275-128">Minden különböző terméket tartalmaznia kell, amely bármely termékváltozatban használható.</span><span class="sxs-lookup"><span data-stu-id="b7275-128">It must include all the different products that can be used in any product variant.</span></span> <span data-ttu-id="b7275-129">Az anyagjegyzék minden sora hivatkozhat egy konfigurációs csoportot.</span><span class="sxs-lookup"><span data-stu-id="b7275-129">Each line in the BOM can reference a configuration group.</span></span> <span data-ttu-id="b7275-130">Ha a sor nem hivatkozik egy konfigurációs csoportot, akkor szerepelni fog az összes termékváltozatban.</span><span class="sxs-lookup"><span data-stu-id="b7275-130">If a line doesn’t reference a configuration group, it will be included in all product variants.</span></span>

### <a name="configuration-route"></a><span data-ttu-id="b7275-131">Konfigurációs útvonal</span><span class="sxs-lookup"><span data-stu-id="b7275-131">Configuration route</span></span>

<span data-ttu-id="b7275-132">A konfigurációs útvonal határozza meg a konfigurációs csoportok sorozatát, amelyek megjelennek a felhasználó számára a termék-konfigurálás során.</span><span class="sxs-lookup"><span data-stu-id="b7275-132">The configuration route determines the sequence of the configuration groups, as they will be displayed to the user during the product configuration process.</span></span>

### <a name="configuration-rules"></a><span data-ttu-id="b7275-133">Konfigurációs szabályok</span><span class="sxs-lookup"><span data-stu-id="b7275-133">Configuration rules</span></span>

<span data-ttu-id="b7275-134">A konfigurációs szabályok egy meg megfeleltetést képviselnek, amely biztosítja, hogy a termék egy konfigurációs csoporthoz tartozik az anyagjegyzékben, amely megköveteli a termék hozzárendelését vagy kizárását különböző konfigurációs csoportokból ugyanabban az anyagjegyzékben.</span><span class="sxs-lookup"><span data-stu-id="b7275-134">The configuration rules represent a mechanism for ensuring that a product included in one configuration group in a BOM enforces either an inclusion or an exclusion of a product in a different configuration group in the same BOM.</span></span>

## <a name="product-modeling-process"></a><span data-ttu-id="b7275-135">Termékmodellezési folyamat</span><span class="sxs-lookup"><span data-stu-id="b7275-135">Product modeling process</span></span>
<span data-ttu-id="b7275-136">Egy termékmodell építés természetes sorozata, egy dimenzión alapuló termékhez, a kívánt konfigurációs csoportok meghatározásával kezdődik.</span><span class="sxs-lookup"><span data-stu-id="b7275-136">The natural sequence for building a product model for a dimension-based product starts with defining the relevant configuration groups.</span></span> <span data-ttu-id="b7275-137">Fontos, hogy az összes anyagjegyzékben használandó termék ahhoz a vállalathoz legyen kiadva, amelyhez a termékmodell épült.</span><span class="sxs-lookup"><span data-stu-id="b7275-137">It is important to ensure that all products which will be used in the BOM have been released to the company that the product model is built for.</span></span> <span data-ttu-id="b7275-138">Ha a felépítési egységek a helyükön vannak, a felhasználó létrehozhat anyagjegyzéket és hozzárendelhet konfigurációs csoportokat az anyagjegyzék érintett soraihoz.</span><span class="sxs-lookup"><span data-stu-id="b7275-138">With these building blocks in place, the user can create the BOM and assign configuration groups to all relevant BOM lines.</span></span> <span data-ttu-id="b7275-139">Ha az anyagjegyzék kész, a konfigurációs útvonal meghatározható a konfigurációs csoportok a megfelelő sorrendben történő rendeléséhez.</span><span class="sxs-lookup"><span data-stu-id="b7275-139">When the BOM is complete, a configuration route can be defined for ordering the configuration groups in the proper sequence.</span></span> <span data-ttu-id="b7275-140">[![Dimenzión alapuló termékmodellezési folyamat](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) Létrehozhat termékkapcsolatot biztosító szabályokat arra az esetre, ha különböző konfigurációs csoportokban található termékeket együtt kell használni, vagy nem használhatóak együtt.</span><span class="sxs-lookup"><span data-stu-id="b7275-140">[![Dimension-based product modeling process](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) If there are certain products from different configuration groups that either must or must not be used together, you can create configuration rules that will enforce these product relationships.</span></span> <span data-ttu-id="b7275-141">Miután az anyagjegyzéket egy anyagjegyzék verzió hozzákapcsolta egy dimenzión alapuló alaptermékhez és mindekettő elfogadása és aktválása után, létrehozhat termékkonfigurációkat, és mindegyiknek nevet adhat.</span><span class="sxs-lookup"><span data-stu-id="b7275-141">After the BOM has been tied together with a dimension-based product master through a BOM version and both have been approved and activated, you can create product configurations and enter a name for each configuration.</span></span> <span data-ttu-id="b7275-142">A konfigurációkat a tranzakciók generálása előtt létre lehet hozni, vagy amikor szükség van egy bizonyos konfigurációra.</span><span class="sxs-lookup"><span data-stu-id="b7275-142">The configurations can be defined before any transactions are generated or it can be done when the need for a certain configuration occurs.</span></span>

### <a name="suggested-use"></a><span data-ttu-id="b7275-143">Javasolt használat</span><span class="sxs-lookup"><span data-stu-id="b7275-143">Suggested use</span></span>

<span data-ttu-id="b7275-144">A dimenzión alapuló konfiguráció technológiát legjobban olyan termékeknél lehet alkalmazni, amelyek változtathatósága korlátozott, és az alap termékdimenziókkal, mérettel, színnel, vagy konfigurációval nem lehet azonosítani a termékváltozatot.</span><span class="sxs-lookup"><span data-stu-id="b7275-144">The dimension-based configuration technology is best used for products with limited variability and the combination of the standard product dimensions size, color, style, and configuration is unsuitable for identifying a specific product variant.</span></span> <span data-ttu-id="b7275-145">Ilyen lehet például a kerékpár keret magassága, kerék mérete, fékbetét-típusok és különböző fokozatok.</span><span class="sxs-lookup"><span data-stu-id="b7275-145">An example could be bicycle with frame height, wheel size, brake types, and different gears.</span></span>

### <a name="next-step"></a><span data-ttu-id="b7275-146">Következő lépés</span><span class="sxs-lookup"><span data-stu-id="b7275-146">Next step</span></span> 

<span data-ttu-id="b7275-147">A következő nyolc feladatútmutató abban a sorrendben van felsorolva, amelyben teljesítenie kell őket.</span><span class="sxs-lookup"><span data-stu-id="b7275-147">The following eight task guides are listed in the order in which you should complete them.</span></span> 

1.  [<span data-ttu-id="b7275-148">Dimenzión alapuló alaptermék létrehozása</span><span class="sxs-lookup"><span data-stu-id="b7275-148">Create a dimension-based product master</span></span>](tasks/create-dimension-based-product-master.md)
2.  [<span data-ttu-id="b7275-149">Dimenzión alapuló alaptermék kibocsátása</span><span class="sxs-lookup"><span data-stu-id="b7275-149">Release a dimension-based product master</span></span>](tasks/release-dimension-based-product-master.md)
3.  [<span data-ttu-id="b7275-150">Kiadott alaptermék alapbeállításának kitöltése</span><span class="sxs-lookup"><span data-stu-id="b7275-150">Complete basic setup of a released product master</span></span>](tasks/complete-basic-setup-released-product-master.md)
4.  [<span data-ttu-id="b7275-151">Konfigurációs csoportok meghatározása</span><span class="sxs-lookup"><span data-stu-id="b7275-151">Define configuration groups</span></span>](tasks/define-configuration-groups.md)
5.  [<span data-ttu-id="b7275-152">A dimenzión alapuló alaptermékre vonatkozó anyagjegyzék létrehozása</span><span class="sxs-lookup"><span data-stu-id="b7275-152">Create a bill of materials for a dimension-based product master</span></span>](tasks/create-bill-materials-dimension-based-product-master.md)
6.  [<span data-ttu-id="b7275-153">Konfigurációs útvonalak meghatározása</span><span class="sxs-lookup"><span data-stu-id="b7275-153">Define configuration routes</span></span>](tasks/define-configuration-route.md)
7.  [<span data-ttu-id="b7275-154">Konfigurációs szabályok létrehozása</span><span class="sxs-lookup"><span data-stu-id="b7275-154">Create configuration rules</span></span>](tasks/create-configuration-rules.md)
8.  [<span data-ttu-id="b7275-155">Dimenzión alapuló konfigurációk létrehozása</span><span class="sxs-lookup"><span data-stu-id="b7275-155">Create dimension-based configurations</span></span>](tasks/create-dimension-based-configurations.md)

