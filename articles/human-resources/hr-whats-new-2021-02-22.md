---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2021. február 22.)
description: Ez a cikk a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2021. február 22-i kiadásban.
author: marcelbf
ms.date: 02/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-02-22
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d07e73ccd922e9d52a9de9260577087a50ef1da4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897835"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-22-2021"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2021. február 22.)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör az új, módosított vagy hamarosan érkező funkciókat írja le Dynamics 365 Human Resources.

A frissítési folyamattal és ütemezéssel kapcsolatos további tudnivalókért lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).

További tájékoztatás az új szolgáltatásokról és a nyilvános megjelenési dátumokról: [A Dynamics 365 Human Resources 2021. második kiadási hullámának áttekintése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Ebben a verzióban

Ez a kiadás az alábbi új funkciókat és hibajavításokat tartalmazza. A változtatások a 8.1.3988-es buildszámra vonatkoznak.

### <a name="new-features"></a>Új funkciók

Az alábbi funkciók általában a következő verzióval lesznek elérhetők.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| Dynamics 365 Human Resources alkalmazás Microsoft Teams redszerhez | [Alkalmazott szabadsági és távolléti élménye a Microsoft Teams rendszerben](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Human Resources alkalmazás a Teamsben](./hr-admin-teams-leave-app.md)<br>[Szabadságkérelmek kezelése a Teamsben](hr-teams-leave-app.md) |

### <a name="bug-fixes"></a>Hibajavítások

Ez a kiadás az alábbi hibajavításokat tartalmazza.

> [!NOTE]
> Célunk, hogy a lehető leghamarabb eljuttassuk Önhöz ezeket az információkat. A cikk első közzététele után frissíthet egy hibajavítást, amely a javításokat tartalmazza a buildben.

| Kiadás száma | Probléma |  Leírás |
| --- | --- | --- |
| 529994 | A **Dolgozó** képernyő **Más néven** mezőjének módosítása nem indít el Dataverse-frissítést | Javítva lett egy olyan hiba, ahol a Dataverse nem frissül, ha a **Más néven** mező frissül a **Dolgozó** képernyőn. |
| 532651 | A Kompenzációs elemzések PBI-jelentése nem használ pénznemátváltást az összes vállalat metrikáinak számításakor | Javítva egy olyan hiba, amely miatt a Kompenzációs elemzések PBI-jelentése nem tudta megfelelően használni a pénznemátváltásokat. |
| 552226 | Az életesemény-feldolgozás bezárul, és egyszeres életeseményhez többször is újra megnyitja a terveket  | Javítva egy olyan hiba, ahol, ha az alkalmazott több jogi személynél is előfordul, és egy életesemény történik, a rendszer egy életeseményrekordot generál minden egyes jogi személyhez, amelyben az alkalmazott van. Az életesemények feldolgozásakor ki kell választani a feldolgozó jogi személyt. A feldolgozási logika azonban nem korlátozza saját magát erre a jogi személyre. Ehelyett feldolgozza az összes jogi személyt, majd bezárja és újra megnyitja a kijelölt jogi személy konstrukcióit. Emiatt az életesemény többször kerül feldolgozásra ugyanabban a jogi személyben, ennek eredményeként az esemény által érintett konstrukciók többszörös zárása/ismételt megnyitása történik. |
| 518064 | Csak egy függő van kiválasztva a jogosult konstrukciókhoz, ha egynél több van megjelölve alapértelmezett kiválasztottként | Javítva egy olyan hiba, amely miatt a jogosult konstrukciókban nem lehet automatikusan több alapértelmezett kijelölt személy. Személyes kapcsolattartóként elsődleges kedvezményezett is kijelölhető már. Az elsődleges kedvezményezett 100%-ként szerepel a jogosult konstrukciókban, ha több kedvezményezett is van. |
| 552365 | A saját adatbázisos (BYOD) exportálási feladatok létrehozása sikertelen a Platform 40-es frissítésre való frissítése után | Javítva egy probléma, ahol a BYOD exportálások sikertelenek a platform 40-es frissítésének környezetre való alkalmazása után. |
| 547123 | A vezérlőpult Feladatlistáján lekérdezett feladatok számának korlátozása | A Feladatlistában látható feladatok száma most 15-re korlátozódik, hogy javítsa a teljesítménnyel kapcsolatos problémát, amelyet a betöltött feladatok túl nagy száma okozott. |

## <a name="in-preview"></a>Előnézetben

Az alábbi új funkciók előzetes verzióban érhetők el. A funkciók be- vagy kikapcsolásával kapcsolatos további információkért lásd a [Szolgáltatások kezelése](hr-admin-manage-features.md) című témakört.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| Szabadságok vállalatközi nézete vezetőknek | [Munkavállalói szabadságok vállalatközi nézete vezetőknek](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Szabadság és távollét paramétereinek konfigurálása](./hr-leave-and-absence-parameters.md) |
| Juttatáskezelési munkaterület | [Juttatáskezelési munkaterület (előzetes verzió)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Juttatáskezelési munkaterület](hr-benefits-management-workspace.md) |
| Az alkalmazottak korlátozása az üzleti kapcsolattartók részleteinek szerkesztése elől | [Az alkalmazottak korlátozása az üzleti kapcsolattartók részleteinek szerkesztése elől](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [Személyes adatok szerkesztésének korlátozása](hr-employee-self-service-restrict-editing.md)|

## <a name="coming-soon"></a>Hamarosan

| Funkció | Részletek |
| --- | --- |
| A vezető által az alkalmazottakhoz megadott szakértelmet egy munkafolyamat automatikusan jóváhagyhatja | Hamarosan. |

A tervezett funkciók és az ütemezett kiadásaik teljes listáját lásd: [A Dynamics 365 Human Resources 2021. első kiadási hullámának áttekintése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="terminology-updates-for-microsoft-dataverse"></a>Terminológiai frissítések a Microsoft Dataverse számára

2020 novemberétől a Common Data Service szolgáltatás új neve: [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). A további tudnivalókat lásd a [hivatalos közleményben](https://powerapps.microsoft.com/blog/reshape-the-future-of-work-with-microsoft-dataverse-for-teams-now-generally-available/) a Power Apps blogon. Ezzel a névváltozással együtt a Dataverse terminológiája is részben frissült. Például az *entitás* mostantól *tábla*, a *mező* pedig *oszlop*. A további tudnivalókat lásd: [Terminológia frissítései](/powerapps/maker/data-platform/data-platform-intro#terminology-updates).

Ebben a kiadásban a Dynamics 365 Human Resources rendszer Dataverse-integrációjával kapcsolatos terminológiáját frissítettük az alkalmazás egészében, hogy tükrözze ezeket a változásokat. Például a **Common Data Service-integráció** űrlapjának neve most **Microsoft Dataverse-integráció**.

A Dynamics 365 Human Resources rendszer Microsoft Dataverse rendszerrel történő integrációjával kapcsolatos további tudnivalókat lásd: [A Microsoft Dataverse-integráció konfigurálása](./hr-admin-integration-common-data-service.md) és [Microsoft Dataverse virtuális táblák konfigurálása](./hr-admin-integration-common-data-service-virtual-entities.md).

## <a name="updates-to-service-deployment"></a>A szolgáltatástelepítés frissítései

A 2021. február 22-i kiadástól kezdve módosítjuk a regionális szolgáltatásfrissítési telepítést. A módosítások között szerepel annak a sorrendnek a rotációja, amelyben a globális régiók megkapják a Human Resources szolgáltatás frissítéseit, és a frissítési fokozatok közötti várakozási időt is módosítják. Ezek a változtatások még jobban összhangban vannak a biztonságos telepítési gyakorlatokkal (SDP), így javítható a szolgáltatás stabilsága, a minőség és a támogatottság.

Továbbra is a telepítés kéthetes sorrendjét folytatjuk. Előfordulhat azonban, hogy az ügyfelek észlelik, hogy a frissítéseket a Human Resources környezetére jellemzően a kéthetes ciklus egy másik napján alkalmazzák, mint a korábbi verziókban.

A szolgáltatás frissítési folyamatával kapcsolatos további tudnivalókat lásd: [Frissítési folyamat](./hr-admin-setup-update-process.md).

## <a name="see-also"></a>Lásd még

[Újdonságok és változások a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2021. első kiadási hullámának áttekintése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]