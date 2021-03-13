---
title: Származási ország
description: Számos szervezet állít ki tanúsítványt a szállítóknak annak biztosítása érdekében, hogy a termékek megfelelnek a meghatározott minősítési szabványoknak. Ezek a tanúsítványok gyakran a származási országtól függenek. Ez a témakör a származási ország funkcióval kapcsolatban tartalmaz tájékoztatást, amely lehetővé teszi, hogy a terméket a származási országhoz kapcsolja, és nyomon kövesse a termék minősítéseit.
author: dasani-madipalli
manager: tfehr
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: COOVendorCerts
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 2eaf0057123cd2cbcad00f95038627291dada517
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007814"
---
# <a name="country-of-origin"></a><span data-ttu-id="b2f28-105">Származási ország</span><span class="sxs-lookup"><span data-stu-id="b2f28-105">Country of origin</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="b2f28-106">Számos szervezet állít ki tanúsítványt a szállítóknak annak biztosítása érdekében, hogy a termékek megfelelnek a meghatározott minősítési szabványoknak.</span><span class="sxs-lookup"><span data-stu-id="b2f28-106">Many organizations issue certificates to their vendors to ensure that products meet specific certification standards.</span></span> <span data-ttu-id="b2f28-107">Ezek a tanúsítványok gyakran a származási országtól függenek.</span><span class="sxs-lookup"><span data-stu-id="b2f28-107">These certificates often depend on the country of origin.</span></span> <span data-ttu-id="b2f28-108">Aa származási ország funkció lehetővé teszi, hogy a terméket a származási országhoz kapcsolja, és nyomon kövesse a termék minősítéseit.</span><span class="sxs-lookup"><span data-stu-id="b2f28-108">The country of origin feature lets you link a product to its country of origin and keep track of its product certifications.</span></span>

## <a name="turn-on-the-country-of-origin-feature"></a><span data-ttu-id="b2f28-109">A származási ország funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="b2f28-109">Turn on the country of origin feature</span></span>

<span data-ttu-id="b2f28-110">A funkció használata előtt be kell azt kapcsolnia saját rendszerében.</span><span class="sxs-lookup"><span data-stu-id="b2f28-110">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="b2f28-111">A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="b2f28-111">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="b2f28-112">A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:</span><span class="sxs-lookup"><span data-stu-id="b2f28-112">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="b2f28-113">**Modul:** *Termékinformáció-kezelés*</span><span class="sxs-lookup"><span data-stu-id="b2f28-113">**Module:** *Product information management*</span></span>
- <span data-ttu-id="b2f28-114">**Funkció neve:** *Származási ország kezelési funkciója*</span><span class="sxs-lookup"><span data-stu-id="b2f28-114">**Feature name:** *Country of origin management feature*</span></span>

## <a name="configure-source-and-destination-countries"></a><span data-ttu-id="b2f28-115">Forrás- és célországok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="b2f28-115">Configure source and destination countries</span></span>

<span data-ttu-id="b2f28-116">A termékre vonatkozó tanúsítvány kiállítása előtt csatolni kell a terméket a célországhoz és a származási országhoz.</span><span class="sxs-lookup"><span data-stu-id="b2f28-116">Before you issue a certificate for a product, you must link the product to its destination country and its country of origin.</span></span>

