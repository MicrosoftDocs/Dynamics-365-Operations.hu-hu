---
title: Új vagy módosult elemek a Dynamics 365 Supply Chain Management 10.0.10 szolgáltatásban (2020. május)
description: Ez a témakör olyan funkciókat ír le, amelyek vagy Dynamics 365 Supply Chain Management újak, vagy módosulnak a 10.0.10-ben.
author: kamaybac
ms.date: 04/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-21
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: c377a910cca8bbf1fd640b6c9a99810be1a8d40f
ms.sourcegitcommit: 9e6a9d644a34158390c6e209e80053ccbdb7d974
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/20/2022
ms.locfileid: "9708694"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10010-may-2020"></a>Új vagy módosult elemek a Dynamics 365 Supply Chain Management 10.0.10 szolgáltatásban (2020. május)

[!include [banner](../includes/banner.md)]

Ez a cikk a Microsoft Dynamics 365 Supply Chain Management 10.0.10 új vagy módosított funkcióit sorolja fel. Ennek a verziónak 10.0.420 a buildszáma, és a következő módon érhető el:

- **Előzetes kiadás**: 2020. március
- **Általános elérhetőség (saját frissítés):** 2020. április
- **Automatikus frissítés:** 2020. május

## <a name="features-included-in-this-release"></a>A verzióban található funkciók

Ez a kiadás a következő funkciókat tartalmazza: A funkciók címei további információkra mutatnaka a [Kiadási tervek](/dynamics365/release-plans/) webhelyen. A további hivatkozások az adott funkcióhoz jelenleg elérhető további dokumentációkat és videókat mutatnak be. Ezen szolgáltatások többségét a használat előtt engedélyezni kell a [Funkciók kezelése](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) alatt.

- [A meglévő ténylegessúly-címkék használatának javítása a raktárkezelési modulban](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/enhancement-use-existing-catch-weight-tags-warehouse-management)

- [A Raktárkezelés modul bejövő terheléskezelésének továbbfejlesztései](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/warehouse-management-inbound-load-management-enhancement)<br> - További információ: [Beszerzési rendelések bejövő rakományának kezelése a raktárban](../warehousing/inbound-load-handling.md).

- [Címkenyomtatással kapcsolatos fejlesztések a raktárkezeléshez](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/label-printing-enhancements-warehouse-management)<br> - – A további tudnivalókat lásd [a Dokumentumirányítás címkeelrendezéseinél](../warehousing/document-routing-layout-for-license-plates.md).

- [Az Alaptervezés olyan cikkeket tartalmaz, amelyek aktuális készlettel rendelkeznek, amikor előfeldolgozási szűrők engedélyezve vannak](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/master-planning-include-items-on-hand-when-pre-processing-filters-are-enabled)

- [Új adatentitások a termelési területhez](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/new-data-entities-manufacturing-area)

- [Raktári folyamatok minőségkezelése](/dynamics365-release-plan/2019wave2/dynamics365-supply-chain-management/quality-management-warehouse-processes)<br> - További információ: [Raktári folyamatok minőségkezelése](../inventory/quality-management-for-warehouses-processes.md).

## <a name="additional-resources"></a>További erőforrások

### <a name="platform-updates-for-finance-and-operations-apps"></a>A pénzügyi és az üzemeltetési alkalmazások platformfrissítései

A Dynamics 365 Supply Chain Management 10.0.10 platformfrissítéseket tartalmaz. A további tudnivalókat [lásd a Pénzügyi és műveleti alkalmazások 10.0.10-es verziójának Platformfrissítései](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-34.md).

### <a name="bug-fixes"></a>Hibajavítások

Ha további tájékoztatást szeretne kapni a frissítésben található hibajavításokról, lépjen be a Lifecycle Services (LCS) szolgáltatásokba, és tekintse meg a [Tudásbázis cikket](https://fix.lcs.dynamics.com/Issue/Details?bugId=424137&dbType=3&qc=bf63d49dcc96e51eb42ac1dd66c6c5e5d7548f1e176f729e324ea3353b9860cb).

### <a name="dynamics-365-2020-release-wave-1-plan"></a>Dynamics 365: 2020-es 1. hullám tervei

Kíváncsi a bármelyik üzleti alkalmazásával vagy platformjával kapcsolatos, közelgő és a közelmúltban bevezetett lehetőségekre?

Lásd: [Dynamics 365: 2020-as 1. frissítési hullám tervét](/dynamics365-release-plan/2020wave1/index). A részleteket minden apró információmorzsáig bezárólag egyetlen dokumentumban rögzítettük, amelyet felhasználhat a tervezés során.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Eltávolított és elavult Supply Chain Management szolgáltatások

A [cikk Eltávolított Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) vagy elavult funkciói olyan funkciókat írnak le, amelyek már el vannak távolítva, illetve amelyek már el vannak távolítva vagy elavultak az Ellátásilánc-kezeléshez.

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Mielőtt a funkciót eltávolítanának a termékből, [Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) az értékcsökkenési értesítés 12 hónappal az eltávolítás előtt törlődik az Eltávolított vagy elavult funkciókból.

Olyan módosítások esetén, amelyek csak a fordítási időt érintik, de binárisan kompatibilisek a tesztkörnyezettel és a termelési környezettel, az elavulási idő 12 hónapnál rövidebb lesz. Ezek általában olyan funkcionális frissítések, amelyeket a fordítón kell elvégezni.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
