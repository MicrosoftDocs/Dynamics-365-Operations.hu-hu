---
title: "Alaptervezés helyfedezethez, a raktár kötelező"
description: "Ez a témakör leírja, hogyan terveznek meg egy fedezeti dimenzióként webhellyel rendelkező cikket. A raktár kötelező dimenzió."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 2454
ms.assetid: aa135030-f98c-48bf-902c-e52f680dc247
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 4ca01913a0338004fabcda5136108ec3c5be8ff7
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="master-planning-for-site-coverage-mandatory-warehouse"></a><span data-ttu-id="73e5a-104">Alaptervezés helyfedezethez, a raktár kötelező</span><span class="sxs-lookup"><span data-stu-id="73e5a-104">Master planning for site coverage, mandatory warehouse</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="73e5a-105">Ez a témakör leírja, hogyan terveznek meg egy fedezeti dimenzióként webhellyel rendelkező cikket.</span><span class="sxs-lookup"><span data-stu-id="73e5a-105">This topic describes how an item that has the site as coverage dimension is planned.</span></span> <span data-ttu-id="73e5a-106">A raktár kötelező dimenzió.</span><span class="sxs-lookup"><span data-stu-id="73e5a-106">Warehouse is a mandatory dimension.</span></span>

<span data-ttu-id="73e5a-107">Ez az alaptervezési eset a következő feltételeket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="73e5a-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="73e5a-108">A telephelydimenzió kötelezőre van állítva, és meg kell adni az igénytranzakcióban.</span><span class="sxs-lookup"><span data-stu-id="73e5a-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span> <span data-ttu-id="73e5a-109">Ez a beállítás nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="73e5a-109">This setting can't be modified.</span></span>
-   <span data-ttu-id="73e5a-110">A raktárdimenzió kötelező, és meg kell adni az igénytranzakcióban.</span><span class="sxs-lookup"><span data-stu-id="73e5a-110">The warehouse dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="73e5a-111">A telephely dimenzió be van állítva a fedezet tervezéséhez.</span><span class="sxs-lookup"><span data-stu-id="73e5a-111">The site dimension is set for coverage planning.</span></span> <span data-ttu-id="73e5a-112">Előfordulhat, hogy más dimenziók is be vannak állítva a fedezet tervezéséhez.</span><span class="sxs-lookup"><span data-stu-id="73e5a-112">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="73e5a-113">A több telephelyes funkciók mindezeket nem érintik.</span><span class="sxs-lookup"><span data-stu-id="73e5a-113">However, they are not affected by the multisite functionality.</span></span>
-   <span data-ttu-id="73e5a-114">A raktárdimenzió nincs beállítva a fedezet tervezéséhez.</span><span class="sxs-lookup"><span data-stu-id="73e5a-114">The warehouse dimension is not set for coverage planning.</span></span> <span data-ttu-id="73e5a-115">Ezért a program telephelyenként esetleg más fedezeti tervezési dimenziók szerint vonja össze a készleteket és az igényeket.</span><span class="sxs-lookup"><span data-stu-id="73e5a-115">Therefore, supply and demand are aggregated by site and, perhaps, other coverage-planned dimensions also.</span></span>

<span data-ttu-id="73e5a-116">Az alábbi ábra az alapütemezés folyamatát illusztrálja.</span><span class="sxs-lookup"><span data-stu-id="73e5a-116">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="73e5a-117">Az ábrán látható paraméterek és helyeik a következők:</span><span class="sxs-lookup"><span data-stu-id="73e5a-117">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="73e5a-118">A cikkre cikkfedezet van meghatározva.</span><span class="sxs-lookup"><span data-stu-id="73e5a-118">Item coverage is defined for the item.</span></span> <span data-ttu-id="73e5a-119">Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="73e5a-119">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="73e5a-120">Válassza ki a cikket, majd kattintson a **Terv &gt; Cikkfedezet** pontra.</span><span class="sxs-lookup"><span data-stu-id="73e5a-120">Select the item, and then click **Plan &gt; Item coverage**.</span></span>
-   <span data-ttu-id="73e5a-121">A raktárban újratöltési viszonyok vannak meghatározva.</span><span class="sxs-lookup"><span data-stu-id="73e5a-121">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="73e5a-122">Kattintson a következő lehetőségre: **Készletgazdálkodás &gt; Beállítás &gt; Készlet részletezése &gt; Raktárak**.</span><span class="sxs-lookup"><span data-stu-id="73e5a-122">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="73e5a-123">Az **Alaptervezés** lapon lásd az **Elsődleges raktár** mezőcsoportot.</span><span class="sxs-lookup"><span data-stu-id="73e5a-123">On the **Master planning** tab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="73e5a-124">Az alapértelmezett rendelési típus beállítása Termelés, Beszerzési rendelés vagy Kanban.</span><span class="sxs-lookup"><span data-stu-id="73e5a-124">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="73e5a-125">Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="73e5a-125">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="73e5a-126">Válassza ki a cikket, majd kattintson a **Terv &gt; Alapértelmezett rendelésbeállítások** parancsra.</span><span class="sxs-lookup"><span data-stu-id="73e5a-126">Select the item, and then click **Plan &gt; Default order settings**.</span></span> <span data-ttu-id="73e5a-127">Az a **Alapértelmezett rendelésbeállítások** űrlapon lásd a **Alapértelmezett rendeléstípus** elemet.</span><span class="sxs-lookup"><span data-stu-id="73e5a-127">In the **Default order settings** form, see the **Default order type**.</span></span>

![Telephely fedezet igénylése, raktár kötelező](./media/multisitedemandexplosionscenarioforsitecoveragewarehousemandatory.jpg)



<a name="see-also"></a><span data-ttu-id="73e5a-129">Lásd még</span><span class="sxs-lookup"><span data-stu-id="73e5a-129">See also</span></span>
--------

[<span data-ttu-id="73e5a-130">Az alaptervezés és a többhelyes funkció</span><span class="sxs-lookup"><span data-stu-id="73e5a-130">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="73e5a-131">Alaptervezés - hely és raktár fedezet, a raktár kötelező</span><span class="sxs-lookup"><span data-stu-id="73e5a-131">Master planning - site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="73e5a-132">Alaptervezés - helyfedezet, a raktár kötelező</span><span class="sxs-lookup"><span data-stu-id="73e5a-132">Master planning - site coverage. warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="73e5a-133">Alaptervezés - hely és raktár fedezet, a raktár nem kötelező</span><span class="sxs-lookup"><span data-stu-id="73e5a-133">Master planning - site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="73e5a-134">Alaptervezés - Anyagjegyzék verzió meghatározása</span><span class="sxs-lookup"><span data-stu-id="73e5a-134">Master planning - How the BOM version is determined</span></span>](master-plan-bom-version-determined.md)