1. <span data-ttu-id="b2f28-117">Lépjen a **Termékinformációk kezelése \> Beállítás \> Termék megfelelősége \> Származási ország \> Származási ország szabályai** elemre.</span><span class="sxs-lookup"><span data-stu-id="b2f28-117">Go to **Product information management \> Setup \> Product compliance \> Country of origin \> Country of origin rules**.</span></span>
2. <span data-ttu-id="b2f28-118">Válasszon ki egy meglévő országbeállítást a szerkesztéshez, vagy a műveleti ablak **új** elemét választva hozzon létre egy új ország-beállítást.</span><span class="sxs-lookup"><span data-stu-id="b2f28-118">Select an existing country setup to edit, or select **New** on the Action Pane to create a new country setup.</span></span>
3. <span data-ttu-id="b2f28-119">Állítsa be a következő értékeket a kiválasztott vagy az új országhoz.</span><span class="sxs-lookup"><span data-stu-id="b2f28-119">Set the following values for the selected or new country.</span></span>

    | <span data-ttu-id="b2f28-120">Mező</span><span class="sxs-lookup"><span data-stu-id="b2f28-120">Field</span></span> | <span data-ttu-id="b2f28-121">Leírás</span><span class="sxs-lookup"><span data-stu-id="b2f28-121">Description</span></span> |
    |---|---|
    | <span data-ttu-id="b2f28-122">Cikkszám</span><span class="sxs-lookup"><span data-stu-id="b2f28-122">Item number</span></span> | <span data-ttu-id="b2f28-123">Válassza ki a termék cikkszámát.</span><span class="sxs-lookup"><span data-stu-id="b2f28-123">Select the item number of the product.</span></span> |
    | <span data-ttu-id="b2f28-124">Célország</span><span class="sxs-lookup"><span data-stu-id="b2f28-124">Destination country</span></span> | <span data-ttu-id="b2f28-125">Válassza ki azt az országot, ahova a terméket küldeni szeretné.</span><span class="sxs-lookup"><span data-stu-id="b2f28-125">Select the country that you're sending the product to.</span></span> |
    | <span data-ttu-id="b2f28-126">Származási ország</span><span class="sxs-lookup"><span data-stu-id="b2f28-126">Origin country</span></span> | <span data-ttu-id="b2f28-127">Válassza ki azt az országot, ahonnan a terméket küldeni szeretné.</span><span class="sxs-lookup"><span data-stu-id="b2f28-127">Select the country that you're shipping the product from.</span></span> |

<span data-ttu-id="b2f28-128">Ennek a beállításnak az a célja, hogy segítséget jelentsen egy darabjegyzék (BOM)-jelentés létrehozásához, ahol megadhatja a származási országot mindegyik részhez, ahol a forrás- és célországot meg kell adni.</span><span class="sxs-lookup"><span data-stu-id="b2f28-128">The purpose of this setup is to help you generate a bill of materials (BOM) report where you can include the country of origin for each part that source and destination countries are specified for.</span></span> <span data-ttu-id="b2f28-129">Ez a jelentés segít Önnek teljes körű képet kapni arról, hogy honnan jönnek az alkatrészek, és hová mennek.</span><span class="sxs-lookup"><span data-stu-id="b2f28-129">This report will help you get a holistic picture of where your parts come from and where they are going.</span></span>

## <a name="keep-track-of-vendor-certificates"></a><span data-ttu-id="b2f28-130">Szállítói tanúsítványok nyomon követése</span><span class="sxs-lookup"><span data-stu-id="b2f28-130">Keep track of vendor certificates</span></span>

<span data-ttu-id="b2f28-131">A **Származási ország szállítói tanúsítványai** oldalon nyomon követheti azokat az minősítéseket, amelyeket szállítóknak kibocsátott.</span><span class="sxs-lookup"><span data-stu-id="b2f28-131">You can use the **Country of origin vendor certificates** page to keep track of certificates that you issue to vendors.</span></span>

<span data-ttu-id="b2f28-132">El kell döntenie, hogy mely minősítési dokumentumokat kell kiadnia, és hogyan fogja jelenteni azokat a vevők számára.</span><span class="sxs-lookup"><span data-stu-id="b2f28-132">You must decide which certificate documents you're issuing and how you will report them to customers.</span></span> <span data-ttu-id="b2f28-133">Ez a funkció segít nyomon követni a tanúsítványokat.</span><span class="sxs-lookup"><span data-stu-id="b2f28-133">This feature helps you keep track of your certificates.</span></span> <span data-ttu-id="b2f28-134">Azt is megadhatja, hogy a megfelelő tanúsítványszámok szerepeljenek-e a számlákon, a szállítóleveleken és/vagy a rendelés-visszaigazolásokon.</span><span class="sxs-lookup"><span data-stu-id="b2f28-134">It also lets you choose whether the relevant certificate numbers appear on invoices, packing slips, and/or order confirmations.</span></span>

<span data-ttu-id="b2f28-135">A tínúsítványadatok beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="b2f28-135">To set up your certificate information, follow these steps.</span></span>

