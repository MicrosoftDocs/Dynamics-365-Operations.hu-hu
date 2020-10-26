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
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 92160b45590245e2b1caab6732d1b0aaeaabd208
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3975920"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-mandatory"></a><span data-ttu-id="14bdb-104">Alaptervezés hely- és raktár fedezethez, a raktár kötelező</span><span class="sxs-lookup"><span data-stu-id="14bdb-104">Master planning for site and warehouse coverage, warehouse mandatory</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="14bdb-105">Ez a témakör leírja, hogyan terveznek meg egy fedezeti dimenziókként webhellyel ás raktárral rendelkező cikket.</span><span class="sxs-lookup"><span data-stu-id="14bdb-105">This topic describes how an item that has site and warehouse as coverage dimensions is planned.</span></span> <span data-ttu-id="14bdb-106">A raktár dimenzió kötelező.</span><span class="sxs-lookup"><span data-stu-id="14bdb-106">The warehouse dimension is mandatory.</span></span>

<span data-ttu-id="14bdb-107">Ez az alaptervezési eset a következő feltételeket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="14bdb-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="14bdb-108">A telephelydimenzió kötelezőre van állítva, és meg kell adni az igénytranzakcióban.</span><span class="sxs-lookup"><span data-stu-id="14bdb-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="14bdb-109">A raktárdimenzió kötelező, és meg kell adni az igénytranzakcióban.</span><span class="sxs-lookup"><span data-stu-id="14bdb-109">The warehouse dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="14bdb-110">A telephely és raktár dimenzió be van állítva a fedezet tervezéséhez.</span><span class="sxs-lookup"><span data-stu-id="14bdb-110">The site and warehouse dimensions are set for coverage planning.</span></span> <span data-ttu-id="14bdb-111">Előfordulhat, hogy más dimenziók is be vannak állítva a fedezet tervezéséhez.</span><span class="sxs-lookup"><span data-stu-id="14bdb-111">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="14bdb-112">A több telephelyes funkciók mindezeket nem érintik.</span><span class="sxs-lookup"><span data-stu-id="14bdb-112">However, they are not affected by the multisite functionality.</span></span>

<span data-ttu-id="14bdb-113">Az alábbi ábra az alapütemezés folyamatát illusztrálja.</span><span class="sxs-lookup"><span data-stu-id="14bdb-113">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="14bdb-114">Az ábrán látható paraméterek és helyeik a következők:</span><span class="sxs-lookup"><span data-stu-id="14bdb-114">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="14bdb-115">A raktár beállítása **Kézi** .</span><span class="sxs-lookup"><span data-stu-id="14bdb-115">The warehouse is set to **Manual** .</span></span> <span data-ttu-id="14bdb-116">Kattintson a következő lehetőségre: **Készletgazdálkodás &gt; Beállítás &gt; Készlet részletezése &gt; Raktárak** .</span><span class="sxs-lookup"><span data-stu-id="14bdb-116">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses** .</span></span> <span data-ttu-id="14bdb-117">Az a **Alaptervezés** gyorslapon lásd a **Kézi** mezőt.</span><span class="sxs-lookup"><span data-stu-id="14bdb-117">On the **Master planning** FastTab, see the **Manual** field.</span></span>
-   <span data-ttu-id="14bdb-118">A cikkre cikkfedezet van meghatározva.</span><span class="sxs-lookup"><span data-stu-id="14bdb-118">Item coverage is defined for the item.</span></span> <span data-ttu-id="14bdb-119">Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="14bdb-119">Click **Product information management &gt; Products&gt; Released products** .</span></span> <span data-ttu-id="14bdb-120">Jelölje ki a cikket, majd a Művelet panelen a **Tervezés** lapon kattintson a **Cikk fedezete** elemre.</span><span class="sxs-lookup"><span data-stu-id="14bdb-120">Select the item, and then, on the Action Pane, on the **Plan** tab, click **Item coverage** .</span></span>
-   <span data-ttu-id="14bdb-121">A raktárban újratöltési viszonyok vannak meghatározva.</span><span class="sxs-lookup"><span data-stu-id="14bdb-121">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="14bdb-122">Kattintson a következő lehetőségre: **Készletgazdálkodás &gt; Beállítás &gt; Készlet részletezése &gt; Raktárak** .</span><span class="sxs-lookup"><span data-stu-id="14bdb-122">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses** .</span></span> <span data-ttu-id="14bdb-123">Az **Alaptervezés** gyorslapon lásd az **Elsődleges raktár** mezőcsoportot.</span><span class="sxs-lookup"><span data-stu-id="14bdb-123">On the **Master planning** FastTab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="14bdb-124">Az alapértelmezett rendelési típus beállítása Termelés, Beszerzési rendelés vagy Kanban.</span><span class="sxs-lookup"><span data-stu-id="14bdb-124">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="14bdb-125">Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="14bdb-125">Click **Product information management &gt; Products&gt; Released products** .</span></span> <span data-ttu-id="14bdb-126">Jelölje ki a cikket, majd a Művelet panelen a **Tervezés** lapon kattintson az **Alapértelmezett rendelésbeállítások** elemre.</span><span class="sxs-lookup"><span data-stu-id="14bdb-126">Select the item, and then, on the Action Pane, on the **Plan** tab, click **Default order settings** .</span></span> <span data-ttu-id="14bdb-127">Az a **Alapértelmezett rendelésbeállítások** űrlapon lásd a **Alapértelmezett rendeléstípus** elemet.</span><span class="sxs-lookup"><span data-stu-id="14bdb-127">In the **Default order settings** form, see the **Default order type** .</span></span>

![Telephely és raktárfedezet igénylése, kötelező raktár](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousemandatory.jpg)



<a name="additional-resources"></a><span data-ttu-id="14bdb-129">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="14bdb-129">Additional resources</span></span>
--------

[<span data-ttu-id="14bdb-130">Az alaptervezés és a többhelyes funkció áttekintése</span><span class="sxs-lookup"><span data-stu-id="14bdb-130">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="14bdb-131">Alaptervezés telephely-lefedettséghez, kötelező raktár</span><span class="sxs-lookup"><span data-stu-id="14bdb-131">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="14bdb-132">Alaptervezés helyfedezethez, a raktár nem kötelező</span><span class="sxs-lookup"><span data-stu-id="14bdb-132">Master planning for site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="14bdb-133">Telephely és raktárfedezet alaptervezése, nem kötelező raktár</span><span class="sxs-lookup"><span data-stu-id="14bdb-133">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="14bdb-134">Anyagjegyzék-verzió meghatározása</span><span class="sxs-lookup"><span data-stu-id="14bdb-134">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)



