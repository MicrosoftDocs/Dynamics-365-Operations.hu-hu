---
title: Integrált szállítói alapadat
description: Ez a témakör a szállítói adatok integrációját ismerteti a Finance and Operations alkalmazás és a Common Data Service között.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 2442a6869daac22a435c1a7504b93ea4b5c14747
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019814"
---
# <a name="integrated-vendor-master"></a><span data-ttu-id="a6150-103">Integrált szállítói alapadat</span><span class="sxs-lookup"><span data-stu-id="a6150-103">Integrated vendor master</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="a6150-104">A *szállító* kifejezés olyan szállító szervezetet vagy kizárólagos tulajdonost jelöl, amely része az ellátási láncnak és árukat biztosít a cégnek.</span><span class="sxs-lookup"><span data-stu-id="a6150-104">The term *vendor* refers to a supplier organization or a sole proprietor that is part of the supply chain process, and that supplies goods for the business.</span></span> <span data-ttu-id="a6150-105">A *szállító* fogalmat ugyan kiterjedten használják a Finance and Operations alkalmazásban, a szállító fogalma nem létezik más Dynamics 365 alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="a6150-105">Although *vendor* is an established concept in Finance and Operations apps, a vendor concept doesn't exist in other Dynamics 365 apps.</span></span> <span data-ttu-id="a6150-106">Egyes cégek túlterhelik a Számla entitást, hogy mind a vevők, mind a szállítók adatait tudják tárolni.</span><span class="sxs-lookup"><span data-stu-id="a6150-106">Instead, some businesses overload the Account entity to store both customer information and vendor information.</span></span> <span data-ttu-id="a6150-107">Más vállalkozások egyéni szállítói fogalmat használnak.</span><span class="sxs-lookup"><span data-stu-id="a6150-107">Other businesses use a custom vendor concept.</span></span> <span data-ttu-id="a6150-108">A Common Data Service integrációja mindkét megoldást támogatja.</span><span class="sxs-lookup"><span data-stu-id="a6150-108">Common Data Service integration supports both these designs.</span></span> <span data-ttu-id="a6150-109">Ennek megfelelően az egyes üzleti esetekben bármelyiket használhatja.</span><span class="sxs-lookup"><span data-stu-id="a6150-109">Therefore, you can enable either of the designs, depending on your business scenario.</span></span>

<span data-ttu-id="a6150-110">A szállítói adatok Finance and Operations-alkalmazások és más Dynamics 365-alkalmazások közötti integrációjával több főkiszolgáló használható az adatokhoz.</span><span class="sxs-lookup"><span data-stu-id="a6150-110">Integration of vendor data between Finance and Operations apps and other Dynamics 365 apps lets you multi-master the data.</span></span> <span data-ttu-id="a6150-111">A szállítói adatokat – a forrásuktól függetlenül – a rendszer a háttérben integrálja az alkalmazások között és az infrastruktúra különbségeitől függetlenül.</span><span class="sxs-lookup"><span data-stu-id="a6150-111">Regardless of where the vendor data originates, it's integrated behind the scenes across application boundaries and infrastructure differences.</span></span> 

### <a name="vendor-data-flow"></a><span data-ttu-id="a6150-112">Szállítói adatok áramlása</span><span class="sxs-lookup"><span data-stu-id="a6150-112">Vendor data flow</span></span>

<span data-ttu-id="a6150-113">Ha a szállítói alapadatokhoz más Dynamics 365 alkalmazásokat szeretné használni, és el szeretné különíteni a szállítók és a vevők adatait, akkor használhatja az új szállítói kialakítást.</span><span class="sxs-lookup"><span data-stu-id="a6150-113">If you want to use other Dynamics 365 apps for vendor mastering, and you want to isolate vendor information from customer information, you can use the new vendor design.</span></span>

![Szállítói adatok áramlása](media/dual-write-vendor-data-flow.png)

