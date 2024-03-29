---
title: Vevői portál áttekintéshez Dynamics 365 Supply Chain Management (videofelvételt tartalmaz)
description: Ez a cikk bemutatja az ügyfélportált, és bemutatja, hogy kinek kell használni, és hogyan kell használni.
author: Henrikan
ms.date: 06/16/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 7f34acd78966cc9f26242653e9d0d16fdf22e0b2
ms.sourcegitcommit: 12b3dbee905f8b2eb2e6c383c822a0fc9fccf063
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2022
ms.locfileid: "9103830"
---
# <a name="customer-portal-for-dynamics-365-supply-chain-management-overview"></a>A Dynamics 365 Supply Chain Management Ügyfélportáljának áttekintése

[!include [banner](../includes/banner.md)]


## <a name="what-is-the-customer-portal"></a>Mi is az Ügyfélportál?

A korszerű ellátásilánc-rendszerek az integrációra támaszkodhatnak. Megkövetelik, hogy a készlet, a vevői igény és az értékesítési osztályok integrálva legyenek ahelyett, hogy különállnának. A Ügyfélportál segíti a Microsoft Dynamics 365 Supply Chain Management alkalmazást futtató szervezeteket, hogy fokozzák ezt az integrációt, és hatékonyabban tájékoztassák a vevőiket.

Az Ügyfélportál egy olyan [Power Apps-portálok](/powerapps/maker/portals/overview) sablon amelyekben a vállalatok egy kívülről elérhető üzleti (B2B) webhelyet hoznak létre az értékesítési rendelés feldolgozásával kapcsolatos esetekhez. A sablon a [kettős írás](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md), Supply Chain Management és Power Apps-portálokkal teszi lehetővé a külső vállalati felhasználók számára, hogy adatokat hozzanak létre a vállalat Dynamics 365 környezetéből.

A Ügyfélportál-sablon minden olyan testreszabási funkcióval rendelkezik, amely a Power Apps portálok funkciója kínál. A sablon egyszerűen módosítható a vállalat márkájának megjelenítésére, a kibővített funkciók hozzáadásához, valamint a felhasználói élmény módosításához. A sablon által a gyári állapotban kínált összes funkció tetszés szerint módosítható.

> [!IMPORTANT]
> A sablon önmagában várhatóan nem teljesen működőképes. Ez csak egy segédtermék olyan felhasználók számára akik külső webhelyeket kívánnak létrehozni annak érdekében, hogy a vállalati vevők a Supply Chain Management alkalmazásból származó adatokkal léphessennek interakcióba.

> [!NOTE]
> Az Ügyfélportál dokumentációját az adminisztrátorok, a testreszabók és a rendszerintegrátorok irányítják, akik a Supply Chain Management telepítése során beállítja a Ügyfélportált. Az _ügyfél_ és a _felhasználó_ kifejezésekkel írja le azokat a személyeket, akik a Supply Chain Management alkalmazást futtató szervezethez ügyfelei, illetve azokat, akik a végső portált használni fogják.

## <a name="video"></a>Videó

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4ylwW]

A [vevői portál Dynamics 365 Supply Chain Management](https://youtu.be/nPrqoLuHfV8) sablonjának áttekintése videofelvételen (fent látható) [a pénzügyi és műveletek elérhetővé](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) tevében YouTube.

## <a name="who-should-use-it"></a>Kinek érdemes használnia?

Az Ügyfélportál a Supply Chain Management alkalmazást futtató vállalatok számára készült, akik ezekkel a jellemzőkkel rendelkeznek:

- Egy kívülről elérhető webhelyet akarnak létrehozni, amely a rendelés feldolgozási adatait (például a rendelési állapotot vagy a partneradatokat) közvetlenül a Supply Chain Management rendszerükből a vállalati vevőknek kommunikálja.
- Átállnak a Dynamics AX 2012 alkalmazásról a Supply Chain Management megoldásra, és korábban [AX 2012 vevői önkiszolgáló portált](/dynamicsax-2012/appuser-itpro/about-the-customer-self-service-portal) használták.

A következő típusú szervezetek **nem** jó jelöltek a Ügyfélportál kiépítéséhez:

- Azok a vállalatok, amelyek nem vállalati vevők számára kívánnak webhelyeket létrehozni. Ezeknek a vállalatoknak érdemes fontolóra venni egy [Dynamics 365 Commerce e-kereskedelmi webhely](../../commerce/create-ecommerce-site.md) létrehozását.
- Azok a vállalatok, amelyek már létező Power Apps portálok webhelyet alkalmaznak hasonló célra. Ezek a vállalatok nem kapnak további előnyöket az Ügyfélportáltól. Az Ügyfélportál egy sablon, amely útmutatóként működik, és kiindulópontként szolgál azoknak a vevőknek, akik kapcsolatot szeretnének létesíteni a kettős írás, a Supply Chain Management és a Power Apps-portálok között. Ha már van olyan webhelye, amely ezt a célt szolgálja, akkor lehet, hogy nem sok értéket jelentene az Ügyfélportál használata egy a webhely ismételt kiépítéséhez.

## <a name="how-does-it-work"></a>Hogyan működik?

Az Ügyfélportál Power Apps-portálok sablonként van szállítva. A Power Apps-portálokon és a kettős íráson alapul.

A [Power Apps-portálok](/powerapps/maker/portals/overview) olyan funkció, amely lehetővé teszi, hogy a felhasználók egy kívülről elérhető hozzanak létre, amelybe a szervezeten kívüli személyek be tudnak jelentkezni. A portálok létrehozásához alig vagy nem szükséges kódolás. A Ügyfélportál a Microsoft által elérhető számos [Dynamics 365 portálsablon egyike](/powerapps/maker/portals/portal-templates#environment-with-model-driven-apps-in-dynamics-365).

[A kettős](/powerapps/maker/portals/overview) írás egy olyan infrastruktúra-termék, amely szinte valós idejű kommunikációt biztosít az ügyfél-megállapodási alkalmazások, illetve a pénzügyi és műveleti alkalmazások között. A kettős írás kétirányú integrációt biztosít a pénzügyek és a műveletalkalmazások, valamint a Microsoft Dataverse. Ezért integrált felhasználói élményt nyújt az alkalmazások között. A Ügyfélportál a kettős írással szinkronizált táblákra épül. Mielőtt az Supply Chain Management alkalmazásból adatok felhasználhatók lennének a vevői portálon, a kettős írást az összes szükséges táblához engedélyezni kell.

![Ügyfélportál függőségei.](media/customer-portal-elements.png "Ügyfélportál függőségei")

A Ügyfélportál kiindulási pontként szolgál olyan szervezeteknek, amelyek a Power Apps portálokat szeretnének használni egy kívülről elérhető webhely kiépítésére, amely a Supply Chain Management telepítés adatait használja. Segíti a szervezeteknek a kettős írás a Supply Chain Management és a Power Apps portálok csatlakoztatásában.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
