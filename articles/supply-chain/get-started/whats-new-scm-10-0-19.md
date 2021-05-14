---
title: A Dynamics 365 Supply Chain Management 10.0.19 előzetes verziója (2021. július)
description: Ez a témakör a Dynamics 365 Supply Chain Management 10.0.19 új vagy módosított szolgáltatásait írja le.
author: kamaybac
ms.date: 04/23/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-04-23
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 8bb4a7c8085b40ab3eca72675dbe7a3be412d8c1
ms.sourcegitcommit: 2eb7a9ae544f504155657c5c584cbac66c21dba4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/29/2021
ms.locfileid: "5961681"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10019-july-2021"></a>A Dynamics 365 Supply Chain Management 10.0.19 előzetes verziója (2021. július)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a témakör a Microsoft Dynamics 365 Supply Chain Management 10.0.19 előzetes kiadásának új vagy módosított szolgáltatásait írja le. Ennek a verziónak 10.0.837 a buildszáma, és a következő módon érhető el:

- **Előzetes kiadás**: 2021. április
- **A kiadás általános elérhetővé tétele (saját frissítés):** 2021. június
- **A kiadás általános elérhetővé tétele (automatikus frissítés):** 2021. július

## <a name="features-included-in-this-release"></a>A verzióban található funkciók

Ez a kiadás a következő táblázatban felsorolt funkciókat tartalmazza: A *Funkció* oszlop a [kiadási tervre](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features) mutató hivatkozásokat tartalmaz, amelyeken látható az egyes funkciók hivatalos kiadási dátuma. A *További tudnivalók* oszlopban a kapcsolódó dokumentációra mutató hivatkozások is találhatóak.

Ezen szolgáltatások többségét a használat előtt engedélyezni kell a [Funkciók kezelése](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) alatt. A felsorolt szolgáltatások egy része továbbra is előnézeti módban van, mások azonban már általánosan elérhetők.

| Szolgáltatásterület | Funkció | További információ |
|---|---|---|
| Készlet és logisztika | [Kapcsolattartó személy adatentitás-exportálásának optimalizálása](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization)  | *Nem érhető el.* |
| Készlet és logisztika | [A raktár-végrehajtási képességek növekményes fejlesztése mérlegegységekkel](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/incremental-enhancements-warehouse-execution-capabilities-scale-units) |[Üzenetfeldolgozó üzenetei](../cloud-edge/cloud-edge-message-processor-messages.md)<br><br>[Raktárkészlet helyesbítése](../cloud-edge/cloud-edge-warehouse-inventory-adjustment.md)<br><br>[Raktérkezelés munkaterhelései felhőalapú és peremhálózat-lépték szerinti egységekhez](../cloud-edge/cloud-edge-workload-warehousing.md) |
| Készlet és logisztika | [Keresési funkció az Értékesítési ajánlat lapon a Dokumentumbevezetés és Dokumentum-összefoglalás mezőkhöz](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/lookup-functionality-document-introduction-document-conclusion-fields-sales-quotation-page) | *Nem érhető el.* |
| Készlet és logisztika | [Raktár végrehajtása az egyéni hardveren található peremhálózati skálaegységekkel](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-execution-edge-scale-units-custom-hardware) | [Peremskálaegységek telepítése egyéni hardverre a LBD használatával](../cloud-edge/cloud-edge-edge-scale-units-lbd.md) |
| Gyártás | [Gyártás végrehajtása az egyéni hardveren található peremhálózati skálaegységekkel](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/manufacturing-execution-edge-scale-units-custom-hardware) | [Peremskálaegységek telepítése egyéni hardverre a LBD használatával](../cloud-edge/cloud-edge-edge-scale-units-lbd.md) |
| Tervezés | Lekérdezés alapú tervezett rendelésmegerősítés | [Biztosra tervezett rendelések](../master-planning/planning-optimization/planned-order-firming.md) |
| Termékinformációk kezelése | [Változatjavaslatok oldalának fejlesztései](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/variant-suggestions-page-improvements) | [Az előre meghatározott termékváltozatok létrehozása](../pim/tasks/create-predefined-product-variants.md) |

## <a name="new-and-updated-documentation-resources"></a>Új és frissített dokumentáció-erőforrások

