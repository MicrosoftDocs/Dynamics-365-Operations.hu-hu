---
title: Integrált vevői alapadat
description: Ez a témakör az ügyféladatok integrációját ismerteti a Finance and Operations és a Dataverse között.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 41e4b6c192b6125a144e4d5ef952ba0975821d44
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8063289"
---
# <a name="integrated-customer-master"></a>Integrált vevői alapadat

[!include [banner](../../includes/banner.md)]



A vevői adatok több mint egy Dynamics 365 alkalmazásban is elsajátíthatók. Egy vevői sor például származhat a Dynamics 365 Sales (egy ügyfélkapcsolati alkalmazás) értékesítési tevékenységéből, illetve a Dynamics 365 Commerce (egy Finance and Operations alkalmazás) kiskereskedelmi tevékenységéből. Nem számít, hogy honnan származik a vevői adatok, a program a háttérben integrálta. Az integrált vevői alapadat bármely Dynamics 365 alkalmazásban biztosítja a vevők alapadatainak létrehozásának rugalmasságát, és a vevő Dynamics 365 alkalmazáscsomagon keresztüli átfogó nézetét.

## <a name="customer-data-flow"></a>Vevő adatfolyama

A *Vevő* egy jól meghatározott fogalom az alkalmazásokban. Ezért az ügyféladatok integrációja mindössze az ügyfélkoncepció harmonizálását jelenti a két alkalmazás között. A következő ábra ábrázolja az ügyféladatok áramlását.

![Vevő adatfolyama.](media/dual-write-customer-data-flow.png)

Az ügyfeleknek általánosságban két típusa van: kereskedelmi/vállalati ügyfelek és a fogyasztók/végfelhasználók. E A két vevőtípust eltérően van tárolva és kezelve a Finance and Operations és Dataverse programokban.

A Finance and Operations alkalmazásban mind a kereskedelmi/szervezeti ügyfelek, mind a fogyasztók/végfelhasználók egyetlen táblában vannak elsajátítva, amelynek neve **CustTable** (CustCustomerV3Entity), és az alapján vannak besorolva **típus** tulajdonság. (Ha **Típus** beállítása **Szervezet**, akkor a vevő kereskedelmi/vállalati vevő, ha a **Típus** beállítása **Személy**, akkor a vevő fogyasztó/végfelhasználó.) Az elsődleges kapcsolattartó adatait az SMMContactPersonEntity táblán keresztül kezeli a rendszer.

A Dataverse megoldásban a kereskedelmi/válalati ügyfelek az Ügyfél táblában vannak regisztrálva és akkor azonosítják ügyfelként, ha **RelationshipType** attribútum értéke **Ügyfél**. A Névjegy tábla képviseli a fogyasztókat/végfelhasználókat és a kapcsolattartót is. Az ügyfél/végfelhasználó és a kapcsolattartó személy közötti egyértelmű elkülönítés biztosítása érdekében **Kapcsolattartó** táblának egy **Eladható** logikai jelölője van. Ha az **Eladható** értéke **Igaz**, a kapcsolattartó fogyasztó/végfelhasználó, és a kapcsolattartóhoz létrehozhatók árajánlatok és megrendelések. Ha az **Eladható** értéke **Hamis**, a kapcsolattartó csak egy ügyfél elsődleges kapcsolattartó személye.

Ha egy nem eladható kapcsolat részt vesz egy árajánlatban vagy rendelési folyamatban, az **Eladható** értéke **Igaz**, hogy a kapcsolattartó eladható kapcsolattartóként legyen megjelölve. Az eladhatóvá válta kapcsolattartó eladható kapcsolattartó marad.

## <a name="templates"></a>Sablonok

Az ügyféladatok a vevőre vonatkozó összes információt tartalmazzák, például a vevőcsoportot, a címeket, a kapcsolattartási adatokat, a fizetési profilt, a számlaprofilt és a hűségi állapotot. Az táblaleképezések gyűjteményei az alábbi tábla szerint működnek együtt az ügyféladata-interakció során.

Finance and Operations alkalmazások | Customer Engagement alkalmazások         | Leírás
----------------------------|---------------------------------|------------
[CDS névjegyek V2](mapping-reference.md#115) | kapcsolattartók | Ez a sablon a vevők és a szállítók összes elsődleges, másodlagos és harmadlagos kapcsolattartási adatát szinkronizálja.
[Vevőcsoportok](mapping-reference.md#126) | msdyn_customergroups | Ez a sablon szinkronizálja a vevői csoport adatait.
[Vevő fizetési módszere](mapping-reference.md#127) | msdyn_customerpaymentmethods | Ez a sablon szinkronizálja a vevők fizetési módra vonatkozó adatait.
[Vevők V3](mapping-reference.md#101) | számlák | Ez a sablon szinkronizálja a vevői törzsadatokat a kereskedelmi és a vállalati ügyfelekhez.
[Vevők V3](mapping-reference.md#116) | kapcsolattartók | Ez a sablon szinkronizálja a vevőkhöz és a végfelhasználókhoz tartozó vevői alapadatokat.
[Névutótagok](mapping-reference.md#155) | msdyn_nameaffixes | Ez a sablon szinkronizálja a vevők és szállítók névutótagjaira vonatkozó hivatkozási adatokat.
[Fizetési nap sorai, CDS V2](mapping-reference.md#157) | msdyn_paymentdaylines | Ez a sablon szinkronizálja a vevők és szállítók fizetési nap soraira vonatkozó hivatkozási adatait.
[Fizetési napok, CDS](mapping-reference.md#158) | msdyn_paymentdays | Ez a sablon szinkronizálja a vevők és szállítók fizetési napokra vonatkozó hivatkozási adatait.
[Kifizetési lista sorai](mapping-reference.md#159) | msdyn_paymentschedulelines | Szinkronizálja a vevők és szállítók fizetési ütemezés soraira vonatkozó hivatkozási adatait.
[Fizetési ütemezés](mapping-reference.md#160) | msdyn_paymentschedules | Ez a sablon szinkronizálja a vevők és szállítók fizetési ütemezésre vonatkozó hivatkozási adatait.
[Fizetési feltételek](mapping-reference.md#161) | msdyn_paymentterms | Ez a sablon szinkronizálja a vevők és szállítók fizetési feltételekre vonatkozó hivatkozási adatait.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
