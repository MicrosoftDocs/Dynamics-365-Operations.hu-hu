---
title: Központi kiegészítő szolgáltatások díjainak és kiegészítő alaptermékek beállítása
description: Ez az eljárás bemutatja, hogyan lehet kiegészítő szolgáltatások alapadatokat létrehozni egy központ számára, és az alapadatok segítségével egy központi kiegészítő díjat létrehozni.
author: ShylaThompson
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSCarrierAccessorial,TMSAccessorialMaster, TMSHubAccessorial
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e012850a390f373088e758418b68c7eaae7ad53e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4973985"
---
# <a name="set-up-hub-accessorial-charges-and-accessorial-masters"></a><span data-ttu-id="f9b4b-103">Központi kiegészítő szolgáltatások díjainak és kiegészítő alaptermékek beállítása</span><span class="sxs-lookup"><span data-stu-id="f9b4b-103">Set up hub accessorial charges and accessorial masters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f9b4b-104">Ez az eljárás bemutatja, hogyan lehet kiegészítő szolgáltatások alapadatokat létrehozni egy központ számára, és az alapadatok segítségével egy központi kiegészítő díjat létrehozni.</span><span class="sxs-lookup"><span data-stu-id="f9b4b-104">This procedure shows how to create an accessorial master for a hub and use that master to create a hub accessorial charge.</span></span> <span data-ttu-id="f9b4b-105">Az eljárás az USMF adatkészletet használja.</span><span class="sxs-lookup"><span data-stu-id="f9b4b-105">The procedure uses the USMF dataset.</span></span> <span data-ttu-id="f9b4b-106">Ezt a beállítást általában egy szállítási koordinátor végzi.</span><span class="sxs-lookup"><span data-stu-id="f9b4b-106">This set up will typically be done by a transportation coordinator.</span></span>


## <a name="set-up-a-hub-master"></a><span data-ttu-id="f9b4b-107">Központ alapadatainak beállítása</span><span class="sxs-lookup"><span data-stu-id="f9b4b-107">Set up a hub master</span></span>
1. <span data-ttu-id="f9b4b-108">Lépjen a Szállításkezelés > Beállítás > Minősítés > Kiegészítő alapszolgáltatások pontra.</span><span class="sxs-lookup"><span data-stu-id="f9b4b-108">Go to Transportation management > Setup > Rating > Accessorial masters.</span></span>
2. <span data-ttu-id="f9b4b-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f9b4b-109">Click New.</span></span>
3. <span data-ttu-id="f9b4b-110">A Kiegészítő alapszolgáltatások mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="f9b4b-110">In the Accessorial master field, type a value.</span></span>
4. <span data-ttu-id="f9b4b-111">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="f9b4b-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="f9b4b-112">A Kiegészítő szolgáltatás típusa mezőben válassza ki a „Központ” elemet.</span><span class="sxs-lookup"><span data-stu-id="f9b4b-112">In the Accessorial type field, select 'Hub'.</span></span>
6. <span data-ttu-id="f9b4b-113">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="f9b4b-113">Click Save.</span></span>
7. <span data-ttu-id="f9b4b-114">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="f9b4b-114">Close the page.</span></span>

## <a name="set-up-a-hub-accessorial-charge"></a><span data-ttu-id="f9b4b-115">Központi kiegészítő szolgáltatások díj létrehozása</span><span class="sxs-lookup"><span data-stu-id="f9b4b-115">Set up a hub accessorial charge</span></span>
1. <span data-ttu-id="f9b4b-116">Lépjen a Szállításkezelés > Beállítás > Minősítés > Központi kiegészítő szolgáltatások díjai pontra.</span><span class="sxs-lookup"><span data-stu-id="f9b4b-116">Go to Transportation management > Setup > Rating > Hub accessorial charges.</span></span>
2. <span data-ttu-id="f9b4b-117">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f9b4b-117">Click New.</span></span>
3. <span data-ttu-id="f9b4b-118">Írjon be egy értéket a Központi kiegészítő szolgáltatások azonosító mezőbe.</span><span class="sxs-lookup"><span data-stu-id="f9b4b-118">In the Hub accessorial ID field, type a value.</span></span>
4. <span data-ttu-id="f9b4b-119">A Központ mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="f9b4b-119">In the Hub field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="f9b4b-120">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="f9b4b-120">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="f9b4b-121">A Központ pozíciója mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f9b4b-121">In the Hub position field, select an option.</span></span>
    * <span data-ttu-id="f9b4b-122">A költség lehet felvételi vagy lerakati.</span><span class="sxs-lookup"><span data-stu-id="f9b4b-122">You can either create the charge as a pickup or drop-off.</span></span> <span data-ttu-id="f9b4b-123">A választástól függően a költség a megfelelő szállítási szegmensre fog vonatkozni az útvonalon.</span><span class="sxs-lookup"><span data-stu-id="f9b4b-123">Depending on your selection the charge will be applied to the corresponding transportation segment on your route.</span></span>  
7. <span data-ttu-id="f9b4b-124">A Kiegészítő alapszolgáltatás mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="f9b4b-124">In the Accessorial master field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="f9b4b-125">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="f9b4b-125">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="f9b4b-126">Jelölje ki az előbb létrehozott alapadatot.</span><span class="sxs-lookup"><span data-stu-id="f9b4b-126">Select the master you just created.</span></span>  
9. <span data-ttu-id="f9b4b-127">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="f9b4b-127">Click Save.</span></span>
10. <span data-ttu-id="f9b4b-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="f9b4b-128">Close the page.</span></span>

