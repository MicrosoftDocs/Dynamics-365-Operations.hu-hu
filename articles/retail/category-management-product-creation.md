---
title: "Retail-termékkategóriák és termékek kezelése"
description: "Ez a témakör leírja, hogy a termékkihelyezési vezetők hogyan használhatják a Retail termékkategóriákat a Retail-termékhierarchia és a kiadott termék részletei közötti kapcsolatok kezeléséhez."
author: ashishmsft
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 
ms.assetid: c7ed2ba5-87c6-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 19c972164474c972aab642c3cccc67cf396a6cb2
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2018

---

# <a name="manage-retail-product-categories-and-products"></a><span data-ttu-id="988cd-103">Retail-termékkategóriák és termékek kezelése</span><span class="sxs-lookup"><span data-stu-id="988cd-103">Manage Retail product categories and products</span></span>

[!include [banner](./includes/banner.md)]

<span data-ttu-id="988cd-104">Ez a témakör a Retail-termékkategóriák és termékek kezelésének továbbfejlesztett módját mutatja be a Microsoft Dynamics 365 for Retail alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="988cd-104">This topic describes an enhanced way to manage Retail product categories and products in Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="988cd-105">A fejlesztések segítségével a termékkihelyezési vezetők megtekinthetik a Retail termékek hierarchiája és a kiadott termékrészletek között megosztott terméktulajdonság-struktúráját.</span><span class="sxs-lookup"><span data-stu-id="988cd-105">The enhancements let merchandising managers view a structure of product properties that is shared between the Retail product hierarchy and released product details.</span></span>

<span data-ttu-id="988cd-106">Ha többet szeretne tudni a Retail-termékkategóriák kezeléséről, a **Kategória és termék kezelése** munkaterületen válassza a **Kiskereskedelmi termékek hierarchiája** csempét.</span><span class="sxs-lookup"><span data-stu-id="988cd-106">To learn more about how to manage Retail product categories, in the **Category and product management** workspace, select the **Retail product hierarchy** tile.</span></span>

<span data-ttu-id="988cd-107">Figyelje meg a megjelenő **Kiskereskedelmi termékek hierarchiája** lap továbbfejlesztett szerkezetét.</span><span class="sxs-lookup"><span data-stu-id="988cd-107">Notice the enhanced structure of the **Retail product hierarchy** page that appears.</span></span> <span data-ttu-id="988cd-108">A Retail korábbi verzióiban a terméktulajdonságok *alapvető terméktulajdonságokra* és *kiskereskedelmi termék tulajdonságaira* lettek felosztva, az alkalmazási hatókör alapján.</span><span class="sxs-lookup"><span data-stu-id="988cd-108">In previous versions of Retail, product properties were divided into *basic product properties* and *Retail product properties*, based on the scope of their applicability.</span></span> <span data-ttu-id="988cd-109">A Retail termékek tulajdonságai alkalmazhatóságukban *globálisak*.</span><span class="sxs-lookup"><span data-stu-id="988cd-109">Retail product properties are *global* in their scope of applicability.</span></span> <span data-ttu-id="988cd-110">Másként megfogalmazva ez azt jelenti, hogy egy adott Retail-terméktulajdonság esetében ugyanaz az érték oszlik meg minden jogi személy esetében.</span><span class="sxs-lookup"><span data-stu-id="988cd-110">In other words, for a given Retail product property, the same value is shared across all legal entities.</span></span> <span data-ttu-id="988cd-111">Az alapvető terméktulajdonságok viszont *jogi személy specifikusak*.</span><span class="sxs-lookup"><span data-stu-id="988cd-111">By contrast, basic product properties are *legal entity–specific*.</span></span> <span data-ttu-id="988cd-112">Ez azt jelenti, hogy egy adott alapvető terméktulajdonság értéke eltérő lehet a jogi személyek esetében a jogi személyek egyedi üzleti igényei alapján.</span><span class="sxs-lookup"><span data-stu-id="988cd-112">In other words, for a given basic product property, the value can differ across legal entities, depending on the individual business requirements of each legal entity.</span></span>

<span data-ttu-id="988cd-113">A továbbfejlesztett Retail-termékkategória struktúrában a terméktulajdonságok logikailag el vannak választva a csoporton belüli alkalmazhatóság alapján a megjelent termék részletei képernyőstruktúrájának megfelelően.</span><span class="sxs-lookup"><span data-stu-id="988cd-113">In the enhanced Retail product category structure, product properties are logically separated based on their applicability in a group, to reflect the structure of the released product details form structure.</span></span>

