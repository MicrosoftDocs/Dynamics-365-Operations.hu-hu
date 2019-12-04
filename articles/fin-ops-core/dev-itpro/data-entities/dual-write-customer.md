---
title: Integrált vevői alapadat
description: Ez a témakör az ügyféladatok integrációját ismerteti a Finance and Operations és a Common Data Service között.
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
ms.openlocfilehash: 09d985e5c6816ec0c718aaf418f4e85fb828f1c6
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2769683"
---
# <a name="integrated-customer-master"></a><span data-ttu-id="8600b-103">Integrált vevői alapadat</span><span class="sxs-lookup"><span data-stu-id="8600b-103">Integrated customer master</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8600b-104">Az ügyfélbejegyzések általában egynél több alkalmazásban is alapadatok lehetnek.</span><span class="sxs-lookup"><span data-stu-id="8600b-104">It's typical for customer records to be mastered in more than one application.</span></span> <span data-ttu-id="8600b-105">Például az értékesítési tevékenység üzleti vevőrekordokat hozhat be egy Sales alkalmazáson keresztül, és az e-kereskedelmi vagy a kiskereskedelmi értékesítés az ügyfélbejegyzéseket hozhat be egy Finance and Operations alkalmazáson keresztül.</span><span class="sxs-lookup"><span data-stu-id="8600b-105">For example, sales activity can bring in commercial customer records through a Sales application, and e-Commerce or retail sales can bring in customer records through a Finance and Operations application.</span></span> <span data-ttu-id="8600b-106">Függetlenül attól, hogy honnan származik az ügyfélrekord, az a színfalak mögött az integrálva lesz az alkalmazáshatárokon és infrastrukturális különbségeken túl.</span><span class="sxs-lookup"><span data-stu-id="8600b-106">Regardless of where the customer record originates, it's integrated behind the scenes across application boundaries and infrastructure differences.</span></span> <span data-ttu-id="8600b-107">Az integrált ügyfél alapadat-kezelés segít a több alapadattal rendelkező forgatókönyveknél abban, hogy átfogó képet kapjon az ügyfélről a teljes Dynamics 365 alkalmazáscsomagban.</span><span class="sxs-lookup"><span data-stu-id="8600b-107">Integrated customer mastering helps handle multi-mastering scenarios and provides a comprehensive view of the customer to the Dynamics 365 application suite.</span></span>

## <a name="customer-data-flow"></a><span data-ttu-id="8600b-108">Vevő adatfolyama</span><span class="sxs-lookup"><span data-stu-id="8600b-108">Customer data flow</span></span>

<span data-ttu-id="8600b-109">A *Vevő* egy jól meghatározott fogalom az alkalmazásokban.</span><span class="sxs-lookup"><span data-stu-id="8600b-109">*Customer* is a well-defined concept in applications.</span></span> <span data-ttu-id="8600b-110">Ezért az ügyféladatok integrációja mindössze az ügyfélkoncepció harmonizálását jelenti a két alkalmazás között.</span><span class="sxs-lookup"><span data-stu-id="8600b-110">Therefore, the integration of customer data just involves harmonizing the customer concept between the two applications.</span></span> <span data-ttu-id="8600b-111">A következő ábra ábrázolja az ügyféladatok áramlását.</span><span class="sxs-lookup"><span data-stu-id="8600b-111">The following illustration shows the customer data flow.</span></span>

![Vevő adatfolyama](media/dual-write-customer-data-flow.png)

<span data-ttu-id="8600b-113">Az ügyfeleknek általánosságban két típusa van: kereskedelmi/vállalati ügyfelek és a fogyasztók/végfelhasználók.</span><span class="sxs-lookup"><span data-stu-id="8600b-113">Customers can be broadly classified into two types: commercial/organizational customers and consumers/end users.</span></span> <span data-ttu-id="8600b-114">E A két vevőtípust eltérően van tárolva és kezelve a Finance and Operations és Common Data Service programokban.</span><span class="sxs-lookup"><span data-stu-id="8600b-114">These two types of customers are stored and handled differently in Finance and Operations and Common Data Service.</span></span>

