---
title: Fuvarlevél egyeztetése manuálisan
description: Ez az eljárás bemutatja, hogyan lehet manuálisan elvégezni a fuvaregyeztetést.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, TMSFreightBillDetail, TMSInvoiceTable, TMSFreightBillInvoiceReconcile, TMSInvoiceJournal, LedgerJournalTable, LedgerJournalTransDaily
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3b466db6d0568918b0833cc28e32c33168fac814
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3978313"
---
# <a name="reconcile-freight-manually"></a><span data-ttu-id="205fd-103">Fuvarlevél egyeztetése manuálisan</span><span class="sxs-lookup"><span data-stu-id="205fd-103">Reconcile freight manually</span></span>

<span data-ttu-id="205fd-104">[!include [banner](../../includes/banner.md)]]</span><span class="sxs-lookup"><span data-stu-id="205fd-104">[!include [banner](../../includes/banner.md)]]</span></span>

<span data-ttu-id="205fd-105">Ez az eljárás bemutatja, hogyan lehet manuálisan elvégezni a fuvaregyeztetést.</span><span class="sxs-lookup"><span data-stu-id="205fd-105">This procedure shows how to reconcile freight manually.</span></span> <span data-ttu-id="205fd-106">Ezt általában egy szállítási koordinátor végzi.</span><span class="sxs-lookup"><span data-stu-id="205fd-106">This is typically done by a transportation coordinator.</span></span> <span data-ttu-id="205fd-107">Az USMF bemutatócég adataiban használhatja ezt az eljárást.</span><span class="sxs-lookup"><span data-stu-id="205fd-107">You can use this procedure in the USMF demo data company.</span></span>


## <a name="select-a-load-to-reconcile"></a><span data-ttu-id="205fd-108">Válassza ki a rakományt az egyeztetéshez</span><span class="sxs-lookup"><span data-stu-id="205fd-108">Select a load to reconcile</span></span>
1. <span data-ttu-id="205fd-109">Ugorjon a Szállításkezelés > Tervezés > Rakománytervező munkaterület elemre.</span><span class="sxs-lookup"><span data-stu-id="205fd-109">Go to Transportation management > Planning > Load planning workbench.</span></span>
2. <span data-ttu-id="205fd-110">Törölje a Szállított és bevételezett elrejtése jelölőnégyzet jelölését.</span><span class="sxs-lookup"><span data-stu-id="205fd-110">Clear the Hide shipped and received check box.</span></span> 
3. <span data-ttu-id="205fd-111">A listában jelölje ki a rakományt, amelynek a rakományazonosítója 00006.</span><span class="sxs-lookup"><span data-stu-id="205fd-111">In the list, select the load that has load ID 00006.</span></span>

## <a name="create-a-carrier-invoice"></a><span data-ttu-id="205fd-112">Szállítói számla létrehozása</span><span class="sxs-lookup"><span data-stu-id="205fd-112">Create a carrier invoice</span></span>
<span data-ttu-id="205fd-113">Ha manuálisan végzi a fuvaregyeztetést, és nem kapja meg automatikusan a szállítói számlákat, a fuvarlevél alapján számlát hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="205fd-113">If you reconcile freight manually and don't receive carrier invoices automatically, you can create an invoice based on the freight bill.</span></span>  
1. <span data-ttu-id="205fd-114">Kattintson a Kapcsolódó információ lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="205fd-114">Click Related information.</span></span>
2. <span data-ttu-id="205fd-115">Kattintson a Fuvarlevél részletei lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="205fd-115">Click Freight bill details.</span></span>
3. <span data-ttu-id="205fd-116">Kattintson a Fuvarlevélszámla generálása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="205fd-116">Click Generate freight bill invoice.</span></span>
4. <span data-ttu-id="205fd-117">Érték beírása a Számla mezőbe.</span><span class="sxs-lookup"><span data-stu-id="205fd-117">In the Invoice field, type a value.</span></span>
5. <span data-ttu-id="205fd-118">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="205fd-118">Click OK.</span></span>

## <a name="reconcile-the-invoice"></a><span data-ttu-id="205fd-119">Számla egyeztetése</span><span class="sxs-lookup"><span data-stu-id="205fd-119">Reconcile the invoice</span></span>
<span data-ttu-id="205fd-120">Ha a fuvarlevél és a szállítói számla egyeztetését végzi, ez soronként történik.</span><span class="sxs-lookup"><span data-stu-id="205fd-120">When you reconcile a carrier invoice and a freight bill, this is done line by line.</span></span>  
1. <span data-ttu-id="205fd-121">Kattintson a Fuvarlevelek és számlák egyeztetése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="205fd-121">Click Match freight bills and invoices.</span></span>
2. <span data-ttu-id="205fd-122">Bontsa ki a Számla részletei szakaszt.</span><span class="sxs-lookup"><span data-stu-id="205fd-122">Expand the Invoice details section.</span></span>
3. <span data-ttu-id="205fd-123">Bontsa ki a Nem egyeztetett fuvarlevél-adatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="205fd-123">Expand the Unmatched freight bill details section.</span></span>
4. <span data-ttu-id="205fd-124">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="205fd-124">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="205fd-125">Kattintson az Egyeztetés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="205fd-125">Click Match.</span></span>
6. <span data-ttu-id="205fd-126">Bontsa ki az Egyeztetett fuvarlevél-adatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="205fd-126">Expand the Matched freight bill details section.</span></span>

## <a name="submit-the-invoice-for-approval"></a><span data-ttu-id="205fd-127">A számla elküldése jóváhagyásra</span><span class="sxs-lookup"><span data-stu-id="205fd-127">Submit the invoice for approval</span></span>
1. <span data-ttu-id="205fd-128">Kattintson az Elküldés jóváhagyásra elemre.</span><span class="sxs-lookup"><span data-stu-id="205fd-128">Click Submit for approval.</span></span>
2. <span data-ttu-id="205fd-129">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="205fd-129">Close the page.</span></span>
3. <span data-ttu-id="205fd-130">Szüntesse meg a Jóváhagyott elrejtése jelölőnégyzet bejelölését.</span><span class="sxs-lookup"><span data-stu-id="205fd-130">Clear the Hide approved check box.</span></span> 
4. <span data-ttu-id="205fd-131">Kattintson a Szállítói számlanaplók elemre.</span><span class="sxs-lookup"><span data-stu-id="205fd-131">Click Vendor invoice journals.</span></span>
5. <span data-ttu-id="205fd-132">Kattintson a Hivatkozási naplószám mezőben található hivatkozás megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="205fd-132">Click to follow the link in the Reference journal number field.</span></span>
6. <span data-ttu-id="205fd-133">Kattintson a Sorok pontra.</span><span class="sxs-lookup"><span data-stu-id="205fd-133">Click Lines.</span></span>

