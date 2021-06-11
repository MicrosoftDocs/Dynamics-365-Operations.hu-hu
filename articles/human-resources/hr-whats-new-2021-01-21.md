---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2021. január 21.)
description: Ez a témakör a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2021. január 21-i kiadásban.
author: marcelbf
ms.date: 01/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-01-21
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 81586fbe996d526e9581bc052c93feafbbc42fc1
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054883"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-january-21-2021"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2021. január 21.)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Dynamics 365 Human Resources új, módosított vagy nemsokára várható szolgáltatásait írja le.

A frissítési folyamattal és ütemezéssel kapcsolatos további tudnivalókért lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).

További tájékoztatás az új szolgáltatásokról és a nyilvános megjelenési dátumokról: [A Dynamics 365 Human Resources 2020. második kiadási hullámának áttekintése](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).


## <a name="in-this-release"></a>Ebben a verzióban

Ez a kiadás az alábbi új funkciókat és hibajavításokat tartalmazza. A változtatások a 8.1.3866-es buildszámra vonatkoznak.

### <a name="new-features"></a>Új funkciók

Az alábbi funkciók általában a következő verzióval lesznek elérhetők.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| 10.0.16(40) platformfrissítés | -- | [Platformfrissítések a Finance and Operations alkalmazás 10.0.16 verziójához (2021. február)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-16.md) |
| Továbbfejlesztett munkafolyamat-kérelmek és -jóváhagyások | [Szervezeti és személyzeti felügyeleti munkafolyamat-tapasztalatok továbbfejlesztései](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Konfigurációs beállítás a hozzám rendelt munkaelemek lista pozicionálásához](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Az 1095-C űrlap, az 1095-B űrlap Affordable Care Act megfelelőségi frissítései, valamint elektronikus jelentéskészítés az örökölt Juttatások szolgáltatásban | -- | -- | 
| A juttatások kezelése mostantól támogatja az ACA-megfelelőségi jelentéseket az egyesült államokbeli jogi személyek számára | -- | [ACA-jelentések készítése a Juttatáskezelésben](hr-benefits-management-aca-reports.md) |
| A juttatások kezelése most juttatási szintekkel és kétszintű juttatási entitásokkal rendelkezik  | -- | -- |

### <a name="bug-fixes"></a>Hibajavítások

Ez a kiadás az alábbi hibajavításokat tartalmazza.

> [!NOTE]
> Célunk, hogy a lehető leghamarabb eljuttassuk Önhöz ezeket az információkat. Előfordulhat, hogy a jelen témakört frissítjök olyan hibajavításokkal, amelyek annak első közzététele után léptek életbe.

| Kiadás száma | Kiadás |  Leírás |
| --- | --- | --- |
| 533079 | Navigációs hiba: „Helytelenül lehívott űrlap” a levonások keresésekor. | Kijavított hiba a juttatások levonásának **Adott dátumtól** történő megtekintésekor. |
| 543641 | Az elektronikus jelentésen nem jelenik meg az irányítószám.  | Belső hiba kijavítva: az ACA elektronikus jelentéseiben nem jelent meg az irányítószám a juttatások kezeléséhez, ha a fedezeti kód M és Q között van. |
| 542815 | Az Alkalmazotti önkiszolgáló szolgáltatásban a személyes kapcsolatfelvételi képernyő segítségével az alkalmazottak láthatják egymás személyes kapcsolattartóját. | Javított hiba: az Alkalmazotti önkiszolgáló személyes kapcsolattartóinak **Szerkesztés** űrlapja nem korlátozza a lekérdezést eléggé annak biztosításához, hogy csak egyetlen személyes kapcsolattartót kérjenek le, így a felhasználó gyorsbillentyűk használatával megtekintheti más személyek kapcsolattartóit. |
| 536157 | A **Microsoft Dataverse integrációja** oldalt nem lehet megnyitni a Rendszerfelügyelet pontban az IsVirtualEntityPackageInstalled() hívás miatt. | A probléma megakadályozza a **Microsoft Dataverse integrációja** oldal Human Resources rendszerben történő betöltését. |
| 533079 | Navigációs hiba: „Helytelenül lehívott űrlap” a levonások keresésekor. | Javított hiba: a **Levonások** űrlapon a juttatások kezelése során az **Adott dátumtól** nézetben hiba lépett fel. |
| 537264 | A **Személyes adatok** gyorslap hiányzik a jelölt rekordjából. | A jelölt személyes adatai most már elérhetők a jelölt rekordjában. |
| 537267 | A **Szakmai tapasztalat** nem jelenik meg a belső jelöltek rekordjaiban. | A **Szakmai tapasztalat** gyorslap most megjelenik a belső jelöltek rekordjaiban. Korábban, ha a jelölt belső volt, a **Szakmai tapasztalat** helyére a **Foglalkoztatási előzmények** (a pályázónak a szervezeten belüli foglalkoztatási előzményei) került. Mindkettő érvényes, és mindkettőnek meg kell jelennie belső jelöltek esetén. |
| 537067 | Nem jelenik meg a **Munkáltatóval való kapcsolatfelvétel engedélyezése** lehetőség. | A **Munkáltatóval való kapcsolatfelvétel engedélyezése** vezérlőt adták hozzá a jelölt rekordjához a **Szakmai tapasztalat szerkesztése** ablaktáblán. |
| 525957 | A **Jelölt állapota** nem frissül belső jelöltek esetén, ha az átvitel befejeződött. | Átvitel befejeződése esetén (kiválasztják a **Beosztás módosítása** vagy a **Folytatás** gombot a **Dolgozó áthelyezése új beosztásba** oldalon), a jelölt rekordjában az **Állapot** lehetőségnek **Felvéve** értékre kell módosulnia. |
| 537051 | Az indiai rúpia és a török líra pénznemszimbólumai nem szinkronizálódnak megfelelően a Dataverse rendszerre | Az indiai rúpia és a török líra szimbólumai most megfelelően szinkronizálódnak a Dataverse rendszerre. |
| 534846 | Az Adatkezelés rendszerhez engedélyezni kell a toborzási táblákat. | A toborzási kérések és jelöltek számára létrehozott új táblázatok mostantól engedélyezve vannak az Adatkezelés rendszerben. Ez lehetővé teszi a változáskövetés engedélyezését a tábláknál, lehetővé téve az OData változáskövetést a Dataverse virtuális táblákon. |
| 533474 | Hiányzó hivatkozás javítása a Microsoft.SqlServer.XEvent.dll fájlra. | A Microsoft.SqlServer.XEvent.dll fájl szerelvény betöltési kivételei blokkolták a Dataverse virtuális táblák bizonyos környezetekben való beállítását. |
| 481122 | A **Személyek** munkaterület megszűnt beosztásokat jelenített meg. | A megszűnt beosztások nyitott beosztásként jelentek meg a **Személyek** munkaterületen. A megszűnt beosztások már nem jelennek meg. | 
| 541978 | Elsődleges e-mail-cím hozzáadása a BaseWorker entitáshoz. | Ez a módosítás hozzáadta a dolgozó elsődleges e-mail-címét a HcmWorkerBaseEntity elemhez. |

## <a name="in-preview"></a>Előnézetben

Az alábbi új funkciók előzetes verzióban érhetők el. A funkciók be- vagy kikapcsolásával kapcsolatos további információkért lásd a [Szolgáltatások kezelése](hr-admin-manage-features.md) című témakört.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| Human Resources alkalmazás a Microsoft Teams alkalmazásban | [Alkalmazott szabadsági és távolléti élménye a Microsoft Teams rendszerben](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Human Resources alkalmazás a Teamsben](./hr-admin-teams-leave-app.md)<br>[Szabadságkérelmek kezelése a Teamsben](hr-teams-leave-app.md) |
| Integráció a LinkedIn Talent Hub szolgáltatással | [Integráció a LinkedIn Talent Hub szolgáltatással](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/integration-linkedin-talent-hub) | [Integráció a LinkedIn Talent Hub szolgáltatással](./hr-admin-integration-linkedin.md) |
| Szabadságok vállalatközi nézete vezetőknek | [Munkavállalói szabadságok vállalatközi nézete vezetőknek](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Szabadság és távollét paramétereinek konfigurálása](./hr-leave-and-absence-parameters.md) |
|További betekintés biztosítása a szabadságegyenlegekbe| [További betekintés biztosítása a szabadságegyenlegekbe](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/provide-additional-insight-into-leave-balances) | [Alkalmazotti szabadság kezelése](./hr-leave-and-absence-manage-employee-leave.md) |
| A vezetők benyújthatnak toborzási kérelmeket pozíciókra | [A vezetők benyújthatnak toborzási kérelmeket a nyitott pozíciókra](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/manager-submit-request-recruit-open-positions) | [Toborzási kérelem hozzáadása](./hr-personnel-recruit.md#add-a-recruiting-request) |
| Továbbfejlesztett jelöltprofil a Személyzetkezelésben | [Továbbfejlesztett jelöltprofil a személyzetkezelésben](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enhanced-candidate-profile-personnel-management) | [Jelöltprofil hozzáadása vagy szerkesztése](./hr-personnel-recruit.md#add-or-edit-a-candidate-profile) |
| Egyszerűsített integráció engedélyezése a toborzási szolgáltatókkal | [Egyszerűsített integráció engedélyezése a toborzási szolgáltatókkal](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enable-simplified-integration-recruiting-providers) | [Jelöltek toborzása](./hr-personnel-recruit.md) |

## <a name="coming-soon"></a>Hamarosan
| Funkció | Részletek |
| --- | --- |
| Juttatási regisztrációk e-mailben való visszaigazolása | Ezzel a funkcióval visszaigazoló e-mailt küldhet az alkalmazottaknak, amikor kijelentkeznek a juttatások regisztrációs szolgáltatásából a Munkavállalói önkiszolgáló rendszerben. További információ: [Juttatáskezelési paraméterek konfigurálása vállalatonként](hr-benefits-setup-parameters-per-company.md). |
| A vezető által az alkalmazottakhoz megadott szakértelmet egy munkafolyamat automatikusan jóváhagyhatja | Hamarosan. |

A tervezett szolgáltatások és az ütemezett kiadások teljes listája az alábbi témakörben olvasható: [A Dynamics 365 Human Resources 2020. második kiadási hullámának áttekintése](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="terminology-updates-for-microsoft-dataverse"></a>Terminológiai frissítések a Microsoft Dataverse számára

2020 novemberétől a Common Data Service szolgáltatás új neve: [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). A további tudnivalókat lásd a [hivatalos közleményben](https://powerapps.microsoft.com/blog/reshape-the-future-of-work-with-microsoft-dataverse-for-teams-now-generally-available/) a Power Apps blogon. Ezzel a névváltozással együtt a Dataverse terminológiája is részben frissült. Például az *entitás* mostantól *tábla*, a *mező* pedig *oszlop*. A további tudnivalókat lásd: [Terminológia frissítései](/powerapps/maker/data-platform/data-platform-intro#terminology-updates).

Ebben a kiadásban a Dynamics 365 Human Resources rendszer Dataverse-integrációjával kapcsolatos terminológiáját frissítettük az alkalmazás egészében, hogy tükrözze ezeket a változásokat. Például a **Common Data Service-integráció** űrlapjának neve most **Microsoft Dataverse-integráció**.

A Dynamics 365 Human Resources rendszer Microsoft Dataverse rendszerrel történő integrációjával kapcsolatos további tudnivalókat lásd: [A Microsoft Dataverse-integráció konfigurálása](./hr-admin-integration-common-data-service.md) és [Microsoft Dataverse virtuális táblák konfigurálása](./hr-admin-integration-common-data-service-virtual-entities.md).

## <a name="see-also"></a>Lásd még

[Újdonságok és változások a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2020. második kiadási hullámának áttekintése](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]