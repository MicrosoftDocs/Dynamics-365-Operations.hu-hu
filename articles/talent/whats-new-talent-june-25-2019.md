---
title: A Dynamics 365 for Talent új és módosult elemei (2019. június 25.)
description: Ez a témakör a Microsoft Dynamics 365 for Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 06/25/2019
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
ms.search.validFrom: 2019-06-25
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 3c7a13373193a6af4033b4609f0c338c2c6128c6
ms.sourcegitcommit: 1bf6a8b2f872394a4f242f9ff13c67e8e1ae8f65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/03/2019
ms.locfileid: "1856353"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-june-25-2019"></a>A Dynamics 365 for Talent új és módosult elemei (2019. június 25.)

[!include [banner](includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 for Talent új vagy módosított szolgáltatásait írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben

Ebben a verzióban kisebb hibajavítások találhatók a Dynamics 365 Talent: Attract alkalmazáshoz.

## <a name="coming-soon-in-attract"></a>Hamarosan az Attract alkalmazásban

### <a name="job-approvals-appear-on-the-home-page"></a>A feladatok jóváhagyása megjelenik a kezdőképernyőn

A jóváhagyások az irányítópult **Jóváhagyások** szakaszában jelennek meg. A jóváhagyók megtekinthetik a rájuk váró jóváhagyásokat az **Önhöz rendelt** részen, ahol látható a feladat azonosítója és neve, a többi jóváhagyó és a feladat hozzárendelésének dátuma. Azok a felhasználók, akik elküldenek jóváhagyásra egy feladatot, az **Ön által küldött kérések** szakaszban látják a feladatot, ahol megjelennek azok a jóváhagyók, akiknek még jóvá kell hagyniuk a feladatot.

## <a name="changes-in-onboard"></a>Változások az Onboard alkalmazásban
Ebben a verzióban kisebb hibajavítások találhatók a Dynamics 365 Talent: Onboard alkalmazáshoz.

## <a name="changes-in-core-hr"></a>A Core HR módosításai

A szakaszban ismertetett módosítások a 8.1.2357-ös buildre vonatkoznak.

### <a name="incorrect-value-displayed-for-primary-position-314266"></a>Helytelen érték jelent meg az elsődleges pozícióhoz (314266)

Ezek a változtatások egységesen, az összes oldal **Elsődleges pozíció** beállítását érintik.

### <a name="cant-edit-after-recalling-the-workflow-in-review-318180"></a>Nem lehetséges a szerkesztés az ellenőrzés alatt lévő munkafolyamat visszahívása után (318180)

A munkafolyamaton keresztül visszahívott érékelések már szerkeszthetők.

### <a name="final-comments-field-in-reviews-isnt-translated-325921"></a>A vélemények között megadott végleges megjegyzések mezője nincs lefordítva (325921)

A Talent **Végleges megjegyzések** címkéjét lefordítottuk.

### <a name="preview-features-will-be-enabled-only-in-sandbox-environments"></a>Az előnézeti szolgáltatások csak a Védőfal környezetekben használhatók.

Amikor új Talent-példányt hoz létre, jelezheti, hogy a példány **Termelési** vagy **Védőfal** típusú legyen-e. A **Védőfal** típusú példányokkal az új szolgáltatások korai tesztelése végezhető el. Minden létező Talent példányt a **Termelési** példány típusára lesz frissítve. Ha a meglévő példányokat **Védőfal** típusúra szeretné frissíteni, kérje az [ügyfélszolgálat](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) segítségét.

További információ a módosítások közzétételéről: [A Talent létesítése](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

## <a name="in-preview"></a>Előnézetben

### <a name="restrict-the-leave-types-in-time-off-requests"></a>A szabadság típusának korlátozása a távolléti kérelmekben

A szervezetek számos különböző típusú szabadságot tudnak nyújtani az alkalmazottak számára. Előfordulhat azonban, hogy egyes szabadságtípusok esetében nem megfelelő megoldás, hogy az alkalmazottak küldjenek be távolléti kérelmet. Lehetséges, hogy ezeket a szabadságtípusokat az emberi erőforrások részlege (HR) kezeli. Ebben a kiadásban konfigurálhatja, hogy az alkalmazottak milyen szabadságtípusokhoz küldhetnek távolléti kérelmet. 

## <a name="coming-soon-in-core-hr"></a>Hamarosan bevezetjük a Core HR-ban

### <a name="feature-management-area-in-talent"></a>Funkciókezelési terület a Talentben

A **Funkció kezelése** funkcióval problémák voltak, ezért eltávolítjuk a **Rendszerfelügyelet** részről. Egy jövőbeli kiadásban vezetjük majd újból be a **Funkció kezelése** szolgáltatást. 

### <a name="common-data-service-entity-support-for-custom-fields"></a>Common Data Service entitás-támogatás egyéni mezőkhöz

A következő entitások támogatják majd az egyéni mezőket **Bérlista bevételkódjai**, **Fix kompenzációs esemény**, **Kompenzációs rács**, **Fizetési időszak** és **Kompenzációs hivatkozási pont**. 

### <a name="new-common-data-service-entities"></a>Új Common Data Service-entitások

A Common Data Service szolgáltatásba felvettük az **Okkódok** entitást.

### <a name="view-performance-information-for-direct-and-extended-reports-in-manager-self-service"></a>A közvetlen és bővített jelentések teljesítményadatainak megtekintése az önkiszolgáló kezelői rendszerben

Egy új beállítással a vezetők mind a közvetlen beosztottak, mind a közvetett beosztottak teljesítményét megtekinthetik. Jelenleg a közvetlen felettesek hozzárendelhetnek teljesítménycélokat és frissíthetik őket, illetve olyan új értékeléseket adhatnak ki. Ezenkívül a közvetlen felettesek és alkalmazottaik karbantarthatják és frissíthetik a teljesítménymutatókat, így megbizonyosodhatnak róla, hogy a teljesítmény ellenőrzési folyamata gördülékenyen megy majd. A módosítás végrehajtásakor a vezetők a közvetlen beosztottakon kívül a bővített jelentések teljesítménnyel kapcsolatos adatait is megtekinthetik és karbantartják.

### <a name="print-performance-reviews"></a>Teljesítményértékelések nyomtatása

Az alkalmazottak, a vezetők és a HR alkalmazottai kinyomtathatják az alkalmazottak teljesítménykimutatását.
