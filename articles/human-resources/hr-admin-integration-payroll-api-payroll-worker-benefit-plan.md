---
title: Bérlistában szereplő dolgozói juttatási terv
description: 'Ez a cikk részletes adatokat és példalekérdezéseket tartalmaz a bérlista dolgozói juttatási tervének entitáshoz a következőben: <a0/<a0/<a3/Dynamics 365 Human Resources.'
author: twheeloc
ms.date: 07/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ef45855d9e60131ac065ae6e2769b71ae3f69537
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902285"
---
# <a name="payroll-worker-benefit-plan"></a>Bérlistában szereplő dolgozói juttatási terv


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a dolgozói juttatási terv bérlistaentitását ismerteti Dynamics 365 Human Resources.

Fizikai név: mshr_payrollworkerbenefitplanentities.

### <a name="description"></a>Leírás

Ez az entitás információt nyújt az adott dolgozóhoz tartozó juttatási tervről.

## <a name="properties"></a>Tulajdonságok

| Tulajdonság</br>**Fizikai név**</br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Személyzeti szám**</br>mshr_personnelnumber</br>*Sztring* | Írásvédett</br>Szükséges | Az alkalmazott egyedi személyzeti száma. |
| **Jogi személy azonosítója**</br>mshr_legalentityID</br>*Sztring* | Írásvédett | Megadja a jogi személyt (vállalatot). |
| **Időszak azonosítója**</br>mshr_periodid</br>*Sztring* | Írásvédett | Az időszak azonosítója. |
| **Tervazonosító**</br>mshr_planid</br>*Sztring* | Írásvédett | A terv azonosítója. |
| **Fedezeti beállítás**</br>mshr_coverageoptionid</br>*Sztring* | Írásvédett | A fedezeti lehetőség azonosítása. |
| **Levonás kezdő dátuma**</br>mshr_deductionstartdatetime</br>*Dátum és idő eltolása* | Írásvédett | A levonás kezdő dátuma. |
| **Levonás záró dátuma**</br>mshr_deductionenddatetime</br>*Dátum és idő eltolása* | Írásvédett | A levonás záró dátuma. |
| **Állapot**</br>mshr_status</br>*[Alkalmazotti juttatási program állapotának beállításkészlete](hr-admin-integration-payroll-api-benefit-employee-plan-status.md)* | Írásvédett | A juttatási terv állapota. |
| **Érvényesség kezdete**</br>mshr_validfrom</br>*Dátum és idő eltolása* | Írásvédett | A rekord érvényességének kezdő időpontja. |
| **Érvényesség vége:**</br>mshr_validto</br>*Dátum és idő eltolása* |  Írásvédett | A rekord érvényességének záró időpontja. |
| **Tervtípus azonosítója**</br>mshr_plantypeid</br>*Sztring* | Írásvédett | A tervtípus azonosítója. |
| **Konstrukció típuskódja**</br>mshr_plantypecode</br>*[juttatási terv típusának fedezetéhez tartozó beállításkészlet](hr-admin-integration-payroll-api-benefit-plan-type-cover.md)* | Írásvédett | A terv típusának meghatározása. |
| **A fizetési időszakok száma**</br>mshr_payperiod</br>*Egész* | Írásvédett | A fizetési időszakok száma, amely meghatározza, hogy milyen gyakran történik fizetés a juttatásszolgáltató vagy az alkalmazottak számára. Ezt az összeget fogják felhasználni az alkalmazott éves juttatásfizetésének kiszámításához. |
| **Alkalmazotti összeg**</br>mshr_amountemployee</br>*Decimális* | Írásvédett | Az alkalmazotti összeg vagy százalékos arány. |
| **Munkáltatói összeg**</br>mshr_amountemployer</br>*Decimális* | Írásvédett | A munkáltatói összeg vagy százalékos arány. |
| **Elsődleges mező**</br>mshr_primaryfield</br>*Sztring* | Rendszer által előállított | Elsődleges mező. |
| **Dolgozó azonosító értéke** </br>_mshr_fk_worker_id_value</br>*GUID* | Idegen kulcs: az mshr_hcmworkerbaseentity entitás mshr_hcmworkerbaseentityid értéke. | A dolgozó rendszer által generált egyedi azonosítója. |
| **Időszak azonosító értéke**</br> _mshr_fk_period_id_value</br>*GUID* | Idegen kulcs: az mshr_benefitperiodentity entitás mshr_benefitperiodentityid értéke. | Az időszak rendszer által generált egyedi azonosítója. |
| **Terv azonosító értéke**</br> _mshr_fk_plan_id_value</br>*GUID* | Idegen kulcs: az mshr_benefitplanentity entitás mshr_benefitplanentityid értéke. | A terv rendszer által generált egyedi azonosítója. |
| **Tervtípus azonosító értéke**</br> _mshr_fk_plantype_id_value</br>*GUID* | Idegen kulcs: az mshr_benefitplantypeentity entitás mshr_benefitplantypeentityid értéke. | A terv rendszer által generált egyedi azonosítója. |
| **Fedezeti beállítás azonosítójának értéke**</br> _mshr_fk_coverageoption_id_value</br>*GUID* | Idegen kulcs: az mshr_benefitcoverageoptionentity entitás mshr_benefitcoverageoptionentityid értéke. | A terv rendszer által generált egyedi azonosítója. |
| **A bérlistában szereplő dolgozói juttatási terv entitásazonosító értéke**</br> mshr_payrollworkerbenefitplanentityid</br>*GUID* | Írásvédett </br> Rendszer által előállított | A rekord rendszer által generált egyedi azonosítója. |

## <a name="example-query-for-payroll-worker-benefit-plan"></a>Példa lekérdezés a bérlistában szereplő dolgozói juttatási tervhez

**Kérelem**

```http
GET [Organization URI]/api/data/v9.1/mshr_payrollworkerbenefitplanentities?$filter=mshr_personnelnumber eq '000020'
```

**Válasz**

```json
{
    "mshr_personnelnumber": "000020",
    "mshr_legalentityid": "USMF",
    "mshr_periodid": "2021",
    "mshr_planid": "Dental plan",
    "mshr_coverageoptionid": "Emp Only",
    "mshr_deductionstartdatetime": "2021-01-01T06:00:00Z",
    "mshr_deductionenddatetime": "2021-12-31T06:00:00Z",
    "mshr_status": 200000001,
    "mshr_validfrom": "2021-01-01T06:00:00Z",
    "mshr_validto": "2021-12-31T06:00:00Z",
    "mshr_plantypeid": "Dental",
    "mshr_plantypecode": 200000001,
    "mshr_payperiod": 12,
    "mshr_amountemployee": 47,
    "mshr_amountemployer": 57,
    "mshr_primaryfield": "000020 | USMF | 2021 | Dental plan",
    "_mshr_fk_worker_id_value": "000000ae-0000-0000-bfff-004105000000",
    "_mshr_fk_period_id_value": "00000807-0000-0000-ee02-005001000000",
    "_mshr_fk_plan_id_value": "00000c61-0000-0000-0200-005001000000",
    "_mshr_fk_plantype_id_value": "0000057c-0000-0000-0200-005001000000",
    "_mshr_fk_coverageoption_id_value": "00000391-0000-0000-0b00-005001000000",
    "mshr_payrollworkerbenefitplanentityid": "000006c4-0000-0000-bfff-004105000000"
}
```
## <a name="see-also"></a>Lásd még

[Bérlista-integrációs API bemutatása](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
