---
title: Alapértelmezett termékéletciklus-állapot létrehozása
description: Ez az eljárás egy alapértelmezett termékéletciklus-állapot létrehozását mutatja be, valamint azt is, hogyan lehet társítani az alapértelmezett állapotot a kiadott termékekhez.
author: cvocph
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b62d47f52da7f9e18bce401578a5e2a629ac5eb8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818133"
---
# <a name="create-a-default-product-lifecycle-state"></a><span data-ttu-id="82a0b-103">Alapértelmezett termékéletciklus-állapot létrehozása</span><span class="sxs-lookup"><span data-stu-id="82a0b-103">Create a default product lifecycle state</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="82a0b-104">Ez az eljárás egy alapértelmezett termékéletciklus-állapot létrehozását mutatja be, valamint azt is, hogyan lehet társítani az alapértelmezett állapotot a kiadott termékekhez.</span><span class="sxs-lookup"><span data-stu-id="82a0b-104">This procedure shows how to create a default product lifecycle state as well as how to associate the default state with released products.</span></span>


## <a name="create-a-default-lifecycle-state"></a><span data-ttu-id="82a0b-105">Alapértelmezett életciklusállapot létrehozása</span><span class="sxs-lookup"><span data-stu-id="82a0b-105">Create a default lifecycle state</span></span>
1. <span data-ttu-id="82a0b-106">Válassza a Termékinformációk kezelése > Beállítás > Termékéletciklus állapota lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="82a0b-106">Go to Product information management > Setup > Product lifecycle state.</span></span>
2. <span data-ttu-id="82a0b-107">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="82a0b-107">Click New.</span></span>
3. <span data-ttu-id="82a0b-108">Az Állapot mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="82a0b-108">In the State field, type a value.</span></span>
4. <span data-ttu-id="82a0b-109">Az Alapértelmezett kiadáskor jogi személynek mezőben válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="82a0b-109">Select Yes in the Default when released to legal entity field.</span></span>
5. <span data-ttu-id="82a0b-110">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="82a0b-110">In the Description field, type a value.</span></span>
6. <span data-ttu-id="82a0b-111">Az Aktív a tervezéshez mezőben várja a Nem lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="82a0b-111">Select No in the Is active for planning field.</span></span>

> [!NOTE]
> <span data-ttu-id="82a0b-112">Ha egy új kiadott terméket nem kell belefoglalni az alaptervezésbe, válassza a Nem lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="82a0b-112">If a new released product should not be included in Master planning, select No.</span></span> <span data-ttu-id="82a0b-113">Ha szerepelnie kell az alaptervezésben, hagyja meg az alapértelmezett Igen értéken.</span><span class="sxs-lookup"><span data-stu-id="82a0b-113">If it should be included in Master planning, leave the control at its default value Yes.</span></span>  

## <a name="create-a-new-released-product"></a><span data-ttu-id="82a0b-114">Új kiadott termék létrehozása</span><span class="sxs-lookup"><span data-stu-id="82a0b-114">Create a new released product</span></span>
1. <span data-ttu-id="82a0b-115">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="82a0b-115">Close the page.</span></span>
2. <span data-ttu-id="82a0b-116">Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="82a0b-116">Go to Product information management > Products > Released products.</span></span>
3. <span data-ttu-id="82a0b-117">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="82a0b-117">Click New.</span></span>
4. <span data-ttu-id="82a0b-118">Írjon be egy értéket a Termékszám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="82a0b-118">In the Product number field, type a value.</span></span>
5. <span data-ttu-id="82a0b-119">Írjon be egy értéket a Terméknév mezőbe.</span><span class="sxs-lookup"><span data-stu-id="82a0b-119">In the Product name field, type a value.</span></span>
6. <span data-ttu-id="82a0b-120">Írjon be egy értéket a Keresési név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="82a0b-120">In the Search name field, type a value.</span></span>
7. <span data-ttu-id="82a0b-121">Az Elem modellcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="82a0b-121">In the Item model group field, enter or select a value.</span></span>
8. <span data-ttu-id="82a0b-122">Az Elemcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="82a0b-122">In the Item group field, enter or select a value.</span></span>
9. <span data-ttu-id="82a0b-123">A Tárolási dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="82a0b-123">In the Storage dimension group field, enter or select a value.</span></span>
10. <span data-ttu-id="82a0b-124">A Nyomon követési dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="82a0b-124">In the Tracking dimension group field, enter or select a value.</span></span>
11. <span data-ttu-id="82a0b-125">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="82a0b-125">Click OK.</span></span>

> [!NOTE]
> <span data-ttu-id="82a0b-126">Az alapértelmezett termékéletciklus-állapot egy globális definíció.</span><span class="sxs-lookup"><span data-stu-id="82a0b-126">The default product lifecycle state is a global definition.</span></span>  

## <a name="change-the-product-to-an-active-state"></a><span data-ttu-id="82a0b-127">Termék aktív állapotra történő módosítása</span><span class="sxs-lookup"><span data-stu-id="82a0b-127">Change the product to an active state</span></span>
1. <span data-ttu-id="82a0b-128">A Termékéletciklus állapota mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="82a0b-128">In the Product lifecycle state field, enter or select a value.</span></span>

> [!NOTE]
> <span data-ttu-id="82a0b-129">Tegyük fel, hogy beállította az aktív állapotot, és most kiválaszthatja az aktív állapotot, engedélyezve a termék használatát az alaptervezésben és az anyagjegyzékszintű számításban.</span><span class="sxs-lookup"><span data-stu-id="82a0b-129">Assume that you have set up an active state, you can now select the active state to allow the product to be used in Master planning and BOM-level calculation.</span></span> <span data-ttu-id="82a0b-130">Ennek természetesen csak akkor van értelme, ha a konzisztens tervezéshez szükséges összes termékrészlet meg van határozva.</span><span class="sxs-lookup"><span data-stu-id="82a0b-130">Obviously, this only makes sense if all the product details that are required for consistent planning are specified.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]