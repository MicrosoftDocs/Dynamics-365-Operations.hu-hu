---
title: Rendkívüli értékcsökkenés beállítása
description: Ez az eljárás bemutatja, hogyan hozzon létre különleges értékcsökkenési keretet, és hogyan társítsa azt tárgyieszköz-könyvhöz.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBonus, AssetGroup, AssetGroupBookSetup, AssetGroupSetupBonus
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 91243a4cee44410a221902990d31a10f1805eb08
ms.sourcegitcommit: c69926b4285cb2ec2d9ce1ad72d1cb852024dd5e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3138253"
---
# <a name="set-up-bonus-depreciation"></a><span data-ttu-id="c67e8-103">Rendkívüli értékcsökkenés beállítása</span><span class="sxs-lookup"><span data-stu-id="c67e8-103">Set up bonus depreciation</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c67e8-104">Ez az eljárás bemutatja, hogyan hozzon létre különleges értékcsökkenési keretet, és hogyan társítsa azt tárgyieszköz-könyvhöz.</span><span class="sxs-lookup"><span data-stu-id="c67e8-104">This procedure shows how to create a special depreciation allowance and associate it with a fixed asset book.</span></span> <span data-ttu-id="c67e8-105">Ez a könyvelői szerepkört és a bemutató adatokat használja a USMF jogi személyhez.</span><span class="sxs-lookup"><span data-stu-id="c67e8-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="create-a-special-depreciation-allowance"></a><span data-ttu-id="c67e8-106">Különleges értékcsökkenési keret létrehozása</span><span class="sxs-lookup"><span data-stu-id="c67e8-106">Create a special depreciation allowance</span></span>
1. <span data-ttu-id="c67e8-107">Ugorjon a Tárgyi eszközök > Beállítás > Különleges értékcsökkenési keret pontra.</span><span class="sxs-lookup"><span data-stu-id="c67e8-107">Go to Fixed assets > Setup > Special depreciation allowance.</span></span>
2. <span data-ttu-id="c67e8-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c67e8-108">Click New.</span></span>
3. <span data-ttu-id="c67e8-109">Írjon egy értéket a Különleges értékcsökkenési keret mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c67e8-109">In the Special depreciation allowance field, type a value.</span></span>
4. <span data-ttu-id="c67e8-110">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c67e8-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="c67e8-111">Adjon meg egy számot a Százalék mezőben.</span><span class="sxs-lookup"><span data-stu-id="c67e8-111">In the Percentage field, enter a number.</span></span>
    * <span data-ttu-id="c67e8-112">Állítson be összeget, amennyiben nem került százalék megjelölésre.</span><span class="sxs-lookup"><span data-stu-id="c67e8-112">If a percentage was not indicated, set an amount.</span></span>  

## <a name="associate-a-special-depreciation-allowance-with-a-fixed-asset-group-book"></a><span data-ttu-id="c67e8-113">Társítson különleges értékcsökkenési keretet tárgyieszköz-csoport könyvéhez</span><span class="sxs-lookup"><span data-stu-id="c67e8-113">Associate a special depreciation allowance with a fixed asset group book</span></span>
1. <span data-ttu-id="c67e8-114">Ugorjon a Tárgyi eszközök > Beállítás > Tárgyieszköz-csoportok pontra.</span><span class="sxs-lookup"><span data-stu-id="c67e8-114">Go to Fixed assets > Setup > Fixed asset groups.</span></span>
2. <span data-ttu-id="c67e8-115">A listából válassza ki a különleges értékcsökkenés könyvhöz társított tárgyieszköz-csoportot.</span><span class="sxs-lookup"><span data-stu-id="c67e8-115">In the list, select the fixed asset group associated with the special depreciation allowance.</span></span>
3. <span data-ttu-id="c67e8-116">Kattintson a Könyvek elemre.</span><span class="sxs-lookup"><span data-stu-id="c67e8-116">Click Books.</span></span>
4. <span data-ttu-id="c67e8-117">A listából válassza ki a különleges értékcsökkenési kerethez társított könyvet.</span><span class="sxs-lookup"><span data-stu-id="c67e8-117">In the list, select the book that is associated with the special depreciation allowance.</span></span>
5. <span data-ttu-id="c67e8-118">Kattintson a Különleges értékcsökkenési keret elemre.</span><span class="sxs-lookup"><span data-stu-id="c67e8-118">Click Special depreciation allowance.</span></span>
6. <span data-ttu-id="c67e8-119">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c67e8-119">Click New.</span></span>
7. <span data-ttu-id="c67e8-120">A Különleges értékcsökkenési keret mezőben írjon be vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c67e8-120">In the Special depreciation allowance field, enter or select a value.</span></span>
    * <span data-ttu-id="c67e8-121">A Százalék vagy Összeg alapértelmezett értéke a különleges értékcsökkenési keret beállításainak megfelelően alakul.</span><span class="sxs-lookup"><span data-stu-id="c67e8-121">The default for Percentage or Amount comes from the special depreciation allowance setup.</span></span>  
8. <span data-ttu-id="c67e8-122">Adjon meg egy számot a Prioritás mezőben.</span><span class="sxs-lookup"><span data-stu-id="c67e8-122">In the Priority field, enter a number.</span></span>

