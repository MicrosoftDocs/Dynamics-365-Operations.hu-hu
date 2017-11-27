---
title: "Fedezeti beállítások"
description: "Az alapütemezés a fedezeti beállítások segítségével számítja ki a cikkszükségleteket."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: bd85f89917659ac9c94590bace765b2123d6e556
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="coverage-settings"></a><span data-ttu-id="4bbc6-103">Fedezeti beállítások</span><span class="sxs-lookup"><span data-stu-id="4bbc6-103">Coverage settings</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="4bbc6-104">Az alapütemezés a fedezeti beállítások segítségével számítja ki a cikkszükségleteket.</span><span class="sxs-lookup"><span data-stu-id="4bbc6-104">Master scheduling uses coverage settings to calculate item requirements.</span></span> 

<span data-ttu-id="4bbc6-105">A fedezeti beállítások többféleképpen is megadhatók:</span><span class="sxs-lookup"><span data-stu-id="4bbc6-105">You can specify coverage settings in several ways:</span></span>

-   <span data-ttu-id="4bbc6-106">Fedezeti csoport fedezeti beállításainak meghatározása.</span><span class="sxs-lookup"><span data-stu-id="4bbc6-106">Specify coverage settings for a coverage group.</span></span> <span data-ttu-id="4bbc6-107">Létrehozhat egy fedezeti csoportot, amely tartalmazza minden hozzákapcsolt termék fedezeti beállításait.</span><span class="sxs-lookup"><span data-stu-id="4bbc6-107">You can create a coverage group that contains settings for all products that are linked to the coverage group.</span></span> <span data-ttu-id="4bbc6-108">Kattintson az **Alaptervezés &gt; Beállítás &gt; Fedezet &gt; Fedezeti csoportok** lehetőségekre fedezeti csoport létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="4bbc6-108">Click **Master planning &gt; Setup &gt; Coverage &gt; Coverage groups** to create a coverage group.</span></span> <span data-ttu-id="4bbc6-109">A fedezeti csoportot hozzákapcsolhatja egy termékhez is.</span><span class="sxs-lookup"><span data-stu-id="4bbc6-109">You can link a coverage group to a product.</span></span> <span data-ttu-id="4bbc6-110">Ha a kapcsolat egy adott telephely, raktár vagy termékdimenzió esetében specifikus használja a **Fedezetcsoport** mezőt a **Cikkfedezet** lapon.</span><span class="sxs-lookup"><span data-stu-id="4bbc6-110">If the link is specific to a site, warehouse, or product dimension, use the **Coverage group** field on the **Item coverage** page.</span></span> <span data-ttu-id="4bbc6-111">Ha a kapcsolat általános, függetlenül a cikkdimenzióktól, használja a **Fedezeti csoport** lehetőséget a **Terv** gyorslapján a **Termékadatok** lapon.</span><span class="sxs-lookup"><span data-stu-id="4bbc6-111">If the link is generic, regardless of the product dimensions, use the **Coverage group** on the **Plan** FastTab on the **Product details** page.</span></span> <span data-ttu-id="4bbc6-112">Ha nem csatol fedezeti csoportot egy termékhez, az alaptervezés az **Általános fedezetcsoport** lehetőséget használja, amely meg van adva az **Alaptervezés paraméterei** oldalon, alapértelmezettként.</span><span class="sxs-lookup"><span data-stu-id="4bbc6-112">If you do not link a coverage group to a product, master planning uses the **General coverage group** that is specified on the **Master planning parameters** page as the default.</span></span>

