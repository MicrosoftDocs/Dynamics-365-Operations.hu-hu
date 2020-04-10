---
title: Központi kiegészítő szolgáltatások díjainak és kiegészítő alaptermékek beállítása
description: Ez az eljárás bemutatja, hogyan lehet kiegészítő szolgáltatások alapadatokat létrehozni egy központ számára, és az alapadatok segítségével egy központi kiegészítő díjat létrehozni.
author: ShylaThompson
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1ea59326a85d97d53795104f80486f2fac24148a
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148522"
---
# <a name="set-up-hub-accessorial-charges-and-accessorial-masters"></a><span data-ttu-id="10e53-103">Központi kiegészítő szolgáltatások díjainak és kiegészítő alaptermékek beállítása</span><span class="sxs-lookup"><span data-stu-id="10e53-103">Set up hub accessorial charges and accessorial masters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="10e53-104">Ez az eljárás bemutatja, hogyan lehet kiegészítő szolgáltatások alapadatokat létrehozni egy központ számára, és az alapadatok segítségével egy központi kiegészítő díjat létrehozni.</span><span class="sxs-lookup"><span data-stu-id="10e53-104">This procedure shows how to create an accessorial master for a hub and use that master to create a hub accessorial charge.</span></span> <span data-ttu-id="10e53-105">Az eljárás az USMF adatkészletet használja.</span><span class="sxs-lookup"><span data-stu-id="10e53-105">The procedure uses the USMF dataset.</span></span> <span data-ttu-id="10e53-106">Ezt a beállítást általában egy szállítási koordinátor végzi.</span><span class="sxs-lookup"><span data-stu-id="10e53-106">This set up will typically be done by a transportation coordinator.</span></span>


## <a name="set-up-a-hub-master"></a><span data-ttu-id="10e53-107">Központ alapadatainak beállítása</span><span class="sxs-lookup"><span data-stu-id="10e53-107">Set up a hub master</span></span>
1. <span data-ttu-id="10e53-108">Lépjen a Szállításkezelés > Beállítás > Minősítés > Kiegészítő alapszolgáltatások pontra.</span><span class="sxs-lookup"><span data-stu-id="10e53-108">Go to Transportation management > Setup > Rating > Accessorial masters.</span></span>
2. <span data-ttu-id="10e53-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="10e53-109">Click New.</span></span>
3. <span data-ttu-id="10e53-110">A Kiegészítő alapszolgáltatások mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="10e53-110">In the Accessorial master field, type a value.</span></span>
4. <span data-ttu-id="10e53-111">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="10e53-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="10e53-112">A Kiegészítő szolgáltatás típusa mezőben válassza ki a „Központ” elemet.</span><span class="sxs-lookup"><span data-stu-id="10e53-112">In the Accessorial type field, select 'Hub'.</span></span>
6. <span data-ttu-id="10e53-113">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="10e53-113">Click Save.</span></span>
7. <span data-ttu-id="10e53-114">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="10e53-114">Close the page.</span></span>

## <a name="set-up-a-hub-accessorial-charge"></a><span data-ttu-id="10e53-115">Központi kiegészítő szolgáltatások díj létrehozása</span><span class="sxs-lookup"><span data-stu-id="10e53-115">Set up a hub accessorial charge</span></span>
1. <span data-ttu-id="10e53-116">Lépjen a Szállításkezelés > Beállítás > Minősítés > Központi kiegészítő szolgáltatások díjai pontra.</span><span class="sxs-lookup"><span data-stu-id="10e53-116">Go to Transportation management > Setup > Rating > Hub accessorial charges.</span></span>
2. <span data-ttu-id="10e53-117">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="10e53-117">Click New.</span></span>
3. <span data-ttu-id="10e53-118">Írjon be egy értéket a Központi kiegészítő szolgáltatások azonosító mezőbe.</span><span class="sxs-lookup"><span data-stu-id="10e53-118">In the Hub accessorial ID field, type a value.</span></span>
4. <span data-ttu-id="10e53-119">A Központ mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="10e53-119">In the Hub field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="10e53-120">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="10e53-120">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="10e53-121">A Központ pozíciója mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="10e53-121">In the Hub position field, select an option.</span></span>
    * <span data-ttu-id="10e53-122">A költség lehet felvételi vagy lerakati.</span><span class="sxs-lookup"><span data-stu-id="10e53-122">You can either create the charge as a pickup or drop-off.</span></span> <span data-ttu-id="10e53-123">A választástól függően a költség a megfelelő szállítási szegmensre fog vonatkozni az útvonalon.</span><span class="sxs-lookup"><span data-stu-id="10e53-123">Depending on your selection the charge will be applied to the corresponding transportation segment on your route.</span></span>  
7. <span data-ttu-id="10e53-124">A Kiegészítő alapszolgáltatás mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="10e53-124">In the Accessorial master field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="10e53-125">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="10e53-125">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="10e53-126">Jelölje ki az előbb létrehozott alapadatot.</span><span class="sxs-lookup"><span data-stu-id="10e53-126">Select the master you just created.</span></span>  
9. <span data-ttu-id="10e53-127">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="10e53-127">Click Save.</span></span>
10. <span data-ttu-id="10e53-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="10e53-128">Close the page.</span></span>

