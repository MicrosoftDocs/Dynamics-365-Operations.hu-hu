---
title: Integrált szállítói alapadat
description: Ez a témakör a szállítói adatok integrációját ismerteti a Finance and Operations alkalmazás és a Dataverse között.
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
ms.openlocfilehash: 636bc57b5ef09d605744f4857fd5fbefceac4875
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685485"
---
# <a name="integrated-vendor-master"></a>Integrált szállítói alapadat

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



A *szállító* kifejezés egy szállító szervezetre vagy egy olyan kizárólagos tulajdonosra vonatkozik, aki árukat vagy szolgáltatásokat nyújt egy vállalkozásnak. A *szállító* fogalmat ugyan kiterjedten használják a Microsoft Dynamics 365 Supply Chain Management alkalmazásban, a szállító fogalma nem létezik más Dynamics 365 modellvezérelt alkalmazásaiban. A szállítói adatok tárolására azonban lehetősége van az **Ügyfél/kapcsolattartó** entitás túlterhelésével. A integrált szállító alapadat a Dynamics 365 modellvezérelt alkalmazásokban explicit szállítói fogalmat vezet be. Használhatja az új szállító megoldást vagy a szállítói adatokat a **Partner/kapcsolattartó** entitásban is tárolhatja. A kettős írás mindkét megközelítést támogatja.

Mindkét módszernél a szállítói adatok integrálva lesznek a Dynamics 365 Supply Chain Management, a Dynamics 365 Sales, a Dynamics 365 Field Service és Power Apps portálok között. A Supply Chain Management alkalmazásban az adatok olyan munkafolyamatokhoz érhetők el, mint például a beszerzési igénylések és a beszerzési rendelések.

## <a name="vendor-data-flow"></a>Szállítói adatok áramlása

Használhatja az új szállító megoldást ha a szállítói adatokat nem szeretné a **Partner/kapcsolattartó** entitásban tárolni a Dataverse megoldásban.

![Szállítói adatok áramlása](media/dual-write-vendor-data-flow.png)

Ha a szállítói adatokat továbbra is a **Partner/kapcsolattartó** szeretné tárolni, használhatja a kibővített szállítói megoldást. A kiterjesztett szállítói megoldás használatához konfigurálnia kell a szállítói munkafolyamatokat a kettős írás megoldási csomagjában. További információ: [Váltás a szállítói arculatok között](vendor-switch.md).

![Bővített szállítói adatok áramlása](media/dual-write-vendor-detail.jpg)

> [!TIP]
> Ha önkiszolgáló szállítókhoz használ Power Apps portálokat, akkor a szállítói információ közvetlenül a Finance and Operations alkalmazásokba is áramoltathatók.

## <a name="templates"></a>Sablonok

A szállítói adatok között a szállító minden részlete (például a szállítói csoport, a címek, a kapcsolatfelvételi adatok, a fizetési és a számlázási profil) szerepel. Ahogy az alábbi táblázatban látható, az táblaleképezések gyűjteménye együttműködik a szállítói adatokkal végzett interakciók során.

Finance and Operations-alkalmazásoknak | Egyéb Dynamics 365 alkalmazások     | Leírás
----------------------------|-----------------------------|------------
Szállító V2                   | Könyvelési számla                     | Azok a cégek, amelyek a Számla entitással tárolják a szállítói adatokat, továbbra is változás nélkül használhatják ezt a megoldást. A Finance and Operations alkalmazások integrációjának köszönhető explicit szállítói funkciókat ugyancsak kihasználhatja.
Szállító V2                   | Msdyn\_vendors              | A szállítókhoz egyéni megoldást használó cégek a Finance and Operations-alkalmazások integrációjának köszönhetően kihasználhatják a Dataverse rendszerben bevezetett kész szállítói fogalmat. 
Szállítói csoportok               | msdyn\_vendorgroups         | Ez a sablon szinkronizálja a szállítói csoport adatait.
Szállítói fizetési mód       | msdyn\_vendorpaymentmethods | Ez a sablon szinkronizálja a szállító fizetési módra vonatkozó adatait.
CDS névjegyek V2             | kapcsolattartók                    | A [névjegyek](customer-mapping.md#cds-contacts-v2-to-contacts) sablon a vevők és a szállítók összes elsődleges, másodlagos és harmadlagos kapcsolattartási adatát szinkronizálja.
Kifizetési lista sorai      | msdyn\_paymentschedulelines | A [fizetési ütemezés sorai](customer-mapping.md#payment-schedule-lines-to-msdyn_paymentschedulelines) sablon a vevők és a szállítók hivatkozási adatait szinkronizálja.
Kifizetés ütemezése            | msdyn\_paymentschedules     | A [fizetési ütemezések](customer-mapping.md#payment-schedule-to-msdyn_paymentschedules) sablon a vevők és a szállítók fizetési ütemezésre vonatkozó hivatkozási adatait szinkronizálja.
Fizetési nap sorai, CDS V2    | msdyn\_paymentdaylines      | A [fizetési nap sorai](customer-mapping.md#payment-day-lines-cds-v2-to-msdyn_paymentdaylines) sablon a vevőkhöz és a szállítókhoz tartozó fizetési napok sorainak hivatkozási adatait szinkronizálja.
Fizetési napok, CDS            | msdyn\_paymentdays          | A [fizetési napok](customer-mapping.md#payment-days-cds-to-msdyn_paymentdays) sablon a vevők és a szállítók fizetési napokra vonatkozó hivatkozási adatait szinkronizálja.
Fizetési feltételek            | msdyn\_paymentterms         | A [fizetési feltételek](customer-mapping.md#terms-of-payment-to-msdyn_paymentterms) sablon a vevők és szállítók fizetési feltételekre vonatkozó hivatkozási adatait szinkronizálja.
Névutótagok                | msdyn\_nameaffixes          | A [névutótagok](customer-mapping.md#name-affixes-to-msdyn_nameaffixes) sablon a vevők és szállítók névutótagjaira vonatkozó hivatkozási adatokat szinkronizálja.

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [Vendors](includes/VendorsV2-msdyn-vendors.md)]

[!include [Vendor groups](includes/VendVendorGroup-msdyn-vendorgroups.md)]

[!include [Vendor payment methods](includes/VendorPaymentMethod-msdyn-vendorpaymentmethods.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]