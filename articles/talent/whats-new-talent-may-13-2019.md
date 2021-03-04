---
title: Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. május 13.)
description: Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 05/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-05-13
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 11c9f03f4b3915d81b624115a1d97a0c7bc31709
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529732"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-may-13-2019"></a>Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. május 13.)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a témakör a Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.

## <a name="coming-soon-in-attract"></a>Hamarosan az Attract alkalmazásban

### <a name="job-approvals-on-home-page"></a>Feladatok jóváhagyása a kezdőképernyőn

A jóváhagyások az irányítópult **Jóváhagyások** szakaszában jelennek meg. A jóváhagyók megtekinthetik a rájuk váró jóváhagyásokat az **Önhöz rendelt** szakaszban, amely megjeleníti a feladat azonosítóját, nevét, egyéb jóváhagyóit és a hozzárendelés dátumát. Azoknak a felhasználóknak, akik a jóváhagyásra elküldenek egy feladatot, megtekinthetik az **Ön által küldött kérések** szakaszban, ahol azokat a jóváhagyókat jelenítik meg, akiknek továbbra is jóvá kell hagynia a feladatot.

## <a name="changes-in-onboard"></a>Változások az Onboard alkalmazásban

A kiadás a Dynamics 365 Talent: Onboard apró hibáinak javításait is tartalmazza.

## <a name="changes-in-core-hr"></a>A Core HR módosításai

A szakaszban ismertetett módosítások a 8.1.2297-ös buildre vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok az Microsoft Dynamics Lifecycle Services (LCS) támogatási számaira vonatkoznak.

### <a name="indicate-instance-type-when-provisioning-talent"></a>Példány típusának jelzése a Talent kiépítése alkalmával

Ha egy új Talent példányt telepít akkor jelezheti, hogy a példány típusa **Termelési** vagy **Védőfal** típusú, és lehetővé teszi az új szolgáltatások korai tesztelését. Minden létező Talent példányt a **Termelési** példány típusára lesz frissítve. Ha azt szeretné, hogy a meglévő példányok frissítve legyenek a **Védőfal** példányra, forduljon a [Támogatáshoz](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) a módosítási kérelem kezdeményezéséhez.

### <a name="common-data-service-entity-support-for-custom-fields"></a>Common Data Service entitás-támogatás egyéni mezőkhöz

Az e heti kiadásban a következő Common Data Service-entitások már támogatják az egyéni mezőket: Foglalkoztatás, Juttatási számítás gyakorisága, Juttatási számítási mértéke, Munkanaptár ünnepei, és Azonosítótípus.

### <a name="common-data-service-integration-page"></a>Common Data Service-integráció oldala

Ez a kiadás új beállítást nyújt a **Rendszerfelügyelet > Hivatkozások > Integrációk > Common Data Service-konfiguráció** pontban. A **Common Data Service-konfiguráció** beállítással a rendszergazda vagy az adatkezelési rendszergazda némi rugalmassággal és betekintéstsel rendelkezik a Common Data Service szolgáltatásba. Ezzel a beállítással engedélyezheti vagy letilthatja Common Data Service-integrációt egy Talent-példánnyal, és megtekintheti a Talent példány és a Common Data Service közötti szinkronizálási részleteit.

### <a name="import-performance-data-with-final-employee-rating-316710"></a>Teljesítményadatok importálása végleges alkalmazotti minősítéssel (316710)

Ebben a kiadásban importálhatja a múltbeli alkalmazottak minősítési adatait. A **FinalEmployeeRatingId** mezőnek most írási engedélye van.

### <a name="cant-create-worker-address-in-common-data-service-and-sync-it-with-talent-317555"></a>Nem hozható létre a Common Data Service szolgáltatásban a dolgozó címe, és nem lehet szinkronizálni a Talent alkalmazással (317555)

Ez a módosítás lehetővé teszi a Common Data Service szolgáltatásban létrehozott címadat szinkronizálását a Talent alkalmazással.

## <a name="in-preview"></a>Előnézetben

### <a name="new-page-to-validate-position-hierarchy-data"></a>Új oldal a beosztás-hierarchia adatainak ellenőrzéséhez

A személyzeti osztály munkatársai (HR) és a rendszergazdák most ellenőrizni tudják a vezetői hierarchiát a véletlenül importált körkörös hivatkozások tekintetében. Ezt az új lapot a **Szervezeti adminisztráció > Hivatkozások > Beosztások > Beosztáshierarchia ellenőrzése** helyről érheti el.

### <a name="specify-reason-codes-on-leave-types"></a>Okkódok meghatározása a távollét típusaihoz

A szervezeteknek kiegészítő információkra lehet szüksége a szabadságkérelmekkel kapcsolatban. Immár megadhat okkódokat egy adott távolléttípushoz, és megengedheti az alkalmazottak számára okkód választását szabadságkérelmükhöz.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Okkódok kérése adott szabadságtípusokhoz a távollétkérelmek során

Előfordulhat, hogy a szervezetek okkódok beállítását kérik, bizonyos távolléttípusokhoz, amikor a munkavállalók távolléti kérelmeket nyújtanak be. Ez a követelmény a vállalat szabályzata vagy a törvényi követelmények miatt állhat fenn. Meghatározhatja, mely szabadságtípusokhoz szükséges okkód, és alkalmazottaktól megkövetelheti okkód megadását a szabadságtípushoz a távollétkérelmekhez.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Egy szabadság és a távolléti tranzakciólista átadása a HR-nek

Az alkalmazotti szabadidő követésének képessége és a szabadidő kiszámításának ismerete azon túl. hogy segít a HR-nek alkalmazott kérdések megválaszolásában, pontos szabadságmegítéléseket biztosít a munkavállalóknak. A HR új betekintést kap a tranzakciókhoz (támogatások, könyvelések, kiigazítások és kérelmek) így a HR munkatársai láthatják a távollétegyenlegek okait.


[!INCLUDE[footer-include](../includes/footer-banner.md)]