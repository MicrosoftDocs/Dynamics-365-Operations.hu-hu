---
title: "Termékkategóriák kezelése"
description: "Ez a témakör leírja, hogy a termékkihelyezési vezetők hogyan használhatják a Retail termékkategóriákat a Retail termékhierarchia és a kiadott termék részletei közötti kapcsolatok kezeléséhez."
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
ms.sourcegitcommit: 25fa39dc81fc721d7593a25a102ce47041ebc5f0
ms.openlocfilehash: 4b7ef962b777a31e1da238a8ec1be9a42ec5bb5f
ms.contentlocale: hu-hu
ms.lasthandoff: 03/13/2018

---


# <a name="enhanced-product-and-category-management"></a><span data-ttu-id="38683-103">Továbbfejlesztett kategória- és termékkezelés</span><span class="sxs-lookup"><span data-stu-id="38683-103">Enhanced product and category management</span></span>

[!include[banner](./includes/banner.md)]

<span data-ttu-id="38683-104">Ez a témakör a Retail termékkategóriák és termékek kezelésének továbbfejlesztett módját mutatja be a Dynamics 365 for Retail alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="38683-104">This topic describes an enhanced way to manage Retail product categories and products in Dynamics 365 for Retail.</span></span> <span data-ttu-id="38683-105">A fejlesztések segítségével a termékkihelyezési vezetők megtekinthetik a Retail termékek hierarchiája és a kiadott termékrészletek közös terméktulajdonság-struktúráját.</span><span class="sxs-lookup"><span data-stu-id="38683-105">These enhancements let merchandising managers view a common structure of product properties between Retail product hierarchy and released product details.</span></span>

<span data-ttu-id="38683-106">A Retail termékkategóriák kezelésével kapcsolatos további tudnivalókért kattintson a **Kiskereskedelmi termékek hierarchiája** elemre a **Kategória és termék kezelése** munkaterületen, és tekintse meg a **Kiskereskedelmi termékkategória** lap továbbfejlesztett szerkezetét.</span><span class="sxs-lookup"><span data-stu-id="38683-106">To learn more about managing Retail product categories, go to **Retail product hierarchy** from the **Category and product management** workspace, and note the enhanced structure of the **Retail product category** page.</span></span>

![Kategória és termék kezelése munkaterület](media/LaunchRetailProductHierarchy.png)

<span data-ttu-id="38683-108">A korábbi verziókban a terméktulajdonságok **alapvető terméktulajdonságokra** és **kiskereskedelmi termék tulajdonságaira** lettek felosztva, az alkalmazási hatókör alapján.</span><span class="sxs-lookup"><span data-stu-id="38683-108">In previous versions, product properties were divided into **Basic product properties** and **Retail product properties**, based on the scope of their applicability.</span></span> <span data-ttu-id="38683-109">A **kiskereskedelmi termék tulajdonságai** *globálisak* voltak az alkalmazás terjedelmét tekintve, ami azt jelenti, hogy egy adott **kiskereskedelmi termék tulajdonság** esetében ugyanazt az értéket mutatja az összes jogi személy.</span><span class="sxs-lookup"><span data-stu-id="38683-109">**Retail product properties** were *global* by scope of applicability, which means that for a given **Retail product property**, the same value is shared across all legal entities.</span></span> <span data-ttu-id="38683-110">Az **alapvető terméktulajdonságok** *jogi személy specifikusak* voltak.</span><span class="sxs-lookup"><span data-stu-id="38683-110">**Basic product properties** are *legal entity specific*.</span></span> <span data-ttu-id="38683-111">Ez azt jelenti, hogy egy adott **alapvető terméktulajdonság** értéke eltérő lehet a jogi személyek esetében az egyedi üzleti igények alapján.</span><span class="sxs-lookup"><span data-stu-id="38683-111">In other words, for a given **Basic product property** the value can differ across legal entities, based on individual business requirements.</span></span>

