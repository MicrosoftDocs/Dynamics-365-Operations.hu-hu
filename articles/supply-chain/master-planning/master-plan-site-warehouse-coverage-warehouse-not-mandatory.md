---
title: "Alaptervezés hely- és raktárfedezethez, a raktár nem kötelező"
description: "Ez a témakör leírja, hogyan terveznek meg egy fedezeti dimenziókként webhellyel ás raktárral rendelkező cikket. A raktár dimenzió nincs kötelezően beállítva."
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
ms.custom: 2514
ms.assetid: 92d47bdd-df68-4f60-ac9a-96aa08236c26
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: a09e8540bac857f93e57b669c04299e1634efa7d
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---

# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-not-mandatory"></a><span data-ttu-id="cab51-104">Alaptervezés hely- és raktárfedezethez, a raktár nem kötelező</span><span class="sxs-lookup"><span data-stu-id="cab51-104">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="cab51-105">Ez a témakör leírja, hogyan terveznek meg egy fedezeti dimenziókként webhellyel ás raktárral rendelkező cikket.</span><span class="sxs-lookup"><span data-stu-id="cab51-105">This topic describes how an item that has site and warehouse as coverage dimensions is planned.</span></span> <span data-ttu-id="cab51-106">A raktár dimenzió nincs kötelezően beállítva.</span><span class="sxs-lookup"><span data-stu-id="cab51-106">The warehouse dimension is not mandatory.</span></span>

<span data-ttu-id="cab51-107">Ez az alaptervezési eset a következő feltételeket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="cab51-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="cab51-108">A telephelydimenzió kötelezőre van állítva, és meg kell adni az igénytranzakcióban.</span><span class="sxs-lookup"><span data-stu-id="cab51-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span> <span data-ttu-id="cab51-109">Ez a beállítás nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="cab51-109">This setting can't be modified.</span></span>
-   <span data-ttu-id="cab51-110">A raktár dimenzió nincs kötelezően beállítva.</span><span class="sxs-lookup"><span data-stu-id="cab51-110">The warehouse dimension is not set to mandatory.</span></span> <span data-ttu-id="cab51-111">Lehet, hogy a raktár ismert, de ez nem befolyásolja az alapütemezési számítást.</span><span class="sxs-lookup"><span data-stu-id="cab51-111">The warehouse may be known, but it is not used in the master planning calculation.</span></span>
-   <span data-ttu-id="cab51-112">A telephely és raktár dimenzió be van állítva a fedezet tervezéséhez.</span><span class="sxs-lookup"><span data-stu-id="cab51-112">The site and warehouse dimensions are set for coverage planning.</span></span> <span data-ttu-id="cab51-113">Előfordulhat, hogy más dimenziók is be vannak állítva a fedezet tervezéséhez.</span><span class="sxs-lookup"><span data-stu-id="cab51-113">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="cab51-114">A több telephelyes funkciók mindezeket nem érintik.</span><span class="sxs-lookup"><span data-stu-id="cab51-114">However, they are not affected by the multisite functionality.</span></span>

<span data-ttu-id="cab51-115">Az alábbi ábra az alapütemezés folyamatát illusztrálja.</span><span class="sxs-lookup"><span data-stu-id="cab51-115">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="cab51-116">Az ábrán látható paraméterek és helyeik a következők:</span><span class="sxs-lookup"><span data-stu-id="cab51-116">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="cab51-117">A raktár beállítása Kézi.</span><span class="sxs-lookup"><span data-stu-id="cab51-117">The warehouse is set to Manual.</span></span> <span data-ttu-id="cab51-118">Kattintson a következő lehetőségre: **Készletgazdálkodás &gt; Beállítás &gt; Készlet részletezése &gt; Raktárak**.</span><span class="sxs-lookup"><span data-stu-id="cab51-118">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="cab51-119">Az a **Alaptervezés** gyorslapon lásd a **Kézi** mezőt.</span><span class="sxs-lookup"><span data-stu-id="cab51-119">On the **Master planning** FastTab, see the **Manual** field.</span></span>
-   <span data-ttu-id="cab51-120">A cikkre cikkfedezet van meghatározva.</span><span class="sxs-lookup"><span data-stu-id="cab51-120">Item coverage is defined for the item.</span></span> <span data-ttu-id="cab51-121">Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cab51-121">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="cab51-122">Jelölje ki a cikket, majd a Műveleti ablak ablakon a **Tervezés** lapon kattintson a **Cikk fedezete** elemre.</span><span class="sxs-lookup"><span data-stu-id="cab51-122">Select the item, and then, on the Action pane, on the **Plan** tab, click **Item coverage**.</span></span>
-   <span data-ttu-id="cab51-123">A raktárban újratöltési viszonyok vannak meghatározva.</span><span class="sxs-lookup"><span data-stu-id="cab51-123">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="cab51-124">Kattintson a következő lehetőségre: **Készletgazdálkodás &gt; Beállítás &gt; Készlet részletezése &gt; Raktárak**.</span><span class="sxs-lookup"><span data-stu-id="cab51-124">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="cab51-125">Az **Alaptervezés** gyorslapon lásd az **Elsődleges raktár** mezőcsoportot.</span><span class="sxs-lookup"><span data-stu-id="cab51-125">On the **Master planning** FastTab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="cab51-126">Az alapértelmezett rendelési típus beállítása Termelés, Beszerzési rendelés vagy Kanban.</span><span class="sxs-lookup"><span data-stu-id="cab51-126">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="cab51-127">Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cab51-127">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="cab51-128">Jelölje ki a cikket, majd a Műveleti ablak ablakon a **Tervezés** lapon kattintson az **Alapértelmezett rendelésbeállítások** elemre.</span><span class="sxs-lookup"><span data-stu-id="cab51-128">Select the item, and then, on the Action pane, on the **Plan** tab, click **Default order settings**.</span></span> <span data-ttu-id="cab51-129">Az a **Alapértelmezett rendelésbeállítások** űrlapon lásd a **Alapértelmezett rendeléstípus** elemet.</span><span class="sxs-lookup"><span data-stu-id="cab51-129">In the **Default order settings** form, see the **Default order type**.</span></span>

![Telephely és raktár igénylése, nem kötelező rakár](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousenotmandatory.jpg)


-



<a name="see-also"></a><span data-ttu-id="cab51-131">Lásd még</span><span class="sxs-lookup"><span data-stu-id="cab51-131">See also</span></span>
--------

[<span data-ttu-id="cab51-132">Az alaptervezés és a többhelyes funkció</span><span class="sxs-lookup"><span data-stu-id="cab51-132">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="cab51-133">Alaptervezés - hely és raktár fedezet, a raktár kötelező</span><span class="sxs-lookup"><span data-stu-id="cab51-133">Master planning - site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="cab51-134">Alaptervezés - helyfedezet, a raktár kötelező</span><span class="sxs-lookup"><span data-stu-id="cab51-134">Master planning - site coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="cab51-135">Alaptervezés - helyfedezet, a raktár nem kötelező</span><span class="sxs-lookup"><span data-stu-id="cab51-135">Master planning - site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="cab51-136">Alaptervezés - Anyagjegyzék verzió meghatározása</span><span class="sxs-lookup"><span data-stu-id="cab51-136">Master planning - How the BOM version is determined</span></span>](master-plan-bom-version-determined.md)




