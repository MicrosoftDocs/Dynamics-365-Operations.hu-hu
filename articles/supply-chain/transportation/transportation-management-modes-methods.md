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
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: b9b548212c6f1f3faac56cd7ca182d84cc339bd2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4973910"
---
# <a name="transportation-management-modes-and-methods"></a><span data-ttu-id="e8a70-103">Szállításkezelési módok és módszerek</span><span class="sxs-lookup"><span data-stu-id="e8a70-103">Transportation management modes and methods</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e8a70-104">A szállításkezelési mód azt a szállítási módot mutatja, amelyet a szállító a fuvarszállítmányokhoz használ, például a kisebb, mint a lload (LTL), truckload vagy a parcella.</span><span class="sxs-lookup"><span data-stu-id="e8a70-104">The transportation management  mode represents the type of transport that the carrier uses for freight deliveries, such as less than load (LTL), truckload (TL), or parcel.</span></span> <span data-ttu-id="e8a70-105">A szállítási mód azt a szállítási módot mutatja, amelyet a szállító a fuvarszállítmányokhoz használ, például légi, földi, vízi vagy vasúti fuvarozás.</span><span class="sxs-lookup"><span data-stu-id="e8a70-105">The transportation method represents the form of transport that the carrier uses for freight deliveries, such as air, ground, ocean, or rail.</span></span>

<span data-ttu-id="e8a70-106">A módok és a szállítási módszerek több kontextusban használatosak.</span><span class="sxs-lookup"><span data-stu-id="e8a70-106">Modes and transportation methods are used in several contexts.</span></span> <span data-ttu-id="e8a70-107">A rendszer csak az útvonalakban használt módokat használja, a szállítmányozók és a szállítmányozói szolgáltatások beállításakor pedig mind a módok, mind a szállítási módszerek használatosak.</span><span class="sxs-lookup"><span data-stu-id="e8a70-107">Only modes are used in route plans, while both modes and transportation methods are used when setting up shipping carriers and carrier services.</span></span> <span data-ttu-id="e8a70-108">Nem létezik explicit kapcsolat vagy hierarchia a módok és a szállítási módszerek között.</span><span class="sxs-lookup"><span data-stu-id="e8a70-108">No explicit relationship or hierarchy exists between modes and transportation methods.</span></span>

## <a name="create-a-mode"></a><span data-ttu-id="e8a70-109">Mód létrehozása</span><span class="sxs-lookup"><span data-stu-id="e8a70-109">Create a mode</span></span>

<span data-ttu-id="e8a70-110">Mód létrehozásához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="e8a70-110">To create a mode, follow these steps:</span></span>

1. <span data-ttu-id="e8a70-111">Ugorjon a **Szállításkezelés \> Beállítás \> Szállítmányozók \> Mód** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e8a70-111">Go to **Transportation management \> Setup \> Carriers \> Mode**.</span></span>
1. <span data-ttu-id="e8a70-112">Válassza ki az **Új** lehetőséget egy új mód létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="e8a70-112">Select **New** to create a new mode.</span></span>
1. <span data-ttu-id="e8a70-113">Adjon meg egy egyedi Azonosítót és a mód, jól felismerhető nevét.</span><span class="sxs-lookup"><span data-stu-id="e8a70-113">Enter a unique ID and a descriptive name for the mode.</span></span>
1. <span data-ttu-id="e8a70-114">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e8a70-114">Close the page.</span></span>

## <a name="create-a-transportation-method"></a><span data-ttu-id="e8a70-115">Szállítmányozási mód létrehozása</span><span class="sxs-lookup"><span data-stu-id="e8a70-115">Create a transportation method</span></span>

<span data-ttu-id="e8a70-116">A szállítmányozási módszer létrehozásához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="e8a70-116">To create a transportation method, follow these steps:</span></span>

1. <span data-ttu-id="e8a70-117">Ugorjon a **Szállításkezelés \> Beállítás \> Szállítmányozók \> Szállítmányozási módszerek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e8a70-117">Go to **Transportation management \> Setup \> Carriers \> Transportation methods**.</span></span>
1. <span data-ttu-id="e8a70-118">Ha új szállímányozási módszert szeretne létrehozni, kattintson az **Új** gombra.</span><span class="sxs-lookup"><span data-stu-id="e8a70-118">Select **New** to create a new transportation method.</span></span>
1. <span data-ttu-id="e8a70-119">Adjon meg egy egyedi Azonosítót és a szállítási mód jól felismerhető nevét.</span><span class="sxs-lookup"><span data-stu-id="e8a70-119">Enter a unique ID and descriptive name for the transportation method.</span></span>
1. <span data-ttu-id="e8a70-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e8a70-120">Close the page.</span></span>
