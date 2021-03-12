---
title: Termékéletciklus-állapot létrehozása a termékek kizárásához az alaptervezésből
description: Ez az eljárás bemutatja, hogyan hozzon létre új termékéletciklus-állapotot, amely kizárja a termékeket az Alaptervezésből és anyagjegyzékszint-számításból.
author: cvocph
manager: tfehr
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6bb18f876e7d279624f60f01c5fbf4e449e9ab27
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4986879"
---
# <a name="create-a-product-lifecycle-state-to-exclude-products-from-master-planning"></a><span data-ttu-id="2d9d7-103">Termékéletciklus-állapot létrehozása a termékek kizárásához az alaptervezésből</span><span class="sxs-lookup"><span data-stu-id="2d9d7-103">Create a product lifecycle state to exclude products from Master planning</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2d9d7-104">Ez az eljárás bemutatja, hogyan hozzon létre új termékéletciklus-állapotot, amely kizárja a termékeket az Alaptervezésből és anyagjegyzékszint-számításból.</span><span class="sxs-lookup"><span data-stu-id="2d9d7-104">This procedure shows how to create a new product lifecycle state that excludes the products from Master planning and BOM-level calculation.</span></span>


## <a name="create-an-obsolete-state"></a><span data-ttu-id="2d9d7-105">Elavult állapot létrehozása</span><span class="sxs-lookup"><span data-stu-id="2d9d7-105">Create an obsolete state</span></span>
1. <span data-ttu-id="2d9d7-106">Válassza a Termékinformációk kezelése > Beállítás > Termékéletciklus állapota lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2d9d7-106">Go to Product information management > Setup > Product lifecycle state.</span></span>
2. <span data-ttu-id="2d9d7-107">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2d9d7-107">Click New.</span></span>
3. <span data-ttu-id="2d9d7-108">Az Állapot mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2d9d7-108">In the State field, type a value.</span></span>
4. <span data-ttu-id="2d9d7-109">Az Aktív a tervezéshez mezőben várja a Nem lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2d9d7-109">Select No in the Is active for planning field.</span></span>
5. <span data-ttu-id="2d9d7-110">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2d9d7-110">In the Description field, type a value.</span></span>

## <a name="associate-the-obsolete-state-to-a-released-product"></a><span data-ttu-id="2d9d7-111">Elavult állapot társítása kiadott termékhez</span><span class="sxs-lookup"><span data-stu-id="2d9d7-111">Associate the obsolete state to a released product</span></span>
1. <span data-ttu-id="2d9d7-112">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="2d9d7-112">Close the page.</span></span>
2. <span data-ttu-id="2d9d7-113">Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2d9d7-113">Go to Product information management > Products > Released products.</span></span>
3. <span data-ttu-id="2d9d7-114">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="2d9d7-114">Use the Quick Filter to find records.</span></span> <span data-ttu-id="2d9d7-115">Végezzen szűrést a Keresési név mezőben az „M00” értékkel.</span><span class="sxs-lookup"><span data-stu-id="2d9d7-115">For example, filter on the Search name field with a value of 'M00'.</span></span>
4. <span data-ttu-id="2d9d7-116">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2d9d7-116">Click Edit.</span></span>
5. <span data-ttu-id="2d9d7-117">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="2d9d7-117">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="2d9d7-118">A Termékéletciklus állapota mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2d9d7-118">In the Product lifecycle state field, enter or select a value.</span></span>

