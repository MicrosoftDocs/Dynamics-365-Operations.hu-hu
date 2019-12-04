---
title: Fedezeti beállítások
description: Ez a témakör az alapütemezés által a cikkszükségletek számításához használt fedezeti beállításokkal kapcsolatban tartalmaz tájékoztatást.
author: roxanadiaconu
manager: AnnBe
ms.date: 09/13/2019
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
ms.openlocfilehash: 8b8263afd8469d9bf3f566c4c44a5976d7ff3e86
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/18/2019
ms.locfileid: "2815203"
---
# <a name="coverage-settings"></a><span data-ttu-id="2616b-103">Fedezeti beállítások</span><span class="sxs-lookup"><span data-stu-id="2616b-103">Coverage settings</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2616b-104">Az alapütemezés a fedezeti beállítások segítségével számítja ki a cikkszükségleteket.</span><span class="sxs-lookup"><span data-stu-id="2616b-104">Master scheduling uses coverage settings to calculate item requirements.</span></span>

<span data-ttu-id="2616b-105">A fedezeti beállítások többféleképpen is megadhatók:</span><span class="sxs-lookup"><span data-stu-id="2616b-105">You can specify coverage settings in several ways:</span></span>

- <span data-ttu-id="2616b-106">Fedezeti csoport fedezeti beállításainak meghatározása.</span><span class="sxs-lookup"><span data-stu-id="2616b-106">Specify coverage settings for a coverage group.</span></span>

    <span data-ttu-id="2616b-107">Létrehozhat egy fedezeti csoportot, amely tartalmazza minden hozzákapcsolt termék fedezeti beállításait.</span><span class="sxs-lookup"><span data-stu-id="2616b-107">You can create a coverage group that contains settings for all products that are linked to the coverage group.</span></span> <span data-ttu-id="2616b-108">Fedezeti csoport létrehozásához kattintson az **Alaptervezés &gt; Beállítás &gt; Fedezet &gt; Fedezeti csoportok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2616b-108">To create a coverage group, go to **Master planning &gt; Setup &gt; Coverage &gt; Coverage groups**.</span></span> <span data-ttu-id="2616b-109">A fedezeti csoportot hozzákapcsolhatja egy termékhez is.</span><span class="sxs-lookup"><span data-stu-id="2616b-109">You can link a coverage group to a product.</span></span> <span data-ttu-id="2616b-110">Ha a kapcsolat egy adott telephely, raktár vagy termékdimenzió esetében specifikus használja a **Fedezetcsoport** mezőt a **Cikkfedezet** lapon.</span><span class="sxs-lookup"><span data-stu-id="2616b-110">If the link is specific to a site, warehouse, or product dimension, use the **Coverage group** field on the **Item coverage** page.</span></span> <span data-ttu-id="2616b-111">Ha a kapcsolat általános, függetlenül a cikkdimenzióktól, használja a **Fedezeti csoport** mezőt a **Terv** gyorslapján a **Termékadatok** lapon.</span><span class="sxs-lookup"><span data-stu-id="2616b-111">If the link is generic, regardless of the product dimensions, use the **Coverage group** field on the **Plan** FastTab of the **Product details** page.</span></span> <span data-ttu-id="2616b-112">Alapértelmezett módon ha nem csatol fedezeti csoportot egy termékhez, az alaptervezés az Általános fedezetcsoport lehetőséget használja, amely meg van adva az **Alaptervezés paraméterei** oldalon.</span><span class="sxs-lookup"><span data-stu-id="2616b-112">By default, if you don't link a coverage group to a product, master planning uses the general coverage group that is specified on the **Master planning parameters** page.</span></span>

