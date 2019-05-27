---
title: Alaptervezés helyfedezethez, a raktár nem kötelező
description: Ez a témakör leírja, hogyan terveznek meg a fedezetre vonatkozó webhely- dimenzió készlettel rendelkező cikket.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2474
ms.assetid: 316da918-67ae-43c5-baea-00ae559e29b0
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9475a7fbe40d7feb60c23e0d7164222469dffa75
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1552322"
---
# <a name="master-planning-for-site-coverage-warehouse-not-mandatory"></a><span data-ttu-id="c7628-103">Alaptervezés helyfedezethez, a raktár nem kötelező</span><span class="sxs-lookup"><span data-stu-id="c7628-103">Master planning for site coverage, warehouse not mandatory</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c7628-104">Ez a témakör leírja, hogyan terveznek meg a fedezetre vonatkozó webhely- dimenzió készlettel rendelkező cikket.</span><span class="sxs-lookup"><span data-stu-id="c7628-104">This topic describes how an item that has the site dimension set for coverage is planned.</span></span>

<span data-ttu-id="c7628-105">Ez az alaptervezési eset a következő feltételeket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="c7628-105">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="c7628-106">A telephelydimenzió kötelezőre van állítva, és meg kell adni az igénytranzakcióban.</span><span class="sxs-lookup"><span data-stu-id="c7628-106">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="c7628-107">A raktár dimenzió nincs kötelezően beállítva.</span><span class="sxs-lookup"><span data-stu-id="c7628-107">The warehouse dimension is not set to mandatory.</span></span> <span data-ttu-id="c7628-108">Lehet, hogy a raktár ismert, de ez nem befolyásolja az alapütemezési számítást.</span><span class="sxs-lookup"><span data-stu-id="c7628-108">The warehouse may be known, but it is not used in the master planning calculation.</span></span>
-   <span data-ttu-id="c7628-109">A telephely dimenzió be van állítva a fedezet tervezéséhez.</span><span class="sxs-lookup"><span data-stu-id="c7628-109">The site dimension is set for coverage planning.</span></span>
-   <span data-ttu-id="c7628-110">A raktárdimenzió nincs beállítva a fedezet tervezéséhez.</span><span class="sxs-lookup"><span data-stu-id="c7628-110">The warehouse dimension is not set for coverage planning.</span></span> <span data-ttu-id="c7628-111">Ezért a program telephelyenként esetleg más fedezeti tervezési dimenziók szerint vonja össze a készleteket és az igényeket.</span><span class="sxs-lookup"><span data-stu-id="c7628-111">Therefore, supply and demand are aggregated by site and, perhaps, other coverage-planned dimensions also.</span></span>

<span data-ttu-id="c7628-112">Az alábbi ábra az alapütemezés folyamatát illusztrálja.</span><span class="sxs-lookup"><span data-stu-id="c7628-112">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="c7628-113">Az ábrán látható paraméterek és helyeik a következők:</span><span class="sxs-lookup"><span data-stu-id="c7628-113">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="c7628-114">A cikkre cikkfedezet van meghatározva.</span><span class="sxs-lookup"><span data-stu-id="c7628-114">Item coverage is defined for the item.</span></span> <span data-ttu-id="c7628-115">Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c7628-115">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="c7628-116">Válassza ki a cikket, majd kattintson a **Terv &gt; Cikkfedezet** pontra.</span><span class="sxs-lookup"><span data-stu-id="c7628-116">Select the item, and then click **Plan &gt; Item coverage**.</span></span>
-   <span data-ttu-id="c7628-117">A raktárban újratöltési viszonyok vannak meghatározva.</span><span class="sxs-lookup"><span data-stu-id="c7628-117">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="c7628-118">Kattintson a következő lehetőségre: **Készletgazdálkodás &gt; Beállítás &gt; Készlet részletezése &gt; Raktárak**.</span><span class="sxs-lookup"><span data-stu-id="c7628-118">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="c7628-119">Az **Alaptervezés** lapon lásd az **Elsődleges raktár** mezőcsoportot.</span><span class="sxs-lookup"><span data-stu-id="c7628-119">On the **Master planning** tab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="c7628-120">Az alapértelmezett rendelési típus beállítása Termelés, Beszerzési rendelés vagy Kanban.</span><span class="sxs-lookup"><span data-stu-id="c7628-120">The default order type is set to Production, Purchase order or Kanban.</span></span> <span data-ttu-id="c7628-121">Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c7628-121">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="c7628-122">Válassza ki a cikket, majd kattintson a **Terv &gt; Alapértelmezett rendelésbeállítások** parancsra.</span><span class="sxs-lookup"><span data-stu-id="c7628-122">Select the item, and then click **Plan &gt; Default order settings**.</span></span> <span data-ttu-id="c7628-123">Az **Alapértelmezett rendelésbeállítások** képernyőn lásd az **Alapértelmezett rendeléstípus** mezőt.</span><span class="sxs-lookup"><span data-stu-id="c7628-123">In the **Default order settings** form, see the **Default order type** field.</span></span>

![Telephely fedezet igénylése, raktár nem kötelező](./media/multisitedemandexplosionscenarioforsitecoveragewarehousenotmandatory.jpg)



<a name="additional-resources"></a><span data-ttu-id="c7628-125">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c7628-125">Additional resources</span></span>
--------

[<span data-ttu-id="c7628-126">Az alaptervezés és a többhelyes funkció</span><span class="sxs-lookup"><span data-stu-id="c7628-126">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="c7628-127">Alaptervezés - helyfedezet, a raktár kötelező</span><span class="sxs-lookup"><span data-stu-id="c7628-127">Master planning - site coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="c7628-128">Alaptervezés - hely és raktár fedezet, a raktár nem kötelező</span><span class="sxs-lookup"><span data-stu-id="c7628-128">Master planning - site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="c7628-129">Alaptervezés - hely és raktár fedezet, a raktár kötelező</span><span class="sxs-lookup"><span data-stu-id="c7628-129">Master planning - site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="c7628-130">Alaptervezés - anyagjegyzék verzió meghatározása</span><span class="sxs-lookup"><span data-stu-id="c7628-130">Master planning - how the BOM version is determined</span></span>](master-plan-bom-version-determined.md)



