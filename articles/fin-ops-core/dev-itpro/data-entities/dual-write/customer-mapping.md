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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 36716c302d86bc5715798bf4cf4899f666d0872c
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997454"
---
# <a name="integrated-customer-master"></a><span data-ttu-id="09c74-103">Integrált vevői alapadat</span><span class="sxs-lookup"><span data-stu-id="09c74-103">Integrated customer master</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="09c74-104">A vevői adatok több mint egy Dynamics 365 alkalmazásban is elsajátíthatók.</span><span class="sxs-lookup"><span data-stu-id="09c74-104">Customer data can be mastered in more than one Dynamics 365 application.</span></span> <span data-ttu-id="09c74-105">Egy vevői rekord például származhat a Dynamics 365 Sales (a Dynamics 365 egyik modellvezérelt alkalmazása) értékesítési tevékenységéből, illetve a Dynamics 365 Commerce (egy Finance and Operations-alkalmazás) kiskereskedelmi tevékenységéből.</span><span class="sxs-lookup"><span data-stu-id="09c74-105">For example, a customer record can originate though sales activity in Dynamics 365 Sales (a model-driven app in Dynamics 365), or a record can originate through retail activity in Dynamics 365 Commerce (a Finance and Operations app).</span></span> <span data-ttu-id="09c74-106">Nem számít, hogy honnan származik a vevői adatok, a program a háttérben integrálta.</span><span class="sxs-lookup"><span data-stu-id="09c74-106">No matter where where the customer data originates, it is integrated behind the scenes.</span></span> <span data-ttu-id="09c74-107">Az integrált vevői alapadat bármely Dynamics 365 alkalmazásban biztosítja a vevők alapadatainak létrehozásának rugalmasságát, és a vevő Dynamics 365 alkalmazáscsomagon keresztüli átfogó nézetét.</span><span class="sxs-lookup"><span data-stu-id="09c74-107">Integrated customer master gives you the flexibility to master customer data in any Dynamics 365 application and provides a comprehensive view of the customer across the Dynamics 365 application suite.</span></span>

## <a name="customer-data-flow"></a><span data-ttu-id="09c74-108">Vevő adatfolyama</span><span class="sxs-lookup"><span data-stu-id="09c74-108">Customer data flow</span></span>

<span data-ttu-id="09c74-109">A *Vevő* egy jól meghatározott fogalom az alkalmazásokban.</span><span class="sxs-lookup"><span data-stu-id="09c74-109">*Customer* is a well-defined concept in applications.</span></span> <span data-ttu-id="09c74-110">Ezért az ügyféladatok integrációja mindössze az ügyfélkoncepció harmonizálását jelenti a két alkalmazás között.</span><span class="sxs-lookup"><span data-stu-id="09c74-110">Therefore, the integration of customer data just involves harmonizing the customer concept between the two applications.</span></span> <span data-ttu-id="09c74-111">A következő ábra ábrázolja az ügyféladatok áramlását.</span><span class="sxs-lookup"><span data-stu-id="09c74-111">The following illustration shows the customer data flow.</span></span>

![Vevő adatfolyama](media/dual-write-customer-data-flow.png)

<span data-ttu-id="09c74-113">Az ügyfeleknek általánosságban két típusa van: kereskedelmi/vállalati ügyfelek és a fogyasztók/végfelhasználók.</span><span class="sxs-lookup"><span data-stu-id="09c74-113">Customers can be broadly classified into two types: commercial/organizational customers and consumers/end users.</span></span> <span data-ttu-id="09c74-114">A két vevőtípus eltérően van tárolva és kezelve a Finance and Operations és Common Data Service programokban.</span><span class="sxs-lookup"><span data-stu-id="09c74-114">These two types of customers are stored and handled differently in Finance and Operations and Common Data Service.</span></span>

