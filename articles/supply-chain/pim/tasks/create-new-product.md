---
title: Új termék létrehozása
description: Ez a témakör azt mutatja be, hogyan lehet új megosztott terméket létrehozni.
author: ShylaThompson
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d6d33a13920e1881cdc69ad7c100180d3b3b441d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5820034"
---
# <a name="create-a-new-product"></a><span data-ttu-id="2a3f2-103">Új termék létrehozása</span><span class="sxs-lookup"><span data-stu-id="2a3f2-103">Create a new product</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2a3f2-104">Ez a témakör azt mutatja be, hogyan lehet új megosztott terméket létrehozni.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-104">This topic describes how to create a new shared product.</span></span> <span data-ttu-id="2a3f2-105">Ezt az eljárást általában a termék tervező végzi.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-105">It is usually carried out by a product designer.</span></span> <span data-ttu-id="2a3f2-106">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-a-product"></a><span data-ttu-id="2a3f2-107">Termék létrehozása</span><span class="sxs-lookup"><span data-stu-id="2a3f2-107">Create a product</span></span>
1. <span data-ttu-id="2a3f2-108">A Navigációs ablaktáblán ugorjon a **Modulok > Termékinformációk kezelése > Termékek > Termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-108">In the Navigation pane, go to **Modules > Product information management > Products > Products**.</span></span>
2. <span data-ttu-id="2a3f2-109">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-109">Select **New**.</span></span>
3. <span data-ttu-id="2a3f2-110">Írjon be egy értéket a **Termékszám** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-110">In the **Product number** field, type a value.</span></span> <span data-ttu-id="2a3f2-111">Ha a számsorozatot nem állították be a termékszámra vonatkozóan, akkor manuálisan kell megadni.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-111">If a number sequence has not been set up for the product number, it must be entered manually.</span></span>  
4. <span data-ttu-id="2a3f2-112">Írjon be egy értéket a **Terméknév** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-112">In the **Product name** field, type a value.</span></span> <span data-ttu-id="2a3f2-113">A Termék neve az alapértelmezett keresési név.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-113">The product name defaults to the search name.</span></span> <span data-ttu-id="2a3f2-114">Ez szükség szerint módosítható.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-114">You can change this if needed.</span></span>  
5. <span data-ttu-id="2a3f2-115">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-115">Select **OK**.</span></span>

## <a name="set-up-dimension-groups"></a><span data-ttu-id="2a3f2-116">Állítsa be a Dimenziócsoportok lehetőséget</span><span class="sxs-lookup"><span data-stu-id="2a3f2-116">Set up dimension groups</span></span>
1. <span data-ttu-id="2a3f2-117">A **Méretcsoportok** gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-117">Select **Dimension groups** to open the drop dialog.</span></span>
2. <span data-ttu-id="2a3f2-118">A **Tárolási dimenziócsoport** mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-118">In the **Storage dimension group** field, enter or select a value.</span></span> <span data-ttu-id="2a3f2-119">A tárolásidimenzió-csoport határozza meg, hogy mely tárolási dimenziót kell megadni termék minden egyes tranzakciójában és hogy hogyan követi nyomon a rendszer a készletben.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-119">The storage dimension group determines which storage dimensions you must enter on each transaction for the product and how it will be tracked in inventory.</span></span>  
3. <span data-ttu-id="2a3f2-120">A **Nyomon követési dimenziócsoport** mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-120">In the **Tracking dimension group** field, enter or select a value.</span></span> <span data-ttu-id="2a3f2-121">A tárolásidimenzió-csoport határozza meg, hogy mely nyomon követési dimenzióit kell megadni termék minden egyes tranzakciójában és hogy hogyan kezeli a rendszer a készletben.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-121">The tracking dimension group determines which tracking dimensions you must enter for each transaction for the product, and how it will be handled in inventory.</span></span>  
4. <span data-ttu-id="2a3f2-122">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-122">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]