-   <span data-ttu-id="4bbc6-113">Termék fedezeti beállításainak meghatározása.</span><span class="sxs-lookup"><span data-stu-id="4bbc6-113">Specify coverage settings for a product.</span></span> <span data-ttu-id="4bbc6-114">Létrehozhatja egy adott termék fedezeti beállításait is.</span><span class="sxs-lookup"><span data-stu-id="4bbc6-114">You can create coverage settings for a specific product.</span></span> <span data-ttu-id="4bbc6-115">Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4bbc6-115">Click **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="4bbc6-116">Válassza ki a terméket a **Műveleti ablakmodulon**, a **Terv** lapon, a **Fedezeti csoportrészben** kattintson **Cikkfedezet** lehetőségre a **Cikkfedezet** lap megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="4bbc6-116">Select the product, on the **Action Pane**, on the **Plan** tab, in the **Coverage group**, click **Item coverage** to open the **Item coverage** page.</span></span> <span data-ttu-id="4bbc6-117">Ha a termék már össze van kapcsolva egy fedezeti csoporttal, akkor a **Felülbírálás** mező beállításával felülbírálhatja a fedezeti csoport beállításait.</span><span class="sxs-lookup"><span data-stu-id="4bbc6-117">If the product is already linked to a coverage group, you can override the coverage group settings by using the **Override** field.</span></span> <span data-ttu-id="4bbc6-118">A fedezeti beállítások a**Cikkfedezet** lapon elsőbbséget élveznek a **Fedezeti csoport** lap beállításaival szemben.</span><span class="sxs-lookup"><span data-stu-id="4bbc6-118">The coverage settings on the **Item coverage** page take precedence over the settings on the **Coverage group** page.</span></span>

<!-- -->

-   <span data-ttu-id="4bbc6-119">Termék fedezeti beállításainak meghatározása varázslóval.</span><span class="sxs-lookup"><span data-stu-id="4bbc6-119">Specify coverage settings for a product by using a wizard.</span></span> <span data-ttu-id="4bbc6-120">A varázsló olyan útmutató, amely segít beállítani az elsődleges cikkfedezeti paramétereket.</span><span class="sxs-lookup"><span data-stu-id="4bbc6-120">The wizard is a step-by-step guide to help you set up the primary item coverage parameters.</span></span> <span data-ttu-id="4bbc6-121">A **Cikkfedezet** lapon kattintson a **Varázsló** lehetőségre a **Cikkfedezet varázsló** megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="4bbc6-121">On the **Item coverage** page, click **Wizard** to open the **Item Coverage Wizard**.</span></span>

<!-- -->

-   <span data-ttu-id="4bbc6-122">Dimenziócsoport fedezeti beállításainak meghatározása.</span><span class="sxs-lookup"><span data-stu-id="4bbc6-122">Specify coverage settings for a dimension group.</span></span> <span data-ttu-id="4bbc6-123">Kattintson a **Termékinformációk kezelése &gt; Közös &gt; Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4bbc6-123">Click **Product information management &gt; Common &gt; Released products**.</span></span> <span data-ttu-id="4bbc6-124">A **Megjelent termék részletei** lapon, az **Általános** lapon a **Felügyelet** csoportban kattintson a **Tárolásidimenzió-csoport** hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="4bbc6-124">On the **Released product detail **page, on the **General** tab, in the **Administration** group, click the **Storage dimension group** link.</span></span> <span data-ttu-id="4bbc6-125">A **Tárolásidimenzió-csoport** oldalon válassza a **Fedezeti terv dimenziónként** mezőt cikkfedezeti beállítások létrehozására egy dimenzióhoz a tárolásidimenzió-csoportban.</span><span class="sxs-lookup"><span data-stu-id="4bbc6-125">On the **Storage dimension group** page, select the **Coverage plan by dimension** field to create the coverage settings for a dimension in the storage dimension group.</span></span> <span data-ttu-id="4bbc6-126">Minden termékdimenzió, például a konfiguráció, szín, méret, stílus, kell, hogy rendelkezzen egy kiválasztott **Fedezeti terv dimenziónként** mezővel.</span><span class="sxs-lookup"><span data-stu-id="4bbc6-126">All product dimensions, such as configuration, color, size, style, must have the **Coverage plan by dimension** field selected.</span></span>



<a name="see-also"></a><span data-ttu-id="4bbc6-127">Lásd még</span><span class="sxs-lookup"><span data-stu-id="4bbc6-127">See also</span></span>
--------

[<span data-ttu-id="4bbc6-128">Alaptervek</span><span class="sxs-lookup"><span data-stu-id="4bbc6-128">Master plans</span></span>](master-plans.md)




