---
title: Fedezeti beállítások
description: Az alapütemezés a fedezeti beállítások segítségével számítja ki a cikkszükségleteket.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 50f47394a4d4e95b4e158ea42a630d9e6e91f05b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "322559"
---
# <a name="coverage-settings"></a><span data-ttu-id="d285d-103">Fedezeti beállítások</span><span class="sxs-lookup"><span data-stu-id="d285d-103">Coverage settings</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d285d-104">Az alapütemezés a fedezeti beállítások segítségével számítja ki a cikkszükségleteket.</span><span class="sxs-lookup"><span data-stu-id="d285d-104">Master scheduling uses coverage settings to calculate item requirements.</span></span> 

<span data-ttu-id="d285d-105">A fedezeti beállítások többféleképpen is megadhatók:</span><span class="sxs-lookup"><span data-stu-id="d285d-105">You can specify coverage settings in several ways:</span></span>

-   <span data-ttu-id="d285d-106">Fedezeti csoport fedezeti beállításainak meghatározása.</span><span class="sxs-lookup"><span data-stu-id="d285d-106">Specify coverage settings for a coverage group.</span></span> <span data-ttu-id="d285d-107">Létrehozhat egy fedezeti csoportot, amely tartalmazza minden hozzákapcsolt termék fedezeti beállításait.</span><span class="sxs-lookup"><span data-stu-id="d285d-107">You can create a coverage group that contains settings for all products that are linked to the coverage group.</span></span> <span data-ttu-id="d285d-108">Kattintson az **Alaptervezés &gt; Beállítás &gt; Fedezet &gt; Fedezeti csoportok** lehetőségekre fedezeti csoport létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="d285d-108">Click **Master planning &gt; Setup &gt; Coverage &gt; Coverage groups** to create a coverage group.</span></span> <span data-ttu-id="d285d-109">A fedezeti csoportot hozzákapcsolhatja egy termékhez is.</span><span class="sxs-lookup"><span data-stu-id="d285d-109">You can link a coverage group to a product.</span></span> <span data-ttu-id="d285d-110">Ha a kapcsolat egy adott telephely, raktár vagy termékdimenzió esetében specifikus használja a **Fedezetcsoport** mezőt a **Cikkfedezet** lapon.</span><span class="sxs-lookup"><span data-stu-id="d285d-110">If the link is specific to a site, warehouse, or product dimension, use the **Coverage group** field on the **Item coverage** page.</span></span> <span data-ttu-id="d285d-111">Ha a kapcsolat általános, függetlenül a cikkdimenzióktól, használja a **Fedezeti csoport** lehetőséget a **Terv** gyorslapján a **Termékadatok** lapon.</span><span class="sxs-lookup"><span data-stu-id="d285d-111">If the link is generic, regardless of the product dimensions, use the **Coverage group** on the **Plan** FastTab on the **Product details** page.</span></span> <span data-ttu-id="d285d-112">Ha nem csatol fedezeti csoportot egy termékhez, az alaptervezés az **Általános fedezetcsoport** lehetőséget használja, amely meg van adva az **Alaptervezés paraméterei** oldalon, alapértelmezettként.</span><span class="sxs-lookup"><span data-stu-id="d285d-112">If you do not link a coverage group to a product, master planning uses the **General coverage group** that is specified on the **Master planning parameters** page as the default.</span></span>

