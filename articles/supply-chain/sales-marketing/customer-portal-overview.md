---
title: A Dynamics 365 Supply Chain Management Ügyfélportáljának áttekintése
description: Ez a témakör bemutatja a Ügyfélportált, valamint ismerteti, hogy kinek érdemes használnia, és hogyan működik.
author: dasani-madipalli
manager: tfehr
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 6b57365d8042c1d791ee2c50c5458a6595a58270
ms.sourcegitcommit: 713b5dfc76a6875d0ba6d86c5cbd585ea502cf9d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/01/2020
ms.locfileid: "3413969"
---
# <a name="customer-portal-for-dynamics-365-supply-chain-management-overview"></a>A Dynamics 365 Supply Chain Management Ügyfélportáljának áttekintése

## <a name="what-is-the-customer-portal"></a>Mi is az Ügyfélportál?

A korszerű ellátásilánc-rendszerek az integrációra támaszkodhatnak. Megkövetelik, hogy a készlet, a vevői igény és az értékesítési osztályok integrálva legyenek ahelyett, hogy különállnának. A Ügyfélportál segíti a Microsoft Dynamics 365 Supply Chain Management alkalmazást futtató szervezeteket, hogy fokozzák ezt az integrációt, és hatékonyabban tájékoztassák a vevőiket.

Az Ügyfélportál egy olyan [Power Apps-portálok](https://docs.microsoft.com/powerapps/maker/portals/overview) sablon amelyekben a vállalatok egy kívülről elérhető üzleti (B2B) webhelyet hoznak létre az értékesítési rendelés feldolgozásával kapcsolatos esetekhez. A sablon a [kettős írás](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page), Supply Chain Management és Power Apps-portálokkal teszi lehetővé a külső vállalati felhasználók számára, hogy adatokat hozzanak létre a vállalat Dynamics 365 környezetéből.

A Ügyfélportál-sablon minden olyan testreszabási funkcióval rendelkezik, amely a Power Apps portálok funkciója kínál. A sablon egyszerűen módosítható a vállalat márkájának megjelenítésére, a kibővített funkciók hozzáadásához, valamint a felhasználói élmény módosításához. A sablon által a gyári állapotban kínált összes funkció tetszés szerint módosítható.

> [!IMPORTANT]
> A sablon önmagában várhatóan nem teljesen működőképes. Ez csak egy segédtermék olyan felhasználók számára akik külső webhelyeket kívánnak létrehozni annak érdekében, hogy a vállalati vevők a Supply Chain Management alkalmazásból származó adatokkal léphessennek interakcióba.

> [!NOTE]
> Az Ügyfélportál dokumentációját az adminisztrátorok, a testreszabók és a rendszerintegrátorok irányítják, akik a Supply Chain Management telepítése során beállítja a Ügyfélportált. Az _ügyfél_ és a _felhasználó_ kifejezésekkel írja le azokat a személyeket, akik a Supply Chain Management alkalmazást futtató szervezethez ügyfelei, illetve azokat, akik a végső portált használni fogják.

## <a name="who-should-use-it"></a>Kinek érdemes használnia?

Az Ügyfélportál a Supply Chain Management alkalmazást futtató vállalatok számára készült, akik ezekkel a jellemzőkkel rendelkeznek:

- Egy kívülről elérhető webhelyet akarnak létrehozni, amely a rendelés feldolgozási adatait (például a rendelési állapotot vagy a partneradatokat) közvetlenül a Supply Chain Management rendszerükből a vállalati vevőknek kommunikálja.
- Átállnak a Dynamics AX 2012 alkalmazásról a Supply Chain Management megoldásra, és korábban [AX 2012 vevői önkiszolgáló portált](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/about-the-customer-self-service-portal) használták.

A következő típusú szervezetek **nem** jó jelöltek a Ügyfélportál kiépítéséhez:

- Azok a vállalatok, amelyek nem vállalati vevők számára kívánnak webhelyeket létrehozni. Ezeknek a vállalatoknak érdemes fontolóra venni egy [Dynamics 365 Commerce e-kereskedelmi webhely](https://docs.microsoft.com/dynamics365/commerce/create-ecommerce-site) létrehozását.
- Azok a vállalatok, amelyek már létező Power Apps portálok webhelyet alkalmaznak hasonló célra. Ezek a vállalatok nem kapnak további előnyöket az Ügyfélportáltól. Az Ügyfélportál egy sablon, amely útmutatóként működik, és kiindulópontként szolgál azoknak a vevőknek, akik kapcsolatot szeretnének létesíteni a kettős írás, a Supply Chain Management és a Power Apps-portálok között. Ha már van olyan webhelye, amely ezt a célt szolgálja, akkor lehet, hogy nem sok értéket jelentene az Ügyfélportál használata egy a webhely ismételt kiépítéséhez.

## <a name="how-does-it-work"></a>Hogyan működik?

Az Ügyfélportál Power Apps-portálok sablonként van szállítva. A Power Apps-portálokon és a kettős íráson alapul.

A [Power Apps-portálok](https://docs.microsoft.com/powerapps/maker/portals/overview) olyan funkció, amely lehetővé teszi, hogy a felhasználók egy kívülről elérhető hozzanak létre, amelybe a szervezeten kívüli személyek be tudnak jelentkezni. A portálok létrehozásához alig vagy nem szükséges kódolás. A Ügyfélportál a Microsoft által elérhető számos [Dynamics 365 portálsablon egyike](https://docs.microsoft.com/powerapps/maker/portals/portal-templates#environment-with-model-driven-apps-in-dynamics-365).

A [kettős írás](https://docs.microsoft.com/powerapps/maker/portals/overview) egy olyan beépített infrastruktúra, amely közel valós idejű interakciót tesz lehetővé a Dynamics 365 modellvezérelt alkalmazásai és a Finance and Operations alkalmazások között. A kettős írás kétirányú integrációt tesz lehetővé a Finance and Operations alkalmazások és a Common Data Service között. Ezért integrált felhasználói élményt nyújt az alkalmazások között. A Ügyfélportál a kettős írással szinkronizált entitásokra épül. Mielőtt az Supply Chain Management alkalmazásból adatok felhasználhatók lennének a vevői portálon, a kettős írást az összes szükséges entitáshoz engedélyezni kell.

![![Ügyfélportál függőségei](media/customer-portal-elements.png "Ügyfélportál függőségei")](media/customer-portal-elements.png "Customer portal dependencies")

A Ügyfélportál kiindulási pontként szolgál olyan szervezeteknek, amelyek a Power Apps portálokat szeretnének használni egy kívülről elérhető webhely kiépítésére, amely a Supply Chain Management telepítés adatait használja. Segíti a szervezeteknek a kettős írás a Supply Chain Management és a Power Apps portálok csatlakoztatásában.
