---
title: Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. december 3.)
description: Ez a cikk a Microsoft Dynamics 365 Talent új vagy módosított funkcióit írja le.
author: Darinkramer
manager: AnnBe
ms.date: 12/03/2019
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
ms.search.validFrom: 2019-12-03
ms.dyn365.ops.version: Talent
ms.openlocfilehash: bf1ad4ca2e0ab18aaa35a7410d80a54e7a2160ce
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528693"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-december-3-2019"></a>Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. december 3.)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a cikk a Dynamics 365 Talent szolgáltatásban található új vagy módosított funkciókat írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben

A kiadás a Dynamics 365 Talent: Attract apró hibáinak javításait is tartalmazza.

## <a name="changes-in-onboard"></a>Változások az Onboard alkalmazásban

A kiadás a Dynamics 365 Talent: Onboard apró hibáinak javításait is tartalmazza.

## <a name="changes-in-core-hr"></a>A Core HR módosításai

A szakaszban ismertetett módosítások a 8.1.2646-ös buildre vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok az Microsoft Dynamics Lifecycle Services (LCS) támogatási számaira vonatkoznak.

### <a name="feature-management-workspace"></a>A Funkciókezelés munkaterület

A **Funkció-kezelés** munkaterülete az egyes kiadásokban kiadott funkciók listáját tartalmazza. Alapértelmezés szerint az új szolgáltatások ki vannak kapcsolva. A munkaterületen bekapcsolhatja a szolgáltatásokat, és megtekintheti a rájuk vonatkozó dokumentációt. A funkciókezeléssel kapcsolatos további tudnivalókat lásd [Funkciókezelés áttekintése](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Minden új funkció megmarad előzetes verzióban legalább 30 napig, és általában 30-60 napig. A főbb funkciók általában az előzetes időszakot követően minden év októberében és áprilisában érhetők el. Amint az új funkciókat a **Funkciókezelés** munkaterületen látja, be lehet kapcsolni őket. Előfordulhat, hogy egyes funkciók alapértelmezés szerint be vannak kapcsolva.
 
Időnként egy szerves funkció alapértelmezésben be van kapcsolva, de nem kapcsolható ki (például a **Funkciókezelési** munkaterület).
 
Ha egy szolgáltatás általában elérhető, előfordulhat, hogy a működési környezetben be van kapcsolva vagy ki van kapcsolva. A **funkciókezelés** munkaterület jelzi, hogy egy előzetes funkció mikor válik kötelezővé. Ez a dátum általában október 1. vagy április 1., hogy a féléves kiadási tervekkel összehangolják. Nem kapcsolhatja ki a kötelező funkciókat. Amíg nem válik kötelezővé, bármely környezetben ki- és bekapcsolhatja a funkciót.

### <a name="add-automatic-scheduling-of-batch-job-history-cleanup-332528"></a>Automatikus ütemezés hozzáadása a kötegelt feladatok előzményeinek törléséhez (332528)

Ezzel a módosítással a **Kötegelt feladatok előzményei** minden éjjel lefut, és eltávolítja a 30 napnál régebbi kötegelt feladatelőzményeket.

### <a name="talent-doesnt-respond-in-worker-actions-when-identification-number-length-doesnt-match-the-identification-type-390971"></a>A Talent nem reagál a munkavállalói tevékenységben, ha az azonosítási szám hossza nem egyezik az azonosító típusával (390971)

Ez a kiadás kijavítja a hibát, ha az azonosítási szám hossza nem egyezik meg az azonosítótípuson belüli definícióval. 

### <a name="fixed-compensation-doesnt-update-level-with-changes-to-position-details--348085"></a>A fix kompenzáció nem frissül a pozícióadatok változásával együtt (348085)

Az e heti kiadásban a **Kompenzáció kezdő dátuma** meghatározza, hogy az adott alkalmazottra vonatkozóan mikor hoz létre új fix kompenzációs rekordot az adott pozícióhoz kapcsolódó feladat.

### <a name="workers-employees-and-contractors-lists-show-worker-type-as-both-when-they-should-only-be-worker-or-contractor-384473"></a>A munkavállalók, az alkalmazottak és a alvállalkozók lista „Mindkettő” értékkel jeleníti meg a munkavállaló típusát, pedig azok csak munkavállalók vagy alvállalkozók (384473)

Ez a módosítás pontosan tükrözi a bevitt dolgozó típusát (vállalkozó vagy alkalmazott).

### <a name="email-notifications-for-new-hire-actions-dont-contain-name-information-due-to-security-policies-383402"></a>Az új felvételi műveletekkel kapcsolatos e-mail-értesítések a biztonsági irányelvek miatt nem tartalmaznak névinformációkat (383402)

Ez a módosítás helyesbíti a helyőrzőkön belüli kereszt- és vezetéknév mezőkben megjelenő információkat az adott munkafolyamat esetében, ha a speciális biztonság engedélyezve van.

### <a name="system-allows-two-full-day-leave-requests-for-the-same-day-379284"></a>A rendszer lehetővé teszi két egész napos szabadság kérését ugyanarra a napra (379284)

Ezzel a módosítással nem lehet két szabadságkérést indítani ugyanarra a napra. 

### <a name="address-changes-list-should-be-sorted-by-effective-date-352798"></a>A címváltozások listáját az Érvényesség dátuma szerint kellene rendezni (352798)

Ezzel a módosítással a címváltozások listája az **Érvényesség dátuma** szerint van rendezve.

### <a name="leave-requests-should-allow-deletes-from-common-data-service-to-talent-376999"></a>A szabadságkérelmeknek lehetővé kellene tenniük a Common Data Service alkalmazásból a Talent alkalmazásba irányuló törléseket (376999)

Ezzel a módosítással a vázlat és visszavont szabadságkérelmek törölhetők a Common Data Service alkalmazásból és ezután a Talent alkalmazásból is eltávolításra kerülnek.

### <a name="delete-earning-codes-is-allowed-when-the-same-earning-code-is-assigned-to-an-employee-371792"></a>A bevételkódok törlése engedélyezett, ha ugyanaz a bevételkód van hozzárendelve egy alkalmazotthoz (371792)

Ebben a kiadásban először el kell távolítani a bevételkódot az alkalmazottból, mielőtt törölné a bevételkódot a rendszerből.

### <a name="leave-and-absence-workflow-with-two-approval-stages-fails-to-complete--391116"></a>A két jóváhagyási fokozatú Szabadság és a távollét munkafolyamat nem fejeződik be (391116)

Ezzel a módosítással a szabadság és távollét munkafolyamat végighalad a lépéseken, ha egynél több jóváhagyási szakasz van beállítva a kérelemhez.

### <a name="issue-date-doesnt-sync-to-common-data-service-when-updated-or-entered-in-talent-397361"></a>A kiadási dátum nincs szinkronizálva a Common Data Service alkalmazással, amikor frissítik vagy beviszik a Talent alkalmazásba (397361)

Ez a változtatás kijavítja azt a hibát, amikor a **Személyazonosító** rekordok nincsenek a Common Data Service és a Talent között szinkronizálva.

### <a name="hierarchy-circular-reference-error-issued-when-assigning-a-manager-to-a-position-386659"></a>A menedzser pozícióhoz rendelésekor a rendszer hierarchia körkörös hivatkozási hibát ad (386659)

Ez a változtatás javít egy olyan egyedi forgatókönyvet, amelyben körkörös hivatkozáshiba jelenik meg egy új felettes egy beosztáshoz történő hozzárendelése során.

### <a name="common-data-service-entities-that-now-support-custom-fields"></a>Common Data Service Entitások, melyek most már támogatják az egyéni mezőket

A következő Common Data Service entitások támogatják már az egyéni mezőket:

| Név | Entitás |
| --- | --- |
| Bankszámla kifizetései | cdm_bankaccountdisbursement |
| Juttatás számítási gyakorisága | cdm_benefitcalculationfrequency |
| Fizetési időszak juttatásszámítási gyakorisága | cdm_benefitcalculationfrequencypayperiod |
| Juttatásszámítás gyakorisága | cdm_benefitcalculationrate |
| Juttatás számítási mértékének részletei | cdm_benefitcalculationratedetail |
| Juttatási lehetőség | cdm_benefitoption |
| Juttatási terv | cdm_benefitplan (egyéni mezőtámogatáshoz nem engedélyezett) |
| Juttatás típusa | cdm_benefittype |
| Üzletifolyamat-naptár | cdm_businessprocesscalendar |
| Üzletifolyamat-csoport hozzárendelése | cdm_businessprocessgroupassignment |
| Üzletifolyamat-tár feladatcsoportja | cdm_businessprocesslibrarytaskgroup |
| Üzleti folyamat szakasza | cdm_businessprocessstage |
| Ellenőrzőlista-sablon fejléce | cdm_businessprocesstemplateheader |
| Ellenőrzőlistasablon-feladat | cdm_businessprocesstemplatetask |
| Cég | cdm_company |
| Fix kompenzációs konstrukció | cdm_compensationfixedplan |
| Kompenzációs rács | cdm_compensationgrid |
| Kompenzációs szint | cdm_compensationlevel |
| Kompenzáció – fizetés gyakorisága | cdm_compensationpayfrequency |
| Kompenzációs hivatkozási pont beállítása | cdm_compensationreferencepointsetup |
| Kompenzációs hivatkozási pontok beállítási sora | cdm_compensationreferencepointsetupline |
| Kompenzációs régió | cdm_compensationregion |
| Kompenzációs struktúra | cdm_compensationstructure |
| Változó kompenzációs konstrukció | cdm_compensationvariableplan |
| Változó kompenzációs konstrukció szintje | cdm_compensationvariableplanlevel |
| Változó kompenzációs konstrukció típusa | cdm_compensationvariableplantype |
| Részleg  | cdm_department |
| Foglalkoztatás | cdm_employment |
| Etnikum | cdm_ethnicorigin |
| Fix kompenzációs esemény | cdm_fixedcompensationevent |
| Állás | cdm_job |
| Beosztás funkciója | cdm_jobfunction |
| Feladat pozíciója | cdm_jobposition |
| Feladattípus | cdm_jobtype |
| Nyelv | cdm_language |
| Szabadság banki tranzakciója | cdm_leavebanktransaction |
| Szabadság regisztrációja | cdm_leaveenrollment |
| Szabadságterv | cdm_leaveplan |
| Szabadságkérelem | cdm_leaverequest |
| Szabadságkérelem részletes adatai | cdm_leaverequestdetail |
| Szabadság típusa | cdm_leavetype |
| Szabadságtípus okkódja | cdm_leavetypereasoncode |
| Fizetési ciklus | cdm_paycycle |
| Fizetési időszak | cdm_payperiod |
| Bérlista bevételkódja | cdm_payrollearningcode |
| Személyazonosító kiállító hivatala | cdm_personidentificationissuingagency |
| Beosztás típusa | cdm_positiontype |
| Beosztáshoz rendelt dolgozó | cdm_positionworkerassignmentmap |
| Okkód | cdm_reasoncode |
| Szakértelemtípus | cdm_skilltype |
| Adórégió | cdm_taxregion |
| Átruházási szabály | cdm_vestingrule |
| Veteránállapot | cdm_veteranstatus |
| Munkanaptár | cdm_workcalendar |
| Munkanaptár napja | cdm_workcalendarday |
| Munkanaptári ünnep |cdm_workcalendarholiday |
| Munkanaptár ünnepsora | cdm_workcalendarholidayline |
| Munkanaptár időintervalluma | cdm_workcalendartimeinterval (egyéni mezőtámogatáshoz nem engedélyezett) |
| Dolgozó | cdm_worker |
| Dolgozó címe | cdm_workeraddress |
| Dolgozói bankszámla | cdm_workerbankaccount |
| Dolgozói fix kompenzáció | cdm_workerfixedcompensation |
| Dolgozói személyes adat | cdm_workerpersonaldetail |
| Dolgozó személyazonosító száma | cdm_workerpersonidentificationnumber |
| Dolgozó személyazonosító típusa | cdm_workerpersonidentificationtype |

## <a name="in-preview"></a>Előnézetben

Az előnézeti szolgáltatások csak **tesztkörnyezetekben** érhetők el.

### <a name="print-performance-reviews"></a>Teljesítményértékelések nyomtatása

Lásd [Teljesítményértékelések nyomtatása](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) a Dynamics 365: 2019 release wave 2 tervben.


[!INCLUDE[footer-include](../includes/footer-banner.md)]