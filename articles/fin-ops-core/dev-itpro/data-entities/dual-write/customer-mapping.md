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
ms.openlocfilehash: 5643be99ac2c58f4da1a2a068e84bf526f8575cb
ms.sourcegitcommit: 164de749f394a133f223c526aa0c46bf922d1ea8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/04/2020
ms.locfileid: "3770012"
---
# <a name="integrated-customer-master"></a>Integrált vevői alapadat

[!include [banner](../../includes/banner.md)]


A vevői adatok több mint egy Dynamics 365 alkalmazásban is elsajátíthatók. Egy vevői rekord például származhat a Dynamics 365 Sales (a Dynamics 365 egyik modellvezérelt alkalmazása) értékesítési tevékenységéből, illetve a Dynamics 365 Commerce (egy Finance and Operations-alkalmazás) kiskereskedelmi tevékenységéből. Nem számít, hogy honnan származik a vevői adatok, a program a háttérben integrálta. Az integrált vevői alapadat bármely Dynamics 365 alkalmazásban biztosítja a vevők alapadatainak létrehozásának rugalmasságát, és a vevő Dynamics 365 alkalmazáscsomagon keresztüli átfogó nézetét.

## <a name="customer-data-flow"></a>Vevő adatfolyama

A *Vevő* egy jól meghatározott fogalom az alkalmazásokban. Ezért az ügyféladatok integrációja mindössze az ügyfélkoncepció harmonizálását jelenti a két alkalmazás között. A következő ábra ábrázolja az ügyféladatok áramlását.

![Vevő adatfolyama](media/dual-write-customer-data-flow.png)

Az ügyfeleknek általánosságban két típusa van: kereskedelmi/vállalati ügyfelek és a fogyasztók/végfelhasználók. A két vevőtípus eltérően van tárolva és kezelve a Finance and Operations és Common Data Service programokban.

A Finance and Operations alkalmazásban a kereskedelmi/vállalati vásárlók és fogyasztók/végfelhasználók egy táblában vannak regisztrálva, ennek neve **CustTable** (CustCustomerV3Entity), és mindkettő a **Típus** attribútum alapján van osztályozva. (Ha **Típus** beállítása **Szervezet**, akkor a vevő kereskedelmi/vállalati vevő, ha a **Típus** beállítása **Személy**, akkor a vevő fogyasztó/végfelhasználó.) Az elsődleges kapcsolattartó adatait az SMMContactPersonEntity entitáson keresztül kezeli a rendszer.

A Common Data Service megoldásban a kereskedelmi/válalati ügyfelek az Ügyfél entitásban vannak regisztrálva és akkor azonosítják ügyfelként, ha **RelationshipType** attribútum értéke **Ügyfél**. A Névjegy entitás képviseli a fogyasztókat/végfelhasználókat és a kapcsolattartót is. Az ügyfél/végfelhasználó és a kapcsolattartó személy közötti egyértelmű elkülönítés biztosítása érdekében **Kapcsolattartó** entitásnak egy **Eladható**logikai jelölője van. Ha az **Eladható** értéke **Igaz**, a kapcsolattartó fogyasztó/végfelhasználó, és a kapcsolattartóhoz létrehozhatók árajánlatok és megrendelések. Ha az **Eladható** értéke **Hamis**, a kapcsolattartó csak egy ügyfél elsődleges kapcsolattartó személye.

Ha egy nem eladható kapcsolat részt vesz egy árajánlatban vagy rendelési folyamatban, az **Eladható** értéke **Igaz**, hogy a kapcsolattartó eladható kapcsolattartóként legyen megjelölve. Az eladhatóvá válta kapcsolattartó eladható kapcsolattartó marad.

## <a name="templates"></a>Sablonok

Az ügyféladatok a vevőre vonatkozó összes információt tartalmazzák, például a vevőcsoportot, a címeket, a kapcsolattartási adatokat, a fizetési profilt, a számlaprofilt és a hűségi állapotot. Az entitásleképezések gyűjteményei az alábbi tábla szerint működnek együtt az ügyféladata-interakció során.

Finance and Operations-alkalmazásoknak | Egyéb Dynamics 365 alkalmazások         | Leírás
----------------------------|---------------------------------|------------
CDS névjegyek V2             | kapcsolattartók                        | Ez a sablon a vevők és a szállítók összes elsődleges, másodlagos és harmadlagos kapcsolattartási adatát szinkronizálja.
Vevőcsoportok             | msdyn_customergroups            | Ez a sablon szinkronizálja a vevői csoport adatait.
Vevő fizetési módszere     | msdyn_customerpaymentmethods    | Ez a sablon szinkronizálja a vevők fizetési módra vonatkozó adatait.
Vevők V3                | számlák                        | Ez a sablon szinkronizálja a vevői törzsadatokat a kereskedelmi és a vállalati ügyfelekhez.
Vevők V3                | kapcsolattartók                        | Ez a sablon szinkronizálja a vevőkhöz és a végfelhasználókhoz tartozó vevői alapadatokat.
Névutótagok                | msdyn_nameaffixes               | Ez a sablon szinkronizálja a vevők és szállítók névutótagjaira vonatkozó hivatkozási adatokat.
Fizetési nap sorai, CDS V2    | msdyn_paymentdaylines           | Ez a sablon szinkronizálja a vevők és szállítók fizetési nap soraira vonatkozó hivatkozási adatait.
Fizetési napok, CDS            | msdyn_paymentdays               | Ez a sablon szinkronizálja a vevők és szállítók fizetési napokra vonatkozó hivatkozási adatait.
Kifizetési lista sorai      | msdyn_paymentschedulelines      | Szinkronizálja a vevők és szállítók fizetési ütemezés soraira vonatkozó hivatkozási adatait.
Fizetési ütemezés            | msdyn_paymentschedules          | Ez a sablon szinkronizálja a vevők és szállítók fizetési ütemezésre vonatkozó hivatkozási adatait.
Fizetési feltételek            | msdyn_paymentterms              | Ez a sablon szinkronizálja a vevők és szállítók fizetési feltételekre vonatkozó hivatkozási adatait.

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
