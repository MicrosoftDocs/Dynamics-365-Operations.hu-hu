---
title: Kiskereskedelmi termékek beállítása
description: Ez a cikk ismerteti kiskereskedelmi termékek beállítását a Dynamics 365 Commerce rendszerben.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailProductAndCategoryWorkspace, EcoResProductDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: e8f624f5feb8ee8f641a9b35ae31bdfe38e5e0ce
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022793"
---
# <a name="set-up-retail-products"></a><span data-ttu-id="42171-103">Retail termékek beállítása</span><span class="sxs-lookup"><span data-stu-id="42171-103">Set up retail products</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="42171-104">Ez a cikk ismerteti a termékek beállítását a Dynamics 365 Commerce rendszerben.</span><span class="sxs-lookup"><span data-stu-id="42171-104">This article describes how to set up products in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="42171-105">Mielőtt kiskereskedelmi értékesítésre kínálna termékeket kereskedelmi csatornái révén, létre kell hoznia és konfigurálnia kell azokat a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="42171-105">Before you can offer products for resale in your commerce channels, you must create and configure the products.</span></span> <span data-ttu-id="42171-106">A Commerce egész szervezetre érvényes termékeket hoz létre az alaptermékben.</span><span class="sxs-lookup"><span data-stu-id="42171-106">Commerce creates organization-wide products in the product master.</span></span> <span data-ttu-id="42171-107">Létrehozhat termékeket, meghatározhatja a terméktulajdonságokat és -attribútumokat, valamint hozzárendelheti a termékeket különböző kereskedelmi hierarchiákhoz.</span><span class="sxs-lookup"><span data-stu-id="42171-107">You can create the products, define the product properties and attributes, and assign the products to commerce category hierarchies.</span></span> <span data-ttu-id="42171-108">Ahhoz, hogy a termék elérhetővé váljon a csatornák számára, valamint hogy felvehesse azokat az aktív szortimentbe, ki kell adnia a termékeket azoknak a jogi személyeknek, amelyekben azok rendelkezésre állnak.</span><span class="sxs-lookup"><span data-stu-id="42171-108">To make the products available to your channels and add them to an active assortment, you must release the products to the legal entities where they are available.</span></span> <span data-ttu-id="42171-109">A csatornák használatával értékesített termékek beállításához hajtsa végre a következő feladatokat.</span><span class="sxs-lookup"><span data-stu-id="42171-109">To set up the products that you sell by using channels, complete the following tasks.</span></span>

