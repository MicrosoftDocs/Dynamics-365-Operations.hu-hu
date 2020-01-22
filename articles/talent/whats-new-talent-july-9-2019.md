---
title: A Dynamics 365 Talent új vagy módosult elemei (2019. július 9.)
description: Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 07/09/2019
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
ms.search.validFrom: 2019-07-09
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 99a7e6130d45229011a185087d4872fe34b8224a
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897626"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-july-9-2019"></a>A Dynamics 365 Talent új vagy módosult elemei (2019. július 9.)

Ez a témakör a Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben

A kiadás a Dynamics 365 Talent: Attract apró hibáinak javításait is tartalmazza.

### <a name="coming-soon-in-attract"></a>Hamarosan az Attract alkalmazásban

#### <a name="job-approvals-appear-on-the-home-page"></a>A feladatok jóváhagyása megjelenik a kezdőképernyőn

A jóváhagyások az irányítópult **Jóváhagyások** szakaszában jelennek meg. A jóváhagyók megtekinthetik a rájuk váró jóváhagyásokat az **Önhöz rendelt** részen, ahol látható a feladat azonosítója és neve, a többi jóváhagyó és a feladat hozzárendelésének dátuma. Azok a felhasználók, akik elküldenek jóváhagyásra egy feladatot, az **Ön által küldött kérések** szakaszban látják a feladatot, ahol megjelennek azok a jóváhagyók, akiknek még jóvá kell hagyniuk a feladatot.

## <a name="changes-in-onboard"></a>Változások az Onboard alkalmazásban

A kiadás a Dynamics 365 Talent: Onboard apró hibáinak javításait is tartalmazza.

## <a name="changes-in-core-hr"></a>A Core HR módosításai

A szakaszban ismertetett módosítások a 8.1.2374-ös buildre vonatkoznak.

### <a name="platform-update-28-for-finance-and-operations"></a>Platform update 28 a Finance and Operations szolgáltatáshoz

További információ a Finance and Operations 28-es platformfrissítésről (Platform update 28): [Előzetes funkciók a Dynamics 365 Finance and Operations platform update 28-es verziójában (2019. július)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-28).

### <a name="entity-support-for-custom-fields-in-common-data-service"></a>Common Data Service – entitástámogatás egyéni mezőkhöz 

A következő entitások támogatják az egyéni mezőket: 

- **Fix kompenzációs konstrukció**
- **Kompenzációs hivatkozási pont beállítása**
- **Kompenzációs hivatkozási pontok beállítási sora**
- **Bérlista bevételkódja**
- **Fizetési időszak**
- **Rögzített kompenzációs esemény**
- **Kompenzációs rács**

A Talent összes frissített entitásának megtekintése:

1. Válassza ki a **Rendszer-adminisztráció** lehetőséet, a **Hivatkozások** pontot, majd a **Common Data Service-konfiguráció** pontot.
2. Válassza ki **a CDS-entitás neve** legördülő menüt. Minden felsorolt entitás a legutóbbi verzióban szerepel. 

###  <a name="full-name-added-to-worker-entity-in-common-data-service"></a>Teljes név hozzáadva a Dolgozó entitáshoz a Common Data Service szolgáltatásban

A **Teljes név** mező hozzáadva a **Dolgozó** entitáshoz.

### <a name="full-time-equivalent-higher-than-10"></a>Teljes munkaidős egyenérték magasabb, mint 1,0.

Egy figyelmeztető üzenet jelenik meg, ha a beosztásnál egy teljes munkaidős alkalmazottnál 1,0-nál nagyobb érték van megadva. 

### <a name="a-warning-no-longer-displays-on-the-worker-page-when-there-is-no-future-dated-employment"></a>Már nem jelenik meg figyelmeztetés a Dolgozó oldalon olyankor, amikor nincs jövőbeli dátummal ellátott foglalkoztatás

A továbbiakban nem jelenik meg üzenet, amely azt jelzi, hogy egy jövőbeli foglalkoztatás létezik olyankor, amikor a **Dolgozó** oldalra lép a **Kilépő alkalmazottak** listából a **Személyzetkezelés** munkaterületen. 

### <a name="unable-to-delete-a-business-process-in-talent"></a>Nem sikerül törölni egy üzleti folyamatot a Talent modulban.

Az üzleti folyamatok mostantól az **Üzleti folyamat** munkaterületen törölhetők.

### <a name="leave-balance-no-longer-displays-zero-for-plans-with-no-accruals-when-using-balance-as-of-accrual-period"></a>A szabadságegyenleg a továbbiakban már nem nullát jelenít meg könyvelés nélkül olyankor, amikor az Egyenleget használja könyvelési időszakként.

A könyvelés nélküli tranzakciókat tartalmazó tervek mostantól egyenleget jeleníthetnek meg.

## <a name="in-preview"></a>Előnézetben

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Az előnézeti szolgáltatások csak a védőfalpéldányokban engedélyezettek

Amikor új Talent-példányt hoz létre, megadhatja, hogy a példány **Termelési** vagy **Védőfal** típusú legyen-e. A **Védőfal** típusú példányokkal az új szolgáltatások korai tesztelése végezhető el. Minden létező Talent példányt a **Termelési** példány típusára lesz frissítve. Ha a meglévő példányokat **Védőfal** típusúra szeretné frissíteni, kérje az [ügyfélszolgálat](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) segítségét.

További információ a módosítások közzétételéről: [A Talent létesítése](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="restrict-leave-types-in-time-off-requests"></a>A szabadság típusának korlátozása a távolléti kérelmekben

A szervezetek számos különböző típusú szabadságot tudnak nyújtani az alkalmazottak számára. Előfordulhat azonban, hogy egyes szabadságtípusok esetében nem megfelelő megoldás, hogy az alkalmazottak küldjenek be távolléti kérelmet. Lehetséges, hogy ezeket a szabadságtípusokat a HR kezeli. Ebben a kiadásban konfigurálhatja, hogy az alkalmazottak milyen szabadságtípusokhoz küldhetnek távolléti kérelmet. 

## <a name="coming-soon-in-core-hr"></a>Hamarosan bevezetjük a Core HR-ban

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Részletes teljesítményadatok megtekintése az önkiszolgáló kezelői rendszerben

Egy új beállítással a vezetők mind a közvetlen beosztottak, mind a közvetett beosztottak teljesítményét megtekinthetik. Jelenleg a közvetlen felettesek hozzárendelhetnek teljesítménycélokat és frissíthetik őket, illetve olyan új értékeléseket adhatnak ki, amelyeket az alkalmazottaik is tudnak kezelni. Ezenkívül a közvetlen felettesek és alkalmazottaik karbantarthatják és frissíthetik a teljesítménymutatókat, így megbizonyosodhatnak róla, hogy a teljesítmény ellenőrzési folyamata gördülékenyen megy majd. A módosítás végrehajtásakor a vezetők a közvetlen beosztottakon kívül a bővített jelentések teljesítménnyel kapcsolatos adatait is megtekinthetik és karbantartják. 

### <a name="entities-supporting-custom-fields"></a>Entitástámogatás egyéni mezőkhöz

A következő entitások lesznek engedélyezve az egyéni mezőknél a Common Data Service szolgáltatásban: 

- **Szabadság típusa**
- **Dolgozói bankszámla**
- **Munkanaptár**