<span data-ttu-id="a6150-115">Ha a szállítói alapadatokhoz más Dynamics 365 alkalmazásokat szeretné használni, akkor érdemes továbbra is a Számla entitást használni a szállítók adatainak tárolásához; használhatja az új, bővített szállítói kialakítást.</span><span class="sxs-lookup"><span data-stu-id="a6150-115">If you want to use other Dynamics 365 apps for vendor mastering, and you want to continue to use the Account entity to store vendor information, you can use the new extended vendor design.</span></span> <span data-ttu-id="a6150-116">Ebben a kialakításban a bővített szállítói adatok (például a szállítói csoport vagy a szállítói feladási profilok) tárolása a szállítói információk között történik.</span><span class="sxs-lookup"><span data-stu-id="a6150-116">In this design, extended vendor information, such as the vendor group and vendor posting profile, are stored in the vendor detail.</span></span>

![Bővített szállítói adatok áramlása](media/dual-write-vendor-detail.jpg)

<span data-ttu-id="a6150-118">A szállítók és a vevők kapcsolatfelvételi adatai hasonlóak.</span><span class="sxs-lookup"><span data-stu-id="a6150-118">Vendor contact information resembles customer contact information.</span></span> <span data-ttu-id="a6150-119">A személyek kapcsolatfelvételi adatainak a tárolásához és lekéréséhez ugyanazokat az entitásokat használja a rendszer a háttérben.</span><span class="sxs-lookup"><span data-stu-id="a6150-119">Behind the scenes, the contact person's information is stored and retrieved from the same entities.</span></span>

## <a name="templates"></a><span data-ttu-id="a6150-120">Sablonok</span><span class="sxs-lookup"><span data-stu-id="a6150-120">Templates</span></span>

<span data-ttu-id="a6150-121">A szállítói adatok között a szállító minden részlete (például a szállítói csoport, a címek, a kapcsolatfelvételi adatok, a fizetési és a számlázási profil) szerepel.</span><span class="sxs-lookup"><span data-stu-id="a6150-121">Vendor data includes all information about the vendor, such as the vendor group, addresses, contact information, payment profile, and invoice profile.</span></span> <span data-ttu-id="a6150-122">Ahogy az alábbi táblázatban látható, az entitásleképezések gyűjteménye együttműködik a szállítói adatokkal végzett interakciók során.</span><span class="sxs-lookup"><span data-stu-id="a6150-122">A collection of entity maps work together during vendor data interaction, as shown in the following table.</span></span>

