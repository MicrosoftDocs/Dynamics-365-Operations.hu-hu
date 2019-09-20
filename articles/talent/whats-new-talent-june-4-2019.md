---
title: A Dynamics 365 for Talent új és módosult elemei (2019. június 4.)
description: Ez a témakör a Microsoft Dynamics 365 for Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 06/04/2019
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
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e19e5d3f1cb2305e5a4153de3e4d0e8f4c7d31ac
ms.sourcegitcommit: 1bf6a8b2f872394a4f242f9ff13c67e8e1ae8f65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/03/2019
ms.locfileid: "1856329"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-june-4-2019"></a>A Dynamics 365 for Talent új és módosult elemei (2019. június 4.)

[!include [banner](includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 for Talent új vagy módosított szolgáltatásait írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben

Ebben a verzióban kisebb hibajavítások találhatók a Dynamics 365 for Talent: Attract alkalmazáshoz.

## <a name="coming-soon-in-attract"></a>Hamarosan az Attract alkalmazásban

### <a name="job-approvals-on-the-home-page"></a>Feladatok jóváhagyása a kezdőképernyőn

A jóváhagyások az irányítópult **Jóváhagyások** szakaszában jelennek meg. A jóváhagyók az **Önhöz rendelve** részen tekinthetik meg a saját jóváhagyásaikat. Ez a szakasz a feladat azonosítóját, nevét, a többi jóváhagyót, valamint a feladat hozzárendelésének dátumát jeleníti meg. Azok a felhasználóknak, akik jóváhagyásra küldenek be egy feladatot, az **Ön által küldött kérések** részen tekinthetik meg a feladatot. Ebben a szakaszban azok a jóváhagyók szerepelnek, akiknek még jóvá kell hagyniuk a beküldött feladatot.

## <a name="changes-in-onboard"></a>Változások az Onboard alkalmazásban

Ebben a verzióban kisebb hibajavítások találhatók a Dynamics 365 for Talent: Onboard alkalmazáshoz.

## <a name="changes-in-core-hr"></a>A Core HR módosításai

A szakaszban ismertetett módosítások a 8.1.2330-ös buildre vonatkoznak.

### <a name="new-page-to-validate-position-hierarchy-data"></a>Új oldal a beosztás-hierarchia adatainak ellenőrzéséhez

A személyzeti osztály munkatársai (HR) és a rendszergazdák ellenőrizni tudják a vezetői hierarchiát a véletlenül importált körkörös hivatkozások esetén. Ezt az új lapot a **Szervezeti adminisztráció \> Hivatkozások \> Beosztások \> Beosztáshierarchia ellenőrzése** részről érheti el.

### <a name="specify-reason-codes-on-leave-types"></a>Okkódok meghatározása a távollét típusaihoz

A szervezeteknek kiegészítő információkra lehet szüksége a szabadságkérelmekkel kapcsolatban. Immár megadhat okkódokat egy adott távolléttípushoz, és megengedheti az alkalmazottak számára okkód választását szabadságkérelmükhöz.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Okkódok kérése adott szabadságtípusokhoz a távollétkérelmek során

Előfordulhat, hogy a szervezetek okkódok beállítását kérik, bizonyos távolléttípusokhoz, amikor a munkavállalók távolléti kérelmeket nyújtanak be. Ez a követelmény a vállalat szabályzata vagy a törvényi követelmények miatt állhat fenn. Meghatározhatja, mely szabadságtípusokhoz szükséges okkód, és alkalmazottaktól megkövetelheti okkód megadását a szabadságtípushoz a távollétkérelmekhez.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Egy szabadság és a távolléti tranzakciólista átadása a HR-nek

Az alkalmazotti szabadság nyomon követése és a szabadidő kiszámításának ismerete nemcsak a HR-nek segít az alkalmazotti kérdések megválaszolásában, hanem lehetővé teszi azt is, hogy a szabadságok alkalmazottaknak történő megítélése pontos legyen. A HR új betekintést kap a tranzakciókhoz (támogatások, könyvelések, kiigazítások és kérelmek) így a HR munkatársai láthatják a távollétegyenlegek okait.

### <a name="deleting-a-record-from-talent-doesnt-remove-the-record-from-common-data-service"></a>A Talent rekordjainak törlése nem távolítja el a rekordot a Common Data Service szolgáltatásból

A Talent Core HR rendszerből eltávolított rekordokat a Common Data Service szolgáltatásból is eltávolítja a rendszer.

### <a name="variable-compensation-plan-valid-fromto-dates-arent-being-honored"></a>A változó kompenzációs terv érvényességének kezdő és záró dátuma nincs figyelembe véve

Ebben a verzióban abban az esetben nem lehet regisztrálni az alkalmazottat egy változó kompenzációs tervre, ha a kezdő dátum a terv kezdő dátuma előtt vagy a záró dátum a terv záró dátuma után van. 

### <a name="performance-review-comments-are-removed-when-users-select-cancel"></a>A teljesítményértékelési megjegyzések törlődnek, ha a felhasználó a Mégse lehetőséget választja

Ebben a kiadásban kijavítottuk azt a hibát, amikor a rendszer eltávolította a felülvizsgálati megjegyzéseket, ha a felhasználó a **Mégse** lehetőséget választotta a megjegyzés módosításának megkezdése után. 

## <a name="in-preview"></a>Előnézetben

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Az előnézeti szolgáltatások csak a védőfalpéldányokban engedélyezettek

Amikor új Talent-példányt hoz létre, megadhatja, hogy a példány **Termelési** vagy **Védőfal** típusú legyen-e. A **Védőfal** típusú példányokkal az új szolgáltatások korai tesztelése végezhető el. Minden létező Talent példányt a **Termelési** példány típusára lesz frissítve. Ha a meglévő példányokat **Védőfal** típusúra szeretné frissíteni, kérje az [ügyfélszolgálat](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) segítségét.

További információ a módosítások közzétételéről: [A Talent létesítése](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="restrict-leave-types-in-time-off-requests"></a>A szabadság típusának korlátozása a távolléti kérelmekben

A szervezetek számos különböző típusú szabadságot tudnak nyújtani az alkalmazottak számára. Előfordulhat azonban, hogy egyes szabadságtípusok esetében nem megfelelő megoldás, hogy az alkalmazottak küldjenek be távolléti kérelmet. Lehetséges, hogy ezeket a szabadságtípusokat a HR kezeli. Ebben a kiadásban konfigurálhatja, hogy az alkalmazottak milyen szabadságtípusokhoz küldhetnek távolléti kérelmet. 

## <a name="coming-soon-in-core-hr"></a>Hamarosan bevezetjük a Core HR-ban

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Részletes teljesítményadatok megtekintése az önkiszolgáló kezelői rendszerben

Egy új beállítással a vezetők mind a közvetlen beosztottak, mind a közvetett beosztottak teljesítményét megtekinthetik. Jelenleg a közvetlen felettesek hozzárendelhetnek teljesítménycélokat és frissíthetik őket, illetve olyan új értékeléseket adhatnak ki, amelyeket az alkalmazottaik is tudnak kezelni. Ezenkívül a közvetlen felettesek és alkalmazottaik karbantarthatják és frissíthetik a teljesítménymutatókat, így garantálható, hogy a teljesítmény ellenőrzési folyamata gördülékenyen megy majd. A módosítás végrehajtásakor a vezetők a közvetlen beosztottakon kívül a bővített jelentések teljesítménnyel kapcsolatos adatait is megtekinthetik és karbantartják. 

### <a name="print-performance-reviews"></a>Teljesítményértékelések nyomtatása

Az alkalmazottak, a vezetők és a HR alkalmazottai kinyomtathatják az alkalmazottak teljesítménykimutatását.
