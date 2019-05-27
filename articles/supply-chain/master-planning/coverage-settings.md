---
title: Fedezeti beállítások
description: Ez a témakör az alapütemezés által a cikkszükségletek számításához használt fedezeti beállításokkal kapcsolatban tartalmaz tájékoztatást.
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
ms.openlocfilehash: 99e094a7131b6d3a299fc72abd0141529908ddd2
ms.sourcegitcommit: 9e50bee6a67f0fe2fa6f86e02c7e8de16d0e2482
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/08/2019
ms.locfileid: "1538894"
---
# <a name="coverage-settings"></a><span data-ttu-id="3d4bc-103">Fedezeti beállítások</span><span class="sxs-lookup"><span data-stu-id="3d4bc-103">Coverage settings</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3d4bc-104">Az alapütemezés a fedezeti beállítások segítségével számítja ki a cikkszükségleteket.</span><span class="sxs-lookup"><span data-stu-id="3d4bc-104">Master scheduling uses coverage settings to calculate item requirements.</span></span>

<span data-ttu-id="3d4bc-105">A fedezeti beállítások többféleképpen is megadhatók:</span><span class="sxs-lookup"><span data-stu-id="3d4bc-105">You can specify coverage settings in several ways:</span></span>

- <span data-ttu-id="3d4bc-106">Fedezeti csoport fedezeti beállításainak meghatározása.</span><span class="sxs-lookup"><span data-stu-id="3d4bc-106">Specify coverage settings for a coverage group.</span></span>

    <span data-ttu-id="3d4bc-107">Létrehozhat egy fedezeti csoportot, amely tartalmazza minden hozzákapcsolt termék fedezeti beállításait.</span><span class="sxs-lookup"><span data-stu-id="3d4bc-107">You can create a coverage group that contains settings for all products that are linked to the coverage group.</span></span> <span data-ttu-id="3d4bc-108">Fedezeti csoport létrehozásához kattintson az **Alaptervezés &gt; Beállítás &gt; Fedezet &gt; Fedezeti csoportok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3d4bc-108">To create a coverage group, go to **Master planning &gt; Setup &gt; Coverage &gt; Coverage groups**.</span></span> <span data-ttu-id="3d4bc-109">A fedezeti csoportot hozzákapcsolhatja egy termékhez is.</span><span class="sxs-lookup"><span data-stu-id="3d4bc-109">You can link a coverage group to a product.</span></span> <span data-ttu-id="3d4bc-110">Ha a kapcsolat egy adott telephely, raktár vagy termékdimenzió esetében specifikus használja a **Fedezetcsoport** mezőt a **Cikkfedezet** lapon.</span><span class="sxs-lookup"><span data-stu-id="3d4bc-110">If the link is specific to a site, warehouse, or product dimension, use the **Coverage group** field on the **Item coverage** page.</span></span> <span data-ttu-id="3d4bc-111">Ha a kapcsolat általános, függetlenül a cikkdimenzióktól, használja a **Fedezeti csoport** mezőt a **Terv** gyorslapján a **Termékadatok** lapon.</span><span class="sxs-lookup"><span data-stu-id="3d4bc-111">If the link is generic, regardless of the product dimensions, use the **Coverage group** field on the **Plan** FastTab of the **Product details** page.</span></span> <span data-ttu-id="3d4bc-112">Alapértelmezett módon ha nem csatol fedezeti csoportot egy termékhez, az alaptervezés az Általános fedezetcsoport lehetőséget használja, amely meg van adva az **Alaptervezés paraméterei** oldalon.</span><span class="sxs-lookup"><span data-stu-id="3d4bc-112">By default, if you don't link a coverage group to a product, master planning uses the general coverage group that is specified on the **Master planning parameters** page.</span></span>

