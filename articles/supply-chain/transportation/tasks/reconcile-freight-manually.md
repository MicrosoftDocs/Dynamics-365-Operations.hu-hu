--- 
title: "Fuvarlevél egyeztetése manuálisan"
description: "Ez az eljárás bemutatja, hogyan lehet manuálisan elvégezni a fuvaregyeztetést."
author: BibiSp
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 15148725664d839694ede8419213d881c7be83dd
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="reconcile-freight-manually"></a><span data-ttu-id="bc18d-103">Fuvarlevél egyeztetése manuálisan</span><span class="sxs-lookup"><span data-stu-id="bc18d-103">Reconcile freight manually</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bc18d-104">Ez az eljárás bemutatja, hogyan lehet manuálisan elvégezni a fuvaregyeztetést.</span><span class="sxs-lookup"><span data-stu-id="bc18d-104">This procedure shows how to reconcile freight manually.</span></span> <span data-ttu-id="bc18d-105">Ezt általában egy szállítási koordinátor végzi.</span><span class="sxs-lookup"><span data-stu-id="bc18d-105">This is typically done by a transportation coordinator.</span></span> <span data-ttu-id="bc18d-106">Az USMF bemutatócég adataiban használhatja ezt az eljárást.</span><span class="sxs-lookup"><span data-stu-id="bc18d-106">You can use this procedure in the USMF demo data company.</span></span>


## <a name="select-a-load-to-reconcile"></a><span data-ttu-id="bc18d-107">Válassza ki a rakományt az egyeztetéshez</span><span class="sxs-lookup"><span data-stu-id="bc18d-107">Select a load to reconcile</span></span>
1. <span data-ttu-id="bc18d-108">Ugorjon a Szállításkezelés > Tervezés > Rakománytervező munkaterület elemre.</span><span class="sxs-lookup"><span data-stu-id="bc18d-108">Go to Transportation management > Planning > Load planning workbench.</span></span>
2. <span data-ttu-id="bc18d-109">Törölje a Szállított és bevételezett elrejtése jelölőnégyzet jelölését.</span><span class="sxs-lookup"><span data-stu-id="bc18d-109">Clear the Hide shipped and received check box.</span></span> 
3. <span data-ttu-id="bc18d-110">A listában jelölje ki a rakományt, amelynek a rakományazonosítója 00006.</span><span class="sxs-lookup"><span data-stu-id="bc18d-110">In the list, select the load that has load ID 00006.</span></span>

## <a name="create-a-carrier-invoice"></a><span data-ttu-id="bc18d-111">Szállítói számla létrehozása</span><span class="sxs-lookup"><span data-stu-id="bc18d-111">Create a carrier invoice</span></span>
    * <span data-ttu-id="bc18d-112">Ha manuálisan végzi a fuvaregyeztetést, és nem kapja meg automatikusan a szállítói számlákat, a fuvarlevél alapján számlát hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="bc18d-112">If you reconcile freight manually and don’t receive carrier invoices automatically, you can create an invoice based on the freight bill.</span></span>  
1. <span data-ttu-id="bc18d-113">Kattintson a Kapcsolódó információ lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bc18d-113">Click Related information.</span></span>
2. <span data-ttu-id="bc18d-114">Kattintson a Fuvarlevél részletei lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bc18d-114">Click Freight bill details.</span></span>
3. <span data-ttu-id="bc18d-115">Kattintson a Fuvarlevélszámla generálása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bc18d-115">Click Generate freight bill invoice.</span></span>
4. <span data-ttu-id="bc18d-116">Érték beírása a Számla mezőbe.</span><span class="sxs-lookup"><span data-stu-id="bc18d-116">In the Invoice field, type a value.</span></span>
5. <span data-ttu-id="bc18d-117">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="bc18d-117">Click OK.</span></span>

## <a name="reconcile-the-invoice"></a><span data-ttu-id="bc18d-118">Számla egyeztetése</span><span class="sxs-lookup"><span data-stu-id="bc18d-118">Reconcile the invoice</span></span>
    * <span data-ttu-id="bc18d-119">Ha a fuvarlevél és a szállítói számla egyeztetését végzi, ez soronként történik.</span><span class="sxs-lookup"><span data-stu-id="bc18d-119">When you reconcile a carrier invoice and a freight bill, this is done line by line.</span></span>  
1. <span data-ttu-id="bc18d-120">Kattintson a Fuvarlevelek és számlák egyeztetése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bc18d-120">Click Match freight bills and invoices.</span></span>
2. <span data-ttu-id="bc18d-121">Bontsa ki a Számla részletei szakaszt.</span><span class="sxs-lookup"><span data-stu-id="bc18d-121">Expand the Invoice details section.</span></span>
3. <span data-ttu-id="bc18d-122">Bontsa ki a Nem egyeztetett fuvarlevél-adatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="bc18d-122">Expand the Unmatched freight bill details section.</span></span>
4. <span data-ttu-id="bc18d-123">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="bc18d-123">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="bc18d-124">Kattintson az Egyeztetés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bc18d-124">Click Match.</span></span>
6. <span data-ttu-id="bc18d-125">Bontsa ki az Egyeztetett fuvarlevél-adatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="bc18d-125">Expand the Matched freight bill details section.</span></span>

## <a name="submit-the-invoice-for-approval"></a><span data-ttu-id="bc18d-126">A számla elküldése jóváhagyásra</span><span class="sxs-lookup"><span data-stu-id="bc18d-126">Submit the invoice for approval</span></span>
1. <span data-ttu-id="bc18d-127">Kattintson az Elküldés jóváhagyásra elemre.</span><span class="sxs-lookup"><span data-stu-id="bc18d-127">Click Submit for approval.</span></span>
2. <span data-ttu-id="bc18d-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="bc18d-128">Close the page.</span></span>
3. <span data-ttu-id="bc18d-129">Szüntesse meg a Jóváhagyott elrejtése jelölőnégyzet bejelölését.</span><span class="sxs-lookup"><span data-stu-id="bc18d-129">Clear the Hide approved check box.</span></span> 
4. <span data-ttu-id="bc18d-130">Kattintson a Szállítói számlanaplók elemre.</span><span class="sxs-lookup"><span data-stu-id="bc18d-130">Click Vendor invoice journals.</span></span>
5. <span data-ttu-id="bc18d-131">Kattintson a Hivatkozási naplószám mezőben található hivatkozás megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="bc18d-131">Click to follow the link in the Reference journal number field.</span></span>
6. <span data-ttu-id="bc18d-132">Kattintson a Sorok pontra.</span><span class="sxs-lookup"><span data-stu-id="bc18d-132">Click Lines.</span></span>