1. <span data-ttu-id="b2f28-136">Lépjen a **Termékinformációk kezelése \> Beállítás \> Termék megfelelősége \> Származási ország \> Származási ország szállítói tanúsítványai** elemre.</span><span class="sxs-lookup"><span data-stu-id="b2f28-136">Go to **Product information management \> Setup \> Product compliance \> Country of origin \> Country of origin vendor certificates**.</span></span>
2. <span data-ttu-id="b2f28-137">Válasszon ki egy meglévő tanúsítványbeállítást a szerkesztéshez, vagy a műveleti ablak **új** elemét választva hozzon létre egy új tanúsítványbeállítást.</span><span class="sxs-lookup"><span data-stu-id="b2f28-137">Select an existing certificate setup to edit, or select **New** on the Action Pane to create a new certificate setup.</span></span>
3. <span data-ttu-id="b2f28-138">Állítsa be a következő beállításokat a kiválasztott vagy az új tanúsítványra.</span><span class="sxs-lookup"><span data-stu-id="b2f28-138">Set the following settings for the selected or new certificate.</span></span>

    | <span data-ttu-id="b2f28-139">Mező</span><span class="sxs-lookup"><span data-stu-id="b2f28-139">Field</span></span> | <span data-ttu-id="b2f28-140">Leírás</span><span class="sxs-lookup"><span data-stu-id="b2f28-140">Description</span></span> |
    |---|---|
    | <span data-ttu-id="b2f28-141">Szállítói számla</span><span class="sxs-lookup"><span data-stu-id="b2f28-141">Vendor account</span></span> | <span data-ttu-id="b2f28-142">Válassza ki azt a szállítót, akinek a tanúsítványt kibocsátotta.</span><span class="sxs-lookup"><span data-stu-id="b2f28-142">Select the vendor that you issued the certificate to.</span></span> |
    | <span data-ttu-id="b2f28-143">Cikkszám</span><span class="sxs-lookup"><span data-stu-id="b2f28-143">Item number</span></span> | <span data-ttu-id="b2f28-144">Válassza ki azt a cikket, akinek a tanúsítványt kibocsátotta.</span><span class="sxs-lookup"><span data-stu-id="b2f28-144">Select the item that you issued the certificate for.</span></span> |
    | <span data-ttu-id="b2f28-145">Ország/régió</span><span class="sxs-lookup"><span data-stu-id="b2f28-145">Country/region</span></span> | <span data-ttu-id="b2f28-146">A célország vagy régió, ahol a tanúsítványt használni kell.</span><span class="sxs-lookup"><span data-stu-id="b2f28-146">The destination country or region where you must use this certificate.</span></span> |
    | <span data-ttu-id="b2f28-147">Tanúsítványszám</span><span class="sxs-lookup"><span data-stu-id="b2f28-147">Certificate number</span></span> | <span data-ttu-id="b2f28-148">Adja meg a kibocsátott tanúsítvány azonosítószámát.</span><span class="sxs-lookup"><span data-stu-id="b2f28-148">Enter the identification number of the certificate that you issued.</span></span> |
    | <span data-ttu-id="b2f28-149">Hatályos</span><span class="sxs-lookup"><span data-stu-id="b2f28-149">Effective</span></span> | <span data-ttu-id="b2f28-150">Válassza ki az első dátumot, amikor az aktuális tanúsítvány érvényes.</span><span class="sxs-lookup"><span data-stu-id="b2f28-150">Select the first date when the current certificate is valid.</span></span>|
    | <span data-ttu-id="b2f28-151">Lejárat</span><span class="sxs-lookup"><span data-stu-id="b2f28-151">Expiration</span></span> | <span data-ttu-id="b2f28-152">Válassza ki az utolsó dátumot, amikor az aktuális tanúsítvány érvényes.</span><span class="sxs-lookup"><span data-stu-id="b2f28-152">Select the last date when the current certificate is valid.</span></span> |
    | <span data-ttu-id="b2f28-153">Nyomtatás számlára</span><span class="sxs-lookup"><span data-stu-id="b2f28-153">Print on invoice</span></span> | <span data-ttu-id="b2f28-154">Jelölje be ezt a jelölőnégyzetet, ha a megadott dátumtartomány során a megadott országnak címzett számlákra rá szeretné nyomtatni a tanúsítvány számát.</span><span class="sxs-lookup"><span data-stu-id="b2f28-154">Select this check box to print the certificate number on invoices that are addressed to the specified country during the specified date range.</span></span> |
    | <span data-ttu-id="b2f28-155">Nyomtatás szállítólevélre</span><span class="sxs-lookup"><span data-stu-id="b2f28-155">Print on packing slip</span></span> | <span data-ttu-id="b2f28-156">Jelölje be ezt a jelölőnégyzetet, ha a megadott dátumtartomány során a megadott országnak címzett szállítólevelekre rá szeretné nyomtatni a tanúsítvány számát.</span><span class="sxs-lookup"><span data-stu-id="b2f28-156">Select this check box to print the certificate number on packing slips that are addressed to the specified country during the specified date range.</span></span> |
    | <span data-ttu-id="b2f28-157">Nyomtatás az értékesítési rendelésre</span><span class="sxs-lookup"><span data-stu-id="b2f28-157">Print on sales order</span></span> | <span data-ttu-id="b2f28-158">Jelölje be ezt a jelölőnégyzetet, ha a megadott dátumtartomány során a megadott országnak címzett értékesítési rendelésekre rá szeretné nyomtatni a tanúsítvány számát.</span><span class="sxs-lookup"><span data-stu-id="b2f28-158">Select this check box to print the certificate number on sales orders that are addressed to the specified country during the specified date range.</span></span> |

