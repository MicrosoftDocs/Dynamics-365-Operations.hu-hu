---
title: A termékek és a kategóriák nem jelennek meg a Commerce webhelyszerkesztőben az új webhely hozzárendelése után
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha a termékek és kategóriák nem jelennek meg a Commerce webhelykészítőben az új webhely hozzárendelése után.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3d7cd2274cb447a622f9ffe6f00b1b27ecc7db52
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801579"
---
# <a name="products-and-categories-dont-appear-in-commerce-site-builder-after-a-new-site-is-mapped"></a><span data-ttu-id="8e738-103">A termékek és a kategóriák nem jelennek meg a Commerce webhelyszerkesztőben az új webhely hozzárendelése után</span><span class="sxs-lookup"><span data-stu-id="8e738-103">Products and categories don't appear in Commerce site builder after a new site is mapped</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8e738-104">Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha a termékek és kategóriák nem jelennek meg a Commerce webhelykészítőben az új webhely hozzárendelése után.</span><span class="sxs-lookup"><span data-stu-id="8e738-104">This topic provides troubleshooting guidance that can help when products and categories don't appear in Commerce site builder after a new site is mapped.</span></span>

## <a name="description"></a><span data-ttu-id="8e738-105">Leírás</span><span class="sxs-lookup"><span data-stu-id="8e738-105">Description</span></span>

<span data-ttu-id="8e738-106">A termékek és a kategóriák nem jelennek meg a Commerce webhelyszerkesztőben az új webhely hozzárendelése után.</span><span class="sxs-lookup"><span data-stu-id="8e738-106">Products and categories don't appear in Commerce site builder after a new site is mapped.</span></span>

## <a name="resolution"></a><span data-ttu-id="8e738-107">Felbontás</span><span class="sxs-lookup"><span data-stu-id="8e738-107">Resolution</span></span>

### <a name="add-products-to-channel-categories-in-commerce-headquarters"></a><span data-ttu-id="8e738-108">Termékek hozzáadása a csatornakategóriákhoz a Commerce központi felületén</span><span class="sxs-lookup"><span data-stu-id="8e738-108">Add products to channel categories in Commerce headquarters</span></span>

<span data-ttu-id="8e738-109">Kövesse az alábbi lépéseket a termékek csatornakategóriákhoz való hozzáadásához a Commerce központi felületén.</span><span class="sxs-lookup"><span data-stu-id="8e738-109">To add products to channel categories in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="8e738-110">Nyissa meg a következőt: **Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Csatornakategóriák és termékattribútumok**.</span><span class="sxs-lookup"><span data-stu-id="8e738-110">Go to **Retail and Commerce \> Channel setup \> Channel categories and product attributes**.</span></span>
1. <span data-ttu-id="8e738-111">Válassza ki a bal oldali navigációs részben azt a kategóriát, amely meg fog jelenni az e-kereskedelmi webhelyen.</span><span class="sxs-lookup"><span data-stu-id="8e738-111">In the left navigation, select the category that should appear on the e-commerce site.</span></span>
1. <span data-ttu-id="8e738-112">A **Termékek** gyorslapon válassza a **Hozzáadás** elemet.</span><span class="sxs-lookup"><span data-stu-id="8e738-112">On the **Products** FastTab, select **Add**.</span></span>
1. <span data-ttu-id="8e738-113">Az **Elérhető termékek** szakaszban válassza ki a megjeleníteni kívánt termékeket, majd válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8e738-113">In the **Available Products** section, select the products that should appear, and then select **Add**.</span></span>
1. <span data-ttu-id="8e738-114">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8e738-114">Select **OK**.</span></span>
1. <span data-ttu-id="8e738-115">Miután a termékek megjelennek a **Termékek** gyorslapon, válassza a **Csatornafrissítések közzététele** lehetőséget a műveleti ablaktáblán.</span><span class="sxs-lookup"><span data-stu-id="8e738-115">After the products appear on the **Products** FastTab, select **Publish channel updates** on the Action Pane.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8e738-116">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="8e738-116">Additional resources</span></span>

[<span data-ttu-id="8e738-117">Csatorna konfigurálása csatorna navigációs hierarchiájának használatára</span><span class="sxs-lookup"><span data-stu-id="8e738-117">Configure a channel to use a channel navigation hierarchy</span></span>](../configure-channel-hierarchy.md)
