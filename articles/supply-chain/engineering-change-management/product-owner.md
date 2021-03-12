---
title: Terméktulajdonosok
description: Ez a témakör a terméktulajdonosokkal kapcsolatban tartalmaz tájékoztatást. A terméktulajdonos olyan felhasználók csoportja, akik bizonyos termékekért felelősek. Csak a csoport tagjai adhatják ki ezeket a termékeket. A terméktulajdonos használható a jóváhagyási munkafolyamatban is.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgProductOwner
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 90f5596f9b5fc45e78cc49a3309c45864e07e70b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967333"
---
# <a name="product-owners"></a><span data-ttu-id="1dbfb-106">Terméktulajdonosok</span><span class="sxs-lookup"><span data-stu-id="1dbfb-106">Product owners</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1dbfb-107">A terméktulajdonos olyan felhasználók csoportja, akik bizonyos termékekért felelősek.</span><span class="sxs-lookup"><span data-stu-id="1dbfb-107">The product owner is a group of users who are responsible for specific products.</span></span> <span data-ttu-id="1dbfb-108">Ha egy terméktulajdonos egy termékhez van hozzárendelve, akkor csak a csoport tagjai adhatják ki a terméket.</span><span class="sxs-lookup"><span data-stu-id="1dbfb-108">When a product owner group is assigned to a product, only the members of that group can release the product.</span></span> <span data-ttu-id="1dbfb-109">A terméktulajdonos használható a jóváhagyási munkafolyamatban is a mérnöki változáskezelésben.</span><span class="sxs-lookup"><span data-stu-id="1dbfb-109">The product owner can also be used in the approval workflow in engineering change management.</span></span>

<span data-ttu-id="1dbfb-110">A terméktulajdonosok globális beállítások.</span><span class="sxs-lookup"><span data-stu-id="1dbfb-110">Product owners are global settings.</span></span> <span data-ttu-id="1dbfb-111">Ennélfogva valamennyi jogi személy számára elérhetők.</span><span class="sxs-lookup"><span data-stu-id="1dbfb-111">Therefore, they are available to all legal entities.</span></span>

## <a name="create-a-product-owner-group"></a><span data-ttu-id="1dbfb-112">Terméktulajdonos csoport létrehozása</span><span class="sxs-lookup"><span data-stu-id="1dbfb-112">Create a product owner group</span></span>

<span data-ttu-id="1dbfb-113">A következő lépések végrehajtásával létrehozhatja a terméktulajdonos csoportját, és tagokat adhat hozzá.</span><span class="sxs-lookup"><span data-stu-id="1dbfb-113">To create a product owner group and add members to it, follow these steps.</span></span>

1. <span data-ttu-id="1dbfb-114">Lépjen a **Mérnöki változtatások kezelése – \> Beállítás \> Terméktulajdonosok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1dbfb-114">Go to **Engineering change management \> Setup \> Product owners**.</span></span>
2. <span data-ttu-id="1dbfb-115">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="1dbfb-115">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="1dbfb-116">A **terméktulajdonos** mezőbe írja a csoport nevét.</span><span class="sxs-lookup"><span data-stu-id="1dbfb-116">In the **Product owner** field, enter a name for the group.</span></span>
4. <span data-ttu-id="1dbfb-117">A **Név** mezőbe írja be a csoport rövid leírását.</span><span class="sxs-lookup"><span data-stu-id="1dbfb-117">In the **Name** field, enter a description of the group.</span></span>
5. <span data-ttu-id="1dbfb-118">A **Tagok** gyorslapon adja meg azokat a dolgozókat, akik tagjai a csoportnak.</span><span class="sxs-lookup"><span data-stu-id="1dbfb-118">On the **Members** FastTab, add the workers who should be members of the group.</span></span>

## <a name="assign-a-product-owner-to-a-product"></a><span data-ttu-id="1dbfb-119">Terméktulajdonos hozzárendelése termékhez</span><span class="sxs-lookup"><span data-stu-id="1dbfb-119">Assign a product owner to a product</span></span>

<span data-ttu-id="1dbfb-120">A terméktulajdonos hozzárendeléséhez egy termékhez, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1dbfb-120">To assign a product owner to a product, follow these steps.</span></span>

1. <span data-ttu-id="1dbfb-121">Nyissa meg a megfelelő termék vagy alaptermék **Termékadatok** oldalát.</span><span class="sxs-lookup"><span data-stu-id="1dbfb-121">Open the **Product details** page for the relevant product or product master.</span></span>
1. <span data-ttu-id="1dbfb-122">Az **Általános** gyorslapon állítsa a **Terméktulajdonos** mezőt a megfelelő terméktulajdonosi csoport nevére.</span><span class="sxs-lookup"><span data-stu-id="1dbfb-122">On the **General** FastTab, set the **Product owner** field to the name of the relevant product owner group.</span></span>

