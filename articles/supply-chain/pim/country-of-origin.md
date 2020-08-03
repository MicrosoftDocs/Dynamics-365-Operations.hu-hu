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
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: fd234c57bf9893e9b8bcfa5ada7439a642f7a288
ms.sourcegitcommit: 70d0b4e6bdacc15ec75935550ae55fc02cb79624
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/15/2020
ms.locfileid: "3596238"
---
# <a name="country-of-origin"></a><span data-ttu-id="b6c1f-105">Származási ország</span><span class="sxs-lookup"><span data-stu-id="b6c1f-105">Country of origin</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b6c1f-106">Számos szervezet állít ki tanúsítványt a szállítóknak annak biztosítása érdekében, hogy a termékek megfelelnek a meghatározott minősítési szabványoknak.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-106">Many organizations issue certificates to their vendors to ensure that products meet specific certification standards.</span></span> <span data-ttu-id="b6c1f-107">Ezek a tanúsítványok gyakran a származási országtól függenek.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-107">These certificates often depend on the country of origin.</span></span> <span data-ttu-id="b6c1f-108">Aa származási ország funkció lehetővé teszi, hogy a terméket a származási országhoz kapcsolja, és nyomon kövesse a termék minősítéseit.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-108">The country of origin feature lets you link a product to its country of origin and keep track of its product certifications.</span></span>

## <a name="configure-source-and-destination-countries"></a><span data-ttu-id="b6c1f-109">Forrás- és célországok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="b6c1f-109">Configure source and destination countries</span></span>

<span data-ttu-id="b6c1f-110">A termékre vonatkozó tanúsítvány kiállítása előtt csatolni kell a terméket a célországhoz és a származási országhoz.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-110">Before you issue a certificate for a product, you must link the product to its destination country and its country of origin.</span></span>

1. <span data-ttu-id="b6c1f-111">Lépjen a **Termékinformációk kezelése \> Beállítás \> Termék megfelelősége \> Származási ország \> Származási ország szabályai** elemre.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-111">Go to **Product information management \> Setup \> Product compliance \> Country of origin \> Country of origin rules**.</span></span>
2. <span data-ttu-id="b6c1f-112">Válasszon ki egy meglévő országbeállítást a szerkesztéshez, vagy a műveleti ablak **új** elemét választva hozzon létre egy új ország-beállítást.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-112">Select an existing country setup to edit, or select **New** on the Action Pane to create a new country setup.</span></span>
3. <span data-ttu-id="b6c1f-113">Állítsa be a következő értékeket a kiválasztott vagy az új országhoz.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-113">Set the following values for the selected or new country.</span></span>

    | <span data-ttu-id="b6c1f-114">Mező</span><span class="sxs-lookup"><span data-stu-id="b6c1f-114">Field</span></span> | <span data-ttu-id="b6c1f-115">Leírás</span><span class="sxs-lookup"><span data-stu-id="b6c1f-115">Description</span></span> |
    |---|---|
    | <span data-ttu-id="b6c1f-116">Cikkszám</span><span class="sxs-lookup"><span data-stu-id="b6c1f-116">Item number</span></span> | <span data-ttu-id="b6c1f-117">Válassza ki a termék cikkszámát.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-117">Select the item number of the product.</span></span> |
    | <span data-ttu-id="b6c1f-118">Célország</span><span class="sxs-lookup"><span data-stu-id="b6c1f-118">Destination country</span></span> | <span data-ttu-id="b6c1f-119">Válassza ki azt az országot, ahova a terméket küldeni szeretné.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-119">Select the country that you're sending the product to.</span></span> |
    | <span data-ttu-id="b6c1f-120">Származási ország</span><span class="sxs-lookup"><span data-stu-id="b6c1f-120">Origin country</span></span> | <span data-ttu-id="b6c1f-121">Válassza ki azt az országot, ahonnan a terméket küldeni szeretné.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-121">Select the country that you're shipping the product from.</span></span> |

<span data-ttu-id="b6c1f-122">Ennek a beállításnak az a célja, hogy segítséget jelentsen egy darabjegyzék (BOM)-jelentés létrehozásához, ahol megadhatja a származási országot mindegyik részhez, ahol a forrás- és célországot meg kell adni.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-122">The purpose of this setup is to help you generate a bill of materials (BOM) report where you can include the country of origin for each part that source and destination countries are specified for.</span></span> <span data-ttu-id="b6c1f-123">Ez a jelentés segít Önnek teljes körű képet kapni arról, hogy honnan jönnek az alkatrészek, és hová mennek.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-123">This report will help you get a holistic picture of where your parts come from and where they are going.</span></span>

