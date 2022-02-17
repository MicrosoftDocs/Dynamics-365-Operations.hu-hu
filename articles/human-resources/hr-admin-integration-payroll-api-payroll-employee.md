---
title: Bárlista alkalmazottja
description: Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérszámfejtés alkalmazott entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: e853a8a5730d397f253c8ce3a330794594dfd907
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8068484"
---
# <a name="payroll-employee"></a>Bárlista alkalmazottja


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Dynamics 365 Human Resources Bérlistabeosztás alkalmazottentitását írja le.

Fizikai név: mshr_payrollemployeeentity.

### <a name="description"></a>Leírás

Ez az entitás információt nyújt az alkalmazottról. Az entitás használata előtt be kell állítania a [bérlista-integráció paramétereit](hr-admin-integration-payroll-api-parameters.md).

>[!IMPORTANT] 
>A **FirstName**, **MiddleName**, **LastName**, **NameValidFrom** és **NameValidTo** mezők már nem állnak rendelkezésre ezen az entitáson. Ez biztosítja, hogy csak egy hatályos dátummal rendelkező adatforrás álljon az entitás mögött.
>Ezek a mezők a **DirPersonNameHistoricalEntity** oldalon érhetők el, amely a 43. platformfrissítésben lett kiadva. OData-kapcsolat áll fenn a **PayrollEmployeeEntity** és a **DirPersonNameHistoricalEntity** között. 

## <a name="properties"></a>Tulajdonságok

| Tulajdonság</br>**Fizikai név**</br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Jogi személy azonosítója**</br>mshr_legalentityid</br>*Sztring* | Írásvédett | Megadja a jogi személyt (vállalatot). |
| **Személyzeti szám**</br>mshr_personnelnumber</br>*Sztring* | Írásvédett | Az alkalmazott egyedi személyzeti száma. |
| **Foglalkoztatás kezdő dátuma**</br>mshr_employmentstartdate</br>*Dátum és idő eltolása* | Írásvédett | Az alkalmazott foglalkoztatásának kezdő dátuma. |
| **Munkaviszony záró dátuma**</br>mshr_employmentenddate</br>*Dátum és idő eltolása* | Írásvédett |Az alkalmazott foglalkoztatásának vége.  |
| **Születési dátum**</br>mshr_birthdate</br>*Dátum és idő eltolása* | Írásvédett | Az alkalmazott születési dátuma. |
| **Nem**</br>mshr_gender</br>[mshr_hcmpersongender beállításkészlet](hr-admin-integration-payroll-api-gender.md) | Írásvédett | Az alkalmazott neme. |
| **Foglalkoztatási típus**</br>mshr_employmenttype</br>[mshr_hcmemploymenttype beállítása](hr-admin-integration-payroll-api-hcmemploymenttype.md) | Írásvédett | A foglalkoztatás típusa. |
| **Azonosítótípus azonosítója**</br>mshr_identificationtypeid</br>*Sztring* |Írásvédett | Az alkalmazotthoz meghatározott azonosító típus. |
| **Az azonosítószám ehhez**</br>mshr_identificationnumber</br>*Sztring* | Írásvédett |Az alkalmazotthoz meghatározott azonosítószám. |
| **Kifizetésre kész**</br>mshr_readytopay</br>[mshr_noyes beállításkészlet](hr-admin-integration-payroll-api-no-yes.md) | Írásvédett | Azt jelzi, hogy az alkalmazott fizetésre készként van-e megjelölve. |
| **Bérlista alkalmazotti entitás azonosítója**</br>mshr_payrollemployeeentityid</br>*GUID* | Rendszer által előállított | Rendszer által generált globálisan egyedi azonosító (GUID) érték, amely egyedileg azonosítja az alkalmazottat. |

## <a name="relations"></a>Kapcsolatok

|Eszközérték | Kapcsolódó entitás | Navigációs tulajdonság | Gyűjtemény típusa |
| --- | --- | --- | --- |
| _mshr_fk_employment_id_value | mshr_hcmemploymentdetailentity | mshr_FK_Employment_id | mshr_FK_HcmEmploymentDetailEntity_PayrollEmployee |
| _mshr_fk_fixedcompplan_id_value | [mshr_payrollfixedcompensationplanentity](hr-admin-integration-payroll-api-payroll-fixed-compensation-plan.md) | mshr_FK_FixedCompPlan_id | mshr_FK_PayrollFixedCompensationPlanEntity_Employee |
| _mshr_fk_name_id_value | mshr_dirpersonnamehistoricalentity | mshr_FK_Name_id | - |
| _mshr_fk_worker_id_value | mshr_hcmworkerbaseentity | mshr_FK_Worker_id | mshr_FK_HcmWorkerBaseEntity_PayrollEmployee |
| _mshr_fk_workerbankaccount_id_value | mshr_hcmworkerbankaccountentity | mshr_FK_WorkerBankAccount_id | mshr_FK_HcmWorkerBankAccountEntity_PayrollEmployee |
| _mshr_fk_variablecompaward_id_value | [mshr_payrollvariablecompensationawardentity](hr-admin-integration-payroll-api-payroll-variable-compensation-plan.md) | mshr_FK_VariableCompAward_id | mshr_FK_PayrollVariableCompensationAwardEntity_Employee |
| _mshr_fk_address_id_value | [mshr_payrollworkeraddressentity](hr-admin-integration-payroll-api-payroll-worker-address.md) | mshr_FK_Address_id | mshr_FK_PayrollWorkerAddressEntity_Worker |

## <a name="example-query-for-payroll-employee"></a>Példa lekérdezés a bérszámfejtési alkalmazotthoz

**Kérelem**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollemployeeentities?$filter=mshr_personnelnumber eq '000041'
```

**Válasz**

```json
{
    "mshr_legalentityid": "USMF",
    "mshr_personnelnumber": "000041",
    "mshr_employmentstartdate": "2011-04-05T07:00:00Z",
    "mshr_employmentenddate": "2154-12-31T23:59:59Z",
    "mshr_birthdate": "1987-09-12T00:00:00Z",
    "mshr_gender": 200000002,
    "mshr_employmenttype": 200000000,
    "mshr_identificationtypeid": "SSN",
    "mshr_identificationnumber": "888-99-9342",
    "mshr_readytopay": 200000000,
    "mshr_dataareaid": "USMF",
    "mshr_primaryfield": "000041 | USMF | 4/5/2011 07:00:00 am",
    "_mshr_fk_employment_id_value": "00000d4e-0000-0000-0600-014105000000",
    "_mshr_fk_fixedcompplan_id_value": "00000598-0000-0000-4cd0-fda002000000",
    "_mshr_fk_name_id_value": "00000832-0000-0000-d700-014105000000",
    "_mshr_fk_worker_id_value": "000000af-0000-0000-d5ff-004105000000",
    "_mshr_fk_workerbankaccount_id_value": "000006f2-0000-0000-b7ff-004105000000",
    "mshr_payrollemployeeentityid": "00000666-0000-0000-d5ff-004105000000",
    "_mshr_fk_address_id_value": null,
    "_mshr_fk_variablecompaward_id_value": null,
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Lásd még

[Bérlista-integrációs API bemutatása](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
