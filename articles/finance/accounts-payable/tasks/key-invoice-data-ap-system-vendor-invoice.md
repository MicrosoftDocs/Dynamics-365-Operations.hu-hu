---
title: Fő számlaadatok a Kintlevőségek rendszerben, szállítói számla használatával
description: Ez a feladat-útmutató segít Önnek szállítói számla létrehozásában egy beszerzési rendelésből, valamint a beszerzési rendelés, nyugta és számla egyeztetési eredményeinek megtekintésében (háromirányú egyeztetés).
author: abruer
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines, VendEditInvoice, InventItemIdLookupSimple, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f80c88b7fb3542f624d233f670cd7cd6ccd48b94
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443815"
---
# <a name="key-invoice-data-in-ap-using-a-vendor-invoice"></a><span data-ttu-id="1945d-103">Fő számlaadatok a Kintlevőségek rendszerben, szállítói számla használatával</span><span class="sxs-lookup"><span data-stu-id="1945d-103">Key invoice data in AP using a vendor invoice</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1945d-104">Ez a feladat-útmutató segít Önnek szállítói számla létrehozásában egy beszerzési rendelésből, valamint a beszerzési rendelés, nyugta és számla egyeztetési eredményeinek megtekintésében (háromirányú egyeztetés).</span><span class="sxs-lookup"><span data-stu-id="1945d-104">This task guide will help you create a vendor invoice from a purchase order and view the results of matching the purchase order, receipt, and invoice (3 way matching).</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="1945d-105">Beszerzési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="1945d-105">Create a purchase order</span></span>
1. <span data-ttu-id="1945d-106">A navigációs ablaktáblán nyissa meg a **Modulok > Kötelezettségek > beszerzési rendelések > Összes beszerzési rendelés** pontot.</span><span class="sxs-lookup"><span data-stu-id="1945d-106">In the Navigation pane, go to **Modules > Accounts payable > Purchase orders > All purchase orders**.</span></span>
2. <span data-ttu-id="1945d-107">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="1945d-107">Click **New**.</span></span>
3. <span data-ttu-id="1945d-108">A **Szállítói számla** mezőben kattintson a legördülő gombra a keresés megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="1945d-108">In the **Vendor account** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="1945d-109">Keressen egy szállítót.</span><span class="sxs-lookup"><span data-stu-id="1945d-109">Find a vendor to select.</span></span> <span data-ttu-id="1945d-110">Például görgessen le a US-104 lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1945d-110">For example, scroll down to US-104.</span></span>
5. <span data-ttu-id="1945d-111">US-104 szállító kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="1945d-111">Select vendor US-104.</span></span>
6. <span data-ttu-id="1945d-112">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="1945d-112">Click **OK**.</span></span>
7. <span data-ttu-id="1945d-113">A **Cikkszám** mezőben kattintson a legördülő gombra a keresés megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="1945d-113">In the **Item number** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="1945d-114">Készletcikk kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="1945d-114">Select an inventory item.</span></span> <span data-ttu-id="1945d-115">Példábul válassza ki az 1000 cikkszámot.</span><span class="sxs-lookup"><span data-stu-id="1945d-115">For example, select item number 1000.</span></span>
9. <span data-ttu-id="1945d-116">Bontsa ki a **Soradatok** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="1945d-116">Expand the **Line details** fastTab.</span></span>
10. <span data-ttu-id="1945d-117">Kattintson a **Beállítás** lapra. Felülírhatja az egyeztetési irányelvet egyeztetés nélkülire, kétirányú egyeztetésre vagy háromirányú egyeztetésre.</span><span class="sxs-lookup"><span data-stu-id="1945d-117">Click the **Setup** tab. You can override the matching policy to use no matching, 2-way matching, or 3-way matching.</span></span>  
11. <span data-ttu-id="1945d-118">A Művelet panelen kattintson a **Beszerzés** elemre.</span><span class="sxs-lookup"><span data-stu-id="1945d-118">On the Action Pane, click **Purchase**.</span></span>
12. <span data-ttu-id="1945d-119">Kattintson a **Megerősítés** gombra.</span><span class="sxs-lookup"><span data-stu-id="1945d-119">Click **Confirm**.</span></span>

