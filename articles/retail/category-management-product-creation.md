---
title: "Termékkategóriák kezelése és létrehozása"
description: "Ez a témakör leírja a fejlesztéseket, amelyek már megtörténtek a kiskereskedelmi termékek kategóriák kezelésére nézve. A fejlesztések segítségével a termékkihelyezési vezetők megtekinthetik a kiskereskedelmi termékek hierarchiája és a megjelent termékrészletek közötti korrelációt."
author: ashishmsft
manager: AnnBe
ms.date: 09/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Core, Retail
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 98250062892e0c5f665616dc3944181a3ff8599a
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="product-category-management-and-creation"></a><span data-ttu-id="fb60c-104">Termékkategóriák kezelése és létrehozása</span><span class="sxs-lookup"><span data-stu-id="fb60c-104">Product category management and creation</span></span>

[!include[banner](./includes/banner.md)]

<span data-ttu-id="fb60c-105">A fejlesztések segítségével, amelyek megtörténtek a kiskereskedelmi termékek kategóriák kezelésére nézve, a termékkihelyezési vezetők megtekinthetik a kiskereskedelmi termékek hierarchiája és a megjelent termékrészletek közötti korrelációt.</span><span class="sxs-lookup"><span data-stu-id="fb60c-105">Enhancements that have been made to the management experience for Retail product categories let merchandising managers have a correlation between Retail product hierarchy and released product details.</span></span> <span data-ttu-id="fb60c-106">A fejlesztések megtekintéséhez a **Kategória és termék kezelése** munkaterületen válassza ki a **Kiskereskedelmi termékek hierarchiája** elemet a **Kiskereskedelmi termékkategória új szerkezete** lap megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="fb60c-106">To view these enhancements, in the **Category & product management**  workspace, select **Retail product hierarchy** to open the **New structure of Retail product category** page.</span></span> 

<span data-ttu-id="fb60c-107">A korábbi kiadásokban a terméktulajdonságok alapvető terméktulajdonságokra és kiskereskedelmi termék tulajdonságaira lettek felosztva, az alkalmazási hatókör alapján.</span><span class="sxs-lookup"><span data-stu-id="fb60c-107">In previous releases, product properties were divided into Basic product properties and Retail product properties, based on the scope of their applicability.</span></span> <span data-ttu-id="fb60c-108">Kiskereskedelmi termék tulajdonságai *globálisak* voltak.</span><span class="sxs-lookup"><span data-stu-id="fb60c-108">Retail product properties were *global*.</span></span> <span data-ttu-id="fb60c-109">Másként megfogalmazva ez azt jelenti, hogy egy adott terméktulajdonság esetében ugyanaz az érték van megosztva minden jogi személy esetében.</span><span class="sxs-lookup"><span data-stu-id="fb60c-109">In other words, for a given product property, the same value is shared across all legal entities.</span></span> <span data-ttu-id="fb60c-110">Az alapvető terméktulajdonságok *jogi személy specifikusak* voltak.</span><span class="sxs-lookup"><span data-stu-id="fb60c-110">Basic product properties were *legal entity–specific*.</span></span> <span data-ttu-id="fb60c-111">Ez azt jelenti, hogy egy adott terméktulajdonság eltérő lehet a jogi személyek esetében az egyedi üzleti igények alapján.</span><span class="sxs-lookup"><span data-stu-id="fb60c-111">In other words, a given product property might differ across legal entities, based on individual business requirements.</span></span>

<span data-ttu-id="fb60c-112">Ezekkel a fejlesztésekkel a kiskereskedelmi termékkategória terméktulajdonságai esetében továbbra is elválasztjuk a mezőket a csoporton belül alkalmazhatóság alapján a megjelent termék részletei képernyőstruktúrájának megfelelően.</span><span class="sxs-lookup"><span data-stu-id="fb60c-112">With these enhancements, for product properties in the Retail product category, we continue to separate the fields, based on their applicability within a group, to reflect the released product details form structure.</span></span>

<span data-ttu-id="fb60c-113">Válthat aközött, hogy a jogi személyhez megadott tulajdonságokat az összes a jogi személyre nézve, vagy egy meghatározott jogi személyre nézve kezeli.</span><span class="sxs-lookup"><span data-stu-id="fb60c-113">You can switch between managing legal-entity specific properties across all legal entities and managing them for a specific legal entity.</span></span> <span data-ttu-id="fb60c-114">Ehhez egyszerűen válassza a **Megjelenítés/szerkesztés minden jogi személyre** vagy a **Megjelenítés/szerkesztés egy meghatározott jogi személyre** lehetőségek közül a megfelelőt.</span><span class="sxs-lookup"><span data-stu-id="fb60c-114">Just select **View/Edit for all legal entities** or **View/Edit for a specific legal entity** as you require.</span></span>

<span data-ttu-id="fb60c-115">A termékkihelyezési vezetők emellett alapértelmezett értékeket határozhatnak meg terméktulajdonságok egy további halmazához az adott kategória szintjén.</span><span class="sxs-lookup"><span data-stu-id="fb60c-115">Merchandising managers can also define default values for an additional set of product properties at the level of an individual category.</span></span> <span data-ttu-id="fb60c-116">Ezeket a tulajdonságértékeket öröklik a termékek a termék létrehozásakor érvényes kategóriatársításuk alapján.</span><span class="sxs-lookup"><span data-stu-id="fb60c-116">These property values are inherited by a product, based on their association with a category at the time of product creation.</span></span>

## <a name="select-properties-to-update-products-from-the-retail-product-category-form"></a><span data-ttu-id="fb60c-117">Jelölje ki a tulajdonságokat a termékek frissítéséhez a kiskereskedelmi termékkategória űrlapról</span><span class="sxs-lookup"><span data-stu-id="fb60c-117">Select properties to update products from the Retail product category form</span></span>

<span data-ttu-id="fb60c-118">Logikai csoportosítási tulajdonságok segítségével válassza ki, melyik frissített terméktulajdonságokat kell leküldeni a kapcsolódó termékekbe.</span><span class="sxs-lookup"><span data-stu-id="fb60c-118">You can use logical grouping properties to select which updated product properties should be pushed to associated products.</span></span>

<span data-ttu-id="fb60c-119">A termékkihelyezési vezetők módosíthatják ezeket az örökölt terméktulajdonságokat az egyes termékekhez, az egyedi üzleti követelményeknek megfelelően.</span><span class="sxs-lookup"><span data-stu-id="fb60c-119">Merchandising managers can modify these inherited product properties for each product, to meet individual business requirements.</span></span>