<span data-ttu-id="8600b-115">A Finance and Operations alkalmazásban a kereskedelmi/vállalati vásárlók és fogyasztók/végfelhasználók egy táblában vannak regisztrálva, ennek neve **CustTable** (CustomerCustomerV3Entity), és mindkettő a **Típus** attribútum alapján van osztályozva.</span><span class="sxs-lookup"><span data-stu-id="8600b-115">In Finance and Operations, both commercial/organizational customers and consumers/end users are mastered in a single table that is named **CustTable** (CustomerCustomerV3Entity), and they are classified based on the **Type** attribute.</span></span> <span data-ttu-id="8600b-116">(Ha **Típus** beállítása **Szervezet**, akkor a vevő kereskedelmi/vállalati vevő, ha a **Típus** beállítása **Személy**, akkor a vevő fogyasztó/végfelhasználó.) Az elsődleges kapcsolattartó adatait az SMMContactPersonEntity entitáson keresztül kezeli a rendszer.</span><span class="sxs-lookup"><span data-stu-id="8600b-116">(If **Type** is set to **Organization**, the customer is a commercial/organizational customer, and if **Type** is set to **Person**, the customer is a consumer/end user.) The primary contact person information is handled through the SMMContactPersonEntity entity.</span></span>

<span data-ttu-id="8600b-117">A Common Data Service megoldásban a kereskedelmi/válalati ügyfelek az Ügyfél entitásban vannak regisztrálva és akkor azonosítják ügyfelként, ha **RelationshipType** attribútum értéke **Ügyfél**.</span><span class="sxs-lookup"><span data-stu-id="8600b-117">In Common Data Service, commercial/organizational customers are mastered in the Account entity and are identified as customers when the **RelationshipType** attribute is set to **Customer**.</span></span> <span data-ttu-id="8600b-118">A Névjegy entitás képviseli a fogyasztókat/végfelhasználókat és a kapcsolattartót is.</span><span class="sxs-lookup"><span data-stu-id="8600b-118">Both consumers/end users and the contact person are represented by the Contact entity.</span></span> <span data-ttu-id="8600b-119">Az ügyfél/végfelhasználó és a kapcsolattartó személy közötti egyértelmű elkülönítés biztosítása érdekében **Kapcsolattartó** entitásnak egy **Eladható**logikai jelölője van.</span><span class="sxs-lookup"><span data-stu-id="8600b-119">To provide a clear separation between a consumer/end user and a contact person, the **Contact** entity has a Boolean flag that is named **Sellable**.</span></span> <span data-ttu-id="8600b-120">Ha az **Eladható** értéke **Igaz**, a kapcsolattartó fogyasztó/végfelhasználó, és a kapcsolattartóhoz létrehozhatók árajánlatok és megrendelések.</span><span class="sxs-lookup"><span data-stu-id="8600b-120">When **Sellable** is **True**, the contact is a consumer/end user, and quotations and orders can be created for that contact.</span></span> <span data-ttu-id="8600b-121">Ha az **Eladható** értéke **Hamis**, a kapcsolattartó csak egy ügyfél elsődleges kapcsolattartó személye.</span><span class="sxs-lookup"><span data-stu-id="8600b-121">When **Sellable** is **False**, the contact is just a primary contact person of a customer.</span></span>

<span data-ttu-id="8600b-122">Ha egy nem eladható kapcsolat részt vesz egy árajánlatban vagy rendelési folyamatban, az **Eladható** értéke **Igaz**, hogy a kapcsolattartó eladható kapcsolattartóként legyen megjelölve.</span><span class="sxs-lookup"><span data-stu-id="8600b-122">When a non-sellable contact participates in a quotation or order process, **Sellable** is set to **True** to flag the contact as a sellable contact.</span></span> <span data-ttu-id="8600b-123">Az eladhatóvá válta kapcsolattartó eladható kapcsolattartó marad.</span><span class="sxs-lookup"><span data-stu-id="8600b-123">A contact that has become a sellable contact remains a sellable contact.</span></span>

## <a name="templates"></a><span data-ttu-id="8600b-124">Sablonok</span><span class="sxs-lookup"><span data-stu-id="8600b-124">Templates</span></span>

<span data-ttu-id="8600b-125">Az ügyféladatok a vevőre vonatkozó összes információt tartalmazzák, például a vevőcsoportot, a címeket, a kapcsolattartási adatokat, a fizetési profilt, a számlaprofilt és a hűségi állapotot.</span><span class="sxs-lookup"><span data-stu-id="8600b-125">Customer data includes all information about the customer, such as the customer group, addresses, contact information, payment profile, invoice profile, and loyalty status.</span></span> <span data-ttu-id="8600b-126">Az entitásleképezések gyűjteményei az alábbi tábla szerint működnek együtt az ügyféladata-interakció során.</span><span class="sxs-lookup"><span data-stu-id="8600b-126">A collection of entity maps works together during customer data interaction, as shown in the following table.</span></span>