## <a name="receive-the-products"></a><span data-ttu-id="1945d-120">A termékek bevételezése</span><span class="sxs-lookup"><span data-stu-id="1945d-120">Receive the products</span></span>
1. <span data-ttu-id="1945d-121">A Művelet panelen kattintson a **Fogadás** elemre.</span><span class="sxs-lookup"><span data-stu-id="1945d-121">On the Action Pane, click **Receive**.</span></span>
2. <span data-ttu-id="1945d-122">Kattintson a **Termékbevételezés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1945d-122">Click **Product receipt**.</span></span>
3. <span data-ttu-id="1945d-123">A **Termékbevételezés** mezőbe írja be a termékbevételezés számát.</span><span class="sxs-lookup"><span data-stu-id="1945d-123">In the **Product receipt** field, enter the product receipt number.</span></span> <span data-ttu-id="1945d-124">Például írja be, hogy PR123.</span><span class="sxs-lookup"><span data-stu-id="1945d-124">For example, enter PR123.</span></span>
4. <span data-ttu-id="1945d-125">Kattintson az **OK** gombra a termékbevételezés feladásához.</span><span class="sxs-lookup"><span data-stu-id="1945d-125">Click **OK** to post the product receipt.</span></span>
5. <span data-ttu-id="1945d-126">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1945d-126">Close the page.</span></span>

