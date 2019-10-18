---
title: Retail-termékkategóriák és termékek kezelése
description: Ez a témakör leírja, hogy a termékkihelyezési vezetők hogyan használhatják a Retail termékkategóriákat a Retail-termékhierarchia és a kiadott termék részletei közötti kapcsolatok kezeléséhez.
author: ashishmsft
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: ''
ms.assetid: c7ed2ba5-87c6-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 27870fe6172479b891b885d9e84ca10b250e3399
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/24/2019
ms.locfileid: "2019508"
---
# <a name="manage-retail-product-categories-and-products"></a><span data-ttu-id="940fc-103">Kiskereskedelmi termékkategóriák és termékek kezelése</span><span class="sxs-lookup"><span data-stu-id="940fc-103">Manage Retail product categories and products</span></span>

[!include [banner](./includes/banner.md)]

<span data-ttu-id="940fc-104">Ez a témakör a termékkategóriák és termékek kezelésének továbbfejlesztett módját mutatja be a Dynamics 365 Retail alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="940fc-104">This topic describes an enhanced way to manage product categories and products in Dynamics 365 Retail.</span></span> <span data-ttu-id="940fc-105">A fejlesztések segítségével a termékkihelyezési vezetők megtekinthetik a termékek hierarchiája és a kiadott termékrészletek között megosztott terméktulajdonság-struktúráját.</span><span class="sxs-lookup"><span data-stu-id="940fc-105">The enhancements let merchandising managers view a structure of product properties that is shared between the product hierarchy and released product details.</span></span>

<span data-ttu-id="940fc-106">Ha többet szeretne tudni a termékkategóriák kezeléséről, a **Kategória és termék kezelése** munkaterületen válassza a **Kiskereskedelmi termékek hierarchiája** csempét.</span><span class="sxs-lookup"><span data-stu-id="940fc-106">To learn more about how to manage product categories, in the **Category and product management** workspace, select the **Retail product hierarchy** tile.</span></span>

<span data-ttu-id="940fc-107">Figyelje meg a megjelenő **Kiskereskedelmi termékek hierarchiája** lap továbbfejlesztett szerkezetét.</span><span class="sxs-lookup"><span data-stu-id="940fc-107">Notice the enhanced structure of the **Retail product hierarchy** page that appears.</span></span> <span data-ttu-id="940fc-108">A Retail korábbi verzióiban a terméktulajdonságok *alapvető terméktulajdonságokra* és *kiskereskedelmi termék tulajdonságaira* lettek felosztva, az alkalmazási hatókör alapján.</span><span class="sxs-lookup"><span data-stu-id="940fc-108">In previous versions of Retail, product properties were divided into *basic product properties* and *Retail product properties*, based on the scope of their applicability.</span></span> <span data-ttu-id="940fc-109">A Retail termékek tulajdonságai alkalmazhatóságukban *globálisak*.</span><span class="sxs-lookup"><span data-stu-id="940fc-109">Retail product properties are *global* in their scope of applicability.</span></span> <span data-ttu-id="940fc-110">Másként megfogalmazva ez azt jelenti, hogy egy adott terméktulajdonság esetében ugyanaz az érték van megosztva minden jogi személy esetében.</span><span class="sxs-lookup"><span data-stu-id="940fc-110">In other words, for a given product property, the same value is shared across all legal entities.</span></span> <span data-ttu-id="940fc-111">Az alapvető terméktulajdonságok viszont *jogi személy specifikusak*.</span><span class="sxs-lookup"><span data-stu-id="940fc-111">By contrast, basic product properties are *legal entity–specific*.</span></span> <span data-ttu-id="940fc-112">Ez azt jelenti, hogy egy adott alapvető terméktulajdonság értéke eltérő lehet a jogi személyek esetében a jogi személyek egyedi üzleti igényei alapján.</span><span class="sxs-lookup"><span data-stu-id="940fc-112">In other words, for a given basic product property, the value can differ across legal entities, depending on the individual business requirements of each legal entity.</span></span>

<span data-ttu-id="940fc-113">A továbbfejlesztett termékkategória struktúrában a terméktulajdonságok logikailag el vannak választva a csoporton belüli alkalmazhatóság alapján a megjelent termék részletei képernyőstruktúrájának megfelelően.</span><span class="sxs-lookup"><span data-stu-id="940fc-113">In the enhanced product category structure, product properties are logically separated based on their applicability in a group, to reflect the structure of the released product details form structure.</span></span>