![Mezők csoportosítása a tulajdonságaik alkalmazhatóságának terjedelme alapján](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

<span data-ttu-id="988cd-115">Válthat aközött, hogy a jogi személyhez megadott tulajdonságokat az összes a jogi személyre, vagy egy meghatározott jogi személyre nézve kezeli.</span><span class="sxs-lookup"><span data-stu-id="988cd-115">You can switch between managing legal entity–specific properties across all legal entities and managing them for a specific legal entity.</span></span>

<span data-ttu-id="988cd-116">A tulajdonságok az összes jogi személy közti kezeléséhez válassza a **Megjelenítés minden jogi személyre** (vagy **Szerkesztés minden jogi személyre**) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="988cd-116">To manage properties across all legal entities, select **View for all legal entities** (or **Edit for all legal entities**).</span></span>

![Megjelenítés/szerkesztés minden jogi személyre](media/ToggleBackToEditForSpecificLegalEntity.PNG)

<span data-ttu-id="988cd-118">A tulajdonságok meghatározott jogi személynél való kezeléséhez válassza a **Megjelenítés egy meghatározott jogi személyre** (vagy **Szerkesztés egy meghatározott jogi személyre**) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="988cd-118">To manage properties for a specific legal entity, select **View for a specific legal entity** (or **Edit for a specific legal entity**).</span></span>

![Megjelenítés/szerkesztés egy meghatározott jogi személyre](media/ToggleToEditForAllLegalEntities.PNG)

<span data-ttu-id="988cd-120">Amellett a bővített Retail termékkategória-szerkezetben a termékkihelyezési vezető most meghatározhat egy alapértelmezett értéket a terméktulajdonságok egy további csoportjához egy egyéni kategória szintjén.</span><span class="sxs-lookup"><span data-stu-id="988cd-120">Additionally, in the enhanced Retail product category structure, a merchandising manager can now define default values for an additional set of product properties at the level of the individual category.</span></span> <span data-ttu-id="988cd-121">Ezután a termékek létrehozáskor öröklik az alapértelmezett értékeket a termék tulajdonságaik alapján, ezen tulajdonságok a Retail termékhierarchiában lévő egyedi kategóriával való társításuk alapján.</span><span class="sxs-lookup"><span data-stu-id="988cd-121">Then, when products are created, they inherit default values for their product properties, based on the association of those properties with an individual category in Retail product hierarchy.</span></span> <span data-ttu-id="988cd-122">A termékkihelyezési vezetők módosíthatják is ezeket az örökölt terméktulajdonságokat az egyes termékekhez, az egyedi üzleti követelményeknek megfelelően.</span><span class="sxs-lookup"><span data-stu-id="988cd-122">These inherited product properties can also be modified for each product to meet individual business requirements.</span></span>

## <a name="selecting-properties-to-update-products-on-the-retail-product-hierarchy-page"></a><span data-ttu-id="988cd-123">Tulajdonságok kiválasztása a termékek frissítéséhez a Retail termékhierarchia lapról</span><span class="sxs-lookup"><span data-stu-id="988cd-123">Selecting properties to update products on the Retail product hierarchy page</span></span>

<span data-ttu-id="988cd-124">A terméktulajdonságok új, továbbfejlesztett struktúrája segítségével kiválaszthatja, melyik frissített terméktulajdonságoknak kell átkerülniük a kapcsolódó termékekbe.</span><span class="sxs-lookup"><span data-stu-id="988cd-124">You can use the new enhanced structure for product properties to select updated product properties that must be pushed to the associated products.</span></span> <span data-ttu-id="988cd-125">A **Kiskereskedelmi termékek hierarchiája** oldalon a műveleti ablaktáblában válassza a **Kategória** elemet, majd a **Termékek frissítése** lehetőséget a **Termékek frissítése** dialógusablak megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="988cd-125">On the **Retail product hierarchy** page, on the Action Pane, select **Category**, and then select **Update products** to open the **Update products** dialog box.</span></span>

![Termékek frissítése párbeszédpanel](media/NewUpdateProductsEnhancedView.PNG)