<span data-ttu-id="38683-112">A továbbfejlesztett Retail termékkategória struktúrában a terméktulajdonságok logikailag el vannak választva a csoporton belüli alkalmazhatóság alapján a megjelent termék részletei képernyőstruktúrájának megfelelően.</span><span class="sxs-lookup"><span data-stu-id="38683-112">In the enhanced Retail product category structure, product properties are logically separated based on their applicability within a group, to reflect the released product details form structure.</span></span>

![Mezők csoportosítása az alkalmazásuk terjedelme alapján](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

<span data-ttu-id="38683-114">Válthat aközött, hogy a jogi személyhez megadott tulajdonságokat az összes a jogi személyre nézve, vagy egy meghatározott jogi személyre nézve kezeli.</span><span class="sxs-lookup"><span data-stu-id="38683-114">You can switch between managing legal-entity specific properties across all legal entities and managing them for a specific legal entity.</span></span> <span data-ttu-id="38683-115">Ehhez válassza a **Megjelenítés/szerkesztés minden jogi személyre** vagy a **Megjelenítés/szerkesztés egy meghatározott jogi személyre** lehetőségek egyikét.</span><span class="sxs-lookup"><span data-stu-id="38683-115">To do this, select either **View/Edit for all legal entities** or **View/Edit for a specific legal entity**.</span></span>

![Nézetváltás az egyén és jogi személyek között](media/ToggleBackToEditForSpecificLegalEntity.PNG)

![Nézetváltás az egyén és jogi személyek között](media/ToggleToEditForAllLegalEntities.PNG)  

<span data-ttu-id="38683-118">Összehasonlítva a korábbi verziókkal, az új Retail termékkategória-szerkezetben a termékkihelyezési vezető meghatározhat egy alapértelmezett értéket a terméktulajdonságok egy további csoportjához egy egyéni kategória szintjén.</span><span class="sxs-lookup"><span data-stu-id="38683-118">Compared to previous versions, in the new Retail product category structure a merchandising manager can also define default values for an additional set of product properties at an individual category level.</span></span> <span data-ttu-id="38683-119">A termék létrehozása során ezeket az alapértelmezett terméktulajdonság értékeket örökli egy termék, egy egyedi kategóriával való társításuk alapján a Retail termékhierarchiájából.</span><span class="sxs-lookup"><span data-stu-id="38683-119">At the time of product creation, these default product property values are inherited by a product, based on their association with an individual category from Retail product hierarchy.</span></span> <span data-ttu-id="38683-120">A termékkihelyezési vezetők módosíthatják is ezeket az örökölt terméktulajdonságokat az egyes termékekhez, az egyedi üzleti követelményeknek megfelelően.</span><span class="sxs-lookup"><span data-stu-id="38683-120">These inherited product properties can also be modified for each product, to meet individual business requirements.</span></span>

## <a name="select-properties-to-update-products-from-the-retail-product-category-form"></a><span data-ttu-id="38683-121">Jelölje ki a tulajdonságokat a termékek frissítéséhez a kiskereskedelmi termékkategória űrlapról</span><span class="sxs-lookup"><span data-stu-id="38683-121">Select properties to update products from the Retail product category form</span></span> 
 
<span data-ttu-id="38683-122">A terméktulajdonságok új, továbbfejlesztett struktúrája segítségével kiválaszthatja, hogy melyik frissített terméktulajdonságoknak kell átkerülniük a kapcsolódó termékekbe.</span><span class="sxs-lookup"><span data-stu-id="38683-122">You can use this new enhanced structure for product properties to select which updated product properties must be pushed to associated products.</span></span> 

![Frissített termékek új, továbbfejlesztett nézete](media/NewUpdateProductsEnhancedView.PNG) 

<span data-ttu-id="38683-124">A termékkihelyezési vezetők módosíthatják ezeket az örökölt terméktulajdonságokat az egyes termékekhez, az egyedi üzleti követelményeknek megfelelően.</span><span class="sxs-lookup"><span data-stu-id="38683-124">Merchandising managers can modify these inherited product properties for each product, to meet individual business requirements.</span></span>


