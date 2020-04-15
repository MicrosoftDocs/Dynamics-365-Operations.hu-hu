---
title: Új termék létrehozása
description: Ez a témakör azt mutatja be, hogyan lehet új megosztott terméket létrehozni.
author: ShylaThompson
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 611fc0cff7fe2d580e971149630e92afd16be228
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3147848"
---
# <a name="create-a-new-product"></a><span data-ttu-id="5dfe3-103">Új termék létrehozása</span><span class="sxs-lookup"><span data-stu-id="5dfe3-103">Create a new product</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5dfe3-104">Ez a témakör azt mutatja be, hogyan lehet új megosztott terméket létrehozni.</span><span class="sxs-lookup"><span data-stu-id="5dfe3-104">This topic describes how to create a new shared product.</span></span> <span data-ttu-id="5dfe3-105">Ezt az eljárást általában a termék tervező végzi.</span><span class="sxs-lookup"><span data-stu-id="5dfe3-105">It is usually carried out by a product designer.</span></span> <span data-ttu-id="5dfe3-106">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="5dfe3-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-a-product"></a><span data-ttu-id="5dfe3-107">Termék létrehozása</span><span class="sxs-lookup"><span data-stu-id="5dfe3-107">Create a product</span></span>
1. <span data-ttu-id="5dfe3-108">A Navigációs ablaktáblán ugorjon a **Modulok > Termékinformációk kezelése > Termékek > Termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5dfe3-108">In the Navigation pane, go to **Modules > Product information management > Products > Products**.</span></span>
2. <span data-ttu-id="5dfe3-109">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5dfe3-109">Select **New**.</span></span>
3. <span data-ttu-id="5dfe3-110">Írjon be egy értéket a **Termékszám** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5dfe3-110">In the **Product number** field, type a value.</span></span> <span data-ttu-id="5dfe3-111">Ha a számsorozatot nem állították be a termékszámra vonatkozóan, akkor manuálisan kell megadni.</span><span class="sxs-lookup"><span data-stu-id="5dfe3-111">If a number sequence has not been set up for the product number, it must be entered manually.</span></span>  
4. <span data-ttu-id="5dfe3-112">Írjon be egy értéket a **Terméknév** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5dfe3-112">In the **Product name** field, type a value.</span></span> <span data-ttu-id="5dfe3-113">A Termék neve az alapértelmezett keresési név.</span><span class="sxs-lookup"><span data-stu-id="5dfe3-113">The product name defaults to the search name.</span></span> <span data-ttu-id="5dfe3-114">Ez szükség szerint módosítható.</span><span class="sxs-lookup"><span data-stu-id="5dfe3-114">You can change this if needed.</span></span>  
5. <span data-ttu-id="5dfe3-115">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5dfe3-115">Select **OK**.</span></span>

## <a name="set-up-dimension-groups"></a><span data-ttu-id="5dfe3-116">Állítsa be a Dimenziócsoportok lehetőséget</span><span class="sxs-lookup"><span data-stu-id="5dfe3-116">Set up dimension groups</span></span>
1. <span data-ttu-id="5dfe3-117">A **Méretcsoportok** gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="5dfe3-117">Select **Dimension groups** to open the drop dialog.</span></span>
2. <span data-ttu-id="5dfe3-118">A **Tárolási dimenziócsoport** mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5dfe3-118">In the **Storage dimension group** field, enter or select a value.</span></span> <span data-ttu-id="5dfe3-119">A tárolásidimenzió-csoport határozza meg, hogy mely tárolási dimenziót kell megadni termék minden egyes tranzakciójában és hogy hogyan követi nyomon a rendszer a készletben.</span><span class="sxs-lookup"><span data-stu-id="5dfe3-119">The storage dimension group determines which storage dimensions you must enter on each transaction for the product and how it will be tracked in inventory.</span></span>  
3. <span data-ttu-id="5dfe3-120">A **Nyomon követési dimenziócsoport** mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5dfe3-120">In the **Tracking dimension group** field, enter or select a value.</span></span> <span data-ttu-id="5dfe3-121">A tárolásidimenzió-csoport határozza meg, hogy mely nyomon követési dimenzióit kell megadni termék minden egyes tranzakciójában és hogy hogyan kezeli a rendszer a készletben.</span><span class="sxs-lookup"><span data-stu-id="5dfe3-121">The tracking dimension group determines which tracking dimensions you must enter for each transaction for the product, and how it will be handled in inventory.</span></span>  
4. <span data-ttu-id="5dfe3-122">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5dfe3-122">Select **OK**.</span></span>

