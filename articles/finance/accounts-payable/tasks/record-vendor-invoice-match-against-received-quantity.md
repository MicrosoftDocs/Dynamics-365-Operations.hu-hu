---
title: A szállítói számlák rögzítése és összevetése a bevételezett mennyiséggel
description: Amikor egy beszerzési rendelés után egy termékekről vagy szolgáltatásokról kiállított szállítói számlát fogad be, az üzleti folyamat megkövetelheti, hogy a számla kifizetésének a jóváhagyását megelőzően az áruk és szolgáltatások be legyenek vételezve.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 66d84f497775ce4f988242dd2b327bf4854faef5
ms.sourcegitcommit: ba1c76497acc9afba85257976f0d4e96836871d1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/04/2019
ms.locfileid: "2890419"
---
# <a name="record-vendor-invoice-and-match-against-received-quantity"></a><span data-ttu-id="cd4ac-103">A szállítói számlák rögzítése és összevetése a bevételezett mennyiséggel</span><span class="sxs-lookup"><span data-stu-id="cd4ac-103">Record vendor invoice and match against received quantity</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cd4ac-104">Amikor egy beszerzési rendelés után egy termékekről vagy szolgáltatásokról kiállított szállítói számlát fogad be, az üzleti folyamat megkövetelheti, hogy a számla kifizetésének a jóváhagyását megelőzően az áruk és szolgáltatások be legyenek vételezve.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-104">When you receive an invoice from a vendor for goods or services on a purchase order, the business processes might require that the goods or services be received before the invoice can be approved for payment.</span></span> <span data-ttu-id="cd4ac-105">Mielőtt elkezdené a beállítást, győződjön meg arról, hogy a Számlaegyeztetés konfigurációs kulcs be van állítva.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-105">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span> 

<span data-ttu-id="cd4ac-106">A Kötelezettségek paraméterei lapon győződjön meg róla, hogy a Számlaegyeztetés ellenőrzés beállítás van kiválasztva, a Számla feladása eltérésekkel mező Jóváhagyás szükséges értékű, és a Soregyeztetés irányelv mező Háromirányú egyeztetés értékű.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-106">In the Accounts payable parameters page, ensure that the Enable invoice matching validation option is selected, the Post invoice with discrepancies field is set to Require approval, and the Line matching policy field is set to Three-way matching.</span></span>

<span data-ttu-id="cd4ac-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-107">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="cd4ac-108">A kötelezettségeket kezelő vezető vagy a könyvelésért felelős vezető ezeket a lépéseket hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-108">The accounts payable manager or accounting manager role would perform these steps.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="cd4ac-109">Beszerzési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="cd4ac-109">Create a purchase order</span></span>
1. <span data-ttu-id="cd4ac-110">Ugrás az összes beszerzési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-110">Go to All purchase orders.</span></span>
2. <span data-ttu-id="cd4ac-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-111">Click New.</span></span>
3. <span data-ttu-id="cd4ac-112">A Szállítói számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-112">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="cd4ac-113">Írjon be egy értéket a Szállítói számla mezőbe.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-113">In the Vendor account field, type a value.</span></span>
5. <span data-ttu-id="cd4ac-114">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-114">Click OK.</span></span>
6. <span data-ttu-id="cd4ac-115">Kattintson az Új sor hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-115">Click Add line.</span></span>
7. <span data-ttu-id="cd4ac-116">A cikkmezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-116">In the Item number field, type a value.</span></span>
8. <span data-ttu-id="cd4ac-117">A Művelet panelen kattintson a Beszerzés elemre.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-117">On the Action Pane, click Purchase.</span></span>
9. <span data-ttu-id="cd4ac-118">Kattintson a Megerősítés gombra.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-118">Click Confirm.</span></span>

## <a name="post-a-product-receipt"></a><span data-ttu-id="cd4ac-119">Egy Termékbevételezés feladása</span><span class="sxs-lookup"><span data-stu-id="cd4ac-119">Post a product receipt</span></span>
1. <span data-ttu-id="cd4ac-120">A Művelet panelen kattintson a Bevételezés elemre.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-120">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="cd4ac-121">Kattintson a Termékbevételezés elemre.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-121">Click Product receipt.</span></span>
3. <span data-ttu-id="cd4ac-122">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-122">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="cd4ac-123">Írjon be egy értéket a Termékbevételezés mezőbe.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-123">In the Product receipt field, type a value.</span></span>
5. <span data-ttu-id="cd4ac-124">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-124">Click OK.</span></span>

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a><span data-ttu-id="cd4ac-125">Szállítói számla rögzítése és egyeztetése a termékbevételezésekkel</span><span class="sxs-lookup"><span data-stu-id="cd4ac-125">Record and match a vendor invoice to a product receipt</span></span>
1. <span data-ttu-id="cd4ac-126">A Művelet panelen kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-126">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="cd4ac-127">Kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-127">Click Invoice.</span></span>
3. <span data-ttu-id="cd4ac-128">Érték beírása a Szám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-128">In the Number field, type a value.</span></span>
4. <span data-ttu-id="cd4ac-129">Kattintson az Alapértelmezett forrás: Rendelt mennyiségre a legördülő párbeszédablak megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-129">Click Default from: Ordered quantity to open the drop dialog.</span></span>
5. <span data-ttu-id="cd4ac-130">Egy lehetőség kiválasztása a Sorok alapértelmezett mennyisége mezőben.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-130">In the Default quantity for lines field, select an option.</span></span>
6. <span data-ttu-id="cd4ac-131">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-131">Click OK.</span></span>
7. <span data-ttu-id="cd4ac-132">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-132">Click Yes.</span></span>
8. <span data-ttu-id="cd4ac-133">Kattintson a Termékbevételezések egyeztetése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-133">Click Match product receipts.</span></span>
9. <span data-ttu-id="cd4ac-134">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-134">Click OK.</span></span>
10. <span data-ttu-id="cd4ac-135">A Művelet panelen kattintson az Áttekintés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-135">On the Action Pane, click Review.</span></span>
11. <span data-ttu-id="cd4ac-136">Kattintson a Részletek egyeztetése elemre.</span><span class="sxs-lookup"><span data-stu-id="cd4ac-136">Click Matching details.</span></span>

