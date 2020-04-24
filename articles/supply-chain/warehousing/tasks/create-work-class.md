---
title: Munkaosztály létrehozása
description: Ez az eljárás bemutatja, hogyan állíthat be egy munkaosztályt.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a965906bfbf6411986594ddd5c67beb426268367
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3217103"
---
# <a name="create-a-work-class"></a><span data-ttu-id="92ebb-103">Munkaosztály létrehozása</span><span class="sxs-lookup"><span data-stu-id="92ebb-103">Create a work class</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="92ebb-104">Ez az eljárás bemutatja, hogyan állíthat be egy munkaosztályt.</span><span class="sxs-lookup"><span data-stu-id="92ebb-104">This procedure shows you how to set up a work class.</span></span> <span data-ttu-id="92ebb-105">A munkaosztályokkal irányítható és/vagy korlátozható azon munkarendeléssorok típusa, amelyeket egy raktári dolgozó feldolgozhat egy mobileszközön.</span><span class="sxs-lookup"><span data-stu-id="92ebb-105">Work classes are used to direct and/or limit the type of work order lines that a warehouse worker can process on a mobile device.</span></span> <span data-ttu-id="92ebb-106">A sorokat, amelyeket egy dolgozó feldolgozhat, a mobileszköz-menü elemeinek munkaosztályai, amelyekhez a raktári dolgozó hozzáférésre jogosult, és a munkasorokban megadott munkaosztályok határozzák meg.</span><span class="sxs-lookup"><span data-stu-id="92ebb-106">The lines that a worker can process are determined from the work classes on the mobile device menu items that the warehouse worker has access to and the work class that's specified on the work lines.</span></span> <span data-ttu-id="92ebb-107">Munkaosztályok használhatók a betárolási hely ellenőrzéséhez is munkarendelési sorhoz.</span><span class="sxs-lookup"><span data-stu-id="92ebb-107">Work classes can also be used to validate the put location for a work order line.</span></span> <span data-ttu-id="92ebb-108">Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja.</span><span class="sxs-lookup"><span data-stu-id="92ebb-108">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="92ebb-109">Ezt az eljárást a raktári vezető használja.</span><span class="sxs-lookup"><span data-stu-id="92ebb-109">This procedure is intended for the warehouse manager.</span></span>

1. <span data-ttu-id="92ebb-110">Ugorjon a Raktárkezelés > Beállítás > Munka > Munkaosztályok pontra.</span><span class="sxs-lookup"><span data-stu-id="92ebb-110">Go to Warehouse management > Setup > Work > Work classes.</span></span>
2. <span data-ttu-id="92ebb-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="92ebb-111">Click New.</span></span>
3. <span data-ttu-id="92ebb-112">Írjon be egy értéket a Munkaosztály azonosítója mezőbe.</span><span class="sxs-lookup"><span data-stu-id="92ebb-112">In the Work class ID field, type a value.</span></span>
4. <span data-ttu-id="92ebb-113">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="92ebb-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="92ebb-114">A Munkarendelés típusa mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="92ebb-114">In the Work order type field, select an option.</span></span>
6. <span data-ttu-id="92ebb-115">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="92ebb-115">Click New.</span></span>
7. <span data-ttu-id="92ebb-116">Írjon be egy értéket a Helytípus mezőbe.</span><span class="sxs-lookup"><span data-stu-id="92ebb-116">In the Location type field, type a value.</span></span>
    * <span data-ttu-id="92ebb-117">Ha kiválaszt egy helytípust, azzal korlátozza a cikkek elhelyezését a kitárolás után.</span><span class="sxs-lookup"><span data-stu-id="92ebb-117">If you select a location type, this sets a restriction on where items can be put after they've been picked.</span></span> <span data-ttu-id="92ebb-118">Akkor használja ezt a beállítást, ha egy helyutasítás a hely feloldására tesz kísérletet, vagy ha egy raktári dolgozó manuálisan biztosítja a mobileszköz-menüpont helyét.</span><span class="sxs-lookup"><span data-stu-id="92ebb-118">This setting is used when a location directive tries to resolve the location, or if a warehouse worker manually provides the location for the mobile device menu item.</span></span>  
8. <span data-ttu-id="92ebb-119">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="92ebb-119">Close the page.</span></span>