<span data-ttu-id="a6150-123">Finance and Operations-alkalmazásoknak</span><span class="sxs-lookup"><span data-stu-id="a6150-123">Finance and Operations apps</span></span> | <span data-ttu-id="a6150-124">Egyéb Dynamics 365 alkalmazások</span><span class="sxs-lookup"><span data-stu-id="a6150-124">Other Dynamics 365 apps</span></span>         | <span data-ttu-id="a6150-125">Leírás</span><span class="sxs-lookup"><span data-stu-id="a6150-125">Description</span></span>
----------------------------|---------------------------------|------------
<span data-ttu-id="a6150-126">Szállító V2</span><span class="sxs-lookup"><span data-stu-id="a6150-126">Vendor V2</span></span>               | <span data-ttu-id="a6150-127">Könyvelési számla</span><span class="sxs-lookup"><span data-stu-id="a6150-127">Account</span></span> | <span data-ttu-id="a6150-128">Azok a cégek, amelyek a Számla entitással tárolják a szállítói adatokat, továbbra is változás nélkül használhatják ezt a megoldást.</span><span class="sxs-lookup"><span data-stu-id="a6150-128">Businesses that use the Account entity to store vendor information can continue to use it in the same way.</span></span> <span data-ttu-id="a6150-129">A Finance and Operations alkalmazások integrációjának köszönhető explicit szállítói funkciókat ugyancsak kihasználhatja.</span><span class="sxs-lookup"><span data-stu-id="a6150-129">They can also take advantage of the explicit vendor functionality that is coming because of Finance and Operations apps integration.</span></span>
<span data-ttu-id="a6150-130">Szállító V2</span><span class="sxs-lookup"><span data-stu-id="a6150-130">Vendor V2</span></span>               | <span data-ttu-id="a6150-131">Msdyn\_vendors</span><span class="sxs-lookup"><span data-stu-id="a6150-131">Msdyn\_vendors</span></span> | <span data-ttu-id="a6150-132">A szállítókhoz egyéni megoldást használó cégek a Finance and Operations-alkalmazások integrációjának köszönhetően kihasználhatják a Common Data Service rendszerben bevezetett kész szállítói fogalmat.</span><span class="sxs-lookup"><span data-stu-id="a6150-132">Businesses that use a custom solution for vendors can take advantage of the out-of-box vendor concept that is being introduced in Common Data Service because of Finance and Operations apps integration.</span></span> 
<span data-ttu-id="a6150-133">Szállítói csoportok</span><span class="sxs-lookup"><span data-stu-id="a6150-133">Vendor groups</span></span> | <span data-ttu-id="a6150-134">msdyn_vendorgroups</span><span class="sxs-lookup"><span data-stu-id="a6150-134">msdyn_vendorgroups</span></span> | <span data-ttu-id="a6150-135">Ez a sablon szinkronizálja a szállítói csoport adatait.</span><span class="sxs-lookup"><span data-stu-id="a6150-135">This template synchronizes vendor group information.</span></span>
<span data-ttu-id="a6150-136">Szállítói fizetési mód</span><span class="sxs-lookup"><span data-stu-id="a6150-136">Vendor payment method</span></span> | <span data-ttu-id="a6150-137">msdyn_vendorpaymentmethods</span><span class="sxs-lookup"><span data-stu-id="a6150-137">msdyn_vendorpaymentmethods</span></span> | <span data-ttu-id="a6150-138">Ez a sablon szinkronizálja a szállító fizetési módra vonatkozó adatait.</span><span class="sxs-lookup"><span data-stu-id="a6150-138">This template synchronizes vendor payment method information.</span></span>
<span data-ttu-id="a6150-139">CDS névjegyek V2</span><span class="sxs-lookup"><span data-stu-id="a6150-139">CDS Contacts V2</span></span>             | <span data-ttu-id="a6150-140">kapcsolattartók</span><span class="sxs-lookup"><span data-stu-id="a6150-140">contacts</span></span>                        | <span data-ttu-id="a6150-141">A [névjegyek](customer-mapping.md#cds-contacts-v2-to-contacts) sablon a vevők és a szállítók összes elsődleges, másodlagos és harmadlagos kapcsolattartási adatát szinkronizálja.</span><span class="sxs-lookup"><span data-stu-id="a6150-141">The [contacts](customer-mapping.md#cds-contacts-v2-to-contacts) template synchronizes all primary, secondary, and tertiary contact information, for both customers and vendors.</span></span>
<span data-ttu-id="a6150-142">Kifizetési lista sorai</span><span class="sxs-lookup"><span data-stu-id="a6150-142">Payment schedule lines</span></span>      | <span data-ttu-id="a6150-143">msdyn_paymentschedulelines</span><span class="sxs-lookup"><span data-stu-id="a6150-143">msdyn_paymentschedulelines</span></span>      | <span data-ttu-id="a6150-144">A [fizetési ütemezés sorai](customer-mapping.md#payment-schedule-lines-to-msdyn_paymentschedulelines) sablon a vevők és a szállítók hivatkozási adatait szinkronizálja.</span><span class="sxs-lookup"><span data-stu-id="a6150-144">The [payment schedule lines](customer-mapping.md#payment-schedule-lines-to-msdyn_paymentschedulelines) template synchronizes reference data for customers and vendors.</span></span>
<span data-ttu-id="a6150-145">Fizetési ütemezés</span><span class="sxs-lookup"><span data-stu-id="a6150-145">Payment schedule</span></span>            | <span data-ttu-id="a6150-146">msdyn_paymentschedules</span><span class="sxs-lookup"><span data-stu-id="a6150-146">msdyn_paymentschedules</span></span>          | <span data-ttu-id="a6150-147">A [fizetési ütemezések](customer-mapping.md#payment-schedule-to-msdyn_paymentschedules) sablon a vevők és a szállítók fizetési ütemezésre vonatkozó hivatkozási adatait szinkronizálja.</span><span class="sxs-lookup"><span data-stu-id="a6150-147">The [payment schedules](customer-mapping.md#payment-schedule-to-msdyn_paymentschedules) template synchronizes payment schedule reference data, for both customers and vendors.</span></span>
<span data-ttu-id="a6150-148">Fizetési nap sorai, CDS V2</span><span class="sxs-lookup"><span data-stu-id="a6150-148">Payment day lines CDS V2</span></span>    | <span data-ttu-id="a6150-149">msdyn_paymentdaylines</span><span class="sxs-lookup"><span data-stu-id="a6150-149">msdyn_paymentdaylines</span></span>           | <span data-ttu-id="a6150-150">A [fizetési nap sorai](customer-mapping.md#payment-day-lines-cds-v2-to-msdyn_paymentdaylines) sablon a vevőkhöz és a szállítókhoz tartozó fizetési napok sorainak hivatkozási adatait szinkronizálja.</span><span class="sxs-lookup"><span data-stu-id="a6150-150">The [payment day lines](customer-mapping.md#payment-day-lines-cds-v2-to-msdyn_paymentdaylines) template synchronizes payment day lines reference data for customers and vendors.</span></span>
<span data-ttu-id="a6150-151">Fizetési napok, CDS</span><span class="sxs-lookup"><span data-stu-id="a6150-151">Payment days CDS</span></span>            | <span data-ttu-id="a6150-152">msdyn_paymentdays</span><span class="sxs-lookup"><span data-stu-id="a6150-152">msdyn_paymentdays</span></span>               | <span data-ttu-id="a6150-153">A [fizetési napok](customer-mapping.md#payment-days-cds-to-msdyn_paymentdays) sablon a vevők és a szállítók fizetési napokra vonatkozó hivatkozási adatait szinkronizálja.</span><span class="sxs-lookup"><span data-stu-id="a6150-153">The [payment days](customer-mapping.md#payment-days-cds-to-msdyn_paymentdays) template synchronizes payment days reference data, for both customers and vendors.</span></span>
<span data-ttu-id="a6150-154">Fizetési feltételek</span><span class="sxs-lookup"><span data-stu-id="a6150-154">Terms of payment</span></span>            | <span data-ttu-id="a6150-155">msdyn_paymentterms</span><span class="sxs-lookup"><span data-stu-id="a6150-155">msdyn_paymentterms</span></span>              | <span data-ttu-id="a6150-156">A [fizetési feltételek](customer-mapping.md#terms-of-payment-to-msdyn_paymentterms) sablon a vevők és szállítók fizetési feltételekre vonatkozó hivatkozási adatait szinkronizálja.</span><span class="sxs-lookup"><span data-stu-id="a6150-156">The [terms of payment](customer-mapping.md#terms-of-payment-to-msdyn_paymentterms) template synchronizes payment terms reference data, for both customers and vendors.</span></span>
<span data-ttu-id="a6150-157">Névutótagok</span><span class="sxs-lookup"><span data-stu-id="a6150-157">Name affixes</span></span>                | <span data-ttu-id="a6150-158">msdyn_nameaffixes</span><span class="sxs-lookup"><span data-stu-id="a6150-158">msdyn_nameaffixes</span></span>               | <span data-ttu-id="a6150-159">A [névutótagok](customer-mapping.md#name-affixes-to-msdyn_nameaffixes) sablon a vevők és szállítók névutótagjaira vonatkozó hivatkozási adatokat szinkronizálja.</span><span class="sxs-lookup"><span data-stu-id="a6150-159">The [name affixes](customer-mapping.md#name-affixes-to-msdyn_nameaffixes) template synchronizes name affixes reference data, for both customers and vendors.</span></span>

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [Vendors](includes/VendorsV2-msdyn-vendors.md)]

[!include [Vendor groups](includes/VendVendorGroup-msdyn-vendorgroups.md)]

[!include [Vendor payment methods](includes/VendorPaymentMethod-msdyn-vendorpaymentmethods.md)]