## <a name="keep-track-of-vendor-certificates"></a><span data-ttu-id="b6c1f-124">Szállítói tanúsítványok nyomon követése</span><span class="sxs-lookup"><span data-stu-id="b6c1f-124">Keep track of vendor certificates</span></span>

<span data-ttu-id="b6c1f-125">A **Származási ország szállítói tanúsítványai** oldalon nyomon követheti azokat az minősítéseket, amelyeket szállítóknak kibocsátott.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-125">You can use the **Country of origin vendor certificates** page to keep track of certificates that you issue to vendors.</span></span>

<span data-ttu-id="b6c1f-126">El kell döntenie, hogy mely minősítési dokumentumokat kell kiadnia, és hogyan fogja jelenteni azokat a vevők számára.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-126">You must decide which certificate documents you're issuing and how you will report them to customers.</span></span> <span data-ttu-id="b6c1f-127">Ez a funkció segít nyomon követni a tanúsítványokat.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-127">This feature helps you keep track of your certificates.</span></span> <span data-ttu-id="b6c1f-128">Azt is megadhatja, hogy a megfelelő tanúsítványszámok szerepeljenek-e a számlákon, a szállítóleveleken és/vagy a rendelés-visszaigazolásokon.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-128">It also lets you choose whether the relevant certificate numbers appear on invoices, packing slips, and/or order confirmations.</span></span>

<span data-ttu-id="b6c1f-129">A tínúsítványadatok beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-129">To set up your certificate information, follow these steps.</span></span>

1. <span data-ttu-id="b6c1f-130">Lépjen a **Termékinformációk kezelése \> Beállítás \> Termék megfelelősége \> Származási ország \> Származási ország szállítói tanúsítványai** elemre.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-130">Go to **Product information management \> Setup \> Product compliance \> Country of origin \> Country of origin vendor certificates**.</span></span>
2. <span data-ttu-id="b6c1f-131">Válasszon ki egy meglévő tanúsítványbeállítást a szerkesztéshez, vagy a műveleti ablak **új** elemét választva hozzon létre egy új tanúsítványbeállítást.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-131">Select an existing certificate setup to edit, or select **New** on the Action Pane to create a new certificate setup.</span></span>
3. <span data-ttu-id="b6c1f-132">Állítsa be a következő beállításokat a kiválasztott vagy az új tanúsítványra.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-132">Set the following settings for the selected or new certificate.</span></span>

    | <span data-ttu-id="b6c1f-133">Mező</span><span class="sxs-lookup"><span data-stu-id="b6c1f-133">Field</span></span> | <span data-ttu-id="b6c1f-134">Leírás</span><span class="sxs-lookup"><span data-stu-id="b6c1f-134">Description</span></span> |
    |---|---|
    | <span data-ttu-id="b6c1f-135">Szállítói számla</span><span class="sxs-lookup"><span data-stu-id="b6c1f-135">Vendor account</span></span> | <span data-ttu-id="b6c1f-136">Válassza ki azt a szállítót, akinek a tanúsítványt kibocsátotta.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-136">Select the vendor that you issued the certificate to.</span></span> |
    | <span data-ttu-id="b6c1f-137">Cikkszám</span><span class="sxs-lookup"><span data-stu-id="b6c1f-137">Item number</span></span> | <span data-ttu-id="b6c1f-138">Válassza ki azt a cikket, akinek a tanúsítványt kibocsátotta.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-138">Select the item that you issued the certificate for.</span></span> |
    | <span data-ttu-id="b6c1f-139">Ország/régió</span><span class="sxs-lookup"><span data-stu-id="b6c1f-139">Country/region</span></span> | <span data-ttu-id="b6c1f-140">A célország vagy régió, ahol a tanúsítványt használni kell.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-140">The destination country or region where you must use this certificate.</span></span> |
    | <span data-ttu-id="b6c1f-141">Tanúsítványszám</span><span class="sxs-lookup"><span data-stu-id="b6c1f-141">Certificate number</span></span> | <span data-ttu-id="b6c1f-142">Adja meg a kibocsátott tanúsítvány azonosítószámát.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-142">Enter the identification number of the certificate that you issued.</span></span> |
    | <span data-ttu-id="b6c1f-143">Hatályos</span><span class="sxs-lookup"><span data-stu-id="b6c1f-143">Effective</span></span> | <span data-ttu-id="b6c1f-144">Válassza ki az első dátumot, amikor az aktuális tanúsítvány érvényes.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-144">Select the first date when the current certificate is valid.</span></span>|
    | <span data-ttu-id="b6c1f-145">Lejárat</span><span class="sxs-lookup"><span data-stu-id="b6c1f-145">Expiration</span></span> | <span data-ttu-id="b6c1f-146">Válassza ki az utolsó dátumot, amikor az aktuális tanúsítvány érvényes.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-146">Select the last date when the current certificate is valid.</span></span> |
    | <span data-ttu-id="b6c1f-147">Nyomtatás számlára</span><span class="sxs-lookup"><span data-stu-id="b6c1f-147">Print on invoice</span></span> | <span data-ttu-id="b6c1f-148">Jelölje be ezt a jelölőnégyzetet, ha a megadott dátumtartomány során a megadott országnak címzett számlákra rá szeretné nyomtatni a tanúsítvány számát.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-148">Select this check box to print the certificate number on invoices that are addressed to the specified country during the specified date range.</span></span> |
    | <span data-ttu-id="b6c1f-149">Nyomtatás szállítólevélre</span><span class="sxs-lookup"><span data-stu-id="b6c1f-149">Print on packing slip</span></span> | <span data-ttu-id="b6c1f-150">Jelölje be ezt a jelölőnégyzetet, ha a megadott dátumtartomány során a megadott országnak címzett szállítólevelekre rá szeretné nyomtatni a tanúsítvány számát.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-150">Select this check box to print the certificate number on packing slips that are addressed to the specified country during the specified date range.</span></span> |
    | <span data-ttu-id="b6c1f-151">Nyomtatás az értékesítési rendelésre</span><span class="sxs-lookup"><span data-stu-id="b6c1f-151">Print on sales order</span></span> | <span data-ttu-id="b6c1f-152">Jelölje be ezt a jelölőnégyzetet, ha a megadott dátumtartomány során a megadott országnak címzett értékesítési rendelésekre rá szeretné nyomtatni a tanúsítvány számát.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-152">Select this check box to print the certificate number on sales orders that are addressed to the specified country during the specified date range.</span></span> |

