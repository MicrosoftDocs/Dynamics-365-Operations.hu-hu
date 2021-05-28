---
title: Termékek és kategóriák hiányoznak környezeti másolás után
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amelyek segítséget nyújt abban az esetben, ha termékek és kategóriák hiányoznak, miután egy webhelyet környezetek között vagy ugyanazon környezeten belül másolt.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
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
ms.openlocfilehash: 4964b9623a91286d4f8260bcae7941feb48f8962
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022398"
---
# <a name="products-and-categories-missing-after-environment-copy"></a><span data-ttu-id="e1fb1-103">Termékek és kategóriák hiányoznak környezeti másolás után</span><span class="sxs-lookup"><span data-stu-id="e1fb1-103">Products and categories missing after environment copy</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e1fb1-104">Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amelyek segítséget nyújt abban az esetben, ha termékek és kategóriák hiányoznak, miután egy webhelyet környezetek között vagy ugyanazon környezeten belül másolt.</span><span class="sxs-lookup"><span data-stu-id="e1fb1-104">This topic provides troubleshooting guidance that can help when products and categories are missing after a site is copied between environments or within the same environment.</span></span>

## <a name="description"></a><span data-ttu-id="e1fb1-105">Leírás</span><span class="sxs-lookup"><span data-stu-id="e1fb1-105">Description</span></span>

<span data-ttu-id="e1fb1-106">Miután a webhelyet átmásolták az egyik környezetből a másikba, vagy a másolás ugyanabban a környezetben történt, termékek és a kategóriák hiányoznak a webhelyről.</span><span class="sxs-lookup"><span data-stu-id="e1fb1-106">After a site is copied from one environment to another, or within the same environment, the products and categories are missing from the site.</span></span> <span data-ttu-id="e1fb1-107">A termékek és kategóriák az e-kereskedelmi üzletből és a Commerce webhelyszerkesztő **Termékek** lapjáról hiányoznak.</span><span class="sxs-lookup"><span data-stu-id="e1fb1-107">The products and categories will be missing from the e-commerce storefront and from the **Products** tab in Commerce site builder.</span></span>

## <a name="resolution"></a><span data-ttu-id="e1fb1-108">Felbontás</span><span class="sxs-lookup"><span data-stu-id="e1fb1-108">Resolution</span></span>

### <a name="map-the-channel-operating-unit-number-to-a-newly-copied-site-in-commerce-site-builder"></a><span data-ttu-id="e1fb1-109">A csatorna üzemiegység-számának hozzárendelése egy újonnan másolt webhelyre a Commerce webhelyszerkesztőben</span><span class="sxs-lookup"><span data-stu-id="e1fb1-109">Map the channel operating unit number to a newly copied site in Commerce site builder</span></span>

<span data-ttu-id="e1fb1-110">Kövesse az alábbi lépéseket a csatorna üzemiegység-számának (OUN) egy újonnan másolt webhelyre való hozzárendeléséhez a Commerce webhelyszerkesztőben.</span><span class="sxs-lookup"><span data-stu-id="e1fb1-110">To map the channel operating unit number (OUN) to a newly copied site in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="e1fb1-111">Válassza ki az újonnan másolt webhelyet.</span><span class="sxs-lookup"><span data-stu-id="e1fb1-111">Select the newly copied site.</span></span>
1. <span data-ttu-id="e1fb1-112">A **Webhely beállításai** pontban válassza ki a **Csatornák** elemet.</span><span class="sxs-lookup"><span data-stu-id="e1fb1-112">Under **Site settings**, select **Channels**.</span></span>
1. <span data-ttu-id="e1fb1-113">A csatorna neve mellett válassza ki a három pontot (**...**), majd válassza az **Online áruházcsatorna módosítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e1fb1-113">Next to the channel name, select the ellipsis (**...**), and then select **Change online store channel**.</span></span>
1. <span data-ttu-id="e1fb1-114">Az **Online áruházcsatorna módosítása** párbeszédpanelen válassza ki az újonnan másolt webhelyhez hozzárendelni kívánt csatornát, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e1fb1-114">In the **Change online store channel** dialog box, select the channel to map to the newly copied site, and then select **OK**.</span></span>
1. <span data-ttu-id="e1fb1-115">Válassza a **Mentés és közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e1fb1-115">Select **Save and publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e1fb1-116">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="e1fb1-116">Additional resources</span></span>

[<span data-ttu-id="e1fb1-117">Dynamics 365 Commerce webhely társítása online csatornával</span><span class="sxs-lookup"><span data-stu-id="e1fb1-117">Associate a Dynamics 365 Commerce site with an online channel</span></span>](../associate-site-online-store.md)
