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
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 66f3b3444b9ff6a93d83c97f1d962c3bdb0699c9
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227112"
---
# <a name="record-vendor-invoice-and-match-against-received-quantity"></a><span data-ttu-id="b8f06-103">A szállítói számlák rögzítése és összevetése a bevételezett mennyiséggel</span><span class="sxs-lookup"><span data-stu-id="b8f06-103">Record vendor invoice and match against received quantity</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b8f06-104">Amikor egy beszerzési rendelés után egy termékekről vagy szolgáltatásokról kiállított szállítói számlát fogad be, az üzleti folyamat megkövetelheti, hogy a számla kifizetésének a jóváhagyását megelőzően az áruk és szolgáltatások be legyenek vételezve.</span><span class="sxs-lookup"><span data-stu-id="b8f06-104">When you receive an invoice from a vendor for goods or services on a purchase order, the business processes might require that the goods or services be received before the invoice can be approved for payment.</span></span> <span data-ttu-id="b8f06-105">Mielőtt elkezdené a beállítást, győződjön meg arról, hogy a Számlaegyeztetés konfigurációs kulcs be van állítva.</span><span class="sxs-lookup"><span data-stu-id="b8f06-105">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span> 

<span data-ttu-id="b8f06-106">A Kötelezettségek paraméterei lapon győződjön meg róla, hogy a Számlaegyeztetés ellenőrzés beállítás van kiválasztva, a Számla feladása eltérésekkel mező Jóváhagyás szükséges értékű, és a Soregyeztetés irányelv mező Háromirányú egyeztetés értékű.</span><span class="sxs-lookup"><span data-stu-id="b8f06-106">In the Accounts payable parameters page, ensure that the Enable invoice matching validation option is selected, the Post invoice with discrepancies field is set to Require approval, and the Line matching policy field is set to Three-way matching.</span></span>

<span data-ttu-id="b8f06-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="b8f06-107">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="b8f06-108">A kötelezettségeket kezelő vezető vagy a könyvelésért felelős vezető ezeket a lépéseket hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="b8f06-108">The accounts payable manager or accounting manager role would perform these steps.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="b8f06-109">Beszerzési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="b8f06-109">Create a purchase order</span></span>
1. <span data-ttu-id="b8f06-110">Ugrás az összes beszerzési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="b8f06-110">Go to All purchase orders.</span></span>
2. <span data-ttu-id="b8f06-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b8f06-111">Click New.</span></span>
3. <span data-ttu-id="b8f06-112">A Szállítói számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="b8f06-112">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="b8f06-113">Írjon be egy értéket a Szállítói számla mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b8f06-113">In the Vendor account field, type a value.</span></span>
5. <span data-ttu-id="b8f06-114">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b8f06-114">Click OK.</span></span>
6. <span data-ttu-id="b8f06-115">Kattintson az Új sor hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b8f06-115">Click Add line.</span></span>
7. <span data-ttu-id="b8f06-116">A cikkmezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b8f06-116">In the Item number field, type a value.</span></span>
8. <span data-ttu-id="b8f06-117">A Művelet panelen kattintson a Beszerzés elemre.</span><span class="sxs-lookup"><span data-stu-id="b8f06-117">On the Action Pane, click Purchase.</span></span>
9. <span data-ttu-id="b8f06-118">Kattintson a Megerősítés gombra.</span><span class="sxs-lookup"><span data-stu-id="b8f06-118">Click Confirm.</span></span>

## <a name="post-a-product-receipt"></a><span data-ttu-id="b8f06-119">Egy Termékbevételezés feladása</span><span class="sxs-lookup"><span data-stu-id="b8f06-119">Post a product receipt</span></span>
1. <span data-ttu-id="b8f06-120">A Művelet panelen kattintson a Bevételezés elemre.</span><span class="sxs-lookup"><span data-stu-id="b8f06-120">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="b8f06-121">Kattintson a Termékbevételezés elemre.</span><span class="sxs-lookup"><span data-stu-id="b8f06-121">Click Product receipt.</span></span>
3. <span data-ttu-id="b8f06-122">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="b8f06-122">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="b8f06-123">Írjon be egy értéket a Termékbevételezés mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b8f06-123">In the Product receipt field, type a value.</span></span>
5. <span data-ttu-id="b8f06-124">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b8f06-124">Click OK.</span></span>

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a><span data-ttu-id="b8f06-125">Szállítói számla rögzítése és egyeztetése a termékbevételezésekkel</span><span class="sxs-lookup"><span data-stu-id="b8f06-125">Record and match a vendor invoice to a product receipt</span></span>
1. <span data-ttu-id="b8f06-126">A Művelet panelen kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b8f06-126">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="b8f06-127">Kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b8f06-127">Click Invoice.</span></span>
3. <span data-ttu-id="b8f06-128">Érték beírása a Szám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b8f06-128">In the Number field, type a value.</span></span>
4. <span data-ttu-id="b8f06-129">Kattintson az Alapértelmezett forrás: Rendelt mennyiségre a legördülő párbeszédablak megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="b8f06-129">Click Default from: Ordered quantity to open the drop dialog.</span></span>
5. <span data-ttu-id="b8f06-130">Egy lehetőség kiválasztása a Sorok alapértelmezett mennyisége mezőben.</span><span class="sxs-lookup"><span data-stu-id="b8f06-130">In the Default quantity for lines field, select an option.</span></span>
6. <span data-ttu-id="b8f06-131">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b8f06-131">Click OK.</span></span>
7. <span data-ttu-id="b8f06-132">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="b8f06-132">Click Yes.</span></span>
8. <span data-ttu-id="b8f06-133">Kattintson a Termékbevételezések egyeztetése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b8f06-133">Click Match product receipts.</span></span>
9. <span data-ttu-id="b8f06-134">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b8f06-134">Click OK.</span></span>
10. <span data-ttu-id="b8f06-135">A Művelet panelen kattintson az Áttekintés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b8f06-135">On the Action Pane, click Review.</span></span>
11. <span data-ttu-id="b8f06-136">Kattintson a Részletek egyeztetése elemre.</span><span class="sxs-lookup"><span data-stu-id="b8f06-136">Click Matching details.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]