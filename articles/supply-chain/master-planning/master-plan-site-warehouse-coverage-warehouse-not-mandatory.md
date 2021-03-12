---
title: Alaptervezés hely- és raktárfedezethez, a raktár nem kötelező
description: Ez a témakör leírja, hogyan terveznek meg egy fedezeti dimenziókként webhellyel ás raktárral rendelkező cikket. A raktár dimenzió nincs kötelezően beállítva.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2514
ms.assetid: 92d47bdd-df68-4f60-ac9a-96aa08236c26
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cdd3614e52da72e32e6781bc8da7c9e2b3162832
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970406"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-not-mandatory"></a><span data-ttu-id="82d8e-104">Alaptervezés hely- és raktárfedezethez, a raktár nem kötelező</span><span class="sxs-lookup"><span data-stu-id="82d8e-104">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="82d8e-105">Ez a témakör leírja, hogyan terveznek meg egy fedezeti dimenziókként webhellyel ás raktárral rendelkező cikket.</span><span class="sxs-lookup"><span data-stu-id="82d8e-105">This topic describes how an item that has site and warehouse as coverage dimensions is planned.</span></span> <span data-ttu-id="82d8e-106">A raktár dimenzió nincs kötelezően beállítva.</span><span class="sxs-lookup"><span data-stu-id="82d8e-106">The warehouse dimension is not mandatory.</span></span>

<span data-ttu-id="82d8e-107">Ez az alaptervezési eset a következő feltételeket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="82d8e-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="82d8e-108">A telephelydimenzió kötelezőre van állítva, és meg kell adni az igénytranzakcióban.</span><span class="sxs-lookup"><span data-stu-id="82d8e-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span> <span data-ttu-id="82d8e-109">Ez a beállítás nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="82d8e-109">This setting can't be modified.</span></span>
-   <span data-ttu-id="82d8e-110">A raktár dimenzió nincs kötelezően beállítva.</span><span class="sxs-lookup"><span data-stu-id="82d8e-110">The warehouse dimension is not set to mandatory.</span></span> <span data-ttu-id="82d8e-111">Lehet, hogy a raktár ismert, de ez nem befolyásolja az alapütemezési számítást.</span><span class="sxs-lookup"><span data-stu-id="82d8e-111">The warehouse may be known, but it is not used in the master planning calculation.</span></span>
-   <span data-ttu-id="82d8e-112">A telephely és raktár dimenzió be van állítva a fedezet tervezéséhez.</span><span class="sxs-lookup"><span data-stu-id="82d8e-112">The site and warehouse dimensions are set for coverage planning.</span></span> <span data-ttu-id="82d8e-113">Előfordulhat, hogy más dimenziók is be vannak állítva a fedezet tervezéséhez.</span><span class="sxs-lookup"><span data-stu-id="82d8e-113">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="82d8e-114">A több telephelyes funkciók mindezeket nem érintik.</span><span class="sxs-lookup"><span data-stu-id="82d8e-114">However, they are not affected by the multisite functionality.</span></span>

<span data-ttu-id="82d8e-115">Az alábbi ábra az alapütemezés folyamatát illusztrálja.</span><span class="sxs-lookup"><span data-stu-id="82d8e-115">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="82d8e-116">Az ábrán látható paraméterek és helyeik a következők:</span><span class="sxs-lookup"><span data-stu-id="82d8e-116">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="82d8e-117">A raktár beállítása Kézi.</span><span class="sxs-lookup"><span data-stu-id="82d8e-117">The warehouse is set to Manual.</span></span> <span data-ttu-id="82d8e-118">Kattintson a következő lehetőségre: **Készletgazdálkodás &gt; Beállítás &gt; Készlet részletezése &gt; Raktárak**.</span><span class="sxs-lookup"><span data-stu-id="82d8e-118">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="82d8e-119">Az a **Alaptervezés** gyorslapon lásd a **Kézi** mezőt.</span><span class="sxs-lookup"><span data-stu-id="82d8e-119">On the **Master planning** FastTab, see the **Manual** field.</span></span>
-   <span data-ttu-id="82d8e-120">A cikkre cikkfedezet van meghatározva.</span><span class="sxs-lookup"><span data-stu-id="82d8e-120">Item coverage is defined for the item.</span></span> <span data-ttu-id="82d8e-121">Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="82d8e-121">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="82d8e-122">Jelölje ki a cikket, majd a Művelet panelen a **Tervezés** lapon kattintson a **Cikk fedezete** elemre.</span><span class="sxs-lookup"><span data-stu-id="82d8e-122">Select the item, and then, on the Action Pane, on the **Plan** tab, click **Item coverage**.</span></span>
-   <span data-ttu-id="82d8e-123">A raktárban újratöltési viszonyok vannak meghatározva.</span><span class="sxs-lookup"><span data-stu-id="82d8e-123">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="82d8e-124">Kattintson a következő lehetőségre: **Készletgazdálkodás &gt; Beállítás &gt; Készlet részletezése &gt; Raktárak**.</span><span class="sxs-lookup"><span data-stu-id="82d8e-124">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="82d8e-125">Az **Alaptervezés** gyorslapon lásd az **Elsődleges raktár** mezőcsoportot.</span><span class="sxs-lookup"><span data-stu-id="82d8e-125">On the **Master planning** FastTab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="82d8e-126">Az alapértelmezett rendelési típus beállítása Termelés, Beszerzési rendelés vagy Kanban.</span><span class="sxs-lookup"><span data-stu-id="82d8e-126">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="82d8e-127">Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="82d8e-127">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="82d8e-128">Jelölje ki a cikket, majd a Művelet panelen a **Tervezés** lapon kattintson az **Alapértelmezett rendelésbeállítások** elemre.</span><span class="sxs-lookup"><span data-stu-id="82d8e-128">Select the item, and then, on the Action Pane, on the **Plan** tab, click **Default order settings**.</span></span> <span data-ttu-id="82d8e-129">Az a **Alapértelmezett rendelésbeállítások** űrlapon lásd a **Alapértelmezett rendeléstípus** elemet.</span><span class="sxs-lookup"><span data-stu-id="82d8e-129">In the **Default order settings** form, see the **Default order type**.</span></span>

![Telephely és raktár igénylése, nem kötelező rakár](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousenotmandatory.jpg)



<a name="additional-resources"></a><span data-ttu-id="82d8e-131">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="82d8e-131">Additional resources</span></span>
--------

[<span data-ttu-id="82d8e-132">Az alaptervezés és a többhelyes funkció áttekintése</span><span class="sxs-lookup"><span data-stu-id="82d8e-132">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="82d8e-133">Alaptervezés telephely-lefedettséghez, kötelező raktár</span><span class="sxs-lookup"><span data-stu-id="82d8e-133">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="82d8e-134">Telephely és raktárfedezet alaptervezése, kötelező raktár</span><span class="sxs-lookup"><span data-stu-id="82d8e-134">Master planning for site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="82d8e-135">Telephely és raktárfedezet alaptervezése, nem kötelező raktár</span><span class="sxs-lookup"><span data-stu-id="82d8e-135">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="82d8e-136">Anyagjegyzék-verzió meghatározása</span><span class="sxs-lookup"><span data-stu-id="82d8e-136">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)



