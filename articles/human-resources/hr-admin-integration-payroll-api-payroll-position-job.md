---
title: Bérlista szerinti beosztás feladata
description: Ez a cikk részletes adatokat és példa-lekérdezést nyújt a bérlistapozíciós feladat entitáshoz a következő helyen:Dynamics 365 Human Resources
author: jcart
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fa347f4b99adc7c29d69daf62ad2bbfc14726a19
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8864083"
---
# <a name="payroll-position-job"></a>Bérlista szerinti beosztás feladata


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a bérlistapozíció feladatentitását írja le Dynamics 365 Human Resources.

### <a name="description"></a>Leírás

Ez az entitás kapcsolatot biztosít egy adott fix kompenzációs konstrukcióhoz tartozó beosztás és feladat között.

Fizikai név: mshr_payrollpositionjobentity.

## <a name="properties"></a>Tulajdonságok

| Tulajdonság</br>**Fizikai név**</br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Beosztásazonosító**</br>mshr_positionid</br>*Sztring* | Írásvédett | A pozíció azonosítója. |
| **Érvényesség kezdete**</br>mshr_validto</br>*Dátum és idő eltolása* | Írásvédett | A dátum, amelytől a beosztás és a feladat kapcsolata érvényes. |
| **Érvényesség vége:**</br>mshr_validto</br>*Dátum és idő eltolása* | Írásvédett | A dátum, ameddig a pozíció és a beosztás kapcsolata érvényes. |
| **Beosztásazonosító**</br>mshr_jobid</br>*Sztring* | Írásvédett | A feladat azonosítója. |
| **Elsődleges mező**</br>mshr_primaryfield</br>*Sztring* | Rendszer által előállított | Az elsődleges mező. |
| **Bérlista szerinti beosztás feladata azonosítója**</br>mshr_payrollpositionjobentityid</br>*Guid* | Rendszer által előállított. | Rendszer által generált globálisan egyedi azonosító (GUID) érték, amely egyedileg azonosítja a munkát. |

## <a name="relations"></a>Kapcsolatok

| Eszközérték | Kapcsolódó entitás | Navigációs tulajdonság | Gyűjtemény típusa |
| --- | --- | --- | --- |
| _mshr_fk_fixedcompplan_id_value | mshr_payrollfixedcompensationplanentity | mshr_FK_FixedCompPlan_id | mshr_FK_PayrollFixedCompensationPlanEntity_Job |
| _mshr_fk_jobdetail_id_value | mshr_hcmjobdetailentity | mshr_FK_JobDetail_id | Nem alkalmazható |
| _mshr_fk_payroll_id_value | mshr_payrollpositionentity | mshr_FK_Payroll_id | mshr_FK_PayrollPositionEntity_Job |

## <a name="example-query"></a>Példa lekérdezésre

**Kérelem**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionjobentities?$filter=mshr_positionid eq '000276'
```

**Válasz**

```json
{
    "mshr_positionid": "000276",
    "mshr_validfrom": "2016-07-06T18:11:33Z",
    "mshr_validto": "2154-12-31T23:59:59Z",
    "mshr_jobid": "Accountant",
    "mshr_primaryfield": "000276 | Accountant | 7/6/2016 06:11:33 pm",
    "_mshr_fk_jobdetail_id_value": "00000b8d-0000-0000-b0ff-004105000000",
    "_mshr_fk_fixedcompplan_id_value": "0000058a-0000-0000-d5ff-004105000000",
    "_mshr_fk_payroll_id_value": "00000427-0000-0000-df00-014105000000",
    "mshr_payrollpositionjobentityid": "00000906-0000-0000-df00-014105000000"
}
```

## <a name="see-also"></a>Lásd még

[Bérlista-integrációs API bemutatása](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
