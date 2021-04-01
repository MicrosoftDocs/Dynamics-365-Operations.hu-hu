---
title: Szállításkezelési számsorozat
description: Ez a témakör azt mutatja be, hogyan lehet beállítani számsorozatokat a szállításkezeléshez.
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
ms.openlocfilehash: cc19110f481c11ab28532d69a4689c1db048f6c3
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233367"
---
# <a name="transportation-management-number-sequence"></a><span data-ttu-id="7a461-103">Szállításkezelési számsorozat</span><span class="sxs-lookup"><span data-stu-id="7a461-103">Transportation management number sequence</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7a461-104">A szállításkezelési modul **Számsorozatok** lapján állíthatja be a különböző pro számokat.</span><span class="sxs-lookup"><span data-stu-id="7a461-104">Use the **Number sequences** page in the transportation management module to set up various pro numbers.</span></span> <span data-ttu-id="7a461-105">A pro számokat a szállítmányozók használják az egyes szállítmányok haladásának rendszerezésére és nyomon követésére.</span><span class="sxs-lookup"><span data-stu-id="7a461-105">Pro numbers are used by carriers to organize and track the progress of each shipment.</span></span>

## <a name="create-a-number-sequence-for-a-pro-number"></a><span data-ttu-id="7a461-106">Hozzon létre egy számsorozatot egy pro számhoz.</span><span class="sxs-lookup"><span data-stu-id="7a461-106">Create a number sequence for a pro number</span></span>

<span data-ttu-id="7a461-107">Egy pro számhoz tartozó számsorozat létrehozásához tegye a következőket:</span><span class="sxs-lookup"><span data-stu-id="7a461-107">To create a number sequence for a pro number, do the following:</span></span>

1. <span data-ttu-id="7a461-108">Ugorjon a **Szállításkezelés \> Beállítás \> Szállítmányozók \> Számsorozatok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7a461-108">Go to **Transportation management \> Setup \> Carriers \> Number sequences**.</span></span>
1. <span data-ttu-id="7a461-109">Válassza ki az **Új** lehetőséget egy új számsorozat létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="7a461-109">Select **New** to create a new number sequence.</span></span>
1. <span data-ttu-id="7a461-110">Adjon meg egy egyedi Azonosítót és a számsorozat jól felismerhető nevét.</span><span class="sxs-lookup"><span data-stu-id="7a461-110">Enter a unique ID and descriptive name for the number sequence.</span></span>
1. <span data-ttu-id="7a461-111">A **Számsorozat típusa** mezőben a *Pro szám* az egyetlen lehetőség.</span><span class="sxs-lookup"><span data-stu-id="7a461-111">In the **Number sequence type** field, *Pro number* is the only option.</span></span>
1. <span data-ttu-id="7a461-112">A **Számjegyellenőrzés** mezőben a *Számjegyellenőrzés* az egyetlen lehetőség, és általános motorként van beállítva.</span><span class="sxs-lookup"><span data-stu-id="7a461-112">In the **Check digit** field, *Check digit* is the only option and is set up as a generic engine.</span></span>
1. <span data-ttu-id="7a461-113">A **Sorozat** gyorslapján adja meg a sorszám adatait.</span><span class="sxs-lookup"><span data-stu-id="7a461-113">On the **Sequence** FastTab, provide information about the sequence.</span></span>
1. <span data-ttu-id="7a461-114">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7a461-114">Close the page.</span></span>

## <a name="link-a-number-sequence-to-a-shipping-carrier"></a><span data-ttu-id="7a461-115">Számsorozat csatolása szállítmányozóhoz</span><span class="sxs-lookup"><span data-stu-id="7a461-115">Link a number sequence to a shipping carrier</span></span>

<span data-ttu-id="7a461-116">Ha egy számsorozatot a szállítmányozóhoz kíván kapcsolni, hajtsa végre a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="7a461-116">To link a number sequence to a carrier, do the following:</span></span>

1. <span data-ttu-id="7a461-117">Ugorjon a **Szállításkezelés \> Beállítás \> Szállítmányozók \> Szállítmányozók** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7a461-117">Go to **Transportation management \> Setup \> Carriers \> Shipping carriers**.</span></span>
1. <span data-ttu-id="7a461-118">Válasszon ki egy szállítmányozót.</span><span class="sxs-lookup"><span data-stu-id="7a461-118">Select a shipping carrier.</span></span>
1. <span data-ttu-id="7a461-119">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="7a461-119">Select **Edit**.</span></span>
1. <span data-ttu-id="7a461-120">Válasszon egy beállítást az **Áttekintés** gyorslap **Pro számsorozarok** mezőjében.</span><span class="sxs-lookup"><span data-stu-id="7a461-120">On the **Overview** FastTab, select an option in the **Pro number sequence** field.</span></span>
1. <span data-ttu-id="7a461-121">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7a461-121">Close the page.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]