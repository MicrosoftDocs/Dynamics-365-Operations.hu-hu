---
title: Intézkedési kódok beállítása
description: Ezzel az eljárással intézkedési kódot hozhat létre, amely mobileszközön használható a visszárurendelés bevételezési folyamatához.
author: ShylaThompson
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSDispositionTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b7c98526423b28fcb6c4e00a9f2cfd84d5a9119e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977013"
---
# <a name="set-up-dispositions-codes"></a><span data-ttu-id="aced0-103">Intézkedési kódok beállítása</span><span class="sxs-lookup"><span data-stu-id="aced0-103">Set up dispositions codes</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="aced0-104">Ezzel az eljárással intézkedési kódot hozhat létre, amely mobileszközön használható a visszárurendelés bevételezési folyamatához.</span><span class="sxs-lookup"><span data-stu-id="aced0-104">This procedure focuses on the setup of a disposition code that can be used on a mobile device for the return order receiving process.</span></span> <span data-ttu-id="aced0-105">Az intézkedési kódok olyan szabálygyűjtemények, melyeket áru beérkezésekor használnak.</span><span class="sxs-lookup"><span data-stu-id="aced0-105">Disposition codes are a collection of rules that can be used when items are received.</span></span> <span data-ttu-id="aced0-106">Például amikor egy munkafelhasználó mobileszközt használ sérült cikkek érkeztetéséhez, a felhasználónak egy intézkedési kódot kell beolvasni a sérült cikkekhez.</span><span class="sxs-lookup"><span data-stu-id="aced0-106">For example, when a work user uses a mobile device to receive items that were damaged, the user must scan a disposition code for damaged items.</span></span> <span data-ttu-id="aced0-107">A kapott áruk készletállapotát, a munkasablont és a helyirányelvet a beolvasott intézkedési kódból lehet meghatározni.</span><span class="sxs-lookup"><span data-stu-id="aced0-107">The inventory status of the goods received, the work template, and the location directive can be determined from the scanned disposition code.</span></span> <span data-ttu-id="aced0-108">A beszerzési rendelés bevételezési folyamathoz és a termelési rendelés jelentés készre jelentési folyamatához intézkedési kód használata nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="aced0-108">For the purchase order receiving process and the production order report as finished process, the use of a disposition code is optional.</span></span> <span data-ttu-id="aced0-109">Az értékesítési rendelés visszáru bevételezési folyamatánál, ha a cikkek regisztrálása mobileszközzel történt, intézkedési kód használata kötelező.</span><span class="sxs-lookup"><span data-stu-id="aced0-109">For the sales order return receiving process, if the items are registered using a mobile device, the use of disposition code is mandatory.</span></span>  <span data-ttu-id="aced0-110">Ez az útmutató a USMF bemutatócég segítségével lett létrehozva.</span><span class="sxs-lookup"><span data-stu-id="aced0-110">This guide was created using the demo data company USMF.</span></span> <span data-ttu-id="aced0-111">Ezt az eljárást a raktári vezető használja.</span><span class="sxs-lookup"><span data-stu-id="aced0-111">This procedure is intended for the warehouse manager.</span></span> 

1. <span data-ttu-id="aced0-112">Ugorjon a a Raktárkezelés > Beállítás > Mobileszköz > Intézkedési kódok menüre.</span><span class="sxs-lookup"><span data-stu-id="aced0-112">Go to Warehouse management > Setup > Mobile device > Disposition codes.</span></span>
2. <span data-ttu-id="aced0-113">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="aced0-113">Click New.</span></span>
    * <span data-ttu-id="aced0-114">Hozzon létre egy új, vevői visszáruhoz használandó intézkedési kódot.</span><span class="sxs-lookup"><span data-stu-id="aced0-114">Create a new disposition code to use for customer returns.</span></span>  
3. <span data-ttu-id="aced0-115">Írjon be egy értéket az Intézkedési kód mezőbe.</span><span class="sxs-lookup"><span data-stu-id="aced0-115">In the Disposition code field, type a value.</span></span>
4. <span data-ttu-id="aced0-116">A Készlet állapota mezőben válasszon ki egy készletállapotot, ahol a készletzárolás van.</span><span class="sxs-lookup"><span data-stu-id="aced0-116">In the Inventory status field, select an inventory status where there is inventory blocking.</span></span>
    * <span data-ttu-id="aced0-117">Ha USMF-et használ, jelölje be a "Blocking" opciót.</span><span class="sxs-lookup"><span data-stu-id="aced0-117">If you're using USMF, select 'Blocking'.</span></span> <span data-ttu-id="aced0-118">Egy készletállapotot adhat az intézkedési kódhoz, ha felül szeretné bírálni az alapértelmezett állapotot, amely a rendelési sorokon van.</span><span class="sxs-lookup"><span data-stu-id="aced0-118">You can add an inventory status to the disposition code to override the default status that's on the order lines.</span></span>  
5. <span data-ttu-id="aced0-119">Írjon be egy értéket a Munkasablon mezőbe.</span><span class="sxs-lookup"><span data-stu-id="aced0-119">In the Work template field, type a value.</span></span>
    * <span data-ttu-id="aced0-120">Választható: A visszárurendeléshez társított munkasablonkód kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="aced0-120">Optional: Select a work template code that is associated with a return order.</span></span> <span data-ttu-id="aced0-121">Ha nincs érték megadva, a munkasablon a rendszerben szokásos szabályok segítségével lesz beállítva.</span><span class="sxs-lookup"><span data-stu-id="aced0-121">If no value is provided, the work template will be resolved using the standard rules configured in your system.</span></span> <span data-ttu-id="aced0-122">Egy munkasablon kiválasztása korlátozza a folyamatokat, amelyekkel ez az intézkedéskód használható.</span><span class="sxs-lookup"><span data-stu-id="aced0-122">Selecting a work template will limit the processes this disposition code can be used with.</span></span> <span data-ttu-id="aced0-123">Például ha egy intézkedési kódhoz egy Munkarendelés típusú beszerzési rendeléssel rendelkező munkasablon tartozik, nem használható vevők által visszaküldött cikkek regisztrálásához.</span><span class="sxs-lookup"><span data-stu-id="aced0-123">For example, if a disposition code has a work template with a work order of type purchase order, it can't be used to register items that are returned by customers.</span></span>  
6. <span data-ttu-id="aced0-124">Írjon be egy értéket a Visszáru-iIntézkedési kód mezőbe.</span><span class="sxs-lookup"><span data-stu-id="aced0-124">In the Return disposition code field, type a value.</span></span>
    * <span data-ttu-id="aced0-125">A visszaküldési intézkedéskód meghatározza a regisztrált cikkek visszáru-rendelési folyamatának többi részét.</span><span class="sxs-lookup"><span data-stu-id="aced0-125">The return disposition code determines the remainder of the return order process for the items registered.</span></span> <span data-ttu-id="aced0-126">Ebben a példában a vevőnek jóváírást kell kapnia.</span><span class="sxs-lookup"><span data-stu-id="aced0-126">In this example, the customer should receive a credit note.</span></span> <span data-ttu-id="aced0-127">Adjon hozzá egy visszáru intézkedési kódot, amely egy Jóváírás műveletet tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="aced0-127">Add a returns disposition code that contains an action Credit.</span></span>  

