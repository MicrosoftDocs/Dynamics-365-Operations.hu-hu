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
ms.openlocfilehash: 9b1cd11cc62f551e43a04b9a8cc17bf7a7e961ab
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5255589"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-not-mandatory"></a><span data-ttu-id="bc5b4-104">Alaptervezés hely- és raktárfedezethez, a raktár nem kötelező</span><span class="sxs-lookup"><span data-stu-id="bc5b4-104">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bc5b4-105">Ez a témakör leírja, hogyan terveznek meg egy fedezeti dimenziókként webhellyel ás raktárral rendelkező cikket.</span><span class="sxs-lookup"><span data-stu-id="bc5b4-105">This topic describes how an item that has site and warehouse as coverage dimensions is planned.</span></span> <span data-ttu-id="bc5b4-106">A raktár dimenzió nincs kötelezően beállítva.</span><span class="sxs-lookup"><span data-stu-id="bc5b4-106">The warehouse dimension is not mandatory.</span></span>

<span data-ttu-id="bc5b4-107">Ez az alaptervezési eset a következő feltételeket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="bc5b4-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="bc5b4-108">A telephelydimenzió kötelezőre van állítva, és meg kell adni az igénytranzakcióban.</span><span class="sxs-lookup"><span data-stu-id="bc5b4-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span> <span data-ttu-id="bc5b4-109">Ez a beállítás nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="bc5b4-109">This setting can't be modified.</span></span>
-   <span data-ttu-id="bc5b4-110">A raktár dimenzió nincs kötelezően beállítva.</span><span class="sxs-lookup"><span data-stu-id="bc5b4-110">The warehouse dimension is not set to mandatory.</span></span> <span data-ttu-id="bc5b4-111">Lehet, hogy a raktár ismert, de ez nem befolyásolja az alapütemezési számítást.</span><span class="sxs-lookup"><span data-stu-id="bc5b4-111">The warehouse may be known, but it is not used in the master planning calculation.</span></span>
-   <span data-ttu-id="bc5b4-112">A telephely és raktár dimenzió be van állítva a fedezet tervezéséhez.</span><span class="sxs-lookup"><span data-stu-id="bc5b4-112">The site and warehouse dimensions are set for coverage planning.</span></span> <span data-ttu-id="bc5b4-113">Előfordulhat, hogy más dimenziók is be vannak állítva a fedezet tervezéséhez.</span><span class="sxs-lookup"><span data-stu-id="bc5b4-113">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="bc5b4-114">A több telephelyes funkciók mindezeket nem érintik.</span><span class="sxs-lookup"><span data-stu-id="bc5b4-114">However, they are not affected by the multisite functionality.</span></span>

<span data-ttu-id="bc5b4-115">Az alábbi ábra az alapütemezés folyamatát illusztrálja.</span><span class="sxs-lookup"><span data-stu-id="bc5b4-115">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="bc5b4-116">Az ábrán látható paraméterek és helyeik a következők:</span><span class="sxs-lookup"><span data-stu-id="bc5b4-116">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="bc5b4-117">A raktár beállítása Kézi.</span><span class="sxs-lookup"><span data-stu-id="bc5b4-117">The warehouse is set to Manual.</span></span> <span data-ttu-id="bc5b4-118">Kattintson a következő lehetőségre: **Készletgazdálkodás &gt; Beállítás &gt; Készlet részletezése &gt; Raktárak**.</span><span class="sxs-lookup"><span data-stu-id="bc5b4-118">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="bc5b4-119">Az a **Alaptervezés** gyorslapon lásd a **Kézi** mezőt.</span><span class="sxs-lookup"><span data-stu-id="bc5b4-119">On the **Master planning** FastTab, see the **Manual** field.</span></span>
-   <span data-ttu-id="bc5b4-120">A cikkre cikkfedezet van meghatározva.</span><span class="sxs-lookup"><span data-stu-id="bc5b4-120">Item coverage is defined for the item.</span></span> <span data-ttu-id="bc5b4-121">Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bc5b4-121">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="bc5b4-122">Jelölje ki a cikket, majd a Művelet panelen a **Tervezés** lapon kattintson a **Cikk fedezete** elemre.</span><span class="sxs-lookup"><span data-stu-id="bc5b4-122">Select the item, and then, on the Action Pane, on the **Plan** tab, click **Item coverage**.</span></span>
-   <span data-ttu-id="bc5b4-123">A raktárban újratöltési viszonyok vannak meghatározva.</span><span class="sxs-lookup"><span data-stu-id="bc5b4-123">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="bc5b4-124">Kattintson a következő lehetőségre: **Készletgazdálkodás &gt; Beállítás &gt; Készlet részletezése &gt; Raktárak**.</span><span class="sxs-lookup"><span data-stu-id="bc5b4-124">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="bc5b4-125">Az **Alaptervezés** gyorslapon lásd az **Elsődleges raktár** mezőcsoportot.</span><span class="sxs-lookup"><span data-stu-id="bc5b4-125">On the **Master planning** FastTab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="bc5b4-126">Az alapértelmezett rendelési típus beállítása Termelés, Beszerzési rendelés vagy Kanban.</span><span class="sxs-lookup"><span data-stu-id="bc5b4-126">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="bc5b4-127">Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bc5b4-127">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="bc5b4-128">Jelölje ki a cikket, majd a Művelet panelen a **Tervezés** lapon kattintson az **Alapértelmezett rendelésbeállítások** elemre.</span><span class="sxs-lookup"><span data-stu-id="bc5b4-128">Select the item, and then, on the Action Pane, on the **Plan** tab, click **Default order settings**.</span></span> <span data-ttu-id="bc5b4-129">Az a **Alapértelmezett rendelésbeállítások** űrlapon lásd a **Alapértelmezett rendeléstípus** elemet.</span><span class="sxs-lookup"><span data-stu-id="bc5b4-129">In the **Default order settings** form, see the **Default order type**.</span></span>

![Telephely és raktár igénylése, nem kötelező rakár](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousenotmandatory.jpg)



<a name="additional-resources"></a><span data-ttu-id="bc5b4-131">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="bc5b4-131">Additional resources</span></span>
--------

[<span data-ttu-id="bc5b4-132">Az alaptervezés és a többhelyes funkció áttekintése</span><span class="sxs-lookup"><span data-stu-id="bc5b4-132">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="bc5b4-133">Alaptervezés telephely-lefedettséghez, kötelező raktár</span><span class="sxs-lookup"><span data-stu-id="bc5b4-133">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="bc5b4-134">Telephely és raktárfedezet alaptervezése, kötelező raktár</span><span class="sxs-lookup"><span data-stu-id="bc5b4-134">Master planning for site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="bc5b4-135">Telephely és raktárfedezet alaptervezése, nem kötelező raktár</span><span class="sxs-lookup"><span data-stu-id="bc5b4-135">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="bc5b4-136">Anyagjegyzék-verzió meghatározása</span><span class="sxs-lookup"><span data-stu-id="bc5b4-136">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]