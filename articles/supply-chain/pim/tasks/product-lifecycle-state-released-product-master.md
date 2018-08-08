--- 
title: "Termékéletciklus-állapot hozzárendelése egy kiadott alaptermékhez"
description: "Ez az eljárás bemutatja a termékéletciklus-állapotnak a kiadott alaptermékhez és annak változataihoz történő hozzáadását."
author: cvocph
manager: AnnBe
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: dd9d40bb331b9e024617c8be55330dfce8ba1cc6
ms.contentlocale: hu-hu
ms.lasthandoff: 08/07/2018

---
# <a name="assign-a-product-lifecycle-state-to-a-released-product-master"></a><span data-ttu-id="2b8db-103">Termékéletciklus-állapot hozzárendelése egy kiadott alaptermékhez</span><span class="sxs-lookup"><span data-stu-id="2b8db-103">Assign a product lifecycle state to a released product master</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2b8db-104">Ez az eljárás bemutatja a termékéletciklus-állapotnak a kiadott alaptermékhez és annak változataihoz történő hozzáadását.</span><span class="sxs-lookup"><span data-stu-id="2b8db-104">This procedure shows how to assign a product lifecycle state to a released product master and its variants.</span></span> <span data-ttu-id="2b8db-105">Előfeltétel: Először le kell játszania az „Új termékéletciklus-állapot létrehozása” feladat-útmutatót, hogy megbizonyosodjon arról, hogy legalább egy termékéletciklus-állapotot létrehozott a jelen feladat-útmutató lejátszása előtt.</span><span class="sxs-lookup"><span data-stu-id="2b8db-105">Prerequisite: You need to play the task guide "Create a new product lifecycle state" first to make sure that you have at least one product lifecycle state created before you can play this task guide.</span></span>


## <a name="find-a-released-product-master"></a><span data-ttu-id="2b8db-106">Keressen meg egy kiadott alapterméket</span><span class="sxs-lookup"><span data-stu-id="2b8db-106">Find a released product master</span></span>
1. <span data-ttu-id="2b8db-107">Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2b8db-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="2b8db-108">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="2b8db-108">In the list, find and select the desired record.</span></span>

> [!NOTE]
> <span data-ttu-id="2b8db-109">Az alaptermék az Alaptermék termékaltípussal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="2b8db-109">A product master has the Product subtype Product master.</span></span>  

## <a name="update-the-lifecycle-state"></a><span data-ttu-id="2b8db-110">Az életciklus-állapot frissítése</span><span class="sxs-lookup"><span data-stu-id="2b8db-110">Update the lifecycle state</span></span>
1. <span data-ttu-id="2b8db-111">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2b8db-111">Click Edit.</span></span>
2. <span data-ttu-id="2b8db-112">A Termékéletciklus állapota mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2b8db-112">In the Product lifecycle state field, enter or select a value.</span></span>
3. <span data-ttu-id="2b8db-113">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="2b8db-113">Click Save.</span></span>
4. <span data-ttu-id="2b8db-114">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="2b8db-114">Click Yes.</span></span>

> [!NOTE]
> <span data-ttu-id="2b8db-115">Ha az Igen van bejelölve, minden kapcsolódó azon kiadott termékváltozat, amelyek eredeti állapota megegyezik a kiadott alaptermékével, ugyancsak frissül az új termékélettartam-állapotra.</span><span class="sxs-lookup"><span data-stu-id="2b8db-115">If Yes is selected, all the related released product variants that have the same original status as the released product master are also updated to the new product lifecycle state.</span></span> <span data-ttu-id="2b8db-116">Ha a Nem van bejelölve, minden változat megőrzi az aktuális állapotát.</span><span class="sxs-lookup"><span data-stu-id="2b8db-116">If No is selected, all variants keep their actual state.</span></span> <span data-ttu-id="2b8db-117">A kiadott alapterméktől eltérő termékéletciklus-állapottal rendelkező változatokat a rendszer nem frissíti.</span><span class="sxs-lookup"><span data-stu-id="2b8db-117">Variants that have a different product lifecycle state from the released product master are not updated.</span></span>  

## <a name="verify-the-lifecycle-state-of-the-variants"></a><span data-ttu-id="2b8db-118">A változatok életciklus-állapotának ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="2b8db-118">Verify the lifecycle state of the variants</span></span>
1. <span data-ttu-id="2b8db-119">Kattintson a Kiadott termékváltozatok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2b8db-119">Click Released product variants.</span></span>

> [!NOTE]
> <span data-ttu-id="2b8db-120">Vegye figyelembe, hogy minden változat esetében öröklődik a kiadott alaptermék kiválasztott életciklus-állapota.</span><span class="sxs-lookup"><span data-stu-id="2b8db-120">Note that all variants have inherited the selected lifecycle state from the released product master.</span></span>  

2. <span data-ttu-id="2b8db-121">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="2b8db-121">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="2b8db-122">A Termékéletciklus állapota mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2b8db-122">In the Product lifecycle state field, enter or select a value.</span></span>


