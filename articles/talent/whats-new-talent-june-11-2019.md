---
title: A Dynamics 365 Talent új és módosult elemei (2019. június 11.)
description: Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 06/11/2019
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
ms.search.validFrom: 2019-06-11
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 20dc0768463d9a5d6762cb062deb0bdbe4d53fe3
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528669"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-june-11-2019"></a>A Dynamics 365 Talent új és módosult elemei (2019. június 11.)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben

### <a name="search-engine-optimization-for-job-posts"></a>Keresőmotor-optimalizálás az álláshirdetésekhez

Ha bekapcsolja a **Keresőmotor-optimalizálást** a Dynamics 365 Talent: Attract felügyeleti központjában, az Attract felkéri a Google Indexing alkalmazásprogramozási felületét (API), hogy térképezze fel a weboldalt, amikor Ön új feladatot tesz közzé vagy aktivál, illetve meglévő feladatot frissít. Ilyen módon a feladat megjelenik a Google és más keresőmotorok keresési eredményei között.

Hasonlóképpen, ha eltávolít egy feladatot, az Attract jelzi az Indexing API-nak, hogy az eltávolított feladat a későbbiekben ne jelenjen meg a keresési eredmények között.

> [!NOTE]
> Az internetes térképezőrobotok nem csak egy megadott időszakban térképezik fel a weblapokat vagy frissítik a keresési eredményeket.

## <a name="coming-soon-in-attract"></a>Hamarosan az Attract alkalmazásban

### <a name="job-approvals-appear-on-the-home-page"></a>A feladatok jóváhagyása megjelenik a kezdőképernyőn

A jóváhagyások az irányítópult **Jóváhagyások** szakaszában jelennek meg. A jóváhagyók megtekinthetik a rájuk váró jóváhagyásokat az **Önhöz rendelt** részen, ahol látható a feladat azonosítója és neve, a többi jóváhagyó és a feladat hozzárendelésének dátuma. Azok a felhasználók, akik elküldenek jóváhagyásra egy feladatot, az **Ön által küldött kérések** szakaszban látják a feladatot, ahol megjelennek azok a jóváhagyók, akiknek még jóvá kell hagyniuk a feladatot.

## <a name="changes-in-onboard"></a>Változások az Onboard alkalmazásban

A kiadás a Dynamics 365 Talent: Onboard apró hibáinak javításait is tartalmazza.

## <a name="changes-in-core-hr"></a>A Core HR módosításai

A szakaszban ismertetett módosítások a 8.1.2337-ös buildre vonatkoznak.

### <a name="platform-update-27-for-finance-and-operations"></a>A Finance and Operations 27-es platformfrissítése

További információ a Finance and Operations 27-es platformfrissítésről (Platform update 27): [Előzetes funkciók a Dynamics 365 Finance and Operations platform update 27 verziójában (2019. június)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-27).

### <a name="feature-management-workspace-in-talent"></a>A funkciókezelési munkaterület a Talentben

A **Rendszerfelügyelet** **Funkció kezelése** munkaterületén megtekintheti, engedélyezheti, letilthatja és ütemezheti az egyes kiadások funkcióit. Alapértelmezés szerint az új szolgáltatások ki vannak kapcsolva. A **Funkció kezelése** munkaterületen bekapcsolhatja a szolgáltatásokat, és megtekintheti a rájuk vonatkozó dokumentációt.

### <a name="common-data-service-entity-support-for-custom-fields"></a>Common Data Service entitás-támogatás egyéni mezőkhöz

A Kiállító szervezet entitás már támogatja az egyéni mezőket.

### <a name="new-common-data-service-entities"></a>Új Common Data Service-entitások

Hozzáadtuk a feladatcsoport entitást.

## <a name="in-preview"></a>Előnézetben

### <a name="preview-features-will-be-enabled-only-in-sandbox-environments"></a>Az előnézeti szolgáltatások csak a Védőfal környezetekben használhatók.

További információ a módosítások közzétételéről: [A Talent létesítése](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

Amikor új Talent-példányt hoz létre, jelezheti, hogy a példány Termelési vagy Védőfal típusú legyen-e. A Védőfal típusú példányokkal az új szolgáltatások korai tesztelése végezhető el. Minden létező Talent példányt a **Termelési** példány típusára lesz frissítve. Ha a meglévő példányokat **Védőfal** típusúra szeretné frissíteni, kérje az [ügyfélszolgálat](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) segítségét.

### <a name="restrict-the-leave-types-in-time-off-requests"></a>A szabadság típusának korlátozása a távolléti kérelmekben

A szervezetek számos különböző típusú szabadságot tudnak nyújtani az alkalmazottak számára. Előfordulhat azonban, hogy egyes szabadságtípusok esetében nem megfelelő megoldás, hogy az alkalmazottak küldjenek be távolléti kérelmet. Lehetséges, hogy ezeket a szabadságtípusokat az emberi erőforrások részlege (HR) kezeli. Ebben a kiadásban konfigurálhatja, hogy az alkalmazottak milyen szabadságtípusokhoz küldhetnek távolléti kérelmet. 

## <a name="coming-soon-in-core-hr"></a>Hamarosan bevezetjük a Core HR-ban

### <a name="view-extended-information-about-report-performance-in-manager-self-service"></a>A jelentések részletes teljesítményadatainak megtekintése az önkiszolgáló kezelői rendszerben

Egy új beállítással a vezetők mind a közvetlen beosztottak, mind a közvetett beosztottak teljesítményét megtekinthetik. Jelenleg a közvetlen felettesek hozzárendelhetnek teljesítménycélokat és frissíthetik őket, illetve olyan új értékeléseket adhatnak ki. Ezenkívül a közvetlen felettesek és alkalmazottaik karbantarthatják és frissíthetik a teljesítménymutatókat, így garantálható, hogy a teljesítmény ellenőrzési folyamata gördülékenyen megy majd. A módosítás végrehajtásakor a vezetők a közvetlen beosztottakon kívül a bővített jelentések teljesítménnyel kapcsolatos adatait is megtekinthetik és karbantartják.

### <a name="print-performance-reviews"></a>Teljesítményértékelések nyomtatása

Az alkalmazottak, a vezetők és a HR alkalmazottai kinyomtathatják az alkalmazottak teljesítménykimutatását.