- <span data-ttu-id="3d4bc-113">Termék fedezeti beállításainak meghatározása.</span><span class="sxs-lookup"><span data-stu-id="3d4bc-113">Specify coverage settings for a product.</span></span>

    <span data-ttu-id="3d4bc-114">Létrehozhatja egy adott termék fedezeti beállításait is.</span><span class="sxs-lookup"><span data-stu-id="3d4bc-114">You can create coverage settings for a specific product.</span></span> <span data-ttu-id="3d4bc-115">Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3d4bc-115">Go to **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="3d4bc-116">Válassza ki a terméket, majd a Műveleti ablakmodulon a **Terv** lapon, a **Fedezet** csoportban válassza a **Cikkfedezet** lehetőségre a **Cikkfedezet** lap megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="3d4bc-116">Select the product, and then, on the Action Pane, on the **Plan** tab, in the **Coverage** group, select **Item coverage** to open the **Item coverage** page.</span></span> <span data-ttu-id="3d4bc-117">Ha a termék már össze van kapcsolva egy fedezeti csoporttal, akkor a **Felülbírálás** mező beállításával felülbírálhatja a fedezeti csoport beállításait.</span><span class="sxs-lookup"><span data-stu-id="3d4bc-117">If the product is already linked to a coverage group, you can override the coverage group settings by using the **Override** field.</span></span> <span data-ttu-id="3d4bc-118">A fedezeti beállítások a**Cikkfedezet** lapon elsőbbséget élveznek a **Fedezeti csoport** lap beállításaival szemben.</span><span class="sxs-lookup"><span data-stu-id="3d4bc-118">The coverage settings on the **Item coverage** page take precedence over the settings on the **Coverage group** page.</span></span>

- <span data-ttu-id="3d4bc-119">Termék fedezeti beállításainak meghatározása varázslóval.</span><span class="sxs-lookup"><span data-stu-id="3d4bc-119">Specify coverage settings for a product by using a wizard.</span></span>

    <span data-ttu-id="3d4bc-120">A varázsló lépésenként végigvezeti az elsődleges cikkfedezeti paraméterek beállításának lépésein.</span><span class="sxs-lookup"><span data-stu-id="3d4bc-120">The wizard guides you step by step through the process of setting up the primary item coverage parameters.</span></span> <span data-ttu-id="3d4bc-121">A **Cikkfedezet** lapon, a műveleti ablaktáblán kattintson a **Varázsló** lehetőségre a **Cikkfedezet varázsló** megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="3d4bc-121">On the **Item coverage** page, on the Action Pane, select **Wizard** to open the **Item Coverage Wizard**.</span></span>

- <span data-ttu-id="3d4bc-122">Dimenziócsoport fedezeti beállításainak meghatározása.</span><span class="sxs-lookup"><span data-stu-id="3d4bc-122">Specify coverage settings for a dimension group.</span></span>

    <span data-ttu-id="3d4bc-123">Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3d4bc-123">Go to **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="3d4bc-124">A **Kiadott termék részletei** oldalon, az **Általános** gyorslapon, az **Adminisztráció** szakaszban válassza a **Tárolásidimenzió-csoport** hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="3d4bc-124">On the **Released product details** page, on the **General** FastTab, in the **Administration** section, select the link in the **Storage dimension group** field.</span></span> <span data-ttu-id="3d4bc-125">A **Tárolásidimenzió-csoportok** oldalon válassza a **Fedezeti terv dimenziónként** jelölőnégyzetet a cikkfedezeti beállítások létrehozására egy dimenzióhoz a tárolásidimenzió-csoportban.</span><span class="sxs-lookup"><span data-stu-id="3d4bc-125">On the **Storage dimension groups** page, select the **Coverage plan by dimension** check box to create the coverage settings for a dimension in the storage dimension group.</span></span> <span data-ttu-id="3d4bc-126">Minden termékdimenzió, például a konfiguráció, szín, méret, stílus esetén ki kell választani a **Fedezeti terv dimenziónként** mezőt.</span><span class="sxs-lookup"><span data-stu-id="3d4bc-126">The **Coverage plan by dimension** field must be selected for all product dimensions, such as configuration, color, size, and style.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3d4bc-127">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="3d4bc-127">Additional resources</span></span>

[<span data-ttu-id="3d4bc-128">Alaptervek</span><span class="sxs-lookup"><span data-stu-id="3d4bc-128">Master plans</span></span>](master-plans.md)