<span data-ttu-id="8600b-127">Finance and Operations alkalmazások</span><span class="sxs-lookup"><span data-stu-id="8600b-127">Finance and Operations apps</span></span> | <span data-ttu-id="8600b-128">Egyéb Dynamics 365 alkalmazások</span><span class="sxs-lookup"><span data-stu-id="8600b-128">Other Dynamics 365 apps</span></span>         | <span data-ttu-id="8600b-129">Leírás</span><span class="sxs-lookup"><span data-stu-id="8600b-129">Description</span></span>
----------------------------|---------------------------------|------------
<span data-ttu-id="8600b-130">CDS névjegyek V2</span><span class="sxs-lookup"><span data-stu-id="8600b-130">CDS Contacts V2</span></span>             | <span data-ttu-id="8600b-131">kapcsolattartók</span><span class="sxs-lookup"><span data-stu-id="8600b-131">contacts</span></span>                        | <span data-ttu-id="8600b-132">Ez a sablon a vevők és a szállítók összes elsődleges, másodlagos és harmadlagos kapcsolattartási adatát szinkronizálja.</span><span class="sxs-lookup"><span data-stu-id="8600b-132">This template synchronizes all primary, secondary, and tertiary contact information, for both customers and vendors.</span></span>
<span data-ttu-id="8600b-133">Vevőcsoportok</span><span class="sxs-lookup"><span data-stu-id="8600b-133">Customer groups</span></span>             | <span data-ttu-id="8600b-134">msdyn_customergroups</span><span class="sxs-lookup"><span data-stu-id="8600b-134">msdyn_customergroups</span></span>            | <span data-ttu-id="8600b-135">Ez a sablon szinkronizálja a vevői csoport adatait.</span><span class="sxs-lookup"><span data-stu-id="8600b-135">This template synchronizes customer group information.</span></span>
<span data-ttu-id="8600b-136">Vevő fizetési módszere</span><span class="sxs-lookup"><span data-stu-id="8600b-136">Customer payment method</span></span>     | <span data-ttu-id="8600b-137">msdyn_customerpaymentmethods</span><span class="sxs-lookup"><span data-stu-id="8600b-137">msdyn_customerpaymentmethods</span></span>    | <span data-ttu-id="8600b-138">Ez a sablon szinkronizálja a vevők fizetési módra vonatkozó adatait.</span><span class="sxs-lookup"><span data-stu-id="8600b-138">This template synchronizes customer payment method information.</span></span>
<span data-ttu-id="8600b-139">Vevők V3</span><span class="sxs-lookup"><span data-stu-id="8600b-139">Customers V3</span></span>                | <span data-ttu-id="8600b-140">számlák</span><span class="sxs-lookup"><span data-stu-id="8600b-140">accounts</span></span>                        | <span data-ttu-id="8600b-141">Ez a sablon szinkronizálja a vevői törzsadatokat a kereskedelmi és a vállalati ügyfelekhez.</span><span class="sxs-lookup"><span data-stu-id="8600b-141">This template synchronizes customer master information for commercial and organizational customers.</span></span>
<span data-ttu-id="8600b-142">Vevők V3</span><span class="sxs-lookup"><span data-stu-id="8600b-142">Customers V3</span></span>                | <span data-ttu-id="8600b-143">kapcsolattartók</span><span class="sxs-lookup"><span data-stu-id="8600b-143">contacts</span></span>                        | <span data-ttu-id="8600b-144">Ez a sablon szinkronizálja a vevőkhöz és a végfelhasználókhoz tartozó vevői alapadatokat.</span><span class="sxs-lookup"><span data-stu-id="8600b-144">This template synchronizes customer master data for consumers and end users.</span></span>
<span data-ttu-id="8600b-145">Hűségkártya</span><span class="sxs-lookup"><span data-stu-id="8600b-145">Loyalty card</span></span>                | <span data-ttu-id="8600b-146">msdyn_loyaltycards</span><span class="sxs-lookup"><span data-stu-id="8600b-146">msdyn_loyaltycards</span></span>              | <span data-ttu-id="8600b-147">Ez a sablon szinkronizálja a vevői hűségkártya adatait.</span><span class="sxs-lookup"><span data-stu-id="8600b-147">This template synchronizes customer loyalty card information.</span></span>
<span data-ttu-id="8600b-148">Névutótagok</span><span class="sxs-lookup"><span data-stu-id="8600b-148">Name affixes</span></span>                | <span data-ttu-id="8600b-149">msdyn_nameaffixes</span><span class="sxs-lookup"><span data-stu-id="8600b-149">msdyn_nameaffixes</span></span>               | <span data-ttu-id="8600b-150">Ez a sablon szinkronizálja a vevők és szállítók névutótagjaira vonatkozó hivatkozási adatokat.</span><span class="sxs-lookup"><span data-stu-id="8600b-150">This template synchronizes name affixes reference data, for both customers and vendors.</span></span>
<span data-ttu-id="8600b-151">Fizetési nap sorai, CDS V2</span><span class="sxs-lookup"><span data-stu-id="8600b-151">Payment day lines CDS V2</span></span>    | <span data-ttu-id="8600b-152">msdyn_paymentdaylines</span><span class="sxs-lookup"><span data-stu-id="8600b-152">msdyn_paymentdaylines</span></span>           | <span data-ttu-id="8600b-153">Ez a sablon szinkronizálja a vevők és szállítók fizetési nap soraira vonatkozó hivatkozási adatait.</span><span class="sxs-lookup"><span data-stu-id="8600b-153">This template synchronizes payment day lines reference data, for both customers and vendors.</span></span>
<span data-ttu-id="8600b-154">Fizetési napok, CDS</span><span class="sxs-lookup"><span data-stu-id="8600b-154">Payment days CDS</span></span>            | <span data-ttu-id="8600b-155">msdyn_paymentdays</span><span class="sxs-lookup"><span data-stu-id="8600b-155">msdyn_paymentdays</span></span>               | <span data-ttu-id="8600b-156">Ez a sablon szinkronizálja a vevők és szállítók fizetési napokra vonatkozó hivatkozási adatait.</span><span class="sxs-lookup"><span data-stu-id="8600b-156">This template synchronizes payment days reference data, for both customers and vendors.</span></span>
<span data-ttu-id="8600b-157">Kifizetési lista sorai</span><span class="sxs-lookup"><span data-stu-id="8600b-157">Payment schedule lines</span></span>      | <span data-ttu-id="8600b-158">msdyn_paymentschedulelines</span><span class="sxs-lookup"><span data-stu-id="8600b-158">msdyn_paymentschedulelines</span></span>      | <span data-ttu-id="8600b-159">Szinkronizálja a vevők és szállítók fizetési ütemezés soraira vonatkozó hivatkozási adatait.</span><span class="sxs-lookup"><span data-stu-id="8600b-159">Syncs payment schedule lines reference data, for both customers and vendors.</span></span>
<span data-ttu-id="8600b-160">Fizetési ütemezés</span><span class="sxs-lookup"><span data-stu-id="8600b-160">Payment schedule</span></span>            | <span data-ttu-id="8600b-161">msdyn_paymentschedules</span><span class="sxs-lookup"><span data-stu-id="8600b-161">msdyn_paymentschedules</span></span>          | <span data-ttu-id="8600b-162">Ez a sablon szinkronizálja a vevők és szállítók fizetési ütemezésre vonatkozó hivatkozási adatait.</span><span class="sxs-lookup"><span data-stu-id="8600b-162">This template synchronizes payment schedule reference data, for both customers and vendors.</span></span>
<span data-ttu-id="8600b-163">Fizetési feltételek</span><span class="sxs-lookup"><span data-stu-id="8600b-163">Terms of payment</span></span>            | <span data-ttu-id="8600b-164">msdyn_paymentterms</span><span class="sxs-lookup"><span data-stu-id="8600b-164">msdyn_paymentterms</span></span>              | <span data-ttu-id="8600b-165">Ez a sablon szinkronizálja a vevők és szállítók fizetési feltételekre vonatkozó hivatkozási adatait.</span><span class="sxs-lookup"><span data-stu-id="8600b-165">This template synchronizes payment terms (terms of payment) reference data, for both customers and vendors.</span></span>

[!include [banner](../includes/dual-write-symbols.md)]

[!include [mapping contacts contacts](dual-write/CDSContactsV2-contacts.md)]

[!include [mapping customer group](dual-write/CustCustomerGroup-msdyn-customergroups.md)]

[!include [mapping customer payment method](dual-write/CustomerPaymentMethod-msdyn-customerpaymentmethods.md)]

[!include [mapping customer accounts](dual-write/CustomersV3-accounts.md)]

[!include [mapping customer contacts](dual-write/CustomersV3-contacts.md)]

[!include [mapping loyalty card](dual-write/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping name affixes](dual-write/NameAffixes-msdyn-nameaffixes.md)]

[!include [mapping payment day lines](dual-write/PaymentDayLinesCdsV2-msdyn-paymentdaylines.md)]

[!include [mapping payment days](dual-write/PaymentDaysCds-msdyn-paymentdays.md)]

[!include [mapping payment schedule lines](dual-write/PaymentScheduleLines-msdyn-paymentschedulelines.md)]

[!include [mapping payment schedules](dual-write/PaymentSchedules-msdyn-paymentschedules.md)]

[!include [mapping terms of payment](dual-write/TermsofPayment-msdyn-paymentterms.md)]
