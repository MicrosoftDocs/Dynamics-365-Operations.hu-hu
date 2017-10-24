--- 
title: "Új termék létrehozása"
description: "Ez a feladat bemutatja, hogy hogyan lehet az új megosztott terméket létrehozni."
author: YuyuScheller
manager: AnnBe
ms.date: 06/08/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 56ce5d965952d0cb41278915e4631ae9d920f5f9
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-new-product"></a><span data-ttu-id="0f47d-103">Új termék létrehozása</span><span class="sxs-lookup"><span data-stu-id="0f47d-103">Create a new product</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0f47d-104">Ez a feladat bemutatja, hogy hogyan lehet az új megosztott terméket létrehozni.</span><span class="sxs-lookup"><span data-stu-id="0f47d-104">This task shows how to create a new shared product.</span></span> <span data-ttu-id="0f47d-105">Ezt az eljárást általában a termék tervező végzi.</span><span class="sxs-lookup"><span data-stu-id="0f47d-105">It is usually carried out by a product designer.</span></span> <span data-ttu-id="0f47d-106">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="0f47d-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="0f47d-107">Ugorjon a Termékinformációk kezelése > Termékek > Termékek pontra.</span><span class="sxs-lookup"><span data-stu-id="0f47d-107">Go to Product information management > Products > Products.</span></span>

## <a name="create-a-product"></a><span data-ttu-id="0f47d-108">Termék létrehozása</span><span class="sxs-lookup"><span data-stu-id="0f47d-108">Create a product</span></span>
1. <span data-ttu-id="0f47d-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0f47d-109">Click New.</span></span>
2. <span data-ttu-id="0f47d-110">Írjon be egy értéket a Termékszám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0f47d-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="0f47d-111">Ha a számsorozatot nem állították be a termékszámra vonatkozóan, akkor manuálisan kell megadni.</span><span class="sxs-lookup"><span data-stu-id="0f47d-111">If a number sequence has not been set up for the product number, it must be entered manually.</span></span>  
3. <span data-ttu-id="0f47d-112">Írjon be egy értéket a Terméknév mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0f47d-112">In the Product name field, type a value.</span></span>
    * <span data-ttu-id="0f47d-113">A Termék neve az alapértelmezett keresési név.</span><span class="sxs-lookup"><span data-stu-id="0f47d-113">The product name defaults to the search name.</span></span> <span data-ttu-id="0f47d-114">Ez szükség szerint módosítható.</span><span class="sxs-lookup"><span data-stu-id="0f47d-114">You can change this if needed.</span></span>  
4. <span data-ttu-id="0f47d-115">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="0f47d-115">Click OK.</span></span>

## <a name="set-up-dimension-groups"></a><span data-ttu-id="0f47d-116">Állítsa be a Dimenziócsoportok lehetőséget</span><span class="sxs-lookup"><span data-stu-id="0f47d-116">Set up dimension groups</span></span>
1. <span data-ttu-id="0f47d-117">A Méretcsoportok gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="0f47d-117">Click Dimension groups to open the drop dialog.</span></span>
2. <span data-ttu-id="0f47d-118">A Tárolási dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0f47d-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="0f47d-119">A tárolásidimenzió-csoport határozza meg, hogy mely tárolási dimenziót kell megadni termék minden egyes tranzakciójában és hogy hogyan követi nyomon a rendszer a készletben.</span><span class="sxs-lookup"><span data-stu-id="0f47d-119">The storage dimension group determines which storage dimensions you must enter on each transaction for the product and how it will be tracked in inventory.</span></span>  
3. <span data-ttu-id="0f47d-120">A Nyomon követési dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0f47d-120">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="0f47d-121">A tárolásidimenzió-csoport határozza meg, hogy mely nyomon követési dimenzióit kell megadni termék minden egyes tranzakciójában és hogy hogyan kezeli a rendszer a készletben.</span><span class="sxs-lookup"><span data-stu-id="0f47d-121">The tracking dimension group determines which tracking dimensions you must enter for each transaction for the product, and how it will be handled in inventory.</span></span>  
4. <span data-ttu-id="0f47d-122">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="0f47d-122">Click OK.</span></span>