-   <span data-ttu-id="d285d-113">Termék fedezeti beállításainak meghatározása.</span><span class="sxs-lookup"><span data-stu-id="d285d-113">Specify coverage settings for a product.</span></span> <span data-ttu-id="d285d-114">Létrehozhatja egy adott termék fedezeti beállításait is.</span><span class="sxs-lookup"><span data-stu-id="d285d-114">You can create coverage settings for a specific product.</span></span> <span data-ttu-id="d285d-115">Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d285d-115">Click **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="d285d-116">Válassza ki a terméket a **Műveleti ablakmodulon**, a **Terv** lapon, a **Fedezeti csoportrészben** kattintson **Cikkfedezet** lehetőségre a **Cikkfedezet** lap megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d285d-116">Select the product, on the **Action Pane**, on the **Plan** tab, in the **Coverage group**, click **Item coverage** to open the **Item coverage** page.</span></span> <span data-ttu-id="d285d-117">Ha a termék már össze van kapcsolva egy fedezeti csoporttal, akkor a **Felülbírálás** mező beállításával felülbírálhatja a fedezeti csoport beállításait.</span><span class="sxs-lookup"><span data-stu-id="d285d-117">If the product is already linked to a coverage group, you can override the coverage group settings by using the **Override** field.</span></span> <span data-ttu-id="d285d-118">A fedezeti beállítások a**Cikkfedezet** lapon elsőbbséget élveznek a **Fedezeti csoport** lap beállításaival szemben.</span><span class="sxs-lookup"><span data-stu-id="d285d-118">The coverage settings on the **Item coverage** page take precedence over the settings on the **Coverage group** page.</span></span>

<!-- -->

-   <span data-ttu-id="d285d-119">Termék fedezeti beállításainak meghatározása varázslóval.</span><span class="sxs-lookup"><span data-stu-id="d285d-119">Specify coverage settings for a product by using a wizard.</span></span> <span data-ttu-id="d285d-120">A varázsló olyan útmutató, amely segít beállítani az elsődleges cikkfedezeti paramétereket.</span><span class="sxs-lookup"><span data-stu-id="d285d-120">The wizard is a step-by-step guide to help you set up the primary item coverage parameters.</span></span> <span data-ttu-id="d285d-121">A **Cikkfedezet** lapon kattintson a **Varázsló** lehetőségre a **Cikkfedezet varázsló** megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d285d-121">On the **Item coverage** page, click **Wizard** to open the **Item Coverage Wizard**.</span></span>

<!-- -->

- <span data-ttu-id="d285d-122">Dimenziócsoport fedezeti beállításainak meghatározása.</span><span class="sxs-lookup"><span data-stu-id="d285d-122">Specify coverage settings for a dimension group.</span></span> <span data-ttu-id="d285d-123">Kattintson a **Termékinformációk kezelése &gt; Közös &gt; Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d285d-123">Click **Product information management &gt; Common &gt; Released products**.</span></span> <span data-ttu-id="d285d-124">A **Kiadott termék részletei** oldalon, az **Általános** fülön, az **Adminisztráció** csoportban kattintson a **Tárolásidimenzió-csoport** hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d285d-124">On the **Released product detail** page, on the **General** tab, in the **Administration** group, click the **Storage dimension group** link.</span></span> <span data-ttu-id="d285d-125">A **Tárolásidimenzió-csoport** oldalon válassza a **Fedezeti terv dimenziónként** mezőt cikkfedezeti beállítások létrehozására egy dimenzióhoz a tárolásidimenzió-csoportban.</span><span class="sxs-lookup"><span data-stu-id="d285d-125">On the **Storage dimension group** page, select the **Coverage plan by dimension** field to create the coverage settings for a dimension in the storage dimension group.</span></span> <span data-ttu-id="d285d-126">Minden termékdimenzió, például a konfiguráció, szín, méret, stílus, kell, hogy rendelkezzen egy kiválasztott **Fedezeti terv dimenziónként** mezővel.</span><span class="sxs-lookup"><span data-stu-id="d285d-126">All product dimensions, such as configuration, color, size, style, must have the **Coverage plan by dimension** field selected.</span></span>



<a name="additional-resources"></a><span data-ttu-id="d285d-127">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="d285d-127">Additional resources</span></span>
--------

[<span data-ttu-id="d285d-128">Alaptervek</span><span class="sxs-lookup"><span data-stu-id="d285d-128">Master plans</span></span>](master-plans.md)



