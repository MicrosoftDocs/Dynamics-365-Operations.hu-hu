---
title: Dataverse-táblák
description: A Microsoft Dynamics 365 Human Resources a Dataverse használatával biztosítja a bővíthetőségi és az integrációs eseteket.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 325bd8a9de07e3978ff6c513975a0e8db22854e0
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054356"
---
# <a name="dataverse-tables"></a>Dataverse-táblák

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A Microsoft Dynamics 365 Human Resources a Dataverse használatával biztosítja a bővíthetőségi és az integrációs eseteket.

> [!NOTE]
> A Human Resources entitások Dataverse-tábláknak felelnek meg. A Dataverse (a korábbi Common Data Service) rendszer kapcsolatos további tudnivalókat és a terminológiai frissítéseket lásd: [Mi a Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)

A következő, Human Resources-entitásokon alapuló Dataverse-táblák érhetők el.

## <a name="benefit-tables"></a>Juttatási táblák

| Név | Tábla |
| --- | --- |
| Juttatás számítási gyakorisága | cdm_benefitcalculationfrequency |
| Fizetési időszak juttatásszámítási gyakorisága | cdm_benefitcalculationfrequencypayperiod |
| Juttatásszámítás gyakorisága | cdm_benefitcalculationrate |
| Juttatás számítási mértékének részletei | cdm_benefitcalculationratedetail |
| Juttatási lehetőség | cdm_benefitoption |
| Juttatási terv | cdm_benefitplan (egyéni mezőtámogatáshoz nem engedélyezett) |
| Juttatás típusa | cdm_benefittype |

## <a name="business-process-tasks-tables"></a>Üzleti folyamat feladatok táblái

| Név | Tábla |
| --- | --- |
| Üzletifolyamat-naptár | cdm_businessprocesscalendar |
| Üzletifolyamat-csoport hozzárendelése | cdm_businessprocessgroupassignment |
| Üzletifolyamat-tár feladatcsoportja | cdm_businessprocesslibrarytaskgroup |
| Üzleti folyamat szakasza | cdm_businessprocessstage |
| Ellenőrzőlista-sablon fejléce | cdm_businessprocesstemplateheader |
| Ellenőrzőlistasablon-feladat | cdm_businessprocesstemplatetask |

## <a name="compensation-tables"></a>Kompenzációs táblák

| Név | Tábla |
| --- | --- |
| Kompenzációs fix terv | cdm_compensationfixedplan |
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
| Fix kompenzációs esemény | cdm_fixedcompensationevent |
| Átruházási szabály | cdm_vestingrule |
| Dolgozói fix kompenzáció | cdm_workerfixedcompensation |

## <a name="organization-tables"></a>Szervezeti táblák

| Név | Tábla |
| --- | --- |
| Részleg | cdm_department |
| Alkalmazás | cdm_employment |
| Cég | cdm_company |
| Állás | cdm_job |
| Beosztás funkciója | cdm_jobfunction |
| Beosztás | cdm_jobposition |
| Beosztás típusa | cdm_positiontype |
| Beosztáshoz rendelt dolgozó | cdm_positionworkerassignmentmap |
| Beosztásdimenzió | cdm_jobpositiondimension|
| Állás típusa | cdm_jobtype |
| Nyelv | cdm_language |
| Megszólítás | cdm_title |

> [!NOTE]
> A **Beosztás típusa**, **Beosztáshoz rendelt dolgozó** és **Foglalkoztatás** pénzügyi dimenziói egyirányú integrációt biztosítanak a Dataverse felé. A pénzügyi dimenziók frissítései jelenleg nem szinkronizálnak a Dataverse szolgáltatásból Human Resources alkalmazásba. 

## <a name="leave-and-absence-tables"></a>Szabadság és távollét táblák

| Név | Tábla |
| --- | --- |
| Szabadsági banki tranzakció | cdm_leavebanktransaction |
| Szabadságbejegyzés | cdm_leaveenrollment |
| Szabadságterv | cdm_leaveplan |
| Szabadságkérelem | cdm_leaverequest |
| Szabadságkérelem részletes adatai | cdm_leaverequestdetail |
| Szabadság típusa | cdm_leavetype |
| Szabadságtípus okkódja | cdm_leavetypereasoncode |

## <a name="payroll-tables"></a>Bérlistatáblák

| Név | Tábla |
| --- | --- |
| Fizetési ciklus | cdm_paycycle |
| Fizetési időszak | cdm_payperiod |
| Bérlista bevételkódja | cdm_payrollearningcode |
| Bankszámla kifizetései | cdm_bankaccountdisbursement |
| Adórégió | cdm_taxregion |

## <a name="worker-tables"></a>Dolgozói táblák

| Név | Tábla |
| --- | --- |
| Dolgozó | cdm_worker |
| Dolgozói cím | cdm_workeraddress |
| Dolgozói személyes adat | cdm_workerpersonaldetail |
| Dolgozó személyazonosító száma | cdm_workerpersonidentificationnumber |
| Dolgozó személyazonosító típusa | cdm_workerpersonidentificationtype |
| Munkanaptár | cdm_workcalendar |
| Munkanaptár napja | cdm_workcalendarday |
| Munkanaptári ünnep |cdm_workcalendarholiday |
| Munkanaptár ünnepsora | cdm_workcalendarholidayline |
| Munkanaptár időintervalluma | cdm_workcalendartimeinterval (egyéni mezőtámogatáshoz nem engedélyezett) |
| Dolgozói bankszámla | cdm_workerbankaccount |

## <a name="worker-setup-tables"></a>Dolgozóbeállítási táblák

| Név | Tábla |
| --- | --- |
| Veteránállapot | cdm_veteranstatus |
| Etnikum | cdm_ethnicorigin |
| Okkód | cdm_reasoncode |
| Személyazonosító-kibocsátó hivatal | cdm_personidentificationissuingagency |

## <a name="competency-tables"></a>Kompetenciatáblák

| Név | Tábla |
| --- | --- |
| Szakértelemtípus | cdm_skilltype |

## <a name="table-relationship-models"></a>Táblakapcsolati modellek

### <a name="worker"></a>Dolgozó

![Dolgozó](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a>Feladat és feladat beosztása

![Feladat és feladat beosztása](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a>Előnyök

![Előnyök](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a>Kompenzáció

![Kompenzáció](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a>Kilépés

![Kilépés](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a>Munkanaptár

![Munkanaptár](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a>Lásd még

[Adatintegrációs technológia kiválasztása](hr-admin-integration-choose-technology.md)<br>
[A Dataverse-integráció konfigurálása](hr-admin-integration-common-data-service.md)<br>
[Dataverse virtuális táblák konfigurálása](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[A Human Resources számára elérhető virtuális táblák – GYIK](hr-admin-virtual-entity-faq.md)<br>
[Mi az a Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Terminológia frissítései](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]