1. <span data-ttu-id="42171-110">**Határozzon meg termékhierarchiát.**</span><span class="sxs-lookup"><span data-stu-id="42171-110">**Define a product hierarchy.**</span></span> <span data-ttu-id="42171-111">A Commerce rendszerben a kategóriahierarchia funkciók segítségével meghatározhatja a hierarchiákat a termékek csoportosításához és kategorizálásához, amelyeket a kiskereskedelmi csatornáin keresztül forgalmaz.</span><span class="sxs-lookup"><span data-stu-id="42171-111">By using the category hierarchy features in Commerce, you can define category hierarchies to group and categorize the products that you distribute to your channels.</span></span> <span data-ttu-id="42171-112">A felhasználó által definiált és rendszerattribútumokat a kategória szintjén lehet megadni.</span><span class="sxs-lookup"><span data-stu-id="42171-112">User-defined and system attributes can be defined at the category level.</span></span> <span data-ttu-id="42171-113">Ezt követően a kategóriához rendelt összes termék örökli azokat az attribútumokat.</span><span class="sxs-lookup"><span data-stu-id="42171-113">Then, all products that are assigned to the category inherit those attributes.</span></span> <span data-ttu-id="42171-114">Több kategóriahierarchiát is meg lehet adni, és az egyes termékeket több hierarchiához is hozzárendelheti.</span><span class="sxs-lookup"><span data-stu-id="42171-114">Multiple category hierarchies can be defined, and each product can be assigned to multiple hierarchies.</span></span> <span data-ttu-id="42171-115">Azonban egy hierarchiában az egyes termékek csak egy kategóriához rendelhetők hozzá.</span><span class="sxs-lookup"><span data-stu-id="42171-115">However, in a single hierarchy, each product can be assigned to only one category.</span></span>
2. <span data-ttu-id="42171-116">**Termékek és termékvariációk hozzáadása az alaptermékhez.**</span><span class="sxs-lookup"><span data-stu-id="42171-116">**Add products and product variants to the product master.**</span></span> <span data-ttu-id="42171-117">A termékek, amelyek alaptermékhez vannak hozzáadva, a globális termékek listáját képviselik.</span><span class="sxs-lookup"><span data-stu-id="42171-117">Products that are added to the product master represent a global list of products.</span></span> <span data-ttu-id="42171-118">Termékeket manuálisan is hozzá lehet adni, egyesével, vagy importálhatja a termékadatokat a szállítóktól.</span><span class="sxs-lookup"><span data-stu-id="42171-118">You can add products manually, one at a time, or you can import product data from your vendors.</span></span>
3. <span data-ttu-id="42171-119">**Termékek kiadása jogi személynek**</span><span class="sxs-lookup"><span data-stu-id="42171-119">**Release the products to legal entities.**</span></span> <span data-ttu-id="42171-120">Csak a jogi személyek számára kiadott termékek bocsáthatók rendelkezésre az Ön csatornái számára.</span><span class="sxs-lookup"><span data-stu-id="42171-120">Only products that have been released to legal entities can be made available to your channels.</span></span> <span data-ttu-id="42171-121">Amikor először határoz meg egy terméket, azt a szervezeti szinten teszi.</span><span class="sxs-lookup"><span data-stu-id="42171-121">When you first define a product, you define it on an organization-wide level.</span></span> <span data-ttu-id="42171-122">Ezután kiválaszthat egy vagy több jogi személyt, akiknek kiadja a terméket.</span><span class="sxs-lookup"><span data-stu-id="42171-122">You can then select one or more legal entities to release the product to.</span></span> <span data-ttu-id="42171-123">A termék ekkor elérhetővé válik több csatorna számára a szervezeten belül.</span><span class="sxs-lookup"><span data-stu-id="42171-123">The product then becomes available to multiple channels across your organization.</span></span> <span data-ttu-id="42171-124">A funkció segítségével lehetséges a termék egyszeri létrehozása, termékattribútumok és tulajdonságok hozzáadása és frissítése egy helyen, a termék szervezeten belüli elosztása a csatornákban, ahol az nem áll rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="42171-124">You can use this functionality to create a product one time, add and update product attributes and properties in one place, and then distribute the product across your organization, to the channels where it's available.</span></span>
4. <span data-ttu-id="42171-125">**Termékek hozzáadása szortimentekhez.**</span><span class="sxs-lookup"><span data-stu-id="42171-125">**Add products to assortments.**</span></span> <span data-ttu-id="42171-126">Egy szortiment felel egy csatornákban kínált termékkollekciónak.</span><span class="sxs-lookup"><span data-stu-id="42171-126">An assortment represents a collection of products that you offer in your channels.</span></span> <span data-ttu-id="42171-127">Megadhat egy vagy több szortimentet, és minden termék egy vagy több szortimenthez rendelhető hozzá.</span><span class="sxs-lookup"><span data-stu-id="42171-127">You can define one or more assortments, and each product can be assigned to one or more assortments.</span></span> <span data-ttu-id="42171-128">Termékek csatornákhoz való hozzárendeléséhez a szortimenteket hozzá kell rendelni a csatornákhoz.</span><span class="sxs-lookup"><span data-stu-id="42171-128">To assign products to channels, you assign the assortments to those channels.</span></span> <span data-ttu-id="42171-129">Ha létrehoz egy szortimentet, hozzáadhat termékeket, ha azokat még nem adták ki jogi személynek.</span><span class="sxs-lookup"><span data-stu-id="42171-129">When you create an assortment, you can add products that haven't yet been released to a legal entity.</span></span> <span data-ttu-id="42171-130">Mielőtt azonban a termékeket a csatornák számára elérhetővé teheti, ki kell adnia őket egy jogi személy számára.</span><span class="sxs-lookup"><span data-stu-id="42171-130">However, you must release the products to a legal entity before those products can be made available to the channels.</span></span>
5. <span data-ttu-id="42171-131">**Termékek hozzáadása a navigációs hierarchiákhoz.**</span><span class="sxs-lookup"><span data-stu-id="42171-131">**Add products to navigation hierarchies.**</span></span> <span data-ttu-id="42171-132">Termékeket a Commerce navigációs hierarchiájában kategorizálni kell, hogy azok tallózhatók legyenek online vagy egy pénztárnál (POS).</span><span class="sxs-lookup"><span data-stu-id="42171-132">Before products can be browsed online or in point of sale (POS), they must be categorized in a Commerce navigation hierarchy.</span></span>
6. <span data-ttu-id="42171-133">**Termékek hozzáadása a katalógusokhoz.**</span><span class="sxs-lookup"><span data-stu-id="42171-133">**Add products to catalogs.**</span></span> <span data-ttu-id="42171-134">Annak ellenére, hogy ez a lépés nem kötelező a POS-hez, az online áruház esetében szükséges, hogy a termékek szerepeljenek legalább egy katalógusban.</span><span class="sxs-lookup"><span data-stu-id="42171-134">Although this step is optional for POS, online stores require that products be included in at least one catalog.</span></span>