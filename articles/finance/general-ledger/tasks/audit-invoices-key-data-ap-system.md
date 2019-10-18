---
title: A kötelezettségkezelési rendszerben levő számlák és kulcsfontosságú adatok vizsgálata
description: Amikor egy beszerzési rendelés után egy termékekről vagy szolgáltatásokról kiállított szállítói számlát fogad be, az üzleti folyamat megkövetelheti, hogy a számla kifizetésének a jóváhagyását megelőzően az áruk és szolgáltatások be legyenek vételezve.
author: saraschi2
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
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c6e8967fe4db67ff98fc7093792bdb82b73a33d9
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178042"
---
# <a name="audit-invoices-and-key-data-in-ap-system"></a><span data-ttu-id="dfbda-103">A kötelezettségkezelési rendszerben levő számlák és kulcsfontosságú adatok vizsgálata</span><span class="sxs-lookup"><span data-stu-id="dfbda-103">Audit invoices and key data in AP system</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="dfbda-104">Amikor egy beszerzési rendelés után egy termékekről vagy szolgáltatásokról kiállított szállítói számlát fogad be, az üzleti folyamat megkövetelheti, hogy a számla kifizetésének a jóváhagyását megelőzően az áruk és szolgáltatások be legyenek vételezve.</span><span class="sxs-lookup"><span data-stu-id="dfbda-104">When you receive an invoice from a vendor for goods or services on a purchase order, the business processes might require that the goods or services be received before the invoice can be approved for payment.</span></span> <span data-ttu-id="dfbda-105">Mielőtt elkezdené a beállítást, győződjön meg arról, hogy a Számlaegyeztetés konfigurációs kulcs be van állítva.</span><span class="sxs-lookup"><span data-stu-id="dfbda-105">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span> 

<span data-ttu-id="dfbda-106">A Kötelezettségek paraméterei lapon győződjön meg róla, hogy a Számlaegyeztetés ellenőrzés beállítás van kiválasztva, a Számla feladása eltérésekkel mező Jóváhagyás szükséges értékű, és a Soregyeztetés irányelv mező Háromirányú egyeztetés értékű.</span><span class="sxs-lookup"><span data-stu-id="dfbda-106">In the Accounts payable parameters page, ensure that the Enable invoice matching validation option is selected, the Post invoice with discrepancies field is set to Require approval, and the Line matching policy field is set to Three-way matching.</span></span>

<span data-ttu-id="dfbda-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="dfbda-107">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="dfbda-108">A kötelezettségeket kezelő vezető vagy a könyvelésért felelős vezető ezeket a lépéseket hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="dfbda-108">The accounts payable manager or accounting manager role would perform these steps.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="dfbda-109">Beszerzési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="dfbda-109">Create a purchase order</span></span>
1. <span data-ttu-id="dfbda-110">Lépjen az **Összes beszerzési rendelés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dfbda-110">Go to **All purchase orders**.</span></span>
2. <span data-ttu-id="dfbda-111">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="dfbda-111">Click **New**.</span></span>
3. <span data-ttu-id="dfbda-112">A **Szállítói számla** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="dfbda-112">In the **Vendor account** field, type a value.</span></span>
4. <span data-ttu-id="dfbda-113">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="dfbda-113">Click **OK**.</span></span>
5. <span data-ttu-id="dfbda-114">Kattintson az **Új sor hozzáadása** elemre.</span><span class="sxs-lookup"><span data-stu-id="dfbda-114">Click **Add line**.</span></span>
6. <span data-ttu-id="dfbda-115">A **Cikkszám** mezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="dfbda-115">In the **Item number** field, type a value.</span></span>
7. <span data-ttu-id="dfbda-116">A Művelet panelen kattintson a **Beszerzés** elemre.</span><span class="sxs-lookup"><span data-stu-id="dfbda-116">On the Action Pane, click **Purchase**.</span></span>
8. <span data-ttu-id="dfbda-117">Kattintson a **Megerősítés** gombra.</span><span class="sxs-lookup"><span data-stu-id="dfbda-117">Click **Confirm**.</span></span>

## <a name="post-a-product-receipt"></a><span data-ttu-id="dfbda-118">Egy Termékbevételezés feladása</span><span class="sxs-lookup"><span data-stu-id="dfbda-118">Post a product receipt</span></span>
1. <span data-ttu-id="dfbda-119">A Művelet panelen kattintson a **Fogadás** elemre.</span><span class="sxs-lookup"><span data-stu-id="dfbda-119">On the Action Pane, click **Receive**.</span></span>
2. <span data-ttu-id="dfbda-120">Kattintson a **Termékbevételezés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dfbda-120">Click **Product receipt**.</span></span>
3. <span data-ttu-id="dfbda-121">Írjon be egy értéket a **Termékbevételezés** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="dfbda-121">In the **Product receipt** field, type a value.</span></span>
4. <span data-ttu-id="dfbda-122">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="dfbda-122">Click **OK**.</span></span>

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a><span data-ttu-id="dfbda-123">Szállítói számla rögzítése és egyeztetése a termékbevételezésekkel</span><span class="sxs-lookup"><span data-stu-id="dfbda-123">Record and match a vendor invoice to a product receipt</span></span>
1. <span data-ttu-id="dfbda-124">A Művelet panelen kattintson a **Számla > Számla** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dfbda-124">On the Action Pane, click **Invoice > Invoice**.</span></span>
2. <span data-ttu-id="dfbda-125">Adjon meg egy értéket a **Szám** mezőben.</span><span class="sxs-lookup"><span data-stu-id="dfbda-125">In the **Number** field, type a value.</span></span>
3. <span data-ttu-id="dfbda-126">Kattintson az **Alapértelmezett forrás: Rendelt mennyiség** elemre a legördülő párbeszédablak megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="dfbda-126">Click **Default from: Ordered quantity** to open the drop dialog.</span></span>
4. <span data-ttu-id="dfbda-127">Válasszon egy lehetőséget a **Sorokhoz tartozó alapértelmezett mennyiség** mezőben.</span><span class="sxs-lookup"><span data-stu-id="dfbda-127">In the **Default quantity for lines** field, select an option.</span></span>
5. <span data-ttu-id="dfbda-128">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="dfbda-128">Click **OK**.</span></span>
6. <span data-ttu-id="dfbda-129">Kattintson az **Igen** gombra.</span><span class="sxs-lookup"><span data-stu-id="dfbda-129">Click **Yes**.</span></span>
7. <span data-ttu-id="dfbda-130">Kattintson a **Termékbevételezések egyeztetése** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dfbda-130">Click **Match product receipts**.</span></span>
8. <span data-ttu-id="dfbda-131">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="dfbda-131">Click **OK**.</span></span>
9. <span data-ttu-id="dfbda-132">A Művelet panelen kattintson az **Áttekintés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dfbda-132">On the Action Pane, click **Review**.</span></span>
10. <span data-ttu-id="dfbda-133">Kattintson a **Részletek egyeztetése** elemre.</span><span class="sxs-lookup"><span data-stu-id="dfbda-133">Click **Matching details**.</span></span>