![Mezők csoportosítása a tulajdonságaik alkalmazhatóságának terjedelme alapján](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

<span data-ttu-id="940fc-115">Válthat aközött, hogy a jogi személyhez megadott tulajdonságokat az összes a jogi személyre, vagy egy meghatározott jogi személyre nézve kezeli.</span><span class="sxs-lookup"><span data-stu-id="940fc-115">You can switch between managing legal entity–specific properties across all legal entities and managing them for a specific legal entity.</span></span>

<span data-ttu-id="940fc-116">A tulajdonságok az összes jogi személy közti kezeléséhez válassza a **Megjelenítés minden jogi személyre** (vagy **Szerkesztés minden jogi személyre**) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="940fc-116">To manage properties across all legal entities, select **View for all legal entities** (or **Edit for all legal entities**).</span></span>

![Megjelenítés/szerkesztés minden jogi személyre](media/ToggleBackToEditForSpecificLegalEntity.PNG)

<span data-ttu-id="940fc-118">A tulajdonságok meghatározott jogi személynél való kezeléséhez válassza a **Megjelenítés egy meghatározott jogi személyre** (vagy **Szerkesztés egy meghatározott jogi személyre**) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="940fc-118">To manage properties for a specific legal entity, select **View for a specific legal entity** (or **Edit for a specific legal entity**).</span></span>

![Megjelenítés/szerkesztés egy meghatározott jogi személyre](media/ToggleToEditForAllLegalEntities.PNG)

<span data-ttu-id="940fc-120">Amellett a bővített Retail termékkategória-szerkezetben a termékkihelyezési vezető most meghatározhat egy alapértelmezett értéket a terméktulajdonságok egy további csoportjához egy egyéni kategória szintjén.</span><span class="sxs-lookup"><span data-stu-id="940fc-120">Additionally, in the enhanced Retail product category structure, a merchandising manager can now define default values for an additional set of product properties at the level of the individual category.</span></span> <span data-ttu-id="940fc-121">Ezután a termékek létrehozáskor öröklik az alapértelmezett értékeket a termék tulajdonságaik alapján, ezen tulajdonságok a termékhierarchiában lévő egyedi kategóriával való társításuk alapján.</span><span class="sxs-lookup"><span data-stu-id="940fc-121">Then, when products are created, they inherit default values for their product properties, based on the association of those properties with an individual category in the product hierarchy.</span></span> <span data-ttu-id="940fc-122">A termékkihelyezési vezetők módosíthatják is ezeket az örökölt terméktulajdonságokat az egyes termékekhez, az egyedi üzleti követelményeknek megfelelően.</span><span class="sxs-lookup"><span data-stu-id="940fc-122">These inherited product properties can also be modified for each product to meet individual business requirements.</span></span>

## <a name="selecting-properties-to-update-products-on-the-retail-product-hierarchy-page"></a><span data-ttu-id="940fc-123">Tulajdonságok kiválasztása a termékek frissítéséhez a Retail termékhierarchia lapról</span><span class="sxs-lookup"><span data-stu-id="940fc-123">Selecting properties to update products on the Retail product hierarchy page</span></span>

<span data-ttu-id="940fc-124">A terméktulajdonságok új, továbbfejlesztett struktúrája segítségével kiválaszthatja, melyik frissített terméktulajdonságoknak kell átkerülniük a kapcsolódó termékekbe.</span><span class="sxs-lookup"><span data-stu-id="940fc-124">You can use the new enhanced structure for product properties to select updated product properties that must be pushed to the associated products.</span></span> <span data-ttu-id="940fc-125">A **Kiskereskedelmi termékek hierarchiája** oldalon a műveleti ablaktáblában válassza a **Kategória** elemet, majd a **Termékek frissítése** lehetőséget a **Termékek frissítése** dialógusablak megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="940fc-125">On the **Retail product hierarchy** page, on the Action Pane, select **Category**, and then select **Update products** to open the **Update products** dialog box.</span></span>

![Termékek frissítése párbeszédpanel](media/NewUpdateProductsEnhancedView.PNG)