## <a name="create-a-vendor-invoice"></a><span data-ttu-id="1945d-127">Szállítói számla létrehozása</span><span class="sxs-lookup"><span data-stu-id="1945d-127">Create a vendor invoice</span></span>
1. <span data-ttu-id="1945d-128">A navigációs ablaktáblán nyissa meg a **Modulok > Kötelezettségek > Beszerzési rendelések > Bevételezett, de nem számlázott beszerzési rendelések** pontot.</span><span class="sxs-lookup"><span data-stu-id="1945d-128">In the Navigation pane, go to **Modules > Accounts payable > Purchase orders > Purchase orders received but not invoiced**.</span></span>
2. <span data-ttu-id="1945d-129">Válassza ki a létrehozott beszerzési rendelést.</span><span class="sxs-lookup"><span data-stu-id="1945d-129">Select the purchase order that you created.</span></span>
3. <span data-ttu-id="1945d-130">A Műveleti ablaktáblán kattintson a **Számla** elemre.</span><span class="sxs-lookup"><span data-stu-id="1945d-130">On the Action Pane, click **Invoice**.</span></span>
4. <span data-ttu-id="1945d-131">Kattintson a **Számla** pontra.</span><span class="sxs-lookup"><span data-stu-id="1945d-131">Click **Invoice**.</span></span>
5. <span data-ttu-id="1945d-132">A **Szám** mezőben adja meg a számlaszámot.</span><span class="sxs-lookup"><span data-stu-id="1945d-132">In the **Number** field, enter the invoice number.</span></span>
6. <span data-ttu-id="1945d-133">A **Számla leírása** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1945d-133">In the **Invoice description** field, type a value.</span></span>
7. <span data-ttu-id="1945d-134">Adjon meg egy dátumot a **Számla dátuma** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1945d-134">In the **Invoice date** field, enter a date.</span></span>
8. <span data-ttu-id="1945d-135">Írjon be 1200 értéket az **Egységár** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1945d-135">In the **Unit price** field, enter 1200.</span></span>
9. <span data-ttu-id="1945d-136">Kattintson az **Új sor hozzáadása** elemre.</span><span class="sxs-lookup"><span data-stu-id="1945d-136">Click **Add line**.</span></span>
10. <span data-ttu-id="1945d-137">A **Cikkszám** mezőben kattintson a legördülő gombra a keresés megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="1945d-137">In the **Item number** field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="1945d-138">Keresse meg a listában a telepítési költség cikkszámát.</span><span class="sxs-lookup"><span data-stu-id="1945d-138">In the list, find the installation charge item number.</span></span> <span data-ttu-id="1945d-139">Például az S0001 elem</span><span class="sxs-lookup"><span data-stu-id="1945d-139">For example, S0001</span></span>
12. <span data-ttu-id="1945d-140">Válassza ki a telepítési költség cikkszámát.</span><span class="sxs-lookup"><span data-stu-id="1945d-140">Select the installation charge item number.</span></span> <span data-ttu-id="1945d-141">Vegye figyelembe, hogy egyeztetés a módosítások óta nem lett végrehajtva.</span><span class="sxs-lookup"><span data-stu-id="1945d-141">Note that matching has not been performed since you made the changes.</span></span>  
13. <span data-ttu-id="1945d-142">Kattintson az **Egyeztetési állapot frissítése** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1945d-142">Click **Update match status**.</span></span>
14. <span data-ttu-id="1945d-143">A Művelet panelen kattintson az **Áttekintés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1945d-143">On the Action Pane, click **Review**.</span></span>
15. <span data-ttu-id="1945d-144">Kattintson a **Részletek egyeztetése** elemre.</span><span class="sxs-lookup"><span data-stu-id="1945d-144">Click **Matching details**.</span></span> <span data-ttu-id="1945d-145">A szolgáltatásokkal rendelkező új sorokat nem kell egyeztetni, ezért az állapotuk „Kihagyva” marad.</span><span class="sxs-lookup"><span data-stu-id="1945d-145">The new line with services does not need to be matched so the status stays "Not performed".</span></span>  
16. <span data-ttu-id="1945d-146">Válassza ki a termékbevételezést a bevételezett készletcikkhez.</span><span class="sxs-lookup"><span data-stu-id="1945d-146">Select the product receipt for the inventory item that you received.</span></span> <span data-ttu-id="1945d-147">A termékbevételezés sora egyeztetve lett, de eltérés található az árban vagy a mennyiségben, ezért sikertelen.</span><span class="sxs-lookup"><span data-stu-id="1945d-147">The line with the product receipt was matched but there is a mismatch of quantity or price so it fails.</span></span>  
17. <span data-ttu-id="1945d-148">Adjon meg egy számot az **Egységár** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1945d-148">In the **Unit price** field, enter a number.</span></span> <span data-ttu-id="1945d-149">Most, hogy az egységár megegyezik, az állapot Sikeres értékre frissül.</span><span class="sxs-lookup"><span data-stu-id="1945d-149">Now that the unit price matches, the status is updated to Passed.</span></span> <span data-ttu-id="1945d-150">Ha az irányelve megengedi az eltéréseket, vagy az egyeztetés csak egy figyelmeztetés, akkor ettől függetlenül fel tudja adni a számlát.</span><span class="sxs-lookup"><span data-stu-id="1945d-150">If your policy allows discrepancies or if matching is only a warning, you can still post the invoice.</span></span>  
18. <span data-ttu-id="1945d-151">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1945d-151">Close the page.</span></span>
19. <span data-ttu-id="1945d-152">Kattintson a **Bejegyzés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1945d-152">Click **Post**.</span></span>
20. <span data-ttu-id="1945d-153">Zárja be az űrlapot.</span><span class="sxs-lookup"><span data-stu-id="1945d-153">Close the form.</span></span> <span data-ttu-id="1945d-154">Ne felejtse, hogy a beszerzési rendelés már nem bevételezettként, hanem nem számlázottként van listázva.</span><span class="sxs-lookup"><span data-stu-id="1945d-154">Note that the purchase order is no longer listed as received but not invoiced.</span></span>  