A következő súgótémakörök a közelmúltban lettek hozzáadva vagy jelentősen frissítve. A program nem feltétlenül kapcsolódik ehhez a kiadáshoz hozzáadott új funkcióhoz, amint az az előző részben szerepel, de segítséget jelenthet a meglévő szolgáltatások kiválasztásában.

| Szolgáltatásterület | Új vagy frissített témakörök |
|---|---|
| Tervezési változáskezelés | [Tervezési változáskezelés GYIK](../engineering-change-management/change-management-faq.md) |
| Beszerzés és forrás | [Szállítók kategóriakérései](../procurement/category-requests-from-vendors.md) |
| Termékinformációk kezelése | [Mértékegység kezelése](../pim/tasks/manage-unit-measure.md)<br><br>[Termékkonfigurációs modell számításai](../pim/config-model-calculations.md) |
| Gyártásvezérlés | [Egyesített számsorozat a feladatazonosítók esetén](../production-control/unified-job-ids.md) |
| Szállításkezelés | [LTL osztályok](../transportation/ltl-class.md)<br><br>[NMFC-kódok](../transportation/nmfc-codes.md) |
| Raktárkezelés | [Raktári kötegelt és sorozatfoglalási hierarchiák hibaelhárítása](../warehousing/troubleshoot-warehouse-batch-and-serial-reservation-hierarchies.md) |
| Raktárkezelés, hullám létrehozása és feldolgozása | [Hullám létrehozása és feldolgozása](../warehousing/wave-processing.md)<br><br>[Raktári paraméterek hullámfeldolgozáshoz](../warehousing/wave-warehouse-parameters.md)<br><br>[Hullámsablonok](../warehousing/wave-templates.md)<br><br>[Hullámfelosztás](../warehousing/wave-allocation-method.md)<br><br>[Munka létrehozásának ütemezése a hullám során](../warehousing/configure-wave-schedule-work-creation.md)<br><br>[Tárolóra bontás](../warehousing/wave-containerization.md)<br><br>[Hullámvégrehajtási értesítések](../warehousing/wave-execution-notifications.md) |

## <a name="additional-resources"></a>További erőforrások

### <a name="platform-updates-for-finance-and-operations-apps"></a>A Finance and Operations-alkalmazások platformfrissítései

A Microsoft Dynamics 365 Supply Chain Management 10.0.19 platformfrissítéseket tartalmaz. További tájékoztatás: [Platform-frissítések az Finance and Operations alkalmazások 10.0.19 verziójához (2021. július)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-19.md).

### <a name="bug-fixes"></a>Hibajavítások

Ha további tájékoztatást szeretne kapni a 10.0.19 részét képező frissítésekben található hibajavításokról, lépjen be a Lifecycle Services (LCS) szolgáltatásokba, és tekintse meg a [Tudásbázis cikket](https://fix.lcs.dynamics.com/Issue/Details?bugId=575415).

### <a name="dynamics-365-2021-release-wave-1-plan"></a>Dynamics 365: 2021-es 1. hullám tervei

Kíváncsi a bármelyik üzleti alkalmazásával vagy platformjával kapcsolatos, közelgő és a közelmúltban bevezetett lehetőségekre?

Lásd: [Dynamics 365: 2021-as 1. frissítési hullám tervét](/dynamics365-release-plan/2021wave1/). A részleteket minden apró információmorzsáig bezárólag egyetlen dokumentumban rögzítettük, amelyet felhasználhat a tervezés során.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Eltávolított és elavult Supply Chain Management szolgáltatások

A [Dynamics 365 Supply Chain Management eltávolított vagy elavult szolgáltatásai](removed-deprecated-features-scm-updates.md) témakör azokat a funkciókat írja le, amelyek el lettek távolítva a Supply Chain Management szolgáltatásól vagy eltávolításuk ütemezve van.

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Mielőtt a termékből eltávolítunk egy szolgáltatást, egy eltávolítással kapcsolatos értesítést teszünk közzé a [Dynamics 365 Supply Chain Management eltávolított vagy elavult funkciói](removed-deprecated-features-scm-updates.md) témakörben 12 hónappal az eltávolítás előtt.

Olyan módosítások esetén, amelyek csak a fordítási időt érintik, de binárisan kompatibilisek a tesztkörnyezettel és a termelési környezettel, az elavulási idő 12 hónapnál rövidebb lesz. Ezek általában olyan funkcionális frissítések, amelyeket a fordítón kell elvégezni.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
