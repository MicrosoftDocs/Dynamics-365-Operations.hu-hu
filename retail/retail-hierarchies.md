---
title: "Kiskereskedelmi hierarchiák"
description: "Ez a cikk a Microsoft Dynamics 365 for Retail kiskereskedelmi hierarchiáit írja le."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 15851
ms.assetid: dfa11d41-2a0c-4cde-99b6-058c49176c94
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 817696566473bc5f31a7ff11c04291351dfd4764
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---

# <a name="retail-hierarchies"></a><span data-ttu-id="c170a-103">Kiskereskedelmi hierarchiák</span><span class="sxs-lookup"><span data-stu-id="c170a-103">Retail hierarchies</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="c170a-104">Ez a cikk a Microsoft Dynamics 365 for Retail kiskereskedelmi hierarchiáit írja le.</span><span class="sxs-lookup"><span data-stu-id="c170a-104">This article describes retail hierarchies in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="c170a-105">A kiskereskedelmi csatornáin keresztül értékesített termékek rendszerezéséhez létrehozhatja a termékeket hierarchiáját.</span><span class="sxs-lookup"><span data-stu-id="c170a-105">You can create a retail category hierarchy to organize the products that you sell through your retail channels.</span></span> <span data-ttu-id="c170a-106">Kiskereskedelmi termék hierarchiák segítségével kategóriákba vagy termékek csoportosítása.</span><span class="sxs-lookup"><span data-stu-id="c170a-106">You can use retail product hierarchies to categorize or group products.</span></span> <span data-ttu-id="c170a-107">Ezeket a termékeket, valamint a vevő hűségprogramok létrehozásához használhatja.</span><span class="sxs-lookup"><span data-stu-id="c170a-107">You can then use these products to create product assortments and customer loyalty programs.</span></span> <span data-ttu-id="c170a-108">Kiválaszthatja is termékattribútumok és tulajdonságok hozzárendelése, hozzárendelése egy árképzési szerkezet, a termékek felvétele a termék promóciók, és a termékeket jelentésekhez használja.</span><span class="sxs-lookup"><span data-stu-id="c170a-108">You can also assign product attributes and properties, assign a pricing structure, include the products in product promotions, and use the products for reporting.</span></span> <span data-ttu-id="c170a-109">Létrehozhat egy kategóriahierarchiát a szervezetben lévő összes termék és kategória képviseletére, majd ezt a kategóriahierarchiát több célra használhatja.</span><span class="sxs-lookup"><span data-stu-id="c170a-109">You can create one retail category hierarchy to represent all the products and categories in your organization, and then use that category hierarchy for multiple purposes.</span></span> <span data-ttu-id="c170a-110">Másik lehetőségként létrehozhat több kategóriahierarchiát különleges célokra, ilyen például a termékpromóció.</span><span class="sxs-lookup"><span data-stu-id="c170a-110">Alternatively, you can create multiple retail category hierarchies for special purposes, such as product promotions.</span></span> <span data-ttu-id="c170a-111">Kiskereskedelmi termékhierarchia létrehozásakor hozzá kell rendelnie a kategóriahierarchia típusát a kategóriahierarchia céljának azonosításához.</span><span class="sxs-lookup"><span data-stu-id="c170a-111">When you create a retail product hierarchy, you must assign a category hierarchy type to identify the purpose of the category hierarchy.</span></span> <span data-ttu-id="c170a-112">Például egyetlen termék hierarchiák értékcsökkenésével a **Kiskereskedelmi navigációs hierarchia** típus hivatkozott tallózásakor termékek kategóriák szerint online, akár in point of értékesítés (POS).</span><span class="sxs-lookup"><span data-stu-id="c170a-112">For example, only product hierarchies that are assigned the **Retail navigation hierarchy** type are referenced when you browse products by category online or in point of sale (POS).</span></span>

## <a name="retail-hierarchy-types"></a><span data-ttu-id="c170a-113">A kiskereskedelmi hierarchia képernyői</span><span class="sxs-lookup"><span data-stu-id="c170a-113">Retail hierarchy types</span></span>
<span data-ttu-id="c170a-114">Az alábbi táblázat felsorolja a választható kategóriahierarchia-típusokat és azok céljait.</span><span class="sxs-lookup"><span data-stu-id="c170a-114">The following table lists the types of retail category hierarchies that are available and the general purpose of each type.</span></span>