- <span data-ttu-id="2616b-113">Termék fedezeti beállításainak meghatározása.</span><span class="sxs-lookup"><span data-stu-id="2616b-113">Specify coverage settings for a product.</span></span>

    <span data-ttu-id="2616b-114">Létrehozhatja egy adott termék fedezeti beállításait is.</span><span class="sxs-lookup"><span data-stu-id="2616b-114">You can create coverage settings for a specific product.</span></span> <span data-ttu-id="2616b-115">Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2616b-115">Go to **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="2616b-116">Válassza ki a terméket, majd a Műveleti ablakmodulon a **Terv** lapon, a **Fedezet** csoportban válassza a **Cikkfedezet** lehetőségre a **Cikkfedezet** lap megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="2616b-116">Select the product, and then, on the Action Pane, on the **Plan** tab, in the **Coverage** group, select **Item coverage** to open the **Item coverage** page.</span></span> <span data-ttu-id="2616b-117">Ha a termék már össze van kapcsolva egy fedezeti csoporttal, akkor a **Felülbírálás** mező beállításával felülbírálhatja a fedezeti csoport beállításait.</span><span class="sxs-lookup"><span data-stu-id="2616b-117">If the product is already linked to a coverage group, you can override the coverage group settings by using the **Override** field.</span></span> <span data-ttu-id="2616b-118">A fedezeti beállítások a**Cikkfedezet** lapon elsőbbséget élveznek a **Fedezeti csoport** lap beállításaival szemben.</span><span class="sxs-lookup"><span data-stu-id="2616b-118">The coverage settings on the **Item coverage** page take precedence over the settings on the **Coverage group** page.</span></span>

- <span data-ttu-id="2616b-119">Termék fedezeti beállításainak meghatározása varázslóval.</span><span class="sxs-lookup"><span data-stu-id="2616b-119">Specify coverage settings for a product by using a wizard.</span></span>

    <span data-ttu-id="2616b-120">A varázsló lépésenként végigvezeti az elsődleges cikkfedezeti paraméterek beállításának lépésein.</span><span class="sxs-lookup"><span data-stu-id="2616b-120">The wizard guides you step by step through the process of setting up the primary item coverage parameters.</span></span> <span data-ttu-id="2616b-121">A **Cikkfedezet** lapon, a műveleti ablaktáblán kattintson a **Varázsló** lehetőségre a **Cikkfedezet varázsló** megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="2616b-121">On the **Item coverage** page, on the Action Pane, select **Wizard** to open the **Item Coverage Wizard**.</span></span>

- <span data-ttu-id="2616b-122">Dimenziócsoport fedezeti beállításainak meghatározása.</span><span class="sxs-lookup"><span data-stu-id="2616b-122">Specify coverage settings for a dimension group.</span></span>

    <span data-ttu-id="2616b-123">Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2616b-123">Go to **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="2616b-124">A **Kiadott termék részletei** oldalon, az **Általános** gyorslapon, az **Adminisztráció** szakaszban válassza a **Tárolásidimenzió-csoport** hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="2616b-124">On the **Released product details** page, on the **General** FastTab, in the **Administration** section, select the link in the **Storage dimension group** field.</span></span> <span data-ttu-id="2616b-125">A **Tárolásidimenzió-csoportok** oldalon válassza a **Fedezeti terv dimenziónként** jelölőnégyzetet a cikkfedezeti beállítások létrehozására egy dimenzióhoz a tárolásidimenzió-csoportban.</span><span class="sxs-lookup"><span data-stu-id="2616b-125">On the **Storage dimension groups** page, select the **Coverage plan by dimension** check box to create the coverage settings for a dimension in the storage dimension group.</span></span> <span data-ttu-id="2616b-126">Minden termékdimenzió, például a konfiguráció, szín, méret, stílus esetén ki kell választani a **Fedezeti terv dimenziónként** mezőt.</span><span class="sxs-lookup"><span data-stu-id="2616b-126">The **Coverage plan by dimension** field must be selected for all product dimensions, such as configuration, color, size, and style.</span></span>


## <a name="coverage-codes"></a><span data-ttu-id="2616b-127">Fedezeti kódok</span><span class="sxs-lookup"><span data-stu-id="2616b-127">Coverage codes</span></span>

