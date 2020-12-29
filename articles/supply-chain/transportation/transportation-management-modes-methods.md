---
title: Szállításkezelési módok és módszerek
description: Ez a témakör azt mutatja be, hogyan lehet beállítani a Szállítási módokat és módszereket.
author: Henrikan
manager: tfehr
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: ceb3930cdb7764f846e88edfff6906b902a7f5fa
ms.sourcegitcommit: fe7ac653efcb1ac6318083f482394b96ed82b4c7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2020
ms.locfileid: "4429983"
---
# <a name="transportation-management-modes-and-methods"></a><span data-ttu-id="bd214-103">Szállításkezelési módok és módszerek</span><span class="sxs-lookup"><span data-stu-id="bd214-103">Transportation management modes and methods</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bd214-104">A szállításkezelési mód azt a szállítási módot mutatja, amelyet a szállító a fuvarszállítmányokhoz használ, például a kisebb, mint a lload (LTL), truckload vagy a parcella.</span><span class="sxs-lookup"><span data-stu-id="bd214-104">The transportation management  mode represents the type of transport that the carrier uses for freight deliveries, such as less than load (LTL), truckload (TL), or parcel.</span></span> <span data-ttu-id="bd214-105">A szállítási mód azt a szállítási módot mutatja, amelyet a szállító a fuvarszállítmányokhoz használ, például légi, földi, vízi vagy vasúti fuvarozás.</span><span class="sxs-lookup"><span data-stu-id="bd214-105">The transportation method represents the form of transport that the carrier uses for freight deliveries, such as air, ground, ocean, or rail.</span></span>

<span data-ttu-id="bd214-106">A módok és a szállítási módszerek több kontextusban használatosak.</span><span class="sxs-lookup"><span data-stu-id="bd214-106">Modes and transportation methods are used in several contexts.</span></span> <span data-ttu-id="bd214-107">A rendszer csak az útvonalakban használt módokat használja, a szállítmányozók és a szállítmányozói szolgáltatások beállításakor pedig mind a módok, mind a szállítási módszerek használatosak.</span><span class="sxs-lookup"><span data-stu-id="bd214-107">Only modes are used in route plans, while both modes and transportation methods are used when setting up shipping carriers and carrier services.</span></span> <span data-ttu-id="bd214-108">Nem létezik explicit kapcsolat vagy hierarchia a módok és a szállítási módszerek között.</span><span class="sxs-lookup"><span data-stu-id="bd214-108">No explicit relationship or hierarchy exists between modes and transportation methods.</span></span>

## <a name="create-a-mode"></a><span data-ttu-id="bd214-109">Mód létrehozása</span><span class="sxs-lookup"><span data-stu-id="bd214-109">Create a mode</span></span>

<span data-ttu-id="bd214-110">Mód létrehozásához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="bd214-110">To create a mode, follow these steps:</span></span>

1. <span data-ttu-id="bd214-111">Ugorjon a **Szállításkezelés \> Beállítás \> Szállítmányozók \> Mód** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bd214-111">Go to **Transportation management \> Setup \> Carriers \> Mode**.</span></span>
1. <span data-ttu-id="bd214-112">Válassza ki az **Új** lehetőséget egy új mód létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="bd214-112">Select **New** to create a new mode.</span></span>
1. <span data-ttu-id="bd214-113">Adjon meg egy egyedi Azonosítót és a mód, jól felismerhető nevét.</span><span class="sxs-lookup"><span data-stu-id="bd214-113">Enter a unique ID and a descriptive name for the mode.</span></span>
1. <span data-ttu-id="bd214-114">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="bd214-114">Close the page.</span></span>

## <a name="create-a-transportation-method"></a><span data-ttu-id="bd214-115">Szállítmányozási mód létrehozása</span><span class="sxs-lookup"><span data-stu-id="bd214-115">Create a transportation method</span></span>

<span data-ttu-id="bd214-116">A szállítmányozási módszer létrehozásához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="bd214-116">To create a transportation method, follow these steps:</span></span>

1. <span data-ttu-id="bd214-117">Ugorjon a **Szállításkezelés \> Beállítás \> Szállítmányozók \> Szállítmányozási módszerek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bd214-117">Go to **Transportation management \> Setup \> Carriers \> Transportation methods**.</span></span>
1. <span data-ttu-id="bd214-118">Ha új szállímányozási módszert szeretne létrehozni, kattintson az **Új** gombra.</span><span class="sxs-lookup"><span data-stu-id="bd214-118">Select **New** to create a new transportation method.</span></span>
1. <span data-ttu-id="bd214-119">Adjon meg egy egyedi Azonosítót és a szállítási mód jól felismerhető nevét.</span><span class="sxs-lookup"><span data-stu-id="bd214-119">Enter a unique ID and descriptive name for the transportation method.</span></span>
1. <span data-ttu-id="bd214-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="bd214-120">Close the page.</span></span>