| <span data-ttu-id="c170a-115">Kategóriahierarchia-típus</span><span class="sxs-lookup"><span data-stu-id="c170a-115">Category hierarchy type</span></span>       | <span data-ttu-id="c170a-116">Cél</span><span class="sxs-lookup"><span data-stu-id="c170a-116">Purpose</span></span>                                                                                                                                                                                                                                                                                                            |
|-------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="c170a-117">Kiskereskedelmi termékek hierarchiája</span><span class="sxs-lookup"><span data-stu-id="c170a-117">Retail product hierarchy</span></span>      | <span data-ttu-id="c170a-118">Válassza ezt a hierarchiatípust a szervezet fő kiskereskedelmi termékhierarchiájának létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="c170a-118">Use this hierarchy type to define the overall product hierarchy for your organization.</span></span> <span data-ttu-id="c170a-119">Ezt a hierarchiatípust árusítási, árképzési és promóciók, jelentések és a szortiment tervezési használható.</span><span class="sxs-lookup"><span data-stu-id="c170a-119">You can use this hierarchy type for merchandising, pricing and promotions, reporting, and assortment planning.</span></span> <span data-ttu-id="c170a-120">Csak egy kiskereskedelmi termékek hierarchiájának ezt a hierarchiatípust is hozzárendelhető.</span><span class="sxs-lookup"><span data-stu-id="c170a-120">Only one retail product hierarchy can be assigned this hierarchy type.</span></span>                                       |
| <span data-ttu-id="c170a-121">Kiegészítő kiskereskedelmi hierarchia</span><span class="sxs-lookup"><span data-stu-id="c170a-121">Supplemental retail hierarchy</span></span> | <span data-ttu-id="c170a-122">Ez a hierarchia típus használható a létrehozni kívánt kiegészítő kiskereskedelmi kategória hierarchiákhoz.</span><span class="sxs-lookup"><span data-stu-id="c170a-122">Use this hierarchy type for any additional retail category hierarchies that you want to create.</span></span> <span data-ttu-id="c170a-123">Ha például a forrás, a akkor fürdőruha a promócióban.</span><span class="sxs-lookup"><span data-stu-id="c170a-123">For example, in the spring, you have a promotion for swimwear.</span></span> <span data-ttu-id="c170a-124">Emiatt a fürdőruha termékek felvétele külön kategóriahierarchia és alkalmazni lehet különböző termékkategóriákat az Akciós árak.</span><span class="sxs-lookup"><span data-stu-id="c170a-124">Therefore, you include your swimwear products in a separate category hierarchy and apply the promotional pricing to the various product categories.</span></span> |
| <span data-ttu-id="c170a-125">Kiskereskedelmi csatornák navigációs hierarchiája</span><span class="sxs-lookup"><span data-stu-id="c170a-125">Retail navigation hierarchy</span></span>   | <span data-ttu-id="c170a-126">Használja ezt a hierarchiatípust csoportosítására és rendszerezésére szolgálnak a termékek kategóriákba úgy, hogy a termékek interneten vagy a POS böngészhetnek.</span><span class="sxs-lookup"><span data-stu-id="c170a-126">Use this hierarchy type to group and organize products into categories so that the products can be browsed online or in POS.</span></span>                                                                                                                                                                                       |

<span data-ttu-id="c170a-127">Egy kiskereskedelmi kategóriahierarchiát a termékek rendszerezik segítségével állítsa be, és termékattribútumok és a kategória szintjén tulajdonságainak karbantartása.</span><span class="sxs-lookup"><span data-stu-id="c170a-127">By using a retail category hierarchy to structure your products, you can set up and maintain product attributes and properties at the category level.</span></span> <span data-ttu-id="c170a-128">Ezek attribútumok tulajdonságainak tartalmaznak cikkdimenziókhoz és POS beállításait.</span><span class="sxs-lookup"><span data-stu-id="c170a-128">These attributes and properties include settings for product dimensions and POS settings.</span></span> <span data-ttu-id="c170a-129">E terméket rendelt kategóriákat automatikusan öröklik az attribútumok és tulajdonságai, hogy mi.</span><span class="sxs-lookup"><span data-stu-id="c170a-129">Any products that you assign to the categories automatically inherit the attributes and properties that you define.</span></span> <span data-ttu-id="c170a-130">A kijelölt kategóriába tartozó termékek több egyszerre is másolhatja egyetlen termékhez sem beállításait.</span><span class="sxs-lookup"><span data-stu-id="c170a-130">You can also copy the property settings for any product to multiple products in a selected category at the same time.</span></span>