<span data-ttu-id="2616b-128">Az Alaptervezés beállítható úgy, hogy különböző feltöltési módokat használjon.</span><span class="sxs-lookup"><span data-stu-id="2616b-128">Master planning can be configured to use different replenishment methods.</span></span> <span data-ttu-id="2616b-129">A feltöltési módok vagy a tételméretezés módszere a rendszer által a beszerzett vagy termelt cikkek kötegméretének meghatározására használt technika.</span><span class="sxs-lookup"><span data-stu-id="2616b-129">The replenishment methods or lot-sizing methods are the techniques used by the system to determine the batch size for purchased or produced items.</span></span> 

<span data-ttu-id="2616b-130">Minden feltöltési mód a következő fedezeti kódok egyikéhez van hozzárendelve:</span><span class="sxs-lookup"><span data-stu-id="2616b-130">Each replenishment method is assigned one of the following coverage codes:</span></span>

- <span data-ttu-id="2616b-131">**Manuális** – Az adagméretezési módszer, amelyen a rendszer nem javasol beszerzési, átviteli vagy termelési rendeléseket a cikkhez.</span><span class="sxs-lookup"><span data-stu-id="2616b-131">**Manual** - The lot-sizing method where the system does not suggest purchased, transfer, or production orders for the item.</span></span> <span data-ttu-id="2616b-132">A termékhez tartozó tervező lesz felelős a cikkek feltöltéséhez szükséges rendelések létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="2616b-132">The planner for the item will be in charge of creating the required orders for the replenishment of the item.</span></span>
- <span data-ttu-id="2616b-133">**Igény szerint** – Az az adagméretezési módszer, amelyben a rendszer a termékre vonatkozó szükséglet alapján tervezett beszerzési, átmozgatási vagy termelési rendelést hoz létre.</span><span class="sxs-lookup"><span data-stu-id="2616b-133">**Per requirement** - The lot-sizing method in which the system creates a planned purchase, transfer, or production order per requirement for the item.</span></span> <span data-ttu-id="2616b-134">Ez általában akkor használatos, ha drága cikkekkel dolgoznak, változó igényekkel.</span><span class="sxs-lookup"><span data-stu-id="2616b-134">This is generally used for expensive items with intermittent demand.</span></span>  
- <span data-ttu-id="2616b-135">**Időszakonként** – Az az adag-méretezési módszer, amely az adott időszakra vonatkozó összes igényt egy rendelésbe egyesíti a cikkre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="2616b-135">**Per period** - The lot-sizing method that combines all the demand for a period into one order for the item.</span></span> <span data-ttu-id="2616b-136">A rendelést az időszak első napján kell megtervezni, és a mennyisége a meghatározott időszakban teljesíti a nettó szükségletet.</span><span class="sxs-lookup"><span data-stu-id="2616b-136">The order will be planned for the first day of the period and its quantity will fulfill the net requirements during the established period.</span></span> <span data-ttu-id="2616b-137">Az időszak a cikk első igényével kezdődik, és a megadott időtartamra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="2616b-137">The period starts with the first demand of the item and covers the defined length in time.</span></span> <span data-ttu-id="2616b-138">A következő időszak a cikk következő igényével kezdődik.</span><span class="sxs-lookup"><span data-stu-id="2616b-138">The next period will start with the next requirements of the item.</span></span>
- <span data-ttu-id="2616b-139">**Min/max** – Az az adagméretezési módszer, amely a készlet feltöltését tartalmazza egy bizonyos szintig, amikor az előre jelzett aktuális készlet egy küszöbérték alatt van.</span><span class="sxs-lookup"><span data-stu-id="2616b-139">**Min/Max** - The lot-sizing method that contains the replenishment of inventory up to a certain level when the predicted on-hand is below a threshold.</span></span> <span data-ttu-id="2616b-140">A feltöltési mennyiség a maximális szint és az előre jelzett aktuális szint közötti különbség lesz.</span><span class="sxs-lookup"><span data-stu-id="2616b-140">The replenishment quantity will be the difference between the maximum level and the predicted on-hand level.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="2616b-141">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="2616b-141">Additional resources</span></span>

[<span data-ttu-id="2616b-142">Alaptervek áttekintése</span><span class="sxs-lookup"><span data-stu-id="2616b-142">Master plans overview</span></span>](master-plans.md)
