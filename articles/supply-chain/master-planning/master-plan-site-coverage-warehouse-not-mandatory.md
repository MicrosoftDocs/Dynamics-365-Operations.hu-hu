---
title: "Alaptervezés helyfedezethez, a raktár nem kötelező"
description: "Ez a témakör leírja, hogyan terveznek meg a fedezetre vonatkozó webhely- dimenzió készlettel rendelkező cikket."
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
ms.custom: 2474
ms.assetid: 316da918-67ae-43c5-baea-00ae559e29b0
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 323da0f71317242c4e0ab667002a195913b565fc
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="master-planning-for-site-coverage-warehouse-not-mandatory"></a><span data-ttu-id="e2643-103">Alaptervezés helyfedezethez, a raktár nem kötelező</span><span class="sxs-lookup"><span data-stu-id="e2643-103">Master planning for site coverage, warehouse not mandatory</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="e2643-104">Ez a témakör leírja, hogyan terveznek meg a fedezetre vonatkozó webhely- dimenzió készlettel rendelkező cikket.</span><span class="sxs-lookup"><span data-stu-id="e2643-104">This topic describes how an item that has the site dimension set for coverage is planned.</span></span>

<span data-ttu-id="e2643-105">Ez az alaptervezési eset a következő feltételeket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="e2643-105">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="e2643-106">A telephelydimenzió kötelezőre van állítva, és meg kell adni az igénytranzakcióban.</span><span class="sxs-lookup"><span data-stu-id="e2643-106">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="e2643-107">A raktár dimenzió nincs kötelezően beállítva.</span><span class="sxs-lookup"><span data-stu-id="e2643-107">The warehouse dimension is not set to mandatory.</span></span> <span data-ttu-id="e2643-108">Lehet, hogy a raktár ismert, de ez nem befolyásolja az alapütemezési számítást.</span><span class="sxs-lookup"><span data-stu-id="e2643-108">The warehouse may be known, but it is not used in the master planning calculation.</span></span>
-   <span data-ttu-id="e2643-109">A telephely dimenzió be van állítva a fedezet tervezéséhez.</span><span class="sxs-lookup"><span data-stu-id="e2643-109">The site dimension is set for coverage planning.</span></span>
-   <span data-ttu-id="e2643-110">A raktárdimenzió nincs beállítva a fedezet tervezéséhez.</span><span class="sxs-lookup"><span data-stu-id="e2643-110">The warehouse dimension is not set for coverage planning.</span></span> <span data-ttu-id="e2643-111">Ezért a program telephelyenként esetleg más fedezeti tervezési dimenziók szerint vonja össze a készleteket és az igényeket.</span><span class="sxs-lookup"><span data-stu-id="e2643-111">Therefore, supply and demand are aggregated by site and, perhaps, other coverage-planned dimensions also.</span></span>

<span data-ttu-id="e2643-112">Az alábbi ábra az alapütemezés folyamatát illusztrálja.</span><span class="sxs-lookup"><span data-stu-id="e2643-112">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="e2643-113">Az ábrán látható paraméterek és helyeik a következők:</span><span class="sxs-lookup"><span data-stu-id="e2643-113">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="e2643-114">A cikkre cikkfedezet van meghatározva.</span><span class="sxs-lookup"><span data-stu-id="e2643-114">Item coverage is defined for the item.</span></span> <span data-ttu-id="e2643-115">Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e2643-115">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="e2643-116">Válassza ki a cikket, majd kattintson a **Terv &gt; Cikkfedezet** pontra.</span><span class="sxs-lookup"><span data-stu-id="e2643-116">Select the item, and then click **Plan &gt; Item coverage**.</span></span>
-   <span data-ttu-id="e2643-117">A raktárban újratöltési viszonyok vannak meghatározva.</span><span class="sxs-lookup"><span data-stu-id="e2643-117">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="e2643-118">Kattintson a következő lehetőségre: **Készletgazdálkodás &gt; Beállítás &gt; Készlet részletezése &gt; Raktárak**.</span><span class="sxs-lookup"><span data-stu-id="e2643-118">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="e2643-119">Az **Alaptervezés** lapon lásd az **Elsődleges raktár** mezőcsoportot.</span><span class="sxs-lookup"><span data-stu-id="e2643-119">On the **Master planning** tab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="e2643-120">Az alapértelmezett rendelési típus beállítása Termelés, Beszerzési rendelés vagy Kanban.</span><span class="sxs-lookup"><span data-stu-id="e2643-120">The default order type is set to Production, Purchase order or Kanban.</span></span> <span data-ttu-id="e2643-121">Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e2643-121">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="e2643-122">Válassza ki a cikket, majd kattintson a **Terv &gt; Alapértelmezett rendelésbeállítások** parancsra.</span><span class="sxs-lookup"><span data-stu-id="e2643-122">Select the item, and then click **Plan &gt; Default order settings**.</span></span> <span data-ttu-id="e2643-123">Az **Alapértelmezett rendelésbeállítások** képernyőn lásd az **Alapértelmezett rendeléstípus** mezőt.</span><span class="sxs-lookup"><span data-stu-id="e2643-123">In the **Default order settings** form, see the **Default order type** field.</span></span>

![Telephely fedezet igénylése, raktár nem kötelező](./media/multisitedemandexplosionscenarioforsitecoveragewarehousenotmandatory.jpg)



<a name="see-also"></a><span data-ttu-id="e2643-125">Lásd még</span><span class="sxs-lookup"><span data-stu-id="e2643-125">See also</span></span>
--------

[<span data-ttu-id="e2643-126">Az alaptervezés és a többhelyes funkció</span><span class="sxs-lookup"><span data-stu-id="e2643-126">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="e2643-127">Alaptervezés - helyfedezet, a raktár kötelező</span><span class="sxs-lookup"><span data-stu-id="e2643-127">Master planning - site coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="e2643-128">Alaptervezés - hely és raktár fedezet, a raktár nem kötelező</span><span class="sxs-lookup"><span data-stu-id="e2643-128">Master planning - site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="e2643-129">Alaptervezés - hely és raktár fedezet, a raktár kötelező</span><span class="sxs-lookup"><span data-stu-id="e2643-129">Master planning - site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="e2643-130">Alaptervezés - anyagjegyzék verzió meghatározása</span><span class="sxs-lookup"><span data-stu-id="e2643-130">Master planning - how the BOM version is determined</span></span>](master-plan-bom-version-determined.md)




