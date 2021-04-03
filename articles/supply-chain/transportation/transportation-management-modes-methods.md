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
ms.openlocfilehash: 0d41d8665252a978962bf6a2e307dce3dad64a5b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233439"
---
# <a name="transportation-management-modes-and-methods"></a><span data-ttu-id="aacc3-103">Szállításkezelési módok és módszerek</span><span class="sxs-lookup"><span data-stu-id="aacc3-103">Transportation management modes and methods</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aacc3-104">A szállításkezelési mód azt a szállítási módot mutatja, amelyet a szállító a fuvarszállítmányokhoz használ, például a kisebb, mint a lload (LTL), truckload vagy a parcella.</span><span class="sxs-lookup"><span data-stu-id="aacc3-104">The transportation management  mode represents the type of transport that the carrier uses for freight deliveries, such as less than load (LTL), truckload (TL), or parcel.</span></span> <span data-ttu-id="aacc3-105">A szállítási mód azt a szállítási módot mutatja, amelyet a szállító a fuvarszállítmányokhoz használ, például légi, földi, vízi vagy vasúti fuvarozás.</span><span class="sxs-lookup"><span data-stu-id="aacc3-105">The transportation method represents the form of transport that the carrier uses for freight deliveries, such as air, ground, ocean, or rail.</span></span>

<span data-ttu-id="aacc3-106">A módok és a szállítási módszerek több kontextusban használatosak.</span><span class="sxs-lookup"><span data-stu-id="aacc3-106">Modes and transportation methods are used in several contexts.</span></span> <span data-ttu-id="aacc3-107">A rendszer csak az útvonalakban használt módokat használja, a szállítmányozók és a szállítmányozói szolgáltatások beállításakor pedig mind a módok, mind a szállítási módszerek használatosak.</span><span class="sxs-lookup"><span data-stu-id="aacc3-107">Only modes are used in route plans, while both modes and transportation methods are used when setting up shipping carriers and carrier services.</span></span> <span data-ttu-id="aacc3-108">Nem létezik explicit kapcsolat vagy hierarchia a módok és a szállítási módszerek között.</span><span class="sxs-lookup"><span data-stu-id="aacc3-108">No explicit relationship or hierarchy exists between modes and transportation methods.</span></span>

## <a name="create-a-mode"></a><span data-ttu-id="aacc3-109">Mód létrehozása</span><span class="sxs-lookup"><span data-stu-id="aacc3-109">Create a mode</span></span>

<span data-ttu-id="aacc3-110">Mód létrehozásához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="aacc3-110">To create a mode, follow these steps:</span></span>

1. <span data-ttu-id="aacc3-111">Ugorjon a **Szállításkezelés \> Beállítás \> Szállítmányozók \> Mód** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="aacc3-111">Go to **Transportation management \> Setup \> Carriers \> Mode**.</span></span>
1. <span data-ttu-id="aacc3-112">Válassza ki az **Új** lehetőséget egy új mód létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="aacc3-112">Select **New** to create a new mode.</span></span>
1. <span data-ttu-id="aacc3-113">Adjon meg egy egyedi Azonosítót és a mód, jól felismerhető nevét.</span><span class="sxs-lookup"><span data-stu-id="aacc3-113">Enter a unique ID and a descriptive name for the mode.</span></span>
1. <span data-ttu-id="aacc3-114">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="aacc3-114">Close the page.</span></span>

## <a name="create-a-transportation-method"></a><span data-ttu-id="aacc3-115">Szállítmányozási mód létrehozása</span><span class="sxs-lookup"><span data-stu-id="aacc3-115">Create a transportation method</span></span>

<span data-ttu-id="aacc3-116">A szállítmányozási módszer létrehozásához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="aacc3-116">To create a transportation method, follow these steps:</span></span>

1. <span data-ttu-id="aacc3-117">Ugorjon a **Szállításkezelés \> Beállítás \> Szállítmányozók \> Szállítmányozási módszerek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="aacc3-117">Go to **Transportation management \> Setup \> Carriers \> Transportation methods**.</span></span>
1. <span data-ttu-id="aacc3-118">Ha új szállímányozási módszert szeretne létrehozni, kattintson az **Új** gombra.</span><span class="sxs-lookup"><span data-stu-id="aacc3-118">Select **New** to create a new transportation method.</span></span>
1. <span data-ttu-id="aacc3-119">Adjon meg egy egyedi Azonosítót és a szállítási mód jól felismerhető nevét.</span><span class="sxs-lookup"><span data-stu-id="aacc3-119">Enter a unique ID and descriptive name for the transportation method.</span></span>
1. <span data-ttu-id="aacc3-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="aacc3-120">Close the page.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]