## <a name="include-the-country-of-origin-on-bom-reports"></a><span data-ttu-id="b6c1f-153">A származási ország szerepeltetése a darabjegyzék-jelentésekben</span><span class="sxs-lookup"><span data-stu-id="b6c1f-153">Include the country of origin on BOM reports</span></span>

<span data-ttu-id="b6c1f-154">Ha DBJ-jelentést hoz létre, akkor a **Származási ország szabályai** oldal mindegyik részénél szerepeltetheti a származási országot, amelyhez meghatározta a cél- és forrásországokat.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-154">When you generate a BOM report, you can include the country of origin for each part that you specified source and destination countries for on the **Country of origin rules** page.</span></span>

1. <span data-ttu-id="b6c1f-155">Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-155">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="b6c1f-156">Válasszon ki vagy hozzon létre egy terméket, és nyissa meg a **Kapcsolódó termékadatok** oldalát.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-156">Select or create a product to open its **Released product details** page.</span></span>
1. <span data-ttu-id="b6c1f-157">A Műveleti ablaktáblán a **Tervező** lapon a **DBJ** csoportban válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-157">On the Action Pane, on the **Engineer** tab, in the **BOM** group, select **Designer**.</span></span>
1. <span data-ttu-id="b6c1f-158">A megjelenő oldalon a műveleti ablaktáblán kattintson a **DBJ \> Nyomtatás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-158">On the page that appears, on the Action Pane, select **BOM \> Print**.</span></span>
1. <span data-ttu-id="b6c1f-159">A **Darabjegyzéksorok** párbeszédablakban állítsa a **Célország** mezőt a jelentésen megtekinteni kívánt célországra.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-159">In **Bill of materials lines** dialog box, set the **Destination country** field to the destination country that you want to view on your report.</span></span>
1. <span data-ttu-id="b6c1f-160">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-160">Select **OK**.</span></span>

<span data-ttu-id="b6c1f-161">Létrejön és megjelenik egy jelentés, amely információt jelenít meg a származási országról az egyes alkatrészekhez.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-161">A report that shows information about the country of origin of each part is generated and shown.</span></span> <span data-ttu-id="b6c1f-162">Íme, egy példa a jelentésre.</span><span class="sxs-lookup"><span data-stu-id="b6c1f-162">Here is an example of the report.</span></span>

<span data-ttu-id="b6c1f-163">![Származási ország jelentés](media/country-of-origin-report.png "Származási ország jelentés")</span><span class="sxs-lookup"><span data-stu-id="b6c1f-163">![Country of origin report](media/country-of-origin-report.png "Country of origin report")</span></span>
