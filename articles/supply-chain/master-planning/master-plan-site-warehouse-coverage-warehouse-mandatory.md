---
title: Alaptervezés hely- és raktár fedezethez, a raktár kötelező
description: Ez a témakör leírja, hogyan terveznek meg egy fedezeti dimenziókként webhellyel ás raktárral rendelkező cikket. A raktár dimenzió kötelező.
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
ms.search.scope: Core, Operations
ms.custom: 2554
ms.assetid: 3211e95f-b91a-4d27-8d92-f328ae2bcf12
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a07a4588d042af53d6281afc174ff58ecf24ca06
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383343"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-mandatory"></a><span data-ttu-id="ddbd8-104">Alaptervezés hely- és raktár fedezethez, a raktár kötelező</span><span class="sxs-lookup"><span data-stu-id="ddbd8-104">Master planning for site and warehouse coverage, warehouse mandatory</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ddbd8-105">Ez a témakör leírja, hogyan terveznek meg egy fedezeti dimenziókként webhellyel ás raktárral rendelkező cikket.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-105">This topic describes how an item that has site and warehouse as coverage dimensions is planned.</span></span> <span data-ttu-id="ddbd8-106">A raktár dimenzió kötelező.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-106">The warehouse dimension is mandatory.</span></span>

<span data-ttu-id="ddbd8-107">Ez az alaptervezési eset a következő feltételeket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="ddbd8-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="ddbd8-108">A telephelydimenzió kötelezőre van állítva, és meg kell adni az igénytranzakcióban.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="ddbd8-109">A raktárdimenzió kötelező, és meg kell adni az igénytranzakcióban.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-109">The warehouse dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="ddbd8-110">A telephely és raktár dimenzió be van állítva a fedezet tervezéséhez.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-110">The site and warehouse dimensions are set for coverage planning.</span></span> <span data-ttu-id="ddbd8-111">Előfordulhat, hogy más dimenziók is be vannak állítva a fedezet tervezéséhez.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-111">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="ddbd8-112">A több telephelyes funkciók mindezeket nem érintik.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-112">However, they are not affected by the multisite functionality.</span></span>

<span data-ttu-id="ddbd8-113">Az alábbi ábra az alapütemezés folyamatát illusztrálja.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-113">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="ddbd8-114">Az ábrán látható paraméterek és helyeik a következők:</span><span class="sxs-lookup"><span data-stu-id="ddbd8-114">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="ddbd8-115">A raktár beállítása **Kézi**.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-115">The warehouse is set to **Manual**.</span></span> <span data-ttu-id="ddbd8-116">Kattintson a következő lehetőségre: **Készletgazdálkodás &gt; Beállítás &gt; Készlet részletezése &gt; Raktárak**.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-116">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="ddbd8-117">Az a **Alaptervezés** gyorslapon lásd a **Kézi** mezőt.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-117">On the **Master planning** FastTab, see the **Manual** field.</span></span>
-   <span data-ttu-id="ddbd8-118">A cikkre cikkfedezet van meghatározva.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-118">Item coverage is defined for the item.</span></span> <span data-ttu-id="ddbd8-119">Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-119">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="ddbd8-120">Jelölje ki a cikket, majd a Művelet panelen a **Tervezés** lapon kattintson a **Cikk fedezete** elemre.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-120">Select the item, and then, on the Action Pane, on the **Plan** tab, click **Item coverage**.</span></span>
-   <span data-ttu-id="ddbd8-121">A raktárban újratöltési viszonyok vannak meghatározva.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-121">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="ddbd8-122">Kattintson a következő lehetőségre: **Készletgazdálkodás &gt; Beállítás &gt; Készlet részletezése &gt; Raktárak**.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-122">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="ddbd8-123">Az **Alaptervezés** gyorslapon lásd az **Elsődleges raktár** mezőcsoportot.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-123">On the **Master planning** FastTab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="ddbd8-124">Az alapértelmezett rendelési típus beállítása Termelés, Beszerzési rendelés vagy Kanban.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-124">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="ddbd8-125">Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-125">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="ddbd8-126">Jelölje ki a cikket, majd a Művelet panelen a **Tervezés** lapon kattintson az **Alapértelmezett rendelésbeállítások** elemre.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-126">Select the item, and then, on the Action Pane, on the **Plan** tab, click **Default order settings**.</span></span> <span data-ttu-id="ddbd8-127">Az a **Alapértelmezett rendelésbeállítások** űrlapon lásd a **Alapértelmezett rendeléstípus** elemet.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-127">In the **Default order settings** form, see the **Default order type**.</span></span>

![Telephely és raktárfedezet igénylése, kötelező raktár](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousemandatory.jpg)



<a name="additional-resources"></a><span data-ttu-id="ddbd8-129">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="ddbd8-129">Additional resources</span></span>
--------

[<span data-ttu-id="ddbd8-130">Az alaptervezés és a többhelyes funkció áttekintése</span><span class="sxs-lookup"><span data-stu-id="ddbd8-130">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="ddbd8-131">Alaptervezés telephely-lefedettséghez, kötelező raktár</span><span class="sxs-lookup"><span data-stu-id="ddbd8-131">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="ddbd8-132">Alaptervezés helyfedezethez, a raktár nem kötelező</span><span class="sxs-lookup"><span data-stu-id="ddbd8-132">Master planning for site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="ddbd8-133">Telephely és raktárfedezet alaptervezése, nem kötelező raktár</span><span class="sxs-lookup"><span data-stu-id="ddbd8-133">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="ddbd8-134">Anyagjegyzék-verzió meghatározása</span><span class="sxs-lookup"><span data-stu-id="ddbd8-134">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)



