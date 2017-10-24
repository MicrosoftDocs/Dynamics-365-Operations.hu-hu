--- 
title: "Rendkívüli értékcsökkenés beállítása"
description: "Ez az eljárás bemutatja, hogyan hozzon létre különleges értékcsökkenési keretet, és hogyan társítsa azt tárgyieszköz-könyvhöz."
author: saraschi2
manager: AnnBe
ms.date: 10/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7e6ebb13084626b477b6e0b24acdc09e2c0d3d6d
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-bonus-depreciation"></a><span data-ttu-id="035c6-103">Rendkívüli értékcsökkenés beállítása</span><span class="sxs-lookup"><span data-stu-id="035c6-103">Set up bonus depreciation</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="035c6-104">Ez az eljárás bemutatja, hogyan hozzon létre különleges értékcsökkenési keretet, és hogyan társítsa azt tárgyieszköz-könyvhöz.</span><span class="sxs-lookup"><span data-stu-id="035c6-104">This procedure shows how to create a special depreciation allowance and associate it with a fixed asset book.</span></span> <span data-ttu-id="035c6-105">Ez a könyvelői szerepkört és a bemutató adatokat használja a USMF jogi személyhez.</span><span class="sxs-lookup"><span data-stu-id="035c6-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="create-a-special-depreciation-allowance"></a><span data-ttu-id="035c6-106">Különleges értékcsökkenési keret létrehozása</span><span class="sxs-lookup"><span data-stu-id="035c6-106">Create a special depreciation allowance</span></span>
1. <span data-ttu-id="035c6-107">Ugorjon a Tárgyi eszközök > Beállítás > Különleges értékcsökkenési keret pontra.</span><span class="sxs-lookup"><span data-stu-id="035c6-107">Go to Fixed assets > Setup > Special depreciation allowance.</span></span>
2. <span data-ttu-id="035c6-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="035c6-108">Click New.</span></span>
3. <span data-ttu-id="035c6-109">Írjon egy értéket a Különleges értékcsökkenési keret mezőbe.</span><span class="sxs-lookup"><span data-stu-id="035c6-109">In the Special depreciation allowance field, type a value.</span></span>
4. <span data-ttu-id="035c6-110">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="035c6-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="035c6-111">Adjon meg egy számot a Százalék mezőben.</span><span class="sxs-lookup"><span data-stu-id="035c6-111">In the Percentage field, enter a number.</span></span>
    * <span data-ttu-id="035c6-112">Állítson be összeget, amennyiben nem került százalék megjelölésre.</span><span class="sxs-lookup"><span data-stu-id="035c6-112">If a percentage was not indicated, set an amount.</span></span>  

## <a name="associate-a-special-depreciation-allowance-with-a-fixed-asset-group-book"></a><span data-ttu-id="035c6-113">Társítson különleges értékcsökkenési keretet tárgyieszköz-csoport könyvéhez</span><span class="sxs-lookup"><span data-stu-id="035c6-113">Associate a special depreciation allowance with a fixed asset group book</span></span>
1. <span data-ttu-id="035c6-114">Ugorjon a Tárgyi eszközök > Beállítás > Tárgyieszköz-csoportok pontra.</span><span class="sxs-lookup"><span data-stu-id="035c6-114">Go to Fixed assets > Setup > Fixed asset groups.</span></span>
2. <span data-ttu-id="035c6-115">A listából válassza ki a különleges értékcsökkenés könyvhöz társított tárgyieszköz-csoportot.</span><span class="sxs-lookup"><span data-stu-id="035c6-115">In the list, select the fixed asset group associated with the special depreciation allowance.</span></span>
3. <span data-ttu-id="035c6-116">Kattintson a Könyvek elemre.</span><span class="sxs-lookup"><span data-stu-id="035c6-116">Click Books.</span></span>
4. <span data-ttu-id="035c6-117">A listából válassza ki a különleges értékcsökkenési kerethez társított könyvet.</span><span class="sxs-lookup"><span data-stu-id="035c6-117">In the list, select the book that is associated with the special depreciation allowance.</span></span>
5. <span data-ttu-id="035c6-118">Kattintson a Különleges értékcsökkenési keret elemre.</span><span class="sxs-lookup"><span data-stu-id="035c6-118">Click Special depreciation allowance.</span></span>
6. <span data-ttu-id="035c6-119">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="035c6-119">Click New.</span></span>
7. <span data-ttu-id="035c6-120">A Különleges értékcsökkenési keret mezőben írjon be vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="035c6-120">In the Special depreciation allowance field, enter or select a value.</span></span>
    * <span data-ttu-id="035c6-121">A Százalék vagy Összeg alapértelmezett értéke a különleges értékcsökkenési keret beállításainak megfelelően alakul.</span><span class="sxs-lookup"><span data-stu-id="035c6-121">The default for Percentage or Amount comes from the special depreciation allowance setup.</span></span>  
8. <span data-ttu-id="035c6-122">Adjon meg egy számot a Prioritás mezőben.</span><span class="sxs-lookup"><span data-stu-id="035c6-122">In the Priority field, enter a number.</span></span>