## <a name="include-the-country-of-origin-on-bom-reports"></a><span data-ttu-id="b2f28-159">A származási ország szerepeltetése a darabjegyzék-jelentésekben</span><span class="sxs-lookup"><span data-stu-id="b2f28-159">Include the country of origin on BOM reports</span></span>

<span data-ttu-id="b2f28-160">Ha DBJ-jelentést hoz létre, akkor a **Származási ország szabályai** oldal mindegyik részénél szerepeltetheti a származási országot, amelyhez meghatározta a cél- és forrásországokat.</span><span class="sxs-lookup"><span data-stu-id="b2f28-160">When you generate a BOM report, you can include the country of origin for each part that you specified source and destination countries for on the **Country of origin rules** page.</span></span>

1. <span data-ttu-id="b2f28-161">Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b2f28-161">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="b2f28-162">Válasszon ki vagy hozzon létre egy terméket, és nyissa meg a **Kapcsolódó termékadatok** oldalát.</span><span class="sxs-lookup"><span data-stu-id="b2f28-162">Select or create a product to open its **Released product details** page.</span></span>
1. <span data-ttu-id="b2f28-163">A Műveleti ablaktáblán a **Tervező** lapon a **DBJ** csoportban válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b2f28-163">On the Action Pane, on the **Engineer** tab, in the **BOM** group, select **Designer**.</span></span>
1. <span data-ttu-id="b2f28-164">A megjelenő oldalon a műveleti ablaktáblán kattintson a **DBJ \> Nyomtatás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b2f28-164">On the page that appears, on the Action Pane, select **BOM \> Print**.</span></span>
1. <span data-ttu-id="b2f28-165">A **Darabjegyzéksorok** párbeszédablakban állítsa a **Célország** mezőt a jelentésen megtekinteni kívánt célországra.</span><span class="sxs-lookup"><span data-stu-id="b2f28-165">In **Bill of materials lines** dialog box, set the **Destination country** field to the destination country that you want to view on your report.</span></span>
1. <span data-ttu-id="b2f28-166">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b2f28-166">Select **OK**.</span></span>

<span data-ttu-id="b2f28-167">Létrejön és megjelenik egy jelentés, amely információt jelenít meg a származási országról az egyes alkatrészekhez.</span><span class="sxs-lookup"><span data-stu-id="b2f28-167">A report that shows information about the country of origin of each part is generated and shown.</span></span> <span data-ttu-id="b2f28-168">Íme, egy példa a jelentésre.</span><span class="sxs-lookup"><span data-stu-id="b2f28-168">Here is an example of the report.</span></span>

<span data-ttu-id="b2f28-169">![Származási ország jelentés](media/country-of-origin-report.png "Származási ország jelentés")</span><span class="sxs-lookup"><span data-stu-id="b2f28-169">![Country of origin report](media/country-of-origin-report.png "Country of origin report")</span></span>
