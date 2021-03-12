---
title: " Pénzügyi dimenziók létrehozása POS-pénztárgépekhez és a dimenzióértékek konfigurálása a pénztárgépeken"
description: Ez az eljárás pénzügyi dimenziók, (POS-) pénztárgépek részére történő létrehozását mutatja be, illetve azt, hogy hogyan konfigurálja a pénzügyi dimenzióértékeket a pénztárgépeken.
author: jashanno
manager: AnnBe
ms.date: 11/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c51c77f4b9f411ae45fb955032aa40cb34738e9a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4964770"
---
# <a name="create-financial-dimensions-for-pos-registers-and-configure-dimension-values-on-registers"></a><span data-ttu-id="e3e60-103"> Pénzügyi dimenziók létrehozása POS-pénztárgépekhez és a dimenzióértékek konfigurálása a pénztárgépeken</span><span class="sxs-lookup"><span data-stu-id="e3e60-103">Create financial dimensions for POS registers and configure dimension values on registers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e3e60-104">Ez az eljárás pénzügyi dimenziók, (POS-) pénztárgépek részére történő létrehozását mutatja be, illetve azt, hogy hogyan konfigurálja a pénzügyi dimenzióértékeket a pénztárgépeken.</span><span class="sxs-lookup"><span data-stu-id="e3e60-104">This procedure walks through creating financial dimensions for point of sale (POS) registers, and demonstrates how to configure financial dimension values on registers.</span></span> <span data-ttu-id="e3e60-105">Ez az eljárás nem tér ki olyan kapcsolódó lépésekre, mint a dimenziókészletek és számlastruktúrák létrehozása.</span><span class="sxs-lookup"><span data-stu-id="e3e60-105">This procedure doesn't include other related steps, such as creating dimension sets and account structures.</span></span> <span data-ttu-id="e3e60-106">Ezeket a feladatokat más témakörök alatt találja meg.</span><span class="sxs-lookup"><span data-stu-id="e3e60-106">Those tasks can be found in other topics.</span></span> <span data-ttu-id="e3e60-107">Ez a felvétel az USRT bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="e3e60-107">This recording uses USRT demo company.</span></span>

1. <span data-ttu-id="e3e60-108">Ugrás a következő útvonalra: Főkönyv > Számlatükör > Dimenziók > Pénzügyi dimenziók.</span><span class="sxs-lookup"><span data-stu-id="e3e60-108">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="e3e60-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e3e60-109">Click New.</span></span>
3. <span data-ttu-id="e3e60-110">Kötelező kiválasztani egy lehetőséget a használandó értékek forrásaként.</span><span class="sxs-lookup"><span data-stu-id="e3e60-110">In the Use values from field, select an option.</span></span>
4. <span data-ttu-id="e3e60-111">Írjon be egy értéket a Dimenziónév mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e3e60-111">In the Dimension name field, type a value.</span></span>
5. <span data-ttu-id="e3e60-112">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="e3e60-112">Click Activate.</span></span>
6. <span data-ttu-id="e3e60-113">Kattintson a Bezárás gombra.</span><span class="sxs-lookup"><span data-stu-id="e3e60-113">Click Close.</span></span>
7. <span data-ttu-id="e3e60-114">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="e3e60-114">Click Activate.</span></span>
8. <span data-ttu-id="e3e60-115">Kattintson a Dimenzióértékek elemre.</span><span class="sxs-lookup"><span data-stu-id="e3e60-115">Click Dimension values.</span></span>
9. <span data-ttu-id="e3e60-116">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e3e60-116">Close the page.</span></span>
10. <span data-ttu-id="e3e60-117">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e3e60-117">Click Save.</span></span>
11. <span data-ttu-id="e3e60-118">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e3e60-118">Close the page.</span></span>
12. <span data-ttu-id="e3e60-119">Ugorjon a Kiskereskedelem és kereskedelem > Csatorna beállítás > Pénztár beállítás > Pénztárgépek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e3e60-119">Go to Retail and Commerce > Channel setup > POS setup > Registers.</span></span>
13. <span data-ttu-id="e3e60-120">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="e3e60-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="e3e60-121">Váltson a Pénzügyi dimenziók szakasz kibontására.</span><span class="sxs-lookup"><span data-stu-id="e3e60-121">Toggle the expansion of the Financial dimensions section.</span></span>
15. <span data-ttu-id="e3e60-122">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e3e60-122">Click Edit.</span></span>
16. <span data-ttu-id="e3e60-123">A Terminál mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e3e60-123">In the Terminal field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="e3e60-124">A listában keresse meg és válassza ki az éppen frissített jegyzék dimenzióértékét.</span><span class="sxs-lookup"><span data-stu-id="e3e60-124">In the list, find and select the dimension value for the register being updated.</span></span>
18. <span data-ttu-id="e3e60-125">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e3e60-125">Click Save.</span></span>