<span data-ttu-id="09c74-115">A Finance and Operations alkalmazásban a kereskedelmi/vállalati vásárlók és fogyasztók/végfelhasználók egy táblában vannak regisztrálva, ennek neve **CustTable** (CustCustomerV3Entity), és mindkettő a **Típus** attribútum alapján van osztályozva.</span><span class="sxs-lookup"><span data-stu-id="09c74-115">In Finance and Operations, both commercial/organizational customers and consumers/end users are mastered in a single table that is named **CustTable** (CustCustomerV3Entity), and they are classified based on the **Type** attribute.</span></span> <span data-ttu-id="09c74-116">(Ha **Típus** beállítása **Szervezet** , akkor a vevő kereskedelmi/vállalati vevő, ha a **Típus** beállítása **Személy** , akkor a vevő fogyasztó/végfelhasználó.) Az elsődleges kapcsolattartó adatait az SMMContactPersonEntity entitáson keresztül kezeli a rendszer.</span><span class="sxs-lookup"><span data-stu-id="09c74-116">(If **Type** is set to **Organization** , the customer is a commercial/organizational customer, and if **Type** is set to **Person** , the customer is a consumer/end user.) The primary contact person information is handled through the SMMContactPersonEntity entity.</span></span>

<span data-ttu-id="09c74-117">A Common Data Service megoldásban a kereskedelmi/válalati ügyfelek az Ügyfél entitásban vannak regisztrálva és akkor azonosítják ügyfelként, ha **RelationshipType** attribútum értéke **Ügyfél**.</span><span class="sxs-lookup"><span data-stu-id="09c74-117">In Common Data Service, commercial/organizational customers are mastered in the Account entity and are identified as customers when the **RelationshipType** attribute is set to **Customer**.</span></span> <span data-ttu-id="09c74-118">A Névjegy entitás képviseli a fogyasztókat/végfelhasználókat és a kapcsolattartót is.</span><span class="sxs-lookup"><span data-stu-id="09c74-118">Both consumers/end users and the contact person are represented by the Contact entity.</span></span> <span data-ttu-id="09c74-119">Az ügyfél/végfelhasználó és a kapcsolattartó személy közötti egyértelmű elkülönítés biztosítása érdekében **Kapcsolattartó** entitásnak egy **Eladható** logikai jelölője van.</span><span class="sxs-lookup"><span data-stu-id="09c74-119">To provide a clear separation between a consumer/end user and a contact person, the **Contact** entity has a Boolean flag that is named **Sellable**.</span></span> <span data-ttu-id="09c74-120">Ha az **Eladható** értéke **Igaz** , a kapcsolattartó fogyasztó/végfelhasználó, és a kapcsolattartóhoz létrehozhatók árajánlatok és megrendelések.</span><span class="sxs-lookup"><span data-stu-id="09c74-120">When **Sellable** is **True** , the contact is a consumer/end user, and quotations and orders can be created for that contact.</span></span> <span data-ttu-id="09c74-121">Ha az **Eladható** értéke **Hamis** , a kapcsolattartó csak egy ügyfél elsődleges kapcsolattartó személye.</span><span class="sxs-lookup"><span data-stu-id="09c74-121">When **Sellable** is **False** , the contact is just a primary contact person of a customer.</span></span>

<span data-ttu-id="09c74-122">Ha egy nem eladható kapcsolat részt vesz egy árajánlatban vagy rendelési folyamatban, az **Eladható** értéke **Igaz** , hogy a kapcsolattartó eladható kapcsolattartóként legyen megjelölve.</span><span class="sxs-lookup"><span data-stu-id="09c74-122">When a non-sellable contact participates in a quotation or order process, **Sellable** is set to **True** to flag the contact as a sellable contact.</span></span> <span data-ttu-id="09c74-123">Az eladhatóvá válta kapcsolattartó eladható kapcsolattartó marad.</span><span class="sxs-lookup"><span data-stu-id="09c74-123">A contact that has become a sellable contact remains a sellable contact.</span></span>

## <a name="templates"></a><span data-ttu-id="09c74-124">Sablonok</span><span class="sxs-lookup"><span data-stu-id="09c74-124">Templates</span></span>

<span data-ttu-id="09c74-125">Az ügyféladatok a vevőre vonatkozó összes információt tartalmazzák, például a vevőcsoportot, a címeket, a kapcsolattartási adatokat, a fizetési profilt, a számlaprofilt és a hűségi állapotot.</span><span class="sxs-lookup"><span data-stu-id="09c74-125">Customer data includes all information about the customer, such as the customer group, addresses, contact information, payment profile, invoice profile, and loyalty status.</span></span> <span data-ttu-id="09c74-126">Az entitásleképezések gyűjteményei az alábbi tábla szerint működnek együtt az ügyféladata-interakció során.</span><span class="sxs-lookup"><span data-stu-id="09c74-126">A collection of entity maps works together during customer data interaction, as shown in the following table.</span></span>