<span data-ttu-id="1dbfb-123">Noha a terméktulajdonos egy termékhez van hozzárendelve, csak a terméktulajdonosi csoport tagjai módosíthatják a **Terméktulajdonos** beállítását.</span><span class="sxs-lookup"><span data-stu-id="1dbfb-123">While a product owner is assigned to a product, only the members of the product owner group can edit the **Product owner** setting.</span></span>

<span data-ttu-id="1dbfb-124">A terméktulajdonos a **Kiadott termékek** oldalon is látható.</span><span class="sxs-lookup"><span data-stu-id="1dbfb-124">The product owner is also visible on the **Released products** page.</span></span>

## <a name="product-owners-and-product-releases"></a><span data-ttu-id="1dbfb-125">A termék tulajdonosai és a termék kiadásai</span><span class="sxs-lookup"><span data-stu-id="1dbfb-125">Product owners and product releases</span></span>

<span data-ttu-id="1dbfb-126">Az adott terméket csak a termék terméktulajdonosi csoportjához tartozó felhasználók adhatják ki.</span><span class="sxs-lookup"><span data-stu-id="1dbfb-126">Only users from a product's product owner group can release that product.</span></span> <span data-ttu-id="1dbfb-127">Azonban van egy kivétel, amikor a termék alárendelt elem, és a fölérendelt elemet a fölérendelt elem tulajdonosa adja ki.</span><span class="sxs-lookup"><span data-stu-id="1dbfb-127">However, there is an exception when the product is a child item, and its parent is released by the parent's owner.</span></span> <span data-ttu-id="1dbfb-128">Más szóval, ha a termék egy másik termék anyagjegyzékének része, a rendszer nem ellenőrzi az anyagjegyzékben szereplő minden egyes cikk terméktulajdonosát.</span><span class="sxs-lookup"><span data-stu-id="1dbfb-128">In other words, if the product is part of the BOM of another product, the system doesn't check the product owner of each item in the BOM.</span></span> <span data-ttu-id="1dbfb-129">Csak a fölérendelt cikk terméktulajdonosát ellenőrzi.</span><span class="sxs-lookup"><span data-stu-id="1dbfb-129">It checks only the product owner of the parent item.</span></span>

<span data-ttu-id="1dbfb-130">Az X termék például a *Design kabinetek* terméktulajdonosi csoportjához vannak hozzárendelve.</span><span class="sxs-lookup"><span data-stu-id="1dbfb-130">For example, product X is assigned to the *Design cabinets* product owner group.</span></span> <span data-ttu-id="1dbfb-131">Az X termék az Y termék AJ része is, amely a *Design hangszórók* terméktulajdonosi csoportjához van hozzárendelve.</span><span class="sxs-lookup"><span data-stu-id="1dbfb-131">Product X is also part of the BOM of product Y, which is assigned to the *Design Speakers* product owner group.</span></span> <span data-ttu-id="1dbfb-132">Ha egy felhasználó a *Design hangszórók* terméktulajdonosi csoporttól kiadja az Y terméket és annak anyagjegyzékét, akkor az X termék az Y termékkel együtt fog megjelenni.</span><span class="sxs-lookup"><span data-stu-id="1dbfb-132">If a user from the *Design Speakers* product owner group releases product Y and its BOM, product X will be released together with product Y.</span></span>

## <a name="product-owners-and-approvals"></a><span data-ttu-id="1dbfb-133">Terméktulajdonosok és jóváhagyások</span><span class="sxs-lookup"><span data-stu-id="1dbfb-133">Product owners and approvals</span></span>

<span data-ttu-id="1dbfb-134">Mivel a terméktulajdonosok tudják, hogy az egyes mérnöki módosítások előnyösek-e termékeik számára, gyakran érdemes ezeket belefoglalni a mérnöki változáskezelés modul jóváhagyási folyamatának részeként.</span><span class="sxs-lookup"><span data-stu-id="1dbfb-134">Because product owners know whether specific engineering changes will benefit their products, it often makes sense to include them as part of the approval process in engineering change management.</span></span> <span data-ttu-id="1dbfb-135">Ezt a módszert úgy hajthatja végre, hogy a termék tulajdonosait a mérnöki változtatások kezeléséhez használt munkafolyamatokban résztvevő szolgáltatókként állítja be.</span><span class="sxs-lookup"><span data-stu-id="1dbfb-135">You can implement this approach by setting up the product owners as participant providers in the workflows that are used for engineering change management.</span></span> <span data-ttu-id="1dbfb-136">A rendszer ezután a munkafolyamatokban hozzárendeli a jóváhagyási feladatokat a mérnöki módosítási kérelmekben és a mérnöki módosítási rendelésekben szereplő termékek alapján.</span><span class="sxs-lookup"><span data-stu-id="1dbfb-136">The system will then assign approval tasks in the workflows, based on the products that are in engineering change requests and engineering change orders.</span></span> <span data-ttu-id="1dbfb-137">További tájékoztatást [A mérnöki termékek módosításának kezelése](engineering-change-management.md) részben talál.</span><span class="sxs-lookup"><span data-stu-id="1dbfb-137">For more information, see [Manage changes to engineering products](engineering-change-management.md).</span></span>
