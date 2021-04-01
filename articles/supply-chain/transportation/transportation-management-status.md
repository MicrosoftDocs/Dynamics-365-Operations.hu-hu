---
title: Szállításkezelési állapotok
description: Ez a témakör azt mutatja be, hogyan lehet egy szállítási állapotot létrehozni, és az állapotot a szállítmányozó állapotához rendelni.
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
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: fb0d98729046330037f96ab7e13a1bf897e35a1e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233343"
---
# <a name="transportation-management-statuses"></a><span data-ttu-id="5786c-103">Szállításkezelési állapotok</span><span class="sxs-lookup"><span data-stu-id="5786c-103">Transportation management statuses</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5786c-104">A rendelkezésre álló szállítási állapotok szállítási törzskódjainak beállításával értelmezheti a szállítmányozók kódjait.</span><span class="sxs-lookup"><span data-stu-id="5786c-104">Set up master codes for transportation statuses to interpret codes that are provided by your shipping carriers.</span></span> <span data-ttu-id="5786c-105">Ez lehetővé teszi a szállítmányozók számára, hog megadják az állapotukat.</span><span class="sxs-lookup"><span data-stu-id="5786c-105">This lets you integrate with shipping carriers to provide a status.</span></span> <span data-ttu-id="5786c-106">A szállítási törzskódhoz meghatározott szállítási állapot alapján követheti nyomon egy rakomány, egy szállítás vagy egy tároló állapotát.</span><span class="sxs-lookup"><span data-stu-id="5786c-106">The transportation status that you provide for a transportation master status code can help you track the status of a load, shipment, or container.</span></span> <span data-ttu-id="5786c-107">Egy rakomány, szállítmány vagy tároló konkrét szállítási állapota csak adatintegrációval frissíthető, és nem a felhasználói felületen keresztül.</span><span class="sxs-lookup"><span data-stu-id="5786c-107">The specific transportation status for a load, shipment, or container can only be updated through data integration and not manually through the user interface.</span></span>

## <a name="create-a-transportation-status"></a><span data-ttu-id="5786c-108">Szállítmányozási állapot létrehozása</span><span class="sxs-lookup"><span data-stu-id="5786c-108">Create a transportation status</span></span>

<span data-ttu-id="5786c-109">A szállítmányozási állapot létrehozásához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="5786c-109">To create a transportation status, follow these steps:</span></span>

1. <span data-ttu-id="5786c-110">Ugorjon a **Szállításkezelés \> Beállítás \> Szállítmányozási törzsállapotok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5786c-110">Go to **Transportation management \> Setup \> Transportation status masters**.</span></span>
1. <span data-ttu-id="5786c-111">Az új szállítási törzsállapot létrehozásához kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="5786c-111">Select **New** to create a transportation status master.</span></span>
1. <span data-ttu-id="5786c-112">A **Szállítmányozási törzsállapot** mezőbe írja be a szállítási állapot egyedi kódját.</span><span class="sxs-lookup"><span data-stu-id="5786c-112">In the **Transportation status master** field, enter a unique code for the transportation status.</span></span>
1. <span data-ttu-id="5786c-113">A **Szállítás típusa** mezőben válassza ki a *Szállítmányozó* vagy a *Központ* lehetőséget a szállítás típusának.</span><span class="sxs-lookup"><span data-stu-id="5786c-113">In the **Transportation type** field, select either *Shipping carrier* or *Hub* as the type of transportation.</span></span>
1. <span data-ttu-id="5786c-114">Adjon meg egy nevet és egy szállítási állapotot.</span><span class="sxs-lookup"><span data-stu-id="5786c-114">Enter a name and transportation status.</span></span>
1. <span data-ttu-id="5786c-115">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5786c-115">Close the page.</span></span>

## <a name="map-a-transportation-status-to-a-carrier-status"></a><span data-ttu-id="5786c-116">Szállítási állapot hozzárendelése a szállítmányozó állapotához</span><span class="sxs-lookup"><span data-stu-id="5786c-116">Map a transportation status to a carrier status</span></span>

<span data-ttu-id="5786c-117">Ha egy szállítási állapotot szállítmányozói állapothoz kíván hozzárendelni, hajtsa végre az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="5786c-117">To map a transportation status to a carrier status, follow these steps:</span></span>

1. <span data-ttu-id="5786c-118">Ugorjon a **Szállításkezelés \> Beállítás \> Szállítmányozók \> Szállítmányozó szállítási állapota** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5786c-118">Go to **Transportation management \> Setup \> Carriers \> Carrier transportation status**.</span></span>
1. <span data-ttu-id="5786c-119">Az **Új** gombra kattitnva rendelhet össze egy szállítmányozói kódot egy szállítói állapot törzskódhoz.</span><span class="sxs-lookup"><span data-stu-id="5786c-119">Select **New** to map a code from a shipping carrier to a transportation status master code.</span></span>
1. <span data-ttu-id="5786c-120">Válassza ki a szállítmányozó és a szállítmányozási szolgáltatás egyedi azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="5786c-120">Select the unique ID for the shipping carrier and the carrier service.</span></span>
1. <span data-ttu-id="5786c-121">Válassza ki azt a szállítási állapotkódot, amelyet a kiválasztott szállítmányozó kódjához hozzá akar rendelni.</span><span class="sxs-lookup"><span data-stu-id="5786c-121">Select the transportation status code that you want to map to the selected shipping carrier's code.</span></span>
1. <span data-ttu-id="5786c-122">Adja meg a szállítmányozó által használt külső kódot.</span><span class="sxs-lookup"><span data-stu-id="5786c-122">Enter the external code that is used by the shipping carrier.</span></span>
1. <span data-ttu-id="5786c-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5786c-123">Close the page.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]