<span data-ttu-id="09c74-127">Finance and Operations-alkalmazásoknak</span><span class="sxs-lookup"><span data-stu-id="09c74-127">Finance and Operations apps</span></span> | <span data-ttu-id="09c74-128">Egyéb Dynamics 365 alkalmazások</span><span class="sxs-lookup"><span data-stu-id="09c74-128">Other Dynamics 365 apps</span></span>         | <span data-ttu-id="09c74-129">Leírás</span><span class="sxs-lookup"><span data-stu-id="09c74-129">Description</span></span>
----------------------------|---------------------------------|------------
<span data-ttu-id="09c74-130">CDS névjegyek V2</span><span class="sxs-lookup"><span data-stu-id="09c74-130">CDS Contacts V2</span></span>             | <span data-ttu-id="09c74-131">kapcsolattartók</span><span class="sxs-lookup"><span data-stu-id="09c74-131">contacts</span></span>                        | <span data-ttu-id="09c74-132">Ez a sablon a vevők és a szállítók összes elsődleges, másodlagos és harmadlagos kapcsolattartási adatát szinkronizálja.</span><span class="sxs-lookup"><span data-stu-id="09c74-132">This template synchronizes all primary, secondary, and tertiary contact information, for both customers and vendors.</span></span>
<span data-ttu-id="09c74-133">Vevőcsoportok</span><span class="sxs-lookup"><span data-stu-id="09c74-133">Customer groups</span></span>             | <span data-ttu-id="09c74-134">msdyn_customergroups</span><span class="sxs-lookup"><span data-stu-id="09c74-134">msdyn_customergroups</span></span>            | <span data-ttu-id="09c74-135">Ez a sablon szinkronizálja a vevői csoport adatait.</span><span class="sxs-lookup"><span data-stu-id="09c74-135">This template synchronizes customer group information.</span></span>
<span data-ttu-id="09c74-136">Vevő fizetési módszere</span><span class="sxs-lookup"><span data-stu-id="09c74-136">Customer payment method</span></span>     | <span data-ttu-id="09c74-137">msdyn_customerpaymentmethods</span><span class="sxs-lookup"><span data-stu-id="09c74-137">msdyn_customerpaymentmethods</span></span>    | <span data-ttu-id="09c74-138">Ez a sablon szinkronizálja a vevők fizetési módra vonatkozó adatait.</span><span class="sxs-lookup"><span data-stu-id="09c74-138">This template synchronizes customer payment method information.</span></span>
<span data-ttu-id="09c74-139">Vevők V3</span><span class="sxs-lookup"><span data-stu-id="09c74-139">Customers V3</span></span>                | <span data-ttu-id="09c74-140">számlák</span><span class="sxs-lookup"><span data-stu-id="09c74-140">accounts</span></span>                        | <span data-ttu-id="09c74-141">Ez a sablon szinkronizálja a vevői törzsadatokat a kereskedelmi és a vállalati ügyfelekhez.</span><span class="sxs-lookup"><span data-stu-id="09c74-141">This template synchronizes customer master information for commercial and organizational customers.</span></span>
<span data-ttu-id="09c74-142">Vevők V3</span><span class="sxs-lookup"><span data-stu-id="09c74-142">Customers V3</span></span>                | <span data-ttu-id="09c74-143">kapcsolattartók</span><span class="sxs-lookup"><span data-stu-id="09c74-143">contacts</span></span>                        | <span data-ttu-id="09c74-144">Ez a sablon szinkronizálja a vevőkhöz és a végfelhasználókhoz tartozó vevői alapadatokat.</span><span class="sxs-lookup"><span data-stu-id="09c74-144">This template synchronizes customer master data for consumers and end users.</span></span>
<span data-ttu-id="09c74-145">Névutótagok</span><span class="sxs-lookup"><span data-stu-id="09c74-145">Name affixes</span></span>                | <span data-ttu-id="09c74-146">msdyn_nameaffixes</span><span class="sxs-lookup"><span data-stu-id="09c74-146">msdyn_nameaffixes</span></span>               | <span data-ttu-id="09c74-147">Ez a sablon szinkronizálja a vevők és szállítók névutótagjaira vonatkozó hivatkozási adatokat.</span><span class="sxs-lookup"><span data-stu-id="09c74-147">This template synchronizes name affixes reference data, for both customers and vendors.</span></span>
<span data-ttu-id="09c74-148">Fizetési nap sorai, CDS V2</span><span class="sxs-lookup"><span data-stu-id="09c74-148">Payment day lines CDS V2</span></span>    | <span data-ttu-id="09c74-149">msdyn_paymentdaylines</span><span class="sxs-lookup"><span data-stu-id="09c74-149">msdyn_paymentdaylines</span></span>           | <span data-ttu-id="09c74-150">Ez a sablon szinkronizálja a vevők és szállítók fizetési nap soraira vonatkozó hivatkozási adatait.</span><span class="sxs-lookup"><span data-stu-id="09c74-150">This template synchronizes payment day lines reference data, for both customers and vendors.</span></span>
<span data-ttu-id="09c74-151">Fizetési napok, CDS</span><span class="sxs-lookup"><span data-stu-id="09c74-151">Payment days CDS</span></span>            | <span data-ttu-id="09c74-152">msdyn_paymentdays</span><span class="sxs-lookup"><span data-stu-id="09c74-152">msdyn_paymentdays</span></span>               | <span data-ttu-id="09c74-153">Ez a sablon szinkronizálja a vevők és szállítók fizetési napokra vonatkozó hivatkozási adatait.</span><span class="sxs-lookup"><span data-stu-id="09c74-153">This template synchronizes payment days reference data, for both customers and vendors.</span></span>
<span data-ttu-id="09c74-154">Kifizetési lista sorai</span><span class="sxs-lookup"><span data-stu-id="09c74-154">Payment schedule lines</span></span>      | <span data-ttu-id="09c74-155">msdyn_paymentschedulelines</span><span class="sxs-lookup"><span data-stu-id="09c74-155">msdyn_paymentschedulelines</span></span>      | <span data-ttu-id="09c74-156">Szinkronizálja a vevők és szállítók fizetési ütemezés soraira vonatkozó hivatkozási adatait.</span><span class="sxs-lookup"><span data-stu-id="09c74-156">Syncs payment schedule lines reference data, for both customers and vendors.</span></span>
<span data-ttu-id="09c74-157">Fizetési ütemezés</span><span class="sxs-lookup"><span data-stu-id="09c74-157">Payment schedule</span></span>            | <span data-ttu-id="09c74-158">msdyn_paymentschedules</span><span class="sxs-lookup"><span data-stu-id="09c74-158">msdyn_paymentschedules</span></span>          | <span data-ttu-id="09c74-159">Ez a sablon szinkronizálja a vevők és szállítók fizetési ütemezésre vonatkozó hivatkozási adatait.</span><span class="sxs-lookup"><span data-stu-id="09c74-159">This template synchronizes payment schedule reference data, for both customers and vendors.</span></span>
<span data-ttu-id="09c74-160">Fizetési feltételek</span><span class="sxs-lookup"><span data-stu-id="09c74-160">Terms of payment</span></span>            | <span data-ttu-id="09c74-161">msdyn_paymentterms</span><span class="sxs-lookup"><span data-stu-id="09c74-161">msdyn_paymentterms</span></span>              | <span data-ttu-id="09c74-162">Ez a sablon szinkronizálja a vevők és szállítók fizetési feltételekre vonatkozó hivatkozási adatait.</span><span class="sxs-lookup"><span data-stu-id="09c74-162">This template synchronizes payment terms (terms of payment) reference data, for both customers and vendors.</span></span>

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping contacts contacts](includes/CDSContactsV2-contacts.md)]

[!include [mapping customer group](includes/CustCustomerGroup-msdyn-customergroups.md)]

[!include [mapping customer payment method](includes/CustomerPaymentMethod-msdyn-customerpaymentmethods.md)]

[!include [mapping customer accounts](includes/CustomersV3-accounts.md)]

[!include [mapping customer contacts](includes/CustomersV3-contacts.md)]

[!include [mapping name affixes](includes/NameAffixes-msdyn-nameaffixes.md)]

[!include [mapping payment day lines](includes/PaymentDayLinesCdsV2-msdyn-paymentdaylines.md)]

[!include [mapping payment days](includes/PaymentDaysCds-msdyn-paymentdays.md)]

[!include [mapping payment schedule lines](includes/PaymentScheduleLines-msdyn-paymentschedulelines.md)]

[!include [mapping payment schedules](includes/PaymentSchedules-msdyn-paymentschedules.md)]

[!include [mapping terms of payment](includes/TermsofPayment-msdyn-paymentterms.md)]
