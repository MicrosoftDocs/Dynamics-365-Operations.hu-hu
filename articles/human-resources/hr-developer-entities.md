---
title: Common Data Service-entitások
description: A Microsoft Dynamics 365 Human Resources a Common Data Service használatával biztosítja a bővíthetőségi és az integrációs eseteket.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 988fa0b6d39a49b973626a8a0abe83c546f42297
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2020
ms.locfileid: "4530006"
---
# <a name="common-data-service-entities"></a>Common Data Service-entitások

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

A Microsoft Dynamics 365 Human Resources a Common Data Service használatával biztosítja a bővíthetőségi és az integrációs eseteket.

A Common Data Service eltávolításával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Mi a Common Data Service?](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).

A Human Resources rendszerhez a következő erőforrások állnak rendelkezésére a Common Data Service szolgáltatásban.

## <a name="benefit-entities"></a>Juttatási egységek

| Név | Entitás |
| --- | --- |
| Juttatás számítási gyakorisága | cdm_benefitcalculationfrequency |
| Fizetési időszak juttatásszámítási gyakorisága | cdm_benefitcalculationfrequencypayperiod |
| Juttatásszámítás gyakorisága | cdm_benefitcalculationrate |
| Juttatás számítási mértékének részletei | cdm_benefitcalculationratedetail |
| Juttatási lehetőség | cdm_benefitoption |
| Juttatási terv | cdm_benefitplan (egyéni mezőtámogatáshoz nem engedélyezett) |
| Juttatás típusa | cdm_benefittype |

## <a name="business-process-tasks-entities"></a>Üzleti folyamat feladatentitásai

| Név | Entitás |
| --- | --- |
| Üzletifolyamat-naptár | cdm_businessprocesscalendar |
| Üzletifolyamat-csoport hozzárendelése | cdm_businessprocessgroupassignment |
| Üzletifolyamat-tár feladatcsoportja | cdm_businessprocesslibrarytaskgroup |
| Üzleti folyamat szakasza | cdm_businessprocessstage |
| Ellenőrzőlista-sablon fejléce | cdm_businessprocesstemplateheader |
| Ellenőrzőlistasablon-feladat | cdm_businessprocesstemplatetask |

## <a name="compensation-entities"></a>Kompenzációs entitások

| Név | Entitás |
| --- | --- |
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
| Fix kompenzációs esemény | cdm_fixedcompensationevent |
| Átruházási szabály | cdm_vestingrule |
| Dolgozói fix kompenzáció | cdm_workerfixedcompensation |

## <a name="organization-entities"></a>Szervezeti entitások

| Név | Entitás |
| --- | --- |
| Részleg  | cdm_department |
| Foglalkoztatás | cdm_employment |
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
> A **Beosztás típusa**, **Beosztáshoz rendelt dolgozó** és **Foglalkoztatás** pénzügyi dimenziói egyirányú integrációt biztosítanak a Common Data Service felé. A pénzügyi dimenziók frissítései jelenleg nem szinkronizálnak a Common Data Service szolgáltatásból Human Resources alkalmazásba. 

## <a name="leave-and-absence-entities"></a>Szabadság- és távollétentitások

| Név | Entitás |
| --- | --- |
| Szabadsági banki tranzakció | cdm_leavebanktransaction |
| Szabadság regisztrációja | cdm_leaveenrollment |
| Szabadságterv | cdm_leaveplan |
| Szabadságkérelem | cdm_leaverequest |
| Szabadságkérelem részletes adatai | cdm_leaverequestdetail |
| Szabadság típusa | cdm_leavetype |
| Szabadságtípus okkódja | cdm_leavetypereasoncode |

## <a name="payroll-entities"></a>Bérlistaentitás

| Név | Entitás |
| --- | --- |
| Fizetési ciklus | cdm_paycycle |
| Fizetési időszak | cdm_payperiod |
| Bérlista bevételkódja | cdm_payrollearningcode |
| Bankszámla kifizetései | cdm_bankaccountdisbursement |
| Adórégió | cdm_taxregion |

## <a name="worker-entities"></a>Dolgozói entitások

| Név | Entitás |
| --- | --- |
| Dolgozó | cdm_worker |
| Dolgozó címe | cdm_workeraddress |
| Dolgozói személyes adat | cdm_workerpersonaldetail |
| Dolgozó személyazonosító száma | cdm_workerpersonidentificationnumber |
| Dolgozó személyazonosító típusa | cdm_workerpersonidentificationtype |
| Munkanaptár | cdm_workcalendar |
| Munkanaptár napja | cdm_workcalendarday |
| Munkanaptári ünnep |cdm_workcalendarholiday |
| Munkanaptár ünnepsora | cdm_workcalendarholidayline |
| Munkanaptár időintervalluma | cdm_workcalendartimeinterval (egyéni mezőtámogatáshoz nem engedélyezett) |
| Dolgozói bankszámla | cdm_workerbankaccount |

## <a name="worker-setup-entities"></a>Dolgozó beállítási entitásai

| Név | Entitás |
| --- | --- |
| Veteránállapot | cdm_veteranstatus |
| Etnikum | cdm_ethnicorigin |
| Okkód | cdm_reasoncode |
| Személyazonosító kiállító hivatala | cdm_personidentificationissuingagency |

## <a name="competency-entities"></a>Kompetenciaentitások

| Név | Entitás |
| --- | --- |
| Szakértelemtípus | cdm_skilltype |

## <a name="entity-relationship-models"></a>Entitáskapcsolati modellek

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

[Válasszon ki egy adatintegrációs technológiát](hr-admin-integration-choose-technology.md)</br>
[A Common Data Service-integráció konfigurálása](hr-admin-integration-common-data-service.md)
