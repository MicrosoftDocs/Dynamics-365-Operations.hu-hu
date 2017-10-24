---
title: "Konfigurációs szabályok"
description: "Ez a cikk a konfigurációs szabályokkal kapcsolatos általános információkat tartalmazza. A konfigurációs szabályok meghatározzák a dimenzió alapú konfigurációs technológiát alkalmazó termékek anyagjegyzékében (BOM) szereplő cikkek kapcsolatát."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMConfigRule
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19761
ms.assetid: e4c6622d-1e2d-4a4d-8047-c553a25d4f87
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 72395b5068f0893d79be6f8095dae988c224d0aa
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="configuration-rules"></a><span data-ttu-id="926fb-104">Konfigurációs szabályok</span><span class="sxs-lookup"><span data-stu-id="926fb-104">Configuration rules</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="926fb-105">Ez a cikk a konfigurációs szabályokkal kapcsolatos általános információkat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="926fb-105">This article provides general information about configuration rules.</span></span> <span data-ttu-id="926fb-106">A konfigurációs szabályok meghatározzák a dimenzió alapú konfigurációs technológiát alkalmazó termékek anyagjegyzékében (BOM) szereplő cikkek kapcsolatát.</span><span class="sxs-lookup"><span data-stu-id="926fb-106">Configuration rules define relationships between items in a bill of materials (BOM) for products that use the dimension-based configuration technology.</span></span>

<span data-ttu-id="926fb-107">A konfigurációs szabályok dimenzión alapuló konfigurációs modellek definiálásakor érhetők el.</span><span class="sxs-lookup"><span data-stu-id="926fb-107">Configuration rules are available when you define dimension-based configuration models.</span></span> <span data-ttu-id="926fb-108">A konfigurációs szabályok segítségével megadott cikk-kombinációkat tehet kötelezővé vagy tilthat le egy anyagjegyzékben (AJ).</span><span class="sxs-lookup"><span data-stu-id="926fb-108">Configuration rules are used to either enforce or prohibit specific item combinations in a bill of materials (BOM).</span></span> <span data-ttu-id="926fb-109">Miután anyagjegyzéket (AJ) hozott létre, és a megfelelő cikkek hozzá lettek rendelve a megfelelő konfigurációs csoportokhoz, egy vagy több konfigurációs szabály adható meg.</span><span class="sxs-lookup"><span data-stu-id="926fb-109">After a BOM has been created and the relevant items have been assigned to their respective configuration groups, one or more configuration rules can be defined.</span></span> <span data-ttu-id="926fb-110">Ha két elem összetartozik, a **Kiválasztás** operátor használatával biztosítható a felvétel.</span><span class="sxs-lookup"><span data-stu-id="926fb-110">If two items belong together, the **Select** operator is used to ensure inclusion.</span></span> <span data-ttu-id="926fb-111">Ha két cikk kölcsönösen kizárja egymást, a **Kijelölés megszüntetése** operátor használatával biztosítható a kizárás.</span><span class="sxs-lookup"><span data-stu-id="926fb-111">If two items are mutually exclusive, the **Deselect** operator is used to ensure exclusion.</span></span>  

<span data-ttu-id="926fb-112">**Megjegyzés:** Ez az információ csak a dimenzión alapuló konfigurációs technológiát használó alaptermékekre vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="926fb-112">**Note:** This information applies only to product masters that use the dimension-based configuration technology.</span></span>  

<span data-ttu-id="926fb-113">A létező konfigurációkra nem vonatkoznak a konfigurációs szabályok későbbi módosításai.</span><span class="sxs-lookup"><span data-stu-id="926fb-113">Existing configurations aren't affected by subsequent changes to the configuration rules.</span></span> <span data-ttu-id="926fb-114">Fontos azonban, hogy a szabályokat az új konfiguráció megadása előtt beállítsa, illetve ellenőrizze őket, ha úgy gondolja, hogy módosultak.</span><span class="sxs-lookup"><span data-stu-id="926fb-114">However, it's important that you set the rules before you define a new configuration, and that you check the rules if you think they have been changed.</span></span>  

<span data-ttu-id="926fb-115">**Megjegyzés:** a **Kijelölés** módszernél a származtatott konfigurációs csoport, cikkszám és konfiguráció automatikusan lesz kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="926fb-115">**Note:** For the **Select** method, the derived configuration group, item number, and configuration are automatically selected.</span></span> <span data-ttu-id="926fb-116">A **Kijelölés megszüntetése** módszer használata esetén a származtatott konfigurációs csoport, cikkszám és konfiguráció nem választható ki.</span><span class="sxs-lookup"><span data-stu-id="926fb-116">For the **Deselect** method, the derived configuration group, item number, and configuration can't be selected.</span></span>

<a name="see-also"></a><span data-ttu-id="926fb-117">Lásd még</span><span class="sxs-lookup"><span data-stu-id="926fb-117">See also</span></span>
--------

[<span data-ttu-id="926fb-118">Dimenzión alapuló termékkonfiguráció</span><span class="sxs-lookup"><span data-stu-id="926fb-118">Dimension-based product configuration</span></span>](dimension-based-product-configuration.md)



