---
title: Fix kompenzációs konstrukció bérlistája
description: Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérlista fix kompenzációs konstrukció entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.
author: jcart
ms.date: 08/25/2021
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
ms.openlocfilehash: dcb253fabbb183003048119c7a627bf0ab960050
ms.sourcegitcommit: 4d11061f5de0ddba1f968bd5c3fd694a8b104ccc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/26/2021
ms.locfileid: "7429229"
---
# <a name="payroll-fixed-compensation-plan"></a>Fix kompenzációs konstrukció bérlistája

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Dynamics 365 Human Resources bérszámfejtési fix kompenzációs konstrukció entitását ismerteti.

### <a name="description"></a>Leírás

Ez az entitás biztosítja az alkalmazott adott beosztásához hozzárendelt fix kompenzációs konstrukciót.

Fizikai név: mshr_payrollfixedcompensationplanentity.

## <a name="properties"></a>Tulajdonságok

| Tulajdonság</br>**Fizikai név**</br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Tervazonosító**</br>mshr_planid</br>*Sztring* | Írásvédett | A kompenzációs konstrukciót adja meg.  |
| **Személyzeti szám**</br>mshr_personnelnumber</br>*Sztring* | Írásvédett | Az alkalmazott egyedi személyzeti száma. |
| **Fizetési díjalap**</br>mshr_payrate</br>*Decimális* | Írásvédett | A fix kompenzációs konstrukcióban meghatározott fizetési díj. |
| **Beosztásazonosító**</br>mshr_positionid</br>*Sztring* | Írásvédett | Az alkalmazotthoz és a fix kompenzációs konstrukcióba való belépéshez társított pozícióazonosító. |
| **Érvényesség kezdete**</br>mshr_validfrom</br>*Dátum és idő eltolása* |  Írásvédett | Az a dátum, amelytől az alkalmazott fix kompenzációja érvényes.  |
| **Érvényesség vége:**</br>mshr_validto</br>*Dátum és idő eltolása* | Írásvédett | Az a dátum, amelyig az alkalmazott fix kompenzációja érvényes. |
| **Fizetési gyakoriság**</br>mshr_payfrequency</br>*Sztring* | Írásvédett | Az alkalmazott fizetésének gyakorisága.  |
| **Pénznem**</br>mshr_currency</br>*Sztring* | Írásvédett | A fix kompenzációs konstrukcióhoz meghatározott pénznem. |
| **Fix kompenzációs konstrukció bérlistája entitás**</br>mshr_payrollfixedcompensationplanentityid</br>*GUID* | Rendszer által előállított | A kompenzációs konstrukció azonosítására szolgáló, rendszer által generált GUID-értéke. |

## <a name="relations"></a>Kapcsolatok

|Eszközérték | Kapcsolódó entitás | Navigációs tulajdonság | Gyűjtemény típusa |
| --- | --- | --- | --- |
| _mshr_fk_employee_id_value | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | mshr_FK_Employee_id | mshr_FK_PayrollEmployeeEntity_FixedCompPlan |
| _mshr_fk_job_id_value | [mshr_payrollpositionjobentity](hr-admin-integration-payroll-api-payroll-position-job.md) | mshr_FK_Job_id | mshr_FK_PayrollPositionJobEntity_FixedCompPlan |
| _mshr_fk_payrollposition_id_value | [mshr_payrollpositionentity](hr-admin-integration-payroll-api-payroll-position.md) | mshr_FK_PayrollPosition_id | mshr_FK_PayrollPositionEntity_FixedCompPlan |
| _mshr_fk_plan_id_value | mshr_hcmcompfixedplantableentity | mshr_FK_Plan_id | - |
| _mshr_fk_variablecompaward_id_value | [mshr_payrollvariablecompensationawardentity](hr-admin-integration-payroll-api-payroll-variable-compensation-plan.md) | mshr_FK_VariableCompAward_id | mshr_FK_PayrollVariableCompensationAwardEntity_FixedComp |

## <a name="example-query"></a>Példa lekérdezésre

**Kérelem**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollfixedcompensationplanentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

**Válasz**

```json
{
    "mshr_planid": "GradeC",
    "mshr_personnelnumber": "000041",
    "mshr_payrate": 75200,
    "mshr_positionid": "000276",
    "mshr_validfrom": "2011-04-05T00:00:00Z",
    "mshr_validto": "2154-12-31T00:00:00Z",
    "mshr_payfrequency": "Annual",
    "mshr_currency": "USD",
    "_mshr_fk_employee_id_value": "00000d3c-0000-0000-d5ff-004105000000",
    "_mshr_fk_plan_id_value": "0000070c-0000-0000-b328-fef003000000",
    "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
    "mshr_payrollfixedcompensationplanentityid": "0000029f-0000-0000-d5ff-004105000000",
    "_mshr_fk_payroll_id_value": null
}
```

## <a name="see-also"></a>Lásd még

[Bérlista-integrációs API bemutatása](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
